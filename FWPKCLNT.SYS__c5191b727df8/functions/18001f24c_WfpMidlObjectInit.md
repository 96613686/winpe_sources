# WfpMidlObjectInit

- ea: `0x18001f24c`
- end: `0x18001f2cb`
- name: `WfpMidlObjectInit`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fc80`

## callees

- `0x18000c354`
- `0x18000c9b4`
- `0x18001f24c`
- `0x18001f2d4`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x18001f259`
- `ntoskrnl!KeInitializeSpinLock` at `0x18001f259`
- `msrpc!MesEncodeDynBufferHandleCreate` at `0x18001f286`
- `msrpc!MesEncodeDynBufferHandleCreate` at `0x18001f286`

## string_xrefs

- `0x18001f299`: `MesEncodeFixedBufferHandleCreate`

## pseudocode

```c
__int64 WfpMidlObjectInit()
{
  __int64 v0; // rbx
  unsigned int v1; // eax
  __int64 v2; // rcx

  KeInitializeSpinLock(&gWfpMidlObject);
  dword_1800487E8 = 1;
  v0 = 0;
  v1 = MesEncodeDynBufferHandleCreate(&unk_180048790, &unk_180048788, &qword_1800487F0);
  if ( v1 )
  {
    v0 = WfpReportSysErrorAsWinError(v2, "MesEncodeFixedBufferHandleCreate", v1);
    if ( v0 )
    {
      WfpMidlObjectShutdown();
      WfpReportError(v0, (int)"WfpMidlObjectInit");
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18001f24c  push    rbx
0x18001f24e  sub     rsp, 20h
0x18001f252  lea     rcx, gWfpMidlObject; SpinLock
0x18001f259  call    cs:__imp_KeInitializeSpinLock
0x18001f260  nop     dword ptr [rax+rax+00h]
0x18001f265  lea     r8, qword_1800487F0
0x18001f26c  mov     cs:dword_1800487E8, 1
0x18001f276  lea     rdx, unk_180048788
0x18001f27d  xor     ebx, ebx
0x18001f27f  lea     rcx, unk_180048790
0x18001f286  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18001f28d  nop     dword ptr [rax+rax+00h]
0x18001f292  test    eax, eax
0x18001f294  jz      short loc_18001F2C1
0x18001f296  mov     r8d, eax
0x18001f299  lea     rdx, aMesencodefixed; "MesEncodeFixedBufferHandleCreate"
0x18001f2a0  call    WfpReportSysErrorAsWinError
0x18001f2a5  mov     rbx, rax
0x18001f2a8  test    rax, rax
0x18001f2ab  jz      short loc_18001F2C1
0x18001f2ad  call    WfpMidlObjectShutdown
0x18001f2b2  lea     rdx, aWfpmidlobjecti; "WfpMidlObjectInit"
0x18001f2b9  mov     rcx, rbx
0x18001f2bc  call    WfpReportError
0x18001f2c1  mov     rax, rbx
0x18001f2c4  add     rsp, 20h
0x18001f2c8  pop     rbx
0x18001f2c9  retn
```
