# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180002020`
- end: `0x180002113`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@3@Z`
- size: `243`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e6f8`
- `0x18000eef0`

## callees

- `0x180001054`
- `0x180002020`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v7; // rcx
  __int64 v8; // rax

  v7 = -1;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(*a7 + 2 * v8) );
  }
  if ( *a5 )
  {
    do
      ++v7;
    while ( *(_WORD *)(*a5 + 2 * v7) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180002020  sub     rsp, 98h
0x180002027  mov     rax, cs:__security_cookie
0x18000202e  xor     rax, rsp
0x180002031  mov     [rsp+98h+var_18], rax
0x180002039  mov     rax, [rsp+98h+arg_30]
0x180002041  mov     r10, rdx
0x180002044  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002048  xor     r9d, r9d
0x18000204b  mov     r8d, 2
0x180002051  mov     rdx, [rax]
0x180002054  test    rdx, rdx
0x180002057  jz      short loc_18000206F
0x180002059  mov     rax, rcx
0x18000205c  inc     rax
0x18000205f  cmp     [rdx+rax*2], r9w
0x180002064  jnz     short loc_18000205C
0x180002066  lea     eax, ds:2[rax*2]
0x18000206d  jmp     short loc_180002079
0x18000206f  lea     rdx, dword_1800150AC
0x180002076  mov     eax, r8d
0x180002079  mov     [rsp+98h+var_20], eax
0x18000207d  mov     rax, [rsp+98h+arg_28]
0x180002085  mov     [rsp+98h+var_38], rax
0x18000208a  mov     rax, [rsp+98h+arg_20]
0x180002092  mov     [rsp+98h+var_28], rdx
0x180002097  mov     [rsp+98h+var_1C], r9d
0x18000209c  mov     [rsp+98h+var_30], 1
0x1800020a5  mov     rdx, [rax]
0x1800020a8  test    rdx, rdx
0x1800020ab  jz      short loc_1800020C1
0x1800020ad  inc     rcx
0x1800020b0  cmp     [rdx+rcx*2], r9w
0x1800020b5  jnz     short loc_1800020AD
0x1800020b7  lea     r8d, ds:2[rcx*2]
0x1800020bf  jmp     short loc_1800020C8
0x1800020c1  lea     rdx, dword_1800150AC
0x1800020c8  lea     rax, [rsp+98h+var_68]
0x1800020cd  mov     [rsp+98h+var_48], rdx
0x1800020d2  mov     [rsp+98h+var_40], r8d
0x1800020d7  lea     rcx, dword_18001C010
0x1800020de  mov     [rsp+98h+var_70], rax
0x1800020e3  xor     r8d, r8d
0x1800020e6  mov     rdx, r10
0x1800020e9  mov     [rsp+98h+var_78], 5
0x1800020f1  mov     [rsp+98h+var_3C], r9d
0x1800020f6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800020fb  mov     rcx, [rsp+98h+var_18]
0x180002103  xor     rcx, rsp; StackCookie
0x180002106  call    __security_check_cookie
0x18000210b  add     rsp, 98h
0x180002112  retn
```
