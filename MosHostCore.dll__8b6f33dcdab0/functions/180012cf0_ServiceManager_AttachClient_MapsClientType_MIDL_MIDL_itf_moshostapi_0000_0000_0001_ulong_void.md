# ServiceManager::AttachClient(MapsClientType,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,ulong,void *)

- ea: `0x180012cf0`
- end: `0x180012ef5`
- name: `?AttachClient@ServiceManager@@UEAAJW4MapsClientType@@W4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@KPEAX@Z`
- size: `517`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, unsigned int, __int64)`
- caller_count: `5`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180013870`
- `0x180015200`
- `0x1800157e0`
- `0x18001b068`
- `0x18001b870`

## callees

- `0x180009c04`
- `0x180009e8c`
- `0x180012cf0`
- `0x1800134b8`
- `0x180014c00`
- `0x180015898`
- `0x18001bcc0`
- `0x18001d870`
- `0x1800205ec`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180012d7f`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180012d7f`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180012ea9`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180012ea9`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180012d97`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180012d97`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180012d47`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180012d47`

## string_xrefs

- `0x180012d26`: `ServiceManager::AttachClient`
- `0x180012d76`: `MapPlatformConfig::GetOfflineMapsSupport`

## pseudocode

```c
__int64 __fastcall ServiceManager::AttachClient(__int64 a1, unsigned int a2, int a3, unsigned int a4, __int64 a5)
{
  char v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // r8d
  int v14; // ecx
  int v15; // eax
  int v16; // edi
  int MapsImmutableRegBoolean; // eax
  int v18; // eax
  int v19; // r8d
  ServiceManager *v20; // rcx
  int v21; // eax
  int v22; // eax
  _BYTE v24[56]; // [rsp+20h] [rbp-38h] BYREF
  char v25; // [rsp+60h] [rbp+8h] BYREF

  v9 = 0;
  CriticalSectionWithConditionVariable::Lock(a1 + 3400, v24);
  if ( *(_BYTE *)(a1 + 4315) )
  {
    v13 = 1420;
    v14 = -2147023641;
LABEL_3:
    v15 = ZTraceReportOrigination(v14, "ServiceManager::AttachClient", v13, (const void *)a1);
LABEL_4:
    v16 = v15;
    goto LABEL_30;
  }
  if ( !*(_DWORD *)(a1 + 4324) )
  {
    v25 = 1;
    MapsImmutableRegBoolean = RegUtils::GetMapsImmutableRegBoolean(v11, v10, v12, &v25);
    if ( MapsImmutableRegBoolean >= 0 )
    {
      *(_DWORD *)(a1 + 4324) = (v25 != 0) + 1;
    }
    else
    {
      v18 = ZTraceReportPropagationNoThis(MapsImmutableRegBoolean, "MapPlatformConfig::GetOfflineMapsSupport", 279);
      if ( v18 < 0 )
      {
        v19 = 1424;
LABEL_9:
        v15 = ZTraceReportPropagation(v18, "ServiceManager::AttachClient", v19, (const void *)a1);
        goto LABEL_4;
      }
    }
  }
  if ( a2 )
  {
    if ( *(_DWORD *)(a1 + 4324) != 2 )
    {
      v13 = 1428;
      v14 = -2080374761;
      goto LABEL_3;
    }
    if ( a2 == 1 )
      *(_DWORD *)(a1 + 4328) = a3;
  }
  else if ( *(_DWORD *)(a1 + 3524) == 7 )
  {
    v21 = ServiceManager::CancelOperationAndWait(a1, 1);
    if ( v21 < 0 )
    {
      v13 = 1441;
      goto LABEL_21;
    }
  }
  v18 = ClientsTracker::Register(a1 + 3816, a4, a2, a5);
  if ( v18 < 0 )
  {
    v19 = 1449;
    goto LABEL_9;
  }
  v9 = 1;
  switch ( a2 )
  {
    case 0u:
      goto LABEL_36;
    case 3u:
      ServiceManager::UninitializeService((ServiceManager *)a1);
      break;
    case 5u:
LABEL_36:
      v21 = ServiceManager::SetMapsRegDateToNow(v20, L"LastMosHostConnection");
      if ( v21 >= 0 )
        break;
      v13 = 1460;
LABEL_21:
      v14 = v21;
      goto LABEL_3;
  }
  v16 = 0;
  if ( !(unsigned __int8)ClientsTracker::HasClientsOf(a1 + 3816, 3) && a2 != 4 )
  {
    v16 = ServiceManager::EnsureServiceInitialized(a1, a2);
    if ( v16 < 0 && a2 == 1 )
      v16 = 0x4000000;
  }
LABEL_30:
  RelockableGate::~RelockableGate((RelockableGate *)v24);
  if ( v16 < 0 )
  {
    if ( v9 )
    {
      v22 = ServiceManager::DetachClient(a1, a2, a4);
      if ( v22 < 0 )
        ZTraceReportIgnore(v22, "ServiceManager::AttachClient", 1480, (const void *)a1);
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180012cf0  mov     [rsp+arg_8], rbx
0x180012cf5  mov     [rsp+arg_10], rbp
0x180012cfa  push    rsi
0x180012cfb  push    rdi
0x180012cfc  push    r13
0x180012cfe  push    r14
0x180012d00  push    r15
0x180012d02  sub     rsp, 30h
0x180012d06  mov     r15d, r9d
0x180012d09  mov     edi, r8d
0x180012d0c  mov     esi, edx
0x180012d0e  mov     rbx, rcx
0x180012d11  xor     r14b, r14b
0x180012d14  add     rcx, 0D48h
0x180012d1b  lea     rdx, [rsp+58h+var_38]
0x180012d20  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180012d25  nop
0x180012d26  lea     r13, aServicemanager_28; "ServiceManager::AttachClient"
0x180012d2d  cmp     [rbx+10DBh], r14b
0x180012d34  jz      short loc_180012D54
0x180012d36  mov     r8d, 58Ch
0x180012d3c  mov     ecx, 800704E7h
0x180012d41  mov     r9, rbx
0x180012d44  mov     rdx, r13
0x180012d47  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180012d4d  mov     edi, eax
0x180012d4f  jmp     loc_180012E77
0x180012d54  cmp     dword ptr [rbx+10E4h], 0
0x180012d5b  jnz     short loc_180012DB1
0x180012d5d  mov     [rsp+58h+arg_0], 1
0x180012d62  lea     r9, [rsp+58h+arg_0]
0x180012d67  call    ?GetMapsImmutableRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z; RegUtils::GetMapsImmutableRegBoolean(MapsRegKeys,ushort const *,bool,bool *)
0x180012d6c  test    eax, eax
0x180012d6e  jns     short loc_180012D9F
0x180012d70  mov     r8d, 117h
0x180012d76  lea     rdx, aMapplatformcon; "MapPlatformConfig::GetOfflineMapsSuppor"...
0x180012d7d  mov     ecx, eax
0x180012d7f  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180012d85  test    eax, eax
0x180012d87  jns     short loc_180012DB1
0x180012d89  mov     r8d, 590h
0x180012d8f  mov     r9, rbx
0x180012d92  mov     rdx, r13
0x180012d95  mov     ecx, eax
0x180012d97  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180012d9d  jmp     short loc_180012D4D
0x180012d9f  mov     al, [rsp+58h+arg_0]
0x180012da3  neg     al
0x180012da5  sbb     ecx, ecx
0x180012da7  neg     ecx
0x180012da9  inc     ecx
0x180012dab  mov     [rbx+10E4h], ecx
0x180012db1  test    esi, esi
0x180012db3  jz      short loc_180012E02
0x180012db5  cmp     dword ptr [rbx+10E4h], 2
0x180012dbc  jz      short loc_180012DCE
0x180012dbe  mov     r8d, 594h
0x180012dc4  mov     ecx, 84000017h
0x180012dc9  jmp     loc_180012D41
0x180012dce  cmp     esi, 1
0x180012dd1  jnz     short loc_180012DD9
0x180012dd3  mov     [rbx+10E8h], edi
0x180012dd9  lea     rbp, [rbx+0EE8h]
0x180012de0  mov     r9, [rsp+58h+arg_20]
0x180012de8  mov     r8d, esi
0x180012deb  mov     edx, r15d
0x180012dee  mov     rcx, rbp
0x180012df1  call    ?Register@ClientsTracker@@QEAAJKW4MapsClientType@@PEAX@Z; ClientsTracker::Register(ulong,MapsClientType,void *)
0x180012df6  test    eax, eax
0x180012df8  jns     short loc_180012E29
0x180012dfa  mov     r8d, 5A9h
0x180012e00  jmp     short loc_180012D8F
0x180012e02  cmp     dword ptr [rbx+0DC4h], 7
0x180012e09  jnz     short loc_180012DD9
0x180012e0b  mov     edx, 1
0x180012e10  mov     rcx, rbx
0x180012e13  call    ?CancelOperationAndWait@ServiceManager@@AEAAJW4CANCELLATION_TYPE@1@@Z; ServiceManager::CancelOperationAndWait(ServiceManager::CANCELLATION_TYPE)
0x180012e18  test    eax, eax
0x180012e1a  jns     short loc_180012DD9
0x180012e1c  mov     r8d, 5A1h
0x180012e22  mov     ecx, eax
0x180012e24  jmp     loc_180012D41
0x180012e29  mov     r14b, 1
0x180012e2c  test    esi, esi
0x180012e2e  jz      loc_180012ED5
0x180012e34  cmp     esi, 3
0x180012e37  jz      loc_180012EC8
0x180012e3d  cmp     esi, 5
0x180012e40  jz      loc_180012ED5
0x180012e46  xor     edi, edi
0x180012e48  lea     edx, [rdi+3]
0x180012e4b  mov     rcx, rbp
0x180012e4e  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x180012e53  test    al, al
0x180012e55  jnz     short loc_180012E77
0x180012e57  cmp     esi, 4
0x180012e5a  jz      short loc_180012E77
0x180012e5c  mov     edx, esi
0x180012e5e  mov     rcx, rbx
0x180012e61  call    ?EnsureServiceInitialized@ServiceManager@@AEAAJW4MapsClientType@@@Z; ServiceManager::EnsureServiceInitialized(MapsClientType)
0x180012e66  mov     edi, eax
0x180012e68  test    eax, eax
0x180012e6a  jns     short loc_180012E77
0x180012e6c  mov     eax, 4000000h
0x180012e71  cmp     esi, 1
0x180012e74  cmovz   edi, eax
0x180012e77  lea     rcx, [rsp+58h+var_38]; this
0x180012e7c  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180012e81  test    edi, edi
0x180012e83  jns     short loc_180012EAF
0x180012e85  test    r14b, r14b
0x180012e88  jz      short loc_180012EAF
0x180012e8a  mov     r8d, r15d
0x180012e8d  mov     edx, esi
0x180012e8f  mov     rcx, rbx
0x180012e92  call    ?DetachClient@ServiceManager@@UEAAJW4MapsClientType@@K@Z; ServiceManager::DetachClient(MapsClientType,ulong)
0x180012e97  test    eax, eax
0x180012e99  jns     short loc_180012EAF
0x180012e9b  mov     r9, rbx
0x180012e9e  mov     r8d, 5C8h
0x180012ea4  mov     rdx, r13
0x180012ea7  mov     ecx, eax
0x180012ea9  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180012eaf  mov     eax, edi
0x180012eb1  mov     rbx, [rsp+58h+arg_8]
0x180012eb6  mov     rbp, [rsp+58h+arg_10]
0x180012ebb  add     rsp, 30h
0x180012ebf  pop     r15
0x180012ec1  pop     r14
0x180012ec3  pop     r13
0x180012ec5  pop     rdi
0x180012ec6  pop     rsi
0x180012ec7  retn
0x180012ec8  mov     rcx, rbx; this
0x180012ecb  call    ?UninitializeService@ServiceManager@@AEAAXXZ; ServiceManager::UninitializeService(void)
0x180012ed0  jmp     loc_180012E46
0x180012ed5  lea     rdx, aLastmoshostcon; "LastMosHostConnection"
0x180012edc  call    ?SetMapsRegDateToNow@ServiceManager@@AEAAJPEBG@Z; ServiceManager::SetMapsRegDateToNow(ushort const *)
0x180012ee1  test    eax, eax
0x180012ee3  jns     loc_180012E46
0x180012ee9  mov     r8d, 5B4h
0x180012eef  jmp     loc_180012E22
```
