# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001424`
- end: `0x1400014c9`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b250`
- `0x14000b454`
- `0x14000ca40`
- `0x14000cd30`

## callees

- `0x140001130`
- `0x140001424`
- `0x14000ded0`

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
  return tlgWriteTransfer_EventWriteTransfer(&dword_140017048, a2, 0, 0);
}

```

## disassembly

```asm
0x140001424  sub     rsp, 88h
0x14000142b  mov     rax, cs:__security_cookie
0x140001432  xor     rax, rsp
0x140001435  mov     [rsp+88h+var_18], rax
0x14000143a  mov     rax, [rsp+88h+arg_28]
0x140001442  xor     r8d, r8d
0x140001445  mov     [rsp+88h+var_28], rax
0x14000144a  mov     r9d, 4
0x140001450  mov     rax, [rsp+88h+arg_20]
0x140001458  mov     [rsp+88h+var_20], r9
0x14000145d  mov     rcx, [rax]
0x140001460  test    rcx, rcx
0x140001463  jz      short loc_14000147C
0x140001465  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001469  inc     rax
0x14000146c  cmp     [rcx+rax*2], r8w
0x140001471  jnz     short loc_140001469
0x140001473  lea     eax, ds:2[rax*2]
0x14000147a  jmp     short loc_140001488
0x14000147c  lea     rcx, qword_140011EC0
0x140001483  mov     eax, 2
0x140001488  mov     [rsp+88h+var_30], eax
0x14000148c  lea     rax, [rsp+88h+var_58]
0x140001491  mov     [rsp+88h+var_60], rax
0x140001496  mov     [rsp+88h+var_68], r9d
0x14000149b  xor     r9d, r9d
0x14000149e  mov     [rsp+88h+var_38], rcx
0x1400014a3  lea     rcx, dword_140017048
0x1400014aa  mov     [rsp+88h+var_2C], r8d
0x1400014af  call    _tlgWriteTransfer_EventWriteTransfer
0x1400014b4  mov     rcx, [rsp+88h+var_18]
0x1400014b9  xor     rcx, rsp; StackCookie
0x1400014bc  call    __security_check_cookie
0x1400014c1  add     rsp, 88h
0x1400014c8  retn
```
