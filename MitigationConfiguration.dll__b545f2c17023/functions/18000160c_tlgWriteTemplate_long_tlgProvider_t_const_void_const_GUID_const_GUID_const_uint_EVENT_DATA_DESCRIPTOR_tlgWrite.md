# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000160c`
- end: `0x1800016b1`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013128`
- `0x1800132c8`

## callees

- `0x18000113c`
- `0x18000160c`
- `0x180001c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v5; // rax

  if ( *a5 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(*a5 + 2 * v5) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, a2, 0);
}

```

## disassembly

```asm
0x18000160c  sub     rsp, 88h
0x180001613  mov     rax, cs:__security_cookie
0x18000161a  xor     rax, rsp
0x18000161d  mov     [rsp+88h+var_18], rax
0x180001622  mov     rax, [rsp+88h+arg_28]
0x18000162a  xor     r8d, r8d
0x18000162d  mov     [rsp+88h+var_28], rax
0x180001632  mov     r9d, 4
0x180001638  mov     rax, [rsp+88h+arg_20]
0x180001640  mov     [rsp+88h+var_20], r9
0x180001645  mov     rcx, [rax]
0x180001648  test    rcx, rcx
0x18000164b  jz      short loc_180001664
0x18000164d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001651  inc     rax
0x180001654  cmp     [rcx+rax*2], r8w
0x180001659  jnz     short loc_180001651
0x18000165b  lea     eax, ds:2[rax*2]
0x180001662  jmp     short loc_180001670
0x180001664  lea     rcx, qword_180018390
0x18000166b  mov     eax, 2
0x180001670  mov     [rsp+88h+var_30], eax
0x180001674  lea     rax, [rsp+88h+var_58]
0x180001679  mov     [rsp+88h+var_60], rax
0x18000167e  mov     [rsp+88h+var_68], r9d
0x180001683  xor     r9d, r9d
0x180001686  mov     [rsp+88h+var_38], rcx
0x18000168b  lea     rcx, dword_18001C038
0x180001692  mov     [rsp+88h+var_2C], r8d
0x180001697  call    _tlgWriteTransfer_EventWriteTransfer
0x18000169c  mov     rcx, [rsp+88h+var_18]
0x1800016a1  xor     rcx, rsp; StackCookie
0x1800016a4  call    __security_check_cookie
0x1800016a9  add     rsp, 88h
0x1800016b0  retn
```
