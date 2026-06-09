# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001d9c`
- end: `0x180001e73`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z`
- size: `215`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e048`

## callees

- `0x180001054`
- `0x180001d9c`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v6; // rcx
  __int64 v7; // rax

  v6 = -1;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(*a6 + 2 * v7) );
  }
  if ( *a5 )
  {
    do
      ++v6;
    while ( *(_WORD *)(*a5 + 2 * v6) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180001d9c  sub     rsp, 88h
0x180001da3  mov     rax, cs:__security_cookie
0x180001daa  xor     rax, rsp
0x180001dad  mov     [rsp+88h+var_18], rax
0x180001db2  mov     rax, [rsp+88h+arg_28]
0x180001dba  mov     r10, rdx
0x180001dbd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001dc1  xor     r9d, r9d
0x180001dc4  mov     r8d, 2
0x180001dca  mov     rdx, [rax]
0x180001dcd  test    rdx, rdx
0x180001dd0  jz      short loc_180001DE8
0x180001dd2  mov     rax, rcx
0x180001dd5  inc     rax
0x180001dd8  cmp     [rdx+rax*2], r9w
0x180001ddd  jnz     short loc_180001DD5
0x180001ddf  lea     eax, ds:2[rax*2]
0x180001de6  jmp     short loc_180001DF2
0x180001de8  lea     rdx, dword_1800150AC
0x180001def  mov     eax, r8d
0x180001df2  mov     [rsp+88h+var_20], eax
0x180001df6  mov     rax, [rsp+88h+arg_20]
0x180001dfe  mov     [rsp+88h+var_28], rdx
0x180001e03  mov     [rsp+88h+var_1C], r9d
0x180001e08  mov     rdx, [rax]
0x180001e0b  test    rdx, rdx
0x180001e0e  jz      short loc_180001E24
0x180001e10  inc     rcx
0x180001e13  cmp     [rdx+rcx*2], r9w
0x180001e18  jnz     short loc_180001E10
0x180001e1a  lea     r8d, ds:2[rcx*2]
0x180001e22  jmp     short loc_180001E2B
0x180001e24  lea     rdx, dword_1800150AC
0x180001e2b  lea     rax, [rsp+88h+var_58]
0x180001e30  mov     [rsp+88h+var_38], rdx
0x180001e35  mov     [rsp+88h+var_30], r8d
0x180001e3a  lea     rcx, dword_18001C010
0x180001e41  mov     [rsp+88h+var_60], rax
0x180001e46  xor     r8d, r8d
0x180001e49  mov     rdx, r10
0x180001e4c  mov     [rsp+88h+var_68], 4
0x180001e54  mov     [rsp+88h+var_2C], r9d
0x180001e59  call    _tlgWriteTransfer_EventWriteTransfer
0x180001e5e  mov     rcx, [rsp+88h+var_18]
0x180001e63  xor     rcx, rsp; StackCookie
0x180001e66  call    __security_check_cookie
0x180001e6b  add     rsp, 88h
0x180001e72  retn
```
