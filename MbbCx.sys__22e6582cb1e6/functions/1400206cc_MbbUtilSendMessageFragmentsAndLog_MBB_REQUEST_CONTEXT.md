# MbbUtilSendMessageFragmentsAndLog(_MBB_REQUEST_CONTEXT *)

- ea: `0x1400206cc`
- end: `0x1400208b6`
- name: `?MbbUtilSendMessageFragmentsAndLog@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `490`
- prototype: `__int64 __fastcall(struct _MBB_REQUEST_CONTEXT *)`
- caller_count: `11`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400026f0`
- `0x140002840`
- `0x140002960`
- `0x140002a40`
- `0x140002bb0`
- `0x140002c90`
- `0x140011070`
- `0x140016c90`
- `0x14001e7b8`
- `0x14001fc2c`
- `0x1400208bc`

## callees

- `0x14001dff0`
- `0x140020330`
- `0x1400206cc`
- `0x140024338`
- `0x14003e100`
- `0x140041664`

## pseudocode

```c
__int64 __fastcall MbbUtilSendMessageFragmentsAndLog(struct _MBB_REQUEST_CONTEXT *a1)
{
  char *v1; // rsi
  char (near **CommandString)[32]; // rax
  int *v4; // r14
  const GUID *v5; // rdi
  int v6; // edx
  char (near **v7)[32]; // rbp
  __int64 v8; // rcx
  int v10; // [rsp+88h] [rbp-70h]
  int v11; // [rsp+B8h] [rbp-40h]
  int v12; // [rsp+100h] [rbp+8h] BYREF
  int v13; // [rsp+108h] [rbp+10h] BYREF
  int v14; // [rsp+110h] [rbp+18h] BYREF
  int v15; // [rsp+118h] [rbp+20h] BYREF

  v1 = (char *)a1 + 604;
  CommandString = MbbUtilGetCommandString((struct _MBB_REQUEST_CONTEXT *)((char *)a1 + 604));
  v4 = (int *)((char *)a1 + 600);
  v15 = 3;
  v5 = (const GUID *)((char *)a1 + 24);
  v6 = *((_DWORD *)a1 + 150) + 48;
  v13 = 1;
  v14 = v6;
  v7 = CommandString;
  v12 = 0;
  if ( (int)MbbEventActivityIdCtl((LPGUID)((char *)a1 + 24)) < 0 )
    v5 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *((_BYTE *)v7 + v8) );
  v10 = *v4;
  MbbWriteEvent(
    &CID_COMMAND_SEND,
    v5,
    0,
    7u,
    (char *)a1 + 432,
    8,
    (char *)a1 + 16,
    4,
    v1,
    16,
    v7,
    v8 + 1,
    v1 + 16,
    4,
    (char *)a1 + 600,
    4,
    *((_QWORD *)a1 + 74),
    v10);
  v11 = *v4;
  MbbWriteEventOpn(
    &COMMAND_MSG,
    v5,
    0,
    0xAu,
    &v15,
    4,
    &v14,
    4,
    (char *)a1 + 20,
    4,
    &v13,
    4,
    &v12,
    4,
    v1,
    16,
    v1 + 16,
    4,
    (char *)a1 + 624,
    4,
    (char *)a1 + 600,
    4,
    *((_QWORD *)a1 + 74),
    v11);
  return MbbUtilSendMessageFragments(a1);
}

```

## disassembly

