# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001008`
- end: `0x1400010af`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140017008`
- `0x14001d03c`

## callees

- `0x140001008`
- `0x1400010b8`
- `0x14000ddc0`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int **a6)
{
  int *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]
  __int64 v12; // [rsp+58h] [rbp-30h]
  int *v13; // [rsp+60h] [rbp-28h]
  int v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+6Ch] [rbp-1Ch]

  v6 = *a6;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)v6 + v7) );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &dword_1400104EC;
    v8 = 2;
  }
  v14 = v8;
  v11 = a5;
  v13 = v6;
  v15 = 0;
  v12 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140013000, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x140001008  sub     rsp, 88h
0x14000100f  mov     rax, cs:__security_cookie
0x140001016  xor     rax, rsp
0x140001019  mov     [rsp+88h+var_18], rax
0x14000101e  mov     rax, [rsp+88h+arg_28]
0x140001026  xor     r8d, r8d
0x140001029  mov     rcx, [rax]
0x14000102c  test    rcx, rcx
0x14000102f  jz      short loc_140001048
0x140001031  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001035  inc     rax
0x140001038  cmp     [rcx+rax*2], r8w
0x14000103d  jnz     short loc_140001035
0x14000103f  lea     eax, ds:2[rax*2]
0x140001046  jmp     short loc_140001054
0x140001048  lea     rcx, dword_1400104EC
0x14000104f  mov     eax, 2
0x140001054  mov     [rsp+88h+var_20], eax
0x140001058  xor     r9d, r9d
0x14000105b  mov     rax, [rsp+88h+arg_20]
0x140001063  mov     [rsp+88h+var_38], rax
0x140001068  lea     rax, [rsp+88h+var_58]
0x14000106d  mov     [rsp+88h+var_28], rcx
0x140001072  lea     rcx, dword_140013000
0x140001079  mov     [rsp+88h+var_60], rax
0x14000107e  mov     [rsp+88h+var_68], 4
0x140001086  mov     [rsp+88h+var_1C], r8d
0x14000108b  mov     [rsp+88h+var_30], 8
0x140001094  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001099  mov     rcx, [rsp+88h+var_18]
0x14000109e  xor     rcx, rsp; StackCookie
0x1400010a1  call    __security_check_cookie
0x1400010a6  add     rsp, 88h
0x1400010ad  retn
```
