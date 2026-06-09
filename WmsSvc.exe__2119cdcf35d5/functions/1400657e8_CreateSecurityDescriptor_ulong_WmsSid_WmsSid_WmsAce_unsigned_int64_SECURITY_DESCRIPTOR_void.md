# CreateSecurityDescriptor(ulong,WmsSid *,WmsSid *,WmsAce *,unsigned __int64,_SECURITY_DESCRIPTOR *,void * *)

- ea: `0x1400657e8`
- end: `0x140065c5b`
- name: `?CreateSecurityDescriptor@@YAJKPEAUWmsSid@@0PEAUWmsAce@@_KPEAU_SECURITY_DESCRIPTOR@@PEAPEAX@Z`
- size: `1139`
- prototype: `__int64 __fastcall(__int64, struct WmsSid *, struct WmsSid *, struct WmsAce *, unsigned __int64, PSECURITY_DESCRIPTOR pSecurityDescriptor, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140044afc`
- `0x140065fdc`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400657e8`
- `0x140066310`
- `0x14007cb9e`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140065c01`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140065c01`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140065ba4`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140065ba4`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140065b45`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140065b45`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140065b0e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140065b0e`
- `ADVAPI32!AddAccessDeniedAce` at `0x140065a06`
- `ADVAPI32!AddAccessDeniedAce` at `0x140065a06`
- `ADVAPI32!AddAccessAllowedAce` at `0x140065a40`
- `ADVAPI32!AddAccessAllowedAce` at `0x140065a40`
- `ADVAPI32!InitializeAcl` at `0x140065901`
- `ADVAPI32!InitializeAcl` at `0x140065901`
- `KERNEL32!GetLastError` at `0x14006590f`
- `KERNEL32!GetLastError` at `0x140065a10`
- `KERNEL32!GetLastError` at `0x140065ad9`
- `KERNEL32!GetLastError` at `0x140065b18`
- `KERNEL32!GetLastError` at `0x140065b4f`
- `KERNEL32!GetLastError` at `0x140065bae`
- `KERNEL32!GetLastError` at `0x140065c0b`
- `KERNEL32!GetLastError` at `0x14006590f`
- `KERNEL32!GetLastError` at `0x140065a10`
- `KERNEL32!GetLastError` at `0x140065ad9`
- `KERNEL32!GetLastError` at `0x140065b18`
- `KERNEL32!GetLastError` at `0x140065b4f`
- `KERNEL32!GetLastError` at `0x140065bae`
- `KERNEL32!GetLastError` at `0x140065c0b`
- `KERNEL32!IsDebuggerPresent` at `0x140065886`
- `KERNEL32!IsDebuggerPresent` at `0x14006596a`
- `KERNEL32!IsDebuggerPresent` at `0x140065aa8`
- `KERNEL32!IsDebuggerPresent` at `0x140065886`
- `KERNEL32!IsDebuggerPresent` at `0x14006596a`
- `KERNEL32!IsDebuggerPresent` at `0x140065aa8`

## string_xrefs

