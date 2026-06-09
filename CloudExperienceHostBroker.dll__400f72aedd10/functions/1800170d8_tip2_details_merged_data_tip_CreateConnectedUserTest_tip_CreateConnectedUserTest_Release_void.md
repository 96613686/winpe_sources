# tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>::Release(void)

- ea: `0x1800170d8`
- end: `0x180017110`
- name: `?Release@?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012228`
- `0x18001256c`
- `0x180019454`
- `0x18001a900`

## callees

- `0x180012268`
- `0x1800170d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800170fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800170fd`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 72);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>::~merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x1800170d8  mov     [rsp+arg_0], rbx
0x1800170dd  push    rdi
0x1800170de  sub     rsp, 20h
0x1800170e2  mov     rdi, rcx
0x1800170e5  or      ebx, 0FFFFFFFFh
0x1800170e8  lock xadd [rcx+120h], ebx
0x1800170f0  sub     ebx, 1
0x1800170f3  jnz     short loc_180017103
0x1800170f5  call    ??1?$merged_data@U_tip_CreateConnectedUserTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>::~merged_data<_tip_CreateConnectedUserTest,_tip_CreateConnectedUserTest>(void)
0x1800170fa  mov     rcx, rdi; pv
0x1800170fd  call    cs:__imp_CoTaskMemFree
0x180017103  mov     eax, ebx
0x180017105  mov     rbx, [rsp+28h+arg_0]
0x18001710a  add     rsp, 20h
0x18001710e  pop     rdi
0x18001710f  retn
```
