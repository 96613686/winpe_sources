# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800015e4`
- end: `0x180001685`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dd4c`
- `0x18000e184`

## callees

- `0x1800011c4`
- `0x1800015e4`
- `0x180010f80`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 a6)
{
  int *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-58h] BYREF
  int *v12; // [rsp+50h] [rbp-38h]
  int v13; // [rsp+58h] [rbp-30h]
  int v14; // [rsp+5Ch] [rbp-2Ch]
  __int64 v15; // [rsp+60h] [rbp-28h]
  __int64 v16; // [rsp+68h] [rbp-20h]

  v15 = a6;
  v16 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)v7 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &dword_18001490C;
    v9 = 2;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 4, v11);
}

```

## disassembly

```asm
0x1800015e4  sub     rsp, 88h
0x1800015eb  mov     rax, cs:__security_cookie
0x1800015f2  xor     rax, rsp
0x1800015f5  mov     [rsp+88h+var_18], rax
0x1800015fa  mov     rax, [rsp+88h+arg_28]
0x180001602  mov     r10, rcx
0x180001605  mov     [rsp+88h+var_28], rax
0x18000160a  xor     r9d, r9d
0x18000160d  mov     rax, [rsp+88h+arg_20]
0x180001615  mov     r11d, 4
0x18000161b  mov     [rsp+88h+var_20], r11
0x180001620  mov     rcx, [rax]
0x180001623  test    rcx, rcx
0x180001626  jz      short loc_18000163F
0x180001628  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000162c  inc     rax
0x18000162f  cmp     [rcx+rax*2], r9w
0x180001634  jnz     short loc_18000162C
0x180001636  lea     eax, ds:2[rax*2]
0x18000163d  jmp     short loc_18000164B
0x18000163f  lea     rcx, dword_18001490C
0x180001646  mov     eax, 2
0x18000164b  mov     [rsp+88h+var_30], eax
0x18000164f  lea     rax, [rsp+88h+var_58]
0x180001654  mov     [rsp+88h+var_38], rcx
0x180001659  mov     rcx, r10
0x18000165c  mov     [rsp+88h+var_60], rax
0x180001661  mov     [rsp+88h+var_68], r11d
0x180001666  mov     [rsp+88h+var_2C], r9d
0x18000166b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001670  mov     rcx, [rsp+88h+var_18]
0x180001675  xor     rcx, rsp; StackCookie
0x180001678  call    __security_check_cookie
0x18000167d  add     rsp, 88h
0x180001684  retn
```
