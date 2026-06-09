# GetEAAumidIfPresent(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x180035494`
- end: `0x180035571`
- name: `?GetEAAumidIfPresent@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(const WCHAR *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180035dbc`

## callees

- `0x18000720c`
- `0x18000c410`
- `0x180011414`
- `0x18001a0d4`
- `0x18001d494`
- `0x18002b244`
- `0x180035494`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800354c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800354c4`
- `ext-ms-win-appmodel-daxcore-l1-1-3!GetExtendedAttributeAUMIDForAutoIdentity` at `0x180035531`
- `ext-ms-win-appmodel-daxcore-l1-1-3!GetExtendedAttributeAUMIDForAutoIdentity` at `0x180035531`

## string_xrefs

- `0x1800354e2`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180035542`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
        (void *)0x1C1A,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)ExtendedAttributeAUMIDForAutoIdentity,
        v8);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C16,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v4);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  return LastError;
}

```

## disassembly

```asm
0x180035494  mov     rax, rsp
0x180035497  mov     [rax+8], rbx
0x18003549b  push    rdi
0x18003549c  sub     rsp, 40h
0x1800354a0  xor     r9d, r9d; lpSecurityAttributes
0x1800354a3  mov     qword ptr [rax-18h], 0
0x1800354ab  mov     rdi, rdx
0x1800354ae  mov     dword ptr [rax-20h], 80h
0x1800354b5  mov     dword ptr [rax-28h], 3
0x1800354bc  lea     edx, [r9+8]; dwDesiredAccess
0x1800354c0  lea     r8d, [r9+1]; dwShareMode
0x1800354c4  call    cs:__imp_CreateFileW
0x1800354ca  mov     rbx, rax
0x1800354cd  mov     [rsp+48h+arg_18], rax
0x1800354d2  inc     rax
0x1800354d5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800354db  jnz     short loc_1800354F7
0x1800354dd  mov     rcx, [rsp+48h]; this
0x1800354e2  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800354e9  mov     edx, 1C16h; void *
0x1800354ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800354f3  mov     ebx, eax
0x1800354f5  jmp     short loc_18003555A
0x1800354f7  xor     edx, edx
0x1800354f9  lea     rcx, [rsp+48h+arg_10]
0x1800354fe  mov     r8d, 82h
0x180035504  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180035509  lea     rdx, [rsp+48h+arg_10]
0x18003550e  mov     rcx, rdi
0x180035511  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180035516  lea     rcx, [rsp+48h+arg_10]
0x18003551b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180035520  mov     r9, [rdi]
0x180035523  mov     edx, 1
0x180035528  mov     r8d, 82h
0x18003552e  mov     rcx, rbx
0x180035531  call    cs:__imp_GetExtendedAttributeAUMIDForAutoIdentity
0x180035537  mov     ebx, eax
0x180035539  test    eax, eax
0x18003553b  jns     short loc_180035558
0x18003553d  mov     rcx, [rsp+48h]; this
0x180035542  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180035549  mov     r9d, eax; char *
0x18003554c  mov     edx, 1C1Ah; void *
0x180035551  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035556  jmp     short loc_18003555A
0x180035558  xor     ebx, ebx
0x18003555a  lea     rcx, [rsp+48h+arg_18]
0x18003555f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180035564  mov     eax, ebx
0x180035566  mov     rbx, [rsp+48h+arg_0]
0x18003556b  add     rsp, 40h
0x18003556f  pop     rdi
0x180035570  retn
```
