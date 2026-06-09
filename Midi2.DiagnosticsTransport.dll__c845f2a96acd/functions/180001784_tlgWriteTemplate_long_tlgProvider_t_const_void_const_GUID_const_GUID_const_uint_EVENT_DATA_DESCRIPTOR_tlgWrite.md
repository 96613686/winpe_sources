# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001784`
- end: `0x18000186f`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b9f0`

## callees

- `0x18000163c`
- `0x180001784`
- `0x1800033d0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 **a7)
{
  __int64 v9; // rcx
  __int64 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  int v14; // ecx
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v17; // [rsp+50h] [rbp-48h]
  int v18; // [rsp+58h] [rbp-40h]
  int v19; // [rsp+5Ch] [rbp-3Ch]
  __int64 v20; // [rsp+60h] [rbp-38h]
  __int64 v21; // [rsp+68h] [rbp-30h]
  __int64 *v22; // [rsp+70h] [rbp-28h]
  int v23; // [rsp+78h] [rbp-20h]
  int v24; // [rsp+7Ch] [rbp-1Ch]

  v9 = -1;
  v10 = *a7;
  if ( *a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = qword_1800159A0;
    v12 = 2;
  }
  v23 = v12;
  v20 = a6;
  v22 = v10;
  v24 = 0;
  v21 = 8;
  v13 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v13 + v9) );
    v14 = v9 + 1;
  }
  else
  {
    v13 = &word_1800151EA;
    v14 = 1;
  }
  v17 = v13;
  v18 = v14;
  v19 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5u, &v16);
}

```

## disassembly

```asm
0x180001784  sub     rsp, 98h
0x18000178b  mov     rax, cs:__security_cookie
0x180001792  xor     rax, rsp
0x180001795  mov     [rsp+98h+var_18], rax
0x18000179d  mov     rax, [rsp+98h+arg_30]
0x1800017a5  mov     r11, rdx
0x1800017a8  mov     r10, rcx
0x1800017ab  xor     r8d, r8d
0x1800017ae  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800017b2  mov     rdx, [rax]
0x1800017b5  test    rdx, rdx
0x1800017b8  jz      short loc_1800017D0
0x1800017ba  mov     rax, rcx
0x1800017bd  inc     rax
0x1800017c0  cmp     [rdx+rax*2], r8w
0x1800017c5  jnz     short loc_1800017BD
0x1800017c7  lea     eax, ds:2[rax*2]
0x1800017ce  jmp     short loc_1800017DC
0x1800017d0  lea     rdx, qword_1800159A0
0x1800017d7  mov     eax, 2
0x1800017dc  mov     [rsp+98h+var_20], eax
0x1800017e0  mov     rax, [rsp+98h+arg_28]
0x1800017e8  mov     [rsp+98h+var_38], rax
0x1800017ed  mov     rax, [rsp+98h+arg_20]
0x1800017f5  mov     [rsp+98h+var_28], rdx
0x1800017fa  mov     [rsp+98h+var_1C], r8d
0x1800017ff  mov     [rsp+98h+var_30], 8
0x180001808  mov     rdx, [rax]
0x18000180b  test    rdx, rdx
0x18000180e  jz      short loc_18000181D
0x180001810  inc     rcx
0x180001813  cmp     [rdx+rcx], r8b
0x180001817  jnz     short loc_180001810
0x180001819  inc     ecx
0x18000181b  jmp     short loc_180001829
0x18000181d  lea     rdx, word_1800151EA
0x180001824  mov     ecx, 1
0x180001829  lea     rax, [rsp+98h+var_68]
0x18000182e  mov     [rsp+98h+var_48], rdx
0x180001833  mov     [rsp+98h+var_40], ecx
0x180001837  xor     r9d, r9d
0x18000183a  mov     [rsp+98h+var_70], rax
0x18000183f  mov     rdx, r11
0x180001842  mov     rcx, r10
0x180001845  mov     [rsp+98h+var_78], 5
0x18000184d  mov     [rsp+98h+var_3C], r8d
0x180001852  call    _tlgWriteTransfer_EventWriteTransfer
0x180001857  mov     rcx, [rsp+98h+var_18]
0x18000185f  xor     rcx, rsp; StackCookie
0x180001862  call    __security_check_cookie
0x180001867  add     rsp, 98h
0x18000186e  retn
```
