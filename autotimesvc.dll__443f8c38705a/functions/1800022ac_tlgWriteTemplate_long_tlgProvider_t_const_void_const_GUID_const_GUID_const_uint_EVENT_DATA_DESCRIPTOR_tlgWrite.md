# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800022ac`
- end: `0x18000236a`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000efb8`

## callees

- `0x180001054`
- `0x1800022ac`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
0x1800022ac  push    rbp
0x1800022ae  lea     rbp, [rsp-37h]
0x1800022b3  sub     rsp, 0A0h
0x1800022ba  mov     rax, cs:__security_cookie
0x1800022c1  xor     rax, rsp
0x1800022c4  mov     [rbp+37h+var_10], rax
0x1800022c8  mov     rax, [rbp+37h+arg_38]
0x1800022cc  xor     r8d, r8d
0x1800022cf  mov     [rbp+37h+var_20], rax
0x1800022d3  mov     rax, [rbp+37h+arg_30]
0x1800022d7  mov     [rbp+37h+var_30], rax
0x1800022db  mov     rax, [rbp+37h+arg_28]
0x1800022df  mov     [rbp+37h+var_40], rax
0x1800022e3  mov     rax, [rbp+37h+arg_20]
0x1800022e7  mov     [rbp+37h+var_18], 4
0x1800022ef  mov     [rbp+37h+var_28], 4
0x1800022f7  mov     [rbp+37h+var_38], 1
0x1800022ff  mov     rcx, [rax]
0x180002302  test    rcx, rcx
0x180002305  jz      short loc_18000231E
0x180002307  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000230b  inc     rax
0x18000230e  cmp     [rcx+rax*2], r8w
0x180002313  jnz     short loc_18000230B
0x180002315  lea     eax, ds:2[rax*2]
0x18000231c  jmp     short loc_18000232A
0x18000231e  lea     rcx, dword_1800150AC
0x180002325  mov     eax, 2
0x18000232a  mov     [rbp+37h+var_48], eax
0x18000232d  xor     r9d, r9d
0x180002330  lea     rax, [rbp+37h+var_70]
0x180002334  mov     [rbp+37h+var_50], rcx
0x180002338  mov     [rsp+0A0h+var_78], rax
0x18000233d  lea     rcx, dword_18001C010
0x180002344  mov     [rsp+0A0h+var_80], 6
0x18000234c  mov     [rbp+37h+var_44], r8d
0x180002350  call    _tlgWriteTransfer_EventWriteTransfer
0x180002355  mov     rcx, [rbp+37h+var_10]
0x180002359  xor     rcx, rsp; StackCookie
0x18000235c  call    __security_check_cookie
0x180002361  add     rsp, 0A0h
0x180002368  pop     rbp
0x180002369  retn
```
