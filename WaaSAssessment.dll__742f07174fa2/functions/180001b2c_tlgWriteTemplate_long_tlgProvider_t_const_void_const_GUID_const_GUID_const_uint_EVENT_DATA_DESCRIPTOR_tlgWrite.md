# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x180001b2c`
- end: `0x180001bb6`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `138`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180017f34`
- `0x180017fd0`
- `0x180018008`
- `0x180018040`

## callees

- `0x180001a8c`
- `0x180001b2c`
- `0x180019760`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
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
    v5 = &dword_18001D62C;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180027080, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x180001b2c  sub     rsp, 78h
0x180001b30  mov     rax, cs:__security_cookie
0x180001b37  xor     rax, rsp
0x180001b3a  mov     [rsp+78h+var_18], rax
0x180001b3f  mov     rax, [rsp+78h+arg_20]
0x180001b47  xor     r8d, r8d
0x180001b4a  mov     rcx, [rax]
0x180001b4d  test    rcx, rcx
0x180001b50  jz      short loc_180001B69
0x180001b52  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001b56  inc     rax
0x180001b59  cmp     [rcx+rax*2], r8w
0x180001b5e  jnz     short loc_180001B56
0x180001b60  lea     eax, ds:2[rax*2]
0x180001b67  jmp     short loc_180001B75
0x180001b69  lea     rcx, dword_18001D62C
0x180001b70  mov     eax, 2
0x180001b75  mov     [rsp+78h+var_20], eax
0x180001b79  xor     r9d, r9d
0x180001b7c  lea     rax, [rsp+78h+var_48]
0x180001b81  mov     [rsp+78h+var_28], rcx
0x180001b86  mov     [rsp+78h+var_50], rax
0x180001b8b  lea     rcx, dword_180027080
0x180001b92  mov     [rsp+78h+var_58], 3
0x180001b9a  mov     [rsp+78h+var_1C], r8d
0x180001b9f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001ba4  mov     rcx, [rsp+78h+var_18]
0x180001ba9  xor     rcx, rsp; StackCookie
0x180001bac  call    __security_check_cookie
0x180001bb1  add     rsp, 78h
0x180001bb5  retn
```
