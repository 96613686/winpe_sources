# FreeCDPComCrossPlatformAppIdEntry

- ea: `0x18001d16c`
- end: `0x18001d19d`
- name: `FreeCDPComCrossPlatformAppIdEntry`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800072b0`
- `0x18000f890`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d179`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d179`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d182`

## pseudocode

```c
void __fastcall FreeCDPComCrossPlatformAppIdEntry(LPVOID *a1)
{
  CoTaskMemFree(a1[1]);
  CoTaskMemFree(*a1);
  a1[1] = 0;
  *a1 = 0;
}

```

## disassembly

```asm
0x18001d16c  push    rbx
0x18001d16e  sub     rsp, 20h
0x18001d172  mov     rbx, rcx
0x18001d175  mov     rcx, [rcx+8]; pv
0x18001d179  call    cs:__imp_CoTaskMemFree
0x18001d17f  mov     rcx, [rbx]; pv
0x18001d182  call    cs:__imp_CoTaskMemFree
0x18001d188  mov     qword ptr [rbx+8], 0
0x18001d190  mov     qword ptr [rbx], 0
0x18001d197  add     rsp, 20h
0x18001d19b  pop     rbx
0x18001d19c  retn
```
