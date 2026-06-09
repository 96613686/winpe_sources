# wdmDevInterfaceDec

- ea: `0x180002558`
- end: `0x18000261f`
- name: `wdmDevInterfaceDec`
- size: `199`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180001564`
- `0x180001660`
- `0x1800023f0`
- `0x1800077ec`
- `0x1800093a0`
- `0x18001705c`
- `0x18001a7a0`

## callees

- `0x180002558`
- `0x18000f5d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800025ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800025ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002576`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002576`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025ab`

## pseudocode

```c
__int64 __fastcall wdmDevInterfaceDec(_DWORD *a1)
{
  _QWORD *i; // rsi
  _DWORD *v3; // rbx
  HANDLE v6; // rcx

  if ( !a1 )
    return 0;
  EnterCriticalSection(&NumDevsCritSec);
  for ( i = &wdmDevZ; ; i = (_QWORD *)*i )
  {
    v3 = (_DWORD *)*i;
    if ( !*i )
      break;
    if ( a1 == v3 + 8 )
    {
      if ( v3[5]-- == 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids, a1);
        }
        v6 = hHeap;
        *i = *(_QWORD *)v3;
        HeapFree(v6, 0, v3);
      }
      LODWORD(v3) = 1;
      break;
    }
  }
  LeaveCriticalSection(&NumDevsCritSec);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002558  mov     [rsp+arg_8], rbx
0x18000255d  mov     [rsp+arg_10], rsi
0x180002562  push    rdi
0x180002563  sub     rsp, 20h
0x180002567  mov     rdi, rcx
0x18000256a  test    rcx, rcx
0x18000256d  jz      short loc_1800025C3
0x18000256f  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180002576  call    cs:__imp_EnterCriticalSection
0x18000257c  lea     rsi, ?wdmDevZ@@3Utag_wdmdeviceinterface@@A; tag_wdmdeviceinterface wdmDevZ
0x180002583  mov     rbx, [rsi]
0x180002586  test    rbx, rbx
0x180002589  jz      short loc_1800025C7
0x18000258b  lea     rax, [rbx+20h]
0x18000258f  cmp     rdi, rax
0x180002592  jz      short loc_180002599
0x180002594  mov     rsi, rbx
0x180002597  jmp     short loc_180002583
0x180002599  add     dword ptr [rbx+14h], 0FFFFFFFFh
0x18000259d  jz      short loc_1800025C9
0x18000259f  mov     ebx, 1
0x1800025a4  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800025ab  call    cs:__imp_LeaveCriticalSection
0x1800025b1  mov     eax, ebx
0x1800025b3  mov     rbx, [rsp+28h+arg_8]
0x1800025b8  mov     rsi, [rsp+28h+arg_10]
0x1800025bd  add     rsp, 20h
0x1800025c1  pop     rdi
0x1800025c2  retn
0x1800025c3  xor     eax, eax
0x1800025c5  jmp     short loc_1800025B3
0x1800025c7  jmp     short loc_1800025A4
0x1800025c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025d0  lea     rax, WPP_GLOBAL_Control
0x1800025d7  cmp     rcx, rax
0x1800025da  jnz     short loc_1800025F6
0x1800025dc  mov     rax, [rbx]
0x1800025df  mov     r8, rbx; lpMem
0x1800025e2  mov     rcx, cs:hHeap; hHeap
0x1800025e9  xor     edx, edx; dwFlags
0x1800025eb  mov     [rsi], rax
0x1800025ee  call    cs:__imp_HeapFree
0x1800025f4  jmp     short loc_18000259F
0x1800025f6  test    dword ptr [rcx+1Ch], 400000h
0x1800025fd  jz      short loc_1800025DC
0x1800025ff  cmp     byte ptr [rcx+19h], 4
0x180002603  jb      short loc_1800025DC
0x180002605  mov     rcx, [rcx+10h]
0x180002609  lea     r8, WPP_9cbfd48b59f836f28c728f41f2315d00_Traceguids
0x180002610  mov     edx, 0Dh
0x180002615  mov     r9, rdi
0x180002618  call    WPP_SF_S
0x18000261d  jmp     short loc_1800025DC
```
