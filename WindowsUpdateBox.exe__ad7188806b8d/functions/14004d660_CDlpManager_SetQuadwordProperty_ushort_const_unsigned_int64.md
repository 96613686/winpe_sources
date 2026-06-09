# CDlpManager::SetQuadwordProperty(ushort const *,unsigned __int64)

- ea: `0x14004d660`
- end: `0x14004d996`
- name: `?SetQuadwordProperty@CDlpManager@@UEAAJPEBG_K@Z`
- size: `822`
- prototype: `int(CDlpManager *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002c158`
- `0x14002c250`
- `0x140034ab4`
- `0x14004d660`
- `0x140082010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14004d90d`
- `KERNEL32!LeaveCriticalSection` at `0x14004d90d`
- `KERNEL32!EnterCriticalSection` at `0x14004d699`
- `KERNEL32!EnterCriticalSection` at `0x14004d699`
- `KERNEL32!CompareStringW` at `0x14004d77b`
- `KERNEL32!CompareStringW` at `0x14004d77b`
- `OLEAUT32!__imp_SysAllocString` at `0x14004d79d`
- `OLEAUT32!__imp_SysAllocString` at `0x14004d79d`
- `OLEAUT32!__imp_SysFreeString` at `0x14004d8f5`
- `OLEAUT32!__imp_SysFreeString` at `0x14004d8f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpManager::SetQuadwordProperty(CDlpManager *this, const unsigned __int16 *a2, __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  OLECHAR *v7; // rbx
  int v8; // edi
  __int64 v9; // rax
  unsigned int v10; // esi
  int v11; // eax
  unsigned int v12; // r15d
  int v13; // ebp
  __int64 v14; // rax
  const WCHAR *v15; // rax
  BSTR v16; // rax
  __int64 v17; // rax
  unsigned int v18; // esi
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned int v22; // ebx
  int v23; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-78h]
  __int64 cchCount2; // [rsp+28h] [rbp-70h]
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+A0h] [rbp+8h]
  OLECHAR *v28; // [rsp+A8h] [rbp+10h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 416);
  v27 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 416);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
  v7 = 0;
  v8 = 0;
  if ( a2 )
  {
    v12 = *((_DWORD *)this + 151);
    v13 = 0;
    if ( v12 )
    {
      while ( 1 )
      {
        v14 = *((_QWORD *)this + 76);
        if ( !v14 )
          v14 = 0;
        v15 = *(const WCHAR **)(v14 + 8LL * v13);
        if ( !v15 )
          v15 = 0;
        if ( CompareStringW(0x409u, 1u, a2, -1, v15, -1) == 2 )
          break;
        if ( ++v13 >= v12 )
          goto LABEL_14;
      }
      v20 = *((_QWORD *)this + 78);
      if ( !v20 )
        v20 = 0;
      *(_QWORD *)(v20 + 8LL * v13) = a3;
      goto LABEL_31;
    }
LABEL_14:
    v16 = SysAllocString(a2);
    if ( !v16 )
    {
      v8 = -2147024882;
      if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
      {
        v17 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
        v18 = 0;
        if ( v17 )
        {
          LODWORD(cchCount2) = -2147024882;
          LODWORD(lpString2) = 2081;
          v19 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v17,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpManager::SetQuadwordProperty",
                  lpString2,
                  cchCount2,
                  -2);
          v18 = v19;
          if ( v19 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v18);
      }
      goto LABEL_31;
    }
    v28 = v16;
    v8 = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 600, &v28);
    if ( v8 >= 0 )
    {
      v8 = CArray<unsigned __int64,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 616, a3);
      if ( v8 >= 0 || !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
        goto LABEL_30;
      v21 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
      v22 = 0;
      if ( !v21 )
        goto LABEL_29;
      LODWORD(cchCount2) = v8;
      LODWORD(lpString2) = 2086;
    }
    else
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
      {
LABEL_30:
        v7 = v28;
LABEL_31:
        v6 = v27;
        goto LABEL_32;
      }
      v21 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
      v22 = 0;
      if ( !v21 )
      {
LABEL_29:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v22);
        goto LABEL_30;
      }
      LODWORD(cchCount2) = v8;
      LODWORD(lpString2) = 2085;
    }
    v23 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v21,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpManager::SetQuadwordProperty",
            lpString2,
            cchCount2,
            -2);
    v22 = v23;
    if ( v23 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
    goto LABEL_29;
  }
  v8 = -2147024809;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
  {
    v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
    v10 = 0;
    if ( v9 )
    {
      v11 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v9,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpManager::SetQuadwordProperty",
              2060,
              -2147024809,
              -2);
      v10 = v11;
      if ( v11 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  }
LABEL_32:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v7 )
    SysFreeString(v7);
  LeaveCriticalSection(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14004d660  mov     rax, rsp
0x14004d663  push    rbp
0x14004d664  push    rsi
0x14004d665  push    rdi
0x14004d666  push    r12
0x14004d668  push    r13
0x14004d66a  push    r14
0x14004d66c  push    r15
0x14004d66e  sub     rsp, 60h
0x14004d672  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x14004d67a  mov     [rax+18h], rbx
0x14004d67e  mov     r12, r8
0x14004d681  mov     r14, rdx
0x14004d684  mov     rsi, rcx
0x14004d687  lea     rbp, [rcx+1A0h]
0x14004d68e  mov     [rsp+98h+arg_0], rbp
0x14004d696  mov     rcx, rbp; lpCriticalSection
0x14004d699  call    cs:__imp_EnterCriticalSection
0x14004d6a0  nop     dword ptr [rax+rax+00h]
0x14004d6a5  mov     [rsp+98h+var_50], 1
0x14004d6ad  xor     r13d, r13d
0x14004d6b0  mov     ebx, r13d
0x14004d6b3  mov     edi, r13d
0x14004d6b6  test    r14, r14
0x14004d6b9  jnz     short loc_14004D732
0x14004d6bb  mov     edi, 80070057h
0x14004d6c0  mov     rax, [rsi+48h]
0x14004d6c4  lea     rcx, [rsi+48h]
0x14004d6c8  mov     rax, [rax+10h]
0x14004d6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d6d1  test    rax, rax
0x14004d6d4  jz      loc_14004D8E6
0x14004d6da  mov     rax, [rsi+48h]
0x14004d6de  lea     rcx, [rsi+48h]
0x14004d6e2  mov     rax, [rax+10h]
0x14004d6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d6eb  mov     esi, r13d
0x14004d6ee  test    rax, rax
0x14004d6f1  jz      short loc_14004D726
0x14004d6f3  mov     dword ptr [rsp+98h+cchCount2], edi
0x14004d6f7  mov     dword ptr [rsp+98h+lpString2], 80Ch
0x14004d6ff  lea     r9, aCdlpmanagerSet; "CDlpManager::SetQuadwordProperty"
0x14004d706  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004d70d  lea     edx, [r13+4]
0x14004d711  mov     rcx, rax
0x14004d714  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004d719  mov     esi, eax
0x14004d71b  test    eax, eax
0x14004d71d  jns     short loc_14004D726
0x14004d71f  mov     ecx, eax
0x14004d721  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004d726  mov     ecx, esi
0x14004d728  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004d72d  jmp     loc_14004D8E6
0x14004d732  mov     r15d, [rsi+25Ch]
0x14004d739  mov     ebp, r13d
0x14004d73c  test    r15d, r15d
0x14004d73f  jz      short loc_14004D79A
0x14004d741  mov     rax, [rsi+260h]
0x14004d748  test    rax, rax
0x14004d74b  cmovz   rax, r13
0x14004d74f  movsxd  r13, ebp
0x14004d752  mov     rax, [rax+r13*8]
0x14004d756  xor     ecx, ecx
0x14004d758  test    rax, rax
0x14004d75b  cmovz   rax, rcx
0x14004d75f  mov     dword ptr [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x14004d767  mov     [rsp+98h+lpString2], rax; lpString2
0x14004d76c  or      r9d, 0FFFFFFFFh; cchCount1
0x14004d770  mov     r8, r14; lpString1
0x14004d773  lea     edx, [rcx+1]; dwCmpFlags
0x14004d776  mov     ecx, 409h; Locale
0x14004d77b  call    cs:__imp_CompareStringW
0x14004d782  nop     dword ptr [rax+rax+00h]
0x14004d787  cmp     eax, 2
0x14004d78a  jz      loc_14004D82A
0x14004d790  inc     ebp
0x14004d792  cmp     ebp, r15d
0x14004d795  mov     r13, rbx
0x14004d798  jb      short loc_14004D741
0x14004d79a  mov     rcx, r14; psz
0x14004d79d  call    cs:__imp_SysAllocString
0x14004d7a4  nop     dword ptr [rax+rax+00h]
0x14004d7a9  test    rax, rax
0x14004d7ac  jnz     loc_14004D846
0x14004d7b2  mov     edi, 8007000Eh
0x14004d7b7  mov     rax, [rsi+48h]
0x14004d7bb  lea     rcx, [rsi+48h]
0x14004d7bf  mov     rax, [rax+10h]
0x14004d7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d7c8  test    rax, rax
0x14004d7cb  jz      loc_14004D8DE
0x14004d7d1  mov     rax, [rsi+48h]
0x14004d7d5  lea     rcx, [rsi+48h]
0x14004d7d9  mov     rax, [rax+10h]
0x14004d7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d7e2  mov     esi, r13d
0x14004d7e5  test    rax, rax
0x14004d7e8  jz      short loc_14004D81E
0x14004d7ea  mov     dword ptr [rsp+98h+cchCount2], edi
0x14004d7ee  mov     dword ptr [rsp+98h+lpString2], 821h
0x14004d7f6  lea     r9, aCdlpmanagerSet; "CDlpManager::SetQuadwordProperty"
0x14004d7fd  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004d804  mov     edx, 4
0x14004d809  mov     rcx, rax
0x14004d80c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004d811  mov     esi, eax
0x14004d813  test    eax, eax
0x14004d815  jns     short loc_14004D81E
0x14004d817  mov     ecx, eax
0x14004d819  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004d81e  mov     ecx, esi
0x14004d820  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004d825  jmp     loc_14004D8DE
0x14004d82a  mov     rax, [rsi+270h]
0x14004d831  xor     ecx, ecx
0x14004d833  test    rax, rax
0x14004d836  cmovz   rax, rcx
0x14004d83a  mov     [rax+r13*8], r12
0x14004d83e  xor     r13d, r13d
0x14004d841  jmp     loc_14004D8DE
0x14004d846  mov     [rsp+98h+arg_8], rax
0x14004d84e  lea     rcx, [rsi+258h]
0x14004d855  lea     rdx, [rsp+98h+arg_8]
0x14004d85d  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x14004d862  mov     edi, eax
0x14004d864  test    eax, eax
0x14004d866  jns     loc_14004D939
0x14004d86c  mov     rdx, [rsi+48h]
0x14004d870  lea     rcx, [rsi+48h]
0x14004d874  mov     rax, [rdx+10h]
0x14004d878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d87d  test    rax, rax
0x14004d880  jz      short loc_14004D8D6
0x14004d882  mov     rax, [rsi+48h]
0x14004d886  lea     rcx, [rsi+48h]
0x14004d88a  mov     rax, [rax+10h]
0x14004d88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d893  mov     ebx, r13d
0x14004d896  test    rax, rax
0x14004d899  jz      short loc_14004D8CF
0x14004d89b  mov     dword ptr [rsp+98h+cchCount2], edi
0x14004d89f  mov     dword ptr [rsp+98h+lpString2], 825h
0x14004d8a7  lea     r9, aCdlpmanagerSet; "CDlpManager::SetQuadwordProperty"
0x14004d8ae  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004d8b5  mov     edx, 4
0x14004d8ba  mov     rcx, rax
0x14004d8bd  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004d8c2  test    eax, eax
0x14004d8c4  mov     ebx, eax
0x14004d8c6  jns     short loc_14004D8CF
0x14004d8c8  mov     ecx, eax
0x14004d8ca  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004d8cf  mov     ecx, ebx
0x14004d8d1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004d8d6  mov     rbx, [rsp+98h+arg_8]
0x14004d8de  mov     rbp, [rsp+98h+arg_0]
0x14004d8e6  mov     ecx, edi
0x14004d8e8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004d8ed  test    rbx, rbx
0x14004d8f0  jz      short loc_14004D902
0x14004d8f2  mov     rcx, rbx; bstrString
0x14004d8f5  call    cs:__imp_SysFreeString
0x14004d8fc  nop     dword ptr [rax+rax+00h]
0x14004d901  nop
0x14004d902  mov     eax, [rsp+98h+var_50]
0x14004d906  test    eax, eax
0x14004d908  jz      short loc_14004D91E
0x14004d90a  mov     rcx, rbp; lpCriticalSection
0x14004d90d  call    cs:__imp_LeaveCriticalSection
0x14004d914  nop     dword ptr [rax+rax+00h]
0x14004d919  mov     [rsp+98h+var_50], r13d
0x14004d91e  mov     eax, edi
0x14004d920  mov     rbx, [rsp+98h+arg_10]
0x14004d928  add     rsp, 60h
0x14004d92c  pop     r15
0x14004d92e  pop     r14
0x14004d930  pop     r13
0x14004d932  pop     r12
0x14004d934  pop     rdi
0x14004d935  pop     rsi
0x14004d936  pop     rbp
0x14004d937  retn
0x14004d939  lea     rcx, [rsi+268h]
0x14004d940  mov     rdx, r12
0x14004d943  call    ?Append@?$CArray@_K_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJ_K@Z; CArray<unsigned __int64,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Append(unsigned __int64)
0x14004d948  mov     edi, eax
0x14004d94a  test    eax, eax
0x14004d94c  jns     short loc_14004D8D6
0x14004d94e  mov     rax, [rsi+48h]
0x14004d952  lea     rcx, [rsi+48h]
0x14004d956  mov     rax, [rax+10h]
0x14004d95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d95f  test    rax, rax
0x14004d962  jz      loc_14004D8D6
0x14004d968  mov     rax, [rsi+48h]
0x14004d96c  lea     rcx, [rsi+48h]
0x14004d970  mov     rax, [rax+10h]
0x14004d974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d979  mov     ebx, r13d
0x14004d97c  test    rax, rax
0x14004d97f  jz      loc_14004D8CF
0x14004d985  mov     dword ptr [rsp+98h+cchCount2], edi
0x14004d989  mov     dword ptr [rsp+98h+lpString2], 826h
0x14004d991  jmp     loc_14004D8A7
```
