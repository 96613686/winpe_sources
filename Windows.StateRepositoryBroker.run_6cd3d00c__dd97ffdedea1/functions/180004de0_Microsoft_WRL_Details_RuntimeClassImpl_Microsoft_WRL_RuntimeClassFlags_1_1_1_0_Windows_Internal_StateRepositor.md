# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180004de0`
- end: `0x180004e3f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000476c`
- `0x180004de0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004e02`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180004de0  mov     [rsp+arg_0], rbx
0x180004de5  push    rdi
0x180004de6  sub     rsp, 20h
0x180004dea  mov     qword ptr [r8], 0
0x180004df1  mov     ecx, 20h ; ' '; cb
0x180004df6  mov     dword ptr [rdx], 0
0x180004dfc  mov     rbx, r8
0x180004dff  mov     rdi, rdx
0x180004e02  call    cs:__imp_CoTaskMemAlloc
0x180004e08  mov     r8, rax
0x180004e0b  test    rax, rax
0x180004e0e  jnz     short loc_180004E17
0x180004e10  mov     eax, 8007000Eh
0x180004e15  jmp     short loc_180004E34
0x180004e17  lea     rdx, [rsp+28h+arg_8]
0x180004e1c  mov     [rsp+28h+arg_8], 0
0x180004e24  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180004e29  mov     dword ptr [rdi], 2
0x180004e2f  xor     eax, eax
0x180004e31  mov     [rbx], r8
0x180004e34  mov     rbx, [rsp+28h+arg_0]
0x180004e39  add     rsp, 20h
0x180004e3d  pop     rdi
0x180004e3e  retn
```
