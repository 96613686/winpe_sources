# tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>::Release(void)

- ea: `0x140013d50`
- end: `0x140013d88`
- name: `?Release@?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000e004`
- `0x1400172d0`
- `0x140017e98`

## callees

- `0x14000e034`
- `0x140013d50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013d75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140013d75`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>::~merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x140013d50  mov     [rsp+arg_0], rbx
0x140013d55  push    rdi
0x140013d56  sub     rsp, 20h
0x140013d5a  mov     rdi, rcx
0x140013d5d  or      ebx, 0FFFFFFFFh
0x140013d60  lock xadd [rcx+118h], ebx
0x140013d68  sub     ebx, 1
0x140013d6b  jnz     short loc_140013D7B
0x140013d6d  call    ??1?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>::~merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>(void)
0x140013d72  mov     rcx, rdi; pv
0x140013d75  call    cs:__imp_CoTaskMemFree
0x140013d7b  mov     eax, ebx
0x140013d7d  mov     rbx, [rsp+28h+arg_0]
0x140013d82  add     rsp, 20h
0x140013d86  pop     rdi
0x140013d87  retn
```
