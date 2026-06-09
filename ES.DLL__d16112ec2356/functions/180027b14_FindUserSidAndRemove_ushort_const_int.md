# FindUserSidAndRemove(ushort const *,int *)

- ea: `0x180027b14`
- end: `0x180027bae`
- name: `?FindUserSidAndRemove@@YAJPEBGPEAH@Z`
- size: `154`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180027aa0`

## callees

- `0x180027b14`
- `0x180033e2c`
- `0x1800340f8`
- `0x180034374`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027b96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027b96`

## pseudocode

```c
__int64 __fastcall FindUserSidAndRemove(const unsigned __int16 *a1, int *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  void *v3; // rbx
  __int64 v5; // rax
  const unsigned __int16 *v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v7 = a1;
  v2 = (struct _RTL_CRITICAL_SECTION *)g_pLogOnLogOff;
  v3 = 0;
  *a2 = 0;
  if ( v2 )
  {
    EnterCriticalSection(v2 + 1);
    v8 = 0;
    if ( (unsigned int)Map<unsigned short const *,unsigned short const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::find(
                         g_pLogOnLogOff,
                         &v7,
                         &v8) )
    {
      v5 = v8;
      *a2 = 1;
      v3 = *(void **)(*(_QWORD *)v5 + 40LL);
      Map<unsigned short const *,unsigned short const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::remove(
        g_pLogOnLogOff,
        &v7);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)g_pLogOnLogOff + 1);
    CoTaskMemFree(v3);
    ReleaseReferenceOnList();
  }
  return 0;
}

```

## disassembly

```asm
0x180027b14  mov     [rsp+arg_10], rbx
0x180027b19  mov     [rsp+arg_0], rcx
0x180027b1e  push    rdi
0x180027b1f  sub     rsp, 20h
0x180027b23  mov     rcx, cs:?g_pLogOnLogOff@@3PECULogOnLogOffList@@EC; LogOnLogOffList volatile * volatile g_pLogOnLogOff
0x180027b2a  xor     ebx, ebx
0x180027b2c  mov     [rdx], ebx
0x180027b2e  mov     rdi, rdx
0x180027b31  test    rcx, rcx
0x180027b34  jz      short loc_180027BA1
0x180027b36  add     rcx, 28h ; '('; lpCriticalSection
0x180027b3a  call    cs:__imp_EnterCriticalSection
0x180027b40  mov     rcx, cs:?g_pLogOnLogOff@@3PECULogOnLogOffList@@EC; LogOnLogOffList volatile * volatile g_pLogOnLogOff
0x180027b47  lea     r8, [rsp+28h+arg_8]
0x180027b4c  lea     rdx, [rsp+28h+arg_0]
0x180027b51  mov     [rsp+28h+arg_8], rbx
0x180027b56  call    ?find@?$Map@PEBGPEBGVHashCaseInsentitiveWSTR@LogOnLogOffList@@VCNonFailFastingAllocator@2@@@AEBAHAEBQEBGPEAPEAPEAVAssoc@1@@Z; Map<ushort const *,ushort const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::find(ushort const * const &,Map<ushort const *,ushort const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::Assoc * * *)
0x180027b5b  test    eax, eax
0x180027b5d  jz      short loc_180027B82
0x180027b5f  mov     rax, [rsp+28h+arg_8]
0x180027b64  lea     rdx, [rsp+28h+arg_0]
0x180027b69  mov     dword ptr [rdi], 1
0x180027b6f  mov     rcx, [rax]
0x180027b72  mov     rbx, [rcx+28h]
0x180027b76  mov     rcx, cs:?g_pLogOnLogOff@@3PECULogOnLogOffList@@EC; LogOnLogOffList volatile * volatile g_pLogOnLogOff
0x180027b7d  call    ?remove@?$Map@PEBGPEBGVHashCaseInsentitiveWSTR@LogOnLogOffList@@VCNonFailFastingAllocator@2@@@QEAAXAEBQEBG@Z; Map<ushort const *,ushort const *,LogOnLogOffList::HashCaseInsentitiveWSTR,LogOnLogOffList::CNonFailFastingAllocator>::remove(ushort const * const &)
0x180027b82  mov     rcx, cs:?g_pLogOnLogOff@@3PECULogOnLogOffList@@EC; LogOnLogOffList volatile * volatile g_pLogOnLogOff
0x180027b89  add     rcx, 28h ; '('; lpCriticalSection
0x180027b8d  call    cs:__imp_LeaveCriticalSection
0x180027b93  mov     rcx, rbx; pv
0x180027b96  call    cs:__imp_CoTaskMemFree
0x180027b9c  call    ?ReleaseReferenceOnList@@YAXXZ; ReleaseReferenceOnList(void)
0x180027ba1  mov     rbx, [rsp+28h+arg_10]
0x180027ba6  xor     eax, eax
0x180027ba8  add     rsp, 20h
0x180027bac  pop     rdi
0x180027bad  retn
```
