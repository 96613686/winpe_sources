# CAVIFile::CF::ReadData(ulong,void *,long *)

- ea: `0x18000b020`
- end: `0x18000b078`
- name: `?ReadData@CF@CAVIFile@@UEAAJKPEAXPEAJ@Z`
- size: `88`
- prototype: `__int64 __fastcall(CAVIFile::CF *this, int, void *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b020`
- `0x18000d1c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b041`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b041`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b065`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b065`

## pseudocode

```c
__int64 __fastcall CAVIFile::CF::ReadData(CAVIFile::CF *this, int a2, void *a3, int *a4)
{
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r14
  unsigned int Extra; // ebx

  v4 = *((_QWORD *)this + 1);
  v8 = (struct _RTL_CRITICAL_SECTION *)(v4 + 1264);
  EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 1264));
  Extra = ReadExtra(v4 + 712, a2, a3, a4);
  if ( v8 )
    LeaveCriticalSection(v8);
  return Extra;
}

```

## disassembly

```asm
0x18000b020  push    rbx
0x18000b022  push    rbp
0x18000b023  push    rsi
0x18000b024  push    rdi
0x18000b025  push    r14
0x18000b027  sub     rsp, 20h
0x18000b02b  mov     rbx, [rcx+8]
0x18000b02f  mov     rdi, r9
0x18000b032  mov     rsi, r8
0x18000b035  mov     ebp, edx
0x18000b037  lea     r14, [rbx+4F0h]
0x18000b03e  mov     rcx, r14; lpCriticalSection
0x18000b041  call    cs:__imp_EnterCriticalSection
0x18000b047  lea     rcx, [rbx+2C8h]
0x18000b04e  mov     r9, rdi
0x18000b051  mov     r8, rsi
0x18000b054  mov     edx, ebp
0x18000b056  call    ReadExtra
0x18000b05b  mov     ebx, eax
0x18000b05d  test    r14, r14
0x18000b060  jz      short loc_18000B06B
0x18000b062  mov     rcx, r14; lpCriticalSection
0x18000b065  call    cs:__imp_LeaveCriticalSection
0x18000b06b  mov     eax, ebx
0x18000b06d  add     rsp, 20h
0x18000b071  pop     r14
0x18000b073  pop     rdi
0x18000b074  pop     rsi
0x18000b075  pop     rbp
0x18000b076  pop     rbx
0x18000b077  retn
```
