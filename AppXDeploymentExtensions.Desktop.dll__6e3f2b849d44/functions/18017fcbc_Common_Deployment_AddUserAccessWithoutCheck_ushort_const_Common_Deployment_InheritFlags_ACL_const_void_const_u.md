# Common::Deployment::AddUserAccessWithoutCheck(ushort const *,Common::Deployment::InheritFlags,_ACL * const,void * const,ulong)

- ea: `0x18017fcbc`
- end: `0x18017feb9`
- name: `?AddUserAccessWithoutCheck@Deployment@Common@@YAJPEBGW4InheritFlags@12@QEAU_ACL@@QEAXK@Z`
- size: `509`
- prototype: `__int64 __fastcall(WCHAR *, char, unsigned __int16 *, void *, DWORD AccessMask)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180068824`

## callees

- `0x18000669c`
- `0x180012fc8`
- `0x18001adb4`
- `0x180022f94`
- `0x180099b44`
- `0x1800af1bc`
- `0x1800af220`
- `0x1800af85a`
- `0x1800af918`
- `0x1800ba45d`
- `0x1800da7c0`
- `0x18017fcbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18017fd55`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18017fd85`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18017fd55`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18017fd85`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18017fcda`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18017fcda`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18017fdc7`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18017fdc7`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18017fe19`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18017fe19`

## string_xrefs

- `0x18017fcf9`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x18017fddf`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x18017fe45`: `onecore\admin\appmodel\common\accesshelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Common::Deployment::AddUserAccessWithoutCheck(
        WCHAR *a1,
        char a2,
        unsigned __int16 *a3,
        void *a4,
        DWORD AccessMask)
{
  DWORD LengthSid; // eax
  DWORD v10; // r10d
  __int64 v11; // rdx
  unsigned int LastError; // ebx
  DWORD v13; // ebp
  struct _ACL *pDacl; // rdi
  size_t v15; // r8
  const char *v16; // r9
  signed int v17; // eax
  const unsigned __int16 *v18; // rax
  __int64 v19; // rcx
  const unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  int pSid; // [rsp+20h] [rbp-68h]
  int pSida; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  LengthSid = GetLengthSid(a4);
  v10 = LengthSid + 12;
  if ( LengthSid + 12 < LengthSid )
  {
    v11 = 106;
LABEL_3:
    LastError = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
      (const char *)0x80070216LL,
      pSid);
    return LastError;
  }
  v13 = v10 + a3[1];
  if ( v13 < v10 )
  {
    v11 = 107;
    goto LABEL_3;
  }
  pDacl = (struct _ACL *)operator new(v13);
  memset_0(pDacl, 0, v13);
  v15 = a3[1];
  if ( a3[1] )
  {
    if ( !pDacl )
    {
      *(_DWORD *)_o__errno() = 22;
LABEL_12:
      invalid_parameter_noinfo();
      goto LABEL_13;
    }
    if ( v13 < v15 )
    {
      memset_0(pDacl, 0, v13);
      *(_DWORD *)_o__errno() = 34;
      goto LABEL_12;
    }
    memcpy_0(pDacl, a3, v15);
  }
LABEL_13:
  pDacl->AclSize = v13;
  if ( AddAccessAllowedAceEx(pDacl, 4u, a2 & 3 | (2 * (a2 & 4)), AccessMask, a4) )
  {
    v17 = SetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
    LastError = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        LastError = (unsigned __int16)v17 | 0x80070000;
      if ( (LastError & 0x80000000) != 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
          (const char *)LastError,
          pSida);
      if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      {
        v18 = RemovePIIfromFilePath(a1);
        McTemplateU0zd_EventWriteTransfer(v19, ChangingAccessRightsFailed, v18, LastError);
      }
      v20 = RemovePIIfromFilePath(a1);
      details::appxLog<unsigned short *,unsigned short *>(LastError, v21, ChangingAccessRightsFailed, v20, LastError);
    }
    else
    {
      LastError = 0;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7B,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
                  v16);
  }
  operator delete(pDacl, (const struct std::nothrow_t *)8);
  return LastError;
}

