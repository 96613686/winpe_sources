# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)

- ea: `0x180001f74`
- end: `0x18000201a`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e6f8`

## callees

- `0x180001054`
- `0x180001f74`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v5; // rax

  if ( *a5 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(*a5 + 2 * v5) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180001f74  sub     rsp, 88h
0x180001f7b  mov     rax, cs:__security_cookie
0x180001f82  xor     rax, rsp
0x180001f85  mov     [rsp+88h+var_18], rax
0x180001f8a  mov     rax, [rsp+88h+arg_28]
0x180001f92  xor     r8d, r8d
0x180001f95  mov     [rsp+88h+var_28], rax
0x180001f9a  mov     rax, [rsp+88h+arg_20]
0x180001fa2  mov     [rsp+88h+var_20], 1
0x180001fab  mov     rcx, [rax]
0x180001fae  test    rcx, rcx
0x180001fb1  jz      short loc_180001FCA
0x180001fb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001fb7  inc     rax
0x180001fba  cmp     [rcx+rax*2], r8w
0x180001fbf  jnz     short loc_180001FB7
0x180001fc1  lea     eax, ds:2[rax*2]
0x180001fc8  jmp     short loc_180001FD6
0x180001fca  lea     rcx, dword_1800150AC
0x180001fd1  mov     eax, 2
0x180001fd6  mov     [rsp+88h+var_30], eax
0x180001fda  xor     r9d, r9d
0x180001fdd  lea     rax, [rsp+88h+var_58]
0x180001fe2  mov     [rsp+88h+var_38], rcx
0x180001fe7  mov     [rsp+88h+var_60], rax
0x180001fec  lea     rcx, dword_18001C010
0x180001ff3  mov     [rsp+88h+var_68], 4
0x180001ffb  mov     [rsp+88h+var_2C], r8d
0x180002000  call    _tlgWriteTransfer_EventWriteTransfer
0x180002005  mov     rcx, [rsp+88h+var_18]
0x18000200a  xor     rcx, rsp; StackCookie
0x18000200d  call    __security_check_cookie
0x180002012  add     rsp, 88h
0x180002019  retn
```
