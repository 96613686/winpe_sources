# MdmCommandParser::ParseLockCommand(uchar *,ulong,ushort * *,ushort * *,int *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18000a528`
- end: `0x18000ac20`
- name: `?ParseLockCommand@MdmCommandParser@@SAJPEAEKPEAPEAG1PEAHAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1784`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004b90`

## callees

- `0x180001520`
- `0x180001544`
- `0x18000269c`
- `0x180002bb8`
- `0x180002de8`
- `0x180002e54`
- `0x1800065c0`
- `0x1800098f0`
- `0x18000a528`
- `0x18001a8c0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18000a916`

## string_xrefs

- `0x18000a5cf`: `CPR(pbCommand)`
- `0x18000a740`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000a7ca`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000a88f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000aaab`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000abe3`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000aa49`: `CBR(cbCommand >= 1)`
- `0x18000aa97`: `CBR(cbCommand >= 1)`
- `0x18000ab2c`: `CBR(cbCommand >= 1)`
- `0x18000ab5a`: `CBR(cbCommand >= 1)`
- `0x18000abcf`: `CBR(cbCommand >= 1)`
- `0x18000aafe`: `CBR(cbCommand >= cbPin)`
- `0x18000a72c`: `CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, cbPin, &pwszPin))`
- `0x18000aa70`: `CBR(cbCommand >= cbCpn)`
- `0x18000a7b6`: `CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, cbCpn, &pwszCpn))`
- `0x18000a9a6`: `CBR(cbCommand >= 16)`
- `0x18000a87b`: `CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, 16, &pwszCid))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MdmCommandParser::ParseLockCommand(
        __int64 a1,
        int a2,
        void **a3,
        unsigned __int16 **a4,
        _DWORD *a5,
        __int64 *a6)
{
  __int64 v7; // rax
  unsigned __int16 *v8; // r12
  unsigned __int16 *v9; // r15
  int v10; // edi
  __int64 v11; // r14
  __int64 v12; // rdi
  int v13; // ecx
  unsigned __int64 v14; // rdx
  __int64 v15; // r14
  int v16; // r13d
  const CHAR *v17; // rax
  void *v18; // rcx
  int v19; // r13d
  __int64 v20; // rcx
  __int64 v21; // r14
  unsigned int v22; // r13d
  const CHAR *v23; // rax
  unsigned int v24; // r13d
  const CHAR *v25; // r14
  int v26; // eax
  char v27; // al
  __int64 v28; // rcx
  const CHAR *v29; // r14
  int v30; // eax
  int v31; // ecx
  __int64 v32; // rcx
  _QWORD *v33; // rdx
  wint_t *v34; // rax
  wint_t *v35; // r14
  wint_t v36; // ax
  unsigned __int16 *v37; // rdx
  unsigned int v38; // r8d
  const char *v39; // r9
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v44; // [rsp+0h] [rbp-F8h] BYREF
  void *v45; // [rsp+30h] [rbp-C8h]
  unsigned __int16 *v46; // [rsp+38h] [rbp-C0h] BYREF
  unsigned __int16 *v47; // [rsp+40h] [rbp-B8h] BYREF
  unsigned __int16 *v48; // [rsp+48h] [rbp-B0h] BYREF
  const CHAR *v49; // [rsp+50h] [rbp-A8h]
  __int128 v50; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-90h]
  __int64 v52; // [rsp+70h] [rbp-88h]
  const CHAR *v53; // [rsp+78h] [rbp-80h]
  _DWORD *v54; // [rsp+80h] [rbp-78h]
  void **v55; // [rsp+88h] [rbp-70h]
  unsigned __int16 **v56; // [rsp+90h] [rbp-68h]
  _QWORD v57[3]; // [rsp+98h] [rbp-60h] BYREF
  unsigned __int64 v58; // [rsp+B0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v56 = a4;
  v55 = a3;
  v7 = a1;
  v52 = a1;
  v54 = a5;
  v45 = 0;
  v46 = 0;
  v8 = 0;
  v47 = 0;
  v50 = 0;
  v51 = 0;
  v9 = 0;
  v48 = 0;
  if ( !a1 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a5,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        74,
        "CPR(pbCommand)");
    goto LABEL_89;
  }
  if ( !a2 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a5,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        75,
        "CBR(cbCommand >= 1)");
    goto LABEL_89;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a5,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        76,
        "CPR(ppwszPin)");
    goto LABEL_89;
  }
  if ( *a3 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a5,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        77,
        "CBR(*ppwszPin == nullptr)");
    goto LABEL_89;
  }
  if ( !a4 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a5,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        78,
        "CPR(ppwszCpn)");
    goto LABEL_89;
  }
  if ( *a4 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a5,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        79,
        "CBR(*ppwszCpn == nullptr)");
    goto LABEL_89;
  }
  if ( !a5 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        80,
        "CPR(pfRingAfterLock)");
    goto LABEL_89;
  }
  *a5 = 0;
  v11 = a6[1];
  v12 = *a6;
  if ( *a6 != v11 )
  {
    do
    {
      std::wstring::~wstring(v12);
      v12 += 32;
    }
    while ( v12 != v11 );
    a6[1] = *a6;
    v7 = v52;
  }
  v13 = a2 - 1;
  if ( a2 == 1 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        90,
        "CBR(cbCommand >= 1)");
    goto LABEL_89;
  }
  v14 = *(_BYTE *)(v7 + 1) != 0;
  LODWORD(v52) = *(_BYTE *)(v7 + 1) != 0;
  if ( a2 == 2 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        1,
        v14,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        94,
        "CBR(cbCommand >= 1)");
    goto LABEL_89;
  }
  v15 = *(unsigned __int8 *)(v7 + 2);
  v16 = a2 - 3;
  if ( v13 - 2 < (unsigned int)v15 )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v13,
        v14,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        98,
        "CBR(cbCommand >= cbPin)");
    goto LABEL_89;
  }
  v10 = 0;
  v17 = (const CHAR *)(v7 + 3);
  v49 = v17;
  if ( !(_BYTE)v15 )
  {
LABEL_28:
    v19 = v16 - v15;
    if ( !v19 )
    {
      v10 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v13,
          v14,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
          105,
          "CBR(cbCommand >= 1)");
      goto LABEL_70;
    }
    v20 = v15;
    v21 = (unsigned __int8)v17[v15];
    v22 = v19 - 1;
    if ( v22 >= (unsigned int)v21 )
    {
      v23 = &v17[v20 + 1];
      v49 = v23;
      if ( (_BYTE)v21 )
      {
        v10 = MdmConverters::ConvertMultiByteToWideChar(v23, v21, &v47);
        if ( v10 < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v20,
              v14,
              v10,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
              112,
              "CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, cbCpn, &pwszCpn))");
          v8 = v47;
LABEL_70:
          v18 = v45;
          goto LABEL_71;
        }
        v8 = v47;
        v23 = v49;
      }
      v24 = v22 - v21;
      if ( v24 )
      {
        v25 = &v23[v21];
        v26 = *(unsigned __int8 *)v25;
        while ( 1 )
        {
          LODWORD(v46) = v26;
          if ( !v26 )
            break;
          if ( (_QWORD)v50 == *((_QWORD *)&v50 + 1) )
          {
            v27 = 1;
            v28 = 1;
          }
          else
          {
            v27 = 0;
            v28 = 16;
          }
          v24 -= v27 != 0 ? 1 : 16;
          if ( v24 < 0x10 )
          {
            v10 = -2147024809;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v28,
                v14,
                -2147024809,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
                120,
                "CBR(cbCommand >= 16)");
            goto LABEL_70;
          }
          v29 = &v25[v28];
          v53 = v29;
          if ( v9 )
          {
            operator delete(v9, v14);
            v48 = 0;
          }
          v30 = MdmConverters::ConvertMultiByteToWideChar(v29, 16, &v48);
          v10 = v30;
          if ( v30 < 0 )
          {
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v31,
                v14,
                v30,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
                128,
                "CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, 16, &pwszCid))");
            v9 = v48;
            goto LABEL_70;
          }
          try
          {
            v9 = v48;
            std::wstring::wstring(v57, v48);
            v32 = v57[0];
            if ( v58 <= 7 )
            {
              v47 = (unsigned __int16 *)v57;
              v33 = v57;
            }
            else
            {
              v47 = (unsigned __int16 *)v57[0];
              v33 = (_QWORD *)v57[0];
            }
            v34 = (wint_t *)v33 + v57[2];
            v49 = (const CHAR *)v34;
            v35 = (wint_t *)v57;
            if ( v58 > 7 )
              v35 = (wint_t *)v57[0];
            while ( v35 != v34 )
            {
              v36 = towupper(*v35);
              v37 = v47;
              *v47 = v36;
              ++v35;
              v47 = v37 + 1;
              v34 = (wint_t *)v49;
            }
            if ( *((_QWORD *)&v50 + 1) == v51 )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v50, *((_QWORD *)&v50 + 1), v57);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
                v32,
                *((_QWORD *)&v50 + 1),
                v57);
              *((_QWORD *)&v50 + 1) += 32LL;
            }
            std::wstring::~wstring(v57);
            v26 = (_DWORD)v46 - 1;
            v25 = v53;
          }
          catch ( ... )
          {
            LODWORD(v46) = wil::details::in1diag3::Return_CaughtException(retaddr, &v44, v38, v39);
            v10 = (int)v46;
            goto LABEL_89;
          }
        }
        *v54 = v52;
        *v55 = v45;
        v45 = 0;
        *v56 = v8;
        v8 = 0;
        if ( a6 == (__int64 *)&v50 )
          goto LABEL_75;
        v40 = *a6;
        *a6 = v50;
        *(_QWORD *)&v50 = v40;
        v41 = a6[1];
        a6[1] = *((_QWORD *)&v50 + 1);
        *((_QWORD *)&v50 + 1) = v41;
        v42 = a6[2];
        a6[2] = v51;
        v51 = v42;
      }
      else
      {
        v10 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v20,
            v14,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
            116,
            "CBR(cbCommand >= 1)");
      }
      goto LABEL_70;
    }
    v10 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v20,
        v14,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        109,
        "CBR(cbCommand >= cbCpn)");
    goto LABEL_70;
  }
  v10 = MdmConverters::ConvertMultiByteToWideChar(v17, v15, &v46);
  if ( v10 >= 0 )
  {
    v45 = v46;
    v17 = v49;
    goto LABEL_28;
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v13,
      v14,
      v10,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
      101,
      "CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, cbPin, &pwszPin))");
  v18 = v46;
