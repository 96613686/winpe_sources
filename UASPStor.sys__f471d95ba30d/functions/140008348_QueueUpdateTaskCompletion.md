# QueueUpdateTaskCompletion

- ea: `0x140008348`
- end: `0x14000841d`
- name: `QueueUpdateTaskCompletion`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140008430`
- `0x140008e00`

## callees

- `0x140002bec`
- `0x140007ee4`
- `0x140008348`

## import_xrefs

- `storport!StorPortNotification` at `0x140008400`
- `storport!StorPortNotification` at `0x140008400`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400083c1`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400083c1`

## pseudocode

```c
__int64 __fastcall QueueUpdateTaskCompletion(__int64 a1)
{
  __int64 v1; // rdi
  __int64 result; // rax
  unsigned __int16 v4; // si
  int Default; // eax
  int v6; // edx

  v1 = *(_QWORD *)(a1 + 32);
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    *(_QWORD *)(a1 + 12) = 0;
    *(_DWORD *)(a1 + 8) = 0;
    if ( *(_BYTE *)(v1 + 2) == 19 )
    {
      if ( !gTracingEnabled || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_10;
      v4 = 40;
    }
    else
    {
      if ( !gTracingEnabled || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_10;
      v4 = 41;
    }
    Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    WPP_RECORDER_SF_P(Default, v6, 5, v4, (__int64)WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v1);
LABEL_10:
    QueueReleaseEntry(a1);
    return StorPortNotification(0, *(_QWORD *)a1, v1);
  }
  return result;
}

```

## disassembly

```asm
0x140008348  mov     [rsp+arg_8], rbx
0x14000834d  mov     [rsp+arg_10], rsi
0x140008352  push    rdi
0x140008353  sub     rsp, 30h
0x140008357  mov     rdi, [rcx+20h]
0x14000835b  mov     rbx, rcx
0x14000835e  or      eax, 0FFFFFFFFh
0x140008361  lock xadd [rcx+18h], eax
0x140008366  cmp     eax, 1
0x140008369  jnz     loc_14000840C
0x14000836f  xor     eax, eax
0x140008371  mov     [rcx+0Ch], rax
0x140008375  mov     [rcx+8], eax
0x140008378  cmp     byte ptr [rdi+2], 13h
0x14000837c  jnz     short loc_14000839D
0x14000837e  cmp     cs:gTracingEnabled, al
0x140008384  jz      short loc_1400083F0
0x140008386  lea     rax, WPP_RECORDER_INITIALIZED
0x14000838d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008394  jz      short loc_1400083F0
0x140008396  mov     esi, 28h ; '('
0x14000839b  jmp     short loc_1400083BA
0x14000839d  cmp     cs:gTracingEnabled, al
0x1400083a3  jz      short loc_1400083F0
0x1400083a5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400083ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400083b3  jz      short loc_1400083F0
0x1400083b5  mov     esi, 29h ; ')'
0x1400083ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400083c1  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400083c8  nop     dword ptr [rax+rax+00h]
0x1400083cd  mov     [rsp+38h+var_10], rdi
0x1400083d2  movzx   r9d, si
0x1400083d6  mov     rcx, rax
0x1400083d9  mov     r8d, 5
0x1400083df  lea     rax, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x1400083e6  mov     [rsp+38h+var_18], rax
0x1400083eb  call    WPP_RECORDER_SF_P
0x1400083f0  mov     rcx, rbx
0x1400083f3  call    QueueReleaseEntry
0x1400083f8  mov     rdx, [rbx]
0x1400083fb  mov     r8, rdi
0x1400083fe  xor     ecx, ecx
0x140008400  call    cs:__imp_StorPortNotification
0x140008407  nop     dword ptr [rax+rax+00h]
0x14000840c  mov     rbx, [rsp+38h+arg_8]
0x140008411  mov     rsi, [rsp+38h+arg_10]
0x140008416  add     rsp, 30h
0x14000841a  pop     rdi
0x14000841b  retn
```
