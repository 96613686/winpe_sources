# CAppContainer::EnumPackages(ushort const *,_GUID *,unsigned __int64 *,ulong,IEnumPackage * *)

- ea: `0x18001cb90`
- end: `0x18001d128`
- name: `?EnumPackages@CAppContainer@@UEAAJPEBGPEAU_GUID@@PEA_KKPEAPEAUIEnumPackage@@@Z`
- size: `1432`
- prototype: `__int64 __fastcall(CAppContainer *this, const unsigned __int16 *, struct _GUID *, FILETIME *, unsigned int, struct IEnumPackage **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800016d0`
- `0x1800016f4`
- `0x180001710`
- `0x180002024`
- `0x180002aa0`
- `0x180008f58`
- `0x18001b1a0`
- `0x18001b780`
- `0x18001cb90`
- `0x180024458`
- `0x180024e04`
- `0x180027e90`
- `0x180027f84`
- `0x180028088`
- `0x180028190`
- `0x180028980`
- `0x18002ad30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cc39`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cc39`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001cdd9`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001cdd9`
- `adsldpc!ADSIGetObjectAttributes` at `0x18001d038`
- `adsldpc!ADSIGetObjectAttributes` at `0x18001d038`
- `adsldpc!FreeADsMem` at `0x18001d071`
- `adsldpc!FreeADsMem` at `0x18001d071`

## string_xrefs

- `0x18001cd16`: `lastUpdateSequence`
- `0x18001ce0a`: `lastUpdateSequence`
- `0x18001ce5e`: `lastUpdateSequence`
- `0x18001cf55`: `(|(|(msiScriptName=*A*)(msiScriptName=*P*))(!(msiScriptName=*)))`
- `0x18001cf90`: `(|(|(msiScriptName=*A*)(msiScriptName=*P*))(!(msiScriptName=*)))`
- `0x18001cf89`: `(|(|(msiScriptName=*A*)(&(canUpgradeScript=*)(msiScriptName=*P*)))(!(msiScriptName=*)))`
- `0x18001cf9d`: `(|(|(msiScriptName=*A*)(&(canUpgradeScript=*)(msiScriptName=*P*)))(!(msiScriptName=*)))`

## pseudocode

```c
__int64 __fastcall CAppContainer::EnumPackages(
        CAppContainer *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        FILETIME *a4,
        unsigned int a5,
        struct IEnumPackage **a6)
{
  FILETIME *v9; // rsi
  CEnumPackage *v11; // rax
  unsigned int v12; // r8d
  FILETIME *v13; // r11
  unsigned int v14; // r15d
  unsigned int v15; // eax
  unsigned int v16; // r12d
  int v17; // eax
  int v18; // ebx
  __int64 v19; // r15
  int v20; // eax
  __int64 v21; // rsi
  int v22; // eax
  int v23; // eax
  int v24; // eax
  CEnumPackage *v25; // rdi
  struct IEnumPackage **v26; // rsi
  const unsigned __int16 *v27; // rdx
  const wchar_t *v28; // rax
  struct tagCSPLATFORM *v29; // rbx
  __int64 v30; // rcx
  int v31; // eax
  const unsigned __int16 *v32; // rcx
  int v33; // eax
  unsigned __int16 *v34; // [rsp+20h] [rbp-E0h]
  struct tagCSPLATFORM *v35; // [rsp+28h] [rbp-D8h]
  struct tagCSPLATFORM *v36; // [rsp+28h] [rbp-D8h]
  unsigned int Spec; // [rsp+50h] [rbp-B0h] BYREF
  struct IEnumPackage **v38; // [rsp+58h] [rbp-A8h]
  CEnumPackage *v39; // [rsp+60h] [rbp-A0h]
  FILETIME *lpFileTime; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID *v41; // [rsp+70h] [rbp-90h] BYREF
  struct tagCSPLATFORM v42; // [rsp+78h] [rbp-88h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v44[40]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v45[1000]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v46[1504]; // [rsp+8C0h] [rbp+7C0h] BYREF

