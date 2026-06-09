# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800011b0`
- end: `0x18000145b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016f4c`

## callees

- `0x1800011b0`
- `0x1800018e8`
- `0x180002c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        __int64 a9,
        _QWORD *a10,
        __int64 a11,
        _QWORD *a12,
        __int64 a13,
        _QWORD *a14,
        __int64 a15,
        _QWORD *a16,
        _QWORD *a17,
        __int64 a18,
        _QWORD *a19,
        _QWORD *a20)
{
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax

  v21 = -1;
  if ( *a20 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(*a20 + 2 * v22) );
  }
  if ( *a19 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(*a19 + v23) );
  }
  if ( *a17 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(*a17 + 2 * v24) );
  }
  if ( *a16 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_BYTE *)(*a16 + v25) );
  }
  if ( *a14 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(*a14 + v26) );
  }
  if ( *a12 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a12 + 2 * v27) );
  }
  if ( *a10 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(*a10 + v28) );
  }
  if ( *a8 )
  {
    do
      ++v21;
    while ( *(_BYTE *)(*a8 + v21) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x1800011b0  mov     [rsp-8+arg_10], rbx
0x1800011b5  push    rbp
0x1800011b6  push    rsi
0x1800011b7  push    rdi
0x1800011b8  lea     rbp, [rsp-60h]
0x1800011bd  sub     rsp, 160h
0x1800011c4  mov     rax, cs:__security_cookie
0x1800011cb  xor     rax, rsp
0x1800011ce  mov     [rbp+70h+var_20], rax
0x1800011d2  mov     rax, [rbp+70h+arg_98]
0x1800011d9  mov     r11, rdx
0x1800011dc  mov     r10, rcx
0x1800011df  xor     ebx, ebx
0x1800011e1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800011e5  mov     r9d, 2
0x1800011eb  mov     rdx, [rax]
0x1800011ee  test    rdx, rdx
0x1800011f1  jz      short loc_180001208
0x1800011f3  mov     rax, rcx
0x1800011f6  inc     rax
0x1800011f9  cmp     [rdx+rax*2], bx
0x1800011fd  jnz     short loc_1800011F6
0x1800011ff  lea     eax, ds:2[rax*2]
0x180001206  jmp     short loc_180001212
0x180001208  lea     rdx, dword_18001E1D4
0x18000120f  mov     eax, r9d
0x180001212  mov     [rbp+70h+var_28], eax
0x180001215  lea     rdi, byte_18001E1D0
0x18000121c  mov     rax, [rbp+70h+arg_90]
0x180001223  mov     r8d, 1
0x180001229  mov     [rbp+70h+var_30], rdx
0x18000122d  mov     [rbp+70h+var_24], ebx
0x180001230  mov     rdx, [rax]
0x180001233  test    rdx, rdx
0x180001236  jz      short loc_180001247
0x180001238  mov     rax, rcx
0x18000123b  inc     rax
0x18000123e  cmp     [rdx+rax], bl
0x180001241  jnz     short loc_18000123B
0x180001243  inc     eax
0x180001245  jmp     short loc_18000124D
0x180001247  mov     rdx, rdi
0x18000124a  mov     eax, r8d
0x18000124d  mov     [rbp+70h+var_38], eax
0x180001250  mov     rax, [rbp+70h+arg_88]
0x180001257  mov     [rbp+70h+var_50], rax
0x18000125b  mov     rax, [rbp+70h+arg_80]
0x180001262  mov     [rbp+70h+var_40], rdx
0x180001266  mov     [rbp+70h+var_34], ebx
0x180001269  mov     [rbp+70h+var_48], 4
0x180001271  mov     rdx, [rax]
0x180001274  test    rdx, rdx
0x180001277  jz      short loc_18000128E
0x180001279  mov     rax, rcx
0x18000127c  inc     rax
0x18000127f  cmp     [rdx+rax*2], bx
0x180001283  jnz     short loc_18000127C
0x180001285  lea     eax, ds:2[rax*2]
0x18000128c  jmp     short loc_180001298
0x18000128e  lea     rdx, dword_18001E1D4
0x180001295  mov     eax, r9d
0x180001298  mov     [rbp+70h+var_58], eax
0x18000129b  mov     rax, [rbp+70h+arg_78]
0x1800012a2  mov     [rbp+70h+var_60], rdx
0x1800012a6  mov     [rbp+70h+var_54], ebx
0x1800012a9  mov     rdx, [rax]
0x1800012ac  test    rdx, rdx
0x1800012af  jz      short loc_1800012C0
0x1800012b1  mov     rax, rcx
0x1800012b4  inc     rax
0x1800012b7  cmp     [rdx+rax], bl
0x1800012ba  jnz     short loc_1800012B4
0x1800012bc  inc     eax
0x1800012be  jmp     short loc_1800012C6
0x1800012c0  mov     rdx, rdi
0x1800012c3  mov     eax, r8d
0x1800012c6  mov     [rbp+70h+var_68], eax
0x1800012c9  mov     rax, [rbp+70h+arg_70]
0x1800012d0  mov     [rbp+70h+var_80], rax
0x1800012d4  mov     rax, [rbp+70h+arg_68]
0x1800012db  mov     [rbp+70h+var_70], rdx
0x1800012df  mov     [rbp+70h+var_64], ebx
0x1800012e2  mov     [rbp+70h+var_78], 4
0x1800012ea  mov     rdx, [rax]
0x1800012ed  test    rdx, rdx
0x1800012f0  jz      short loc_180001301
0x1800012f2  mov     rax, rcx
0x1800012f5  inc     rax
0x1800012f8  cmp     [rdx+rax], bl
0x1800012fb  jnz     short loc_1800012F5
0x1800012fd  inc     eax
0x1800012ff  jmp     short loc_180001307
0x180001301  mov     rdx, rdi
0x180001304  mov     eax, r8d
0x180001307  mov     [rbp+70h+var_88], eax
0x18000130a  mov     rax, [rbp+70h+arg_60]
0x180001311  mov     [rbp+70h+var_A0], rax
0x180001315  mov     rax, [rbp+70h+arg_58]
0x18000131c  mov     [rbp+70h+var_90], rdx
0x180001320  mov     [rbp+70h+var_84], ebx
0x180001323  mov     [rbp+70h+var_98], 4
0x18000132b  mov     rdx, [rax]
0x18000132e  test    rdx, rdx
0x180001331  jz      short loc_180001349
0x180001333  mov     rax, rcx
0x180001336  inc     rax
0x180001339  cmp     [rdx+rax*2], bx
0x18000133d  jnz     short loc_180001336
0x18000133f  lea     r9d, ds:2[rax*2]
0x180001347  jmp     short loc_180001350
0x180001349  lea     rdx, dword_18001E1D4
0x180001350  mov     rax, [rbp+70h+arg_50]
0x180001357  mov     [rbp+70h+var_C0], rax
0x18000135b  mov     rax, [rbp+70h+arg_48]
0x180001362  mov     [rbp+70h+var_B0], rdx
0x180001366  mov     [rbp+70h+var_A8], r9d
0x18000136a  mov     [rbp+70h+var_A4], ebx
0x18000136d  mov     rdx, [rax]
0x180001370  mov     [rbp+70h+var_B8], 4
0x180001378  test    rdx, rdx
0x18000137b  jz      short loc_18000138C
0x18000137d  mov     rax, rcx
0x180001380  inc     rax
0x180001383  cmp     [rdx+rax], bl
0x180001386  jnz     short loc_180001380
0x180001388  inc     eax
0x18000138a  jmp     short loc_180001392
0x18000138c  mov     rdx, rdi
0x18000138f  mov     eax, r8d
0x180001392  mov     [rbp+70h+var_C8], eax
0x180001395  mov     rax, [rbp+70h+arg_40]
0x18000139c  mov     [rbp+70h+var_E0], rax
0x1800013a0  mov     rax, [rbp+70h+arg_38]
0x1800013a7  mov     [rbp+70h+var_D0], rdx
0x1800013ab  mov     [rbp+70h+var_C4], ebx
0x1800013ae  mov     [rbp+70h+var_D8], 4
0x1800013b6  mov     rdx, [rax]
0x1800013b9  test    rdx, rdx
0x1800013bc  jz      short loc_1800013CC
0x1800013be  inc     rcx
0x1800013c1  cmp     [rdx+rcx], bl
0x1800013c4  jnz     short loc_1800013BE
0x1800013c6  lea     r8d, [rcx+1]
0x1800013ca  jmp     short loc_1800013CF
0x1800013cc  mov     rdx, rdi
0x1800013cf  mov     rax, [rbp+70h+arg_30]
0x1800013d6  xor     r9d, r9d
0x1800013d9  mov     [rsp+170h+var_100], rax
0x1800013de  mov     rcx, r10
0x1800013e1  mov     rax, [rbp+70h+arg_28]
0x1800013e8  mov     [rsp+170h+var_110], rax
0x1800013ed  mov     rax, [rbp+70h+arg_20]
0x1800013f4  mov     [rsp+170h+var_120], rax
0x1800013f9  lea     rax, [rsp+170h+var_140]
0x1800013fe  mov     [rbp+70h+var_F0], rdx
0x180001402  mov     rdx, r11
0x180001405  mov     [rbp+70h+var_E8], r8d
0x180001409  xor     r8d, r8d
0x18000140c  mov     [rsp+170h+var_148], rax
0x180001411  mov     [rsp+170h+var_150], 12h
0x180001419  mov     [rbp+70h+var_E4], ebx
0x18000141c  mov     [rsp+170h+var_F8], 4
0x180001425  mov     [rsp+170h+var_108], 8
0x18000142e  mov     [rsp+170h+var_118], 8
0x180001437  call    _tlgWriteTransfer_EventWriteTransfer
0x18000143c  mov     rcx, [rbp+70h+var_20]
0x180001440  xor     rcx, rsp; StackCookie
0x180001443  call    __security_check_cookie
0x180001448  mov     rbx, [rsp+170h+arg_10]
0x180001450  add     rsp, 160h
0x180001457  pop     rdi
0x180001458  pop     rsi
0x180001459  pop     rbp
0x18000145a  retn
```
