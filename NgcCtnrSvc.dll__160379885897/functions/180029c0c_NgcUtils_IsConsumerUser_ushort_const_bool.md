# NgcUtils::IsConsumerUser(ushort const *,bool *)

- ea: `0x180029c0c`
- end: `0x180029d3c`
- name: `?IsConsumerUser@NgcUtils@@YAJPEBGPEA_N@Z`
- size: `304`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029b94`

## callees

- `0x180014384`
- `0x180016550`
- `0x180018194`
- `0x180029c0c`
- `0x18005a42c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c71`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180029c56`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180029c56`

## pseudocode

```c
__int64 __fastcall NgcUtils::IsConsumerUser(const WCHAR *this, unsigned __int16 *a2, bool *a3)
{
  BOOL v4; // ebx
  enum NgcUserAccountType *v5; // r8
  DWORD LastError; // eax
  signed int v7; // ebx
  int UserAccountType; // eax
  NgcUtils **v10; // [rsp+30h] [rbp-20h] BYREF
  PSID Sid; // [rsp+38h] [rbp-18h] BYREF
  char v12; // [rsp+40h] [rbp-10h]
  DWORD v13; // [rsp+60h] [rbp+10h] BYREF
  NgcUtils *v14; // [rsp+70h] [rbp+20h] BYREF

  if ( !this || !a2 )
    return 2147942487LL;
  *(_BYTE *)a2 = 1;
  v10 = &v14;
  v14 = 0;
  Sid = 0;
  v12 = 1;
  v4 = ConvertStringSidToSidW(this, &Sid);
  wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v10);
  if ( v4 )
  {
    v13 = 0;
    UserAccountType = NgcUtils::GetUserAccountType(v14, &v13, v5);
    v7 = UserAccountType;
    if ( UserAccountType >= 0 )
    {
      *(_BYTE *)a2 = v13 - 1 <= 1;
    }
    else if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v13 = UserAccountType;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&word_1800AE09E,
        0,
        0,
        (__int64)&v13);
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v13 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AE071,
        0,
        0,
        (__int64)&v13);
    }
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
  }
  wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
    &v14,
    0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180029c0c  mov     [rsp-8+arg_8], rbx
0x180029c11  mov     [rsp-8+arg_18], rdi
0x180029c16  push    rbp
0x180029c17  mov     rbp, rsp
0x180029c1a  sub     rsp, 50h
0x180029c1e  mov     rdi, rdx
0x180029c21  test    rcx, rcx
0x180029c24  jz      loc_180029D26
0x180029c2a  test    rdx, rdx
0x180029c2d  jz      loc_180029D26
0x180029c33  mov     byte ptr [rdx], 1
0x180029c36  lea     rax, [rbp+arg_10]
0x180029c3a  lea     rdx, [rbp+Sid]; Sid
0x180029c3e  mov     [rbp+var_20], rax
0x180029c42  mov     [rbp+arg_10], 0
0x180029c4a  mov     [rbp+Sid], 0
0x180029c52  mov     [rbp+var_10], 1
0x180029c56  call    cs:__imp_ConvertStringSidToSidW
0x180029c5d  nop     dword ptr [rax+rax+00h]
0x180029c62  lea     rcx, [rbp+var_20]
0x180029c66  mov     ebx, eax
0x180029c68  call    ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180029c6d  test    ebx, ebx
0x180029c6f  jnz     short loc_180029CBE
0x180029c71  call    cs:__imp_GetLastError
0x180029c78  nop     dword ptr [rax+rax+00h]
0x180029c7d  mov     ecx, cs:dword_1800BE0B8
0x180029c83  mov     ebx, eax
0x180029c85  cmp     ecx, 2
0x180029c88  jbe     short loc_180029CAF
0x180029c8a  mov     [rbp+arg_0], eax
0x180029c8d  lea     rdx, byte_1800AE071
0x180029c94  lea     rax, [rbp+arg_0]
0x180029c98  xor     r9d, r9d
0x180029c9b  xor     r8d, r8d
0x180029c9e  mov     [rsp+50h+var_30], rax
0x180029ca3  lea     rcx, dword_1800BE0B8
0x180029caa  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180029caf  test    ebx, ebx
0x180029cb1  jle     short loc_180029D08
0x180029cb3  movzx   ebx, bx
0x180029cb6  or      ebx, 80070000h
0x180029cbc  jmp     short loc_180029D08
0x180029cbe  mov     rcx, [rbp+arg_10]; this
0x180029cc2  lea     rdx, [rbp+arg_0]; void *
0x180029cc6  mov     [rbp+arg_0], 0
0x180029ccd  call    ?GetUserAccountType@NgcUtils@@YAJPEAXPEAW4NgcUserAccountType@@@Z; NgcUtils::GetUserAccountType(void *,NgcUserAccountType *)
0x180029cd2  mov     ebx, eax
0x180029cd4  test    eax, eax
0x180029cd6  jns     short loc_180029D17
0x180029cd8  mov     ecx, cs:dword_1800BE0B8
0x180029cde  cmp     ecx, 2
0x180029ce1  jbe     short loc_180029D08
0x180029ce3  mov     [rbp+arg_0], eax
0x180029ce6  lea     rdx, word_1800AE09E
0x180029ced  lea     rax, [rbp+arg_0]
0x180029cf1  xor     r9d, r9d
0x180029cf4  xor     r8d, r8d
0x180029cf7  mov     [rsp+50h+var_30], rax
0x180029cfc  lea     rcx, dword_1800BE0B8
0x180029d03  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180029d08  xor     edx, edx
0x180029d0a  lea     rcx, [rbp+arg_10]
0x180029d0e  call    ?reset@?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SECURITY_DESCRIPTOR *)
0x180029d13  mov     eax, ebx
0x180029d15  jmp     short loc_180029D2B
0x180029d17  mov     eax, [rbp+arg_0]
0x180029d1a  dec     eax
0x180029d1c  cmp     eax, 1
0x180029d1f  setbe   al
0x180029d22  mov     [rdi], al
0x180029d24  jmp     short loc_180029D08
0x180029d26  mov     eax, 80070057h
0x180029d2b  mov     rbx, [rsp+50h+arg_8]
0x180029d30  mov     rdi, [rsp+50h+arg_18]
0x180029d35  add     rsp, 50h
0x180029d39  pop     rbp
0x180029d3a  retn
```
