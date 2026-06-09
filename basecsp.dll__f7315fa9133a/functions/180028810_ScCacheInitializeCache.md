# ScCacheInitializeCache

- ea: `0x180028810`
- end: `0x180028964`
- name: `ScCacheInitializeCache`
- size: `340`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18001040c`
- `0x1800225d4`

## callees

- `0x180019430`
- `0x180019650`
- `0x1800196ac`
- `0x18001c96c`
- `0x180028008`
- `0x1800280a4`
- `0x180028810`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800288df`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800288df`

## pseudocode

```c
__int64 __fastcall ScCacheInitializeCache(struct _RTL_CRITICAL_SECTION **a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  unsigned int v7; // ebx
  PVOID v8; // rcx
  struct _RTL_CRITICAL_SECTION_DEBUG *v9; // rax

  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v4 = (*(__int64 (__fastcall **)(__int64))(a2 + 16))(104);
  v6 = (struct _RTL_CRITICAL_SECTION *)v4;
  if ( v4 )
  {
    *(_DWORD *)(v4 + 88) = *(_DWORD *)a2;
    *(_DWORD *)(v4 + 92) = *(_DWORD *)(a2 + 4);
    *(_DWORD *)(v4 + 96) = *(_DWORD *)(a2 + 8);
    *(_QWORD *)(v4 + 48) = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(v4 + 56) = *(_QWORD *)(a2 + 24);
    InitializeCriticalSection((LPCRITICAL_SECTION)v4);
    v9 = (struct _RTL_CRITICAL_SECTION_DEBUG *)MIDL_user_allocate(0x88u);
    if ( v9 )
    {
      v7 = 0;
      v6[1].DebugInfo = v9;
      I_ScInitializeCacheReadData(v6, 0, 0);
      *a1 = v6;
    }
    else
    {
      I_ServerCacheCleanup(v6);
      v7 = 8;
    }
  }
  else
  {
    WppTraceIndent(v5, 2u);
    v7 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
    }
  }
  WppTraceIndent((__int64)v8, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180028810  push    rbx
0x180028812  push    rsi
0x180028813  push    rdi
0x180028814  push    r15
0x180028816  sub     rsp, 38h
0x18002881a  mov     rbx, rdx
0x18002881d  mov     rsi, rcx
0x180028820  xor     edx, edx
0x180028822  call    WppTraceIndent
0x180028827  mov     rcx, cs:WPP_GLOBAL_Control
0x18002882e  lea     r15, WPP_GLOBAL_Control
0x180028835  cmp     rcx, r15
0x180028838  jz      short loc_180028862
0x18002883a  test    byte ptr [rcx+1Ch], 2
0x18002883e  jz      short loc_180028862
0x180028840  cmp     byte ptr [rcx+19h], 5
0x180028844  jb      short loc_180028862
0x180028846  mov     r9, cs:WPP_pszIndent
0x18002884d  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028854  mov     rcx, [rcx+10h]
0x180028858  mov     edx, 14h
0x18002885d  call    WPP_SF_s
0x180028862  mov     rax, [rbx+10h]
0x180028866  mov     ecx, 68h ; 'h'
0x18002886b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028870  mov     rdi, rax
0x180028873  test    rax, rax
0x180028876  jnz     short loc_1800288BB
0x180028878  lea     edx, [rax+2]
0x18002887b  call    WppTraceIndent
0x180028880  lea     ebx, [rdi+8]
0x180028883  mov     rcx, cs:WPP_GLOBAL_Control
0x18002888a  cmp     rcx, r15
0x18002888d  jz      loc_180028916
0x180028893  test    byte ptr [rcx+1Ch], 1
0x180028897  jz      short loc_180028916
0x180028899  cmp     byte ptr [rcx+19h], 2
0x18002889d  jb      short loc_180028916
0x18002889f  mov     r9, cs:WPP_pszIndent
0x1800288a6  lea     edx, [rdi+15h]
0x1800288a9  mov     rcx, [rcx+10h]
0x1800288ad  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800288b4  call    WPP_SF_s
0x1800288b9  jmp     short loc_180028916
0x1800288bb  mov     eax, [rbx]
0x1800288bd  mov     rcx, rdi; lpCriticalSection
0x1800288c0  mov     [rdi+58h], eax
0x1800288c3  mov     eax, [rbx+4]
0x1800288c6  mov     [rdi+5Ch], eax
0x1800288c9  mov     eax, [rbx+8]
0x1800288cc  mov     [rdi+60h], eax
0x1800288cf  mov     rax, [rbx+10h]
0x1800288d3  mov     [rdi+30h], rax
0x1800288d7  mov     rax, [rbx+18h]
0x1800288db  mov     [rdi+38h], rax
0x1800288df  call    cs:__imp_InitializeCriticalSection
0x1800288e5  mov     ecx, 88h; size
0x1800288ea  call    MIDL_user_allocate
0x1800288ef  mov     rcx, rdi
0x1800288f2  test    rax, rax
0x1800288f5  jz      short loc_18002890C
0x1800288f7  xor     ebx, ebx
0x1800288f9  mov     [rdi+28h], rax
0x1800288fd  xor     r8d, r8d
0x180028900  xor     edx, edx
0x180028902  call    I_ScInitializeCacheReadData
0x180028907  mov     [rsi], rdi
0x18002890a  jmp     short loc_180028916
0x18002890c  call    I_ServerCacheCleanup
0x180028911  mov     ebx, 8
0x180028916  mov     edx, 1
0x18002891b  call    WppTraceIndent
0x180028920  mov     rcx, cs:WPP_GLOBAL_Control
0x180028927  cmp     rcx, r15
0x18002892a  jz      short loc_180028958
0x18002892c  test    byte ptr [rcx+1Ch], 2
0x180028930  jz      short loc_180028958
0x180028932  cmp     byte ptr [rcx+19h], 5
0x180028936  jb      short loc_180028958
0x180028938  mov     r9, cs:WPP_pszIndent
0x18002893f  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028946  mov     rcx, [rcx+10h]
0x18002894a  mov     edx, 16h
0x18002894f  mov     [rsp+58h+var_38], ebx
0x180028953  call    WPP_SF_sD
0x180028958  mov     eax, ebx
0x18002895a  add     rsp, 38h
0x18002895e  pop     r15
0x180028960  pop     rdi
0x180028961  pop     rsi
0x180028962  pop     rbx
0x180028963  retn
```
