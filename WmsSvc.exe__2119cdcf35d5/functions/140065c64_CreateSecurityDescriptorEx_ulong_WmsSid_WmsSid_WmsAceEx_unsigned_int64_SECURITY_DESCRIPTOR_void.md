# CreateSecurityDescriptorEx(ulong,WmsSid *,WmsSid *,WmsAceEx *,unsigned __int64,_SECURITY_DESCRIPTOR *,void * *)

- ea: `0x140065c64`
- end: `0x140065fd3`
- name: `?CreateSecurityDescriptorEx@@YAJKPEAUWmsSid@@0PEAUWmsAceEx@@_KPEAU_SECURITY_DESCRIPTOR@@PEAPEAX@Z`
- size: `879`
- prototype: `__int64 __fastcall(__int64, struct WmsSid *, struct WmsSid *, struct WmsAceEx *, unsigned __int64, PSECURITY_DESCRIPTOR pSecurityDescriptor, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140076488`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140065c64`
- `0x140066310`
- `0x14007cb9e`

## import_xrefs

- `ADVAPI32!AddAccessDeniedAceEx` at `0x140065dc2`
- `ADVAPI32!AddAccessDeniedAceEx` at `0x140065dc2`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x140065e03`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x140065e03`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140065ee0`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140065ee0`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140065e2b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140065e2b`
- `ADVAPI32!InitializeAcl` at `0x140065d39`
- `ADVAPI32!InitializeAcl` at `0x140065d39`
- `KERNEL32!GetLastError` at `0x140065d43`
- `KERNEL32!GetLastError` at `0x140065dcc`
- `KERNEL32!GetLastError` at `0x140065e39`
- `KERNEL32!GetLastError` at `0x140065eea`
- `KERNEL32!GetLastError` at `0x140065f1a`
- `KERNEL32!GetLastError` at `0x140065d43`
- `KERNEL32!GetLastError` at `0x140065dcc`
- `KERNEL32!GetLastError` at `0x140065e39`
- `KERNEL32!GetLastError` at `0x140065eea`
- `KERNEL32!GetLastError` at `0x140065f1a`
- `KERNEL32!IsDebuggerPresent` at `0x140065cca`
- `KERNEL32!IsDebuggerPresent` at `0x140065e98`
- `KERNEL32!IsDebuggerPresent` at `0x140065f75`
- `KERNEL32!IsDebuggerPresent` at `0x140065cca`
- `KERNEL32!IsDebuggerPresent` at `0x140065e98`
- `KERNEL32!IsDebuggerPresent` at `0x140065f75`

## string_xrefs

- `0x140065ca7`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140065e75`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140065f4a`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140065cae`: `pSDTempBuffer`
- `0x140065c97`: `CreateSecurityDescriptorEx`
- `0x140065e65`: `CreateSecurityDescriptorEx`
- `0x140065f43`: `CreateSecurityDescriptorEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateSecurityDescriptorEx(
        __int64 a1,
        struct WmsSid *a2,
        struct WmsSid *a3,
        struct WmsAceEx *a4,
        unsigned __int64 a5,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        void **a7)
{
  struct _ACL *v7; // rax
  struct _ACL *v8; // r15
  int WmsSid; // ebx
  unsigned int v10; // ebp
  __int64 v11; // r9
  __int64 v12; // r8
  signed int LastError; // eax
  unsigned int v14; // r13d
  __int64 v15; // rsi
  __int64 v16; // rdi
  int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  const unsigned __int16 *pSid; // [rsp+20h] [rbp-68h]
  const unsigned __int16 *v24; // [rsp+28h] [rbp-60h]
  const unsigned __int16 *v25; // [rsp+28h] [rbp-60h]
  const unsigned __int16 *v26; // [rsp+30h] [rbp-58h]
  int v27; // [rsp+30h] [rbp-58h]
  int v28; // [rsp+38h] [rbp-50h]

  v7 = (struct _ACL *)operator new(0x124u);
  v8 = v7;
  if ( !v7 )
  {
    WmsSid = -2147024882;
    v10 = 1064;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x428u,
      L"CreateSecurityDescriptorEx",
      L"CPR",
      L"pSDTempBuffer",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      v28 = -2147024882;
      v26 = L"pSDTempBuffer";
      v11 = 1064;
      v24 = L"CPR";
LABEL_4:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v11,
        L"CreateSecurityDescriptorEx",
        v24,
        v26,
        v28);
      goto LABEL_42;
    }
    v27 = -2147024882;
    v25 = L"pSDTempBuffer";
    pSid = L"CPR";
