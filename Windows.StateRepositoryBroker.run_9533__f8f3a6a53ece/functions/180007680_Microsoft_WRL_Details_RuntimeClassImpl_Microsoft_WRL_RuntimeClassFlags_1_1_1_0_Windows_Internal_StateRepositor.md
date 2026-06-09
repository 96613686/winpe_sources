# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IPackageResourceResolver,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180007680`
- end: `0x1800076df`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIPackageResourceResolver@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000765c`
- `0x180007680`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800076a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800076a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IPackageResourceResolver,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::IPackageResourceResolver,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180007680  mov     [rsp+arg_0], rbx
0x180007685  push    rdi
0x180007686  sub     rsp, 20h
0x18000768a  mov     qword ptr [r8], 0
0x180007691  mov     ecx, 20h ; ' '; cb
0x180007696  mov     dword ptr [rdx], 0
0x18000769c  mov     rbx, r8
0x18000769f  mov     rdi, rdx
0x1800076a2  call    cs:__imp_CoTaskMemAlloc
0x1800076a8  mov     r8, rax
0x1800076ab  test    rax, rax
0x1800076ae  jnz     short loc_1800076B7
0x1800076b0  mov     eax, 8007000Eh
0x1800076b5  jmp     short loc_1800076D4
0x1800076b7  lea     rdx, [rsp+28h+arg_8]
0x1800076bc  mov     [rsp+28h+arg_8], 0
0x1800076c4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIPackageResourceResolver@StateRepository@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::IPackageResourceResolver,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800076c9  mov     dword ptr [rdi], 2
0x1800076cf  xor     eax, eax
0x1800076d1  mov     [rbx], r8
0x1800076d4  mov     rbx, [rsp+28h+arg_0]
0x1800076d9  add     rsp, 20h
0x1800076dd  pop     rdi
0x1800076de  retn
```
