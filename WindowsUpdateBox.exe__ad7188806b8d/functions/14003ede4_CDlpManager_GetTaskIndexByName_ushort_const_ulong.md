# CDlpManager::GetTaskIndexByName(ushort const *,ulong *)

- ea: `0x14003ede4`
- end: `0x14003efd8`
- name: `?GetTaskIndexByName@CDlpManager@@AEAAJPEBGPEAK@Z`
- size: `500`
- prototype: `int(CDlpManager *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400319f0`
- `0x14003ea30`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x140034ab4`
- `0x14003ede4`
- `0x140082010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14003ef2e`
- `KERNEL32!LeaveCriticalSection` at `0x14003ef2e`
- `KERNEL32!EnterCriticalSection` at `0x14003ee1b`
- `KERNEL32!EnterCriticalSection` at `0x14003ee1b`
- `KERNEL32!CompareStringW` at `0x14003eed3`
- `KERNEL32!CompareStringW` at `0x14003eed3`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ee56`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ef0f`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ee56`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ef0f`

## string_xrefs

- `0x14003efa4`: `CDlpManager::GetTaskIndexByName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpManager::GetTaskIndexByName(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r14
  OLECHAR *v7; // rax
  unsigned int RecursionCount; // ebp
  signed int v9; // edi
  _QWORD **OwningThread; // rcx
  int v11; // ebx
  __int64 v13; // rax
  unsigned int v14; // edi
  int v15; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-68h]
  __int64 cchCount2; // [rsp+28h] [rbp-60h]
  PCNZWCH v18; // [rsp+90h] [rbp+8h] BYREF

  v6 = this + 5;
  EnterCriticalSection(this + 5);
  v7 = 0;
  v18 = 0;
  RecursionCount = this[13].RecursionCount;
  v9 = 0;
  if ( !RecursionCount )
  {
LABEL_13:
    v11 = -2147023728;
    goto LABEL_14;
  }
  while ( 1 )
  {
    if ( v7 )
    {
      SysFreeString(v7);
      v18 = 0;
    }
    OwningThread = (_QWORD **)this[13].OwningThread;
    if ( !OwningThread )
      OwningThread = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD *, PCNZWCH *))(*OwningThread[v9] + 200LL))(OwningThread[v9], &v18);
    if ( v11 == -2147023728 )
    {
      v11 = 0;
      goto LABEL_9;
    }
    if ( v11 < 0 )
      break;
