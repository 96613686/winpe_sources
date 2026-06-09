# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000135c`
- end: `0x180001402`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006df0`

## callees

- `0x1800012b8`
- `0x18000135c`
- `0x18001f420`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v11; // [rsp+50h] [rbp-38h]
  int v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+5Ch] [rbp-2Ch]
  __int64 v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-20h]

  v14 = a6;
  v15 = 4;
  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &dword_180022F6C;
    v8 = 2;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002B000, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x18000135c  sub     rsp, 88h
0x180001363  mov     rax, cs:__security_cookie
0x18000136a  xor     rax, rsp
0x18000136d  mov     [rsp+88h+var_18], rax
0x180001372  mov     rax, [rsp+88h+arg_28]
0x18000137a  xor     r8d, r8d
0x18000137d  mov     [rsp+88h+var_28], rax
0x180001382  mov     r9d, 4
0x180001388  mov     rax, [rsp+88h+arg_20]
0x180001390  mov     [rsp+88h+var_20], r9
0x180001395  mov     rcx, [rax]
0x180001398  test    rcx, rcx
0x18000139b  jz      short loc_1800013B4
0x18000139d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800013a1  inc     rax
0x1800013a4  cmp     [rcx+rax*2], r8w
0x1800013a9  jnz     short loc_1800013A1
0x1800013ab  lea     eax, ds:2[rax*2]
0x1800013b2  jmp     short loc_1800013C0
0x1800013b4  lea     rcx, dword_180022F6C
0x1800013bb  mov     eax, 2
0x1800013c0  mov     [rsp+88h+var_30], eax
0x1800013c4  lea     rax, [rsp+88h+var_58]
0x1800013c9  mov     [rsp+88h+var_60], rax
0x1800013ce  mov     [rsp+88h+var_68], r9d
0x1800013d3  xor     r9d, r9d
0x1800013d6  mov     [rsp+88h+var_38], rcx
0x1800013db  lea     rcx, dword_18002B000
0x1800013e2  mov     [rsp+88h+var_2C], r8d
0x1800013e7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013ec  mov     rcx, [rsp+88h+var_18]
0x1800013f1  xor     rcx, rsp; StackCookie
0x1800013f4  call    __security_check_cookie
0x1800013f9  add     rsp, 88h
0x180001400  retn
```
