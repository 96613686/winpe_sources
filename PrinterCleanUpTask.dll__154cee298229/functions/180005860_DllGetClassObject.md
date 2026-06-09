# DllGetClassObject

- ea: `0x180005860`
- end: `0x1800058f8`
- name: `DllGetClassObject`
- size: `152`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003510`
- `0x180003ad4`
- `0x180003e44`
- `0x180003ef8`
- `0x180005860`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v4; // rax
  __int64 v6; // rax
  __int64 *v7; // rax

  v4 = *(_QWORD *)&CLSID_PrinterCleanupTask.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&CLSID_PrinterCleanupTask.Data1 == *(_QWORD *)&rclsid->Data1 )
    v4 = *(_QWORD *)CLSID_PrinterCleanupTask.Data4 - *(_QWORD *)rclsid->Data4;
  if ( !v4 )
    return CWinTaskModuleT<PrinterCleanupTask,&_GUID const CLSID_PrinterCleanupTask>::DllGetClassObject(
             (__int64)rclsid,
             rclsid,
             (__int64)riid,
             ppv);
  v6 = *(_QWORD *)&CLSID_PrintJobCleanupTask.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&CLSID_PrintJobCleanupTask.Data1 == *(_QWORD *)&rclsid->Data1 )
    v6 = *(_QWORD *)CLSID_PrintJobCleanupTask.Data4 - *(_QWORD *)rclsid->Data4;
  if ( !v6 )
    return CWinTaskModuleT<PrintJobCleanupTask,&_GUID const CLSID_PrintJobCleanupTask>::DllGetClassObject(
             (__int64)rclsid,
             rclsid,
             (__int64)riid,
             ppv);
  v7 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  return Microsoft::WRL::Details::GetClassObject<1>((Microsoft::WRL::Details *)v7, ppv);
}

```

## disassembly

```asm
0x180005860  mov     [rsp+arg_0], rbx
0x180005865  mov     [rsp+arg_8], rsi
0x18000586a  push    rdi
0x18000586b  sub     rsp, 30h
0x18000586f  mov     rax, qword ptr cs:CLSID_PrinterCleanupTask.Data1
0x180005876  mov     rdi, r8
0x180005879  mov     rsi, rdx
0x18000587c  mov     rbx, rcx
0x18000587f  sub     rax, [rcx]
0x180005882  jnz     short loc_18000588F
0x180005884  mov     rax, qword ptr cs:CLSID_PrinterCleanupTask.Data4
0x18000588b  sub     rax, [rcx+8]
0x18000588f  test    rax, rax
0x180005892  jnz     short loc_1800058A4
0x180005894  mov     r9, rdi
0x180005897  mov     r8, rsi
0x18000589a  mov     rdx, rbx
0x18000589d  call    ?DllGetClassObject@?$CWinTaskModuleT@VPrinterCleanupTask@@$1?CLSID_PrinterCleanupTask@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z; CWinTaskModuleT<PrinterCleanupTask,&_GUID const CLSID_PrinterCleanupTask>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x1800058a2  jmp     short loc_1800058E8
0x1800058a4  mov     rax, qword ptr cs:CLSID_PrintJobCleanupTask.Data1
0x1800058ab  sub     rax, [rcx]
0x1800058ae  jnz     short loc_1800058BB
0x1800058b0  mov     rax, qword ptr cs:CLSID_PrintJobCleanupTask.Data4
0x1800058b7  sub     rax, [rcx+8]
0x1800058bb  test    rax, rax
0x1800058be  jnz     short loc_1800058D0
0x1800058c0  mov     r9, rdi
0x1800058c3  mov     r8, rsi
0x1800058c6  mov     rdx, rbx
0x1800058c9  call    ?DllGetClassObject@?$CWinTaskModuleT@VPrintJobCleanupTask@@$1?CLSID_PrintJobCleanupTask@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z; CWinTaskModuleT<PrintJobCleanupTask,&_GUID const CLSID_PrintJobCleanupTask>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x1800058ce  jmp     short loc_1800058E8
0x1800058d0  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800058d5  mov     r9, rsi
0x1800058d8  mov     [rsp+38h+var_18], rdi; PVOID
0x1800058dd  mov     r8, rbx
0x1800058e0  mov     rcx, rax; this
0x1800058e3  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x1800058e8  mov     rbx, [rsp+38h+arg_0]
0x1800058ed  mov     rsi, [rsp+38h+arg_8]
0x1800058f2  add     rsp, 30h
0x1800058f6  pop     rdi
0x1800058f7  retn
```
