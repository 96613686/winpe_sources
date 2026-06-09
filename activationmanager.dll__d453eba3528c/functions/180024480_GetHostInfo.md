# GetHostInfo

- ea: `0x180024480`
- end: `0x180024767`
- name: `GetHostInfo`
- size: `743`
- prototype: `__int64 __fastcall(int, int, int, int, GUID *pguid, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023f20`

## callees

- `0x18000b5c0`
- `0x180024480`
- `0x180024770`
- `0x180024840`
- `0x1800248f0`
- `0x180044514`
- `0x18005ae90`
- `0x18005ba40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800244d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800244d2`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800244df`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800244df`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180024659`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180024659`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x18002460c`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x18002460c`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002453d`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18002453d`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x180024596`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x180024596`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x180024580`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x180024580`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdRetrieveDynamicId` at `0x1800246fa`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdRetrieveDynamicId` at `0x1800246fa`

## pseudocode

```c
int __fastcall GetHostInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        GUID *pguid,
        __int64 a6,
        unsigned __int16 *a7)
{
  DWORD CurrentProcessId; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int Key; // eax
  unsigned __int64 v17; // rdx
  unsigned __int8 v18; // cl
  int v19; // eax
  int v20; // eax
  AAMTraceProvider *v21; // rcx
  int KeyWithDynamicId; // eax
  HRESULT Guid; // eax
  HRESULT v25; // r12d
  __int64 v26; // rax
  int DynamicId; // eax
  int v28; // [rsp+20h] [rbp-498h]
  DWORD pSessionId[4]; // [rsp+40h] [rbp-478h] BYREF
  _BYTE v30[1056]; // [rsp+50h] [rbp-468h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+0h]

  pSessionId[0] = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, pSessionId);
  if ( *a4 == -1 || *(_DWORD *)(a1 + 60) == 1 && (*(_DWORD *)(a1 + 56) & 0x400000) == 0 )
  {
    if ( *(_DWORD *)(a1 + 60) != 1 || (*(_DWORD *)(a1 + 56) & 0x400000) != 0 )
    {
      Guid = CoCreateGuid(pguid);
      v25 = Guid;
      if ( Guid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
          (const char *)(unsigned int)Guid,
          v28);
        return v25;
      }
    }
    v11 = *(_QWORD *)&GUID_NULL.Data1;
    v12 = *(_QWORD *)GUID_NULL.Data4;
  }
  else
  {
    DynamicId = HamHostIdRetrieveDynamicId(a2, pSessionId[0], *a4, pguid);
    if ( DynamicId < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x4B,
               (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
               (const char *)(unsigned int)DynamicId,
               v28);
    v11 = *(_QWORD *)&GUID_NULL.Data1;
    v12 = *(_QWORD *)GUID_NULL.Data4;
    v26 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&pguid->Data1;
    if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&pguid->Data1 )
      v26 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)pguid->Data4;
    if ( !v26 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
        (const char *)0x80070057LL,
        v28);
      return -2147024809;
    }
  }
  v13 = *(_QWORD *)&pguid->Data1 - v11;
  if ( *(_QWORD *)&pguid->Data1 == v11 )
    v13 = *(_QWORD *)pguid->Data4 - v12;
  v14 = *(_QWORD *)(a1 + 16);
  v15 = *(_QWORD *)(a1 + 40);
  if ( v13 )
  {
    KeyWithDynamicId = PsmCreateKeyWithDynamicId(v15, v14, pguid, a7);
    if ( KeyWithDynamicId < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x57,
               (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
               (const char *)(unsigned int)KeyWithDynamicId,
               a6);
  }
  else
  {
    Key = PsmCreateKey(v15, v14, a7, a6);
    if ( Key < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x5B,
               (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
               (const char *)(unsigned int)Key,
               v28);
  }
  if ( *a4 != -1 )
    goto LABEL_32;
  memset_0(v30, 0, 0x418u);
  v19 = HamHostIdInitializeKey(a7, a2, pSessionId[0], 0);
  if ( v19 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x62,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
             (const char *)(unsigned int)v19,
             0);
  v20 = HamHostIdFindOrCreate(v30, a4);
  if ( v20 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x63,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostresolver.cpp",
             (const char *)(unsigned int)v20,
             0);
LABEL_32:
  if ( AAMTraceProvider::IsEnabled(v18, v17) )
  {
    AAMTraceProvider::Instance();
    AAMTraceProvider::GetHostInfo_(
      v21,
      *(_QWORD *)a1,
      *(_QWORD *)(a1 + 8),
      *(const unsigned __int16 **)(a1 + 24),
      *a4,
      pguid,
      a7);
  }
  return 0;
}

```

