# CRemoteTextTextAndSelectionUpdatingEventArgs::`scalar deleting destructor'(uint)

- ea: `0x18001aef0`
- end: `0x18001af39`
- name: `??_GCRemoteTextTextAndSelectionUpdatingEventArgs@@UEAAPEAXI@Z`
- size: `73`
- prototype: `void *__fastcall(CRemoteTextTextAndSelectionUpdatingEventArgs *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000271c`
- `0x18001a038`
- `0x18001aef0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001af03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001af03`

## pseudocode

```c
HSTRING *__fastcall CRemoteTextTextAndSelectionUpdatingEventArgs::`scalar deleting destructor'(HSTRING *this, char a2)
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
0x18001aef0  mov     [rsp+arg_0], rbx
0x18001aef5  push    rdi
0x18001aef6  sub     rsp, 20h
0x18001aefa  mov     rdi, rcx
0x18001aefd  mov     ebx, edx
0x18001aeff  mov     rcx, [rcx+58h]; string
0x18001af03  call    cs:__imp_WindowsDeleteString
0x18001af09  mov     rcx, rdi
0x18001af0c  mov     qword ptr [rdi+58h], 0
0x18001af14  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextOccludingInputViewsChangedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>(void)
0x18001af19  test    bl, 1
0x18001af1c  jz      short loc_18001AF2B
0x18001af1e  mov     edx, 68h ; 'h'
0x18001af23  mov     rcx, rdi; Block
0x18001af26  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001af2b  mov     rbx, [rsp+28h+arg_0]
0x18001af30  mov     rax, rdi
0x18001af33  add     rsp, 20h
0x18001af37  pop     rdi
0x18001af38  retn
```
