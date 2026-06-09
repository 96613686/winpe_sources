# Streaming::StrmGlobalData::LoadFilter(_DRIVER_OBJECT *)

- ea: `0x140001204`
- end: `0x14000157c`
- name: `?LoadFilter@StrmGlobalData@Streaming@@QEAAJPEAU_DRIVER_OBJECT@@@Z`
- size: `888`
- prototype: `int(Streaming::StrmGlobalData *__hidden this, struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400135b4`

## callees

- `0x140001204`
- `0x140001698`
- `0x1400053a4`
- `0x140013d84`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x140001436`
- `ntoskrnl!ExInitializeResourceLite` at `0x140001436`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000135f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001465`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000135f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001465`
- `ntoskrnl!ExAllocatePool2` at `0x140001345`
- `ntoskrnl!ExAllocatePool2` at `0x1400013ec`
- `ntoskrnl!ExAllocatePool2` at `0x140001417`
- `ntoskrnl!ExAllocatePool2` at `0x140001345`
- `ntoskrnl!ExAllocatePool2` at `0x1400013ec`
- `ntoskrnl!ExAllocatePool2` at `0x140001417`
- `FLTMGR!FltStartFiltering` at `0x1400014f1`
- `FLTMGR!FltStartFiltering` at `0x1400014f1`
- `FLTMGR!FltRegisterFilter` at `0x1400012bd`
- `FLTMGR!FltRegisterFilter` at `0x1400012bd`

## string_xrefs

- `0x140001486`: `\StrmFltCommunicationClientServerPort`
- `0x1400014b8`: `StrmGlobalData::LoadFilter() - The streaming filter could not open connection port with user mode applications. Failure Status 0x%08X.`
- `0x1400014c4`: `\StrmFltCommunicationServerClientPort`

## pseudocode

```c
NTSTATUS __fastcall Streaming::StrmGlobalData::LoadFilter(Streaming::StrmGlobalData *this, struct _DRIVER_OBJECT *a2)
{
  PFLT_FILTER *v2; // r14
  __int64 v4; // rdx
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v6; // rbx
  NTSTATUS v7; // edi
  __int64 *v8; // rax
  volatile signed __int32 *v9; // rbx
  NTSTATUS result; // eax
  __int64 Pool2; // rax
  PFLT_FILTER v12; // rcx
  __int64 v13; // rbx
  __int64 *v14; // rax
  volatile signed __int32 *v15; // rbx
  __int64 v16; // rax
  struct _FLT_FILTER *v17; // rbx
  struct _ERESOURCE *v18; // rax
  PFLT_FILTER v19; // r15
  __int64 v20; // r8
  __int64 *v21; // rax
  __int64 *v22; // rax
  _QWORD v23[2]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v24[2]; // [rsp+30h] [rbp-20h] BYREF
  char v25[8]; // [rsp+40h] [rbp-10h] BYREF
  volatile signed __int32 *v26; // [rsp+48h] [rbp-8h]

  v2 = (PFLT_FILTER *)Streaming::gStrmFltData;
  McGenEventRegister_EtwRegister(
    PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS,
    a2,
    PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
    PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context);
  McGenEventRegister_EtwRegister(
    PROVIDER_MICROSOFT_APPV_CLIENT,
    v4,
    PROVIDER_MICROSOFT_APPV_CLIENT_Context,
    PROVIDER_MICROSOFT_APPV_CLIENT_Context);
  CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v25);
  LogWrite(4, *CurrentActivityID, L"StrmGlobalData::LoadFilter() - Filter driver is loaded.");
  v6 = v26;
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  v7 = FltRegisterFilter(a2, &Registration, v2 + 1);
  if ( v7 < 0 )
  {
LABEL_6:
    v8 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v25);
    LogWrite(
      1,
      *v8,
      L"StrmGlobalData::LoadFilter() - Microsoft Windows Streaming Mini-Filter failed to load with status 0x%08X.",
      (unsigned int)v7);
    goto LABEL_7;
  }
  Pool2 = ExAllocatePool2(64, 1, 1769170547);
  v12 = v2[2];
  v13 = Pool2;
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  v2[2] = (PFLT_FILTER)v13;
  if ( !v13 )
  {
    v14 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v25);
    LogWrite(1, *v14, L"StrmGlobalData::LoadFilter() - Low memory error.");
    v15 = v26;
    if ( !v26 )
      return -1073741670;
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) != 1 )
      return -1073741670;
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) != 1 )
      return -1073741670;
    goto LABEL_37;
  }
  v16 = ExAllocatePool2(256, 32, 1667851891);
  v17 = (struct _FLT_FILTER *)v16;
  if ( v16 )
  {
    *(_DWORD *)(v16 + 16) = 1667851891;
    *(_QWORD *)(v16 + 24) = 0;
    v18 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 1667851891);
    *((_QWORD *)v17 + 3) = v18;
    if ( v18 )
      v7 = ExInitializeResourceLite(v18);
    else
      v7 = -1073741670;
    *((_QWORD *)v17 + 1) = v17;
    *(_QWORD *)v17 = v17;
  }
  else
  {
    v17 = 0;
  }
  v19 = v2[3];
  if ( v19 )
  {
    Streaming::Messaging::UserCommunication::~UserCommunication(v2[3]);
    ExFreePoolWithTag(v19, 0);
  }
  v2[3] = v17;
  if ( !v17 || v7 < 0 )
  {
    v22 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v25);
    LogWrite(1, *v22, L"StrmGlobalData::LoadFilter() - Low memory error.");
    v15 = v26;
    if ( !v26 )
      return -1073741670;
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) != 1 )
      return -1073741670;
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) != 1 )
      return -1073741670;
