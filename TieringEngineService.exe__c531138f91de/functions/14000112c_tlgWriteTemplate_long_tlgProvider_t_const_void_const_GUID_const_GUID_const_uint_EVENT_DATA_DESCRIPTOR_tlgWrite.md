# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000112c`
- end: `0x14000123c`
- name: `??$Write@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@5@Z`
- size: `272`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned __int16 **, __int64 **, __int64, __int64 **, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400192c4`
- `0x140019ad8`
- `0x14001a270`

## callees

- `0x14000108c`
- `0x14000112c`
- `0x14003fbb0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 **a5,
        __int64 **a6,
        __int64 a7,
        __int64 **a8,
        __int64 a9)
{
  __int64 v10; // rcx
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  __int64 *v14; // rdx
  int v15; // ecx
  int v16; // ecx
  _BYTE v18[32]; // [rsp+30h] [rbp-61h] BYREF
  _DWORD *v19; // [rsp+50h] [rbp-41h]
  __int64 v20; // [rsp+58h] [rbp-39h]
  __int64 v21; // [rsp+60h] [rbp-31h]
  _DWORD v22[2]; // [rsp+68h] [rbp-29h] BYREF
  __int64 *v23; // [rsp+70h] [rbp-21h]
  int v24; // [rsp+78h] [rbp-19h]
  int v25; // [rsp+7Ch] [rbp-15h]
  __int64 v26; // [rsp+80h] [rbp-11h]
  __int64 v27; // [rsp+88h] [rbp-9h]
  __int64 *v28; // [rsp+90h] [rbp-1h]
  int v29; // [rsp+98h] [rbp+7h]
  int v30; // [rsp+9Ch] [rbp+Bh]
  __int64 v31; // [rsp+A0h] [rbp+Fh]
  __int64 v32; // [rsp+A8h] [rbp+17h]

  v31 = a9;
  v10 = -1;
  v32 = 4;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &qword_140044A80;
    v13 = 1;
  }
  v29 = v13;
  v26 = a7;
  v28 = v11;
  v30 = 0;
  v27 = 4;
  v14 = *a6;
  if ( *a6 )
  {
    do
      ++v10;
    while ( *((_WORD *)v14 + v10) );
    v15 = 2 * v10 + 2;
  }
  else
  {
    v14 = &qword_140043BD0;
    v15 = 2;
  }
  v23 = v14;
  v19 = v22;
  v24 = v15;
  v20 = 2;
  v25 = 0;
  v16 = **a5;
  v21 = *((_QWORD *)*a5 + 1);
  v22[0] = v16;
  v22[1] = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_14004C098, a2, 0, 0, 8, v18);
}

```

## disassembly

```asm
0x14000112c  push    rbp
0x14000112e  lea     rbp, [rsp-2Fh]
0x140001133  sub     rsp, 0C0h
0x14000113a  mov     rax, cs:__security_cookie
0x140001141  xor     rax, rsp
0x140001144  mov     [rbp+2Fh+var_10], rax
0x140001148  mov     rax, [rbp+2Fh+arg_40]
0x14000114c  mov     r10, rdx
0x14000114f  mov     [rbp+2Fh+var_20], rax
0x140001153  xor     r8d, r8d
0x140001156  mov     rax, [rbp+2Fh+arg_38]
0x14000115a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000115e  mov     [rbp+2Fh+var_18], 4
0x140001166  mov     rdx, [rax]
0x140001169  test    rdx, rdx
0x14000116c  jz      short loc_14000117E
0x14000116e  mov     rax, rcx
0x140001171  inc     rax
0x140001174  cmp     [rdx+rax], r8b
0x140001178  jnz     short loc_140001171
0x14000117a  inc     eax
0x14000117c  jmp     short loc_14000118A
0x14000117e  lea     rdx, qword_140044A80
0x140001185  mov     eax, 1
0x14000118a  mov     [rbp+2Fh+var_28], eax
0x14000118d  mov     r9d, 2
0x140001193  mov     rax, [rbp+2Fh+arg_30]
0x140001197  mov     [rbp+2Fh+var_40], rax
0x14000119b  mov     rax, [rbp+2Fh+arg_28]
0x14000119f  mov     [rbp+2Fh+var_30], rdx
0x1400011a3  mov     [rbp+2Fh+var_24], r8d
0x1400011a7  mov     [rbp+2Fh+var_38], 4
0x1400011af  mov     rdx, [rax]
0x1400011b2  test    rdx, rdx
0x1400011b5  jz      short loc_1400011CA
0x1400011b7  inc     rcx
0x1400011ba  cmp     [rdx+rcx*2], r8w
0x1400011bf  jnz     short loc_1400011B7
0x1400011c1  lea     ecx, ds:2[rcx*2]
0x1400011c8  jmp     short loc_1400011D4
0x1400011ca  lea     rdx, qword_140043BD0
0x1400011d1  mov     ecx, r9d
0x1400011d4  mov     [rbp+2Fh+var_50], rdx
0x1400011d8  lea     rax, [rbp+2Fh+var_58]
0x1400011dc  mov     [rbp+2Fh+var_70], rax
0x1400011e0  mov     rdx, r10
0x1400011e3  mov     rax, [rbp+2Fh+arg_20]
0x1400011e7  mov     [rbp+2Fh+var_48], ecx
0x1400011ea  mov     [rbp+2Fh+var_68], r9
0x1400011ee  xor     r9d, r9d
0x1400011f1  mov     [rbp+2Fh+var_44], r8d
0x1400011f5  mov     rax, [rax]
0x1400011f8  movzx   ecx, word ptr [rax]
0x1400011fb  mov     rax, [rax+8]
0x1400011ff  mov     [rbp+2Fh+var_60], rax
0x140001203  lea     rax, [rbp+2Fh+var_90]
0x140001207  mov     [rbp+2Fh+var_58], ecx
0x14000120a  lea     rcx, dword_14004C098
0x140001211  mov     [rsp+0C0h+var_98], rax
0x140001216  mov     [rsp+0C0h+var_A0], 8
0x14000121e  mov     [rbp+2Fh+var_54], r8d
0x140001222  call    _tlgWriteTransfer_EventWriteTransfer
0x140001227  mov     rcx, [rbp+2Fh+var_10]
0x14000122b  xor     rcx, rsp; StackCookie
0x14000122e  call    __security_check_cookie
0x140001233  add     rsp, 0C0h
0x14000123a  pop     rbp
0x14000123b  retn
```
