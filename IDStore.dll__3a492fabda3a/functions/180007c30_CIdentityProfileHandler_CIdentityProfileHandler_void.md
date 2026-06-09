# CIdentityProfileHandler::CIdentityProfileHandler(void)

- ea: `0x180007c30`
- end: `0x180007e89`
- name: `??0CIdentityProfileHandler@@QEAA@XZ`
- size: `601`
- prototype: `CIdentityProfileHandler *__fastcall(CIdentityProfileHandler *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007b20`
- `0x180010e78`

## callees

- `0x180007c30`
- `0x18000a680`
- `0x18000fb96`
- `0x1800144b4`
- `0x180019750`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007df3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007df3`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180007e11`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180007e1f`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180007e11`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180007e1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007de0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007de0`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180007c9f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180007c9f`

## string_xrefs

- `0x180007c93`: `IDStoreCache`
- `0x180007c68`: `Software\Microsoft\IdentityStore\Cache`
- `0x180007e34`: `Software\Microsoft\IdentityStore\Cache`

## pseudocode

```c
CIdentityProfileHandler *__fastcall CIdentityProfileHandler::CIdentityProfileHandler(CIdentityProfileHandler *this)
{
  __int64 v2; // rbx
  unsigned int v3; // r14d
  unsigned int v4; // ecx
  unsigned int v5; // esi
  void *v6; // rbp
  unsigned int v7; // r14d
  HANDLE v8; // rax
  LPVOID v9; // rax
  int v10; // ebp
  size_t v11; // rbx
  __int64 v12; // rcx
  void *v14; // rsi
  HANDLE ProcessHeap; // rax
  LPVOID v16; // rax
  _WORD Src[264]; // [rsp+30h] [rbp-248h] BYREF

  *((_DWORD *)this + 2) = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_BYTE *)this + 56) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 22) = 0;
  if ( (unsigned int)GetPersistedRegistryLocationW(
                       L"IDStoreCache",
                       L"Software\\Microsoft\\IdentityStore\\Cache",
                       Src,
                       520,
                       0) )
  {
    v10 = CDynamicString::Assign(
            (CIdentityProfileHandler *)((char *)this + 64),
            L"Software\\Microsoft\\IdentityStore\\Cache");
    goto LABEL_12;
  }
  v2 = -1;
  do
    ++v2;
  while ( Src[v2] );
  v3 = *((_DWORD *)this + 19);
  if ( !v3 )
  {
    v4 = *((_DWORD *)this + 22);
    if ( v4 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      v3 = v4 + (v4 >> 1) + 32;
      ProcessHeap = GetProcessHeap();
      if ( v14 )
        v16 = HeapReAlloc(ProcessHeap, 0, v14, 2 * v3);
      else
        v16 = HeapAlloc(ProcessHeap, 0, 2 * v3);
      if ( !v16 )
        goto LABEL_20;
      *((_QWORD *)this + 8) = v16;
      *((_DWORD *)this + 19) = v3;
    }
  }
  v5 = v2 + 1;
  *((_DWORD *)this + 18) = 0;
  if ( (int)v2 + 1 > v3 )
  {
    v6 = (void *)*((_QWORD *)this + 8);
    v7 = v5 + (v5 >> 1) + 32;
    v8 = GetProcessHeap();
    if ( v6 )
      v9 = HeapReAlloc(v8, 0, v6, 2 * v7);
    else
      v9 = HeapAlloc(v8, 0, 2 * v7);
    if ( v9 )
    {
      *((_QWORD *)this + 8) = v9;
      *((_DWORD *)this + 19) = v7;
      goto LABEL_11;
    }
LABEL_20:
    v10 = -2147024882;
    goto LABEL_12;
  }
LABEL_11:
  v10 = 0;
  v11 = 2LL * (unsigned int)v2;
  memcpy_0(*((void **)this + 8), Src, v11);
  v12 = *((_QWORD *)this + 8);
  *((_DWORD *)this + 18) = v5;
  *(_WORD *)(v11 + v12) = 0;
LABEL_12:
  if ( v10 < 0
    && WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_0955e053d70b3b28b837838791dca877_Traceguids,
      (unsigned int)v10);
  }
  return this;
}

```

