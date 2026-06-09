# SharingPlatform::DeviceSessionChannel::~DeviceSessionChannel(void)

- ea: `0x18001d7d8`
- end: `0x18001d88b`
- name: `??1DeviceSessionChannel@SharingPlatform@@UEAA@XZ`
- size: `179`
- prototype: `void __fastcall(SharingPlatform::DeviceSessionChannel *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180048590`

## callees

- `0x180004928`
- `0x18001d7d8`
- `0x18001d894`
- `0x1800543f4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d86b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d859`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d86b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SharingPlatform::DeviceSessionChannel::~DeviceSessionChannel(
        SharingPlatform::DeviceSessionChannel *this)
{
  __int64 *v2; // rdi
  __int64 v3; // rcx
  struct IInspectable *v4; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &SharingPlatform::DeviceSessionChannel::`vftable'{for `SharingPlatform::IDeviceSessionChannel'};
  *((_QWORD *)this + 1) = &SharingPlatform::DeviceSessionChannel::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<9>,1,IWeakReferenceSource>'};
  v4 = 0;
  v2 = (__int64 *)((char *)this + 56);
  Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionInternal>(
    (SharingPlatform::DeviceSessionChannel *)((char *)this + 56),
    &v4);
  if ( v4 )
    ((void (__fastcall *)(struct IInspectable *, _QWORD))v4->lpVtbl[1].GetIids)(v4, *((_QWORD *)this + 5));
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v4);
  v3 = *v2;
  if ( *v2 )
  {
    *v2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  WindowsDeleteString(*((HSTRING *)this + 4));
  *((_QWORD *)this + 4) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,IInspectable>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,IInspectable>(this);
}

```

## disassembly

```asm
0x18001d7d8  mov     [rsp+arg_8], rbx
0x18001d7dd  push    rdi
0x18001d7de  sub     rsp, 20h
0x18001d7e2  mov     rbx, rcx
0x18001d7e5  lea     rax, ??_7DeviceSessionChannel@SharingPlatform@@6BIDeviceSessionChannel@1@@; const SharingPlatform::DeviceSessionChannel::`vftable'{for `SharingPlatform::IDeviceSessionChannel'}
0x18001d7ec  mov     [rcx], rax
0x18001d7ef  lea     rax, ??_7DeviceSessionChannel@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const SharingPlatform::DeviceSessionChannel::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<9>,1,IWeakReferenceSource>'}
0x18001d7f6  mov     [rcx+8], rax
0x18001d7fa  mov     [rsp+28h+arg_0], 0
0x18001d803  lea     rdi, [rcx+38h]
0x18001d807  lea     rdx, [rsp+28h+arg_0]; struct IInspectable **
0x18001d80c  mov     rcx, rdi; this
0x18001d80f  call    ??$As@UISessionInternal@SharingPlatform@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISessionInternal@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::ISessionInternal>>)
0x18001d814  mov     rcx, [rsp+28h+arg_0]
0x18001d819  test    rcx, rcx
0x18001d81c  jz      short loc_18001D82E
0x18001d81e  mov     rax, [rcx]
0x18001d821  mov     rdx, [rbx+28h]
0x18001d825  mov     rax, [rax+48h]
0x18001d829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d82e  lea     rcx, [rsp+28h+arg_0]
0x18001d833  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001d838  nop
0x18001d839  mov     rcx, [rdi]
0x18001d83c  test    rcx, rcx
0x18001d83f  jz      short loc_18001D855
0x18001d841  mov     qword ptr [rdi], 0
0x18001d848  mov     rax, [rcx]
0x18001d84b  mov     rax, [rax+10h]
0x18001d84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d854  nop
0x18001d855  mov     rcx, [rbx+28h]; string
0x18001d859  call    cs:__imp_WindowsDeleteString
0x18001d85f  mov     qword ptr [rbx+28h], 0
0x18001d867  mov     rcx, [rbx+20h]; string
0x18001d86b  call    cs:__imp_WindowsDeleteString
0x18001d871  mov     qword ptr [rbx+20h], 0
0x18001d879  mov     rcx, rbx
0x18001d87c  mov     rbx, [rsp+28h+arg_8]
0x18001d881  add     rsp, 20h
0x18001d885  pop     rdi
0x18001d886  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UIInspectable@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,IInspectable>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,IInspectable>(void)
```
