# IsExtensionPDF(ushort const *)

- ea: `0x18001ce74`
- end: `0x18001cef7`
- name: `?IsExtensionPDF@@YA_NPEBG@Z`
- size: `131`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c950`
- `0x18001c9b0`
- `0x18001e0b8`

## callees

- `0x18001ce74`
- `0x18001e9a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001cea5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001cea5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001ce90`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001ce90`

## pseudocode

```c
char __fastcall IsExtensionPDF(const unsigned __int16 *a1)
{
  char v2; // bl
  LPWSTR ExtensionW; // rax
  unsigned __int64 v4; // rax

  v2 = 0;
  if ( a1 )
  {
    ExtensionW = PathFindExtensionW(a1);
    if ( ExtensionW )
    {
      if ( (unsigned int)_o__wcsicmp(ExtensionW, L".pdf") )
      {
        v4 = -1;
        do
          ++v4;
        while ( a1[v4] );
        if ( v4 >= 0x15 )
          return wmemcmp(&a1[v4 - 20], L".pdf:Zone.Identifier", 0x14u) == 0;
      }
      else
      {
        return 1;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001ce74  mov     [rsp+arg_0], rbx
0x18001ce79  mov     [rsp+arg_8], rsi
0x18001ce7e  push    rdi
0x18001ce7f  sub     rsp, 20h
0x18001ce83  xor     esi, esi
0x18001ce85  mov     rdi, rcx
0x18001ce88  mov     bl, sil
0x18001ce8b  test    rcx, rcx
0x18001ce8e  jz      short loc_18001CEE5
0x18001ce90  call    cs:__imp_PathFindExtensionW
0x18001ce96  test    rax, rax
0x18001ce99  jz      short loc_18001CEE5
0x18001ce9b  lea     rdx, aPdf; ".pdf"
0x18001cea2  mov     rcx, rax
0x18001cea5  call    cs:__imp__o__wcsicmp
0x18001ceab  test    eax, eax
0x18001cead  jnz     short loc_18001CEB3
0x18001ceaf  mov     bl, 1
0x18001ceb1  jmp     short loc_18001CEE5
0x18001ceb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ceb7  inc     rax
0x18001ceba  cmp     [rdi+rax*2], si
0x18001cebe  jnz     short loc_18001CEB7
0x18001cec0  cmp     rax, 15h
0x18001cec4  jb      short loc_18001CEE5
0x18001cec6  add     rax, 0FFFFFFFFFFFFFFECh
0x18001ceca  lea     rdx, aPdfZoneIdentif; ".pdf:Zone.Identifier"
0x18001ced1  mov     r8d, 14h; N
0x18001ced7  lea     rcx, [rdi+rax*2]; S1
0x18001cedb  call    wmemcmp
0x18001cee0  test    eax, eax
0x18001cee2  setz    bl
0x18001cee5  mov     rsi, [rsp+28h+arg_8]
0x18001ceea  mov     al, bl
0x18001ceec  mov     rbx, [rsp+28h+arg_0]
0x18001cef1  add     rsp, 20h
0x18001cef5  pop     rdi
0x18001cef6  retn
```
