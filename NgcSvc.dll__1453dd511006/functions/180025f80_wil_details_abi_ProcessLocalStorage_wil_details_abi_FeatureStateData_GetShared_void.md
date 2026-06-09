# wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)

- ea: `0x180025f80`
- end: `0x180026409`
- name: `?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ`
- size: `1161`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800524f0`

## callees

- `0x18000782c`
- `0x180007964`
- `0x18000948c`
- `0x1800094b8`
- `0x180025f80`
- `0x180026410`
- `0x180026498`
- `0x180048098`
- `0x18004cf08`
- `0x18005cee0`
- `0x18006110c`
- `0x180061824`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002600a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002600a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002602a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002602a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002612d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002620e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002612d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002620e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800262bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025fc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025fc8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(__int64 a1)
{
  _DWORD *v2; // rsi
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rdi
  DWORD v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details *v11; // r15
  WCHAR *v12; // r8
  unsigned __int64 v13; // r13
  WCHAR *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  bool v17; // zf
  WCHAR *v18; // rcx
  __int64 v19; // rdx
  WCHAR *v20; // rax
  __int64 v21; // r8
  const wchar_t *v22; // r9
  __int64 v23; // rcx
  WCHAR *v24; // rdx
  __int64 v25; // rax
  WCHAR *v26; // rcx
  wil::details *v27; // rax
  wil::details *v28; // rsi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // r14d
  void *v31; // rdx
  __int64 v32; // rdx
  WCHAR *v33; // rax
  __int64 v34; // r8
  WCHAR *v35; // rax
  const wchar_t *v36; // rcx
  __int64 v37; // rbx
  __int64 v38; // r8
  WCHAR *v39; // rdx
  wil::details *v40; // rax
  const char *v41; // r9
  wil::details *v42; // rbx
  int v43; // eax
  void *v44; // rdx
  void *v45; // rdx
  void *v46; // rdx
  void *v47; // rdx
  void *v48; // rdx
  const char *v49; // r9
  void *v50; // rdx
  wil::details *v51; // rcx
  int v52; // eax
  int v54; // [rsp+20h] [rbp-E0h]
  int v55; // [rsp+20h] [rbp-E0h]
  int v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+30h] [rbp-D0h] BYREF
  int v58; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v59; // [rsp+38h] [rbp-C8h]
  _DWORD *v60; // [rsp+40h] [rbp-C0h]
  wil::details *v61; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR v62[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  if ( *(_QWORD *)(a1 + 8) )
    return (*(_QWORD *)(a1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(a1 + 8) != 0);
  v2 = 0;
  v60 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v54 = 304;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v59 = Mutex;
  v6 = Mutex;
  if ( Mutex )
  {
    v7 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
    if ( v7 == 258 )
    {
      v11 = 0;
    }
    else
    {
      if ( (v7 & 0xFFFFFF7F) != 0 )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, v8, v9, v10);
      v11 = v6;
    }
    v61 = v11;
    v12 = Name;
    v13 = 0;
    v14 = v62;
    v15 = 2147483646;
    v16 = 260;
    do
    {
      if ( !v15 )
        break;
      if ( !*v12 )
        break;
      *v14++ = *v12++;
      --v15;
      --v16;
    }
    while ( v16 );
    v17 = v16 == 0;
    v18 = v14 - 1;
    v19 = 260;
    if ( !v17 )
      v18 = v14;
    v20 = v62;
    *v18 = 0;
    do
    {
      if ( !*v20 )
        break;
      ++v20;
      --v19;
    }
    while ( v19 );
    v21 = (260 - v19) & -(__int64)(v19 != 0);
    if ( v19 )
    {
      v22 = L"_p0";
      v23 = 2147483646;
      v24 = &v62[v21];
      v25 = 260 - v21;
      if ( v21 != 260 )
      {
        do
        {
          if ( !v23 )
            break;
          if ( !*v22 )
            break;
          *v24++ = *v22++;
          --v23;
          --v25;
        }
        while ( v25 );
      }
      v26 = v24 - 1;
      if ( v25 )
        v26 = v24;
      *v26 = 0;
    }
    v27 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, v62);
    v28 = v27;
    if ( v27 )
    {
      v58 = 0;
      v57 = 0;
      ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v27, &v58);
      LastError = ValueFromSemaphore;
      if ( ValueFromSemaphore < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD6,
          (unsigned int)"wil",
          (const char *)(unsigned int)ValueFromSemaphore,
          304);
LABEL_28:
        wil::details::CloseHandle(v28, v31);
LABEL_51:
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, (unsigned int)"wil", (const char *)LastError, v54);
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastError, v55);
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)LastError, v56);
        if ( v11 )
          wil::details::ReleaseMutex(v11, v50);
        v51 = v6;
LABEL_54:
        wil::details::CloseHandle(v51, v50);
        return (*(_QWORD *)(a1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(a1 + 8) != 0);
      }
      v32 = 260;
      v33 = v62;
      do
      {
        if ( !*v33 )
          break;
        ++v33;
        --v32;
      }
      while ( v32 );
      v34 = (260 - v32) & -(__int64)(v32 != 0);
      if ( v32 )
      {
        v35 = &v62[v34];
        v36 = L"h";
        v37 = 260 - v34;
        if ( 260 != v34 )
        {
          v38 = 2147483646;
          do
          {
            if ( !v38 )
              break;
            if ( !*v36 )
              break;
            *v35++ = *v36++;
            --v38;
            --v37;
          }
          while ( v37 );
        }
        v39 = v35 - 1;
        if ( v37 )
          v39 = v35;
        *v39 = 0;
      }
      v40 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, v62);
      v42 = v40;
      if ( v40 )
      {
        v43 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v40, &v57);
        LastError = v43;
        if ( v43 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDE,
            (unsigned int)"wil",
            (const char *)(unsigned int)v43,
            304);
          wil::details::CloseHandle(v42, v45);
          goto LABEL_28;
        }
        wil::details::CloseHandle(v42, v44);
        v13 = v58 | (unsigned __int64)((__int64)v57 << 31);
        wil::details::CloseHandle(v28, v46);
        goto LABEL_45;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v41);
      wil::details::CloseHandle(v28, v48);
    }
    else
    {
      if ( GetLastError() == 2 )
      {
LABEL_45:
        v2 = (_DWORD *)(4 * v13);
        if ( 4 * v13 )
        {
          ++*v2;
        }
        else
        {
          v52 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
          if ( v52 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x137,
              (unsigned int)"wil",
              (const char *)(unsigned int)v52,
              304);
            __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v61);
            v51 = v59;
            if ( !v59 )
              return (*(_QWORD *)(a1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(a1 + 8) != 0);
            goto LABEL_54;
          }
          v2 = v60;
          v6 = v59;
        }
        if ( v11 )
          wil::details::ReleaseMutex(v11, v47);
        if ( v6 )
          wil::details::CloseHandle(v6, v47);
        goto LABEL_64;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v49);
    }
    if ( (LastError & 0x80000000) != 0 )
      goto LABEL_51;
    goto LABEL_45;
  }
  if ( (int)wil::details::GetLastErrorFailHr(v5) < 0 )
    return (*(_QWORD *)(a1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(a1 + 8) != 0);
LABEL_64:
  if ( !*(_QWORD *)(a1 + 8) )
    *(_QWORD *)(a1 + 8) = v2;
  return (*(_QWORD *)(a1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(a1 + 8) != 0);
}

```

