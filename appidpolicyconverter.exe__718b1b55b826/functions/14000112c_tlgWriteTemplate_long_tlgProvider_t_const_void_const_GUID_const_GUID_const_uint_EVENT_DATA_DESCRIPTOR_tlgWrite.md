# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000112c`
- end: `0x14000120f`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@355@Z`
- size: `227`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140003330`

## callees

- `0x14000112c`
- `0x1400013e8`
- `0x140013b10`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
    while ( *(_WORD *)(*a6 + 2 * v6) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2);
}

```

## disassembly

```asm
0x14000112c  push    rbp
0x14000112e  lea     rbp, [rsp-27h]
0x140001133  sub     rsp, 0C0h
0x14000113a  mov     rax, cs:__security_cookie
0x140001141  xor     rax, rsp
0x140001144  mov     [rbp+27h+var_10], rax
0x140001148  mov     rax, [rbp+27h+arg_48]
0x14000114c  mov     r10, rcx
0x14000114f  mov     [rbp+27h+var_20], rax
0x140001153  xor     r11d, r11d
0x140001156  mov     rax, [rbp+27h+arg_40]
0x14000115a  mov     [rbp+27h+var_30], rax
0x14000115e  mov     rax, [rbp+27h+arg_38]
0x140001162  mov     [rbp+27h+var_18], 4
0x14000116a  mov     [rbp+27h+var_28], 4
0x140001172  mov     [rbp+27h+var_38], 10h
0x14000117a  mov     rcx, [rax]
0x14000117d  mov     rax, [rbp+27h+arg_30]
0x140001181  mov     [rbp+27h+var_50], rax
0x140001185  mov     rax, [rbp+27h+arg_28]
0x140001189  mov     [rbp+27h+var_40], rcx
0x14000118d  mov     [rbp+27h+var_48], 4
0x140001195  mov     rcx, [rax]
0x140001198  test    rcx, rcx
0x14000119b  jz      short loc_1400011B4
0x14000119d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400011a1  inc     rax
0x1400011a4  cmp     [rcx+rax*2], r11w
0x1400011a9  jnz     short loc_1400011A1
0x1400011ab  lea     eax, ds:2[rax*2]
0x1400011b2  jmp     short loc_1400011C0
0x1400011b4  lea     rcx, dword_140018714
0x1400011bb  mov     eax, 2
0x1400011c0  mov     [rbp+27h+var_58], eax
0x1400011c3  mov     rax, [rbp+27h+arg_20]
0x1400011c7  mov     [rbp+27h+var_60], rcx
0x1400011cb  mov     rcx, r10
0x1400011ce  mov     [rbp+27h+var_54], r11d
0x1400011d2  mov     [rbp+27h+var_68], 10h
0x1400011da  mov     r9, [rax]
0x1400011dd  lea     rax, [rbp+27h+var_90]
0x1400011e1  mov     [rbp+27h+var_70], r9
0x1400011e5  xor     r9d, r9d
0x1400011e8  mov     [rsp+0C0h+var_98], rax
0x1400011ed  mov     [rsp+0C0h+var_A0], 8
0x1400011f5  call    _tlgWriteTransfer_EventWriteTransfer
0x1400011fa  mov     rcx, [rbp+27h+var_10]
0x1400011fe  xor     rcx, rsp; StackCookie
0x140001201  call    __security_check_cookie
0x140001206  add     rsp, 0C0h
0x14000120d  pop     rbp
0x14000120e  retn
```
