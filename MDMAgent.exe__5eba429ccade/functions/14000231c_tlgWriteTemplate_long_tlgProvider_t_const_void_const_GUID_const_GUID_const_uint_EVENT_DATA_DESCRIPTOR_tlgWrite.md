# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)

- ea: `0x14000231c`
- end: `0x1400023bc`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017880`

## callees

- `0x140001f48`
- `0x14000231c`
- `0x140002930`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
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
    v6 = &byte_14001ACA1;
    v8 = 1;
  }
  v14 = v8;
  v11 = a5;
  v13 = v6;
  v15 = 0;
  v12 = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140024038, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x14000231c  sub     rsp, 88h
0x140002323  mov     rax, cs:__security_cookie
0x14000232a  xor     rax, rsp
0x14000232d  mov     [rsp+88h+var_18], rax
0x140002332  mov     rax, [rsp+88h+arg_28]
0x14000233a  xor     r8d, r8d
0x14000233d  mov     rcx, [rax]
0x140002340  test    rcx, rcx
0x140002343  jz      short loc_140002356
0x140002345  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002349  inc     rax
0x14000234c  cmp     [rcx+rax], r8b
0x140002350  jnz     short loc_140002349
0x140002352  inc     eax
0x140002354  jmp     short loc_140002362
0x140002356  lea     rcx, byte_14001ACA1
0x14000235d  mov     eax, 1
0x140002362  mov     [rsp+88h+var_20], eax
0x140002366  xor     r9d, r9d
0x140002369  mov     rax, [rsp+88h+arg_20]
0x140002371  mov     [rsp+88h+var_38], rax
0x140002376  lea     rax, [rsp+88h+var_58]
0x14000237b  mov     [rsp+88h+var_28], rcx
0x140002380  lea     rcx, dword_140024038
0x140002387  mov     [rsp+88h+var_60], rax
0x14000238c  mov     [rsp+88h+var_68], 4
0x140002394  mov     [rsp+88h+var_1C], r8d
0x140002399  mov     [rsp+88h+var_30], 8
0x1400023a2  call    _tlgWriteTransfer_EventWriteTransfer
0x1400023a7  mov     rcx, [rsp+88h+var_18]
0x1400023ac  xor     rcx, rsp; StackCookie
0x1400023af  call    __security_check_cookie
0x1400023b4  add     rsp, 88h
0x1400023bb  retn
```
