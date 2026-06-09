# CUserModeHangReport::Cleanup(void)

- ea: `0x140024220`
- end: `0x140024303`
- name: `?Cleanup@CUserModeHangReport@@MEAAXXZ`
- size: `227`
- prototype: `void __fastcall(CUserModeHangReport *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140023dc8`

## callees

- `0x14001ecd0`
- `0x1400207c4`
- `0x140024220`
- `0x140025780`
- `0x14003536c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400242eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400242eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002426b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002426b`
- `wer!WerpFlushImageCache` at `0x1400242c0`
- `wer!WerpFlushImageCache` at `0x1400242c0`
- `wer!WerpFreeUnmappedVaRanges` at `0x1400242a2`
- `wer!WerpFreeUnmappedVaRanges` at `0x1400242a2`
- `wer!WerpAuxmdFree` at `0x14002428f`
- `wer!WerpAuxmdFree` at `0x14002428f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CUserModeHangReport::Cleanup(RTL_SRWLOCK *this)
{
  __int64 i; // rdi
  PVOID Ptr; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-18h] BYREF
  char v5; // [rsp+28h] [rbp-10h]

  CHangReport::Lock((__int64)this, (__int64)&lpCriticalSection, (int)L"CUserModeHangReport::Cleanup");
  HamConnector::Disconnect(this + 3134);
  for ( i = 0; i != 16; ++i )
  {
    Ptr = this[i + 3118].Ptr;
    this[i + 3118].Ptr = 0;
    if ( (unsigned __int64)Ptr + 1 > 1 )
      CloseHandle(Ptr);
  }
  CUserModeHangReport::ResumeSuspendedAuxiliaryProcesses((CUserModeHangReport *)this);
  WerpAuxmdFree(&this[4647]);
  WerpFreeUnmappedVaRanges(&this[4643]);
  if ( LODWORD(this[5272].Ptr) )
  {
    WerpFlushImageCache((struct WERP_IMAGE_CACHE *)&this[5171], 0);
    LODWORD(this[5272].Ptr) = 0;
  }
  CHangReport::Cleanup((CPluginList **)this);
  if ( v5 )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x140024220  mov     [rsp+arg_0], rbx
0x140024225  push    rdi
0x140024226  sub     rsp, 30h
0x14002422a  mov     rbx, rcx
0x14002422d  lea     r8, aCusermodehangr_0; "CUserModeHangReport::Cleanup"
0x140024234  lea     rdx, [rsp+38h+lpCriticalSection]
0x140024239  call    ?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z; CHangReport::Lock(wchar_t const *)
0x14002423e  nop
0x14002423f  lea     rcx, [rbx+61F0h]; SRWLock
0x140024246  call    ?Disconnect@HamConnector@@QEAAJXZ; HamConnector::Disconnect(void)
0x14002424b  xor     edi, edi
0x14002424d  mov     rcx, [rbx+rdi*8+6170h]; hObject
0x140024255  mov     qword ptr [rbx+rdi*8+6170h], 0
0x140024261  lea     rax, [rcx+1]
0x140024265  cmp     rax, 1
0x140024269  jbe     short loc_140024277
0x14002426b  call    cs:__imp_CloseHandle
0x140024272  nop     dword ptr [rax+rax+00h]
0x140024277  inc     rdi
0x14002427a  cmp     rdi, 10h
0x14002427e  jnz     short loc_14002424D
0x140024280  mov     rcx, rbx; this
0x140024283  call    ?ResumeSuspendedAuxiliaryProcesses@CUserModeHangReport@@AEAAXXZ; CUserModeHangReport::ResumeSuspendedAuxiliaryProcesses(void)
0x140024288  lea     rcx, [rbx+9138h]
0x14002428f  call    cs:__imp_WerpAuxmdFree
0x140024296  nop     dword ptr [rax+rax+00h]
0x14002429b  lea     rcx, [rbx+9118h]
0x1400242a2  call    cs:__imp_WerpFreeUnmappedVaRanges
0x1400242a9  nop     dword ptr [rax+rax+00h]
0x1400242ae  cmp     dword ptr [rbx+0A4C0h], 0
0x1400242b5  jz      short loc_1400242D6
0x1400242b7  lea     rcx, [rbx+0A198h]
0x1400242be  xor     edx, edx
0x1400242c0  call    cs:__imp_?WerpFlushImageCache@@YAKPEAUWERP_IMAGE_CACHE@@K@Z; WerpFlushImageCache(WERP_IMAGE_CACHE *,ulong)
0x1400242c7  nop     dword ptr [rax+rax+00h]
0x1400242cc  mov     dword ptr [rbx+0A4C0h], 0
0x1400242d6  mov     rcx, rbx; this
0x1400242d9  call    ?Cleanup@CHangReport@@MEAAXXZ; CHangReport::Cleanup(void)
0x1400242de  nop
0x1400242df  cmp     [rsp+38h+var_10], 0
0x1400242e4  jz      short loc_1400242F7
0x1400242e6  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1400242eb  call    cs:__imp_LeaveCriticalSection
0x1400242f2  nop     dword ptr [rax+rax+00h]
0x1400242f7  mov     rbx, [rsp+38h+arg_0]
0x1400242fc  add     rsp, 30h
0x140024300  pop     rdi
0x140024301  retn
```
