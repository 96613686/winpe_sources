# ESEDataSource::_InitJetInstance(ushort const *)

- ea: `0x180011b6c`
- end: `0x180011f67`
- name: `?_InitJetInstance@ESEDataSource@@AEAAJPEBG@Z`
- size: `1019`
- prototype: `__int64 __fastcall(ESEDataSource *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ee40`
- `0x180011f70`

## callees

- `0x18000c6dc`
- `0x1800104b8`
- `0x180010638`
- `0x180011b6c`
- `0x180021064`
- `0x180021098`
- `0x18002115c`

## import_xrefs

- `ESENT!JetCreateInstanceW` at `0x180011bf0`
- `ESENT!JetCreateInstanceW` at `0x180011bf0`
- `ESENT!JetSetSystemParameterW` at `0x180011c28`
- `ESENT!JetSetSystemParameterW` at `0x180011c5a`
- `ESENT!JetSetSystemParameterW` at `0x180011c84`
- `ESENT!JetSetSystemParameterW` at `0x180011cb1`
- `ESENT!JetSetSystemParameterW` at `0x180011ce2`
- `ESENT!JetSetSystemParameterW` at `0x180011e61`
- `ESENT!JetSetSystemParameterW` at `0x180011e91`
- `ESENT!JetSetSystemParameterW` at `0x180011ec1`
- `ESENT!JetSetSystemParameterW` at `0x180011c28`
- `ESENT!JetSetSystemParameterW` at `0x180011c5a`
- `ESENT!JetSetSystemParameterW` at `0x180011c84`
- `ESENT!JetSetSystemParameterW` at `0x180011cb1`
- `ESENT!JetSetSystemParameterW` at `0x180011ce2`
- `ESENT!JetSetSystemParameterW` at `0x180011e61`
- `ESENT!JetSetSystemParameterW` at `0x180011e91`
- `ESENT!JetSetSystemParameterW` at `0x180011ec1`
- `ESENT!JetSetSystemParameterA` at `0x180011d12`
- `ESENT!JetSetSystemParameterA` at `0x180011d41`
- `ESENT!JetSetSystemParameterA` at `0x180011d71`
- `ESENT!JetSetSystemParameterA` at `0x180011da1`
- `ESENT!JetSetSystemParameterA` at `0x180011dd1`
- `ESENT!JetSetSystemParameterA` at `0x180011e01`
- `ESENT!JetSetSystemParameterA` at `0x180011e31`
- `ESENT!JetSetSystemParameterA` at `0x180011d12`
- `ESENT!JetSetSystemParameterA` at `0x180011d41`
- `ESENT!JetSetSystemParameterA` at `0x180011d71`
- `ESENT!JetSetSystemParameterA` at `0x180011da1`
- `ESENT!JetSetSystemParameterA` at `0x180011dd1`
- `ESENT!JetSetSystemParameterA` at `0x180011e01`
- `ESENT!JetSetSystemParameterA` at `0x180011e31`
- `ESENT!JetInit2` at `0x180011ee2`
- `ESENT!JetInit2` at `0x180011ee2`
- `unistore!GetUnistoreJetInstance` at `0x180011b99`
- `unistore!GetUnistoreJetInstance` at `0x180011b99`
- `UserDataPlatformHelperUtil!SetCommsServiceJetGlobalSystemParameters` at `0x180011bc1`
- `UserDataPlatformHelperUtil!SetCommsServiceJetGlobalSystemParameters` at `0x180011bc1`

## pseudocode

