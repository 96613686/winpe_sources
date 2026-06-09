# BthDispatchClose

- ea: `0x140001cd0`
- end: `0x140001dcf`
- name: `BthDispatchClose`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001328`
- `0x1400013e8`
- `0x140001cd0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001d8b`
- `ntoskrnl!IofCompleteRequest` at `0x140001d8b`
- `ntoskrnl!IofCallDriver` at `0x140001d5c`
- `ntoskrnl!IofCallDriver` at `0x140001d5c`

## pseudocode

```c
__int64 __fastcall BthDispatchClose(__int64 a1, IRP *a2)
{
  PDEVICE_OBJECT *v4; // rbx
  int v5; // eax
  int v6; // edx
  unsigned int v7; // ebx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      4,
      18,
      (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids);
  v4 = *(PDEVICE_OBJECT **)(a1 + 64);
  v5 = *(_DWORD *)v4;
  if ( *(_DWORD *)v4 == 542065734 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        3,
        19,
        (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids);
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v7 = IofCallDriver(v4[3], a2);
  }
  else
  {
    a2->IoStatus.Information = 0;
    v7 = v5 != 1329877060 ? 0xC00000BB : 0;
    a2->IoStatus.Status = v7;
    IofCompleteRequest(a2, 0);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      4,
      20,
      (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids,
      v7);
  return v7;
}

```

## disassembly

```asm
0x140001cd0  push    rbx
0x140001cd2  push    rbp
0x140001cd3  push    rsi
0x140001cd4  push    rdi
0x140001cd5  sub     rsp, 38h
0x140001cd9  mov     rdi, rdx
0x140001cdc  mov     rbx, rcx
0x140001cdf  lea     rsi, WPP_RECORDER_INITIALIZED
0x140001ce6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001ced  lea     rbp, WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids
0x140001cf4  jz      short loc_140001D15
0x140001cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x140001cfd  mov     r9d, 12h
0x140001d03  mov     [rsp+58h+var_38], rbp
0x140001d08  mov     rcx, [rcx+40h]
0x140001d0c  lea     r8d, [r9-0Eh]
0x140001d10  call    WPP_RECORDER_SF_
0x140001d15  mov     rbx, [rbx+40h]
0x140001d19  mov     eax, [rbx]
0x140001d1b  cmp     eax, 204F4446h
0x140001d20  jnz     short loc_140001D6C
0x140001d22  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001d29  jz      short loc_140001D4A
0x140001d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d32  mov     r9d, 13h
0x140001d38  mov     [rsp+58h+var_38], rbp
0x140001d3d  mov     rcx, [rcx+40h]
0x140001d41  lea     r8d, [r9-10h]
0x140001d45  call    WPP_RECORDER_SF_
0x140001d4a  inc     byte ptr [rdi+43h]
0x140001d4d  mov     rdx, rdi; Irp
0x140001d50  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140001d58  mov     rcx, [rbx+18h]; DeviceObject
0x140001d5c  call    cs:__imp_IofCallDriver
0x140001d63  nop     dword ptr [rax+rax+00h]
0x140001d68  mov     ebx, eax
0x140001d6a  jmp     short loc_140001D97
0x140001d6c  sub     eax, 4F445044h
0x140001d71  mov     qword ptr [rdi+38h], 0
0x140001d79  neg     eax
0x140001d7b  mov     rcx, rdi; Irp
0x140001d7e  sbb     ebx, ebx
0x140001d80  xor     edx, edx; PriorityBoost
0x140001d82  and     ebx, 0C00000BBh
0x140001d88  mov     [rdi+30h], ebx
0x140001d8b  call    cs:__imp_IofCompleteRequest
0x140001d92  nop     dword ptr [rax+rax+00h]
0x140001d97  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001d9e  jz      short loc_140001DC3
0x140001da0  mov     rcx, cs:WPP_GLOBAL_Control
0x140001da7  mov     r9d, 14h
0x140001dad  mov     [rsp+58h+var_30], ebx
0x140001db1  mov     [rsp+58h+var_38], rbp
0x140001db6  mov     rcx, [rcx+40h]
0x140001dba  lea     r8d, [r9-10h]
0x140001dbe  call    WPP_RECORDER_SF_d
0x140001dc3  mov     eax, ebx
0x140001dc5  add     rsp, 38h
0x140001dc9  pop     rdi
0x140001dca  pop     rsi
0x140001dcb  pop     rbp
0x140001dcc  pop     rbx
0x140001dcd  retn
```
