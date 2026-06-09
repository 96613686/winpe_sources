# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001010`
- end: `0x1800010b7`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const WCHAR **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007a04`
- `0x180010a80`

## callees

- `0x180001010`
- `0x180001918`
- `0x180002020`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const WCHAR **a5,
        __int64 a6)
{
  const WCHAR *v6; // rax
  __int64 v7; // r8
  int v9; // r8d
  _BYTE v11[32]; // [rsp+30h] [rbp-58h] BYREF
  const WCHAR *v12; // [rsp+50h] [rbp-38h]
  int v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+5Ch] [rbp-2Ch]
  __int64 v15; // [rsp+60h] [rbp-28h]
  __int64 v16; // [rsp+68h] [rbp-20h]

  v15 = a6;
  v16 = 8;
  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    while ( v6[++v7] != 0 )
      ;
    v9 = 2 * v7 + 2;
  }
  else
  {
    v6 = &LocaleName;
    v9 = 2;
  }
  v12 = v6;
  v13 = v9;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 4, v11);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 88h
0x180001017  mov     rax, cs:__security_cookie
0x18000101e  xor     rax, rsp
0x180001021  mov     [rsp+88h+var_18], rax
0x180001026  mov     rax, [rsp+88h+arg_28]
0x18000102e  xor     r9d, r9d
0x180001031  mov     [rsp+88h+var_28], rax
0x180001036  mov     rax, [rsp+88h+arg_20]
0x18000103e  mov     [rsp+88h+var_20], 8
0x180001047  mov     rax, [rax]
0x18000104a  test    rax, rax
0x18000104d  jz      short loc_18000106C
0x18000104f  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180001056  cmp     [rax+r8*2+2], r9w
0x18000105c  lea     r8, [r8+1]
0x180001060  jnz     short loc_180001056
0x180001062  lea     r8d, ds:2[r8*2]
0x18000106a  jmp     short loc_180001079
0x18000106c  lea     rax, LocaleName
0x180001073  mov     r8d, 2
0x180001079  mov     [rsp+88h+var_38], rax
0x18000107e  lea     rax, [rsp+88h+var_58]
0x180001083  mov     [rsp+88h+var_30], r8d
0x180001088  xor     r8d, r8d
0x18000108b  mov     [rsp+88h+var_60], rax
0x180001090  mov     [rsp+88h+var_68], 4
0x180001098  mov     [rsp+88h+var_2C], r9d
0x18000109d  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010a2  mov     rcx, [rsp+88h+var_18]
0x1800010a7  xor     rcx, rsp; StackCookie
0x1800010aa  call    __security_check_cookie
0x1800010af  add     rsp, 88h
0x1800010b6  retn
```