- `0x140065863`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14006593f`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140065a84`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14006586a`: `pSDTempBuffer`
- `0x140065853`: `CreateSecurityDescriptor`
- `0x14006592f`: `CreateSecurityDescriptor`
- `0x140065a73`: `CreateSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CreateSecurityDescriptor(
        __int64 a1,
        struct WmsSid *a2,
        struct WmsSid *a3,
        struct WmsAce *a4,
        unsigned __int64 a5,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        void **a7)
{
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // r13
  struct _ACL *v12; // rax
  struct _ACL *v13; // r15
  signed int WmsSid; // ebx
  signed int LastError; // eax
  unsigned int v16; // r13d
  __int64 v17; // r9
  char *v18; // rcx
  __int64 v19; // rsi
  struct _SID *v20; // r13
  __int64 v21; // rdi
  int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  signed int v28; // eax
  const unsigned __int16 *v30; // [rsp+30h] [rbp-58h]
  int v31; // [rsp+38h] [rbp-50h]
  __int64 v32; // [rsp+40h] [rbp-48h]
  unsigned __int64 v35; // [rsp+B0h] [rbp+28h]

  v9 = (unsigned int)(80 * a5 + 8);
  v10 = v9;
  v11 = v9 + 68 * a5;
  v32 = v11;
  v12 = (struct _ACL *)operator new(v11 + 136);
  v13 = v12;
  if ( !v12 )
  {
    WmsSid = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x3AFu,
      L"CreateSecurityDescriptor",
      L"CPR",
      L"pSDTempBuffer",
      -2147024882);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        943,
        L"CreateSecurityDescriptor",
        L"CPR",
        L"pSDTempBuffer",
        -2147024882);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        943,
        L"CreateSecurityDescriptor",
        L"CPR",
        L"pSDTempBuffer",
        -2147024882);
    goto LABEL_56;
  }
  memset_0(v12, 0, 68 * a5);
  if ( !InitializeAcl(v13, v9, 2u) )
  {
    LastError = GetLastError();
    WmsSid = LastError;
    if ( LastError > 0 )
      WmsSid = (unsigned __int16)LastError | 0x80070000;
    v16 = 957;
LABEL_11:
    if ( WmsSid >= 0 )
      WmsSid = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v16,
      L"CreateSecurityDescriptor",
      L"CBRAEx",
      L"fSuccess",
      WmsSid);
    if ( IsDebuggerPresent() )
    {
      v31 = WmsSid;
      v17 = v16;
      v30 = L"fSuccess";
LABEL_15:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v17,
        L"CreateSecurityDescriptor",
        L"CBRAEx",
        v30,
        v31);
    }
    else
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v16,
        L"CreateSecurityDescriptor",
        L"CBRAEx",
        L"fSuccess",
        WmsSid);
    }
    goto LABEL_56;
  }
  WmsSid = 0;
  v18 = (char *)v13 + v10;
  v19 = 0;
  v35 = (unsigned __int64)v13 + v10;
  if ( !a5 )
  {
LABEL_35:
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v13, 0) )
      {
        if ( !a2 )
          goto LABEL_59;
        WmsSid = CreateWmsSid(a2, (struct _SID *)((char *)v13 + v11), 0x44u);
        if ( WmsSid < 0 )
          goto LABEL_56;
        if ( SetSecurityDescriptorOwner(pSecurityDescriptor, (char *)v13 + v11, 0) )
        {
LABEL_59:
          if ( !a3 )
            goto LABEL_55;
          WmsSid = CreateWmsSid(a3, (struct _SID *)((char *)&v13[8].AceCount + v11), 0x44u);
          if ( WmsSid < 0 )
            goto LABEL_56;
          if ( SetSecurityDescriptorGroup(pSecurityDescriptor, (char *)&v13[8].AceCount + v11, 0) )
          {
LABEL_55:
            *a7 = v13;
            v13 = 0;
            goto LABEL_56;
          }
          v28 = GetLastError();
          WmsSid = v28;
          if ( v28 > 0 )
            WmsSid = (unsigned __int16)v28 | 0x80070000;
          v16 = 1009;
        }
        else
        {
          v27 = GetLastError();
          WmsSid = v27;
          if ( v27 > 0 )
            WmsSid = (unsigned __int16)v27 | 0x80070000;
          v16 = 999;
        }
      }
      else
      {
        v26 = GetLastError();
        WmsSid = v26;
        if ( v26 > 0 )
          WmsSid = (unsigned __int16)v26 | 0x80070000;
        v16 = 990;
      }
    }
    else
    {
      v25 = GetLastError();
      WmsSid = v25;
      if ( v25 > 0 )
        WmsSid = (unsigned __int16)v25 | 0x80070000;
      v16 = 987;
    }
    goto LABEL_11;
  }
  while ( 1 )
  {
    v20 = (struct _SID *)&v18[68 * v19];
    v21 = 32 * v19;
    WmsSid = CreateWmsSid((struct WmsAce *)((char *)a4 + 32 * v19 + 16), v20, 0x44u);
    if ( WmsSid < 0 )
      break;
    v22 = *(_DWORD *)((char *)a4 + v21);
    if ( v22 )
    {
      if ( v22 != 1 )
      {
        WmsSid = -2147024809;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          0x3D5u,
          L"CreateSecurityDescriptor",
          L"CBRAEx",
          L"0",
          -2147024809);
        if ( IsDebuggerPresent() )
        {
          v31 = -2147024809;
          v17 = 981;
          v30 = L"0";
          goto LABEL_15;
        }
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          981,
          L"CreateSecurityDescriptor",
          L"CBRAEx",
          L"0",
          -2147024809);
        break;
      }
      if ( !AddAccessDeniedAce(v13, *(_DWORD *)((char *)a4 + v21 + 4), *(_DWORD *)((char *)a4 + v21 + 8), v20) )
      {
        v23 = GetLastError();
        WmsSid = v23;
        if ( v23 > 0 )
          WmsSid = (unsigned __int16)v23 | 0x80070000;
        v16 = 977;
        goto LABEL_11;
      }
    }
    else if ( !AddAccessAllowedAce(v13, *(_DWORD *)((char *)a4 + v21 + 4), *(_DWORD *)((char *)a4 + v21 + 8), v20) )
    {
      v24 = GetLastError();
      WmsSid = v24;
      if ( v24 > 0 )
        WmsSid = (unsigned __int16)v24 | 0x80070000;
      v16 = 972;
      goto LABEL_11;
    }
    if ( ++v19 >= a5 )
    {
      v11 = v32;
      goto LABEL_35;
    }
    v18 = (char *)v35;
  }
