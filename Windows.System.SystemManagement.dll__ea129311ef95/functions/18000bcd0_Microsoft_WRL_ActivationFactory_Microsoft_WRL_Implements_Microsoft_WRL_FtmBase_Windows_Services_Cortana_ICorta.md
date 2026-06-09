# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Services::Cortana::ICortanaSettingsStatics>,IInspectable,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18000bcd0`
- end: `0x18000bd3a`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UICortanaSettingsStatics@Cortana@Services@Windows@@@WRL@Microsoft@@UIInspectable@@VNil@Details@23@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bd40`
- `0x18000bd50`

## callees

- `0x18000bc14`
- `0x18000bcd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bcf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bcf2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Services::Cortana::ICortanaSettingsStatics>,IInspectable,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Services::Cortana::ICortanaSettingsStatics>>,IInspectable,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x18000bcd0  mov     [rsp+arg_0], rbx
0x18000bcd5  push    rdi
0x18000bcd6  sub     rsp, 20h
0x18000bcda  mov     qword ptr [r8], 0
0x18000bce1  mov     ecx, 30h ; '0'; cb
0x18000bce6  mov     dword ptr [rdx], 0
0x18000bcec  mov     rbx, r8
0x18000bcef  mov     rdi, rdx
0x18000bcf2  call    cs:__imp_CoTaskMemAlloc
0x18000bcf8  mov     r8, rax
0x18000bcfb  test    rax, rax
0x18000bcfe  jnz     short loc_18000BD07
0x18000bd00  mov     eax, 8007000Eh
0x18000bd05  jmp     short loc_18000BD2F
0x18000bd07  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000bd0e  lea     rdx, [rsp+28h+arg_8]
0x18000bd13  mov     [rsp+28h+arg_8], 1
0x18000bd1b  movdqu  xmmword ptr [rax], xmm0
0x18000bd1f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@VFtmBase@WRL@Microsoft@@UICortanaSettingsStatics@Cortana@Services@Windows@@@WRL@Microsoft@@@Details@23@UIInspectable@@VNil@523@V7523@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Services::Cortana::ICortanaSettingsStatics>>,IInspectable,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x18000bd24  mov     dword ptr [rdi], 3
0x18000bd2a  xor     eax, eax
0x18000bd2c  mov     [rbx], r8
0x18000bd2f  mov     rbx, [rsp+28h+arg_0]
0x18000bd34  add     rsp, 20h
0x18000bd38  pop     rdi
0x18000bd39  retn
```
