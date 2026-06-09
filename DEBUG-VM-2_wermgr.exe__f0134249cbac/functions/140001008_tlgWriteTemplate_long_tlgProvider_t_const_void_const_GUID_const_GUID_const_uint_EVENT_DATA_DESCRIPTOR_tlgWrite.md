# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)

- ea: `0x140001008`
- end: `0x140001092`
- name: `??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z`
- size: `138`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b70c`
- `0x14000be08`
- `0x14000c798`

## callees

- `0x140001008`
- `0x14000162c`
- `0x140003200`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5)
{
  int *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  int *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v5 + v6) );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &dword_1400241F4;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14002C000, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x140001008  sub     rsp, 78h
0x14000100c  mov     rax, cs:__security_cookie
0x140001013  xor     rax, rsp
0x140001016  mov     [rsp+78h+var_18], rax
0x14000101b  mov     rax, [rsp+78h+arg_20]
0x140001023  xor     r8d, r8d
0x140001026  mov     rcx, [rax]
0x140001029  test    rcx, rcx
0x14000102c  jz      short loc_140001045
0x14000102e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001032  inc     rax
0x140001035  cmp     [rcx+rax*2], r8w
0x14000103a  jnz     short loc_140001032
0x14000103c  lea     eax, ds:2[rax*2]
0x140001043  jmp     short loc_140001051
0x140001045  lea     rcx, dword_1400241F4
0x14000104c  mov     eax, 2
0x140001051  mov     [rsp+78h+var_20], eax
0x140001055  xor     r9d, r9d
0x140001058  lea     rax, [rsp+78h+var_48]
0x14000105d  mov     [rsp+78h+var_28], rcx
0x140001062  mov     [rsp+78h+var_50], rax
0x140001067  lea     rcx, dword_14002C000
0x14000106e  mov     [rsp+78h+var_58], 3
0x140001076  mov     [rsp+78h+var_1C], r8d
0x14000107b  call    _tlgWriteTransfer_EventWriteTransfer
0x140001080  mov     rcx, [rsp+78h+var_18]
0x140001085  xor     rcx, rsp; StackCookie
0x140001088  call    __security_check_cookie
0x14000108d  add     rsp, 78h
0x140001091  retn
```
