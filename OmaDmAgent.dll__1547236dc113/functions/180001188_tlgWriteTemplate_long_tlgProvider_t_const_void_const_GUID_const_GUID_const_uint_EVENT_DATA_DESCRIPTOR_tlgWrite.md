# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x180001188`
- end: `0x180001213`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004950`

## callees

- `0x180001188`
- `0x1800012b8`
- `0x18001f420`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5)
{
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &dword_180022F6C;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002B000, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x180001188  sub     rsp, 78h
0x18000118c  mov     rax, cs:__security_cookie
0x180001193  xor     rax, rsp
0x180001196  mov     [rsp+78h+var_18], rax
0x18000119b  mov     rax, [rsp+78h+arg_20]
0x1800011a3  xor     r8d, r8d
0x1800011a6  mov     rcx, [rax]
0x1800011a9  test    rcx, rcx
0x1800011ac  jz      short loc_1800011C5
0x1800011ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011b2  inc     rax
0x1800011b5  cmp     [rcx+rax*2], r8w
0x1800011ba  jnz     short loc_1800011B2
0x1800011bc  lea     eax, ds:2[rax*2]
0x1800011c3  jmp     short loc_1800011D1
0x1800011c5  lea     rcx, dword_180022F6C
0x1800011cc  mov     eax, 2
0x1800011d1  mov     [rsp+78h+var_20], eax
0x1800011d5  xor     r9d, r9d
0x1800011d8  lea     rax, [rsp+78h+var_48]
0x1800011dd  mov     [rsp+78h+var_28], rcx
0x1800011e2  mov     [rsp+78h+var_50], rax
0x1800011e7  lea     rcx, dword_18002B000
0x1800011ee  mov     [rsp+78h+var_58], 3
0x1800011f6  mov     [rsp+78h+var_1C], r8d
0x1800011fb  call    _tlgWriteTransfer_EventWriteTransfer
0x180001200  mov     rcx, [rsp+78h+var_18]
0x180001205  xor     rcx, rsp; StackCookie
0x180001208  call    __security_check_cookie
0x18000120d  add     rsp, 78h
0x180001211  retn
```
