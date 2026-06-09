# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Graphics::Imaging::Internal::IHighDynamicRangeResult,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180030180`
- end: `0x1800301df`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003015c`
- `0x180030180`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800301a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800301a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Graphics::Imaging::Internal::IHighDynamicRangeResult,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Graphics::Imaging::Internal::IHighDynamicRangeResult,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180030180  mov     [rsp+arg_0], rbx
0x180030185  push    rdi
0x180030186  sub     rsp, 20h
0x18003018a  mov     qword ptr [r8], 0
0x180030191  mov     ecx, 20h ; ' '; cb
0x180030196  mov     dword ptr [rdx], 0
0x18003019c  mov     rbx, r8
0x18003019f  mov     rdi, rdx
0x1800301a2  call    cs:__imp_CoTaskMemAlloc
0x1800301a8  mov     r8, rax
0x1800301ab  test    rax, rax
0x1800301ae  jnz     short loc_1800301B7
0x1800301b0  mov     eax, 8007000Eh
0x1800301b5  jmp     short loc_1800301D4
0x1800301b7  lea     rdx, [rsp+28h+arg_8]
0x1800301bc  mov     [rsp+28h+arg_8], 0
0x1800301c4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Graphics::Imaging::Internal::IHighDynamicRangeResult,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800301c9  mov     dword ptr [rdi], 2
0x1800301cf  xor     eax, eax
0x1800301d1  mov     [rbx], r8
0x1800301d4  mov     rbx, [rsp+28h+arg_0]
0x1800301d9  add     rsp, 20h
0x1800301dd  pop     rdi
0x1800301de  retn
```
