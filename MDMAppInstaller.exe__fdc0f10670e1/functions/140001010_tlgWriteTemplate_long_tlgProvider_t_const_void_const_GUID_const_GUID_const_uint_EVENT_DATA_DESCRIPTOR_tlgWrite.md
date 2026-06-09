# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x140001010`
- end: `0x14000109f`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const OLECHAR **)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000740c`
- `0x1400074d4`
- `0x14000759c`
- `0x14000767c`
- `0x14000775c`

## callees

- `0x140001010`
- `0x1400017d8`
- `0x14001a8d0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const OLECHAR **a5)
{
  const OLECHAR *v5; // rax
  __int64 v6; // r8
  int v8; // r8d
  _BYTE v10[32]; // [rsp+30h] [rbp-48h] BYREF
  const OLECHAR *v11; // [rsp+50h] [rbp-28h]
  int v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    while ( v5[++v6] != 0 )
      ;
    v8 = 2 * v6 + 2;
  }
  else
  {
    v5 = &word_14001E5B4;
    v8 = 2;
  }
  v11 = v5;
  v12 = v8;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 3, v10);
}

```

## disassembly

```asm
0x140001010  sub     rsp, 78h
0x140001014  mov     rax, cs:__security_cookie
0x14000101b  xor     rax, rsp
0x14000101e  mov     [rsp+78h+var_18], rax
0x140001023  mov     rax, [rsp+78h+arg_20]
0x14000102b  mov     rax, [rax]
0x14000102e  test    rax, rax
0x140001031  jz      short loc_140001051
0x140001033  mov     r8, 0FFFFFFFFFFFFFFFFh
0x14000103a  cmp     word ptr [rax+r8*2+2], 0
0x140001041  lea     r8, [r8+1]
0x140001045  jnz     short loc_14000103A
0x140001047  lea     r8d, ds:2[r8*2]
0x14000104f  jmp     short loc_14000105E
0x140001051  lea     rax, word_14001E5B4
0x140001058  mov     r8d, 2
0x14000105e  mov     [rsp+78h+var_28], rax
0x140001063  xor     r9d, r9d
0x140001066  lea     rax, [rsp+78h+var_48]
0x14000106b  mov     [rsp+78h+var_20], r8d
0x140001070  mov     [rsp+78h+var_50], rax
0x140001075  xor     r8d, r8d
0x140001078  mov     [rsp+78h+var_58], 3
0x140001080  mov     [rsp+78h+var_1C], 0
0x140001088  call    _tlgWriteTransfer_EventWriteTransfer
0x14000108d  mov     rcx, [rsp+78h+var_18]
0x140001092  xor     rcx, rsp; StackCookie
0x140001095  call    __security_check_cookie
0x14000109a  add     rsp, 78h
0x14000109e  retn
```
