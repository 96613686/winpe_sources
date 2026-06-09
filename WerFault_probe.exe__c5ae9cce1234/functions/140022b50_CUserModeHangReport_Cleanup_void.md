# CUserModeHangReport::Cleanup(void)

- ea: `0x140022b50`
- end: `0x140022c14`
- name: `?Cleanup@CUserModeHangReport@@MEAAXXZ`
- size: `196`
- prototype: `void __fastcall(CUserModeHangReport *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140022728`

## callees

- `0x14001d800`
- `0x14001f200`
- `0x140022b50`
- `0x140023fb4`
- `0x140032fb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140022c03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140022c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022b9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022b9b`
- `wer!WerpFlushImageCache` at `0x140022bde`
- `wer!WerpFlushImageCache` at `0x140022bde`
- `wer!WerpFreeUnmappedVaRanges` at `0x140022bc6`
- `wer!WerpFreeUnmappedVaRanges` at `0x140022bc6`
- `wer!WerpAuxmdFree` at `0x140022bb9`
- `wer!WerpAuxmdFree` at `0x140022bb9`

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
0x140022b50  mov     [rsp+arg_0], rbx
0x140022b55  push    rdi
0x140022b56  sub     rsp, 30h
0x140022b5a  mov     rbx, rcx
0x140022b5d  lea     r8, aCusermodehangr_0; "CUserModeHangReport::Cleanup"
0x140022b64  lea     rdx, [rsp+38h+lpCriticalSection]
0x140022b69  call    ?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z; CHangReport::Lock(wchar_t const *)
0x140022b6e  nop
0x140022b6f  lea     rcx, [rbx+61F0h]; SRWLock
0x140022b76  call    ?Disconnect@HamConnector@@QEAAJXZ; HamConnector::Disconnect(void)
0x140022b7b  xor     edi, edi
0x140022b7d  mov     rcx, [rbx+rdi*8+6170h]; hObject
0x140022b85  mov     qword ptr [rbx+rdi*8+6170h], 0
0x140022b91  lea     rax, [rcx+1]
0x140022b95  cmp     rax, 1
0x140022b99  jbe     short loc_140022BA1
0x140022b9b  call    cs:__imp_CloseHandle
0x140022ba1  inc     rdi
0x140022ba4  cmp     rdi, 10h
0x140022ba8  jnz     short loc_140022B7D
0x140022baa  mov     rcx, rbx; this
0x140022bad  call    ?ResumeSuspendedAuxiliaryProcesses@CUserModeHangReport@@AEAAXXZ; CUserModeHangReport::ResumeSuspendedAuxiliaryProcesses(void)
0x140022bb2  lea     rcx, [rbx+9138h]
0x140022bb9  call    cs:__imp_WerpAuxmdFree
0x140022bbf  lea     rcx, [rbx+9118h]
0x140022bc6  call    cs:__imp_WerpFreeUnmappedVaRanges
0x140022bcc  cmp     dword ptr [rbx+0A4C0h], 0
0x140022bd3  jz      short loc_140022BEE
0x140022bd5  lea     rcx, [rbx+0A198h]
0x140022bdc  xor     edx, edx
0x140022bde  call    cs:__imp_?WerpFlushImageCache@@YAKPEAUWERP_IMAGE_CACHE@@K@Z; WerpFlushImageCache(WERP_IMAGE_CACHE *,ulong)
0x140022be4  mov     dword ptr [rbx+0A4C0h], 0
0x140022bee  mov     rcx, rbx; this
0x140022bf1  call    ?Cleanup@CHangReport@@MEAAXXZ; CHangReport::Cleanup(void)
0x140022bf6  nop
0x140022bf7  cmp     [rsp+38h+var_10], 0
0x140022bfc  jz      short loc_140022C09
0x140022bfe  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x140022c03  call    cs:__imp_LeaveCriticalSection
0x140022c09  mov     rbx, [rsp+38h+arg_0]
0x140022c0e  add     rsp, 30h
0x140022c12  pop     rdi
0x140022c13  retn
```
