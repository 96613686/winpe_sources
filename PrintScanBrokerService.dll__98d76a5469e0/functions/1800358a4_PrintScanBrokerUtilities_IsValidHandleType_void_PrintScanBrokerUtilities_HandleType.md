# PrintScanBrokerUtilities::IsValidHandleType(void *,PrintScanBrokerUtilities::HandleType)

- ea: `0x1800358a4`
- end: `0x180035a5f`
- name: `?IsValidHandleType@PrintScanBrokerUtilities@@YA_NPEAXW4HandleType@1@@Z`
- size: `443`
- prototype: `bool __fastcall(HANDLE hFile, void *, enum HandleType)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030df0`
- `0x1800310b0`
- `0x180033254`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000f8a8`
- `0x180012498`
- `0x18001d0e4`
- `0x1800230fc`
- `0x1800264dc`
- `0x180030940`
- `0x1800328a8`
- `0x1800358a4`

## import_xrefs

- `ntdll!NtQueryObject` at `0x1800358fd`
- `ntdll!NtQueryObject` at `0x180035986`
- `ntdll!NtQueryObject` at `0x1800358fd`
- `ntdll!NtQueryObject` at `0x180035986`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800359ef`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800359ef`

## string_xrefs

- `0x18003599f`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall PrintScanBrokerUtilities::IsValidHandleType(HANDLE hFile, void *a2, enum HandleType a3)
{
  int v3; // esi
  unsigned int v5; // eax
  char *v6; // rbx
  size_t v7; // rdi
  int v8; // esi
  const wchar_t *v9; // rdx
  bool v10; // zf
  bool v12; // bl
  const char *v13; // [rsp+28h] [rbp-58h]
  ULONG ReturnLength; // [rsp+30h] [rbp-50h] BYREF
  PVOID ObjectInformation; // [rsp+38h] [rbp-48h] BYREF
  void *v16; // [rsp+40h] [rbp-40h]
  __int64 v17; // [rsp+48h] [rbp-38h]
  _BYTE v18[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v3 = (int)a2;
  ReturnLength = 624;
  std::vector<unsigned char>::vector<unsigned char>(&ObjectInformation, 624);
  v5 = NtQueryObject(
         hFile,
         ObjectTypeInformation,
         ObjectInformation,
         (_DWORD)v16 - (_DWORD)ObjectInformation,
         &ReturnLength);
  if ( v5 == -1073741820 || v5 == -2147483643 || v5 == -1073741789 )
  {
    v6 = (char *)v16;
    if ( ReturnLength < (unsigned __int64)((_BYTE *)v16 - (_BYTE *)ObjectInformation) )
    {
      v6 = (char *)ObjectInformation + ReturnLength;
LABEL_10:
      v16 = v6;
      goto LABEL_11;
    }
    if ( ReturnLength > (unsigned __int64)((_BYTE *)v16 - (_BYTE *)ObjectInformation) )
    {
      if ( ReturnLength <= (unsigned __int64)(v17 - (_QWORD)ObjectInformation) )
      {
        v7 = ReturnLength - ((_BYTE *)v16 - (_BYTE *)ObjectInformation);
        memset_0(v16, 0, v7);
        v6 += v7;
        goto LABEL_10;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&ObjectInformation, ReturnLength);
      LODWORD(v6) = (_DWORD)v16;
    }
LABEL_11:
    v5 = NtQueryObject(
           hFile,
           ObjectTypeInformation,
           ObjectInformation,
           (_DWORD)v6 - (_DWORD)ObjectInformation,
           &ReturnLength);
  }
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x49,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
    (const char *)v5,
    (unsigned int)"NtQueryObject failed!",
    v13);
  std::wstring::wstring((__int64)v18, *((_QWORD *)ObjectInformation + 1));
  if ( !v3 )
  {
    v9 = L"Event";
    goto LABEL_20;
  }
  v8 = v3 - 1;
  if ( v8 )
  {
    if ( v8 == 1 )
    {
      v9 = L"Key";
LABEL_20:
      v10 = (unsigned int)std::wstring::compare(v18, v9) == 0;
      goto LABEL_21;
    }
LABEL_18:
    std::wstring::_Tidy_deallocate(v18);
    std::vector<unsigned char>::_Tidy(&ObjectInformation);
    return 0;
  }
  if ( (unsigned int)std::wstring::compare(v18, L"File") )
    goto LABEL_18;
  v10 = GetFileType(hFile) == 1;
LABEL_21:
  v12 = v10;
  std::wstring::_Tidy_deallocate(v18);
  std::vector<unsigned char>::_Tidy(&ObjectInformation);
  return v12;
}

```

## disassembly

