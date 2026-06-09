# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x180001310`
- end: `0x1800013cd`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `189`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ba38`
- `0x18001bb18`
- `0x18001bbac`
- `0x18001bc24`
- `0x18001bcb8`
- `0x18001bd4c`
- `0x18001be70`
- `0x18001bf04`
- `0x18001bf98`

## callees

- `0x180001310`
- `0x1800014a4`
- `0x180001c60`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7)
{
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+50h] [rbp-48h]
  __int64 v13; // [rsp+58h] [rbp-40h]
  __int64 v14; // [rsp+60h] [rbp-38h]
  __int64 v15; // [rsp+68h] [rbp-30h]
  const unsigned __int16 *v16; // [rsp+70h] [rbp-28h]
  int v17; // [rsp+78h] [rbp-20h]
  int v18; // [rsp+7Ch] [rbp-1Ch]

  v7 = *a7;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &qword_180020258;
    v9 = 1;
  }
  v17 = v9;
  v14 = a6;
  v12 = a5;
  v16 = v7;
  v18 = 0;
  v15 = 8;
  v13 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180029000, a2, 0, 0, 5u, &v11);
}

```

## disassembly

```asm
0x180001310  sub     rsp, 98h
0x180001317  mov     rax, cs:__security_cookie
0x18000131e  xor     rax, rsp
0x180001321  mov     [rsp+98h+var_18], rax
0x180001329  mov     rax, [rsp+98h+arg_30]
0x180001331  xor     r8d, r8d
0x180001334  mov     rcx, [rax]
0x180001337  test    rcx, rcx
0x18000133a  jz      short loc_18000134D
0x18000133c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001340  inc     rax
0x180001343  cmp     [rcx+rax], r8b
0x180001347  jnz     short loc_180001340
0x180001349  inc     eax
0x18000134b  jmp     short loc_180001359
0x18000134d  lea     rcx, qword_180020258
0x180001354  mov     eax, 1
0x180001359  mov     [rsp+98h+var_20], eax
0x18000135d  xor     r9d, r9d
0x180001360  mov     rax, [rsp+98h+arg_28]
0x180001368  mov     [rsp+98h+var_38], rax
0x18000136d  mov     rax, [rsp+98h+arg_20]
0x180001375  mov     [rsp+98h+var_48], rax
0x18000137a  lea     rax, [rsp+98h+var_68]
0x18000137f  mov     [rsp+98h+var_28], rcx
0x180001384  lea     rcx, dword_180029000
0x18000138b  mov     [rsp+98h+var_70], rax
0x180001390  mov     [rsp+98h+var_78], 5
0x180001398  mov     [rsp+98h+var_1C], r8d
0x18000139d  mov     [rsp+98h+var_30], 8
0x1800013a6  mov     [rsp+98h+var_40], 4
0x1800013af  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013b4  mov     rcx, [rsp+98h+var_18]
0x1800013bc  xor     rcx, rsp; StackCookie
0x1800013bf  call    __security_check_cookie
0x1800013c4  add     rsp, 98h
0x1800013cb  retn
```
