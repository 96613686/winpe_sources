# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)

- ea: `0x18000108c`
- end: `0x180001112`
- name: `??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180009430`
- `0x180009800`
- `0x18000dd4c`
- `0x1800103d0`

## callees

- `0x18000108c`
- `0x1800011c4`
- `0x180010f80`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5)
{
  int *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-48h] BYREF
  int *v11; // [rsp+50h] [rbp-28h]
  int v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+5Ch] [rbp-1Ch]

  v6 = *a5;
  if ( *a5 )
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
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 3, v10);
}

```

## disassembly

```asm
0x18000108c  sub     rsp, 78h
0x180001090  mov     rax, cs:__security_cookie
0x180001097  xor     rax, rsp
0x18000109a  mov     [rsp+78h+var_18], rax
0x18000109f  mov     rax, [rsp+78h+arg_20]
0x1800010a7  mov     r10, rcx
0x1800010aa  xor     r11d, r11d
0x1800010ad  mov     rcx, [rax]
0x1800010b0  test    rcx, rcx
0x1800010b3  jz      short loc_1800010CC
0x1800010b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800010b9  inc     rax
0x1800010bc  cmp     [rcx+rax*2], r11w
0x1800010c1  jnz     short loc_1800010B9
0x1800010c3  lea     eax, ds:2[rax*2]
0x1800010ca  jmp     short loc_1800010D8
0x1800010cc  lea     rcx, dword_18001490C
0x1800010d3  mov     eax, 2
0x1800010d8  mov     [rsp+78h+var_20], eax
0x1800010dc  lea     rax, [rsp+78h+var_48]
0x1800010e1  mov     [rsp+78h+var_28], rcx
0x1800010e6  mov     rcx, r10
0x1800010e9  mov     [rsp+78h+var_50], rax
0x1800010ee  mov     [rsp+78h+var_58], 3
0x1800010f6  mov     [rsp+78h+var_1C], r11d
0x1800010fb  call    _tlgWriteTransfer_EventWriteTransfer
0x180001100  mov     rcx, [rsp+78h+var_18]
0x180001105  xor     rcx, rsp; StackCookie
0x180001108  call    __security_check_cookie
0x18000110d  add     rsp, 78h
0x180001111  retn
```
