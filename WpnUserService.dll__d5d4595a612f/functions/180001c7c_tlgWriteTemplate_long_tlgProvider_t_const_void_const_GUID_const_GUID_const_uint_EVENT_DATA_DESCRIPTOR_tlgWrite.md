# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001c7c`
- end: `0x180001d52`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z`
- size: `214`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 **, __int64 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e9e8`
- `0x18000edbc`

## callees

- `0x180001bdc`
- `0x180001c7c`
- `0x180002bc0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 **a6)
{
  __int64 v8; // rcx
  int v9; // r8d
  __int64 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  __int64 *v13; // rdx
  _BYTE v15[32]; // [rsp+30h] [rbp-58h] BYREF
  __int64 *v16; // [rsp+50h] [rbp-38h]
  int v17; // [rsp+58h] [rbp-30h]
  int v18; // [rsp+5Ch] [rbp-2Ch]
  __int64 *v19; // [rsp+60h] [rbp-28h]
  int v20; // [rsp+68h] [rbp-20h]
  int v21; // [rsp+6Ch] [rbp-1Ch]

  v8 = -1;
  v9 = 2;
  v10 = *a6;
  if ( *a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &qword_1800142D0;
    v12 = 2;
  }
  v20 = v12;
  v19 = v10;
  v21 = 0;
  v13 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_WORD *)v13 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v13 = &qword_1800142D0;
  }
  v16 = v13;
  v17 = v9;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 4, v15);
}

```

## disassembly

```asm
0x180001c7c  sub     rsp, 88h
0x180001c83  mov     rax, cs:__security_cookie
0x180001c8a  xor     rax, rsp
0x180001c8d  mov     [rsp+88h+var_18], rax
0x180001c92  mov     rax, [rsp+88h+arg_28]
0x180001c9a  mov     r11, rdx
0x180001c9d  mov     r10, rcx
0x180001ca0  xor     r9d, r9d
0x180001ca3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001ca7  mov     r8d, 2
0x180001cad  mov     rdx, [rax]
0x180001cb0  test    rdx, rdx
0x180001cb3  jz      short loc_180001CCB
0x180001cb5  mov     rax, rcx
0x180001cb8  inc     rax
0x180001cbb  cmp     [rdx+rax*2], r9w
0x180001cc0  jnz     short loc_180001CB8
0x180001cc2  lea     eax, ds:2[rax*2]
0x180001cc9  jmp     short loc_180001CD5
0x180001ccb  lea     rdx, qword_1800142D0
0x180001cd2  mov     eax, r8d
0x180001cd5  mov     [rsp+88h+var_20], eax
0x180001cd9  mov     rax, [rsp+88h+arg_20]
0x180001ce1  mov     [rsp+88h+var_28], rdx
0x180001ce6  mov     [rsp+88h+var_1C], r9d
0x180001ceb  mov     rdx, [rax]
0x180001cee  test    rdx, rdx
0x180001cf1  jz      short loc_180001D07
0x180001cf3  inc     rcx
0x180001cf6  cmp     [rdx+rcx*2], r9w
0x180001cfb  jnz     short loc_180001CF3
0x180001cfd  lea     r8d, ds:2[rcx*2]
0x180001d05  jmp     short loc_180001D0E
0x180001d07  lea     rdx, qword_1800142D0
0x180001d0e  lea     rax, [rsp+88h+var_58]
0x180001d13  mov     [rsp+88h+var_38], rdx
0x180001d18  mov     [rsp+88h+var_30], r8d
0x180001d1d  mov     rdx, r11
0x180001d20  mov     [rsp+88h+var_60], rax
0x180001d25  xor     r8d, r8d
0x180001d28  mov     rcx, r10
0x180001d2b  mov     [rsp+88h+var_68], 4
0x180001d33  mov     [rsp+88h+var_2C], r9d
0x180001d38  call    _tlgWriteTransfer_EventWriteTransfer
0x180001d3d  mov     rcx, [rsp+88h+var_18]
0x180001d42  xor     rcx, rsp; StackCookie
0x180001d45  call    __security_check_cookie
0x180001d4a  add     rsp, 88h
0x180001d51  retn
```
