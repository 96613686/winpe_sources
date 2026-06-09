# Tracker::StartReading(void)

- ea: `0x140004ba4`
- end: `0x140004c13`
- name: `?StartReading@Tracker@@AEAAJXZ`
- size: `111`
- prototype: `__int64 __fastcall(Tracker *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140004280`

## callees

- `0x1400013c4`
- `0x140004410`
- `0x140004638`
- `0x140004ba4`
- `0x140004f90`

## string_xrefs

- `0x140004bf5`: `StartReading`

## pseudocode

```c
__int64 __fastcall Tracker::StartReading(Tracker *this)
{
  ReadBuffer *v2; // rax
  unsigned int v3; // ebx

  v2 = (ReadBuffer *)MemAllocClear(0x58u);
  *((_QWORD *)this + 26) = v2;
  if ( v2 )
  {
    v3 = ReadBuffer::Init(v2, this, 0, 0);
    if ( !v3 )
      v3 = Tracker::ProcessReading(this, 0, 0xFFFFFFFF);
  }
  else
  {
    v3 = -2147024882;
  }
  Tracker::RecordProcessError(this, v3, L"StartReading");
  return v3;
}

```

## disassembly

```asm
0x140004ba4  mov     [rsp+arg_0], rbx
0x140004ba9  push    rdi
0x140004baa  sub     rsp, 20h
0x140004bae  mov     rdi, rcx
0x140004bb1  mov     ecx, 58h ; 'X'; unsigned __int64
0x140004bb6  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x140004bbb  mov     [rdi+0D0h], rax
0x140004bc2  test    rax, rax
0x140004bc5  jnz     short loc_140004BCE
0x140004bc7  mov     ebx, 8007000Eh
0x140004bcc  jmp     short loc_140004BF5
0x140004bce  xor     r9d, r9d; int *
0x140004bd1  xor     r8d, r8d; struct ReadBuffer *
0x140004bd4  mov     rdx, rdi; struct Tracker *
0x140004bd7  mov     rcx, rax; this
0x140004bda  call    ?Init@ReadBuffer@@QEAAJPEAVTracker@@PEAV1@PEAH@Z; ReadBuffer::Init(Tracker *,ReadBuffer *,int *)
0x140004bdf  mov     ebx, eax
0x140004be1  test    eax, eax
0x140004be3  jnz     short loc_140004BF5
0x140004be5  or      r8d, 0FFFFFFFFh; unsigned int
0x140004be9  xor     edx, edx; int
0x140004beb  mov     rcx, rdi; this
0x140004bee  call    ?ProcessReading@Tracker@@AEAAJJH@Z; Tracker::ProcessReading(long,int)
0x140004bf3  mov     ebx, eax
0x140004bf5  lea     r8, aStartreading; "StartReading"
0x140004bfc  mov     edx, ebx; int
0x140004bfe  mov     rcx, rdi; this
0x140004c01  call    ?RecordProcessError@Tracker@@AEAAXJPEBG@Z; Tracker::RecordProcessError(long,ushort const *)
0x140004c06  mov     eax, ebx
0x140004c08  mov     rbx, [rsp+28h+arg_0]
0x140004c0d  add     rsp, 20h
0x140004c11  pop     rdi
0x140004c12  retn
```
