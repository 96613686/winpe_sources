# GetEAAumidIfPresent(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1800321c8`
- end: `0x1800322af`
- name: `?GetEAAumidIfPresent@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180032ad0`

## callees

- `0x180007c78`
- `0x18000f9e0`
- `0x180012634`
- `0x180018400`
- `0x180026910`
- `0x180027490`
- `0x1800321c8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800321f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800321f5`
- `ext-ms-win-appmodel-daxcore-l1-1-3!GetExtendedAttributeAUMIDForAutoIdentity` at `0x180032268`
- `ext-ms-win-appmodel-daxcore-l1-1-3!GetExtendedAttributeAUMIDForAutoIdentity` at `0x180032268`

## string_xrefs

- `0x180032219`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003227f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
        (void *)0x19D5,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)ExtendedAttributeAUMIDForAutoIdentity,
        v8);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x19D1,
                  (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                  v4);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  return LastError;
}

```

## disassembly

```asm
0x1800321c8  mov     rax, rsp
0x1800321cb  mov     [rax+8], rbx
0x1800321cf  push    rdi
0x1800321d0  sub     rsp, 40h
0x1800321d4  and     qword ptr [rax-18h], 0
0x1800321d9  xor     r9d, r9d; lpSecurityAttributes
0x1800321dc  mov     rdi, rdx
0x1800321df  mov     dword ptr [rax-20h], 80h
0x1800321e6  mov     dword ptr [rax-28h], 3
0x1800321ed  lea     edx, [r9+8]; dwDesiredAccess
0x1800321f1  lea     r8d, [r9+1]; dwShareMode
0x1800321f5  call    cs:__imp_CreateFileW
0x1800321fc  nop     dword ptr [rax+rax+00h]
0x180032201  mov     rbx, rax
0x180032204  mov     [rsp+48h+arg_18], rax
0x180032209  inc     rax
0x18003220c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180032212  jnz     short loc_18003222E
0x180032214  mov     rcx, [rsp+48h]; this
0x180032219  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032220  mov     edx, 19D1h; void *
0x180032225  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003222a  mov     ebx, eax
0x18003222c  jmp     short loc_180032297
0x18003222e  xor     edx, edx
0x180032230  lea     rcx, [rsp+48h+arg_10]
0x180032235  mov     r8d, 82h
0x18003223b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180032240  lea     rdx, [rsp+48h+arg_10]
0x180032245  mov     rcx, rdi
0x180032248  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003224d  lea     rcx, [rsp+48h+arg_10]
0x180032252  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032257  mov     r9, [rdi]
0x18003225a  mov     edx, 1
0x18003225f  mov     r8d, 82h
0x180032265  mov     rcx, rbx
0x180032268  call    cs:__imp_GetExtendedAttributeAUMIDForAutoIdentity
0x18003226f  nop     dword ptr [rax+rax+00h]
0x180032274  mov     ebx, eax
0x180032276  test    eax, eax
0x180032278  jns     short loc_180032295
0x18003227a  mov     rcx, [rsp+48h]; this
0x18003227f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180032286  mov     r9d, eax; char *
0x180032289  mov     edx, 19D5h; void *
0x18003228e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032293  jmp     short loc_180032297
0x180032295  xor     ebx, ebx
0x180032297  lea     rcx, [rsp+48h+arg_18]
0x18003229c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800322a1  mov     eax, ebx
0x1800322a3  mov     rbx, [rsp+48h+arg_0]
0x1800322a8  add     rsp, 40h
0x1800322ac  pop     rdi
0x1800322ad  retn
```
