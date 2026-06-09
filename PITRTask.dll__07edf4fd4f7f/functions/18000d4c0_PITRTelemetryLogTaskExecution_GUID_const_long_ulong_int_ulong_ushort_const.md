# PITRTelemetryLogTaskExecution(_GUID const *,long,ulong,int,ulong,ushort const *)

- ea: `0x18000d4c0`
- end: `0x18000d659`
- name: `?PITRTelemetryLogTaskExecution@@YAXPEBU_GUID@@JKHKPEBG@Z`
- size: `409`
- prototype: `void __fastcall(const struct _GUID *, int, int, int, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a4f0`

## callees

- `0x180001008`
- `0x18000d4c0`
- `0x18000ece8`
- `0x1800107c0`

## pseudocode

```c
void __fastcall PITRTelemetryLogTaskExecution(
        const struct _GUID *a1,
        int a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned __int16 *a6)
{
  const struct _GUID *v10; // rdx
  __int64 *v11; // rcx
  __int64 v12; // rax
  bool v13; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-A5h] BYREF
  int v15; // [rsp+38h] [rbp-A1h] BYREF
  int v16; // [rsp+3Ch] [rbp-9Dh] BYREF
  __int64 v17; // [rsp+40h] [rbp-99h] BYREF
  __int128 v18; // [rsp+48h] [rbp-91h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+60h] [rbp-79h] BYREF
  __int64 *v20; // [rsp+80h] [rbp-59h]
  __int64 v21; // [rsp+88h] [rbp-51h]
  const struct _GUID *v22; // [rsp+90h] [rbp-49h]
  __int64 v23; // [rsp+98h] [rbp-41h]
  int *v24; // [rsp+A0h] [rbp-39h]
  __int64 v25; // [rsp+A8h] [rbp-31h]
  int *v26; // [rsp+B0h] [rbp-29h]
  __int64 v27; // [rsp+B8h] [rbp-21h]
  bool *v28; // [rsp+C0h] [rbp-19h]
  __int64 v29; // [rsp+C8h] [rbp-11h]
  unsigned int *v30; // [rsp+D0h] [rbp-9h]
  __int64 v31; // [rsp+D8h] [rbp-1h]
  __int64 *v32; // [rsp+E0h] [rbp+7h]
  int v33; // [rsp+E8h] [rbp+Fh]
  int v34; // [rsp+ECh] [rbp+13h]

  if ( (int)PITRTelemetryInitialize() >= 0 && dword_18001BFA0 && (unsigned int)dword_18001B000 > 4 )
  {
    v10 = (const struct _GUID *)&v18;
    v18 = 0;
    if ( a1 )
      v10 = a1;
    if ( (unsigned int)dword_18001B000 > 4
      && (qword_18001B010 & 0x800000000000LL) != 0
      && (qword_18001B018 & 0x800000000000LL) == qword_18001B018 )
    {
      v11 = (__int64 *)a6;
      v15 = a3;
      v16 = a2;
      if ( !a6 )
        v11 = qword_180015BA0;
      v14 = a5;
      v17 = 0x80000000LL;
      v13 = a4 != 0;
      v12 = -1;
      do
        ++v12;
      while ( *((_WORD *)v11 + v12) );
      v32 = v11;
      v33 = 2 * v12 + 2;
      v31 = 4;
      v30 = &v14;
      v28 = &v13;
      v26 = &v15;
      v24 = &v16;
      v20 = &v17;
      v27 = 4;
      v25 = 4;
      v22 = v10;
      v34 = 0;
      v29 = 1;
      v23 = 16;
      v21 = 8;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_18001B000, (int)&byte_1800171CB, 0, 0, 9u, &v19);
    }
  }
}

```

## disassembly

