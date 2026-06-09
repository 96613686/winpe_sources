# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)

- ea: `0x140001a2c`
- end: `0x140001ab3`
- name: `??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b5dc`
- `0x14000b64c`
- `0x14000b6bc`
- `0x14000b72c`

## callees

- `0x14000198c`
- `0x140001a2c`
- `0x140002a30`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5)
{
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  _BYTE v9[32]; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_BYTE *)v5 + v6) );
    v7 = v6 + 1;
  }
  else
  {
    v5 = &qword_1400150C8;
    v7 = 1;
  }
  v11 = v7;
  v10 = v5;
  v12 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140020038, a2, 0, 0, 3, v9);
}

```

## disassembly

```asm
0x140001a2c  sub     rsp, 78h
0x140001a30  mov     rax, cs:__security_cookie
0x140001a37  xor     rax, rsp
0x140001a3a  mov     [rsp+78h+var_18], rax
0x140001a3f  mov     rax, [rsp+78h+arg_20]
0x140001a47  mov     rcx, [rax]
0x140001a4a  test    rcx, rcx
0x140001a4d  jz      short loc_140001A60
0x140001a4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001a53  inc     rax
0x140001a56  cmp     byte ptr [rcx+rax], 0
0x140001a5a  jnz     short loc_140001A53
0x140001a5c  inc     eax
0x140001a5e  jmp     short loc_140001A6C
0x140001a60  lea     rcx, qword_1400150C8
0x140001a67  mov     eax, 1
0x140001a6c  mov     [rsp+78h+var_20], eax
0x140001a70  xor     r9d, r9d
0x140001a73  lea     rax, [rsp+78h+var_48]
0x140001a78  mov     [rsp+78h+var_28], rcx
0x140001a7d  mov     [rsp+78h+var_50], rax
0x140001a82  lea     rcx, dword_140020038
0x140001a89  xor     r8d, r8d
0x140001a8c  mov     [rsp+78h+var_58], 3
0x140001a94  mov     [rsp+78h+var_1C], 0
0x140001a9c  call    _tlgWriteTransfer_EventWriteTransfer
0x140001aa1  mov     rcx, [rsp+78h+var_18]
0x140001aa6  xor     rcx, rsp; StackCookie
0x140001aa9  call    __security_check_cookie
0x140001aae  add     rsp, 78h
0x140001ab2  retn
```