LABEL_37:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
    return -1073741670;
  }
  v23[0] = 4980810;
  v23[1] = L"\\StrmFltCommunicationClientServerPort";
  v7 = Streaming::Messaging::UserCommunication::InitializeConnection(v2 + 5, v23, 0);
  if ( v7 >= 0 )
  {
    v24[0] = 4980810;
    v24[1] = L"\\StrmFltCommunicationServerClientPort";
    LOBYTE(v20) = 1;
    v7 = Streaming::Messaging::UserCommunication::InitializeConnection(v2 + 4, v24, v20);
    if ( v7 >= 0 )
    {
      result = FltStartFiltering(v2[1]);
      v7 = result;
      if ( result >= 0 )
        return result;
      goto LABEL_6;
    }
  }
  v21 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v25);
  LogWrite(
    1,
    *v21,
    L"StrmGlobalData::LoadFilter() - The streaming filter could not open connection port with user mode applications. Fail"
     "ure Status 0x%08X.",
    (unsigned int)v7);
LABEL_7:
  v9 = v26;
  if ( v26 && _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x140001204  push    rbp
0x140001206  push    rbx
0x140001207  push    rdi
0x140001208  push    r12
0x14000120a  push    r13
0x14000120c  push    r14
0x14000120e  push    r15
0x140001210  mov     rbp, rsp
0x140001213  sub     rsp, 50h
0x140001217  mov     r14, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x14000121e  lea     r8, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140001225  mov     r9, r8
0x140001228  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS
0x14000122f  mov     rdi, rdx
0x140001232  call    McGenEventRegister_EtwRegister
0x140001237  lea     r8, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14000123e  mov     r9, r8
0x140001241  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT
0x140001248  call    McGenEventRegister_EtwRegister
0x14000124d  lea     rcx, [rbp+var_10]
0x140001251  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140001256  lea     r8, aStrmglobaldata_2; "StrmGlobalData::LoadFilter() - Filter d"...
0x14000125d  mov     ecx, 4
0x140001262  mov     rdx, [rax]
0x140001265  call    LogWrite
0x14000126a  mov     rbx, [rbp+var_8]
0x14000126e  or      r13d, 0FFFFFFFFh
0x140001272  test    rbx, rbx
0x140001275  jz      short loc_1400012AF
0x140001277  mov     eax, r13d
0x14000127a  lock xadd [rbx+8], eax
0x14000127f  add     eax, r13d
0x140001282  jnz     short loc_1400012AF
0x140001284  mov     rax, [rbx]
0x140001287  mov     rcx, rbx
0x14000128a  mov     rax, [rax+8]
0x14000128e  call    _guard_dispatch_icall
0x140001293  mov     eax, r13d
0x140001296  lock xadd [rbx+0Ch], eax
0x14000129b  add     eax, r13d
0x14000129e  jnz     short loc_1400012AF
0x1400012a0  mov     rax, [rbx]
0x1400012a3  mov     rcx, rbx
0x1400012a6  mov     rax, [rax+10h]
0x1400012aa  call    _guard_dispatch_icall
0x1400012af  lea     r8, [r14+8]; RetFilter
0x1400012b3  mov     rcx, rdi; Driver
0x1400012b6  lea     rdx, Registration; Registration
0x1400012bd  call    cs:__imp_FltRegisterFilter
0x1400012c4  nop     dword ptr [rax+rax+00h]
0x1400012c9  mov     edi, eax
0x1400012cb  test    eax, eax
0x1400012cd  jns     short loc_140001337
0x1400012cf  lea     rcx, [rbp+var_10]
0x1400012d3  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400012d8  lea     r8, aStrmglobaldata; "StrmGlobalData::LoadFilter() - Microsof"...
0x1400012df  mov     rdx, [rax]
0x1400012e2  mov     r9d, edi
0x1400012e5  mov     ecx, 1
0x1400012ea  call    LogWrite
0x1400012ef  mov     rbx, [rbp+var_8]
0x1400012f3  test    rbx, rbx
0x1400012f6  jz      short loc_140001330
0x1400012f8  mov     eax, r13d
0x1400012fb  lock xadd [rbx+8], eax
0x140001300  add     eax, r13d
0x140001303  jnz     short loc_140001330
0x140001305  mov     rax, [rbx]
0x140001308  mov     rcx, rbx
0x14000130b  mov     rax, [rax+8]
0x14000130f  call    _guard_dispatch_icall
0x140001314  mov     eax, r13d
0x140001317  lock xadd [rbx+0Ch], eax
0x14000131c  add     eax, r13d
0x14000131f  jnz     short loc_140001330
0x140001321  mov     rax, [rbx]
0x140001324  mov     rcx, rbx
0x140001327  mov     rax, [rax+10h]
0x14000132b  call    _guard_dispatch_icall
0x140001330  mov     eax, edi
0x140001332  jmp     loc_14000156B
0x140001337  mov     edx, 1
0x14000133c  mov     r8d, 69736673h
0x140001342  lea     ecx, [rdx+3Fh]
0x140001345  call    cs:__imp_ExAllocatePool2
0x14000134c  nop     dword ptr [rax+rax+00h]
0x140001351  mov     rcx, [r14+10h]; P
0x140001355  mov     rbx, rax
0x140001358  test    rcx, rcx
0x14000135b  jz      short loc_14000136B
0x14000135d  xor     edx, edx; Tag
0x14000135f  call    cs:__imp_ExFreePoolWithTag
0x140001366  nop     dword ptr [rax+rax+00h]
0x14000136b  mov     [r14+10h], rbx
0x14000136f  test    rbx, rbx
0x140001372  jnz     short loc_1400013D9
0x140001374  lea     rcx, [rbp+var_10]
0x140001378  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000137d  lea     r8, aStrmglobaldata_1; "StrmGlobalData::LoadFilter() - Low memo"...
0x140001384  lea     ecx, [rbx+1]
0x140001387  mov     rdx, [rax]
0x14000138a  call    LogWrite
0x14000138f  mov     rbx, [rbp+var_8]
0x140001393  test    rbx, rbx
0x140001396  jz      loc_140001566
0x14000139c  mov     eax, r13d
0x14000139f  lock xadd [rbx+8], eax
0x1400013a4  add     eax, r13d
0x1400013a7  jnz     loc_140001566
0x1400013ad  mov     rax, [rbx]
0x1400013b0  mov     rcx, rbx
0x1400013b3  mov     rax, [rax+8]
0x1400013b7  call    _guard_dispatch_icall
0x1400013bc  mov     eax, r13d
0x1400013bf  lock xadd [rbx+0Ch], eax
0x1400013c4  add     eax, r13d
0x1400013c7  jnz     loc_140001566
0x1400013cd  mov     rax, [rbx]
0x1400013d0  mov     rax, [rax+10h]
0x1400013d4  jmp     loc_14000155E
0x1400013d9  mov     r15d, 63696673h
0x1400013df  mov     edx, 20h ; ' '
0x1400013e4  mov     r8d, r15d
0x1400013e7  mov     ecx, 100h
0x1400013ec  call    cs:__imp_ExAllocatePool2
0x1400013f3  nop     dword ptr [rax+rax+00h]
0x1400013f8  mov     rbx, rax
0x1400013fb  test    rax, rax
0x1400013fe  jz      short loc_14000144D
0x140001400  mov     edx, 68h ; 'h'
0x140001405  mov     [rax+10h], r15d
0x140001409  mov     r8d, r15d
0x14000140c  mov     qword ptr [rax+18h], 0
0x140001414  lea     ecx, [rdx-28h]
0x140001417  call    cs:__imp_ExAllocatePool2
0x14000141e  nop     dword ptr [rax+rax+00h]
0x140001423  mov     [rbx+18h], rax
0x140001427  test    rax, rax
0x14000142a  jnz     short loc_140001433
0x14000142c  mov     edi, 0C000009Ah
0x140001431  jmp     short loc_140001444
0x140001433  mov     rcx, rax; Resource
0x140001436  call    cs:__imp_ExInitializeResourceLite
0x14000143d  nop     dword ptr [rax+rax+00h]
0x140001442  mov     edi, eax
0x140001444  mov     [rbx+8], rbx
0x140001448  mov     [rbx], rbx
0x14000144b  jmp     short loc_14000144F
0x14000144d  xor     ebx, ebx
0x14000144f  mov     r15, [r14+18h]
0x140001453  test    r15, r15
0x140001456  jz      short loc_140001471
0x140001458  mov     rcx, r15; this
0x14000145b  call    ??1UserCommunication@Messaging@Streaming@@QEAA@XZ; Streaming::Messaging::UserCommunication::~UserCommunication(void)
0x140001460  xor     edx, edx; Tag
0x140001462  mov     rcx, r15; P
0x140001465  call    cs:__imp_ExFreePoolWithTag
0x14000146c  nop     dword ptr [rax+rax+00h]
0x140001471  mov     [r14+18h], rbx
0x140001475  test    rbx, rbx
0x140001478  jz      loc_140001508
0x14000147e  test    edi, edi
0x140001480  js      loc_140001508
0x140001486  lea     rax, aStrmfltcommuni; "\\StrmFltCommunicationClientServerPort"
0x14000148d  mov     [rbp+var_30], 4C004Ah
0x140001495  lea     rcx, [r14+28h]
0x140001499  mov     [rbp+var_28], rax
0x14000149d  xor     r8d, r8d
0x1400014a0  lea     rdx, [rbp+var_30]
0x1400014a4  call    ?InitializeConnection@UserCommunication@Messaging@Streaming@@SAJAEAV?$auto_ptr@VUserCommunication@Messaging@Streaming@@UUserCommunicationDelete@23@@kernel@shared@appv@@AEAU_UNICODE_STRING@@_N@Z; Streaming::Messaging::UserCommunication::InitializeConnection(appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete> &,_UNICODE_STRING &,bool)
0x1400014a9  mov     edi, eax
0x1400014ab  test    eax, eax
0x1400014ad  jns     short loc_1400014C4
0x1400014af  lea     rcx, [rbp+var_10]
0x1400014b3  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400014b8  lea     r8, aStrmglobaldata_0; "StrmGlobalData::LoadFilter() - The stre"...
0x1400014bf  jmp     loc_1400012DF
0x1400014c4  lea     rax, aStrmfltcommuni_0; "\\StrmFltCommunicationServerClientPort"
0x1400014cb  mov     [rbp+var_20], 4C004Ah
0x1400014d3  lea     rcx, [r14+20h]
0x1400014d7  mov     [rbp+var_18], rax
0x1400014db  mov     r8b, 1
0x1400014de  lea     rdx, [rbp+var_20]
0x1400014e2  call    ?InitializeConnection@UserCommunication@Messaging@Streaming@@SAJAEAV?$auto_ptr@VUserCommunication@Messaging@Streaming@@UUserCommunicationDelete@23@@kernel@shared@appv@@AEAU_UNICODE_STRING@@_N@Z; Streaming::Messaging::UserCommunication::InitializeConnection(appv::shared::kernel::auto_ptr<Streaming::Messaging::UserCommunication,Streaming::Messaging::UserCommunicationDelete> &,_UNICODE_STRING &,bool)
0x1400014e7  mov     edi, eax
0x1400014e9  test    eax, eax
0x1400014eb  js      short loc_1400014AF
0x1400014ed  mov     rcx, [r14+8]; Filter
0x1400014f1  call    cs:__imp_FltStartFiltering
0x1400014f8  nop     dword ptr [rax+rax+00h]
0x1400014fd  mov     edi, eax
0x1400014ff  test    eax, eax
0x140001501  jns     short loc_14000156B
0x140001503  jmp     loc_1400012CF
0x140001508  lea     rcx, [rbp+var_10]
0x14000150c  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140001511  lea     r8, aStrmglobaldata_1; "StrmGlobalData::LoadFilter() - Low memo"...
0x140001518  mov     ecx, 1
0x14000151d  mov     rdx, [rax]
0x140001520  call    LogWrite
0x140001525  mov     rbx, [rbp+var_8]
0x140001529  test    rbx, rbx
0x14000152c  jz      short loc_140001566
0x14000152e  mov     eax, r13d
0x140001531  lock xadd [rbx+8], eax
0x140001536  add     eax, r13d
0x140001539  jnz     short loc_140001566
0x14000153b  mov     rax, [rbx]
0x14000153e  mov     rcx, rbx
0x140001541  mov     rax, [rax+8]
0x140001545  call    _guard_dispatch_icall
0x14000154a  mov     edx, r13d
0x14000154d  lock xadd [rbx+0Ch], edx
0x140001552  add     edx, r13d
0x140001555  jnz     short loc_140001566
0x140001557  mov     rdx, [rbx]
0x14000155a  mov     rax, [rdx+10h]
0x14000155e  mov     rcx, rbx
0x140001561  call    _guard_dispatch_icall
0x140001566  mov     eax, 0C000009Ah
0x14000156b  add     rsp, 50h
0x14000156f  pop     r15
0x140001571  pop     r14
0x140001573  pop     r13
0x140001575  pop     r12
0x140001577  pop     rdi
0x140001578  pop     rbx
0x140001579  pop     rbp
0x14000157a  retn
```
