# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IDateTimeSettingsStatics>,IInspectable,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18000bd60`
- end: `0x18000bdca`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIDateTimeSettingsStatics@System@Windows@@@WRL@Microsoft@@UIInspectable@@VNil@Details@23@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bdd0`
- `0x18000bde0`

## callees

- `0x18000bc44`
- `0x18000bd60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bd82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bd82`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IDateTimeSettingsStatics>,IInspectable,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IDateTimeSettingsStatics>>,IInspectable,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x18000bd60  mov     [rsp+arg_0], rbx
0x18000bd65  push    rdi
0x18000bd66  sub     rsp, 20h
0x18000bd6a  mov     qword ptr [r8], 0
0x18000bd71  mov     ecx, 30h ; '0'; cb
0x18000bd76  mov     dword ptr [rdx], 0
0x18000bd7c  mov     rbx, r8
0x18000bd7f  mov     rdi, rdx
0x18000bd82  call    cs:__imp_CoTaskMemAlloc
0x18000bd88  mov     r8, rax
0x18000bd8b  test    rax, rax
0x18000bd8e  jnz     short loc_18000BD97
0x18000bd90  mov     eax, 8007000Eh
0x18000bd95  jmp     short loc_18000BDBF
0x18000bd97  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000bd9e  lea     rdx, [rsp+28h+arg_8]
0x18000bda3  mov     [rsp+28h+arg_8], 1
0x18000bdab  movdqu  xmmword ptr [rax], xmm0
0x18000bdaf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@VFtmBase@WRL@Microsoft@@UIDateTimeSettingsStatics@System@Windows@@@WRL@Microsoft@@@Details@23@UIInspectable@@VNil@523@V7523@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IDateTimeSettingsStatics>>,IInspectable,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x18000bdb4  mov     dword ptr [rdi], 3
0x18000bdba  xor     eax, eax
0x18000bdbc  mov     [rbx], r8
0x18000bdbf  mov     rbx, [rsp+28h+arg_0]
0x18000bdc4  add     rsp, 20h
0x18000bdc8  pop     rdi
0x18000bdc9  retn
```
