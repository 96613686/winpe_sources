# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001d58`
- end: `0x180001e48`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 **, __int64 **, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d564`
- `0x18000d600`
- `0x18000d69c`

## callees

- `0x180001bdc`
- `0x180001d58`
- `0x180002bc0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 **a6,
        __int64 a7)
{
  __int64 v9; // rcx
  int v10; // r8d
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rdx
  _BYTE v16[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v17; // [rsp+50h] [rbp-48h]
  int v18; // [rsp+58h] [rbp-40h]
  int v19; // [rsp+5Ch] [rbp-3Ch]
  __int64 *v20; // [rsp+60h] [rbp-38h]
  int v21; // [rsp+68h] [rbp-30h]
  int v22; // [rsp+6Ch] [rbp-2Ch]
  __int64 v23; // [rsp+70h] [rbp-28h]
  __int64 v24; // [rsp+78h] [rbp-20h]

  v23 = a7;
  v9 = -1;
  v24 = 4;
  v10 = 2;
  v11 = *a6;
  if ( *a6 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &qword_1800142D0;
    v13 = 2;
  }
  v21 = v13;
  v20 = v11;
  v22 = 0;
  v14 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_WORD *)v14 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v14 = &qword_1800142D0;
  }
  v17 = v14;
  v18 = v10;
  v19 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5, v16);
}

```

## disassembly

```asm
0x180001d58  sub     rsp, 98h
0x180001d5f  mov     rax, cs:__security_cookie
0x180001d66  xor     rax, rsp
0x180001d69  mov     [rsp+98h+var_18], rax
0x180001d71  mov     rax, [rsp+98h+arg_30]
0x180001d79  xor     r9d, r9d
0x180001d7c  mov     [rsp+98h+var_28], rax
0x180001d81  mov     r11, rdx
0x180001d84  mov     rax, [rsp+98h+arg_28]
0x180001d8c  mov     r10, rcx
0x180001d8f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001d93  mov     [rsp+98h+var_20], 4
0x180001d9c  lea     r8d, [r9+2]
0x180001da0  mov     rdx, [rax]
0x180001da3  test    rdx, rdx
0x180001da6  jz      short loc_180001DBE
0x180001da8  mov     rax, rcx
0x180001dab  inc     rax
0x180001dae  cmp     [rdx+rax*2], r9w
0x180001db3  jnz     short loc_180001DAB
0x180001db5  lea     eax, ds:2[rax*2]
0x180001dbc  jmp     short loc_180001DC8
0x180001dbe  lea     rdx, qword_1800142D0
0x180001dc5  mov     eax, r8d
0x180001dc8  mov     [rsp+98h+var_30], eax
0x180001dcc  mov     rax, [rsp+98h+arg_20]
0x180001dd4  mov     [rsp+98h+var_38], rdx
0x180001dd9  mov     [rsp+98h+var_2C], r9d
0x180001dde  mov     rdx, [rax]
0x180001de1  test    rdx, rdx
0x180001de4  jz      short loc_180001DFA
0x180001de6  inc     rcx
0x180001de9  cmp     [rdx+rcx*2], r9w
0x180001dee  jnz     short loc_180001DE6
0x180001df0  lea     r8d, ds:2[rcx*2]
0x180001df8  jmp     short loc_180001E01
0x180001dfa  lea     rdx, qword_1800142D0
0x180001e01  lea     rax, [rsp+98h+var_68]
0x180001e06  mov     [rsp+98h+var_48], rdx
0x180001e0b  mov     [rsp+98h+var_40], r8d
0x180001e10  mov     rdx, r11
0x180001e13  mov     [rsp+98h+var_70], rax
0x180001e18  xor     r8d, r8d
0x180001e1b  mov     rcx, r10
0x180001e1e  mov     [rsp+98h+var_78], 5
0x180001e26  mov     [rsp+98h+var_3C], r9d
0x180001e2b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001e30  mov     rcx, [rsp+98h+var_18]
0x180001e38  xor     rcx, rsp; StackCookie
0x180001e3b  call    __security_check_cookie
0x180001e40  add     rsp, 98h
0x180001e47  retn
```
