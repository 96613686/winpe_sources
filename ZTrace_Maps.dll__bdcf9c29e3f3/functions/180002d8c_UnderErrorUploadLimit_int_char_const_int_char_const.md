# UnderErrorUploadLimit(int,char const *,int,char const *)

- ea: `0x180002d8c`
- end: `0x180002e51`
- name: `?UnderErrorUploadLimit@@YAHHPEBDH0@Z`
- size: `197`
- prototype: `_BOOL8 __fastcall(int, const char *, __int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028d4`
- `0x180002a54`
- `0x18000308c`

## callees

- `0x18000108c`
- `0x180002d8c`

## pseudocode

```c
_BOOL8 __fastcall UnderErrorUploadLimit(int a1, const char *a2, __int64 a3, const char *a4)
{
  signed __int32 v4; // ebx
  int v6; // [rsp+50h] [rbp-28h] BYREF
  int v7; // [rsp+54h] [rbp-24h] BYREF
  __int64 v8; // [rsp+58h] [rbp-20h]
  const char *v9; // [rsp+60h] [rbp-18h] BYREF
  const char *v10; // [rsp+68h] [rbp-10h] BYREF

  v4 = _InterlockedExchangeAdd(&dword_180007240, 1u);
  if ( v4 == 300
    && (unsigned int)dword_180007000 > 5
    && (qword_180007010 & 0x400000000000LL) != 0
    && (qword_180007018 & 0x400000000000LL) == qword_180007018 )
  {
    v10 = a2;
    v8 = 50331648;
    v9 = a4;
    v6 = a3;
    v7 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      qword_180007018,
      (__int64)byte_180005BE5,
      a3,
      (__int64)a4,
      (__int64)&v7,
      &v10,
      (__int64)&v6,
      &v9);
  }
  return v4 < 300;
}

```

## disassembly

```asm
0x180002d8c  push    rbx
0x180002d8e  sub     rsp, 70h
0x180002d92  mov     r10d, ecx
0x180002d95  mov     ebx, 1
0x180002d9a  lock xadd cs:dword_180007240, ebx
0x180002da2  cmp     ebx, 12Ch
0x180002da8  jnz     loc_180002E40
0x180002dae  mov     eax, cs:dword_180007000
0x180002db4  cmp     eax, 5
0x180002db7  jbe     loc_180002E40
0x180002dbd  mov     rcx, cs:qword_180007018
0x180002dc4  mov     r11, 400000000000h
0x180002dce  mov     rax, cs:qword_180007010
0x180002dd5  test    r11, rax
0x180002dd8  jz      short loc_180002E40
0x180002dda  mov     rax, rcx
0x180002ddd  and     rax, r11
0x180002de0  cmp     rax, rcx
0x180002de3  jnz     short loc_180002E40
0x180002de5  lea     rax, [rsp+78h+var_20]
0x180002dea  mov     [rsp+78h+var_10], rdx
0x180002def  mov     [rsp+78h+var_38], rax
0x180002df4  lea     rdx, byte_180005BE5
0x180002dfb  lea     rax, [rsp+78h+var_18]
0x180002e00  mov     [rsp+78h+var_20], 3000000h
0x180002e09  mov     [rsp+78h+var_40], rax
0x180002e0e  lea     rax, [rsp+78h+var_28]
0x180002e13  mov     [rsp+78h+var_48], rax
0x180002e18  lea     rax, [rsp+78h+var_10]
0x180002e1d  mov     [rsp+78h+var_50], rax
0x180002e22  lea     rax, [rsp+78h+var_24]
0x180002e27  mov     [rsp+78h+var_58], rax
0x180002e2c  mov     [rsp+78h+var_18], r9
0x180002e31  mov     [rsp+78h+var_28], r8d
0x180002e36  mov     [rsp+78h+var_24], r10d
0x180002e3b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@34AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180002e40  xor     eax, eax
0x180002e42  cmp     ebx, 12Ch
0x180002e48  setl    al
0x180002e4b  add     rsp, 70h
0x180002e4f  pop     rbx
0x180002e50  retn
```
