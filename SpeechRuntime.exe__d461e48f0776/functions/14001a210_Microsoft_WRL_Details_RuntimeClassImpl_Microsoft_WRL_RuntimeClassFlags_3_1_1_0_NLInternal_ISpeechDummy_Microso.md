# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,NLInternal::ISpeechDummy,Microsoft::WRL::CloakedIid<ISharedRecoCustomMarshaller>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x14001a210`
- end: `0x14001a26f`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UISpeechDummy@NLInternal@@U?$CloakedIid@UISharedRecoCustomMarshaller@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001a280`

## callees

- `0x14001a1e8`
- `0x14001a210`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001a232`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001a232`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,NLInternal::ISpeechDummy,Microsoft::WRL::CloakedIid<ISharedRecoCustomMarshaller>,Microsoft::WRL::FtmBase>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,NLInternal::ISpeechDummy,IWeakReferenceSource,Microsoft::WRL::CloakedIid<ISharedRecoCustomMarshaller>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x14001a210  mov     [rsp+arg_0], rbx
0x14001a215  push    rdi
0x14001a216  sub     rsp, 20h
0x14001a21a  mov     qword ptr [r8], 0
0x14001a221  mov     ecx, 20h ; ' '; cb
0x14001a226  mov     dword ptr [rdx], 0
0x14001a22c  mov     rbx, r8
0x14001a22f  mov     rdi, rdx
0x14001a232  call    cs:__imp_CoTaskMemAlloc
0x14001a238  mov     r8, rax
0x14001a23b  test    rax, rax
0x14001a23e  jnz     short loc_14001A247
0x14001a240  mov     eax, 8007000Eh
0x14001a245  jmp     short loc_14001A264
0x14001a247  lea     rdx, [rsp+28h+arg_8]
0x14001a24c  mov     [rsp+28h+arg_8], 0
0x14001a254  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UISpeechDummy@NLInternal@@UIWeakReferenceSource@@U?$CloakedIid@UISharedRecoCustomMarshaller@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,NLInternal::ISpeechDummy,IWeakReferenceSource,Microsoft::WRL::CloakedIid<ISharedRecoCustomMarshaller>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x14001a259  mov     dword ptr [rdi], 2
0x14001a25f  xor     eax, eax
0x14001a261  mov     [rbx], r8
0x14001a264  mov     rbx, [rsp+28h+arg_0]
0x14001a269  add     rsp, 20h
0x14001a26d  pop     rdi
0x14001a26e  retn
```
