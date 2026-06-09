# GetNextToken

- ea: `0x1800141f4`
- end: `0x180014252`
- name: `GetNextToken`
- size: `94`
- prototype: `const WCHAR *__fastcall(const WCHAR **, WCHAR)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012f48`
- `0x180013280`

## callees

- `0x1800141f4`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x180014215`
- `SHLWAPI!StrChrW` at `0x180014215`

## pseudocode

```c
const WCHAR *__fastcall GetNextToken(const WCHAR **a1, WCHAR a2)
{
  const WCHAR *v3; // rcx
  PWSTR v4; // rdx
  const WCHAR *result; // rax
  const WCHAR *v6; // rcx
  __int64 v7; // rcx

  if ( !a1 )
    return 0;
  v3 = *a1;
  if ( !v3 || !*v3 )
    return 0;
  v4 = StrChrW(v3, a2);
  result = *a1;
  if ( v4 )
  {
    *v4 = 0;
    v6 = v4 + 1;
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( result[v7] );
    v6 = &result[v7];
  }
  *a1 = v6;
  return result;
}

```

## disassembly

```asm
0x1800141f4  mov     [rsp+arg_0], rbx
0x1800141f9  push    rdi
0x1800141fa  sub     rsp, 20h
0x1800141fe  xor     edi, edi
0x180014200  mov     rbx, rcx
0x180014203  test    rcx, rcx
0x180014206  jz      short loc_180014245
0x180014208  mov     rcx, [rcx]; pszStart
0x18001420b  test    rcx, rcx
0x18001420e  jz      short loc_180014245
0x180014210  cmp     [rcx], di
0x180014213  jz      short loc_180014245
0x180014215  call    cs:__imp_StrChrW
0x18001421b  mov     rdx, rax
0x18001421e  mov     rax, [rbx]
0x180014221  test    rdx, rdx
0x180014224  jz      short loc_18001422F
0x180014226  mov     [rdx], di
0x180014229  lea     rcx, [rdx+2]
0x18001422d  jmp     short loc_180014240
0x18001422f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180014233  inc     rcx
0x180014236  cmp     [rax+rcx*2], di
0x18001423a  jnz     short loc_180014233
0x18001423c  lea     rcx, [rax+rcx*2]
0x180014240  mov     [rbx], rcx
0x180014243  jmp     short loc_180014247
0x180014245  xor     eax, eax
0x180014247  mov     rbx, [rsp+28h+arg_0]
0x18001424c  add     rsp, 20h
0x180014250  pop     rdi
0x180014251  retn
```