LABEL_71:
  if ( v18 )
    operator delete(v18, v14);
  if ( v8 )
    operator delete(v8, v14);
LABEL_75:
  if ( v9 )
    operator delete(v9, v14);
LABEL_89:
  std::vector<std::wstring>::~vector<std::wstring>(&v50);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a528  push    rbx
0x18000a52a  push    rsi
0x18000a52b  push    rdi
0x18000a52c  push    r12
0x18000a52e  push    r13
0x18000a530  push    r14
0x18000a532  push    r15
0x18000a534  sub     rsp, 0C0h
0x18000a53b  mov     rax, cs:__security_cookie
0x18000a542  xor     rax, rsp
0x18000a545  mov     [rsp+0F8h+var_40], rax
0x18000a54d  mov     r10, r9
0x18000a550  mov     [rsp+0F8h+var_68], r9
0x18000a558  mov     r9, r8
0x18000a55b  mov     [rsp+0F8h+var_70], r8
0x18000a563  mov     r13d, edx
0x18000a566  mov     rax, rcx
0x18000a569  mov     [rsp+0F8h+var_88], rcx
0x18000a56e  mov     rcx, [rsp+0F8h+arg_20]
0x18000a576  mov     [rsp+0F8h+var_78], rcx
0x18000a57e  mov     rsi, [rsp+0F8h+arg_28]
0x18000a586  xor     r8d, r8d
0x18000a589  mov     [rsp+0F8h+var_C8], r8
0x18000a58e  mov     [rsp+0F8h+var_C0], r8
0x18000a593  xor     r12d, r12d
0x18000a596  mov     [rsp+0F8h+var_B8], r12
0x18000a59b  xorps   xmm0, xmm0
0x18000a59e  movdqu  [rsp+0F8h+var_A0], xmm0
0x18000a5a4  mov     [rsp+0F8h+var_90], r8
0x18000a5a9  xor     r15d, r15d
0x18000a5ac  mov     [rsp+0F8h+var_B0], r15
0x18000a5b1  lea     ebx, [r8+1]
0x18000a5b5  test    rax, rax
0x18000a5b8  jnz     short loc_18000A5E8
0x18000a5ba  mov     r8d, 80070057h
0x18000a5c0  mov     edi, r8d
0x18000a5c3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a5c9  jz      loc_18000ABF0
0x18000a5cf  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x18000a5d6  mov     [rsp+0F8h+var_D0], rax
0x18000a5db  mov     [rsp+0F8h+var_D8], 4Ah ; 'J'
0x18000a5e3  jmp     loc_18000ABE3
0x18000a5e8  cmp     r13d, ebx
0x18000a5eb  jb      loc_18000ABBE
0x18000a5f1  test    r9, r9
0x18000a5f4  jnz     short loc_18000A624
0x18000a5f6  mov     r8d, 80070057h
0x18000a5fc  mov     edi, r8d
0x18000a5ff  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a605  jz      loc_18000ABF0
0x18000a60b  lea     rax, aCprPpwszpin; "CPR(ppwszPin)"
0x18000a612  mov     [rsp+0F8h+var_D0], rax
0x18000a617  mov     [rsp+0F8h+var_D8], 4Ch ; 'L'
0x18000a61f  jmp     loc_18000ABE3
0x18000a624  cmp     [r9], r15
0x18000a627  jnz     loc_18000AB97
0x18000a62d  test    r10, r10
0x18000a630  jnz     short loc_18000A660
0x18000a632  mov     r8d, 80070057h
0x18000a638  mov     edi, r8d
0x18000a63b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a641  jz      loc_18000ABF0
0x18000a647  lea     rax, aCprPpwszcpn; "CPR(ppwszCpn)"
0x18000a64e  mov     [rsp+0F8h+var_D0], rax
0x18000a653  mov     [rsp+0F8h+var_D8], 4Eh ; 'N'
0x18000a65b  jmp     loc_18000ABE3
0x18000a660  cmp     [r10], r15
0x18000a663  jnz     loc_18000AB70
0x18000a669  test    rcx, rcx
0x18000a66c  jnz     short loc_18000A69C
0x18000a66e  mov     r8d, 80070057h
0x18000a674  mov     edi, r8d
0x18000a677  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a67d  jz      loc_18000ABF0
0x18000a683  lea     rax, aCprPfringafter; "CPR(pfRingAfterLock)"
0x18000a68a  mov     [rsp+0F8h+var_D0], rax
0x18000a68f  mov     [rsp+0F8h+var_D8], 50h ; 'P'
0x18000a697  jmp     loc_18000ABE3
0x18000a69c  mov     [rcx], r15d
0x18000a69f  mov     r14, [rsi+8]
0x18000a6a3  mov     rdi, [rsi]
0x18000a6a6  cmp     rdi, r14
0x18000a6a9  jz      short loc_18000A6C8
0x18000a6ab  mov     rcx, rdi
0x18000a6ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a6b3  add     rdi, 20h ; ' '
0x18000a6b7  cmp     rdi, r14
0x18000a6ba  jnz     short loc_18000A6AB
0x18000a6bc  mov     rax, [rsi]
0x18000a6bf  mov     [rsi+8], rax
0x18000a6c3  mov     rax, [rsp+0F8h+var_88]
0x18000a6c8  lea     ecx, [r13-1]
0x18000a6cc  cmp     ecx, ebx
0x18000a6ce  jb      loc_18000AB45
0x18000a6d4  xor     edx, edx
0x18000a6d6  cmp     [rax+1], dl
0x18000a6d9  setnbe  dl
0x18000a6dc  mov     dword ptr [rsp+0F8h+var_88], edx
0x18000a6e0  lea     r13d, [rcx-1]
0x18000a6e4  cmp     r13d, ebx
0x18000a6e7  jb      loc_18000AB17
0x18000a6ed  movzx   r14d, byte ptr [rax+2]
0x18000a6f2  dec     r13d
0x18000a6f5  cmp     r13d, r14d
0x18000a6f8  jb      loc_18000AAE9
0x18000a6fe  xor     edi, edi
0x18000a700  add     rax, 3
0x18000a704  mov     [rsp+0F8h+var_A8], rax
0x18000a709  test    r14b, r14b
0x18000a70c  jz      short loc_18000A768
0x18000a70e  lea     r8, [rsp+0F8h+var_C0]; unsigned __int16 **
0x18000a713  mov     edx, r14d; cbMultiByte
0x18000a716  mov     rcx, rax; lpMultiByteStr
0x18000a719  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x18000a71e  mov     edi, eax
0x18000a720  test    eax, eax
0x18000a722  jns     short loc_18000A759
0x18000a724  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a72a  jz      short loc_18000A74F
0x18000a72c  lea     rax, aChrMdmconverte_2; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x18000a733  mov     [rsp+0F8h+var_D0], rax
0x18000a738  mov     [rsp+0F8h+var_D8], 65h ; 'e'
0x18000a740  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000a747  mov     r8d, edi
0x18000a74a  call    McTemplateU0dsqs_EventWriteTransfer
0x18000a74f  mov     rcx, [rsp+0F8h+var_C0]
0x18000a754  jmp     loc_18000AABC
0x18000a759  mov     r8, [rsp+0F8h+var_C0]
0x18000a75e  mov     [rsp+0F8h+var_C8], r8
0x18000a763  mov     rax, [rsp+0F8h+var_A8]
0x18000a768  sub     r13d, r14d
0x18000a76b  cmp     r13d, ebx
0x18000a76e  jb      loc_18000AA86
0x18000a774  mov     rcx, r14
0x18000a777  movzx   r14d, byte ptr [r14+rax]
0x18000a77c  dec     r13d
0x18000a77f  cmp     r13d, r14d
0x18000a782  jb      loc_18000AA5F
0x18000a788  inc     rax
0x18000a78b  add     rax, rcx
0x18000a78e  mov     [rsp+0F8h+var_A8], rax
0x18000a793  test    r14b, r14b
0x18000a796  jz      short loc_18000A7ED
0x18000a798  lea     r8, [rsp+0F8h+var_B8]; unsigned __int16 **
0x18000a79d  mov     edx, r14d; cbMultiByte
0x18000a7a0  mov     rcx, rax; lpMultiByteStr
0x18000a7a3  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x18000a7a8  mov     edi, eax
0x18000a7aa  test    eax, eax
0x18000a7ac  jns     short loc_18000A7E3
0x18000a7ae  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a7b4  jz      short loc_18000A7D9
0x18000a7b6  lea     rax, aChrMdmconverte; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x18000a7bd  mov     [rsp+0F8h+var_D0], rax
0x18000a7c2  mov     [rsp+0F8h+var_D8], 70h ; 'p'
0x18000a7ca  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000a7d1  mov     r8d, edi
0x18000a7d4  call    McTemplateU0dsqs_EventWriteTransfer
0x18000a7d9  mov     r12, [rsp+0F8h+var_B8]
0x18000a7de  jmp     loc_18000AAB7
0x18000a7e3  mov     r12, [rsp+0F8h+var_B8]
0x18000a7e8  mov     rax, [rsp+0F8h+var_A8]
0x18000a7ed  sub     r13d, r14d
0x18000a7f0  cmp     r13d, ebx
0x18000a7f3  jb      loc_18000AA38
0x18000a7f9  add     r14, rax
0x18000a7fc  movzx   eax, byte ptr [r14]
0x18000a800  mov     dword ptr [rsp+0F8h+var_C0], eax
0x18000a804  test    eax, eax
0x18000a806  jz      loc_18000A9BF
0x18000a80c  mov     rax, qword ptr [rsp+0F8h+var_A0+8]
0x18000a811  cmp     qword ptr [rsp+0F8h+var_A0], rax
0x18000a816  jnz     short loc_18000A81F
0x18000a818  mov     al, bl
0x18000a81a  mov     rcx, rbx
0x18000a81d  jmp     short loc_18000A826
0x18000a81f  xor     al, al
0x18000a821  mov     ecx, 10h
0x18000a826  neg     al
0x18000a828  sbb     eax, eax
0x18000a82a  and     eax, 0FFFFFFF1h
0x18000a82d  add     eax, 10h
0x18000a830  sub     r13d, eax
0x18000a833  cmp     r13d, 10h
0x18000a837  jb      loc_18000A991
0x18000a83d  add     r14, rcx
0x18000a840  mov     [rsp+0F8h+var_80], r14
0x18000a845  test    r15, r15
0x18000a848  jz      short loc_18000A85B
0x18000a84a  mov     rcx, r15; void *
0x18000a84d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a852  mov     [rsp+0F8h+var_B0], 0
0x18000a85b  lea     r8, [rsp+0F8h+var_B0]; unsigned __int16 **
0x18000a860  mov     edx, 10h; cbMultiByte
0x18000a865  mov     rcx, r14; lpMultiByteStr
0x18000a868  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x18000a86d  mov     edi, eax
0x18000a86f  test    eax, eax
0x18000a871  jns     short loc_18000A8A8
0x18000a873  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a879  jz      short loc_18000A89E
0x18000a87b  lea     rax, aChrMdmconverte_1; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x18000a882  mov     [rsp+0F8h+var_D0], rax
0x18000a887  mov     [rsp+0F8h+var_D8], 80h
0x18000a88f  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000a896  mov     r8d, edi
0x18000a899  call    McTemplateU0dsqs_EventWriteTransfer
0x18000a89e  mov     r15, [rsp+0F8h+var_B0]
0x18000a8a3  jmp     loc_18000AAB7
0x18000a8a8  mov     r15, [rsp+0F8h+var_B0]
0x18000a8ad  mov     rdx, r15
0x18000a8b0  lea     rcx, [rsp+0F8h+var_60]
0x18000a8b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000a8bd  nop
0x18000a8be  mov     rcx, [rsp+0F8h+var_60]
0x18000a8c6  cmp     [rsp+0F8h+var_48], 7
0x18000a8cf  jbe     short loc_18000A8DB
0x18000a8d1  mov     [rsp+0F8h+var_B8], rcx
0x18000a8d6  mov     rdx, rcx
0x18000a8d9  jmp     short loc_18000A8F0
0x18000a8db  lea     rax, [rsp+0F8h+var_60]
0x18000a8e3  mov     [rsp+0F8h+var_B8], rax
0x18000a8e8  lea     rdx, [rsp+0F8h+var_60]
0x18000a8f0  mov     rax, [rsp+0F8h+var_50]
0x18000a8f8  lea     rax, [rdx+rax*2]
0x18000a8fc  mov     [rsp+0F8h+var_A8], rax
0x18000a901  lea     r14, [rsp+0F8h+var_60]
0x18000a909  cmova   r14, rcx
0x18000a90d  cmp     r14, rax
0x18000a910  jz      short loc_18000A93E
0x18000a912  movzx   ecx, word ptr [r14]
0x18000a916  mov     rax, cs:__imp_towupper
0x18000a91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a922  mov     rdx, [rsp+0F8h+var_B8]
0x18000a927  mov     [rdx], ax
0x18000a92a  add     r14, 2
0x18000a92e  add     rdx, 2
0x18000a932  mov     [rsp+0F8h+var_B8], rdx
0x18000a937  mov     rax, [rsp+0F8h+var_A8]
0x18000a93c  jmp     short loc_18000A90D
0x18000a93e  mov     rdx, qword ptr [rsp+0F8h+var_A0+8]
0x18000a943  lea     r8, [rsp+0F8h+var_60]
0x18000a94b  cmp     rdx, [rsp+0F8h+var_90]
0x18000a950  jz      short loc_18000A95F
0x18000a952  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(std::allocator<std::wstring> &,std::wstring * const,std::wstring const &)
0x18000a957  add     qword ptr [rsp+0F8h+var_A0+8], 20h ; ' '
0x18000a95d  jmp     short loc_18000A96A
0x18000a95f  lea     rcx, [rsp+0F8h+var_A0]
0x18000a964  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18000a969  nop
0x18000a96a  lea     rcx, [rsp+0F8h+var_60]
0x18000a972  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a977  nop
0x18000a978  mov     eax, dword ptr [rsp+0F8h+var_C0]
0x18000a97c  dec     eax
0x18000a97e  mov     r14, [rsp+0F8h+var_80]
0x18000a983  jmp     loc_18000A800
0x18000a988  mov     edi, dword ptr [rsp+0F8h+var_C0]
0x18000a98c  jmp     loc_18000ABF0
0x18000a991  mov     r8d, 80070057h
0x18000a997  mov     edi, r8d
0x18000a99a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a9a0  jz      loc_18000AAB7
0x18000a9a6  lea     rax, aCbrCbcommand16; "CBR(cbCommand >= 16)"
0x18000a9ad  mov     [rsp+0F8h+var_D0], rax
0x18000a9b2  mov     [rsp+0F8h+var_D8], 78h ; 'x'
0x18000a9ba  jmp     loc_18000AAAB
0x18000a9bf  mov     rax, [rsp+0F8h+var_78]
0x18000a9c7  mov     ecx, dword ptr [rsp+0F8h+var_88]
0x18000a9cb  mov     [rax], ecx
0x18000a9cd  mov     rcx, [rsp+0F8h+var_C8]
0x18000a9d2  mov     rax, [rsp+0F8h+var_70]
0x18000a9da  mov     [rax], rcx
0x18000a9dd  mov     [rsp+0F8h+var_C8], 0
0x18000a9e6  mov     rax, [rsp+0F8h+var_68]
0x18000a9ee  mov     [rax], r12
0x18000a9f1  xor     r12d, r12d
0x18000a9f4  lea     rax, [rsp+0F8h+var_A0]
0x18000a9f9  cmp     rsi, rax
0x18000a9fc  jz      loc_18000AAD3
0x18000aa02  mov     rcx, [rsi]
0x18000aa05  mov     rax, qword ptr [rsp+0F8h+var_A0]
0x18000aa0a  mov     [rsi], rax
0x18000aa0d  mov     qword ptr [rsp+0F8h+var_A0], rcx
0x18000aa12  mov     rcx, [rsi+8]
0x18000aa16  mov     rax, qword ptr [rsp+0F8h+var_A0+8]
0x18000aa1b  mov     [rsi+8], rax
0x18000aa1f  mov     qword ptr [rsp+0F8h+var_A0+8], rcx
0x18000aa24  mov     rcx, [rsi+10h]
0x18000aa28  mov     rax, [rsp+0F8h+var_90]
0x18000aa2d  mov     [rsi+10h], rax
0x18000aa31  mov     [rsp+0F8h+var_90], rcx
0x18000aa36  jmp     short loc_18000AAB7
0x18000aa38  mov     r8d, 80070057h
0x18000aa3e  mov     edi, r8d
0x18000aa41  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000aa47  jz      short loc_18000AAB7
0x18000aa49  lea     rax, aCbrCbcommand1; "CBR(cbCommand >= 1)"
0x18000aa50  mov     [rsp+0F8h+var_D0], rax
0x18000aa55  mov     [rsp+0F8h+var_D8], 74h ; 't'
  ... truncated ...
```
