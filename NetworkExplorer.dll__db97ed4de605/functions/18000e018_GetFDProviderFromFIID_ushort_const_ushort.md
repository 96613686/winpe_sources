# GetFDProviderFromFIID(ushort const *,ushort * *)

- ea: `0x18000e018`
- end: `0x18000e11a`
- name: `?GetFDProviderFromFIID@@YAJPEBGPEAPEAG@Z`
- size: `258`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006030`

## callees

- `0x180005d00`
- `0x18000e018`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e0a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e0a6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e0e9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e0e9`

## pseudocode

```c
__int64 __fastcall GetFDProviderFromFIID(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 v2; // ax
  const unsigned __int16 *v3; // rbx
  unsigned int v5; // ebp
  unsigned __int16 v6; // ax
  const unsigned __int16 *v7; // rdi
  signed __int64 v8; // rdi
  unsigned __int16 *v9; // rax

  v2 = *a1;
  v3 = a1;
  *a2 = 0;
  v5 = -2147024809;
  while ( v2 && v2 != 46 )
    v2 = *++v3;
  if ( *v3 )
  {
    do
      ++v3;
    while ( *v3 && *v3 != 46 );
    v6 = *v3;
    if ( *v3 )
    {
      v7 = v3;
      do
      {
        if ( v6 == 47 )
          break;
        v6 = *++v7;
      }
      while ( *v7 );
      if ( *v7 )
      {
        v8 = v7 - v3;
        if ( v8 > 1 )
        {
          v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
          *a2 = v9;
          if ( v9 )
          {
            v5 = 0;
            StringCchCopyNW(v9, v8, v3 + 1, v8 - 1);
            if ( CompareStringW(0x7Fu, 1u, *a2, -1, L"NetBIOS", -1) == 2 )
              StringCchCopyNW(*a2, v8, L"NetBIOS", v8 - 1);
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000e018  push    rbx
0x18000e01a  push    rbp
0x18000e01b  push    rsi
0x18000e01c  push    rdi
0x18000e01d  push    r14
0x18000e01f  sub     rsp, 30h
0x18000e023  movzx   eax, word ptr [rcx]
0x18000e026  xor     r14d, r14d
0x18000e029  mov     rbx, rcx
0x18000e02c  mov     [rdx], r14
0x18000e02f  mov     rsi, rdx
0x18000e032  mov     ebp, 80070057h
0x18000e037  lea     ecx, [r14+2Eh]
0x18000e03b  jmp     short loc_18000E049
0x18000e03d  cmp     cx, ax
0x18000e040  jz      short loc_18000E04E
0x18000e042  add     rbx, 2
0x18000e046  movzx   eax, word ptr [rbx]
0x18000e049  test    ax, ax
0x18000e04c  jnz     short loc_18000E03D
0x18000e04e  cmp     [rbx], r14w
0x18000e052  jz      loc_18000E10D
0x18000e058  jmp     short loc_18000E05F
0x18000e05a  cmp     cx, ax
0x18000e05d  jz      short loc_18000E06B
0x18000e05f  add     rbx, 2
0x18000e063  movzx   eax, word ptr [rbx]
0x18000e066  test    ax, ax
0x18000e069  jnz     short loc_18000E05A
0x18000e06b  movzx   eax, word ptr [rbx]
0x18000e06e  test    ax, ax
0x18000e071  jz      loc_18000E10D
0x18000e077  mov     rdi, rbx
0x18000e07a  mov     ecx, 2Fh ; '/'
0x18000e07f  cmp     cx, ax
0x18000e082  jz      short loc_18000E090
0x18000e084  add     rdi, 2
0x18000e088  movzx   eax, word ptr [rdi]
0x18000e08b  test    ax, ax
0x18000e08e  jnz     short loc_18000E07A
0x18000e090  cmp     [rdi], r14w
0x18000e094  jz      short loc_18000E10D
0x18000e096  sub     rdi, rbx
0x18000e099  sar     rdi, 1
0x18000e09c  cmp     rdi, 1
0x18000e0a0  jle     short loc_18000E10D
0x18000e0a2  lea     rcx, [rdi+rdi]; cb
0x18000e0a6  call    cs:__imp_CoTaskMemAlloc
0x18000e0ac  mov     [rsi], rax
0x18000e0af  test    rax, rax
0x18000e0b2  jz      short loc_18000E108
0x18000e0b4  lea     r8, [rbx+2]; unsigned __int16 *
0x18000e0b8  mov     rdx, rdi; unsigned __int64
0x18000e0bb  lea     r9, [rdi-1]; unsigned __int64
0x18000e0bf  mov     rcx, rax; unsigned __int16 *
0x18000e0c2  mov     ebp, r14d
0x18000e0c5  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000e0ca  mov     r8, [rsi]; lpString1
0x18000e0cd  lea     rbx, String2; "NetBIOS"
0x18000e0d4  or      r9d, 0FFFFFFFFh; cchCount1
0x18000e0d8  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x18000e0dd  mov     [rsp+58h+lpString2], rbx; lpString2
0x18000e0e2  lea     edx, [r9+2]; dwCmpFlags
0x18000e0e6  lea     ecx, [rdx+7Eh]; Locale
0x18000e0e9  call    cs:__imp_CompareStringW
0x18000e0ef  cmp     eax, 2
0x18000e0f2  jnz     short loc_18000E10D
0x18000e0f4  mov     rcx, [rsi]; unsigned __int16 *
0x18000e0f7  lea     r9, [rdi-1]; unsigned __int64
0x18000e0fb  mov     r8, rbx; unsigned __int16 *
0x18000e0fe  mov     rdx, rdi; unsigned __int64
0x18000e101  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000e106  jmp     short loc_18000E10D
0x18000e108  mov     ebp, 8007000Eh
0x18000e10d  mov     eax, ebp
0x18000e10f  add     rsp, 30h
0x18000e113  pop     r14
0x18000e115  pop     rdi
0x18000e116  pop     rsi
0x18000e117  pop     rbp
0x18000e118  pop     rbx
0x18000e119  retn
```
