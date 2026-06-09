# CApplicationManager::ResetProcessDataFlowAccessCheckResults(ushort const *,ushort const *)

- ea: `0x18003cd84`
- end: `0x18003ce42`
- name: `?ResetProcessDataFlowAccessCheckResults@CApplicationManager@@QEAAXPEBG0@Z`
- size: `190`
- prototype: `void(CApplicationManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180044bd0`

## callees

- `0x18001b750`
- `0x18002cb40`
- `0x18003cd84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cda5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cda5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ce33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ce33`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003cde7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003ce10`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003cde7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003ce10`

## pseudocode

```c
void __fastcall CApplicationManager::ResetProcessDataFlowAccessCheckResults(
        CApplicationManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  CApplicationManager *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  __int64 v7; // rcx
  LPCWCH *v8; // rbx
  CApplicationManager *v9; // [rsp+60h] [rbp+8h] BYREF

  v9 = this;
  v3 = g_ApplicationManager;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)g_ApplicationManager + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_ApplicationManager + 32));
  v9 = (CApplicationManager *)*((_QWORD *)v3 + 16);
  while ( v9 )
  {
    v8 = *(LPCWCH **)ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::GetNext(v7, &v9);
    if ( (!a2 || CompareStringOrdinal(a2, -1, v8[25], -1, 1) == 2)
      && (!a3 || CompareStringOrdinal(a3, -1, v8[23], -1, 1) == 2) )
    {
      CProcess::ResetDataFlowAccessCheckResults((CProcess *)v8);
    }
  }
  if ( v6 )
    LeaveCriticalSection(v6);
}

```

## disassembly

```asm
0x18003cd84  mov     [rsp+arg_0], rcx
0x18003cd89  push    rbx
0x18003cd8a  push    rbp
0x18003cd8b  push    rsi
0x18003cd8c  push    rdi
0x18003cd8d  sub     rsp, 38h
0x18003cd91  mov     rbx, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x18003cd98  mov     rsi, r8
0x18003cd9b  mov     rbp, rdx
0x18003cd9e  lea     rdi, [rbx+20h]
0x18003cda2  mov     rcx, rdi; lpCriticalSection
0x18003cda5  call    cs:__imp_EnterCriticalSection
0x18003cdab  mov     rax, [rbx+80h]
0x18003cdb2  mov     [rsp+58h+arg_0], rax
0x18003cdb7  test    rax, rax
0x18003cdba  jz      short loc_18003CE2B
0x18003cdbc  lea     rdx, [rsp+58h+arg_0]
0x18003cdc1  call    ?GetNext@?$CAtlList@PEAVCProcess@@V?$CElementTraits@PEAVCProcess@@@ATL@@@ATL@@QEAAAEAPEAVCProcess@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::GetNext(__POSITION * &)
0x18003cdc6  mov     rbx, [rax]
0x18003cdc9  test    rbp, rbp
0x18003cdcc  jz      short loc_18003CDF2
0x18003cdce  mov     r8, [rbx+0C8h]; lpString2
0x18003cdd5  or      r9d, 0FFFFFFFFh; cchCount2
0x18003cdd9  or      edx, r9d; cchCount1
0x18003cddc  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18003cde4  mov     rcx, rbp; lpString1
0x18003cde7  call    cs:__imp_CompareStringOrdinal
0x18003cded  cmp     eax, 2
0x18003cdf0  jnz     short loc_18003CE23
0x18003cdf2  test    rsi, rsi
0x18003cdf5  jz      short loc_18003CE1B
0x18003cdf7  mov     r8, [rbx+0B8h]; lpString2
0x18003cdfe  or      r9d, 0FFFFFFFFh; cchCount2
0x18003ce02  or      edx, r9d; cchCount1
0x18003ce05  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18003ce0d  mov     rcx, rsi; lpString1
0x18003ce10  call    cs:__imp_CompareStringOrdinal
0x18003ce16  cmp     eax, 2
0x18003ce19  jnz     short loc_18003CE23
0x18003ce1b  mov     rcx, rbx; this
0x18003ce1e  call    ?ResetDataFlowAccessCheckResults@CProcess@@QEAAXXZ; CProcess::ResetDataFlowAccessCheckResults(void)
0x18003ce23  cmp     [rsp+58h+arg_0], 0
0x18003ce29  jnz     short loc_18003CDBC
0x18003ce2b  test    rdi, rdi
0x18003ce2e  jz      short loc_18003CE39
0x18003ce30  mov     rcx, rdi; lpCriticalSection
0x18003ce33  call    cs:__imp_LeaveCriticalSection
0x18003ce39  add     rsp, 38h
0x18003ce3d  pop     rdi
0x18003ce3e  pop     rsi
0x18003ce3f  pop     rbp
0x18003ce40  pop     rbx
0x18003ce41  retn
```
