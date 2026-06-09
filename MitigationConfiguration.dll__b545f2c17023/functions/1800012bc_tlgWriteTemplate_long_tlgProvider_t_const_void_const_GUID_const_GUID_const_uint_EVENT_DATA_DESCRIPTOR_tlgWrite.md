# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800012bc`
- end: `0x1800013d2`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z`
- size: `278`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013528`
- `0x180013720`

## callees

- `0x18000113c`
- `0x1800012bc`
- `0x180001c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7)
{
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax

  v7 = -1;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(*a7 + 2 * v8) );
  }
  if ( *a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(*a6 + 2 * v9) );
  }
  if ( *a5 )
  {
    do
      ++v7;
    while ( *(_WORD *)(*a5 + 2 * v7) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, a2, 0);
}

```

## disassembly

```asm
0x1800012bc  sub     rsp, 98h
0x1800012c3  mov     rax, cs:__security_cookie
0x1800012ca  xor     rax, rsp
0x1800012cd  mov     [rsp+98h+var_18], rax
0x1800012d5  mov     rax, [rsp+98h+arg_30]
0x1800012dd  lea     r11, qword_180018390
0x1800012e4  mov     r10, rdx
0x1800012e7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800012eb  xor     r9d, r9d
0x1800012ee  mov     r8d, 2
0x1800012f4  mov     rdx, [rax]
0x1800012f7  test    rdx, rdx
0x1800012fa  jz      short loc_180001312
0x1800012fc  mov     rax, rcx
0x1800012ff  inc     rax
0x180001302  cmp     [rdx+rax*2], r9w
0x180001307  jnz     short loc_1800012FF
0x180001309  lea     eax, ds:2[rax*2]
0x180001310  jmp     short loc_180001318
0x180001312  mov     rdx, r11
0x180001315  mov     eax, r8d
0x180001318  mov     [rsp+98h+var_20], eax
0x18000131c  mov     rax, [rsp+98h+arg_28]
0x180001324  mov     [rsp+98h+var_28], rdx
0x180001329  mov     [rsp+98h+var_1C], r9d
0x18000132e  mov     rdx, [rax]
0x180001331  test    rdx, rdx
0x180001334  jz      short loc_18000134C
0x180001336  mov     rax, rcx
0x180001339  inc     rax
0x18000133c  cmp     [rdx+rax*2], r9w
0x180001341  jnz     short loc_180001339
0x180001343  lea     eax, ds:2[rax*2]
0x18000134a  jmp     short loc_180001352
0x18000134c  mov     rdx, r11
0x18000134f  mov     eax, r8d
0x180001352  mov     [rsp+98h+var_30], eax
0x180001356  mov     rax, [rsp+98h+arg_20]
0x18000135e  mov     [rsp+98h+var_38], rdx
0x180001363  mov     [rsp+98h+var_2C], r9d
0x180001368  mov     rdx, [rax]
0x18000136b  test    rdx, rdx
0x18000136e  jz      short loc_180001384
0x180001370  inc     rcx
0x180001373  cmp     [rdx+rcx*2], r9w
0x180001378  jnz     short loc_180001370
0x18000137a  lea     r8d, ds:2[rcx*2]
0x180001382  jmp     short loc_180001387
0x180001384  mov     rdx, r11
0x180001387  lea     rax, [rsp+98h+var_68]
0x18000138c  mov     [rsp+98h+var_48], rdx
0x180001391  mov     [rsp+98h+var_40], r8d
0x180001396  lea     rcx, dword_18001C038
0x18000139d  mov     [rsp+98h+var_70], rax
0x1800013a2  xor     r8d, r8d
0x1800013a5  mov     rdx, r10
0x1800013a8  mov     [rsp+98h+var_78], 5
0x1800013b0  mov     [rsp+98h+var_3C], r9d
0x1800013b5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800013ba  mov     rcx, [rsp+98h+var_18]
0x1800013c2  xor     rcx, rsp; StackCookie
0x1800013c5  call    __security_check_cookie
0x1800013ca  add     rsp, 98h
0x1800013d1  retn
```
