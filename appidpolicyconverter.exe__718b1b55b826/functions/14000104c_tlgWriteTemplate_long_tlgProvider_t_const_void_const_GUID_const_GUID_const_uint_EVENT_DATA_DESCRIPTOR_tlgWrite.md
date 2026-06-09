# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000104c`
- end: `0x140001126`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4444@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005194`

## callees

- `0x14000104c`
- `0x1400013e8`
- `0x140013b10`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2);
}

```

## disassembly

```asm
0x14000104c  push    rbp
0x14000104e  lea     rbp, [rsp-27h]
0x140001053  sub     rsp, 0C0h
0x14000105a  mov     rax, cs:__security_cookie
0x140001061  xor     rax, rsp
0x140001064  mov     [rbp+27h+var_10], rax
0x140001068  mov     rax, [rbp+27h+arg_48]
0x14000106c  mov     r10, rcx
0x14000106f  mov     [rbp+27h+var_20], rax
0x140001073  xor     r9d, r9d
0x140001076  mov     rax, [rbp+27h+arg_40]
0x14000107a  mov     [rbp+27h+var_30], rax
0x14000107e  mov     rax, [rbp+27h+arg_38]
0x140001082  mov     [rbp+27h+var_40], rax
0x140001086  mov     rax, [rbp+27h+arg_30]
0x14000108a  mov     [rbp+27h+var_50], rax
0x14000108e  mov     rax, [rbp+27h+arg_28]
0x140001092  mov     [rbp+27h+var_60], rax
0x140001096  mov     rax, [rbp+27h+arg_20]
0x14000109a  mov     [rbp+27h+var_18], 4
0x1400010a2  mov     [rbp+27h+var_28], 4
0x1400010aa  mov     [rbp+27h+var_38], 4
0x1400010b2  mov     rcx, [rax]
0x1400010b5  mov     [rbp+27h+var_48], 4
0x1400010bd  mov     [rbp+27h+var_58], 4
0x1400010c5  test    rcx, rcx
0x1400010c8  jz      short loc_1400010E1
0x1400010ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400010ce  inc     rax
0x1400010d1  cmp     [rcx+rax*2], r9w
0x1400010d6  jnz     short loc_1400010CE
0x1400010d8  lea     eax, ds:2[rax*2]
0x1400010df  jmp     short loc_1400010ED
0x1400010e1  lea     rcx, dword_140018714
0x1400010e8  mov     eax, 2
0x1400010ed  mov     [rbp+27h+var_68], eax
0x1400010f0  lea     rax, [rbp+27h+var_90]
0x1400010f4  mov     [rbp+27h+var_70], rcx
0x1400010f8  mov     rcx, r10
0x1400010fb  mov     [rsp+0C0h+var_98], rax
0x140001100  mov     [rsp+0C0h+var_A0], 8
0x140001108  mov     [rbp+27h+var_64], r9d
0x14000110c  call    _tlgWriteTransfer_EventWriteTransfer
0x140001111  mov     rcx, [rbp+27h+var_10]
0x140001115  xor     rcx, rsp; StackCookie
0x140001118  call    __security_check_cookie
0x14000111d  add     rsp, 0C0h
0x140001124  pop     rbp
0x140001125  retn
```
