# CreateSecurityDescriptor(ulong,WmsSid *,WmsSid *,WmsAce *,unsigned __int64,_SECURITY_DESCRIPTOR *,void * *)

- ea: `0x140006a88`
- end: `0x140006e1e`
- name: `?CreateSecurityDescriptor@@YAJKPEAUWmsSid@@0PEAUWmsAce@@_KPEAU_SECURITY_DESCRIPTOR@@PEAPEAX@Z`
- size: `918`
- prototype: `__int64 __fastcall(__int64, struct WmsSid *, struct WmsSid *, struct WmsAce *, unsigned __int64, PSECURITY_DESCRIPTOR pSecurityDescriptor, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140006e24`

## callees

- `0x1400011d4`
- `0x140001b34`
- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140006a88`
- `0x140007158`
- `0x14000ae32`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140006dcb`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140006dcb`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140006d8f`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140006d8f`
- `ADVAPI32!AddAccessDeniedAce` at `0x140006c90`
- `ADVAPI32!AddAccessDeniedAce` at `0x140006c90`
- `ADVAPI32!AddAccessAllowedAce` at `0x140006cc9`
- `ADVAPI32!AddAccessAllowedAce` at `0x140006cc9`
- `ADVAPI32!InitializeAcl` at `0x140006b8d`
- `ADVAPI32!InitializeAcl` at `0x140006b8d`
- `KERNEL32!IsDebuggerPresent` at `0x140006b12`
- `KERNEL32!IsDebuggerPresent` at `0x140006bf6`
- `KERNEL32!IsDebuggerPresent` at `0x140006d31`
- `KERNEL32!IsDebuggerPresent` at `0x140006b12`
- `KERNEL32!IsDebuggerPresent` at `0x140006bf6`
- `KERNEL32!IsDebuggerPresent` at `0x140006d31`
- `KERNEL32!GetLastError` at `0x140006b9b`
- `KERNEL32!GetLastError` at `0x140006c9a`
- `KERNEL32!GetLastError` at `0x140006d62`
- `KERNEL32!GetLastError` at `0x140006d99`
- `KERNEL32!GetLastError` at `0x140006dd5`
- `KERNEL32!GetLastError` at `0x140006b9b`
- `KERNEL32!GetLastError` at `0x140006c9a`
- `KERNEL32!GetLastError` at `0x140006d62`
- `KERNEL32!GetLastError` at `0x140006d99`
- `KERNEL32!GetLastError` at `0x140006dd5`

## string_xrefs

- `0x140006aef`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140006bcb`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140006d0d`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140006af6`: `pSDTempBuffer`
- `0x140006adf`: `CreateSecurityDescriptor`
- `0x140006bbb`: `CreateSecurityDescriptor`
- `0x140006cfc`: `CreateSecurityDescriptor`

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
  __int64 v8; // rdi
  struct _ACL *v9; // rax
  struct _ACL *v10; // r15
  signed int WmsSid; // ebx
  signed int LastError; // eax
  unsigned int v13; // r13d
  __int64 v14; // r9
  char *v15; // rcx
  __int64 v16; // rsi
  struct _SID *v17; // r13
  __int64 v18; // rdi
  int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  const unsigned __int16 *v25; // [rsp+30h] [rbp-58h]
  int v26; // [rsp+38h] [rbp-50h]
  char *v27; // [rsp+A0h] [rbp+18h]

  v8 = (unsigned int)(80 * a5 + 8);
  v9 = (struct _ACL *)operator new(v8 + 68 * a5 + 136);
  v10 = v9;
  if ( !v9 )
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
    goto LABEL_43;
  }
  memset_0(v9, 0, 68 * a5);
  if ( !InitializeAcl(v10, 80 * a5 + 8, 2u) )
  {
    LastError = GetLastError();
    WmsSid = LastError;
    if ( LastError > 0 )
      WmsSid = (unsigned __int16)LastError | 0x80070000;
    v13 = 957;
LABEL_11:
    if ( WmsSid >= 0 )
      WmsSid = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v13,
      L"CreateSecurityDescriptor",
      L"CBRAEx",
      L"fSuccess",
      WmsSid);
    if ( IsDebuggerPresent() )
    {
      v26 = WmsSid;
      v14 = v13;
      v25 = L"fSuccess";
LABEL_15:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v14,
        L"CreateSecurityDescriptor",
        L"CBRAEx",
        v25,
        v26);
    }
    else
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v13,
        L"CreateSecurityDescriptor",
        L"CBRAEx",
        L"fSuccess",
        WmsSid);
    }
    goto LABEL_43;
  }
  WmsSid = 0;
  v15 = (char *)v10 + v8;
  v16 = 0;
  v27 = (char *)v10 + v8;
  if ( !a5 )
  {
LABEL_34:
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v10, 0) )
      {
        *a7 = v10;
        v10 = 0;
        goto LABEL_43;
      }
      v23 = GetLastError();
      WmsSid = v23;
      if ( v23 > 0 )
        WmsSid = (unsigned __int16)v23 | 0x80070000;
      v13 = 990;
    }
    else
    {
      v22 = GetLastError();
      WmsSid = v22;
      if ( v22 > 0 )
        WmsSid = (unsigned __int16)v22 | 0x80070000;
      v13 = 987;
    }
    goto LABEL_11;
  }
  while ( 1 )
  {
    v17 = (struct _SID *)&v15[68 * v16];
    v18 = 32 * v16;
    WmsSid = CreateWmsSid((struct WmsAce *)((char *)a4 + 32 * v16 + 16), v17, 0x44u);
    if ( WmsSid < 0 )
      break;
    v19 = *(_DWORD *)((char *)a4 + v18);
    if ( v19 )
    {
      if ( v19 != 1 )
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
          v26 = -2147024809;
          v14 = 981;
          v25 = L"0";
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
      if ( !AddAccessDeniedAce(v10, *(_DWORD *)((char *)a4 + v18 + 4), *(_DWORD *)((char *)a4 + v18 + 8), v17) )
      {
        v20 = GetLastError();
        WmsSid = v20;
        if ( v20 > 0 )
          WmsSid = (unsigned __int16)v20 | 0x80070000;
        v13 = 977;
        goto LABEL_11;
      }
    }
    else if ( !AddAccessAllowedAce(v10, *(_DWORD *)((char *)a4 + v18 + 4), *(_DWORD *)((char *)a4 + v18 + 8), v17) )
    {
      v21 = GetLastError();
      WmsSid = v21;
      if ( v21 > 0 )
        WmsSid = (unsigned __int16)v21 | 0x80070000;
      v13 = 972;
      goto LABEL_11;
    }
    if ( ++v16 >= a5 )
      goto LABEL_34;
    v15 = v27;
  }
