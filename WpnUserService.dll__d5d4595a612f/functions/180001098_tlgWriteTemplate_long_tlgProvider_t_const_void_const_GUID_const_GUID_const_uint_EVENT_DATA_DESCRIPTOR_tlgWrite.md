# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001098`
- end: `0x18000113c`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 **, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007efc`
- `0x180007f84`

## callees

- `0x180001098`
- `0x180001bdc`
- `0x180002bc0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6)
{
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-58h] BYREF
  __int64 *v12; // [rsp+50h] [rbp-38h]
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
    v7 = &qword_1800142D0;
    v9 = 2;
  }
  v13 = v9;
  v12 = v7;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 4, v11);
}

```

## disassembly

```asm
0x180001098  sub     rsp, 88h
0x18000109f  mov     rax, cs:__security_cookie
0x1800010a6  xor     rax, rsp
0x1800010a9  mov     [rsp+88h+var_18], rax
0x1800010ae  mov     rax, [rsp+88h+arg_28]
0x1800010b6  mov     r10, rcx
0x1800010b9  mov     [rsp+88h+var_28], rax
0x1800010be  xor     r8d, r8d
0x1800010c1  mov     rax, [rsp+88h+arg_20]
0x1800010c9  mov     r9d, 4
0x1800010cf  mov     [rsp+88h+var_20], r9
0x1800010d4  mov     rcx, [rax]
0x1800010d7  test    rcx, rcx
0x1800010da  jz      short loc_1800010F3
0x1800010dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800010e0  inc     rax
0x1800010e3  cmp     [rcx+rax*2], r8w
0x1800010e8  jnz     short loc_1800010E0
0x1800010ea  lea     eax, ds:2[rax*2]
0x1800010f1  jmp     short loc_1800010FF
0x1800010f3  lea     rcx, qword_1800142D0
0x1800010fa  mov     eax, 2
0x1800010ff  mov     [rsp+88h+var_30], eax
0x180001103  lea     rax, [rsp+88h+var_58]
0x180001108  mov     [rsp+88h+var_60], rax
0x18000110d  mov     [rsp+88h+var_68], r9d
0x180001112  xor     r9d, r9d
0x180001115  mov     [rsp+88h+var_38], rcx
0x18000111a  mov     rcx, r10
0x18000111d  mov     [rsp+88h+var_2C], r8d
0x180001122  call    _tlgWriteTransfer_EventWriteTransfer
0x180001127  mov     rcx, [rsp+88h+var_18]
0x18000112c  xor     rcx, rsp; StackCookie
0x18000112f  call    __security_check_cookie
0x180001134  add     rsp, 88h
0x18000113b  retn
```
