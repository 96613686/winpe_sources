# CDedupOptimizer::CreateRunThreadpool(ulong)

- ea: `0x140076f24`
- end: `0x140077045`
- name: `?CreateRunThreadpool@CDedupOptimizer@@AEAAKK@Z`
- size: `289`
- prototype: `unsigned int __fastcall(CDedupOptimizer *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14007ae04`

## callees

- `0x1400635dc`
- `0x140076f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140076f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140076f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140076f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140076f94`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x140076f35`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x140076f35`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x140076f7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x140076f7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x14007702b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x14007702b`

## string_xrefs

- `0x140076f63`: `Failed to create threadpool, error = 0x%x\n`

## pseudocode

```c
DWORD __fastcall CDedupOptimizer::CreateRunThreadpool(CDedupOptimizer *this, int a2)
{
  PTP_POOL Threadpool; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  struct _TP_POOL *v7; // rcx
  DWORD v8; // edx
  DWORD LastError; // [rsp+30h] [rbp+8h] BYREF

  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 38) = Threadpool;
  if ( Threadpool )
  {
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *((_QWORD *)this + 48) = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      if ( !a2 )
        a2 = 64;
      *((_DWORD *)this + 98) = a2;
      *((_DWORD *)this + 78) = 3;
      *((_QWORD *)this + 43) = 0;
      *((_QWORD *)this + 44) = 0;
      *((_QWORD *)this + 45) = 0;
      *((_DWORD *)this + 92) = 0;
      *((_DWORD *)this + 93) = 1;
      *((_DWORD *)this + 94) = 72;
      *((_QWORD *)this + 41) = *((_QWORD *)this + 48);
      *((_QWORD *)this + 42) = 0;
      v7 = (struct _TP_POOL *)*((_QWORD *)this + 38);
      v8 = *((_DWORD *)this + 98);
      *((_QWORD *)this + 40) = v7;
      SetThreadpoolThreadMaximum(v7, v8);
      return 0;
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    LastError = GetLastError();
    DedupUtil::Print<unsigned long &>(6, L"Failed to create threadpool, error = 0x%x\n", &LastError);
    return LastError;
  }
}

```

## disassembly

```asm
0x140076f24  mov     [rsp+arg_8], rbx
0x140076f29  push    rdi
0x140076f2a  sub     rsp, 20h
0x140076f2e  mov     rbx, rcx
0x140076f31  mov     edi, edx
0x140076f33  xor     ecx, ecx; reserved
0x140076f35  call    cs:__imp_CreateThreadpool
0x140076f3c  nop     dword ptr [rax+rax+00h]
0x140076f41  mov     [rbx+130h], rax
0x140076f48  test    rax, rax
0x140076f4b  jnz     short loc_140076F7C
0x140076f4d  call    cs:__imp_GetLastError
0x140076f54  nop     dword ptr [rax+rax+00h]
0x140076f59  lea     r8, [rsp+28h+arg_0]
0x140076f5e  mov     ecx, 6
0x140076f63  lea     rdx, aFailedToCreate_2; "Failed to create threadpool, error = 0x"...
0x140076f6a  mov     [rsp+28h+arg_0], eax
0x140076f6e  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x140076f73  mov     eax, [rsp+28h+arg_0]
0x140076f77  jmp     loc_140077039
0x140076f7c  call    cs:__imp_CreateThreadpoolCleanupGroup
0x140076f83  nop     dword ptr [rax+rax+00h]
0x140076f88  mov     [rbx+180h], rax
0x140076f8f  test    rax, rax
0x140076f92  jnz     short loc_140076FA5
0x140076f94  call    cs:__imp_GetLastError
0x140076f9b  nop     dword ptr [rax+rax+00h]
0x140076fa0  jmp     loc_140077039
0x140076fa5  mov     eax, 40h ; '@'
0x140076faa  test    edi, edi
0x140076fac  cmovz   edi, eax
0x140076faf  mov     [rbx+188h], edi
0x140076fb5  mov     dword ptr [rbx+138h], 3
0x140076fbf  mov     qword ptr [rbx+158h], 0
0x140076fca  mov     qword ptr [rbx+160h], 0
0x140076fd5  mov     qword ptr [rbx+168h], 0
0x140076fe0  mov     dword ptr [rbx+170h], 0
0x140076fea  mov     dword ptr [rbx+174h], 1
0x140076ff4  mov     dword ptr [rbx+178h], 48h ; 'H'
0x140076ffe  mov     rax, [rbx+180h]
0x140077005  mov     [rbx+148h], rax
0x14007700c  mov     qword ptr [rbx+150h], 0
0x140077017  mov     rcx, [rbx+130h]; ptpp
0x14007701e  mov     edx, [rbx+188h]; cthrdMost
0x140077024  mov     [rbx+140h], rcx
0x14007702b  call    cs:__imp_SetThreadpoolThreadMaximum
0x140077032  nop     dword ptr [rax+rax+00h]
0x140077037  xor     eax, eax
0x140077039  mov     rbx, [rsp+28h+arg_8]
0x14007703e  add     rsp, 20h
0x140077042  pop     rdi
0x140077043  retn
```
