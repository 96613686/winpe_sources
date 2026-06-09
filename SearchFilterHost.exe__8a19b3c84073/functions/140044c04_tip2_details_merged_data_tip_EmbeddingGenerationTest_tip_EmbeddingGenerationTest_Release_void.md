# tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>::Release(void)

- ea: `0x140044c04`
- end: `0x140044c3c`
- name: `?Release@?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140043974`
- `0x140046234`
- `0x1400463b0`

## callees

- `0x1400439f4`
- `0x140044c04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044c29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044c29`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 74);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>::~merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x140044c04  mov     [rsp+arg_0], rbx
0x140044c09  push    rdi
0x140044c0a  sub     rsp, 20h
0x140044c0e  mov     rdi, rcx
0x140044c11  or      ebx, 0FFFFFFFFh
0x140044c14  lock xadd [rcx+128h], ebx
0x140044c1c  sub     ebx, 1
0x140044c1f  jnz     short loc_140044C2F
0x140044c21  call    ??1?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>::~merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>(void)
0x140044c26  mov     rcx, rdi; pv
0x140044c29  call    cs:__imp_CoTaskMemFree
0x140044c2f  mov     eax, ebx
0x140044c31  mov     rbx, [rsp+28h+arg_0]
0x140044c36  add     rsp, 20h
0x140044c3a  pop     rdi
0x140044c3b  retn
```