LABEL_6:
    v12 = v10;
    goto LABEL_41;
  }
  memset_0(v7, 0, 0x44u);
  if ( !InitializeAcl(v8, 0x58u, 2u) )
  {
    LastError = GetLastError();
    WmsSid = LastError;
    if ( LastError > 0 )
      WmsSid = (unsigned __int16)LastError | 0x80070000;
    v14 = 1078;
LABEL_36:
    if ( WmsSid >= 0 )
      WmsSid = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v14,
      L"CreateSecurityDescriptorEx",
      L"CBRAEx",
      L"fSuccess",
      WmsSid);
    if ( IsDebuggerPresent() )
    {
      v28 = WmsSid;
      v11 = v14;
      v26 = L"fSuccess";
      v24 = L"CBRAEx";
      goto LABEL_4;
    }
    v27 = WmsSid;
    v12 = v14;
    v25 = L"fSuccess";
    pSid = L"CBRAEx";
LABEL_41:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v12,
      L"CreateSecurityDescriptorEx",
      pSid,
      v25,
      v27);
    goto LABEL_42;
  }
  v15 = 0;
  while ( 1 )
  {
    v16 = 4 * v15;
    WmsSid = CreateWmsSid((struct WmsSid *)&qword_1400EE7C0[4 * v15 + 2], (struct _SID *)((char *)&v8[11] + 68 * v15));
    if ( WmsSid < 0 )
      break;
    v17 = qword_1400EE7C0[v16];
    if ( v17 )
    {
      if ( v17 != 1 )
      {
        WmsSid = -2147024809;
        v10 = 1102;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          0x44Eu,
          L"CreateSecurityDescriptorEx",
          L"CHRA",
          L"((HRESULT)0x80070057L)",
          -2147024809);
        if ( IsDebuggerPresent() )
        {
          v28 = -2147024809;
          v11 = 1102;
          v26 = L"((HRESULT)0x80070057L)";
          v24 = L"CHRA";
          goto LABEL_4;
        }
        v27 = -2147024809;
        v25 = L"((HRESULT)0x80070057L)";
        pSid = L"CHRA";
        goto LABEL_6;
      }
      if ( !AddAccessDeniedAceEx(
              v8,
              HIDWORD(qword_1400EE7C0[v16]),
              qword_1400EE7C0[v16 + 1],
              HIDWORD(qword_1400EE7C0[v16 + 1]),
              (char *)&v8[11] + 68 * v15) )
      {
        v18 = GetLastError();
        WmsSid = v18;
        if ( v18 > 0 )
          WmsSid = (unsigned __int16)v18 | 0x80070000;
        v14 = 1098;
        goto LABEL_36;
      }
    }
    else if ( !AddAccessAllowedAceEx(
                 v8,
                 HIDWORD(qword_1400EE7C0[v16]),
                 qword_1400EE7C0[v16 + 1],
                 HIDWORD(qword_1400EE7C0[v16 + 1]),
                 (char *)&v8[11] + 68 * v15) )
    {
      v21 = GetLastError();
      WmsSid = v21;
      if ( v21 > 0 )
        WmsSid = (unsigned __int16)v21 | 0x80070000;
      v14 = 1093;
      goto LABEL_36;
    }
    if ( ++v15 )
    {
      if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
      {
        if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v8, 0) )
        {
          *a7 = v8;
          v8 = 0;
          break;
        }
        v20 = GetLastError();
        WmsSid = v20;
        if ( v20 > 0 )
          WmsSid = (unsigned __int16)v20 | 0x80070000;
        v14 = 1111;
      }
      else
      {
        v19 = GetLastError();
        WmsSid = v19;
        if ( v19 > 0 )
          WmsSid = (unsigned __int16)v19 | 0x80070000;
        v14 = 1108;
      }
      goto LABEL_36;
    }
  }
