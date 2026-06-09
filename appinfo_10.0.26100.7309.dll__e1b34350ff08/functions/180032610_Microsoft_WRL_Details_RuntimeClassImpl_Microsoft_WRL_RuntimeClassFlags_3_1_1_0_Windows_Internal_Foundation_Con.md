# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180032610`
- end: `0x180032674`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002d168`
- `0x180032610`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003262f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003262f`

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
0x180032610  mov     [rsp+arg_0], rbx
0x180032615  mov     [rsp+arg_10], rsi
0x18003261a  push    rdi
0x18003261b  sub     rsp, 20h
0x18003261f  xor     ebx, ebx
0x180032621  mov     rdi, r8
0x180032624  mov     [r8], rbx
0x180032627  mov     rsi, rdx
0x18003262a  mov     [rdx], ebx
0x18003262c  lea     ecx, [rbx+20h]; cb
0x18003262f  call    cs:__imp_CoTaskMemAlloc
0x180032636  nop     dword ptr [rax+rax+00h]
0x18003263b  mov     r8, rax
0x18003263e  test    rax, rax
0x180032641  jnz     short loc_18003264A
0x180032643  mov     ebx, 8007000Eh
0x180032648  jmp     short loc_180032661
0x18003264a  lea     rdx, [rsp+28h+arg_8]
0x18003264f  mov     [rsp+28h+arg_8], ebx
0x180032653  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180032658  mov     dword ptr [rsi], 2
0x18003265e  mov     [rdi], r8
0x180032661  mov     rsi, [rsp+28h+arg_10]
0x180032666  mov     eax, ebx
0x180032668  mov     rbx, [rsp+28h+arg_0]
0x18003266d  add     rsp, 20h
0x180032671  pop     rdi
0x180032672  retn
```
