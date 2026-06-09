# PiiSafeShellitemParsingNameProperties::CalculatePathDepth(ushort const *,bool)

- ea: `0x180072350`
- end: `0x1800723a8`
- name: `?CalculatePathDepth@PiiSafeShellitemParsingNameProperties@@AEAAEPEBG_N@Z`
- size: `88`
- prototype: `unsigned __int8(PiiSafeShellitemParsingNameProperties *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180072f50`
- `0x180075bec`

## callees

- `0x180072350`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindNextComponentW` at `0x18007237d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindNextComponentW` at `0x18007237d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x180072365`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x180072365`

## pseudocode

```c
char __fastcall PiiSafeShellitemParsingNameProperties::CalculatePathDepth(
        PiiSafeShellitemParsingNameProperties *this,
        const unsigned __int16 *a2,
        char a3)
{
  LPWSTR NextComponentW; // rax
  char v5; // bl

  NextComponentW = PathSkipRootW(a2);
  v5 = 0;
  if ( NextComponentW )
  {
    do
    {
      if ( !*NextComponentW )
        break;
      NextComponentW = PathFindNextComponentW(NextComponentW);
      ++v5;
    }
    while ( NextComponentW );
    if ( v5 && a3 )
      --v5;
  }
  return v5;
}

```

## disassembly

```asm
0x180072350  mov     [rsp+arg_0], rbx
0x180072355  mov     [rsp+arg_8], rsi
0x18007235a  push    rdi
0x18007235b  sub     rsp, 20h
0x18007235f  mov     rcx, rdx; pszPath
0x180072362  mov     dil, r8b
0x180072365  call    cs:__imp_PathSkipRootW
0x18007236b  xor     esi, esi
0x18007236d  mov     bl, sil
0x180072370  test    rax, rax
0x180072373  jz      short loc_180072396
0x180072375  cmp     [rax], si
0x180072378  jz      short loc_18007238A
0x18007237a  mov     rcx, rax; pszPath
0x18007237d  call    cs:__imp_PathFindNextComponentW
0x180072383  inc     bl
0x180072385  test    rax, rax
0x180072388  jnz     short loc_180072375
0x18007238a  test    bl, bl
0x18007238c  jz      short loc_180072396
0x18007238e  test    dil, dil
0x180072391  jz      short loc_180072396
0x180072393  add     bl, 0FFh
0x180072396  mov     rsi, [rsp+28h+arg_8]
0x18007239b  mov     al, bl
0x18007239d  mov     rbx, [rsp+28h+arg_0]
0x1800723a2  add     rsp, 20h
0x1800723a6  pop     rdi
0x1800723a7  retn
```
