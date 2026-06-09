# MilInstrumentationHandleFailure_MaybeFailFast(long,ulong,uint,void *)

- ea: `0x14000f8b8`
- end: `0x14000f94d`
- name: `?MilInstrumentationHandleFailure_MaybeFailFast@@YAXJKIPEAX@Z`
- size: `149`
- prototype: `void __fastcall(int, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140002e6c`

## callees

- `0x140003644`
- `0x1400043bc`
- `0x14000f724`
- `0x14000f8b8`
- `0x14000fa84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f8fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f8fe`

## pseudocode

```c
void __fastcall MilInstrumentationHandleFailure_MaybeFailFast(unsigned int a1, unsigned int a2, int a3, void *a4)
{
  if ( a1 + 2003303422 <= 1
    || a1 == -2003302654
    || a1 == -2147024890
    || (a2 & 0x10) != 0 && IsOOM(a1)
    || g_dwFailFastForThreadId
    && g_dwFailFastForThreadId == GetCurrentThreadId()
    && (g_hrFailFastExpectedError >= 0 || a1 == g_hrFailFastExpectedError) )
  {
    ModuleFailFastForHRESULT(a1, a4);
  }
  if ( (a2 & 4) != 0 )
    DoStackCapture(a1, a3, a4);
  if ( (a2 & 1) != 0 )
    MilInstrumentationBreak(a2, a2);
}

```

## disassembly

```asm
0x14000f8b8  push    rbx
0x14000f8ba  push    rbp
0x14000f8bb  push    rsi
0x14000f8bc  push    rdi
0x14000f8bd  sub     rsp, 28h
0x14000f8c1  lea     eax, [rcx+7767FBFEh]
0x14000f8c7  mov     rsi, r9
0x14000f8ca  mov     ebp, r8d
0x14000f8cd  mov     edi, edx
0x14000f8cf  mov     ebx, ecx
0x14000f8d1  cmp     eax, 1
0x14000f8d4  jbe     short loc_14000F942
0x14000f8d6  cmp     ecx, 88980702h
0x14000f8dc  jz      short loc_14000F942
0x14000f8de  cmp     ecx, 80070006h
0x14000f8e4  jz      short loc_14000F942
0x14000f8e6  test    dil, 10h
0x14000f8ea  jz      short loc_14000F8F5
0x14000f8ec  call    ?IsOOM@@YA_NJ@Z; IsOOM(long)
0x14000f8f1  test    al, al
0x14000f8f3  jnz     short loc_14000F942
0x14000f8f5  cmp     cs:?g_dwFailFastForThreadId@@3KA, 0; ulong g_dwFailFastForThreadId
0x14000f8fc  jz      short loc_14000F91A
0x14000f8fe  call    cs:__imp_GetCurrentThreadId
0x14000f904  cmp     cs:?g_dwFailFastForThreadId@@3KA, eax; ulong g_dwFailFastForThreadId
0x14000f90a  jnz     short loc_14000F91A
0x14000f90c  mov     eax, cs:?g_hrFailFastExpectedError@@3JA; long g_hrFailFastExpectedError
0x14000f912  test    eax, eax
0x14000f914  jns     short loc_14000F942
0x14000f916  cmp     ebx, eax
0x14000f918  jz      short loc_14000F942
0x14000f91a  test    dil, 4
0x14000f91e  jz      short loc_14000F92C
0x14000f920  mov     r8, rsi; void *
0x14000f923  mov     edx, ebp; unsigned int
0x14000f925  mov     ecx, ebx; int
0x14000f927  call    ?DoStackCapture@@YAXJIPEAX@Z; DoStackCapture(long,uint,void *)
0x14000f92c  test    dil, 1
0x14000f930  jz      short loc_14000F939
0x14000f932  mov     ecx, edi; unsigned int
0x14000f934  call    ?MilInstrumentationBreak@@YAXK_N@Z; MilInstrumentationBreak(ulong,bool)
0x14000f939  add     rsp, 28h
0x14000f93d  pop     rdi
0x14000f93e  pop     rsi
0x14000f93f  pop     rbp
0x14000f940  pop     rbx
0x14000f941  retn
0x14000f942  mov     rdx, rsi
0x14000f945  mov     ecx, ebx
0x14000f947  call    ModuleFailFastForHRESULT
```
