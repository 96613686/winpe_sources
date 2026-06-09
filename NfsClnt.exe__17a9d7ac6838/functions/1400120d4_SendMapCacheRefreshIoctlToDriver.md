# SendMapCacheRefreshIoctlToDriver

- ea: `0x1400120d4`
- end: `0x140012112`
- name: `SendMapCacheRefreshIoctlToDriver`
- size: `62`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400114ac`
- `0x140011614`
- `0x140011800`
- `0x140011968`

## callees

- `0x1400120d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140012102`
- `KERNEL32!GetLastError` at `0x140012102`
- `KERNEL32!DeviceIoControl` at `0x1400120f8`
- `KERNEL32!DeviceIoControl` at `0x1400120f8`

## pseudocode

```c
__int64 __fastcall SendMapCacheRefreshIoctlToDriver(void *a1)
{
  unsigned int v1; // ebx

  v1 = 0;
  if ( !DeviceIoControl(a1, 0x10008404u, 0, 0, 0, 0, 0, 0) )
    return GetLastError();
  return v1;
}

```

## disassembly

```asm
0x1400120d4  mov     rax, rsp
0x1400120d7  push    rbx
0x1400120d8  sub     rsp, 40h
0x1400120dc  xor     ebx, ebx
0x1400120de  xor     r9d, r9d; nInBufferSize
0x1400120e1  mov     [rax-10h], rbx
0x1400120e5  xor     r8d, r8d; lpInBuffer
0x1400120e8  mov     [rax-18h], rbx
0x1400120ec  mov     edx, 10008404h; dwIoControlCode
0x1400120f1  mov     [rax-20h], ebx
0x1400120f4  mov     [rax-28h], rbx
0x1400120f8  call    cs:__imp_DeviceIoControl
0x1400120fe  test    eax, eax
0x140012100  jnz     short loc_14001210A
0x140012102  call    cs:__imp_GetLastError
0x140012108  mov     ebx, eax
0x14001210a  mov     eax, ebx
0x14001210c  add     rsp, 40h
0x140012110  pop     rbx
0x140012111  retn
```
