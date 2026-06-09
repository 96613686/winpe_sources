# wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)

- ea: `0x1800100cc`
- end: `0x1800101b3`
- name: `?ContinueOnCurrentThread@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ`
- size: `231`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800139a4`
- `0x180019ec0`
- `0x1800229a0`

## callees

- `0x180009fc8`
- `0x18000bbe8`
- `0x1800100cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010136`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010128`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010128`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
        __int64 a1,
        __int64 a2)
{
  int *v4; // rdx
  int v5; // eax
  _WORD *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rbp
  HANDLE ProcessHeap; // rax
  void *v10; // rax

  v4 = *(int **)(a1 + 272);
  v5 = *v4;
  *(_BYTE *)(a2 + 24) = 0;
  if ( v5 == 1 )
  {
    *(_DWORD *)a2 = v4[10];
    *(_QWORD *)(a2 + 8) = *((_QWORD *)v4 + 6);
    v6 = (_WORD *)*((_QWORD *)v4 + 7);
    if ( *((_BYTE *)v4 + 64) )
    {
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      if ( v7 )
      {
        v8 = 2 * v7 + 2;
        ProcessHeap = GetProcessHeap();
        v10 = HeapAlloc(ProcessHeap, 0, v8);
        *(_QWORD *)(a2 + 16) = v10;
        if ( v10 )
        {
          *(_BYTE *)(a2 + 24) = 1;
          memcpy_s(v10, v8, v6, v8);
        }
      }
    }
    else
    {
      *(_QWORD *)(a2 + 16) = v6;
    }
    *(_QWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 40) = a1;
    *(_QWORD *)(a2 + 48) = 0;
    *(_DWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = a2;
    *(_BYTE *)(a2 + 72) = 0;
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a2 + 32));
  }
  else
  {
    *(_OWORD *)a2 = 0;
    *(_OWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 32) = 0;
    *(_QWORD *)(a2 + 40) = 0;
    *(_QWORD *)(a2 + 48) = 0;
    *(_DWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = 0;
    *(_BYTE *)(a2 + 72) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1800100cc  push    rbx
0x1800100ce  push    rbp
0x1800100cf  push    rsi
0x1800100d0  push    rdi
0x1800100d1  push    r14
0x1800100d3  sub     rsp, 20h
0x1800100d7  mov     rbx, rdx
0x1800100da  mov     rsi, rcx
0x1800100dd  mov     rdx, [rcx+110h]
0x1800100e4  mov     eax, [rdx]
0x1800100e6  xor     r14d, r14d
0x1800100e9  mov     [rbx+18h], r14b
0x1800100ed  cmp     eax, 1
0x1800100f0  jnz     loc_180010183
0x1800100f6  mov     eax, [rdx+28h]
0x1800100f9  mov     [rbx], eax
0x1800100fb  mov     rax, [rdx+30h]
0x1800100ff  mov     [rbx+8], rax
0x180010103  mov     rdi, [rdx+38h]
0x180010107  cmp     [rdx+40h], r14b
0x18001010b  jz      short loc_18001015C
0x18001010d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010111  inc     rax
0x180010114  cmp     [rdi+rax*2], r14w
0x180010119  jnz     short loc_180010111
0x18001011b  test    rax, rax
0x18001011e  jz      short loc_180010160
0x180010120  lea     rbp, ds:2[rax*2]
0x180010128  call    cs:__imp_GetProcessHeap
0x18001012e  mov     rcx, rax; hHeap
0x180010131  mov     r8, rbp; dwBytes
0x180010134  xor     edx, edx; dwFlags
0x180010136  call    cs:__imp_HeapAlloc
0x18001013c  mov     [rbx+10h], rax
0x180010140  test    rax, rax
0x180010143  jz      short loc_180010160
0x180010145  mov     byte ptr [rbx+18h], 1
0x180010149  mov     r9, rbp; SourceSize
0x18001014c  mov     r8, rdi; Source
0x18001014f  mov     rdx, rbp; DestinationSize
0x180010152  mov     rcx, rax; Destination
0x180010155  call    memcpy_s
0x18001015a  jmp     short loc_180010160
0x18001015c  mov     [rbx+10h], rdi
0x180010160  lea     rcx, [rbx+20h]; this
0x180010164  mov     [rcx], r14
0x180010167  mov     [rcx+8], rsi
0x18001016b  mov     [rcx+10h], r14
0x18001016f  mov     [rcx+18h], r14d
0x180010173  mov     [rcx+20h], rbx
0x180010177  mov     [rcx+28h], r14b
0x18001017b  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180010180  nop
0x180010181  jmp     short loc_1800101A5
0x180010183  xorps   xmm0, xmm0
0x180010186  movups  xmmword ptr [rbx], xmm0
0x180010189  movups  xmmword ptr [rbx+10h], xmm0
0x18001018d  mov     [rbx+20h], r14
0x180010191  mov     [rbx+28h], r14
0x180010195  mov     [rbx+30h], r14
0x180010199  mov     [rbx+38h], r14d
0x18001019d  mov     [rbx+40h], r14
0x1800101a1  mov     [rbx+48h], r14b
0x1800101a5  mov     rax, rbx
0x1800101a8  add     rsp, 20h
0x1800101ac  pop     r14
0x1800101ae  pop     rdi
0x1800101af  pop     rsi
0x1800101b0  pop     rbp
0x1800101b1  pop     rbx
0x1800101b2  retn
```
