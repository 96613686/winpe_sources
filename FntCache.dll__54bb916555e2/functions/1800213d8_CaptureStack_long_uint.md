# CaptureStack(long,uint)

- ea: `0x1800213d8`
- end: `0x18002146e`
- name: `?CaptureStack@@YAXJI@Z`
- size: `150`
- prototype: `void __fastcall(int, unsigned int)`
- caller_count: `32`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000da8c`
- `0x18000de84`
- `0x18000f56c`
- `0x1800127fc`
- `0x18001c490`
- `0x180020368`
- `0x180020e6c`
- `0x180021650`
- `0x1800217ac`
- `0x180022400`
- `0x180025a90`
- `0x180025d84`
- `0x180026044`
- `0x18002a760`
- `0x18002aa00`
- `0x18002b050`
- `0x18002c984`
- `0x18002cf80`
- `0x180030b4c`
- `0x1800448b4`
- `0x18005446c`
- `0x18005531c`
- `0x180088cc0`
- `0x18009ade8`
- `0x18009e3b8`
- `0x18009e420`
- `0x18009f1ec`
- `0x18009fed4`
- `0x18009ff3c`
- `0x1800a1558`
- `0x1800a1d7c`
- `0x1800a456c`

## callees

- `0x1800213d8`
- `0x18004d664`
- `0x180092294`
- `0x1800ab180`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021420`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021420`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18002143a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18002143a`

## pseudocode

```c
void __fastcall CaptureStack(int a1, const char *a2)
{
  int v2; // esi
  volatile int v4; // ecx
  __int64 v5; // rdx
  struct StackCaptureFrame near **v6; // rbx

  v2 = (int)a2;
  if ( !a1 )
  {
    FailAssert(0x7Bu, a2);
    __debugbreak();
  }
  EnsureStackCaptureRegisteredWithWER();
  do
  {
    v4 = g_nCurrentStackCaptureIndex;
    v5 = ((_BYTE)g_nCurrentStackCaptureIndex + 1) & 7;
  }
  while ( v4 != _InterlockedCompareExchange(&g_nCurrentStackCaptureIndex, v5, g_nCurrentStackCaptureIndex) );
  v6 = &g_StackCaptureFrames + 10 * v5;
  *((_DWORD *)v6 + 16) = a1;
  *((_DWORD *)v6 + 17) = v2;
  *((_DWORD *)v6 + 18) = GetCurrentThreadId();
  *v6 = 0;
  if ( !RtlCaptureStackBackTrace(1u, 8u, (PVOID *)v6, 0) )
    memset_0(v6, 224, 0x40u);
}

```

## disassembly

```asm
0x1800213d8  push    rbx
0x1800213da  push    rbp
0x1800213db  push    rsi
0x1800213dc  push    rdi
0x1800213dd  sub     rsp, 28h
0x1800213e1  mov     esi, edx
0x1800213e3  mov     edi, ecx
0x1800213e5  test    ecx, ecx
0x1800213e7  jz      short loc_18002144E
0x1800213e9  call    ?EnsureStackCaptureRegisteredWithWER@@YAXXZ; EnsureStackCaptureRegisteredWithWER(void)
0x1800213ee  mov     ecx, cs:?g_nCurrentStackCaptureIndex@@3JC; long volatile g_nCurrentStackCaptureIndex
0x1800213f4  mov     eax, ecx
0x1800213f6  lea     edx, [rcx+1]
0x1800213f9  and     edx, 7
0x1800213fc  lock cmpxchg cs:?g_nCurrentStackCaptureIndex@@3JC, edx; long volatile g_nCurrentStackCaptureIndex
0x180021404  cmp     ecx, eax
0x180021406  jnz     short loc_1800213EE
0x180021408  lea     rbx, [rdx+rdx*4]
0x18002140c  lea     rax, ?g_StackCaptureFrames@@3PAUStackCaptureFrame@@A; StackCaptureFrame near * g_StackCaptureFrames
0x180021413  shl     rbx, 4
0x180021417  add     rbx, rax
0x18002141a  mov     [rbx+40h], edi
0x18002141d  mov     [rbx+44h], esi
0x180021420  call    cs:__imp_GetCurrentThreadId
0x180021426  mov     [rbx+48h], eax
0x180021429  xor     r9d, r9d; BackTraceHash
0x18002142c  xor     eax, eax
0x18002142e  mov     r8, rbx; BackTrace
0x180021431  mov     [rbx], rax
0x180021434  lea     edx, [rax+8]; FramesToCapture
0x180021437  lea     ecx, [rax+1]; FramesToSkip
0x18002143a  call    cs:__imp_RtlCaptureStackBackTrace
0x180021440  test    ax, ax
0x180021443  jz      short loc_180021459
0x180021445  add     rsp, 28h
0x180021449  pop     rdi
0x18002144a  pop     rsi
0x18002144b  pop     rbp
0x18002144c  pop     rbx
0x18002144d  retn
0x18002144e  mov     ecx, 7Bh ; '{'; unsigned int
0x180021453  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x180021458  int     3; Trap to Debugger
0x180021459  mov     edx, 0E0h; Val
0x18002145e  mov     r8d, 40h ; '@'; Size
0x180021464  mov     rcx, rbx; void *
0x180021467  call    memset_0
0x18002146c  jmp     short loc_180021445
```
