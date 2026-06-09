# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000104c`
- end: `0x140001105`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009a08`

## callees

- `0x14000104c`
- `0x140001280`
- `0x140009d00`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        __int64 a7)
{
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-68h] BYREF
  __int64 v13; // [rsp+50h] [rbp-48h]
  __int64 v14; // [rsp+58h] [rbp-40h]
  const unsigned __int16 *v15; // [rsp+60h] [rbp-38h]
  int v16; // [rsp+68h] [rbp-30h]
  int v17; // [rsp+6Ch] [rbp-2Ch]
  __int64 v18; // [rsp+70h] [rbp-28h]
  __int64 v19; // [rsp+78h] [rbp-20h]

  v18 = a7;
  v19 = 4;
  v8 = *a6;
  if ( *a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v8 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v8 = &dword_14000DC44;
    v10 = 1;
  }
  v16 = v10;
  v13 = a5;
  v15 = v8;
  v17 = 0;
  v14 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 5u, &v12);
}

```

## disassembly

```asm
0x14000104c  sub     rsp, 98h
0x140001053  mov     rax, cs:__security_cookie
0x14000105a  xor     rax, rsp
0x14000105d  mov     [rsp+98h+var_18], rax
0x140001065  mov     rax, [rsp+98h+arg_30]
0x14000106d  mov     r10, rcx
0x140001070  mov     [rsp+98h+var_28], rax
0x140001075  xor     r9d, r9d
0x140001078  mov     rax, [rsp+98h+arg_28]
0x140001080  mov     [rsp+98h+var_20], 4
0x140001089  mov     rcx, [rax]
0x14000108c  test    rcx, rcx
0x14000108f  jz      short loc_1400010A2
0x140001091  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001095  inc     rax
0x140001098  cmp     [rcx+rax], r9b
0x14000109c  jnz     short loc_140001095
0x14000109e  inc     eax
0x1400010a0  jmp     short loc_1400010AE
0x1400010a2  lea     rcx, dword_14000DC44
0x1400010a9  mov     eax, 1
0x1400010ae  mov     [rsp+98h+var_30], eax
0x1400010b2  mov     rax, [rsp+98h+arg_20]
0x1400010ba  mov     [rsp+98h+var_48], rax
0x1400010bf  lea     rax, [rsp+98h+var_68]
0x1400010c4  mov     [rsp+98h+var_38], rcx
0x1400010c9  mov     rcx, r10
0x1400010cc  mov     [rsp+98h+var_70], rax
0x1400010d1  mov     [rsp+98h+var_78], 5
0x1400010d9  mov     [rsp+98h+var_2C], r9d
0x1400010de  mov     [rsp+98h+var_40], 8
0x1400010e7  call    _tlgWriteTransfer_EventWriteTransfer
0x1400010ec  mov     rcx, [rsp+98h+var_18]
0x1400010f4  xor     rcx, rsp; StackCookie
0x1400010f7  call    __security_check_cookie
0x1400010fc  add     rsp, 98h
0x140001103  retn
```
