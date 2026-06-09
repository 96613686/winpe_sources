# LogEpmapDebugEvent

- ea: `0x18000804c`
- end: `0x1800080f1`
- name: `LogEpmapDebugEvent`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800018a0`
- `0x180002798`
- `0x180006b20`

## callees

- `0x1800028f8`
- `0x18000804c`
- `0x18000a980`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800080d6`
- `ntdll!EtwEventWrite` at `0x1800080d6`

## pseudocode

```c
__int64 __fastcall LogEpmapDebugEvent(__int16 a1, int a2, int a3)
{
  __int64 result; // rax
  _QWORD v4[2]; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v5[8]; // [rsp+30h] [rbp-50h] BYREF
  __int16 v6; // [rsp+90h] [rbp+10h] BYREF
  int v7; // [rsp+98h] [rbp+18h] BYREF
  int v8; // [rsp+A0h] [rbp+20h] BYREF

  v8 = a3;
  v7 = a2;
  v6 = a1;
  LODWORD(v4[0]) = 0;
  result = IsEpmapEventEnabled((struct _EVENT_DESCRIPTOR *)&EpmapDebugEvent);
  if ( (_DWORD)result )
  {
    v5[0] = &v6;
    v5[1] = 2;
    v5[3] = 4;
    v5[2] = &v7;
    v5[5] = 4;
    v5[4] = &v8;
    v5[6] = v4;
    v5[7] = 4;
    return ((__int64 (__fastcall *)(__int64, const struct _EVENT_DESCRIPTOR *, __int64, _QWORD *, _QWORD, _QWORD))EtwEventWrite)(
             g_EpmapEtwHandle,
             &EpmapDebugEvent,
             4,
             v5,
             v4[0],
             v4[1]);
  }
  return result;
}

```

## disassembly

```asm
0x18000804c  mov     [rsp-8+arg_10], r8d
0x180008051  mov     [rsp-8+arg_8], edx
0x180008055  mov     [rsp-8+arg_0], cx
0x18000805a  push    rbp
0x18000805b  mov     rbp, rsp
0x18000805e  sub     rsp, 80h
0x180008065  mov     rax, cs:__security_cookie
0x18000806c  xor     rax, rsp
0x18000806f  mov     [rbp+var_10], rax
0x180008073  lea     rcx, EpmapDebugEvent; struct _EVENT_DESCRIPTOR *
0x18000807a  mov     [rbp+var_60], 0
0x180008081  call    ?IsEpmapEventEnabled@@YAHPEAU_EVENT_DESCRIPTOR@@@Z; IsEpmapEventEnabled(_EVENT_DESCRIPTOR *)
0x180008086  test    eax, eax
0x180008088  jz      short loc_1800080DC
0x18000808a  mov     rcx, cs:g_EpmapEtwHandle
0x180008091  lea     rax, [rbp+arg_0]
0x180008095  mov     [rbp+var_50], rax
0x180008099  lea     r9, [rbp+var_50]
0x18000809d  mov     r8d, 4
0x1800080a3  mov     [rbp+var_48], 2
0x1800080ab  lea     rax, [rbp+arg_8]
0x1800080af  mov     [rbp+var_38], r8
0x1800080b3  mov     [rbp+var_40], rax
0x1800080b7  lea     rdx, EpmapDebugEvent
0x1800080be  lea     rax, [rbp+arg_10]
0x1800080c2  mov     [rbp+var_28], r8
0x1800080c6  mov     [rbp+var_30], rax
0x1800080ca  lea     rax, [rbp+var_60]
0x1800080ce  mov     [rbp+var_20], rax
0x1800080d2  mov     [rbp+var_18], r8
0x1800080d6  call    cs:__imp_EtwEventWrite
0x1800080dc  mov     rcx, [rbp+var_10]
0x1800080e0  xor     rcx, rsp; StackCookie
0x1800080e3  call    __security_check_cookie
0x1800080e8  add     rsp, 80h
0x1800080ef  pop     rbp
0x1800080f0  retn
```
