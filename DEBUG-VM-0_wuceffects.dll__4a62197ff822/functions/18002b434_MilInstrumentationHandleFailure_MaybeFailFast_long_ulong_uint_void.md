# MilInstrumentationHandleFailure_MaybeFailFast(long,ulong,uint,void *)

- ea: `0x18002b434`
- end: `0x18002b4c9`
- name: `?MilInstrumentationHandleFailure_MaybeFailFast@@YAXJKIPEAX@Z`
- size: `149`
- prototype: `void __fastcall(int, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002b3b0`

## callees

- `0x180026134`
- `0x18002b188`
- `0x18002b318`
- `0x18002b434`
- `0x18002b5cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b47a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b47a`

## pseudocode

```c
void __fastcall MilInstrumentationHandleFailure_MaybeFailFast(unsigned int a1, unsigned int a2, int a3, void *a4)
{
  if ( a1 + 2003303422 <= 1
    || a1 == -2147024890
    || a1 == -2003302654
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
0x18002b434  push    rbx
0x18002b436  push    rbp
0x18002b437  push    rsi
0x18002b438  push    rdi
0x18002b439  sub     rsp, 28h
0x18002b43d  lea     eax, [rcx+7767FBFEh]
0x18002b443  mov     rsi, r9
0x18002b446  mov     ebp, r8d
0x18002b449  mov     edi, edx
0x18002b44b  mov     ebx, ecx
0x18002b44d  cmp     eax, 1
0x18002b450  jbe     short loc_18002B4BE
0x18002b452  cmp     ecx, 80070006h
0x18002b458  jz      short loc_18002B4BE
0x18002b45a  cmp     ecx, 88980702h
0x18002b460  jz      short loc_18002B4BE
0x18002b462  test    dil, 10h
0x18002b466  jz      short loc_18002B471
0x18002b468  call    ?IsOOM@@YA_NJ@Z; IsOOM(long)
0x18002b46d  test    al, al
0x18002b46f  jnz     short loc_18002B4BE
0x18002b471  cmp     cs:?g_dwFailFastForThreadId@@3KA, 0; ulong g_dwFailFastForThreadId
0x18002b478  jz      short loc_18002B496
0x18002b47a  call    cs:__imp_GetCurrentThreadId
0x18002b480  cmp     cs:?g_dwFailFastForThreadId@@3KA, eax; ulong g_dwFailFastForThreadId
0x18002b486  jnz     short loc_18002B496
0x18002b488  mov     eax, cs:?g_hrFailFastExpectedError@@3JA; long g_hrFailFastExpectedError
0x18002b48e  test    eax, eax
0x18002b490  jns     short loc_18002B4BE
0x18002b492  cmp     ebx, eax
0x18002b494  jz      short loc_18002B4BE
0x18002b496  test    dil, 4
0x18002b49a  jz      short loc_18002B4A8
0x18002b49c  mov     r8, rsi; void *
0x18002b49f  mov     edx, ebp; unsigned int
0x18002b4a1  mov     ecx, ebx; int
0x18002b4a3  call    ?DoStackCapture@@YAXJIPEAX@Z; DoStackCapture(long,uint,void *)
0x18002b4a8  test    dil, 1
0x18002b4ac  jz      short loc_18002B4B5
0x18002b4ae  mov     ecx, edi; unsigned int
0x18002b4b0  call    ?MilInstrumentationBreak@@YAXK_N@Z; MilInstrumentationBreak(ulong,bool)
0x18002b4b5  add     rsp, 28h
0x18002b4b9  pop     rdi
0x18002b4ba  pop     rsi
0x18002b4bb  pop     rbp
0x18002b4bc  pop     rbx
0x18002b4bd  retn
0x18002b4be  mov     rdx, rsi
0x18002b4c1  mov     ecx, ebx
0x18002b4c3  call    ModuleFailFastForHRESULT
```
