# _PROG_RESOURCES::Init(void)

- ea: `0x180011ea8`
- end: `0x180011f3a`
- name: `?Init@_PROG_RESOURCES@@QEAAHXZ`
- size: `146`
- prototype: `__int64 __fastcall(_PROG_RESOURCES *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c568`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180011f1d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180011f1d`

## pseudocode

```c
_BOOL8 __fastcall _PROG_RESOURCES::Init(_PROG_RESOURCES *this)
{
  g_ProgRes = 0;
  *(_OWORD *)&pUnk = 0;
  *(_QWORD *)&dwRegister = 0;
  dword_180032A28 = 0;
  dword_180032A54 = 1;
  dword_180032CC8 = 1;
  dword_180032A50 = 0;
  hMutex = 0;
  qword_180032A60 = 0;
  hObject = 0;
  *(_OWORD *)&xmmword_180032A70 = 0;
  qword_180032A80 = 0;
  qword_180032CD0 = 0;
  word_180032CD8 = 0;
  hMutex = CreateMutexW(0, 0, 0);
  return hMutex != 0;
}

```

## disassembly

```asm
0x180011ea8  push    rbx
0x180011eaa  sub     rsp, 20h
0x180011eae  xor     ebx, ebx
0x180011eb0  xorps   xmm0, xmm0
0x180011eb3  xor     r8d, r8d; lpName
0x180011eb6  mov     cs:?g_ProgRes@@3U_PROG_RESOURCES@@A, rbx; _PROG_RESOURCES g_ProgRes
0x180011ebd  xor     edx, edx; bInitialOwner
0x180011ebf  movdqa  cs:pUnk, xmm0
0x180011ec7  xor     ecx, ecx; lpMutexAttributes
0x180011ec9  mov     cs:dwRegister, rbx
0x180011ed0  lea     eax, [rbx+1]
0x180011ed3  mov     cs:dword_180032A28, ebx
0x180011ed9  mov     cs:dword_180032A54, eax
0x180011edf  mov     cs:dword_180032CC8, eax
0x180011ee5  mov     cs:dword_180032A50, ebx
0x180011eeb  mov     cs:hMutex, rbx
0x180011ef2  mov     cs:qword_180032A60, rbx
0x180011ef9  mov     cs:hObject, rbx
0x180011f00  movdqa  cs:xmmword_180032A70, xmm0
0x180011f08  mov     cs:qword_180032A80, rbx
0x180011f0f  mov     cs:qword_180032CD0, rbx
0x180011f16  mov     cs:word_180032CD8, bx
0x180011f1d  call    cs:__imp_CreateMutexW
0x180011f23  test    rax, rax
0x180011f26  mov     cs:hMutex, rax
0x180011f2d  mov     ecx, ebx
0x180011f2f  setnz   cl
0x180011f32  mov     eax, ecx
0x180011f34  add     rsp, 20h
0x180011f38  pop     rbx
0x180011f39  retn
```
