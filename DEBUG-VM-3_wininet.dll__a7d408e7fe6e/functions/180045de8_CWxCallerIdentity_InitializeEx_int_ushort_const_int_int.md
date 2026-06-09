# CWxCallerIdentity::InitializeEx(int,ushort const *,int,int)

- ea: `0x180045de8`
- end: `0x180046329`
- name: `?InitializeEx@CWxCallerIdentity@@QEAAJHPEBGHH@Z`
- size: `1345`
- prototype: `int(CWxCallerIdentity *__hidden this, int, const unsigned __int16 *, int, int)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800432d4`
- `0x1800433f0`
- `0x180043960`
- `0x180044c68`

## callees

- `0x18001eaec`
- `0x180025514`
- `0x180025910`
- `0x180027ec0`
- `0x180044d78`
- `0x180045de8`
- `0x180046330`
- `0x180046a1c`
- `0x1800548ec`
- `0x1800701d0`
- `0x18012ce48`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801dd7e8`
- `0x1801e4988`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045f72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045f72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045fc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045fc7`
- `ntdll!RtlFreeSid` at `0x1800462ac`
- `ntdll!RtlFreeSid` at `0x1800462ac`
- `ntdll!RtlGetAppContainerParent` at `0x180046273`
- `ntdll!RtlGetAppContainerParent` at `0x180046273`
- `ntdll!RtlGetAppContainerSidType` at `0x18004607a`
- `ntdll!RtlGetAppContainerSidType` at `0x18004607a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180045f0b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180045f0b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045edb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045edb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180045f42`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180045f42`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18004611c`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18004611c`

## pseudocode

```c
__int64 __fastcall CWxCallerIdentity::InitializeEx(
        CWxCallerIdentity *this,
        int a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  const WCHAR *v11; // rsi
  signed int AdjustedCallerToken; // edi
  int v14; // r12d
  struct _SID *v15; // rcx
  int v16; // eax
  int v17; // esi
  bool v18; // sf
  int v19; // eax
  int LastError; // eax
  int v21; // eax
  int v22; // eax
  int AppContainerParent; // eax
  const WCHAR *v24; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v25; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v27[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v28[2]; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+84h] [rbp-7Ch]
  int v32; // [rsp+88h] [rbp-78h] BYREF
  _BYTE pDestinationSid[80]; // [rsp+90h] [rbp-70h] BYREF
  PSID TokenInformation[10]; // [rsp+E0h] [rbp-20h] BYREF

  v31 = 0;
  TokenHandle = 0;
  v25 = 0;
  memset_0(pDestinationSid, 0, 0x44u);
  v11 = &Data;
  v27[1] = 0;
  v27[0] = (unsigned __int16 *)&Data;
  v32 = 0;
  if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
    WPP_SF_qSll(v9, v8, v10, (_DWORD)this, (__int64)a3);
  AdjustedCallerToken = WxGetAdjustedCallerToken(*((_DWORD *)this + 6), &v32, &v25, &TokenHandle);
  if ( AdjustedCallerToken < 0 )
  {
    v31 = 366;
    goto LABEL_21;
  }
  if ( *((_DWORD *)this + 6) )
    *((_DWORD *)this + 7) = v32;
  if ( a2 )
  {
    AdjustedCallerToken = CWxString::Set((CWxCallerIdentity *)((char *)this + 8), a3);
    if ( AdjustedCallerToken < 0 )
    {
      v31 = 385;
      goto LABEL_21;
    }
    *((_DWORD *)this + 9) = 1;
    goto LABEL_20;
  }
  if ( v25 != 1 )
  {
    if ( v25 == 2 )
    {
      AdjustedCallerToken = CWxString::Set((CWxCallerIdentity *)((char *)this + 8), &c_wszLowIl);
      if ( AdjustedCallerToken < 0 )
      {
        v31 = 418;
        goto LABEL_21;
      }
    }
    else
    {
      if ( v25 != 3 )
      {
        AdjustedCallerToken = -2147418113;
        v31 = 427;
        goto LABEL_21;
      }
      AdjustedCallerToken = CWxString::Set((CWxCallerIdentity *)((char *)this + 8), "M");
      if ( AdjustedCallerToken < 0 )
      {
        v31 = 422;
        goto LABEL_21;
      }
    }
    goto LABEL_20;
  }
  HIDWORD(StringSid) = v25 - 1;
  ReturnLength = 76;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, TokenInformation, 0x4Cu, &ReturnLength) )
  {
    if ( !TokenInformation[0] )
    {
      HIDWORD(StringSid) = 226;
      AdjustedCallerToken = -2147418113;
      goto LABEL_76;
    }
    if ( CopySid(0x44u, pDestinationSid, TokenInformation[0]) )
    {
      AdjustedCallerToken = 0;
    }
    else
    {
      LastError = WxGetLastError();
      AdjustedCallerToken = LastError;
      if ( LastError > 0 )
        AdjustedCallerToken = (unsigned __int16)LastError | 0x80070000;
      HIDWORD(StringSid) = 228;
      if ( AdjustedCallerToken >= 0 )
        AdjustedCallerToken = -2147418113;
    }
  }
  else
  {
    v19 = WxGetLastError();
    AdjustedCallerToken = v19;
    if ( v19 > 0 )
      AdjustedCallerToken = (unsigned __int16)v19 | 0x80070000;
    HIDWORD(StringSid) = 224;
    if ( AdjustedCallerToken >= 0 )
      AdjustedCallerToken = -2147418113;
  }
  if ( AdjustedCallerToken < 0 )
  {
LABEL_76:
    v31 = 396;
    goto LABEL_21;
  }
  if ( a5 )
  {
    HIDWORD(v24) = 0;
    v32 = 0;
    StringSid = 0;
    v28[0] = &Data;
    v28[1] = 0;
    ReturnLength = 0;
    memset_0(TokenInformation, 0, 0x44u);
    v14 = 0;
    CWxString::Empty((CWxString *)v27);
    if ( (int)RtlGetAppContainerSidType(pDestinationSid, &v32) < 0 )
    {
      AdjustedCallerToken = 0;
    }
    else
    {
      v15 = (struct _SID *)pDestinationSid;
      if ( v32 == 1 )
      {
        AppContainerParent = RtlGetAppContainerParent(pDestinationSid, &StringSid);
        v16 = HRESULT_FROM_NTSTATUS(AppContainerParent);
        AdjustedCallerToken = v16;
        if ( v16 < 0 )
        {
          HIDWORD(v24) = 413;
          goto LABEL_37;
        }
        v15 = (struct _SID *)StringSid;
      }
      v16 = WxSIDToSIDString(v15, (struct CWxString *)v28);
      AdjustedCallerToken = v16;
      if ( v16 < 0 )
      {
        HIDWORD(v24) = 423;
LABEL_37:
        v17 = v16;
LABEL_42:
        if ( StringSid )
        {
          RtlFreeSid(StringSid);
          StringSid = 0;
        }
        CWxString::_Release((CWxString *)v28);
        v18 = v17 < 0;
        v11 = v27[0];
        if ( v18 )
        {
          v31 = 403;
          goto LABEL_21;
        }
        if ( !v14 )
          goto LABEL_14;
        AdjustedCallerToken = CWxString::Set((CWxCallerIdentity *)((char *)this + 8), L"Shared_", v27[0]);
        if ( AdjustedCallerToken < 0 )
        {
          v31 = 407;
          goto LABEL_21;
        }
        *((_DWORD *)this + 8) = 1;
LABEL_20:
        *((_DWORD *)this + 1) = v25;
        goto LABEL_21;
      }
      if ( !(unsigned int)CheckTokenCapability(TokenHandle, &c_rgbCapabilityChildWebContentSid, &ReturnLength) )
      {
        v21 = WxGetLastError();
        AdjustedCallerToken = v21;
        if ( v21 > 0 )
          AdjustedCallerToken = (unsigned __int16)v21 | 0x80070000;
        if ( AdjustedCallerToken < 0 )
        {
          v17 = AdjustedCallerToken;
        }
        else
        {
          AdjustedCallerToken = -2147418113;
          v17 = -2147418113;
        }
        HIDWORD(v24) = 428;
        goto LABEL_42;
      }
      AdjustedCallerToken = 0;
      if ( ReturnLength )
      {
        CWxString::Transfer((CWxString *)v28, (struct CWxString *)v27);
        v14 = 1;
      }
    }
    v17 = 0;
    goto LABEL_42;
  }
