# TlmiUpdateFirstRunExpStatus

- ea: `0x18001a54c`
- end: `0x18001a637`
- name: `TlmiUpdateFirstRunExpStatus`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180011e18`
- `0x180017728`

## callees

- `0x18001a54c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a5a4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a5a4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a628`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a628`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001a61b`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001a61b`

## pseudocode

```c
void __fastcall TlmiUpdateFirstRunExpStatus(__int64 a1, char a2, __int64 a3, int a4)
{
  LARGE_INTEGER DueTime; // [rsp+30h] [rbp-38h] BYREF

  DueTime.QuadPart = 0;
  if ( byte_180028930 && !NtCurrentPeb()->Ldr->ShutdownInProgress && byte_180028968 )
  {
    RtlAcquireSRWLockExclusive(&qword_180028970);
    if ( a4 < 0 && qword_180028998 >= 0 )
      HIDWORD(qword_180028998) = a4;
    qword_180028980 = a1;
    if ( a2 && a3 )
    {
      if ( (int)qword_180028998 <= 0 )
        qword_180028988 = a1;
      LODWORD(qword_180028998) = *(_DWORD *)(a3 + 16) + qword_180028998;
      qword_180028990 = a1;
    }
    DueTime.QuadPart = -150000000;
    SetWaitableTimer(hTimer, &DueTime, 0, 0, 0, 0);
    RtlReleaseSRWLockExclusive(&qword_180028970);
  }
}

```

## disassembly

```asm
0x18001a54c  push    rbx
0x18001a54e  push    rbp
0x18001a54f  push    rsi
0x18001a550  push    rdi
0x18001a551  sub     rsp, 48h
0x18001a555  cmp     cs:byte_180028930, 0
0x18001a55c  mov     esi, r9d
0x18001a55f  mov     rdi, r8
0x18001a562  mov     qword ptr [rsp+68h+DueTime], 0
0x18001a56b  mov     bpl, dl
0x18001a56e  mov     rbx, rcx
0x18001a571  jz      loc_18001A62E
0x18001a577  mov     rax, gs:60h
0x18001a580  mov     r10, [rax+18h]
0x18001a584  cmp     byte ptr [r10+48h], 0
0x18001a589  jnz     loc_18001A62E
0x18001a58f  mov     al, cs:byte_180028968
0x18001a595  test    al, al
0x18001a597  jz      loc_18001A62E
0x18001a59d  lea     rcx, qword_180028970
0x18001a5a4  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a5aa  test    esi, esi
0x18001a5ac  jns     short loc_18001A5BD
0x18001a5ae  cmp     dword ptr cs:qword_180028998+4, 0
0x18001a5b5  jl      short loc_18001A5BD
0x18001a5b7  mov     dword ptr cs:qword_180028998+4, esi
0x18001a5bd  mov     cs:qword_180028980, rbx
0x18001a5c4  test    bpl, bpl
0x18001a5c7  jz      short loc_18001A5EF
0x18001a5c9  test    rdi, rdi
0x18001a5cc  jz      short loc_18001A5EF
0x18001a5ce  mov     eax, dword ptr cs:qword_180028998
0x18001a5d4  test    eax, eax
0x18001a5d6  jg      short loc_18001A5DF
0x18001a5d8  mov     cs:qword_180028988, rbx
0x18001a5df  add     eax, [rdi+10h]
0x18001a5e2  mov     dword ptr cs:qword_180028998, eax
0x18001a5e8  mov     cs:qword_180028990, rbx
0x18001a5ef  mov     rcx, cs:hTimer; hTimer
0x18001a5f6  lea     rdx, [rsp+68h+DueTime]; lpDueTime
0x18001a5fb  mov     [rsp+68h+fResume], 0; fResume
0x18001a603  xor     r9d, r9d; pfnCompletionRoutine
0x18001a606  xor     r8d, r8d; lPeriod
0x18001a609  mov     [rsp+68h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18001a612  mov     qword ptr [rsp+68h+DueTime], 0FFFFFFFFF70F2E80h
0x18001a61b  call    cs:__imp_SetWaitableTimer
0x18001a621  lea     rcx, qword_180028970
0x18001a628  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001a62e  add     rsp, 48h
0x18001a632  pop     rdi
0x18001a633  pop     rsi
0x18001a634  pop     rbp
0x18001a635  pop     rbx
0x18001a636  retn
```
