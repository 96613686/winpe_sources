# MdmCommandParser::ParseLockCommand(uchar *,ulong,ushort * *,ushort * *,int *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18000a314`
- end: `0x18000aa0b`
- name: `?ParseLockCommand@MdmCommandParser@@SAJPEAEKPEAPEAG1PEAHAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1783`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, const char *, unsigned __int16 **, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004b60`

## callees

- `0x180001520`
- `0x180001544`
- `0x18000269c`
- `0x180002bb8`
- `0x180002de4`
- `0x180002e50`
- `0x180006548`
- `0x180009710`
- `0x18000a314`
- `0x18001a39c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18000a702`

## string_xrefs

- `0x18000a3bb`: `CPR(pbCommand)`
- `0x18000a52c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000a5b6`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000a67b`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000a897`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000a9cf`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000a835`: `CBR(cbCommand >= 1)`
- `0x18000a883`: `CBR(cbCommand >= 1)`
- `0x18000a918`: `CBR(cbCommand >= 1)`
- `0x18000a946`: `CBR(cbCommand >= 1)`
- `0x18000a9bb`: `CBR(cbCommand >= 1)`
- `0x18000a8ea`: `CBR(cbCommand >= cbPin)`
- `0x18000a518`: `CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, cbPin, &pwszPin))`
- `0x18000a85c`: `CBR(cbCommand >= cbCpn)`
- `0x18000a5a2`: `CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, cbCpn, &pwszCpn))`
- `0x18000a792`: `CBR(cbCommand >= 16)`
- `0x18000a667`: `CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, 16, &pwszCid))`

## pseudocode

```c
__int64 __fastcall MdmCommandParser::ParseLockCommand(
        __int64 a1,
        unsigned __int64 a2,
        const char *a3,
        unsigned __int16 **a4,
        _DWORD *a5,
        __int64 *a6)
{
  const char *v7; // r9
  int v8; // r13d
  __int64 v9; // rax
  __int64 v10; // r8
  unsigned __int16 *v11; // r12
  unsigned __int16 *v12; // r15
  int v13; // edi
  __int64 v14; // r14
  __int64 v15; // rdi
  __int64 v16; // r14
  int v17; // r13d
  const CHAR *v18; // rax
  void *v19; // rcx
  int v20; // r13d
  __int64 v21; // r14
  unsigned int v22; // r13d
  const CHAR *v23; // rax
  unsigned int v24; // r13d
  const CHAR *v25; // r14
  int v26; // eax
  char v27; // al
  const CHAR *v28; // r14
  int v29; // eax
  int v30; // ecx
  __int64 v31; // rcx
  _QWORD *v32; // rdx
  wint_t *v33; // rax
  wint_t *v34; // r14
  wint_t v35; // ax
  unsigned __int16 *v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v41; // [rsp+0h] [rbp-F8h] BYREF
  int v42; // [rsp+20h] [rbp-D8h]
  const char *v43; // [rsp+28h] [rbp-D0h]
  void *v44; // [rsp+30h] [rbp-C8h]
  unsigned __int16 *v45; // [rsp+38h] [rbp-C0h] BYREF
  unsigned __int16 *v46; // [rsp+40h] [rbp-B8h] BYREF
  unsigned __int16 *v47; // [rsp+48h] [rbp-B0h] BYREF
  const CHAR *v48; // [rsp+50h] [rbp-A8h]
  __int128 v49; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+68h] [rbp-90h]
  __int64 v51; // [rsp+70h] [rbp-88h]
  const CHAR *v52; // [rsp+78h] [rbp-80h]
  _DWORD *v53; // [rsp+80h] [rbp-78h]
  void **v54; // [rsp+88h] [rbp-70h]
  unsigned __int16 **v55; // [rsp+90h] [rbp-68h]
  _QWORD v56[3]; // [rsp+98h] [rbp-60h] BYREF
  unsigned __int64 v57; // [rsp+B0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v55 = a4;
  v7 = a3;
  v54 = (void **)a3;
  v8 = a2;
  v9 = a1;
  v51 = a1;
  LODWORD(a1) = (_DWORD)a5;
  v53 = a5;
  v10 = 0;
  v44 = 0;
  v45 = 0;
  v11 = 0;
  v46 = 0;
  v49 = 0;
  v50 = 0;
  v12 = 0;
  v47 = 0;
  if ( !v9 )
  {
    v10 = 2147942487LL;
    v13 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      v43 = "CPR(pbCommand)";
      v42 = 74;
LABEL_90:
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
        v42,
        (__int64)v43);
      goto LABEL_91;
    }
    goto LABEL_91;
  }
  if ( !(_DWORD)a2 )
  {
    v10 = 2147942487LL;
    v13 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      v43 = "CBR(cbCommand >= 1)";
      v42 = 75;
      goto LABEL_90;
    }
    goto LABEL_91;
  }
  if ( v7 )
  {
    if ( *(_QWORD *)v7 )
    {
      v10 = 2147942487LL;
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v43 = "CBR(*ppwszPin == nullptr)";
        v42 = 77;
        goto LABEL_90;
      }
      goto LABEL_91;
    }
    if ( !a4 )
    {
      v10 = 2147942487LL;
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v43 = "CPR(ppwszCpn)";
        v42 = 78;
        goto LABEL_90;
      }
      goto LABEL_91;
    }
    if ( *a4 )
    {
      v10 = 2147942487LL;
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v43 = "CBR(*ppwszCpn == nullptr)";
        v42 = 79;
        goto LABEL_90;
      }
      goto LABEL_91;
    }
    if ( !a5 )
    {
      v10 = 2147942487LL;
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v43 = "CPR(pfRingAfterLock)";
        v42 = 80;
        goto LABEL_90;
      }
      goto LABEL_91;
    }
    *a5 = 0;
    v14 = a6[1];
    v15 = *a6;
    if ( *a6 != v14 )
    {
      do
      {
        std::wstring::~wstring(v15);
        v15 += 32;
      }
      while ( v15 != v14 );
      a6[1] = *a6;
      v9 = v51;
    }
    LODWORD(a1) = v8 - 1;
    if ( v8 == 1 )
    {
      v10 = 2147942487LL;
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v43 = "CBR(cbCommand >= 1)";
        v42 = 90;
        goto LABEL_90;
      }
      goto LABEL_91;
    }
    a2 = *(_BYTE *)(v9 + 1) != 0;
    LODWORD(v51) = *(_BYTE *)(v9 + 1) != 0;
    if ( v8 == 2 )
    {
      v10 = 2147942487LL;
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v43 = "CBR(cbCommand >= 1)";
        v42 = 94;
        goto LABEL_90;
      }
      goto LABEL_91;
    }
    v16 = *(unsigned __int8 *)(v9 + 2);
    v17 = v8 - 3;
    if ( (int)a1 - 2 < (unsigned int)v16 )
    {
      v10 = 2147942487LL;
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v43 = "CBR(cbCommand >= cbPin)";
        v42 = 98;
        goto LABEL_90;
      }
      goto LABEL_91;
    }
    v13 = 0;
    v18 = (const CHAR *)(v9 + 3);
    v48 = v18;
    if ( (_BYTE)v16 )
    {
      v13 = MdmConverters::ConvertMultiByteToWideChar(v18, v16, &v45);
      if ( v13 < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            a1,
            a2,
            v13,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
            101,
            (__int64)"CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, cbPin, &pwszPin))");
        v19 = v45;
LABEL_72:
        if ( v19 )
          operator delete(v19, a2);
        if ( v11 )
          operator delete(v11, a2);
LABEL_76:
        if ( v12 )
          operator delete(v12, a2);
        goto LABEL_91;
      }
      v10 = (__int64)v45;
      v44 = v45;
      v18 = v48;
    }
    v20 = v17 - v16;
    if ( v20 )
    {
      a1 = v16;
      v21 = (unsigned __int8)v18[v16];
      v22 = v20 - 1;
      if ( v22 < (unsigned int)v21 )
      {
        v10 = 2147942487LL;
        v13 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v43 = "CBR(cbCommand >= cbCpn)";
          v42 = 109;
          goto LABEL_70;
        }
      }
      else
      {
        v23 = &v18[a1 + 1];
        v48 = v23;
        if ( (_BYTE)v21 )
        {
          v13 = MdmConverters::ConvertMultiByteToWideChar(v23, v21, &v46);
          if ( v13 < 0 )
          {
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                a1,
                a2,
                v13,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
                112,
                (__int64)"CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, cbCpn, &pwszCpn))");
            v11 = v46;
            goto LABEL_71;
          }
          v11 = v46;
          v23 = v48;
        }
        v24 = v22 - v21;
        if ( v24 )
        {
          v25 = &v23[v21];
          v26 = *(unsigned __int8 *)v25;
          while ( 1 )
          {
            LODWORD(v45) = v26;
            if ( !v26 )
              break;
            if ( (_QWORD)v49 == *((_QWORD *)&v49 + 1) )
            {
              v27 = 1;
              a1 = 1;
            }
            else
            {
              v27 = 0;
              a1 = 16;
            }
            v24 -= v27 != 0 ? 1 : 16;
            if ( v24 < 0x10 )
            {
              v10 = 2147942487LL;
              v13 = -2147024809;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                goto LABEL_71;
              v43 = "CBR(cbCommand >= 16)";
              v42 = 120;
              goto LABEL_70;
            }
            v28 = &v25[a1];
            v52 = v28;
            if ( v12 )
            {
              operator delete(v12, a2);
              v47 = 0;
            }
            v29 = MdmConverters::ConvertMultiByteToWideChar(v28, 0x10u, &v47);
            v13 = v29;
            if ( v29 < 0 )
            {
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v30,
                  a2,
                  v29,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
                  128,
                  (__int64)"CHR(MdmConverters::ConvertMultiByteToWideChar(pbCommand, 16, &pwszCid))");
              v12 = v47;
              goto LABEL_71;
            }
            try
            {
              v12 = v47;
              std::wstring::wstring(v56, v47);
              v31 = v56[0];
              if ( v57 <= 7 )
              {
                v46 = (unsigned __int16 *)v56;
                v32 = v56;
              }
              else
              {
                v46 = (unsigned __int16 *)v56[0];
                v32 = (_QWORD *)v56[0];
              }
              v33 = (wint_t *)v32 + v56[2];
              v48 = (const CHAR *)v33;
              v34 = (wint_t *)v56;
              if ( v57 > 7 )
                v34 = (wint_t *)v56[0];
              while ( v34 != v33 )
              {
                v35 = towupper(*v34);
                v36 = v46;
                *v46 = v35;
                ++v34;
                v46 = v36 + 1;
                v33 = (wint_t *)v48;
              }
              if ( *((_QWORD *)&v49 + 1) == v50 )
              {
                std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v49, *((_QWORD *)&v49 + 1), v56);
              }
              else
              {
                std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(
                  v31,
                  *((_QWORD *)&v49 + 1),
                  v56);
                *((_QWORD *)&v49 + 1) += 32LL;
              }
              std::wstring::~wstring(v56);
              v26 = (_DWORD)v45 - 1;
              v25 = v52;
            }
            catch ( ... )
            {
              LODWORD(v45) = wil::details::in1diag3::Return_CaughtException(retaddr, &v41, v10, v7);
              v13 = (int)v45;
              goto LABEL_91;
            }
          }
          *v53 = v51;
          *v54 = v44;
          v44 = 0;
          *v55 = v11;
          v11 = 0;
          if ( a6 == (__int64 *)&v49 )
            goto LABEL_76;
          v37 = *a6;
          *a6 = v49;
          *(_QWORD *)&v49 = v37;
          v38 = a6[1];
          a6[1] = *((_QWORD *)&v49 + 1);
          *((_QWORD *)&v49 + 1) = v38;
          v39 = a6[2];
          a6[2] = v50;
          v50 = v39;
          goto LABEL_71;
        }
        v10 = 2147942487LL;
        v13 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        {
          v43 = "CBR(cbCommand >= 1)";
          v42 = 116;
LABEL_70:
          McTemplateU0dsqs_EventWriteTransfer(
            a1,
            a2,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
            v42,
            (__int64)v43);
        }
      }
    }
    else
    {
      v10 = 2147942487LL;
      v13 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        v43 = "CBR(cbCommand >= 1)";
        v42 = 105;
        goto LABEL_70;
      }
    }