```asm
0x1400206cc  push    rbx
0x1400206ce  push    rbp
0x1400206cf  push    rsi
0x1400206d0  push    rdi
0x1400206d1  push    r12
0x1400206d3  push    r14
0x1400206d5  push    r15
0x1400206d7  sub     rsp, 0C0h
0x1400206de  lea     rsi, [rcx+25Ch]
0x1400206e5  mov     rbx, rcx
0x1400206e8  mov     rcx, rsi; Source1
0x1400206eb  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x1400206f0  lea     r14, [rbx+258h]
0x1400206f7  mov     [rsp+0F8h+arg_18], 3
0x140020702  mov     edx, [r14]
0x140020705  lea     rdi, [rbx+18h]
0x140020709  add     edx, 30h ; '0'
0x14002070c  mov     [rsp+0F8h+arg_8], 1
0x140020717  mov     rcx, rdi; ActivityId
0x14002071a  mov     [rsp+0F8h+arg_10], edx
0x140020721  mov     rbp, rax
0x140020724  mov     [rsp+0F8h+arg_0], 0
0x14002072f  call    ?MbbEventActivityIdCtl@@YAJPEAU_GUID@@@Z; MbbEventActivityIdCtl(_GUID *)
0x140020734  xor     ecx, ecx
0x140020736  lea     r15, [rsi+10h]
0x14002073a  test    eax, eax
0x14002073c  cmovs   rdi, rcx
0x140020740  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140020744  inc     rcx
0x140020747  cmp     byte ptr [rcx+rbp], 0
0x14002074b  jnz     short loc_140020744
0x14002074d  mov     eax, [r14]
0x140020750  lea     rdx, [rbx+10h]
0x140020754  mov     dword ptr [rsp+0F8h+var_70], eax
0x14002075b  lea     r8, [rbx+1B0h]
0x140020762  mov     rax, [rbx+250h]
0x140020769  mov     r9d, 7; unsigned __int16
0x14002076f  mov     [rsp+0F8h+var_78], rax
0x140020777  inc     rcx
0x14002077a  lea     r12d, [r9-3]
0x14002077e  mov     [rsp+0F8h+var_80], r12
0x140020783  mov     [rsp+0F8h+var_88], r14
0x140020788  mov     [rsp+0F8h+var_90], r12
0x14002078d  mov     [rsp+0F8h+var_98], r15
0x140020792  mov     [rsp+0F8h+var_A0], rcx
0x140020797  lea     rcx, CID_COMMAND_SEND; EventDescriptor
0x14002079e  mov     [rsp+0F8h+var_A8], rbp
0x1400207a3  lea     ebp, [r9+9]
0x1400207a7  mov     [rsp+0F8h+var_B0], rbp
0x1400207ac  mov     [rsp+0F8h+var_B8], rsi
0x1400207b1  mov     [rsp+0F8h+var_C0], r12
0x1400207b6  mov     [rsp+0F8h+var_C8], rdx
0x1400207bb  mov     rdx, rdi; ActivityId
0x1400207be  mov     [rsp+0F8h+var_D0], 8
0x1400207c7  mov     [rsp+0F8h+var_D8], r8
0x1400207cc  xor     r8d, r8d; RelatedActivityId
0x1400207cf  call    ?MbbWriteEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEvent(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x1400207d4  mov     eax, [r14]
0x1400207d7  lea     rcx, [rbx+270h]
0x1400207de  mov     [rsp+0F8h+var_40], eax
0x1400207e5  lea     r8, [rbx+14h]
0x1400207e9  mov     rax, [rbx+250h]
0x1400207f0  lea     r9d, [r12+6]; unsigned __int16
0x1400207f5  mov     [rsp+0F8h+var_48], rax
0x1400207fd  mov     rdx, rdi; ActivityId
0x140020800  mov     [rsp+0F8h+var_50], r12
0x140020808  lea     rax, [rsp+0F8h+arg_0]
0x140020810  mov     [rsp+0F8h+var_58], r14
0x140020818  mov     [rsp+0F8h+var_60], r12
0x140020820  mov     [rsp+0F8h+var_68], rcx
0x140020828  lea     rcx, COMMAND_MSG; EventDescriptor
0x14002082f  mov     [rsp+0F8h+var_70], r12
0x140020837  mov     [rsp+0F8h+var_78], r15
0x14002083f  mov     [rsp+0F8h+var_80], rbp
0x140020844  mov     [rsp+0F8h+var_88], rsi
0x140020849  mov     [rsp+0F8h+var_90], r12
0x14002084e  mov     [rsp+0F8h+var_98], rax
0x140020853  lea     rax, [rsp+0F8h+arg_8]
0x14002085b  mov     [rsp+0F8h+var_A0], r12
0x140020860  mov     [rsp+0F8h+var_A8], rax
0x140020865  lea     rax, [rsp+0F8h+arg_10]
0x14002086d  mov     [rsp+0F8h+var_B0], r12
0x140020872  mov     [rsp+0F8h+var_B8], r8
0x140020877  xor     r8d, r8d; RelatedActivityId
0x14002087a  mov     [rsp+0F8h+var_C0], r12
0x14002087f  mov     [rsp+0F8h+var_C8], rax
0x140020884  lea     rax, [rsp+0F8h+arg_18]
0x14002088c  mov     [rsp+0F8h+var_D0], r12
0x140020891  mov     [rsp+0F8h+var_D8], rax
0x140020896  call    ?MbbWriteEventOpn@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEventOpn(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x14002089b  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x14002089e  call    ?MbbUtilSendMessageFragments@@YAHPEAU_MBB_REQUEST_CONTEXT@@@Z; MbbUtilSendMessageFragments(_MBB_REQUEST_CONTEXT *)
0x1400208a3  add     rsp, 0C0h
0x1400208aa  pop     r15
0x1400208ac  pop     r14
0x1400208ae  pop     r12
0x1400208b0  pop     rdi
0x1400208b1  pop     rsi
0x1400208b2  pop     rbp
0x1400208b3  pop     rbx
0x1400208b4  retn
```
