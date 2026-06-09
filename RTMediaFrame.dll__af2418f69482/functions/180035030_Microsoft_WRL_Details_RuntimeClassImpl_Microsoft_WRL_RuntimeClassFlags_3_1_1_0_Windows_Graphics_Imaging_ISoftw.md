# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180035030`
- end: `0x18003509a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UISoftwareBitmap@Imaging@Graphics@Windows@@UIClosable@Foundation@7@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800350a0`
- `0x1800350b0`

## callees

- `0x180035000`
- `0x180035030`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035052`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Imaging::ISoftwareBitmap,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_689e0708_7eef_483f_963f_da938818e073;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180035030  mov     [rsp+arg_0], rbx
0x180035035  push    rdi
0x180035036  sub     rsp, 20h
0x18003503a  mov     qword ptr [r8], 0
0x180035041  mov     ecx, 30h ; '0'; cb
0x180035046  mov     dword ptr [rdx], 0
0x18003504c  mov     rbx, r8
0x18003504f  mov     rdi, rdx
0x180035052  call    cs:__imp_CoTaskMemAlloc
0x180035058  mov     r8, rax
0x18003505b  test    rax, rax
0x18003505e  jnz     short loc_180035067
0x180035060  mov     eax, 8007000Eh
0x180035065  jmp     short loc_18003508F
0x180035067  movups  xmm0, xmmword ptr cs:_GUID_689e0708_7eef_483f_963f_da938818e073.Data1
0x18003506e  lea     rdx, [rsp+28h+arg_8]
0x180035073  mov     [rsp+28h+arg_8], 1
0x18003507b  movdqu  xmmword ptr [rax], xmm0
0x18003507f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISoftwareBitmapNative@@@23@U?$CloakedIid@UISoftwareBitmapInternal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<ISoftwareBitmapNative>,Microsoft::WRL::CloakedIid<ISoftwareBitmapInternal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180035084  mov     dword ptr [rdi], 3
0x18003508a  xor     eax, eax
0x18003508c  mov     [rbx], r8
0x18003508f  mov     rbx, [rsp+28h+arg_0]
0x180035094  add     rsp, 20h
0x180035098  pop     rdi
0x180035099  retn
```
