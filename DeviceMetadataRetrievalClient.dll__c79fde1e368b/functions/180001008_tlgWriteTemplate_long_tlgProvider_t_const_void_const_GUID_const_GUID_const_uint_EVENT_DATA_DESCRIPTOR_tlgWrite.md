# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x1800012c6`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapSz@G@@U4@U4@U4@U4@U4@U?$_tlgWrapperByVal@$03@@U5@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapSz@G@@66666AEBU?$_tlgWrapperByVal@$03@@7666@Z`
- size: `702`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, __int64, __int64, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006904`

## callees

- `0x180001008`
- `0x1800012cc`
- `0x180013700`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        _QWORD *a10,
        _QWORD *a11,
        _QWORD *a12,
        _QWORD *a13,
        _QWORD *a14,
        __int64 a15,
        __int64 a16,
        _QWORD *a17,
        _QWORD *a18,
        _QWORD *a19)
{
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax

  v19 = -1;
  if ( *a19 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_WORD *)(*a19 + 2 * v20) );
  }
  if ( *a18 )
  {
    v21 = -1;
    do
      ++v21;
    while ( *(_WORD *)(*a18 + 2 * v21) );
  }
  if ( *a17 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(*a17 + 2 * v22) );
  }
  if ( *a14 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(*a14 + 2 * v23) );
  }
  if ( *a13 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(*a13 + 2 * v24) );
  }
  if ( *a12 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(*a12 + 2 * v25) );
  }
  if ( *a11 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(*a11 + 2 * v26) );
  }
  if ( *a10 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a10 + 2 * v27) );
  }
  if ( *a9 )
  {
    do
      ++v19;
    while ( *(_WORD *)(*a9 + 2 * v19) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001E2A0, a2, 0);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-50h]
0x18000100f  sub     rsp, 150h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+50h+var_10], rax
0x180001024  mov     rax, [rbp+50h+arg_90]
0x18000102b  lea     r11, dword_180017E8C
0x180001032  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001036  xor     r9d, r9d
0x180001039  mov     r10, rdx
0x18000103c  mov     edx, 2
0x180001041  mov     r8, [rax]
0x180001044  test    r8, r8
0x180001047  jz      short loc_18000105F
0x180001049  mov     rax, rcx
0x18000104c  inc     rax
0x18000104f  cmp     [r8+rax*2], r9w
0x180001054  jnz     short loc_18000104C
0x180001056  lea     eax, ds:2[rax*2]
0x18000105d  jmp     short loc_180001064
0x18000105f  mov     r8, r11
0x180001062  mov     eax, edx
0x180001064  mov     [rbp+50h+var_18], eax
0x180001067  mov     rax, [rbp+50h+arg_88]
0x18000106e  mov     [rbp+50h+var_20], r8
0x180001072  mov     [rbp+50h+var_14], r9d
0x180001076  mov     r8, [rax]
0x180001079  test    r8, r8
0x18000107c  jz      short loc_180001094
0x18000107e  mov     rax, rcx
0x180001081  inc     rax
0x180001084  cmp     [r8+rax*2], r9w
0x180001089  jnz     short loc_180001081
0x18000108b  lea     eax, ds:2[rax*2]
0x180001092  jmp     short loc_180001099
0x180001094  mov     r8, r11
0x180001097  mov     eax, edx
0x180001099  mov     [rbp+50h+var_28], eax
0x18000109c  mov     rax, [rbp+50h+arg_80]
0x1800010a3  mov     [rbp+50h+var_30], r8
0x1800010a7  mov     [rbp+50h+var_24], r9d
0x1800010ab  mov     r8, [rax]
0x1800010ae  test    r8, r8
0x1800010b1  jz      short loc_1800010C9
0x1800010b3  mov     rax, rcx
0x1800010b6  inc     rax
0x1800010b9  cmp     [r8+rax*2], r9w
0x1800010be  jnz     short loc_1800010B6
0x1800010c0  lea     eax, ds:2[rax*2]
0x1800010c7  jmp     short loc_1800010CE
0x1800010c9  mov     r8, r11
0x1800010cc  mov     eax, edx
0x1800010ce  mov     [rbp+50h+var_38], eax
0x1800010d1  mov     rax, [rbp+50h+arg_78]
0x1800010d8  mov     [rbp+50h+var_50], rax
0x1800010dc  mov     rax, [rbp+50h+arg_70]
0x1800010e3  mov     [rbp+50h+var_60], rax
0x1800010e7  mov     rax, [rbp+50h+arg_68]
0x1800010ee  mov     [rbp+50h+var_40], r8
0x1800010f2  mov     [rbp+50h+var_34], r9d
0x1800010f6  mov     [rbp+50h+var_48], 4
0x1800010fe  mov     r8, [rax]
0x180001101  mov     [rbp+50h+var_58], 4
0x180001109  test    r8, r8
0x18000110c  jz      short loc_180001124
0x18000110e  mov     rax, rcx
0x180001111  inc     rax
0x180001114  cmp     [r8+rax*2], r9w
0x180001119  jnz     short loc_180001111
0x18000111b  lea     eax, ds:2[rax*2]
0x180001122  jmp     short loc_180001129
0x180001124  mov     r8, r11
0x180001127  mov     eax, edx
0x180001129  mov     [rbp+50h+var_68], eax
0x18000112c  mov     rax, [rbp+50h+arg_60]
0x180001133  mov     [rbp+50h+var_70], r8
0x180001137  mov     [rbp+50h+var_64], r9d
0x18000113b  mov     r8, [rax]
0x18000113e  test    r8, r8
0x180001141  jz      short loc_180001159
0x180001143  mov     rax, rcx
0x180001146  inc     rax
0x180001149  cmp     [r8+rax*2], r9w
0x18000114e  jnz     short loc_180001146
0x180001150  lea     eax, ds:2[rax*2]
0x180001157  jmp     short loc_18000115E
0x180001159  mov     r8, r11
0x18000115c  mov     eax, edx
0x18000115e  mov     [rbp+50h+var_78], eax
0x180001161  mov     rax, [rbp+50h+arg_58]
0x180001168  mov     [rbp+50h+var_80], r8
0x18000116c  mov     [rbp+50h+var_74], r9d
0x180001170  mov     r8, [rax]
0x180001173  test    r8, r8
0x180001176  jz      short loc_18000118E
0x180001178  mov     rax, rcx
0x18000117b  inc     rax
0x18000117e  cmp     [r8+rax*2], r9w
0x180001183  jnz     short loc_18000117B
0x180001185  lea     eax, ds:2[rax*2]
0x18000118c  jmp     short loc_180001193
0x18000118e  mov     r8, r11
0x180001191  mov     eax, edx
0x180001193  mov     [rbp+50h+var_88], eax
0x180001196  mov     rax, [rbp+50h+arg_50]
0x18000119d  mov     [rbp+50h+var_90], r8
0x1800011a1  mov     [rbp+50h+var_84], r9d
0x1800011a5  mov     r8, [rax]
0x1800011a8  test    r8, r8
0x1800011ab  jz      short loc_1800011C3
0x1800011ad  mov     rax, rcx
0x1800011b0  inc     rax
0x1800011b3  cmp     [r8+rax*2], r9w
0x1800011b8  jnz     short loc_1800011B0
0x1800011ba  lea     eax, ds:2[rax*2]
0x1800011c1  jmp     short loc_1800011C8
0x1800011c3  mov     r8, r11
0x1800011c6  mov     eax, edx
0x1800011c8  mov     [rbp+50h+var_98], eax
0x1800011cb  mov     rax, [rbp+50h+arg_48]
0x1800011d2  mov     [rbp+50h+var_A0], r8
0x1800011d6  mov     [rbp+50h+var_94], r9d
0x1800011da  mov     r8, [rax]
0x1800011dd  test    r8, r8
0x1800011e0  jz      short loc_1800011F8
0x1800011e2  mov     rax, rcx
0x1800011e5  inc     rax
0x1800011e8  cmp     [r8+rax*2], r9w
0x1800011ed  jnz     short loc_1800011E5
0x1800011ef  lea     eax, ds:2[rax*2]
0x1800011f6  jmp     short loc_1800011FD
0x1800011f8  mov     r8, r11
0x1800011fb  mov     eax, edx
0x1800011fd  mov     [rbp+50h+var_A8], eax
0x180001200  mov     rax, [rbp+50h+arg_40]
0x180001207  mov     [rbp+50h+var_B0], r8
0x18000120b  mov     [rbp+50h+var_A4], r9d
0x18000120f  mov     r8, [rax]
0x180001212  test    r8, r8
0x180001215  jz      short loc_18000122A
0x180001217  inc     rcx
0x18000121a  cmp     [r8+rcx*2], r9w
0x18000121f  jnz     short loc_180001217
0x180001221  lea     edx, ds:2[rcx*2]
0x180001228  jmp     short loc_18000122D
0x18000122a  mov     r8, r11
0x18000122d  mov     rax, [rbp+50h+arg_38]
0x180001234  mov     [rbp+50h+var_D0], rax
0x180001238  mov     rax, [rbp+50h+arg_30]
0x18000123f  mov     [rsp+150h+var_E0], rax
0x180001244  mov     rax, [rbp+50h+arg_28]
0x18000124b  mov     [rbp+50h+var_C0], r8
0x18000124f  xor     r8d, r8d
0x180001252  mov     [rbp+50h+var_B8], edx
0x180001255  mov     rdx, r10
0x180001258  mov     [rbp+50h+var_B4], r9d
0x18000125c  mov     rcx, [rax]
0x18000125f  mov     rax, [rbp+50h+arg_20]
0x180001266  mov     [rsp+150h+var_100], rax
0x18000126b  lea     rax, [rsp+150h+var_120]
0x180001270  mov     [rsp+150h+var_F0], rcx
0x180001275  lea     rcx, dword_18001E2A0
0x18000127c  mov     [rsp+150h+var_128], rax
0x180001281  mov     [rsp+150h+var_130], 11h
0x180001289  mov     [rbp+50h+var_C8], 8
0x180001291  mov     [rsp+150h+var_D8], 1
0x18000129a  mov     [rsp+150h+var_E8], 10h
0x1800012a3  mov     [rsp+150h+var_F8], 8
0x1800012ac  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012b1  mov     rcx, [rbp+50h+var_10]
0x1800012b5  xor     rcx, rsp; StackCookie
0x1800012b8  call    __security_check_cookie
0x1800012bd  add     rsp, 150h
0x1800012c4  pop     rbp
0x1800012c5  retn
```
