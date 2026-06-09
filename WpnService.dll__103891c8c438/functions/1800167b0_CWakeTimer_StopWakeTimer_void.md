# CWakeTimer::StopWakeTimer(void * *)

- ea: `0x1800167b0`
- end: `0x180016887`
- name: `?StopWakeTimer@CWakeTimer@@SAXPEAPEAX@Z`
- size: `215`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180016498`

## callees

- `0x1800167b0`
- `0x1800341f4`
- `0x180034224`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180016825`
- `ntdll!RtlNtStatusToDosError` at `0x180016825`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x180016801`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x180016801`

## pseudocode

```c
void __fastcall CWakeTimer::StopWakeTimer(void **a1)
{
  _QWORD *v2; // rcx
  NTSTATUS v3; // eax
  signed int v4; // eax
  __int64 v5; // r8

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 && *a1 )
  {
    v3 = EaDeleteAggregatedEvent(*a1, 0);
    if ( v3 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RtlNtStatusToDosError(v3);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v5, (unsigned int)v4);
    }
    *a1 = 0;
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_(v2[2], 26);
}

```

## disassembly

```asm
0x1800167b0  mov     [rsp+arg_0], rbx
0x1800167b5  push    rsi
0x1800167b6  sub     rsp, 20h
0x1800167ba  mov     rbx, rcx
0x1800167bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167c4  lea     rsi, WPP_GLOBAL_Control
0x1800167cb  cmp     rcx, rsi
0x1800167ce  jz      short loc_1800167F1
0x1800167d0  test    byte ptr [rcx+1Ch], 8
0x1800167d4  jz      short loc_1800167F1
0x1800167d6  cmp     byte ptr [rcx+19h], 6
0x1800167da  jb      short loc_1800167F1
0x1800167dc  mov     rcx, [rcx+10h]
0x1800167e0  mov     edx, 18h
0x1800167e5  call    WPP_SF_
0x1800167ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167f1  test    rbx, rbx
0x1800167f4  jz      short loc_18001685D
0x1800167f6  cmp     qword ptr [rbx], 0
0x1800167fa  jz      short loc_18001685D
0x1800167fc  mov     rcx, [rbx]
0x1800167ff  xor     edx, edx
0x180016801  call    cs:__imp_EaDeleteAggregatedEvent
0x180016807  test    eax, eax
0x180016809  jns     short loc_18001684F
0x18001680b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016812  cmp     rcx, rsi
0x180016815  jz      short loc_18001684F
0x180016817  test    byte ptr [rcx+1Ch], 8
0x18001681b  jz      short loc_18001684F
0x18001681d  cmp     byte ptr [rcx+19h], 2
0x180016821  jb      short loc_18001684F
0x180016823  mov     ecx, eax; Status
0x180016825  call    cs:__imp_RtlNtStatusToDosError
0x18001682b  test    eax, eax
0x18001682d  jle     short loc_180016837
0x18001682f  movzx   eax, ax
0x180016832  or      eax, 80070000h
0x180016837  mov     rcx, cs:WPP_GLOBAL_Control
0x18001683e  mov     edx, 19h
0x180016843  mov     r9d, eax
0x180016846  mov     rcx, [rcx+10h]
0x18001684a  call    WPP_SF_d
0x18001684f  mov     qword ptr [rbx], 0
0x180016856  mov     rcx, cs:WPP_GLOBAL_Control
0x18001685d  cmp     rcx, rsi
0x180016860  jz      short loc_18001687C
0x180016862  test    byte ptr [rcx+1Ch], 8
0x180016866  jz      short loc_18001687C
0x180016868  cmp     byte ptr [rcx+19h], 6
0x18001686c  jb      short loc_18001687C
0x18001686e  mov     rcx, [rcx+10h]
0x180016872  mov     edx, 1Ah
0x180016877  call    WPP_SF_
0x18001687c  mov     rbx, [rsp+28h+arg_0]
0x180016881  add     rsp, 20h
0x180016885  pop     rsi
0x180016886  retn
```
