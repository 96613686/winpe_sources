# WskTdiInit

- ea: `0x14003fe5c`
- end: `0x14003ff8e`
- name: `WskTdiInit`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140034334`

## callees

- `0x14003fe5c`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ff39`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ff6f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ff39`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003ff6f`
- `NETIO!NetioShutdownWorkQueue` at `0x14003febf`
- `NETIO!NetioShutdownWorkQueue` at `0x14003ff01`
- `NETIO!NetioShutdownWorkQueue` at `0x14003febf`
- `NETIO!NetioShutdownWorkQueue` at `0x14003ff01`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fe7a`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fea6`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fee8`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fe7a`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fea6`
- `NETIO!NetioInitializeWorkQueue` at `0x14003fee8`

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
0x14003fe5c  push    rbx
0x14003fe5e  sub     rsp, 40h
0x14003fe62  mov     r9, cs:AfdDeviceObject
0x14003fe69  lea     rdx, WskTdiWQRoutineEndpointClose
0x14003fe70  xor     r8d, r8d
0x14003fe73  lea     rcx, WskTdiWQEndpointClose
0x14003fe7a  call    cs:__imp_NetioInitializeWorkQueue
0x14003fe81  nop     dword ptr [rax+rax+00h]
0x14003fe86  test    eax, eax
0x14003fe88  js      loc_14003FF87
0x14003fe8e  mov     r9, cs:AfdDeviceObject
0x14003fe95  lea     rdx, WskTdiWQRoutineEndpointBind
0x14003fe9c  xor     r8d, r8d
0x14003fe9f  lea     rcx, WskTdiWQEndpointBind
0x14003fea6  call    cs:__imp_NetioInitializeWorkQueue
0x14003fead  nop     dword ptr [rax+rax+00h]
0x14003feb2  mov     ebx, eax
0x14003feb4  test    eax, eax
0x14003feb6  jns     short loc_14003FED0
0x14003feb8  lea     rcx, WskTdiWQEndpointClose
0x14003febf  call    cs:__imp_NetioShutdownWorkQueue
0x14003fec6  nop     dword ptr [rax+rax+00h]
0x14003fecb  jmp     loc_14003FF85
0x14003fed0  mov     r9, cs:AfdDeviceObject
0x14003fed7  lea     rdx, WskTdiWQRoutineEndpointCreate
0x14003fede  xor     r8d, r8d
0x14003fee1  lea     rcx, WskTdiWQEndpointCreate
0x14003fee8  call    cs:__imp_NetioInitializeWorkQueue
0x14003feef  nop     dword ptr [rax+rax+00h]
0x14003fef4  mov     ebx, eax
0x14003fef6  test    eax, eax
0x14003fef8  jns     short loc_14003FF0F
0x14003fefa  lea     rcx, WskTdiWQEndpointBind
0x14003ff01  call    cs:__imp_NetioShutdownWorkQueue
0x14003ff08  nop     dword ptr [rax+rax+00h]
0x14003ff0d  jmp     short loc_14003FEB8
0x14003ff0f  xor     eax, eax
0x14003ff11  lea     rcx, Lookaside; Lookaside
0x14003ff18  mov     [rsp+48h+Depth], ax; Depth
0x14003ff1d  mov     r9d, 200h; Flags
0x14003ff23  mov     [rsp+48h+Tag], 724B5357h; Tag
0x14003ff2b  xor     r8d, r8d; Free
0x14003ff2e  xor     edx, edx; Allocate
0x14003ff30  mov     [rsp+48h+Size], 68h ; 'h'; Size
0x14003ff39  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003ff40  nop     dword ptr [rax+rax+00h]
0x14003ff45  xor     eax, eax
0x14003ff47  lea     rcx, stru_1400877C0; Lookaside
0x14003ff4e  mov     [rsp+48h+Depth], ax; Depth
0x14003ff53  mov     r9d, 200h; Flags
0x14003ff59  mov     [rsp+48h+Tag], 614B5357h; Tag
0x14003ff61  xor     r8d, r8d; Free
0x14003ff64  xor     edx, edx; Allocate
0x14003ff66  mov     [rsp+48h+Size], 0C8h; Size
0x14003ff6f  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003ff76  nop     dword ptr [rax+rax+00h]
0x14003ff7b  mov     cs:dword_140087748, 0
0x14003ff85  mov     eax, ebx
0x14003ff87  add     rsp, 40h
0x14003ff8b  pop     rbx
0x14003ff8c  retn
```
