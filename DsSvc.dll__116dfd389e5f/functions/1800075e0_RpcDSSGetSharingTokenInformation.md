# RpcDSSGetSharingTokenInformation

- ea: `0x1800075e0`
- end: `0x1800076e1`
- name: `RpcDSSGetSharingTokenInformation`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800037e0`
- `0x180006070`
- `0x180006cb0`
- `0x180006f78`
- `0x1800075e0`
- `0x18000bf80`
- `0x18000c100`
- `0x18000c12c`
- `0x18000d0d0`

## string_xrefs

- `0x180007626`: `DSSGetSharingTokenInformation started.`
- `0x180007652`: `DSSGetSharingTokenInformation finished.`
- `0x180007682`: `RpcDSSGetSharingTokenInformation`

## pseudocode

```c
__int64 __fastcall RpcDSSGetSharingTokenInformation(
        void *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        enum _DS_SHARE_PERMISSION *a5)
{
  int *v9; // rax
  int v10; // ebx
  __int64 v11; // rcx
  int *v12; // rax
  int *v13; // rax
  __int64 *v14; // rax
  int v16; // [rsp+20h] [rbp-58h]
  __int64 v17; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v18[40]; // [rsp+38h] [rbp-40h] BYREF
  int v19; // [rsp+88h] [rbp+10h] BYREF

  if ( !a2 || !*a2 || !a3 || !a4 || !a5 )
  {
    v10 = -2147024809;
LABEL_9:
    v13 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
    v16 = v10;
    DSLogger::LogError((DSLogger *)v13, L"RpcDSSGetSharingTokenInformation", 232, L"hr=0x%x.", v16);
    goto LABEL_10;
  }
  v9 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get((__int64)a1);
  DSLogger::LogServiceApiStarted((DSLogger *)v9, L"DSSGetSharingTokenInformation started.");
  v10 = DSSGetSharingTokenInformation(a2, a3, a4, a5);
  v12 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v11);
  DSLogger::LogServiceApiCompleted((DSLogger *)v12, L"DSSGetSharingTokenInformation finished.");
  if ( v10 < 0 )
    goto LABEL_9;
LABEL_10:
  v14 = (__int64 *)RpcClientProcessInfo((__int64)v18, a1);
  v19 = v10;
  v17 = *v14;
  DataSharingServiceTelemetry::DSSGetToken<unsigned long,unsigned short const *>(&v19, &v17);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v18);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800075e0  mov     [rsp+arg_0], rbx
0x1800075e5  mov     [rsp+arg_10], rbp
0x1800075ea  push    rsi
0x1800075eb  push    r14
0x1800075ed  push    r15
0x1800075ef  sub     rsp, 60h
0x1800075f3  xor     r15d, r15d
0x1800075f6  mov     rsi, r9
0x1800075f9  mov     rbp, r8
0x1800075fc  mov     rbx, rdx
0x1800075ff  mov     r14, rcx
0x180007602  test    rdx, rdx
0x180007605  jz      short loc_180007667
0x180007607  cmp     [rdx], r15w
0x18000760b  jz      short loc_180007667
0x18000760d  test    r8, r8
0x180007610  jz      short loc_180007667
0x180007612  test    r9, r9
0x180007615  jz      short loc_180007667
0x180007617  cmp     [rsp+78h+arg_20], r15
0x18000761f  jz      short loc_180007667
0x180007621  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007626  lea     rdx, aDssgetsharingt_0; "DSSGetSharingTokenInformation started."
0x18000762d  mov     rcx, rax; this
0x180007630  call    ?LogServiceApiStarted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiStarted(ushort const *)
0x180007635  mov     r9, [rsp+78h+arg_20]; enum _DS_SHARE_PERMISSION *
0x18000763d  mov     r8, rsi; unsigned __int16 **
0x180007640  mov     rdx, rbp; unsigned __int16 **
0x180007643  mov     rcx, rbx; unsigned __int16 *
0x180007646  call    ?DSSGetSharingTokenInformation@@YAJPEBGPEAPEAG1PEAW4_DS_SHARE_PERMISSION@@@Z; DSSGetSharingTokenInformation(ushort const *,ushort * *,ushort * *,_DS_SHARE_PERMISSION *)
0x18000764b  mov     ebx, eax
0x18000764d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007652  lea     rdx, aDssgetsharingt_1; "DSSGetSharingTokenInformation finished."
0x180007659  mov     rcx, rax; this
0x18000765c  call    ?LogServiceApiCompleted@DSLogger@@QEAAXPEBG@Z; DSLogger::LogServiceApiCompleted(ushort const *)
0x180007661  test    ebx, ebx
0x180007663  jns     short loc_180007691
0x180007665  jmp     short loc_18000766C
0x180007667  mov     ebx, 80070057h
0x18000766c  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180007671  lea     r9, aHr0xX; "hr=0x%x."
0x180007678  mov     [rsp+78h+var_58], ebx
0x18000767c  mov     r8d, 0E8h; unsigned int
0x180007682  lea     rdx, aRpcdssgetshari; "RpcDSSGetSharingTokenInformation"
0x180007689  mov     rcx, rax; this
0x18000768c  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180007691  mov     rdx, r14
0x180007694  lea     rcx, [rsp+78h+var_40]
0x180007699  call    ?RpcClientProcessInfo@@YA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAX@Z; RpcClientProcessInfo(void *)
0x18000769e  lea     rdx, [rsp+78h+var_48]
0x1800076a3  mov     [rsp+78h+arg_8], ebx
0x1800076aa  mov     rcx, [rax]
0x1800076ad  mov     [rsp+78h+var_48], rcx
0x1800076b2  lea     rcx, [rsp+78h+arg_8]
0x1800076ba  call    ??$DSSGetToken@KPEBG@DataSharingServiceTelemetry@@SAX$$QEAK$$QEAPEBG@Z; DataSharingServiceTelemetry::DSSGetToken<ulong,ushort const *>(ulong &&,ushort const * &&)
0x1800076bf  lea     rcx, [rsp+78h+var_40]
0x1800076c4  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800076c9  lea     r11, [rsp+78h+var_18]
0x1800076ce  mov     eax, ebx
0x1800076d0  mov     rbx, [r11+20h]
0x1800076d4  mov     rbp, [r11+30h]
0x1800076d8  mov     rsp, r11
0x1800076db  pop     r15
0x1800076dd  pop     r14
0x1800076df  pop     rsi
0x1800076e0  retn
```