LABEL_43:
  operator delete(v10);
  return (unsigned int)WmsSid;
}

```

## disassembly

```asm
0x140006a88  mov     [rsp+arg_10], r8
0x140006a8d  push    rbx
0x140006a8e  push    rbp
0x140006a8f  push    rsi
0x140006a90  push    rdi
0x140006a91  push    r12
0x140006a93  push    r13
0x140006a95  push    r14
0x140006a97  push    r15
0x140006a99  sub     rsp, 48h
0x140006a9d  mov     r14, [rsp+88h+arg_20]
0x140006aa5  mov     rbp, r9
0x140006aa8  imul    rsi, r14, 44h ; 'D'
0x140006aac  lea     ebx, [r14+r14*4]
0x140006ab0  shl     ebx, 4
0x140006ab3  add     ebx, 8
0x140006ab6  mov     edi, ebx
0x140006ab8  lea     rcx, [rsi+88h]
0x140006abf  add     rcx, rdi; Size
0x140006ac2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006ac7  mov     r15, rax
0x140006aca  test    rax, rax
0x140006acd  jnz     loc_140006B72
0x140006ad3  mov     ebx, 8007000Eh
0x140006ad8  lea     r12, aCpr; "CPR"
0x140006adf  lea     rsi, aCreatesecurity; "CreateSecurityDescriptor"
0x140006ae6  mov     [rsp+88h+var_60], ebx; int
0x140006aea  mov     ebp, 3AFh
0x140006aef  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140006af6  lea     r14, aPsdtempbuffer; "pSDTempBuffer"
0x140006afd  mov     r9, r12; unsigned __int16 *
0x140006b00  mov     r8, rsi; unsigned __int16 *
0x140006b03  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x140006b08  mov     edx, ebp; unsigned int
0x140006b0a  mov     rcx, rdi; unsigned __int16 *
0x140006b0d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140006b12  call    cs:__imp_IsDebuggerPresent
0x140006b18  test    eax, eax
0x140006b1a  jz      short loc_140006B4A
0x140006b1c  mov     [rsp+88h+var_50], ebx
0x140006b20  lea     ecx, [r15+2]; unsigned __int8
0x140006b24  mov     [rsp+88h+var_58], r14
0x140006b29  mov     r9d, ebp
0x140006b2c  mov     qword ptr [rsp+88h+var_60], r12
0x140006b31  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140006b38  mov     [rsp+88h+var_68], rsi
0x140006b3d  mov     r8, rdi
0x140006b40  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140006b45  jmp     loc_140006E03
0x140006b4a  mov     dword ptr [rsp+88h+var_58], ebx
0x140006b4e  mov     r8d, ebp
0x140006b51  mov     qword ptr [rsp+88h+var_60], r14
0x140006b56  mov     [rsp+88h+var_68], r12
0x140006b5b  mov     r9, rsi
0x140006b5e  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140006b65  mov     rdx, rdi
0x140006b68  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140006b6d  jmp     loc_140006E03
0x140006b72  mov     r8, rsi; Size
0x140006b75  xor     edx, edx; Val
0x140006b77  mov     rcx, r15; void *
0x140006b7a  call    memset_0
0x140006b7f  mov     r12d, 2
0x140006b85  mov     edx, ebx; nAclLength
0x140006b87  mov     r8d, r12d; dwAclRevision
0x140006b8a  mov     rcx, r15; pAcl
0x140006b8d  call    cs:__imp_InitializeAcl
0x140006b93  test    eax, eax
0x140006b95  jnz     loc_140006C2F
0x140006b9b  call    cs:__imp_GetLastError
0x140006ba1  mov     ebx, eax
0x140006ba3  test    eax, eax
0x140006ba5  jle     short loc_140006BB0
0x140006ba7  movzx   ebx, ax
0x140006baa  or      ebx, 80070000h
0x140006bb0  mov     r13d, 3BDh
0x140006bb6  mov     eax, 80004005h
0x140006bbb  lea     rsi, aCreatesecurity; "CreateSecurityDescriptor"
0x140006bc2  test    ebx, ebx
0x140006bc4  lea     rbp, aCbraex; "CBRAEx"
0x140006bcb  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140006bd2  mov     r8, rsi; unsigned __int16 *
0x140006bd5  cmovns  ebx, eax
0x140006bd8  lea     r14, aFsuccess; "fSuccess"
0x140006bdf  mov     [rsp+88h+var_60], ebx; int
0x140006be3  mov     r9, rbp; unsigned __int16 *
0x140006be6  mov     edx, r13d; unsigned int
0x140006be9  mov     [rsp+88h+var_68], r14; unsigned __int16 *
0x140006bee  mov     rcx, rdi; unsigned __int16 *
0x140006bf1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140006bf6  call    cs:__imp_IsDebuggerPresent
0x140006bfc  test    eax, eax
0x140006bfe  jz      short loc_140006C19
0x140006c00  mov     [rsp+88h+var_50], ebx
0x140006c04  mov     r9d, r13d
0x140006c07  mov     [rsp+88h+var_58], r14
0x140006c0c  mov     qword ptr [rsp+88h+var_60], rbp
0x140006c11  mov     ecx, r12d
0x140006c14  jmp     loc_140006B31
0x140006c19  mov     dword ptr [rsp+88h+var_58], ebx
0x140006c1d  mov     r8d, r13d
0x140006c20  mov     qword ptr [rsp+88h+var_60], r14
0x140006c25  mov     [rsp+88h+var_68], rbp
0x140006c2a  jmp     loc_140006B5B
0x140006c2f  xor     ebx, ebx
0x140006c31  lea     rcx, [rdi+r15]
0x140006c35  xor     esi, esi
0x140006c37  mov     [rsp+88h+arg_10], rcx
0x140006c3f  test    r14, r14
0x140006c42  jz      loc_140006D82
0x140006c48  imul    r13, rsi, 44h ; 'D'
0x140006c4c  mov     rdi, rsi
0x140006c4f  mov     r8d, 44h ; 'D'; unsigned __int64
0x140006c55  add     r13, rcx
0x140006c58  shl     rdi, 5
0x140006c5c  lea     rcx, [rbp+10h]
0x140006c60  mov     rdx, r13; struct _SID *
0x140006c63  add     rcx, rdi; struct WmsSid *
0x140006c66  call    ?CreateWmsSid@@YAJPEAUWmsSid@@PEAU_SID@@_K@Z; CreateWmsSid(WmsSid *,_SID *,unsigned __int64)
0x140006c6b  mov     ebx, eax
0x140006c6d  test    eax, eax
0x140006c6f  js      loc_140006E03
0x140006c75  mov     eax, [rdi+rbp]
0x140006c78  test    eax, eax
0x140006c7a  jz      short loc_140006CBA
0x140006c7c  cmp     eax, 1
0x140006c7f  jnz     short loc_140006CF0
0x140006c81  mov     r8d, [rdi+rbp+8]; AccessMask
0x140006c86  mov     r9, r13; pSid
0x140006c89  mov     edx, [rdi+rbp+4]; dwAceRevision
0x140006c8d  mov     rcx, r15; pAcl
0x140006c90  call    cs:__imp_AddAccessDeniedAce
0x140006c96  test    eax, eax
0x140006c98  jnz     short loc_140006CD7
0x140006c9a  call    cs:__imp_GetLastError
0x140006ca0  mov     ebx, eax
0x140006ca2  test    eax, eax
0x140006ca4  jle     short loc_140006CAF
0x140006ca6  movzx   ebx, ax
0x140006ca9  or      ebx, 80070000h
0x140006caf  mov     r13d, 3D1h
0x140006cb5  jmp     loc_140006BB6
0x140006cba  mov     r8d, [rdi+rbp+8]; AccessMask
0x140006cbf  mov     r9, r13; pSid
0x140006cc2  mov     edx, [rdi+rbp+4]; dwAceRevision
0x140006cc6  mov     rcx, r15; pAcl
0x140006cc9  call    cs:__imp_AddAccessAllowedAce
0x140006ccf  test    eax, eax
0x140006cd1  jz      loc_140006D62
0x140006cd7  inc     rsi
0x140006cda  cmp     rsi, r14
0x140006cdd  jnb     loc_140006D82
0x140006ce3  mov     rcx, [rsp+88h+arg_10]
0x140006ceb  jmp     loc_140006C48
0x140006cf0  mov     ebx, 80070057h
0x140006cf5  lea     rbp, aCbraex; "CBRAEx"
0x140006cfc  lea     rsi, aCreatesecurity; "CreateSecurityDescriptor"
0x140006d03  mov     [rsp+88h+var_60], ebx; int
0x140006d07  mov     r14d, 3D5h
0x140006d0d  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140006d14  lea     r13, a0; "0"
0x140006d1b  mov     r9, rbp; unsigned __int16 *
0x140006d1e  mov     r8, rsi; unsigned __int16 *
0x140006d21  mov     [rsp+88h+var_68], r13; unsigned __int16 *
0x140006d26  mov     edx, r14d; unsigned int
0x140006d29  mov     rcx, rdi; unsigned __int16 *
0x140006d2c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140006d31  call    cs:__imp_IsDebuggerPresent
0x140006d37  test    eax, eax
0x140006d39  jz      short loc_140006D4C
0x140006d3b  mov     [rsp+88h+var_50], ebx
0x140006d3f  mov     r9d, r14d
0x140006d42  mov     [rsp+88h+var_58], r13
0x140006d47  jmp     loc_140006C0C
0x140006d4c  mov     dword ptr [rsp+88h+var_58], ebx
0x140006d50  mov     r8d, r14d
0x140006d53  mov     qword ptr [rsp+88h+var_60], r13
0x140006d58  mov     [rsp+88h+var_68], rbp
0x140006d5d  jmp     loc_140006B5B
0x140006d62  call    cs:__imp_GetLastError
0x140006d68  mov     ebx, eax
0x140006d6a  test    eax, eax
0x140006d6c  jle     short loc_140006D77
0x140006d6e  movzx   ebx, ax
0x140006d71  or      ebx, 80070000h
0x140006d77  mov     r13d, 3CCh
0x140006d7d  jmp     loc_140006BB6
0x140006d82  mov     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x140006d8a  mov     edx, 1; dwRevision
0x140006d8f  call    cs:__imp_InitializeSecurityDescriptor
0x140006d95  test    eax, eax
0x140006d97  jnz     short loc_140006DB9
0x140006d99  call    cs:__imp_GetLastError
0x140006d9f  mov     ebx, eax
0x140006da1  test    eax, eax
0x140006da3  jle     short loc_140006DAE
0x140006da5  movzx   ebx, ax
0x140006da8  or      ebx, 80070000h
0x140006dae  mov     r13d, 3DBh
0x140006db4  jmp     loc_140006BB6
0x140006db9  mov     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x140006dc1  xor     r9d, r9d; bDaclDefaulted
0x140006dc4  mov     r8, r15; pDacl
0x140006dc7  lea     edx, [r9+1]; bDaclPresent
0x140006dcb  call    cs:__imp_SetSecurityDescriptorDacl
0x140006dd1  test    eax, eax
0x140006dd3  jnz     short loc_140006DF5
0x140006dd5  call    cs:__imp_GetLastError
0x140006ddb  mov     ebx, eax
0x140006ddd  test    eax, eax
0x140006ddf  jle     short loc_140006DEA
0x140006de1  movzx   ebx, ax
0x140006de4  or      ebx, 80070000h
0x140006dea  mov     r13d, 3DEh
0x140006df0  jmp     loc_140006BB6
0x140006df5  mov     rax, [rsp+88h+arg_30]
0x140006dfd  mov     [rax], r15
0x140006e00  xor     r15d, r15d
0x140006e03  mov     rcx, r15; Block
0x140006e06  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140006e0b  mov     eax, ebx
0x140006e0d  add     rsp, 48h
0x140006e11  pop     r15
0x140006e13  pop     r14
0x140006e15  pop     r13
0x140006e17  pop     r12
0x140006e19  pop     rdi
0x140006e1a  pop     rsi
0x140006e1b  pop     rbp
0x140006e1c  pop     rbx
0x140006e1d  retn
```
