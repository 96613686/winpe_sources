# MdmHttpRequest::AddDelegationTicketHeader(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001aa88`
- end: `0x18001acdc`
- name: `?AddDelegationTicketHeader@MdmHttpRequest@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(__int64, _WORD *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x18000611c`
- `0x1800062a4`
- `0x180006548`
- `0x18001aa88`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001abb2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001abb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001acc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001acc2`

## string_xrefs

- `0x18001acb0`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001ab42`: `msaauth1.0 usertoken="%s", delegationtoken="%s"`
- `0x18001abd1`: `msaauth1.0 usertoken="%s", delegationtoken="%s"`
- `0x18001ab86`: `CHR(StringCchLengthW(L"msaauth1.0 usertoken=\"%s\", delegationtoken=\"%s\"", 2147483647, &cchfStrLen))`
- `0x18001abf6`: `CHR(StringCchPrintfW(pwszHeaderValue, allocSize, L"msaauth1.0 usertoken=\"%s\", delegationtoken=\"%s\"", pwszDeviceTicket, pwszDelegationTicket))`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::AddDelegationTicketHeader(__int64 a1, _WORD *a2, _QWORD *a3)
{
  _WORD *v4; // r15
  __int64 v5; // r14
  unsigned __int16 *v6; // rdi
  __int64 v7; // r9
  _WORD *v8; // rax
  signed int v9; // ebx
  __int64 v10; // r8
  _WORD *v11; // rax
  const unsigned __int16 *v12; // rax
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  int v15; // ecx
  __int64 v17; // [rsp+0h] [rbp-58h] BYREF
  __int64 v18; // [rsp+20h] [rbp-38h]
  const char *v19; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v20; // [rsp+78h] [rbp+20h]

  v4 = a2;
  v5 = a1;
  v6 = 0;
  if ( !a1 )
  {
    v9 = -2147024809;
    goto LABEL_27;
  }
  v7 = 0x7FFFFFFF;
  v8 = (_WORD *)a1;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  LODWORD(a2) = -2147024809;
  v9 = v7 == 0 ? 0x80070057 : 0;
  LODWORD(a1) = 0x7FFFFFFF - v7;
  if ( !v7 )
  {
LABEL_27:
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      v19 = "CHR(StringCchLengthW(pwszDeviceTicket, 2147483647, &cchDeviceTicketLen))";
      LODWORD(v18) = 823;
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  if ( !v4 )
  {
    v9 = -2147024809;
    goto LABEL_24;
  }
  v10 = 0x7FFFFFFF;
  v11 = v4;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  v9 = v10 == 0 ? 0x80070057 : 0;
  LODWORD(a1) = 0x7FFFFFFF - v10;
  if ( !v10 )
  {
LABEL_24:
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      v19 = "CHR(StringCchLengthW(pwszDelegationTicket, 2147483647, &cchDelegationTicketLen))";
      LODWORD(v18) = 824;
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  a1 = 0x7FFFFFFF;
  v12 = L"msaauth1.0 usertoken=\"%s\", delegationtoken=\"%s\"";
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --a1;
  }
  while ( a1 );
  v9 = a1 == 0 ? 0x80070057 : 0;
  a2 = (_WORD *)((0x7FFFFFFF - a1) & ((unsigned __int128)-(__int128)(unsigned __int64)a1 >> 64));
  if ( a1 )
  {
    v13 = (unsigned __int64)a2
        + ((0x7FFFFFFF - v10) & -(__int64)(v10 != 0))
        + ((0x7FFFFFFF - v7) & -(__int64)(v7 != 0))
        + 1;
    v14 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v13);
    v6 = v14;
    v20 = v14;
    if ( v14 )
    {
      v9 = StringCchPrintfW(v14, v13, L"msaauth1.0 usertoken=\"%s\", delegationtoken=\"%s\"", v5, v4);
      if ( v9 >= 0 )
      {
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          std::wstring::append(a3, L"Authorization: ");
          std::wstring::append(a3, v6);
          std::wstring::append(a3, L"\r\n");
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v15,
                (unsigned int)&v17,
                -2147024882,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
                75,
                "CHR(((HRESULT)0x8007000EL))");
            v9 = -2147024882;
            v6 = v20;
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001AC3E);
          }
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v19 = "CHR(StringCchPrintfW(pwszHeaderValue, allocSize, L\"msaauth1.0 usertoken=\\\"%s\\\", delegationtoken=\\\"%"
              "s\\\"\", pwszDeviceTicket, pwszDelegationTicket))";
        LODWORD(v18) = 833;
        goto LABEL_29;
      }
    }
    else
    {
      v9 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v19 = "CBR(pwszHeaderValue != nullptr)";
        LODWORD(v18) = 831;
        goto LABEL_29;
      }
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    v19 = "CHR(StringCchLengthW(L\"msaauth1.0 usertoken=\\\"%s\\\", delegationtoken=\\\"%s\\\"\", 2147483647, &cchfStrLen))";
    LODWORD(v18) = 825;
