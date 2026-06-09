# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001150`
- end: `0x180001212`
- name: `??$Write@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapSz@G@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000891c`

## callees

- `0x180001054`
- `0x180001150`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v7; // rax

  if ( *a7 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(*a7 + 2 * v7) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180001150  sub     rsp, 98h
0x180001157  mov     rax, cs:__security_cookie
0x18000115e  xor     rax, rsp
0x180001161  mov     [rsp+98h+var_18], rax
0x180001169  mov     rax, [rsp+98h+arg_30]
0x180001171  xor     r8d, r8d
0x180001174  mov     rcx, [rax]
0x180001177  test    rcx, rcx
0x18000117a  jz      short loc_180001193
0x18000117c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001180  inc     rax
0x180001183  cmp     [rcx+rax*2], r8w
0x180001188  jnz     short loc_180001180
0x18000118a  lea     eax, ds:2[rax*2]
0x180001191  jmp     short loc_18000119F
0x180001193  lea     rcx, dword_1800150AC
0x18000119a  mov     eax, 2
0x18000119f  mov     [rsp+98h+var_20], eax
0x1800011a3  xor     r9d, r9d
0x1800011a6  mov     rax, [rsp+98h+arg_28]
0x1800011ae  mov     [rsp+98h+var_38], rax
0x1800011b3  mov     rax, [rsp+98h+arg_20]
0x1800011bb  mov     [rsp+98h+var_48], rax
0x1800011c0  lea     rax, [rsp+98h+var_68]
0x1800011c5  mov     [rsp+98h+var_28], rcx
0x1800011ca  lea     rcx, dword_18001C010
0x1800011d1  mov     [rsp+98h+var_70], rax
0x1800011d6  mov     [rsp+98h+var_78], 5
0x1800011de  mov     [rsp+98h+var_1C], r8d
0x1800011e3  mov     [rsp+98h+var_30], 1
0x1800011ec  mov     [rsp+98h+var_40], 1
0x1800011f5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011fa  mov     rcx, [rsp+98h+var_18]
0x180001202  xor     rcx, rsp; StackCookie
0x180001205  call    __security_check_cookie
0x18000120a  add     rsp, 98h
0x180001211  retn
```