LABEL_56:
  operator delete(v13);
  return (unsigned int)WmsSid;
}

```

## disassembly

```asm
0x1400657e8  mov     [rsp+arg_0], rbx
0x1400657ed  mov     [rsp+arg_10], r8
0x1400657f2  mov     [rsp+arg_8], rdx
0x1400657f7  push    rbp
0x1400657f8  push    rsi
0x1400657f9  push    rdi
0x1400657fa  push    r12
0x1400657fc  push    r13
0x1400657fe  push    r14
0x140065800  push    r15
0x140065802  sub     rsp, 50h
0x140065806  mov     rbp, [rsp+88h+arg_20]
0x14006580e  mov     r14, r9
0x140065811  imul    rsi, rbp, 44h ; 'D'
0x140065815  lea     ebx, ds:0[rbp*4]
0x14006581c  add     ebx, ebp
0x14006581e  shl     ebx, 4
0x140065821  add     ebx, 8
0x140065824  mov     edi, ebx
0x140065826  lea     r13, [rbx+rsi]
0x14006582a  lea     rcx, [r13+88h]; Size
0x140065831  mov     [rsp+88h+var_48], r13
0x140065836  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006583b  mov     r15, rax
0x14006583e  test    rax, rax
0x140065841  jnz     loc_1400658E6
0x140065847  mov     ebx, 8007000Eh
0x14006584c  lea     r12, aCpr; "CPR"
0x140065853  lea     rsi, aCreatesecurity_0; "CreateSecurityDescriptor"
0x14006585a  mov     [rsp+88h+var_60], ebx; int
0x14006585e  mov     ebp, 3AFh
0x140065863  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006586a  lea     r14, aPsdtempbuffer; "pSDTempBuffer"
0x140065871  mov     r9, r12; unsigned __int16 *
0x140065874  mov     r8, rsi; unsigned __int16 *
0x140065877  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x14006587c  mov     edx, ebp; unsigned int
0x14006587e  mov     rcx, rdi; unsigned __int16 *
0x140065881  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140065886  call    cs:__imp_IsDebuggerPresent
0x14006588c  test    eax, eax
0x14006588e  jz      short loc_1400658BE
0x140065890  mov     [rsp+88h+var_50], ebx
0x140065894  lea     ecx, [r15+2]; unsigned __int8
0x140065898  mov     [rsp+88h+var_58], r14
0x14006589d  mov     r9d, ebp
0x1400658a0  mov     qword ptr [rsp+88h+var_60], r12
0x1400658a5  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400658ac  mov     [rsp+88h+var_68], rsi
0x1400658b1  mov     r8, rdi
0x1400658b4  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400658b9  jmp     loc_140065C39
0x1400658be  mov     dword ptr [rsp+88h+var_58], ebx
0x1400658c2  mov     r8d, ebp
0x1400658c5  mov     qword ptr [rsp+88h+var_60], r14
0x1400658ca  mov     [rsp+88h+var_68], r12
0x1400658cf  mov     r9, rsi
0x1400658d2  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400658d9  mov     rdx, rdi
0x1400658dc  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400658e1  jmp     loc_140065C39
0x1400658e6  mov     r8, rsi; Size
0x1400658e9  xor     edx, edx; Val
0x1400658eb  mov     rcx, r15; void *
0x1400658ee  call    memset_0
0x1400658f3  mov     r12d, 2
0x1400658f9  mov     edx, ebx; nAclLength
0x1400658fb  mov     r8d, r12d; dwAclRevision
0x1400658fe  mov     rcx, r15; pAcl
0x140065901  call    cs:__imp_InitializeAcl
0x140065907  test    eax, eax
0x140065909  jnz     loc_1400659A3
0x14006590f  call    cs:__imp_GetLastError
0x140065915  mov     ebx, eax
0x140065917  test    eax, eax
0x140065919  jle     short loc_140065924
0x14006591b  movzx   ebx, ax
0x14006591e  or      ebx, 80070000h
0x140065924  mov     r13d, 3BDh
0x14006592a  mov     eax, 80004005h
0x14006592f  lea     rsi, aCreatesecurity_0; "CreateSecurityDescriptor"
0x140065936  test    ebx, ebx
0x140065938  lea     rbp, aCbraex; "CBRAEx"
0x14006593f  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140065946  mov     r8, rsi; unsigned __int16 *
0x140065949  cmovns  ebx, eax
0x14006594c  lea     r14, aFsuccess; "fSuccess"
0x140065953  mov     [rsp+88h+var_60], ebx; int
0x140065957  mov     r9, rbp; unsigned __int16 *
0x14006595a  mov     edx, r13d; unsigned int
0x14006595d  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x140065962  mov     rcx, rdi; unsigned __int16 *
0x140065965  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006596a  call    cs:__imp_IsDebuggerPresent
0x140065970  test    eax, eax
0x140065972  jz      short loc_14006598D
0x140065974  mov     [rsp+88h+var_50], ebx
0x140065978  mov     r9d, r13d
0x14006597b  mov     [rsp+88h+var_58], r14
0x140065980  mov     qword ptr [rsp+88h+var_60], rbp
0x140065985  mov     ecx, r12d
0x140065988  jmp     loc_1400658A5
0x14006598d  mov     dword ptr [rsp+88h+var_58], ebx
0x140065991  mov     r8d, r13d
0x140065994  mov     qword ptr [rsp+88h+var_60], r14
0x140065999  mov     [rsp+88h+var_68], rbp
0x14006599e  jmp     loc_1400658CF
0x1400659a3  xor     ebx, ebx
0x1400659a5  lea     rcx, [rdi+r15]
0x1400659a9  xor     esi, esi
0x1400659ab  mov     [rsp+88h+arg_20], rcx
0x1400659b3  test    rbp, rbp
0x1400659b6  jz      loc_140065AFE
0x1400659bc  imul    r13, rsi, 44h ; 'D'
0x1400659c0  mov     rdi, rsi
0x1400659c3  mov     r8d, 44h ; 'D'; unsigned __int64
0x1400659c9  add     r13, rcx
0x1400659cc  shl     rdi, 5
0x1400659d0  lea     rcx, [r14+10h]
0x1400659d4  mov     rdx, r13; struct _SID *
0x1400659d7  add     rcx, rdi; struct WmsSid *
0x1400659da  call    ?CreateWmsSid@@YAJPEAUWmsSid@@PEAU_SID@@_K@Z; CreateWmsSid(WmsSid *,_SID *,unsigned __int64)
0x1400659df  mov     ebx, eax
0x1400659e1  test    eax, eax
0x1400659e3  js      loc_140065C39
0x1400659e9  mov     eax, [rdi+r14]
0x1400659ed  test    eax, eax
0x1400659ef  jz      short loc_140065A30
0x1400659f1  cmp     eax, 1
0x1400659f4  jnz     short loc_140065A67
0x1400659f6  mov     r8d, [rdi+r14+8]; AccessMask
0x1400659fb  mov     r9, r13; pSid
0x1400659fe  mov     edx, [rdi+r14+4]; dwAceRevision
0x140065a03  mov     rcx, r15; pAcl
0x140065a06  call    cs:__imp_AddAccessDeniedAce
0x140065a0c  test    eax, eax
0x140065a0e  jnz     short loc_140065A4E
0x140065a10  call    cs:__imp_GetLastError
0x140065a16  mov     ebx, eax
0x140065a18  test    eax, eax
0x140065a1a  jle     short loc_140065A25
0x140065a1c  movzx   ebx, ax
0x140065a1f  or      ebx, 80070000h
0x140065a25  mov     r13d, 3D1h
0x140065a2b  jmp     loc_14006592A
0x140065a30  mov     r8d, [rdi+r14+8]; AccessMask
0x140065a35  mov     r9, r13; pSid
0x140065a38  mov     edx, [rdi+r14+4]; dwAceRevision
0x140065a3d  mov     rcx, r15; pAcl
0x140065a40  call    cs:__imp_AddAccessAllowedAce
0x140065a46  test    eax, eax
0x140065a48  jz      loc_140065AD9
0x140065a4e  inc     rsi
0x140065a51  cmp     rsi, rbp
0x140065a54  jnb     loc_140065AF9
0x140065a5a  mov     rcx, [rsp+88h+arg_20]
0x140065a62  jmp     loc_1400659BC
0x140065a67  mov     ebx, 80070057h
0x140065a6c  lea     rbp, aCbraex; "CBRAEx"
0x140065a73  lea     rsi, aCreatesecurity_0; "CreateSecurityDescriptor"
0x140065a7a  mov     [rsp+88h+var_60], ebx; int
0x140065a7e  mov     r14d, 3D5h
0x140065a84  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140065a8b  lea     r13, a0; "0"
0x140065a92  mov     r9, rbp; unsigned __int16 *
0x140065a95  mov     r8, rsi; unsigned __int16 *
0x140065a98  mov     [rsp+88h+var_68], r13; unsigned __int16 *
0x140065a9d  mov     edx, r14d; unsigned int
0x140065aa0  mov     rcx, rdi; unsigned __int16 *
0x140065aa3  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140065aa8  call    cs:__imp_IsDebuggerPresent
0x140065aae  test    eax, eax
0x140065ab0  jz      short loc_140065AC3
0x140065ab2  mov     [rsp+88h+var_50], ebx
0x140065ab6  mov     r9d, r14d
0x140065ab9  mov     [rsp+88h+var_58], r13
0x140065abe  jmp     loc_140065980
0x140065ac3  mov     dword ptr [rsp+88h+var_58], ebx
0x140065ac7  mov     r8d, r14d
0x140065aca  mov     qword ptr [rsp+88h+var_60], r13
0x140065acf  mov     [rsp+88h+var_68], rbp
0x140065ad4  jmp     loc_1400658CF
0x140065ad9  call    cs:__imp_GetLastError
0x140065adf  mov     ebx, eax
0x140065ae1  test    eax, eax
0x140065ae3  jle     short loc_140065AEE
0x140065ae5  movzx   ebx, ax
0x140065ae8  or      ebx, 80070000h
0x140065aee  mov     r13d, 3CCh
0x140065af4  jmp     loc_14006592A
0x140065af9  mov     r13, [rsp+88h+var_48]
0x140065afe  mov     rdi, [rsp+88h+pSecurityDescriptor]
0x140065b06  mov     edx, 1; dwRevision
0x140065b0b  mov     rcx, rdi; pSecurityDescriptor
0x140065b0e  call    cs:__imp_InitializeSecurityDescriptor
0x140065b14  test    eax, eax
0x140065b16  jnz     short loc_140065B38
0x140065b18  call    cs:__imp_GetLastError
0x140065b1e  mov     ebx, eax
0x140065b20  test    eax, eax
0x140065b22  jle     short loc_140065B2D
0x140065b24  movzx   ebx, ax
0x140065b27  or      ebx, 80070000h
0x140065b2d  mov     r13d, 3DBh
0x140065b33  jmp     loc_14006592A
0x140065b38  xor     r9d, r9d; bDaclDefaulted
0x140065b3b  mov     r8, r15; pDacl
0x140065b3e  mov     rcx, rdi; pSecurityDescriptor
0x140065b41  lea     edx, [r9+1]; bDaclPresent
0x140065b45  call    cs:__imp_SetSecurityDescriptorDacl
0x140065b4b  test    eax, eax
0x140065b4d  jnz     short loc_140065B6F
0x140065b4f  call    cs:__imp_GetLastError
0x140065b55  mov     ebx, eax
0x140065b57  test    eax, eax
0x140065b59  jle     short loc_140065B64
0x140065b5b  movzx   ebx, ax
0x140065b5e  or      ebx, 80070000h
0x140065b64  mov     r13d, 3DEh
0x140065b6a  jmp     loc_14006592A
0x140065b6f  mov     rax, [rsp+88h+arg_8]
0x140065b77  test    rax, rax
0x140065b7a  jz      short loc_140065BCE
0x140065b7c  lea     rsi, [r15+r13]
0x140065b80  mov     r8d, 44h ; 'D'; unsigned __int64
0x140065b86  mov     rdx, rsi; struct _SID *
0x140065b89  mov     rcx, rax; struct WmsSid *
0x140065b8c  call    ?CreateWmsSid@@YAJPEAUWmsSid@@PEAU_SID@@_K@Z; CreateWmsSid(WmsSid *,_SID *,unsigned __int64)
0x140065b91  mov     ebx, eax
0x140065b93  test    eax, eax
0x140065b95  js      loc_140065C39
0x140065b9b  xor     r8d, r8d; bOwnerDefaulted
0x140065b9e  mov     rdx, rsi; pOwner
0x140065ba1  mov     rcx, rdi; pSecurityDescriptor
0x140065ba4  call    cs:__imp_SetSecurityDescriptorOwner
0x140065baa  test    eax, eax
0x140065bac  jnz     short loc_140065BCE
0x140065bae  call    cs:__imp_GetLastError
0x140065bb4  mov     ebx, eax
0x140065bb6  test    eax, eax
0x140065bb8  jle     short loc_140065BC3
0x140065bba  movzx   ebx, ax
0x140065bbd  or      ebx, 80070000h
0x140065bc3  mov     r13d, 3E7h
0x140065bc9  jmp     loc_14006592A
0x140065bce  mov     rax, [rsp+88h+arg_10]
0x140065bd6  test    rax, rax
0x140065bd9  jz      short loc_140065C2B
0x140065bdb  lea     rsi, [r15+r13]
0x140065bdf  mov     r8d, 44h ; 'D'; unsigned __int64
0x140065be5  lea     rdx, [rsi+44h]; struct _SID *
0x140065be9  mov     rcx, rax; struct WmsSid *
0x140065bec  call    ?CreateWmsSid@@YAJPEAUWmsSid@@PEAU_SID@@_K@Z; CreateWmsSid(WmsSid *,_SID *,unsigned __int64)
0x140065bf1  mov     ebx, eax
0x140065bf3  test    eax, eax
0x140065bf5  js      short loc_140065C39
0x140065bf7  xor     r8d, r8d; bGroupDefaulted
0x140065bfa  lea     rdx, [rsi+44h]; pGroup
0x140065bfe  mov     rcx, rdi; pSecurityDescriptor
0x140065c01  call    cs:__imp_SetSecurityDescriptorGroup
0x140065c07  test    eax, eax
0x140065c09  jnz     short loc_140065C2B
0x140065c0b  call    cs:__imp_GetLastError
0x140065c11  mov     ebx, eax
0x140065c13  test    eax, eax
0x140065c15  jle     short loc_140065C20
0x140065c17  movzx   ebx, ax
0x140065c1a  or      ebx, 80070000h
0x140065c20  mov     r13d, 3F1h
0x140065c26  jmp     loc_14006592A
0x140065c2b  mov     rax, [rsp+88h+arg_30]
0x140065c33  mov     [rax], r15
0x140065c36  xor     r15d, r15d
0x140065c39  mov     rcx, r15; Block
0x140065c3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140065c41  mov     eax, ebx
0x140065c43  mov     rbx, [rsp+88h+arg_0]
0x140065c4b  add     rsp, 50h
0x140065c4f  pop     r15
0x140065c51  pop     r14
0x140065c53  pop     r13
0x140065c55  pop     r12
0x140065c57  pop     rdi
0x140065c58  pop     rsi
0x140065c59  pop     rbp
0x140065c5a  retn
```
