# FaceDetectedEventArgsImpl::GetIids(ulong *,_GUID * *)

- ea: `0x180029de0`
- end: `0x180029e3f`
- name: `?GetIids@FaceDetectedEventArgsImpl@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: `__int64 __fastcall(FaceDetectedEventArgsImpl *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180029db0`
- `0x180029de0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029e02`

## pseudocode

```c
__int64 __fastcall FaceDetectedEventArgsImpl::GetIids(
        FaceDetectedEventArgsImpl *this,
        unsigned int *a2,
        struct _GUID **a3)
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Media::Core::IFaceDetectedEventArgs,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x180029de0  mov     [rsp+arg_0], rbx
0x180029de5  push    rdi
0x180029de6  sub     rsp, 20h
0x180029dea  mov     qword ptr [r8], 0
0x180029df1  mov     ecx, 20h ; ' '; cb
0x180029df6  mov     dword ptr [rdx], 0
0x180029dfc  mov     rbx, r8
0x180029dff  mov     rdi, rdx
0x180029e02  call    cs:__imp_CoTaskMemAlloc
0x180029e08  mov     r8, rax
0x180029e0b  test    rax, rax
0x180029e0e  jnz     short loc_180029E17
0x180029e10  mov     eax, 8007000Eh
0x180029e15  jmp     short loc_180029E34
0x180029e17  lea     rdx, [rsp+28h+arg_8]
0x180029e1c  mov     [rsp+28h+arg_8], 0
0x180029e24  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIFaceDetectedEventArgs@Core@Media@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Media::Core::IFaceDetectedEventArgs,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180029e29  mov     dword ptr [rdi], 2
0x180029e2f  xor     eax, eax
0x180029e31  mov     [rbx], r8
0x180029e34  mov     rbx, [rsp+28h+arg_0]
0x180029e39  add     rsp, 20h
0x180029e3d  pop     rdi
0x180029e3e  retn
```
