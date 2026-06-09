# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000132c`
- end: `0x14000141d`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b454`

## callees

- `0x140001130`
- `0x14000132c`
- `0x14000ded0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v6; // rcx
  __int64 v7; // rax

  v6 = -1;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(*a6 + 2 * v7) );
  }
  if ( *a5 )
  {
    do
      ++v6;
    while ( *(_WORD *)(*a5 + 2 * v6) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_140017048, a2, 0, 0);
}

```

## disassembly

```asm
0x14000132c  sub     rsp, 98h
0x140001333  mov     rax, cs:__security_cookie
0x14000133a  xor     rax, rsp
0x14000133d  mov     [rsp+98h+var_18], rax
0x140001345  mov     rax, [rsp+98h+arg_30]
0x14000134d  xor     r9d, r9d
0x140001350  mov     [rsp+98h+var_28], rax
0x140001355  mov     r10, rdx
0x140001358  mov     rax, [rsp+98h+arg_28]
0x140001360  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001364  mov     [rsp+98h+var_20], 4
0x14000136d  lea     r8d, [r9+2]
0x140001371  mov     rdx, [rax]
0x140001374  test    rdx, rdx
0x140001377  jz      short loc_14000138F
0x140001379  mov     rax, rcx
0x14000137c  inc     rax
0x14000137f  cmp     [rdx+rax*2], r9w
0x140001384  jnz     short loc_14000137C
0x140001386  lea     eax, ds:2[rax*2]
0x14000138d  jmp     short loc_140001399
0x14000138f  lea     rdx, qword_140011EC0
0x140001396  mov     eax, r8d
0x140001399  mov     [rsp+98h+var_30], eax
0x14000139d  mov     rax, [rsp+98h+arg_20]
0x1400013a5  mov     [rsp+98h+var_38], rdx
0x1400013aa  mov     [rsp+98h+var_2C], r9d
0x1400013af  mov     rdx, [rax]
0x1400013b2  test    rdx, rdx
0x1400013b5  jz      short loc_1400013CB
0x1400013b7  inc     rcx
0x1400013ba  cmp     [rdx+rcx*2], r9w
0x1400013bf  jnz     short loc_1400013B7
0x1400013c1  lea     r8d, ds:2[rcx*2]
0x1400013c9  jmp     short loc_1400013D2
0x1400013cb  lea     rdx, qword_140011EC0
0x1400013d2  lea     rax, [rsp+98h+var_68]
0x1400013d7  mov     [rsp+98h+var_48], rdx
0x1400013dc  mov     [rsp+98h+var_40], r8d
0x1400013e1  lea     rcx, dword_140017048
0x1400013e8  mov     [rsp+98h+var_70], rax
0x1400013ed  xor     r8d, r8d
0x1400013f0  mov     rdx, r10
0x1400013f3  mov     [rsp+98h+var_78], 5
0x1400013fb  mov     [rsp+98h+var_3C], r9d
0x140001400  call    _tlgWriteTransfer_EventWriteTransfer
0x140001405  mov     rcx, [rsp+98h+var_18]
0x14000140d  xor     rcx, rsp; StackCookie
0x140001410  call    __security_check_cookie
0x140001415  add     rsp, 98h
0x14000141c  retn
```
