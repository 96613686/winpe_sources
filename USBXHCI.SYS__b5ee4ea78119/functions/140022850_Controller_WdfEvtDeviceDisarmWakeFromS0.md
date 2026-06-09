# Controller_WdfEvtDeviceDisarmWakeFromS0

- ea: `0x140022850`
- end: `0x140022a28`
- name: `Controller_WdfEvtDeviceDisarmWakeFromS0`
- size: `472`
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
- `0x140022850`
- `0x140031928`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400228f1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400229d9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400228f1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400229d9`

## string_xrefs

- `0x1400229fc`: `Code Path Requires Passive Level`

## pseudocode

```c
__int64 __fastcall Controller_WdfEvtDeviceDisarmWakeFromS0(__int64 a1)
{
  char v1; // bl
  int v2; // edx
  __int64 v3; // rsi
  __int64 v4; // rbp
  __int64 result; // rax
  unsigned int i; // r14d
  char v7; // r12
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // r15
  int *v11; // rbx
  __int16 Ulong; // ax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  char v16; // bl
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
      3316);
  v4 = *(_QWORD *)(v3 + 152);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 4;
    WPP_RECORDER_SF_q(*(_QWORD *)(v3 + 72), v2, 4, 93, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v1);
  }
  result = *(unsigned int *)(v3 + 736);
  *(_BYTE *)(v3 + 868) = 0;
  if ( (result & 0x20000000) == 0 )
  {
    for ( i = 0; i < *(_DWORD *)(v4 + 16); ++i )
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
      v10 = 120LL * i;
      DynamicLock_Acquire(*(_QWORD *)(v9 + v10 + 24));
      *(_BYTE *)(v9 + v10 + 32) = v7;
      v11 = (int *)(16LL * i + *(_QWORD *)(v4 + 40));
      Ulong = XilRegister_ReadUlong(*(_QWORD *)(v3 + 88), v11);
      v13 = *(_QWORD *)(v3 + 88);
      v14 = Ulong & 0xC200;
      v18 = v14;
      if ( *(_BYTE *)(*(_QWORD *)(v13 + 8) + 1041LL) )
      {
        Register_WriteSecureMmio(v13, v11, 2, &v18);
      }
      else
      {
        *v11 = v14;
        _InterlockedOr(v17, 0);
      }
      v15 = *(_QWORD *)(v4 + 48);
      v16 = *(_BYTE *)(v10 + v15 + 32);
      *(_BYTE *)(v10 + v15 + 32) = 0;
      result = DynamicLock_Release(*(_QWORD *)(v10 + v15 + 24));
      if ( v16 )
        result = Controller_RaiseAndTrackIrql(*(_QWORD *)(v4 + 8));
    }
  }
  return result;
}

