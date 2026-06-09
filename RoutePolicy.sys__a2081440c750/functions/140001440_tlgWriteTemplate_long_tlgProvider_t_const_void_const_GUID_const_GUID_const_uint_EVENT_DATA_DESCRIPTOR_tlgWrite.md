# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001440`
- end: `0x140001547`
- name: `??$Write@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140004330`

## callees

- `0x1400012f0`
- `0x140001440`
- `0x14000a680`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 **a7,
        __int64 a8,
        __int64 a9,
        __int64 **a10)
{
  __int64 v11; // rcx
  __int64 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  __int64 *v15; // rdx
  int v16; // ecx
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-69h] BYREF
  __int64 v19; // [rsp+50h] [rbp-49h]
  __int64 v20; // [rsp+58h] [rbp-41h]
  __int64 v21; // [rsp+60h] [rbp-39h]
  __int64 v22; // [rsp+68h] [rbp-31h]
  __int64 *v23; // [rsp+70h] [rbp-29h]
  int v24; // [rsp+78h] [rbp-21h]
  int v25; // [rsp+7Ch] [rbp-1Dh]
  __int64 v26; // [rsp+80h] [rbp-19h]
  __int64 v27; // [rsp+88h] [rbp-11h]
  __int64 v28; // [rsp+90h] [rbp-9h]
  __int64 v29; // [rsp+98h] [rbp-1h]
  __int64 *v30; // [rsp+A0h] [rbp+7h]
  int v31; // [rsp+A8h] [rbp+Fh]
  int v32; // [rsp+ACh] [rbp+13h]

  v11 = -1;
  v12 = *a10;
  if ( *a10 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v12 + v13) );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &qword_14000C868;
    v14 = 2;
  }
  v31 = v14;
  v28 = a9;
  v26 = a8;
  v30 = v12;
  v32 = 0;
  v29 = 8;
  v15 = *a7;
  v27 = 1;
  if ( v15 )
  {
    do
      ++v11;
    while ( *((_WORD *)v15 + v11) );
    v16 = 2 * v11 + 2;
  }
  else
  {
    v15 = &qword_14000C868;
    v16 = 2;
  }
  v21 = a6;
  v19 = a5;
  v23 = v15;
  v24 = v16;
  v22 = 2;
  v20 = 2;
  v25 = 0;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, a2, 0, 0, 8u, &v18);
}

```

## disassembly

```asm
0x140001440  push    rbp
0x140001442  lea     rbp, [rsp-27h]
0x140001447  sub     rsp, 0C0h
0x14000144e  mov     rax, cs:__security_cookie
0x140001455  xor     rax, rsp
0x140001458  mov     [rbp+27h+var_10], rax
0x14000145c  mov     rax, [rbp+27h+arg_48]
0x140001460  mov     r10, rdx
0x140001463  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001467  xor     r8d, r8d; int
0x14000146a  mov     r9d, 2
0x140001470  mov     rdx, [rax]
0x140001473  test    rdx, rdx
0x140001476  jz      short loc_14000148E
0x140001478  mov     rax, rcx
0x14000147b  inc     rax
0x14000147e  cmp     [rdx+rax*2], r8w
0x140001483  jnz     short loc_14000147B
0x140001485  lea     eax, ds:2[rax*2]
0x14000148c  jmp     short loc_140001498
0x14000148e  lea     rdx, qword_14000C868
0x140001495  mov     eax, r9d
0x140001498  mov     [rbp+27h+var_18], eax
0x14000149b  mov     r11d, 8
0x1400014a1  mov     rax, [rbp+27h+arg_40]
0x1400014a5  mov     [rbp+27h+var_30], rax
0x1400014a9  mov     rax, [rbp+27h+arg_38]
0x1400014ad  mov     [rbp+27h+var_40], rax
0x1400014b1  mov     rax, [rbp+27h+arg_30]
0x1400014b5  mov     [rbp+27h+var_20], rdx
0x1400014b9  mov     [rbp+27h+var_14], r8d
0x1400014bd  mov     [rbp+27h+var_28], r11
0x1400014c1  mov     rdx, [rax]
0x1400014c4  mov     [rbp+27h+var_38], 1
0x1400014cc  test    rdx, rdx
0x1400014cf  jz      short loc_1400014E4
0x1400014d1  inc     rcx
0x1400014d4  cmp     [rdx+rcx*2], r8w
0x1400014d9  jnz     short loc_1400014D1
0x1400014db  lea     ecx, ds:2[rcx*2]
0x1400014e2  jmp     short loc_1400014EE
0x1400014e4  lea     rdx, qword_14000C868
0x1400014eb  mov     ecx, r9d
0x1400014ee  mov     rax, [rbp+27h+arg_28]
0x1400014f2  mov     [rbp+27h+var_60], rax
0x1400014f6  mov     rax, [rbp+27h+arg_20]
0x1400014fa  mov     [rbp+27h+var_70], rax
0x1400014fe  lea     rax, [rbp+27h+var_90]
0x140001502  mov     [rbp+27h+var_50], rdx
0x140001506  mov     rdx, r10; int
0x140001509  mov     [rbp+27h+var_48], ecx
0x14000150c  lea     rcx, dword_140012050; int
0x140001513  mov     [rbp+27h+var_58], r9
0x140001517  mov     [rbp+27h+var_68], r9
0x14000151b  xor     r9d, r9d; int
0x14000151e  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x140001523  mov     [rsp+0C0h+var_A0], r11d; ULONG
0x140001528  mov     [rbp+27h+var_44], r8d
0x14000152c  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001531  mov     rcx, [rbp+27h+var_10]
0x140001535  xor     rcx, rsp; StackCookie
0x140001538  call    __security_check_cookie
0x14000153d  add     rsp, 0C0h
0x140001544  pop     rbp
0x140001545  retn
```