```

## disassembly

```asm
0x18017fcbc  push    rbx
0x18017fcbe  push    rbp
0x18017fcbf  push    rsi
0x18017fcc0  push    rdi
0x18017fcc1  push    r12
0x18017fcc3  push    r14
0x18017fcc5  push    r15
0x18017fcc7  sub     rsp, 50h
0x18017fccb  mov     r12, r9
0x18017fcce  mov     rsi, r8
0x18017fcd1  mov     r15d, edx
0x18017fcd4  mov     r14, rcx
0x18017fcd7  mov     rcx, r9; pSid
0x18017fcda  call    cs:__imp_GetLengthSid
0x18017fce1  nop     dword ptr [rax+rax+00h]
0x18017fce6  lea     r10d, [rax+0Ch]
0x18017fcea  cmp     r10d, eax
0x18017fced  jnb     short loc_18017FD15
0x18017fcef  mov     edx, 6Ah ; 'j'; void *
0x18017fcf4  mov     ebx, 80070216h
0x18017fcf9  lea     r8, aOnecoreAdminAp_116; "onecore\\admin\\appmodel\\common\\acces"...
0x18017fd00  mov     r9d, ebx; char *
0x18017fd03  mov     rcx, [rsp+88h]; this
0x18017fd0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017fd10  jmp     loc_18017FEA7
0x18017fd15  movzx   ebp, word ptr [rsi+2]
0x18017fd19  add     ebp, r10d
0x18017fd1c  cmp     ebp, r10d
0x18017fd1f  jnb     short loc_18017FD28
0x18017fd21  mov     edx, 6Bh ; 'k'
0x18017fd26  jmp     short loc_18017FCF4
0x18017fd28  mov     ebx, ebp
0x18017fd2a  mov     ecx, ebp; Size
0x18017fd2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18017fd31  mov     rdi, rax
0x18017fd34  mov     [rsp+88h+var_48], rax
0x18017fd39  mov     r8d, ebp; Size
0x18017fd3c  xor     edx, edx; Val
0x18017fd3e  mov     rcx, rax; void *
0x18017fd41  call    memset_0
0x18017fd46  movzx   r8d, word ptr [rsi+2]; Size
0x18017fd4b  test    r8, r8
0x18017fd4e  jz      short loc_18017FD9C
0x18017fd50  test    rdi, rdi
0x18017fd53  jnz     short loc_18017FD69
0x18017fd55  call    cs:__imp__o__errno
0x18017fd5c  nop     dword ptr [rax+rax+00h]
0x18017fd61  mov     dword ptr [rax], 16h
0x18017fd67  jmp     short loc_18017FD97
0x18017fd69  mov     rcx, rdi; void *
0x18017fd6c  cmp     rbx, r8
0x18017fd6f  jb      short loc_18017FD7B
0x18017fd71  mov     rdx, rsi; Src
0x18017fd74  call    memcpy_0
0x18017fd79  jmp     short loc_18017FD9C
0x18017fd7b  mov     r8, rbx; Size
0x18017fd7e  xor     edx, edx; Val
0x18017fd80  call    memset_0
0x18017fd85  call    cs:__imp__o__errno
0x18017fd8c  nop     dword ptr [rax+rax+00h]
0x18017fd91  mov     dword ptr [rax], 22h ; '"'
0x18017fd97  call    _invalid_parameter_noinfo
0x18017fd9c  mov     [rdi+2], bp
0x18017fda0  mov     r8d, r15d
0x18017fda3  mov     ebx, 4
0x18017fda8  and     r8d, ebx
0x18017fdab  add     r8d, r8d
0x18017fdae  and     r15d, 3
0x18017fdb2  or      r8d, r15d; AceFlags
0x18017fdb5  mov     [rsp+88h+pSid], r12; pSid
0x18017fdba  mov     r9d, [rsp+88h+AccessMask]; AccessMask
0x18017fdc2  mov     edx, ebx; dwAceRevision
0x18017fdc4  mov     rcx, rdi; pAcl
0x18017fdc7  call    cs:__imp_AddAccessAllowedAceEx
0x18017fdce  nop     dword ptr [rax+rax+00h]
0x18017fdd3  test    eax, eax
0x18017fdd5  jnz     short loc_18017FDF5
0x18017fdd7  mov     rcx, [rsp+88h]; this
0x18017fddf  lea     r8, aOnecoreAdminAp_116; "onecore\\admin\\appmodel\\common\\acces"...
0x18017fde6  lea     edx, [rbx+77h]; void *
0x18017fde9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18017fdee  mov     ebx, eax
0x18017fdf0  jmp     loc_18017FE9A
0x18017fdf5  mov     [rsp+88h+pSacl], 0; pSacl
0x18017fdfe  mov     [rsp+88h+pDacl], rdi; pDacl
0x18017fe03  mov     [rsp+88h+pSid], 0; int
0x18017fe0c  xor     r9d, r9d; psidOwner
0x18017fe0f  mov     r8d, ebx; SecurityInfo
0x18017fe12  lea     edx, [r9+1]; ObjectType
0x18017fe16  mov     rcx, r14; pObjectName
0x18017fe19  call    cs:__imp_SetNamedSecurityInfoW
0x18017fe20  nop     dword ptr [rax+rax+00h]
0x18017fe25  mov     ebx, eax
0x18017fe27  test    eax, eax
0x18017fe29  jz      short loc_18017FE98
0x18017fe2b  jle     short loc_18017FE36
0x18017fe2d  movzx   ebx, ax
0x18017fe30  or      ebx, 80070000h
0x18017fe36  mov     rcx, [rsp+88h]; this
0x18017fe3e  test    ebx, ebx
0x18017fe40  jns     short loc_18017FE56
0x18017fe42  mov     r9d, ebx; char *
0x18017fe45  lea     r8, aOnecoreAdminAp_116; "onecore\\admin\\appmodel\\common\\acces"...
0x18017fe4c  mov     edx, 8Dh; void *
0x18017fe51  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017fe56  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x18017fe5d  jge     short loc_18017FE79
0x18017fe5f  mov     rcx, r14; unsigned __int16 *
0x18017fe62  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18017fe67  mov     r8, rax
0x18017fe6a  mov     r9d, ebx
0x18017fe6d  lea     rdx, ChangingAccessRightsFailed
0x18017fe74  call    McTemplateU0zd_EventWriteTransfer
0x18017fe79  mov     rcx, r14; unsigned __int16 *
0x18017fe7c  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x18017fe81  mov     r9, rax
0x18017fe84  mov     dword ptr [rsp+88h+pSid], ebx
0x18017fe88  lea     r8, ChangingAccessRightsFailed
0x18017fe8f  mov     ecx, ebx
0x18017fe91  call    ??$appxLog@PEAGPEAG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEAG2@Z; details::appxLog<ushort *,ushort *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort *,ushort *)
0x18017fe96  jmp     short loc_18017FE9A
0x18017fe98  xor     ebx, ebx
0x18017fe9a  mov     edx, 8; struct std::nothrow_t *
0x18017fe9f  mov     rcx, rdi; void *
0x18017fea2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18017fea7  mov     eax, ebx
0x18017fea9  add     rsp, 50h
0x18017fead  pop     r15
0x18017feaf  pop     r14
0x18017feb1  pop     r12
0x18017feb3  pop     rdi
0x18017feb4  pop     rsi
0x18017feb5  pop     rbp
0x18017feb6  pop     rbx
0x18017feb7  retn
```
