# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001514`
- end: `0x180001605`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013128`
- `0x1800132c8`

## callees

- `0x18000113c`
- `0x180001514`
- `0x180001c00`

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
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, a2, 0);
}

```

## disassembly

```asm
0x180001514  sub     rsp, 98h
0x18000151b  mov     rax, cs:__security_cookie
0x180001522  xor     rax, rsp
0x180001525  mov     [rsp+98h+var_18], rax
0x18000152d  mov     rax, [rsp+98h+arg_30]
0x180001535  xor     r9d, r9d
0x180001538  mov     [rsp+98h+var_28], rax
0x18000153d  mov     r10, rdx
0x180001540  mov     rax, [rsp+98h+arg_28]
0x180001548  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000154c  mov     [rsp+98h+var_20], 4
0x180001555  lea     r8d, [r9+2]
0x180001559  mov     rdx, [rax]
0x18000155c  test    rdx, rdx
0x18000155f  jz      short loc_180001577
0x180001561  mov     rax, rcx
0x180001564  inc     rax
0x180001567  cmp     [rdx+rax*2], r9w
0x18000156c  jnz     short loc_180001564
0x18000156e  lea     eax, ds:2[rax*2]
0x180001575  jmp     short loc_180001581
0x180001577  lea     rdx, qword_180018390
0x18000157e  mov     eax, r8d
0x180001581  mov     [rsp+98h+var_30], eax
0x180001585  mov     rax, [rsp+98h+arg_20]
0x18000158d  mov     [rsp+98h+var_38], rdx
0x180001592  mov     [rsp+98h+var_2C], r9d
0x180001597  mov     rdx, [rax]
0x18000159a  test    rdx, rdx
0x18000159d  jz      short loc_1800015B3
0x18000159f  inc     rcx
0x1800015a2  cmp     [rdx+rcx*2], r9w
0x1800015a7  jnz     short loc_18000159F
0x1800015a9  lea     r8d, ds:2[rcx*2]
0x1800015b1  jmp     short loc_1800015BA
0x1800015b3  lea     rdx, qword_180018390
0x1800015ba  lea     rax, [rsp+98h+var_68]
0x1800015bf  mov     [rsp+98h+var_48], rdx
0x1800015c4  mov     [rsp+98h+var_40], r8d
0x1800015c9  lea     rcx, dword_18001C038
0x1800015d0  mov     [rsp+98h+var_70], rax
0x1800015d5  xor     r8d, r8d
0x1800015d8  mov     rdx, r10
0x1800015db  mov     [rsp+98h+var_78], 5
0x1800015e3  mov     [rsp+98h+var_3C], r9d
0x1800015e8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800015ed  mov     rcx, [rsp+98h+var_18]
0x1800015f5  xor     rcx, rsp; StackCookie
0x1800015f8  call    __security_check_cookie
0x1800015fd  add     rsp, 98h
0x180001604  retn
```
