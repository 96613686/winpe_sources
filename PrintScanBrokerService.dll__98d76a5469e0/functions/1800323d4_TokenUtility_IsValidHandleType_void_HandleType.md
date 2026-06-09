# TokenUtility::_IsValidHandleType(void *,HandleType)

- ea: `0x1800323d4`
- end: `0x180032581`
- name: `?_IsValidHandleType@TokenUtility@@AEAA_NPEAXW4HandleType@@@Z`
- size: `429`
- prototype: `bool(TokenUtility *__hidden this, void *, enum HandleType)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030df0`
- `0x1800310b0`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000f8a8`
- `0x180012498`
- `0x18001d0e4`
- `0x1800230fc`
- `0x1800264dc`
- `0x180030940`
- `0x1800323d4`
- `0x1800328a8`

## import_xrefs

- `ntdll!NtQueryObject` at `0x18003242e`
- `ntdll!NtQueryObject` at `0x1800324b7`
- `ntdll!NtQueryObject` at `0x18003242e`
- `ntdll!NtQueryObject` at `0x1800324b7`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180032512`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180032512`

## string_xrefs

- `0x1800324d0`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall TokenUtility::_IsValidHandleType(TokenUtility *this, void *a2, enum HandleType a3)
{
  unsigned int v5; // eax
  char *v6; // rbx
  size_t v7; // rdi
  bool v8; // zf
  bool v10; // bl
  const char *v11; // [rsp+28h] [rbp-58h]
  ULONG ReturnLength; // [rsp+30h] [rbp-50h] BYREF
  PVOID ObjectInformation; // [rsp+38h] [rbp-48h] BYREF
  void *v14; // [rsp+40h] [rbp-40h]
  __int64 v15; // [rsp+48h] [rbp-38h]
  _BYTE v16[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  ReturnLength = 624;
  std::vector<unsigned char>::vector<unsigned char>(&ObjectInformation, 624);
  v5 = NtQueryObject(
         a2,
         ObjectTypeInformation,
         ObjectInformation,
         (_DWORD)v14 - (_DWORD)ObjectInformation,
         &ReturnLength);
  if ( v5 == -1073741820 || v5 == -2147483643 || v5 == -1073741789 )
  {
    v6 = (char *)v14;
    if ( ReturnLength < (unsigned __int64)((_BYTE *)v14 - (_BYTE *)ObjectInformation) )
    {
      v6 = (char *)ObjectInformation + ReturnLength;
LABEL_10:
      v14 = v6;
      goto LABEL_11;
    }
    if ( ReturnLength > (unsigned __int64)((_BYTE *)v14 - (_BYTE *)ObjectInformation) )
    {
      if ( ReturnLength <= (unsigned __int64)(v15 - (_QWORD)ObjectInformation) )
      {
        v7 = ReturnLength - ((_BYTE *)v14 - (_BYTE *)ObjectInformation);
        memset_0(v14, 0, v7);
        v6 += v7;
        goto LABEL_10;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&ObjectInformation, ReturnLength);
      LODWORD(v6) = (_DWORD)v14;
    }
LABEL_11:
    v5 = NtQueryObject(
           a2,
           ObjectTypeInformation,
           ObjectInformation,
           (_DWORD)v6 - (_DWORD)ObjectInformation,
           &ReturnLength);
  }
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x190,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v5,
    (unsigned int)"NtQueryObject failed!",
    v11);
  std::wstring::wstring((__int64)v16, *((_QWORD *)ObjectInformation + 1));
  if ( a3 )
  {
    if ( a3 != Asymmetric || (unsigned int)std::wstring::compare(v16, L"File") )
    {
      std::wstring::_Tidy_deallocate(v16);
      std::vector<unsigned char>::_Tidy(&ObjectInformation);
      return 0;
    }
    v8 = GetFileType(a2) == 1;
  }
  else
  {
    v8 = (unsigned int)std::wstring::compare(v16, L"Event") == 0;
  }
  v10 = v8;
  std::wstring::_Tidy_deallocate(v16);
  std::vector<unsigned char>::_Tidy(&ObjectInformation);
  return v10;
}

```

## disassembly

