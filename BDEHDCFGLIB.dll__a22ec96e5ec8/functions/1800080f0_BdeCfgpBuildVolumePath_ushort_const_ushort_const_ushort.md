# BdeCfgpBuildVolumePath(ushort const *,ushort const *,ushort * *)

- ea: `0x1800080f0`
- end: `0x1800081b5`
- name: `?BdeCfgpBuildVolumePath@@YAJPEBG0PEAPEAG@Z`
- size: `197`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180007070`
- `0x180007bd0`
- `0x1800083c4`
- `0x1800086f8`

## callees

- `0x180006bbc`
- `0x1800080f0`
- `0x180008e1c`
- `0x18000990c`

## import_xrefs

- `msvcrt!wcsstr` at `0x180008187`
- `msvcrt!wcsstr` at `0x180008187`
- `KERNEL32!HeapAlloc` at `0x180008140`
- `KERNEL32!HeapAlloc` at `0x180008140`
- `KERNEL32!GetProcessHeap` at `0x18000812f`
- `KERNEL32!GetProcessHeap` at `0x18000812f`

## pseudocode

```c
__int64 __fastcall BdeCfgpBuildVolumePath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v3; // rax
  __int64 v5; // r9
  unsigned __int64 v8; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rbx
  int v12; // edi

  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  do
    ++v3;
  while ( a1[v3] );
  v8 = v3 + v5 + 1;
  ProcessHeap = GetProcessHeap();
  v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v8);
  v11 = v10;
  if ( v10 )
  {
    v12 = StringCchCopyW(v10, v8, a1);
    if ( v12 >= 0 )
    {
      v12 = StringCchCatW(v11, v8, a2);
      if ( v12 >= 0 )
      {
        if ( wcsstr(v11, L"\\\\?") == v11 )
          v11[1] = 63;
        *a3 = v11;
        v11 = 0;
      }
    }
  }
  else
  {
    v12 = -2147024882;
  }
  BdeCfgpFree(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800080f0  push    rbx
0x1800080f2  push    rbp
0x1800080f3  push    rsi
0x1800080f4  push    rdi
0x1800080f5  push    r14
0x1800080f7  push    r15
0x1800080f9  sub     rsp, 28h
0x1800080fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008101  mov     r14, r8
0x180008104  mov     r9, rax
0x180008107  xor     r15d, r15d
0x18000810a  mov     rbp, rdx
0x18000810d  mov     rdi, rcx
0x180008110  inc     r9
0x180008113  cmp     [rdx+r9*2], r15w
0x180008118  jnz     short loc_180008110
0x18000811a  inc     rax
0x18000811d  cmp     [rcx+rax*2], r15w
0x180008122  jnz     short loc_18000811A
0x180008124  lea     rsi, [r9+1]
0x180008128  add     rsi, rax
0x18000812b  lea     rbx, [rsi+rsi]
0x18000812f  call    cs:__imp_GetProcessHeap
0x180008135  mov     r8, rbx; dwBytes
0x180008138  mov     edx, 8; dwFlags
0x18000813d  mov     rcx, rax; hHeap
0x180008140  call    cs:__imp_HeapAlloc
0x180008146  mov     rbx, rax
0x180008149  test    rax, rax
0x18000814c  jnz     short loc_180008155
0x18000814e  mov     edi, 8007000Eh
0x180008153  jmp     short loc_18000819E
0x180008155  mov     r8, rdi; unsigned __int16 *
0x180008158  mov     rdx, rsi; unsigned __int64
0x18000815b  mov     rcx, rbx; unsigned __int16 *
0x18000815e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008163  mov     edi, eax
0x180008165  test    eax, eax
0x180008167  js      short loc_18000819E
0x180008169  mov     r8, rbp; unsigned __int16 *
0x18000816c  mov     rdx, rsi; unsigned __int64
0x18000816f  mov     rcx, rbx; unsigned __int16 *
0x180008172  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008177  mov     edi, eax
0x180008179  test    eax, eax
0x18000817b  js      short loc_18000819E
0x18000817d  lea     rdx, SubStr; "\\\\?"
0x180008184  mov     rcx, rbx; Str
0x180008187  call    cs:__imp_wcsstr
0x18000818d  cmp     rax, rbx
0x180008190  jnz     short loc_180008198
0x180008192  mov     word ptr [rbx+2], 3Fh ; '?'
0x180008198  mov     [r14], rbx
0x18000819b  mov     rbx, r15
0x18000819e  mov     rcx, rbx; lpMem
0x1800081a1  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x1800081a6  mov     eax, edi
0x1800081a8  add     rsp, 28h
0x1800081ac  pop     r15
0x1800081ae  pop     r14
0x1800081b0  pop     rdi
0x1800081b1  pop     rsi
0x1800081b2  pop     rbp
0x1800081b3  pop     rbx
0x1800081b4  retn
```
