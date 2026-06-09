# Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo::`vector deleting destructor'(uint)

- ea: `0x18000f970`
- end: `0x18000f9cb`
- name: `??_EParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@UEAAPEAXI@Z`
- size: `91`
- prototype: `HSTRING *__fastcall(HSTRING *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800036e4`
- `0x180005f54`
- `0x18000f970`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f983`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f995`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f983`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f995`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo::`vector deleting destructor'(
        HSTRING *this,
        char a2)
{
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[8]);
  this[8] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInfo,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInfo,Microsoft::WRL::FtmBase>(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000f970  mov     [rsp+arg_0], rbx
0x18000f975  push    rdi
0x18000f976  sub     rsp, 20h
0x18000f97a  mov     rdi, rcx
0x18000f97d  mov     ebx, edx
0x18000f97f  mov     rcx, [rcx+48h]; string
0x18000f983  call    cs:__imp_WindowsDeleteString
0x18000f989  mov     qword ptr [rdi+48h], 0
0x18000f991  mov     rcx, [rdi+40h]; string
0x18000f995  call    cs:__imp_WindowsDeleteString
0x18000f99b  mov     rcx, rdi
0x18000f99e  mov     qword ptr [rdi+40h], 0
0x18000f9a6  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInfo,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::FamilySafety::AppLimits::IParentalControlsAppInfo,Microsoft::WRL::FtmBase>(void)
0x18000f9ab  test    bl, 1
0x18000f9ae  jz      short loc_18000F9BD
0x18000f9b0  mov     edx, 50h ; 'P'
0x18000f9b5  mov     rcx, rdi; Block
0x18000f9b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f9bd  mov     rbx, [rsp+28h+arg_0]
0x18000f9c2  mov     rax, rdi
0x18000f9c5  add     rsp, 20h
0x18000f9c9  pop     rdi
0x18000f9ca  retn
```
