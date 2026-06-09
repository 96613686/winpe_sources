# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x14000d820`
- end: `0x14000d87f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000c28c`
- `0x14000d820`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000d842`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000d842`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x14000d820  mov     [rsp+arg_0], rbx
0x14000d825  push    rdi
0x14000d826  sub     rsp, 20h
0x14000d82a  mov     qword ptr [r8], 0
0x14000d831  mov     ecx, 20h ; ' '; cb
0x14000d836  mov     dword ptr [rdx], 0
0x14000d83c  mov     rbx, r8
0x14000d83f  mov     rdi, rdx
0x14000d842  call    cs:__imp_CoTaskMemAlloc
0x14000d848  mov     r8, rax
0x14000d84b  test    rax, rax
0x14000d84e  jnz     short loc_14000D857
0x14000d850  mov     eax, 8007000Eh
0x14000d855  jmp     short loc_14000D874
0x14000d857  lea     rdx, [rsp+28h+arg_8]
0x14000d85c  mov     [rsp+28h+arg_8], 0
0x14000d864  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14000d869  mov     dword ptr [rdi], 2
0x14000d86f  xor     eax, eax
0x14000d871  mov     [rbx], r8
0x14000d874  mov     rbx, [rsp+28h+arg_0]
0x14000d879  add     rsp, 20h
0x14000d87d  pop     rdi
0x14000d87e  retn
```
