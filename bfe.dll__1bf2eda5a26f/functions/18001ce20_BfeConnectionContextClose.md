# BfeConnectionContextClose

- ea: `0x18001ce20`
- end: `0x18001ced0`
- name: `BfeConnectionContextClose`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18001cbb4`

## callees

- `0x180008240`
- `0x18000e000`
- `0x18001ce20`
- `0x18001ced8`
- `0x180055d28`
- `0x180057364`
- `0x180058b30`
- `0x180076f28`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18001ce4a`
- `ntdll!RtlRemoveEntryHashTable` at `0x18001ce6a`
- `ntdll!RtlRemoveEntryHashTable` at `0x18001ce4a`
- `ntdll!RtlRemoveEntryHashTable` at `0x18001ce6a`

## pseudocode

```c
__int64 __fastcall BfeConnectionContextClose(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v4; // [rsp+20h] [rbp-18h] BYREF

  v4 = a1;
  RtlRemoveEntryHashTable(&qword_1800F2668[248], a1, 0);
  WfpRestructureHashtable(&qword_1800F2668[248]);
  RtlRemoveEntryHashTable(&qword_1800F2668[242], a1 + 24, 0);
  WfpRestructureHashtable(&qword_1800F2668[242]);
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
0x18001ce20  push    rbx
0x18001ce22  sub     rsp, 30h
0x18001ce26  mov     rax, cs:__security_cookie
0x18001ce2d  xor     rax, rsp
0x18001ce30  mov     [rsp+38h+var_10], rax
0x18001ce35  mov     rbx, rcx
0x18001ce38  mov     [rsp+38h+var_18], rcx
0x18001ce3d  mov     rdx, rcx
0x18001ce40  xor     r8d, r8d
0x18001ce43  lea     rcx, qword_1800F2668+7C0h
0x18001ce4a  call    cs:__imp_RtlRemoveEntryHashTable
0x18001ce50  lea     rcx, qword_1800F2668+7C0h
0x18001ce57  call    WfpRestructureHashtable
0x18001ce5c  lea     rdx, [rbx+18h]
0x18001ce60  xor     r8d, r8d
0x18001ce63  lea     rcx, qword_1800F2668+790h
0x18001ce6a  call    cs:__imp_RtlRemoveEntryHashTable
0x18001ce70  lea     rcx, qword_1800F2668+790h
0x18001ce77  call    WfpRestructureHashtable
0x18001ce7c  mov     rdx, [rbx+30h]
0x18001ce80  mov     ecx, 1
0x18001ce85  call    BfeConnectionChangeDispatch
0x18001ce8a  mov     rcx, [rbx+30h]
0x18001ce8e  call    BfeConnectionLogClose
0x18001ce93  mov     rcx, [rbx+30h]
0x18001ce97  call    BfeConnectionStatAccountingCloseConnection
0x18001ce9c  mov     rcx, [rbx+30h]
0x18001cea0  test    rcx, rcx
0x18001cea3  jz      short loc_18001CEAA
0x18001cea5  call    BfeDestroyInner_FWPM_CONNECTION0
0x18001ceaa  lea     rcx, [rbx+30h]
0x18001ceae  call    WfpMemFree
0x18001ceb3  lea     rcx, [rsp+38h+var_18]
0x18001ceb8  call    WfpMemFree
0x18001cebd  mov     rcx, [rsp+38h+var_10]
0x18001cec2  xor     rcx, rsp; StackCookie
0x18001cec5  call    __security_check_cookie
0x18001ceca  add     rsp, 30h
0x18001cece  pop     rbx
0x18001cecf  retn
```
