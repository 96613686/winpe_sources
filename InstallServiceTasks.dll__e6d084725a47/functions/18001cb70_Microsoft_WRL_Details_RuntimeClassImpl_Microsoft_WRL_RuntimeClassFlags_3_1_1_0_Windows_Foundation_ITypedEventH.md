# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18001cb70`
- end: `0x18001cbda`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001cab8`
- `0x18001cb70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cb92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cb92`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18001cb70  mov     [rsp+arg_0], rbx
0x18001cb75  push    rdi
0x18001cb76  sub     rsp, 20h
0x18001cb7a  mov     qword ptr [r8], 0
0x18001cb81  mov     ecx, 30h ; '0'; cb
0x18001cb86  mov     dword ptr [rdx], 0
0x18001cb8c  mov     rbx, r8
0x18001cb8f  mov     rdi, rdx
0x18001cb92  call    cs:__imp_CoTaskMemAlloc
0x18001cb98  mov     r8, rax
0x18001cb9b  test    rax, rax
0x18001cb9e  jnz     short loc_18001CBA7
0x18001cba0  mov     eax, 8007000Eh
0x18001cba5  jmp     short loc_18001CBCF
0x18001cba7  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18001cbae  lea     rdx, [rsp+28h+arg_8]
0x18001cbb3  mov     [rsp+28h+arg_8], 1
0x18001cbbb  movdqu  xmmword ptr [rax], xmm0
0x18001cbbf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Foundation@Windows@@UIWeakReferenceSource@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,IInspectable *>,IWeakReferenceSource,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001cbc4  mov     dword ptr [rdi], 3
0x18001cbca  xor     eax, eax
0x18001cbcc  mov     [rbx], r8
0x18001cbcf  mov     rbx, [rsp+28h+arg_0]
0x18001cbd4  add     rsp, 20h
0x18001cbd8  pop     rdi
0x18001cbd9  retn
```
