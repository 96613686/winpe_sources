# CreateAsyncWorkQueue(IAsyncWorkQueue * *)

- ea: `0x18007d2f0`
- end: `0x18007d40d`
- name: `?CreateAsyncWorkQueue@@YAJPEAPEAUIAsyncWorkQueue@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(struct IAsyncWorkQueue **)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800124e0`
- `0x180015b40`
- `0x180056c2c`
- `0x1800678cc`
- `0x18007dcf0`

## callees

- `0x180005660`
- `0x18007d2f0`
- `0x18008d95a`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007d341`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007d341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d3c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d3c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007d39b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007d39b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007d3b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007d3b5`

## pseudocode

```c
__int64 __fastcall CreateAsyncWorkQueue(PTP_WORK **a1)
{
  PTP_WORK *v2; // rax
  PTP_WORK *v3; // rdi
  PTP_WORK ThreadpoolWork; // rbx
  struct _TP_WORK *v5; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx

  v2 = (PTP_WORK *)operator new(0x70u);
  v3 = v2;
  if ( v2 )
  {
    memset_0((char *)v2 + 12, 0, 0x64u);
    *((_DWORD *)v3 + 2) = 0;
    *v3 = (PTP_WORK)&AsyncWorkQueue::`vftable';
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v3 + 2), 0, 0);
    v3[10] = 0;
    v3[7] = (PTP_WORK)(v3 + 7);
    v3[8] = (PTP_WORK)(v3 + 7);
    v3[9] = 0;
    *((_DWORD *)v3 + 22) = 0;
    *((_DWORD *)v3 + 23) = 0;
    v3[12] = 0;
    *((_DWORD *)v3 + 26) = 0;
    (*((void (__fastcall **)(PTP_WORK *))*v3 + 1))(v3);
    ThreadpoolWork = CreateThreadpoolWork(AsyncWorkQueue::WorkCallBack, v3, 0);
    v5 = v3[12];
    if ( ThreadpoolWork == v5 )
    {
      ThreadpoolWork = v3[12];
    }
    else
    {
      if ( v5 )
        CloseThreadpoolWork(v3[12]);
      v3[12] = ThreadpoolWork;
    }
    if ( ThreadpoolWork )
    {
      *a1 = v3;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      (*((void (__fastcall **)(PTP_WORK *))*v3 + 2))(v3);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x18007d2f0  mov     [rsp+arg_8], rbx
0x18007d2f5  mov     [rsp+arg_10], rsi
0x18007d2fa  push    rdi
0x18007d2fb  sub     rsp, 20h
0x18007d2ff  mov     rsi, rcx
0x18007d302  mov     ecx, 70h ; 'p'; Size
0x18007d307  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007d30c  mov     rdi, rax
0x18007d30f  test    rax, rax
0x18007d312  jz      loc_18007D3F6
0x18007d318  xor     edx, edx; Val
0x18007d31a  lea     rcx, [rax+0Ch]; void *
0x18007d31e  lea     r8d, [rdx+64h]; Size
0x18007d322  call    memset_0
0x18007d327  lea     rax, ??_7AsyncWorkQueue@@6B@; const AsyncWorkQueue::`vftable'
0x18007d32e  mov     dword ptr [rdi+8], 0
0x18007d335  lea     rcx, [rdi+10h]; lpCriticalSection
0x18007d339  mov     [rdi], rax
0x18007d33c  xor     r8d, r8d; Flags
0x18007d33f  xor     edx, edx; dwSpinCount
0x18007d341  call    cs:__imp_InitializeCriticalSectionEx
0x18007d347  lea     rax, [rdi+38h]
0x18007d34b  mov     qword ptr [rdi+50h], 0
0x18007d353  mov     [rax], rax
0x18007d356  mov     rcx, rdi
0x18007d359  mov     [rax+8], rax
0x18007d35d  mov     qword ptr [rax+10h], 0
0x18007d365  mov     dword ptr [rdi+58h], 0
0x18007d36c  mov     dword ptr [rdi+5Ch], 0
0x18007d373  mov     qword ptr [rdi+60h], 0
0x18007d37b  mov     dword ptr [rdi+68h], 0
0x18007d382  mov     rax, [rdi]
0x18007d385  mov     rax, [rax+8]
0x18007d389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d38e  xor     r8d, r8d; pcbe
0x18007d391  lea     rcx, ?WorkCallBack@AsyncWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18007d398  mov     rdx, rdi; pv
0x18007d39b  call    cs:__imp_CreateThreadpoolWork
0x18007d3a1  mov     rbx, rax
0x18007d3a4  mov     rax, [rdi+60h]
0x18007d3a8  cmp     rbx, rax
0x18007d3ab  jz      short loc_18007D3C1
0x18007d3ad  test    rax, rax
0x18007d3b0  jz      short loc_18007D3BB
0x18007d3b2  mov     rcx, rax; pwk
0x18007d3b5  call    cs:__imp_CloseThreadpoolWork
0x18007d3bb  mov     [rdi+60h], rbx
0x18007d3bf  jmp     short loc_18007D3C4
0x18007d3c1  mov     rbx, rax
0x18007d3c4  test    rbx, rbx
0x18007d3c7  jnz     short loc_18007D3EF
0x18007d3c9  call    cs:__imp_GetLastError
0x18007d3cf  mov     ebx, eax
0x18007d3d1  test    eax, eax
0x18007d3d3  jle     short loc_18007D3DE
0x18007d3d5  movzx   ebx, ax
0x18007d3d8  or      ebx, 80070000h
0x18007d3de  mov     rax, [rdi]
0x18007d3e1  mov     rcx, rdi
0x18007d3e4  mov     rax, [rax+10h]
0x18007d3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d3ed  jmp     short loc_18007D3FB
0x18007d3ef  mov     [rsi], rdi
0x18007d3f2  xor     ebx, ebx
0x18007d3f4  jmp     short loc_18007D3FB
0x18007d3f6  mov     ebx, 8007000Eh
0x18007d3fb  mov     rsi, [rsp+28h+arg_10]
0x18007d400  mov     eax, ebx
0x18007d402  mov     rbx, [rsp+28h+arg_8]
0x18007d407  add     rsp, 20h
0x18007d40b  pop     rdi
0x18007d40c  retn
```
