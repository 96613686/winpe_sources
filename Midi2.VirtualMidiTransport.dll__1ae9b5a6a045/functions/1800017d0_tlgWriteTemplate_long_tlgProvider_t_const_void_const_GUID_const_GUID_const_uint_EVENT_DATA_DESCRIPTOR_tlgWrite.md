# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800017d0`
- end: `0x18000186f`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `159`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e0a4`
- `0x18000e840`
- `0x180010b50`
- `0x1800114f0`
- `0x180018b70`
- `0x18001d080`
- `0x18001d430`

## callees

- `0x18000163c`
- `0x1800017d0`
- `0x1800038f0`

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
    v7 = &word_18002377A;
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
0x1800017d0  sub     rsp, 88h
0x1800017d7  mov     rax, cs:__security_cookie
0x1800017de  xor     rax, rsp
0x1800017e1  mov     [rsp+88h+var_18], rax
0x1800017e6  mov     rax, [rsp+88h+arg_28]
0x1800017ee  mov     r10, rcx
0x1800017f1  mov     [rsp+88h+var_28], rax
0x1800017f6  xor     r8d, r8d
0x1800017f9  mov     rax, [rsp+88h+arg_20]
0x180001801  mov     [rsp+88h+var_20], 8
0x18000180a  mov     rcx, [rax]
0x18000180d  test    rcx, rcx
0x180001810  jz      short loc_180001823
0x180001812  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001816  inc     rax
0x180001819  cmp     [rcx+rax], r8b
0x18000181d  jnz     short loc_180001816
0x18000181f  inc     eax
0x180001821  jmp     short loc_18000182F
0x180001823  lea     rcx, word_18002377A
0x18000182a  mov     eax, 1
0x18000182f  mov     [rsp+88h+var_30], eax
0x180001833  xor     r9d, r9d
0x180001836  lea     rax, [rsp+88h+var_58]
0x18000183b  mov     [rsp+88h+var_38], rcx
0x180001840  mov     [rsp+88h+var_60], rax
0x180001845  mov     rcx, r10
0x180001848  mov     [rsp+88h+var_68], 4
0x180001850  mov     [rsp+88h+var_2C], r8d
0x180001855  call    _tlgWriteTransfer_EventWriteTransfer
0x18000185a  mov     rcx, [rsp+88h+var_18]
0x18000185f  xor     rcx, rsp; StackCookie
0x180001862  call    __security_check_cookie
0x180001867  add     rsp, 88h
0x18000186e  retn
```