LABEL_29:
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      (_DWORD)a2,
      v9,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      v18,
      v19);
  }
LABEL_30:
  LocalFree(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001aa88  mov     [rsp+arg_8], rbx
0x18001aa8d  push    rsi
0x18001aa8e  push    rdi
0x18001aa8f  push    r12
0x18001aa91  push    r14
0x18001aa93  push    r15
0x18001aa95  sub     rsp, 30h
0x18001aa99  mov     rsi, r8
0x18001aa9c  mov     r15, rdx
0x18001aa9f  mov     r14, rcx
0x18001aaa2  xor     r12d, r12d
0x18001aaa5  mov     edi, r12d
0x18001aaa8  test    rcx, rcx
0x18001aaab  jz      loc_18001AC8E
0x18001aab1  mov     r10d, 7FFFFFFFh
0x18001aab7  mov     r9d, r10d
0x18001aaba  mov     rax, rcx
0x18001aabd  cmp     [rax], r12w
0x18001aac1  jz      short loc_18001AACD
0x18001aac3  add     rax, 2
0x18001aac7  sub     r9, 1
0x18001aacb  jnz     short loc_18001AABD
0x18001aacd  mov     rax, r9
0x18001aad0  neg     rax
0x18001aad3  sbb     ebx, ebx
0x18001aad5  not     ebx
0x18001aad7  mov     edx, 80070057h
0x18001aadc  and     ebx, edx
0x18001aade  mov     rax, r9
0x18001aae1  mov     rcx, r10
0x18001aae4  sub     rcx, r9
0x18001aae7  neg     rax
0x18001aaea  sbb     r11, r11
0x18001aaed  and     r11, rcx
0x18001aaf0  test    r9, r9
0x18001aaf3  jz      loc_18001AC93
0x18001aaf9  test    r15, r15
0x18001aafc  jz      loc_18001AC6D
0x18001ab02  mov     r8, r10
0x18001ab05  mov     rax, r15
0x18001ab08  cmp     [rax], r12w
0x18001ab0c  jz      short loc_18001AB18
0x18001ab0e  add     rax, 2
0x18001ab12  sub     r8, 1
0x18001ab16  jnz     short loc_18001AB08
0x18001ab18  mov     rax, r8
0x18001ab1b  neg     rax
0x18001ab1e  sbb     ebx, ebx
0x18001ab20  not     ebx
0x18001ab22  and     ebx, edx
0x18001ab24  mov     rax, r8
0x18001ab27  mov     rcx, r10
0x18001ab2a  sub     rcx, r8
0x18001ab2d  neg     rax
0x18001ab30  sbb     r9, r9
0x18001ab33  and     r9, rcx
0x18001ab36  test    r8, r8
0x18001ab39  jz      loc_18001AC6F
0x18001ab3f  mov     rcx, r10
0x18001ab42  lea     rax, aMsaauth10Usert; "msaauth1.0 usertoken=\"%s\", delegation"...
0x18001ab49  cmp     [rax], r12w
0x18001ab4d  jz      short loc_18001AB59
0x18001ab4f  add     rax, 2
0x18001ab53  sub     rcx, 1
0x18001ab57  jnz     short loc_18001AB49
0x18001ab59  mov     rax, rcx
0x18001ab5c  neg     rax
0x18001ab5f  sbb     ebx, ebx
0x18001ab61  not     ebx
0x18001ab63  and     ebx, edx
0x18001ab65  mov     rax, rcx
0x18001ab68  sub     r10, rcx
0x18001ab6b  neg     rax
0x18001ab6e  sbb     rdx, rdx
0x18001ab71  and     rdx, r10
0x18001ab74  test    rcx, rcx
0x18001ab77  jnz     short loc_18001AB9F
0x18001ab79  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ab80  jz      loc_18001ACBF
0x18001ab86  lea     rax, aChrStringcchle_1; "CHR(StringCchLengthW(L\"msaauth1.0 user"...
0x18001ab8d  mov     [rsp+58h+var_30], rax
0x18001ab92  mov     dword ptr [rsp+58h+var_38], 339h
0x18001ab9a  jmp     loc_18001ACB0
0x18001ab9f  lea     rbx, [rdx+r9]
0x18001aba3  inc     r11
0x18001aba6  add     rbx, r11
0x18001aba9  lea     rdx, [rbx+rbx]; uBytes
0x18001abad  mov     ecx, 40h ; '@'; uFlags
0x18001abb2  call    cs:__imp_LocalAlloc
0x18001abb8  mov     rdi, rax
0x18001abbb  mov     [rsp+58h+arg_18], rax
0x18001abc0  test    rax, rax
0x18001abc3  jz      loc_18001AC49
0x18001abc9  mov     [rsp+58h+var_38], r15
0x18001abce  mov     r9, r14
0x18001abd1  lea     r8, aMsaauth10Usert; "msaauth1.0 usertoken=\"%s\", delegation"...
0x18001abd8  mov     rdx, rbx; unsigned __int64
0x18001abdb  mov     rcx, rax; unsigned __int16 *
0x18001abde  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001abe3  mov     ebx, eax
0x18001abe5  test    eax, eax
0x18001abe7  jns     short loc_18001AC0F
0x18001abe9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001abf0  jz      loc_18001ACBF
0x18001abf6  lea     rax, aChrStringcchpr_1; "CHR(StringCchPrintfW(pwszHeaderValue, a"...
0x18001abfd  mov     [rsp+58h+var_30], rax
0x18001ac02  mov     dword ptr [rsp+58h+var_38], 341h
0x18001ac0a  jmp     loc_18001ACB0
0x18001ac0f  lea     rdx, aAuthorization; "Authorization: "
0x18001ac16  mov     rcx, rsi; Src
0x18001ac19  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001ac1e  mov     rdx, rdi; void *
0x18001ac21  mov     rcx, rsi; Src
0x18001ac24  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001ac29  lea     rdx, asc_18002B100; "\r\n"
0x18001ac30  mov     rcx, rsi; Src
0x18001ac33  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001ac38  nop
0x18001ac39  jmp     loc_18001ACBF
0x18001ac3e  mov     ebx, [rsp+58h+arg_0]
0x18001ac42  mov     rdi, [rsp+58h+arg_18]
0x18001ac47  jmp     short loc_18001ACBF
0x18001ac49  mov     ebx, 8007000Eh
0x18001ac4e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ac55  jz      short loc_18001ACBF
0x18001ac57  lea     rax, aCbrPwszheaderv; "CBR(pwszHeaderValue != nullptr)"
0x18001ac5e  mov     [rsp+58h+var_30], rax
0x18001ac63  mov     dword ptr [rsp+58h+var_38], 33Fh
0x18001ac6b  jmp     short loc_18001ACB0
0x18001ac6d  mov     ebx, edx
0x18001ac6f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ac76  jz      short loc_18001ACBF
0x18001ac78  lea     rax, aChrStringcchle_0; "CHR(StringCchLengthW(pwszDelegationTick"...
0x18001ac7f  mov     [rsp+58h+var_30], rax
0x18001ac84  mov     dword ptr [rsp+58h+var_38], 338h
0x18001ac8c  jmp     short loc_18001ACB0
0x18001ac8e  mov     ebx, 80070057h
0x18001ac93  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ac9a  jz      short loc_18001ACBF
0x18001ac9c  lea     rax, aChrStringcchle; "CHR(StringCchLengthW(pwszDeviceTicket, "...
0x18001aca3  mov     [rsp+58h+var_30], rax
0x18001aca8  mov     dword ptr [rsp+58h+var_38], 337h
0x18001acb0  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001acb7  mov     r8d, ebx
0x18001acba  call    McTemplateU0dsqs_EventWriteTransfer
0x18001acbf  mov     rcx, rdi; hMem
0x18001acc2  call    cs:__imp_LocalFree
0x18001acc8  mov     eax, ebx
0x18001acca  mov     rbx, [rsp+58h+arg_8]
0x18001accf  add     rsp, 30h
0x18001acd3  pop     r15
0x18001acd5  pop     r14
0x18001acd7  pop     r12
0x18001acd9  pop     rdi
0x18001acda  pop     rsi
0x18001acdb  retn
```
