# AfdDispatchDeviceControl

- ea: `0x14001ef30`
- end: `0x14001f011`
- name: `AfdDispatchDeviceControl`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140020500`

## callees

- `0x140007350`
- `0x140008210`
- `0x1400166c0`
- `0x140019810`
- `0x14001ef30`
- `0x14001f120`
- `0x140022470`
- `0x14002a1e0`
- `0x14002e9c0`
- `0x14002f800`
- `0x1400343d0`
- `0x140034b20`
- `0x140037ea0`
- `0x140038b00`
- `0x1400398d0`
- `0x14003ae50`
- `0x140044700`
- `0x140046c60`
- `0x1400489b0`
- `0x140048c00`
- `0x140048e90`
- `0x14004cce0`
- `0x14004e9f0`
- `0x14004f210`
- `0x14004fde0`
- `0x1400505f0`
- `0x140051df0`
- `0x140054a50`
- `0x140057100`
- `0x140057a30`
- `0x140058d10`
- `0x140059590`
- `0x140059ab0`
- `0x14006a4c0`
- `0x140072920`
- `0x1400932cc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001efc9`
- `ntoskrnl!IofCompleteRequest` at `0x1400774d5`
- `ntoskrnl!IofCompleteRequest` at `0x14001efc9`
- `ntoskrnl!IofCompleteRequest` at `0x1400774d5`
- `NETIO!NetioNrtIsTrackerDevice` at `0x14001ef4c`
- `NETIO!NetioNrtIsTrackerDevice` at `0x14001ef4c`
- `NETIO!NetioNrtDispatch` at `0x14001efb3`
- `NETIO!NetioNrtDispatch` at `0x14001efb3`

## pseudocode

```c
__int64 __fastcall AfdDispatchDeviceControl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 LowPart; // r9
  __int64 v6; // rax
  __int64 (__fastcall *v7)(PIRP); // rax
  unsigned int v9; // ebx
  CCHAR v10; // dl

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( (unsigned __int8)NetioNrtIsTrackerDevice(a1) )
  {
    v9 = NetioNrtDispatch(a1, a2);
    a2->IoStatus.Status = v9;
    IofCompleteRequest(a2, 0);
    return v9;
  }
  else
  {
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    v6 = (CurrentStackLocation->Parameters.Read.ByteOffset.LowPart >> 2) & 0x3FF;
    if ( (unsigned int)v6 < 0x4A
      && AfdIoctlTable[v6] == (_DWORD)LowPart
      && (CurrentStackLocation->MinorFunction = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart >> 2,
          (v7 = AfdIrpCallDispatch[v6]) != 0) )
    {
      return ((__int64 (__fastcall *)(IRP *, struct _IO_STACK_LOCATION *))v7)(a2, CurrentStackLocation);
    }
    else
    {
      if ( (BYTE10(xmmword_1400875D0) & 0x20) != 0 )
        WPP_SF_d(789, 11, WPP_750cd5b025b73ac1a6ce4c47647b8469_Traceguids, LowPart);
      v10 = AfdPriorityBoost;
      a2->IoStatus.Status = -1073741808;
      IofCompleteRequest(a2, v10);
      return 3221225488LL;
    }
  }
}

```

## disassembly

```asm
0x14001ef30  mov     [rsp+arg_0], rbx
0x14001ef35  mov     [rsp+arg_8], rsi
0x14001ef3a  push    rdi
0x14001ef3b  sub     rsp, 20h
0x14001ef3f  mov     rbx, [rdx+0B8h]
0x14001ef46  mov     rdi, rdx
0x14001ef49  mov     rsi, rcx
0x14001ef4c  call    cs:__imp_NetioNrtIsTrackerDevice
0x14001ef53  nop     dword ptr [rax+rax+00h]
0x14001ef58  test    al, al
0x14001ef5a  jnz     short loc_14001EFAD
0x14001ef5c  mov     r9d, [rbx+18h]
0x14001ef60  mov     eax, r9d
0x14001ef63  shr     eax, 2
0x14001ef66  and     eax, 3FFh
0x14001ef6b  cmp     eax, 4Ah ; 'J'
0x14001ef6e  jnb     short loc_14001EFE8
0x14001ef70  lea     rdx, cs:140000000h
0x14001ef77  cmp     ds:rva AfdIoctlTable[rdx+rax*4], r9d
0x14001ef7f  jnz     short loc_14001EFE8
0x14001ef81  mov     [rbx+1], al
0x14001ef84  mov     rax, ds:(AfdIrpCallDispatch - 140000000h)[rdx+rax*8]
0x14001ef8c  test    rax, rax
0x14001ef8f  jz      short loc_14001EFE8
0x14001ef91  mov     rdx, rbx
0x14001ef94  mov     rcx, rdi; Irp
0x14001ef97  call    _guard_dispatch_icall
0x14001ef9c  mov     rbx, [rsp+28h+arg_0]
0x14001efa1  mov     rsi, [rsp+28h+arg_8]
0x14001efa6  add     rsp, 20h
0x14001efaa  pop     rdi
0x14001efab  retn
0x14001efad  mov     rdx, rdi
0x14001efb0  mov     rcx, rsi
0x14001efb3  call    cs:__imp_NetioNrtDispatch
0x14001efba  nop     dword ptr [rax+rax+00h]
0x14001efbf  xor     edx, edx; PriorityBoost
0x14001efc1  mov     rcx, rdi; Irp
0x14001efc4  mov     ebx, eax
0x14001efc6  mov     [rdi+30h], eax
0x14001efc9  call    cs:__imp_IofCompleteRequest
0x14001efd0  nop     dword ptr [rax+rax+00h]
0x14001efd5  mov     rsi, [rsp+28h+arg_8]
0x14001efda  mov     eax, ebx
0x14001efdc  mov     rbx, [rsp+28h+arg_0]
0x14001efe1  add     rsp, 20h
0x14001efe5  pop     rdi
0x14001efe6  retn
0x14001efe8  test    byte ptr cs:xmmword_1400875D0+0Ah, 20h
0x14001efef  jz      loc_1400774C4
0x14001eff5  mov     edx, 0Bh
0x14001effa  lea     r8, WPP_750cd5b025b73ac1a6ce4c47647b8469_Traceguids
0x14001f001  mov     ecx, 315h
0x14001f006  call    WPP_SF_d
0x14001f00b  nop
0x14001f00c  jmp     loc_1400774C4
0x1400774c4  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x1400774cb  mov     rcx, rdi; Irp
0x1400774ce  mov     dword ptr [rdi+30h], 0C0000010h
0x1400774d5  call    cs:__imp_IofCompleteRequest
0x1400774dc  nop     dword ptr [rax+rax+00h]
0x1400774e1  mov     eax, 0C0000010h
0x1400774e6  jmp     loc_14001EF9C
```
