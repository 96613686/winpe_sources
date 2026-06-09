# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)

- ea: `0x14000209c`
- end: `0x14000218b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ac0c`

## callees

- `0x14000209c`
- `0x140002318`
- `0x140002f40`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 **a7,
        __int64 **a8)
{
  __int64 v10; // rcx
  int v12; // r8d
  __int64 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  __int64 *v16; // rdx
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-49h] BYREF
  __int64 v19; // [rsp+50h] [rbp-29h]
  __int64 v20; // [rsp+58h] [rbp-21h]
  __int64 v21; // [rsp+60h] [rbp-19h]
  __int64 v22; // [rsp+68h] [rbp-11h]
  __int64 *v23; // [rsp+70h] [rbp-9h]
  int v24; // [rsp+78h] [rbp-1h]
  int v25; // [rsp+7Ch] [rbp+3h]
  __int64 *v26; // [rsp+80h] [rbp+7h]
  int v27; // [rsp+88h] [rbp+Fh]
  int v28; // [rsp+8Ch] [rbp+13h]

  v10 = -1;
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
    v13 = &qword_14001C2F8;
    v15 = 2;
  }
  v27 = v15;
  v26 = v13;
  v28 = 0;
  v16 = *a7;
  if ( *a7 )
  {
    do
      ++v10;
    while ( *((_WORD *)v16 + v10) );
    v12 = 2 * v10 + 2;
  }
  else
  {
    v16 = &qword_14001C2F8;
  }
  v21 = a6;
  v19 = a5;
  v23 = v16;
  v24 = v12;
  v25 = 0;
  v22 = 4;
  v20 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 6u, &v18);
}

```

## disassembly

```asm
0x14000209c  push    rbp
0x14000209e  push    rbx
0x14000209f  push    rdi
0x1400020a0  lea     rbp, [rsp-27h]
0x1400020a5  sub     rsp, 0A0h
0x1400020ac  mov     rax, cs:__security_cookie
0x1400020b3  xor     rax, rsp
0x1400020b6  mov     [rbp+37h+var_20], rax
0x1400020ba  mov     rax, [rbp+37h+arg_38]
0x1400020be  mov     r11, rdx
0x1400020c1  mov     r10, rcx
0x1400020c4  xor     edi, edi
0x1400020c6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400020ca  mov     rbx, r8
0x1400020cd  mov     r8d, 2
0x1400020d3  mov     rdx, [rax]
0x1400020d6  test    rdx, rdx
0x1400020d9  jz      short loc_1400020F0
0x1400020db  mov     rax, rcx
0x1400020de  inc     rax
0x1400020e1  cmp     [rdx+rax*2], di
0x1400020e5  jnz     short loc_1400020DE
0x1400020e7  lea     eax, ds:2[rax*2]
0x1400020ee  jmp     short loc_1400020FA
0x1400020f0  lea     rdx, qword_14001C2F8
0x1400020f7  mov     eax, r8d
0x1400020fa  mov     [rbp+37h+var_28], eax
0x1400020fd  mov     rax, [rbp+37h+arg_30]
0x140002101  mov     [rbp+37h+var_30], rdx
0x140002105  mov     [rbp+37h+var_24], edi
0x140002108  mov     rdx, [rax]
0x14000210b  test    rdx, rdx
0x14000210e  jz      short loc_140002123
0x140002110  inc     rcx
0x140002113  cmp     [rdx+rcx*2], di
0x140002117  jnz     short loc_140002110
0x140002119  lea     r8d, ds:2[rcx*2]
0x140002121  jmp     short loc_14000212A
0x140002123  lea     rdx, qword_14001C2F8
0x14000212a  mov     rax, [rbp+37h+arg_28]
0x14000212e  mov     rcx, r10
0x140002131  mov     [rbp+37h+var_50], rax
0x140002135  mov     rax, [rbp+37h+arg_20]
0x140002139  mov     [rbp+37h+var_60], rax
0x14000213d  lea     rax, [rbp+37h+var_80]
0x140002141  mov     [rbp+37h+var_40], rdx
0x140002145  mov     rdx, r11
0x140002148  mov     [rbp+37h+var_38], r8d
0x14000214c  mov     r8, rbx
0x14000214f  mov     [rsp+0B0h+var_88], rax
0x140002154  mov     [rsp+0B0h+var_90], 6
0x14000215c  mov     [rbp+37h+var_34], edi
0x14000215f  mov     [rbp+37h+var_48], 4
0x140002167  mov     [rbp+37h+var_58], 8
0x14000216f  call    _tlgWriteTransfer_EventWriteTransfer
0x140002174  mov     rcx, [rbp+37h+var_20]
0x140002178  xor     rcx, rsp; StackCookie
0x14000217b  call    __security_check_cookie
0x140002180  add     rsp, 0A0h
0x140002187  pop     rdi
0x140002188  pop     rbx
0x140002189  pop     rbp
0x14000218a  retn
```
