# GetEAAumidIfPresent(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180031f0c`
- end: `0x180031ff3`
- name: `?GetEAAumidIfPresent@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180032810`

## callees

- `0x180007c78`
- `0x18000f9e0`
- `0x180012634`
- `0x180018400`
- `0x180026840`
- `0x1800273c0`
- `0x180031f0c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031f39`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031f39`
- `ext-ms-win-appmodel-daxcore-l1-1-3!GetExtendedAttributeAUMIDForAutoIdentity` at `0x180031fac`
- `ext-ms-win-appmodel-daxcore-l1-1-3!GetExtendedAttributeAUMIDForAutoIdentity` at `0x180031fac`

## string_xrefs

- `0x180031f5d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180031fc3`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall GetEAAumidIfPresent(const WCHAR *a1, _QWORD *a2)
{
  HANDLE FileW; // rbx
  const char *v4; // r9
  unsigned int LastError; // ebx
  int ExtendedAttributeAUMIDForAutoIdentity; // eax
  int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v10; // [rsp+60h] [rbp+18h] BYREF
  HANDLE v11; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(a1, 8u, 1u, 0, 3u, 0x80u, 0);
  v11 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v10,
      0,
      130);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a2,
      &v10);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
    ExtendedAttributeAUMIDForAutoIdentity = GetExtendedAttributeAUMIDForAutoIdentity(FileW, 1, 130, *a2);
    LastError = ExtendedAttributeAUMIDForAutoIdentity;
    if ( ExtendedAttributeAUMIDForAutoIdentity >= 0 )
      LastError = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x199E,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)ExtendedAttributeAUMIDForAutoIdentity,
        v8);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x199A,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v4);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  return LastError;
}

```

## disassembly

```asm
0x180031f0c  mov     rax, rsp
0x180031f0f  mov     [rax+8], rbx
0x180031f13  push    rdi
0x180031f14  sub     rsp, 40h
0x180031f18  and     qword ptr [rax-18h], 0
0x180031f1d  xor     r9d, r9d; lpSecurityAttributes
0x180031f20  mov     rdi, rdx
0x180031f23  mov     dword ptr [rax-20h], 80h
0x180031f2a  mov     dword ptr [rax-28h], 3
0x180031f31  lea     edx, [r9+8]; dwDesiredAccess
0x180031f35  lea     r8d, [r9+1]; dwShareMode
0x180031f39  call    cs:__imp_CreateFileW
0x180031f40  nop     dword ptr [rax+rax+00h]
0x180031f45  mov     rbx, rax
0x180031f48  mov     [rsp+48h+arg_18], rax
0x180031f4d  inc     rax
0x180031f50  test    rax, 0FFFFFFFFFFFFFFFEh
0x180031f56  jnz     short loc_180031F72
0x180031f58  mov     rcx, [rsp+48h]; this
0x180031f5d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180031f64  mov     edx, 199Ah; void *
0x180031f69  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031f6e  mov     ebx, eax
0x180031f70  jmp     short loc_180031FDB
0x180031f72  xor     edx, edx
0x180031f74  lea     rcx, [rsp+48h+arg_10]
0x180031f79  mov     r8d, 82h
0x180031f7f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180031f84  lea     rdx, [rsp+48h+arg_10]
0x180031f89  mov     rcx, rdi
0x180031f8c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180031f91  lea     rcx, [rsp+48h+arg_10]
0x180031f96  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180031f9b  mov     r9, [rdi]
0x180031f9e  mov     edx, 1
0x180031fa3  mov     r8d, 82h
0x180031fa9  mov     rcx, rbx
0x180031fac  call    cs:__imp_GetExtendedAttributeAUMIDForAutoIdentity
0x180031fb3  nop     dword ptr [rax+rax+00h]
0x180031fb8  mov     ebx, eax
0x180031fba  test    eax, eax
0x180031fbc  jns     short loc_180031FD9
0x180031fbe  mov     rcx, [rsp+48h]; this
0x180031fc3  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180031fca  mov     r9d, eax; char *
0x180031fcd  mov     edx, 199Eh; void *
0x180031fd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031fd7  jmp     short loc_180031FDB
0x180031fd9  xor     ebx, ebx
0x180031fdb  lea     rcx, [rsp+48h+arg_18]
0x180031fe0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031fe5  mov     eax, ebx
0x180031fe7  mov     rbx, [rsp+48h+arg_0]
0x180031fec  add     rsp, 40h
0x180031ff0  pop     rdi
0x180031ff1  retn
```
