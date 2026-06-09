# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000214c`
- end: `0x180002216`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z`
- size: `202`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64 **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f628`
- `0x18000f908`

## callees

- `0x180001bdc`
- `0x18000214c`
- `0x180002bc0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 **a8,
        __int64 a9)
{
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  _BYTE v14[32]; // [rsp+30h] [rbp-51h] BYREF
  __int64 v15; // [rsp+50h] [rbp-31h]
  __int64 v16; // [rsp+58h] [rbp-29h]
  __int64 v17; // [rsp+60h] [rbp-21h]
  __int64 v18; // [rsp+68h] [rbp-19h]
  __int64 v19; // [rsp+70h] [rbp-11h]
  __int64 v20; // [rsp+78h] [rbp-9h]
  __int64 *v21; // [rsp+80h] [rbp-1h]
  int v22; // [rsp+88h] [rbp+7h]
  int v23; // [rsp+8Ch] [rbp+Bh]
  __int64 v24; // [rsp+90h] [rbp+Fh]
  __int64 v25; // [rsp+98h] [rbp+17h]

  v24 = a9;
  v25 = 4;
  v10 = *a8;
  if ( *a8 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &qword_1800142D0;
    v12 = 2;
  }
  v22 = v12;
  v19 = a7;
  v17 = a6;
  v15 = a5;
  v21 = v10;
  v23 = 0;
  v20 = 4;
  v18 = 4;
  v16 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 7, v14);
}

```

## disassembly

```asm
0x18000214c  push    rbp
0x18000214e  lea     rbp, [rsp-2Fh]
0x180002153  sub     rsp, 0B0h
0x18000215a  mov     rax, cs:__security_cookie
0x180002161  xor     rax, rsp
0x180002164  mov     [rbp+2Fh+var_10], rax
0x180002168  mov     rax, [rbp+2Fh+arg_40]
0x18000216c  mov     r10, rcx
0x18000216f  mov     [rbp+2Fh+var_20], rax
0x180002173  xor     r9d, r9d
0x180002176  mov     rax, [rbp+2Fh+arg_38]
0x18000217a  mov     [rbp+2Fh+var_18], 4
0x180002182  mov     rcx, [rax]
0x180002185  test    rcx, rcx
0x180002188  jz      short loc_1800021A1
0x18000218a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000218e  inc     rax
0x180002191  cmp     [rcx+rax*2], r9w
0x180002196  jnz     short loc_18000218E
0x180002198  lea     eax, ds:2[rax*2]
0x18000219f  jmp     short loc_1800021AD
0x1800021a1  lea     rcx, qword_1800142D0
0x1800021a8  mov     eax, 2
0x1800021ad  mov     [rbp+2Fh+var_28], eax
0x1800021b0  mov     rax, [rbp+2Fh+arg_30]
0x1800021b4  mov     [rbp+2Fh+var_40], rax
0x1800021b8  mov     rax, [rbp+2Fh+arg_28]
0x1800021bc  mov     [rbp+2Fh+var_50], rax
0x1800021c0  mov     rax, [rbp+2Fh+arg_20]
0x1800021c4  mov     [rbp+2Fh+var_60], rax
0x1800021c8  lea     rax, [rbp+2Fh+var_80]
0x1800021cc  mov     [rbp+2Fh+var_30], rcx
0x1800021d0  mov     rcx, r10
0x1800021d3  mov     [rsp+0B0h+var_88], rax
0x1800021d8  mov     [rsp+0B0h+var_90], 7
0x1800021e0  mov     [rbp+2Fh+var_24], r9d
0x1800021e4  mov     [rbp+2Fh+var_38], 4
0x1800021ec  mov     [rbp+2Fh+var_48], 4
0x1800021f4  mov     [rbp+2Fh+var_58], 8
0x1800021fc  call    _tlgWriteTransfer_EventWriteTransfer
0x180002201  mov     rcx, [rbp+2Fh+var_10]
0x180002205  xor     rcx, rsp; StackCookie
0x180002208  call    __security_check_cookie
0x18000220d  add     rsp, 0B0h
0x180002214  pop     rbp
0x180002215  retn
```