## disassembly

```asm
0x180025f80  push    rbp
0x180025f82  push    rbx
0x180025f83  push    rsi
0x180025f84  push    rdi
0x180025f85  push    r12
0x180025f87  push    r13
0x180025f89  push    r14
0x180025f8b  push    r15
0x180025f8d  lea     rbp, [rsp-388h]
0x180025f95  sub     rsp, 488h
0x180025f9c  mov     rax, cs:__security_cookie
0x180025fa3  xor     rax, rsp
0x180025fa6  mov     [rbp+3C0h+var_50], rax
0x180025fad  xor     r14d, r14d
0x180025fb0  mov     r12, rcx
0x180025fb3  cmp     [rcx+8], r14
0x180025fb7  jnz     loc_1800263D4
0x180025fbd  mov     rbx, [rcx]
0x180025fc0  mov     esi, r14d
0x180025fc3  mov     [rsp+4C0h+var_480], r14
0x180025fc8  call    cs:__imp_GetCurrentProcessId
0x180025fce  mov     [rsp+4C0h+var_498], rbx
0x180025fd3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180025fda  mov     ebx, 104h
0x180025fdf  mov     [rsp+4C0h+var_4A0], 130h; int
0x180025fe7  mov     edx, ebx; unsigned __int64
0x180025fe9  lea     rcx, [rbp+3C0h+Name]; unsigned __int16 *
0x180025ff0  mov     r9d, eax
0x180025ff3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025ff8  mov     r9d, 1F0001h; dwDesiredAccess
0x180025ffe  lea     rdx, [rbp+3C0h+Name]; lpName
0x180026005  xor     r8d, r8d; dwFlags
0x180026008  xor     ecx, ecx; lpMutexAttributes
0x18002600a  call    cs:__imp_CreateMutexExW
0x180026010  mov     [rsp+4C0h+var_488], rax
0x180026015  mov     rdi, rax
0x180026018  test    rax, rax
0x18002601b  jz      loc_1800263BF
0x180026021  xor     r8d, r8d; bAlertable
0x180026024  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180026027  mov     rcx, rax; hHandle
0x18002602a  call    cs:__imp_WaitForSingleObjectEx
0x180026030  cmp     eax, 102h
0x180026035  jz      short loc_180026050
0x180026037  test    eax, 0FFFFFF7Fh
0x18002603c  jz      short loc_18002604B
0x18002603e  mov     rcx, [rbp+3C8h]; this
0x180026045  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002604b  mov     r15, rdi
0x18002604e  jmp     short loc_180026053
0x180026050  mov     r15, r14
0x180026053  mov     [rsp+4C0h+var_478], r15
0x180026058  lea     r8, [rbp+3C0h+Name]
0x18002605f  mov     r13, r14
0x180026062  lea     rax, [rsp+4C0h+var_470]
0x180026067  mov     ecx, 7FFFFFFEh
0x18002606c  mov     rdx, rbx
0x18002606f  test    rcx, rcx
0x180026072  jz      short loc_180026093
0x180026074  movzx   r9d, word ptr [r8]
0x180026078  test    r9w, r9w
0x18002607c  jz      short loc_180026093
0x18002607e  mov     [rax], r9w
0x180026082  add     r8, 2
0x180026086  add     rax, 2
0x18002608a  dec     rcx
0x18002608d  sub     rdx, 1
0x180026091  jnz     short loc_18002606F
0x180026093  test    rdx, rdx
0x180026096  lea     rcx, [rax-2]
0x18002609a  mov     rdx, rbx
0x18002609d  cmovnz  rcx, rax
0x1800260a1  lea     rax, [rsp+4C0h+var_470]
0x1800260a6  mov     [rcx], r14w
0x1800260aa  cmp     [rax], r14w
0x1800260ae  jz      short loc_1800260BA
0x1800260b0  add     rax, 2
0x1800260b4  sub     rdx, 1
0x1800260b8  jnz     short loc_1800260AA
0x1800260ba  mov     rcx, rbx
0x1800260bd  mov     rax, rdx
0x1800260c0  sub     rcx, rdx
0x1800260c3  neg     rax
0x1800260c6  sbb     r8, r8
0x1800260c9  and     r8, rcx
0x1800260cc  test    rdx, rdx
0x1800260cf  jz      short loc_180026121
0x1800260d1  mov     rax, rbx
0x1800260d4  lea     rdx, [rsp+4C0h+var_470]
0x1800260d9  lea     r9, aP0; "_p0"
0x1800260e0  mov     ecx, 7FFFFFFEh
0x1800260e5  lea     rdx, [rdx+r8*2]
0x1800260e9  sub     rax, r8
0x1800260ec  jz      short loc_180026112
0x1800260ee  test    rcx, rcx
0x1800260f1  jz      short loc_180026112
0x1800260f3  movzx   r8d, word ptr [r9]
0x1800260f7  test    r8w, r8w
0x1800260fb  jz      short loc_180026112
0x1800260fd  mov     [rdx], r8w
0x180026101  add     r9, 2
0x180026105  add     rdx, 2
0x180026109  dec     rcx
0x18002610c  sub     rax, 1
0x180026110  jnz     short loc_1800260EE
0x180026112  test    rax, rax
0x180026115  lea     rcx, [rdx-2]
0x180026119  cmovnz  rcx, rdx
0x18002611d  mov     [rcx], r14w
0x180026121  lea     r8, [rsp+4C0h+var_470]; lpName
0x180026126  xor     edx, edx; bInheritHandle
0x180026128  mov     ecx, 1F0003h; dwDesiredAccess
0x18002612d  call    cs:__imp_OpenSemaphoreW
0x180026133  mov     rsi, rax
0x180026136  test    rax, rax
0x180026139  jz      loc_1800262BD
0x18002613f  lea     rdx, [rsp+4C0h+var_48C]; int *
0x180026144  mov     [rsp+4C0h+var_48C], r14d
0x180026149  mov     rcx, rax; hHandle
0x18002614c  mov     [rsp+4C0h+var_490], r14d
0x180026151  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026156  xor     r9d, r9d
0x180026159  mov     r14d, eax
0x18002615c  test    eax, eax
0x18002615e  jns     short loc_180026188
0x180026160  mov     rcx, [rbp+3C8h]; this
0x180026167  lea     r8, aWil; "wil"
0x18002616e  mov     r9d, eax; char *
0x180026171  mov     edx, 0D6h; void *
0x180026176  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002617b  mov     rcx, rsi; this
0x18002617e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180026183  jmp     loc_1800262E8
0x180026188  mov     rdx, rbx
0x18002618b  lea     rax, [rsp+4C0h+var_470]
0x180026190  cmp     [rax], r9w
0x180026194  jz      short loc_1800261A0
0x180026196  add     rax, 2
0x18002619a  sub     rdx, 1
0x18002619e  jnz     short loc_180026190
0x1800261a0  mov     rcx, rbx
0x1800261a3  mov     rax, rdx
0x1800261a6  sub     rcx, rdx
0x1800261a9  neg     rax
0x1800261ac  sbb     r8, r8
0x1800261af  and     r8, rcx
0x1800261b2  test    rdx, rdx
0x1800261b5  jz      short loc_180026202
0x1800261b7  lea     rax, [rsp+4C0h+var_470]
0x1800261bc  lea     rax, [rax+r8*2]
0x1800261c0  lea     rcx, asc_1800DB980; "h"
0x1800261c7  sub     rbx, r8
0x1800261ca  jz      short loc_1800261F3
0x1800261cc  mov     r8d, 7FFFFFFEh
0x1800261d2  test    r8, r8
0x1800261d5  jz      short loc_1800261F3
0x1800261d7  movzx   edx, word ptr [rcx]
0x1800261da  test    dx, dx
0x1800261dd  jz      short loc_1800261F3
0x1800261df  mov     [rax], dx
0x1800261e2  add     rcx, 2
0x1800261e6  add     rax, 2
0x1800261ea  dec     r8
0x1800261ed  sub     rbx, 1
0x1800261f1  jnz     short loc_1800261D2
0x1800261f3  test    rbx, rbx
0x1800261f6  lea     rdx, [rax-2]
0x1800261fa  cmovnz  rdx, rax
0x1800261fe  mov     [rdx], r9w
0x180026202  lea     r8, [rsp+4C0h+var_470]; lpName
0x180026207  xor     edx, edx; bInheritHandle
0x180026209  mov     ecx, 1F0003h; dwDesiredAccess
0x18002620e  call    cs:__imp_OpenSemaphoreW
0x180026214  mov     rbx, rax
0x180026217  test    rax, rax
0x18002621a  jz      short loc_180026298
0x18002621c  lea     rdx, [rsp+4C0h+var_490]; int *
0x180026221  mov     rcx, rax; hHandle
0x180026224  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026229  mov     r14d, eax
0x18002622c  test    eax, eax
0x18002622e  jns     short loc_180026258
0x180026230  mov     rcx, [rbp+3C8h]; this
0x180026237  lea     r8, aWil; "wil"
0x18002623e  mov     r9d, eax; char *
0x180026241  mov     edx, 0DEh; void *
0x180026246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002624b  mov     rcx, rbx; this
0x18002624e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180026253  jmp     loc_18002617B
0x180026258  mov     rcx, rbx; this
0x18002625b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180026260  movsxd  rax, [rsp+4C0h+var_48C]
0x180026265  mov     rcx, rsi; this
0x180026268  movsxd  r13, [rsp+4C0h+var_490]
0x18002626d  shl     r13, 1Fh
0x180026271  or      r13, rax
0x180026274  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180026279  xor     r14d, r14d
0x18002627c  lea     rsi, ds:0[r13*4]
0x180026284  test    rsi, rsi
0x180026287  jz      loc_18002634E
0x18002628d  mov     eax, [rsi]
0x18002628f  inc     eax
0x180026291  mov     [rsi], eax
0x180026293  jmp     loc_1800263A3
0x180026298  mov     rcx, [rbp+3C8h]; this
0x18002629f  lea     r8, aWil; "wil"
0x1800262a6  mov     edx, 0DCh; void *
0x1800262ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800262b0  mov     rcx, rsi; this
0x1800262b3  mov     r14d, eax
0x1800262b6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800262bb  jmp     short loc_1800262E3
0x1800262bd  call    cs:__imp_GetLastError
0x1800262c3  cmp     eax, 2
0x1800262c6  jz      short loc_18002627C
0x1800262c8  mov     rcx, [rbp+3C8h]; this
0x1800262cf  lea     r8, aWil; "wil"
0x1800262d6  mov     edx, 0D0h; void *
0x1800262db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800262e0  mov     r14d, eax
0x1800262e3  test    r14d, r14d
0x1800262e6  jns     short loc_180026279
0x1800262e8  mov     rcx, [rbp+3C8h]; this
0x1800262ef  lea     rsi, aWil; "wil"
0x1800262f6  mov     r8, rsi; unsigned int
0x1800262f9  mov     r9d, r14d; char *
0x1800262fc  mov     edx, 66h ; 'f'; void *
0x180026301  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026306  mov     rcx, [rbp+3C8h]; this
0x18002630d  mov     r9d, r14d; char *
0x180026310  mov     r8, rsi; unsigned int
0x180026313  mov     edx, 6Fh ; 'o'; void *
0x180026318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002631d  mov     rcx, [rbp+3C8h]; this
0x180026324  mov     r9d, r14d; char *
0x180026327  mov     r8, rsi; unsigned int
0x18002632a  mov     edx, 12Eh; void *
0x18002632f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026334  test    r15, r15
0x180026337  jz      short loc_180026341
0x180026339  mov     rcx, r15; this
0x18002633c  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180026341  mov     rcx, rdi; this
0x180026344  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180026349  jmp     loc_1800263D4
0x18002634e  lea     r8, [rsp+4C0h+var_480]
0x180026353  lea     rdx, [rsp+4C0h+var_488]
0x180026358  lea     rcx, [rbp+3C0h+Name]; unsigned __int16 *
0x18002635f  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180026364  test    eax, eax
0x180026366  jns     short loc_180026399
0x180026368  mov     rcx, [rbp+3C8h]; this
0x18002636f  lea     r8, aWil; "wil"
0x180026376  mov     r9d, eax; char *
0x180026379  mov     edx, 137h; void *
0x18002637e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026383  lea     rcx, [rsp+4C0h+var_478]
0x180026388  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002638d  mov     rcx, [rsp+4C0h+var_488]
0x180026392  test    rcx, rcx
0x180026395  jz      short loc_1800263D4
0x180026397  jmp     short loc_180026344
0x180026399  mov     rsi, [rsp+4C0h+var_480]
0x18002639e  mov     rdi, [rsp+4C0h+var_488]
0x1800263a3  test    r15, r15
0x1800263a6  jz      short loc_1800263B0
0x1800263a8  mov     rcx, r15; this
0x1800263ab  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800263b0  test    rdi, rdi
0x1800263b3  jz      short loc_1800263C8
0x1800263b5  mov     rcx, rdi; this
0x1800263b8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800263bd  jmp     short loc_1800263C8
0x1800263bf  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800263c4  test    eax, eax
0x1800263c6  js      short loc_1800263D4
0x1800263c8  cmp     [r12+8], r14
0x1800263cd  jnz     short loc_1800263D4
0x1800263cf  mov     [r12+8], rsi
0x1800263d4  mov     rax, [r12+8]
0x1800263d9  lea     rcx, [rax+20h]
0x1800263dd  neg     rax
0x1800263e0  sbb     rax, rax
0x1800263e3  and     rax, rcx
0x1800263e6  mov     rcx, [rbp+3C0h+var_50]
0x1800263ed  xor     rcx, rsp; StackCookie
0x1800263f0  call    __security_check_cookie
0x1800263f5  add     rsp, 488h
0x1800263fc  pop     r15
0x1800263fe  pop     r14
0x180026400  pop     r13
0x180026402  pop     r12
0x180026404  pop     rdi
0x180026405  pop     rsi
0x180026406  pop     rbx
0x180026407  pop     rbp
0x180026408  retn
```
