# GeotagBrokerImpl::GetIids(ulong *,_GUID * *)

- ea: `0x180046f80`
- end: `0x180046fdf`
- name: `?GetIids@GeotagBrokerImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(GeotagBrokerImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800458c0`
- `0x180046f80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046fa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046fa2`

## pseudocode

```c
__int64 __fastcall GeotagBrokerImpl::GetIids(GeotagBrokerImpl *this, unsigned int *a2, struct _GUID **a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::IGeotagBroker,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180046f80  mov     [rsp+arg_0], rbx
0x180046f85  push    rdi
0x180046f86  sub     rsp, 20h
0x180046f8a  mov     qword ptr [r8], 0
0x180046f91  mov     ecx, 20h ; ' '; cb
0x180046f96  mov     dword ptr [rdx], 0
0x180046f9c  mov     rbx, r8
0x180046f9f  mov     rdi, rdx
0x180046fa2  call    cs:__imp_CoTaskMemAlloc
0x180046fa8  mov     r8, rax
0x180046fab  test    rax, rax
0x180046fae  jnz     short loc_180046FB7
0x180046fb0  mov     eax, 8007000Eh
0x180046fb5  jmp     short loc_180046FD4
0x180046fb7  lea     rdx, [rsp+28h+arg_8]
0x180046fbc  mov     [rsp+28h+arg_8], 0
0x180046fc4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIGeotagBroker@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::IGeotagBroker,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180046fc9  mov     dword ptr [rdi], 2
0x180046fcf  xor     eax, eax
0x180046fd1  mov     [rbx], r8
0x180046fd4  mov     rbx, [rsp+28h+arg_0]
0x180046fd9  add     rsp, 20h
0x180046fdd  pop     rdi
0x180046fde  retn
```
