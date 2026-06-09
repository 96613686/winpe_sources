# CDlpManager::SetStringProperty(ushort const *,ushort const *)

- ea: `0x14004e730`
- end: `0x14004ebae`
- name: `?SetStringProperty@CDlpManager@@UEAAJPEBG0@Z`
- size: `1150`
- prototype: `int(CDlpManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002c158`
- `0x140034ab4`
- `0x14004e730`
- `0x140082010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14004eb82`
- `KERNEL32!LeaveCriticalSection` at `0x14004eb82`
- `KERNEL32!EnterCriticalSection` at `0x14004e769`
- `KERNEL32!EnterCriticalSection` at `0x14004e769`
- `KERNEL32!CompareStringW` at `0x14004e94f`
- `KERNEL32!CompareStringW` at `0x14004e94f`
- `OLEAUT32!__imp_SysAllocString` at `0x14004e861`
- `OLEAUT32!__imp_SysAllocString` at `0x14004e96e`
- `OLEAUT32!__imp_SysAllocString` at `0x14004e861`
- `OLEAUT32!__imp_SysAllocString` at `0x14004e96e`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e9fd`
- `OLEAUT32!__imp_SysFreeString` at `0x14004eb56`
- `OLEAUT32!__imp_SysFreeString` at `0x14004eb6a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e9fd`
- `OLEAUT32!__imp_SysFreeString` at `0x14004eb56`
- `OLEAUT32!__imp_SysFreeString` at `0x14004eb6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpManager::SetStringProperty(
        CDlpManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r15
  OLECHAR *v7; // rbx
  OLECHAR *v8; // rdi
  int v9; // esi
  __int64 v10; // rax
  unsigned int v11; // ebp
  int v12; // eax
  BSTR v13; // rax
  BSTR v14; // r15
  __int64 v15; // rax
  unsigned int v16; // ebp
  int v17; // eax
  unsigned int v18; // r13d
  int v19; // r14d
  __int64 v20; // rax
  const WCHAR *v21; // rax
  BSTR v22; // rax
  __int64 v23; // r14
  OLECHAR *v24; // rbp
  OLECHAR *v25; // rcx
  BSTR v26; // rax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-78h]
  int lpString2a; // [rsp+20h] [rbp-78h]
  __int64 cchCount2; // [rsp+28h] [rbp-70h]
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+A0h] [rbp+8h]
  OLECHAR *v36; // [rsp+A8h] [rbp+10h] BYREF
  OLECHAR *v37; // [rsp+B8h] [rbp+20h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 472);
  v35 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 472);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
      goto LABEL_52;
    v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
    v11 = 0;
    if ( !v10 )
      goto LABEL_7;
    lpString2a = 2114;
    goto LABEL_5;
  }
  if ( a3 )
  {
    v13 = SysAllocString(a3);
    v14 = v13;
    if ( v13 )
    {
      v8 = v13;
      v37 = v13;
      v18 = *((_DWORD *)this + 135);
      v19 = 0;
      if ( v18 )
      {
        while ( 1 )
        {
          v20 = *((_QWORD *)this + 68);
          if ( !v20 )
            v20 = 0;
          v36 = (OLECHAR *)v19;
          v21 = *(const WCHAR **)(v20 + 8LL * v19);
          if ( !v21 )
            v21 = 0;
          if ( CompareStringW(0x409u, 1u, a2, -1, v21, -1) == 2 )
            break;
          if ( ++v19 >= v18 )
            goto LABEL_26;
        }
        v23 = *((_QWORD *)this + 70);
        if ( !v23 )
          v23 = 0;
        v8 = 0;
        v24 = v36;
        v25 = *(OLECHAR **)(v23 + 8LL * (_QWORD)v36);
        if ( v25 )
          SysFreeString(v25);
        v26 = 0;
        if ( v14 )
          v26 = v14;
        *(_QWORD *)(v23 + 8LL * (_QWORD)v24) = v26;
        goto LABEL_51;
      }
LABEL_26:
      v22 = SysAllocString(a2);
      if ( v22 )
      {
        v36 = v22;
        v9 = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 536, &v36);
        if ( v9 >= 0 )
        {
          v9 = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 552, &v37);
          if ( v9 < 0 && (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
          {
            v29 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
            if ( v29 )
            {
              LODWORD(cchCount2) = v9;
              LODWORD(lpString2) = 2146;
              v30 = CDlpLogT<CEmptyType>::DlpLogFormat(
                      v29,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDlpManager::SetStringProperty",
                      lpString2,
                      cchCount2,
                      -2);
              LODWORD(v7) = v30;
              if ( v30 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v30);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
          }
          v8 = v37;
        }
        else if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
        {
          v27 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
          if ( v27 )
          {
            LODWORD(cchCount2) = v9;
            LODWORD(lpString2) = 2145;
            v28 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v27,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpManager::SetStringProperty",
                    lpString2,
                    cchCount2,
                    -2);
            LODWORD(v7) = v28;
            if ( v28 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v28);
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
        }
        v7 = v36;
        goto LABEL_51;
      }
      v9 = -2147024882;
      if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
      {
        v15 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
        v16 = 0;
        if ( v15 )
        {
          LODWORD(cchCount2) = -2147024882;
          LODWORD(lpString2) = 2141;
LABEL_16:
          v17 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v15,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpManager::SetStringProperty",
                  lpString2,
                  cchCount2,
                  -2);
          v16 = v17;
          if ( v17 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
        }
LABEL_18:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v16);
      }
    }
    else
    {
      v9 = -2147024882;
      if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
      {
        v15 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
        v16 = 0;
        if ( v15 )
        {
          LODWORD(cchCount2) = -2147024882;
          LODWORD(lpString2) = 2120;
          goto LABEL_16;
        }
        goto LABEL_18;
      }
    }
LABEL_51:
    v6 = v35;
    goto LABEL_52;
  }
  v9 = -2147024809;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
  {
    v10 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
    v11 = 0;
    if ( !v10 )
    {
LABEL_7:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
      goto LABEL_52;
    }
    lpString2a = 2115;
LABEL_5:
    v12 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v10,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpManager::SetStringProperty",
            lpString2a,
            -2147024809,
            -2);
    v11 = v12;
    if ( v12 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
    goto LABEL_7;
  }
