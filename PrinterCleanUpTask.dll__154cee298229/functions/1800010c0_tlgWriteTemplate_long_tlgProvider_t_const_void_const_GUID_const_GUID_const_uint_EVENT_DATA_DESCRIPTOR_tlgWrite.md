# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800010c0`
- end: `0x1800011de`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, const WCHAR **, const WCHAR **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007a74`

## callees

- `0x1800010c0`
- `0x180001918`
- `0x180002020`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const WCHAR **a6,
        const WCHAR **a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v11; // rcx
  int v12; // r8d
  const WCHAR *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const WCHAR *v16; // rdx
  __int64 v17; // rax
  const unsigned __int16 *v18; // rdx
  int v19; // ecx
  _BYTE v21[32]; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-31h]
  int v23; // [rsp+58h] [rbp-29h]
  int v24; // [rsp+5Ch] [rbp-25h]
  const WCHAR *v25; // [rsp+60h] [rbp-21h]
  int v26; // [rsp+68h] [rbp-19h]
  int v27; // [rsp+6Ch] [rbp-15h]
  const WCHAR *v28; // [rsp+70h] [rbp-11h]
  int v29; // [rsp+78h] [rbp-9h]
  int v30; // [rsp+7Ch] [rbp-5h]
  __int64 v31; // [rsp+80h] [rbp-1h]
  __int64 v32; // [rsp+88h] [rbp+7h]
  __int64 v33; // [rsp+90h] [rbp+Fh]
  __int64 v34; // [rsp+98h] [rbp+17h]

  v33 = a9;
  v31 = a8;
  v11 = -1;
  v12 = 2;
  v34 = 8;
  v32 = 4;
  v13 = *a7;
  if ( *a7 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = &LocaleName;
    v15 = 2;
  }
  v29 = v15;
  v28 = v13;
  v30 = 0;
  v16 = *a6;
  if ( *a6 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    v12 = 2 * v17 + 2;
  }
  else
  {
    v16 = &LocaleName;
  }
  v25 = v16;
  v26 = v12;
  v27 = 0;
  v18 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v18 + v11) );
    v19 = v11 + 1;
  }
  else
  {
    v18 = &dword_18001A274;
    v19 = 1;
  }
  v22 = v18;
  v23 = v19;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 7, v21);
}

```

## disassembly

```asm
0x1800010c0  push    rbp
0x1800010c2  lea     rbp, [rsp-2Fh]
0x1800010c7  sub     rsp, 0B0h
0x1800010ce  mov     rax, cs:__security_cookie
0x1800010d5  xor     rax, rsp
0x1800010d8  mov     [rbp+2Fh+var_10], rax
0x1800010dc  mov     rax, [rbp+2Fh+arg_40]
0x1800010e0  xor     r9d, r9d
0x1800010e3  mov     [rbp+2Fh+var_20], rax
0x1800010e7  mov     r11, rdx
0x1800010ea  mov     rax, [rbp+2Fh+arg_38]
0x1800010ee  mov     r10, rcx
0x1800010f1  mov     [rbp+2Fh+var_30], rax
0x1800010f5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800010f9  mov     rax, [rbp+2Fh+arg_30]
0x1800010fd  lea     r8d, [r9+2]
0x180001101  mov     [rbp+2Fh+var_18], 8
0x180001109  mov     [rbp+2Fh+var_28], 4
0x180001111  mov     rdx, [rax]
0x180001114  test    rdx, rdx
0x180001117  jz      short loc_18000112F
0x180001119  mov     rax, rcx
0x18000111c  inc     rax
0x18000111f  cmp     [rdx+rax*2], r9w
0x180001124  jnz     short loc_18000111C
0x180001126  lea     eax, ds:2[rax*2]
0x18000112d  jmp     short loc_180001139
0x18000112f  lea     rdx, LocaleName
0x180001136  mov     eax, r8d
0x180001139  mov     [rbp+2Fh+var_38], eax
0x18000113c  mov     rax, [rbp+2Fh+arg_28]
0x180001140  mov     [rbp+2Fh+var_40], rdx
0x180001144  mov     [rbp+2Fh+var_34], r9d
0x180001148  mov     rdx, [rax]
0x18000114b  test    rdx, rdx
0x18000114e  jz      short loc_180001167
0x180001150  mov     rax, rcx
0x180001153  inc     rax
0x180001156  cmp     [rdx+rax*2], r9w
0x18000115b  jnz     short loc_180001153
0x18000115d  lea     r8d, ds:2[rax*2]
0x180001165  jmp     short loc_18000116E
0x180001167  lea     rdx, LocaleName
0x18000116e  mov     rax, [rbp+2Fh+arg_20]
0x180001172  mov     [rbp+2Fh+var_50], rdx
0x180001176  mov     [rbp+2Fh+var_48], r8d
0x18000117a  mov     [rbp+2Fh+var_44], r9d
0x18000117e  mov     rdx, [rax]
0x180001181  test    rdx, rdx
0x180001184  jz      short loc_180001193
0x180001186  inc     rcx
0x180001189  cmp     [rdx+rcx], r9b
0x18000118d  jnz     short loc_180001186
0x18000118f  inc     ecx
0x180001191  jmp     short loc_18000119F
0x180001193  lea     rdx, dword_18001A274
0x18000119a  mov     ecx, 1
0x18000119f  lea     rax, [rbp+2Fh+var_80]
0x1800011a3  mov     [rbp+2Fh+var_60], rdx
0x1800011a7  mov     [rbp+2Fh+var_58], ecx
0x1800011aa  xor     r8d, r8d
0x1800011ad  mov     [rsp+0B0h+var_88], rax
0x1800011b2  mov     rdx, r11
0x1800011b5  mov     rcx, r10
0x1800011b8  mov     [rsp+0B0h+var_90], 7
0x1800011c0  mov     [rbp+2Fh+var_54], r9d
0x1800011c4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011c9  mov     rcx, [rbp+2Fh+var_10]
0x1800011cd  xor     rcx, rsp; StackCookie
0x1800011d0  call    __security_check_cookie
0x1800011d5  add     rsp, 0B0h
0x1800011dc  pop     rbp
0x1800011dd  retn
```