  v41 = a3;
  v38 = a6;
  lpFileTime = a4;
  v9 = a4;
  memset_0(v45, 0, sizeof(v45));
  v42 = 0;
  if ( a5 != 1 && a5 != 2 && a5 != 3 && a5 != 4 && a5 - 5 >= 2 )
    return 2147942487LL;
  *a6 = 0;
  v11 = (CEnumPackage *)LocalAlloc(0, 0x480u);
  if ( v11 )
  {
    v35 = (struct tagCSPLATFORM *)*((_QWORD *)this + 145);
    SystemTime = (struct _SYSTEMTIME)*((_OWORD *)this + 35);
    v39 = CEnumPackage::CEnumPackage(
            v11,
            (CAppContainer *)((char *)this + 1168),
            (struct _GUID *)&SystemTime,
            0,
            (const unsigned __int16 *)this + 4,
            v35);
    if ( v39 )
    {
      Spec = ClientSideFilterFromQuerySpec(a5, *((_QWORD *)this + 145) != 0);
      v14 = Spec;
      v15 = (_DWORD)v13 + 1;
      if ( a2 && *a2 != (_WORD)v13 )
        v12 = (_DWORD)v13 + 1;
      if ( v9 && (FILETIME *)*v9 != v13 )
        v12 += v15;
      v16 = v12 + 1;
      if ( !a3 )
        v16 = v12;
      if ( !v16 )
      {
        v17 = StringCchPrintfW(v45, 0x3E8u, L"(%s=%s)", L"objectclass", L"packageRegistration");
        v13 = 0;
        v18 = v17;
        if ( v17 < 0 )
        {
          v25 = v39;
          v26 = a6;
          goto LABEL_45;
        }
LABEL_49:
        if ( a5 == 1 )
        {
          StringCchCopyW(v46, 0x5DCu, v45);
LABEL_62:
          if ( gDebug != (_DWORD)v13 )
          {
            _DebugMsg(2, 0xC87u, v46, v14);
            v13 = 0;
          }
          if ( (v14 & 0x800000) != 0 )
          {
            v29 = &v42;
            GetDefaultPlatform(&v42, 0, 0);
            v13 = 0;
          }
          else
          {
            v29 = (struct tagCSPLATFORM *)v13;
          }
          if ( v9 )
          {
            v30 = *((_QWORD *)this + 68);
            v41 = (struct _GUID *)L"lastUpdateSequence";
            lpFileTime = v13;
            Spec = (unsigned int)v13;
            v31 = ADSIGetObjectAttributes(v30, &v41, 1, &lpFileTime, &Spec);
            v13 = 0;
            if ( v31 >= 0 )
            {
              if ( Spec )
              {
                if ( lpFileTime[3].dwLowDateTime )
                  v32 = *(const unsigned __int16 **)(*(_QWORD *)&lpFileTime[2] + 8LL);
                else
                  v32 = 0;
                TimeToUsn(v32, v9);
                FreeADsMem(lpFileTime);
                v13 = 0;
              }
            }
          }
          v25 = v39;
          v33 = (int)v13;
          LOBYTE(v33) = *((_QWORD *)this + 145) != (_QWORD)v13;
          v18 = CEnumPackage::Initialize(v39, *((const unsigned __int16 **)this + 66), v46, a5, v33, v29);
          if ( v18 >= 0 )
          {
            v26 = v38;
            v18 = (**(__int64 (__fastcall ***)(CEnumPackage *, GUID *, struct IEnumPackage **))v25)(
                    v25,
                    &IID_IEnumPackage,
                    v38);
            if ( v18 >= 0 )
              return 0;
LABEL_45:
            CEnumPackage::~CEnumPackage(v25);
            operator delete(v25);
            *v26 = 0;
            return RemapErrorCode(v18, v27);
          }
LABEL_44:
          v26 = v38;
          goto LABEL_45;
        }
        if ( a5 != 2 )
        {
          if ( a5 == 3 )
          {
            v28 = L"(|(|(msiScriptName=*A*)(&(canUpgradeScript=*)(msiScriptName=*P*)))(!(msiScriptName=*)))";
            goto LABEL_56;
          }
          if ( a5 != 4 )
          {
            if ( a5 == 5 )
            {
              v28 = L"(|(|(msiScriptName=*A*)(msiScriptName=*P*))(!(msiScriptName=*)))";
              if ( *((FILETIME **)this + 145) == v13 )
                v28 = L"(|(|(msiScriptName=*A*)(&(canUpgradeScript=*)(msiScriptName=*P*)))(!(msiScriptName=*)))";
              goto LABEL_56;
            }
            if ( a5 != 6 )
              goto LABEL_62;
          }
        }
        v28 = L"(|(|(msiScriptName=*A*)(msiScriptName=*P*))(!(msiScriptName=*)))";
LABEL_56:
        StringCchPrintfW(v46, 0x5DCu, L"(&%s%s)", v45, v28);
        v13 = 0;
        goto LABEL_62;
      }
      v19 = -1;
      if ( v16 <= v15 )
      {
        LODWORD(v21) = (_DWORD)v13;
      }
      else
      {
        v20 = StringCchPrintfW(v45, 0x3E8u, L"(&");
        v13 = 0;
        v18 = v20;
        if ( v20 < 0 )
          goto LABEL_43;
        v21 = -1;
        do
          ++v21;
        while ( v45[v21] );
      }
      if ( a2 && *a2 != (_WORD)v13 )
      {
        v22 = StringCchPrintfW(&v45[(unsigned int)v21], (unsigned int)(1000 - v21), L"(%s=*%s*)", L"packageName", a2);
        v13 = 0;
        v18 = v22;
        if ( v22 < 0 )
          goto LABEL_43;
        v21 = -1;
        do
          ++v21;
        while ( v45[v21] );
      }
      if ( lpFileTime && (FILETIME *)*lpFileTime != v13 )
      {
        SystemTime = 0;
        FileTimeToSystemTime(lpFileTime, &SystemTime);
        LODWORD(v36) = SystemTime.wMonth;
        LODWORD(v34) = SystemTime.wYear;
        v23 = StringCchPrintfW(
                &v45[(unsigned int)v21],
                (unsigned int)(1000 - v21),
                L"(%s>=%04d%02d%02d%02d%02d%02d)",
                L"lastUpdateSequence",
                v34,
                v36,
                SystemTime.wDay,
                SystemTime.wHour,
                SystemTime.wMinute,
                (unsigned int)SystemTime.wSecond + 1);
        v13 = 0;
        v18 = v23;
        if ( v23 < 0 )
          goto LABEL_43;
        v21 = -1;
        do
          ++v21;
        while ( v45[v21] );
      }
      if ( !v41 )
        goto LABEL_40;
      StringFromGUID(v41, v44);
      v24 = StringCchPrintfW(&v45[(unsigned int)v21], (unsigned int)(1000 - v21), L"(%s=%s)", L"categories", v44);
      v13 = 0;
      v18 = v24;
      if ( v24 >= 0 )
      {
        do
          ++v19;
        while ( v45[v19] );
        LODWORD(v21) = v19;
LABEL_40:
        if ( v16 > 1 )
        {
          if ( (unsigned int)(1000 - v21) < 2 )
          {
            v18 = -2147024774;
            goto LABEL_43;
          }
          v45[(unsigned int)v21] = 41;
          if ( 2 * (unsigned __int64)(unsigned int)(v21 + 1) >= 0x7D0 )
            _report_rangecheckfailure();
          v45[(unsigned int)(v21 + 1)] = (unsigned __int16)v13;
        }
        v14 = Spec;
        v9 = lpFileTime;
        goto LABEL_49;
      }
LABEL_43:
      v25 = v39;
      goto LABEL_44;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001cb90  push    rbp
0x18001cb92  push    rbx
0x18001cb93  push    rsi
0x18001cb94  push    rdi
0x18001cb95  push    r12
0x18001cb97  push    r13
0x18001cb99  push    r14
0x18001cb9b  push    r15
0x18001cb9d  lea     rbp, [rsp-1398h]
0x18001cba5  mov     eax, 1498h
0x18001cbaa  call    _alloca_probe
0x18001cbaf  sub     rsp, rax
0x18001cbb2  mov     rax, cs:__security_cookie
0x18001cbb9  xor     rax, rsp
0x18001cbbc  mov     [rbp+13D0h+var_50], rax
0x18001cbc3  mov     r14, [rbp+13D0h+arg_28]
0x18001cbca  mov     rbx, r8
0x18001cbcd  mov     rdi, rdx
0x18001cbd0  mov     [rsp+14D0h+var_1460], rbx
0x18001cbd5  mov     r13, rcx
0x18001cbd8  mov     [rsp+14D0h+var_1478], r14
0x18001cbdd  xor     edx, edx; Val
0x18001cbdf  mov     [rsp+14D0h+lpFileTime], r9
0x18001cbe4  mov     r8d, 7D0h; Size
0x18001cbea  lea     rcx, [rbp+13D0h+var_13E0]; void *
0x18001cbee  mov     rsi, r9
0x18001cbf1  call    memset_0
0x18001cbf6  mov     eax, [rbp+13D0h+arg_20]
0x18001cbfc  xorps   xmm0, xmm0
0x18001cbff  movups  xmmword ptr [rsp+14D0h+var_1458.dwPlatformId], xmm0
0x18001cc04  sub     eax, 1
0x18001cc07  jz      short loc_18001CC2C
0x18001cc09  sub     eax, 1
0x18001cc0c  jz      short loc_18001CC2C
0x18001cc0e  sub     eax, 1
0x18001cc11  jz      short loc_18001CC2C
0x18001cc13  sub     eax, 1
0x18001cc16  jz      short loc_18001CC2C
0x18001cc18  sub     eax, 1
0x18001cc1b  jz      short loc_18001CC2C
0x18001cc1d  cmp     eax, 1
0x18001cc20  jz      short loc_18001CC2C
0x18001cc22  mov     eax, 80070057h
0x18001cc27  jmp     loc_18001D0FF
0x18001cc2c  xor     r15d, r15d
0x18001cc2f  mov     edx, 480h; uBytes
0x18001cc34  xor     ecx, ecx; uFlags
0x18001cc36  mov     [r14], r15
0x18001cc39  call    cs:__imp_LocalAlloc
0x18001cc3f  test    rax, rax
0x18001cc42  jz      loc_18001D0FA
0x18001cc48  mov     rcx, [r13+488h]
0x18001cc4f  lea     r8, [r13+8]
0x18001cc53  movups  xmm0, xmmword ptr [r13+230h]
0x18001cc5b  mov     [rsp+14D0h+var_14A8], rcx; void *
0x18001cc60  lea     rdx, [r13+490h]; struct CServerContext *
0x18001cc67  mov     [rsp+14D0h+var_14B0], r8; unsigned __int16 *
0x18001cc6c  xor     r9d, r9d; unsigned __int16 *
0x18001cc6f  lea     r8, [rbp+13D0h+SystemTime]; struct _GUID *
0x18001cc73  mov     rcx, rax; this
0x18001cc76  movdqu  xmmword ptr [rbp+13D0h+SystemTime.wYear], xmm0
0x18001cc7b  call    ??0CEnumPackage@@QEAA@PEAVCServerContext@@U_GUID@@PEBG2PEAX@Z; CEnumPackage::CEnumPackage(CServerContext *,_GUID,ushort const *,ushort const *,void *)
0x18001cc80  xor     r11d, r11d
0x18001cc83  mov     [rsp+14D0h+var_1470], rax
0x18001cc88  test    rax, rax
0x18001cc8b  jz      loc_18001D0FA
0x18001cc91  cmp     [r13+488h], r11
0x18001cc98  mov     edx, r11d
0x18001cc9b  mov     ecx, [rbp+13D0h+arg_20]; unsigned int
0x18001cca1  mov     r8d, r11d
0x18001cca4  setnz   dl; int
0x18001cca7  call    ?ClientSideFilterFromQuerySpec@@YAKKH@Z; ClientSideFilterFromQuerySpec(ulong,int)
0x18001ccac  mov     [rsp+14D0h+var_1480], eax
0x18001ccb0  mov     r15d, eax
0x18001ccb3  lea     eax, [r11+1]
0x18001ccb7  test    rdi, rdi
0x18001ccba  jz      short loc_18001CCC4
0x18001ccbc  cmp     [rdi], r11w
0x18001ccc0  cmovnz  r8d, eax
0x18001ccc4  test    rsi, rsi
0x18001ccc7  jz      short loc_18001CCD1
0x18001ccc9  cmp     [rsi], r11
0x18001cccc  jz      short loc_18001CCD1
0x18001ccce  add     r8d, eax
0x18001ccd1  test    rbx, rbx
0x18001ccd4  lea     r12d, [r8+1]
0x18001ccd8  cmovz   r12d, r8d
0x18001ccdc  test    r12d, r12d
0x18001ccdf  jnz     short loc_18001CD22
0x18001cce1  lea     rax, aPackageregistr; "packageRegistration"
0x18001cce8  mov     edx, 3E8h; unsigned __int64
0x18001cced  lea     r9, aObjectclass; "objectclass"
0x18001ccf4  mov     [rsp+14D0h+var_14B0], rax
0x18001ccf9  lea     r8, aSS; "(%s=%s)"
0x18001cd00  lea     rcx, [rbp+13D0h+var_13E0]; unsigned __int16 *
0x18001cd04  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cd09  xor     r11d, r11d
0x18001cd0c  mov     ebx, eax
0x18001cd0e  test    eax, eax
0x18001cd10  js      loc_18001D0EA
0x18001cd16  lea     rdi, aLastupdatesequ; "lastUpdateSequence"
0x18001cd1d  jmp     loc_18001CF31
0x18001cd22  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001cd26  mov     r14d, 3E8h
0x18001cd2c  cmp     r12d, eax
0x18001cd2f  jbe     short loc_18001CD64
0x18001cd31  lea     r8, asc_180030D70; "(&"
0x18001cd38  mov     edx, r14d; unsigned __int64
0x18001cd3b  lea     rcx, [rbp+13D0h+var_13E0]; unsigned __int16 *
0x18001cd3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cd44  xor     r11d, r11d
0x18001cd47  mov     ebx, eax
0x18001cd49  test    eax, eax
0x18001cd4b  js      loc_18001CED1
0x18001cd51  lea     rax, [rbp+13D0h+var_13E0]
0x18001cd55  mov     rsi, r15
0x18001cd58  inc     rsi
0x18001cd5b  cmp     [rax+rsi*2], r11w
0x18001cd60  jnz     short loc_18001CD58
0x18001cd62  jmp     short loc_18001CD67
0x18001cd64  mov     esi, r11d
0x18001cd67  test    rdi, rdi
0x18001cd6a  jz      short loc_18001CDB7
0x18001cd6c  cmp     [rdi], r11w
0x18001cd70  jz      short loc_18001CDB7
0x18001cd72  mov     eax, esi
0x18001cd74  lea     rcx, [rbp+13D0h+var_13E0]
0x18001cd78  mov     edx, r14d
0x18001cd7b  mov     [rsp+14D0h+var_14B0], rdi
0x18001cd80  sub     edx, esi; unsigned __int64
0x18001cd82  lea     r9, aPackagename_0; "packageName"
0x18001cd89  lea     r8, aSS_4; "(%s=*%s*)"
0x18001cd90  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18001cd94  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cd99  xor     r11d, r11d
0x18001cd9c  mov     ebx, eax
0x18001cd9e  test    eax, eax
0x18001cda0  js      loc_18001CED1
0x18001cda6  lea     rax, [rbp+13D0h+var_13E0]
0x18001cdaa  mov     rsi, r15
0x18001cdad  inc     rsi
0x18001cdb0  cmp     [rax+rsi*2], r11w
0x18001cdb5  jnz     short loc_18001CDAD
0x18001cdb7  mov     rcx, [rsp+14D0h+lpFileTime]; lpFileTime
0x18001cdbc  test    rcx, rcx
0x18001cdbf  jz      loc_18001CE5E
0x18001cdc5  cmp     [rcx], r11
0x18001cdc8  jz      loc_18001CE5E
0x18001cdce  xorps   xmm0, xmm0
0x18001cdd1  lea     rdx, [rbp+13D0h+SystemTime]; lpSystemTime
0x18001cdd5  movups  xmmword ptr [rbp+13D0h+SystemTime.wYear], xmm0
0x18001cdd9  call    cs:__imp_FileTimeToSystemTime
0x18001cddf  movzx   edi, [rbp+13D0h+SystemTime.wSecond]
0x18001cde3  lea     rcx, [rbp+13D0h+var_13E0]
0x18001cde7  movzx   r8d, [rbp+13D0h+SystemTime.wMinute]
0x18001cdec  inc     edi
0x18001cdee  movzx   r9d, [rbp+13D0h+SystemTime.wHour]
0x18001cdf3  mov     edx, r14d
0x18001cdf6  movzx   r10d, [rbp+13D0h+SystemTime.wDay]
0x18001cdfb  sub     edx, esi; unsigned __int64
0x18001cdfd  movzx   r11d, [rbp+13D0h+SystemTime.wMonth]
0x18001ce02  movzx   ebx, [rbp+13D0h+SystemTime.wYear]
0x18001ce06  mov     [rsp+14D0h+var_1488], edi
0x18001ce0a  lea     rdi, aLastupdatesequ; "lastUpdateSequence"
0x18001ce11  mov     [rsp+14D0h+var_1490], r8d
0x18001ce16  lea     r8, aS04d02d02d02d0; "(%s>=%04d%02d%02d%02d%02d%02d)"
0x18001ce1d  mov     [rsp+14D0h+var_1498], r9d
0x18001ce22  mov     r9, rdi
0x18001ce25  mov     [rsp+14D0h+var_14A0], r10d
0x18001ce2a  mov     eax, esi
0x18001ce2c  mov     dword ptr [rsp+14D0h+var_14A8], r11d
0x18001ce31  mov     dword ptr [rsp+14D0h+var_14B0], ebx
0x18001ce35  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18001ce39  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ce3e  xor     r11d, r11d
0x18001ce41  mov     ebx, eax
0x18001ce43  test    eax, eax
0x18001ce45  js      loc_18001CED1
0x18001ce4b  lea     rax, [rbp+13D0h+var_13E0]
0x18001ce4f  mov     rsi, r15
0x18001ce52  inc     rsi
0x18001ce55  cmp     [rax+rsi*2], r11w
0x18001ce5a  jnz     short loc_18001CE52
0x18001ce5c  jmp     short loc_18001CE65
0x18001ce5e  lea     rdi, aLastupdatesequ; "lastUpdateSequence"
0x18001ce65  mov     rcx, [rsp+14D0h+var_1460]; struct _GUID *
0x18001ce6a  test    rcx, rcx
0x18001ce6d  jz      short loc_18001CEBD
0x18001ce6f  lea     rdx, [rbp+13D0h+var_1430]; unsigned __int16 *
0x18001ce73  call    ?StringFromGUID@@YAHAEBU_GUID@@PEAG@Z; StringFromGUID(_GUID const &,ushort *)
0x18001ce78  mov     eax, esi
0x18001ce7a  lea     rcx, [rbp+13D0h+var_13E0]
0x18001ce7e  mov     edx, r14d
0x18001ce81  lea     r9, aCategories; "categories"
0x18001ce88  sub     edx, esi; unsigned __int64
0x18001ce8a  lea     r8, aSS; "(%s=%s)"
0x18001ce91  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18001ce95  lea     rax, [rbp+13D0h+var_1430]
0x18001ce99  mov     [rsp+14D0h+var_14B0], rax
0x18001ce9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cea3  xor     r11d, r11d
0x18001cea6  mov     ebx, eax
0x18001cea8  test    eax, eax
0x18001ceaa  js      short loc_18001CED1
0x18001ceac  lea     rax, [rbp+13D0h+var_13E0]
0x18001ceb0  inc     r15
0x18001ceb3  cmp     [rax+r15*2], r11w
0x18001ceb8  jnz     short loc_18001CEB0
0x18001ceba  mov     esi, r15d
0x18001cebd  cmp     r12d, 1
0x18001cec1  jbe     short loc_18001CF27
0x18001cec3  sub     r14d, esi
0x18001cec6  cmp     r14d, 2
0x18001ceca  jnb     short loc_18001CF02
0x18001cecc  mov     ebx, 8007007Ah
0x18001ced1  mov     rdi, [rsp+14D0h+var_1470]
0x18001ced6  xor     r15d, r15d
0x18001ced9  mov     rsi, [rsp+14D0h+var_1478]
0x18001cede  mov     rcx, rdi; this
0x18001cee1  call    ??1CEnumPackage@@QEAA@XZ; CEnumPackage::~CEnumPackage(void)
0x18001cee6  mov     edx, 480h; unsigned __int64
0x18001ceeb  mov     rcx, rdi; void *
0x18001ceee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cef3  mov     ecx, ebx; int
0x18001cef5  mov     [rsi], r15
0x18001cef8  call    ?RemapErrorCode@@YAJJPEBG@Z; RemapErrorCode(long,ushort const *)
0x18001cefd  jmp     loc_18001D0FF
0x18001cf02  mov     ecx, 29h ; ')'
0x18001cf07  mov     eax, esi
0x18001cf09  mov     [rbp+rax*2+13D0h+var_13E0], cx
0x18001cf0e  lea     ecx, [rsi+1]
0x18001cf11  add     rcx, rcx
0x18001cf14  cmp     rcx, 7D0h
0x18001cf1b  jnb     loc_18001D122
0x18001cf21  mov     [rbp+rcx+13D0h+var_13E0], r11w
0x18001cf27  mov     r15d, [rsp+14D0h+var_1480]
0x18001cf2c  mov     rsi, [rsp+14D0h+lpFileTime]
0x18001cf31  mov     eax, [rbp+13D0h+arg_20]
0x18001cf37  sub     eax, 1
0x18001cf3a  jz      short loc_18001CFA6
0x18001cf3c  sub     eax, 1
0x18001cf3f  jz      short loc_18001CF55
0x18001cf41  sub     eax, 1
0x18001cf44  jz      short loc_18001CF9D
0x18001cf46  sub     eax, 1
0x18001cf49  jz      short loc_18001CF55
0x18001cf4b  sub     eax, 1
0x18001cf4e  jz      short loc_18001CF82
0x18001cf50  cmp     eax, 1
0x18001cf53  jnz     short loc_18001CFBB
0x18001cf55  lea     rax, aMsiscriptnameA; "(|(|(msiScriptName=*A*)(msiScriptName=*"...
0x18001cf5c  lea     r9, [rbp+13D0h+var_13E0]
0x18001cf60  mov     [rsp+14D0h+var_14B0], rax
0x18001cf65  lea     r8, aSS_0; "(&%s%s)"
0x18001cf6c  mov     edx, 5DCh; unsigned __int64
0x18001cf71  lea     rcx, [rbp+13D0h+var_C10]; unsigned __int16 *
0x18001cf78  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001cf7d  xor     r11d, r11d
0x18001cf80  jmp     short loc_18001CFBB
0x18001cf82  cmp     [r13+488h], r11
0x18001cf89  lea     rcx, aMsiscriptnameA_0; "(|(|(msiScriptName=*A*)(&(canUpgradeScr"...
0x18001cf90  lea     rax, aMsiscriptnameA; "(|(|(msiScriptName=*A*)(msiScriptName=*"...
0x18001cf97  cmovz   rax, rcx
0x18001cf9b  jmp     short loc_18001CF5C
0x18001cf9d  lea     rax, aMsiscriptnameA_0; "(|(|(msiScriptName=*A*)(&(canUpgradeScr"...
0x18001cfa4  jmp     short loc_18001CF5C
0x18001cfa6  lea     r8, [rbp+13D0h+var_13E0]; unsigned __int16 *
0x18001cfaa  mov     edx, 5DCh; unsigned __int64
0x18001cfaf  lea     rcx, [rbp+13D0h+var_C10]; unsigned __int16 *
0x18001cfb6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001cfbb  cmp     cs:?gDebug@@3KA, r11d; ulong gDebug
0x18001cfc2  jz      short loc_18001CFE0
0x18001cfc4  mov     r9d, r15d
0x18001cfc7  lea     r8, [rbp+13D0h+var_C10]
0x18001cfce  mov     edx, 0C87h; unsigned int
0x18001cfd3  mov     ecx, 2; unsigned int
0x18001cfd8  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001cfdd  xor     r11d, r11d
0x18001cfe0  bt      r15d, 17h
0x18001cfe5  jb      short loc_18001CFEC
0x18001cfe7  mov     rbx, r11
0x18001cfea  jmp     short loc_18001D003
0x18001cfec  xor     r8d, r8d; int
0x18001cfef  lea     rcx, [rsp+14D0h+var_1458]; struct tagCSPLATFORM *
0x18001cff4  xor     edx, edx; int
0x18001cff6  lea     rbx, [rsp+14D0h+var_1458]
0x18001cffb  call    ?GetDefaultPlatform@@YAXPEAUtagCSPLATFORM@@HJ@Z; GetDefaultPlatform(tagCSPLATFORM *,int,long)
0x18001d000  xor     r11d, r11d
0x18001d003  test    rsi, rsi
0x18001d006  jz      short loc_18001D07A
0x18001d008  mov     rcx, [r13+220h]
0x18001d00f  lea     rax, [rsp+14D0h+var_1480]
0x18001d014  lea     r9, [rsp+14D0h+lpFileTime]
0x18001d019  mov     [rsp+14D0h+var_14B0], rax
0x18001d01e  mov     r8d, 1
0x18001d024  mov     [rsp+14D0h+var_1460], rdi
0x18001d029  lea     rdx, [rsp+14D0h+var_1460]
0x18001d02e  mov     [rsp+14D0h+lpFileTime], r11
0x18001d033  mov     [rsp+14D0h+var_1480], r11d
0x18001d038  call    cs:__imp_ADSIGetObjectAttributes
  ... truncated ...
```
