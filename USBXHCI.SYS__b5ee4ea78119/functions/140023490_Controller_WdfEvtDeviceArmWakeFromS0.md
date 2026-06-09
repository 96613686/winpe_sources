# Controller_WdfEvtDeviceArmWakeFromS0

- ea: `0x140023490`
- end: `0x14002366f`
- name: `Controller_WdfEvtDeviceArmWakeFromS0`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140010d40`
- `0x1400110e0`
- `0x14001a214`
- `0x14001bb78`
- `0x14001f830`
- `0x1400218a0`
- `0x1400219b0`
- `0x140023490`
- `0x140031928`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140023527`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400235f4`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023527`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400235f4`

## string_xrefs

- `0x140023617`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall Controller_WdfEvtDeviceArmWakeFromS0(__int64 a1)
{
  char v1; // bl
  int v2; // edx
  __int64 v3; // rsi
  __int64 v4; // rdi
  unsigned int v5; // ebp
  __int64 v6; // r14
  char v7; // r12
  __int64 v8; // rcx
  __int64 v9; // rbx
  int *v10; // rbx
  __int16 Ulong; // ax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  char v15; // bl
  signed __int32 v17[8]; // [rsp+0h] [rbp-58h] BYREF
  int v18; // [rsp+68h] [rbp+10h] BYREF

  v1 = a1;
  v3 = *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_14006C2C0)
                 + 8);
  if ( *(_BYTE *)(v3 + 1041) && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\controller.c",
      3263);
  v4 = *(_QWORD *)(v3 + 152);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 4;
    WPP_RECORDER_SF_q(*(_QWORD *)(v3 + 72), v2, 4, 92, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v1);
  }
  v5 = 0;
  for ( *(_BYTE *)(v3 + 868) = 1; v5 < *(_DWORD *)(v4 + 16); ++v5 )
  {
    v6 = 120LL * v5;
    if ( (*(_DWORD *)(v6 + *(_QWORD *)(v4 + 48) + 64) & 2) == 0 )
    {
      v7 = 0;
      if ( KeGetCurrentIrql() == 2 )
      {
        v8 = *(_QWORD *)(v4 + 8);
        if ( *(_BYTE *)(v8 + 1041) )
        {
          Controller_LowerAndTrackIrql(v8);
          v7 = 1;
        }
      }
      v9 = *(_QWORD *)(v4 + 48);
      DynamicLock_Acquire(*(_QWORD *)(v9 + v6 + 24));
      *(_BYTE *)(v9 + v6 + 32) = v7;
      v10 = (int *)(16LL * v5 + *(_QWORD *)(v4 + 40));
      Ulong = XilRegister_ReadUlong(*(_QWORD *)(v3 + 88), v10);
      v12 = *(_QWORD *)(v3 + 88);
      v13 = Ulong & 0xC200 | 0xE000000;
      v18 = v13;
      if ( *(_BYTE *)(*(_QWORD *)(v12 + 8) + 1041LL) )
      {
        Register_WriteSecureMmio(v12, v10, 2, &v18);
      }
      else
      {
        *v10 = v13;
        _InterlockedOr(v17, 0);
      }
      v14 = *(_QWORD *)(v4 + 48);
      v15 = *(_BYTE *)(v14 + v6 + 32);
      *(_BYTE *)(v14 + v6 + 32) = 0;
      DynamicLock_Release(*(_QWORD *)(v14 + v6 + 24));
      if ( v15 )
        Controller_RaiseAndTrackIrql(*(_QWORD *)(v4 + 8));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140023490  mov     [rsp+arg_0], rbx
0x140023495  mov     [rsp+arg_10], rbp
0x14002349a  push    rsi
0x14002349b  push    rdi
0x14002349c  push    r12
0x14002349e  push    r14
0x1400234a0  push    r15
0x1400234a2  sub     rsp, 30h
0x1400234a6  mov     rax, cs:WdfFunctions_01033
0x1400234ad  mov     rbx, rcx
0x1400234b0  mov     r8, cs:off_14006C2C0
0x1400234b7  mov     rdx, rcx
0x1400234ba  mov     rcx, cs:WdfDriverGlobals
0x1400234c1  mov     rax, [rax+650h]
0x1400234c8  call    _guard_dispatch_icall
0x1400234cd  mov     rsi, [rax+8]
0x1400234d1  cmp     byte ptr [rsi+411h], 0
0x1400234d8  jnz     loc_1400235F4
0x1400234de  mov     rdi, [rsi+98h]
0x1400234e5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400234ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400234f3  jnz     loc_140023628
0x1400234f9  xor     ebp, ebp
0x1400234fb  mov     byte ptr [rsi+364h], 1
0x140023502  cmp     [rdi+10h], ebp
0x140023505  jbe     loc_1400235C5
0x14002350b  mov     rax, [rdi+30h]
0x14002350f  mov     r15d, ebp
0x140023512  imul    r14, r15, 78h ; 'x'
0x140023516  mov     ecx, [r14+rax+40h]
0x14002351b  test    cl, 2
0x14002351e  jnz     loc_1400235BA
0x140023524  xor     r12b, r12b
0x140023527  call    cs:__imp_KeGetCurrentIrql
0x14002352e  nop     dword ptr [rax+rax+00h]
0x140023533  cmp     al, 2
0x140023535  jnz     short loc_140023548
0x140023537  mov     rcx, [rdi+8]
0x14002353b  cmp     [rcx+411h], r12b
0x140023542  jnz     loc_140023654
0x140023548  mov     rbx, [rdi+30h]
0x14002354c  mov     rcx, [rbx+r14+18h]
0x140023551  call    DynamicLock_Acquire
0x140023556  mov     [rbx+r14+20h], r12b
0x14002355b  mov     rbx, [rdi+28h]
0x14002355f  mov     rcx, [rsi+58h]
0x140023563  shl     r15, 4
0x140023567  add     rbx, r15
0x14002356a  mov     rdx, rbx
0x14002356d  call    XilRegister_ReadUlong
0x140023572  mov     rcx, [rsi+58h]
0x140023576  and     eax, 0C200h
0x14002357b  or      eax, 0E000000h
0x140023580  mov     [rsp+58h+arg_8], eax
0x140023584  mov     r8, [rcx+8]
0x140023588  cmp     byte ptr [r8+411h], 0
0x140023590  jnz     short loc_1400235DF
0x140023592  mov     [rbx], eax
0x140023594  lock or [rsp+58h+var_58], 0
0x140023599  mov     rcx, [rdi+30h]
0x14002359d  mov     bl, [rcx+r14+20h]
0x1400235a2  mov     byte ptr [rcx+r14+20h], 0
0x1400235a8  mov     rcx, [rcx+r14+18h]
0x1400235ad  call    DynamicLock_Release
0x1400235b2  test    bl, bl
0x1400235b4  jnz     loc_140023661
0x1400235ba  inc     ebp
0x1400235bc  cmp     ebp, [rdi+10h]
0x1400235bf  jb      loc_14002350B
0x1400235c5  mov     rbx, [rsp+58h+arg_0]
0x1400235ca  xor     eax, eax
0x1400235cc  mov     rbp, [rsp+58h+arg_10]
0x1400235d1  add     rsp, 30h
0x1400235d5  pop     r15
0x1400235d7  pop     r14
0x1400235d9  pop     r12
0x1400235db  pop     rdi
0x1400235dc  pop     rsi
0x1400235dd  retn
0x1400235df  lea     r9, [rsp+58h+arg_8]
0x1400235e4  mov     r8d, 2
0x1400235ea  mov     rdx, rbx
0x1400235ed  call    Register_WriteSecureMmio
0x1400235f2  jmp     short loc_140023599
0x1400235f4  call    cs:__imp_KeGetCurrentIrql
0x1400235fb  nop     dword ptr [rax+rax+00h]
0x140023600  test    al, al
0x140023602  jz      loc_1400234DE
0x140023608  mov     r9d, 0CBFh
0x14002360e  lea     r8, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140023615  xor     edx, edx
0x140023617  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x14002361e  call    Debug_FreAssertMsg
0x140023623  jmp     loc_1400234DE
0x140023628  mov     rcx, [rsi+48h]
0x14002362c  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140023633  mov     r9d, 5Ch ; '\'
0x140023639  mov     [rsp+58h+var_30], rbx
0x14002363e  mov     [rsp+58h+var_38], rax
0x140023643  lea     r8d, [r9-58h]
0x140023647  mov     dl, r8b
0x14002364a  call    WPP_RECORDER_SF_q
0x14002364f  jmp     loc_1400234F9
0x140023654  call    Controller_LowerAndTrackIrql
0x140023659  mov     r12b, 1
0x14002365c  jmp     loc_140023548
0x140023661  mov     rcx, [rdi+8]
0x140023665  call    Controller_RaiseAndTrackIrql
0x14002366a  jmp     loc_1400235BA
```
