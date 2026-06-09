# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x180001010`
- end: `0x18000109f`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007354`

## callees

- `0x180001010`
- `0x1800017d8`
- `0x180001e00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5)
{
  int *v5; // rax
  __int64 v6; // r8
  int v8; // r8d
  _BYTE v10[32]; // [rsp+30h] [rbp-48h] BYREF
  int *v11; // [rsp+50h] [rbp-28h]
  int v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    while ( *((_WORD *)v5 + ++v6) != 0 )
      ;
    v8 = 2 * v6 + 2;
  }
  else
  {
    v5 = &dword_18000B8A4;
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
0x180001010  sub     rsp, 78h
0x180001014  mov     rax, cs:__security_cookie
0x18000101b  xor     rax, rsp
0x18000101e  mov     [rsp+78h+var_18], rax
0x180001023  mov     rax, [rsp+78h+arg_20]
0x18000102b  mov     rax, [rax]
0x18000102e  test    rax, rax
0x180001031  jz      short loc_180001051
0x180001033  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000103a  cmp     word ptr [rax+r8*2+2], 0
0x180001041  lea     r8, [r8+1]
0x180001045  jnz     short loc_18000103A
0x180001047  lea     r8d, ds:2[r8*2]
0x18000104f  jmp     short loc_18000105E
0x180001051  lea     rax, dword_18000B8A4
0x180001058  mov     r8d, 2
0x18000105e  mov     [rsp+78h+var_28], rax
0x180001063  xor     r9d, r9d
0x180001066  lea     rax, [rsp+78h+var_48]
0x18000106b  mov     [rsp+78h+var_20], r8d
0x180001070  mov     [rsp+78h+var_50], rax
0x180001075  xor     r8d, r8d
0x180001078  mov     [rsp+78h+var_58], 3
0x180001080  mov     [rsp+78h+var_1C], 0
0x180001088  call    _tlgWriteTransfer_EventWriteTransfer
0x18000108d  mov     rcx, [rsp+78h+var_18]
0x180001092  xor     rcx, rsp; StackCookie
0x180001095  call    __security_check_cookie
0x18000109a  add     rsp, 78h
0x18000109e  retn
```
