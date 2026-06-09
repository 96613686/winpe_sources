# WskTdiInit

- ea: `0x14003fe3c`
- end: `0x14003ff6e`
- name: `WskTdiInit`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140034314`

## callees

- `0x14003fe3c`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ff19`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ff4f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ff19`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ff4f`
- `NETIO!NetioShutdownWorkQueue` at `0x14003fe9f`
- `NETIO!NetioShutdownWorkQueue` at `0x14003fee1`
- `NETIO!NetioShutdownWorkQueue` at `0x14003fe9f`
- `NETIO!NetioShutdownWorkQueue` at `0x14003fee1`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fe5a`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fe86`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fec8`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fe5a`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fe86`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fec8`

## pseudocode

```c
__int64 WskTdiInit()
{
  __int64 result; // rax
  int v1; // ebx

  result = NetioInitializeWorkQueue(WskTdiWQEndpointClose, WskTdiWQRoutineEndpointClose, 0, AfdDeviceObject);
  if ( (int)result >= 0 )
  {
    v1 = NetioInitializeWorkQueue(WskTdiWQEndpointBind, WskTdiWQRoutineEndpointBind, 0, AfdDeviceObject);
    if ( v1 >= 0 )
    {
      v1 = NetioInitializeWorkQueue(WskTdiWQEndpointCreate, WskTdiWQRoutineEndpointCreate, 0, AfdDeviceObject);
      if ( v1 >= 0 )
      {
        ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0x68u, 0x724B5357u, 0);
        ExInitializeNPagedLookasideList(&stru_1400877C0, 0, 0, 0x200u, 0xC8u, 0x614B5357u, 0);
        dword_140087748 = 0;
        return (unsigned int)v1;
      }
      NetioShutdownWorkQueue(WskTdiWQEndpointBind);
    }
    NetioShutdownWorkQueue(WskTdiWQEndpointClose);
    return (unsigned int)v1;
  }
  return result;
}

```

## disassembly

```asm
0x14003fe3c  push    rbx
0x14003fe3e  sub     rsp, 40h
0x14003fe42  mov     r9, cs:AfdDeviceObject
0x14003fe49  lea     rdx, WskTdiWQRoutineEndpointClose
0x14003fe50  xor     r8d, r8d
0x14003fe53  lea     rcx, WskTdiWQEndpointClose
0x14003fe5a  call    cs:__imp_NetioInitializeWorkQueue
0x14003fe61  nop     dword ptr [rax+rax+00h]
0x14003fe66  test    eax, eax
0x14003fe68  js      loc_14003FF67
0x14003fe6e  mov     r9, cs:AfdDeviceObject
0x14003fe75  lea     rdx, WskTdiWQRoutineEndpointBind
0x14003fe7c  xor     r8d, r8d
0x14003fe7f  lea     rcx, WskTdiWQEndpointBind
0x14003fe86  call    cs:__imp_NetioInitializeWorkQueue
0x14003fe8d  nop     dword ptr [rax+rax+00h]
0x14003fe92  mov     ebx, eax
0x14003fe94  test    eax, eax
0x14003fe96  jns     short loc_14003FEB0
0x14003fe98  lea     rcx, WskTdiWQEndpointClose
0x14003fe9f  call    cs:__imp_NetioShutdownWorkQueue
0x14003fea6  nop     dword ptr [rax+rax+00h]
0x14003feab  jmp     loc_14003FF65
0x14003feb0  mov     r9, cs:AfdDeviceObject
0x14003feb7  lea     rdx, WskTdiWQRoutineEndpointCreate
0x14003febe  xor     r8d, r8d
0x14003fec1  lea     rcx, WskTdiWQEndpointCreate
0x14003fec8  call    cs:__imp_NetioInitializeWorkQueue
0x14003fecf  nop     dword ptr [rax+rax+00h]
0x14003fed4  mov     ebx, eax
0x14003fed6  test    eax, eax
0x14003fed8  jns     short loc_14003FEEF
0x14003feda  lea     rcx, WskTdiWQEndpointBind
0x14003fee1  call    cs:__imp_NetioShutdownWorkQueue
0x14003fee8  nop     dword ptr [rax+rax+00h]
0x14003feed  jmp     short loc_14003FE98
0x14003feef  xor     eax, eax
0x14003fef1  lea     rcx, Lookaside; Lookaside
0x14003fef8  mov     [rsp+48h+Depth], ax; Depth
0x14003fefd  mov     r9d, 200h; Flags
0x14003ff03  mov     [rsp+48h+Tag], 724B5357h; Tag
0x14003ff0b  xor     r8d, r8d; Free
0x14003ff0e  xor     edx, edx; Allocate
0x14003ff10  mov     [rsp+48h+Size], 68h ; 'h'; Size
0x14003ff19  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003ff20  nop     dword ptr [rax+rax+00h]
0x14003ff25  xor     eax, eax
0x14003ff27  lea     rcx, stru_1400877C0; Lookaside
0x14003ff2e  mov     [rsp+48h+Depth], ax; Depth
0x14003ff33  mov     r9d, 200h; Flags
0x14003ff39  mov     [rsp+48h+Tag], 614B5357h; Tag
0x14003ff41  xor     r8d, r8d; Free
0x14003ff44  xor     edx, edx; Allocate
0x14003ff46  mov     [rsp+48h+Size], 0C8h; Size
0x14003ff4f  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003ff56  nop     dword ptr [rax+rax+00h]
0x14003ff5b  mov     cs:dword_140087748, 0
0x14003ff65  mov     eax, ebx
0x14003ff67  add     rsp, 40h
0x14003ff6b  pop     rbx
0x14003ff6c  retn
```
