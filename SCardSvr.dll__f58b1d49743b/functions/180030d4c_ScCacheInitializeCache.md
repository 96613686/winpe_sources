# ScCacheInitializeCache

- ea: `0x180030d4c`
- end: `0x180030eae`
- name: `ScCacheInitializeCache`
- size: `354`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001943c`

## callees

- `0x1800028b0`
- `0x180005700`
- `0x180028b78`
- `0x18002ab90`
- `0x180030680`
- `0x180030c0c`
- `0x180030d4c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180030e23`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180030e23`

## pseudocode

```c
__int64 __fastcall ScCacheInitializeCache(__int64 a1, __int64 a2, _DWORD *a3, unsigned int a4)
{
  __int64 v7; // rax
  __int64 v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  unsigned int v10; // ebx
  PVOID v11; // rcx
  struct _RTL_CRITICAL_SECTION_DEBUG *v12; // rax

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v7 = (*(__int64 (__fastcall **)(__int64))(a2 + 16))(104);
  v9 = (struct _RTL_CRITICAL_SECTION *)v7;
  if ( v7 )
  {
    *(_DWORD *)(v7 + 88) = *(_DWORD *)a2;
    *(_DWORD *)(v7 + 92) = *(_DWORD *)(a2 + 4);
    *(_DWORD *)(v7 + 96) = *(_DWORD *)(a2 + 8);
    *(_QWORD *)(v7 + 48) = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(v7 + 56) = *(_QWORD *)(a2 + 24);
    InitializeCriticalSection((LPCRITICAL_SECTION)v7);
    v12 = (struct _RTL_CRITICAL_SECTION_DEBUG *)AllocH(0x88u);
    if ( v12 )
    {
      v10 = 0;
      v9[1].DebugInfo = v12;
      I_ScInitializeCacheReadData((__int64)v9, a3, a4);
      g_pCacheHandle = v9;
    }
    else
    {
      I_ServerCacheCleanup(v9);
      v10 = 8;
    }
  }
  else
  {
    WppTraceIndent(v8, 2);
    v10 = 8;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
    }
  }
  WppTraceIndent((__int64)v11, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180030d4c  push    rbx
0x180030d4e  push    rbp
0x180030d4f  push    rsi
0x180030d50  push    rdi
0x180030d51  push    r12
0x180030d53  sub     rsp, 30h
0x180030d57  mov     rbx, rdx
0x180030d5a  mov     esi, r9d
0x180030d5d  xor     edx, edx
0x180030d5f  mov     rbp, r8
0x180030d62  call    WppTraceIndent
0x180030d67  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d6e  lea     r12, WPP_GLOBAL_Control
0x180030d75  cmp     rcx, r12
0x180030d78  jz      short loc_180030DA2
0x180030d7a  test    byte ptr [rcx+1Ch], 2
0x180030d7e  jz      short loc_180030DA2
0x180030d80  cmp     byte ptr [rcx+19h], 5
0x180030d84  jb      short loc_180030DA2
0x180030d86  mov     r9, cs:WPP_pszIndent
0x180030d8d  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180030d94  mov     rcx, [rcx+10h]
0x180030d98  mov     edx, 14h
0x180030d9d  call    WPP_SF_s
0x180030da2  mov     rax, [rbx+10h]
0x180030da6  mov     ecx, 68h ; 'h'
0x180030dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030db0  mov     rdi, rax
0x180030db3  test    rax, rax
0x180030db6  jnz     short loc_180030DFF
0x180030db8  lea     edx, [rax+2]
0x180030dbb  call    WppTraceIndent
0x180030dc0  lea     ebx, [rdi+8]
0x180030dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dca  cmp     rcx, r12
0x180030dcd  jz      loc_180030E5F
0x180030dd3  test    byte ptr [rcx+1Ch], 1
0x180030dd7  jz      loc_180030E5F
0x180030ddd  cmp     byte ptr [rcx+19h], 2
0x180030de1  jb      short loc_180030E5F
0x180030de3  mov     r9, cs:WPP_pszIndent
0x180030dea  lea     edx, [rdi+15h]
0x180030ded  mov     rcx, [rcx+10h]
0x180030df1  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180030df8  call    WPP_SF_s
0x180030dfd  jmp     short loc_180030E5F
0x180030dff  mov     eax, [rbx]
0x180030e01  mov     rcx, rdi; lpCriticalSection
0x180030e04  mov     [rdi+58h], eax
0x180030e07  mov     eax, [rbx+4]
0x180030e0a  mov     [rdi+5Ch], eax
0x180030e0d  mov     eax, [rbx+8]
0x180030e10  mov     [rdi+60h], eax
0x180030e13  mov     rax, [rbx+10h]
0x180030e17  mov     [rdi+30h], rax
0x180030e1b  mov     rax, [rbx+18h]
0x180030e1f  mov     [rdi+38h], rax
0x180030e23  call    cs:__imp_InitializeCriticalSection
0x180030e29  mov     ecx, 88h; unsigned __int64
0x180030e2e  call    ?AllocH@@YAPEAX_K@Z; AllocH(unsigned __int64)
0x180030e33  mov     rcx, rdi
0x180030e36  test    rax, rax
0x180030e39  jz      short loc_180030E55
0x180030e3b  xor     ebx, ebx
0x180030e3d  mov     [rdi+28h], rax
0x180030e41  mov     r8d, esi
0x180030e44  mov     rdx, rbp
0x180030e47  call    I_ScInitializeCacheReadData
0x180030e4c  mov     cs:?g_pCacheHandle@@3_KA, rdi; unsigned __int64 g_pCacheHandle
0x180030e53  jmp     short loc_180030E5F
0x180030e55  call    I_ServerCacheCleanup
0x180030e5a  mov     ebx, 8
0x180030e5f  mov     edx, 1
0x180030e64  call    WppTraceIndent
0x180030e69  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e70  cmp     rcx, r12
0x180030e73  jz      short loc_180030EA1
0x180030e75  test    byte ptr [rcx+1Ch], 2
0x180030e79  jz      short loc_180030EA1
0x180030e7b  cmp     byte ptr [rcx+19h], 5
0x180030e7f  jb      short loc_180030EA1
0x180030e81  mov     r9, cs:WPP_pszIndent
0x180030e88  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180030e8f  mov     rcx, [rcx+10h]
0x180030e93  mov     edx, 16h
0x180030e98  mov     [rsp+58h+var_38], ebx
0x180030e9c  call    WPP_SF_sD
0x180030ea1  mov     eax, ebx
0x180030ea3  add     rsp, 30h
0x180030ea7  pop     r12
0x180030ea9  pop     rdi
0x180030eaa  pop     rsi
0x180030eab  pop     rbp
0x180030eac  pop     rbx
0x180030ead  retn
```
