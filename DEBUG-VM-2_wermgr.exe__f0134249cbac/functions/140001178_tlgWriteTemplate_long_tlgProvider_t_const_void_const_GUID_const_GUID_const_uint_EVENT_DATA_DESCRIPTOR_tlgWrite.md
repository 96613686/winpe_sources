# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001178`
- end: `0x140001269`
- name: `??$Write@U?$_tlgWrapSz@_W@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000be08`

## callees

- `0x140001178`
- `0x14000162c`
- `0x140003200`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        int **a6,
        __int64 a7)
{
  __int64 v8; // rcx
  int v9; // r8d
  int *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  int *v13; // rdx
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-68h] BYREF
  int *v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  int v18; // [rsp+5Ch] [rbp-3Ch]
  int *v19; // [rsp+60h] [rbp-38h]
  int v20; // [rsp+68h] [rbp-30h]
  int v21; // [rsp+6Ch] [rbp-2Ch]
  __int64 v22; // [rsp+70h] [rbp-28h]
  __int64 v23; // [rsp+78h] [rbp-20h]

  v22 = a7;
  v8 = -1;
  v23 = 4;
  v9 = 2;
  v10 = *a6;
  if ( *a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)v10 + v11) );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &dword_1400241F4;
    v12 = 2;
  }
  v20 = v12;
  v19 = v10;
  v21 = 0;
  v13 = *a5;
  if ( *a5 )
  {
    do
      ++v8;
    while ( *((_WORD *)v13 + v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v13 = &dword_1400241F4;
  }
  v16 = v13;
  v17 = v9;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14002C000, a2, 0, 0, 5u, &v15);
}

```

## disassembly

```asm
0x140001178  sub     rsp, 98h
0x14000117f  mov     rax, cs:__security_cookie
0x140001186  xor     rax, rsp
0x140001189  mov     [rsp+98h+var_18], rax
0x140001191  mov     rax, [rsp+98h+arg_30]
0x140001199  xor     r9d, r9d
0x14000119c  mov     [rsp+98h+var_28], rax
0x1400011a1  mov     r10, rdx
0x1400011a4  mov     rax, [rsp+98h+arg_28]
0x1400011ac  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400011b0  mov     [rsp+98h+var_20], 4
0x1400011b9  lea     r8d, [r9+2]
0x1400011bd  mov     rdx, [rax]
0x1400011c0  test    rdx, rdx
0x1400011c3  jz      short loc_1400011DB
0x1400011c5  mov     rax, rcx
0x1400011c8  inc     rax
0x1400011cb  cmp     [rdx+rax*2], r9w
0x1400011d0  jnz     short loc_1400011C8
0x1400011d2  lea     eax, ds:2[rax*2]
0x1400011d9  jmp     short loc_1400011E5
0x1400011db  lea     rdx, dword_1400241F4
0x1400011e2  mov     eax, r8d
0x1400011e5  mov     [rsp+98h+var_30], eax
0x1400011e9  mov     rax, [rsp+98h+arg_20]
0x1400011f1  mov     [rsp+98h+var_38], rdx
0x1400011f6  mov     [rsp+98h+var_2C], r9d
0x1400011fb  mov     rdx, [rax]
0x1400011fe  test    rdx, rdx
0x140001201  jz      short loc_140001217
0x140001203  inc     rcx
0x140001206  cmp     [rdx+rcx*2], r9w
0x14000120b  jnz     short loc_140001203
0x14000120d  lea     r8d, ds:2[rcx*2]
0x140001215  jmp     short loc_14000121E
0x140001217  lea     rdx, dword_1400241F4
0x14000121e  lea     rax, [rsp+98h+var_68]
0x140001223  mov     [rsp+98h+var_48], rdx
0x140001228  mov     [rsp+98h+var_40], r8d
0x14000122d  lea     rcx, dword_14002C000
0x140001234  mov     [rsp+98h+var_70], rax
0x140001239  xor     r8d, r8d
0x14000123c  mov     rdx, r10
0x14000123f  mov     [rsp+98h+var_78], 5
0x140001247  mov     [rsp+98h+var_3C], r9d
0x14000124c  call    _tlgWriteTransfer_EventWriteTransfer
0x140001251  mov     rcx, [rsp+98h+var_18]
0x140001259  xor     rcx, rsp; StackCookie
0x14000125c  call    __security_check_cookie
0x140001261  add     rsp, 98h
0x140001268  retn
```
