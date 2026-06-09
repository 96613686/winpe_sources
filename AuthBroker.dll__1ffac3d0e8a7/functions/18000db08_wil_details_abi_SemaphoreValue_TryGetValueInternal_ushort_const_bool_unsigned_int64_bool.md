# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000db08`
- end: `0x18000dcc6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `HRESULT __fastcall(const wchar_t *name, bool value, unsigned __int64 *name, bool *is64Bit)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000da84`

## callees

- `0x180003f40`
- `0x1800053f8`
- `0x1800060f8`
- `0x18000a28c`
- `0x18000baf0`
- `0x18000d3c0`
- `0x18000db08`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000db71`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dc11`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000db71`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000dc11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db81`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *name,
        bool value,
        unsigned __int64 *a3,
        bool *is64Bit)
{
  HANDLE v5; // rax
  unsigned int LastError; // ebx
  HRESULT ValueFromSemaphore; // eax
  HANDLE v8; // rax
  HRESULT v9; // eax
  int countHigh; // [rsp+20h] [rbp-E0h] BYREF
  int countLow; // [rsp+24h] [rbp-DCh] BYREF
  wil::unique_any_t<wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > semaphoreHigh; // [rsp+28h] [rbp-D8h] BYREF
  wil::unique_any_t<wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > semaphoreLow; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t localName[264]; // [rsp+40h] [rbp-C0h] BYREF
  void *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(localName, 0x104u, name);
  StringCchCatW(localName, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, localName);
  semaphoreLow.m_ptr = v5;
  if ( v5 )
  {
    countLow = 0;
    countHigh = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &countLow);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0xD6u, "wil", ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(localName, 0x104u, L"h");
    v8 = OpenSemaphoreW(0x1F0003u, 0, localName);
    semaphoreHigh.m_ptr = v8;
    if ( v8 )
    {
      v9 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v8, &countHigh);
      LastError = v9;
      if ( v9 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&semaphoreHigh);
        *a3 = countLow | (unsigned __int64)((__int64)countHigh << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, 0xDEu, "wil", v9);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, 0xDCu, "wil");
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&semaphoreHigh);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, 0xD0u, "wil");
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&semaphoreLow);
  return LastError;
}

```

## disassembly

```asm
0x18000db08  mov     [rsp-8+arg_8], rbx
0x18000db0d  push    rbp
0x18000db0e  push    rdi
0x18000db0f  push    r14
0x18000db11  lea     rbp, [rsp-160h]
0x18000db19  sub     rsp, 260h
0x18000db20  mov     rax, cs:__security_cookie
0x18000db27  xor     rax, rsp
0x18000db2a  mov     [rbp+170h+var_20], rax
0x18000db31  mov     rdi, value
0x18000db34  mov     qword ptr [value], 0
0x18000db3b  mov     value, name; pszSrc
0x18000db3e  mov     r14d, 104h
0x18000db44  mov     edx, r14d; cchDest
0x18000db47  lea     name, [rsp+270h+localName]; pszDest
0x18000db4c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000db51  lea     value, aP0; "_p0"
0x18000db58  mov     edx, r14d; cchDest
0x18000db5b  lea     name, [rsp+270h+localName]; pszDest
0x18000db60  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000db65  lea     value, [rsp+270h+localName]; lpName
0x18000db6a  xor     edx, edx; bInheritHandle
0x18000db6c  mov     ecx, 1F0003h; dwDesiredAccess
0x18000db71  call    cs:__imp_OpenSemaphoreW
0x18000db77  mov     [rsp+270h+semaphoreLow.m_ptr], rax
0x18000db7c  test    rax, rax
0x18000db7f  jnz     short loc_18000DBAE
0x18000db81  call    cs:__imp_GetLastError
0x18000db87  cmp     eax, 2
0x18000db8a  jz      loc_18000DC95
0x18000db90  mov     name, [rbp+178h]; callerReturnAddress
0x18000db97  lea     value, aWil; "wil"
0x18000db9e  lea     edx, [r14-34h]; lineNumber
0x18000dba2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dba7  mov     ebx, eax
0x18000dba9  jmp     loc_18000DC97
0x18000dbae  lea     rdx, [rsp+270h+countLow]; count
0x18000dbb3  mov     [rsp+270h+countLow], 0
0x18000dbbb  mov     name, rax; semaphore
0x18000dbbe  mov     [rsp+270h+countHigh], 0
0x18000dbc6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000dbcb  mov     ebx, eax
0x18000dbcd  test    eax, eax
0x18000dbcf  jns     short loc_18000DBF1
0x18000dbd1  mov     name, [rbp+178h]; callerReturnAddress
0x18000dbd8  lea     value, aWil; "wil"
0x18000dbdf  mov     r9d, eax; hr
0x18000dbe2  mov     edx, 0D6h; lineNumber
0x18000dbe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbec  jmp     loc_18000DC97
0x18000dbf1  lea     value, asc_1800271D8; "h"
0x18000dbf8  mov     rdx, r14; cchDest
0x18000dbfb  lea     name, [rsp+270h+localName]; pszDest
0x18000dc00  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000dc05  lea     value, [rsp+270h+localName]; lpName
0x18000dc0a  xor     edx, edx; bInheritHandle
0x18000dc0c  mov     ecx, 1F0003h; dwDesiredAccess
0x18000dc11  call    cs:__imp_OpenSemaphoreW
0x18000dc17  mov     [rsp+270h+semaphoreHigh.m_ptr], rax
0x18000dc1c  test    rax, rax
0x18000dc1f  jnz     short loc_18000DC47
0x18000dc21  mov     name, [rbp+178h]; callerReturnAddress
0x18000dc28  lea     value, aWil; "wil"
0x18000dc2f  mov     edx, 0DCh; lineNumber
0x18000dc34  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dc39  mov     ebx, eax
0x18000dc3b  lea     name, [rsp+270h+semaphoreHigh]; this
0x18000dc40  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000dc45  jmp     short loc_18000DC97
0x18000dc47  lea     rdx, [rsp+270h+countHigh]; count
0x18000dc4c  mov     name, rax; semaphore
0x18000dc4f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000dc54  mov     ebx, eax
0x18000dc56  test    eax, eax
0x18000dc58  jns     short loc_18000DC77
0x18000dc5a  mov     name, [rbp+178h]; callerReturnAddress
0x18000dc61  lea     value, aWil; "wil"
0x18000dc68  mov     r9d, eax; hr
0x18000dc6b  mov     edx, 0DEh; lineNumber
0x18000dc70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc75  jmp     short loc_18000DC3B
0x18000dc77  lea     name, [rsp+270h+semaphoreHigh]; this
0x18000dc7c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000dc81  movsxd  name, [rsp+270h+countHigh]
0x18000dc86  movsxd  rax, [rsp+270h+countLow]
0x18000dc8b  shl     name, 1Fh
0x18000dc8f  or      name, rax
0x18000dc92  mov     [rdi], name
0x18000dc95  xor     ebx, ebx
0x18000dc97  lea     name, [rsp+270h+semaphoreLow]; this
0x18000dc9c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000dca1  mov     eax, ebx
0x18000dca3  mov     name, [rbp+170h+var_20]
0x18000dcaa  xor     name, rsp; StackCookie
0x18000dcad  call    __security_check_cookie
0x18000dcb2  mov     rbx, [rsp+270h+arg_8]
0x18000dcba  add     rsp, 260h
0x18000dcc1  pop     r14
0x18000dcc3  pop     rdi
0x18000dcc4  pop     rbp
0x18000dcc5  retn
```
