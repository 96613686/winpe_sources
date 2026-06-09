# CacheWriter::~CacheWriter(void)

- ea: `0x18006fc1c`
- end: `0x18006fc76`
- name: `??1CacheWriter@@UEAA@XZ`
- size: `90`
- prototype: `void __fastcall(CacheWriter *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800113a4`
- `0x18006f82c`
- `0x18006f8b0`
- `0x18006fbe0`

## callees

- `0x18006fc1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006fc33`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006fc33`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18006fc58`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18006fc58`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18006fc48`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18006fc48`

## pseudocode

```c
void __fastcall CacheWriter::~CacheWriter(CacheWriter *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CacheWriter::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    if ( *((_BYTE *)this + 24) )
      UnmapViewOfFile(v2);
    else
      VirtualFree(v2, 0, 0x8000u);
    *((_QWORD *)this + 2) = 0;
  }
  *(_QWORD *)this = &ICacheReference::`vftable';
}

```

## disassembly

```asm
0x18006fc1c  push    rbx
0x18006fc1e  sub     rsp, 20h
0x18006fc22  lea     rax, ??_7CacheWriter@@6B@; const CacheWriter::`vftable'
0x18006fc29  mov     rbx, rcx
0x18006fc2c  mov     [rcx], rax
0x18006fc2f  add     rcx, 20h ; ' '; lpCriticalSection
0x18006fc33  call    cs:__imp_DeleteCriticalSection
0x18006fc39  mov     rcx, [rbx+10h]; lpAddress
0x18006fc3d  test    rcx, rcx
0x18006fc40  jz      short loc_18006FC66
0x18006fc42  cmp     byte ptr [rbx+18h], 0
0x18006fc46  jz      short loc_18006FC50
0x18006fc48  call    cs:__imp_UnmapViewOfFile
0x18006fc4e  jmp     short loc_18006FC5E
0x18006fc50  xor     edx, edx; dwSize
0x18006fc52  mov     r8d, 8000h; dwFreeType
0x18006fc58  call    cs:__imp_VirtualFree
0x18006fc5e  mov     qword ptr [rbx+10h], 0
0x18006fc66  lea     rax, ??_7ICacheReference@@6B@; const ICacheReference::`vftable'
0x18006fc6d  mov     [rbx], rax
0x18006fc70  add     rsp, 20h
0x18006fc74  pop     rbx
0x18006fc75  retn
```