```asm
0x1800323d4  mov     [rsp-18h+arg_0], rbx
0x1800323d9  mov     [rsp-18h+arg_10], rsi
0x1800323de  push    rbp
0x1800323df  push    rdi
0x1800323e0  push    r14
0x1800323e2  mov     rbp, rsp
0x1800323e5  sub     rsp, 80h
0x1800323ec  mov     rax, cs:__security_cookie
0x1800323f3  xor     rax, rsp
0x1800323f6  mov     [rbp+var_10], rax
0x1800323fa  mov     esi, r8d
0x1800323fd  mov     r14, rdx
0x180032400  mov     edx, 270h
0x180032405  mov     [rbp+var_50], edx
0x180032408  lea     rcx, [rbp+ObjectInformation]
0x18003240c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180032411  nop
0x180032412  mov     r8, [rbp+ObjectInformation]; ObjectInformation
0x180032416  mov     r9d, dword ptr [rbp+var_40]
0x18003241a  sub     r9d, r8d; ObjectInformationLength
0x18003241d  lea     rax, [rbp+var_50]
0x180032421  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180032426  mov     edx, 2; ObjectInformationClass
0x18003242b  mov     rcx, r14; Handle
0x18003242e  call    cs:__imp_NtQueryObject
0x180032434  cmp     eax, 0C0000004h
0x180032439  jz      short loc_180032449
0x18003243b  cmp     eax, 80000005h
0x180032440  jz      short loc_180032449
0x180032442  cmp     eax, 0C0000023h
0x180032447  jnz     short loc_1800324BD
0x180032449  mov     edi, [rbp+var_50]
0x18003244c  mov     rdx, [rbp+ObjectInformation]
0x180032450  mov     rbx, [rbp+var_40]
0x180032454  mov     rcx, rbx
0x180032457  sub     rcx, rdx
0x18003245a  cmp     rdi, rcx
0x18003245d  jnb     short loc_180032465
0x18003245f  lea     rbx, [rdi+rdx]
0x180032463  jmp     short loc_180032498
0x180032465  jbe     short loc_18003249C
0x180032467  mov     rax, [rbp+var_38]
0x18003246b  sub     rax, rdx
0x18003246e  cmp     rdi, rax
0x180032471  jbe     short loc_180032485
0x180032473  mov     rdx, rdi
0x180032476  lea     rcx, [rbp+ObjectInformation]
0x18003247a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003247f  mov     rbx, [rbp+var_40]
0x180032483  jmp     short loc_18003249C
0x180032485  sub     rdi, rcx
0x180032488  mov     r8, rdi; Size
0x18003248b  xor     edx, edx; Val
0x18003248d  mov     rcx, rbx; void *
0x180032490  call    memset_0
0x180032495  add     rbx, rdi
0x180032498  mov     [rbp+var_40], rbx
0x18003249c  mov     r8, [rbp+ObjectInformation]; ObjectInformation
0x1800324a0  sub     ebx, r8d
0x1800324a3  lea     rax, [rbp+var_50]
0x1800324a7  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1800324ac  mov     r9d, ebx; ObjectInformationLength
0x1800324af  mov     edx, 2; ObjectInformationClass
0x1800324b4  mov     rcx, r14; Handle
0x1800324b7  call    cs:__imp_NtQueryObject
0x1800324bd  mov     rcx, [rbp+18h]; this
0x1800324c1  lea     rdx, aNtqueryobjectF; "NtQueryObject failed!"
0x1800324c8  mov     [rsp+80h+ReturnLength], rdx; unsigned int
0x1800324cd  mov     r9d, eax; char *
0x1800324d0  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x1800324d7  mov     edx, 190h; void *
0x1800324dc  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800324e1  mov     rdx, [rbp+ObjectInformation]
0x1800324e5  mov     rdx, [rdx+8]
0x1800324e9  lea     rcx, [rbp+var_30]
0x1800324ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800324f2  test    esi, esi
0x1800324f4  jz      short loc_180032533
0x1800324f6  cmp     esi, 1
0x1800324f9  jnz     short loc_18003251C
0x1800324fb  lea     rdx, aFile; "File"
0x180032502  lea     rcx, [rbp+var_30]
0x180032506  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003250b  test    eax, eax
0x18003250d  jnz     short loc_18003251C
0x18003250f  mov     rcx, r14; hFile
0x180032512  call    cs:__imp_GetFileType
0x180032518  cmp     eax, esi
0x18003251a  jmp     short loc_180032545
0x18003251c  lea     rcx, [rbp+var_30]
0x180032520  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032525  nop
0x180032526  lea     rcx, [rbp+ObjectInformation]
0x18003252a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003252f  xor     al, al
0x180032531  jmp     short loc_18003255D
0x180032533  lea     rdx, aEvent; "Event"
0x18003253a  lea     rcx, [rbp+var_30]
0x18003253e  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180032543  test    eax, eax
0x180032545  setz    bl
0x180032548  lea     rcx, [rbp+var_30]
0x18003254c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032551  nop
0x180032552  lea     rcx, [rbp+ObjectInformation]
0x180032556  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003255b  mov     al, bl
0x18003255d  mov     rcx, [rbp+var_10]
0x180032561  xor     rcx, rsp; StackCookie
0x180032564  call    __security_check_cookie
0x180032569  lea     r11, [rsp+80h+var_s0]
0x180032571  mov     rbx, [r11+20h]
0x180032575  mov     rsi, [r11+30h]
0x180032579  mov     rsp, r11
0x18003257c  pop     r14
0x18003257e  pop     rdi
0x18003257f  pop     rbp
0x180032580  retn
```
