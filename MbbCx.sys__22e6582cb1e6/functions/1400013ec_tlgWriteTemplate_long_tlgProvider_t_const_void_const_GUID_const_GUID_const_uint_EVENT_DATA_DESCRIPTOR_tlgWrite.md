# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400013ec`
- end: `0x1400014a8`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400450ac`

## callees

- `0x1400010b4`
- `0x1400013ec`
- `0x140047e50`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 a7)
{
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v12; // [rsp+50h] [rbp-48h]
  int v13; // [rsp+58h] [rbp-40h]
  int v14; // [rsp+5Ch] [rbp-3Ch]
  __int64 v15; // [rsp+60h] [rbp-38h]
  __int64 v16; // [rsp+68h] [rbp-30h]
  __int64 v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v17 = a7;
  v15 = a6;
  v18 = 4;
  v16 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &qword_14004EC80;
    v9 = 1;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14005E0C8, a2, 0, 0, 5u, &v11);
}

```

## disassembly

```asm
0x1400013ec  mov     r11, rsp
0x1400013ef  sub     rsp, 98h
0x1400013f6  mov     rax, cs:__security_cookie
0x1400013fd  xor     rax, rsp
0x140001400  mov     [rsp+98h+var_18], rax
0x140001408  mov     rax, [rsp+98h+arg_30]
0x140001410  xor     r8d, r8d
0x140001413  mov     [r11-28h], rax
0x140001417  mov     rax, [rsp+98h+arg_28]
0x14000141f  mov     [r11-38h], rax
0x140001423  mov     rax, [rsp+98h+arg_20]
0x14000142b  mov     qword ptr [r11-20h], 4
0x140001433  mov     qword ptr [r11-30h], 4
0x14000143b  mov     rcx, [rax]
0x14000143e  test    rcx, rcx
0x140001441  jz      short loc_140001454
0x140001443  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001447  inc     rax
0x14000144a  cmp     [rcx+rax], r8b
0x14000144e  jnz     short loc_140001447
0x140001450  inc     eax
0x140001452  jmp     short loc_140001460
0x140001454  lea     rcx, qword_14004EC80
0x14000145b  mov     eax, 1
0x140001460  mov     [rsp+98h+var_40], eax
0x140001464  xor     r9d, r9d
0x140001467  lea     rax, [rsp+98h+var_68]
0x14000146c  mov     [rsp+98h+var_48], rcx
0x140001471  mov     [rsp+98h+var_70], rax
0x140001476  lea     rcx, dword_14005E0C8
0x14000147d  mov     [rsp+98h+var_78], 5
0x140001485  mov     [rsp+98h+var_3C], r8d
0x14000148a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000148f  mov     rcx, [rsp+98h+var_18]
0x140001497  xor     rcx, rsp; StackCookie
0x14000149a  call    __security_check_cookie
0x14000149f  add     rsp, 98h
0x1400014a6  retn
```
