# tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>::Release(void)

- ea: `0x140044c44`
- end: `0x140044c7c`
- name: `?Release@?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140043990`
- `0x14004625c`
- `0x140046478`

## callees

- `0x140043a24`
- `0x140044c44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044c69`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>::~merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x140044c44  mov     [rsp+arg_0], rbx
0x140044c49  push    rdi
0x140044c4a  sub     rsp, 20h
0x140044c4e  mov     rdi, rcx
0x140044c51  or      ebx, 0FFFFFFFFh
0x140044c54  lock xadd [rcx+118h], ebx
0x140044c5c  sub     ebx, 1
0x140044c5f  jnz     short loc_140044C6F
0x140044c61  call    ??1?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>::~merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>(void)
0x140044c66  mov     rcx, rdi; pv
0x140044c69  call    cs:__imp_CoTaskMemFree
0x140044c6f  mov     eax, ebx
0x140044c71  mov     rbx, [rsp+28h+arg_0]
0x140044c76  add     rsp, 20h
0x140044c7a  pop     rdi
0x140044c7b  retn
```
