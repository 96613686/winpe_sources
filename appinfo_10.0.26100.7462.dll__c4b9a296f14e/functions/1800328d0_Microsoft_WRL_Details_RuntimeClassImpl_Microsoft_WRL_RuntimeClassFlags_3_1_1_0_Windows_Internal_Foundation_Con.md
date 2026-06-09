# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800328d0`
- end: `0x180032934`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002d238`
- `0x1800328d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800328ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800328ef`

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
0x1800328d0  mov     [rsp+arg_0], rbx
0x1800328d5  mov     [rsp+arg_10], rsi
0x1800328da  push    rdi
0x1800328db  sub     rsp, 20h
0x1800328df  xor     ebx, ebx
0x1800328e1  mov     rdi, r8
0x1800328e4  mov     [r8], rbx
0x1800328e7  mov     rsi, rdx
0x1800328ea  mov     [rdx], ebx
0x1800328ec  lea     ecx, [rbx+20h]; cb
0x1800328ef  call    cs:__imp_CoTaskMemAlloc
0x1800328f6  nop     dword ptr [rax+rax+00h]
0x1800328fb  mov     r8, rax
0x1800328fe  test    rax, rax
0x180032901  jnz     short loc_18003290A
0x180032903  mov     ebx, 8007000Eh
0x180032908  jmp     short loc_180032921
0x18003290a  lea     rdx, [rsp+28h+arg_8]
0x18003290f  mov     [rsp+28h+arg_8], ebx
0x180032913  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180032918  mov     dword ptr [rsi], 2
0x18003291e  mov     [rdi], r8
0x180032921  mov     rsi, [rsp+28h+arg_10]
0x180032926  mov     eax, ebx
0x180032928  mov     rbx, [rsp+28h+arg_0]
0x18003292d  add     rsp, 20h
0x180032931  pop     rdi
0x180032932  retn
```
