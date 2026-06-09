# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x140009310`
- end: `0x14000936f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140009194`
- `0x140009310`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140009332`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140009332`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x140009310  mov     [rsp+arg_0], rbx
0x140009315  push    rdi
0x140009316  sub     rsp, 20h
0x14000931a  mov     qword ptr [r8], 0
0x140009321  mov     ecx, 20h ; ' '; cb
0x140009326  mov     dword ptr [rdx], 0
0x14000932c  mov     rbx, r8
0x14000932f  mov     rdi, rdx
0x140009332  call    cs:__imp_CoTaskMemAlloc
0x140009338  mov     r8, rax
0x14000933b  test    rax, rax
0x14000933e  jnz     short loc_140009347
0x140009340  mov     eax, 8007000Eh
0x140009345  jmp     short loc_140009364
0x140009347  lea     rdx, [rsp+28h+arg_8]
0x14000934c  mov     [rsp+28h+arg_8], 0
0x140009354  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$0A@UIBuffer@Streams@Storage@Windows@@UIWeakReferenceSource@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x140009359  mov     dword ptr [rdi], 2
0x14000935f  xor     eax, eax
0x140009361  mov     [rbx], r8
0x140009364  mov     rbx, [rsp+28h+arg_0]
0x140009369  add     rsp, 20h
0x14000936d  pop     rdi
0x14000936e  retn
```
