# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800018bc`
- end: `0x180001984`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a2c8`

## callees

- `0x180001010`
- `0x1800018bc`
- `0x1800050f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        unsigned __int16 **a6,
        __int64 a7)
{
  int v8; // edx
  int v9; // ecx
  int *v10; // rcx
  __int64 v11; // rax
  _BYTE v13[32]; // [rsp+30h] [rbp-31h] BYREF
  int *v14; // [rsp+50h] [rbp-11h]
  int v15; // [rsp+58h] [rbp-9h]
  int v16; // [rsp+5Ch] [rbp-5h]
  _DWORD *v17; // [rsp+60h] [rbp-1h]
  __int64 v18; // [rsp+68h] [rbp+7h]
  __int64 v19; // [rsp+70h] [rbp+Fh]
  _DWORD v20[2]; // [rsp+78h] [rbp+17h] BYREF
  __int64 v21; // [rsp+80h] [rbp+1Fh]
  __int64 v22; // [rsp+88h] [rbp+27h]

  v21 = a7;
  v22 = 8;
  v17 = v20;
  v8 = 2;
  v18 = 2;
  v9 = **a6;
  v19 = *((_QWORD *)*a6 + 1);
  v20[0] = v9;
  v20[1] = 0;
  v10 = *a5;
  if ( *a5 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v8 = 2 * v11 + 2;
  }
  else
  {
    v10 = &dword_180031EE4;
  }
  v14 = v10;
  v15 = v8;
  v16 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180040010, a2, 0, 0, 6, v13);
}

```

## disassembly

```asm
0x1800018bc  push    rbp
0x1800018be  lea     rbp, [rsp-3Fh]
0x1800018c3  sub     rsp, 0A0h
0x1800018ca  mov     rax, cs:__security_cookie
0x1800018d1  xor     rax, rsp
0x1800018d4  mov     [rbp+3Fh+var_10], rax
0x1800018d8  mov     rax, [rbp+3Fh+arg_30]
0x1800018dc  xor     r8d, r8d
0x1800018df  mov     [rbp+3Fh+var_20], rax
0x1800018e3  mov     r10, rdx
0x1800018e6  lea     rax, [rbp+3Fh+var_28]
0x1800018ea  mov     [rbp+3Fh+var_18], 8
0x1800018f2  mov     [rbp+3Fh+var_40], rax
0x1800018f6  mov     rax, [rbp+3Fh+arg_28]
0x1800018fa  lea     edx, [r8+2]
0x1800018fe  mov     [rbp+3Fh+var_38], rdx
0x180001902  mov     rax, [rax]
0x180001905  movzx   ecx, word ptr [rax]
0x180001908  mov     rax, [rax+8]
0x18000190c  mov     [rbp+3Fh+var_30], rax
0x180001910  mov     rax, [rbp+3Fh+arg_20]
0x180001914  mov     [rbp+3Fh+var_28], ecx
0x180001917  mov     [rbp+3Fh+var_24], r8d
0x18000191b  mov     rcx, [rax]
0x18000191e  test    rcx, rcx
0x180001921  jz      short loc_18000193A
0x180001923  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001927  inc     rax
0x18000192a  cmp     [rcx+rax*2], r8w
0x18000192f  jnz     short loc_180001927
0x180001931  lea     edx, ds:2[rax*2]
0x180001938  jmp     short loc_180001941
0x18000193a  lea     rcx, dword_180031EE4
0x180001941  lea     rax, [rbp+3Fh+var_70]
0x180001945  mov     [rbp+3Fh+var_50], rcx
0x180001949  mov     [rbp+3Fh+var_48], edx
0x18000194c  lea     rcx, dword_180040010
0x180001953  mov     [rsp+0A0h+var_78], rax
0x180001958  xor     r9d, r9d
0x18000195b  mov     rdx, r10
0x18000195e  mov     [rsp+0A0h+var_80], 6
0x180001966  mov     [rbp+3Fh+var_44], r8d
0x18000196a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000196f  mov     rcx, [rbp+3Fh+var_10]
0x180001973  xor     rcx, rsp; StackCookie
0x180001976  call    __security_check_cookie
0x18000197b  add     rsp, 0A0h
0x180001982  pop     rbp
0x180001983  retn
```
