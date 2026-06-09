# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x140001d40`
- end: `0x140001e6d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@545@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e8c4`

## callees

- `0x14000113c`
- `0x140001d40`
- `0x1400023d0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int **a7,
        int **a8,
        __int64 a9,
        int **a10)
{
  __int64 v11; // rcx
  int v12; // r8d
  int *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  int *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  int *v19; // rdx
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-69h] BYREF
  __int64 v22; // [rsp+50h] [rbp-49h]
  __int64 v23; // [rsp+58h] [rbp-41h]
  __int64 v24; // [rsp+60h] [rbp-39h]
  __int64 v25; // [rsp+68h] [rbp-31h]
  int *v26; // [rsp+70h] [rbp-29h]
  int v27; // [rsp+78h] [rbp-21h]
  int v28; // [rsp+7Ch] [rbp-1Dh]
  int *v29; // [rsp+80h] [rbp-19h]
  int v30; // [rsp+88h] [rbp-11h]
  int v31; // [rsp+8Ch] [rbp-Dh]
  __int64 v32; // [rsp+90h] [rbp-9h]
  __int64 v33; // [rsp+98h] [rbp-1h]
  int *v34; // [rsp+A0h] [rbp+7h]
  int v35; // [rsp+A8h] [rbp+Fh]
  int v36; // [rsp+ACh] [rbp+13h]

  v11 = -1;
  v12 = 2;
  v13 = *a10;
  if ( *a10 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v13 + v14) );
    v15 = 2 * v14 + 2;
  }
  else
  {
    v13 = &dword_140014A6C;
    v15 = 2;
  }
  v35 = v15;
  v32 = a9;
  v34 = v13;
  v36 = 0;
  v33 = 4;
  v16 = *a8;
  if ( *a8 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v16 + v17) );
    v18 = 2 * v17 + 2;
  }
  else
  {
    v16 = &dword_140014A6C;
    v18 = 2;
  }
  v30 = v18;
  v29 = v16;
  v31 = 0;
  v19 = *a7;
  if ( *a7 )
  {
    do
      ++v11;
    while ( *((_WORD *)v19 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v19 = &dword_140014A6C;
  }
  v24 = a6;
  v22 = a5;
  v26 = v19;
  v27 = v12;
  v23 = 8;
  v28 = 0;
  v25 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14001A000, a2, 0, 0, 8u, &v21);
}

```

## disassembly

```asm
0x140001d40  push    rbp
0x140001d42  lea     rbp, [rsp-27h]
0x140001d47  sub     rsp, 0C0h
0x140001d4e  mov     rax, cs:__security_cookie
0x140001d55  xor     rax, rsp
0x140001d58  mov     [rbp+27h+var_10], rax
0x140001d5c  mov     rax, [rbp+27h+arg_48]
0x140001d60  lea     r11, dword_140014A6C
0x140001d67  mov     r10, rdx
0x140001d6a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001d6e  xor     r9d, r9d
0x140001d71  mov     r8d, 2
0x140001d77  mov     rdx, [rax]
0x140001d7a  test    rdx, rdx
0x140001d7d  jz      short loc_140001D95
0x140001d7f  mov     rax, rcx
0x140001d82  inc     rax
0x140001d85  cmp     [rdx+rax*2], r9w
0x140001d8a  jnz     short loc_140001D82
0x140001d8c  lea     eax, ds:2[rax*2]
0x140001d93  jmp     short loc_140001D9B
0x140001d95  mov     rdx, r11
0x140001d98  mov     eax, r8d
0x140001d9b  mov     [rbp+27h+var_18], eax
0x140001d9e  mov     rax, [rbp+27h+arg_40]
0x140001da2  mov     [rbp+27h+var_30], rax
0x140001da6  mov     rax, [rbp+27h+arg_38]
0x140001daa  mov     [rbp+27h+var_20], rdx
0x140001dae  mov     [rbp+27h+var_14], r9d
0x140001db2  mov     [rbp+27h+var_28], 4
0x140001dba  mov     rdx, [rax]
0x140001dbd  test    rdx, rdx
0x140001dc0  jz      short loc_140001DD8
0x140001dc2  mov     rax, rcx
0x140001dc5  inc     rax
0x140001dc8  cmp     [rdx+rax*2], r9w
0x140001dcd  jnz     short loc_140001DC5
0x140001dcf  lea     eax, ds:2[rax*2]
0x140001dd6  jmp     short loc_140001DDE
0x140001dd8  mov     rdx, r11
0x140001ddb  mov     eax, r8d
0x140001dde  mov     [rbp+27h+var_38], eax
0x140001de1  mov     rax, [rbp+27h+arg_30]
0x140001de5  mov     [rbp+27h+var_40], rdx
0x140001de9  mov     [rbp+27h+var_34], r9d
0x140001ded  mov     rdx, [rax]
0x140001df0  test    rdx, rdx
0x140001df3  jz      short loc_140001E09
0x140001df5  inc     rcx
0x140001df8  cmp     [rdx+rcx*2], r9w
0x140001dfd  jnz     short loc_140001DF5
0x140001dff  lea     r8d, ds:2[rcx*2]
0x140001e07  jmp     short loc_140001E0C
0x140001e09  mov     rdx, r11
0x140001e0c  mov     rax, [rbp+27h+arg_28]
0x140001e10  mov     ecx, 8
0x140001e15  mov     [rbp+27h+var_60], rax
0x140001e19  mov     rax, [rbp+27h+arg_20]
0x140001e1d  mov     [rbp+27h+var_70], rax
0x140001e21  lea     rax, [rbp+27h+var_90]
0x140001e25  mov     [rsp+0C0h+var_98], rax
0x140001e2a  mov     [rsp+0C0h+var_A0], ecx
0x140001e2e  mov     [rbp+27h+var_50], rdx
0x140001e32  mov     rdx, r10
0x140001e35  mov     [rbp+27h+var_48], r8d
0x140001e39  xor     r8d, r8d
0x140001e3c  mov     [rbp+27h+var_68], rcx
0x140001e40  lea     rcx, dword_14001A000
0x140001e47  mov     [rbp+27h+var_44], r9d
0x140001e4b  mov     [rbp+27h+var_58], 4
0x140001e53  call    _tlgWriteTransfer_EventWriteTransfer
0x140001e58  mov     rcx, [rbp+27h+var_10]
0x140001e5c  xor     rcx, rsp; StackCookie
0x140001e5f  call    __security_check_cookie
0x140001e64  add     rsp, 0C0h
0x140001e6b  pop     rbp
0x140001e6c  retn
```
