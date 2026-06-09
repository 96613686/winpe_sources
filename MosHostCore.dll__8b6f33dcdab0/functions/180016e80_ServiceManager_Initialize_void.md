# ServiceManager::Initialize(void)

- ea: `0x180016e80`
- end: `0x180016f1a`
- name: `?Initialize@ServiceManager@@UEAAJXZ`
- size: `154`
- prototype: `int __fastcall(ServiceManager *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x180013e7c`
- `0x180016e80`
- `0x180018120`
- `0x18001f224`
- `0x180022a54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180016ed7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x180016ed7`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180016f0b`

## string_xrefs

- `0x180016ef7`: `ServiceManager::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall ServiceManager::Initialize(ServiceManager *this)
{
  ServiceManager *v1; // rbx
  unsigned __int64 v2; // rdx
  unsigned __int8 v3; // cl
  OfflineMapsTelemetry *v4; // rax
  int Instance; // eax

  v1 = this;
  LOBYTE(this) = 1;
  MapPlatformConfig::GetChinaVariant((__int64)this);
  *((_BYTE *)v1 + 4317) = MapPlatformConfig::GetChinaVariant(0);
  if ( OfflineMapsTelemetry::IsEnabled(v3, v2) )
  {
    v4 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::MapsBrokerServiceSetUp_(v4, 0, *((_BYTE *)v1 + 4317));
  }
  ServiceManager::CollectChinaVariantTelemetry(v1);
  if ( qword_180035650 )
    __int2c();
  qword_180035650 = (__int64)SetUnhandledExceptionFilter(ProcessUnhandledException);
  Instance = Threadpool::CreateInstance((__int64 *)v1 + 424);
  if ( Instance >= 0 )
    return 0;
  else
    return ZTraceReportPropagation(Instance, "ServiceManager::Initialize", 177, v1);
}

```

## disassembly

```asm
0x180016e80  push    rbx
0x180016e82  sub     rsp, 20h
0x180016e86  mov     rbx, rcx
0x180016e89  mov     cl, 1; bool
0x180016e8b  call    ?GetChinaVariant@MapPlatformConfig@@CA_N_N@Z; MapPlatformConfig::GetChinaVariant(bool)
0x180016e90  xor     ecx, ecx; bool
0x180016e92  call    ?GetChinaVariant@MapPlatformConfig@@CA_N_N@Z; MapPlatformConfig::GetChinaVariant(bool)
0x180016e97  mov     [rbx+10DDh], al
0x180016e9d  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180016ea2  test    al, al
0x180016ea4  jz      short loc_180016EBC
0x180016ea6  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180016eab  mov     r8b, [rbx+10DDh]; bool
0x180016eb2  xor     edx, edx; bool
0x180016eb4  mov     rcx, rax; this
0x180016eb7  call    ?MapsBrokerServiceSetUp_@OfflineMapsTelemetry@@QEAAX_N0@Z; OfflineMapsTelemetry::MapsBrokerServiceSetUp_(bool,bool)
0x180016ebc  mov     rcx, rbx; this
0x180016ebf  call    ?CollectChinaVariantTelemetry@ServiceManager@@AEAAXXZ; ServiceManager::CollectChinaVariantTelemetry(void)
0x180016ec4  cmp     cs:qword_180035650, 0
0x180016ecc  jz      short loc_180016ED0
0x180016ece  int     2Ch; Windows NT - assertion failure
0x180016ed0  lea     rcx, ProcessUnhandledException; lpTopLevelExceptionFilter
0x180016ed7  call    cs:__imp_SetUnhandledExceptionFilter
0x180016edd  lea     rcx, [rbx+0D40h]
0x180016ee4  mov     cs:qword_180035650, rax
0x180016eeb  call    ?CreateInstance@Threadpool@@SAJPEAV?$unique_ptr@VThreadpool@@U?$default_delete@VThreadpool@@@std@@@std@@@Z; Threadpool::CreateInstance(std::unique_ptr<Threadpool> *)
0x180016ef0  test    eax, eax
0x180016ef2  jns     short loc_180016F12
0x180016ef4  mov     r9, rbx
0x180016ef7  lea     rdx, aServicemanager_54; "ServiceManager::Initialize"
0x180016efe  mov     r8d, 0B1h
0x180016f04  mov     ecx, eax
0x180016f06  add     rsp, 20h
0x180016f0a  pop     rbx
0x180016f0b  jmp     cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180016f12  xor     eax, eax
0x180016f14  add     rsp, 20h
0x180016f18  pop     rbx
0x180016f19  retn
```
