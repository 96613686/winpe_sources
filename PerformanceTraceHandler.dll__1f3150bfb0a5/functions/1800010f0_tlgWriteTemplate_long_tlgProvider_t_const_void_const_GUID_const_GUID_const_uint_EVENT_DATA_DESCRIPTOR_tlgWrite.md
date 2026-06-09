# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800010f0`
- end: `0x1800011a7`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013da8`

## callees

- `0x1800010f0`
- `0x1800018e8`
- `0x180002c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v7; // rax

  if ( *a7 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_BYTE *)(*a7 + v7) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x1800010f0  push    rbp
0x1800010f2  lea     rbp, [rsp-37h]
0x1800010f7  sub     rsp, 0A0h
0x1800010fe  mov     rax, cs:__security_cookie
0x180001105  xor     rax, rsp
0x180001108  mov     [rbp+37h+var_10], rax
0x18000110c  mov     rax, [rbp+37h+arg_38]
0x180001110  mov     r10, rcx
0x180001113  mov     [rbp+37h+var_20], rax
0x180001117  xor     r8d, r8d
0x18000111a  mov     rax, [rbp+37h+arg_30]
0x18000111e  mov     [rbp+37h+var_18], 8
0x180001126  mov     rcx, [rax]
0x180001129  test    rcx, rcx
0x18000112c  jz      short loc_18000113F
0x18000112e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001132  inc     rax
0x180001135  cmp     [rcx+rax], r8b
0x180001139  jnz     short loc_180001132
0x18000113b  inc     eax
0x18000113d  jmp     short loc_18000114B
0x18000113f  lea     rcx, byte_18001E1D0
0x180001146  mov     eax, 1
0x18000114b  mov     [rbp+37h+var_28], eax
0x18000114e  xor     r9d, r9d
0x180001151  mov     rax, [rbp+37h+arg_28]
0x180001155  mov     [rbp+37h+var_40], rax
0x180001159  mov     rax, [rbp+37h+arg_20]
0x18000115d  mov     [rbp+37h+var_50], rax
0x180001161  lea     rax, [rbp+37h+var_70]
0x180001165  mov     [rbp+37h+var_30], rcx
0x180001169  mov     rcx, r10
0x18000116c  mov     [rsp+0A0h+var_78], rax
0x180001171  mov     [rsp+0A0h+var_80], 6
0x180001179  mov     [rbp+37h+var_24], r8d
0x18000117d  mov     [rbp+37h+var_38], 4
0x180001185  mov     [rbp+37h+var_48], 4
0x18000118d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001192  mov     rcx, [rbp+37h+var_10]
0x180001196  xor     rcx, rsp; StackCookie
0x180001199  call    __security_check_cookie
0x18000119e  add     rsp, 0A0h
0x1800011a5  pop     rbp
0x1800011a6  retn
```
