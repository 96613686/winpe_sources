# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001540`
- end: `0x180001629`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `233`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f800`
- `0x180012684`
- `0x18002cf1c`
- `0x18002d6b0`
- `0x18002fca4`
- `0x18004a07c`
- `0x18004a9cc`
- `0x18004b340`

## callees

- `0x180001414`
- `0x180001540`
- `0x18004c8e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 **a5,
        __int64 a6,
        __int64 **a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  __int64 *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  __int64 *v13; // rdx
  _BYTE v15[32]; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  int v18; // [rsp+5Ch] [rbp-3Ch]
  __int64 v19; // [rsp+60h] [rbp-38h]
  __int64 v20; // [rsp+68h] [rbp-30h]
  __int64 *v21; // [rsp+70h] [rbp-28h]
  int v22; // [rsp+78h] [rbp-20h]
  int v23; // [rsp+7Ch] [rbp-1Ch]

  v8 = -1;
  v9 = 1;
  v10 = *a7;
  if ( *a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_BYTE *)v10 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v10 = &qword_1800528B8;
    v12 = 1;
  }
  v22 = v12;
  v19 = a6;
  v21 = v10;
  v23 = 0;
  v20 = 4;
  v13 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_BYTE *)v13 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v13 = &qword_1800528B8;
  }
  v16 = v13;
  v17 = v9;
  v18 = 0;
  return tlgWriteTransfer_GameInputEventWriteTransfer((__int64)&dword_180069000, a2, 0, 0, 5, (__int64)v15);
}

```

## disassembly

```asm
0x180001540  sub     rsp, 98h
0x180001547  mov     rax, cs:__security_cookie
0x18000154e  xor     rax, rsp
0x180001551  mov     [rsp+98h+var_18], rax
0x180001559  mov     rax, [rsp+98h+arg_30]
0x180001561  mov     r10, rdx
0x180001564  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001568  xor     r9d, r9d
0x18000156b  mov     r8d, 1
0x180001571  mov     rdx, [rax]
0x180001574  test    rdx, rdx
0x180001577  jz      short loc_180001589
0x180001579  mov     rax, rcx
0x18000157c  inc     rax
0x18000157f  cmp     [rdx+rax], r9b
0x180001583  jnz     short loc_18000157C
0x180001585  inc     eax
0x180001587  jmp     short loc_180001593
0x180001589  lea     rdx, qword_1800528B8
0x180001590  mov     eax, r8d
0x180001593  mov     [rsp+98h+var_20], eax
0x180001597  mov     rax, [rsp+98h+arg_28]
0x18000159f  mov     [rsp+98h+var_38], rax
0x1800015a4  mov     rax, [rsp+98h+arg_20]
0x1800015ac  mov     [rsp+98h+var_28], rdx
0x1800015b1  mov     [rsp+98h+var_1C], r9d
0x1800015b6  mov     [rsp+98h+var_30], 4
0x1800015bf  mov     rdx, [rax]
0x1800015c2  test    rdx, rdx
0x1800015c5  jz      short loc_1800015D6
0x1800015c7  inc     rcx
0x1800015ca  cmp     [rdx+rcx], r9b
0x1800015ce  jnz     short loc_1800015C7
0x1800015d0  lea     r8d, [rcx+1]
0x1800015d4  jmp     short loc_1800015DD
0x1800015d6  lea     rdx, qword_1800528B8
0x1800015dd  lea     rax, [rsp+98h+var_68]
0x1800015e2  mov     [rsp+98h+var_48], rdx
0x1800015e7  mov     [rsp+98h+var_40], r8d
0x1800015ec  lea     rcx, dword_180069000
0x1800015f3  mov     [rsp+98h+var_70], rax
0x1800015f8  xor     r8d, r8d
0x1800015fb  mov     rdx, r10
0x1800015fe  mov     [rsp+98h+var_78], 5
0x180001606  mov     [rsp+98h+var_3C], r9d
0x18000160b  call    _tlgWriteTransfer_GameInputEventWriteTransfer
0x180001610  mov     rcx, [rsp+98h+var_18]
0x180001618  xor     rcx, rsp; StackCookie
0x18000161b  call    __security_check_cookie
0x180001620  add     rsp, 98h
0x180001627  retn
```
