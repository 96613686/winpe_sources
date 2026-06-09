# ADM_SECURE_DATA::DoClientSideKeyExchange(IUnknown *)

- ea: `0x180003538`
- end: `0x1800039cb`
- name: `?DoClientSideKeyExchange@ADM_SECURE_DATA@@AEAAJPEAUIUnknown@@@Z`
- size: `1171`
- prototype: `__int64 __fastcall(ADM_SECURE_DATA *__hidden this, struct IUnknown *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x180002e90`
- `0x18000413c`

## callees

- `0x180001124`
- `0x180001130`
- `0x180003298`
- `0x180003538`
- `0x1800041ac`
- `0x180004e6c`
- `0x180004eb4`
- `0x180004f68`
- `0x1800053bc`
- `0x180005900`
- `0x180005bd8`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180003591`
- `KERNEL32!GetCurrentThread` at `0x180003591`
- `KERNEL32!GetLastError` at `0x180003744`
- `KERNEL32!GetLastError` at `0x180003755`
- `KERNEL32!GetLastError` at `0x180003990`
- `KERNEL32!GetLastError` at `0x180003744`
- `KERNEL32!GetLastError` at `0x180003755`
- `KERNEL32!GetLastError` at `0x180003990`
- `KERNEL32!CloseHandle` at `0x1800039a8`
- `KERNEL32!CloseHandle` at `0x1800039a8`
- `ADVAPI32!OpenThreadToken` at `0x1800035a8`
- `ADVAPI32!OpenThreadToken` at `0x1800035a8`
- `ADVAPI32!RevertToSelf` at `0x1800035b6`
- `ADVAPI32!RevertToSelf` at `0x1800035b6`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180003986`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180003986`
- `RPCRT4!NdrClientCall2` at `0x18000369a`
- `RPCRT4!NdrClientCall2` at `0x180003702`
- `RPCRT4!NdrClientCall2` at `0x18000369a`
- `RPCRT4!NdrClientCall2` at `0x180003702`
- `ole32!CoTaskMemFree` at `0x180003788`
- `ole32!CoTaskMemFree` at `0x1800037f0`
- `ole32!CoTaskMemFree` at `0x1800038c6`
- `ole32!CoTaskMemFree` at `0x1800038d9`
- `ole32!CoTaskMemFree` at `0x1800038ea`
- `ole32!CoTaskMemFree` at `0x1800038fc`
- `ole32!CoTaskMemFree` at `0x180003920`
- `ole32!CoTaskMemFree` at `0x180003932`
- `ole32!CoTaskMemFree` at `0x180003944`
- `ole32!CoTaskMemFree` at `0x180003956`
- `ole32!CoTaskMemFree` at `0x180003788`
- `ole32!CoTaskMemFree` at `0x1800037f0`
- `ole32!CoTaskMemFree` at `0x1800038c6`
- `ole32!CoTaskMemFree` at `0x1800038d9`
- `ole32!CoTaskMemFree` at `0x1800038ea`
- `ole32!CoTaskMemFree` at `0x1800038fc`
- `ole32!CoTaskMemFree` at `0x180003920`
- `ole32!CoTaskMemFree` at `0x180003932`
- `ole32!CoTaskMemFree` at `0x180003944`
- `ole32!CoTaskMemFree` at `0x180003956`

## pseudocode

```c
__int64 __fastcall ADM_SECURE_DATA::DoClientSideKeyExchange(ADM_SECURE_DATA *this, struct IUnknown *a2)
{
  IIS_CRYPTO_EXCHANGE_CLIENT *v3; // rdi
  _BYTE *v4; // rsi
  struct _IIS_CRYPTO_BLOB *v5; // r14
  ADM_SECURE_DATA *v6; // r13
  HANDLE CurrentThread; // rax
  unsigned __int64 v8; // rbx
  int CryptoProviderHelper; // eax
  IIS_CRYPTO_EXCHANGE_CLIENT *v10; // rax
  unsigned __int64 v11; // r8
  signed int v12; // ebx
  int v13; // eax
  struct _IIS_CRYPTO_BLOB *v14; // r13
  struct _IIS_CRYPTO_BLOB *v15; // r12
  int Pointer; // eax
  int v17; // eax
  _QWORD *v18; // r15
  int HashWorker; // eax
  void *v20; // rcx
  signed int LastError; // eax
  _QWORD *v22; // rax
  unsigned __int64 v23; // r9
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // rdx
  IIS_CRYPTO_STORAGE *v26; // rax
  unsigned __int64 v27; // r9
  IIS_CRYPTO_STORAGE *v28; // rcx
  unsigned __int64 v29; // r8
  unsigned __int64 v30; // rdx
  struct _IIS_CRYPTO_BLOB *v31; // rcx
  struct _IIS_CRYPTO_BLOB *v32; // rcx
  struct _IIS_CRYPTO_BLOB *v33; // rcx
  void *v34; // rcx
  signed int v35; // eax
  struct _IIS_CRYPTO_BLOB **v37; // [rsp+20h] [rbp-60h]
  struct _IIS_CRYPTO_BLOB *v38; // [rsp+40h] [rbp-40h] BYREF
  struct _IIS_CRYPTO_BLOB *v39; // [rsp+48h] [rbp-38h] BYREF
  struct _IIS_CRYPTO_BLOB *v40; // [rsp+50h] [rbp-30h] BYREF
  LPVOID v41; // [rsp+58h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int64 v43; // [rsp+68h] [rbp-18h] BYREF
  struct _IIS_CRYPTO_BLOB *v44; // [rsp+70h] [rbp-10h] BYREF
  struct _IIS_CRYPTO_BLOB *v45; // [rsp+78h] [rbp-8h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp+50h] BYREF
  struct _IIS_CRYPTO_BLOB *v48; // [rsp+D8h] [rbp+58h] BYREF

  v43 = 0;
  v3 = 0;
  v44 = 0;
  v4 = 0;
  v45 = 0;
  v5 = 0;
  pv = 0;
  v6 = this;
  v48 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000000u, 1, &TokenHandle) )
  {
    RevertToSelf();
    goto LABEL_3;
  }
  if ( GetLastError() == 1008 )
  {
LABEL_3:
    v8 = ADM_SECURE_DATA::sm_ClientCryptoProvider;
    if ( !ADM_SECURE_DATA::sm_ClientCryptoProvider )
    {
      CryptoProviderHelper = ADM_SECURE_DATA::GetCryptoProviderHelper(
                               v6,
                               &v43,
                               &ADM_SECURE_DATA::sm_ClientCryptoProvider,
                               0,
                               0);
      if ( CryptoProviderHelper < 0 )
      {
        v12 = CryptoProviderHelper;
        goto LABEL_47;
      }
      v8 = v43;
    }
    v10 = (IIS_CRYPTO_EXCHANGE_CLIENT *)operator new(0x40u);
    v3 = v10;
    if ( !v10 )
    {
      v12 = -2147024888;
      v3 = 0;
      goto LABEL_47;
    }
    *(_QWORD *)v10 = 0;
    *((_DWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 3) = 0;
    *((_QWORD *)v10 + 4) = 0;
    *((_QWORD *)v10 + 5) = 0;
    *((_QWORD *)v10 + 6) = 0;
    *((_QWORD *)v10 + 7) = 0;
    v12 = IIS_CRYPTO_BASE::Initialize(v10, v8, v11, 0, 1);
    if ( v12 < 0 )
      goto LABEL_47;
    v13 = IIS_CRYPTO_EXCHANGE_CLIENT::ClientPhase1(v3, &v44, &v45);
    v14 = v44;
    v12 = v13;
    v15 = v45;
    if ( v13 < 0 )
      goto LABEL_36;
    Pointer = (unsigned int)NdrClientCall2(&pStubDescriptor, &byte_18000B748, a2, v44, v45, &v38, &v39, &v40).Pointer;
    if ( Pointer < 0 )
    {
      v12 = Pointer;
      goto LABEL_36;
    }
    v17 = IIS_CRYPTO_EXCHANGE_CLIENT::ClientPhase2(v3, v38, v39, v40, (struct _IIS_CRYPTO_BLOB **)&pv, &v48);
    v5 = v48;
    v12 = v17;
    v4 = pv;
    if ( v17 < 0 )
      goto LABEL_36;
    v12 = (unsigned int)NdrClientCall2(&pStubDescriptor, &byte_18000B786, a2, pv, v48, &v41).Pointer;
    if ( v12 < 0 )
      goto LABEL_36;
    v18 = v41;
    pv = 0;
    HashWorker = IIS_CRYPTO_EXCHANGE_BASE::CreateHashWorker((HCRYPTPROV *)v3, (struct _IIS_CRYPTO_BLOB **)&pv, 0);
    v20 = pv;
    v12 = HashWorker;
    if ( HashWorker >= 0 )
    {
      if ( !pv )
      {
        v12 = -2147467259;
        goto LABEL_22;
      }
      if ( *v18 == *(_QWORD *)pv )
      {
        *(_BYTE *)pv = 88;
        CoTaskMemFree(v20);
LABEL_23:
        v22 = operator new(0x30u);
        if ( v22 )
        {
          v22[1] = 0;
          *((_DWORD *)v22 + 4) = 0;
          v22[3] = 0;
          v22[4] = 0;
          *v22 = &IIS_CRYPTO_STORAGE::`vftable';
          v22[5] = 0;
        }
        *((_QWORD *)this + 6) = v22;
        if ( v22 )
        {
          v24 = *((_QWORD *)v3 + 5);
          v25 = *(_QWORD *)v3;
          *((_QWORD *)v3 + 5) = 0;
          v12 = IIS_CRYPTO_STORAGE::Initialize((IIS_CRYPTO_STORAGE *)v22, v25, v24, v23, 0, 1);
          if ( v12 < 0 )
            goto LABEL_36;
          v26 = (IIS_CRYPTO_STORAGE *)operator new(0x30u);
          v28 = v26;
          if ( v26 )
          {
            *((_QWORD *)v26 + 1) = 0;
            *((_DWORD *)v26 + 4) = 0;
            *((_QWORD *)v26 + 3) = 0;
            *((_QWORD *)v26 + 4) = 0;
            *(_QWORD *)v26 = &IIS_CRYPTO_STORAGE::`vftable';
            *((_QWORD *)v26 + 5) = 0;
          }
          else
          {
            v28 = 0;
          }
          *((_QWORD *)this + 7) = v28;
          if ( v28 )
          {
            v29 = *((_QWORD *)v3 + 4);
            v30 = *(_QWORD *)v3;
            v37 = (struct _IIS_CRYPTO_BLOB **)*((_QWORD *)v3 + 7);
            *((_QWORD *)v3 + 7) = 0;
            *((_QWORD *)v3 + 4) = 0;
            v12 = IIS_CRYPTO_STORAGE::Initialize(v28, v30, v29, v27, (unsigned __int64)v37, 1);
            if ( v12 >= 0 )
              *((_QWORD *)this + 4) = v3;
            goto LABEL_36;
          }
        }
        v12 = -2147024888;
LABEL_36:
        if ( v14 )
        {
          *(_BYTE *)v14 = 88;
          CoTaskMemFree(v14);
        }
        if ( v15 )
        {
          *(_BYTE *)v15 = 88;
          CoTaskMemFree(v15);
        }
        if ( v4 )
        {
          *v4 = 88;
          CoTaskMemFree(v4);
        }
        if ( v5 )
        {
          *(_BYTE *)v5 = 88;
          CoTaskMemFree(v5);
        }
        v6 = this;
        goto LABEL_47;
      }
      v12 = 13;
    }
    if ( pv )
    {
      *(_BYTE *)pv = 88;
      CoTaskMemFree(v20);
    }
LABEL_22:
    if ( v12 < 0 )
      goto LABEL_36;
    goto LABEL_23;
  }
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_47:
  v31 = v38;
  if ( v38 )
  {
    *(_BYTE *)v38 = 88;
    CoTaskMemFree(v31);
  }
  v32 = v39;
  if ( v39 )
  {
    *(_BYTE *)v39 = 88;
    CoTaskMemFree(v32);
  }
  v33 = v40;
  if ( v40 )
  {
    *(_BYTE *)v40 = 88;
    CoTaskMemFree(v33);
  }
  v34 = v41;
  if ( v41 )
  {
    *(_BYTE *)v41 = 88;
    CoTaskMemFree(v34);
  }
  if ( v12 < 0 )
  {
    if ( v3 )
    {
      IIS_CRYPTO_EXCHANGE_SERVER::~IIS_CRYPTO_EXCHANGE_SERVER(v3);
      operator delete(v3);
    }
    ADM_SECURE_DATA::CleanupCryptoData(v6);
  }
  if ( TokenHandle )
  {
    if ( !ImpersonateLoggedOnUser(TokenHandle) )
    {
      v35 = GetLastError();
      if ( v35 > 0 )
        v35 = (unsigned __int16)v35 | 0x80070000;
      v12 = v35;
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180003538  mov     [rsp-38h+arg_8], rbx
0x18000353d  mov     [rsp-38h+arg_0], rcx
0x180003542  push    rbp
0x180003543  push    rsi
0x180003544  push    rdi
0x180003545  push    r12
0x180003547  push    r13
0x180003549  push    r14
0x18000354b  push    r15
0x18000354d  mov     rbp, rsp
0x180003550  sub     rsp, 80h
0x180003557  xor     r12d, r12d
0x18000355a  mov     r15, rdx
0x18000355d  mov     [rbp+var_18], r12
0x180003561  mov     edi, r12d
0x180003564  mov     [rbp+var_10], r12
0x180003568  mov     esi, r12d
0x18000356b  mov     [rbp+var_8], r12
0x18000356f  mov     r14d, r12d
0x180003572  mov     [rbp+pv], r12
0x180003576  mov     r13, rcx
0x180003579  mov     [rbp+arg_18], r12
0x18000357d  mov     [rbp+var_40], r12
0x180003581  mov     [rbp+var_38], r12
0x180003585  mov     [rbp+var_30], r12
0x180003589  mov     [rbp+var_28], r12
0x18000358d  mov     [rbp+TokenHandle], r12
0x180003591  call    cs:__imp_GetCurrentThread
0x180003597  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000359b  mov     edx, 2000000h; DesiredAccess
0x1800035a0  mov     rcx, rax; ThreadHandle
0x1800035a3  lea     r8d, [r12+1]; OpenAsSelf
0x1800035a8  call    cs:__imp_OpenThreadToken
0x1800035ae  test    eax, eax
0x1800035b0  jz      loc_180003744
0x1800035b6  call    cs:__imp_RevertToSelf
0x1800035bc  mov     rbx, cs:?sm_ClientCryptoProvider@ADM_SECURE_DATA@@0_KA; unsigned __int64 ADM_SECURE_DATA::sm_ClientCryptoProvider
0x1800035c3  test    rbx, rbx
0x1800035c6  jnz     short loc_1800035EF
0x1800035c8  xor     r9d, r9d; char *
0x1800035cb  mov     dword ptr [rsp+80h+var_60], r12d; unsigned int
0x1800035d0  lea     r8, ?sm_ClientCryptoProvider@ADM_SECURE_DATA@@0_KA; unsigned __int64 *
0x1800035d7  mov     rcx, r13; this
0x1800035da  lea     rdx, [rbp+var_18]; unsigned __int64 *
0x1800035de  call    ?GetCryptoProviderHelper@ADM_SECURE_DATA@@AEAAJPEA_K0PEADK@Z; ADM_SECURE_DATA::GetCryptoProviderHelper(unsigned __int64 *,unsigned __int64 *,char *,ulong)
0x1800035e3  test    eax, eax
0x1800035e5  js      loc_180003912
0x1800035eb  mov     rbx, [rbp+var_18]
0x1800035ef  mov     ecx, 40h ; '@'; Size
0x1800035f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800035f9  mov     rdi, rax
0x1800035fc  test    rax, rax
0x1800035ff  jz      loc_180003908
0x180003605  xor     r9d, r9d; unsigned __int64
0x180003608  mov     [rax], r12
0x18000360b  mov     rdx, rbx; unsigned __int64
0x18000360e  mov     [rax+8], r12d
0x180003612  mov     rcx, rax; this
0x180003615  mov     [rax+10h], r12
0x180003619  mov     [rax+18h], r12
0x18000361d  mov     [rax+20h], r12
0x180003621  mov     [rax+28h], r12
0x180003625  mov     [rax+30h], r12
0x180003629  mov     [rax+38h], r12
0x18000362d  mov     dword ptr [rsp+80h+var_60], 1; int
0x180003635  call    ?Initialize@IIS_CRYPTO_BASE@@QEAAJ_K00H@Z; IIS_CRYPTO_BASE::Initialize(unsigned __int64,unsigned __int64,unsigned __int64,int)
0x18000363a  mov     ebx, eax
0x18000363c  test    eax, eax
0x18000363e  js      loc_180003914
0x180003644  lea     r8, [rbp+var_8]; struct _IIS_CRYPTO_BLOB **
0x180003648  mov     rcx, rdi; this
0x18000364b  lea     rdx, [rbp+var_10]; struct _IIS_CRYPTO_BLOB **
0x18000364f  call    ?ClientPhase1@IIS_CRYPTO_EXCHANGE_CLIENT@@QEAAJPEAPEFAU_IIS_CRYPTO_BLOB@@0@Z; IIS_CRYPTO_EXCHANGE_CLIENT::ClientPhase1(_IIS_CRYPTO_BLOB * *,_IIS_CRYPTO_BLOB * *)
0x180003654  mov     r13, [rbp+var_10]
0x180003658  mov     ebx, eax
0x18000365a  mov     r12, [rbp+var_8]
0x18000365e  test    eax, eax
0x180003660  js      loc_1800038B9
0x180003666  lea     rax, [rbp+var_30]
0x18000366a  mov     r9, r13
0x18000366d  mov     [rsp+80h+var_48], rax
0x180003672  lea     rdx, byte_18000B748; pFormat
0x180003679  lea     rax, [rbp+var_38]
0x18000367d  mov     r8, r15
0x180003680  mov     [rsp+80h+var_50], rax
0x180003685  lea     rcx, pStubDescriptor; pStubDescriptor
0x18000368c  lea     rax, [rbp+var_40]
0x180003690  mov     [rsp+80h+var_58], rax
0x180003695  mov     [rsp+80h+var_60], r12
0x18000369a  call    cs:__imp_NdrClientCall2
0x1800036a0  test    eax, eax
0x1800036a2  js      loc_1800038B7
0x1800036a8  mov     r9, [rbp+var_30]; struct _IIS_CRYPTO_BLOB *
0x1800036ac  lea     rax, [rbp+arg_18]
0x1800036b0  mov     r8, [rbp+var_38]; struct _IIS_CRYPTO_BLOB *
0x1800036b4  mov     rcx, rdi; this
0x1800036b7  mov     rdx, [rbp+var_40]; struct _IIS_CRYPTO_BLOB *
0x1800036bb  mov     [rsp+80h+var_58], rax; struct _IIS_CRYPTO_BLOB **
0x1800036c0  lea     rax, [rbp+pv]
0x1800036c4  mov     [rsp+80h+var_60], rax; struct _IIS_CRYPTO_BLOB **
0x1800036c9  call    ?ClientPhase2@IIS_CRYPTO_EXCHANGE_CLIENT@@QEAAJPEFAU_IIS_CRYPTO_BLOB@@00PEAPEFAU2@1@Z; IIS_CRYPTO_EXCHANGE_CLIENT::ClientPhase2(_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB *,_IIS_CRYPTO_BLOB * *,_IIS_CRYPTO_BLOB * *)
0x1800036ce  mov     r14, [rbp+arg_18]
0x1800036d2  mov     ebx, eax
0x1800036d4  mov     rsi, [rbp+pv]
0x1800036d8  test    eax, eax
0x1800036da  js      loc_1800038B9
0x1800036e0  lea     rax, [rbp+var_28]
0x1800036e4  mov     r9, rsi
0x1800036e7  mov     [rsp+80h+var_58], rax
0x1800036ec  lea     rdx, byte_18000B786; pFormat
0x1800036f3  mov     r8, r15
0x1800036f6  mov     [rsp+80h+var_60], r14
0x1800036fb  lea     rcx, pStubDescriptor; pStubDescriptor
0x180003702  call    cs:__imp_NdrClientCall2
0x180003708  mov     rbx, rax
0x18000370b  test    eax, eax
0x18000370d  js      loc_1800038B9
0x180003713  mov     r15, [rbp+var_28]
0x180003717  lea     rdx, [rbp+pv]; struct _IIS_CRYPTO_BLOB **
0x18000371b  xor     r8d, r8d; int
0x18000371e  mov     [rbp+pv], 0
0x180003726  mov     rcx, rdi; this
0x180003729  call    ?CreateHashWorker@IIS_CRYPTO_EXCHANGE_BASE@@AEAAJPEAPEFAU_IIS_CRYPTO_BLOB@@H@Z; IIS_CRYPTO_EXCHANGE_BASE::CreateHashWorker(_IIS_CRYPTO_BLOB * *,int)
0x18000372e  mov     rcx, [rbp+pv]; pv
0x180003732  mov     ebx, eax
0x180003734  test    eax, eax
0x180003736  js      short loc_180003780
0x180003738  test    rcx, rcx
0x18000373b  jnz     short loc_180003773
0x18000373d  mov     ebx, 80004005h
0x180003742  jmp     short loc_18000378E
0x180003744  call    cs:__imp_GetLastError
0x18000374a  cmp     eax, 3F0h
0x18000374f  jz      loc_1800035BC
0x180003755  call    cs:__imp_GetLastError
0x18000375b  mov     ebx, eax
0x18000375d  test    eax, eax
0x18000375f  jle     loc_180003914
0x180003765  movzx   ebx, ax
0x180003768  or      ebx, 80070000h
0x18000376e  jmp     loc_180003914
0x180003773  mov     rax, [r15]
0x180003776  cmp     rax, [rcx]
0x180003779  jz      short loc_1800037ED
0x18000377b  mov     ebx, 0Dh
0x180003780  test    rcx, rcx
0x180003783  jz      short loc_18000378E
0x180003785  mov     byte ptr [rcx], 58h ; 'X'
0x180003788  call    cs:__imp_CoTaskMemFree
0x18000378e  test    ebx, ebx
0x180003790  js      loc_1800038B9
0x180003796  mov     ecx, 30h ; '0'; Size
0x18000379b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800037a0  lea     rcx, ??_7IIS_CRYPTO_STORAGE@@6B@; const IIS_CRYPTO_STORAGE::`vftable'
0x1800037a7  test    rax, rax
0x1800037aa  jz      short loc_1800037D6
0x1800037ac  mov     qword ptr [rax+8], 0
0x1800037b4  mov     dword ptr [rax+10h], 0
0x1800037bb  mov     qword ptr [rax+18h], 0
0x1800037c3  mov     qword ptr [rax+20h], 0
0x1800037cb  mov     [rax], rcx
0x1800037ce  mov     qword ptr [rax+28h], 0
0x1800037d6  mov     r15, [rbp+arg_0]
0x1800037da  mov     [r15+30h], rax
0x1800037de  test    rax, rax
0x1800037e1  jnz     short loc_1800037F8
0x1800037e3  mov     ebx, 80070008h
0x1800037e8  jmp     loc_1800038B9
0x1800037ed  mov     byte ptr [rcx], 58h ; 'X'
0x1800037f0  call    cs:__imp_CoTaskMemFree
0x1800037f6  jmp     short loc_180003796
0x1800037f8  mov     r8, [rdi+28h]; unsigned __int64
0x1800037fc  mov     rcx, rax; this
0x1800037ff  mov     rdx, [rdi]; unsigned __int64
0x180003802  mov     dword ptr [rsp+80h+var_58], 1; int
0x18000380a  mov     qword ptr [rdi+28h], 0
0x180003812  mov     [rsp+80h+var_60], 0; unsigned __int64
0x18000381b  call    ?Initialize@IIS_CRYPTO_STORAGE@@QEAAJ_K000H@Z; IIS_CRYPTO_STORAGE::Initialize(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,int)
0x180003820  mov     ebx, eax
0x180003822  test    eax, eax
0x180003824  js      loc_1800038B9
0x18000382a  mov     ecx, 30h ; '0'; Size
0x18000382f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003834  mov     rcx, rax
0x180003837  test    rax, rax
0x18000383a  jz      short loc_18000386F
0x18000383c  mov     qword ptr [rax+8], 0
0x180003844  mov     dword ptr [rax+10h], 0
0x18000384b  mov     qword ptr [rax+18h], 0
0x180003853  mov     qword ptr [rax+20h], 0
0x18000385b  lea     rax, ??_7IIS_CRYPTO_STORAGE@@6B@; const IIS_CRYPTO_STORAGE::`vftable'
0x180003862  mov     [rcx], rax
0x180003865  mov     qword ptr [rcx+28h], 0
0x18000386d  jmp     short loc_180003871
0x18000386f  xor     ecx, ecx; this
0x180003871  mov     [r15+38h], rcx
0x180003875  test    rcx, rcx
0x180003878  jz      loc_1800037E3
0x18000387e  mov     rax, [rdi+38h]
0x180003882  mov     r8, [rdi+20h]; unsigned __int64
0x180003886  mov     rdx, [rdi]; unsigned __int64
0x180003889  mov     dword ptr [rsp+80h+var_58], 1; int
0x180003891  mov     [rsp+80h+var_60], rax; unsigned __int64
0x180003896  mov     qword ptr [rdi+38h], 0
0x18000389e  mov     qword ptr [rdi+20h], 0
0x1800038a6  call    ?Initialize@IIS_CRYPTO_STORAGE@@QEAAJ_K000H@Z; IIS_CRYPTO_STORAGE::Initialize(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,int)
0x1800038ab  mov     ebx, eax
0x1800038ad  test    eax, eax
0x1800038af  js      short loc_1800038B9
0x1800038b1  mov     [r15+20h], rdi
0x1800038b5  jmp     short loc_1800038B9
0x1800038b7  mov     ebx, eax
0x1800038b9  test    r13, r13
0x1800038bc  jz      short loc_1800038CC
0x1800038be  mov     rcx, r13; pv
0x1800038c1  mov     byte ptr [r13+0], 58h ; 'X'
0x1800038c6  call    cs:__imp_CoTaskMemFree
0x1800038cc  test    r12, r12
0x1800038cf  jz      short loc_1800038DF
0x1800038d1  mov     rcx, r12; pv
0x1800038d4  mov     byte ptr [r12], 58h ; 'X'
0x1800038d9  call    cs:__imp_CoTaskMemFree
0x1800038df  test    rsi, rsi
0x1800038e2  jz      short loc_1800038F0
0x1800038e4  mov     rcx, rsi; pv
0x1800038e7  mov     byte ptr [rsi], 58h ; 'X'
0x1800038ea  call    cs:__imp_CoTaskMemFree
0x1800038f0  test    r14, r14
0x1800038f3  jz      short loc_180003902
0x1800038f5  mov     rcx, r14; pv
0x1800038f8  mov     byte ptr [r14], 58h ; 'X'
0x1800038fc  call    cs:__imp_CoTaskMemFree
0x180003902  mov     r13, [rbp+arg_0]
0x180003906  jmp     short loc_180003914
0x180003908  mov     ebx, 80070008h
0x18000390d  mov     rdi, r12
0x180003910  jmp     short loc_180003914
0x180003912  mov     ebx, eax
0x180003914  mov     rcx, [rbp+var_40]; pv
0x180003918  test    rcx, rcx
0x18000391b  jz      short loc_180003926
0x18000391d  mov     byte ptr [rcx], 58h ; 'X'
0x180003920  call    cs:__imp_CoTaskMemFree
0x180003926  mov     rcx, [rbp+var_38]; pv
0x18000392a  test    rcx, rcx
0x18000392d  jz      short loc_180003938
0x18000392f  mov     byte ptr [rcx], 58h ; 'X'
0x180003932  call    cs:__imp_CoTaskMemFree
0x180003938  mov     rcx, [rbp+var_30]; pv
0x18000393c  test    rcx, rcx
0x18000393f  jz      short loc_18000394A
0x180003941  mov     byte ptr [rcx], 58h ; 'X'
0x180003944  call    cs:__imp_CoTaskMemFree
0x18000394a  mov     rcx, [rbp+var_28]; pv
0x18000394e  test    rcx, rcx
0x180003951  jz      short loc_18000395C
0x180003953  mov     byte ptr [rcx], 58h ; 'X'
0x180003956  call    cs:__imp_CoTaskMemFree
0x18000395c  test    ebx, ebx
0x18000395e  jns     short loc_18000397D
0x180003960  test    rdi, rdi
0x180003963  jz      short loc_180003975
0x180003965  mov     rcx, rdi; this
0x180003968  call    ??1IIS_CRYPTO_EXCHANGE_SERVER@@QEAA@XZ; IIS_CRYPTO_EXCHANGE_SERVER::~IIS_CRYPTO_EXCHANGE_SERVER(void)
0x18000396d  mov     rcx, rdi; Block
0x180003970  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003975  mov     rcx, r13; this
0x180003978  call    ?CleanupCryptoData@ADM_SECURE_DATA@@AEAAXXZ; ADM_SECURE_DATA::CleanupCryptoData(void)
0x18000397d  mov     rcx, [rbp+TokenHandle]; hToken
0x180003981  test    rcx, rcx
0x180003984  jz      short loc_1800039AE
0x180003986  call    cs:__imp_ImpersonateLoggedOnUser
0x18000398c  test    eax, eax
0x18000398e  jnz     short loc_1800039A4
0x180003990  call    cs:__imp_GetLastError
0x180003996  test    eax, eax
0x180003998  jle     short loc_1800039A2
0x18000399a  movzx   eax, ax
0x18000399d  or      eax, 80070000h
0x1800039a2  mov     ebx, eax
0x1800039a4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800039a8  call    cs:__imp_CloseHandle
0x1800039ae  mov     eax, ebx
0x1800039b0  mov     rbx, [rsp+80h+arg_8]
0x1800039b8  add     rsp, 80h
0x1800039bf  pop     r15
0x1800039c1  pop     r14
0x1800039c3  pop     r13
0x1800039c5  pop     r12
0x1800039c7  pop     rdi
0x1800039c8  pop     rsi
0x1800039c9  pop     rbp
0x1800039ca  retn
```
