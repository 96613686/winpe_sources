# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180002440`
- end: `0x1800024e5`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e048`

## callees

- `0x180001054`
- `0x180002440`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
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
0x180002440  sub     rsp, 88h
0x180002447  mov     rax, cs:__security_cookie
0x18000244e  xor     rax, rsp
0x180002451  mov     [rsp+88h+var_18], rax
0x180002456  mov     rax, [rsp+88h+arg_28]
0x18000245e  xor     r8d, r8d
0x180002461  mov     [rsp+88h+var_28], rax
0x180002466  mov     r9d, 4
0x18000246c  mov     rax, [rsp+88h+arg_20]
0x180002474  mov     [rsp+88h+var_20], r9
0x180002479  mov     rcx, [rax]
0x18000247c  test    rcx, rcx
0x18000247f  jz      short loc_180002498
0x180002481  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002485  inc     rax
0x180002488  cmp     [rcx+rax*2], r8w
0x18000248d  jnz     short loc_180002485
0x18000248f  lea     eax, ds:2[rax*2]
0x180002496  jmp     short loc_1800024A4
0x180002498  lea     rcx, dword_1800150AC
0x18000249f  mov     eax, 2
0x1800024a4  mov     [rsp+88h+var_30], eax
0x1800024a8  lea     rax, [rsp+88h+var_58]
0x1800024ad  mov     [rsp+88h+var_60], rax
0x1800024b2  mov     [rsp+88h+var_68], r9d
0x1800024b7  xor     r9d, r9d
0x1800024ba  mov     [rsp+88h+var_38], rcx
0x1800024bf  lea     rcx, dword_18001C010
0x1800024c6  mov     [rsp+88h+var_2C], r8d
0x1800024cb  call    _tlgWriteTransfer_EventWriteTransfer
0x1800024d0  mov     rcx, [rsp+88h+var_18]
0x1800024d5  xor     rcx, rsp; StackCookie
0x1800024d8  call    __security_check_cookie
0x1800024dd  add     rsp, 88h
0x1800024e4  retn
```
