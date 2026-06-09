# ServiceManager::DeserializeOperationState(IServiceManager::OPERATION_TYPE *)

- ea: `0x180014b3c`
- end: `0x180014bf9`
- name: `?DeserializeOperationState@ServiceManager@@AEAAJPEAW4OPERATION_TYPE@IServiceManager@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, enum IServiceManager::OPERATION_TYPE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001b1a4`

## callees

- `0x180014b3c`
- `0x180020720`
- `0x1800207d0`
- `0x1800208d4`
- `0x180020978`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x180014b7e`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180014b7e`

## string_xrefs

- `0x180014b92`: `AutoUpdateInProgress`
- `0x180014b75`: `ServiceManager::DeserializeOperationState`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::DeserializeOperationState(
        ServiceManager *this,
        enum IServiceManager::OPERATION_TYPE *a2)
{
  int MapsPersistedRegDword; // eax
  __int64 v5; // rcx
  int v6; // r8d
  unsigned int v7; // ecx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r8
  int v13; // [rsp+40h] [rbp+18h] BYREF

  v13 = 0;
  MapsPersistedRegDword = RegUtils::GetMapsPersistedRegDword((__int64)this, L"CurrentOperation", 0, &v13);
  if ( MapsPersistedRegDword >= 0 )
  {
    MapsPersistedRegDword = RegUtils::GetMapsPersistedRegBoolean(v5, L"AutoUpdateInProgress", 0, (char *)this + 4314);
    if ( MapsPersistedRegDword >= 0 )
    {
      MapsPersistedRegDword = RegUtils::GetMapsPersistedRegFileTime(v9, v8, 0, (char *)this + 4332);
      if ( MapsPersistedRegDword >= 0 )
      {
        MapsPersistedRegDword = RegUtils::GetMapsPersistedRegQword(
                                  v10,
                                  L"CurrentOperationActiveTime",
                                  v11,
                                  (char *)this + 4344);
        if ( MapsPersistedRegDword >= 0 )
        {
          v7 = 0;
          *(_DWORD *)a2 = v13;
          return v7;
        }
        v6 = 1261;
      }
      else
      {
        v6 = 1260;
      }
    }
    else
    {
      v6 = 1259;
    }
  }
  else
  {
    v6 = 1258;
  }
  return (unsigned int)ZTraceReportOrigination(
                         MapsPersistedRegDword,
                         "ServiceManager::DeserializeOperationState",
                         v6,
                         this);
}

```

## disassembly

```asm
0x180014b3c  mov     [rsp+arg_0], rbx
0x180014b41  push    rdi
0x180014b42  sub     rsp, 20h
0x180014b46  mov     rdi, rdx
0x180014b49  mov     [rsp+28h+arg_10], 0
0x180014b51  lea     rdx, aCurrentoperati_0; "CurrentOperation"
0x180014b58  xor     r8d, r8d
0x180014b5b  lea     r9, [rsp+28h+arg_10]
0x180014b60  mov     rbx, rcx
0x180014b63  call    ?GetMapsPersistedRegDword@RegUtils@@SAJW4MapsRegKeys@@PEBGKPEAK@Z; RegUtils::GetMapsPersistedRegDword(MapsRegKeys,ushort const *,ulong,ulong *)
0x180014b68  test    eax, eax
0x180014b6a  jns     short loc_180014B88
0x180014b6c  mov     r8d, 4EAh
0x180014b72  mov     r9, rbx
0x180014b75  lea     rdx, aServicemanager_32; "ServiceManager::DeserializeOperationSta"...
0x180014b7c  mov     ecx, eax
0x180014b7e  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180014b84  mov     ecx, eax
0x180014b86  jmp     short loc_180014BEC
0x180014b88  lea     r9, [rbx+10DAh]
0x180014b8f  xor     r8d, r8d
0x180014b92  lea     rdx, aAutoupdateinpr; "AutoUpdateInProgress"
0x180014b99  call    ?GetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_NPEA_N@Z; RegUtils::GetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool,bool *)
0x180014b9e  test    eax, eax
0x180014ba0  jns     short loc_180014BAA
0x180014ba2  mov     r8d, 4EBh
0x180014ba8  jmp     short loc_180014B72
0x180014baa  xor     r8d, r8d
0x180014bad  lea     r9, [rbx+10ECh]
0x180014bb4  call    ?GetMapsPersistedRegFileTime@RegUtils@@SAJW4MapsRegKeys@@PEBGU_FILETIME@@PEAU3@@Z; RegUtils::GetMapsPersistedRegFileTime(MapsRegKeys,ushort const *,_FILETIME,_FILETIME *)
0x180014bb9  test    eax, eax
0x180014bbb  jns     short loc_180014BC5
0x180014bbd  mov     r8d, 4ECh
0x180014bc3  jmp     short loc_180014B72
0x180014bc5  lea     r9, [rbx+10F8h]
0x180014bcc  lea     rdx, aCurrentoperati; "CurrentOperationActiveTime"
0x180014bd3  call    ?GetMapsPersistedRegQword@RegUtils@@SAJW4MapsRegKeys@@PEBG_KPEA_K@Z; RegUtils::GetMapsPersistedRegQword(MapsRegKeys,ushort const *,unsigned __int64,unsigned __int64 *)
0x180014bd8  test    eax, eax
0x180014bda  jns     short loc_180014BE4
0x180014bdc  mov     r8d, 4EDh
0x180014be2  jmp     short loc_180014B72
0x180014be4  mov     eax, [rsp+28h+arg_10]
0x180014be8  xor     ecx, ecx
0x180014bea  mov     [rdi], eax
0x180014bec  mov     rbx, [rsp+28h+arg_0]
0x180014bf1  mov     eax, ecx
0x180014bf3  add     rsp, 20h
0x180014bf7  pop     rdi
0x180014bf8  retn
```
