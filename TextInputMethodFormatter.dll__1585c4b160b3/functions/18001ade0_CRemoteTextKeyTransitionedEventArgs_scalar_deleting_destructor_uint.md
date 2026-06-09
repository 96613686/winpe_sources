# CRemoteTextKeyTransitionedEventArgs::`scalar deleting destructor'(uint)

- ea: `0x18001ade0`
- end: `0x18001ae47`
- name: `??_GCRemoteTextKeyTransitionedEventArgs@@UEAAPEAXI@Z`
- size: `103`
- prototype: `void *__fastcall(CRemoteTextKeyTransitionedEventArgs *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000271c`
- `0x18001a038`
- `0x18001ade0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001adf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ae0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001adf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ae0e`

## pseudocode

```c
HSTRING *__fastcall CRemoteTextKeyTransitionedEventArgs::`scalar deleting destructor'(HSTRING *this, char a2)
{
  WindowsDeleteString(this[56]);
  this[56] = 0;
  WindowsDeleteString(this[54]);
  this[54] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001ade0  mov     [rsp+arg_0], rbx
0x18001ade5  push    rdi
0x18001ade6  sub     rsp, 20h
0x18001adea  mov     rdi, rcx
0x18001aded  mov     ebx, edx
0x18001adef  mov     rcx, [rcx+1C0h]; string
0x18001adf6  call    cs:__imp_WindowsDeleteString
0x18001adfc  mov     qword ptr [rdi+1C0h], 0
0x18001ae07  mov     rcx, [rdi+1B0h]; string
0x18001ae0e  call    cs:__imp_WindowsDeleteString
0x18001ae14  mov     rcx, rdi
0x18001ae17  mov     qword ptr [rdi+1B0h], 0
0x18001ae22  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextOccludingInputViewsChangedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>(void)
0x18001ae27  test    bl, 1
0x18001ae2a  jz      short loc_18001AE39
0x18001ae2c  mov     edx, 1C8h
0x18001ae31  mov     rcx, rdi; Block
0x18001ae34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ae39  mov     rbx, [rsp+28h+arg_0]
0x18001ae3e  mov     rax, rdi
0x18001ae41  add     rsp, 20h
0x18001ae45  pop     rdi
0x18001ae46  retn
```
