# Auto<uchar *,CoTaskMemAllocFunctor<uchar *>,DummyContext>::~Auto<uchar *,CoTaskMemAllocFunctor<uchar *>,DummyContext>(void)

- ea: `0x18000d934`
- end: `0x18000d960`
- name: `??1?$Auto@PEAEV?$CoTaskMemAllocFunctor@PEAE@@VDummyContext@@@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010320`
- `0x18002b940`
- `0x18003099c`
- `0x1800315d2`

## callees

- `0x18000d934`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d945`

## pseudocode

```c
void __fastcall Auto<unsigned char *,CoTaskMemAllocFunctor<unsigned char *>,DummyContext>::~Auto<unsigned char *,CoTaskMemAllocFunctor<unsigned char *>,DummyContext>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000d934  push    rbx
0x18000d936  sub     rsp, 20h
0x18000d93a  mov     rbx, rcx
0x18000d93d  mov     rcx, [rcx]; pv
0x18000d940  test    rcx, rcx
0x18000d943  jz      short loc_18000D95A
0x18000d945  call    cs:__imp_CoTaskMemFree
0x18000d94b  mov     qword ptr [rbx], 0
0x18000d952  mov     qword ptr [rbx+8], 0
0x18000d95a  add     rsp, 20h
0x18000d95e  pop     rbx
0x18000d95f  retn
```
