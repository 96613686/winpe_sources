# ScCacheRead

- ea: `0x180005090`
- end: `0x1800056ec`
- name: `ScCacheRead`
- size: `1628`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, int, unsigned __int16 *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180005eac`

## callees

- `0x180005090`
- `0x180005700`
- `0x1800058ec`
- `0x180018488`
- `0x180023276`
- `0x180028b78`
- `0x18002ab90`
- `0x180031294`
- `0x180032696`
- `0x1800326d0`
- `0x180037010`

## import_xrefs

- `msvcrt!time` at `0x1800053b4`
- `msvcrt!time` at `0x1800053b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800051bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800051bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005313`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005313`
- `bcrypt!BCryptHashData` at `0x18000522b`
- `bcrypt!BCryptHashData` at `0x18000522b`
- `bcrypt!BCryptDestroyHash` at `0x18000523f`
- `bcrypt!BCryptDestroyHash` at `0x18000526c`
- `bcrypt!BCryptDestroyHash` at `0x18000523f`
- `bcrypt!BCryptDestroyHash` at `0x18000526c`
- `bcrypt!BCryptFinishHash` at `0x18000525c`
- `bcrypt!BCryptFinishHash` at `0x18000525c`
- `bcrypt!BCryptCreateHash` at `0x1800051f2`
- `bcrypt!BCryptCreateHash` at `0x1800051f2`
- `ntdll!RtlNtStatusToDosError` at `0x180005645`
- `ntdll!RtlNtStatusToDosError` at `0x180005645`

## string_xrefs

- `0x180005617`: `ScCacheRead`

## pseudocode

