# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x1800010a8`
- end: `0x180001132`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c92c`
- `0x18000c984`

## callees

- `0x180001008`
- `0x1800010a8`
- `0x18000d300`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5)
{
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v10; // [rsp+50h] [rbp-28h]
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
    v5 = &qword_18000FAB0;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180013000, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x1800010a8  sub     rsp, 78h
0x1800010ac  mov     rax, cs:__security_cookie
0x1800010b3  xor     rax, rsp
0x1800010b6  mov     [rsp+78h+var_18], rax
0x1800010bb  mov     rax, [rsp+78h+arg_20]
0x1800010c3  xor     r8d, r8d
0x1800010c6  mov     rcx, [rax]
0x1800010c9  test    rcx, rcx
0x1800010cc  jz      short loc_1800010E5
0x1800010ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800010d2  inc     rax
0x1800010d5  cmp     [rcx+rax*2], r8w
0x1800010da  jnz     short loc_1800010D2
0x1800010dc  lea     eax, ds:2[rax*2]
0x1800010e3  jmp     short loc_1800010F1
0x1800010e5  lea     rcx, qword_18000FAB0
0x1800010ec  mov     eax, 2
0x1800010f1  mov     [rsp+78h+var_20], eax
0x1800010f5  xor     r9d, r9d
0x1800010f8  lea     rax, [rsp+78h+var_48]
0x1800010fd  mov     [rsp+78h+var_28], rcx
0x180001102  mov     [rsp+78h+var_50], rax
0x180001107  lea     rcx, dword_180013000
0x18000110e  mov     [rsp+78h+var_58], 3
0x180001116  mov     [rsp+78h+var_1C], r8d
0x18000111b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001120  mov     rcx, [rsp+78h+var_18]
0x180001125  xor     rcx, rsp; StackCookie
0x180001128  call    __security_check_cookie
0x18000112d  add     rsp, 78h
0x180001131  retn
```
