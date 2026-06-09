# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001ac0`
- end: `0x180001b7b`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800186c0`

## callees

- `0x1800018e8`
- `0x180001ac0`
- `0x180002c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6)
{
  __int64 v6; // rax

  if ( *a6 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_BYTE *)(*a6 + v6) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x180001ac0  sub     rsp, 98h
0x180001ac7  mov     rax, cs:__security_cookie
0x180001ace  xor     rax, rsp
0x180001ad1  mov     [rsp+98h+var_18], rax
0x180001ad9  mov     rax, [rsp+98h+arg_30]
0x180001ae1  mov     r10, rcx
0x180001ae4  mov     [rsp+98h+var_28], rax
0x180001ae9  xor     r8d, r8d
0x180001aec  mov     rax, [rsp+98h+arg_28]
0x180001af4  mov     [rsp+98h+var_20], 8
0x180001afd  mov     rcx, [rax]
0x180001b00  test    rcx, rcx
0x180001b03  jz      short loc_180001B16
0x180001b05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001b09  inc     rax
0x180001b0c  cmp     [rcx+rax], r8b
0x180001b10  jnz     short loc_180001B09
0x180001b12  inc     eax
0x180001b14  jmp     short loc_180001B22
0x180001b16  lea     rcx, byte_18001E1D0
0x180001b1d  mov     eax, 1
0x180001b22  mov     [rsp+98h+var_30], eax
0x180001b26  xor     r9d, r9d
0x180001b29  mov     rax, [rsp+98h+arg_20]
0x180001b31  mov     [rsp+98h+var_48], rax
0x180001b36  lea     rax, [rsp+98h+var_68]
0x180001b3b  mov     [rsp+98h+var_38], rcx
0x180001b40  mov     rcx, r10
0x180001b43  mov     [rsp+98h+var_70], rax
0x180001b48  mov     [rsp+98h+var_78], 5
0x180001b50  mov     [rsp+98h+var_2C], r8d
0x180001b55  mov     [rsp+98h+var_40], 4
0x180001b5e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001b63  mov     rcx, [rsp+98h+var_18]
0x180001b6b  xor     rcx, rsp; StackCookie
0x180001b6e  call    __security_check_cookie
0x180001b73  add     rsp, 98h
0x180001b7a  retn
```
