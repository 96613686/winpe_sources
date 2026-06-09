# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800325a0`
- end: `0x180032604`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002e788`
- `0x1800325a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800325bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800325bf`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  __int64 v6; // rcx
  LPVOID v7; // r8
  __int64 v8; // r8
  int v10; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  *a3 = 0;
  *a2 = 0;
  v7 = CoTaskMemAlloc(0x20u);
  if ( v7 )
  {
    v10 = 0;
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
      v6,
      &v10,
      v7);
    *a2 = 2;
    *a3 = v8;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v3;
}

```

## disassembly

```asm
0x1800325a0  mov     [rsp+arg_0], rbx
0x1800325a5  mov     [rsp+arg_10], rsi
0x1800325aa  push    rdi
0x1800325ab  sub     rsp, 20h
0x1800325af  xor     ebx, ebx
0x1800325b1  mov     rdi, r8
0x1800325b4  mov     [r8], rbx
0x1800325b7  mov     rsi, rdx
0x1800325ba  mov     [rdx], ebx
0x1800325bc  lea     ecx, [rbx+20h]; cb
0x1800325bf  call    cs:__imp_CoTaskMemAlloc
0x1800325c6  nop     dword ptr [rax+rax+00h]
0x1800325cb  mov     r8, rax
0x1800325ce  test    rax, rax
0x1800325d1  jnz     short loc_1800325DA
0x1800325d3  mov     ebx, 8007000Eh
0x1800325d8  jmp     short loc_1800325F1
0x1800325da  lea     rdx, [rsp+28h+arg_8]
0x1800325df  mov     [rsp+28h+arg_8], ebx
0x1800325e3  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800325e8  mov     dword ptr [rsi], 2
0x1800325ee  mov     [rdi], r8
0x1800325f1  mov     rsi, [rsp+28h+arg_10]
0x1800325f6  mov     eax, ebx
0x1800325f8  mov     rbx, [rsp+28h+arg_0]
0x1800325fd  add     rsp, 20h
0x180032601  pop     rdi
0x180032602  retn
```
