# WdagPluginNotifyRoutine

- ea: `0x14002daa0`
- end: `0x14002dbb5`
- name: `WdagPluginNotifyRoutine`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140001010`
- `0x140001044`
- `0x140006a20`
- `0x14002daa0`
- `0x14002dbbc`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14002db0f`
- `ntoskrnl!PsGetProcessId` at `0x14002db0f`

## pseudocode

```c
__int64 __fastcall WdagPluginNotifyRoutine(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct _KPROCESS *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9)
{
  __int64 v11; // rcx
  int v12; // r14d
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int v17; // [rsp+30h] [rbp-81h] BYREF
  int v18; // [rsp+34h] [rbp-7Dh] BYREF
  __int64 v19[2]; // [rsp+38h] [rbp-79h] BYREF
  int v20; // [rsp+48h] [rbp-69h]
  int v21; // [rsp+4Ch] [rbp-65h]
  __int64 v22; // [rsp+50h] [rbp-61h]
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+60h] [rbp-51h] BYREF
  int *v24; // [rsp+80h] [rbp-31h]
  __int64 v25; // [rsp+88h] [rbp-29h]
  __int64 v26; // [rsp+90h] [rbp-21h]
  __int64 v27; // [rsp+98h] [rbp-19h]
  int *v28; // [rsp+A0h] [rbp-11h]
  __int64 v29; // [rsp+A8h] [rbp-9h]

  v19[1] = a1;
  v19[0] = a6;
  v21 = 0;
  v20 = a2;
  v22 = a3;
  v12 = WdagPluginEvaluate(v19, a2);
  if ( v12 < 0 && dword_140019000 )
  {
    if ( a4 )
      PsGetProcessId(a4);
    if ( (unsigned int)dword_140019000 > 4 && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      v17 = v14;
      v24 = &v17;
      v25 = v15;
      v28 = &v18;
      v26 = a1;
      v27 = 16;
      v18 = v12;
      v29 = v15;
      tlgWriteTransfer_EtwWriteTransfer(v13, (unsigned __int8 *)&dword_14001612C, v14, v15, 5u, &v23);
    }
  }
  *a9 = 0;
  return 0;
}

```

## disassembly

```asm
0x14002daa0  push    rbp
0x14002daa2  push    rbx
0x14002daa3  push    rsi
0x14002daa4  push    rdi
0x14002daa5  push    r14
0x14002daa7  lea     rbp, [rsp-0Fh]
0x14002daac  sub     rsp, 0C0h
0x14002dab3  mov     rax, cs:__security_cookie
0x14002daba  xor     rax, rsp
0x14002dabd  mov     [rbp+2Fh+var_30], rax
0x14002dac1  mov     rax, [rbp+2Fh+arg_28]
0x14002dac5  mov     rsi, rcx
0x14002dac8  mov     rdi, [rbp+2Fh+arg_40]
0x14002dacc  mov     rbx, r9
0x14002dacf  mov     [rbp+2Fh+var_A0], rcx
0x14002dad3  lea     rcx, [rbp+2Fh+var_A8]
0x14002dad7  mov     [rbp+2Fh+var_A8], rax
0x14002dadb  mov     [rbp+2Fh+var_94], 0
0x14002dae2  mov     [rbp+2Fh+var_98], edx
0x14002dae5  mov     [rbp+2Fh+var_90], r8
0x14002dae9  call    WdagPluginEvaluate
0x14002daee  mov     r14d, eax
0x14002daf1  test    eax, eax
0x14002daf3  jns     loc_14002DB92
0x14002daf9  mov     edx, cs:dword_140019000
0x14002daff  test    edx, edx
0x14002db01  jz      loc_14002DB92
0x14002db07  test    rbx, rbx
0x14002db0a  jz      short loc_14002DB20
0x14002db0c  mov     rcx, rbx; Process
0x14002db0f  call    cs:__imp_PsGetProcessId
0x14002db16  nop     dword ptr [rax+rax+00h]
0x14002db1b  mov     r8, rax
0x14002db1e  jmp     short loc_14002DB23
0x14002db20  xor     r8d, r8d
0x14002db23  mov     eax, cs:dword_140019000
0x14002db29  mov     r9d, 4
0x14002db2f  cmp     eax, r9d
0x14002db32  jbe     short loc_14002DB92
0x14002db34  mov     rdx, 400000000000h
0x14002db3e  call    _tlgKeywordOn
0x14002db43  test    al, al
0x14002db45  jz      short loc_14002DB92
0x14002db47  lea     rax, [rsp+0E0h+var_B0]
0x14002db4c  mov     [rsp+0E0h+var_B0], r8d
0x14002db51  mov     [rbp+2Fh+var_60], rax
0x14002db55  lea     rdx, dword_14001612C; int
0x14002db5c  lea     rax, [rbp+2Fh+var_AC]
0x14002db60  mov     [rbp+2Fh+var_58], r9
0x14002db64  mov     [rbp+2Fh+var_40], rax
0x14002db68  lea     rax, [rbp+2Fh+var_80]
0x14002db6c  mov     [rsp+0E0h+var_B8], rax; __int64
0x14002db71  mov     [rsp+0E0h+var_C0], 5; ULONG
0x14002db79  mov     [rbp+2Fh+var_50], rsi
0x14002db7d  mov     [rbp+2Fh+var_48], 10h
0x14002db85  mov     [rbp+2Fh+var_AC], r14d
0x14002db89  mov     [rbp+2Fh+var_38], r9
0x14002db8d  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002db92  mov     dword ptr [rdi], 0
0x14002db98  xor     eax, eax
0x14002db9a  mov     rcx, [rbp+2Fh+var_30]
0x14002db9e  xor     rcx, rsp; StackCookie
0x14002dba1  call    __security_check_cookie
0x14002dba6  add     rsp, 0C0h
0x14002dbad  pop     r14
0x14002dbaf  pop     rdi
0x14002dbb0  pop     rsi
0x14002dbb1  pop     rbx
0x14002dbb2  pop     rbp
0x14002dbb3  retn
```
