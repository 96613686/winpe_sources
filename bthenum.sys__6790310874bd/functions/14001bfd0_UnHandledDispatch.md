# UnHandledDispatch

- ea: `0x14001bfd0`
- end: `0x14001c09b`
- name: `UnHandledDispatch`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001328`
- `0x1400013e8`
- `0x14001bfd0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001c056`
- `ntoskrnl!IofCompleteRequest` at `0x14001c056`
- `ntoskrnl!IofCallDriver` at `0x14001c031`
- `ntoskrnl!IofCallDriver` at `0x14001c031`

## pseudocode

```c
__int64 __fastcall UnHandledDispatch(__int64 a1, IRP *a2)
{
  __int64 v2; // rdi
  int v4; // edx
  unsigned int v5; // edi
  unsigned int v7; // [rsp+28h] [rbp-30h]

  v2 = *(_QWORD *)(a1 + 64);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      4,
      26,
      (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids);
  if ( *(_DWORD *)v2 == 542065734 )
  {
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v5 = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 24), a2);
  }
  else
  {
    v5 = -1073741637;
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741637;
    IofCompleteRequest(a2, 0);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = v5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      4,
      28,
      (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids,
      v7);
  }
  return v5;
}

```

## disassembly

```asm
0x14001bfd0  push    rbx
0x14001bfd2  push    rsi
0x14001bfd3  push    rdi
0x14001bfd4  push    r14
0x14001bfd6  sub     rsp, 38h
0x14001bfda  mov     rdi, [rcx+40h]
0x14001bfde  mov     rbx, rdx
0x14001bfe1  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001bfe8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001bfef  lea     r14, WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids
0x14001bff6  jz      short loc_14001C017
0x14001bff8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bfff  mov     r9d, 1Ah
0x14001c005  mov     [rsp+58h+var_38], r14
0x14001c00a  mov     rcx, [rcx+40h]
0x14001c00e  lea     r8d, [r9-16h]
0x14001c012  call    WPP_RECORDER_SF_
0x14001c017  cmp     dword ptr [rdi], 204F4446h
0x14001c01d  jnz     short loc_14001C041
0x14001c01f  inc     byte ptr [rbx+43h]
0x14001c022  mov     rdx, rbx; Irp
0x14001c025  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14001c02d  mov     rcx, [rdi+18h]; DeviceObject
0x14001c031  call    cs:__imp_IofCallDriver
0x14001c038  nop     dword ptr [rax+rax+00h]
0x14001c03d  mov     edi, eax
0x14001c03f  jmp     short loc_14001C062
0x14001c041  mov     edi, 0C00000BBh
0x14001c046  mov     qword ptr [rbx+38h], 0
0x14001c04e  xor     edx, edx; PriorityBoost
0x14001c050  mov     [rbx+30h], edi
0x14001c053  mov     rcx, rbx; Irp
0x14001c056  call    cs:__imp_IofCompleteRequest
0x14001c05d  nop     dword ptr [rax+rax+00h]
0x14001c062  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001c069  jz      short loc_14001C08E
0x14001c06b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c072  mov     r9d, 1Ch
0x14001c078  mov     [rsp+58h+var_30], edi
0x14001c07c  mov     [rsp+58h+var_38], r14
0x14001c081  mov     rcx, [rcx+40h]
0x14001c085  lea     r8d, [r9-18h]
0x14001c089  call    WPP_RECORDER_SF_d
0x14001c08e  mov     eax, edi
0x14001c090  add     rsp, 38h
0x14001c094  pop     r14
0x14001c096  pop     rdi
0x14001c097  pop     rsi
0x14001c098  pop     rbx
0x14001c099  retn
```
