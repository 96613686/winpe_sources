# MdmHttpRequest::AddDelegationTicketHeader(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001afdc`
- end: `0x18001b23d`
- name: `?AddDelegationTicketHeader@MdmHttpRequest@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `609`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001be50`

## callees

- `0x180006174`
- `0x18000630c`
- `0x1800065c0`
- `0x18001afdc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b106`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b106`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b21c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b21c`

## string_xrefs

- `0x18001b20a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b096`: `msaauth1.0 usertoken="%s", delegationtoken="%s"`
- `0x18001b12b`: `msaauth1.0 usertoken="%s", delegationtoken="%s"`
- `0x18001b0da`: `CHR(StringCchLengthW(L"msaauth1.0 usertoken=\"%s\", delegationtoken=\"%s\"", 2147483647, &cchfStrLen))`
- `0x18001b150`: `CHR(StringCchPrintfW(pwszHeaderValue, allocSize, L"msaauth1.0 usertoken=\"%s\", delegationtoken=\"%s\"", pwszDeviceTicket, pwszDelegationTicket))`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::AddDelegationTicketHeader(_WORD *a1, _WORD *a2, void *a3)
{
  _WORD *v4; // r15
  _WORD *v5; // r14
  unsigned __int16 *v6; // rdi
  __int64 v7; // r9
  _WORD *v8; // rax
  signed int v9; // ebx
  __int64 v10; // r8
  _WORD *v11; // rax
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  unsigned __int64 v15; // rbx
  unsigned __int16 *v16; // rax
  int v17; // edx
  int v18; // ecx
  int v19; // edx
  int v20; // ecx
  int v21; // ecx
  __int64 v23; // [rsp+0h] [rbp-58h] BYREF
  unsigned __int16 *v24; // [rsp+78h] [rbp+20h]

  v4 = a2;
  v5 = a1;
  v6 = 0;
  if ( !a1 )
  {
    v9 = -2147024809;
    goto LABEL_27;
  }
  v7 = 0x7FFFFFFF;
  v8 = a1;
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
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        (_DWORD)a2,
        v9,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        55,
        "CHR(StringCchLengthW(pwszDeviceTicket, 2147483647, &cchDeviceTicketLen))");
    goto LABEL_29;
  }
  if ( v4 )
  {
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
    if ( v10 )
    {
      v12 = 0x7FFFFFFF;
      v13 = L"msaauth1.0 usertoken=\"%s\", delegationtoken=\"%s\"";
      do
      {
        if ( !*v13 )
          break;
        ++v13;
        --v12;
      }
      while ( v12 );
      v9 = v12 == 0 ? 0x80070057 : 0;
      v14 = (0x7FFFFFFF - v12) & ((unsigned __int128)-(__int128)(unsigned __int64)v12 >> 64);
      if ( v12 )
      {
        v15 = ((0x7FFFFFFF - v7) & -(__int64)(v7 != 0)) + 1 + v14 + ((0x7FFFFFFF - v10) & -(__int64)(v10 != 0));
        v16 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v15);
        v6 = v16;
        v24 = v16;
        if ( v16 )
        {
          v9 = StringCchPrintfW(v16, v15, L"msaauth1.0 usertoken=\"%s\", delegationtoken=\"%s\"", v5, v4);
          if ( v9 >= 0 )
          {
            try
            {
              std::wstring::append(a3, L"Authorization: ");
              std::wstring::append(a3, v6);
              std::wstring::append(a3, L"\r\n");
            }
            catch ( std::bad_alloc )
            {
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v21,
                  (unsigned int)&v23,
                  -2147024882,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
                  75,
                  "CHR(((HRESULT)0x8007000EL))");
              v9 = -2147024882;
              v6 = v24;
              goto LABEL_29;
            }
          }
          else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v20,
              v19,
              v9,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
              65,
              "CHR(StringCchPrintfW(pwszHeaderValue, allocSize, L\"msaauth1.0 usertoken=\\\"%s\\\", delegationtoken=\\\"%"
              "s\\\"\", pwszDeviceTicket, pwszDelegationTicket))");
          }
        }
        else
        {
          v9 = -2147024882;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v18,
              v17,
              -2147024882,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
              63,
              "CBR(pwszHeaderValue != nullptr)");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          0,
          v14,
          v9,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          57,
          "CHR(StringCchLengthW(L\"msaauth1.0 usertoken=\\\"%s\\\", delegationtoken=\\\"%s\\\"\", 2147483647, &cchfStrLen))");
      }
      goto LABEL_29;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      -2147024809,
      v9,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      56,
      "CHR(StringCchLengthW(pwszDelegationTicket, 2147483647, &cchDelegationTicketLen))");
