# BthUsb_ScoWriteStopWait(_DEVICE_EXTENSION *)

- ea: `0x1400098bc`
- end: `0x140009a03`
- name: `?BthUsb_ScoWriteStopWait@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `327`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000581c`

## callees

- `0x14000175c`
- `0x1400017d4`
- `0x1400098bc`
- `0x14000db7c`
- `0x14000dbc4`
- `0x14001b73c`

## pseudocode

```c
void __fastcall BthUsb_ScoWriteStopWait(struct _DEVICE_EXTENSION *a1, __int16 a2, int a3)
{
  char v4; // bl
  unsigned __int16 v5; // dx
  int v6; // r9d
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  __int16 v10; // dx
  int v11; // r8d

  v4 = 1;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    a2,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    19,
    (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids);
  ResourceQueue_Stop(&a1->Sco.WriteCtxQueue);
  v7 = BthUsb_PipeRequest(a1, v5, a1->Pipes[4].PipeHandle, v6);
  if ( v7 < 0 )
  {
    LOBYTE(v8) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      20,
      (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids,
      v7);
  }
  LOBYTE(v8) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    (_WORD)v8,
    v9,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    21,
    (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids);
  ResourceQueue_StopAndWait(&a1->Sco.WriteCtxQueue);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  LOBYTE(v10) = v4;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v10,
    v11,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    22,
    (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids);
}

```

## disassembly

```asm
0x1400098bc  push    rbx
0x1400098be  push    rbp
0x1400098bf  push    rsi
0x1400098c0  push    rdi
0x1400098c1  push    r15
0x1400098c3  sub     rsp, 50h
0x1400098c7  mov     rdi, rcx
0x1400098ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400098d1  mov     bl, 1
0x1400098d3  mov     ebp, 4
0x1400098d8  mov     eax, [rcx+2Ch]
0x1400098db  test    al, 8
0x1400098dd  jz      short loc_1400098E9
0x1400098df  cmp     [rcx+29h], bpl
0x1400098e3  jb      short loc_1400098E9
0x1400098e5  mov     dl, bl
0x1400098e7  jmp     short loc_1400098EB
0x1400098e9  xor     dl, dl
0x1400098eb  mov     r9, [rcx+40h]
0x1400098ef  lea     r15, WPP_5fbab361c58e305795b7101c701f7776_Traceguids
0x1400098f6  mov     rcx, [rcx+18h]
0x1400098fa  mov     [rsp+78h+var_40], r15
0x1400098ff  mov     [rsp+78h+var_48], 13h
0x140009906  mov     [rsp+78h+var_50], ebp
0x14000990a  mov     [rsp+78h+var_58], bpl
0x14000990f  call    WPP_RECORDER_AND_TRACE_SF_
0x140009914  lea     rsi, [rdi+138h]
0x14000991b  mov     rcx, rsi
0x14000991e  call    ResourceQueue_Stop
0x140009923  mov     r8, [rdi+0D8h]; void *
0x14000992a  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14000992d  call    ?BthUsb_PipeRequest@@YAJPEAU_DEVICE_EXTENSION@@GPEAXJ@Z; BthUsb_PipeRequest(_DEVICE_EXTENSION *,ushort,void *,long)
0x140009932  test    eax, eax
0x140009934  jns     short loc_140009979
0x140009936  mov     r8, cs:WPP_GLOBAL_Control
0x14000993d  mov     ecx, [r8+2Ch]
0x140009941  test    cl, 8
0x140009944  jz      short loc_140009951
0x140009946  cmp     byte ptr [r8+29h], 2
0x14000994b  jb      short loc_140009951
0x14000994d  mov     dl, bl
0x14000994f  jmp     short loc_140009953
0x140009951  xor     dl, dl
0x140009953  mov     r9, [r8+40h]
0x140009957  mov     rcx, [r8+18h]
0x14000995b  mov     [rsp+78h+var_38], eax
0x14000995f  mov     [rsp+78h+var_40], r15
0x140009964  mov     [rsp+78h+var_48], 14h
0x14000996b  mov     [rsp+78h+var_50], ebp
0x14000996f  mov     [rsp+78h+var_58], 2
0x140009974  call    WPP_RECORDER_AND_TRACE_SF_D
0x140009979  mov     rcx, cs:WPP_GLOBAL_Control
0x140009980  mov     eax, [rcx+2Ch]
0x140009983  test    al, 8
0x140009985  jz      short loc_140009991
0x140009987  cmp     [rcx+29h], bpl
0x14000998b  jb      short loc_140009991
0x14000998d  mov     dl, bl
0x14000998f  jmp     short loc_140009993
0x140009991  xor     dl, dl
0x140009993  mov     r9, [rcx+40h]
0x140009997  mov     rcx, [rcx+18h]
0x14000999b  mov     [rsp+78h+var_40], r15
0x1400099a0  mov     [rsp+78h+var_48], 15h
0x1400099a7  mov     [rsp+78h+var_50], ebp
0x1400099ab  mov     [rsp+78h+var_58], bpl
0x1400099b0  call    WPP_RECORDER_AND_TRACE_SF_
0x1400099b5  mov     rcx, rsi
0x1400099b8  call    ResourceQueue_StopAndWait
0x1400099bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400099c4  mov     eax, [rcx+2Ch]
0x1400099c7  test    al, 8
0x1400099c9  jz      short loc_1400099D1
0x1400099cb  cmp     [rcx+29h], bpl
0x1400099cf  jnb     short loc_1400099D3
0x1400099d1  xor     bl, bl
0x1400099d3  mov     r9, [rcx+40h]
0x1400099d7  mov     dl, bl
0x1400099d9  mov     rcx, [rcx+18h]
0x1400099dd  mov     [rsp+78h+var_40], r15
0x1400099e2  mov     [rsp+78h+var_48], 16h
0x1400099e9  mov     [rsp+78h+var_50], ebp
0x1400099ed  mov     [rsp+78h+var_58], bpl
0x1400099f2  call    WPP_RECORDER_AND_TRACE_SF_
0x1400099f7  add     rsp, 50h
0x1400099fb  pop     r15
0x1400099fd  pop     rdi
0x1400099fe  pop     rsi
0x1400099ff  pop     rbp
0x140009a00  pop     rbx
0x140009a01  retn
```
