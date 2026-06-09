# win_dox::OpcDigitalSignatureImpl::GetSignatureXml(void)

- ea: `0x1800bdb70`
- end: `0x1800bdc6e`
- name: `?GetSignatureXml@OpcDigitalSignatureImpl@win_dox@@QEAA?AU?$SMART_VECTOR@V?$scope@PEAEU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@2@XZ`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800fbc30`

## callees

- `0x1800517a0`
- `0x1800bdb70`
- `0x1800cd38c`
- `0x1800d5fd8`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bdbc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bdbc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bdbda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bdbda`

## string_xrefs

- `0x1800bdc28`: `Unable to copy string`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcDigitalSignatureImpl::GetSignatureXml(__int64 a1, __int64 a2)
{
  LPVOID v4; // rax
  void *v5; // rcx
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-B8h] BYREF

  *(_QWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = 0;
  v4 = CoTaskMemAlloc(*(unsigned int *)(a1 + 224));
  v5 = *(void **)a2;
  *(_QWORD *)a2 = v4;
  if ( v5 )
    CoTaskMemFree(v5);
  if ( !*(_QWORD *)a2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x8Du,
      0x8007000E,
      (struct win_musl::TStringEllipseBase *)L"Unable to copy string");
    throw (SplException::THResultException *)pExceptionObject;
  }
  memcpy_0(*(void **)a2, *(const void **)(a1 + 216), *(unsigned int *)(a1 + 224));
  *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 224);
  return a2;
}

```

## disassembly

```asm
0x1800bdb70  mov     rax, rsp
0x1800bdb73  push    rdi
0x1800bdb74  sub     rsp, 110h
0x1800bdb7b  mov     [rsp+118h+var_D0], 0FFFFFFFFFFFFFFFEh
0x1800bdb84  mov     [rax+18h], rbx
0x1800bdb88  mov     rax, cs:__security_cookie
0x1800bdb8f  xor     rax, rsp
0x1800bdb92  mov     [rsp+118h+var_18], rax
0x1800bdb9a  mov     rbx, rdx
0x1800bdb9d  mov     rdi, rcx
0x1800bdba0  mov     [rsp+118h+var_C8], rdx
0x1800bdba5  mov     [rsp+118h+var_D8], 0
0x1800bdbad  mov     qword ptr [rdx], 0
0x1800bdbb4  mov     dword ptr [rdx+8], 0
0x1800bdbbb  mov     [rsp+118h+var_D8], 1
0x1800bdbc3  mov     ecx, [rcx+0E0h]; cb
0x1800bdbc9  call    cs:__imp_CoTaskMemAlloc
0x1800bdbcf  mov     rcx, [rbx]; pv
0x1800bdbd2  mov     [rbx], rax
0x1800bdbd5  test    rcx, rcx
0x1800bdbd8  jz      short loc_1800BDBE0
0x1800bdbda  call    cs:__imp_CoTaskMemFree
0x1800bdbe0  mov     rcx, [rbx]; void *
0x1800bdbe3  test    rcx, rcx
0x1800bdbe6  jz      short loc_1800BDC28
0x1800bdbe8  mov     r8d, [rdi+0E0h]; Size
0x1800bdbef  mov     rdx, [rdi+0D8h]; Src
0x1800bdbf6  call    memcpy_0
0x1800bdbfb  mov     ecx, [rdi+0E0h]
0x1800bdc01  mov     [rbx+8], ecx
0x1800bdc04  mov     rax, rbx
0x1800bdc07  mov     rcx, [rsp+118h+var_18]
0x1800bdc0f  xor     rcx, rsp; StackCookie
0x1800bdc12  call    __security_check_cookie
0x1800bdc17  mov     rbx, [rsp+118h+arg_10]
0x1800bdc1f  add     rsp, 110h
0x1800bdc26  pop     rdi
0x1800bdc27  retn
0x1800bdc28  lea     rax, aUnableToCopySt; "Unable to copy string"
0x1800bdc2f  mov     [rsp+118h+var_E8], rax; struct win_musl::TStringEllipseBase *
0x1800bdc34  mov     [rsp+118h+var_F0], 8007000Eh; unsigned int
0x1800bdc3c  mov     [rsp+118h+var_F8], 8Dh; unsigned int
0x1800bdc44  lea     r9, word_18013A0B6
0x1800bdc4b  lea     r8, aNoFilename; "(no filename)"
0x1800bdc52  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1800bdc57  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800bdc5c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800bdc63  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800bdc68  call    _CxxThrowException_0
```
