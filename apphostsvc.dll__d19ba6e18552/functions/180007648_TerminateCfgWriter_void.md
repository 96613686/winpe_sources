# TerminateCfgWriter(void * *)

- ea: `0x180007648`
- end: `0x1800076d9`
- name: `?TerminateCfgWriter@@YAXPEAPEAX@Z`
- size: `145`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006ad0`

## callees

- `0x180007648`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000765c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000765c`

## pseudocode

```c
void __fastcall TerminateCfgWriter(void **a1)
{
  HANDLE v2; // rcx
  struct CIISCfgVssWriter *v3; // rcx
  __int64 v4; // rdx

  v2 = *a1;
  if ( v2 )
  {
    if ( !WaitForSingleObject(v2, 0xFFFFFFFF) )
    {
      v3 = g_pIISCfgVssWriter;
      if ( g_pIISCfgVssWriter )
      {
        if ( g_fCfgWriterSubscribed )
        {
          v4 = *((_QWORD *)g_pIISCfgVssWriter + 1);
          if ( v4 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4 + 40LL))(*((_QWORD *)g_pIISCfgVssWriter + 1));
            v3 = g_pIISCfgVssWriter;
            g_fCfgWriterSubscribed = 0;
          }
        }
        if ( v3 )
          (**(void (__fastcall ***)(struct CIISCfgVssWriter *, __int64))v3)(v3, 1);
        g_pIISCfgVssWriter = 0;
      }
    }
    CloseHandle(*a1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180007648  push    rbx
0x18000764a  sub     rsp, 20h
0x18000764e  mov     rbx, rcx
0x180007651  mov     rcx, [rcx]; hHandle
0x180007654  test    rcx, rcx
0x180007657  jz      short loc_1800076D3
0x180007659  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000765c  call    cs:__imp_WaitForSingleObject
0x180007662  test    eax, eax
0x180007664  jnz     short loc_1800076C3
0x180007666  mov     rcx, cs:?g_pIISCfgVssWriter@@3PEAVCIISCfgVssWriter@@EA; CIISCfgVssWriter * g_pIISCfgVssWriter
0x18000766d  test    rcx, rcx
0x180007670  jz      short loc_1800076C3
0x180007672  cmp     cs:?g_fCfgWriterSubscribed@@3HA, eax; int g_fCfgWriterSubscribed
0x180007678  jz      short loc_1800076A3
0x18000767a  mov     rdx, [rcx+8]
0x18000767e  test    rdx, rdx
0x180007681  jz      short loc_1800076A3
0x180007683  mov     rax, [rdx]
0x180007686  mov     rcx, rdx
0x180007689  mov     rax, [rax+28h]
0x18000768d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007692  mov     rcx, cs:?g_pIISCfgVssWriter@@3PEAVCIISCfgVssWriter@@EA; CIISCfgVssWriter * g_pIISCfgVssWriter
0x180007699  mov     cs:?g_fCfgWriterSubscribed@@3HA, 0; int g_fCfgWriterSubscribed
0x1800076a3  test    rcx, rcx
0x1800076a6  jz      short loc_1800076B8
0x1800076a8  mov     rax, [rcx]
0x1800076ab  mov     edx, 1
0x1800076b0  mov     rax, [rax]
0x1800076b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076b8  mov     cs:?g_pIISCfgVssWriter@@3PEAVCIISCfgVssWriter@@EA, 0; CIISCfgVssWriter * g_pIISCfgVssWriter
0x1800076c3  mov     rcx, [rbx]; hObject
0x1800076c6  call    cs:__imp_CloseHandle
0x1800076cc  mov     qword ptr [rbx], 0
0x1800076d3  add     rsp, 20h
0x1800076d7  pop     rbx
0x1800076d8  retn
```
