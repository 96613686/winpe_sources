# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperArray<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800010d0`
- end: `0x18000117c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperArray@$03@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperArray@$03@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002dcc`

## callees

- `0x18000120c`
- `0x180001d40`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-49h] BYREF
  __int64 v10; // [rsp+50h] [rbp-29h]
  __int64 v11; // [rsp+58h] [rbp-21h]
  __int64 *v12; // [rsp+60h] [rbp-19h]
  __int64 v13; // [rsp+68h] [rbp-11h]
  __int64 v14; // [rsp+70h] [rbp-9h]
  int v15; // [rsp+78h] [rbp-1h]
  int v16; // [rsp+7Ch] [rbp+3h]
  __int64 v17; // [rsp+80h] [rbp+7h]
  __int64 v18; // [rsp+88h] [rbp+Fh]
  __int64 v19; // [rsp+90h] [rbp+17h]
  __int64 v20; // [rsp+98h] [rbp+1Fh]

  v19 = a8;
  v17 = a7;
  v20 = 4;
  v18 = 8;
  v13 = 2;
  v16 = 0;
  v14 = *a6;
  v15 = 4 * *((unsigned __int16 *)a6 + 4);
  v10 = a5;
  v12 = a6 + 1;
  v11 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180029000, a2, 0, 0, 7u, &v9);
}

```

## disassembly

```asm
0x1800010d0  push    rbp
0x1800010d2  lea     rbp, [rsp-37h]
0x1800010d7  sub     rsp, 0B0h
0x1800010de  mov     rax, cs:__security_cookie
0x1800010e5  xor     rax, rsp
0x1800010e8  mov     [rbp+37h+var_10], rax
0x1800010ec  mov     rax, [rbp+37h+arg_38]
0x1800010f0  xor     r9d, r9d
0x1800010f3  mov     [rbp+37h+var_20], rax
0x1800010f7  xor     r8d, r8d
0x1800010fa  mov     rax, [rbp+37h+arg_30]
0x1800010fe  mov     [rbp+37h+var_30], rax
0x180001102  mov     rax, [rbp+37h+arg_28]
0x180001106  mov     [rbp+37h+var_18], 4
0x18000110e  mov     [rbp+37h+var_28], 8
0x180001116  mov     [rbp+37h+var_48], 2
0x18000111e  lea     rcx, [rax+8]
0x180001122  mov     [rbp+37h+var_34], r9d
0x180001126  mov     rax, [rax]
0x180001129  mov     [rbp+37h+var_40], rax
0x18000112d  movzx   eax, word ptr [rcx]
0x180001130  shl     eax, 2
0x180001133  mov     [rbp+37h+var_38], eax
0x180001136  mov     rax, [rbp+37h+arg_20]
0x18000113a  mov     [rbp+37h+var_60], rax
0x18000113e  lea     rax, [rbp+37h+var_80]
0x180001142  mov     [rbp+37h+var_50], rcx
0x180001146  lea     rcx, dword_180029000
0x18000114d  mov     [rsp+0B0h+var_88], rax
0x180001152  mov     [rsp+0B0h+var_90], 7
0x18000115a  mov     [rbp+37h+var_58], 8
0x180001162  call    _tlgWriteTransfer_EventWriteTransfer
0x180001167  mov     rcx, [rbp+37h+var_10]
0x18000116b  xor     rcx, rsp; StackCookie
0x18000116e  call    __security_check_cookie
0x180001173  add     rsp, 0B0h
0x18000117a  pop     rbp
0x18000117b  retn
```
