# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001c78`
- end: `0x180001d73`
- name: `??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$07@@5@Z`
- size: `251`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018d58`

## callees

- `0x1800018e8`
- `0x180001c78`
- `0x180002c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _QWORD *a7)
{
  __int64 v8; // rcx
  __int64 v9; // rax

  v8 = -1;
  if ( *a7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(*a7 + 2 * v9) );
  }
  if ( *a6 )
  {
    do
      ++v8;
    while ( *(_WORD *)(*a6 + 2 * v8) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x180001c78  push    rbp
0x180001c7a  lea     rbp, [rsp-2Fh]
0x180001c7f  sub     rsp, 0B0h
0x180001c86  mov     rax, cs:__security_cookie
0x180001c8d  xor     rax, rsp
0x180001c90  mov     [rbp+2Fh+var_10], rax
0x180001c94  mov     rax, [rbp+2Fh+arg_40]
0x180001c98  xor     r9d, r9d
0x180001c9b  mov     [rbp+2Fh+var_20], rax
0x180001c9f  mov     r11, rdx
0x180001ca2  mov     rax, [rbp+2Fh+arg_38]
0x180001ca6  mov     r10, rcx
0x180001ca9  mov     [rbp+2Fh+var_30], rax
0x180001cad  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001cb1  mov     rax, [rbp+2Fh+arg_30]
0x180001cb5  lea     r8d, [r9+2]
0x180001cb9  mov     [rbp+2Fh+var_18], 8
0x180001cc1  mov     [rbp+2Fh+var_28], 8
0x180001cc9  mov     rdx, [rax]
0x180001ccc  test    rdx, rdx
0x180001ccf  jz      short loc_180001CE7
0x180001cd1  mov     rax, rcx
0x180001cd4  inc     rax
0x180001cd7  cmp     [rdx+rax*2], r9w
0x180001cdc  jnz     short loc_180001CD4
0x180001cde  lea     eax, ds:2[rax*2]
0x180001ce5  jmp     short loc_180001CF1
0x180001ce7  lea     rdx, dword_18001E1D4
0x180001cee  mov     eax, r8d
0x180001cf1  mov     [rbp+2Fh+var_38], eax
0x180001cf4  mov     rax, [rbp+2Fh+arg_28]
0x180001cf8  mov     [rbp+2Fh+var_40], rdx
0x180001cfc  mov     [rbp+2Fh+var_34], r9d
0x180001d00  mov     rdx, [rax]
0x180001d03  test    rdx, rdx
0x180001d06  jz      short loc_180001D1C
0x180001d08  inc     rcx
0x180001d0b  cmp     [rdx+rcx*2], r9w
0x180001d10  jnz     short loc_180001D08
0x180001d12  lea     r8d, ds:2[rcx*2]
0x180001d1a  jmp     short loc_180001D23
0x180001d1c  lea     rdx, dword_18001E1D4
0x180001d23  mov     rax, [rbp+2Fh+arg_20]
0x180001d27  mov     rcx, r10
0x180001d2a  mov     [rbp+2Fh+var_60], rax
0x180001d2e  lea     rax, [rbp+2Fh+var_80]
0x180001d32  mov     [rbp+2Fh+var_50], rdx
0x180001d36  mov     rdx, r11
0x180001d39  mov     [rbp+2Fh+var_48], r8d
0x180001d3d  xor     r8d, r8d
0x180001d40  mov     [rsp+0B0h+var_88], rax
0x180001d45  mov     [rsp+0B0h+var_90], 7
0x180001d4d  mov     [rbp+2Fh+var_44], r9d
0x180001d51  mov     [rbp+2Fh+var_58], 1
0x180001d59  call    _tlgWriteTransfer_EventWriteTransfer
0x180001d5e  mov     rcx, [rbp+2Fh+var_10]
0x180001d62  xor     rcx, rsp; StackCookie
0x180001d65  call    __security_check_cookie
0x180001d6a  add     rsp, 0B0h
0x180001d71  pop     rbp
0x180001d72  retn
```
