# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001118`
- end: `0x1800011bb`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b6d8`
- `0x18000b8f8`

## callees

- `0x180001118`
- `0x1800011c4`
- `0x180010f80`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int **a6)
{
  int *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]
  __int64 v12; // [rsp+58h] [rbp-30h]
  int *v13; // [rsp+60h] [rbp-28h]
  int v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+6Ch] [rbp-1Ch]

  v6 = *a6;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)v6 + v7) );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &dword_18001490C;
    v8 = 2;
  }
  v14 = v8;
  v13 = v6;
  v11 = a5;
  v12 = 4;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180019000, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x180001118  sub     rsp, 88h
0x18000111f  mov     rax, cs:__security_cookie
0x180001126  xor     rax, rsp
0x180001129  mov     [rsp+88h+var_18], rax
0x18000112e  mov     rax, [rsp+88h+arg_28]
0x180001136  xor     r8d, r8d
0x180001139  mov     rcx, [rax]
0x18000113c  test    rcx, rcx
0x18000113f  jz      short loc_180001158
0x180001141  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001145  inc     rax
0x180001148  cmp     [rcx+rax*2], r8w
0x18000114d  jnz     short loc_180001145
0x18000114f  lea     eax, ds:2[rax*2]
0x180001156  jmp     short loc_180001164
0x180001158  lea     rcx, dword_18001490C
0x18000115f  mov     eax, 2
0x180001164  mov     [rsp+88h+var_20], eax
0x180001168  xor     r9d, r9d
0x18000116b  mov     rax, [rsp+88h+arg_20]
0x180001173  mov     [rsp+88h+var_28], rcx
0x180001178  mov     ecx, 4
0x18000117d  mov     [rsp+88h+var_38], rax
0x180001182  lea     rax, [rsp+88h+var_58]
0x180001187  mov     [rsp+88h+var_60], rax
0x18000118c  mov     [rsp+88h+var_68], ecx
0x180001190  mov     [rsp+88h+var_30], rcx
0x180001195  lea     rcx, dword_180019000
0x18000119c  mov     [rsp+88h+var_1C], r8d
0x1800011a1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011a6  mov     rcx, [rsp+88h+var_18]
0x1800011ab  xor     rcx, rsp; StackCookie
0x1800011ae  call    __security_check_cookie
0x1800011b3  add     rsp, 88h
0x1800011ba  retn
```
