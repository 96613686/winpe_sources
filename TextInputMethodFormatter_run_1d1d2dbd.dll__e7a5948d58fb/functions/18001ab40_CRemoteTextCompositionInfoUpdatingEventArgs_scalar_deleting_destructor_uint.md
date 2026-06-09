# CRemoteTextCompositionInfoUpdatingEventArgs::`scalar deleting destructor'(uint)

- ea: `0x18001ab40`
- end: `0x18001ab89`
- name: `??_GCRemoteTextCompositionInfoUpdatingEventArgs@@UEAAPEAXI@Z`
- size: `73`
- prototype: `void *__fastcall(CRemoteTextCompositionInfoUpdatingEventArgs *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000271c`
- `0x18001a038`
- `0x18001ab40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ab53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ab53`

## pseudocode

```c
HSTRING *__fastcall CRemoteTextCompositionInfoUpdatingEventArgs::`scalar deleting destructor'(HSTRING *this, char a2)
{
  WindowsDeleteString(this[11]);
  this[11] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001ab40  mov     [rsp+arg_0], rbx
0x18001ab45  push    rdi
0x18001ab46  sub     rsp, 20h
0x18001ab4a  mov     rdi, rcx
0x18001ab4d  mov     ebx, edx
0x18001ab4f  mov     rcx, [rcx+58h]; string
0x18001ab53  call    cs:__imp_WindowsDeleteString
0x18001ab59  mov     rcx, rdi
0x18001ab5c  mov     qword ptr [rdi+58h], 0
0x18001ab64  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextOccludingInputViewsChangedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>(void)
0x18001ab69  test    bl, 1
0x18001ab6c  jz      short loc_18001AB7B
0x18001ab6e  mov     edx, 60h ; '`'
0x18001ab73  mov     rcx, rdi; Block
0x18001ab76  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ab7b  mov     rbx, [rsp+28h+arg_0]
0x18001ab80  mov     rax, rdi
0x18001ab83  add     rsp, 20h
0x18001ab87  pop     rdi
0x18001ab88  retn
```
