# CPerfMainBlock::Init(int)

- ea: `0x180003160`
- end: `0x18000323f`
- name: `?Init@CPerfMainBlock@@QEAAJH@Z`
- size: `223`
- prototype: `__int64 __fastcall(CPerfMainBlock *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002dd0`

## callees

- `0x180003160`
- `0x180003248`
- `0x180049c54`

## import_xrefs

- `KERNEL32!OpenEventA` at `0x180003210`
- `KERNEL32!OpenEventA` at `0x180003210`
- `KERNEL32!OpenEventW` at `0x1800031ee`
- `KERNEL32!OpenEventW` at `0x1800031ee`
- `KERNEL32!OpenMutexA` at `0x180003174`
- `KERNEL32!OpenMutexA` at `0x180003174`
- `KERNEL32!OpenProcess` at `0x1800031cc`
- `KERNEL32!OpenProcess` at `0x1800031cc`
- `KERNEL32!GetLastError` at `0x1800253b3`
- `KERNEL32!GetLastError` at `0x1800253b3`

## pseudocode

```c
__int64 __fastcall CPerfMainBlock::Init(CPerfMainBlock *this)
{
  signed int inited; // ebx
  signed int LastError; // eax

  hMutex = OpenMutexA(0x100000u, 0, "Global\\ASP_PERFMON_MUTEX");
  if ( !hMutex )
  {
    inited = -2147467259;
LABEL_10:
    CPerfMainBlock::UnInit((CPerfMainBlock *)g_PerfMain);
    return (unsigned int)inited;
  }
  inited = CSharedMemBlock::InitMap((CSharedMemBlock *)g_PerfMain, "Global\\ASP_PERFMON_MAIN_BLOCK", 0x28ACu, 0);
  if ( inited < 0 )
    goto LABEL_10;
  Src = (void *)qword_18007A1F8;
  *(_QWORD *)&xmmword_18007A230 = OpenProcess(0x100000u, 0, *(_DWORD *)(qword_18007A1F8 + 8360));
  *((_QWORD *)&xmmword_18007A230 + 1) = OpenEventW(0x100000u, 0, (LPCWSTR)Src + 4182);
  if ( *((_QWORD *)&xmmword_18007A230 + 1) && (*(&hMutex + 1) = OpenEventA(2u, 0, "Global\\ASP_PERFMON_ADD_EVENT")) != 0 )
  {
    inited = 0;
  }
  else
  {
    LastError = GetLastError();
    inited = LastError;
    if ( LastError > 0 )
      inited = (unsigned __int16)LastError | 0x80070000;
  }
  if ( inited < 0 )
    goto LABEL_10;
  dword_18007A218 |= 1u;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180003160  push    rbx
0x180003162  sub     rsp, 20h
0x180003166  lea     r8, Name; "Global\\ASP_PERFMON_MUTEX"
0x18000316d  xor     edx, edx; bInheritHandle
0x18000316f  mov     ecx, 100000h; dwDesiredAccess
0x180003174  call    cs:__imp_OpenMutexA
0x18000317a  mov     qword ptr cs:hMutex, rax
0x180003181  test    rax, rax
0x180003184  jz      loc_18002539C
0x18000318a  xor     r9d, r9d; int
0x18000318d  lea     rdx, aGlobalAspPerfm_1; "Global\\ASP_PERFMON_MAIN_BLOCK"
0x180003194  mov     r8d, 28ACh; Size
0x18000319a  lea     rcx, ?g_PerfMain@@3VCPerfMainBlock@@A; this
0x1800031a1  call    ?InitMap@CSharedMemBlock@@QEAAJPEBDKH@Z; CSharedMemBlock::InitMap(char const *,ulong,int)
0x1800031a6  mov     ebx, eax
0x1800031a8  test    eax, eax
0x1800031aa  js      loc_1800253A1
0x1800031b0  mov     r8, cs:qword_18007A1F8
0x1800031b7  xor     edx, edx; bInheritHandle
0x1800031b9  mov     cs:Src, r8
0x1800031c0  mov     ecx, 100000h; dwDesiredAccess
0x1800031c5  mov     r8d, [r8+20A8h]; dwProcessId
0x1800031cc  call    cs:__imp_OpenProcess
0x1800031d2  mov     r8, cs:Src
0x1800031d9  xor     edx, edx; bInheritHandle
0x1800031db  add     r8, 20ACh; lpName
0x1800031e2  mov     qword ptr cs:xmmword_18007A230, rax
0x1800031e9  mov     ecx, 100000h; dwDesiredAccess
0x1800031ee  call    cs:__imp_OpenEventW
0x1800031f4  mov     qword ptr cs:xmmword_18007A230+8, rax
0x1800031fb  test    rax, rax
0x1800031fe  jz      loc_1800253B3
0x180003204  xor     edx, edx; bInheritHandle
0x180003206  lea     r8, aGlobalAspPerfm; "Global\\ASP_PERFMON_ADD_EVENT"
0x18000320d  lea     ecx, [rdx+2]; dwDesiredAccess
0x180003210  call    cs:__imp_OpenEventA
0x180003216  mov     qword ptr cs:hMutex+8, rax
0x18000321d  test    rax, rax
0x180003220  jz      loc_1800253B3
0x180003226  xor     ebx, ebx
0x180003228  test    ebx, ebx
0x18000322a  js      loc_1800253A1
0x180003230  or      cs:dword_18007A218, 1
0x180003237  mov     eax, ebx
0x180003239  add     rsp, 20h
0x18000323d  pop     rbx
0x18000323e  retn
0x18002539c  mov     ebx, 80004005h
0x1800253a1  lea     rcx, ?g_PerfMain@@3VCPerfMainBlock@@A; this
0x1800253a8  call    ?UnInit@CPerfMainBlock@@QEAAJXZ; CPerfMainBlock::UnInit(void)
0x1800253ad  nop
0x1800253ae  jmp     loc_180003237
0x1800253b3  call    cs:__imp_GetLastError
0x1800253b9  mov     ebx, eax
0x1800253bb  test    eax, eax
0x1800253bd  jle     loc_180003228
0x1800253c3  movzx   ebx, ax
0x1800253c6  or      ebx, 80070000h
0x1800253cc  jmp     loc_180003228
```
