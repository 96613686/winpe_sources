# A2DP_Device::StopIoQueueWithStatus(_IO_QUEUE *,long)

- ea: `0x140033fe0`
- end: `0x1400340ea`
- name: `?StopIoQueueWithStatus@A2DP_Device@@QEAAXPEAU_IO_QUEUE@@J@Z`
- size: `266`
- prototype: `void __fastcall(A2DP_Device *__hidden this, struct _IO_QUEUE *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140032818`
- `0x140033e10`

## callees

- `0x140010628`
- `0x14001d0c0`
- `0x140033fe0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400340ce`
- `ntoskrnl!IofCompleteRequest` at `0x1400340ce`

## pseudocode

```c
void __fastcall A2DP_Device::StopIoQueueWithStatus(A2DP_Device *this, struct _IO_QUEUE *a2, __int64 a3)
{
  struct _IO_QUEUE *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rcx
  IRP *v6; // rcx
  _QWORD v7[3]; // [rsp+50h] [rbp-18h] BYREF

  v3 = a2;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      147,
      (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
      182,
      (char)this);
  v7[1] = v7;
  v7[0] = v7;
  IoQueue_StopAndDrain(v3, v7, a3);
  while ( 1 )
  {
    v4 = v7[0];
    if ( (_QWORD *)v7[0] == v7 )
      break;
    if ( *(_QWORD **)(v7[0] + 8LL) != v7 || (v5 = *(_QWORD *)v7[0], *(_QWORD *)(*(_QWORD *)v7[0] + 8LL) != v7[0]) )
      __fastfail(3u);
    v7[0] = *(_QWORD *)v7[0];
    *(_QWORD *)(v5 + 8) = v7;
    v6 = (IRP *)(v4 - 168);
    if ( v4 != 168 )
    {
      v6->IoStatus.Status = -1073741130;
      IofCompleteRequest(v6, 0);
    }
  }
}

```

## disassembly

```asm
0x140033fe0  push    rbx
0x140033fe2  sub     rsp, 60h
0x140033fe6  mov     rbx, rdx
0x140033fe9  mov     r9, rcx
0x140033fec  mov     rcx, cs:WPP_GLOBAL_Control
0x140033ff3  lea     rax, WPP_GLOBAL_Control
0x140033ffa  cmp     rcx, rax
0x140033ffd  jz      short loc_140034010
0x140033fff  mov     eax, [rcx+2Ch]
0x140034002  test    al, 10h
0x140034004  jz      short loc_140034010
0x140034006  cmp     byte ptr [rcx+29h], 4
0x14003400a  jb      short loc_140034010
0x14003400c  mov     dl, 1
0x14003400e  jmp     short loc_140034012
0x140034010  xor     dl, dl
0x140034012  lea     rax, WPP_RECORDER_INITIALIZED
0x140034019  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034020  setnz   r8b
0x140034024  test    dl, dl
0x140034026  jnz     short loc_14003402D
0x140034028  test    r8b, r8b
0x14003402b  jz      short loc_140034067
0x14003402d  mov     [rsp+68h+var_20], r9
0x140034032  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x140034039  mov     r9, [rcx+40h]
0x14003403d  mov     rcx, [rcx+18h]
0x140034041  mov     [rsp+68h+var_28], 0C00002B6h
0x140034049  mov     [rsp+68h+var_30], rax
0x14003404e  mov     [rsp+68h+var_38], 93h
0x140034055  mov     [rsp+68h+var_40], 5
0x14003405d  mov     [rsp+68h+var_48], 4
0x140034062  call    WPP_RECORDER_AND_TRACE_SF_dq
0x140034067  lea     rax, [rsp+68h+var_18]
0x14003406c  mov     rcx, rbx
0x14003406f  mov     [rsp+68h+var_10], rax
0x140034074  lea     rdx, [rsp+68h+var_18]
0x140034079  lea     rax, [rsp+68h+var_18]
0x14003407e  mov     [rsp+68h+var_18], rax
0x140034083  call    IoQueue_StopAndDrain
0x140034088  mov     rax, [rsp+68h+var_18]
0x14003408d  lea     rcx, [rsp+68h+var_18]
0x140034092  cmp     rax, rcx
0x140034095  jz      short loc_1400340E3
0x140034097  lea     rcx, [rsp+68h+var_18]
0x14003409c  cmp     [rax+8], rcx
0x1400340a0  jnz     short loc_1400340DC
0x1400340a2  mov     rcx, [rax]
0x1400340a5  cmp     [rcx+8], rax
0x1400340a9  jnz     short loc_1400340DC
0x1400340ab  mov     [rsp+68h+var_18], rcx
0x1400340b0  lea     rdx, [rsp+68h+var_18]
0x1400340b5  mov     [rcx+8], rdx
0x1400340b9  lea     rcx, [rax-0A8h]; Irp
0x1400340c0  test    rcx, rcx
0x1400340c3  jz      short loc_140034088
0x1400340c5  xor     edx, edx; PriorityBoost
0x1400340c7  mov     dword ptr [rcx+30h], 0C00002B6h
0x1400340ce  call    cs:__imp_IofCompleteRequest
0x1400340d5  nop     dword ptr [rax+rax+00h]
0x1400340da  jmp     short loc_140034088
0x1400340dc  mov     ecx, 3
0x1400340e1  int     29h; Win8: RtlFailFast(ecx)
0x1400340e3  add     rsp, 60h
0x1400340e7  pop     rbx
0x1400340e8  retn
```
