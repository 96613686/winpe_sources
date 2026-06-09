# PrivilegedAction::~PrivilegedAction(void)

- ea: `0x180037e94`
- end: `0x180037f26`
- name: `??1PrivilegedAction@@UEAA@XZ`
- size: `146`
- prototype: `void __fastcall(PrivilegedAction *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180038230`

## callees

- `0x18000abc4`
- `0x18001055c`
- `0x180013b04`
- `0x18002407c`
- `0x180037e94`
- `0x180037f58`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037ebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037ea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037ebc`

## pseudocode

```c
void __fastcall PrivilegedAction::~PrivilegedAction(HSTRING *this)
{
  unsigned __int64 v2; // rdx
  HSTRING v3; // rcx

  WindowsDeleteString(this[22]);
  this[22] = 0;
  WindowsDeleteString(this[21]);
  this[21] = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(this + 20);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(this + 19);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(this + 16);
  std::wstring::_Tidy_deallocate(this + 12);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(this + 9);
  v3 = this[7];
  this[7] = 0;
  if ( v3 )
    operator delete(v3, v2);
  ServiceDrivenAction::~ServiceDrivenAction((ServiceDrivenAction *)this);
}

```

## disassembly

```asm
0x180037e94  push    rbx
0x180037e96  sub     rsp, 20h
0x180037e9a  mov     rbx, rcx
0x180037e9d  mov     rcx, [rcx+0B0h]; string
0x180037ea4  call    cs:__imp_WindowsDeleteString
0x180037eaa  mov     qword ptr [rbx+0B0h], 0
0x180037eb5  mov     rcx, [rbx+0A8h]; string
0x180037ebc  call    cs:__imp_WindowsDeleteString
0x180037ec2  lea     rcx, [rbx+0A0h]
0x180037ec9  mov     qword ptr [rbx+0A8h], 0
0x180037ed4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180037ed9  lea     rcx, [rbx+98h]
0x180037ee0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180037ee5  lea     rcx, [rbx+80h]
0x180037eec  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180037ef1  lea     rcx, [rbx+60h]
0x180037ef5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037efa  lea     rcx, [rbx+48h]
0x180037efe  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180037f03  mov     rcx, [rbx+38h]; void *
0x180037f07  mov     qword ptr [rbx+38h], 0
0x180037f0f  test    rcx, rcx
0x180037f12  jz      short loc_180037F19
0x180037f14  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180037f19  mov     rcx, rbx; this
0x180037f1c  add     rsp, 20h
0x180037f20  pop     rbx
0x180037f21  jmp     ??1ServiceDrivenAction@@UEAA@XZ; ServiceDrivenAction::~ServiceDrivenAction(void)
```
