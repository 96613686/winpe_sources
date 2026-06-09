# Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::GetIids(ulong *,_GUID * *)

- ea: `0x180012f70`
- end: `0x180012fcf`
- name: `?GetIids@?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010524`
- `0x180012f70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012f92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012f92`

## pseudocode

```c
__int64 __fastcall Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180012f70  mov     [rsp+arg_0], rbx
0x180012f75  push    rdi
0x180012f76  sub     rsp, 20h
0x180012f7a  mov     qword ptr [r8], 0
0x180012f81  mov     ecx, 20h ; ' '; cb
0x180012f86  mov     dword ptr [rdx], 0
0x180012f8c  mov     rbx, r8
0x180012f8f  mov     rdi, rdx
0x180012f92  call    cs:__imp_CoTaskMemAlloc
0x180012f98  mov     r8, rax
0x180012f9b  test    rax, rax
0x180012f9e  jnz     short loc_180012FA7
0x180012fa0  mov     eax, 8007000Eh
0x180012fa5  jmp     short loc_180012FC4
0x180012fa7  lea     rdx, [rsp+28h+arg_8]
0x180012fac  mov     [rsp+28h+arg_8], 0
0x180012fb4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$0A@UIBuffer@Streams@Storage@Windows@@UIWeakReferenceSource@@VFtmBase@23@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@V923@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180012fb9  mov     dword ptr [rdi], 2
0x180012fbf  xor     eax, eax
0x180012fc1  mov     [rbx], r8
0x180012fc4  mov     rbx, [rsp+28h+arg_0]
0x180012fc9  add     rsp, 20h
0x180012fcd  pop     rdi
0x180012fce  retn
```