```

## disassembly

```asm
0x140022850  mov     [rsp+arg_0], rbx
0x140022855  mov     [rsp+arg_10], rbp
0x14002285a  push    rsi
0x14002285b  push    rdi
0x14002285c  push    r12
0x14002285e  push    r14
0x140022860  push    r15
0x140022862  sub     rsp, 30h
0x140022866  mov     rax, cs:WdfFunctions_01033
0x14002286d  mov     rbx, rcx
0x140022870  mov     r8, cs:off_14006C2C0
0x140022877  mov     rdx, rcx
0x14002287a  mov     rcx, cs:WdfDriverGlobals
0x140022881  mov     rax, [rax+650h]
0x140022888  call    _guard_dispatch_icall
0x14002288d  mov     rsi, [rax+8]
0x140022891  cmp     byte ptr [rsi+411h], 0
0x140022898  jnz     loc_1400229D9
0x14002289e  mov     rbp, [rsi+98h]
0x1400228a5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400228ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400228b3  jnz     loc_1400229AD
0x1400228b9  mov     eax, [rsi+2E0h]
0x1400228bf  mov     byte ptr [rsi+364h], 0
0x1400228c6  bt      rax, 1Dh
0x1400228cb  jnb     short loc_1400228E5
0x1400228cd  mov     rbx, [rsp+58h+arg_0]
0x1400228d2  mov     rbp, [rsp+58h+arg_10]
0x1400228d7  add     rsp, 30h
0x1400228db  pop     r15
0x1400228dd  pop     r14
0x1400228df  pop     r12
0x1400228e1  pop     rdi
0x1400228e2  pop     rsi
0x1400228e3  retn
0x1400228e5  xor     r14d, r14d
0x1400228e8  cmp     [rbp+10h], r14d
0x1400228ec  jbe     short loc_1400228CD
0x1400228ee  xor     r12b, r12b
0x1400228f1  call    cs:__imp_KeGetCurrentIrql
0x1400228f8  nop     dword ptr [rax+rax+00h]
0x1400228fd  cmp     al, 2
0x1400228ff  jnz     short loc_140022912
0x140022901  mov     rcx, [rbp+8]
0x140022905  cmp     [rcx+411h], r12b
0x14002290c  jnz     loc_140022A0D
0x140022912  mov     rbx, [rbp+30h]
0x140022916  mov     edi, r14d
0x140022919  imul    r15, rdi, 78h ; 'x'
0x14002291d  mov     rcx, [rbx+r15+18h]
0x140022922  call    DynamicLock_Acquire
0x140022927  mov     [rbx+r15+20h], r12b
0x14002292c  mov     rbx, [rbp+28h]
0x140022930  mov     rcx, [rsi+58h]
0x140022934  shl     rdi, 4
0x140022938  add     rbx, rdi
0x14002293b  mov     rdx, rbx
0x14002293e  call    XilRegister_ReadUlong
0x140022943  mov     rcx, [rsi+58h]
0x140022947  and     eax, 0C200h
0x14002294c  mov     [rsp+58h+arg_8], eax
0x140022950  mov     r8, [rcx+8]
0x140022954  cmp     byte ptr [r8+411h], 0
0x14002295c  jnz     short loc_140022998
0x14002295e  mov     [rbx], eax
0x140022960  lock or [rsp+58h+var_58], 0
0x140022965  mov     rcx, [rbp+30h]
0x140022969  mov     bl, [r15+rcx+20h]
0x14002296e  mov     byte ptr [r15+rcx+20h], 0
0x140022974  mov     rcx, [r15+rcx+18h]
0x140022979  call    DynamicLock_Release
0x14002297e  test    bl, bl
0x140022980  jnz     loc_140022A1A
0x140022986  inc     r14d
0x140022989  cmp     r14d, [rbp+10h]
0x14002298d  jb      loc_1400228EE
0x140022993  jmp     loc_1400228CD
0x140022998  lea     r9, [rsp+58h+arg_8]
0x14002299d  mov     r8d, 2
0x1400229a3  mov     rdx, rbx
0x1400229a6  call    Register_WriteSecureMmio
0x1400229ab  jmp     short loc_140022965
0x1400229ad  mov     rcx, [rsi+48h]
0x1400229b1  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x1400229b8  mov     r9d, 5Dh ; ']'
0x1400229be  mov     [rsp+58h+var_30], rbx
0x1400229c3  mov     [rsp+58h+var_38], rax
0x1400229c8  lea     r8d, [r9-59h]
0x1400229cc  mov     dl, r8b
0x1400229cf  call    WPP_RECORDER_SF_q
0x1400229d4  jmp     loc_1400228B9
0x1400229d9  call    cs:__imp_KeGetCurrentIrql
0x1400229e0  nop     dword ptr [rax+rax+00h]
0x1400229e5  test    al, al
0x1400229e7  jz      loc_14002289E
0x1400229ed  mov     r9d, 0CF4h
0x1400229f3  lea     r8, aOnecoreDrivers; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x1400229fa  xor     edx, edx
0x1400229fc  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x140022a03  call    Debug_FreAssertMsg
0x140022a08  jmp     loc_14002289E
0x140022a0d  call    Controller_LowerAndTrackIrql
0x140022a12  mov     r12b, 1
0x140022a15  jmp     loc_140022912
0x140022a1a  mov     rcx, [rbp+8]
0x140022a1e  call    Controller_RaiseAndTrackIrql
0x140022a23  jmp     loc_140022986
```