```asm
0x18000d4c0  push    rbp
0x18000d4c2  push    rbx
0x18000d4c3  push    rsi
0x18000d4c4  push    rdi
0x18000d4c5  push    r14
0x18000d4c7  lea     rbp, [rsp-27h]
0x18000d4cc  sub     rsp, 100h
0x18000d4d3  mov     rax, cs:__security_cookie
0x18000d4da  xor     rax, rsp
0x18000d4dd  mov     [rbp+47h+var_30], rax
0x18000d4e1  mov     edi, r9d
0x18000d4e4  mov     esi, r8d
0x18000d4e7  mov     r14d, edx
0x18000d4ea  mov     rbx, rcx
0x18000d4ed  call    ?PITRTelemetryInitialize@@YAJXZ; PITRTelemetryInitialize(void)
0x18000d4f2  xor     r8d, r8d; int
0x18000d4f5  test    eax, eax
0x18000d4f7  js      loc_18000D63F
0x18000d4fd  cmp     cs:dword_18001BFA0, r8d
0x18000d504  jz      loc_18000D63F
0x18000d50a  mov     eax, cs:dword_18001B000
0x18000d510  lea     r9d, [r8+4]
0x18000d514  cmp     eax, r9d
0x18000d517  jbe     loc_18000D63F
0x18000d51d  mov     eax, cs:dword_18001B000
0x18000d523  lea     rdx, [rsp+120h+var_D8]
0x18000d528  test    rbx, rbx
0x18000d52b  xorps   xmm0, xmm0
0x18000d52e  movups  [rsp+120h+var_D8], xmm0
0x18000d533  cmovnz  rdx, rbx
0x18000d537  cmp     eax, r9d
0x18000d53a  jbe     loc_18000D63F
0x18000d540  mov     rcx, cs:qword_18001B018
0x18000d547  mov     r10, 800000000000h
0x18000d551  mov     rax, cs:qword_18001B010
0x18000d558  test    r10, rax
0x18000d55b  jz      loc_18000D63F
0x18000d561  mov     rax, rcx
0x18000d564  and     rax, r10
0x18000d567  cmp     rax, rcx
0x18000d56a  jnz     loc_18000D63F
0x18000d570  mov     rcx, [rbp+47h+arg_28]
0x18000d574  lea     rax, qword_180015BA0
0x18000d57b  test    rcx, rcx
0x18000d57e  mov     [rsp+120h+var_E8], esi
0x18000d582  mov     [rsp+120h+var_E4], r14d
0x18000d587  cmovz   rcx, rax
0x18000d58b  mov     eax, [rbp+47h+arg_20]
0x18000d58e  mov     [rsp+120h+var_EC], eax
0x18000d592  test    edi, edi
0x18000d594  mov     eax, 80000000h
0x18000d599  mov     [rsp+120h+var_E0], rax
0x18000d59e  setnz   [rsp+120h+var_F0]
0x18000d5a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d5a7  inc     rax
0x18000d5aa  cmp     [rcx+rax*2], r8w
0x18000d5af  jnz     short loc_18000D5A7
0x18000d5b1  lea     eax, ds:2[rax*2]
0x18000d5b8  mov     [rbp+47h+var_40], rcx
0x18000d5bc  mov     [rbp+47h+var_38], eax
0x18000d5bf  lea     rcx, dword_18001B000; int
0x18000d5c6  lea     rax, [rsp+120h+var_EC]
0x18000d5cb  mov     [rbp+47h+var_48], r9
0x18000d5cf  mov     [rbp+47h+var_50], rax
0x18000d5d3  lea     rax, [rsp+120h+var_F0]
0x18000d5d8  mov     [rbp+47h+var_60], rax
0x18000d5dc  lea     rax, [rsp+120h+var_E8]
0x18000d5e1  mov     [rbp+47h+var_70], rax
0x18000d5e5  lea     rax, [rsp+120h+var_E4]
0x18000d5ea  mov     [rbp+47h+var_80], rax
0x18000d5ee  lea     rax, [rsp+120h+var_E0]
0x18000d5f3  mov     [rbp+47h+var_A0], rax
0x18000d5f7  lea     rax, [rbp+47h+var_C0]
0x18000d5fb  mov     [rbp+47h+var_68], r9
0x18000d5ff  mov     [rbp+47h+var_78], r9
0x18000d603  xor     r9d, r9d; int
0x18000d606  mov     [rbp+47h+var_90], rdx
0x18000d60a  lea     rdx, byte_1800171CB; int
0x18000d611  mov     [rsp+120h+var_F8], rax; PEVENT_DATA_DESCRIPTOR
0x18000d616  mov     [rsp+120h+var_100], 9; ULONG
0x18000d61e  mov     [rbp+47h+var_34], r8d
0x18000d622  mov     [rbp+47h+var_58], 1
0x18000d62a  mov     [rbp+47h+var_88], 10h
0x18000d632  mov     [rbp+47h+var_98], 8
0x18000d63a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d63f  mov     rcx, [rbp+47h+var_30]
0x18000d643  xor     rcx, rsp; StackCookie
0x18000d646  call    __security_check_cookie
0x18000d64b  add     rsp, 100h
0x18000d652  pop     r14
0x18000d654  pop     rdi
0x18000d655  pop     rsi
0x18000d656  pop     rbx
0x18000d657  pop     rbp
0x18000d658  retn
```