## disassembly

```asm
0x180007c30  mov     r11, rsp
0x180007c33  push    rbp
0x180007c34  push    r13
0x180007c36  sub     rsp, 268h
0x180007c3d  mov     rax, cs:__security_cookie
0x180007c44  xor     rax, rsp
0x180007c47  mov     [rsp+278h+var_38], rax
0x180007c4f  xorps   xmm0, xmm0
0x180007c52  mov     [r11+20h], rdi
0x180007c56  xor     eax, eax
0x180007c58  mov     [r11-18h], r12
0x180007c5c  xor     r12d, r12d
0x180007c5f  lea     r8, [rsp+278h+Src]
0x180007c64  mov     [rcx+8], r12d
0x180007c68  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\IdentityStore\\Cac"...
0x180007c6f  movups  xmmword ptr [rcx+10h], xmm0
0x180007c73  mov     r13, rcx
0x180007c76  mov     r9d, 208h
0x180007c7c  movups  xmmword ptr [rcx+20h], xmm0
0x180007c80  mov     [rcx+30h], rax
0x180007c84  mov     [rcx+38h], al
0x180007c87  mov     [rcx+40h], r12
0x180007c8b  mov     [rcx+48h], r12
0x180007c8f  mov     [rcx+58h], r12d
0x180007c93  lea     rcx, aIdstorecache; "IDStoreCache"
0x180007c9a  mov     [rsp+278h+var_258], r12
0x180007c9f  call    cs:__imp_GetPersistedRegistryLocationW
0x180007ca5  test    eax, eax
0x180007ca7  jnz     loc_180007E34
0x180007cad  mov     [rsp+278h+arg_8], rbx
0x180007cb5  lea     rax, [rsp+278h+Src]
0x180007cba  mov     [rsp+278h+var_20], r14
0x180007cc2  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180007cc9  nop     dword ptr [rax+00000000h]
0x180007cd0  inc     rbx
0x180007cd3  cmp     [rax+rbx*2], r12w
0x180007cd8  jnz     short loc_180007CD0
0x180007cda  mov     r14d, [r13+4Ch]
0x180007cde  mov     [rsp+278h+arg_10], rsi
0x180007ce6  test    r14d, r14d
0x180007ce9  jnz     short loc_180007CF7
0x180007ceb  mov     ecx, [r13+58h]
0x180007cef  test    ecx, ecx
0x180007cf1  jnz     loc_180007DCB
0x180007cf7  lea     esi, [rbx+1]
0x180007cfa  mov     [r13+48h], r12d
0x180007cfe  cmp     esi, r14d
0x180007d01  jbe     short loc_180007D56
0x180007d03  mov     rbp, [r13+40h]
0x180007d07  mov     r14d, esi
0x180007d0a  shr     r14d, 1
0x180007d0d  add     r14d, 20h ; ' '
0x180007d11  mov     [rsp+278h+var_28], r15
0x180007d19  add     r14d, esi
0x180007d1c  lea     r15d, [r14+r14]
0x180007d20  call    cs:__imp_GetProcessHeap
0x180007d26  xor     edx, edx; dwFlags
0x180007d28  mov     rcx, rax; hHeap
0x180007d2b  test    rbp, rbp
0x180007d2e  jnz     loc_180007E19
0x180007d34  mov     r8d, r15d; dwBytes
0x180007d37  call    cs:__imp_HeapAlloc
0x180007d3d  mov     r15, [rsp+278h+var_28]
0x180007d45  test    rax, rax
0x180007d48  jz      loc_180007E2A
0x180007d4e  mov     [r13+40h], rax
0x180007d52  mov     [r13+4Ch], r14d
0x180007d56  mov     rcx, [r13+40h]; void *
0x180007d5a  lea     rdx, [rsp+278h+Src]; Src
0x180007d5f  mov     eax, ebx
0x180007d61  mov     ebp, r12d
0x180007d64  lea     rbx, [rax+rax]
0x180007d68  mov     r8, rbx; Size
0x180007d6b  call    memcpy_0
0x180007d70  mov     rcx, [r13+40h]
0x180007d74  mov     [r13+48h], esi
0x180007d78  mov     [rbx+rcx], r12w
0x180007d7d  mov     r14, [rsp+278h+var_20]
0x180007d85  mov     rsi, [rsp+278h+arg_10]
0x180007d8d  mov     rbx, [rsp+278h+arg_8]
0x180007d95  mov     r12, [rsp+278h+var_18]
0x180007d9d  mov     rdi, [rsp+278h+arg_18]
0x180007da5  test    ebp, ebp
0x180007da7  js      loc_180007E4B
0x180007dad  mov     rax, r13
0x180007db0  mov     rcx, [rsp+278h+var_38]
0x180007db8  xor     rcx, rsp; StackCookie
0x180007dbb  call    __security_check_cookie
0x180007dc0  add     rsp, 268h
0x180007dc7  pop     r13
0x180007dc9  pop     rbp
0x180007dca  retn
0x180007dcb  mov     rsi, [r13+40h]
0x180007dcf  mov     r14d, ecx
0x180007dd2  shr     r14d, 1
0x180007dd5  add     r14d, 20h ; ' '
0x180007dd9  add     r14d, ecx
0x180007ddc  lea     ebp, [r14+r14]
0x180007de0  call    cs:__imp_GetProcessHeap
0x180007de6  xor     edx, edx; dwFlags
0x180007de8  mov     rcx, rax; hHeap
0x180007deb  test    rsi, rsi
0x180007dee  jnz     short loc_180007E0B
0x180007df0  mov     r8d, ebp; dwBytes
0x180007df3  call    cs:__imp_HeapAlloc
0x180007df9  test    rax, rax
0x180007dfc  jz      short loc_180007E2A
0x180007dfe  mov     [r13+40h], rax
0x180007e02  mov     [r13+4Ch], r14d
0x180007e06  jmp     loc_180007CF7
0x180007e0b  mov     r9, rbp; dwBytes
0x180007e0e  mov     r8, rsi; lpMem
0x180007e11  call    cs:__imp_HeapReAlloc
0x180007e17  jmp     short loc_180007DF9
0x180007e19  mov     r9, r15; dwBytes
0x180007e1c  mov     r8, rbp; lpMem
0x180007e1f  call    cs:__imp_HeapReAlloc
0x180007e25  jmp     loc_180007D3D
0x180007e2a  mov     ebp, 8007000Eh
0x180007e2f  jmp     loc_180007D7D
0x180007e34  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\IdentityStore\\Cac"...
0x180007e3b  lea     rcx, [r13+40h]; this
0x180007e3f  call    ?Assign@CDynamicString@@QEAAJPEBG@Z; CDynamicString::Assign(ushort const *)
0x180007e44  mov     ebp, eax
0x180007e46  jmp     loc_180007D95
0x180007e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e52  lea     rax, WPP_GLOBAL_Control
0x180007e59  cmp     rcx, rax
0x180007e5c  jz      loc_180007DAD
0x180007e62  test    byte ptr [rcx+1Ch], 4
0x180007e66  jz      loc_180007DAD
0x180007e6c  mov     rcx, [rcx+10h]
0x180007e70  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x180007e77  mov     edx, 14h
0x180007e7c  mov     r9d, ebp
0x180007e7f  call    WPP_SF_d
0x180007e84  jmp     loc_180007DAD
```
