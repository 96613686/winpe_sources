# JobExecution::PerformValidation(_Job const &)

- ea: `0x14000e9bc`
- end: `0x14000eadf`
- name: `?PerformValidation@JobExecution@@CAJAEBU_Job@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(const struct _Job *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000e6cc`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x14000e9bc`
- `0x140017174`
- `0x14001a8d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14000ea3b`
- `msvcrt!_wcsnicmp` at `0x14000ea3b`

## string_xrefs

- `0x14000ea56`: `The file content hash does not match. Computed file content hash = %1`

## pseudocode

```c
__int64 __fastcall JobExecution::PerformValidation(const struct _Job *a1)
{
  __int64 v2; // rdx
  int v3; // edi
  wchar_t *v4; // r8
  const wchar_t *v5; // rdx
  const wchar_t *v6; // rcx
  wchar_t **v7; // rdx
  __int64 v8; // rdx
  wchar_t *String2[3]; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int64 v11; // [rsp+38h] [rbp-20h]

  std::wstring::wstring(String2, &word_14001E5B4);
  if ( *((_QWORD *)a1 + 38) )
  {
    v3 = HashFileContent((char *)a1 + 200, v2, String2);
    if ( v3 >= 0 )
    {
      v4 = (wchar_t *)*((_QWORD *)a1 + 38);
      if ( v4 != String2[2] )
        goto LABEL_9;
      v5 = (const wchar_t *)String2;
      if ( v11 >= 8 )
        v5 = String2[0];
      v6 = (const wchar_t *)((char *)a1 + 288);
      if ( *((_QWORD *)a1 + 39) >= 8u )
        v6 = *(const wchar_t **)v6;
      if ( _wcsnicmp(v6, v5, (size_t)v4) )
      {
LABEL_9:
        v7 = String2;
        if ( v11 >= 8 )
          v7 = (wchar_t **)String2[0];
        LogError(L"The file content hash does not match. Computed file content hash = %1", v7);
        v3 = -2146889721;
      }
    }
  }
  else
  {
    LogError(L"File hash value for the job is empty.");
    v3 = -2147467259;
  }
  if ( v3 >= 0 )
  {
    if ( *((_QWORD *)a1 + 3) >= 8u )
      a1 = *(const struct _Job **)a1;
    LogInfo(L"Successfully validated the content for job %1.", a1);
  }
  else
  {
    if ( *((_QWORD *)a1 + 3) >= 8u )
      a1 = *(const struct _Job **)a1;
    LogError(L"Failed to validated the app content for job %1.  Error = 0x%2!x!.", a1, (unsigned int)v3);
  }
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(String2, v8, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000e9bc  mov     [rsp+arg_8], rbx
0x14000e9c1  push    rdi
0x14000e9c2  sub     rsp, 50h
0x14000e9c6  mov     rax, cs:__security_cookie
0x14000e9cd  xor     rax, rsp
0x14000e9d0  mov     [rsp+58h+var_18], rax
0x14000e9d5  mov     rbx, rcx
0x14000e9d8  lea     rdx, word_14001E5B4
0x14000e9df  lea     rcx, [rsp+58h+String2]
0x14000e9e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000e9e9  nop
0x14000e9ea  cmp     qword ptr [rbx+130h], 0
0x14000e9f2  jz      short loc_14000EA69
0x14000e9f4  lea     rcx, [rbx+0C8h]
0x14000e9fb  lea     r8, [rsp+58h+String2]
0x14000ea00  call    ?HashFileContent@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IAEAV12@@Z; HashFileContent(std::wstring const &,uint,std::wstring &)
0x14000ea05  mov     edi, eax
0x14000ea07  test    eax, eax
0x14000ea09  js      short loc_14000EA7A
0x14000ea0b  mov     r8, [rbx+130h]; MaxCount
0x14000ea12  cmp     r8, [rsp+58h+var_28]
0x14000ea17  jnz     short loc_14000EA45
0x14000ea19  lea     rdx, [rsp+58h+String2]
0x14000ea1e  cmp     [rsp+58h+var_20], 8
0x14000ea24  cmovnb  rdx, [rsp+58h+String2]; String2
0x14000ea2a  lea     rcx, [rbx+120h]
0x14000ea31  cmp     qword ptr [rcx+18h], 8
0x14000ea36  jb      short loc_14000EA3B
0x14000ea38  mov     rcx, [rcx]; String1
0x14000ea3b  call    cs:__imp__wcsnicmp
0x14000ea41  test    eax, eax
0x14000ea43  jz      short loc_14000EA7A
0x14000ea45  lea     rdx, [rsp+58h+String2]
0x14000ea4a  cmp     [rsp+58h+var_20], 8
0x14000ea50  cmovnb  rdx, [rsp+58h+String2]
0x14000ea56  lea     rcx, aTheFileContent; "The file content hash does not match. C"...
0x14000ea5d  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000ea62  mov     edi, 80091007h
0x14000ea67  jmp     short loc_14000EA7A
0x14000ea69  lea     rcx, aFileHashValueF; "File hash value for the job is empty."
0x14000ea70  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000ea75  mov     edi, 80004005h
0x14000ea7a  test    edi, edi
0x14000ea7c  jns     short loc_14000EA9C
0x14000ea7e  cmp     qword ptr [rbx+18h], 8
0x14000ea83  jb      short loc_14000EA88
0x14000ea85  mov     rbx, [rbx]
0x14000ea88  mov     r8d, edi
0x14000ea8b  mov     rdx, rbx
0x14000ea8e  lea     rcx, aFailedToValida; "Failed to validated the app content for"...
0x14000ea95  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000ea9a  jmp     short loc_14000EAB6
0x14000ea9c  cmp     qword ptr [rbx+18h], 8
0x14000eaa1  jb      short loc_14000EAA6
0x14000eaa3  mov     rbx, [rbx]
0x14000eaa6  mov     rdx, rbx
0x14000eaa9  lea     rcx, aSuccessfullyVa; "Successfully validated the content for "...
0x14000eab0  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000eab5  nop
0x14000eab6  xor     r8d, r8d
0x14000eab9  mov     dl, 1
0x14000eabb  lea     rcx, [rsp+58h+String2]
0x14000eac0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000eac5  mov     eax, edi
0x14000eac7  mov     rcx, [rsp+58h+var_18]
0x14000eacc  xor     rcx, rsp; StackCookie
0x14000eacf  call    __security_check_cookie
0x14000ead4  mov     rbx, [rsp+58h+arg_8]
0x14000ead9  add     rsp, 50h
0x14000eadd  pop     rdi
0x14000eade  retn
```