## disassembly

```asm
0x180024480  mov     [rsp+arg_10], rbx
0x180024485  push    rbp
0x180024486  push    rsi
0x180024487  push    rdi
0x180024488  push    r12
0x18002448a  push    r13
0x18002448c  push    r14
0x18002448e  push    r15
0x180024490  sub     rsp, 480h
0x180024497  mov     rax, cs:__security_cookie
0x18002449e  xor     rax, rsp
0x1800244a1  mov     [rsp+4B8h+var_48], rax
0x1800244a9  mov     rsi, [rsp+4B8h+pguid]
0x1800244b1  xor     r13d, r13d
0x1800244b4  mov     r14, [rsp+4B8h+arg_28]
0x1800244bc  mov     rdi, r9
0x1800244bf  mov     rbp, [rsp+4B8h+arg_30]
0x1800244c7  mov     r15, rdx
0x1800244ca  mov     [rsp+4B8h+pSessionId], r13d
0x1800244cf  mov     rbx, rcx
0x1800244d2  call    cs:__imp_GetCurrentProcessId
0x1800244d8  mov     ecx, eax; dwProcessId
0x1800244da  lea     rdx, [rsp+4B8h+pSessionId]; pSessionId
0x1800244df  call    cs:__imp_ProcessIdToSessionId
0x1800244e5  mov     r8, [rdi]
0x1800244e8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800244ec  jnz     loc_1800246DD
0x1800244f2  cmp     dword ptr [rbx+3Ch], 1
0x1800244f6  jnz     loc_180024656
0x1800244fc  test    dword ptr [rbx+38h], 400000h
0x180024503  jnz     loc_180024656
0x180024509  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x180024510  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x180024517  mov     rax, [rsi]
0x18002451a  sub     rax, rcx
0x18002451d  jnz     short loc_180024526
0x18002451f  mov     rax, [rsi+8]
0x180024523  sub     rax, rdx
0x180024526  mov     rdx, [rbx+10h]
0x18002452a  mov     rcx, [rbx+28h]
0x18002452e  test    rax, rax
0x180024531  jnz     loc_180024601
0x180024537  mov     r9, r14
0x18002453a  mov     r8, rbp
0x18002453d  call    cs:__imp_PsmCreateKey
0x180024543  test    eax, eax
0x180024545  js      loc_180024725
0x18002454b  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18002454f  jnz     short loc_1800245A4
0x180024551  xor     edx, edx; Val
0x180024553  lea     rcx, [rsp+4B8h+var_468]; void *
0x180024558  mov     r8d, 418h; Size
0x18002455e  call    memset_0
0x180024563  mov     r8d, [rsp+4B8h+pSessionId]
0x180024568  lea     rax, [rsp+4B8h+var_468]
0x18002456d  mov     [rsp+4B8h+var_490], rax
0x180024572  xor     r9d, r9d
0x180024575  mov     rdx, r15
0x180024578  mov     [rsp+4B8h+var_498], r13; int
0x18002457d  mov     rcx, rbp
0x180024580  call    cs:__imp_HamHostIdInitializeKey
0x180024586  test    eax, eax
0x180024588  js      loc_180024638
0x18002458e  mov     rdx, rdi
0x180024591  lea     rcx, [rsp+4B8h+var_468]
0x180024596  call    cs:__imp_HamHostIdFindOrCreate
0x18002459c  test    eax, eax
0x18002459e  js      loc_180024746
0x1800245a4  call    ?IsEnabled@AAMTraceProvider@@SA_NE_K@Z; AAMTraceProvider::IsEnabled(uchar,unsigned __int64)
0x1800245a9  test    al, al
0x1800245ab  jz      short loc_1800245D4
0x1800245ad  call    ?Instance@AAMTraceProvider@@KAPEAV1@XZ; AAMTraceProvider::Instance(void)
0x1800245b2  mov     rax, [rdi]
0x1800245b5  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800245b9  mov     r8, [rbx+8]; unsigned __int64
0x1800245bd  mov     rdx, [rbx]; unsigned __int64
0x1800245c0  mov     [rsp+4B8h+var_488], rbp; unsigned __int16 *
0x1800245c5  mov     [rsp+4B8h+var_490], rsi; struct _GUID *
0x1800245ca  mov     [rsp+4B8h+var_498], rax; unsigned __int64
0x1800245cf  call    ?GetHostInfo_@AAMTraceProvider@@QEAAX_K0PEBG0AEBU_GUID@@1@Z; AAMTraceProvider::GetHostInfo_(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64,_GUID const &,ushort const *)
0x1800245d4  xor     eax, eax
0x1800245d6  mov     rcx, [rsp+4B8h+var_48]
0x1800245de  xor     rcx, rsp; StackCookie
0x1800245e1  call    __security_check_cookie
0x1800245e6  mov     rbx, [rsp+4B8h+arg_10]
0x1800245ee  add     rsp, 480h
0x1800245f5  pop     r15
0x1800245f7  pop     r14
0x1800245f9  pop     r13
0x1800245fb  pop     r12
0x1800245fd  pop     rdi
0x1800245fe  pop     rsi
0x1800245ff  pop     rbp
0x180024600  retn
0x180024601  mov     r9, rbp
0x180024604  mov     [rsp+4B8h+var_498], r14; int
0x180024609  mov     r8, rsi
0x18002460c  call    cs:__imp_PsmCreateKeyWithDynamicId
0x180024612  test    eax, eax
0x180024614  jns     loc_18002454B
0x18002461a  mov     rcx, [rsp+4B8h]; this
0x180024622  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180024629  mov     r9d, eax; char *
0x18002462c  mov     edx, 57h ; 'W'; void *
0x180024631  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180024636  jmp     short loc_1800245D6
0x180024638  mov     rcx, [rsp+4B8h]; this
0x180024640  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180024647  mov     r9d, eax; char *
0x18002464a  mov     edx, 62h ; 'b'; void *
0x18002464f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180024654  jmp     short loc_1800245D6
0x180024656  mov     rcx, rsi; pguid
0x180024659  call    cs:__imp_CoCreateGuid
0x18002465f  mov     r12d, eax
0x180024662  test    eax, eax
0x180024664  jns     loc_180024509
0x18002466a  mov     rcx, [rsp+4B8h]; this
0x180024672  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180024679  mov     r9d, eax; char *
0x18002467c  mov     edx, 51h ; 'Q'; void *
0x180024681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024686  mov     eax, r12d
0x180024689  jmp     loc_1800245D6
0x18002468e  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x180024695  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x18002469c  mov     rax, rcx
0x18002469f  sub     rax, [rsi]
0x1800246a2  jnz     short loc_1800246AB
0x1800246a4  mov     rax, rdx
0x1800246a7  sub     rax, [rsi+8]
0x1800246ab  test    rax, rax
0x1800246ae  jnz     loc_180024517
0x1800246b4  mov     rcx, [rsp+4B8h]; this
0x1800246bc  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800246c3  mov     r9d, 80070057h; char *
0x1800246c9  mov     edx, 4Dh ; 'M'; void *
0x1800246ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246d3  mov     eax, 80070057h
0x1800246d8  jmp     loc_1800245D6
0x1800246dd  cmp     dword ptr [rbx+3Ch], 1
0x1800246e1  jnz     short loc_1800246F0
0x1800246e3  test    dword ptr [rbx+38h], 400000h
0x1800246ea  jz      loc_1800244F2
0x1800246f0  mov     edx, [rsp+4B8h+pSessionId]
0x1800246f4  mov     r9, rsi
0x1800246f7  mov     rcx, r15
0x1800246fa  call    cs:__imp_HamHostIdRetrieveDynamicId
0x180024700  test    eax, eax
0x180024702  jns     short loc_18002468E
0x180024704  mov     rcx, [rsp+4B8h]; this
0x18002470c  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180024713  mov     r9d, eax; char *
0x180024716  mov     edx, 4Bh ; 'K'; void *
0x18002471b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180024720  jmp     loc_1800245D6
0x180024725  mov     rcx, [rsp+4B8h]; this
0x18002472d  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180024734  mov     r9d, eax; char *
0x180024737  mov     edx, 5Bh ; '['; void *
0x18002473c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180024741  jmp     loc_1800245D6
0x180024746  mov     rcx, [rsp+4B8h]; this
0x18002474e  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180024755  mov     r9d, eax; char *
0x180024758  mov     edx, 63h ; 'c'; void *
0x18002475d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180024762  jmp     loc_1800245D6
```
