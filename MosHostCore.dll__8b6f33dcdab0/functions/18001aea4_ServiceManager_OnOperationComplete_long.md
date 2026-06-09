# ServiceManager::OnOperationComplete(long)

- ea: `0x18001aea4`
- end: `0x18001af09`
- name: `?OnOperationComplete@ServiceManager@@AEAAJJ@Z`
- size: `101`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013580`
- `0x1800142c4`
- `0x18001b068`

## callees

- `0x18000fe2c`
- `0x18001aea4`
- `0x18001b79c`
- `0x18001ba6c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001aecf`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001aefb`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001aecf`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001aefb`

## string_xrefs

- `0x18001aec0`: `ServiceManager::OnOperationComplete`
- `0x18001aeec`: `ServiceManager::OnOperationComplete`

## pseudocode

```c
__int64 __fastcall ServiceManager::OnOperationComplete(ServiceManager *this, int a2)
{
  int v3; // eax
  int v4; // eax

  v3 = PackageManager::OnOperationComplete((ServiceManager *)((char *)this + 3568), a2);
  if ( v3 < 0 )
    ZTraceReportIgnore(v3, "ServiceManager::OnOperationComplete", 674, this);
  ServiceManager::ResetOperationState(this);
  v4 = ServiceManager::SerializeOperationState(this);
  if ( v4 < 0 )
    ZTraceReportIgnore(v4, "ServiceManager::OnOperationComplete", 676, this);
  return 0;
}

```

## disassembly

```asm
0x18001aea4  push    rbx
0x18001aea6  sub     rsp, 20h
0x18001aeaa  mov     rbx, rcx
0x18001aead  add     rcx, 0DF0h; this
0x18001aeb4  call    ?OnOperationComplete@PackageManager@@QEAAJJ@Z; PackageManager::OnOperationComplete(long)
0x18001aeb9  test    eax, eax
0x18001aebb  jns     short loc_18001AED5
0x18001aebd  mov     r9, rbx
0x18001aec0  lea     rdx, aServicemanager_89; "ServiceManager::OnOperationComplete"
0x18001aec7  mov     r8d, 2A2h
0x18001aecd  mov     ecx, eax
0x18001aecf  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001aed5  mov     rcx, rbx; this
0x18001aed8  call    ?ResetOperationState@ServiceManager@@AEAAXXZ; ServiceManager::ResetOperationState(void)
0x18001aedd  mov     rcx, rbx; this
0x18001aee0  call    ?SerializeOperationState@ServiceManager@@AEAAJXZ; ServiceManager::SerializeOperationState(void)
0x18001aee5  test    eax, eax
0x18001aee7  jns     short loc_18001AF01
0x18001aee9  mov     r9, rbx
0x18001aeec  lea     rdx, aServicemanager_89; "ServiceManager::OnOperationComplete"
0x18001aef3  mov     r8d, 2A4h
0x18001aef9  mov     ecx, eax
0x18001aefb  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001af01  xor     eax, eax
0x18001af03  add     rsp, 20h
0x18001af07  pop     rbx
0x18001af08  retn
```
