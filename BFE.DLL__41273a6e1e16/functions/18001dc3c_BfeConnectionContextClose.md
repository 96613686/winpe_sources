# BfeConnectionContextClose

- ea: `0x18001dc3c`
- end: `0x18001dcf9`
- name: `BfeConnectionContextClose`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18001d9ac`

## callees

- `0x1800087f0`
- `0x18000e7e0`
- `0x18001dc3c`
- `0x18001dd00`
- `0x180057b80`
- `0x180059568`
- `0x18005aa60`
- `0x1800799f0`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18001dc66`
- `ntdll!RtlRemoveEntryHashTable` at `0x18001dc8c`
- `ntdll!RtlRemoveEntryHashTable` at `0x18001dc66`
- `ntdll!RtlRemoveEntryHashTable` at `0x18001dc8c`

## pseudocode

```c
__int64 __fastcall BfeConnectionContextClose(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v4; // [rsp+20h] [rbp-18h] BYREF

  v4 = a1;
  RtlRemoveEntryHashTable(qword_1800F5E48, a1, 0);
  WfpRestructureHashtable(qword_1800F5E48);
  RtlRemoveEntryHashTable(qword_1800F5E18, a1 + 24, 0);
  WfpRestructureHashtable(qword_1800F5E18);
  BfeConnectionChangeDispatch(1, *(_QWORD *)(a1 + 48));
  BfeConnectionLogClose(*(_QWORD *)(a1 + 48));
  BfeConnectionStatAccountingCloseConnection(*(_QWORD *)(a1 + 48));
  v2 = *(_QWORD *)(a1 + 48);
  if ( v2 )
    BfeDestroyInner_FWPM_CONNECTION0(v2);
  WfpMemFree(a1 + 48);
  return WfpMemFree(&v4);
}

```

## disassembly

```asm
0x18001dc3c  push    rbx
0x18001dc3e  sub     rsp, 30h
0x18001dc42  mov     rax, cs:__security_cookie
0x18001dc49  xor     rax, rsp
0x18001dc4c  mov     [rsp+38h+var_10], rax
0x18001dc51  mov     rbx, rcx
0x18001dc54  mov     [rsp+38h+var_18], rcx
0x18001dc59  mov     rdx, rcx
0x18001dc5c  xor     r8d, r8d
0x18001dc5f  lea     rcx, qword_1800F5E48
0x18001dc66  call    cs:__imp_RtlRemoveEntryHashTable
0x18001dc6d  nop     dword ptr [rax+rax+00h]
0x18001dc72  lea     rcx, qword_1800F5E48
0x18001dc79  call    WfpRestructureHashtable
0x18001dc7e  lea     rdx, [rbx+18h]
0x18001dc82  xor     r8d, r8d
0x18001dc85  lea     rcx, qword_1800F5E18
0x18001dc8c  call    cs:__imp_RtlRemoveEntryHashTable
0x18001dc93  nop     dword ptr [rax+rax+00h]
0x18001dc98  lea     rcx, qword_1800F5E18
0x18001dc9f  call    WfpRestructureHashtable
0x18001dca4  mov     rdx, [rbx+30h]
0x18001dca8  mov     ecx, 1
0x18001dcad  call    BfeConnectionChangeDispatch
0x18001dcb2  mov     rcx, [rbx+30h]
0x18001dcb6  call    BfeConnectionLogClose
0x18001dcbb  mov     rcx, [rbx+30h]
0x18001dcbf  call    BfeConnectionStatAccountingCloseConnection
0x18001dcc4  mov     rcx, [rbx+30h]
0x18001dcc8  test    rcx, rcx
0x18001dccb  jz      short loc_18001DCD2
0x18001dccd  call    BfeDestroyInner_FWPM_CONNECTION0
0x18001dcd2  lea     rcx, [rbx+30h]
0x18001dcd6  call    WfpMemFree
0x18001dcdb  lea     rcx, [rsp+38h+var_18]
0x18001dce0  call    WfpMemFree
0x18001dce5  mov     rcx, [rsp+38h+var_10]
0x18001dcea  xor     rcx, rsp; StackCookie
0x18001dced  call    __security_check_cookie
0x18001dcf2  add     rsp, 30h
0x18001dcf6  pop     rbx
0x18001dcf7  retn
```
