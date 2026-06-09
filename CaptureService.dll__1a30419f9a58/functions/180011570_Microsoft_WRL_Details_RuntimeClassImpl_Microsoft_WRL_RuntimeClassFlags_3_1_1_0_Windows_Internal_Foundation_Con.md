# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180011570`
- end: `0x1800115cf`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fe30`
- `0x180011570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011592`

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
0x180011570  mov     [rsp+arg_0], rbx
0x180011575  push    rdi
0x180011576  sub     rsp, 20h
0x18001157a  mov     qword ptr [r8], 0
0x180011581  mov     ecx, 20h ; ' '; cb
0x180011586  mov     dword ptr [rdx], 0
0x18001158c  mov     rbx, r8
0x18001158f  mov     rdi, rdx
0x180011592  call    cs:__imp_CoTaskMemAlloc
0x180011598  mov     r8, rax
0x18001159b  test    rax, rax
0x18001159e  jnz     short loc_1800115A7
0x1800115a0  mov     eax, 8007000Eh
0x1800115a5  jmp     short loc_1800115C4
0x1800115a7  lea     rdx, [rsp+28h+arg_8]
0x1800115ac  mov     [rsp+28h+arg_8], 0
0x1800115b4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800115b9  mov     dword ptr [rdi], 2
0x1800115bf  xor     eax, eax
0x1800115c1  mov     [rbx], r8
0x1800115c4  mov     rbx, [rsp+28h+arg_0]
0x1800115c9  add     rsp, 20h
0x1800115cd  pop     rdi
0x1800115ce  retn
```