LABEL_71:
    v19 = v44;
    goto LABEL_72;
  }
  v10 = 2147942487LL;
  v13 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    v43 = "CPR(ppwszPin)";
    v42 = 76;
    goto LABEL_90;
  }
LABEL_91:
  std::vector<std::wstring>::~vector<std::wstring>(&v49, a2, v10, v7);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000a314  push    rbx
0x18000a316  push    rsi
0x18000a317  push    rdi
0x18000a318  push    r12
0x18000a31a  push    r13
0x18000a31c  push    r14
0x18000a31e  push    r15
0x18000a320  sub     rsp, 0C0h
0x18000a327  mov     rax, cs:__security_cookie
0x18000a32e  xor     rax, rsp
0x18000a331  mov     [rsp+0F8h+var_40], rax
0x18000a339  mov     r10, r9
0x18000a33c  mov     [rsp+0F8h+var_68], r9
0x18000a344  mov     r9, r8
0x18000a347  mov     [rsp+0F8h+var_70], r8
0x18000a34f  mov     r13d, edx
0x18000a352  mov     rax, rcx
0x18000a355  mov     [rsp+0F8h+var_88], rcx
0x18000a35a  mov     rcx, [rsp+0F8h+arg_20]
0x18000a362  mov     [rsp+0F8h+var_78], rcx
0x18000a36a  mov     rsi, [rsp+0F8h+arg_28]
0x18000a372  xor     r8d, r8d
0x18000a375  mov     [rsp+0F8h+var_C8], r8
0x18000a37a  mov     [rsp+0F8h+var_C0], r8
0x18000a37f  xor     r12d, r12d
0x18000a382  mov     [rsp+0F8h+var_B8], r12
0x18000a387  xorps   xmm0, xmm0
0x18000a38a  movdqu  [rsp+0F8h+var_A0], xmm0
0x18000a390  mov     [rsp+0F8h+var_90], r8
0x18000a395  xor     r15d, r15d
0x18000a398  mov     [rsp+0F8h+var_B0], r15
0x18000a39d  lea     ebx, [r8+1]
0x18000a3a1  test    rax, rax
0x18000a3a4  jnz     short loc_18000A3D4
0x18000a3a6  mov     r8d, 80070057h
0x18000a3ac  mov     edi, r8d
0x18000a3af  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a3b5  jz      loc_18000A9DC
0x18000a3bb  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x18000a3c2  mov     [rsp+0F8h+var_D0], rax
0x18000a3c7  mov     [rsp+0F8h+var_D8], 4Ah ; 'J'
0x18000a3cf  jmp     loc_18000A9CF
0x18000a3d4  cmp     r13d, ebx
0x18000a3d7  jb      loc_18000A9AA
0x18000a3dd  test    r9, r9
0x18000a3e0  jnz     short loc_18000A410
0x18000a3e2  mov     r8d, 80070057h
0x18000a3e8  mov     edi, r8d
0x18000a3eb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a3f1  jz      loc_18000A9DC
0x18000a3f7  lea     rax, aCprPpwszpin; "CPR(ppwszPin)"
0x18000a3fe  mov     [rsp+0F8h+var_D0], rax
0x18000a403  mov     [rsp+0F8h+var_D8], 4Ch ; 'L'
0x18000a40b  jmp     loc_18000A9CF
0x18000a410  cmp     [r9], r15
0x18000a413  jnz     loc_18000A983
0x18000a419  test    r10, r10
0x18000a41c  jnz     short loc_18000A44C
0x18000a41e  mov     r8d, 80070057h
0x18000a424  mov     edi, r8d
0x18000a427  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a42d  jz      loc_18000A9DC
0x18000a433  lea     rax, aCprPpwszcpn; "CPR(ppwszCpn)"
0x18000a43a  mov     [rsp+0F8h+var_D0], rax
0x18000a43f  mov     [rsp+0F8h+var_D8], 4Eh ; 'N'
0x18000a447  jmp     loc_18000A9CF
0x18000a44c  cmp     [r10], r15
0x18000a44f  jnz     loc_18000A95C
0x18000a455  test    rcx, rcx
0x18000a458  jnz     short loc_18000A488
0x18000a45a  mov     r8d, 80070057h
0x18000a460  mov     edi, r8d
0x18000a463  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a469  jz      loc_18000A9DC
0x18000a46f  lea     rax, aCprPfringafter; "CPR(pfRingAfterLock)"
0x18000a476  mov     [rsp+0F8h+var_D0], rax
0x18000a47b  mov     [rsp+0F8h+var_D8], 50h ; 'P'
0x18000a483  jmp     loc_18000A9CF
0x18000a488  mov     [rcx], r15d
0x18000a48b  mov     r14, [rsi+8]
0x18000a48f  mov     rdi, [rsi]
0x18000a492  cmp     rdi, r14
0x18000a495  jz      short loc_18000A4B4
0x18000a497  mov     rcx, rdi
0x18000a49a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a49f  add     rdi, 20h ; ' '
0x18000a4a3  cmp     rdi, r14
0x18000a4a6  jnz     short loc_18000A497
0x18000a4a8  mov     rax, [rsi]
0x18000a4ab  mov     [rsi+8], rax
0x18000a4af  mov     rax, [rsp+0F8h+var_88]
0x18000a4b4  lea     ecx, [r13-1]
0x18000a4b8  cmp     ecx, ebx
0x18000a4ba  jb      loc_18000A931
0x18000a4c0  xor     edx, edx
0x18000a4c2  cmp     [rax+1], dl
0x18000a4c5  setnbe  dl
0x18000a4c8  mov     dword ptr [rsp+0F8h+var_88], edx
0x18000a4cc  lea     r13d, [rcx-1]
0x18000a4d0  cmp     r13d, ebx
0x18000a4d3  jb      loc_18000A903
0x18000a4d9  movzx   r14d, byte ptr [rax+2]
0x18000a4de  dec     r13d
0x18000a4e1  cmp     r13d, r14d
0x18000a4e4  jb      loc_18000A8D5
0x18000a4ea  xor     edi, edi
0x18000a4ec  add     rax, 3
0x18000a4f0  mov     [rsp+0F8h+var_A8], rax
0x18000a4f5  test    r14b, r14b
0x18000a4f8  jz      short loc_18000A554
0x18000a4fa  lea     r8, [rsp+0F8h+var_C0]; unsigned __int16 **
0x18000a4ff  mov     edx, r14d; cbMultiByte
0x18000a502  mov     rcx, rax; lpMultiByteStr
0x18000a505  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x18000a50a  mov     edi, eax
0x18000a50c  test    eax, eax
0x18000a50e  jns     short loc_18000A545
0x18000a510  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a516  jz      short loc_18000A53B
0x18000a518  lea     rax, aChrMdmconverte_2; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x18000a51f  mov     [rsp+0F8h+var_D0], rax
0x18000a524  mov     [rsp+0F8h+var_D8], 65h ; 'e'
0x18000a52c  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000a533  mov     r8d, edi
0x18000a536  call    McTemplateU0dsqs_EventWriteTransfer
0x18000a53b  mov     rcx, [rsp+0F8h+var_C0]
0x18000a540  jmp     loc_18000A8A8
0x18000a545  mov     r8, [rsp+0F8h+var_C0]
0x18000a54a  mov     [rsp+0F8h+var_C8], r8
0x18000a54f  mov     rax, [rsp+0F8h+var_A8]
0x18000a554  sub     r13d, r14d
0x18000a557  cmp     r13d, ebx
0x18000a55a  jb      loc_18000A872
0x18000a560  mov     rcx, r14
0x18000a563  movzx   r14d, byte ptr [r14+rax]
0x18000a568  dec     r13d
0x18000a56b  cmp     r13d, r14d
0x18000a56e  jb      loc_18000A84B
0x18000a574  inc     rax
0x18000a577  add     rax, rcx
0x18000a57a  mov     [rsp+0F8h+var_A8], rax
0x18000a57f  test    r14b, r14b
0x18000a582  jz      short loc_18000A5D9
0x18000a584  lea     r8, [rsp+0F8h+var_B8]; unsigned __int16 **
0x18000a589  mov     edx, r14d; cbMultiByte
0x18000a58c  mov     rcx, rax; lpMultiByteStr
0x18000a58f  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x18000a594  mov     edi, eax
0x18000a596  test    eax, eax
0x18000a598  jns     short loc_18000A5CF
0x18000a59a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a5a0  jz      short loc_18000A5C5
0x18000a5a2  lea     rax, aChrMdmconverte; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x18000a5a9  mov     [rsp+0F8h+var_D0], rax
0x18000a5ae  mov     [rsp+0F8h+var_D8], 70h ; 'p'
0x18000a5b6  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000a5bd  mov     r8d, edi
0x18000a5c0  call    McTemplateU0dsqs_EventWriteTransfer
0x18000a5c5  mov     r12, [rsp+0F8h+var_B8]
0x18000a5ca  jmp     loc_18000A8A3
0x18000a5cf  mov     r12, [rsp+0F8h+var_B8]
0x18000a5d4  mov     rax, [rsp+0F8h+var_A8]
0x18000a5d9  sub     r13d, r14d
0x18000a5dc  cmp     r13d, ebx
0x18000a5df  jb      loc_18000A824
0x18000a5e5  add     r14, rax
0x18000a5e8  movzx   eax, byte ptr [r14]
0x18000a5ec  mov     dword ptr [rsp+0F8h+var_C0], eax
0x18000a5f0  test    eax, eax
0x18000a5f2  jz      loc_18000A7AB
0x18000a5f8  mov     rax, qword ptr [rsp+0F8h+var_A0+8]
0x18000a5fd  cmp     qword ptr [rsp+0F8h+var_A0], rax
0x18000a602  jnz     short loc_18000A60B
0x18000a604  mov     al, bl
0x18000a606  mov     rcx, rbx
0x18000a609  jmp     short loc_18000A612
0x18000a60b  xor     al, al
0x18000a60d  mov     ecx, 10h
0x18000a612  neg     al
0x18000a614  sbb     eax, eax
0x18000a616  and     eax, 0FFFFFFF1h
0x18000a619  add     eax, 10h
0x18000a61c  sub     r13d, eax
0x18000a61f  cmp     r13d, 10h
0x18000a623  jb      loc_18000A77D
0x18000a629  add     r14, rcx
0x18000a62c  mov     [rsp+0F8h+var_80], r14
0x18000a631  test    r15, r15
0x18000a634  jz      short loc_18000A647
0x18000a636  mov     rcx, r15; void *
0x18000a639  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a63e  mov     [rsp+0F8h+var_B0], 0
0x18000a647  lea     r8, [rsp+0F8h+var_B0]; unsigned __int16 **
0x18000a64c  mov     edx, 10h; cbMultiByte
0x18000a651  mov     rcx, r14; lpMultiByteStr
0x18000a654  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x18000a659  mov     edi, eax
0x18000a65b  test    eax, eax
0x18000a65d  jns     short loc_18000A694
0x18000a65f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a665  jz      short loc_18000A68A
0x18000a667  lea     rax, aChrMdmconverte_1; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x18000a66e  mov     [rsp+0F8h+var_D0], rax
0x18000a673  mov     [rsp+0F8h+var_D8], 80h
0x18000a67b  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000a682  mov     r8d, edi
0x18000a685  call    McTemplateU0dsqs_EventWriteTransfer
0x18000a68a  mov     r15, [rsp+0F8h+var_B0]
0x18000a68f  jmp     loc_18000A8A3
0x18000a694  mov     r15, [rsp+0F8h+var_B0]
0x18000a699  mov     rdx, r15
0x18000a69c  lea     rcx, [rsp+0F8h+var_60]
0x18000a6a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000a6a9  nop
0x18000a6aa  mov     rcx, [rsp+0F8h+var_60]
0x18000a6b2  cmp     [rsp+0F8h+var_48], 7
0x18000a6bb  jbe     short loc_18000A6C7
0x18000a6bd  mov     [rsp+0F8h+var_B8], rcx
0x18000a6c2  mov     rdx, rcx
0x18000a6c5  jmp     short loc_18000A6DC
0x18000a6c7  lea     rax, [rsp+0F8h+var_60]
0x18000a6cf  mov     [rsp+0F8h+var_B8], rax
0x18000a6d4  lea     rdx, [rsp+0F8h+var_60]
0x18000a6dc  mov     rax, [rsp+0F8h+var_50]
0x18000a6e4  lea     rax, [rdx+rax*2]
0x18000a6e8  mov     [rsp+0F8h+var_A8], rax
0x18000a6ed  lea     r14, [rsp+0F8h+var_60]
0x18000a6f5  cmova   r14, rcx
0x18000a6f9  cmp     r14, rax
0x18000a6fc  jz      short loc_18000A72A
0x18000a6fe  movzx   ecx, word ptr [r14]
0x18000a702  mov     rax, cs:__imp_towupper
0x18000a709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a70e  mov     rdx, [rsp+0F8h+var_B8]
0x18000a713  mov     [rdx], ax
0x18000a716  add     r14, 2
0x18000a71a  add     rdx, 2
0x18000a71e  mov     [rsp+0F8h+var_B8], rdx
0x18000a723  mov     rax, [rsp+0F8h+var_A8]
0x18000a728  jmp     short loc_18000A6F9
0x18000a72a  mov     rdx, qword ptr [rsp+0F8h+var_A0+8]
0x18000a72f  lea     r8, [rsp+0F8h+var_60]
0x18000a737  cmp     rdx, [rsp+0F8h+var_90]
0x18000a73c  jz      short loc_18000A74B
0x18000a73e  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring const &>(std::allocator<std::wstring> &,std::wstring * const,std::wstring const &)
0x18000a743  add     qword ptr [rsp+0F8h+var_A0+8], 20h ; ' '
0x18000a749  jmp     short loc_18000A756
0x18000a74b  lea     rcx, [rsp+0F8h+var_A0]
0x18000a750  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18000a755  nop
0x18000a756  lea     rcx, [rsp+0F8h+var_60]
0x18000a75e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a763  nop
0x18000a764  mov     eax, dword ptr [rsp+0F8h+var_C0]
0x18000a768  dec     eax
0x18000a76a  mov     r14, [rsp+0F8h+var_80]
0x18000a76f  jmp     loc_18000A5EC
0x18000a774  mov     edi, dword ptr [rsp+0F8h+var_C0]
0x18000a778  jmp     loc_18000A9DC
0x18000a77d  mov     r8d, 80070057h
0x18000a783  mov     edi, r8d
0x18000a786  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a78c  jz      loc_18000A8A3
0x18000a792  lea     rax, aCbrCbcommand16; "CBR(cbCommand >= 16)"
0x18000a799  mov     [rsp+0F8h+var_D0], rax
0x18000a79e  mov     [rsp+0F8h+var_D8], 78h ; 'x'
0x18000a7a6  jmp     loc_18000A897
0x18000a7ab  mov     rax, [rsp+0F8h+var_78]
0x18000a7b3  mov     ecx, dword ptr [rsp+0F8h+var_88]
0x18000a7b7  mov     [rax], ecx
0x18000a7b9  mov     rcx, [rsp+0F8h+var_C8]
0x18000a7be  mov     rax, [rsp+0F8h+var_70]
0x18000a7c6  mov     [rax], rcx
0x18000a7c9  mov     [rsp+0F8h+var_C8], 0
0x18000a7d2  mov     rax, [rsp+0F8h+var_68]
0x18000a7da  mov     [rax], r12
0x18000a7dd  xor     r12d, r12d
0x18000a7e0  lea     rax, [rsp+0F8h+var_A0]
0x18000a7e5  cmp     rsi, rax
0x18000a7e8  jz      loc_18000A8BF
0x18000a7ee  mov     rcx, [rsi]
0x18000a7f1  mov     rax, qword ptr [rsp+0F8h+var_A0]
0x18000a7f6  mov     [rsi], rax
0x18000a7f9  mov     qword ptr [rsp+0F8h+var_A0], rcx
0x18000a7fe  mov     rcx, [rsi+8]
0x18000a802  mov     rax, qword ptr [rsp+0F8h+var_A0+8]
0x18000a807  mov     [rsi+8], rax
0x18000a80b  mov     qword ptr [rsp+0F8h+var_A0+8], rcx
0x18000a810  mov     rcx, [rsi+10h]
0x18000a814  mov     rax, [rsp+0F8h+var_90]
0x18000a819  mov     [rsi+10h], rax
0x18000a81d  mov     [rsp+0F8h+var_90], rcx
0x18000a822  jmp     short loc_18000A8A3
0x18000a824  mov     r8d, 80070057h
0x18000a82a  mov     edi, r8d
0x18000a82d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, bl
0x18000a833  jz      short loc_18000A8A3
0x18000a835  lea     rax, aCbrCbcommand1; "CBR(cbCommand >= 1)"
0x18000a83c  mov     [rsp+0F8h+var_D0], rax
0x18000a841  mov     [rsp+0F8h+var_D8], 74h ; 't'
  ... truncated ...
```
