# wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18000f270`
- end: `0x18000f2e0`
- name: `?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `112`
- prototype: ``
- caller_count: `44`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ac4`
- `0x18000a2a0`
- `0x180018fa0`
- `0x180019520`
- `0x180019d80`
- `0x180019fc0`
- `0x18001a200`
- `0x18001a440`
- `0x18001a680`
- `0x18001a8c0`
- `0x18001ab00`
- `0x18001ad40`
- `0x18001af80`
- `0x18001b7f0`
- `0x18001c650`
- `0x18001c890`
- `0x18001cad0`
- `0x18001cd10`
- `0x18001cf50`
- `0x18001d7b0`
- `0x18001d9f0`
- `0x18001dc20`
- `0x18001e480`
- `0x18001ece0`
- `0x18001f7c8`
- `0x180023efc`
- `0x18002c4dc`
- `0x18002c760`
- `0x18002c990`
- `0x18002d7e0`
- `0x18002da20`
- `0x18002ebf0`
- `0x18002ee30`
- `0x18002f070`
- `0x18002f2b0`
- `0x180030620`
- `0x180030850`
- `0x180030a90`
- `0x180030cd0`
- `0x180030f10`
- `0x180032920`
- `0x180033880`
- `0x180033ac0`
- `0x180033d00`

## callees

- `0x18000f270`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f286`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f286`

## string_xrefs

- `0x18000f2bb`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 **v1; // rbx
  __int64 v2; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v1 = (__int64 **)(a1 + 288);
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v1 + 6) = 0;
    while ( 1 )
    {
      v2 = **v1;
      if ( !v2 )
        break;
      if ( (__int64 **)v2 == v1 )
      {
        **v1 = (__int64)v1[2];
        break;
      }
      *v1 = (__int64 *)(v2 + 16);
    }
    *v1 = 0;
  }
}

```

## disassembly

```asm
0x18000f270  push    rbx
0x18000f272  sub     rsp, 20h
0x18000f276  cmp     dword ptr [rcx+138h], 0
0x18000f27d  jz      short loc_18000F2A4
0x18000f27f  lea     rbx, [rcx+120h]
0x18000f286  call    cs:__imp_GetCurrentThreadId
0x18000f28c  cmp     [rbx+18h], eax
0x18000f28f  jnz     short loc_18000F2AA
0x18000f291  xor     edx, edx
0x18000f293  mov     [rbx+18h], edx
0x18000f296  mov     rcx, [rbx]
0x18000f299  mov     rax, [rcx]
0x18000f29c  test    rax, rax
0x18000f29f  jnz     short loc_18000F2C9
0x18000f2a1  mov     [rbx], rdx
0x18000f2a4  add     rsp, 20h
0x18000f2a8  pop     rbx
0x18000f2a9  retn
0x18000f2aa  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000f2b1  test    rax, rax
0x18000f2b4  jz      short loc_18000F291
0x18000f2b6  mov     rdx, [rsp+28h]
0x18000f2bb  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000f2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2c7  jmp     short loc_18000F291
0x18000f2c9  cmp     rax, rbx
0x18000f2cc  jz      short loc_18000F2D7
0x18000f2ce  add     rax, 10h
0x18000f2d2  mov     [rbx], rax
0x18000f2d5  jmp     short loc_18000F296
0x18000f2d7  mov     rax, [rbx+10h]
0x18000f2db  mov     [rcx], rax
0x18000f2de  jmp     short loc_18000F2A1
```
