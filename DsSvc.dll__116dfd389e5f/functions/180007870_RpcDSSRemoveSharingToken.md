# RpcDSSRemoveSharingToken

- ea: `0x180007870`
- end: `0x180007937`
- name: `RpcDSSRemoveSharingToken`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800038f8`
- `0x180006070`
- `0x180006cb0`
- `0x180006f78`
- `0x180007870`
- `0x18000bf80`
- `0x18000c100`
- `0x18000c12c`
- `0x18000d7b8`

## string_xrefs

- `0x180007896`: `DSSRemoveSharingToken started.`
- `0x1800078b4`: `DSSRemoveSharingToken finished.`
- `0x1800078e4`: `RpcDSSRemoveSharingToken`

## pseudocode

```c
__int64 __fastcall RpcDSSRemoveSharingToken(void *a1, const unsigned __int16 *a2)
{
  int *v4; // rax
  int v5; // ebx
  __int64 v6; // rcx
  int *v7; // rax
  int *v8; // rax
  __int64 *v9; // rax
  int v11; // [rsp+20h] [rbp-38h]
  _BYTE v12[40]; // [rsp+30h] [rbp-28h] BYREF
  int v13; // [rsp+68h] [rbp+10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  if ( !a2 || !*a2 )
  {
    v5 = -2147024809;
LABEL_6:
    v8 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
    v11 = v5;
    DSLogger::LogError((DSLogger *)v8, L"RpcDSSRemoveSharingToken", 280, L"hr=0x%x.", v11);
    goto LABEL_7;
  }
  v4 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
  DSLogger::LogServiceApiStarted((DSLogger *)v4, L"DSSRemoveSharingToken started.");
  v5 = DSSRemoveSharingToken(a2);
  v7 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v6);
  DSLogger::LogServiceApiCompleted((DSLogger *)v7, L"DSSRemoveSharingToken finished.");
  if ( v5 < 0 )
    goto LABEL_6;
LABEL_7:
  v9 = (__int64 *)RpcClientProcessInfo((__int64)v12, a1);
  v13 = v5;
  v14 = *v9;
  DataSharingServiceTelemetry::DSSRemove<unsigned long,unsigned short const *>(&v13, &v14);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007870  mov     [rsp+arg_0], rbx
0x180007875  mov     [rsp+arg_18], rsi
0x18000787a  push    rdi
0x18000787b  sub     rsp, 50h
0x18000787f  xor     esi, esi
0x180007881  mov     rbx, rdx
0x180007884  mov     rdi, rcx
0x180007887  test    rdx, rdx
0x18000788a  jz      short loc_1800078C9
0x18000788c  cmp     [rdx], si
0x18000788f  jz      short loc_1800078C9
0x180007891  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007896  lea     rdx, aDssremoveshari_1; "DSSRemoveSharingToken started."
0x18000789d  mov     rcx, rax; this
0x1800078a0  call    ?LogServiceApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiStarted(ushort const *)
0x1800078a5  mov     rcx, rbx; unsigned __int16 *
0x1800078a8  call    ?DSSRemoveSharingToken@@YAJPEBG@Z; DSSRemoveSharingToken(ushort const *)
0x1800078ad  mov     ebx, eax
0x1800078af  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800078b4  lea     rdx, aDssremoveshari; "DSSRemoveSharingToken finished."
0x1800078bb  mov     rcx, rax; this
0x1800078be  call    ?LogServiceApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiCompleted(ushort const *)
0x1800078c3  test    ebx, ebx
0x1800078c5  jns     short loc_1800078F3
0x1800078c7  jmp     short loc_1800078CE
0x1800078c9  mov     ebx, 80070057h
0x1800078ce  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800078d3  lea     r9, aHr0xX; "hr=0x%x."
0x1800078da  mov     [rsp+58h+var_38], ebx
0x1800078de  mov     r8d, 118h; unsigned int
0x1800078e4  lea     rdx, aRpcdssremovesh; "RpcDSSRemoveSharingToken"
0x1800078eb  mov     rcx, rax; this
0x1800078ee  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800078f3  mov     rdx, rdi
0x1800078f6  lea     rcx, [rsp+58h+var_28]
0x1800078fb  call    ?RpcClientProcessInfo@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAX@Z; RpcClientProcessInfo(void *)
0x180007900  lea     rdx, [rsp+58h+arg_10]
0x180007905  mov     [rsp+58h+arg_8], ebx
0x180007909  mov     rcx, [rax]
0x18000790c  mov     [rsp+58h+arg_10], rcx
0x180007911  lea     rcx, [rsp+58h+arg_8]
0x180007916  call    ??$DSSRemove@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z; DataSharingServiceTelemetry::DSSRemove<ulong,ushort const *>(ulong &&,ushort const * &&)
0x18000791b  lea     rcx, [rsp+58h+var_28]
0x180007920  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180007925  mov     rsi, [rsp+58h+arg_18]
0x18000792a  mov     eax, ebx
0x18000792c  mov     rbx, [rsp+58h+arg_0]
0x180007931  add     rsp, 50h
0x180007935  pop     rdi
0x180007936  retn
```