```c
__int64 __fastcall ScCacheRead(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        unsigned __int16 *a6,
        _QWORD *a7,
        _DWORD *a8)
{
  unsigned __int16 *v8; // rbp
  LPCRITICAL_SECTION v9; // r12
  PVOID v12; // rcx
  __int64 v13; // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rsi
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // edi
  ULONG v18; // eax
  int v19; // ebx
  __int64 v20; // rbx
  const void **v21; // rdi
  unsigned int v22; // ebx
  unsigned int v23; // eax
  unsigned int v24; // r9d
  __int64 i; // r10
  unsigned __int16 *v27; // rcx
  int v28; // eax
  int v29; // edx
  __int64 v30; // rax
  _QWORD *v31; // rcx
  _QWORD *v32; // rcx
  ULONG_PTR SpinCount; // rax
  void *v34; // rax
  _QWORD *v35; // rcx
  void *v36; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+A0h] [rbp-A8h] BYREF
  char v38[8]; // [rsp+A8h] [rbp-A0h]
  time_t Time; // [rsp+B0h] [rbp-98h] BYREF
  _QWORD *v40; // [rsp+B8h] [rbp-90h]
  _DWORD *v41; // [rsp+C0h] [rbp-88h]
  ULONG cbInput[2]; // [rsp+C8h] [rbp-80h] BYREF
  PUCHAR pbInput; // [rsp+D0h] [rbp-78h]
  int v44; // [rsp+D8h] [rbp-70h]
  __int64 v45; // [rsp+E0h] [rbp-68h]
  __int128 v46; // [rsp+E8h] [rbp-60h]
  UCHAR pbOutput[32]; // [rsp+F8h] [rbp-50h] BYREF

  v8 = a6;
  v9 = g_pCacheHandle;
  v40 = a7;
  *(_DWORD *)v38 = a3;
  phHash = a6;
  v41 = a8;
  Time = 0;
  WppTraceIndent(a1, 0);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v46 = 0;
  if ( !a4 )
  {
    v22 = -2146435068;
    goto LABEL_27;
  }
  if ( !a2 )
  {
    v22 = -2146434960;
    goto LABEL_27;
  }
  WppTraceIndent(v12, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ssDDDDDDDDDDDSDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)"ScCacheRead",
      *(_DWORD *)a2,
      *(_WORD *)(a2 + 4),
      *(_WORD *)(a2 + 6),
      *(_BYTE *)(a2 + 8),
      *(_BYTE *)(a2 + 9),
      *(_BYTE *)(a2 + 10),
      *(_BYTE *)(a2 + 11),
      *(_BYTE *)(a2 + 12),
      *(_BYTE *)(a2 + 13),
      *(_BYTE *)(a2 + 14),
      *(_BYTE *)(a2 + 15),
      a4,
      v38[0],
      (__int64)phHash);
    v8 = (unsigned __int16 *)phHash;
  }
  v13 = -1;
  cbInput[0] = 16;
  pbInput = (PUCHAR)a2;
  do
    ++v13;
  while ( *(_WORD *)(a4 + 2 * v13) );
  v45 = a4;
  v44 = 2 * v13;
  EnterCriticalSection(v9);
  DebugInfo = v9[1].DebugInfo;
  phHash = 0;
  v15 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
  if ( v15 )
  {
    v18 = WIN32_FROM_NTSTATUS(v15);
  }
  else
  {
    v16 = 2;
    while ( v16 )
    {
      --v16;
      v17 = BCryptHashData(phHash, (&pbInput)[2 * v16], cbInput[4 * v16], 0);
      if ( v17 )
      {
        BCryptDestroyHash(phHash);
        v18 = WIN32_FROM_NTSTATUS(v17);
        goto LABEL_14;
      }
    }
    v19 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
    BCryptDestroyHash(phHash);
    if ( v19 < 0 )
    {
      v18 = RtlNtStatusToDosError(v19);
      if ( v18 == 317 )
        v18 = v19;
    }
    else
    {
      v18 = 0;
    }
  }
LABEL_14:
  if ( v18 )
  {
    v23 = WIN32_FROM_NTSTATUS(v18);
    v22 = v23;
    if ( v23 )
    {
      if ( v23 != 1168 )
        goto LABEL_26;
      goto LABEL_25;
    }
    v21 = (const void **)*((_QWORD *)&v46 + 1);
  }
  else
  {
    v20 = *((_QWORD *)&DebugInfo->Type + (pbOutput[0] & 0xF));
    if ( !v20 )
      goto LABEL_25;
    while ( memcmp_0((const void *)(v20 + 24), pbOutput, 0x20u) )
    {
      v20 = *(_QWORD *)(v20 + 16);
      if ( !v20 )
        goto LABEL_25;
    }
    v21 = *(const void ***)(v20 + 8);
    if ( !v21 || !*(_DWORD *)v20 )
      goto LABEL_25;
    v22 = 0;
  }
  if ( a5 != 1 )
    goto LABEL_33;
  v24 = *((_DWORD *)v21 + 18);
  for ( i = 0; (unsigned int)i < v24; i = (unsigned int)(i + 1) )
  {
    v27 = v8;
    do
    {
      v28 = *(unsigned __int16 *)((char *)v27 + *((_QWORD *)v21[8] + i) - (_QWORD)v8);
      v29 = *v27 - v28;
      if ( v29 )
        break;
      ++v27;
    }
    while ( v28 );
    if ( !v29 )
      goto LABEL_33;
  }
  if ( (_DWORD)i != v24 )
  {
LABEL_33:
    time(&Time);
    v30 = (__int64)v21[2];
    if ( Time - v30 >= 0
      && v30 >= 0
      && Time - v30 <= (unsigned int)(86400 * LODWORD(v9[2].OwningThread))
      && *(_DWORD *)v38 == *((_DWORD *)v21 + 3) )
    {
      if ( v21 != (const void **)v9[1].SpinCount )
      {
        if ( v9[1].LockSemaphore == v21 )
        {
          v36 = (void *)v21[7];
          if ( v36 )
            v9[1].LockSemaphore = v36;
        }
        v31 = v21[7];
        if ( v31 )
          v31[6] = v21[6];
        v32 = v21[6];
        if ( v32 )
          v32[7] = v21[7];
        v21[7] = 0;
        SpinCount = v9[1].SpinCount;
        if ( (const void **)SpinCount != v21 && SpinCount )
        {
          v21[6] = (const void *)SpinCount;
          *(_QWORD *)(v9[1].SpinCount + 56) = v21;
        }
        v9[1].SpinCount = (ULONG_PTR)v21;
      }
      v34 = (void *)(*(__int64 (__fastcall **)(_QWORD))&v9[1].LockCount)(*((unsigned int *)v21 + 2));
      v35 = v40;
      *v40 = v34;
      if ( v34 )
      {
        memcpy_0(v34, *v21, *((unsigned int *)v21 + 2));
        *v41 = *((_DWORD *)v21 + 2);
      }
      else
      {
        WppTraceIndent(v35, 2);
        v22 = 8;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            &WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
            WPP_pszIndent);
        }
      }
    }
    else
    {
      I_ServerCacheRemoveItem(v9, v21, cbInput);
      v22 = -2146434959;
    }
    goto LABEL_26;
  }
LABEL_25:
  v22 = -2146434960;
LABEL_26:
  LeaveCriticalSection(v9);
LABEL_27:
  WppTraceIndent(v12, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)&WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v22);
  }
  return v22;
}

```

