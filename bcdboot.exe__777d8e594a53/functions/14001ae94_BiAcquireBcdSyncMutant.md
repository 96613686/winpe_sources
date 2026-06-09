# BiAcquireBcdSyncMutant

- ea: `0x14001ae94`
- end: `0x14001aef7`
- name: `BiAcquireBcdSyncMutant`
- size: `99`
- prototype: `NTSTATUS __fastcall(char)`
- caller_count: `19`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140013b48`
- `0x140013b9c`
- `0x140013c1c`
- `0x140013ee8`
- `0x1400140c4`
- `0x14001474c`
- `0x140014ec8`
- `0x1400186fc`
- `0x140018890`
- `0x140018b54`
- `0x140019990`
- `0x14001a8c4`
- `0x14001a964`
- `0x14001ac80`
- `0x14001acec`
- `0x14001adb8`
- `0x14001ae30`
- `0x14001bb00`
- `0x140021c10`

## callees

- `0x14001ae94`
- `0x14001b57c`

## import_xrefs

- `ntdll!ZwWaitForSingleObject` at `0x14001aedb`
- `ntdll!ZwWaitForSingleObject` at `0x14001aedb`

## pseudocode

```c
NTSTATUS __fastcall BiAcquireBcdSyncMutant(char a1)
{
  NTSTATUS result; // eax
  __int64 v2; // [rsp+38h] [rbp+10h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  Timeout.QuadPart = 0;
  if ( a1 )
    return 0;
  result = BiGetCurrentBcdMutantHandle(&v2);
  if ( result < 0 )
    return result;
  if ( v2 == -1 )
    return 0;
  Timeout.QuadPart = -600000000;
  result = ZwWaitForSingleObject(BcdMutantHandle, 0, &Timeout);
  if ( result == 258 )
    return -1073741823;
  return result;
}

```

## disassembly

```asm
0x14001ae94  sub     rsp, 28h
0x14001ae98  mov     [rsp+28h+arg_8], 0
0x14001aea1  mov     qword ptr [rsp+28h+Timeout], 0
0x14001aeaa  test    cl, cl
0x14001aeac  jnz     short loc_14001AEF0
0x14001aeae  lea     rcx, [rsp+28h+arg_8]
0x14001aeb3  call    BiGetCurrentBcdMutantHandle
0x14001aeb8  test    eax, eax
0x14001aeba  js      short loc_14001AEF2
0x14001aebc  cmp     [rsp+28h+arg_8], 0FFFFFFFFFFFFFFFFh
0x14001aec2  jz      short loc_14001AEF0
0x14001aec4  mov     rcx, cs:BcdMutantHandle; Handle
0x14001aecb  lea     r8, [rsp+28h+Timeout]; Timeout
0x14001aed0  xor     edx, edx; Alertable
0x14001aed2  mov     qword ptr [rsp+28h+Timeout], 0FFFFFFFFDC3CBA00h
0x14001aedb  call    cs:__imp_ZwWaitForSingleObject
0x14001aee1  cmp     eax, 102h
0x14001aee6  mov     ecx, 0C0000001h
0x14001aeeb  cmovz   eax, ecx
0x14001aeee  jmp     short loc_14001AEF2
0x14001aef0  xor     eax, eax
0x14001aef2  add     rsp, 28h
0x14001aef6  retn
```
