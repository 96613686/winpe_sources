# CDeviceInitializeJob::FinishJob(_DEVICE_INITIALIZE_JOB_STATE,int)

- ea: `0x140068e44`
- end: `0x140068ed5`
- name: `?FinishJob@CDeviceInitializeJob@@AEAAXW4_DEVICE_INITIALIZE_JOB_STATE@@H@Z`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400699d0`
- `0x14006a230`

## callees

- `0x140012f80`
- `0x14001ed44`
- `0x140068e44`

## import_xrefs

- `NDIS!NdisWriteErrorLogEntry` at `0x140068eb3`
- `NDIS!NdisWriteErrorLogEntry` at `0x140068eb3`

## pseudocode

```c
__int64 __fastcall CDeviceInitializeJob::FinishJob(CAdapter **a1, __int64 a2, int a3)
{
  void *AdapterNdisHandleFromNdisPortNumber; // rax
  int v6; // r11d
  int v7; // edx
  ULONG v8; // r10d

  if ( a3 )
  {
    AdapterNdisHandleFromNdisPortNumber = CAdapter::GetAdapterNdisHandleFromNdisPortNumber(a1[68], 0);
    NdisWriteErrorLogEntry(AdapterNdisHandleFromNdisPortNumber, v8, v7 + 2, v6 | 0x30000u, a3);
  }
  return CJobBase::CompleteJob((CJobBase *)a1, a3);
}

```

## disassembly

```asm
0x140068e44  mov     [rsp+arg_0], rbx
0x140068e49  push    rdi
0x140068e4a  sub     rsp, 30h
0x140068e4e  mov     ebx, r8d
0x140068e51  mov     r11d, edx
0x140068e54  mov     rdi, rcx
0x140068e57  test    r8d, r8d
0x140068e5a  jz      short loc_140068EBF
0x140068e5c  mov     r9d, edx
0x140068e5f  test    edx, edx
0x140068e61  jz      short loc_140068E87
0x140068e63  sub     r9d, 1
0x140068e67  jz      short loc_140068E7F
0x140068e69  cmp     r9d, 1
0x140068e6d  jz      short loc_140068E77
0x140068e6f  mov     r10d, 0C000138Dh
0x140068e75  jmp     short loc_140068E8D
0x140068e77  mov     r10d, 0C0001393h
0x140068e7d  jmp     short loc_140068E8D
0x140068e7f  mov     r10d, 0C0001390h
0x140068e85  jmp     short loc_140068E8D
0x140068e87  mov     r10d, 0C0001389h
0x140068e8d  mov     rcx, [rcx+220h]; this
0x140068e94  xor     edx, edx; unsigned int
0x140068e96  call    ?GetAdapterNdisHandleFromNdisPortNumber@CAdapter@@QEAAPEAXK@Z; CAdapter::GetAdapterNdisHandleFromNdisPortNumber(ulong)
0x140068e9b  or      r11d, 30000h
0x140068ea2  mov     [rsp+38h+var_18], ebx
0x140068ea6  lea     r8d, [rdx+2]; NumberOfErrorValues
0x140068eaa  mov     r9d, r11d
0x140068ead  mov     edx, r10d; ErrorCode
0x140068eb0  mov     rcx, rax; NdisAdapterHandle
0x140068eb3  call    cs:__imp_NdisWriteErrorLogEntry
0x140068eba  nop     dword ptr [rax+rax+00h]
0x140068ebf  mov     edx, ebx; int
0x140068ec1  mov     rcx, rdi; this
0x140068ec4  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x140068ec9  mov     rbx, [rsp+38h+arg_0]
0x140068ece  add     rsp, 30h
0x140068ed2  pop     rdi
0x140068ed3  retn
```