## disassembly

```asm
0x180005090  mov     r11, rsp
0x180005093  push    rbx
0x180005094  sub     rsp, 140h
0x18000509b  mov     rax, cs:__security_cookie
0x1800050a2  xor     rax, rsp
0x1800050a5  mov     [rsp+148h+var_30], rax
0x1800050ad  mov     rax, [rsp+148h+arg_30]
0x1800050b5  mov     [r11+8], rbp
0x1800050b9  mov     rbp, [rsp+148h+arg_28]
0x1800050c1  mov     [r11+18h], rdi
0x1800050c5  xor     edi, edi
0x1800050c7  mov     [r11-10h], r12
0x1800050cb  mov     r12, cs:?g_pCacheHandle@@3_KA; unsigned __int64 g_pCacheHandle
0x1800050d2  mov     [r11-20h], r14
0x1800050d6  mov     r14, r9
0x1800050d9  mov     [r11-28h], r15
0x1800050dd  mov     r15, rdx
0x1800050e0  mov     [rsp+148h+var_90], rax
0x1800050e8  xor     edx, edx
0x1800050ea  mov     rax, [rsp+148h+arg_38]
0x1800050f2  mov     dword ptr [rsp+148h+var_A0], r8d
0x1800050fa  mov     [rsp+148h+phHash], rbp
0x180005102  mov     [rsp+148h+var_88], rax
0x18000510a  mov     [r11-98h], rdi
0x180005111  call    WppTraceIndent
0x180005116  mov     rcx, cs:WPP_GLOBAL_Control
0x18000511d  lea     rbx, WPP_GLOBAL_Control
0x180005124  cmp     rcx, rbx
0x180005127  jnz     loc_1800054C4
0x18000512d  xorps   xmm0, xmm0
0x180005130  movups  [rsp+148h+var_60], xmm0
0x180005138  test    r14, r14
0x18000513b  jz      loc_180005516
0x180005141  test    r15, r15
0x180005144  jz      loc_180005553
0x18000514a  mov     [rsp+148h+arg_8], rsi
0x180005152  mov     edx, 2
0x180005157  mov     [rsp+148h+var_18], r13
0x18000515f  call    WppTraceIndent
0x180005164  mov     r13, cs:WPP_GLOBAL_Control
0x18000516b  cmp     r13, rbx
0x18000516e  jnz     loc_180005564
0x180005174  mov     r13, [rsp+148h+var_18]
0x18000517c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180005183  mov     [rsp+148h+cbInput], 10h
0x18000518e  mov     [rsp+148h+pbInput], r15
0x180005196  nop     word ptr [rax+rax+00000000h]
0x1800051a0  inc     rax
0x1800051a3  cmp     word ptr [r14+rax*2], 0
0x1800051a9  jnz     short loc_1800051A0
0x1800051ab  add     eax, eax
0x1800051ad  mov     [rsp+148h+var_68], r14
0x1800051b5  mov     rcx, r12; lpCriticalSection
0x1800051b8  mov     [rsp+148h+var_70], eax
0x1800051bf  call    cs:__imp_EnterCriticalSection
0x1800051c5  mov     rsi, [r12+28h]
0x1800051ca  lea     rdx, [rsp+148h+phHash]; phHash
0x1800051d2  mov     [rsp+148h+dwFlags], edi; dwFlags
0x1800051d6  xor     r9d, r9d; cbHashObject
0x1800051d9  mov     [rsp+148h+cbSecret], edi; cbSecret
0x1800051dd  xor     r8d, r8d; pbHashObject
0x1800051e0  mov     ecx, 41h ; 'A'; hAlgorithm
0x1800051e5  mov     [rsp+148h+pbSecret], rdi; pbSecret
0x1800051ea  mov     [rsp+148h+phHash], rdi
0x1800051f2  call    cs:__imp_BCryptCreateHash
0x1800051f8  test    eax, eax
0x1800051fa  jnz     loc_180005637
0x180005200  mov     ebx, 2
0x180005205  mov     rcx, [rsp+148h+phHash]; hHash
0x18000520d  xor     r9d, r9d; dwFlags
0x180005210  test    ebx, ebx
0x180005212  jz      short loc_18000524E
0x180005214  dec     ebx
0x180005216  mov     edx, ebx
0x180005218  add     rdx, rdx
0x18000521b  mov     r8d, [rsp+rdx*8+148h+cbInput]; cbInput
0x180005223  mov     rdx, [rsp+rdx*8+148h+pbInput]; pbInput
0x18000522b  call    cs:__imp_BCryptHashData
0x180005231  mov     edi, eax
0x180005233  test    eax, eax
0x180005235  jz      short loc_180005205
0x180005237  mov     rcx, [rsp+148h+phHash]; hHash
0x18000523f  call    cs:__imp_BCryptDestroyHash
0x180005245  mov     ecx, edi
0x180005247  call    WIN32_FROM_NTSTATUS
0x18000524c  jmp     short loc_18000527C
0x18000524e  mov     r8d, 20h ; ' '; cbOutput
0x180005254  lea     rdx, [rsp+148h+pbOutput]; pbOutput
0x18000525c  call    cs:__imp_BCryptFinishHash
0x180005262  mov     rcx, [rsp+148h+phHash]; hHash
0x18000526a  mov     ebx, eax
0x18000526c  call    cs:__imp_BCryptDestroyHash
0x180005272  test    ebx, ebx
0x180005274  js      loc_180005643
0x18000527a  xor     eax, eax
0x18000527c  test    eax, eax
0x18000527e  jnz     short loc_1800052C4
0x180005280  movzx   eax, [rsp+148h+pbOutput]
0x180005288  and     eax, 0Fh
0x18000528b  mov     rbx, [rsi+rax*8]
0x18000528f  test    rbx, rbx
0x180005292  jz      short loc_180005304
0x180005294  lea     rcx, [rbx+18h]; Buf1
0x180005298  mov     r8d, 20h ; ' '; Size
0x18000529e  lea     rdx, [rsp+148h+pbOutput]; Buf2
0x1800052a6  call    memcmp_0
0x1800052ab  test    eax, eax
0x1800052ad  jnz     loc_180005668
0x1800052b3  mov     rdi, [rbx+8]
0x1800052b7  test    rdi, rdi
0x1800052ba  jz      short loc_180005304
0x1800052bc  cmp     [rbx], eax
0x1800052be  jz      short loc_180005304
0x1800052c0  xor     ebx, ebx
0x1800052c2  jmp     short loc_1800052DD
0x1800052c4  mov     ecx, eax
0x1800052c6  call    WIN32_FROM_NTSTATUS
0x1800052cb  mov     ebx, eax
0x1800052cd  test    eax, eax
0x1800052cf  jnz     loc_180005658
0x1800052d5  mov     rdi, qword ptr [rsp+148h+var_60+8]
0x1800052dd  cmp     [rsp+148h+arg_20], 1
0x1800052e5  jnz     loc_1800053AC
0x1800052eb  mov     r9d, [rdi+48h]
0x1800052ef  xor     r10d, r10d
0x1800052f2  test    r9d, r9d
0x1800052f5  jnz     loc_18000537E
0x1800052fb  cmp     r10d, r9d
0x1800052fe  jnz     loc_1800053AC
0x180005304  mov     ebx, 80100070h
0x180005309  lea     rdi, WPP_GLOBAL_Control
0x180005310  mov     rcx, r12; lpCriticalSection
0x180005313  call    cs:__imp_LeaveCriticalSection
0x180005319  mov     rsi, [rsp+148h+arg_8]
0x180005321  mov     edx, 1
0x180005326  call    WppTraceIndent
0x18000532b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005332  mov     r15, [rsp+148h+var_28]
0x18000533a  cmp     rcx, rdi
0x18000533d  mov     rdi, [rsp+148h+arg_10]
0x180005345  mov     r14, [rsp+148h+var_20]
0x18000534d  mov     r12, [rsp+148h+var_10]
0x180005355  mov     rbp, [rsp+148h+arg_0]
0x18000535d  jnz     loc_18000548B
0x180005363  mov     eax, ebx
0x180005365  mov     rcx, [rsp+148h+var_30]
0x18000536d  xor     rcx, rsp; StackCookie
0x180005370  call    __security_check_cookie
0x180005375  add     rsp, 140h
0x18000537c  pop     rbx
0x18000537d  retn
0x18000537e  mov     r11, [rdi+40h]
0x180005382  mov     r8, [r11+r10*8]
0x180005386  mov     rcx, rbp
0x180005389  sub     r8, rbp
0x18000538c  nop     dword ptr [rax+00h]
0x180005390  movzx   edx, word ptr [rcx]
0x180005393  movzx   eax, word ptr [rcx+r8]
0x180005398  sub     edx, eax
0x18000539a  jnz     short loc_1800053A4
0x18000539c  add     rcx, 2
0x1800053a0  test    eax, eax
0x1800053a2  jnz     short loc_180005390
0x1800053a4  test    edx, edx
0x1800053a6  jnz     loc_180005527
0x1800053ac  lea     rcx, [rsp+148h+Time]; Time
0x1800053b4  call    cs:__imp_time
0x1800053ba  mov     rax, [rdi+10h]
0x1800053be  mov     rdx, [rsp+148h+Time]
0x1800053c6  sub     rdx, rax
0x1800053c9  js      loc_1800054F9
0x1800053cf  test    rax, rax
0x1800053d2  js      loc_1800054F9
0x1800053d8  imul    ecx, [r12+60h], 15180h
0x1800053e1  cmp     rdx, rcx
0x1800053e4  jg      loc_1800054F9
0x1800053ea  mov     eax, dword ptr [rsp+148h+var_A0]
0x1800053f1  cmp     eax, [rdi+0Ch]
0x1800053f4  jnz     loc_1800054F9
0x1800053fa  cmp     rdi, [r12+48h]
0x1800053ff  jz      short loc_180005449
0x180005401  cmp     [r12+40h], rdi
0x180005406  jz      loc_18000567A
0x18000540c  mov     rcx, [rdi+38h]
0x180005410  test    rcx, rcx
0x180005413  jz      short loc_18000541D
0x180005415  mov     rax, [rdi+30h]
0x180005419  mov     [rcx+30h], rax
0x18000541d  mov     rcx, [rdi+30h]
0x180005421  test    rcx, rcx
0x180005424  jz      short loc_18000542E
0x180005426  mov     rax, [rdi+38h]
0x18000542a  mov     [rcx+38h], rax
0x18000542e  mov     qword ptr [rdi+38h], 0
0x180005436  mov     rax, [r12+48h]
0x18000543b  cmp     rax, rdi
0x18000543e  jnz     loc_180005538
0x180005444  mov     [r12+48h], rdi
0x180005449  mov     ecx, [rdi+8]
0x18000544c  mov     rax, [r12+30h]
0x180005451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005456  mov     rcx, [rsp+148h+var_90]
0x18000545e  mov     [rcx], rax
0x180005461  test    rax, rax
0x180005464  jz      loc_180005691
0x18000546a  mov     r8d, [rdi+8]; Size
0x18000546e  mov     rcx, rax; void *
0x180005471  mov     rdx, [rdi]; Src
0x180005474  call    memcpy_0
0x180005479  mov     rcx, [rsp+148h+var_88]
0x180005481  mov     eax, [rdi+8]
0x180005484  mov     [rcx], eax
0x180005486  jmp     loc_180005309
0x18000548b  test    byte ptr [rcx+1Ch], 2
0x18000548f  jz      loc_180005363
0x180005495  cmp     byte ptr [rcx+19h], 5
0x180005499  jb      loc_180005363
0x18000549f  mov     r9, cs:WPP_pszIndent
0x1800054a6  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800054ad  mov     rcx, [rcx+10h]
0x1800054b1  mov     edx, 1Ah
0x1800054b6  mov     dword ptr [rsp+148h+pbSecret], ebx
0x1800054ba  call    WPP_SF_sD
0x1800054bf  jmp     loc_180005363
0x1800054c4  test    byte ptr [rcx+1Ch], 2
0x1800054c8  jz      loc_18000512D
0x1800054ce  cmp     byte ptr [rcx+19h], 5
0x1800054d2  jb      loc_18000512D
0x1800054d8  mov     r9, cs:WPP_pszIndent
0x1800054df  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800054e6  mov     rcx, [rcx+10h]
0x1800054ea  mov     edx, 17h
0x1800054ef  call    WPP_SF_s
0x1800054f4  jmp     loc_18000512D
0x1800054f9  lea     r8, [rsp+148h+cbInput]
0x180005501  mov     rdx, rdi
0x180005504  mov     rcx, r12
0x180005507  call    I_ServerCacheRemoveItem
0x18000550c  mov     ebx, 80100071h
0x180005511  jmp     loc_180005309
0x180005516  mov     ebx, 80100004h
0x18000551b  lea     rdi, WPP_GLOBAL_Control
0x180005522  jmp     loc_180005321
0x180005527  inc     r10d
0x18000552a  cmp     r10d, r9d
0x18000552d  jb      loc_180005382
0x180005533  jmp     loc_1800052FB
0x180005538  test    rax, rax
0x18000553b  jz      loc_180005444
0x180005541  mov     [rdi+30h], rax
0x180005545  mov     rax, [r12+48h]
0x18000554a  mov     [rax+38h], rdi
0x18000554e  jmp     loc_180005444
0x180005553  mov     ebx, 80100070h
0x180005558  lea     rdi, WPP_GLOBAL_Control
0x18000555f  jmp     loc_180005321
0x180005564  test    byte ptr [r13+1Ch], 4
0x180005569  jz      loc_180005174
0x18000556f  cmp     byte ptr [r13+19h], 4
0x180005574  jb      loc_180005174
0x18000557a  movzx   eax, byte ptr [r15+0Fh]
0x18000557f  mov     edx, 18h
0x180005584  mov     r13, [rsp+148h+phHash]
0x18000558c  movzx   ecx, byte ptr [r15+0Eh]
0x180005591  movzx   r8d, byte ptr [r15+0Dh]
0x180005596  movzx   r9d, byte ptr [r15+0Ch]
0x18000559b  movzx   r10d, byte ptr [r15+0Bh]
0x1800055a0  movzx   r11d, byte ptr [r15+0Ah]
0x1800055a5  movzx   ebx, byte ptr [r15+9]
0x1800055aa  movzx   edi, byte ptr [r15+8]
0x1800055af  movzx   esi, word ptr [r15+6]
0x1800055b4  movzx   ebp, word ptr [r15+4]
0x1800055b9  mov     [rsp+148h+var_B8], r13; __int64
0x1800055c1  mov     r13d, dword ptr [rsp+148h+var_A0]
0x1800055c9  mov     dword ptr [rsp+148h+var_C0], r13d; char
0x1800055d1  mov     r13, cs:WPP_GLOBAL_Control
0x1800055d8  mov     [rsp+148h+var_C8], r14; __int64
0x1800055e0  mov     dword ptr [rsp+148h+var_D0], eax; char
0x1800055e4  mov     eax, [r15]
0x1800055e7  mov     dword ptr [rsp+148h+var_D8], ecx; char
0x1800055eb  mov     rcx, [r13+10h]; LoggerHandle
0x1800055ef  mov     dword ptr [rsp+148h+var_E0], r8d; char
0x1800055f4  mov     dword ptr [rsp+148h+var_E8], r9d; char
0x1800055f9  mov     dword ptr [rsp+148h+var_F0], r10d; char
0x1800055fe  mov     dword ptr [rsp+148h+var_F8], r11d; char
0x180005603  mov     dword ptr [rsp+148h+var_100], ebx; char
0x180005607  mov     dword ptr [rsp+148h+var_108], edi; char
0x18000560b  mov     dword ptr [rsp+148h+var_110], esi; char
0x18000560f  mov     [rsp+148h+dwFlags], ebp; char
0x180005613  mov     [rsp+148h+cbSecret], eax; char
0x180005617  lea     rax, aSccacheread; "ScCacheRead"
0x18000561e  mov     [rsp+148h+pbSecret], rax; __int64
0x180005623  call    WPP_SF_ssDDDDDDDDDDDSDS
0x180005628  mov     rbp, [rsp+148h+phHash]
0x180005630  xor     edi, edi
0x180005632  jmp     loc_180005174
0x180005637  mov     ecx, eax
0x180005639  call    WIN32_FROM_NTSTATUS
0x18000563e  jmp     loc_18000527C
0x180005643  mov     ecx, ebx; Status
  ... truncated ...
```
