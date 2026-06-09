# Windows::Internal::AssignedAccess::AssignedAccessConfigurationHelper::FindUserInfoIf__lambda_85f277e70fc2df7bef089658807efc79___

- ea: `0x18000ba5c`
- end: `0x18000bccd`
- name: `Windows::Internal::AssignedAccess::AssignedAccessConfigurationHelper::FindUserInfoIf__lambda_85f277e70fc2df7bef089658807efc79___`
- size: `625`
- prototype: `__int64 __fastcall(_QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be8c`

## callees

- `0x180006804`
- `0x18000ba5c`
- `0x18000bcd4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bbec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000bbec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bbba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bbba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bba7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bbe0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bbe0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bbb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bc05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bbb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bc05`

## string_xrefs

- `0x18000ba90`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`
- `0x18000bace`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigurationHelper::FindUserInfoIf__lambda_85f277e70fc2df7bef089658807efc79___(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  int v6; // eax
  unsigned int v7; // edi
  int v8; // edx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, _QWORD *); // rsi
  __int64 v11; // rcx
  unsigned int v12; // esi
  unsigned int v13; // eax
  __int64 v14; // r14
  int (__fastcall *v15)(__int64, HSTRING *); // r12
  HSTRING v16; // r15
  DWORD LastError; // edi
  PCWSTR StringRawBuffer; // rax
  char v19; // di
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, _QWORD *); // r14
  __int64 v22; // rcx
  __int64 v23; // rcx
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  __int64 v25; // [rsp+28h] [rbp-38h] BYREF
  __int64 v26; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-28h]
  int *v28; // [rsp+40h] [rbp-20h]
  _QWORD v29[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v31; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int i; // [rsp+B8h] [rbp+58h]

  if ( a2 )
  {
    *a3 = 0;
    v25 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 80LL))(a2, &v25);
    v7 = v6;
    if ( v6 >= 0 )
    {
      wil::GetRangeNoThrow<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *>((__int64)&v26, v25);
      v8 = *v28;
      if ( *v28 >= 0 && v27 )
      {
        v9 = v26;
        v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v26 + 48LL);
        v11 = v29[0];
        if ( v29[0] )
        {
          v29[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        v8 = v10(v9, 0, v29);
        *v28 = v8;
      }
      v12 = 0;
      v13 = v27;
      for ( i = v27; ; v13 = i )
      {
        if ( v8 < 0 || v12 == v13 )
        {
          v23 = v29[0];
          goto LABEL_35;
        }
        v14 = v29[0];
        string = 0;
        v31 = 0;
        if ( (*(int (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v29[0] + 88LL))(v29[0], &v31) < 0 || v31 > 1 )
          goto LABEL_21;
        v15 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 48LL);
        v16 = string;
        if ( string )
        {
          LastError = GetLastError();
          WindowsDeleteString(v16);
          SetLastError(LastError);
        }
        string = 0;
        if ( v15(v14, &string) < 0
          || (StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
              v19 = 1,
              (unsigned int)_o__wcsicmp(*a1, StringRawBuffer)) )
        {
LABEL_21:
          v19 = 0;
        }
        if ( string )
          WindowsDeleteString(string);
        if ( v19 )
          break;
        ++v12;
        v8 = *v28;
        if ( *v28 >= 0 && v12 < v27 )
        {
          v20 = v26;
          v21 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v26 + 48LL);
          v22 = v29[0];
          if ( v29[0] )
          {
            v29[0] = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          v8 = v21(v20, v12, v29);
          *v28 = v8;
        }
      }
      v23 = v29[0];
      if ( v29[0] )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v29[0] + 8LL))(v29[0]);
        v23 = v29[0];
      }
      *a3 = v23;
LABEL_35:
      if ( v23 )
      {
        v29[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10,
        (int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
        (const char *)(unsigned int)v6);
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD,
      (int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
      (const char *)0x80070057LL);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000ba5c  mov     [rsp-38h+arg_0], rbx
0x18000ba61  push    rbp
0x18000ba62  push    rsi
0x18000ba63  push    rdi
0x18000ba64  push    r12
0x18000ba66  push    r13
0x18000ba68  push    r14
0x18000ba6a  push    r15
0x18000ba6c  mov     rbp, rsp
0x18000ba6f  sub     rsp, 60h
0x18000ba73  mov     r13, r8
0x18000ba76  mov     r9, rdx
0x18000ba79  mov     rbx, rcx
0x18000ba7c  xor     r15d, r15d
0x18000ba7f  test    rdx, rdx
0x18000ba82  jnz     short loc_18000BAA7
0x18000ba84  mov     rcx, [rbp+38h]; this
0x18000ba88  mov     ebx, 80070057h
0x18000ba8d  mov     r9d, ebx; char *
0x18000ba90  lea     r8, aShellcommondes_2; "shellcommondesktopbase\\base\\embedded"...
0x18000ba97  lea     edx, [r15+0Dh]; void *
0x18000ba9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000baa0  mov     eax, ebx
0x18000baa2  jmp     loc_18000BCB5
0x18000baa7  mov     [r8], r15
0x18000baaa  mov     [rbp+var_38], r15
0x18000baae  mov     rax, [rdx]
0x18000bab1  lea     rdx, [rbp+var_38]
0x18000bab5  mov     rcx, r9
0x18000bab8  mov     rax, [rax+50h]
0x18000babc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bac1  mov     edi, eax
0x18000bac3  test    eax, eax
0x18000bac5  jns     short loc_18000BAFB
0x18000bac7  mov     rcx, [rbp+38h]; this
0x18000bacb  mov     r9d, eax; char *
0x18000bace  lea     r8, aShellcommondes_2; "shellcommondesktopbase\\base\\embedded"...
0x18000bad5  mov     edx, 10h; void *
0x18000bada  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000badf  mov     rcx, [rbp+var_38]
0x18000bae3  test    rcx, rcx
0x18000bae6  jz      short loc_18000BAF4
0x18000bae8  mov     rdx, [rcx]
0x18000baeb  mov     rax, [rdx+10h]
0x18000baef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baf4  mov     eax, edi
0x18000baf6  jmp     loc_18000BCB5
0x18000bafb  mov     rdx, [rbp+var_38]
0x18000baff  lea     rcx, [rbp+var_30]
0x18000bb03  call    ??$GetRangeNoThrow@PEAVAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@wil@@YA?AV?$vector_range_nothrow@U?$IVectorView@PEAVAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@@0@PEAU?$IVectorView@PEAVAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *>(Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessUserInfo *> *,long *)
0x18000bb08  mov     rax, [rbp+var_20]
0x18000bb0c  mov     edx, [rax]
0x18000bb0e  test    edx, edx
0x18000bb10  js      short loc_18000BB55
0x18000bb12  cmp     [rbp+var_28], r15d
0x18000bb16  jbe     short loc_18000BB55
0x18000bb18  mov     rdi, [rbp+var_30]
0x18000bb1c  mov     rax, [rdi]
0x18000bb1f  mov     rsi, [rax+30h]
0x18000bb23  mov     rcx, [rbp+var_10]
0x18000bb27  test    rcx, rcx
0x18000bb2a  jz      short loc_18000BB3C
0x18000bb2c  mov     [rbp+var_10], r15
0x18000bb30  mov     rdx, [rcx]
0x18000bb33  mov     rax, [rdx+10h]
0x18000bb37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb3c  lea     r8, [rbp+var_10]
0x18000bb40  xor     edx, edx
0x18000bb42  mov     rcx, rdi
0x18000bb45  mov     rax, rsi
0x18000bb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb4d  mov     edx, eax
0x18000bb4f  mov     rcx, [rbp+var_20]
0x18000bb53  mov     [rcx], eax
0x18000bb55  mov     esi, r15d
0x18000bb58  mov     eax, [rbp+var_28]
0x18000bb5b  mov     [rbp+arg_18], eax
0x18000bb5e  test    edx, edx
0x18000bb60  js      loc_18000BC85
0x18000bb66  cmp     esi, eax
0x18000bb68  jz      loc_18000BC85
0x18000bb6e  mov     r14, [rbp+var_10]
0x18000bb72  mov     [rbp+string], r15
0x18000bb76  mov     [rbp+arg_8], r15d
0x18000bb7a  mov     rax, [r14]
0x18000bb7d  lea     rdx, [rbp+arg_8]
0x18000bb81  mov     rcx, r14
0x18000bb84  mov     rax, [rax+58h]
0x18000bb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb8d  test    eax, eax
0x18000bb8f  js      short loc_18000BBF9
0x18000bb91  cmp     [rbp+arg_8], 1
0x18000bb95  ja      short loc_18000BBF9
0x18000bb97  mov     rax, [r14]
0x18000bb9a  mov     r12, [rax+30h]
0x18000bb9e  mov     r15, [rbp+string]
0x18000bba2  test    r15, r15
0x18000bba5  jz      short loc_18000BBC0
0x18000bba7  call    cs:__imp_GetLastError
0x18000bbad  mov     edi, eax
0x18000bbaf  mov     rcx, r15; string
0x18000bbb2  call    cs:__imp_WindowsDeleteString
0x18000bbb8  mov     ecx, edi; dwErrCode
0x18000bbba  call    cs:__imp_SetLastError
0x18000bbc0  xor     r15d, r15d
0x18000bbc3  mov     [rbp+string], r15
0x18000bbc7  lea     rdx, [rbp+string]
0x18000bbcb  mov     rcx, r14
0x18000bbce  mov     rax, r12
0x18000bbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbd6  test    eax, eax
0x18000bbd8  js      short loc_18000BBF9
0x18000bbda  xor     edx, edx; length
0x18000bbdc  mov     rcx, [rbp+string]; string
0x18000bbe0  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bbe6  mov     rdx, rax
0x18000bbe9  mov     rcx, [rbx]
0x18000bbec  call    cs:__imp__o__wcsicmp
0x18000bbf2  test    eax, eax
0x18000bbf4  mov     dil, 1
0x18000bbf7  jz      short loc_18000BBFC
0x18000bbf9  mov     dil, r15b
0x18000bbfc  mov     rcx, [rbp+string]; string
0x18000bc00  test    rcx, rcx
0x18000bc03  jz      short loc_18000BC0B
0x18000bc05  call    cs:__imp_WindowsDeleteString
0x18000bc0b  test    dil, dil
0x18000bc0e  jnz     short loc_18000BC66
0x18000bc10  inc     esi
0x18000bc12  mov     rax, [rbp+var_20]
0x18000bc16  mov     edx, [rax]
0x18000bc18  test    edx, edx
0x18000bc1a  js      short loc_18000BC5E
0x18000bc1c  cmp     esi, [rbp+var_28]
0x18000bc1f  jnb     short loc_18000BC5E
0x18000bc21  mov     rdi, [rbp+var_30]
0x18000bc25  mov     rax, [rdi]
0x18000bc28  mov     r14, [rax+30h]
0x18000bc2c  mov     rcx, [rbp+var_10]
0x18000bc30  test    rcx, rcx
0x18000bc33  jz      short loc_18000BC45
0x18000bc35  mov     [rbp+var_10], r15
0x18000bc39  mov     rdx, [rcx]
0x18000bc3c  mov     rax, [rdx+10h]
0x18000bc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc45  lea     r8, [rbp+var_10]
0x18000bc49  mov     edx, esi
0x18000bc4b  mov     rcx, rdi
0x18000bc4e  mov     rax, r14
0x18000bc51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc56  mov     edx, eax
0x18000bc58  mov     rax, [rbp+var_20]
0x18000bc5c  mov     [rax], edx
0x18000bc5e  mov     eax, [rbp+arg_18]
0x18000bc61  jmp     loc_18000BB5E
0x18000bc66  mov     rcx, [rbp+var_10]
0x18000bc6a  test    rcx, rcx
0x18000bc6d  jz      short loc_18000BC7F
0x18000bc6f  mov     rax, [rcx]
0x18000bc72  mov     rax, [rax+8]
0x18000bc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc7b  mov     rcx, [rbp+var_10]
0x18000bc7f  mov     [r13+0], rcx
0x18000bc83  jmp     short loc_18000BC89
0x18000bc85  mov     rcx, [rbp+var_10]
0x18000bc89  test    rcx, rcx
0x18000bc8c  jz      short loc_18000BC9E
0x18000bc8e  mov     [rbp+var_10], r15
0x18000bc92  mov     rax, [rcx]
0x18000bc95  mov     rax, [rax+10h]
0x18000bc99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc9e  mov     rcx, [rbp+var_38]
0x18000bca2  test    rcx, rcx
0x18000bca5  jz      short loc_18000BCB3
0x18000bca7  mov     rax, [rcx]
0x18000bcaa  mov     rax, [rax+10h]
0x18000bcae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcb3  xor     eax, eax
0x18000bcb5  mov     rbx, [rsp+60h+arg_0]
0x18000bcbd  add     rsp, 60h
0x18000bcc1  pop     r15
0x18000bcc3  pop     r14
0x18000bcc5  pop     r13
0x18000bcc7  pop     r12
0x18000bcc9  pop     rdi
0x18000bcca  pop     rsi
0x18000bccb  pop     rbp
0x18000bccc  retn
```
