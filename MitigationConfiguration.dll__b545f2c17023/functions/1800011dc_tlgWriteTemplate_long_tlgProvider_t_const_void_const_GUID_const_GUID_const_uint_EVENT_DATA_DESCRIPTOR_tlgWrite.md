# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800011dc`
- end: `0x1800012b3`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z`
- size: `215`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013468`

## callees

- `0x18000113c`
- `0x1800011dc`
- `0x180001c00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
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
0x1800011dc  sub     rsp, 88h
0x1800011e3  mov     rax, cs:__security_cookie
0x1800011ea  xor     rax, rsp
0x1800011ed  mov     [rsp+88h+var_18], rax
0x1800011f2  mov     rax, [rsp+88h+arg_28]
0x1800011fa  mov     r10, rdx
0x1800011fd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001201  xor     r9d, r9d
0x180001204  mov     r8d, 2
0x18000120a  mov     rdx, [rax]
0x18000120d  test    rdx, rdx
0x180001210  jz      short loc_180001228
0x180001212  mov     rax, rcx
0x180001215  inc     rax
0x180001218  cmp     [rdx+rax*2], r9w
0x18000121d  jnz     short loc_180001215
0x18000121f  lea     eax, ds:2[rax*2]
0x180001226  jmp     short loc_180001232
0x180001228  lea     rdx, qword_180018390
0x18000122f  mov     eax, r8d
0x180001232  mov     [rsp+88h+var_20], eax
0x180001236  mov     rax, [rsp+88h+arg_20]
0x18000123e  mov     [rsp+88h+var_28], rdx
0x180001243  mov     [rsp+88h+var_1C], r9d
0x180001248  mov     rdx, [rax]
0x18000124b  test    rdx, rdx
0x18000124e  jz      short loc_180001264
0x180001250  inc     rcx
0x180001253  cmp     [rdx+rcx*2], r9w
0x180001258  jnz     short loc_180001250
0x18000125a  lea     r8d, ds:2[rcx*2]
0x180001262  jmp     short loc_18000126B
0x180001264  lea     rdx, qword_180018390
0x18000126b  lea     rax, [rsp+88h+var_58]
0x180001270  mov     [rsp+88h+var_38], rdx
0x180001275  mov     [rsp+88h+var_30], r8d
0x18000127a  lea     rcx, dword_18001C038
0x180001281  mov     [rsp+88h+var_60], rax
0x180001286  xor     r8d, r8d
0x180001289  mov     rdx, r10
0x18000128c  mov     [rsp+88h+var_68], 4
0x180001294  mov     [rsp+88h+var_2C], r9d
0x180001299  call    _tlgWriteTransfer_EventWriteTransfer
0x18000129e  mov     rcx, [rsp+88h+var_18]
0x1800012a3  xor     rcx, rsp; StackCookie
0x1800012a6  call    __security_check_cookie
0x1800012ab  add     rsp, 88h
0x1800012b2  retn
```
