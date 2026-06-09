# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IApplicationResourceResolver,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180007110`
- end: `0x18000716f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIApplicationResourceResolver@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800070ec`
- `0x180007110`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007132`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IApplicationResourceResolver,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::IApplicationResourceResolver,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180007110  mov     [rsp+arg_0], rbx
0x180007115  push    rdi
0x180007116  sub     rsp, 20h
0x18000711a  mov     qword ptr [r8], 0
0x180007121  mov     ecx, 20h ; ' '; cb
0x180007126  mov     dword ptr [rdx], 0
0x18000712c  mov     rbx, r8
0x18000712f  mov     rdi, rdx
0x180007132  call    cs:__imp_CoTaskMemAlloc
0x180007138  mov     r8, rax
0x18000713b  test    rax, rax
0x18000713e  jnz     short loc_180007147
0x180007140  mov     eax, 8007000Eh
0x180007145  jmp     short loc_180007164
0x180007147  lea     rdx, [rsp+28h+arg_8]
0x18000714c  mov     [rsp+28h+arg_8], 0
0x180007154  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIApplicationResourceResolver@StateRepository@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::StateRepository::IApplicationResourceResolver,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180007159  mov     dword ptr [rdi], 2
0x18000715f  xor     eax, eax
0x180007161  mov     [rbx], r8
0x180007164  mov     rbx, [rsp+28h+arg_0]
0x180007169  add     rsp, 20h
0x18000716d  pop     rdi
0x18000716e  retn
```
