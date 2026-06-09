# CDlpManager::SetDwordProperty(ushort const *,ulong)

- ea: `0x14004c540`
- end: `0x14004c876`
- name: `?SetDwordProperty@CDlpManager@@UEAAJPEBGK@Z`
- size: `822`
- prototype: `int(CDlpManager *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002bc70`
- `0x14002c158`
- `0x140034ab4`
- `0x14004c540`
- `0x140082010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14004c7ed`
- `KERNEL32!LeaveCriticalSection` at `0x14004c7ed`
- `KERNEL32!EnterCriticalSection` at `0x14004c579`
- `KERNEL32!EnterCriticalSection` at `0x14004c579`
- `KERNEL32!CompareStringW` at `0x14004c65b`
- `KERNEL32!CompareStringW` at `0x14004c65b`
- `OLEAUT32!__imp_SysAllocString` at `0x14004c67d`
- `OLEAUT32!__imp_SysAllocString` at `0x14004c67d`
- `OLEAUT32!__imp_SysFreeString` at `0x14004c7d5`
- `OLEAUT32!__imp_SysFreeString` at `0x14004c7d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpManager::SetDwordProperty(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  OLECHAR *v7; // rbx
  int v8; // edi
  __int64 v9; // rax
  unsigned int v10; // esi
  int v11; // eax
  unsigned int RecursionCount; // r15d
  int v13; // ebp
  _QWORD *OwningThread; // rax
  const WCHAR *v15; // rax
  BSTR v16; // rax
  __int64 v17; // rax
  unsigned int v18; // esi
  int v19; // eax
  ULONG_PTR SpinCount; // rax
  __int64 v21; // rax
  unsigned int v22; // ebx
  int v23; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-78h]
  __int64 cchCount2; // [rsp+28h] [rbp-70h]
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+A0h] [rbp+8h]
  OLECHAR *v28; // [rsp+A8h] [rbp+10h] BYREF

  v6 = this + 9;
  v27 = this + 9;
  EnterCriticalSection(this + 9);
  v7 = 0;
  v8 = 0;
  if ( a2 )
  {
    RecursionCount = this[14].RecursionCount;
    v13 = 0;
    if ( RecursionCount )
    {
      while ( 1 )
      {
        OwningThread = this[14].OwningThread;
        if ( !OwningThread )
          OwningThread = 0;
        v15 = (const WCHAR *)OwningThread[v13];
        if ( !v15 )
          v15 = 0;
        if ( CompareStringW(0x409u, 1u, a2, -1, v15, -1) == 2 )
          break;
        if ( ++v13 >= RecursionCount )
          goto LABEL_14;
      }
      SpinCount = this[14].SpinCount;
      if ( !SpinCount )
        SpinCount = 0;
      *(_DWORD *)(SpinCount + 4LL * v13) = a3;
      goto LABEL_31;
    }
LABEL_14:
    v16 = SysAllocString(a2);
    if ( !v16 )
    {
      v8 = -2147024882;
      if ( (*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount) )
      {
        v17 = (*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount);
        v18 = 0;
        if ( v17 )
        {
          LODWORD(cchCount2) = -2147024882;
          LODWORD(lpString2) = 1806;
          v19 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v17,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpManager::SetDwordProperty",
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
    v8 = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(&this[14].LockCount, &v28);
    if ( v8 >= 0 )
    {
      v8 = CArray<unsigned long,unsigned long,CAdaptorDefault,CPoliciesDefault>::Append(&this[14].LockSemaphore, a3);
      if ( v8 >= 0 || !(*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount) )
        goto LABEL_30;
      v21 = (*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount);
      v22 = 0;
      if ( !v21 )
        goto LABEL_29;
      LODWORD(cchCount2) = v8;
      LODWORD(lpString2) = 1811;
    }
    else
    {
      if ( !(*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount) )
      {
LABEL_30:
        v7 = v28;
LABEL_31:
        v6 = v27;
        goto LABEL_32;
      }
      v21 = (*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount);
      v22 = 0;
      if ( !v21 )
      {
LABEL_29:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v22);
        goto LABEL_30;
      }
      LODWORD(cchCount2) = v8;
      LODWORD(lpString2) = 1810;
    }
    v23 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v21,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpManager::SetDwordProperty",
            lpString2,
            cchCount2,
            -2);
    v22 = v23;
    if ( v23 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
    goto LABEL_29;
  }
  v8 = -2147024809;
  if ( (*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount) )
  {
    v9 = (*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount);
    v10 = 0;
    if ( v9 )
    {
      v11 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v9,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpManager::SetDwordProperty",
              1785,
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
0x14004c540  mov     rax, rsp
0x14004c543  push    rbp
0x14004c544  push    rsi
0x14004c545  push    rdi
0x14004c546  push    r12
0x14004c548  push    r13
0x14004c54a  push    r14
0x14004c54c  push    r15
0x14004c54e  sub     rsp, 60h
0x14004c552  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x14004c55a  mov     [rax+18h], rbx
0x14004c55e  mov     r12d, r8d
0x14004c561  mov     r14, rdx
0x14004c564  mov     rsi, rcx
0x14004c567  lea     rbp, [rcx+168h]
0x14004c56e  mov     [rsp+98h+arg_0], rbp
0x14004c576  mov     rcx, rbp; lpCriticalSection
0x14004c579  call    cs:__imp_EnterCriticalSection
0x14004c580  nop     dword ptr [rax+rax+00h]
0x14004c585  mov     [rsp+98h+var_50], 1
0x14004c58d  xor     r13d, r13d
0x14004c590  mov     ebx, r13d
0x14004c593  mov     edi, r13d
0x14004c596  test    r14, r14
0x14004c599  jnz     short loc_14004C612
0x14004c59b  mov     edi, 80070057h
0x14004c5a0  mov     rax, [rsi+48h]
0x14004c5a4  lea     rcx, [rsi+48h]
0x14004c5a8  mov     rax, [rax+10h]
0x14004c5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c5b1  test    rax, rax
0x14004c5b4  jz      loc_14004C7C6
0x14004c5ba  mov     rax, [rsi+48h]
0x14004c5be  lea     rcx, [rsi+48h]
0x14004c5c2  mov     rax, [rax+10h]
0x14004c5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c5cb  mov     esi, r13d
0x14004c5ce  test    rax, rax
0x14004c5d1  jz      short loc_14004C606
0x14004c5d3  mov     dword ptr [rsp+98h+cchCount2], edi
0x14004c5d7  mov     dword ptr [rsp+98h+lpString2], 6F9h
0x14004c5df  lea     r9, aCdlpmanagerSet_0; "CDlpManager::SetDwordProperty"
0x14004c5e6  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004c5ed  lea     edx, [r13+4]
0x14004c5f1  mov     rcx, rax
0x14004c5f4  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004c5f9  mov     esi, eax
0x14004c5fb  test    eax, eax
0x14004c5fd  jns     short loc_14004C606
0x14004c5ff  mov     ecx, eax
0x14004c601  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004c606  mov     ecx, esi
0x14004c608  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004c60d  jmp     loc_14004C7C6
0x14004c612  mov     r15d, [rsi+23Ch]
0x14004c619  mov     ebp, r13d
0x14004c61c  test    r15d, r15d
0x14004c61f  jz      short loc_14004C67A
0x14004c621  mov     rax, [rsi+240h]
0x14004c628  test    rax, rax
0x14004c62b  cmovz   rax, r13
0x14004c62f  movsxd  r13, ebp
0x14004c632  mov     rax, [rax+r13*8]
0x14004c636  xor     ecx, ecx
0x14004c638  test    rax, rax
0x14004c63b  cmovz   rax, rcx
0x14004c63f  mov     dword ptr [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x14004c647  mov     [rsp+98h+lpString2], rax; lpString2
0x14004c64c  or      r9d, 0FFFFFFFFh; cchCount1
0x14004c650  mov     r8, r14; lpString1
0x14004c653  lea     edx, [rcx+1]; dwCmpFlags
0x14004c656  mov     ecx, 409h; Locale
0x14004c65b  call    cs:__imp_CompareStringW
0x14004c662  nop     dword ptr [rax+rax+00h]
0x14004c667  cmp     eax, 2
0x14004c66a  jz      loc_14004C70A
0x14004c670  inc     ebp
0x14004c672  cmp     ebp, r15d
0x14004c675  mov     r13, rbx
0x14004c678  jb      short loc_14004C621
0x14004c67a  mov     rcx, r14; psz
0x14004c67d  call    cs:__imp_SysAllocString
0x14004c684  nop     dword ptr [rax+rax+00h]
0x14004c689  test    rax, rax
0x14004c68c  jnz     loc_14004C726
0x14004c692  mov     edi, 8007000Eh
0x14004c697  mov     rax, [rsi+48h]
0x14004c69b  lea     rcx, [rsi+48h]
0x14004c69f  mov     rax, [rax+10h]
0x14004c6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c6a8  test    rax, rax
0x14004c6ab  jz      loc_14004C7BE
0x14004c6b1  mov     rax, [rsi+48h]
0x14004c6b5  lea     rcx, [rsi+48h]
0x14004c6b9  mov     rax, [rax+10h]
0x14004c6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c6c2  mov     esi, r13d
0x14004c6c5  test    rax, rax
0x14004c6c8  jz      short loc_14004C6FE
0x14004c6ca  mov     dword ptr [rsp+98h+cchCount2], edi
0x14004c6ce  mov     dword ptr [rsp+98h+lpString2], 70Eh
0x14004c6d6  lea     r9, aCdlpmanagerSet_0; "CDlpManager::SetDwordProperty"
0x14004c6dd  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004c6e4  mov     edx, 4
0x14004c6e9  mov     rcx, rax
0x14004c6ec  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004c6f1  mov     esi, eax
0x14004c6f3  test    eax, eax
0x14004c6f5  jns     short loc_14004C6FE
0x14004c6f7  mov     ecx, eax
0x14004c6f9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004c6fe  mov     ecx, esi
0x14004c700  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004c705  jmp     loc_14004C7BE
0x14004c70a  mov     rax, [rsi+250h]
0x14004c711  xor     ecx, ecx
0x14004c713  test    rax, rax
0x14004c716  cmovz   rax, rcx
0x14004c71a  mov     [rax+r13*4], r12d
0x14004c71e  xor     r13d, r13d
0x14004c721  jmp     loc_14004C7BE
0x14004c726  mov     [rsp+98h+arg_8], rax
0x14004c72e  lea     rcx, [rsi+238h]
0x14004c735  lea     rdx, [rsp+98h+arg_8]
0x14004c73d  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x14004c742  mov     edi, eax
0x14004c744  test    eax, eax
0x14004c746  jns     loc_14004C819
0x14004c74c  mov     rdx, [rsi+48h]
0x14004c750  lea     rcx, [rsi+48h]
0x14004c754  mov     rax, [rdx+10h]
0x14004c758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c75d  test    rax, rax
0x14004c760  jz      short loc_14004C7B6
0x14004c762  mov     rax, [rsi+48h]
0x14004c766  lea     rcx, [rsi+48h]
0x14004c76a  mov     rax, [rax+10h]
0x14004c76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c773  mov     ebx, r13d
0x14004c776  test    rax, rax
0x14004c779  jz      short loc_14004C7AF
0x14004c77b  mov     dword ptr [rsp+98h+cchCount2], edi
0x14004c77f  mov     dword ptr [rsp+98h+lpString2], 712h
0x14004c787  lea     r9, aCdlpmanagerSet_0; "CDlpManager::SetDwordProperty"
0x14004c78e  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14004c795  mov     edx, 4
0x14004c79a  mov     rcx, rax
0x14004c79d  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004c7a2  test    eax, eax
0x14004c7a4  mov     ebx, eax
0x14004c7a6  jns     short loc_14004C7AF
0x14004c7a8  mov     ecx, eax
0x14004c7aa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14004c7af  mov     ecx, ebx
0x14004c7b1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004c7b6  mov     rbx, [rsp+98h+arg_8]
0x14004c7be  mov     rbp, [rsp+98h+arg_0]
0x14004c7c6  mov     ecx, edi
0x14004c7c8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14004c7cd  test    rbx, rbx
0x14004c7d0  jz      short loc_14004C7E2
0x14004c7d2  mov     rcx, rbx; bstrString
0x14004c7d5  call    cs:__imp_SysFreeString
0x14004c7dc  nop     dword ptr [rax+rax+00h]
0x14004c7e1  nop
0x14004c7e2  mov     eax, [rsp+98h+var_50]
0x14004c7e6  test    eax, eax
0x14004c7e8  jz      short loc_14004C7FE
0x14004c7ea  mov     rcx, rbp; lpCriticalSection
0x14004c7ed  call    cs:__imp_LeaveCriticalSection
0x14004c7f4  nop     dword ptr [rax+rax+00h]
0x14004c7f9  mov     [rsp+98h+var_50], r13d
0x14004c7fe  mov     eax, edi
0x14004c800  mov     rbx, [rsp+98h+arg_10]
0x14004c808  add     rsp, 60h
0x14004c80c  pop     r15
0x14004c80e  pop     r14
0x14004c810  pop     r13
0x14004c812  pop     r12
0x14004c814  pop     rdi
0x14004c815  pop     rsi
0x14004c816  pop     rbp
0x14004c817  retn
0x14004c819  lea     rcx, [rsi+248h]
0x14004c820  mov     edx, r12d
0x14004c823  call    ?Append@?$CArray@KKVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJK@Z; CArray<ulong,ulong,CAdaptorDefault,CPoliciesDefault>::Append(ulong)
0x14004c828  mov     edi, eax
0x14004c82a  test    eax, eax
0x14004c82c  jns     short loc_14004C7B6
0x14004c82e  mov     rax, [rsi+48h]
0x14004c832  lea     rcx, [rsi+48h]
0x14004c836  mov     rax, [rax+10h]
0x14004c83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c83f  test    rax, rax
0x14004c842  jz      loc_14004C7B6
0x14004c848  mov     rax, [rsi+48h]
0x14004c84c  lea     rcx, [rsi+48h]
0x14004c850  mov     rax, [rax+10h]
0x14004c854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c859  mov     ebx, r13d
0x14004c85c  test    rax, rax
0x14004c85f  jz      loc_14004C7AF
0x14004c865  mov     dword ptr [rsp+98h+cchCount2], edi
0x14004c869  mov     dword ptr [rsp+98h+lpString2], 713h
0x14004c871  jmp     loc_14004C787
```
