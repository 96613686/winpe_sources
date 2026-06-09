# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x140002274`
- end: `0x140002331`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `189`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1400184e8`
- `0x1400185c8`
- `0x14001865c`
- `0x1400186d4`
- `0x140018768`
- `0x1400187fc`
- `0x140018920`
- `0x1400189b4`
- `0x140018aec`

## callees

- `0x140001f60`
- `0x140002274`
- `0x1400029c0`

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
    v7 = &byte_14001BCA1;
    v9 = 1;
  }
  v17 = v9;
  v14 = a6;
  v12 = a5;
  v16 = v7;
  v18 = 0;
  v15 = 8;
  v13 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140025000, a2, 0, 0, 5u, &v11);
}

```

## disassembly

```asm
0x140002274  sub     rsp, 98h
0x14000227b  mov     rax, cs:__security_cookie
0x140002282  xor     rax, rsp
0x140002285  mov     [rsp+98h+var_18], rax
0x14000228d  mov     rax, [rsp+98h+arg_30]
0x140002295  xor     r8d, r8d
0x140002298  mov     rcx, [rax]
0x14000229b  test    rcx, rcx
0x14000229e  jz      short loc_1400022B1
0x1400022a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400022a4  inc     rax
0x1400022a7  cmp     [rcx+rax], r8b
0x1400022ab  jnz     short loc_1400022A4
0x1400022ad  inc     eax
0x1400022af  jmp     short loc_1400022BD
0x1400022b1  lea     rcx, byte_14001BCA1
0x1400022b8  mov     eax, 1
0x1400022bd  mov     [rsp+98h+var_20], eax
0x1400022c1  xor     r9d, r9d
0x1400022c4  mov     rax, [rsp+98h+arg_28]
0x1400022cc  mov     [rsp+98h+var_38], rax
0x1400022d1  mov     rax, [rsp+98h+arg_20]
0x1400022d9  mov     [rsp+98h+var_48], rax
0x1400022de  lea     rax, [rsp+98h+var_68]
0x1400022e3  mov     [rsp+98h+var_28], rcx
0x1400022e8  lea     rcx, dword_140025000
0x1400022ef  mov     [rsp+98h+var_70], rax
0x1400022f4  mov     [rsp+98h+var_78], 5
0x1400022fc  mov     [rsp+98h+var_1C], r8d
0x140002301  mov     [rsp+98h+var_30], 8
0x14000230a  mov     [rsp+98h+var_40], 4
0x140002313  call    _tlgWriteTransfer_EventWriteTransfer
0x140002318  mov     rcx, [rsp+98h+var_18]
0x140002320  xor     rcx, rsp; StackCookie
0x140002323  call    __security_check_cookie
0x140002328  add     rsp, 98h
0x14000232f  retn
```
