# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001988`
- end: `0x180001ab8`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4@Z`
- size: `304`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800185f8`

## callees

- `0x1800018e8`
- `0x180001988`
- `0x180002c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9)
{
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax

  v10 = -1;
  if ( *a9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(*a9 + v11) );
  }
  if ( *a6 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(*a6 + 2 * v12) );
  }
  if ( *a5 )
  {
    do
      ++v10;
    while ( *(_WORD *)(*a5 + 2 * v10) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x180001988  push    rbp
0x18000198a  lea     rbp, [rsp-27h]
0x18000198f  sub     rsp, 0C0h
0x180001996  mov     rax, cs:__security_cookie
0x18000199d  xor     rax, rsp
0x1800019a0  mov     [rbp+27h+var_10], rax
0x1800019a4  mov     rax, [rbp+27h+arg_48]
0x1800019a8  mov     r11, rdx
0x1800019ab  mov     [rbp+27h+var_20], rax
0x1800019af  mov     r10, rcx
0x1800019b2  mov     rax, [rbp+27h+arg_40]
0x1800019b6  xor     r9d, r9d
0x1800019b9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800019bd  mov     [rbp+27h+var_18], 8
0x1800019c5  mov     rdx, [rax]
0x1800019c8  test    rdx, rdx
0x1800019cb  jz      short loc_1800019DD
0x1800019cd  mov     rax, rcx
0x1800019d0  inc     rax
0x1800019d3  cmp     [rdx+rax], r9b
0x1800019d7  jnz     short loc_1800019D0
0x1800019d9  inc     eax
0x1800019db  jmp     short loc_1800019E9
0x1800019dd  lea     rdx, byte_18001E1D0
0x1800019e4  mov     eax, 1
0x1800019e9  mov     [rbp+27h+var_28], eax
0x1800019ec  mov     r8d, 2
0x1800019f2  mov     rax, [rbp+27h+arg_38]
0x1800019f6  mov     [rbp+27h+var_40], rax
0x1800019fa  mov     rax, [rbp+27h+arg_30]
0x1800019fe  mov     [rbp+27h+var_50], rax
0x180001a02  mov     rax, [rbp+27h+arg_28]
0x180001a06  mov     [rbp+27h+var_30], rdx
0x180001a0a  mov     [rbp+27h+var_24], r9d
0x180001a0e  mov     [rbp+27h+var_38], 4
0x180001a16  mov     rdx, [rax]
0x180001a19  mov     [rbp+27h+var_48], 8
0x180001a21  test    rdx, rdx
0x180001a24  jz      short loc_180001A3C
0x180001a26  mov     rax, rcx
0x180001a29  inc     rax
0x180001a2c  cmp     [rdx+rax*2], r9w
0x180001a31  jnz     short loc_180001A29
0x180001a33  lea     eax, ds:2[rax*2]
0x180001a3a  jmp     short loc_180001A46
0x180001a3c  lea     rdx, dword_18001E1D4
0x180001a43  mov     eax, r8d
0x180001a46  mov     [rbp+27h+var_58], eax
0x180001a49  mov     rax, [rbp+27h+arg_20]
0x180001a4d  mov     [rbp+27h+var_60], rdx
0x180001a51  mov     [rbp+27h+var_54], r9d
0x180001a55  mov     rdx, [rax]
0x180001a58  test    rdx, rdx
0x180001a5b  jz      short loc_180001A71
0x180001a5d  inc     rcx
0x180001a60  cmp     [rdx+rcx*2], r9w
0x180001a65  jnz     short loc_180001A5D
0x180001a67  lea     r8d, ds:2[rcx*2]
0x180001a6f  jmp     short loc_180001A78
0x180001a71  lea     rdx, dword_18001E1D4
0x180001a78  lea     rax, [rbp+27h+var_90]
0x180001a7c  mov     [rbp+27h+var_70], rdx
0x180001a80  mov     [rbp+27h+var_68], r8d
0x180001a84  mov     rdx, r11
0x180001a87  mov     [rsp+0C0h+var_98], rax
0x180001a8c  xor     r8d, r8d
0x180001a8f  mov     rcx, r10
0x180001a92  mov     [rsp+0C0h+var_A0], 8
0x180001a9a  mov     [rbp+27h+var_64], r9d
0x180001a9e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001aa3  mov     rcx, [rbp+27h+var_10]
0x180001aa7  xor     rcx, rsp; StackCookie
0x180001aaa  call    __security_check_cookie
0x180001aaf  add     rsp, 0C0h
0x180001ab6  pop     rbp
0x180001ab7  retn
```
