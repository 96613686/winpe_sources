# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::UserProfile::IFirstSignInSettings,Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18005c3e0`
- end: `0x18005c456`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIFirstSignInSettings@UserProfile@System@Windows@@U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@7@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@9Foundation@7@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005c460`
- `0x18005c470`

## callees

- `0x18005b5ac`
- `0x18005c3e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005c402`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005c402`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::UserProfile::IFirstSignInSettings,Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::GetIids(
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
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 2;
  *v5 = GUID_3e945153_3a5e_452e_a601_f5baad2a4870;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 4;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18005c3e0  mov     [rsp+arg_0], rbx
0x18005c3e5  push    rdi
0x18005c3e6  sub     rsp, 20h
0x18005c3ea  mov     qword ptr [r8], 0
0x18005c3f1  mov     ecx, 40h ; '@'; cb
0x18005c3f6  mov     dword ptr [rdx], 0
0x18005c3fc  mov     rbx, r8
0x18005c3ff  mov     rdi, rdx
0x18005c402  call    cs:__imp_CoTaskMemAlloc
0x18005c408  mov     r8, rax
0x18005c40b  test    rax, rax
0x18005c40e  jnz     short loc_18005C417
0x18005c410  mov     eax, 8007000Eh
0x18005c415  jmp     short loc_18005C44B
0x18005c417  movups  xmm0, xmmword ptr cs:_GUID_3e945153_3a5e_452e_a601_f5baad2a4870.Data1
0x18005c41e  lea     rdx, [rsp+28h+arg_8]
0x18005c423  mov     [rsp+28h+arg_8], 2
0x18005c42b  movdqu  xmmword ptr [rax], xmm0
0x18005c42f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18005c436  movdqu  xmmword ptr [rax+10h], xmm1
0x18005c43b  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@567@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18005c440  mov     dword ptr [rdi], 4
0x18005c446  xor     eax, eax
0x18005c448  mov     [rbx], r8
0x18005c44b  mov     rbx, [rsp+28h+arg_0]
0x18005c450  add     rsp, 20h
0x18005c454  pop     rdi
0x18005c455  retn
```
