# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1400020e4`
- end: `0x140002182`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018b80`

## callees

- `0x140001f60`
- `0x1400020e4`
- `0x1400029c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-58h] BYREF
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
    v6 = &byte_14001BCA1;
    v8 = 1;
  }
  v14 = v8;
  v13 = v6;
  v11 = a5;
  v12 = 4;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140025000, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x1400020e4  sub     rsp, 88h
0x1400020eb  mov     rax, cs:__security_cookie
0x1400020f2  xor     rax, rsp
0x1400020f5  mov     [rsp+88h+var_18], rax
0x1400020fa  mov     rax, [rsp+88h+arg_28]
0x140002102  xor     r8d, r8d
0x140002105  mov     rcx, [rax]
0x140002108  test    rcx, rcx
0x14000210b  jz      short loc_14000211E
0x14000210d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002111  inc     rax
0x140002114  cmp     [rcx+rax], r8b
0x140002118  jnz     short loc_140002111
0x14000211a  inc     eax
0x14000211c  jmp     short loc_14000212A
0x14000211e  lea     rcx, byte_14001BCA1
0x140002125  mov     eax, 1
0x14000212a  mov     [rsp+88h+var_20], eax
0x14000212e  xor     r9d, r9d
0x140002131  mov     rax, [rsp+88h+arg_20]
0x140002139  mov     [rsp+88h+var_28], rcx
0x14000213e  mov     ecx, 4
0x140002143  mov     [rsp+88h+var_38], rax
0x140002148  lea     rax, [rsp+88h+var_58]
0x14000214d  mov     [rsp+88h+var_60], rax
0x140002152  mov     [rsp+88h+var_68], ecx
0x140002156  mov     [rsp+88h+var_30], rcx
0x14000215b  lea     rcx, dword_140025000
0x140002162  mov     [rsp+88h+var_1C], r8d
0x140002167  call    _tlgWriteTransfer_EventWriteTransfer
0x14000216c  mov     rcx, [rsp+88h+var_18]
0x140002171  xor     rcx, rsp; StackCookie
0x140002174  call    __security_check_cookie
0x140002179  add     rsp, 88h
0x140002180  retn
```
