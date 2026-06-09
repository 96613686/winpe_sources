# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001184`
- end: `0x18000123c`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800028d4`
- `0x180002a54`

## callees

- `0x180001184`
- `0x180001244`
- `0x180001730`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
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
  return tlgWriteTransfer_EventWriteTransfer(&dword_180007000, a2, 0);
}

```

## disassembly

```asm
0x180001184  push    rbp
0x180001186  lea     rbp, [rsp-37h]
0x18000118b  sub     rsp, 0A0h
0x180001192  mov     rax, cs:__security_cookie
0x180001199  xor     rax, rsp
0x18000119c  mov     [rbp+37h+var_10], rax
0x1800011a0  mov     rax, [rbp+37h+arg_38]
0x1800011a4  xor     r8d, r8d
0x1800011a7  mov     [rbp+37h+var_20], rax
0x1800011ab  mov     rax, [rbp+37h+arg_30]
0x1800011af  mov     [rbp+37h+var_30], rax
0x1800011b3  mov     rax, [rbp+37h+arg_28]
0x1800011b7  mov     [rbp+37h+var_18], 8
0x1800011bf  mov     [rbp+37h+var_28], 4
0x1800011c7  mov     rcx, [rax]
0x1800011ca  test    rcx, rcx
0x1800011cd  jz      short loc_1800011E0
0x1800011cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011d3  inc     rax
0x1800011d6  cmp     [rcx+rax], r8b
0x1800011da  jnz     short loc_1800011D3
0x1800011dc  inc     eax
0x1800011de  jmp     short loc_1800011EC
0x1800011e0  lea     rcx, word_18000563E
0x1800011e7  mov     eax, 1
0x1800011ec  mov     [rbp+37h+var_38], eax
0x1800011ef  xor     r9d, r9d
0x1800011f2  mov     rax, [rbp+37h+arg_20]
0x1800011f6  mov     [rbp+37h+var_50], rax
0x1800011fa  lea     rax, [rbp+37h+var_70]
0x1800011fe  mov     [rbp+37h+var_40], rcx
0x180001202  lea     rcx, dword_180007000
0x180001209  mov     [rsp+0A0h+var_78], rax
0x18000120e  mov     [rsp+0A0h+var_80], 6
0x180001216  mov     [rbp+37h+var_34], r8d
0x18000121a  mov     [rbp+37h+var_48], 4
0x180001222  call    _tlgWriteTransfer_EventWriteTransfer
0x180001227  mov     rcx, [rbp+37h+var_10]
0x18000122b  xor     rcx, rsp; StackCookie
0x18000122e  call    __security_check_cookie
0x180001233  add     rsp, 0A0h
0x18000123a  pop     rbp
0x18000123b  retn
```
