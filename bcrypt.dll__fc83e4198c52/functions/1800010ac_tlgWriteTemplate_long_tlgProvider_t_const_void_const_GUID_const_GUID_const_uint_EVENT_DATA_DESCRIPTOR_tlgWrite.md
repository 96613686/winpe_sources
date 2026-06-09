# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x1800010ac`
- end: `0x180001137`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180019500`
- `0x180019920`

## callees

- `0x180001008`
- `0x1800010ac`
- `0x18001b7e0`

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
    v5 = &dword_18001E7A4;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180024050, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x1800010ac  sub     rsp, 78h
0x1800010b0  mov     rax, cs:__security_cookie
0x1800010b7  xor     rax, rsp
0x1800010ba  mov     [rsp+78h+var_18], rax
0x1800010bf  mov     rax, [rsp+78h+arg_20]
0x1800010c7  xor     r8d, r8d
0x1800010ca  mov     rcx, [rax]
0x1800010cd  test    rcx, rcx
0x1800010d0  jz      short loc_1800010E9
0x1800010d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800010d6  inc     rax
0x1800010d9  cmp     [rcx+rax*2], r8w
0x1800010de  jnz     short loc_1800010D6
0x1800010e0  lea     eax, ds:2[rax*2]
0x1800010e7  jmp     short loc_1800010F5
0x1800010e9  lea     rcx, dword_18001E7A4
0x1800010f0  mov     eax, 2
0x1800010f5  mov     [rsp+78h+var_20], eax
0x1800010f9  xor     r9d, r9d
0x1800010fc  lea     rax, [rsp+78h+var_48]
0x180001101  mov     [rsp+78h+var_28], rcx
0x180001106  mov     [rsp+78h+var_50], rax
0x18000110b  lea     rcx, dword_180024050
0x180001112  mov     [rsp+78h+var_58], 3
0x18000111a  mov     [rsp+78h+var_1C], r8d
0x18000111f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001124  mov     rcx, [rsp+78h+var_18]
0x180001129  xor     rcx, rsp; StackCookie
0x18000112c  call    __security_check_cookie
0x180001131  add     rsp, 78h
0x180001135  retn
```
