# CRemoteTextFeatureModeUpdatingEventArgs::`scalar deleting destructor'(uint)

- ea: `0x18001ac50`
- end: `0x18001ac99`
- name: `??_GCRemoteTextFeatureModeUpdatingEventArgs@@UEAAPEAXI@Z`
- size: `73`
- prototype: `void *__fastcall(CRemoteTextFeatureModeUpdatingEventArgs *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000271c`
- `0x18001a038`
- `0x18001ac50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ac63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ac63`

## pseudocode

```c
HSTRING *__fastcall CRemoteTextFeatureModeUpdatingEventArgs::`scalar deleting destructor'(HSTRING *this, char a2)
{
  WindowsDeleteString(this[12]);
  this[12] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001ac50  mov     [rsp+arg_0], rbx
0x18001ac55  push    rdi
0x18001ac56  sub     rsp, 20h
0x18001ac5a  mov     rdi, rcx
0x18001ac5d  mov     ebx, edx
0x18001ac5f  mov     rcx, [rcx+60h]; string
0x18001ac63  call    cs:__imp_WindowsDeleteString
0x18001ac69  mov     rcx, rdi
0x18001ac6c  mov     qword ptr [rdi+60h], 0
0x18001ac74  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIRemoteTextOccludingInputViewsChangedEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Internal::Text::Remote::IRemoteTextOccludingInputViewsChangedEventArgs,Microsoft::WRL::FtmBase>(void)
0x18001ac79  test    bl, 1
0x18001ac7c  jz      short loc_18001AC8B
0x18001ac7e  mov     edx, 68h ; 'h'
0x18001ac83  mov     rcx, rdi; Block
0x18001ac86  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ac8b  mov     rbx, [rsp+28h+arg_0]
0x18001ac90  mov     rax, rdi
0x18001ac93  add     rsp, 20h
0x18001ac97  pop     rdi
0x18001ac98  retn
```