```asm
0x1800358a4  mov     [rsp-18h+arg_8], rbx
0x1800358a9  mov     [rsp-18h+arg_10], rsi
0x1800358ae  push    rbp
0x1800358af  push    rdi
0x1800358b0  push    r14
0x1800358b2  mov     rbp, rsp
0x1800358b5  sub     rsp, 80h
0x1800358bc  mov     rax, cs:__security_cookie
0x1800358c3  xor     rax, rsp
0x1800358c6  mov     [rbp+var_10], rax
0x1800358ca  mov     esi, edx
0x1800358cc  mov     r14, rcx
0x1800358cf  mov     edx, 270h
0x1800358d4  mov     [rbp+var_50], edx
0x1800358d7  lea     rcx, [rbp+ObjectInformation]
0x1800358db  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800358e0  nop
0x1800358e1  mov     r8, [rbp+ObjectInformation]; ObjectInformation
0x1800358e5  mov     r9d, dword ptr [rbp+var_40]
0x1800358e9  sub     r9d, r8d; ObjectInformationLength
0x1800358ec  lea     rax, [rbp+var_50]
0x1800358f0  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1800358f5  mov     edx, 2; ObjectInformationClass
0x1800358fa  mov     rcx, r14; Handle
0x1800358fd  call    cs:__imp_NtQueryObject
0x180035903  cmp     eax, 0C0000004h
0x180035908  jz      short loc_180035918
0x18003590a  cmp     eax, 80000005h
0x18003590f  jz      short loc_180035918
0x180035911  cmp     eax, 0C0000023h
0x180035916  jnz     short loc_18003598C
0x180035918  mov     edi, [rbp+var_50]
0x18003591b  mov     rdx, [rbp+ObjectInformation]
0x18003591f  mov     rbx, [rbp+var_40]
0x180035923  mov     rcx, rbx
0x180035926  sub     rcx, rdx
0x180035929  cmp     rdi, rcx
0x18003592c  jnb     short loc_180035934
0x18003592e  lea     rbx, [rdi+rdx]
0x180035932  jmp     short loc_180035967
0x180035934  jbe     short loc_18003596B
0x180035936  mov     rax, [rbp+var_38]
0x18003593a  sub     rax, rdx
0x18003593d  cmp     rdi, rax
0x180035940  jbe     short loc_180035954
0x180035942  mov     rdx, rdi
0x180035945  lea     rcx, [rbp+ObjectInformation]
0x180035949  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003594e  mov     rbx, [rbp+var_40]
0x180035952  jmp     short loc_18003596B
0x180035954  sub     rdi, rcx
0x180035957  mov     r8, rdi; Size
0x18003595a  xor     edx, edx; Val
0x18003595c  mov     rcx, rbx; void *
0x18003595f  call    memset_0
0x180035964  add     rbx, rdi
0x180035967  mov     [rbp+var_40], rbx
0x18003596b  mov     r8, [rbp+ObjectInformation]; ObjectInformation
0x18003596f  sub     ebx, r8d
0x180035972  lea     rax, [rbp+var_50]
0x180035976  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18003597b  mov     r9d, ebx; ObjectInformationLength
0x18003597e  mov     edx, 2; ObjectInformationClass
0x180035983  mov     rcx, r14; Handle
0x180035986  call    cs:__imp_NtQueryObject
0x18003598c  mov     rcx, [rbp+18h]; this
0x180035990  lea     rdx, aNtqueryobjectF; "NtQueryObject failed!"
0x180035997  mov     [rsp+80h+ReturnLength], rdx; unsigned int
0x18003599c  mov     r9d, eax; char *
0x18003599f  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x1800359a6  mov     edx, 49h ; 'I'; void *
0x1800359ab  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800359b0  mov     rdx, [rbp+ObjectInformation]
0x1800359b4  mov     rdx, [rdx+8]
0x1800359b8  lea     rcx, [rbp+var_30]
0x1800359bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800359c1  test    esi, esi
0x1800359c3  jz      short loc_180035A11
0x1800359c5  sub     esi, 1
0x1800359c8  jz      short loc_1800359D8
0x1800359ca  cmp     esi, 1
0x1800359cd  jnz     short loc_1800359FA
0x1800359cf  lea     rdx, aKey; "Key"
0x1800359d6  jmp     short loc_180035A18
0x1800359d8  lea     rdx, aFile; "File"
0x1800359df  lea     rcx, [rbp+var_30]
0x1800359e3  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800359e8  test    eax, eax
0x1800359ea  jnz     short loc_1800359FA
0x1800359ec  mov     rcx, r14; hFile
0x1800359ef  call    cs:__imp_GetFileType
0x1800359f5  cmp     eax, 1
0x1800359f8  jmp     short loc_180035A23
0x1800359fa  lea     rcx, [rbp+var_30]
0x1800359fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035a03  nop
0x180035a04  lea     rcx, [rbp+ObjectInformation]
0x180035a08  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180035a0d  xor     al, al
0x180035a0f  jmp     short loc_180035A3B
0x180035a11  lea     rdx, aEvent; "Event"
0x180035a18  lea     rcx, [rbp+var_30]
0x180035a1c  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180035a21  test    eax, eax
0x180035a23  setz    bl
0x180035a26  lea     rcx, [rbp+var_30]
0x180035a2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035a2f  nop
0x180035a30  lea     rcx, [rbp+ObjectInformation]
0x180035a34  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180035a39  mov     al, bl
0x180035a3b  mov     rcx, [rbp+var_10]
0x180035a3f  xor     rcx, rsp; StackCookie
0x180035a42  call    __security_check_cookie
0x180035a47  lea     r11, [rsp+80h+var_s0]
0x180035a4f  mov     rbx, [r11+28h]
0x180035a53  mov     rsi, [r11+30h]
0x180035a57  mov     rsp, r11
0x180035a5a  pop     r14
0x180035a5c  pop     rdi
0x180035a5d  pop     rbp
0x180035a5e  retn
```