LABEL_42:
  operator delete(v8);
  return (unsigned int)WmsSid;
}

```

## disassembly

```asm
0x140065c64  push    rbx
0x140065c66  push    rbp
0x140065c67  push    rsi
0x140065c68  push    rdi
0x140065c69  push    r12
0x140065c6b  push    r13
0x140065c6d  push    r14
0x140065c6f  push    r15
0x140065c71  sub     rsp, 48h
0x140065c75  mov     ecx, 124h; Size
0x140065c7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140065c7f  mov     r15, rax
0x140065c82  test    rax, rax
0x140065c85  jnz     loc_140065D18
0x140065c8b  mov     ebx, 8007000Eh
0x140065c90  lea     r12, aCpr; "CPR"
0x140065c97  lea     rsi, aCreatesecurity; "CreateSecurityDescriptorEx"
0x140065c9e  mov     [rsp+88h+var_60], ebx; int
0x140065ca2  mov     ebp, 428h
0x140065ca7  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140065cae  lea     r14, aPsdtempbuffer; "pSDTempBuffer"
0x140065cb5  mov     r9, r12; unsigned __int16 *
0x140065cb8  mov     r8, rsi; unsigned __int16 *
0x140065cbb  mov     [rsp+88h+pSid], r14; unsigned __int16 *
0x140065cc0  mov     edx, ebp; unsigned int
0x140065cc2  mov     rcx, rdi; unsigned __int16 *
0x140065cc5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140065cca  call    cs:__imp_IsDebuggerPresent
0x140065cd0  test    eax, eax
0x140065cd2  jz      short loc_140065D02
0x140065cd4  mov     [rsp+88h+var_50], ebx
0x140065cd8  lea     ecx, [r15+2]; unsigned __int8
0x140065cdc  mov     [rsp+88h+var_58], r14
0x140065ce1  mov     r9d, ebp
0x140065ce4  mov     qword ptr [rsp+88h+var_60], r12
0x140065ce9  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140065cf0  mov     [rsp+88h+pSid], rsi
0x140065cf5  mov     r8, rdi
0x140065cf8  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140065cfd  jmp     loc_140065FB8
0x140065d02  mov     dword ptr [rsp+88h+var_58], ebx
0x140065d06  mov     qword ptr [rsp+88h+var_60], r14
0x140065d0b  mov     [rsp+88h+pSid], r12
0x140065d10  mov     r8d, ebp
0x140065d13  jmp     loc_140065FA6
0x140065d18  mov     r13d, 44h ; 'D'
0x140065d1e  xor     edx, edx; Val
0x140065d20  mov     r8d, r13d; Size
0x140065d23  mov     rcx, r15; void *
0x140065d26  call    memset_0
0x140065d2b  lea     r12d, [r13-42h]
0x140065d2f  mov     rcx, r15; pAcl
0x140065d32  mov     r8d, r12d; dwAclRevision
0x140065d35  lea     edx, [r13+14h]; nAclLength
0x140065d39  call    cs:__imp_InitializeAcl
0x140065d3f  test    eax, eax
0x140065d41  jnz     short loc_140065D63
0x140065d43  call    cs:__imp_GetLastError
0x140065d49  mov     ebx, eax
0x140065d4b  test    eax, eax
0x140065d4d  jle     short loc_140065D58
0x140065d4f  movzx   ebx, ax
0x140065d52  or      ebx, 80070000h
0x140065d58  mov     r13d, 436h
0x140065d5e  jmp     loc_140065F35
0x140065d63  xor     esi, esi
0x140065d65  lea     r14, qword_1400EE7C0
0x140065d6c  imul    rbp, rsi, 44h ; 'D'
0x140065d70  mov     rdi, rsi
0x140065d73  lea     rcx, [r14+10h]
0x140065d77  add     rbp, 58h ; 'X'
0x140065d7b  shl     rdi, 5
0x140065d7f  add     rbp, r15
0x140065d82  add     rcx, rdi; struct WmsSid *
0x140065d85  mov     rdx, rbp; struct _SID *
0x140065d88  mov     r8, r13; unsigned __int64
0x140065d8b  call    ?CreateWmsSid@@YAJPEAUWmsSid@@PEAU_SID@@_K@Z; CreateWmsSid(WmsSid *,_SID *,unsigned __int64)
0x140065d90  mov     ebx, eax
0x140065d92  test    eax, eax
0x140065d94  js      loc_140065FB8
0x140065d9a  mov     eax, [rdi+r14]
0x140065d9e  test    eax, eax
0x140065da0  jz      short loc_140065DEC
0x140065da2  cmp     eax, 1
0x140065da5  jnz     loc_140065E59
0x140065dab  mov     r9d, [rdi+r14+0Ch]; AccessMask
0x140065db0  mov     rcx, r15; pAcl
0x140065db3  mov     r8d, [rdi+r14+8]; AceFlags
0x140065db8  mov     edx, [rdi+r14+4]; dwAceRevision
0x140065dbd  mov     [rsp+88h+pSid], rbp; pSid
0x140065dc2  call    cs:__imp_AddAccessDeniedAceEx
0x140065dc8  test    eax, eax
0x140065dca  jnz     short loc_140065E11
0x140065dcc  call    cs:__imp_GetLastError
0x140065dd2  mov     ebx, eax
0x140065dd4  test    eax, eax
0x140065dd6  jle     short loc_140065DE1
0x140065dd8  movzx   ebx, ax
0x140065ddb  or      ebx, 80070000h
0x140065de1  mov     r13d, 44Ah
0x140065de7  jmp     loc_140065F35
0x140065dec  mov     r9d, [rdi+r14+0Ch]; AccessMask
0x140065df1  mov     rcx, r15; pAcl
0x140065df4  mov     r8d, [rdi+r14+8]; AceFlags
0x140065df9  mov     edx, [rdi+r14+4]; dwAceRevision
0x140065dfe  mov     [rsp+88h+pSid], rbp; pSid
0x140065e03  call    cs:__imp_AddAccessAllowedAceEx
0x140065e09  test    eax, eax
0x140065e0b  jz      loc_140065F1A
0x140065e11  inc     rsi
0x140065e14  cmp     rsi, 1
0x140065e18  jb      loc_140065D6C
0x140065e1e  mov     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x140065e26  mov     edx, 1; dwRevision
0x140065e2b  call    cs:__imp_InitializeSecurityDescriptor
0x140065e31  test    eax, eax
0x140065e33  jnz     loc_140065ECE
0x140065e39  call    cs:__imp_GetLastError
0x140065e3f  mov     ebx, eax
0x140065e41  test    eax, eax
0x140065e43  jle     short loc_140065E4E
0x140065e45  movzx   ebx, ax
0x140065e48  or      ebx, 80070000h
0x140065e4e  mov     r13d, 454h
0x140065e54  jmp     loc_140065F35
0x140065e59  mov     ebx, 80070057h
0x140065e5e  lea     r13, aChra; "CHRA"
0x140065e65  lea     rsi, aCreatesecurity; "CreateSecurityDescriptorEx"
0x140065e6c  mov     [rsp+88h+var_60], ebx; int
0x140065e70  mov     ebp, 44Eh
0x140065e75  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140065e7c  lea     r14, aHresult0x80070; "((HRESULT)0x80070057L)"
0x140065e83  mov     r9, r13; unsigned __int16 *
0x140065e86  mov     r8, rsi; unsigned __int16 *
0x140065e89  mov     [rsp+88h+pSid], r14; unsigned __int16 *
0x140065e8e  mov     edx, ebp; unsigned int
0x140065e90  mov     rcx, rdi; unsigned __int16 *
0x140065e93  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140065e98  call    cs:__imp_IsDebuggerPresent
0x140065e9e  test    eax, eax
0x140065ea0  jz      short loc_140065EBB
0x140065ea2  mov     [rsp+88h+var_50], ebx
0x140065ea6  mov     r9d, ebp
0x140065ea9  mov     [rsp+88h+var_58], r14
0x140065eae  mov     qword ptr [rsp+88h+var_60], r13
0x140065eb3  mov     ecx, r12d
0x140065eb6  jmp     loc_140065CE9
0x140065ebb  mov     dword ptr [rsp+88h+var_58], ebx
0x140065ebf  mov     qword ptr [rsp+88h+var_60], r14
0x140065ec4  mov     [rsp+88h+pSid], r13
0x140065ec9  jmp     loc_140065D10
0x140065ece  mov     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x140065ed6  xor     r9d, r9d; bDaclDefaulted
0x140065ed9  mov     r8, r15; pDacl
0x140065edc  lea     edx, [r9+1]; bDaclPresent
0x140065ee0  call    cs:__imp_SetSecurityDescriptorDacl
0x140065ee6  test    eax, eax
0x140065ee8  jnz     short loc_140065F07
0x140065eea  call    cs:__imp_GetLastError
0x140065ef0  mov     ebx, eax
0x140065ef2  test    eax, eax
0x140065ef4  jle     short loc_140065EFF
0x140065ef6  movzx   ebx, ax
0x140065ef9  or      ebx, 80070000h
0x140065eff  mov     r13d, 457h
0x140065f05  jmp     short loc_140065F35
0x140065f07  mov     rax, [rsp+88h+arg_30]
0x140065f0f  mov     [rax], r15
0x140065f12  xor     r15d, r15d
0x140065f15  jmp     loc_140065FB8
0x140065f1a  call    cs:__imp_GetLastError
0x140065f20  mov     ebx, eax
0x140065f22  test    eax, eax
0x140065f24  jle     short loc_140065F2F
0x140065f26  movzx   ebx, ax
0x140065f29  or      ebx, 80070000h
0x140065f2f  mov     r13d, 445h
0x140065f35  mov     eax, 80004005h
0x140065f3a  lea     r14, aCbraex; "CBRAEx"
0x140065f41  test    ebx, ebx
0x140065f43  lea     rsi, aCreatesecurity; "CreateSecurityDescriptorEx"
0x140065f4a  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140065f51  mov     r9, r14; unsigned __int16 *
0x140065f54  cmovns  ebx, eax
0x140065f57  lea     rbp, aFsuccess; "fSuccess"
0x140065f5e  mov     [rsp+88h+var_60], ebx; int
0x140065f62  mov     r8, rsi; unsigned __int16 *
0x140065f65  mov     edx, r13d; unsigned int
0x140065f68  mov     [rsp+88h+pSid], rbp; unsigned __int16 *
0x140065f6d  mov     rcx, rdi; unsigned __int16 *
0x140065f70  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140065f75  call    cs:__imp_IsDebuggerPresent
0x140065f7b  test    eax, eax
0x140065f7d  jz      short loc_140065F95
0x140065f7f  mov     [rsp+88h+var_50], ebx
0x140065f83  mov     r9d, r13d
0x140065f86  mov     [rsp+88h+var_58], rbp
0x140065f8b  mov     qword ptr [rsp+88h+var_60], r14
0x140065f90  jmp     loc_140065EB3
0x140065f95  mov     dword ptr [rsp+88h+var_58], ebx
0x140065f99  mov     r8d, r13d
0x140065f9c  mov     qword ptr [rsp+88h+var_60], rbp
0x140065fa1  mov     [rsp+88h+pSid], r14
0x140065fa6  mov     r9, rsi
0x140065fa9  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140065fb0  mov     rdx, rdi
0x140065fb3  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140065fb8  mov     rcx, r15; Block
0x140065fbb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140065fc0  mov     eax, ebx
0x140065fc2  add     rsp, 48h
0x140065fc6  pop     r15
0x140065fc8  pop     r14
0x140065fca  pop     r13
0x140065fcc  pop     r12
0x140065fce  pop     rdi
0x140065fcf  pop     rsi
0x140065fd0  pop     rbp
0x140065fd1  pop     rbx
0x140065fd2  retn
```
