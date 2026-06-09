# CSecurityHelper::CreateSecurityDescriptor(CSecurityHelper::CSid const *,CSecurityHelper::CSid const *,ulong,CSecurityHelper::CSidAndAccess const *,bool,bool)

- ea: `0x180060850`
- end: `0x180060bbd`
- name: `?CreateSecurityDescriptor@CSecurityHelper@@SA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@PEBUCSid@1@0KPEBUCSidAndAccess@1@_N2@Z`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c7390`

## callees

- `0x180002ab0`
- `0x180002f98`
- `0x1800035f8`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180011314`
- `0x1800155b8`
- `0x180028cdc`
- `0x180035564`
- `0x180060850`
- `0x180060d38`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x1800609a2`
- `ADVAPI32!InitializeAcl` at `0x1800609a2`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x180060a23`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x180060a23`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180060a73`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180060a73`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180060aca`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180060aca`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180060b1c`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180060b1c`

## string_xrefs

- `0x1800608e5`: `CSecurityHelper::CreateSecurityDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _ACL **__fastcall CSecurityHelper::CreateSecurityDescriptor(
        struct _ACL **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v6; // r14d
  _BYTE *v7; // rax
  char v8; // cl
  unsigned int v9; // r13d
  unsigned int v10; // ebx
  void *v11; // rax
  struct _ACL *v12; // r15
  struct _ACL *v13; // rdi
  unsigned int v14; // edx
  __int16 i; // cx
  int pExceptionObject; // [rsp+30h] [rbp-A1h] BYREF
  int LastFailureAsHRESULT; // [rsp+38h] [rbp-99h] BYREF
  int v19; // [rsp+3Ch] [rbp-95h]
  char v20; // [rsp+40h] [rbp-91h]
  const char *v21; // [rsp+48h] [rbp-89h]
  __int64 v22; // [rsp+50h] [rbp-81h]
  int v23; // [rsp+58h] [rbp-79h]
  _QWORD v24[2]; // [rsp+60h] [rbp-71h] BYREF
  _BYTE pSid[80]; // [rsp+70h] [rbp-61h] BYREF

  v24[1] = a1;
  v6 = 0;
  v23 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
    {
LABEL_7:
      v8 = 0;
      goto LABEL_8;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_4342751f50db37403eb675fae9cba500_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( (v7[68] & 2) == 0 )
    goto LABEL_7;
  v8 = 1;
  if ( v7[65] < 6u )
    goto LABEL_7;
LABEL_8:
  v20 = v8;
  v21 = "CSecurityHelper::CreateSecurityDescriptor";
  v22 = 0;
  memset_0(pSid, 0, 0x44u);
  ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(a1);
  v23 = 1;
  ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(v24);
  v9 = a5 != 0 ? 3 : 0;
  LastFailureAsHRESULT = 0;
  v19 = 516;
  v10 = 76 * v9 + 184;
  if ( v10 < 76 * v9 )
  {
    LastFailureAsHRESULT = -2147024362;
    HIWORD(v19) = 517;
    pExceptionObject = -2147024362;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v19) = 517;
  v11 = operator new[](v10);
  std::unique_ptr<unsigned char [0]>::reset<unsigned char *,0>((void **)a1, v11);
  v12 = *a1;
  v13 = *a1 + 22;
  if ( a5 )
  {
    if ( !InitializeAcl(*a1 + 22, 76 * v9 + 8, 2u) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v19) = 524;
      pExceptionObject = LastFailureAsHRESULT;
      throw (long *)&pExceptionObject;
    }
    for ( i = 524; ; i = 531 )
    {
      LastFailureAsHRESULT = 0;
      LOWORD(v19) = i;
      if ( v6 >= v9 )
        break;
      CSecurityHelper::ResolveSid((const struct CSecurityHelper::CSid *)(a5 + 24LL * v6), v14, pSid);
      if ( !AddAccessAllowedAceEx(v13, 2u, *(_DWORD *)(a5 + 24LL * v6 + 16), *(_DWORD *)(a5 + 24LL * v6 + 20), pSid) )
      {
        LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
        HIWORD(v19) = 531;
        pExceptionObject = LastFailureAsHRESULT;
        throw (long *)&pExceptionObject;
      }
      ++v6;
    }
  }
  LastFailureAsHRESULT = 0;
  if ( !InitializeSecurityDescriptor(v12, 1u) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v19) = 535;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v19) = 535;
  if ( a5 )
  {
    LastFailureAsHRESULT = 0;
    if ( !SetSecurityDescriptorDacl(v12, 1, v13, 0) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v19) = 551;
      pExceptionObject = LastFailureAsHRESULT;
      throw (long *)&pExceptionObject;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v19) = 551;
  }
  LastFailureAsHRESULT = 0;
  if ( !SetSecurityDescriptorControl(v12, 0x1000u, 0x1000u) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v19) = 556;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v19) = 556;
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v24);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return a1;
}

