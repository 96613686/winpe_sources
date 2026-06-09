# tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::Release(void)

- ea: `0x140039db0`
- end: `0x140039de8`
- name: `?Release@?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140037db0`
- `0x140038f90`
- `0x14003a4b0`
- `0x14003a618`

## callees

- `0x140037dcc`
- `0x140039db0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039dd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140039dd5`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 78);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::~merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x140039db0  mov     [rsp+arg_0], rbx
0x140039db5  push    rdi
0x140039db6  sub     rsp, 20h
0x140039dba  mov     rdi, rcx
0x140039dbd  or      ebx, 0FFFFFFFFh
0x140039dc0  lock xadd [rcx+138h], ebx
0x140039dc8  sub     ebx, 1
0x140039dcb  jnz     short loc_140039DDB
0x140039dcd  call    ??1?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::~merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>(void)
0x140039dd2  mov     rcx, rdi; pv
0x140039dd5  call    cs:__imp_CoTaskMemFree
0x140039ddb  mov     eax, ebx
0x140039ddd  mov     rbx, [rsp+28h+arg_0]
0x140039de2  add     rsp, 20h
0x140039de6  pop     rdi
0x140039de7  retn
```
