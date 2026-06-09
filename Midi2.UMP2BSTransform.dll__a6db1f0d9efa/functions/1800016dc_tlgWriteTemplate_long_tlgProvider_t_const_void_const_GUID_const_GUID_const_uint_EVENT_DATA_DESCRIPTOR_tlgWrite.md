# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800016dc`
- end: `0x18000177b`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c2c0`
- `0x18000d200`

## callees

- `0x18000163c`
- `0x1800016dc`
- `0x180001ef0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6)
{
  const unsigned __int16 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v12; // [rsp+50h] [rbp-38h]
  int v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+5Ch] [rbp-2Ch]
  __int64 v15; // [rsp+60h] [rbp-28h]
  __int64 v16; // [rsp+68h] [rbp-20h]

  v15 = a6;
  v16 = 8;
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
    v7 = &word_180010E0A;
    v9 = 1;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 4u, &v11);
}

```

## disassembly

```asm
0x1800016dc  sub     rsp, 88h
0x1800016e3  mov     rax, cs:__security_cookie
0x1800016ea  xor     rax, rsp
0x1800016ed  mov     [rsp+88h+var_18], rax
0x1800016f2  mov     rax, [rsp+88h+arg_28]
0x1800016fa  mov     r10, rcx
0x1800016fd  mov     [rsp+88h+var_28], rax
0x180001702  xor     r8d, r8d
0x180001705  mov     rax, [rsp+88h+arg_20]
0x18000170d  mov     [rsp+88h+var_20], 8
0x180001716  mov     rcx, [rax]
0x180001719  test    rcx, rcx
0x18000171c  jz      short loc_18000172F
0x18000171e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001722  inc     rax
0x180001725  cmp     [rcx+rax], r8b
0x180001729  jnz     short loc_180001722
0x18000172b  inc     eax
0x18000172d  jmp     short loc_18000173B
0x18000172f  lea     rcx, word_180010E0A
0x180001736  mov     eax, 1
0x18000173b  mov     [rsp+88h+var_30], eax
0x18000173f  xor     r9d, r9d
0x180001742  lea     rax, [rsp+88h+var_58]
0x180001747  mov     [rsp+88h+var_38], rcx
0x18000174c  mov     [rsp+88h+var_60], rax
0x180001751  mov     rcx, r10
0x180001754  mov     [rsp+88h+var_68], 4
0x18000175c  mov     [rsp+88h+var_2C], r8d
0x180001761  call    _tlgWriteTransfer_EventWriteTransfer
0x180001766  mov     rcx, [rsp+88h+var_18]
0x18000176b  xor     rcx, rsp; StackCookie
0x18000176e  call    __security_check_cookie
0x180001773  add     rsp, 88h
0x18000177a  retn
```
