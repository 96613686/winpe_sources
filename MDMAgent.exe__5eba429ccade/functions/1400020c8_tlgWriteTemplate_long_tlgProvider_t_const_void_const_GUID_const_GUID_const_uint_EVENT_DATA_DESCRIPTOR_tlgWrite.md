# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400020c8`
- end: `0x140002165`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017e7c`

## callees

- `0x140001f48`
- `0x1400020c8`
- `0x140002930`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v10[32]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]
  __int64 v12; // [rsp+58h] [rbp-30h]
  const unsigned __int16 *v13; // [rsp+60h] [rbp-28h]
  int v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+6Ch] [rbp-1Ch]

  v6 = *a6;
  if ( *a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *((_BYTE *)v6 + v7) );
    v8 = v7 + 1;
  }
  else
  {
    v6 = &byte_14001ACA1;
    v8 = 1;
  }
  v14 = v8;
  v13 = v6;
  v11 = a5;
  v12 = 4;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140024000, a2, 0, 0, 4, v10);
}

```

## disassembly

```asm
0x1400020c8  sub     rsp, 88h
0x1400020cf  mov     rax, cs:__security_cookie
0x1400020d6  xor     rax, rsp
0x1400020d9  mov     [rsp+88h+var_18], rax
0x1400020de  mov     rax, [rsp+88h+arg_28]
0x1400020e6  xor     r8d, r8d
0x1400020e9  mov     rcx, [rax]
0x1400020ec  test    rcx, rcx
0x1400020ef  jz      short loc_140002102
0x1400020f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400020f5  inc     rax
0x1400020f8  cmp     [rcx+rax], r8b
0x1400020fc  jnz     short loc_1400020F5
0x1400020fe  inc     eax
0x140002100  jmp     short loc_14000210E
0x140002102  lea     rcx, byte_14001ACA1
0x140002109  mov     eax, 1
0x14000210e  mov     [rsp+88h+var_20], eax
0x140002112  xor     r9d, r9d
0x140002115  mov     rax, [rsp+88h+arg_20]
0x14000211d  mov     [rsp+88h+var_28], rcx
0x140002122  mov     ecx, 4
0x140002127  mov     [rsp+88h+var_38], rax
0x14000212c  lea     rax, [rsp+88h+var_58]
0x140002131  mov     [rsp+88h+var_60], rax
0x140002136  mov     [rsp+88h+var_68], ecx
0x14000213a  mov     [rsp+88h+var_30], rcx
0x14000213f  lea     rcx, dword_140024000
0x140002146  mov     [rsp+88h+var_1C], r8d
0x14000214b  call    _tlgWriteTransfer_EventWriteTransfer
0x140002150  mov     rcx, [rsp+88h+var_18]
0x140002155  xor     rcx, rsp; StackCookie
0x140002158  call    __security_check_cookie
0x14000215d  add     rsp, 88h
0x140002164  retn
```
