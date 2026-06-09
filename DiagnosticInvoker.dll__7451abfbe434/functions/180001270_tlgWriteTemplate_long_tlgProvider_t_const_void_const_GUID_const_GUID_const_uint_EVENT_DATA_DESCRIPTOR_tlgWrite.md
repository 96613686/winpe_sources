# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001270`
- end: `0x1800013bb`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@434@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *, _QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b994`

## callees

- `0x1800011d0`
- `0x180001270`
- `0x180001e20`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
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
0x180001270  push    rbp
0x180001272  lea     rbp, [rsp-1Fh]
0x180001277  sub     rsp, 0D0h
0x18000127e  mov     rax, cs:__security_cookie
0x180001285  xor     rax, rsp
0x180001288  mov     [rbp+1Fh+var_10], rax
0x18000128c  mov     rax, [rbp+1Fh+arg_50]
0x180001290  lea     r11, qword_1800150F8
0x180001297  xor     r9d, r9d
0x18000129a  mov     [rbp+1Fh+var_20], rax
0x18000129e  mov     rax, [rbp+1Fh+arg_48]
0x1800012a2  mov     r10, rdx
0x1800012a5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800012a9  mov     [rbp+1Fh+var_18], 4
0x1800012b1  lea     r8d, [r9+1]
0x1800012b5  mov     rdx, [rax]
0x1800012b8  test    rdx, rdx
0x1800012bb  jz      short loc_1800012CD
0x1800012bd  mov     rax, rcx
0x1800012c0  inc     rax
0x1800012c3  cmp     [rdx+rax], r9b
0x1800012c7  jnz     short loc_1800012C0
0x1800012c9  inc     eax
0x1800012cb  jmp     short loc_1800012D3
0x1800012cd  mov     rdx, r11
0x1800012d0  mov     eax, r8d
0x1800012d3  mov     [rbp+1Fh+var_28], eax
0x1800012d6  mov     rax, [rbp+1Fh+arg_40]
0x1800012da  mov     [rbp+1Fh+var_40], rax
0x1800012de  mov     rax, [rbp+1Fh+arg_38]
0x1800012e2  mov     [rbp+1Fh+var_50], rax
0x1800012e6  mov     rax, [rbp+1Fh+arg_30]
0x1800012ea  mov     [rbp+1Fh+var_30], rdx
0x1800012ee  mov     [rbp+1Fh+var_24], r9d
0x1800012f2  mov     [rbp+1Fh+var_38], 4
0x1800012fa  mov     rdx, [rax]
0x1800012fd  mov     [rbp+1Fh+var_48], 4
0x180001305  test    rdx, rdx
0x180001308  jz      short loc_18000131A
0x18000130a  mov     rax, rcx
0x18000130d  inc     rax
0x180001310  cmp     [rdx+rax], r9b
0x180001314  jnz     short loc_18000130D
0x180001316  inc     eax
0x180001318  jmp     short loc_180001320
0x18000131a  mov     rdx, r11
0x18000131d  mov     eax, r8d
0x180001320  mov     [rbp+1Fh+var_58], eax
0x180001323  mov     rax, [rbp+1Fh+arg_28]
0x180001327  mov     [rbp+1Fh+var_60], rdx
0x18000132b  mov     [rbp+1Fh+var_54], r9d
0x18000132f  mov     rdx, [rax]
0x180001332  test    rdx, rdx
0x180001335  jz      short loc_180001347
0x180001337  mov     rax, rcx
0x18000133a  inc     rax
0x18000133d  cmp     [rdx+rax], r9b
0x180001341  jnz     short loc_18000133A
0x180001343  inc     eax
0x180001345  jmp     short loc_18000134D
0x180001347  mov     rdx, r11
0x18000134a  mov     eax, r8d
0x18000134d  mov     [rbp+1Fh+var_68], eax
0x180001350  mov     rax, [rbp+1Fh+arg_20]
0x180001354  mov     [rbp+1Fh+var_70], rdx
0x180001358  mov     [rbp+1Fh+var_64], r9d
0x18000135c  mov     rdx, [rax]
0x18000135f  test    rdx, rdx
0x180001362  jz      short loc_180001373
0x180001364  inc     rcx
0x180001367  cmp     [rdx+rcx], r9b
0x18000136b  jnz     short loc_180001364
0x18000136d  lea     r8d, [rcx+1]
0x180001371  jmp     short loc_180001376
0x180001373  mov     rdx, r11
0x180001376  lea     rax, [rsp+0D0h+var_A0]
0x18000137b  mov     [rbp+1Fh+var_80], rdx
0x18000137f  mov     [rbp+1Fh+var_78], r8d
0x180001383  lea     rcx, dword_18001D000
0x18000138a  mov     [rsp+0D0h+var_A8], rax
0x18000138f  xor     r8d, r8d
0x180001392  mov     rdx, r10
0x180001395  mov     [rsp+0D0h+var_B0], 9
0x18000139d  mov     [rbp+1Fh+var_74], r9d
0x1800013a1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013a6  mov     rcx, [rbp+1Fh+var_10]
0x1800013aa  xor     rcx, rsp; StackCookie
0x1800013ad  call    __security_check_cookie
0x1800013b2  add     rsp, 0D0h
0x1800013b9  pop     rbp
0x1800013ba  retn
```
