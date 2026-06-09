# CLogFile::~CLogFile(void)

- ea: `0x180003d3c`
- end: `0x180003d8e`
- name: `??1CLogFile@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(CLogFile *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004560`

## callees

- `0x180003d3c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180003d59`
- `KERNEL32!CloseHandle` at `0x180003d70`
- `KERNEL32!CloseHandle` at `0x180003d59`
- `KERNEL32!CloseHandle` at `0x180003d70`
- `KERNEL32!DeleteCriticalSection` at `0x180003d87`

## pseudocode

```c
void __fastcall CLogFile::~CLogFile(CLogFile *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CLogFile::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 2) = -1;
  }
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 5) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x180003d3c  push    rbx
0x180003d3e  sub     rsp, 20h
0x180003d42  lea     rax, ??_7CLogFile@@6B@; const CLogFile::`vftable'
0x180003d49  mov     rbx, rcx
0x180003d4c  mov     [rcx], rax
0x180003d4f  mov     rcx, [rcx+10h]; hObject
0x180003d53  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003d57  jz      short loc_180003D67
0x180003d59  call    cs:__imp_CloseHandle
0x180003d5f  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x180003d67  mov     rcx, [rbx+28h]; hObject
0x180003d6b  test    rcx, rcx
0x180003d6e  jz      short loc_180003D7E
0x180003d70  call    cs:__imp_CloseHandle
0x180003d76  mov     qword ptr [rbx+28h], 0
0x180003d7e  lea     rcx, [rbx+30h]
0x180003d82  add     rsp, 20h
0x180003d86  pop     rbx
0x180003d87  jmp     cs:__imp_DeleteCriticalSection
```
