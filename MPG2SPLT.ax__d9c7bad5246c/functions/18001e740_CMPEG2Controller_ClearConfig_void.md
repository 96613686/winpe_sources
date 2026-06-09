# CMPEG2Controller::ClearConfig(void)

- ea: `0x18001e740`
- end: `0x18001e7c9`
- name: `?ClearConfig@CMPEG2Controller@@UEAAJXZ`
- size: `137`
- prototype: `__int64 __fastcall(CMPEG2Controller *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001d5d4`

## callees

- `0x180021bfc`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001e7a5`
- `KERNEL32!LeaveCriticalSection` at `0x18001e7b6`
- `KERNEL32!LeaveCriticalSection` at `0x18001e7a5`
- `KERNEL32!LeaveCriticalSection` at `0x18001e7b6`
- `KERNEL32!EnterCriticalSection` at `0x18001e758`
- `KERNEL32!EnterCriticalSection` at `0x18001e765`
- `KERNEL32!EnterCriticalSection` at `0x18001e758`
- `KERNEL32!EnterCriticalSection` at `0x18001e765`

## pseudocode

```c
__int64 __fastcall CMPEG2Controller::ClearConfig(CMPEG2Controller *this)
{
  unsigned int v2; // ebx
  struct _RTL_CRITICAL_SECTION *v3; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 15) + 296LL));
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 23));
  v2 = CMPEG2Controller::UnmapAllStreamsLocked_(this, 0);
  (*(void (__fastcall **)(CMPEG2Controller *, _QWORD))(*(_QWORD *)this + 96LL))(this, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 23);
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  LeaveCriticalSection(v3);
  LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 15) + 296LL));
  return v2;
}

```

## disassembly

```asm
0x18001e740  mov     [rsp+arg_0], rbx
0x18001e745  push    rdi
0x18001e746  sub     rsp, 20h
0x18001e74a  mov     rdi, rcx
0x18001e74d  mov     rcx, [rcx+78h]
0x18001e751  add     rcx, 128h; lpCriticalSection
0x18001e758  call    cs:__imp_EnterCriticalSection
0x18001e75e  mov     rcx, [rdi+0B8h]; lpCriticalSection
0x18001e765  call    cs:__imp_EnterCriticalSection
0x18001e76b  xor     edx, edx; struct CMPEG2DemuxOutputPin *
0x18001e76d  mov     rcx, rdi; this
0x18001e770  call    ?UnmapAllStreamsLocked_@CMPEG2Controller@@AEAAJPEAVCMPEG2DemuxOutputPin@@@Z; CMPEG2Controller::UnmapAllStreamsLocked_(CMPEG2DemuxOutputPin *)
0x18001e775  mov     rcx, [rdi]
0x18001e778  mov     ebx, eax
0x18001e77a  xor     edx, edx
0x18001e77c  mov     rax, [rcx+60h]
0x18001e780  mov     rcx, rdi
0x18001e783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e788  mov     rcx, [rdi+0B8h]; lpCriticalSection
0x18001e78f  mov     qword ptr [rdi+0D0h], 0
0x18001e79a  mov     qword ptr [rdi+0D8h], 0
0x18001e7a5  call    cs:__imp_LeaveCriticalSection
0x18001e7ab  mov     rcx, [rdi+78h]
0x18001e7af  add     rcx, 128h; lpCriticalSection
0x18001e7b6  call    cs:__imp_LeaveCriticalSection
0x18001e7bc  mov     eax, ebx
0x18001e7be  mov     rbx, [rsp+28h+arg_0]
0x18001e7c3  add     rsp, 20h
0x18001e7c7  pop     rdi
0x18001e7c8  retn
```
