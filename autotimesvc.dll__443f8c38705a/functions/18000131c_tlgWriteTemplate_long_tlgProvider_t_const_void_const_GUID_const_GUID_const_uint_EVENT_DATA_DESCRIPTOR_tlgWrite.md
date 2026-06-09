# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x18000131c`
- end: `0x1800013a6`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b264`
- `0x18000d330`
- `0x18000e048`
- `0x18000e550`
- `0x18000e6f8`
- `0x18000f6e0`

## callees

- `0x180001054`
- `0x18000131c`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
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
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x18000131c  sub     rsp, 78h
0x180001320  mov     rax, cs:__security_cookie
0x180001327  xor     rax, rsp
0x18000132a  mov     [rsp+78h+var_18], rax
0x18000132f  mov     rax, [rsp+78h+arg_20]
0x180001337  xor     r8d, r8d
0x18000133a  mov     rcx, [rax]
0x18000133d  test    rcx, rcx
0x180001340  jz      short loc_180001359
0x180001342  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001346  inc     rax
0x180001349  cmp     [rcx+rax*2], r8w
0x18000134e  jnz     short loc_180001346
0x180001350  lea     eax, ds:2[rax*2]
0x180001357  jmp     short loc_180001365
0x180001359  lea     rcx, dword_1800150AC
0x180001360  mov     eax, 2
0x180001365  mov     [rsp+78h+var_20], eax
0x180001369  xor     r9d, r9d
0x18000136c  lea     rax, [rsp+78h+var_48]
0x180001371  mov     [rsp+78h+var_28], rcx
0x180001376  mov     [rsp+78h+var_50], rax
0x18000137b  lea     rcx, dword_18001C010
0x180001382  mov     [rsp+78h+var_58], 3
0x18000138a  mov     [rsp+78h+var_1C], r8d
0x18000138f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001394  mov     rcx, [rsp+78h+var_18]
0x180001399  xor     rcx, rsp; StackCookie
0x18000139c  call    __security_check_cookie
0x1800013a1  add     rsp, 78h
0x1800013a5  retn
```
