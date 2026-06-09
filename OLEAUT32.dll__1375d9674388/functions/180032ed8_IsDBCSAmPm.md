# IsDBCSAmPm

- ea: `0x180032ed8`
- end: `0x180032ff0`
- name: `IsDBCSAmPm`
- size: `280`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180046790`
- `0x180046df4`

## callees

- `0x180032ed8`
- `0x180032ff8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032f5f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032fc1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032f5f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032fc1`

## pseudocode

```c
__int64 __fastcall IsDBCSAmPm(PCNZWCH lpString1, unsigned int *a2, __int64 a3)
{
  __int64 v3; // rdi
  unsigned int v7; // eax
  unsigned int v8; // ebx

  v3 = -1;
  do
    ++v3;
  while ( lpString1[v3] );
  if ( !*(_DWORD *)(a3 + 116) )
  {
    v7 = IsPrefix(lpString1, v3, (const unsigned __int16 *)(a3 + 1120), (const struct tagDATEINFO *)a3);
    if ( v7 )
      goto LABEL_14;
  }
  v7 = IsPrefix(lpString1, v3, *(const unsigned __int16 **)(a3 + 1104), (const struct tagDATEINFO *)a3);
  if ( v7 )
    goto LABEL_14;
  v8 = 2;
  if ( (unsigned int)v3 >= 2 && CompareStringW(*(_DWORD *)(a3 + 16), 1u, lpString1, 2, L"am", 2) == 2 )
  {
    v7 = 2;
LABEL_14:
    v8 = 1;
    goto LABEL_15;
  }
  if ( *(_DWORD *)(a3 + 116)
    || (v7 = IsPrefix(lpString1, v3, (const unsigned __int16 *)(a3 + 1144), (const struct tagDATEINFO *)a3)) == 0 )
  {
    v7 = IsPrefix(lpString1, v3, *(const unsigned __int16 **)(a3 + 1112), (const struct tagDATEINFO *)a3);
    if ( !v7 )
    {
      if ( (unsigned int)v3 < 2 || CompareStringW(*(_DWORD *)(a3 + 16), 1u, lpString1, 2, L"pm", 2) != 2 )
        return 0;
      v7 = 2;
    }
  }
LABEL_15:
  *a2 = v7;
  return v8;
}

```

## disassembly

```asm
0x180032ed8  push    rbx
0x180032eda  push    rbp
0x180032edb  push    rsi
0x180032edc  push    rdi
0x180032edd  push    r12
0x180032edf  push    r14
0x180032ee1  push    r15
0x180032ee3  sub     rsp, 30h
0x180032ee7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180032eeb  mov     rsi, r8
0x180032eee  xor     r12d, r12d
0x180032ef1  mov     r15, rdx
0x180032ef4  mov     rbp, rcx
0x180032ef7  inc     rdi
0x180032efa  cmp     [rcx+rdi*2], r12w
0x180032eff  jnz     short loc_180032EF7
0x180032f01  cmp     [r8+74h], r12d
0x180032f05  jnz     short loc_180032F20
0x180032f07  add     r8, 460h; unsigned __int16 *
0x180032f0e  mov     r9, rsi; struct tagDATEINFO *
0x180032f11  mov     edx, edi; unsigned int
0x180032f13  call    ?IsPrefix@@YAIPEBGI0PEBUtagDATEINFO@@@Z; IsPrefix(ushort const *,uint,ushort const *,tagDATEINFO const *)
0x180032f18  test    eax, eax
0x180032f1a  jnz     loc_180032FCF
0x180032f20  mov     r8, [rsi+450h]; unsigned __int16 *
0x180032f27  mov     r9, rsi; struct tagDATEINFO *
0x180032f2a  mov     edx, edi; unsigned int
0x180032f2c  mov     rcx, rbp; lpString1
0x180032f2f  call    ?IsPrefix@@YAIPEBGI0PEBUtagDATEINFO@@@Z; IsPrefix(ushort const *,uint,ushort const *,tagDATEINFO const *)
0x180032f34  test    eax, eax
0x180032f36  jnz     loc_180032FCF
0x180032f3c  lea     ebx, [rax+2]
0x180032f3f  cmp     edi, ebx
0x180032f41  jb      short loc_180032F69
0x180032f43  mov     ecx, [rsi+10h]; Locale
0x180032f46  lea     rax, aAm; "am"
0x180032f4d  mov     [rsp+68h+cchCount2], ebx; cchCount2
0x180032f51  lea     edx, [rbx-1]; dwCmpFlags
0x180032f54  mov     r9d, ebx; cchCount1
0x180032f57  mov     [rsp+68h+lpString2], rax; lpString2
0x180032f5c  mov     r8, rbp; lpString1
0x180032f5f  call    cs:__imp_CompareStringW
0x180032f65  cmp     eax, ebx
0x180032f67  jz      short loc_180032FE8
0x180032f69  cmp     [rsi+74h], r12d
0x180032f6d  jnz     short loc_180032F87
0x180032f6f  lea     r8, [rsi+478h]; unsigned __int16 *
0x180032f76  mov     r9, rsi; struct tagDATEINFO *
0x180032f79  mov     edx, edi; unsigned int
0x180032f7b  mov     rcx, rbp; lpString1
0x180032f7e  call    ?IsPrefix@@YAIPEBGI0PEBUtagDATEINFO@@@Z; IsPrefix(ushort const *,uint,ushort const *,tagDATEINFO const *)
0x180032f83  test    eax, eax
0x180032f85  jnz     short loc_180032FD4
0x180032f87  mov     r8, [rsi+458h]; unsigned __int16 *
0x180032f8e  mov     r9, rsi; struct tagDATEINFO *
0x180032f91  mov     edx, edi; unsigned int
0x180032f93  mov     rcx, rbp; lpString1
0x180032f96  call    ?IsPrefix@@YAIPEBGI0PEBUtagDATEINFO@@@Z; IsPrefix(ushort const *,uint,ushort const *,tagDATEINFO const *)
0x180032f9b  test    eax, eax
0x180032f9d  jnz     short loc_180032FD4
0x180032f9f  cmp     edi, ebx
0x180032fa1  jb      short loc_180032FCB
0x180032fa3  mov     ecx, [rsi+10h]; Locale
0x180032fa6  lea     rax, aPm; "pm"
0x180032fad  mov     [rsp+68h+cchCount2], ebx; cchCount2
0x180032fb1  mov     r9d, ebx; cchCount1
0x180032fb4  mov     r8, rbp; lpString1
0x180032fb7  mov     [rsp+68h+lpString2], rax; lpString2
0x180032fbc  mov     edx, 1; dwCmpFlags
0x180032fc1  call    cs:__imp_CompareStringW
0x180032fc7  cmp     eax, ebx
0x180032fc9  jz      short loc_180032FEC
0x180032fcb  xor     eax, eax
0x180032fcd  jmp     short loc_180032FD9
0x180032fcf  mov     ebx, 1
0x180032fd4  mov     [r15], eax
0x180032fd7  mov     eax, ebx
0x180032fd9  add     rsp, 30h
0x180032fdd  pop     r15
0x180032fdf  pop     r14
0x180032fe1  pop     r12
0x180032fe3  pop     rdi
0x180032fe4  pop     rsi
0x180032fe5  pop     rbp
0x180032fe6  pop     rbx
0x180032fe7  retn
0x180032fe8  mov     eax, ebx
0x180032fea  jmp     short loc_180032FCF
0x180032fec  mov     eax, ebx
0x180032fee  jmp     short loc_180032FD4
```
