# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800017f4`
- end: `0x180001912`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000af80`
- `0x18000b540`

## callees

- `0x18000163c`
- `0x1800017f4`
- `0x180002000`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 **a7,
        __int64 **a8,
        __int64 a9)
{
  __int64 v11; // rcx
  int v12; // r8d
  __int64 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  __int64 *v16; // rdx
  __int64 v17; // rax
  const unsigned __int16 *v18; // rdx
  int v19; // ecx
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-31h]
  int v23; // [rsp+58h] [rbp-29h]
  int v24; // [rsp+5Ch] [rbp-25h]
  __int64 v25; // [rsp+60h] [rbp-21h]
  __int64 v26; // [rsp+68h] [rbp-19h]
  __int64 *v27; // [rsp+70h] [rbp-11h]
  int v28; // [rsp+78h] [rbp-9h]
  int v29; // [rsp+7Ch] [rbp-5h]
  __int64 *v30; // [rsp+80h] [rbp-1h]
  int v31; // [rsp+88h] [rbp+7h]
  int v32; // [rsp+8Ch] [rbp+Bh]
  __int64 v33; // [rsp+90h] [rbp+Fh]
  __int64 v34; // [rsp+98h] [rbp+17h]

  v33 = a9;
  v11 = -1;
  v34 = 4;
  v12 = 2;
  v13 = *a8;
  if ( *a8 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v13 + v14) );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = &qword_1800105E0;
    v15 = 2;
  }
  v31 = v15;
  v30 = v13;
  v32 = 0;
  v16 = *a7;
  if ( *a7 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v16 + v17) );
    v12 = 2 * v17 + 2;
  }
  else
  {
    v16 = &qword_1800105E0;
  }
  v25 = a6;
  v27 = v16;
  v28 = v12;
  v29 = 0;
  v18 = *a5;
  v26 = 8;
  if ( v18 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v18 + v11) );
    v19 = v11 + 1;
  }
  else
  {
    v18 = &word_18000FE2A;
    v19 = 1;
  }
  v22 = v18;
  v23 = v19;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 7u, &v21);
}

```

## disassembly

```asm
0x1800017f4  push    rbp
0x1800017f6  lea     rbp, [rsp-2Fh]
0x1800017fb  sub     rsp, 0B0h
0x180001802  mov     rax, cs:__security_cookie
0x180001809  xor     rax, rsp
0x18000180c  mov     [rbp+2Fh+var_10], rax
0x180001810  mov     rax, [rbp+2Fh+arg_40]
0x180001814  xor     r9d, r9d
0x180001817  mov     [rbp+2Fh+var_20], rax
0x18000181b  mov     r11, rdx
0x18000181e  mov     rax, [rbp+2Fh+arg_38]
0x180001822  mov     r10, rcx
0x180001825  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001829  mov     [rbp+2Fh+var_18], 4
0x180001831  lea     r8d, [r9+2]
0x180001835  mov     rdx, [rax]
0x180001838  test    rdx, rdx
0x18000183b  jz      short loc_180001853
0x18000183d  mov     rax, rcx
0x180001840  inc     rax
0x180001843  cmp     [rdx+rax*2], r9w
0x180001848  jnz     short loc_180001840
0x18000184a  lea     eax, ds:2[rax*2]
0x180001851  jmp     short loc_18000185D
0x180001853  lea     rdx, qword_1800105E0
0x18000185a  mov     eax, r8d
0x18000185d  mov     [rbp+2Fh+var_28], eax
0x180001860  mov     rax, [rbp+2Fh+arg_30]
0x180001864  mov     [rbp+2Fh+var_30], rdx
0x180001868  mov     [rbp+2Fh+var_24], r9d
0x18000186c  mov     rdx, [rax]
0x18000186f  test    rdx, rdx
0x180001872  jz      short loc_18000188B
0x180001874  mov     rax, rcx
0x180001877  inc     rax
0x18000187a  cmp     [rdx+rax*2], r9w
0x18000187f  jnz     short loc_180001877
0x180001881  lea     r8d, ds:2[rax*2]
0x180001889  jmp     short loc_180001892
0x18000188b  lea     rdx, qword_1800105E0
0x180001892  mov     rax, [rbp+2Fh+arg_28]
0x180001896  mov     [rbp+2Fh+var_50], rax
0x18000189a  mov     rax, [rbp+2Fh+arg_20]
0x18000189e  mov     [rbp+2Fh+var_40], rdx
0x1800018a2  mov     [rbp+2Fh+var_38], r8d
0x1800018a6  mov     [rbp+2Fh+var_34], r9d
0x1800018aa  mov     rdx, [rax]
0x1800018ad  mov     [rbp+2Fh+var_48], 8
0x1800018b5  test    rdx, rdx
0x1800018b8  jz      short loc_1800018C7
0x1800018ba  inc     rcx
0x1800018bd  cmp     [rdx+rcx], r9b
0x1800018c1  jnz     short loc_1800018BA
0x1800018c3  inc     ecx
0x1800018c5  jmp     short loc_1800018D3
0x1800018c7  lea     rdx, word_18000FE2A
0x1800018ce  mov     ecx, 1
0x1800018d3  lea     rax, [rbp+2Fh+var_80]
0x1800018d7  mov     [rbp+2Fh+var_60], rdx
0x1800018db  mov     [rbp+2Fh+var_58], ecx
0x1800018de  xor     r8d, r8d
0x1800018e1  mov     [rsp+0B0h+var_88], rax
0x1800018e6  mov     rdx, r11
0x1800018e9  mov     rcx, r10
0x1800018ec  mov     [rsp+0B0h+var_90], 7
0x1800018f4  mov     [rbp+2Fh+var_54], r9d
0x1800018f8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800018fd  mov     rcx, [rbp+2Fh+var_10]
0x180001901  xor     rcx, rsp; StackCookie
0x180001904  call    __security_check_cookie
0x180001909  add     rsp, 0B0h
0x180001910  pop     rbp
0x180001911  retn
```
