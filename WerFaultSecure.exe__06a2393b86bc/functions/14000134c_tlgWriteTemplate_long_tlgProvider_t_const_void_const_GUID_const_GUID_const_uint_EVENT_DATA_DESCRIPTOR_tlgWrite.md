# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000134c`
- end: `0x1400013f1`
- name: `??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cfc4`

## callees

- `0x14000113c`
- `0x14000134c`
- `0x1400023d0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 a6)
{
  int *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
  int *v11; // [rsp+50h] [rbp-38h]
  int v12; // [rsp+58h] [rbp-30h]
  int v13; // [rsp+5Ch] [rbp-2Ch]
  __int64 v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-20h]

  v14 = a6;
  v15 = 4;
  v6 = *a5;
  if ( *a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)v6 + v7) );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v6 = &dword_140014A6C;
    v8 = 2;
  }
  v12 = v8;
  v11 = v6;
  v13 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_14001A000, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x14000134c  sub     rsp, 88h
0x140001353  mov     rax, cs:__security_cookie
0x14000135a  xor     rax, rsp
0x14000135d  mov     [rsp+88h+var_18], rax
0x140001362  mov     rax, [rsp+88h+arg_28]
0x14000136a  xor     r8d, r8d
0x14000136d  mov     [rsp+88h+var_28], rax
0x140001372  mov     r9d, 4
0x140001378  mov     rax, [rsp+88h+arg_20]
0x140001380  mov     [rsp+88h+var_20], r9
0x140001385  mov     rcx, [rax]
0x140001388  test    rcx, rcx
0x14000138b  jz      short loc_1400013A4
0x14000138d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001391  inc     rax
0x140001394  cmp     [rcx+rax*2], r8w
0x140001399  jnz     short loc_140001391
0x14000139b  lea     eax, ds:2[rax*2]
0x1400013a2  jmp     short loc_1400013B0
0x1400013a4  lea     rcx, dword_140014A6C
0x1400013ab  mov     eax, 2
0x1400013b0  mov     [rsp+88h+var_30], eax
0x1400013b4  lea     rax, [rsp+88h+var_58]
0x1400013b9  mov     [rsp+88h+var_60], rax
0x1400013be  mov     [rsp+88h+var_68], r9d
0x1400013c3  xor     r9d, r9d
0x1400013c6  mov     [rsp+88h+var_38], rcx
0x1400013cb  lea     rcx, dword_14001A000
0x1400013d2  mov     [rsp+88h+var_2C], r8d
0x1400013d7  call    _tlgWriteTransfer_EventWriteTransfer
0x1400013dc  mov     rcx, [rsp+88h+var_18]
0x1400013e1  xor     rcx, rsp; StackCookie
0x1400013e4  call    __security_check_cookie
0x1400013e9  add     rsp, 88h
0x1400013f0  retn
```
