# ServiceManager::HandleTrafficUpdate(bool,uint)

- ea: `0x180016a54`
- end: `0x180016b4b`
- name: `?HandleTrafficUpdate@ServiceManager@@AEAAX_NI@Z`
- size: `247`
- prototype: `void __fastcall(ServiceManager *this, char, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x18001e8c0`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180009d0c`
- `0x180009db4`
- `0x180016a54`
- `0x18001a660`
- `0x18001db8c`

## import_xrefs

- `MosStorage!MosStorageGetCurrentLocation` at `0x180016aba`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180016aba`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016a9d`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016ad6`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016a9d`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180016ad6`

## string_xrefs

- `0x180016a8e`: `ServiceManager::HandleTrafficUpdate`
- `0x180016ac7`: `ServiceManager::HandleTrafficUpdate`

## pseudocode

```c
void __fastcall ServiceManager::HandleTrafficUpdate(ServiceManager *this, char a2, unsigned int a3)
{
  int updated; // eax
  int CurrentLocation; // eax
  unsigned __int64 v7; // rdx
  unsigned __int8 v8; // cl
  bool v9; // di
  OfflineMapsTelemetry *v10; // rax
  _BYTE v11[4]; // [rsp+40h] [rbp-688h] BYREF
  int v12; // [rsp+44h] [rbp-684h]
  unsigned int v13; // [rsp+254h] [rbp-474h]
  unsigned int v14; // [rsp+6A0h] [rbp-28h]

  if ( a2 )
  {
    updated = ServiceManager::UpdateTransferPolicies(this);
    if ( updated < 0 )
      ZTraceReportIgnore(updated, "ServiceManager::HandleTrafficUpdate", 3377, this);
  }
  memset_0(v11, 0, 0x670u);
  CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v11);
  if ( CurrentLocation < 0 )
    ZTraceReportIgnore(CurrentLocation, "ServiceManager::HandleTrafficUpdate", 3381, this);
  v9 = v12 != 0;
  if ( OfflineMapsTelemetry::IsEnabled(v8, v7) )
  {
    v10 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::OfflineTransferSpeed_(
      v10,
      a3,
      *(struct _FILETIME *)((char *)this + 4332),
      *((_QWORD *)this + 543),
      v9,
      v13,
      v14);
  }
}

```

## disassembly

```asm
0x180016a54  mov     [rsp+arg_8], rbx
0x180016a59  mov     [rsp+arg_18], rsi
0x180016a5e  push    rdi
0x180016a5f  sub     rsp, 6C0h
0x180016a66  mov     rax, cs:__security_cookie
0x180016a6d  xor     rax, rsp
0x180016a70  mov     [rsp+6C8h+var_18], rax
0x180016a78  mov     esi, r8d
0x180016a7b  mov     rbx, rcx
0x180016a7e  test    dl, dl
0x180016a80  jz      short loc_180016AA3
0x180016a82  call    ?UpdateTransferPolicies@ServiceManager@@AEAAJXZ; ServiceManager::UpdateTransferPolicies(void)
0x180016a87  test    eax, eax
0x180016a89  jns     short loc_180016AA3
0x180016a8b  mov     r9, rbx
0x180016a8e  lea     rdx, aServicemanager_0; "ServiceManager::HandleTrafficUpdate"
0x180016a95  mov     r8d, 0D31h
0x180016a9b  mov     ecx, eax
0x180016a9d  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180016aa3  xor     edx, edx; Val
0x180016aa5  lea     rcx, [rsp+6C8h+var_688]; void *
0x180016aaa  mov     r8d, 670h; Size
0x180016ab0  call    memset_0
0x180016ab5  lea     rcx, [rsp+6C8h+var_688]
0x180016aba  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x180016ac0  test    eax, eax
0x180016ac2  jns     short loc_180016ADC
0x180016ac4  mov     r9, rbx
0x180016ac7  lea     rdx, aServicemanager_0; "ServiceManager::HandleTrafficUpdate"
0x180016ace  mov     r8d, 0D35h
0x180016ad4  mov     ecx, eax
0x180016ad6  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180016adc  cmp     [rsp+6C8h+var_684], 0
0x180016ae1  setnz   dil
0x180016ae5  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180016aea  test    al, al
0x180016aec  jz      short loc_180016B26
0x180016aee  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180016af3  mov     ecx, [rsp+6C8h+var_28]
0x180016afa  mov     edx, esi; unsigned int
0x180016afc  mov     r9, [rbx+10F8h]; unsigned __int64
0x180016b03  mov     r8, [rbx+10ECh]; struct _FILETIME
0x180016b0a  mov     [rsp+6C8h+var_698], ecx; unsigned int
0x180016b0e  mov     ecx, [rsp+6C8h+var_474]
0x180016b15  mov     [rsp+6C8h+var_6A0], ecx; unsigned int
0x180016b19  mov     rcx, rax; this
0x180016b1c  mov     [rsp+6C8h+var_6A8], dil; bool
0x180016b21  call    ?OfflineTransferSpeed_@OfflineMapsTelemetry@@QEAAXIU_FILETIME@@_K_NII@Z; OfflineMapsTelemetry::OfflineTransferSpeed_(uint,_FILETIME,unsigned __int64,bool,uint,uint)
0x180016b26  mov     rcx, [rsp+6C8h+var_18]
0x180016b2e  xor     rcx, rsp; StackCookie
0x180016b31  call    __security_check_cookie
0x180016b36  lea     r11, [rsp+6C8h+var_8]
0x180016b3e  mov     rbx, [r11+18h]
0x180016b42  mov     rsi, [r11+28h]
0x180016b46  mov     rsp, r11
0x180016b49  pop     rdi
0x180016b4a  retn
```
