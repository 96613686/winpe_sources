# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x140001008`
- end: `0x140001092`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1400059ac`
- `0x14000ad18`
- `0x14000b250`
- `0x14000b454`
- `0x14000ca40`
- `0x14000cd30`
- `0x14000d394`

## callees

- `0x140001008`
- `0x140001130`
- `0x14000ded0`

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
  return tlgWriteTransfer_EventWriteTransfer(&dword_140017048, a2, 0, 0);
}

```

## disassembly

```asm
0x140001008  sub     rsp, 78h
0x14000100c  mov     rax, cs:__security_cookie
0x140001013  xor     rax, rsp
0x140001016  mov     [rsp+78h+var_18], rax
0x14000101b  mov     rax, [rsp+78h+arg_20]
0x140001023  xor     r8d, r8d
0x140001026  mov     rcx, [rax]
0x140001029  test    rcx, rcx
0x14000102c  jz      short loc_140001045
0x14000102e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001032  inc     rax
0x140001035  cmp     [rcx+rax*2], r8w
0x14000103a  jnz     short loc_140001032
0x14000103c  lea     eax, ds:2[rax*2]
0x140001043  jmp     short loc_140001051
0x140001045  lea     rcx, qword_140011EC0
0x14000104c  mov     eax, 2
0x140001051  mov     [rsp+78h+var_20], eax
0x140001055  xor     r9d, r9d
0x140001058  lea     rax, [rsp+78h+var_48]
0x14000105d  mov     [rsp+78h+var_28], rcx
0x140001062  mov     [rsp+78h+var_50], rax
0x140001067  lea     rcx, dword_140017048
0x14000106e  mov     [rsp+78h+var_58], 3
0x140001076  mov     [rsp+78h+var_1C], r8d
0x14000107b  call    _tlgWriteTransfer_EventWriteTransfer
0x140001080  mov     rcx, [rsp+78h+var_18]
0x140001085  xor     rcx, rsp; StackCookie
0x140001088  call    __security_check_cookie
0x14000108d  add     rsp, 78h
0x140001091  retn
```
