# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)

- ea: `0x180001540`
- end: `0x1800016a1`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U?$_tlgWrapperByRef@$0BA@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43AEBU?$_tlgWrapperByRef@$0BA@@@5@Z`
- size: `353`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000881c`

## callees

- `0x1800011d0`
- `0x180001540`
- `0x180001e20`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10)
{
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax

  v10 = -1;
  if ( *a10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(*a10 + v11) );
  }
  if ( *a7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_BYTE *)(*a7 + v12) );
  }
  if ( *a6 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_BYTE *)(*a6 + v13) );
  }
  if ( *a5 )
  {
    do
      ++v10;
    while ( *(_BYTE *)(*a5 + v10) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001D000, a2, 0);
}

```

## disassembly

```asm
0x180001540  push    rbp
0x180001542  lea     rbp, [rsp-17h]
0x180001547  sub     rsp, 0E0h
0x18000154e  mov     rax, cs:__security_cookie
0x180001555  xor     rax, rsp
0x180001558  mov     [rbp+17h+var_10], rax
0x18000155c  mov     rax, [rbp+17h+arg_58]
0x180001560  lea     r11, qword_1800150F8
0x180001567  xor     r9d, r9d
0x18000156a  mov     [rbp+17h+var_18], 10h
0x180001572  mov     r10, rdx
0x180001575  mov     [rbp+17h+var_28], 10h
0x18000157d  mov     rcx, [rax]
0x180001580  mov     rax, [rbp+17h+arg_50]
0x180001584  lea     r8d, [r9+1]
0x180001588  mov     [rbp+17h+var_20], rcx
0x18000158c  mov     rcx, [rax]
0x18000158f  mov     rax, [rbp+17h+arg_48]
0x180001593  mov     [rbp+17h+var_30], rcx
0x180001597  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000159b  mov     rdx, [rax]
0x18000159e  test    rdx, rdx
0x1800015a1  jz      short loc_1800015B3
0x1800015a3  mov     rax, rcx
0x1800015a6  inc     rax
0x1800015a9  cmp     [rdx+rax], r9b
0x1800015ad  jnz     short loc_1800015A6
0x1800015af  inc     eax
0x1800015b1  jmp     short loc_1800015B9
0x1800015b3  mov     rdx, r11
0x1800015b6  mov     eax, r8d
0x1800015b9  mov     [rbp+17h+var_38], eax
0x1800015bc  mov     rax, [rbp+17h+arg_40]
0x1800015c0  mov     [rbp+17h+var_50], rax
0x1800015c4  mov     rax, [rbp+17h+arg_38]
0x1800015c8  mov     [rbp+17h+var_60], rax
0x1800015cc  mov     rax, [rbp+17h+arg_30]
0x1800015d0  mov     [rbp+17h+var_40], rdx
0x1800015d4  mov     [rbp+17h+var_34], r9d
0x1800015d8  mov     [rbp+17h+var_48], 4
0x1800015e0  mov     rdx, [rax]
0x1800015e3  mov     [rbp+17h+var_58], 4
0x1800015eb  test    rdx, rdx
0x1800015ee  jz      short loc_180001600
0x1800015f0  mov     rax, rcx
0x1800015f3  inc     rax
0x1800015f6  cmp     [rdx+rax], r9b
0x1800015fa  jnz     short loc_1800015F3
0x1800015fc  inc     eax
0x1800015fe  jmp     short loc_180001606
0x180001600  mov     rdx, r11
0x180001603  mov     eax, r8d
0x180001606  mov     [rbp+17h+var_68], eax
0x180001609  mov     rax, [rbp+17h+arg_28]
0x18000160d  mov     [rbp+17h+var_70], rdx
0x180001611  mov     [rbp+17h+var_64], r9d
0x180001615  mov     rdx, [rax]
0x180001618  test    rdx, rdx
0x18000161b  jz      short loc_18000162D
0x18000161d  mov     rax, rcx
0x180001620  inc     rax
0x180001623  cmp     [rdx+rax], r9b
0x180001627  jnz     short loc_180001620
0x180001629  inc     eax
0x18000162b  jmp     short loc_180001633
0x18000162d  mov     rdx, r11
0x180001630  mov     eax, r8d
0x180001633  mov     [rbp+17h+var_78], eax
0x180001636  mov     rax, [rbp+17h+arg_20]
0x18000163a  mov     [rbp+17h+var_80], rdx
0x18000163e  mov     [rbp+17h+var_74], r9d
0x180001642  mov     rdx, [rax]
0x180001645  test    rdx, rdx
0x180001648  jz      short loc_180001659
0x18000164a  inc     rcx
0x18000164d  cmp     [rdx+rcx], r9b
0x180001651  jnz     short loc_18000164A
0x180001653  lea     r8d, [rcx+1]
0x180001657  jmp     short loc_18000165C
0x180001659  mov     rdx, r11
0x18000165c  lea     rax, [rsp+0E0h+var_B0]
0x180001661  mov     [rbp+17h+var_90], rdx
0x180001665  mov     [rbp+17h+var_88], r8d
0x180001669  lea     rcx, dword_18001D000
0x180001670  mov     [rsp+0E0h+var_B8], rax
0x180001675  xor     r8d, r8d
0x180001678  mov     rdx, r10
0x18000167b  mov     [rsp+0E0h+var_C0], 0Ah
0x180001683  mov     [rbp+17h+var_84], r9d
0x180001687  call    _tlgWriteTransfer_EventWriteTransfer
0x18000168c  mov     rcx, [rbp+17h+var_10]
0x180001690  xor     rcx, rsp; StackCookie
0x180001693  call    __security_check_cookie
0x180001698  add     rsp, 0E0h
0x18000169f  pop     rbp
0x1800016a0  retn
```
