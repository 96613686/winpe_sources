# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001180`
- end: `0x18000121e`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c02c`

## callees

- `0x180001180`
- `0x1800014a4`
- `0x180001c60`

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
    v6 = &qword_180020258;
    v8 = 1;
  }
  v14 = v8;
  v13 = v6;
  v11 = a5;
  v12 = 4;
  v15 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180029000, a2, 0, 0, 4u, &v10);
}

```

## disassembly

```asm
0x180001180  sub     rsp, 88h
0x180001187  mov     rax, cs:__security_cookie
0x18000118e  xor     rax, rsp
0x180001191  mov     [rsp+88h+var_18], rax
0x180001196  mov     rax, [rsp+88h+arg_28]
0x18000119e  xor     r8d, r8d
0x1800011a1  mov     rcx, [rax]
0x1800011a4  test    rcx, rcx
0x1800011a7  jz      short loc_1800011BA
0x1800011a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800011ad  inc     rax
0x1800011b0  cmp     [rcx+rax], r8b
0x1800011b4  jnz     short loc_1800011AD
0x1800011b6  inc     eax
0x1800011b8  jmp     short loc_1800011C6
0x1800011ba  lea     rcx, qword_180020258
0x1800011c1  mov     eax, 1
0x1800011c6  mov     [rsp+88h+var_20], eax
0x1800011ca  xor     r9d, r9d
0x1800011cd  mov     rax, [rsp+88h+arg_20]
0x1800011d5  mov     [rsp+88h+var_28], rcx
0x1800011da  mov     ecx, 4
0x1800011df  mov     [rsp+88h+var_38], rax
0x1800011e4  lea     rax, [rsp+88h+var_58]
0x1800011e9  mov     [rsp+88h+var_60], rax
0x1800011ee  mov     [rsp+88h+var_68], ecx
0x1800011f2  mov     [rsp+88h+var_30], rcx
0x1800011f7  lea     rcx, dword_180029000
0x1800011fe  mov     [rsp+88h+var_1C], r8d
0x180001203  call    _tlgWriteTransfer_EventWriteTransfer
0x180001208  mov     rcx, [rsp+88h+var_18]
0x18000120d  xor     rcx, rsp; StackCookie
0x180001210  call    __security_check_cookie
0x180001215  add     rsp, 88h
0x18000121c  retn
```
