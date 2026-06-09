# Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::VerifySecured(void *,ushort const *)

- ea: `0x18002da4c`
- end: `0x18002de3c`
- name: `?VerifySecured@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@SAJPEAXPEBG@Z`
- size: `1008`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *String1)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003d54`

## callees

- `0x18002d780`
- `0x18002da4c`
- `0x18002f0fc`
- `0x18002fc38`
- `0x180030650`
- `0x18003070c`
- `0x180031094`
- `0x18003153c`
- `0x1800315c8`
- `0x1800316c4`
- `0x180049b50`
- `0x18004ad26`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002db2c`
- `KERNEL32!LocalFree` at `0x18002db2c`
- `KERNEL32!SetLastError` at `0x18002db04`
- `KERNEL32!SetLastError` at `0x18002db04`
- `ADVAPI32!IsValidSid` at `0x18002db42`
- `ADVAPI32!IsValidSid` at `0x18002db5e`
- `ADVAPI32!IsValidSid` at `0x18002dcde`
- `ADVAPI32!IsValidSid` at `0x18002dcfa`
- `ADVAPI32!IsValidSid` at `0x18002dd2b`
- `ADVAPI32!IsValidSid` at `0x18002dd47`
- `ADVAPI32!IsValidSid` at `0x18002db42`
- `ADVAPI32!IsValidSid` at `0x18002db5e`
- `ADVAPI32!IsValidSid` at `0x18002dcde`
- `ADVAPI32!IsValidSid` at `0x18002dcfa`
- `ADVAPI32!IsValidSid` at `0x18002dd2b`
- `ADVAPI32!IsValidSid` at `0x18002dd47`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18002daf8`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18002daf8`
- `ADVAPI32!EqualSid` at `0x18002db77`
- `ADVAPI32!EqualSid` at `0x18002dd11`
- `ADVAPI32!EqualSid` at `0x18002dd60`
- `ADVAPI32!EqualSid` at `0x18002db77`
- `ADVAPI32!EqualSid` at `0x18002dd11`
- `ADVAPI32!EqualSid` at `0x18002dd60`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::VerifySecured(
        HANDLE hFile,
        wchar_t *String1)
{
  unsigned int v3; // esi
  __int64 result; // rax
  DWORD NamedSecurityInfoW; // eax
  enum _SE_OBJECT_TYPE v6; // edx
  unsigned int i; // edi
  __int64 v9; // rbx
  int v10; // r14d
  int v11; // esi
  bool v12; // bl
  _BYTE v13[8]; // [rsp+50h] [rbp-208h] BYREF
  _BYTE pSid1[120]; // [rsp+58h] [rbp-200h] BYREF
  PSID ppsidOwner; // [rsp+D0h] [rbp-188h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+D8h] [rbp-180h] BYREF
  _QWORD v17[3]; // [rsp+E0h] [rbp-178h] BYREF
  __int128 v18; // [rsp+F8h] [rbp-160h]
  __int64 v19; // [rsp+108h] [rbp-150h]
  __int64 v20; // [rsp+110h] [rbp-148h]
  _BYTE v21[8]; // [rsp+120h] [rbp-138h] BYREF
  _BYTE pSid2[68]; // [rsp+128h] [rbp-130h] BYREF
  char v23; // [rsp+16Ch] [rbp-ECh]
  _BYTE v24[8]; // [rsp+1A0h] [rbp-B8h] BYREF
  _BYTE pSid[120]; // [rsp+1A8h] [rbp-B0h] BYREF

  v3 = 0;
  LODWORD(ppsidOwner) = 0;
  result = anonymous_namespace_::ValidateSamePath_1(String1, hFile);
  if ( !(_DWORD)result )
  {
    std::call_once<void (&)(void),>();
    memset_0(v24, 0, 0x78u);
    ATL::CSid::CSid((ATL::CSid *)v24);
    if ( !String1 )
    {
LABEL_34:
      ATL::CSid::~CSid((ATL::CSid *)v24);
      return 2147549183LL;
    }
    NamedSecurityInfoW = GetNamedSecurityInfoW(String1, SE_FILE_OBJECT, 1u, &ppsidOwner, 0, 0, 0, &hMem);
    if ( NamedSecurityInfoW )
    {
      SetLastError(NamedSecurityInfoW);
      goto LABEL_34;
    }
    ATL::CSid::operator=(v24, ppsidOwner);
    LocalFree(hMem);
    if ( !byte_1800770BC
      || !IsValidSid(qword_180077078)
      || !pSid[68]
      || !IsValidSid(pSid)
      || !EqualSid(qword_180077078, pSid) )
    {
      ATL::CSid::~CSid((ATL::CSid *)v24);
      return 1;
    }
    else
    {
      v17[1] = 0;
      v17[2] = 0x200000000LL;
      v17[0] = &ATL::CDacl::`vftable';
      v18 = 0;
      v19 = 0;
      v20 = 0;
      if ( ATL::AtlGetDacl(String1, v6, (struct ATL::CDacl *)v17) )
      {
        for ( i = 0; i < DWORD2(v18); ++i )
        {
          memset_0(v21, 0, 0x78u);
          ATL::CSid::CSid((ATL::CSid *)v21);
          v9 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(v17[0] + 32LL))(v17, i);
          ATL::CSid::operator=(v21, v9 + 8);
          v10 = *(_DWORD *)(v9 + 128);
          ATL::CSid::CSid(
            (ATL::CSid *)v13,
            (const struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority,
            2u);
          v11 = v3 | 3;
          v12 = pSid1[68] && IsValidSid(pSid1) && v23 && IsValidSid(pSid2) && EqualSid(pSid1, pSid2)
             || byte_1800770BC
             && IsValidSid(qword_180077078)
             && v23
             && IsValidSid(pSid2)
             && EqualSid(qword_180077078, pSid2);
          v3 = v11 & 0xFFFFFFFE;
          ATL::CSid::~CSid((ATL::CSid *)v13);
          if ( !v12 && v10 != 1179785 )
          {
            ATL::CSid::~CSid((ATL::CSid *)v21);
            ATL::CDacl::~CDacl((ATL::CDacl *)v17);
            ATL::CSid::~CSid((ATL::CSid *)v24);
            return 1;
          }
          ATL::CSid::~CSid((ATL::CSid *)v21);
        }
        ATL::CDacl::~CDacl((ATL::CDacl *)v17);
        ATL::CSid::~CSid((ATL::CSid *)v24);
        return 0;
      }
      else
      {
        ATL::CDacl::~CDacl((ATL::CDacl *)v17);
        ATL::CSid::~CSid((ATL::CSid *)v24);
        return 2147549183LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002da4c  mov     [rsp+arg_10], rbx
0x18002da51  push    rsi
0x18002da52  push    rdi
0x18002da53  push    r12
0x18002da55  push    r14
0x18002da57  push    r15
0x18002da59  sub     rsp, 230h
0x18002da60  mov     rax, cs:__security_cookie
0x18002da67  xor     rax, rsp
0x18002da6a  mov     [rsp+258h+var_38], rax
0x18002da72  mov     rbx, rdx
0x18002da75  xor     r15d, r15d
0x18002da78  mov     esi, r15d
0x18002da7b  mov     dword ptr [rsp+258h+ppsidOwner], r15d
0x18002da83  mov     rdx, rcx; hFile
0x18002da86  mov     rcx, rbx; String1
0x18002da89  call    _anonymous_namespace___ValidateSamePath_1
0x18002da8e  test    eax, eax
0x18002da90  jnz     loc_18002DE13
0x18002da96  call    ??$call_once@A6AXXZ$$V@std@@YAXAEAUonce_flag@0@A6AXXZ@Z; std::call_once<void (&)(void),>(std::once_flag &,void (&)(void))
0x18002da9b  xor     edx, edx; Val
0x18002da9d  lea     r8d, [rdx+78h]; Size
0x18002daa1  lea     rcx, [rsp+258h+var_B8]; void *
0x18002daa9  call    memset_0
0x18002daae  lea     rcx, [rsp+258h+var_B8]; this
0x18002dab6  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x18002dabb  nop
0x18002dabc  test    rbx, rbx
0x18002dabf  jz      loc_18002DDEE
0x18002dac5  lea     rax, [rsp+258h+hMem]
0x18002dacd  mov     [rsp+258h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002dad2  mov     [rsp+258h+ppSacl], r15; ppSacl
0x18002dad7  mov     [rsp+258h+ppDacl], r15; ppDacl
0x18002dadc  mov     [rsp+258h+ppsidGroup], r15; ppsidGroup
0x18002dae1  lea     r9, [rsp+258h+ppsidOwner]; ppsidOwner
0x18002dae9  mov     r12d, 1
0x18002daef  mov     r8d, r12d; SecurityInfo
0x18002daf2  mov     edx, r12d; ObjectType
0x18002daf5  mov     rcx, rbx; pObjectName
0x18002daf8  call    cs:__imp_GetNamedSecurityInfoW
0x18002dafe  test    eax, eax
0x18002db00  jz      short loc_18002DB0F
0x18002db02  mov     ecx, eax; dwErrCode
0x18002db04  call    cs:__imp_SetLastError
0x18002db0a  jmp     loc_18002DDEE
0x18002db0f  mov     rdx, [rsp+258h+ppsidOwner]
0x18002db17  lea     rcx, [rsp+258h+var_B8]
0x18002db1f  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x18002db24  mov     rcx, [rsp+258h+hMem]; hMem
0x18002db2c  call    cs:__imp_LocalFree
0x18002db32  cmp     cs:byte_1800770BC, r15b
0x18002db39  jz      short loc_18002DB84
0x18002db3b  lea     rcx, qword_180077078; pSid
0x18002db42  call    cs:__imp_IsValidSid
0x18002db48  test    eax, eax
0x18002db4a  jz      short loc_18002DB84
0x18002db4c  cmp     [rsp+258h+var_6C], r15b
0x18002db54  jz      short loc_18002DB84
0x18002db56  lea     rcx, [rsp+258h+pSid]; pSid
0x18002db5e  call    cs:__imp_IsValidSid
0x18002db64  test    eax, eax
0x18002db66  jz      short loc_18002DB84
0x18002db68  lea     rdx, [rsp+258h+pSid]; pSid2
0x18002db70  lea     rcx, qword_180077078; pSid1
0x18002db77  call    cs:__imp_EqualSid
0x18002db7d  test    eax, eax
0x18002db7f  setz    cl
0x18002db82  jmp     short loc_18002DB87
0x18002db84  mov     ecx, r12d
0x18002db87  test    cl, cl
0x18002db89  jz      short loc_18002DBA0
0x18002db8b  lea     rcx, [rsp+258h+var_B8]; this
0x18002db93  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002db98  mov     eax, r12d
0x18002db9b  jmp     loc_18002DE13
0x18002dba0  xorps   xmm0, xmm0
0x18002dba3  xor     eax, eax
0x18002dba5  movups  [rsp+258h+var_178], xmm0
0x18002dbad  movups  [rsp+258h+var_168], xmm0
0x18002dbb5  movups  [rsp+258h+var_158], xmm0
0x18002dbbd  mov     [rsp+258h+var_148], rax
0x18002dbc5  mov     qword ptr [rsp+258h+var_178+8], r15
0x18002dbcd  mov     byte ptr [rsp+258h+var_168], r15b
0x18002dbd5  mov     dword ptr [rsp+258h+var_168+4], 2
0x18002dbe0  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x18002dbe7  mov     qword ptr [rsp+258h+var_178], rax
0x18002dbef  movdqu  [rsp+258h+var_168+8], xmm0
0x18002dbf8  mov     qword ptr [rsp+258h+var_158+8], r15
0x18002dc00  mov     dword ptr [rsp+258h+var_148], r15d
0x18002dc08  lea     r8, [rsp+258h+var_178]; struct ATL::CDacl *
0x18002dc10  mov     rcx, rbx; unsigned __int16 *
0x18002dc13  call    ?AtlGetDacl@ATL@@YA_NPEBGW4_SE_OBJECT_TYPE@@PEAVCDacl@1@@Z; ATL::AtlGetDacl(ushort const *,_SE_OBJECT_TYPE,ATL::CDacl *)
0x18002dc18  test    al, al
0x18002dc1a  jnz     short loc_18002DC41
0x18002dc1c  lea     rcx, [rsp+258h+var_178]; this
0x18002dc24  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x18002dc29  nop
0x18002dc2a  lea     rcx, [rsp+258h+var_B8]; this
0x18002dc32  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002dc37  mov     eax, 8000FFFFh
0x18002dc3c  jmp     loc_18002DE13
0x18002dc41  mov     edi, r15d
0x18002dc44  cmp     edi, dword ptr [rsp+258h+var_158]
0x18002dc4b  jnb     loc_18002DDCF
0x18002dc51  xor     edx, edx; Val
0x18002dc53  lea     r8d, [rdx+78h]; Size
0x18002dc57  lea     rcx, [rsp+258h+var_138]; void *
0x18002dc5f  call    memset_0
0x18002dc64  lea     rcx, [rsp+258h+var_138]; this
0x18002dc6c  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x18002dc71  nop
0x18002dc72  mov     rax, qword ptr [rsp+258h+var_178]
0x18002dc7a  mov     edx, edi
0x18002dc7c  lea     rcx, [rsp+258h+var_178]
0x18002dc84  mov     rax, [rax+20h]
0x18002dc88  call    cs:__guard_dispatch_icall_fptr
0x18002dc8e  mov     rbx, rax
0x18002dc91  lea     rdx, [rax+8]
0x18002dc95  lea     rcx, [rsp+258h+var_138]
0x18002dc9d  call    ??4CSid@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSid::operator=(ATL::CSid const &)
0x18002dca2  mov     r14d, [rbx+80h]
0x18002dca9  mov     dword ptr [rsp+258h+ppsidGroup], 220h
0x18002dcb1  mov     r9d, 20h ; ' '
0x18002dcb7  lea     r8d, [r9-1Eh]; unsigned __int8
0x18002dcbb  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x18002dcc2  lea     rcx, [rsp+258h+var_208]; this
0x18002dcc7  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x18002dccc  or      esi, 3
0x18002dccf  cmp     [rsp+258h+var_1BC], r15b
0x18002dcd7  jz      short loc_18002DD1B
0x18002dcd9  lea     rcx, [rsp+258h+pSid1]; pSid
0x18002dcde  call    cs:__imp_IsValidSid
0x18002dce4  test    eax, eax
0x18002dce6  jz      short loc_18002DD1B
0x18002dce8  cmp     [rsp+258h+var_EC], r15b
0x18002dcf0  jz      short loc_18002DD1B
0x18002dcf2  lea     rcx, [rsp+258h+pSid2]; pSid
0x18002dcfa  call    cs:__imp_IsValidSid
0x18002dd00  test    eax, eax
0x18002dd02  jz      short loc_18002DD1B
0x18002dd04  lea     rdx, [rsp+258h+pSid2]; pSid2
0x18002dd0c  lea     rcx, [rsp+258h+pSid1]; pSid1
0x18002dd11  call    cs:__imp_EqualSid
0x18002dd17  test    eax, eax
0x18002dd19  jnz     short loc_18002DD6A
0x18002dd1b  cmp     cs:byte_1800770BC, r15b
0x18002dd22  jz      short loc_18002DD6F
0x18002dd24  lea     rcx, qword_180077078; pSid
0x18002dd2b  call    cs:__imp_IsValidSid
0x18002dd31  test    eax, eax
0x18002dd33  jz      short loc_18002DD6F
0x18002dd35  cmp     [rsp+258h+var_EC], r15b
0x18002dd3d  jz      short loc_18002DD6F
0x18002dd3f  lea     rcx, [rsp+258h+pSid2]; pSid
0x18002dd47  call    cs:__imp_IsValidSid
0x18002dd4d  test    eax, eax
0x18002dd4f  jz      short loc_18002DD6F
0x18002dd51  lea     rdx, [rsp+258h+pSid2]; pSid2
0x18002dd59  lea     rcx, qword_180077078; pSid1
0x18002dd60  call    cs:__imp_EqualSid
0x18002dd66  test    eax, eax
0x18002dd68  jz      short loc_18002DD6F
0x18002dd6a  mov     bl, r12b
0x18002dd6d  jmp     short loc_18002DD72
0x18002dd6f  mov     bl, r15b
0x18002dd72  and     esi, 0FFFFFFFEh
0x18002dd75  lea     rcx, [rsp+258h+var_208]; this
0x18002dd7a  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002dd7f  test    bl, bl
0x18002dd81  jnz     short loc_18002DDBA
0x18002dd83  cmp     r14d, 120089h
0x18002dd8a  jz      short loc_18002DDBA
0x18002dd8c  lea     rcx, [rsp+258h+var_138]; this
0x18002dd94  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002dd99  nop
0x18002dd9a  lea     rcx, [rsp+258h+var_178]; this
0x18002dda2  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x18002dda7  nop
0x18002dda8  lea     rcx, [rsp+258h+var_B8]; this
0x18002ddb0  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002ddb5  mov     eax, r12d
0x18002ddb8  jmp     short loc_18002DE13
0x18002ddba  lea     rcx, [rsp+258h+var_138]; this
0x18002ddc2  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002ddc7  add     edi, r12d
0x18002ddca  jmp     loc_18002DC44
0x18002ddcf  lea     rcx, [rsp+258h+var_178]; this
0x18002ddd7  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x18002dddc  nop
0x18002dddd  lea     rcx, [rsp+258h+var_B8]; this
0x18002dde5  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002ddea  xor     eax, eax
0x18002ddec  jmp     short loc_18002DE13
0x18002ddee  lea     rcx, [rsp+258h+var_B8]; this
0x18002ddf6  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002ddfb  mov     eax, 8000FFFFh
0x18002de00  jmp     short loc_18002DE13
0x18002de02  mov     eax, 8007000Eh
0x18002de07  jmp     short loc_18002DE13
0x18002de09  mov     eax, [rsp+258h+var_218]
0x18002de0d  jmp     short loc_18002DE13
0x18002de0f  mov     eax, [rsp+258h+var_214]
0x18002de13  mov     rcx, [rsp+258h+var_38]
0x18002de1b  xor     rcx, rsp; StackCookie
0x18002de1e  call    __security_check_cookie
0x18002de23  mov     rbx, [rsp+258h+arg_10]
0x18002de2b  add     rsp, 230h
0x18002de32  pop     r15
0x18002de34  pop     r14
0x18002de36  pop     r12
0x18002de38  pop     rdi
0x18002de39  pop     rsi
0x18002de3a  retn
```
