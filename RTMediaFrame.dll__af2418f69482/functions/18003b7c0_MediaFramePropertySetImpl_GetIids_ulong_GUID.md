# MediaFramePropertySetImpl::GetIids(ulong *,_GUID * *)

- ea: `0x18003b7c0`
- end: `0x18003b842`
- name: `?GetIids@MediaFramePropertySetImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(MediaFramePropertySetImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003b850`
- `0x18003b860`
- `0x18003b870`

## callees

- `0x18003b0f0`
- `0x18003b7c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b7e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b7e2`

## pseudocode

```c
__int64 __fastcall MediaFramePropertySetImpl::GetIids(
        MediaFramePropertySetImpl *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 3;
  *v5 = GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_fe2f3d47_5d47_5499_8374_430c7cda0204;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 5;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18003b7c0  mov     [rsp+arg_0], rbx
0x18003b7c5  push    rdi
0x18003b7c6  sub     rsp, 20h
0x18003b7ca  mov     qword ptr [r8], 0
0x18003b7d1  mov     ecx, 50h ; 'P'; cb
0x18003b7d6  mov     dword ptr [rdx], 0
0x18003b7dc  mov     rbx, r8
0x18003b7df  mov     rdi, rdx
0x18003b7e2  call    cs:__imp_CoTaskMemAlloc
0x18003b7e8  mov     r8, rax
0x18003b7eb  test    rax, rax
0x18003b7ee  jnz     short loc_18003B7F7
0x18003b7f0  mov     eax, 8007000Eh
0x18003b7f5  jmp     short loc_18003B837
0x18003b7f7  movups  xmm0, xmmword ptr cs:_GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca.Data1
0x18003b7fe  lea     rdx, [rsp+28h+arg_8]
0x18003b803  mov     [rsp+28h+arg_8], 3
0x18003b80b  movdqu  xmmword ptr [rax], xmm0
0x18003b80f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18003b816  movdqu  xmmword ptr [rax+10h], xmm1
0x18003b81b  movups  xmm0, xmmword ptr cs:_GUID_fe2f3d47_5d47_5499_8374_430c7cda0204.Data1
0x18003b822  movdqu  xmmword ptr [rax+20h], xmm0
0x18003b827  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18003b82c  mov     dword ptr [rdi], 5
0x18003b832  xor     eax, eax
0x18003b834  mov     [rbx], r8
0x18003b837  mov     rbx, [rsp+28h+arg_0]
0x18003b83c  add     rsp, 20h
0x18003b840  pop     rdi
0x18003b841  retn
```
