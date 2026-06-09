# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001008`
- end: `0x1800010e8`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180013ed8`
- `0x180013f80`
- `0x180014024`
- `0x1800140cc`
- `0x180014170`
- `0x180014218`

## callees

- `0x180001008`
- `0x1800018e8`
- `0x180002c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v8; // rcx
  __int64 v9; // rax

  v8 = -1;
  if ( *a7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(*a7 + v9) );
  }
  if ( *a5 )
  {
    do
      ++v8;
    while ( *(_BYTE *)(*a5 + v8) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-37h]
0x18000100f  sub     rsp, 0A0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+37h+var_10], rax
0x180001024  mov     rax, [rbp+37h+arg_38]
0x180001028  xor     r9d, r9d
0x18000102b  mov     [rbp+37h+var_20], rax
0x18000102f  mov     r11, rdx
0x180001032  mov     rax, [rbp+37h+arg_30]
0x180001036  mov     r10, rcx
0x180001039  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000103d  mov     [rbp+37h+var_18], 8
0x180001045  lea     r8d, [r9+1]
0x180001049  mov     rdx, [rax]
0x18000104c  test    rdx, rdx
0x18000104f  jz      short loc_180001061
0x180001051  mov     rax, rcx
0x180001054  inc     rax
0x180001057  cmp     [rdx+rax], r9b
0x18000105b  jnz     short loc_180001054
0x18000105d  inc     eax
0x18000105f  jmp     short loc_18000106B
0x180001061  lea     rdx, byte_18001E1D0
0x180001068  mov     eax, r8d
0x18000106b  mov     [rbp+37h+var_28], eax
0x18000106e  mov     rax, [rbp+37h+arg_28]
0x180001072  mov     [rbp+37h+var_40], rax
0x180001076  mov     rax, [rbp+37h+arg_20]
0x18000107a  mov     [rbp+37h+var_30], rdx
0x18000107e  mov     [rbp+37h+var_24], r9d
0x180001082  mov     [rbp+37h+var_38], 4
0x18000108a  mov     rdx, [rax]
0x18000108d  test    rdx, rdx
0x180001090  jz      short loc_1800010A1
0x180001092  inc     rcx
0x180001095  cmp     [rdx+rcx], r9b
0x180001099  jnz     short loc_180001092
0x18000109b  lea     r8d, [rcx+1]
0x18000109f  jmp     short loc_1800010A8
0x1800010a1  lea     rdx, byte_18001E1D0
0x1800010a8  lea     rax, [rbp+37h+var_70]
0x1800010ac  mov     [rbp+37h+var_50], rdx
0x1800010b0  mov     [rbp+37h+var_48], r8d
0x1800010b4  mov     rdx, r11
0x1800010b7  mov     [rsp+0A0h+var_78], rax
0x1800010bc  xor     r8d, r8d
0x1800010bf  mov     rcx, r10
0x1800010c2  mov     [rsp+0A0h+var_80], 6
0x1800010ca  mov     [rbp+37h+var_44], r9d
0x1800010ce  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010d3  mov     rcx, [rbp+37h+var_10]
0x1800010d7  xor     rcx, rsp; StackCookie
0x1800010da  call    __security_check_cookie
0x1800010df  add     rsp, 0A0h
0x1800010e6  pop     rbp
0x1800010e7  retn
```
