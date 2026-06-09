# MilInstrumentationHandleFailure_MaybeFailFast(long,ulong,uint,void *)

- ea: `0x180020370`
- end: `0x180020405`
- name: `?MilInstrumentationHandleFailure_MaybeFailFast@@YAXJKIPEAX@Z`
- size: `149`
- prototype: `void __fastcall(int, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800202ec`

## callees

- `0x18002006c`
- `0x1800200c0`
- `0x180020254`
- `0x180020370`
- `0x180020504`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800203b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800203b6`

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
    JUMPOUT(0x180020404LL);
  }
  if ( (a2 & 4) != 0 )
    DoStackCapture(a1, a3, a4);
  if ( (a2 & 1) != 0 )
    MilInstrumentationBreak(a2, a2);
}

```

## disassembly

```asm
0x180020370  push    rbx
0x180020372  push    rbp
0x180020373  push    rsi
0x180020374  push    rdi
0x180020375  sub     rsp, 28h
0x180020379  lea     eax, [rcx+7767FBFEh]
0x18002037f  mov     rsi, r9
0x180020382  mov     ebp, r8d
0x180020385  mov     edi, edx
0x180020387  mov     ebx, ecx
0x180020389  cmp     eax, 1
0x18002038c  jbe     short loc_1800203FA
0x18002038e  cmp     ecx, 88980702h
0x180020394  jz      short loc_1800203FA
0x180020396  cmp     ecx, 80070006h
0x18002039c  jz      short loc_1800203FA
0x18002039e  test    dil, 10h
0x1800203a2  jz      short loc_1800203AD
0x1800203a4  call    ?IsOOM@@YA_NJ@Z; IsOOM(long)
0x1800203a9  test    al, al
0x1800203ab  jnz     short loc_1800203FA
0x1800203ad  cmp     cs:?g_dwFailFastForThreadId@@3KA, 0; ulong g_dwFailFastForThreadId
0x1800203b4  jz      short loc_1800203D2
0x1800203b6  call    cs:__imp_GetCurrentThreadId
0x1800203bc  cmp     cs:?g_dwFailFastForThreadId@@3KA, eax; ulong g_dwFailFastForThreadId
0x1800203c2  jnz     short loc_1800203D2
0x1800203c4  mov     eax, cs:?g_hrFailFastExpectedError@@3JA; long g_hrFailFastExpectedError
0x1800203ca  test    eax, eax
0x1800203cc  jns     short loc_1800203FA
0x1800203ce  cmp     ebx, eax
0x1800203d0  jz      short loc_1800203FA
0x1800203d2  test    dil, 4
0x1800203d6  jz      short loc_1800203E4
0x1800203d8  mov     r8, rsi; void *
0x1800203db  mov     edx, ebp; unsigned int
0x1800203dd  mov     ecx, ebx; int
0x1800203df  call    ?DoStackCapture@@YAXJIPEAX@Z; DoStackCapture(long,uint,void *)
0x1800203e4  test    dil, 1
0x1800203e8  jz      short loc_1800203F1
0x1800203ea  mov     ecx, edi; unsigned int
0x1800203ec  call    ?MilInstrumentationBreak@@YAXK_N@Z; MilInstrumentationBreak(ulong,bool)
0x1800203f1  add     rsp, 28h
0x1800203f5  pop     rdi
0x1800203f6  pop     rsi
0x1800203f7  pop     rbp
0x1800203f8  pop     rbx
0x1800203f9  retn
0x1800203fa  mov     rdx, rsi
0x1800203fd  mov     ecx, ebx
0x1800203ff  call    ModuleFailFastForHRESULT
```
