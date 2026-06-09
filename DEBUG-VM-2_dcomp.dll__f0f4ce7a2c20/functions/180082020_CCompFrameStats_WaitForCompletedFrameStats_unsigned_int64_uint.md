# CCompFrameStats::WaitForCompletedFrameStats(unsigned __int64,uint)

- ea: `0x180082020`
- end: `0x180082099`
- name: `?WaitForCompletedFrameStats@CCompFrameStats@@IEAA_N_KI@Z`
- size: `121`
- prototype: `bool __fastcall(CCompFrameStats *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180082530`

## callees

- `0x180082020`
- `0x1800827d0`

## import_xrefs

- `win32u!NtDCompositionSyncWait` at `0x180082066`
- `win32u!NtDCompositionSyncWait` at `0x180082066`
- `win32u!NtDCompositionGetFrameId` at `0x180082050`
- `win32u!NtDCompositionGetFrameId` at `0x180082050`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180082079`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180082079`

## pseudocode

```c
char __fastcall CCompFrameStats::WaitForCompletedFrameStats(CCompFrameStats *this, unsigned __int64 a2)
{
  unsigned int v3; // ebx
  int FrameId; // eax
  unsigned __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( a2 > *((_QWORD *)this + 16) )
  {
    v3 = 0;
    while ( 1 )
    {
      v6 = 0;
      FrameId = NtDCompositionGetFrameId(2, &v6);
      if ( (int)DirectComposition::CDevice::HRESULTFromNTSTATUS(FrameId) >= 0 && v6 >= a2 )
        break;
      NtDCompositionSyncWait(1);
      v3 += 5;
      if ( v3 > 0x32 )
        return 0;
      Sleep(5u);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180082020  mov     [rsp+arg_8], rbx
0x180082025  push    rdi
0x180082026  sub     rsp, 20h
0x18008202a  mov     rdi, rdx
0x18008202d  cmp     rdx, [rcx+80h]
0x180082034  jbe     short loc_180082088
0x180082036  xor     ebx, ebx
0x180082038  cmp     ebx, 32h ; '2'
0x18008203b  ja      short loc_180082095
0x18008203d  lea     rdx, [rsp+28h+arg_0]
0x180082042  mov     [rsp+28h+arg_0], 0
0x18008204b  mov     ecx, 2
0x180082050  call    cs:__imp_NtDCompositionGetFrameId
0x180082056  mov     ecx, eax; int
0x180082058  call    ?HRESULTFromNTSTATUS@CDevice@DirectComposition@@SAJJ@Z; DirectComposition::CDevice::HRESULTFromNTSTATUS(long)
0x18008205d  test    eax, eax
0x18008205f  jns     short loc_180082081
0x180082061  mov     ecx, 1
0x180082066  call    cs:__imp_NtDCompositionSyncWait
0x18008206c  add     ebx, 5
0x18008206f  cmp     ebx, 32h ; '2'
0x180082072  ja      short loc_180082095
0x180082074  mov     ecx, 5; dwMilliseconds
0x180082079  call    cs:__imp_Sleep
0x18008207f  jmp     short loc_180082038
0x180082081  cmp     [rsp+28h+arg_0], rdi
0x180082086  jb      short loc_180082061
0x180082088  mov     al, 1
0x18008208a  mov     rbx, [rsp+28h+arg_8]
0x18008208f  add     rsp, 20h
0x180082093  pop     rdi
0x180082094  retn
0x180082095  xor     al, al
0x180082097  jmp     short loc_18008208A
```
