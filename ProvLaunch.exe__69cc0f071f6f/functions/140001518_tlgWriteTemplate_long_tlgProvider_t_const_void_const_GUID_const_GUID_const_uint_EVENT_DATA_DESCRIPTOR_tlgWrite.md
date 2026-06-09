# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x140001518`
- end: `0x1400015a2`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140008b38`
- `0x140008f54`
- `0x1400090ec`

## callees

- `0x1400011ac`
- `0x140001518`
- `0x14000a370`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5)
{
  int *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  _BYTE v9[32]; // [rsp+30h] [rbp-48h] BYREF
  int *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)v5 + v6) );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v5 = &dword_14000C834;
    v7 = 2;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140010000, a2, 0, 0, 3, v9);
}

```

## disassembly

```asm
0x140001518  sub     rsp, 78h
0x14000151c  mov     rax, cs:__security_cookie
0x140001523  xor     rax, rsp
0x140001526  mov     [rsp+78h+var_18], rax
0x14000152b  mov     rax, [rsp+78h+arg_20]
0x140001533  xor     r8d, r8d
0x140001536  mov     rcx, [rax]
0x140001539  test    rcx, rcx
0x14000153c  jz      short loc_140001555
0x14000153e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001542  inc     rax
0x140001545  cmp     [rcx+rax*2], r8w
0x14000154a  jnz     short loc_140001542
0x14000154c  lea     eax, ds:2[rax*2]
0x140001553  jmp     short loc_140001561
0x140001555  lea     rcx, dword_14000C834
0x14000155c  mov     eax, 2
0x140001561  mov     [rsp+78h+var_20], eax
0x140001565  xor     r9d, r9d
0x140001568  lea     rax, [rsp+78h+var_48]
0x14000156d  mov     [rsp+78h+var_28], rcx
0x140001572  mov     [rsp+78h+var_50], rax
0x140001577  lea     rcx, dword_140010000
0x14000157e  mov     [rsp+78h+var_58], 3
0x140001586  mov     [rsp+78h+var_1C], r8d
0x14000158b  call    _tlgWriteTransfer_EventWriteTransfer
0x140001590  mov     rcx, [rsp+78h+var_18]
0x140001595  xor     rcx, rsp; StackCookie
0x140001598  call    __security_check_cookie
0x14000159d  add     rsp, 78h
0x1400015a1  retn
```
