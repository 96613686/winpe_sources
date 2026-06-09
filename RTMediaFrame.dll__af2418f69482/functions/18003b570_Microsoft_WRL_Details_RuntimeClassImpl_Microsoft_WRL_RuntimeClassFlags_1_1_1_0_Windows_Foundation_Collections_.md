# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x18003b570`
- end: `0x18003b5da`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b5e0`

## callees

- `0x18003b134`
- `0x18003b570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b592`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::GetIids(
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
  *v5 = GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18003b570  mov     [rsp+arg_0], rbx
0x18003b575  push    rdi
0x18003b576  sub     rsp, 20h
0x18003b57a  mov     qword ptr [r8], 0
0x18003b581  mov     ecx, 30h ; '0'; cb
0x18003b586  mov     dword ptr [rdx], 0
0x18003b58c  mov     rbx, r8
0x18003b58f  mov     rdi, rdx
0x18003b592  call    cs:__imp_CoTaskMemAlloc
0x18003b598  mov     r8, rax
0x18003b59b  test    rax, rax
0x18003b59e  jnz     short loc_18003B5A7
0x18003b5a0  mov     eax, 8007000Eh
0x18003b5a5  jmp     short loc_18003B5CF
0x18003b5a7  movups  xmm0, xmmword ptr cs:_GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca.Data1
0x18003b5ae  lea     rdx, [rsp+28h+arg_8]
0x18003b5b3  mov     [rsp+28h+arg_8], 1
0x18003b5bb  movdqu  xmmword ptr [rax], xmm0
0x18003b5bf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003b5c4  mov     dword ptr [rdi], 3
0x18003b5ca  xor     eax, eax
0x18003b5cc  mov     [rbx], r8
0x18003b5cf  mov     rbx, [rsp+28h+arg_0]
0x18003b5d4  add     rsp, 20h
0x18003b5d8  pop     rdi
0x18003b5d9  retn
```
