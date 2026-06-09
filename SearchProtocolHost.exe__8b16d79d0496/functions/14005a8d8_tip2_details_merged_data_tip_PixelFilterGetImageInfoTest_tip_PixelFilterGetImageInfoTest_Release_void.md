# tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::Release(void)

- ea: `0x14005a8d8`
- end: `0x14005a910`
- name: `?Release@?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400586ac`
- `0x140059a60`
- `0x14005b324`
- `0x14005b798`

## callees

- `0x1400586c8`
- `0x14005a8d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a8fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a8fd`

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
0x14005a8d8  mov     [rsp+arg_0], rbx
0x14005a8dd  push    rdi
0x14005a8de  sub     rsp, 20h
0x14005a8e2  mov     rdi, rcx
0x14005a8e5  or      ebx, 0FFFFFFFFh
0x14005a8e8  lock xadd [rcx+138h], ebx
0x14005a8f0  sub     ebx, 1
0x14005a8f3  jnz     short loc_14005A903
0x14005a8f5  call    ??1?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>::~merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>(void)
0x14005a8fa  mov     rcx, rdi; pv
0x14005a8fd  call    cs:__imp_CoTaskMemFree
0x14005a903  mov     eax, ebx
0x14005a905  mov     rbx, [rsp+28h+arg_0]
0x14005a90a  add     rsp, 20h
0x14005a90e  pop     rdi
0x14005a90f  retn
```
