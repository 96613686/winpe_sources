# DeleteFileWithLogging

- ea: `0x18001042c`
- end: `0x18001056c`
- name: `DeleteFileWithLogging`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010170`

## callees

- `0x1800078b0`
- `0x180009b2c`
- `0x18000d524`
- `0x18000ebf4`
- `0x18001042c`
- `0x1800158d4`
- `0x18001a42c`
- `0x1800233ac`
- `0x180023634`
- `0x18002377c`
- `0x18002386c`
- `0x1800259b4`

## import_xrefs

- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x180010478`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x180010478`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010451`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104ac`

## string_xrefs

- `0x18001048f`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteFileWithLogging(const WCHAR *a1, _WORD *a2, unsigned int *a3)
{
  BOOL v6; // eax
  __int64 v7; // rax
  const char *v8; // r9
  __int64 result; // rax
  DWORD LastError; // r14d
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // [rsp+20h] [rbp-48h]
  _BYTE v16[16]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v17; // [rsp+38h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v6 = DeleteFileW(a1);
  try
  {
    if ( v6 )
    {
      v7 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(a3, a1);
      std::basic_ostream<unsigned short>::operator<<(v7);
      if ( std::ios_base::fail((std::ios_base *)((char *)a3 + *(int *)(*(_QWORD *)a3 + 4LL))) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E7,
          (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
          (const char *)0x8007000ELL,
          v15);
        return 2147942414LL;
      }
      ++*a2;
    }
    else
    {
      LastError = GetLastError();
      std::wstring::wstring((__int64)v16, (__int64)a1);
      if ( (Microsoft_Windows_TPM_WMIEnableBits & 2) != 0 )
      {
        v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
        McTemplateU0zq_EventWriteTransfer(v13, v12, v11, LastError);
      }
      std::wstring::_Tidy_deallocate(v16);
    }
    if ( *a2 >= 0x19u )
    {
      LogDeleteFileSuccess(a2, a3);
      *a2 = 0;
      std::wstring::wstring((__int64)v16, (__int64)&sourceString);
      std::basic_stringbuf<unsigned short>::_Tidy(a3 + 2);
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
      std::basic_stringbuf<unsigned short>::_Init(a3 + 2, v14, v17, a3[30]);
      std::wstring::_Tidy_deallocate(v16);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2F9,
                           (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18001042c  mov     [rsp+arg_18], rbx
0x180010431  push    rsi
0x180010432  push    rdi
0x180010433  push    r14
0x180010435  sub     rsp, 50h
0x180010439  mov     rax, cs:__security_cookie
0x180010440  xor     rax, rsp
0x180010443  mov     [rsp+68h+var_20], rax
0x180010448  mov     rdi, r8
0x18001044b  mov     rbx, rdx
0x18001044e  mov     rsi, rcx
0x180010451  call    cs:__imp_DeleteFileW
0x180010457  test    eax, eax
0x180010459  jz      short loc_1800104AC
0x18001045b  mov     rdx, rsi
0x18001045e  mov     rcx, rdi
0x180010461  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180010466  mov     rcx, rax
0x180010469  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x18001046e  mov     rax, [rdi]
0x180010471  movsxd  rcx, dword ptr [rax+4]
0x180010475  add     rcx, rdi
0x180010478  call    cs:__imp_?fail@ios_base@std@@QEBA_NXZ; std::ios_base::fail(void)
0x18001047e  test    al, al
0x180010480  jz      short loc_1800104A7
0x180010482  mov     rcx, [rsp+68h]; this
0x180010487  mov     ebx, 8007000Eh
0x18001048c  mov     r9d, ebx; char *
0x18001048f  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x180010496  mov     edx, 2E7h; void *
0x18001049b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800104a0  mov     eax, ebx
0x1800104a2  jmp     loc_18001054D
0x1800104a7  inc     word ptr [rbx]
0x1800104aa  jmp     short loc_1800104EA
0x1800104ac  call    cs:__imp_GetLastError
0x1800104b2  mov     r14d, eax
0x1800104b5  mov     rdx, rsi
0x1800104b8  lea     rcx, [rsp+68h+var_40]
0x1800104bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800104c2  test    byte ptr cs:Microsoft_Windows_TPM_WMIEnableBits, 2
0x1800104c9  jz      short loc_1800104E0
0x1800104cb  lea     rcx, [rsp+68h+var_40]
0x1800104d0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800104d5  mov     r8, rax
0x1800104d8  mov     r9d, r14d
0x1800104db  call    McTemplateU0zq_EventWriteTransfer
0x1800104e0  lea     rcx, [rsp+68h+var_40]
0x1800104e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800104ea  cmp     word ptr [rbx], 19h
0x1800104ee  jb      short loc_180010545
0x1800104f0  mov     rdx, rdi
0x1800104f3  mov     rcx, rbx
0x1800104f6  call    LogDeleteFileSuccess
0x1800104fb  xor     eax, eax
0x1800104fd  mov     [rbx], ax
0x180010500  lea     rdx, sourceString
0x180010507  lea     rcx, [rsp+68h+var_40]
0x18001050c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180010511  nop
0x180010512  lea     rcx, [rdi+8]
0x180010516  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x18001051b  lea     rcx, [rsp+68h+var_40]
0x180010520  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180010525  mov     rdx, rax
0x180010528  mov     r9d, [rdi+78h]
0x18001052c  mov     r8, [rsp+68h+var_30]
0x180010531  lea     rcx, [rdi+8]
0x180010535  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x18001053a  nop
0x18001053b  lea     rcx, [rsp+68h+var_40]
0x180010540  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010545  xor     eax, eax
0x180010547  jmp     short loc_18001054D
0x180010549  mov     eax, [rsp+68h+var_48]
0x18001054d  mov     rcx, [rsp+68h+var_20]
0x180010552  xor     rcx, rsp; StackCookie
0x180010555  call    __security_check_cookie
0x18001055a  mov     rbx, [rsp+68h+arg_18]
0x180010562  add     rsp, 50h
0x180010566  pop     r14
0x180010568  pop     rdi
0x180010569  pop     rsi
0x18001056a  retn
```
