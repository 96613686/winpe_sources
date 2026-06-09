# CAVIStream::CS::ReadData(ulong,void *,long *)

- ea: `0x18000b080`
- end: `0x18000b0df`
- name: `?ReadData@CS@CAVIStream@@UEAAJKPEAXPEAJ@Z`
- size: `95`
- prototype: `__int64 __fastcall(CAVIStream::CS *__hidden this, unsigned int, void *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b080`
- `0x18000d1c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b0a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b0a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b0cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b0cc`

## pseudocode

```c
__int64 __fastcall CAVIStream::CS::ReadData(CAVIStream::CS *this, unsigned int a2, void *a3, int *a4)
{
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r14
  unsigned int Extra; // ebx

  v4 = *((_QWORD *)this + 1);
  v8 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v4 + 272) + 1264LL);
  EnterCriticalSection(v8);
  Extra = ReadExtra(v4 + 1368, a2, a3, a4);
  if ( v8 )
    LeaveCriticalSection(v8);
  return Extra;
}

```

## disassembly

```asm
0x18000b080  push    rbx
0x18000b082  push    rbp
0x18000b083  push    rsi
0x18000b084  push    rdi
0x18000b085  push    r14
0x18000b087  sub     rsp, 20h
0x18000b08b  mov     rbx, [rcx+8]
0x18000b08f  mov     rdi, r9
0x18000b092  mov     rsi, r8
0x18000b095  mov     ebp, edx
0x18000b097  mov     r14, [rbx+110h]
0x18000b09e  add     r14, 4F0h
0x18000b0a5  mov     rcx, r14; lpCriticalSection
0x18000b0a8  call    cs:__imp_EnterCriticalSection
0x18000b0ae  lea     rcx, [rbx+558h]
0x18000b0b5  mov     r9, rdi
0x18000b0b8  mov     r8, rsi
0x18000b0bb  mov     edx, ebp
0x18000b0bd  call    ReadExtra
0x18000b0c2  mov     ebx, eax
0x18000b0c4  test    r14, r14
0x18000b0c7  jz      short loc_18000B0D2
0x18000b0c9  mov     rcx, r14; lpCriticalSection
0x18000b0cc  call    cs:__imp_LeaveCriticalSection
0x18000b0d2  mov     eax, ebx
0x18000b0d4  add     rsp, 20h
0x18000b0d8  pop     r14
0x18000b0da  pop     rdi
0x18000b0db  pop     rsi
0x18000b0dc  pop     rbp
0x18000b0dd  pop     rbx
0x18000b0de  retn
```
