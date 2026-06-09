# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)

- ea: `0x1400011dc`
- end: `0x140001266`
- name: `??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cfc4`

## callees

- `0x14000113c`
- `0x1400011dc`
- `0x1400023d0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        void **a5)
{
  _WORD *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-48h] BYREF
  _WORD *v10; // [rsp+50h] [rbp-28h]
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
    v5 = &unk_140014A6C;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14001A000, a2, 0, 0, 3u, &v9);
}

```

## disassembly

```asm
0x1400011dc  sub     rsp, 78h
0x1400011e0  mov     rax, cs:__security_cookie
0x1400011e7  xor     rax, rsp
0x1400011ea  mov     [rsp+78h+var_18], rax
0x1400011ef  mov     rax, [rsp+78h+arg_20]
0x1400011f7  xor     r8d, r8d
0x1400011fa  mov     rcx, [rax]
0x1400011fd  test    rcx, rcx
0x140001200  jz      short loc_140001219
0x140001202  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001206  inc     rax
0x140001209  cmp     [rcx+rax*2], r8w
0x14000120e  jnz     short loc_140001206
0x140001210  lea     eax, ds:2[rax*2]
0x140001217  jmp     short loc_140001225
0x140001219  lea     rcx, unk_140014A6C
0x140001220  mov     eax, 2
0x140001225  mov     [rsp+78h+var_20], eax
0x140001229  xor     r9d, r9d
0x14000122c  lea     rax, [rsp+78h+var_48]
0x140001231  mov     [rsp+78h+var_28], rcx
0x140001236  mov     [rsp+78h+var_50], rax
0x14000123b  lea     rcx, dword_14001A000
0x140001242  mov     [rsp+78h+var_58], 3
0x14000124a  mov     [rsp+78h+var_1C], r8d
0x14000124f  call    _tlgWriteTransfer_EventWriteTransfer
0x140001254  mov     rcx, [rsp+78h+var_18]
0x140001259  xor     rcx, rsp; StackCookie
0x14000125c  call    __security_check_cookie
0x140001261  add     rsp, 78h
0x140001265  retn
```
