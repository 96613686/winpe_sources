# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800016a8`
- end: `0x1800017f0`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@444AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@6@Z`
- size: `328`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000881c`
- `0x18000dad0`
- `0x18000e070`

## callees

- `0x1800011d0`
- `0x1800016a8`
- `0x180001e20`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        _QWORD *a12)
{
  __int64 v13; // rdx
  __int64 v14; // rax

  v13 = -1;
  if ( *a12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(*a12 + 2 * v14) );
  }
  if ( *a5 )
  {
    do
      ++v13;
    while ( *(_BYTE *)(*a5 + v13) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001D000, a2, 0);
}

```

## disassembly

```asm
0x1800016a8  push    rbp
0x1800016aa  lea     rbp, [rsp-0Fh]
0x1800016af  sub     rsp, 0F0h
0x1800016b6  mov     rax, cs:__security_cookie
0x1800016bd  xor     rax, rsp
0x1800016c0  mov     [rbp+0Fh+var_10], rax
0x1800016c4  mov     rax, [rbp+0Fh+arg_60]
0x1800016c8  mov     r10, rdx
0x1800016cb  mov     [rbp+0Fh+var_20], rax
0x1800016cf  xor     r9d, r9d
0x1800016d2  mov     rax, [rbp+0Fh+arg_58]
0x1800016d6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800016da  mov     [rbp+0Fh+var_18], 4
0x1800016e2  mov     rcx, [rax]
0x1800016e5  test    rcx, rcx
0x1800016e8  jz      short loc_180001700
0x1800016ea  mov     rax, rdx
0x1800016ed  inc     rax
0x1800016f0  cmp     [rcx+rax*2], r9w
0x1800016f5  jnz     short loc_1800016ED
0x1800016f7  lea     eax, ds:2[rax*2]
0x1800016fe  jmp     short loc_18000170C
0x180001700  lea     rcx, byte_180017140
0x180001707  mov     eax, 2
0x18000170c  mov     [rbp+0Fh+var_28], eax
0x18000170f  mov     rax, [rbp+0Fh+arg_50]
0x180001713  mov     [rbp+0Fh+var_40], rax
0x180001717  mov     rax, [rbp+0Fh+arg_48]
0x18000171b  mov     [rbp+0Fh+var_50], rax
0x18000171f  mov     rax, [rbp+0Fh+arg_40]
0x180001723  mov     [rbp+0Fh+var_30], rcx
0x180001727  mov     [rbp+0Fh+var_24], r9d
0x18000172b  mov     [rbp+0Fh+var_38], 4
0x180001733  mov     rcx, [rax]
0x180001736  mov     rax, [rbp+0Fh+arg_38]
0x18000173a  mov     [rbp+0Fh+var_60], rcx
0x18000173e  mov     [rbp+0Fh+var_48], 8
0x180001746  mov     [rbp+0Fh+var_58], 10h
0x18000174e  mov     rcx, [rax]
0x180001751  mov     rax, [rbp+0Fh+arg_30]
0x180001755  mov     [rbp+0Fh+var_70], rcx
0x180001759  mov     [rbp+0Fh+var_68], 10h
0x180001761  mov     [rbp+0Fh+var_78], 10h
0x180001769  mov     rcx, [rax]
0x18000176c  mov     rax, [rbp+0Fh+arg_28]
0x180001770  mov     [rbp+0Fh+var_80], rcx
0x180001774  mov     [rbp+0Fh+var_88], 10h
0x18000177c  mov     rcx, [rax]
0x18000177f  mov     rax, [rbp+0Fh+arg_20]
0x180001783  mov     [rsp+0F0h+var_90], rcx
0x180001788  mov     rcx, [rax]
0x18000178b  test    rcx, rcx
0x18000178e  jz      short loc_18000179D
0x180001790  inc     rdx
0x180001793  cmp     [rcx+rdx], r9b
0x180001797  jnz     short loc_180001790
0x180001799  inc     edx
0x18000179b  jmp     short loc_1800017A9
0x18000179d  lea     rcx, qword_1800150F8
0x1800017a4  mov     edx, 1
0x1800017a9  lea     rax, [rsp+0F0h+var_C0]
0x1800017ae  mov     [rsp+0F0h+var_A0], rcx
0x1800017b3  mov     [rsp+0F0h+var_98], edx
0x1800017b7  lea     rcx, dword_18001D000
0x1800017be  mov     [rsp+0F0h+var_C8], rax
0x1800017c3  xor     r8d, r8d
0x1800017c6  mov     rdx, r10
0x1800017c9  mov     [rsp+0F0h+var_D0], 0Bh
0x1800017d1  mov     [rsp+0F0h+var_94], r9d
0x1800017d6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800017db  mov     rcx, [rbp+0Fh+var_10]
0x1800017df  xor     rcx, rsp; StackCookie
0x1800017e2  call    __security_check_cookie
0x1800017e7  add     rsp, 0F0h
0x1800017ee  pop     rbp
0x1800017ef  retn
```
