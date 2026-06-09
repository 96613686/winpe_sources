# FileOperationServiceDrivenAction::~FileOperationServiceDrivenAction(void)

- ea: `0x180037df8`
- end: `0x180037e66`
- name: `??1FileOperationServiceDrivenAction@@UEAA@XZ`
- size: `110`
- prototype: `void __fastcall(FileOperationServiceDrivenAction *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800381f0`

## callees

- `0x18000abc4`
- `0x18001055c`
- `0x18002407c`
- `0x180037df8`
- `0x180037f58`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037e27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037e27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037e39`

## pseudocode

```c
void __fastcall FileOperationServiceDrivenAction::~FileOperationServiceDrivenAction(
        FileOperationServiceDrivenAction *this)
{
  unsigned __int64 v2; // rdx
  void *v3; // rcx

  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 136);
  v3 = (void *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  if ( v3 )
    operator delete(v3, v2);
  WindowsDeleteString(*((HSTRING *)this + 14));
  *((_QWORD *)this + 14) = 0;
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 80);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 56);
  ServiceDrivenAction::~ServiceDrivenAction(this);
}

```

## disassembly

```asm
0x180037df8  push    rbx
0x180037dfa  sub     rsp, 20h
0x180037dfe  mov     rbx, rcx
0x180037e01  add     rcx, 88h
0x180037e08  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180037e0d  mov     rcx, [rbx+78h]; void *
0x180037e11  mov     qword ptr [rbx+78h], 0
0x180037e19  test    rcx, rcx
0x180037e1c  jz      short loc_180037E23
0x180037e1e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180037e23  mov     rcx, [rbx+70h]; string
0x180037e27  call    cs:__imp_WindowsDeleteString
0x180037e2d  mov     qword ptr [rbx+70h], 0
0x180037e35  mov     rcx, [rbx+68h]; string
0x180037e39  call    cs:__imp_WindowsDeleteString
0x180037e3f  lea     rcx, [rbx+50h]
0x180037e43  mov     qword ptr [rbx+68h], 0
0x180037e4b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180037e50  lea     rcx, [rbx+38h]
0x180037e54  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180037e59  mov     rcx, rbx; this
0x180037e5c  add     rsp, 20h
0x180037e60  pop     rbx
0x180037e61  jmp     ??1ServiceDrivenAction@@UEAA@XZ; ServiceDrivenAction::~ServiceDrivenAction(void)
```
