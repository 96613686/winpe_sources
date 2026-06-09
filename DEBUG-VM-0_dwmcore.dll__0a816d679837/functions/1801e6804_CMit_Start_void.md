# CMit::Start(void)

- ea: `0x1801e6804`
- end: `0x1801e68c2`
- name: `?Start@CMit@@QEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(CMit *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18015541c`

## callees

- `0x180042de0`
- `0x1801e6804`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801e68b2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801e68b2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801e68a8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801e68a8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801e686c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801e686c`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1801e6899`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1801e6899`

## string_xrefs

- `0x1801e688f`: `DWM Master Input Thread`

## pseudocode

```c
__int64 __fastcall CMit::Start(HANDLE *this)
{
  unsigned int v2; // ebx
  HANDLE v3; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 32) )
  {
    v2 = -2147467260;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_180357050, 2u, -2147467260, 0x61u, 0);
  }
  else
  {
    ThreadId = 0;
    v3 = CreateThread(0, 0, CMit::RunInputThreadStatic, this, 4u, &ThreadId);
    this[2] = v3;
    if ( v3 )
    {
      SetThreadDescription(v3, L"DWM Master Input Thread");
      SetThreadPriority(this[2], 16);
      ResumeThread(this[2]);
      return 0;
    }
    else
    {
      v2 = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_180357050, 2u, -2147024882, 0x73u, 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1801e6804  push    rbx
0x1801e6806  sub     rsp, 30h
0x1801e680a  cmp     byte ptr [rcx+20h], 0
0x1801e680e  mov     rbx, rcx
0x1801e6811  jz      short loc_1801E6844
0x1801e6813  mov     [rsp+38h+lpThreadId], 0; void *
0x1801e681c  mov     ebx, 80004004h
0x1801e6821  mov     [rsp+38h+dwCreationFlags], 61h ; 'a'; unsigned int
0x1801e6829  mov     r8d, 2; unsigned int
0x1801e682f  lea     rdx, dword_180357050; int *
0x1801e6836  mov     r9d, ebx; int
0x1801e6839  lea     ecx, [r8+12h]; unsigned int
0x1801e683d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801e6842  jmp     short loc_1801E68BA
0x1801e6844  lea     rax, [rsp+38h+ThreadId]
0x1801e6849  mov     [rsp+38h+ThreadId], 0
0x1801e6851  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1801e6856  lea     r8, ?RunInputThreadStatic@CMit@@SAKPEAX@Z; lpStartAddress
0x1801e685d  mov     r9, rbx; lpParameter
0x1801e6860  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1801e6868  xor     edx, edx; dwStackSize
0x1801e686a  xor     ecx, ecx; lpThreadAttributes
0x1801e686c  call    cs:__imp_CreateThread
0x1801e6872  mov     [rbx+10h], rax
0x1801e6876  test    rax, rax
0x1801e6879  jnz     short loc_1801E688F
0x1801e687b  mov     [rsp+38h+lpThreadId], rax
0x1801e6880  mov     ebx, 8007000Eh
0x1801e6885  mov     [rsp+38h+dwCreationFlags], 73h ; 's'
0x1801e688d  jmp     short loc_1801E6829
0x1801e688f  lea     rdx, aDwmMasterInput; "DWM Master Input Thread"
0x1801e6896  mov     rcx, rax; hThread
0x1801e6899  call    cs:__imp_SetThreadDescription
0x1801e689f  mov     rcx, [rbx+10h]; hThread
0x1801e68a3  mov     edx, 10h; nPriority
0x1801e68a8  call    cs:__imp_SetThreadPriority
0x1801e68ae  mov     rcx, [rbx+10h]; hThread
0x1801e68b2  call    cs:__imp_ResumeThread
0x1801e68b8  xor     ebx, ebx
0x1801e68ba  mov     eax, ebx
0x1801e68bc  add     rsp, 30h
0x1801e68c0  pop     rbx
0x1801e68c1  retn
```
