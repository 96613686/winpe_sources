# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001010`
- end: `0x1400010bd`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140028f40`
- `0x14003003c`

## callees

- `0x140001010`
- `0x1400010f4`
- `0x14001adc0`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int **a6)
{
  int *v6; // rax
  __int64 v7; // rcx
  int v9; // ecx
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-58h] BYREF
  __int64 v12; // [rsp+50h] [rbp-38h]
  __int64 v13; // [rsp+58h] [rbp-30h]
  int *v14; // [rsp+60h] [rbp-28h]
  int v15; // [rsp+68h] [rbp-20h]
  int v16; // [rsp+6Ch] [rbp-1Ch]

  v6 = *a6;
  if ( *a6 )
  {
    v7 = -1;
    while ( *((_WORD *)v6 + ++v7) != 0 )
      ;
    v9 = 2 * v7 + 2;
  }
  else
  {
    v6 = &dword_14001D99C;
    v9 = 2;
  }
  v14 = v6;
  v15 = v9;
  v12 = a5;
  v16 = 0;
  v13 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140022000, a2, 0, 0, 4u, &v11);
}

```

## disassembly

```asm
0x140001010  sub     rsp, 88h
0x140001017  mov     rax, cs:__security_cookie
0x14000101e  xor     rax, rsp
0x140001021  mov     [rsp+88h+var_18], rax
0x140001026  mov     rax, [rsp+88h+arg_28]
0x14000102e  mov     rax, [rax]
0x140001031  test    rax, rax
0x140001034  jz      short loc_140001052
0x140001036  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000103d  cmp     word ptr [rax+rcx*2+2], 0
0x140001043  lea     rcx, [rcx+1]
0x140001047  jnz     short loc_14000103D
0x140001049  lea     ecx, ds:2[rcx*2]
0x140001050  jmp     short loc_14000105E
0x140001052  lea     rax, dword_14001D99C
0x140001059  mov     ecx, 2
0x14000105e  mov     [rsp+88h+var_28], rax
0x140001063  xor     r9d, r9d
0x140001066  mov     rax, [rsp+88h+arg_20]
0x14000106e  xor     r8d, r8d
0x140001071  mov     [rsp+88h+var_20], ecx
0x140001075  xor     ecx, ecx
0x140001077  mov     [rsp+88h+var_38], rax
0x14000107c  lea     rax, [rsp+88h+var_58]
0x140001081  mov     [rsp+88h+var_1C], ecx
0x140001085  lea     rcx, dword_140022000
0x14000108c  mov     [rsp+88h+var_60], rax
0x140001091  mov     [rsp+88h+var_68], 4
0x140001099  mov     [rsp+88h+var_30], 8
0x1400010a2  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400010a7  mov     rcx, [rsp+88h+var_18]
0x1400010ac  xor     rcx, rsp; StackCookie
0x1400010af  call    __security_check_cookie
0x1400010b4  add     rsp, 88h
0x1400010bb  retn
```