LABEL_9:
    v7 = (OLECHAR *)v18;
    if ( v18 )
    {
      if ( CompareStringW(0x409u, 1u, a2, -1, v18, -1) == 2 )
      {
        *a3 = v9;
        goto LABEL_14;
      }
      v7 = (OLECHAR *)v18;
    }
    if ( ++v9 >= RecursionCount )
      goto LABEL_13;
  }
  if ( ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
  {
    v13 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
    v14 = 0;
    if ( v13 )
    {
      LODWORD(cchCount2) = v11;
      LODWORD(lpString2) = 2514;
      v15 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v13,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpManager::GetTaskIndexByName",
              lpString2,
              cchCount2,
              -2);
      v14 = v15;
      if ( v15 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
  }
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( v18 )
  {
    SysFreeString((BSTR)v18);
    v18 = 0;
  }
  LeaveCriticalSection(v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14003ede4  mov     rax, rsp
0x14003ede7  push    rdi
0x14003ede8  push    r12
0x14003edea  push    r13
0x14003edec  push    r14
0x14003edee  push    r15
0x14003edf0  sub     rsp, 60h
0x14003edf4  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x14003edfc  mov     [rax+10h], rbx
0x14003ee00  mov     [rax+18h], rbp
0x14003ee04  mov     [rax+20h], rsi
0x14003ee08  mov     r15, r8
0x14003ee0b  mov     r12, rdx
0x14003ee0e  mov     rsi, rcx
0x14003ee11  lea     r14, [rcx+0C8h]
0x14003ee18  mov     rcx, r14; lpCriticalSection
0x14003ee1b  call    cs:__imp_EnterCriticalSection
0x14003ee22  nop     dword ptr [rax+rax+00h]
0x14003ee27  mov     [rsp+88h+var_40], 1
0x14003ee2f  xor     r13d, r13d
0x14003ee32  mov     eax, r13d
0x14003ee35  mov     [rsp+88h+arg_0], rax
0x14003ee3d  mov     ebp, [rsi+214h]
0x14003ee43  mov     edi, r13d
0x14003ee46  test    ebp, ebp
0x14003ee48  jz      loc_14003EEF6
0x14003ee4e  test    rax, rax
0x14003ee51  jz      short loc_14003EE6A
0x14003ee53  mov     rcx, rax; bstrString
0x14003ee56  call    cs:__imp_SysFreeString
0x14003ee5d  nop     dword ptr [rax+rax+00h]
0x14003ee62  mov     [rsp+88h+arg_0], r13
0x14003ee6a  mov     rcx, [rsi+218h]
0x14003ee71  test    rcx, rcx
0x14003ee74  cmovz   rcx, r13
0x14003ee78  movsxd  rax, edi
0x14003ee7b  mov     rcx, [rcx+rax*8]
0x14003ee7f  mov     rax, [rcx]
0x14003ee82  lea     rdx, [rsp+88h+arg_0]
0x14003ee8a  mov     rax, [rax+0C8h]
0x14003ee91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ee96  mov     ebx, eax
0x14003ee98  cmp     eax, 80070490h
0x14003ee9d  jnz     short loc_14003EEA4
0x14003ee9f  mov     ebx, r13d
0x14003eea2  jmp     short loc_14003EEAC
0x14003eea4  test    ebx, ebx
0x14003eea6  js      loc_14003EF65
0x14003eeac  mov     rax, [rsp+88h+arg_0]
0x14003eeb4  test    rax, rax
0x14003eeb7  jz      short loc_14003EEEC
0x14003eeb9  or      ecx, 0FFFFFFFFh
0x14003eebc  mov     dword ptr [rsp+88h+cchCount2], ecx; cchCount2
0x14003eec0  mov     [rsp+88h+lpString2], rax; lpString2
0x14003eec5  mov     r9d, ecx; cchCount1
0x14003eec8  mov     r8, r12; lpString1
0x14003eecb  lea     edx, [rcx+2]; dwCmpFlags
0x14003eece  mov     ecx, 409h; Locale
0x14003eed3  call    cs:__imp_CompareStringW
0x14003eeda  nop     dword ptr [rax+rax+00h]
0x14003eedf  cmp     eax, 2
0x14003eee2  jz      short loc_14003EF60
0x14003eee4  mov     rax, [rsp+88h+arg_0]
0x14003eeec  inc     edi
0x14003eeee  cmp     edi, ebp
0x14003eef0  jb      loc_14003EE4E
0x14003eef6  mov     ebx, 80070490h
0x14003eefb  mov     ecx, ebx
0x14003eefd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14003ef02  mov     rcx, [rsp+88h+arg_0]; bstrString
0x14003ef0a  test    rcx, rcx
0x14003ef0d  jz      short loc_14003EF23
0x14003ef0f  call    cs:__imp_SysFreeString
0x14003ef16  nop     dword ptr [rax+rax+00h]
0x14003ef1b  mov     [rsp+88h+arg_0], r13
0x14003ef23  mov     edx, [rsp+88h+var_40]
0x14003ef27  test    edx, edx
0x14003ef29  jz      short loc_14003EF3F
0x14003ef2b  mov     rcx, r14; lpCriticalSection
0x14003ef2e  call    cs:__imp_LeaveCriticalSection
0x14003ef35  nop     dword ptr [rax+rax+00h]
0x14003ef3a  mov     [rsp+88h+var_40], r13d
0x14003ef3f  mov     eax, ebx
0x14003ef41  lea     r11, [rsp+88h+var_28]
0x14003ef46  mov     rbx, [r11+38h]
0x14003ef4a  mov     rbp, [r11+40h]
0x14003ef4e  mov     rsi, [r11+48h]
0x14003ef52  mov     rsp, r11
0x14003ef55  pop     r15
0x14003ef57  pop     r14
0x14003ef59  pop     r13
0x14003ef5b  pop     r12
0x14003ef5d  pop     rdi
0x14003ef5e  retn
0x14003ef60  mov     [r15], edi
0x14003ef63  jmp     short loc_14003EEFB
0x14003ef65  lea     rdi, [rsi+50h]
0x14003ef69  mov     rax, [rdi]
0x14003ef6c  mov     rcx, rdi
0x14003ef6f  mov     rax, [rax+10h]
0x14003ef73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ef78  test    rax, rax
0x14003ef7b  jz      loc_14003EEFB
0x14003ef81  mov     rax, [rdi]
0x14003ef84  mov     rcx, rdi
0x14003ef87  mov     rax, [rax+10h]
0x14003ef8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ef90  mov     edi, r13d
0x14003ef93  test    rax, rax
0x14003ef96  jz      short loc_14003EFCC
0x14003ef98  mov     dword ptr [rsp+88h+cchCount2], ebx
0x14003ef9c  mov     dword ptr [rsp+88h+lpString2], 9D2h
0x14003efa4  lea     r9, aCdlpmanagerGet_15; "CDlpManager::GetTaskIndexByName"
0x14003efab  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14003efb2  mov     edx, 4
0x14003efb7  mov     rcx, rax
0x14003efba  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14003efbf  mov     edi, eax
0x14003efc1  test    eax, eax
0x14003efc3  jns     short loc_14003EFCC
0x14003efc5  mov     ecx, eax
0x14003efc7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14003efcc  mov     ecx, edi
0x14003efce  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14003efd3  jmp     loc_14003EEFB
```
