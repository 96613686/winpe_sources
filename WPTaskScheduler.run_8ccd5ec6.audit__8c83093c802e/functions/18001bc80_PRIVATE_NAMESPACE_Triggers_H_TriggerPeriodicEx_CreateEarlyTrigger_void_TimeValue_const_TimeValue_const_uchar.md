# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx::CreateEarlyTrigger(void *,TimeValue const &,TimeValue const &,uchar)

- ea: `0x18001bc80`
- end: `0x18001be23`
- name: `?CreateEarlyTrigger@TriggerPeriodicEx@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAXAEBVTimeValue@@1E@Z`
- size: `419`
- prototype: `int(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx *__hidden this, void *, const struct TimeValue *, const struct TimeValue *, unsigned __int8)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180009aa0`
- `0x18000ea40`
- `0x18001bc80`
- `0x18001dd84`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx::CreateEarlyTrigger(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx *this,
        __int64 a2,
        const struct TimeValue *a3,
        const struct TimeValue *a4,
        unsigned __int8 a5)
{
  __int64 *v5; // rbx
  __int64 v10; // rcx
  unsigned int i; // ebx
  __int64 v13; // rsi
  __int64 v14; // r8
  int v15; // eax
  struct Trigger *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  struct _TASK_TRIGGER v19; // [rsp+40h] [rbp-68h] BYREF

  v5 = (__int64 *)((char *)this + 760);
  if ( (byte_180030D04 & 2) != 0 )
    McTemplateU0t_EventWriteTransfer(this, a2, *v5 != 0);
  v10 = *v5;
  if ( !*v5 )
    return 0;
  *(_QWORD *)&v19.cbTriggerSize = 2;
  *(_QWORD *)&v19.wBeginDay = v10;
  if ( *(int *)v10 >= 2 || !*(_DWORD *)(v10 + 4) || !*(_QWORD *)(v10 + 8) )
    return 2194604295LL;
  for ( i = 0; i < *(_DWORD *)(v10 + 4); ++i )
  {
    v13 = *(_QWORD *)(v10 + 8);
    if ( *(_DWORD *)(v13 + 16LL * i) != 1 )
      return 2194604295LL;
    v14 = *(_QWORD *)(v13 + 16LL * i + 8);
    v15 = *(_DWORD *)(v14 + 28) & 1;
    if ( (*(_BYTE *)(v14 + 28) & 1) == 0 )
    {
      *(_DWORD *)(v14 + 28) |= 1u;
      if ( byte_180030D03 < (char)v15 )
        McGenEventWrite_EventWriteTransfer(
          v10,
          (const EVENT_DESCRIPTOR *)LevelWnfStateEarlyTriggerOverride,
          v14,
          1u,
          (PEVENT_DATA_DESCRIPTOR)&v19.wStartHour);
      v10 = *(_QWORD *)&v19.wBeginDay;
    }
    if ( *(_DWORD *)(*(_QWORD *)(v13 + 16LL * i + 8) + 24LL) )
    {
      if ( (byte_180030D04 & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          v10,
          (const EVENT_DESCRIPTOR *)DelayedEarlyTriggerError,
          v14,
          1u,
          (PEVENT_DATA_DESCRIPTOR)&v19.wStartHour);
      return 2194604295LL;
    }
  }
  v16 = Trigger::Alloc(a2, &v19, a3, a4, 0, a5 + 1, 0);
  if ( v16 )
  {
    *((_QWORD *)this + 51) = v16;
    return 0;
  }
  if ( (byte_180030D04 & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v17,
      (const EVENT_DESCRIPTOR *)FailedCreateEarlyTriggerError,
      v18,
      1u,
      (PEVENT_DATA_DESCRIPTOR)&v19.wStartHour);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001bc80  push    rbx
0x18001bc82  push    rbp
0x18001bc83  push    rsi
0x18001bc84  push    rdi
0x18001bc85  push    r12
0x18001bc87  push    r14
0x18001bc89  push    r15
0x18001bc8b  sub     rsp, 70h
0x18001bc8f  mov     rax, cs:__security_cookie
0x18001bc96  xor     rax, rsp
0x18001bc99  mov     qword ptr [rsp+0A8h+var_68.TriggerType], rax
0x18001bc9e  test    cs:byte_180030D04, 2
0x18001bca5  lea     rbx, [rcx+2F8h]
0x18001bcac  mov     r12, r9
0x18001bcaf  mov     r15, r8
0x18001bcb2  mov     r14, rdx
0x18001bcb5  mov     rbp, rcx
0x18001bcb8  jz      short loc_18001BCC9
0x18001bcba  xor     r8d, r8d
0x18001bcbd  cmp     [rbx], r8
0x18001bcc0  setnz   r8b
0x18001bcc4  call    McTemplateU0t_EventWriteTransfer
0x18001bcc9  mov     rcx, [rbx]
0x18001bccc  test    rcx, rcx
0x18001bccf  jnz     short loc_18001BCD8
0x18001bcd1  xor     eax, eax
0x18001bcd3  jmp     loc_18001BD98
0x18001bcd8  mov     qword ptr [rsp+0A8h+var_68.cbTriggerSize], 2
0x18001bce1  mov     qword ptr [rsp+0A8h+var_68.wBeginDay], rcx
0x18001bce6  cmp     dword ptr [rcx], 2
0x18001bce9  jge     loc_18001BD93
0x18001bcef  cmp     dword ptr [rcx+4], 0
0x18001bcf3  jz      loc_18001BD93
0x18001bcf9  cmp     qword ptr [rcx+8], 0
0x18001bcfe  jz      loc_18001BD93
0x18001bd04  xor     ebx, ebx
0x18001bd06  lea     r9d, [rbx+1]
0x18001bd0a  cmp     ebx, [rcx+4]
0x18001bd0d  jnb     loc_18001BDB4
0x18001bd13  mov     rsi, [rcx+8]
0x18001bd17  mov     edi, ebx
0x18001bd19  add     rdi, rdi
0x18001bd1c  cmp     [rsi+rdi*8], r9d
0x18001bd20  jnz     short loc_18001BD93
0x18001bd22  mov     r8, [rsi+rdi*8+8]
0x18001bd27  mov     edx, [r8+1Ch]
0x18001bd2b  mov     eax, edx
0x18001bd2d  and     eax, r9d
0x18001bd30  test    al, al
0x18001bd32  jnz     short loc_18001BD64
0x18001bd34  or      edx, r9d
0x18001bd37  mov     [r8+1Ch], edx
0x18001bd3b  cmp     cs:byte_180030D03, al
0x18001bd41  jge     short loc_18001BD5F
0x18001bd43  lea     rax, [rsp+0A8h+var_68.wStartHour]
0x18001bd48  lea     rdx, LevelWnfStateEarlyTriggerOverride
0x18001bd4f  mov     [rsp+0A8h+var_88], rax
0x18001bd54  call    McGenEventWrite_EventWriteTransfer
0x18001bd59  mov     r9d, 1
0x18001bd5f  mov     rcx, qword ptr [rsp+0A8h+var_68.wBeginDay]
0x18001bd64  mov     rax, [rsi+rdi*8+8]
0x18001bd69  cmp     dword ptr [rax+18h], 0
0x18001bd6d  ja      short loc_18001BD74
0x18001bd6f  add     ebx, r9d
0x18001bd72  jmp     short loc_18001BD0A
0x18001bd74  test    cs:byte_180030D04, r9b
0x18001bd7b  jz      short loc_18001BD93
0x18001bd7d  lea     rax, [rsp+0A8h+var_68.wStartHour]
0x18001bd82  lea     rdx, DelayedEarlyTriggerError
0x18001bd89  mov     [rsp+0A8h+var_88], rax
0x18001bd8e  call    McGenEventWrite_EventWriteTransfer
0x18001bd93  mov     eax, 82CF0107h
0x18001bd98  mov     rcx, qword ptr [rsp+0A8h+var_68.TriggerType]
0x18001bd9d  xor     rcx, rsp; StackCookie
0x18001bda0  call    __security_check_cookie
0x18001bda5  add     rsp, 70h
0x18001bda9  pop     r15
0x18001bdab  pop     r14
0x18001bdad  pop     r12
0x18001bdaf  pop     rdi
0x18001bdb0  pop     rsi
0x18001bdb1  pop     rbp
0x18001bdb2  pop     rbx
0x18001bdb3  retn
0x18001bdb4  mov     al, [rsp+0A8h+arg_20]
0x18001bdbb  lea     rdx, [rsp+0A8h+var_68]; struct _TASK_TRIGGER *
0x18001bdc0  add     al, r9b
0x18001bdc3  mov     [rsp+0A8h+var_78], 0; unsigned int
0x18001bdcb  mov     [rsp+0A8h+var_80], al; char
0x18001bdcf  mov     r9, r12; struct TimeValue *
0x18001bdd2  mov     r8, r15; struct TimeValue *
0x18001bdd5  mov     [rsp+0A8h+var_88], 0; struct _TASK_RUNTIME_DATA *
0x18001bdde  mov     rcx, r14; void *
0x18001bde1  call    ?Alloc@Trigger@@SAPEAV1@PEAXPEAU_TASK_TRIGGER@@AEBVTimeValue@@2PEAU_TASK_RUNTIME_DATA@@EK@Z; Trigger::Alloc(void *,_TASK_TRIGGER *,TimeValue const &,TimeValue const &,_TASK_RUNTIME_DATA *,uchar,ulong)
0x18001bde6  test    rax, rax
0x18001bde9  jnz     short loc_18001BE17
0x18001bdeb  test    cs:byte_180030D04, 8
0x18001bdf2  jz      short loc_18001BE10
0x18001bdf4  lea     rax, [rsp+0A8h+var_68.wStartHour]
0x18001bdf9  mov     r9d, 1
0x18001bdff  lea     rdx, FailedCreateEarlyTriggerError
0x18001be06  mov     [rsp+0A8h+var_88], rax
0x18001be0b  call    McGenEventWrite_EventWriteTransfer
0x18001be10  mov     eax, 8007000Eh
0x18001be15  jmp     short loc_18001BD98
0x18001be17  mov     [rbp+198h], rax
0x18001be1e  jmp     loc_18001BCD1
```