LABEL_52:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v9);
  if ( v8 )
    SysFreeString(v8);
  if ( v7 )
    SysFreeString(v7);
  LeaveCriticalSection(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14004e730  mov     rax, rsp
0x14004e733  push    rbp
0x14004e734  push    rsi
0x14004e735  push    rdi
0x14004e736  push    r12
0x14004e738  push    r13
0x14004e73a  push    r14
0x14004e73c  push    r15
0x14004e73e  sub     rsp, 60h
0x14004e742  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x14004e74a  mov     [rax+18h], rbx
0x14004e74e  mov     r14, r8
0x14004e751  mov     r12, rdx
0x14004e754  mov     rbp, rcx
0x14004e757  lea     r15, [rcx+1D8h]
0x14004e75e  mov     [rsp+98h+arg_0], r15
0x14004e766  mov     rcx, r15; lpCriticalSection
0x14004e769  call    cs:__imp_EnterCriticalSection
0x14004e770  nop     dword ptr [rax+rax+00h]
0x14004e775  mov     [rsp+98h+var_50], 1
0x14004e77d  xor     r13d, r13d
0x14004e780  mov     ebx, r13d
0x14004e783  mov     edi, r13d
0x14004e786  mov     esi, r13d
0x14004e789  test    r12, r12
0x14004e78c  jnz     short loc_14004E80B
0x14004e78e  mov     r14d, 80070057h
0x14004e794  mov     esi, r14d
0x14004e797  mov     rax, [rbp+48h]
0x14004e79b  lea     rcx, [rbp+48h]
0x14004e79f  mov     rax, [rax+10h]
0x14004e7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e7a8  test    rax, rax
0x14004e7ab  jz      loc_14004EB47
0x14004e7b1  mov     rax, [rbp+48h]
0x14004e7b5  lea     rcx, [rbp+48h]
0x14004e7b9  mov     rax, [rax+10h]
0x14004e7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e7c2  mov     ebp, r13d
0x14004e7c5  test    rax, rax
0x14004e7c8  jz      short loc_14004E7FF
0x14004e7ca  mov     dword ptr [rsp+98h+cchCount2], r14d
0x14004e7cf  mov     dword ptr [rsp+98h+lpString2], 842h
0x14004e7d7  lea     r9, aCdlpmanagerSet_1; "CDlpManager::SetStringProperty"
0x14004e7de  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004e7e5  mov     edx, 4
0x14004e7ea  mov     rcx, rax
0x14004e7ed  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004e7f2  test    eax, eax
0x14004e7f4  mov     ebp, eax
0x14004e7f6  jns     short loc_14004E7FF
0x14004e7f8  mov     ecx, eax
0x14004e7fa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004e7ff  mov     ecx, ebp
0x14004e801  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004e806  jmp     loc_14004EB47
0x14004e80b  test    r14, r14
0x14004e80e  jnz     short loc_14004E85E
0x14004e810  mov     r14d, 80070057h
0x14004e816  mov     esi, r14d
0x14004e819  mov     rax, [rbp+48h]
0x14004e81d  lea     rcx, [rbp+48h]
0x14004e821  mov     rax, [rax+10h]
0x14004e825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e82a  test    rax, rax
0x14004e82d  jz      loc_14004EB47
0x14004e833  mov     rax, [rbp+48h]
0x14004e837  lea     rcx, [rbp+48h]
0x14004e83b  mov     rax, [rax+10h]
0x14004e83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e844  mov     ebp, r13d
0x14004e847  test    rax, rax
0x14004e84a  jz      short loc_14004E7FF
0x14004e84c  mov     dword ptr [rsp+98h+cchCount2], r14d
0x14004e851  mov     dword ptr [rsp+98h+lpString2], 843h
0x14004e859  jmp     loc_14004E7D7
0x14004e85e  mov     rcx, r14; psz
0x14004e861  call    cs:__imp_SysAllocString
0x14004e868  nop     dword ptr [rax+rax+00h]
0x14004e86d  mov     r15, rax
0x14004e870  test    rax, rax
0x14004e873  jnz     short loc_14004E8F2
0x14004e875  mov     r14d, 8007000Eh
0x14004e87b  mov     esi, r14d
0x14004e87e  mov     rax, [rbp+48h]
0x14004e882  lea     rcx, [rbp+48h]
0x14004e886  mov     rax, [rax+10h]
0x14004e88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e88f  test    rax, rax
0x14004e892  jz      loc_14004EB3F
0x14004e898  mov     rax, [rbp+48h]
0x14004e89c  lea     rcx, [rbp+48h]
0x14004e8a0  mov     rax, [rax+10h]
0x14004e8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e8a9  mov     ebp, r13d
0x14004e8ac  test    rax, rax
0x14004e8af  jz      short loc_14004E8E6
0x14004e8b1  mov     dword ptr [rsp+98h+cchCount2], r14d
0x14004e8b6  mov     dword ptr [rsp+98h+lpString2], 848h
0x14004e8be  lea     r9, aCdlpmanagerSet_1; "CDlpManager::SetStringProperty"
0x14004e8c5  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004e8cc  mov     edx, 4
0x14004e8d1  mov     rcx, rax
0x14004e8d4  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004e8d9  test    eax, eax
0x14004e8db  mov     ebp, eax
0x14004e8dd  jns     short loc_14004E8E6
0x14004e8df  mov     ecx, eax
0x14004e8e1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004e8e6  mov     ecx, ebp
0x14004e8e8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004e8ed  jmp     loc_14004EB3F
0x14004e8f2  mov     rdi, r15
0x14004e8f5  mov     [rsp+98h+arg_18], r15
0x14004e8fd  mov     r13d, [rbp+21Ch]
0x14004e904  xor     edx, edx
0x14004e906  mov     r14d, edx
0x14004e909  test    r13d, r13d
0x14004e90c  jz      short loc_14004E96B
0x14004e90e  mov     rax, [rbp+220h]
0x14004e915  test    rax, rax
0x14004e918  cmovz   rax, rdx
0x14004e91c  movsxd  rcx, r14d
0x14004e91f  mov     [rsp+98h+arg_8], rcx
0x14004e927  mov     rax, [rax+rcx*8]
0x14004e92b  test    rax, rax
0x14004e92e  cmovz   rax, rdx
0x14004e932  mov     dword ptr [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x14004e93a  mov     [rsp+98h+lpString2], rax; lpString2
0x14004e93f  or      r9d, 0FFFFFFFFh; cchCount1
0x14004e943  mov     r8, r12; lpString1
0x14004e946  lea     edx, [r9+2]; dwCmpFlags
0x14004e94a  mov     ecx, 409h; Locale
0x14004e94f  call    cs:__imp_CompareStringW
0x14004e956  nop     dword ptr [rax+rax+00h]
0x14004e95b  cmp     eax, 2
0x14004e95e  jz      short loc_14004E9D8
0x14004e960  inc     r14d
0x14004e963  cmp     r14d, r13d
0x14004e966  mov     rdx, rbx
0x14004e969  jb      short loc_14004E90E
0x14004e96b  mov     rcx, r12; psz
0x14004e96e  call    cs:__imp_SysAllocString
0x14004e975  nop     dword ptr [rax+rax+00h]
0x14004e97a  xor     r13d, r13d
0x14004e97d  test    rax, rax
0x14004e980  jnz     loc_14004EA1C
0x14004e986  mov     r14d, 8007000Eh
0x14004e98c  mov     esi, r14d
0x14004e98f  mov     rax, [rbp+48h]
0x14004e993  lea     rcx, [rbp+48h]
0x14004e997  mov     rax, [rax+10h]
0x14004e99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e9a0  test    rax, rax
0x14004e9a3  jz      loc_14004EB3F
0x14004e9a9  mov     rax, [rbp+48h]
0x14004e9ad  lea     rcx, [rbp+48h]
0x14004e9b1  mov     rax, [rax+10h]
0x14004e9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e9ba  mov     ebp, r13d
0x14004e9bd  test    rax, rax
0x14004e9c0  jz      loc_14004E8E6
0x14004e9c6  mov     dword ptr [rsp+98h+cchCount2], r14d
0x14004e9cb  mov     dword ptr [rsp+98h+lpString2], 85Dh
0x14004e9d3  jmp     loc_14004E8BE
0x14004e9d8  mov     r14, [rbp+230h]
0x14004e9df  xor     r13d, r13d
0x14004e9e2  test    r14, r14
0x14004e9e5  cmovz   r14, r13
0x14004e9e9  mov     edi, r13d
0x14004e9ec  mov     rbp, [rsp+98h+arg_8]
0x14004e9f4  mov     rcx, [r14+rbp*8]; bstrString
0x14004e9f8  test    rcx, rcx
0x14004e9fb  jz      short loc_14004EA09
0x14004e9fd  call    cs:__imp_SysFreeString
0x14004ea04  nop     dword ptr [rax+rax+00h]
0x14004ea09  mov     rax, r13
0x14004ea0c  test    r15, r15
0x14004ea0f  cmovnz  rax, r15
0x14004ea13  mov     [r14+rbp*8], rax
0x14004ea17  jmp     loc_14004EB3F
0x14004ea1c  mov     [rsp+98h+arg_8], rax
0x14004ea24  lea     rcx, [rbp+218h]
0x14004ea2b  lea     rdx, [rsp+98h+arg_8]
0x14004ea33  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x14004ea38  mov     esi, eax
0x14004ea3a  test    eax, eax
0x14004ea3c  jns     short loc_14004EAAE
0x14004ea3e  mov     rdx, [rbp+48h]
0x14004ea42  lea     rcx, [rbp+48h]
0x14004ea46  mov     rax, [rdx+10h]
0x14004ea4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ea4f  test    rax, rax
0x14004ea52  jz      loc_14004EB37
0x14004ea58  mov     rax, [rbp+48h]
0x14004ea5c  lea     rcx, [rbp+48h]
0x14004ea60  mov     rax, [rax+10h]
0x14004ea64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ea69  test    rax, rax
0x14004ea6c  jz      short loc_14004EAA2
0x14004ea6e  mov     dword ptr [rsp+98h+cchCount2], esi
0x14004ea72  mov     dword ptr [rsp+98h+lpString2], 861h
0x14004ea7a  lea     r9, aCdlpmanagerSet_1; "CDlpManager::SetStringProperty"
0x14004ea81  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004ea88  mov     edx, 4
0x14004ea8d  mov     rcx, rax
0x14004ea90  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004ea95  mov     ebx, eax
0x14004ea97  test    eax, eax
0x14004ea99  jns     short loc_14004EAA2
0x14004ea9b  mov     ecx, eax
0x14004ea9d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004eaa2  mov     ecx, ebx
0x14004eaa4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004eaa9  jmp     loc_14004EB37
0x14004eaae  lea     rcx, [rbp+228h]
0x14004eab5  lea     rdx, [rsp+98h+arg_18]
0x14004eabd  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x14004eac2  mov     esi, eax
0x14004eac4  test    eax, eax
0x14004eac6  jns     short loc_14004EB2F
0x14004eac8  mov     rax, [rbp+48h]
0x14004eacc  lea     rcx, [rbp+48h]
0x14004ead0  mov     rax, [rax+10h]
0x14004ead4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ead9  test    rax, rax
0x14004eadc  jz      short loc_14004EB2F
0x14004eade  mov     rax, [rbp+48h]
0x14004eae2  lea     rcx, [rbp+48h]
0x14004eae6  mov     rax, [rax+10h]
0x14004eaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004eaef  test    rax, rax
0x14004eaf2  jz      short loc_14004EB28
0x14004eaf4  mov     dword ptr [rsp+98h+cchCount2], esi
0x14004eaf8  mov     dword ptr [rsp+98h+lpString2], 862h
0x14004eb00  lea     r9, aCdlpmanagerSet_1; "CDlpManager::SetStringProperty"
0x14004eb07  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004eb0e  mov     edx, 4
0x14004eb13  mov     rcx, rax
0x14004eb16  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004eb1b  mov     ebx, eax
0x14004eb1d  test    eax, eax
0x14004eb1f  jns     short loc_14004EB28
0x14004eb21  mov     ecx, eax
0x14004eb23  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004eb28  mov     ecx, ebx
0x14004eb2a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004eb2f  mov     rdi, [rsp+98h+arg_18]
0x14004eb37  mov     rbx, [rsp+98h+arg_8]
0x14004eb3f  mov     r15, [rsp+98h+arg_0]
0x14004eb47  mov     ecx, esi
0x14004eb49  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004eb4e  test    rdi, rdi
0x14004eb51  jz      short loc_14004EB62
0x14004eb53  mov     rcx, rdi; bstrString
0x14004eb56  call    cs:__imp_SysFreeString
0x14004eb5d  nop     dword ptr [rax+rax+00h]
0x14004eb62  test    rbx, rbx
0x14004eb65  jz      short loc_14004EB77
0x14004eb67  mov     rcx, rbx; bstrString
0x14004eb6a  call    cs:__imp_SysFreeString
0x14004eb71  nop     dword ptr [rax+rax+00h]
0x14004eb76  nop
0x14004eb77  mov     eax, [rsp+98h+var_50]
0x14004eb7b  test    eax, eax
0x14004eb7d  jz      short loc_14004EB93
0x14004eb7f  mov     rcx, r15; lpCriticalSection
0x14004eb82  call    cs:__imp_LeaveCriticalSection
0x14004eb89  nop     dword ptr [rax+rax+00h]
0x14004eb8e  mov     [rsp+98h+var_50], r13d
0x14004eb93  mov     eax, esi
0x14004eb95  mov     rbx, [rsp+98h+arg_10]
0x14004eb9d  add     rsp, 60h
0x14004eba1  pop     r15
0x14004eba3  pop     r14
0x14004eba5  pop     r13
0x14004eba7  pop     r12
0x14004eba9  pop     rdi
0x14004ebaa  pop     rsi
0x14004ebab  pop     rbp
0x14004ebac  retn
```