```c
__int64 __fastcall ESEDataSource::_InitJetInstance(ESEDataSource *this, const unsigned __int16 *a2)
{
  JET_INSTANCE *v2; // rbx
  int UnistoreJetInstance; // ebx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // esi
  JET_ERR InstanceW; // eax
  unsigned int HresultFromJetError; // eax
  JET_ERR v15; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  JET_ERR v18; // eax
  JET_ERR v19; // eax
  JET_ERR v20; // eax
  JET_ERR v21; // eax
  JET_ERR v22; // eax
  JET_ERR v23; // eax
  JET_ERR v24; // eax
  JET_ERR v25; // eax
  JET_ERR v26; // eax
  JET_ERR v27; // eax
  JET_ERR v28; // eax
  JET_ERR v29; // eax
  JET_ERR v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  unsigned int v33; // ebx
  __int64 v34; // r9

  v2 = (JET_INSTANCE *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) == -1 )
  {
    if ( *((_DWORD *)this + 25) )
    {
      UnistoreJetInstance = GetUnistoreJetInstance((char *)this + 8);
      if ( UnistoreJetInstance < 0 )
      {
        v6 = 1;
        v7 = 660;
LABEL_5:
        v8 = (unsigned int)UnistoreJetInstance;
LABEL_6:
        Log_HREvent_2(v8, v6, v5, v7);
        return (unsigned int)UnistoreJetInstance;
      }
      return 0;
    }
    v10 = SetCommsServiceJetGlobalSystemParameters();
    v12 = v10;
    if ( v10 < 0 )
    {
      Log_HREvent_2((unsigned int)v10, 1, v11, 664);
      return v12;
    }
    InstanceW = JetCreateInstanceW(v2, L"PimIdxMaint");
    if ( InstanceW < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(InstanceW);
      v7 = 669;
LABEL_11:
      v6 = 0;
      UnistoreJetInstance = HresultFromJetError;
      v8 = HresultFromJetError;
      goto LABEL_6;
    }
    v15 = JetSetSystemParameterW(v2, 0xFFFFFFFFFFFFFFFFuLL, 0x82u, 1u, 0);
    if ( v15 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v15);
      v7 = 671;
      goto LABEL_11;
    }
    v16 = JetSetSystemParameterW(v2, 0xFFFFFFFFFFFFFFFFuLL, 3u, 0, L"PIM");
    if ( v16 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v16);
      v7 = 672;
      goto LABEL_11;
    }
    v17 = JetSetSystemParameterW(v2, 0xFFFFFFFFFFFFFFFFuLL, 0, 0, a2);
    if ( v17 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v17);
      v7 = 673;
      goto LABEL_11;
    }
    v18 = JetSetSystemParameterW(v2, 0xFFFFFFFFFFFFFFFFuLL, 1u, 0, a2);
    if ( v18 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v18);
      v7 = 674;
      goto LABEL_11;
    }
    v19 = JetSetSystemParameterW(v2, 0xFFFFFFFFFFFFFFFFuLL, 2u, 0, a2);
    if ( v19 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v19);
      v7 = 675;
      goto LABEL_11;
    }
    v20 = JetSetSystemParameterA(v2, 0, 0x18u, 0x500000u, 0);
    if ( v20 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v20);
      v7 = 678;
      goto LABEL_11;
    }
    v21 = JetSetSystemParameterA(v2, 0, 0x98u, 2u, 0);
    if ( v21 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v21);
      v7 = 681;
      goto LABEL_11;
    }
    v22 = JetSetSystemParameterA(v2, 0xFFFFFFFFFFFFFFFFuLL, 0x45u, 1u, 0);
    if ( v22 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v22);
      v7 = 684;
      goto LABEL_11;
    }
    v23 = JetSetSystemParameterA(v2, 0, 0xCu, 0x200u, 0);
    if ( v23 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v23);
      v7 = 689;
      goto LABEL_11;
    }
    v24 = JetSetSystemParameterA(v2, 0, 0xBu, 0xC00u, 0);
    if ( v24 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v24);
      v7 = 692;
      goto LABEL_11;
    }
    v25 = JetSetSystemParameterA(v2, 0, 0x12u, 0x80u, 0);
    if ( v25 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v25);
      v7 = 695;
      goto LABEL_11;
    }
    v26 = JetSetSystemParameterA(v2, 0, 0xB1u, 0x14u, 0);
    if ( v26 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v26);
      v7 = 698;
      goto LABEL_11;
    }
    v27 = JetSetSystemParameterW(v2, 0xFFFFFFFFFFFFFFFFuLL, 0x30u, 1u, 0);
    if ( v27 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v27);
      v7 = 700;
      goto LABEL_11;
    }
    v28 = JetSetSystemParameterW(v2, 0xFFFFFFFFFFFFFFFFuLL, 0x11u, 1u, 0);
    if ( v28 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v28);
      v7 = 701;
      goto LABEL_11;
    }
    v29 = JetSetSystemParameterW(v2, 0xFFFFFFFFFFFFFFFFuLL, 0x2Du, 1u, 0);
    if ( v29 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v29);
      v7 = 702;
      goto LABEL_11;
    }
    v30 = JetInit2(v2, 0);
    v33 = v30;
    if ( v30 )
    {
      if ( v30 == -1811 )
      {
        UnistoreJetInstance = -2147024894;
        v34 = 101;
LABEL_51:
        Log_HREvent_10((unsigned int)UnistoreJetInstance, v31, v32, v34);
        goto LABEL_52;
      }
      if ( (unsigned int)IsFatalJetInitializationError(v30) )
      {
        if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x40) != 0 )
          McTemplateU0d_EventWriteTransfer(&MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context, JetInitFailed, v33);
        UnistoreJetInstance = -2147023538;
        v34 = 113;
        goto LABEL_51;
      }
      UnistoreJetInstance = GetHresultFromJetError(v33);
      if ( UnistoreJetInstance < 0 )
      {
LABEL_52:
        v7 = 707;
        v6 = 1;
        goto LABEL_5;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011b6c  push    rbx
0x180011b6e  push    rbp
0x180011b6f  push    rsi
0x180011b70  push    rdi
0x180011b71  push    r14
0x180011b73  push    r15
0x180011b75  sub     rsp, 38h
0x180011b79  lea     rbx, [rcx+8]
0x180011b7d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180011b81  mov     rbp, rdx
0x180011b84  cmp     [rbx], r15
0x180011b87  jnz     loc_180011F1A
0x180011b8d  xor     r14d, r14d
0x180011b90  cmp     [rcx+64h], r14d
0x180011b94  jz      short loc_180011BC1
0x180011b96  mov     rcx, rbx
0x180011b99  call    cs:__imp_GetUnistoreJetInstance
0x180011b9f  mov     ebx, eax
0x180011ba1  test    eax, eax
0x180011ba3  jns     loc_180011F1A
0x180011ba9  lea     edx, [r15+2]
0x180011bad  mov     r9d, 294h
0x180011bb3  mov     ecx, ebx
0x180011bb5  call    Log_HREvent_2
0x180011bba  mov     eax, ebx
0x180011bbc  jmp     loc_180011F1C
0x180011bc1  call    cs:__imp_SetCommsServiceJetGlobalSystemParameters
0x180011bc7  mov     esi, eax
0x180011bc9  test    eax, eax
0x180011bcb  jns     short loc_180011BE6
0x180011bcd  mov     edx, 1
0x180011bd2  mov     r9d, 298h
0x180011bd8  mov     ecx, eax
0x180011bda  call    Log_HREvent_2
0x180011bdf  mov     eax, esi
0x180011be1  jmp     loc_180011F1C
0x180011be6  lea     rdx, szInstanceName; "PimIdxMaint"
0x180011bed  mov     rcx, rbx; pinstance
0x180011bf0  call    cs:__imp_JetCreateInstanceW
0x180011bf6  test    eax, eax
0x180011bf8  jns     short loc_180011C0F
0x180011bfa  mov     ecx, eax; int
0x180011bfc  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011c01  mov     r9d, 29Dh
0x180011c07  xor     edx, edx
0x180011c09  mov     ebx, eax
0x180011c0b  mov     ecx, eax
0x180011c0d  jmp     short loc_180011BB5
0x180011c0f  mov     edi, 1
0x180011c14  mov     [rsp+68h+szParam], r14; szParam
0x180011c19  mov     r9d, edi; lParam
0x180011c1c  mov     r8d, 82h; paramid
0x180011c22  mov     rdx, r15; sesid
0x180011c25  mov     rcx, rbx; pinstance
0x180011c28  call    cs:__imp_JetSetSystemParameterW
0x180011c2e  test    eax, eax
0x180011c30  jns     short loc_180011C41
0x180011c32  mov     ecx, eax; int
0x180011c34  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011c39  mov     r9d, 29Fh
0x180011c3f  jmp     short loc_180011C07
0x180011c41  xor     r9d, r9d; lParam
0x180011c44  lea     rax, szParam; "PIM"
0x180011c4b  mov     rdx, r15; sesid
0x180011c4e  mov     [rsp+68h+szParam], rax; szParam
0x180011c53  mov     rcx, rbx; pinstance
0x180011c56  lea     r8d, [r9+3]; paramid
0x180011c5a  call    cs:__imp_JetSetSystemParameterW
0x180011c60  test    eax, eax
0x180011c62  jns     short loc_180011C73
0x180011c64  mov     ecx, eax; int
0x180011c66  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011c6b  mov     r9d, 2A0h
0x180011c71  jmp     short loc_180011C07
0x180011c73  xor     r9d, r9d; lParam
0x180011c76  mov     [rsp+68h+szParam], rbp; szParam
0x180011c7b  xor     r8d, r8d; paramid
0x180011c7e  mov     rdx, r15; sesid
0x180011c81  mov     rcx, rbx; pinstance
0x180011c84  call    cs:__imp_JetSetSystemParameterW
0x180011c8a  test    eax, eax
0x180011c8c  jns     short loc_180011CA0
0x180011c8e  mov     ecx, eax; int
0x180011c90  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011c95  mov     r9d, 2A1h
0x180011c9b  jmp     loc_180011C07
0x180011ca0  xor     r9d, r9d; lParam
0x180011ca3  mov     [rsp+68h+szParam], rbp; szParam
0x180011ca8  mov     r8d, edi; paramid
0x180011cab  mov     rdx, r15; sesid
0x180011cae  mov     rcx, rbx; pinstance
0x180011cb1  call    cs:__imp_JetSetSystemParameterW
0x180011cb7  test    eax, eax
0x180011cb9  jns     short loc_180011CCD
0x180011cbb  mov     ecx, eax; int
0x180011cbd  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011cc2  mov     r9d, 2A2h
0x180011cc8  jmp     loc_180011C07
0x180011ccd  xor     r9d, r9d; lParam
0x180011cd0  mov     [rsp+68h+szParam], rbp; szParam
0x180011cd5  mov     rdx, r15; sesid
0x180011cd8  mov     rcx, rbx; pinstance
0x180011cdb  lea     esi, [r9+2]
0x180011cdf  mov     r8d, esi; paramid
0x180011ce2  call    cs:__imp_JetSetSystemParameterW
0x180011ce8  test    eax, eax
0x180011cea  jns     short loc_180011CFE
0x180011cec  mov     ecx, eax; int
0x180011cee  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011cf3  mov     r9d, 2A3h
0x180011cf9  jmp     loc_180011C07
0x180011cfe  xor     edx, edx; sesid
0x180011d00  mov     [rsp+68h+szParam], r14; szParam
0x180011d05  mov     r9d, 500000h; lParam
0x180011d0b  mov     rcx, rbx; pinstance
0x180011d0e  lea     r8d, [rdx+18h]; paramid
0x180011d12  call    cs:__imp_JetSetSystemParameterA
0x180011d18  test    eax, eax
0x180011d1a  jns     short loc_180011D2E
0x180011d1c  mov     ecx, eax; int
0x180011d1e  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011d23  mov     r9d, 2A6h
0x180011d29  jmp     loc_180011C07
0x180011d2e  mov     r9, rsi; lParam
0x180011d31  mov     [rsp+68h+szParam], r14; szParam
0x180011d36  xor     edx, edx; sesid
0x180011d38  mov     r8d, 98h; paramid
0x180011d3e  mov     rcx, rbx; pinstance
0x180011d41  call    cs:__imp_JetSetSystemParameterA
0x180011d47  test    eax, eax
0x180011d49  jns     short loc_180011D5D
0x180011d4b  mov     ecx, eax; int
0x180011d4d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011d52  mov     r9d, 2A9h
0x180011d58  jmp     loc_180011C07
0x180011d5d  mov     r9, rdi; lParam
0x180011d60  mov     [rsp+68h+szParam], r14; szParam
0x180011d65  mov     r8d, 45h ; 'E'; paramid
0x180011d6b  mov     rdx, r15; sesid
0x180011d6e  mov     rcx, rbx; pinstance
0x180011d71  call    cs:__imp_JetSetSystemParameterA
0x180011d77  test    eax, eax
0x180011d79  jns     short loc_180011D8D
0x180011d7b  mov     ecx, eax; int
0x180011d7d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011d82  mov     r9d, 2ACh
0x180011d88  jmp     loc_180011C07
0x180011d8d  xor     edx, edx; sesid
0x180011d8f  mov     [rsp+68h+szParam], r14; szParam
0x180011d94  mov     r9d, 200h; lParam
0x180011d9a  mov     rcx, rbx; pinstance
0x180011d9d  lea     r8d, [rdx+0Ch]; paramid
0x180011da1  call    cs:__imp_JetSetSystemParameterA
0x180011da7  test    eax, eax
0x180011da9  jns     short loc_180011DBD
0x180011dab  mov     ecx, eax; int
0x180011dad  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011db2  mov     r9d, 2B1h
0x180011db8  jmp     loc_180011C07
0x180011dbd  xor     edx, edx; sesid
0x180011dbf  mov     [rsp+68h+szParam], r14; szParam
0x180011dc4  mov     r9d, 0C00h; lParam
0x180011dca  mov     rcx, rbx; pinstance
0x180011dcd  lea     r8d, [rdx+0Bh]; paramid
0x180011dd1  call    cs:__imp_JetSetSystemParameterA
0x180011dd7  test    eax, eax
0x180011dd9  jns     short loc_180011DED
0x180011ddb  mov     ecx, eax; int
0x180011ddd  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011de2  mov     r9d, 2B4h
0x180011de8  jmp     loc_180011C07
0x180011ded  xor     edx, edx; sesid
0x180011def  mov     [rsp+68h+szParam], r14; szParam
0x180011df4  mov     r9d, 80h; lParam
0x180011dfa  mov     rcx, rbx; pinstance
0x180011dfd  lea     r8d, [rdx+12h]; paramid
0x180011e01  call    cs:__imp_JetSetSystemParameterA
0x180011e07  test    eax, eax
0x180011e09  jns     short loc_180011E1D
0x180011e0b  mov     ecx, eax; int
0x180011e0d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011e12  mov     r9d, 2B7h
0x180011e18  jmp     loc_180011C07
0x180011e1d  xor     edx, edx; sesid
0x180011e1f  mov     [rsp+68h+szParam], r14; szParam
0x180011e24  mov     r8d, 0B1h; paramid
0x180011e2a  mov     rcx, rbx; pinstance
0x180011e2d  lea     r9d, [rdx+14h]; lParam
0x180011e31  call    cs:__imp_JetSetSystemParameterA
0x180011e37  test    eax, eax
0x180011e39  jns     short loc_180011E4D
0x180011e3b  mov     ecx, eax; int
0x180011e3d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011e42  mov     r9d, 2BAh
0x180011e48  jmp     loc_180011C07
0x180011e4d  mov     r9, rdi; lParam
0x180011e50  mov     [rsp+68h+szParam], r14; szParam
0x180011e55  mov     r8d, 30h ; '0'; paramid
0x180011e5b  mov     rdx, r15; sesid
0x180011e5e  mov     rcx, rbx; pinstance
0x180011e61  call    cs:__imp_JetSetSystemParameterW
0x180011e67  test    eax, eax
0x180011e69  jns     short loc_180011E7D
0x180011e6b  mov     ecx, eax; int
0x180011e6d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011e72  mov     r9d, 2BCh
0x180011e78  jmp     loc_180011C07
0x180011e7d  mov     r9, rdi; lParam
0x180011e80  mov     [rsp+68h+szParam], r14; szParam
0x180011e85  mov     r8d, 11h; paramid
0x180011e8b  mov     rdx, r15; sesid
0x180011e8e  mov     rcx, rbx; pinstance
0x180011e91  call    cs:__imp_JetSetSystemParameterW
0x180011e97  test    eax, eax
0x180011e99  jns     short loc_180011EAD
0x180011e9b  mov     ecx, eax; int
0x180011e9d  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011ea2  mov     r9d, 2BDh
0x180011ea8  jmp     loc_180011C07
0x180011ead  mov     r9, rdi; lParam
0x180011eb0  mov     [rsp+68h+szParam], r14; szParam
0x180011eb5  mov     r8d, 2Dh ; '-'; paramid
0x180011ebb  mov     rdx, r15; sesid
0x180011ebe  mov     rcx, rbx; pinstance
0x180011ec1  call    cs:__imp_JetSetSystemParameterW
0x180011ec7  test    eax, eax
0x180011ec9  jns     short loc_180011EDD
0x180011ecb  mov     ecx, eax; int
0x180011ecd  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180011ed2  mov     r9d, 2BEh
0x180011ed8  jmp     loc_180011C07
0x180011edd  xor     edx, edx; grbit
0x180011edf  mov     rcx, rbx; pinstance
0x180011ee2  call    cs:__imp_JetInit2
0x180011ee8  mov     ebx, eax
0x180011eea  test    eax, eax
0x180011eec  jz      short loc_180011F1A
0x180011eee  cmp     eax, 0FFFFF8EDh
0x180011ef3  jnz     short loc_180011F02
0x180011ef5  mov     ebx, 80070002h
0x180011efa  mov     r9d, 65h ; 'e'
0x180011f00  jmp     short loc_180011F53
0x180011f02  mov     ecx, ebx; int
0x180011f04  call    ?IsFatalJetInitializationError@@YAHJ@Z; IsFatalJetInitializationError(long)
0x180011f09  test    eax, eax
0x180011f0b  jnz     short loc_180011F29
0x180011f0d  mov     ecx, ebx; int
0x180011f0f  call    ?GetHresultFromJetError@@YAJJ@Z; GetHresultFromJetError(long)
0x180011f14  mov     ebx, eax
0x180011f16  test    eax, eax
0x180011f18  js      short loc_180011F5A
0x180011f1a  xor     eax, eax
0x180011f1c  add     rsp, 38h
0x180011f20  pop     r15
0x180011f22  pop     r14
0x180011f24  pop     rdi
0x180011f25  pop     rsi
0x180011f26  pop     rbp
0x180011f27  pop     rbx
0x180011f28  retn
0x180011f29  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 40h
0x180011f30  jz      short loc_180011F48
0x180011f32  mov     r8d, ebx
0x180011f35  lea     rdx, JetInitFailed
0x180011f3c  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context
0x180011f43  call    McTemplateU0d_EventWriteTransfer
0x180011f48  mov     ebx, 8007054Eh
0x180011f4d  mov     r9d, 71h ; 'q'
0x180011f53  mov     ecx, ebx
0x180011f55  call    Log_HREvent_10
0x180011f5a  mov     r9d, 2C3h
0x180011f60  mov     edx, edi
0x180011f62  jmp     loc_180011BB3
```