```

## disassembly

```asm
0x180060850  push    rbp
0x180060852  push    rbx
0x180060853  push    rsi
0x180060854  push    rdi
0x180060855  push    r12
0x180060857  push    r13
0x180060859  push    r14
0x18006085b  push    r15
0x18006085d  lea     rbp, [rsp-7]
0x180060862  sub     rsp, 0D8h
0x180060869  mov     rax, cs:__security_cookie
0x180060870  xor     rax, rsp
0x180060873  mov     [rbp+3Fh+var_50], rax
0x180060877  mov     rsi, rcx
0x18006087a  mov     r12, [rbp+3Fh+arg_20]
0x18006087e  mov     [rbp+3Fh+var_A8], rcx
0x180060882  xor     r14d, r14d
0x180060885  mov     [rbp+3Fh+var_B8], r14d
0x180060889  lea     rcx, WPP_GLOBAL_Control
0x180060890  mov     rax, cs:WPP_GLOBAL_Control
0x180060897  cmp     rax, rcx
0x18006089a  jz      short loc_1800608C3
0x18006089c  test    byte ptr [rax+44h], 2
0x1800608a0  jz      short loc_1800608D1
0x1800608a2  cmp     byte ptr [rax+41h], 6
0x1800608a6  jb      short loc_1800608C3
0x1800608a8  lea     edx, [r14+14h]
0x1800608ac  lea     r8, WPP_4342751f50db37403eb675fae9cba500_Traceguids
0x1800608b3  mov     rcx, [rax+38h]
0x1800608b7  call    WPP_SF_
0x1800608bc  mov     rax, cs:WPP_GLOBAL_Control
0x1800608c3  test    byte ptr [rax+44h], 2
0x1800608c7  jz      short loc_1800608D1
0x1800608c9  cmp     byte ptr [rax+41h], 6
0x1800608cd  mov     cl, 1
0x1800608cf  jnb     short loc_1800608D4
0x1800608d1  mov     cl, r14b
0x1800608d4  mov     [rsp+110h+var_D8], r14d
0x1800608d9  mov     [rsp+110h+var_D4], 1E9h
0x1800608e1  mov     [rsp+110h+var_D0], cl
0x1800608e5  lea     rax, aCsecurityhelpe; "CSecurityHelper::CreateSecurityDescript"...
0x1800608ec  mov     [rsp+110h+var_C8], rax
0x1800608f1  mov     [rsp+110h+var_C0], r14
0x1800608f6  xor     edx, edx; Val
0x1800608f8  lea     r8d, [rdx+44h]; Size
0x1800608fc  lea     rcx, [rbp+3Fh+var_A0]; void *
0x180060900  call    memset_0
0x180060905  mov     rcx, rsi
0x180060908  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x18006090d  mov     [rbp+3Fh+var_B8], 1
0x180060914  lea     rcx, [rbp+3Fh+var_B0]
0x180060918  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x18006091d  nop
0x18006091e  mov     rax, r14
0x180060921  sub     rax, r12
0x180060924  neg     rax
0x180060927  sbb     r13d, r13d
0x18006092a  and     r13d, 3
0x18006092e  imul    eax, r13d, 4Ch ; 'L'
0x180060932  mov     [rsp+110h+var_D8], r14d
0x180060937  mov     [rsp+110h+var_D8], r14d
0x18006093c  mov     ecx, 204h
0x180060941  mov     word ptr [rsp+110h+var_D4], cx
0x180060946  lea     ebx, [rax+0B8h]
0x18006094c  cmp     ebx, eax
0x18006094e  lea     eax, [rcx+1]
0x180060951  jb      loc_180060B95
0x180060957  mov     [rsp+110h+var_D8], r14d
0x18006095c  mov     [rsp+110h+var_D8], r14d
0x180060961  mov     word ptr [rsp+110h+var_D4], ax
0x180060966  mov     ecx, ebx; unsigned __int64
0x180060968  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006096d  mov     rdx, rax
0x180060970  mov     rcx, rsi
0x180060973  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0]>::reset<uchar *,0>(uchar *)
0x180060978  mov     r15, [rsi]
0x18006097b  lea     rdi, [r15+0B0h]
0x180060982  mov     eax, [rsp+110h+var_D8]
0x180060986  test    r12, r12
0x180060989  jz      loc_180060A65
0x18006098f  mov     [rsp+110h+var_D8], eax
0x180060993  lea     edx, [rbx-0B0h]; nAclLength
0x180060999  mov     r8d, 2; dwAclRevision
0x18006099f  mov     rcx, rdi; pAcl
0x1800609a2  call    cs:__imp_InitializeAcl
0x1800609a8  test    eax, eax
0x1800609aa  jnz     short loc_1800609D5
0x1800609ac  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800609b1  mov     [rsp+110h+var_D8], eax
0x1800609b5  mov     ecx, 20Ch
0x1800609ba  mov     word ptr [rsp+110h+var_D4+2], cx
0x1800609bf  mov     [rsp+110h+pExceptionObject], eax
0x1800609c3  lea     rdx, _TI1J; pThrowInfo
0x1800609ca  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x1800609cf  call    _CxxThrowException_0
0x1800609d5  mov     eax, r14d
0x1800609d8  mov     ecx, 20Ch
0x1800609dd  mov     [rsp+110h+var_D8], eax
0x1800609e1  mov     word ptr [rsp+110h+var_D4], cx
0x1800609e6  cmp     r14d, r13d
0x1800609e9  jnb     short loc_180060A62
0x1800609eb  mov     eax, r14d
0x1800609ee  lea     rcx, [rax+rax*2]
0x1800609f2  lea     rbx, [r12+rcx*8]
0x1800609f6  lea     r8, [rbp+3Fh+var_A0]; void *
0x1800609fa  mov     rcx, rbx; struct CSecurityHelper::CSid *
0x1800609fd  call    ?ResolveSid@CSecurityHelper@@CAXAEBUCSid@1@KPEAX@Z; CSecurityHelper::ResolveSid(CSecurityHelper::CSid const &,ulong,void *)
0x180060a02  mov     eax, [rsp+110h+var_D8]
0x180060a06  mov     [rsp+110h+var_D8], eax
0x180060a0a  lea     rax, [rbp+3Fh+var_A0]
0x180060a0e  mov     [rsp+110h+pSid], rax; pSid
0x180060a13  mov     r9d, [rbx+14h]; AccessMask
0x180060a17  mov     r8d, [rbx+10h]; AceFlags
0x180060a1b  mov     edx, 2; dwAceRevision
0x180060a20  mov     rcx, rdi; pAcl
0x180060a23  call    cs:__imp_AddAccessAllowedAceEx
0x180060a29  test    eax, eax
0x180060a2b  jz      short loc_180060A39
0x180060a2d  xor     eax, eax
0x180060a2f  mov     ecx, 213h
0x180060a34  inc     r14d
0x180060a37  jmp     short loc_1800609DD
0x180060a39  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180060a3e  mov     [rsp+110h+var_D8], eax
0x180060a42  mov     ecx, 213h
0x180060a47  mov     word ptr [rsp+110h+var_D4+2], cx
0x180060a4c  mov     [rsp+110h+pExceptionObject], eax
0x180060a50  lea     rdx, _TI1J; pThrowInfo
0x180060a57  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180060a5c  call    _CxxThrowException_0
0x180060a62  xor     r14d, r14d
0x180060a65  mov     [rsp+110h+var_D8], eax
0x180060a69  mov     ebx, 1
0x180060a6e  mov     edx, ebx; dwRevision
0x180060a70  mov     rcx, r15; pSecurityDescriptor
0x180060a73  call    cs:__imp_InitializeSecurityDescriptor
0x180060a79  test    eax, eax
0x180060a7b  jnz     short loc_180060AA6
0x180060a7d  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180060a82  mov     [rsp+110h+var_D8], eax
0x180060a86  mov     ecx, 217h
0x180060a8b  mov     word ptr [rsp+110h+var_D4+2], cx
0x180060a90  mov     [rsp+110h+pExceptionObject], eax
0x180060a94  lea     rdx, _TI1J; pThrowInfo
0x180060a9b  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180060aa0  call    _CxxThrowException_0
0x180060aa6  mov     [rsp+110h+var_D8], r14d
0x180060aab  mov     ecx, 217h
0x180060ab0  mov     word ptr [rsp+110h+var_D4], cx
0x180060ab5  test    r12, r12
0x180060ab8  jz      short loc_180060B0C
0x180060aba  mov     [rsp+110h+var_D8], r14d
0x180060abf  xor     r9d, r9d; bDaclDefaulted
0x180060ac2  mov     r8, rdi; pDacl
0x180060ac5  mov     edx, ebx; bDaclPresent
0x180060ac7  mov     rcx, r15; pSecurityDescriptor
0x180060aca  call    cs:__imp_SetSecurityDescriptorDacl
0x180060ad0  test    eax, eax
0x180060ad2  jnz     short loc_180060AFD
0x180060ad4  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180060ad9  mov     [rsp+110h+var_D8], eax
0x180060add  mov     ecx, 227h
0x180060ae2  mov     word ptr [rsp+110h+var_D4+2], cx
0x180060ae7  mov     [rsp+110h+pExceptionObject], eax
0x180060aeb  lea     rdx, _TI1J; pThrowInfo
0x180060af2  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180060af7  call    _CxxThrowException_0
0x180060afd  mov     [rsp+110h+var_D8], r14d
0x180060b02  mov     ecx, 227h
0x180060b07  mov     word ptr [rsp+110h+var_D4], cx
0x180060b0c  mov     [rsp+110h+var_D8], r14d
0x180060b11  mov     edx, 1000h; ControlBitsOfInterest
0x180060b16  mov     r8d, edx; ControlBitsToSet
0x180060b19  mov     rcx, r15; pSecurityDescriptor
0x180060b1c  call    cs:__imp_SetSecurityDescriptorControl
0x180060b22  test    eax, eax
0x180060b24  jnz     short loc_180060B4F
0x180060b26  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180060b2b  mov     [rsp+110h+var_D8], eax
0x180060b2f  mov     ecx, 22Ch
0x180060b34  mov     word ptr [rsp+110h+var_D4+2], cx
0x180060b39  mov     [rsp+110h+pExceptionObject], eax
0x180060b3d  lea     rdx, _TI1J; pThrowInfo
0x180060b44  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180060b49  call    _CxxThrowException_0
0x180060b4f  mov     [rsp+110h+var_D8], r14d
0x180060b54  mov     ecx, 22Ch
0x180060b59  mov     word ptr [rsp+110h+var_D4], cx
0x180060b5e  lea     rcx, [rbp+3Fh+var_B0]
0x180060b62  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180060b67  nop
0x180060b68  lea     rcx, [rsp+110h+var_D8]; this
0x180060b6d  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180060b72  mov     rax, rsi
0x180060b75  mov     rcx, [rbp+3Fh+var_50]
0x180060b79  xor     rcx, rsp; StackCookie
0x180060b7c  call    __security_check_cookie
0x180060b81  add     rsp, 0D8h
0x180060b88  pop     r15
0x180060b8a  pop     r14
0x180060b8c  pop     r13
0x180060b8e  pop     r12
0x180060b90  pop     rdi
0x180060b91  pop     rsi
0x180060b92  pop     rbx
0x180060b93  pop     rbp
0x180060b94  retn
0x180060b95  mov     ecx, 80070216h
0x180060b9a  mov     [rsp+110h+var_D8], ecx
0x180060b9e  mov     [rsp+110h+var_D8], ecx
0x180060ba2  mov     word ptr [rsp+110h+var_D4+2], ax
0x180060ba7  mov     [rsp+110h+pExceptionObject], ecx
0x180060bab  lea     rdx, _TI1J; pThrowInfo
0x180060bb2  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180060bb7  call    _CxxThrowException_0
```
