# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001b84`
- end: `0x180001c6f`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `235`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018ca4`

## callees

- `0x1800018e8`
- `0x180001b84`
- `0x180002c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v7; // rcx
  __int64 v8; // rax

  v7 = -1;
  if ( *a6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(*a6 + 2 * v8) );
  }
  if ( *a5 )
  {
    do
      ++v7;
    while ( *(_WORD *)(*a5 + 2 * v7) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x180001b84  push    rbp
0x180001b86  lea     rbp, [rsp-37h]
0x180001b8b  sub     rsp, 0A0h
0x180001b92  mov     rax, cs:__security_cookie
0x180001b99  xor     rax, rsp
0x180001b9c  mov     [rbp+37h+var_10], rax
0x180001ba0  mov     rax, [rbp+37h+arg_38]
0x180001ba4  xor     r9d, r9d
0x180001ba7  mov     [rbp+37h+var_20], rax
0x180001bab  mov     r11, rdx
0x180001bae  mov     rax, [rbp+37h+arg_30]
0x180001bb2  mov     r10, rcx
0x180001bb5  mov     [rbp+37h+var_30], rax
0x180001bb9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001bbd  mov     rax, [rbp+37h+arg_28]
0x180001bc1  lea     r8d, [r9+2]
0x180001bc5  mov     [rbp+37h+var_18], 8
0x180001bcd  mov     [rbp+37h+var_28], 8
0x180001bd5  mov     rdx, [rax]
0x180001bd8  test    rdx, rdx
0x180001bdb  jz      short loc_180001BF3
0x180001bdd  mov     rax, rcx
0x180001be0  inc     rax
0x180001be3  cmp     [rdx+rax*2], r9w
0x180001be8  jnz     short loc_180001BE0
0x180001bea  lea     eax, ds:2[rax*2]
0x180001bf1  jmp     short loc_180001BFD
0x180001bf3  lea     rdx, dword_18001E1D4
0x180001bfa  mov     eax, r8d
0x180001bfd  mov     [rbp+37h+var_38], eax
0x180001c00  mov     rax, [rbp+37h+arg_20]
0x180001c04  mov     [rbp+37h+var_40], rdx
0x180001c08  mov     [rbp+37h+var_34], r9d
0x180001c0c  mov     rdx, [rax]
0x180001c0f  test    rdx, rdx
0x180001c12  jz      short loc_180001C28
0x180001c14  inc     rcx
0x180001c17  cmp     [rdx+rcx*2], r9w
0x180001c1c  jnz     short loc_180001C14
0x180001c1e  lea     r8d, ds:2[rcx*2]
0x180001c26  jmp     short loc_180001C2F
0x180001c28  lea     rdx, dword_18001E1D4
0x180001c2f  lea     rax, [rbp+37h+var_70]
0x180001c33  mov     [rbp+37h+var_50], rdx
0x180001c37  mov     [rbp+37h+var_48], r8d
0x180001c3b  mov     rdx, r11
0x180001c3e  mov     [rsp+0A0h+var_78], rax
0x180001c43  xor     r8d, r8d
0x180001c46  mov     rcx, r10
0x180001c49  mov     [rsp+0A0h+var_80], 6
0x180001c51  mov     [rbp+37h+var_44], r9d
0x180001c55  call    _tlgWriteTransfer_EventWriteTransfer
0x180001c5a  mov     rcx, [rbp+37h+var_10]
0x180001c5e  xor     rcx, rsp; StackCookie
0x180001c61  call    __security_check_cookie
0x180001c66  add     rsp, 0A0h
0x180001c6d  pop     rbp
0x180001c6e  retn
```
