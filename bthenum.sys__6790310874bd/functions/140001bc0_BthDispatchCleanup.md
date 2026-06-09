# BthDispatchCleanup

- ea: `0x140001bc0`
- end: `0x140001cbf`
- name: `BthDispatchCleanup`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001328`
- `0x1400013e8`
- `0x140001bc0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001c7b`
- `ntoskrnl!IofCompleteRequest` at `0x140001c7b`
- `ntoskrnl!IofCallDriver` at `0x140001c4c`
- `ntoskrnl!IofCallDriver` at `0x140001c4c`

## pseudocode

```c
__int64 __fastcall BthDispatchCleanup(__int64 a1, IRP *a2)
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
      15,
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
        16,
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
      17,
      (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids,
      v7);
  return v7;
}

```

## disassembly

```asm
0x140001bc0  push    rbx
0x140001bc2  push    rbp
0x140001bc3  push    rsi
0x140001bc4  push    rdi
0x140001bc5  sub     rsp, 38h
0x140001bc9  mov     rdi, rdx
0x140001bcc  mov     rbx, rcx
0x140001bcf  lea     rsi, WPP_RECORDER_INITIALIZED
0x140001bd6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001bdd  lea     rbp, WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids
0x140001be4  jz      short loc_140001C05
0x140001be6  mov     rcx, cs:WPP_GLOBAL_Control
0x140001bed  mov     r9d, 0Fh
0x140001bf3  mov     [rsp+58h+var_38], rbp
0x140001bf8  mov     rcx, [rcx+40h]
0x140001bfc  lea     r8d, [r9-0Bh]
0x140001c00  call    WPP_RECORDER_SF_
0x140001c05  mov     rbx, [rbx+40h]
0x140001c09  mov     eax, [rbx]
0x140001c0b  cmp     eax, 204F4446h
0x140001c10  jnz     short loc_140001C5C
0x140001c12  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001c19  jz      short loc_140001C3A
0x140001c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c22  mov     r9d, 10h
0x140001c28  mov     [rsp+58h+var_38], rbp
0x140001c2d  mov     rcx, [rcx+40h]
0x140001c31  lea     r8d, [r9-0Dh]
0x140001c35  call    WPP_RECORDER_SF_
0x140001c3a  inc     byte ptr [rdi+43h]
0x140001c3d  mov     rdx, rdi; Irp
0x140001c40  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140001c48  mov     rcx, [rbx+18h]; DeviceObject
0x140001c4c  call    cs:__imp_IofCallDriver
0x140001c53  nop     dword ptr [rax+rax+00h]
0x140001c58  mov     ebx, eax
0x140001c5a  jmp     short loc_140001C87
0x140001c5c  sub     eax, 4F445044h
0x140001c61  mov     qword ptr [rdi+38h], 0
0x140001c69  neg     eax
0x140001c6b  mov     rcx, rdi; Irp
0x140001c6e  sbb     ebx, ebx
0x140001c70  xor     edx, edx; PriorityBoost
0x140001c72  and     ebx, 0C00000BBh
0x140001c78  mov     [rdi+30h], ebx
0x140001c7b  call    cs:__imp_IofCompleteRequest
0x140001c82  nop     dword ptr [rax+rax+00h]
0x140001c87  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001c8e  jz      short loc_140001CB3
0x140001c90  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c97  mov     r9d, 11h
0x140001c9d  mov     [rsp+58h+var_30], ebx
0x140001ca1  mov     [rsp+58h+var_38], rbp
0x140001ca6  mov     rcx, [rcx+40h]
0x140001caa  lea     r8d, [r9-0Dh]
0x140001cae  call    WPP_RECORDER_SF_d
0x140001cb3  mov     eax, ebx
0x140001cb5  add     rsp, 38h
0x140001cb9  pop     rdi
0x140001cba  pop     rsi
0x140001cbb  pop     rbp
0x140001cbc  pop     rbx
0x140001cbd  retn
```
