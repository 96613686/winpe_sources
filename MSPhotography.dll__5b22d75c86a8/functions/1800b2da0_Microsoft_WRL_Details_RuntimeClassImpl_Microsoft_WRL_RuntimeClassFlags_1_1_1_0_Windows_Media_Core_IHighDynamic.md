# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Core::IHighDynamicRangeControl,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x1800b2da0`
- end: `0x1800b2dff`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIHighDynamicRangeControl@Core@Media@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800b2d58`
- `0x1800b2da0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b2dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b2dc2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Media::Core::IHighDynamicRangeControl,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Media::Core::IHighDynamicRangeControl,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x1800b2da0  mov     [rsp+arg_0], rbx
0x1800b2da5  push    rdi
0x1800b2da6  sub     rsp, 20h
0x1800b2daa  mov     qword ptr [r8], 0
0x1800b2db1  mov     ecx, 20h ; ' '; cb
0x1800b2db6  mov     dword ptr [rdx], 0
0x1800b2dbc  mov     rbx, r8
0x1800b2dbf  mov     rdi, rdx
0x1800b2dc2  call    cs:__imp_CoTaskMemAlloc
0x1800b2dc8  mov     r8, rax
0x1800b2dcb  test    rax, rax
0x1800b2dce  jnz     short loc_1800B2DD7
0x1800b2dd0  mov     eax, 8007000Eh
0x1800b2dd5  jmp     short loc_1800B2DF4
0x1800b2dd7  lea     rdx, [rsp+28h+arg_8]
0x1800b2ddc  mov     [rsp+28h+arg_8], 0
0x1800b2de4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIHighDynamicRangeControl@Core@Media@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Media::Core::IHighDynamicRangeControl,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800b2de9  mov     dword ptr [rdi], 2
0x1800b2def  xor     eax, eax
0x1800b2df1  mov     [rbx], r8
0x1800b2df4  mov     rbx, [rsp+28h+arg_0]
0x1800b2df9  add     rsp, 20h
0x1800b2dfd  pop     rdi
0x1800b2dfe  retn
```