LABEL_14:
  HIDWORD(v24) = 0;
  StringSid = 0;
  if ( ConvertSidToStringSidW(pDestinationSid, &StringSid) )
  {
    AdjustedCallerToken = CWxString::Set((CWxCallerIdentity *)((char *)this + 8), StringSid);
    if ( AdjustedCallerToken < 0 )
      HIDWORD(v24) = 115;
  }
  else
  {
    v22 = WxGetLastError();
    AdjustedCallerToken = v22;
    if ( v22 > 0 )
      AdjustedCallerToken = (unsigned __int16)v22 | 0x80070000;
    HIDWORD(v24) = 114;
    if ( AdjustedCallerToken >= 0 )
      AdjustedCallerToken = -2147418113;
  }
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( AdjustedCallerToken >= 0 )
    goto LABEL_20;
  v31 = 414;
LABEL_21:
  if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
    WPP_SF_qD(1053, 12, &WPP_f1ca5156dd39373ce438d8bd3c0a11eb_Traceguids, this, AdjustedCallerToken);
  v24 = v11;
  if ( v11 != &Data && v11 )
    WxFreeHeapEx(&v24);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)AdjustedCallerToken;
}

```

## disassembly

```asm
0x180045de8  mov     [rsp-8+arg_8], rsi
0x180045ded  mov     [rsp-8+arg_18], rdi
0x180045df2  push    rbp
0x180045df3  push    r12
0x180045df5  push    r13
0x180045df7  push    r14
0x180045df9  push    r15
0x180045dfb  lea     rbp, [rsp-40h]
0x180045e00  sub     rsp, 140h
0x180045e07  mov     rax, cs:__security_cookie
0x180045e0e  xor     rax, rsp
0x180045e11  mov     [rbp+60h+var_30], rax
0x180045e15  mov     r12d, edx
0x180045e18  mov     [rbp+60h+var_DC], 0
0x180045e1f  xor     edx, edx; Val
0x180045e21  mov     [rsp+160h+TokenHandle], 0
0x180045e2a  mov     r15, r8
0x180045e2d  mov     [rsp+160h+var_118], 0
0x180045e35  mov     r14, rcx
0x180045e38  lea     rcx, [rbp+60h+pDestinationSid]; void *
0x180045e3c  lea     r8d, [rdx+44h]; Size
0x180045e40  call    memset_0
0x180045e45  lea     rsi, Data
0x180045e4c  mov     [rsp+160h+var_100], 0
0x180045e55  mov     [rsp+160h+var_108], rsi
0x180045e5a  mov     [rbp+60h+var_D8], 0
0x180045e61  test    byte ptr cs:xmmword_180266B60+3, 20h
0x180045e68  mov     r13d, [rbp+60h+arg_20]
0x180045e6f  jnz     loc_1800461E5
0x180045e75  mov     ecx, [r14+18h]; int
0x180045e79  lea     r9, [rsp+160h+TokenHandle]; void **
0x180045e7e  lea     r8, [rsp+160h+var_118]; unsigned int *
0x180045e83  lea     rdx, [rbp+60h+var_D8]; int *
0x180045e87  call    ?WxGetAdjustedCallerToken@@YAJHPEAHPEAKPEAPEAX@Z; WxGetAdjustedCallerToken(int,int *,ulong *,void * *)
0x180045e8c  mov     edi, eax
0x180045e8e  test    eax, eax
0x180045e90  js      loc_1800461FC
0x180045e96  cmp     dword ptr [r14+18h], 0
0x180045e9b  jnz     loc_180046208
0x180045ea1  test    r12d, r12d
0x180045ea4  jnz     loc_1800460AE
0x180045eaa  mov     eax, [rsp+160h+var_118]
0x180045eae  sub     eax, 1
0x180045eb1  jnz     loc_180045FF8
0x180045eb7  mov     rcx, [rsp+160h+TokenHandle]; TokenHandle
0x180045ebc  lea     r9d, [r12+4Ch]; TokenInformationLength
0x180045ec1  mov     dword ptr [rsp+160h+StringSid+4], eax
0x180045ec5  lea     r8, [rbp+60h+TokenInformation]; TokenInformation
0x180045ec9  lea     rax, [rbp+60h+var_E0]
0x180045ecd  mov     [rbp+60h+var_E0], r9d
0x180045ed1  lea     edx, [r12+1Fh]; TokenInformationClass
0x180045ed6  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x180045edb  call    cs:__imp_GetTokenInformation
0x180045ee1  mov     r15d, 8000FFFFh
0x180045ee7  mov     r12d, 80070000h
0x180045eed  test    eax, eax
0x180045eef  jz      loc_180046152
0x180045ef5  mov     r8, [rbp+60h+TokenInformation]; pSourceSid
0x180045ef9  test    r8, r8
0x180045efc  jz      loc_180046257
0x180045f02  lea     rdx, [rbp+60h+pDestinationSid]; pDestinationSid
0x180045f06  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180045f0b  call    cs:__imp_CopySid
0x180045f11  test    eax, eax
0x180045f13  jz      loc_180046176
0x180045f19  xor     edi, edi
0x180045f1b  test    edi, edi
0x180045f1d  js      loc_180046262
0x180045f23  test    r13d, r13d
0x180045f26  jnz     loc_180046030
0x180045f2c  xor     r13d, r13d
0x180045f2f  lea     rdx, [rsp+160h+StringSid]; StringSid
0x180045f34  mov     dword ptr [rsp+160h+var_120+4], r13d
0x180045f39  lea     rcx, [rbp+60h+pDestinationSid]; Sid
0x180045f3d  mov     [rsp+160h+StringSid], r13
0x180045f42  call    cs:__imp_ConvertSidToStringSidW
0x180045f48  test    eax, eax
0x180045f4a  jz      loc_1800461C1
0x180045f50  mov     rdx, [rsp+160h+StringSid]; unsigned __int16 *
0x180045f55  lea     rcx, [r14+8]; this
0x180045f59  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x180045f5e  mov     edi, eax
0x180045f60  test    eax, eax
0x180045f62  js      loc_1800462EE
0x180045f68  mov     rcx, [rsp+160h+StringSid]; hMem
0x180045f6d  test    rcx, rcx
0x180045f70  jz      short loc_180045F7D
0x180045f72  call    cs:__imp_LocalFree
0x180045f78  mov     [rsp+160h+StringSid], r13
0x180045f7d  test    edi, edi
0x180045f7f  js      loc_1800462FB
0x180045f85  mov     eax, [rsp+160h+var_118]
0x180045f89  mov     [r14+4], eax
0x180045f8d  test    byte ptr cs:xmmword_180266B60+3, 20h
0x180045f94  jnz     loc_180046307
0x180045f9a  lea     rax, Data
0x180045fa1  mov     [rsp+160h+var_120], rsi
0x180045fa6  cmp     rsi, rax
0x180045fa9  jz      short loc_180045FBA
0x180045fab  test    rsi, rsi
0x180045fae  jz      short loc_180045FBA
0x180045fb0  lea     rcx, [rsp+160h+var_120]
0x180045fb5  call    WxFreeHeapEx
0x180045fba  cmp     [rsp+160h+TokenHandle], 0
0x180045fc0  jz      short loc_180045FCD
0x180045fc2  mov     rcx, [rsp+160h+TokenHandle]; hObject
0x180045fc7  call    cs:__imp_CloseHandle
0x180045fcd  mov     eax, edi
0x180045fcf  mov     rcx, [rbp+60h+var_30]
0x180045fd3  xor     rcx, rsp; StackCookie
0x180045fd6  call    __security_check_cookie
0x180045fdb  lea     r11, [rsp+160h+var_20]
0x180045fe3  mov     rsi, [r11+38h]
0x180045fe7  mov     rdi, [r11+48h]
0x180045feb  mov     rsp, r11
0x180045fee  pop     r15
0x180045ff0  pop     r14
0x180045ff2  pop     r13
0x180045ff4  pop     r12
0x180045ff6  pop     rbp
0x180045ff7  retn
0x180045ff8  sub     eax, 1
0x180045ffb  jz      loc_180046231
0x180046001  cmp     eax, 1
0x180046004  jnz     loc_180046220
0x18004600a  lea     rcx, [r14+8]; this
0x18004600e  lea     rdx, ?c_wszMediumIl@@3QBGB; "M"
0x180046015  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x18004601a  mov     edi, eax
0x18004601c  test    eax, eax
0x18004601e  jns     loc_180045F85
0x180046024  mov     [rbp+60h+var_DC], 1A6h
0x18004602b  jmp     loc_180045F8D
0x180046030  xor     r13d, r13d
0x180046033  lea     rax, Data
0x18004603a  xor     edx, edx; Val
0x18004603c  mov     dword ptr [rsp+160h+var_120+4], r13d
0x180046041  lea     rcx, [rbp+60h+TokenInformation]; void *
0x180046045  mov     [rbp+60h+var_D8], r13d
0x180046049  mov     [rsp+160h+StringSid], r13
0x18004604e  lea     r8d, [r13+44h]; Size
0x180046052  mov     [rsp+160h+var_F8], rax
0x180046057  mov     [rsp+160h+var_F0], r13
0x18004605c  mov     [rbp+60h+var_E0], r13d
0x180046060  call    memset_0
0x180046065  lea     rcx, [rsp+160h+var_108]; this
0x18004606a  mov     r12d, r13d
0x18004606d  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x180046072  lea     rcx, [rbp+60h+pDestinationSid]
0x180046076  lea     rdx, [rbp+60h+var_D8]
0x18004607a  call    cs:__imp_RtlGetAppContainerSidType
0x180046080  test    eax, eax
0x180046082  js      short loc_1800460D1
0x180046084  cmp     [rbp+60h+var_D8], 1
0x180046088  lea     rcx, [rbp+60h+pDestinationSid]; struct _SID *
0x18004608c  jz      loc_18004626E
0x180046092  lea     rdx, [rsp+160h+var_F8]; struct CWxString *
0x180046097  call    ?WxSIDToSIDString@@YAJPEAU_SID@@PEAVCWxString@@@Z; WxSIDToSIDString(_SID *,CWxString *)
0x18004609c  mov     edi, eax
0x18004609e  test    eax, eax
0x1800460a0  jns     short loc_18004610C
0x1800460a2  mov     dword ptr [rsp+160h+var_120+4], 1A7h
0x1800460aa  mov     esi, eax
0x1800460ac  jmp     short loc_1800460D7
0x1800460ae  lea     rcx, [r14+8]; this
0x1800460b2  mov     rdx, r15; unsigned __int16 *
0x1800460b5  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x1800460ba  mov     edi, eax
0x1800460bc  test    eax, eax
0x1800460be  js      loc_180046214
0x1800460c4  mov     dword ptr [r14+24h], 1
0x1800460cc  jmp     loc_180045F85
0x1800460d1  mov     edi, r13d
0x1800460d4  mov     esi, r13d
0x1800460d7  mov     rcx, [rsp+160h+StringSid]; Sid
0x1800460dc  test    rcx, rcx
0x1800460df  jnz     loc_1800462AC
0x1800460e5  lea     rcx, [rsp+160h+var_F8]; this
0x1800460ea  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800460ef  test    esi, esi
0x1800460f1  mov     rsi, [rsp+160h+var_108]
0x1800460f6  js      short loc_180046146
0x1800460f8  test    r12d, r12d
0x1800460fb  jnz     loc_1800462BC
0x180046101  mov     r12d, 80070000h
0x180046107  jmp     loc_180045F2F
0x18004610c  mov     rcx, [rsp+160h+TokenHandle]
0x180046111  lea     r8, [rbp+60h+var_E0]
0x180046115  lea     rdx, c_rgbCapabilityChildWebContentSid
0x18004611c  call    cs:__imp_CheckTokenCapability
0x180046122  test    eax, eax
0x180046124  jz      short loc_18004619A
0x180046126  mov     edi, r13d
0x180046129  cmp     [rbp+60h+var_E0], r13d
0x18004612d  jz      short loc_1800460D4
0x18004612f  lea     rdx, [rsp+160h+var_108]; struct CWxString *
0x180046134  lea     rcx, [rsp+160h+var_F8]; this
0x180046139  call    ?Transfer@CWxString@@QEAAXPEAV1@@Z; CWxString::Transfer(CWxString *)
0x18004613e  mov     r12d, 1
0x180046144  jmp     short loc_1800460D4
0x180046146  mov     [rbp+60h+var_DC], 193h
0x18004614d  jmp     loc_180045F8D
0x180046152  call    WxGetLastError
0x180046157  mov     edi, eax
0x180046159  test    eax, eax
0x18004615b  jle     short loc_180046163
0x18004615d  movzx   edi, ax
0x180046160  or      edi, r12d
0x180046163  test    edi, edi
0x180046165  mov     dword ptr [rsp+160h+StringSid+4], 0E0h
0x18004616d  cmovns  edi, r15d
0x180046171  jmp     loc_180045F1B
0x180046176  call    WxGetLastError
0x18004617b  mov     edi, eax
0x18004617d  test    eax, eax
0x18004617f  jle     short loc_180046187
0x180046181  movzx   edi, ax
0x180046184  or      edi, r12d
0x180046187  test    edi, edi
0x180046189  mov     dword ptr [rsp+160h+StringSid+4], 0E4h
0x180046191  cmovns  edi, r15d
0x180046195  jmp     loc_180045F1B
0x18004619a  call    WxGetLastError
0x18004619f  mov     edi, eax
0x1800461a1  test    eax, eax
0x1800461a3  jle     short loc_1800461AE
0x1800461a5  movzx   edi, ax
0x1800461a8  or      edi, 80070000h
0x1800461ae  test    edi, edi
0x1800461b0  js      loc_18004629D
0x1800461b6  mov     edi, r15d
0x1800461b9  mov     esi, r15d
0x1800461bc  jmp     loc_18004629F
0x1800461c1  call    WxGetLastError
0x1800461c6  mov     edi, eax
0x1800461c8  test    eax, eax
0x1800461ca  jle     short loc_1800461D2
0x1800461cc  movzx   edi, ax
0x1800461cf  or      edi, r12d
0x1800461d2  test    edi, edi
0x1800461d4  mov     dword ptr [rsp+160h+var_120+4], 72h ; 'r'
0x1800461dc  cmovns  edi, r15d
0x1800461e0  jmp     loc_180045F68
0x1800461e5  mov     [rsp+160h+var_130], r13d
0x1800461ea  mov     r9, r14
0x1800461ed  mov     [rsp+160h+ReturnLength], r15
0x1800461f2  call    WPP_SF_qSll
0x1800461f7  jmp     loc_180045E75
0x1800461fc  mov     [rbp+60h+var_DC], 16Eh
0x180046203  jmp     loc_180045F8D
0x180046208  mov     eax, [rbp+60h+var_D8]
0x18004620b  mov     [r14+1Ch], eax
0x18004620f  jmp     loc_180045EA1
0x180046214  mov     [rbp+60h+var_DC], 181h
0x18004621b  jmp     loc_180045F8D
0x180046220  mov     edi, 8000FFFFh
0x180046225  mov     [rbp+60h+var_DC], 1ABh
0x18004622c  jmp     loc_180045F8D
0x180046231  lea     rcx, [r14+8]; this
0x180046235  lea     rdx, ?c_wszLowIl@@3QBGB; unsigned __int16 *
0x18004623c  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x180046241  mov     edi, eax
0x180046243  test    eax, eax
0x180046245  jns     loc_180045F85
0x18004624b  mov     [rbp+60h+var_DC], 1A2h
0x180046252  jmp     loc_180045F8D
0x180046257  mov     dword ptr [rsp+160h+StringSid+4], 0E2h
0x18004625f  mov     edi, r15d
0x180046262  mov     [rbp+60h+var_DC], 18Ch
0x180046269  jmp     loc_180045F8D
0x18004626e  lea     rdx, [rsp+160h+StringSid]
0x180046273  call    cs:__imp_RtlGetAppContainerParent
0x180046279  mov     ecx, eax; int
0x18004627b  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x180046280  mov     edi, eax
0x180046282  test    eax, eax
0x180046284  jns     short loc_180046293
0x180046286  mov     dword ptr [rsp+160h+var_120+4], 19Dh
0x18004628e  jmp     loc_1800460AA
0x180046293  mov     rcx, [rsp+160h+StringSid]
0x180046298  jmp     loc_180046092
0x18004629d  mov     esi, edi
0x18004629f  mov     dword ptr [rsp+160h+var_120+4], 1ACh
0x1800462a7  jmp     loc_1800460D7
0x1800462ac  call    cs:__imp_RtlFreeSid
0x1800462b2  mov     [rsp+160h+StringSid], r13
0x1800462b7  jmp     loc_1800460E5
0x1800462bc  lea     rcx, [r14+8]; this
0x1800462c0  mov     r8, rsi; unsigned __int16 *
0x1800462c3  lea     rdx, ?c_wszSharedStatePrefix@@3QBGB; "Shared_"
0x1800462ca  call    ?Set@CWxString@@QEAAJPEBG0@Z; CWxString::Set(ushort const *,ushort const *)
0x1800462cf  mov     edi, eax
0x1800462d1  test    eax, eax
0x1800462d3  jns     short loc_1800462E1
0x1800462d5  mov     [rbp+60h+var_DC], 197h
0x1800462dc  jmp     loc_180045F8D
0x1800462e1  mov     dword ptr [r14+20h], 1
0x1800462e9  jmp     loc_180045F85
0x1800462ee  mov     dword ptr [rsp+160h+var_120+4], 73h ; 's'
0x1800462f6  jmp     loc_180045F68
  ... truncated ...
```
