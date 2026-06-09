# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001e7c`
- end: `0x180001f6d`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e048`

## callees

- `0x180001054`
- `0x180001e7c`
- `0x180002a70`

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
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180001e7c  sub     rsp, 98h
0x180001e83  mov     rax, cs:__security_cookie
0x180001e8a  xor     rax, rsp
0x180001e8d  mov     [rsp+98h+var_18], rax
0x180001e95  mov     rax, [rsp+98h+arg_30]
0x180001e9d  xor     r9d, r9d
0x180001ea0  mov     [rsp+98h+var_28], rax
0x180001ea5  mov     r10, rdx
0x180001ea8  mov     rax, [rsp+98h+arg_28]
0x180001eb0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001eb4  mov     [rsp+98h+var_20], 4
0x180001ebd  lea     r8d, [r9+2]
0x180001ec1  mov     rdx, [rax]
0x180001ec4  test    rdx, rdx
0x180001ec7  jz      short loc_180001EDF
0x180001ec9  mov     rax, rcx
0x180001ecc  inc     rax
0x180001ecf  cmp     [rdx+rax*2], r9w
0x180001ed4  jnz     short loc_180001ECC
0x180001ed6  lea     eax, ds:2[rax*2]
0x180001edd  jmp     short loc_180001EE9
0x180001edf  lea     rdx, dword_1800150AC
0x180001ee6  mov     eax, r8d
0x180001ee9  mov     [rsp+98h+var_30], eax
0x180001eed  mov     rax, [rsp+98h+arg_20]
0x180001ef5  mov     [rsp+98h+var_38], rdx
0x180001efa  mov     [rsp+98h+var_2C], r9d
0x180001eff  mov     rdx, [rax]
0x180001f02  test    rdx, rdx
0x180001f05  jz      short loc_180001F1B
0x180001f07  inc     rcx
0x180001f0a  cmp     [rdx+rcx*2], r9w
0x180001f0f  jnz     short loc_180001F07
0x180001f11  lea     r8d, ds:2[rcx*2]
0x180001f19  jmp     short loc_180001F22
0x180001f1b  lea     rdx, dword_1800150AC
0x180001f22  lea     rax, [rsp+98h+var_68]
0x180001f27  mov     [rsp+98h+var_48], rdx
0x180001f2c  mov     [rsp+98h+var_40], r8d
0x180001f31  lea     rcx, dword_18001C010
0x180001f38  mov     [rsp+98h+var_70], rax
0x180001f3d  xor     r8d, r8d
0x180001f40  mov     rdx, r10
0x180001f43  mov     [rsp+98h+var_78], 5
0x180001f4b  mov     [rsp+98h+var_3C], r9d
0x180001f50  call    _tlgWriteTransfer_EventWriteTransfer
0x180001f55  mov     rcx, [rsp+98h+var_18]
0x180001f5d  xor     rcx, rsp; StackCookie
0x180001f60  call    __security_check_cookie
0x180001f65  add     rsp, 98h
0x180001f6c  retn
```
