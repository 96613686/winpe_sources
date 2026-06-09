# SiIsValidDiskDevice

- ea: `0x140020ae8`
- end: `0x140020b9e`
- name: `SiIsValidDiskDevice`
- size: `182`
- prototype: `char __fastcall(wchar_t *String1, wchar_t *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140020ba4`

## callees

- `0x140001864`
- `0x140020ae8`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140020b32`
- `msvcrt!_wcsnicmp` at `0x140020b32`

## string_xrefs

- `0x140020b0f`: `SymbolicLink`
- `0x140020afa`: `Directory`

## pseudocode

```c
char __fastcall SiIsValidDiskDevice(wchar_t *String1, wchar_t *a2, int *a3)
{
  wchar_t *v6; // r8
  wchar_t v7; // cx
  int v8; // edx
  __int16 v10; // r9

  if ( wcsicmp_0(a2, L"Directory") && wcsicmp_0(a2, L"SymbolicLink") )
    return 0;
  if ( _wcsnicmp(String1, L"Harddisk", 8u) )
    return 0;
  v6 = String1 + 8;
  v7 = String1[8];
  if ( !v7 )
    return 0;
  v8 = 0;
  if ( v7 != 48 )
  {
    v10 = 0;
    while ( (unsigned __int16)(v7 - 48) <= 9u )
    {
      if ( (unsigned __int16)++v10 > 0xAu )
        break;
      ++v6;
      v8 = v7 + 2 * (5 * v8 - 24);
      v7 = *v6;
      if ( !*v6 )
        goto LABEL_12;
    }
    return 0;
  }
  if ( String1[9] )
    return 0;
LABEL_12:
  if ( a3 )
    *a3 = v8;
  return 1;
}

```

## disassembly

```asm
0x140020ae8  push    rbx
0x140020aea  push    rbp
0x140020aeb  push    rsi
0x140020aec  push    rdi
0x140020aed  sub     rsp, 28h
0x140020af1  mov     rsi, rdx
0x140020af4  mov     rbx, rcx
0x140020af7  mov     rcx, rsi; String1
0x140020afa  lea     rdx, aDirectory; "Directory"
0x140020b01  mov     rdi, r8
0x140020b04  call    _wcsicmp_0
0x140020b09  xor     ebp, ebp
0x140020b0b  test    eax, eax
0x140020b0d  jz      short loc_140020B22
0x140020b0f  lea     rdx, aSymboliclink; "SymbolicLink"
0x140020b16  mov     rcx, rsi; String1
0x140020b19  call    _wcsicmp_0
0x140020b1e  test    eax, eax
0x140020b20  jnz     short loc_140020B58
0x140020b22  mov     r8d, 8; MaxCount
0x140020b28  lea     rdx, aHarddisk_0; "Harddisk"
0x140020b2f  mov     rcx, rbx; String1
0x140020b32  call    cs:__imp__wcsnicmp
0x140020b38  test    eax, eax
0x140020b3a  jnz     short loc_140020B58
0x140020b3c  lea     r8, [rbx+10h]
0x140020b40  movzx   ecx, word ptr [r8]
0x140020b44  test    cx, cx
0x140020b47  jz      short loc_140020B58
0x140020b49  mov     edx, ebp
0x140020b4b  cmp     cx, 30h ; '0'
0x140020b4f  jnz     short loc_140020B63
0x140020b51  cmp     [r8+2], bp
0x140020b56  jz      short loc_140020B93
0x140020b58  xor     al, al
0x140020b5a  add     rsp, 28h
0x140020b5e  pop     rdi
0x140020b5f  pop     rsi
0x140020b60  pop     rbp
0x140020b61  pop     rbx
0x140020b62  retn
0x140020b63  mov     r9d, ebp
0x140020b66  lea     eax, [rcx-30h]
0x140020b69  cmp     ax, 9
0x140020b6d  ja      short loc_140020B58
0x140020b6f  inc     r9w
0x140020b73  cmp     r9w, 0Ah
0x140020b78  ja      short loc_140020B58
0x140020b7a  movzx   ecx, cx
0x140020b7d  lea     edx, [rdx+rdx*4]
0x140020b80  add     r8, 2
0x140020b84  lea     edx, [rdx-18h]
0x140020b87  lea     edx, [rcx+rdx*2]
0x140020b8a  movzx   ecx, word ptr [r8]
0x140020b8e  test    cx, cx
0x140020b91  jnz     short loc_140020B66
0x140020b93  test    rdi, rdi
0x140020b96  jz      short loc_140020B9A
0x140020b98  mov     [rdi], edx
0x140020b9a  mov     al, 1
0x140020b9c  jmp     short loc_140020B5A
```
