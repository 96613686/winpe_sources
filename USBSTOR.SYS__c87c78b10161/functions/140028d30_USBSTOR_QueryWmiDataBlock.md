# USBSTOR_QueryWmiDataBlock

- ea: `0x140028d30`
- end: `0x140028d97`
- name: `USBSTOR_QueryWmiDataBlock`
- size: `103`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000b4a0`
- `0x140028d30`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x140028d85`
- `WMILIB!WmiCompleteRequest` at `0x140028d85`

## pseudocode

```c
NTSTATUS __fastcall USBSTOR_QueryWmiDataBlock(
        PDEVICE_OBJECT DeviceObject,
        IRP *a2,
        int a3,
        __int64 a4,
        int a5,
        ULONG *a6,
        int a7,
        bool *a8)
{
  struct _DEVICE_OBJECT *v8; // r10
  ULONG v9; // r9d
  NTSTATUS v10; // r8d
  char IsSelectiveSuspendEnabled; // al

  v8 = DeviceObject;
  if ( a3 == 1 )
  {
    v9 = 1;
    if ( a7 )
    {
      IsSelectiveSuspendEnabled = USBSTOR_IsSelectiveSuspendEnabled(DeviceObject->DeviceExtension);
      v10 = 0;
      *a8 = IsSelectiveSuspendEnabled != 0;
      *a6 = v9;
    }
    else
    {
      v10 = -1073741789;
    }
  }
  else
  {
    v9 = 0;
    v10 = -1073741163;
  }
  return WmiCompleteRequest(v8, a2, v10, v9, 0);
}

```

## disassembly

```asm
0x140028d30  sub     rsp, 38h
0x140028d34  mov     r10, rcx
0x140028d37  cmp     r8d, 1
0x140028d3b  jz      short loc_140028D48
0x140028d3d  xor     r9d, r9d
0x140028d40  mov     r8d, 0C0000295h
0x140028d46  jmp     short loc_140028D7D
0x140028d48  mov     r9d, 1
0x140028d4e  cmp     [rsp+38h+arg_30], r9d
0x140028d53  jnb     short loc_140028D5D
0x140028d55  mov     r8d, 0C0000023h
0x140028d5b  jmp     short loc_140028D7D
0x140028d5d  mov     rcx, [rcx+40h]
0x140028d61  call    USBSTOR_IsSelectiveSuspendEnabled
0x140028d66  test    al, al
0x140028d68  mov     rax, [rsp+38h+arg_38]
0x140028d6d  setnz   cl
0x140028d70  xor     r8d, r8d; Status
0x140028d73  mov     [rax], cl
0x140028d75  mov     rax, [rsp+38h+arg_28]
0x140028d7a  mov     [rax], r9d
0x140028d7d  mov     rcx, r10; DeviceObject
0x140028d80  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x140028d85  call    cs:__imp_WmiCompleteRequest
0x140028d8c  nop     dword ptr [rax+rax+00h]
0x140028d91  add     rsp, 38h
0x140028d95  retn
```
