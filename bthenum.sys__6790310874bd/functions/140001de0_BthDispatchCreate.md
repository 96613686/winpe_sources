# BthDispatchCreate

- ea: `0x140001de0`
- end: `0x140001f3c`
- name: `BthDispatchCreate`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001328`
- `0x1400013e8`
- `0x140001de0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001ef8`
- `ntoskrnl!IofCompleteRequest` at `0x140001ef8`
- `ntoskrnl!IofCallDriver` at `0x140001e6c`
- `ntoskrnl!IofCallDriver` at `0x140001e6c`

## pseudocode

```c
__int64 __fastcall BthDispatchCreate(__int64 a1, IRP *a2)
{
  int *v4; // rdi
  int v5; // eax
  int v6; // edx
  unsigned int v7; // edi
  __int64 v9; // [rsp+28h] [rbp-30h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      4,
      10,
      (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids);
  v4 = *(int **)(a1 + 64);
  v5 = *v4;
  if ( *v4 == 542065734 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        3,
        11,
        (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids);
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v7 = IofCallDriver(*((PDEVICE_OBJECT *)v4 + 3), a2);
  }
  else
  {
    if ( v5 != 1329877060 || v4[52] == 3 )
    {
      v7 = -1073741637;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          3,
          13,
          (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids,
          v5);
    }
    else
    {
      v7 = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          3,
          12,
          (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids);
    }
    a2->IoStatus.Status = v7;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v9) = v7;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      4,
      14,
      (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids,
      v9);
  }
  return v7;
}

```

## disassembly

```asm
0x140001de0  push    rbx
0x140001de2  push    rbp
0x140001de3  push    rsi
0x140001de4  push    rdi
0x140001de5  sub     rsp, 38h
0x140001de9  mov     rbx, rdx
0x140001dec  mov     rdi, rcx
0x140001def  lea     rsi, WPP_RECORDER_INITIALIZED
0x140001df6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001dfd  lea     rbp, WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids
0x140001e04  jz      short loc_140001E25
0x140001e06  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e0d  mov     r9d, 0Ah
0x140001e13  mov     [rsp+58h+var_38], rbp
0x140001e18  mov     rcx, [rcx+40h]
0x140001e1c  lea     r8d, [r9-6]
0x140001e20  call    WPP_RECORDER_SF_
0x140001e25  mov     rdi, [rdi+40h]
0x140001e29  mov     eax, [rdi]
0x140001e2b  cmp     eax, 204F4446h
0x140001e30  jnz     short loc_140001E7F
0x140001e32  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001e39  jz      short loc_140001E5A
0x140001e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e42  mov     r9d, 0Bh
0x140001e48  mov     [rsp+58h+var_38], rbp
0x140001e4d  mov     rcx, [rcx+40h]
0x140001e51  lea     r8d, [r9-8]
0x140001e55  call    WPP_RECORDER_SF_
0x140001e5a  inc     byte ptr [rbx+43h]
0x140001e5d  mov     rdx, rbx; Irp
0x140001e60  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140001e68  mov     rcx, [rdi+18h]; DeviceObject
0x140001e6c  call    cs:__imp_IofCallDriver
0x140001e73  nop     dword ptr [rax+rax+00h]
0x140001e78  mov     edi, eax
0x140001e7a  jmp     loc_140001F04
0x140001e7f  mov     r8d, 3
0x140001e85  cmp     eax, 4F445044h
0x140001e8a  jnz     short loc_140001EBB
0x140001e8c  cmp     [rdi+0D0h], r8d
0x140001e93  jz      short loc_140001EBB
0x140001e95  xor     edi, edi
0x140001e97  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001e9e  jz      short loc_140001EE8
0x140001ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ea7  lea     r9d, [r8+9]
0x140001eab  mov     [rsp+58h+var_38], rbp
0x140001eb0  mov     rcx, [rcx+40h]
0x140001eb4  call    WPP_RECORDER_SF_
0x140001eb9  jmp     short loc_140001EE8
0x140001ebb  mov     edi, 0C00000BBh
0x140001ec0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001ec7  jz      short loc_140001EE8
0x140001ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ed0  mov     r9d, 0Dh
0x140001ed6  mov     dword ptr [rsp+58h+var_30], eax
0x140001eda  mov     [rsp+58h+var_38], rbp
0x140001edf  mov     rcx, [rcx+40h]
0x140001ee3  call    WPP_RECORDER_SF_d
0x140001ee8  xor     edx, edx; PriorityBoost
0x140001eea  mov     [rbx+30h], edi
0x140001eed  mov     rcx, rbx; Irp
0x140001ef0  mov     qword ptr [rbx+38h], 0
0x140001ef8  call    cs:__imp_IofCompleteRequest
0x140001eff  nop     dword ptr [rax+rax+00h]
0x140001f04  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001f0b  jz      short loc_140001F30
0x140001f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f14  mov     r9d, 0Eh
0x140001f1a  mov     dword ptr [rsp+58h+var_30], edi
0x140001f1e  mov     [rsp+58h+var_38], rbp
0x140001f23  mov     rcx, [rcx+40h]
0x140001f27  lea     r8d, [r9-0Ah]
0x140001f2b  call    WPP_RECORDER_SF_d
0x140001f30  mov     eax, edi
0x140001f32  add     rsp, 38h
0x140001f36  pop     rdi
0x140001f37  pop     rsi
0x140001f38  pop     rbp
0x140001f39  pop     rbx
0x140001f3a  retn
```
