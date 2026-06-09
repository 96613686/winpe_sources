# VidTraceInt3Routine

- ea: `0x140034840`
- end: `0x140034934`
- name: `VidTraceInt3Routine`
- size: `244`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x14001bed4`
- `0x140025e74`
- `0x140026090`
- `0x14002ab18`
- `0x14002b790`
- `0x14002b934`
- `0x14002bab0`
- `0x14002bd44`
- `0x14002c610`
- `0x14002e5b0`
- `0x1400a8bd0`
- `0x1400d633c`
- `0x1400db3c0`
- `0x1400de334`
- `0x1400e0af8`
- `0x1400e37a0`

## callees

- `0x140021c60`
- `0x140034840`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x140034895`
- `ntoskrnl!EtwActivityIdControl` at `0x140034895`
- `ntoskrnl!EtwWrite` at `0x140034903`
- `ntoskrnl!EtwWrite` at `0x140034903`

## pseudocode

```c
NTSTATUS __fastcall VidTraceInt3Routine(PCEVENT_DESCRIPTOR EventDescriptor, __int64 a2, __int64 a3, __int64 a4)
{
  GUID v4; // xmm1
  GUID ActivityId; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+40h] [rbp-19h] BYREF
  __int64 v12; // [rsp+48h] [rbp-11h] BYREF
  GUID v13; // [rsp+50h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp+7h] BYREF
  __int64 *v15; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]
  GUID *p_ActivityId; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]

  v4 = 0;
  v13 = 0;
  ActivityId = 0;
  if ( VID_TRACE_ETW_GUID_Context )
  {
    EtwActivityIdControl(1u, &ActivityId);
    v4 = ActivityId;
  }
  UserData.Ptr = (ULONGLONG)&v11;
  v13 = v4;
  v15 = &v12;
  *(_QWORD *)&ActivityId.Data1 = a4;
  p_ActivityId = &ActivityId;
  v12 = a3;
  v11 = a2;
  *(_QWORD *)&UserData.Size = 8;
  v16 = 8;
  v18 = 8;
  return EtwWrite(VID_TRACE_ETW_GUID_Context, EventDescriptor, &v13, 3u, &UserData);
}

```

## disassembly

```asm
0x140034840  mov     [rsp-8+arg_8], rbx
0x140034845  mov     [rsp-8+arg_10], rsi
0x14003484a  push    rbp
0x14003484b  push    rdi
0x14003484c  push    r14
0x14003484e  lea     rbp, [rsp-47h]
0x140034853  sub     rsp, 0A0h
0x14003485a  mov     rax, cs:__security_cookie
0x140034861  xor     rax, rsp
0x140034864  mov     [rbp+57h+var_20], rax
0x140034868  cmp     cs:VID_TRACE_ETW_GUID_Context, 0
0x140034870  xorps   xmm0, xmm0
0x140034873  xorps   xmm1, xmm1
0x140034876  mov     rbx, r9
0x140034879  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x14003487d  mov     rdi, r8
0x140034880  mov     rsi, rdx
0x140034883  movaps  xmmword ptr [rbp+57h+ActivityId.Data1], xmm1
0x140034887  mov     r14, rcx
0x14003488a  jz      short loc_1400348A5
0x14003488c  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x140034890  mov     ecx, 1; ControlCode
0x140034895  call    cs:__imp_EtwActivityIdControl
0x14003489c  nop     dword ptr [rax+rax+00h]
0x1400348a1  movaps  xmm1, xmmword ptr [rbp+57h+ActivityId.Data1]
0x1400348a5  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x1400348ac  lea     rax, [rbp+57h+var_70]
0x1400348b0  mov     [rbp+57h+var_50.Ptr], rax
0x1400348b4  lea     r8, [rbp+57h+var_60]; ActivityId
0x1400348b8  lea     rax, [rbp+57h+var_68]
0x1400348bc  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm1
0x1400348c1  mov     [rbp+57h+var_40], rax
0x1400348c5  mov     r9d, 3; UserDataCount
0x1400348cb  lea     rax, [rbp+57h+ActivityId]
0x1400348cf  mov     qword ptr [rbp+57h+ActivityId.Data1], rbx
0x1400348d3  mov     [rbp+57h+var_30], rax
0x1400348d7  mov     rdx, r14; EventDescriptor
0x1400348da  lea     rax, [rbp+57h+var_50]
0x1400348de  mov     [rbp+57h+var_68], rdi
0x1400348e2  mov     [rsp+0B0h+UserData], rax; UserData
0x1400348e7  mov     [rbp+57h+var_70], rsi
0x1400348eb  mov     qword ptr [rbp+57h+var_50.Size], 8
0x1400348f3  mov     [rbp+57h+var_38], 8
0x1400348fb  mov     [rbp+57h+var_28], 8
0x140034903  call    cs:__imp_EtwWrite
0x14003490a  nop     dword ptr [rax+rax+00h]
0x14003490f  mov     rcx, [rbp+57h+var_20]
0x140034913  xor     rcx, rsp; StackCookie
0x140034916  call    __security_check_cookie
0x14003491b  lea     r11, [rsp+0B0h+var_10]
0x140034923  mov     rbx, [r11+28h]
0x140034927  mov     rsi, [r11+30h]
0x14003492b  mov     rsp, r11
0x14003492e  pop     r14
0x140034930  pop     rdi
0x140034931  pop     rbp
0x140034932  retn
```
