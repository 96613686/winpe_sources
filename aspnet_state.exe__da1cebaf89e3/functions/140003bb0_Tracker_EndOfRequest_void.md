# Tracker::EndOfRequest(void)

- ea: `0x140003bb0`
- end: `0x140003c89`
- name: `?EndOfRequest@Tracker@@QEAAXXZ`
- size: `217`
- prototype: `void __fastcall(Tracker *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140002b70`
- `0x1400033ec`

## callees

- `0x1400038ec`
- `0x140003a9c`
- `0x140003bb0`
- `0x140004638`
- `0x140004730`
- `0x140004f90`
- `0x140006590`

## pseudocode

```c
void __fastcall Tracker::EndOfRequest(Tracker *this)
{
  bool v2; // zf
  int *v3; // rax
  RefCount *v4; // rbx
  int v5; // eax
  unsigned int (__fastcall *v6)(RefCount *__hidden); // rax

  if ( !*((_BYTE *)this + 274) )
  {
    v2 = *((_BYTE *)this + 273) == 0;
    *((_BYTE *)this + 274) = 1;
    if ( v2 )
    {
      v3 = (int *)MemAllocClear(0x118u);
      v4 = (RefCount *)v3;
      if ( v3 )
      {
        v3[2] = 1;
        *(_QWORD *)v3 = &Tracker::`vftable';
        _InterlockedIncrement(&Tracker::s_cTrackers);
        *((_QWORD *)v3 + 6) = -1;
        v3[54] = -1;
        *((_BYTE *)v3 + 275) = 0;
        v5 = TrackerList::AddEntry(Tracker::s_pTrackerList, (struct Tracker *)v3, v3 + 54);
        if ( v5 || (v5 = Tracker::ContinueReading(v4, this)) != 0 )
        {
          Tracker::RecordProcessError(this, v5, L"EndOfRequest");
          v6 = *(unsigned int (__fastcall **)(RefCount *__hidden))(*(_QWORD *)v4 + 16LL);
          if ( v6 == RefCount::Release )
            RefCount::Release(v4);
          else
            v6(v4);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140003bb0  mov     [rsp+arg_0], rbx
0x140003bb5  push    rdi
0x140003bb6  sub     rsp, 20h
0x140003bba  cmp     byte ptr [rcx+112h], 0
0x140003bc1  mov     rdi, rcx
0x140003bc4  jnz     loc_140003C7E
0x140003bca  cmp     byte ptr [rcx+111h], 0
0x140003bd1  mov     byte ptr [rcx+112h], 1
0x140003bd8  jnz     loc_140003C7E
0x140003bde  mov     ecx, 118h; unsigned __int64
0x140003be3  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x140003be8  mov     rbx, rax
0x140003beb  test    rax, rax
0x140003bee  jz      loc_140003C7E
0x140003bf4  mov     dword ptr [rax+8], 1
0x140003bfb  lea     rax, ??_7Tracker@@6B@; const Tracker::`vftable'
0x140003c02  mov     [rbx], rax
0x140003c05  lock inc cs:?s_cTrackers@Tracker@@0JA; long Tracker::s_cTrackers
0x140003c0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003c10  lea     r8, [rbx+0D8h]; int *
0x140003c17  mov     [rbx+30h], rax
0x140003c1b  mov     rdx, rbx; struct Tracker *
0x140003c1e  mov     [rbx+0D8h], eax
0x140003c24  mov     byte ptr [rbx+113h], 0
0x140003c2b  mov     rcx, cs:?s_pTrackerList@Tracker@@0PEAVTrackerList@@EA; this
0x140003c32  call    ?AddEntry@TrackerList@@QEAAJPEAVTracker@@PEAH@Z; TrackerList::AddEntry(Tracker *,int *)
0x140003c37  test    eax, eax
0x140003c39  jnz     short loc_140003C4A
0x140003c3b  mov     rdx, rdi; struct Tracker *
0x140003c3e  mov     rcx, rbx; this
0x140003c41  call    ?ContinueReading@Tracker@@AEAAJPEAV1@@Z; Tracker::ContinueReading(Tracker *)
0x140003c46  test    eax, eax
0x140003c48  jz      short loc_140003C7E
0x140003c4a  lea     r8, aEndofrequest; "EndOfRequest"
0x140003c51  mov     edx, eax; int
0x140003c53  mov     rcx, rdi; this
0x140003c56  call    ?RecordProcessError@Tracker@@AEAAXJPEBG@Z; Tracker::RecordProcessError(long,ushort const *)
0x140003c5b  mov     rax, [rbx]
0x140003c5e  lea     rcx, ?Release@RefCount@@UEAAKXZ; RefCount::Release(void)
0x140003c65  mov     rax, [rax+10h]
0x140003c69  cmp     rax, rcx
0x140003c6c  mov     rcx, rbx; this
0x140003c6f  jnz     short loc_140003C78
0x140003c71  call    ?Release@RefCount@@UEAAKXZ; RefCount::Release(void)
0x140003c76  jmp     short loc_140003C7E
0x140003c78  call    cs:__guard_dispatch_icall_fptr
0x140003c7e  mov     rbx, [rsp+28h+arg_0]
0x140003c83  add     rsp, 20h
0x140003c87  pop     rdi
0x140003c88  retn
```
