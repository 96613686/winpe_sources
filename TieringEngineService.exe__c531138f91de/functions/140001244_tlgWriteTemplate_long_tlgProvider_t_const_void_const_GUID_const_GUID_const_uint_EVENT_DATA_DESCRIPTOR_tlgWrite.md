# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001244`
- end: `0x140001364`
- name: `??$Write@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@55@Z`
- size: `288`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned __int16 **, __int64 **, __int64, __int64 **, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140019ad8`
- `0x14001a270`

## callees

- `0x14000108c`
- `0x140001244`
- `0x14003fbb0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 **a5,
        __int64 **a6,
        __int64 a7,
        __int64 **a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v11; // rcx
  __int64 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 *v15; // rdx
  int v16; // ecx
  int v17; // ecx
  _BYTE v19[32]; // [rsp+30h] [rbp-79h] BYREF
  _DWORD *v20; // [rsp+50h] [rbp-59h]
  __int64 v21; // [rsp+58h] [rbp-51h]
  __int64 v22; // [rsp+60h] [rbp-49h]
  _DWORD v23[2]; // [rsp+68h] [rbp-41h] BYREF
  __int64 *v24; // [rsp+70h] [rbp-39h]
  int v25; // [rsp+78h] [rbp-31h]
  int v26; // [rsp+7Ch] [rbp-2Dh]
  __int64 v27; // [rsp+80h] [rbp-29h]
  __int64 v28; // [rsp+88h] [rbp-21h]
  __int64 *v29; // [rsp+90h] [rbp-19h]
  int v30; // [rsp+98h] [rbp-11h]
  int v31; // [rsp+9Ch] [rbp-Dh]
  __int64 v32; // [rsp+A0h] [rbp-9h]
  __int64 v33; // [rsp+A8h] [rbp-1h]
  __int64 v34; // [rsp+B0h] [rbp+7h]
  __int64 v35; // [rsp+B8h] [rbp+Fh]

  v34 = a10;
  v11 = -1;
  v32 = a9;
  v35 = 4;
  v33 = 4;
  v12 = *a8;
  if ( *a8 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v12 = &qword_140044A80;
    v14 = 1;
  }
  v30 = v14;
  v27 = a7;
  v29 = v12;
  v31 = 0;
  v28 = 4;
  v15 = *a6;
  if ( *a6 )
  {
    do
      ++v11;
    while ( *((_WORD *)v15 + v11) );
    v16 = 2 * v11 + 2;
  }
  else
  {
    v15 = &qword_140043BD0;
    v16 = 2;
  }
  v24 = v15;
  v20 = v23;
  v25 = v16;
  v21 = 2;
  v26 = 0;
  v17 = **a5;
  v22 = *((_QWORD *)*a5 + 1);
  v23[0] = v17;
  v23[1] = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_14004C098, a2, 0, 0, 9, v19);
}

```

## disassembly

```asm
0x140001244  push    rbp
0x140001246  lea     rbp, [rsp-27h]
0x14000124b  sub     rsp, 0D0h
0x140001252  mov     rax, cs:__security_cookie
0x140001259  xor     rax, rsp
0x14000125c  mov     [rbp+27h+var_10], rax
0x140001260  mov     rax, [rbp+27h+arg_48]
0x140001264  mov     r10, rdx
0x140001267  mov     [rbp+27h+var_20], rax
0x14000126b  xor     r8d, r8d
0x14000126e  mov     rax, [rbp+27h+arg_40]
0x140001272  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001276  mov     [rbp+27h+var_30], rax
0x14000127a  mov     rax, [rbp+27h+arg_38]
0x14000127e  mov     [rbp+27h+var_18], 4
0x140001286  mov     [rbp+27h+var_28], 4
0x14000128e  mov     rdx, [rax]
0x140001291  test    rdx, rdx
0x140001294  jz      short loc_1400012A6
0x140001296  mov     rax, rcx
0x140001299  inc     rax
0x14000129c  cmp     [rdx+rax], r8b
0x1400012a0  jnz     short loc_140001299
0x1400012a2  inc     eax
0x1400012a4  jmp     short loc_1400012B2
0x1400012a6  lea     rdx, qword_140044A80
0x1400012ad  mov     eax, 1
0x1400012b2  mov     [rbp+27h+var_38], eax
0x1400012b5  mov     r9d, 2
0x1400012bb  mov     rax, [rbp+27h+arg_30]
0x1400012bf  mov     [rbp+27h+var_50], rax
0x1400012c3  mov     rax, [rbp+27h+arg_28]
0x1400012c7  mov     [rbp+27h+var_40], rdx
0x1400012cb  mov     [rbp+27h+var_34], r8d
0x1400012cf  mov     [rbp+27h+var_48], 4
0x1400012d7  mov     rdx, [rax]
0x1400012da  test    rdx, rdx
0x1400012dd  jz      short loc_1400012F2
0x1400012df  inc     rcx
0x1400012e2  cmp     [rdx+rcx*2], r8w
0x1400012e7  jnz     short loc_1400012DF
0x1400012e9  lea     ecx, ds:2[rcx*2]
0x1400012f0  jmp     short loc_1400012FC
0x1400012f2  lea     rdx, qword_140043BD0
0x1400012f9  mov     ecx, r9d
0x1400012fc  mov     [rbp+27h+var_60], rdx
0x140001300  lea     rax, [rbp+27h+var_68]
0x140001304  mov     [rbp+27h+var_80], rax
0x140001308  mov     rdx, r10
0x14000130b  mov     rax, [rbp+27h+arg_20]
0x14000130f  mov     [rbp+27h+var_58], ecx
0x140001312  mov     [rbp+27h+var_78], r9
0x140001316  xor     r9d, r9d
0x140001319  mov     [rbp+27h+var_54], r8d
0x14000131d  mov     rax, [rax]
0x140001320  movzx   ecx, word ptr [rax]
0x140001323  mov     rax, [rax+8]
0x140001327  mov     [rbp+27h+var_70], rax
0x14000132b  lea     rax, [rbp+27h+var_A0]
0x14000132f  mov     [rbp+27h+var_68], ecx
0x140001332  lea     rcx, dword_14004C098
0x140001339  mov     [rsp+0D0h+var_A8], rax
0x14000133e  mov     [rsp+0D0h+var_B0], 9
0x140001346  mov     [rbp+27h+var_64], r8d
0x14000134a  call    _tlgWriteTransfer_EventWriteTransfer
0x14000134f  mov     rcx, [rbp+27h+var_10]
0x140001353  xor     rcx, rsp; StackCookie
0x140001356  call    __security_check_cookie
0x14000135b  add     rsp, 0D0h
0x140001362  pop     rbp
0x140001363  retn
```
