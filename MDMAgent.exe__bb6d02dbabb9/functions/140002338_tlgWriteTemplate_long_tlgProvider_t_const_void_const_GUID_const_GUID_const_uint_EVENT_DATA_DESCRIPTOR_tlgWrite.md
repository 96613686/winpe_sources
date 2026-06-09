# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x140002338`
- end: `0x1400023d9`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018560`

## callees

- `0x140001f60`
- `0x140002338`
- `0x1400029c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]
  __int64 v12; // [rsp+58h] [rbp-30h]
  const unsigned __int16 *v13; // [rsp+60h] [rbp-28h]
  int v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+6Ch] [rbp-1Ch]

  v6 = *a6;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_BYTE *)v6 + v7) );
    v8 = v7 + 1;
  }
  else
  {
    v6 = &byte_14001BCA1;
    v8 = 1;
  }
  v14 = v8;
  v11 = a5;
  v13 = v6;
  v15 = 0;
  v12 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140025038, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x140002338  sub     rsp, 88h
0x14000233f  mov     rax, cs:__security_cookie
0x140002346  xor     rax, rsp
0x140002349  mov     [rsp+88h+var_18], rax
0x14000234e  mov     rax, [rsp+88h+arg_28]
0x140002356  xor     r8d, r8d
0x140002359  mov     rcx, [rax]
0x14000235c  test    rcx, rcx
0x14000235f  jz      short loc_140002372
0x140002361  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002365  inc     rax
0x140002368  cmp     [rcx+rax], r8b
0x14000236c  jnz     short loc_140002365
0x14000236e  inc     eax
0x140002370  jmp     short loc_14000237E
0x140002372  lea     rcx, byte_14001BCA1
0x140002379  mov     eax, 1
0x14000237e  mov     [rsp+88h+var_20], eax
0x140002382  xor     r9d, r9d
0x140002385  mov     rax, [rsp+88h+arg_20]
0x14000238d  mov     [rsp+88h+var_38], rax
0x140002392  lea     rax, [rsp+88h+var_58]
0x140002397  mov     [rsp+88h+var_28], rcx
0x14000239c  lea     rcx, dword_140025038
0x1400023a3  mov     [rsp+88h+var_60], rax
0x1400023a8  mov     [rsp+88h+var_68], 4
0x1400023b0  mov     [rsp+88h+var_1C], r8d
0x1400023b5  mov     [rsp+88h+var_30], 8
0x1400023be  call    _tlgWriteTransfer_EventWriteTransfer
0x1400023c3  mov     rcx, [rsp+88h+var_18]
0x1400023c8  xor     rcx, rsp; StackCookie
0x1400023cb  call    __security_check_cookie
0x1400023d0  add     rsp, 88h
0x1400023d7  retn
```