LABEL_29:
  LocalFree(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001afdc  mov     [rsp+arg_8], rbx
0x18001afe1  push    rsi
0x18001afe2  push    rdi
0x18001afe3  push    r12
0x18001afe5  push    r14
0x18001afe7  push    r15
0x18001afe9  sub     rsp, 30h
0x18001afed  mov     rsi, r8
0x18001aff0  mov     r15, rdx
0x18001aff3  mov     r14, rcx
0x18001aff6  xor     r12d, r12d
0x18001aff9  mov     edi, r12d
0x18001affc  test    rcx, rcx
0x18001afff  jz      loc_18001B1E8
0x18001b005  mov     r10d, 7FFFFFFFh
0x18001b00b  mov     r9d, r10d
0x18001b00e  mov     rax, rcx
0x18001b011  cmp     [rax], r12w
0x18001b015  jz      short loc_18001B021
0x18001b017  add     rax, 2
0x18001b01b  sub     r9, 1
0x18001b01f  jnz     short loc_18001B011
0x18001b021  mov     rax, r9
0x18001b024  neg     rax
0x18001b027  sbb     ebx, ebx
0x18001b029  not     ebx
0x18001b02b  mov     edx, 80070057h
0x18001b030  and     ebx, edx
0x18001b032  mov     rax, r9
0x18001b035  mov     rcx, r10
0x18001b038  sub     rcx, r9
0x18001b03b  neg     rax
0x18001b03e  sbb     r11, r11
0x18001b041  and     r11, rcx
0x18001b044  test    r9, r9
0x18001b047  jz      loc_18001B1ED
0x18001b04d  test    r15, r15
0x18001b050  jz      loc_18001B1C7
0x18001b056  mov     r8, r10
0x18001b059  mov     rax, r15
0x18001b05c  cmp     [rax], r12w
0x18001b060  jz      short loc_18001B06C
0x18001b062  add     rax, 2
0x18001b066  sub     r8, 1
0x18001b06a  jnz     short loc_18001B05C
0x18001b06c  mov     rax, r8
0x18001b06f  neg     rax
0x18001b072  sbb     ebx, ebx
0x18001b074  not     ebx
0x18001b076  and     ebx, edx
0x18001b078  mov     rax, r8
0x18001b07b  mov     rcx, r10
0x18001b07e  sub     rcx, r8
0x18001b081  neg     rax
0x18001b084  sbb     r9, r9
0x18001b087  and     r9, rcx
0x18001b08a  test    r8, r8
0x18001b08d  jz      loc_18001B1C9
0x18001b093  mov     rcx, r10
0x18001b096  lea     rax, aMsaauth10Usert; "msaauth1.0 usertoken=\"%s\", delegation"...
0x18001b09d  cmp     [rax], r12w
0x18001b0a1  jz      short loc_18001B0AD
0x18001b0a3  add     rax, 2
0x18001b0a7  sub     rcx, 1
0x18001b0ab  jnz     short loc_18001B09D
0x18001b0ad  mov     rax, rcx
0x18001b0b0  neg     rax
0x18001b0b3  sbb     ebx, ebx
0x18001b0b5  not     ebx
0x18001b0b7  and     ebx, edx
0x18001b0b9  mov     rax, rcx
0x18001b0bc  sub     r10, rcx
0x18001b0bf  neg     rax
0x18001b0c2  sbb     rdx, rdx
0x18001b0c5  and     rdx, r10
0x18001b0c8  test    rcx, rcx
0x18001b0cb  jnz     short loc_18001B0F3
0x18001b0cd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b0d4  jz      loc_18001B219
0x18001b0da  lea     rax, aChrStringcchle_1; "CHR(StringCchLengthW(L\"msaauth1.0 user"...
0x18001b0e1  mov     [rsp+58h+var_30], rax
0x18001b0e6  mov     dword ptr [rsp+58h+var_38], 339h
0x18001b0ee  jmp     loc_18001B20A
0x18001b0f3  lea     rbx, [rdx+r9]
0x18001b0f7  inc     r11
0x18001b0fa  add     rbx, r11
0x18001b0fd  lea     rdx, [rbx+rbx]; uBytes
0x18001b101  mov     ecx, 40h ; '@'; uFlags
0x18001b106  call    cs:__imp_LocalAlloc
0x18001b10d  nop     dword ptr [rax+rax+00h]
0x18001b112  mov     rdi, rax
0x18001b115  mov     [rsp+58h+arg_18], rax
0x18001b11a  test    rax, rax
0x18001b11d  jz      loc_18001B1A3
0x18001b123  mov     [rsp+58h+var_38], r15
0x18001b128  mov     r9, r14
0x18001b12b  lea     r8, aMsaauth10Usert; "msaauth1.0 usertoken=\"%s\", delegation"...
0x18001b132  mov     rdx, rbx; unsigned __int64
0x18001b135  mov     rcx, rax; unsigned __int16 *
0x18001b138  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b13d  mov     ebx, eax
0x18001b13f  test    eax, eax
0x18001b141  jns     short loc_18001B169
0x18001b143  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b14a  jz      loc_18001B219
0x18001b150  lea     rax, aChrStringcchpr_1; "CHR(StringCchPrintfW(pwszHeaderValue, a"...
0x18001b157  mov     [rsp+58h+var_30], rax
0x18001b15c  mov     dword ptr [rsp+58h+var_38], 341h
0x18001b164  jmp     loc_18001B20A
0x18001b169  lea     rdx, aAuthorization; "Authorization: "
0x18001b170  mov     rcx, rsi; Src
0x18001b173  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b178  mov     rdx, rdi; void *
0x18001b17b  mov     rcx, rsi; Src
0x18001b17e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b183  lea     rdx, asc_18002B100; "\r\n"
0x18001b18a  mov     rcx, rsi; Src
0x18001b18d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b192  nop
0x18001b193  jmp     loc_18001B219
0x18001b198  mov     ebx, [rsp+58h+arg_0]
0x18001b19c  mov     rdi, [rsp+58h+arg_18]
0x18001b1a1  jmp     short loc_18001B219
0x18001b1a3  mov     ebx, 8007000Eh
0x18001b1a8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b1af  jz      short loc_18001B219
0x18001b1b1  lea     rax, aCbrPwszheaderv; "CBR(pwszHeaderValue != nullptr)"
0x18001b1b8  mov     [rsp+58h+var_30], rax
0x18001b1bd  mov     dword ptr [rsp+58h+var_38], 33Fh
0x18001b1c5  jmp     short loc_18001B20A
0x18001b1c7  mov     ebx, edx
0x18001b1c9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b1d0  jz      short loc_18001B219
0x18001b1d2  lea     rax, aChrStringcchle_0; "CHR(StringCchLengthW(pwszDelegationTick"...
0x18001b1d9  mov     [rsp+58h+var_30], rax
0x18001b1de  mov     dword ptr [rsp+58h+var_38], 338h
0x18001b1e6  jmp     short loc_18001B20A
0x18001b1e8  mov     ebx, 80070057h
0x18001b1ed  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b1f4  jz      short loc_18001B219
0x18001b1f6  lea     rax, aChrStringcchle; "CHR(StringCchLengthW(pwszDeviceTicket, "...
0x18001b1fd  mov     [rsp+58h+var_30], rax
0x18001b202  mov     dword ptr [rsp+58h+var_38], 337h
0x18001b20a  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b211  mov     r8d, ebx
0x18001b214  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b219  mov     rcx, rdi; hMem
0x18001b21c  call    cs:__imp_LocalFree
0x18001b223  nop     dword ptr [rax+rax+00h]
0x18001b228  mov     eax, ebx
0x18001b22a  mov     rbx, [rsp+58h+arg_8]
0x18001b22f  add     rsp, 30h
0x18001b233  pop     r15
0x18001b235  pop     r14
0x18001b237  pop     r12
0x18001b239  pop     rdi
0x18001b23a  pop     rsi
0x18001b23b  retn
```
