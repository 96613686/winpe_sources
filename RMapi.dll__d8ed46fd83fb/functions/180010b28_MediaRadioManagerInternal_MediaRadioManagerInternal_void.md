# MediaRadioManagerInternal::~MediaRadioManagerInternal(void)

- ea: `0x180010b28`
- end: `0x180010bb2`
- name: `??1MediaRadioManagerInternal@@UEAA@XZ`
- size: `138`
- prototype: `void __fastcall(MediaRadioManagerInternal *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010bf0`

## callees

- `0x180003fa0`
- `0x1800086d0`
- `0x180010b28`
- `0x180024090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010b91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010b91`

## pseudocode

```c
void __fastcall MediaRadioManagerInternal::~MediaRadioManagerInternal(
        MediaRadioManagerInternal *this,
        struct IUnknown *a2,
        __int64 a3,
        unsigned int a4)
{
  const struct _GUID *v5; // r8

  *(_QWORD *)this = &MediaRadioManagerInternal::`vftable'{for `IMediaRadioManagerNotifySink'};
  *((_QWORD *)this + 1) = &MediaRadioManagerInternal::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMediaRadioManagerInternal>'};
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_q(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, a3, this);
  v5 = (const struct _GUID *)*((unsigned int *)this + 8);
  if ( (_DWORD)v5 )
  {
    RMAPI::Unadvise(*((RMAPI **)this + 3), a2, v5, a4);
    *((_DWORD *)this + 8) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x180010b28  mov     [rsp+arg_0], rbx
0x180010b2d  push    rdi
0x180010b2e  sub     rsp, 20h
0x180010b32  lea     rax, ??_7MediaRadioManagerInternal@@6BIMediaRadioManagerNotifySink@@@; const MediaRadioManagerInternal::`vftable'{for `IMediaRadioManagerNotifySink'}
0x180010b39  mov     rbx, rcx
0x180010b3c  mov     [rcx], rax
0x180010b3f  lea     rax, ??_7MediaRadioManagerInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMediaRadioManagerInternal@@@Details@WRL@Microsoft@@@; const MediaRadioManagerInternal::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMediaRadioManagerInternal>'}
0x180010b46  mov     [rcx+8], rax
0x180010b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b51  lea     rax, WPP_GLOBAL_Control
0x180010b58  cmp     rcx, rax
0x180010b5b  jz      short loc_180010B74
0x180010b5d  test    byte ptr [rcx+1Ch], 4
0x180010b61  jz      short loc_180010B74
0x180010b63  mov     rcx, [rcx+10h]
0x180010b67  mov     edx, 0Bh
0x180010b6c  mov     r9, rbx
0x180010b6f  call    WPP_SF_q
0x180010b74  mov     r8d, [rbx+20h]; struct _GUID *
0x180010b78  test    r8d, r8d
0x180010b7b  jz      short loc_180010B8D
0x180010b7d  mov     rcx, [rbx+18h]; this
0x180010b81  call    ?Unadvise@RMAPI@@YAJPEAUIUnknown@@AEBU_GUID@@K@Z; RMAPI::Unadvise(IUnknown *,_GUID const &,ulong)
0x180010b86  mov     dword ptr [rbx+20h], 0
0x180010b8d  lea     rcx, [rbx+28h]; lpCriticalSection
0x180010b91  call    cs:__imp_DeleteCriticalSection
0x180010b97  lea     rcx, [rbx+18h]
0x180010b9b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010ba0  mov     dword ptr [rbx+14h], 0C0000001h
0x180010ba7  mov     rbx, [rsp+28h+arg_0]
0x180010bac  add     rsp, 20h
0x180010bb0  pop     rdi
0x180010bb1  retn
```
