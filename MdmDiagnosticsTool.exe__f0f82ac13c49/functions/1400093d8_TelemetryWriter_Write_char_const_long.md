# TelemetryWriter::Write(char const *,long)

- ea: `0x1400093d8`
- end: `0x140009461`
- name: `?Write@TelemetryWriter@@QEAAXPEBDJ@Z`
- size: `137`
- prototype: `void __fastcall(TelemetryWriter *__hidden this, const char *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140008130`
- `0x140009db6`

## callees

- `0x14000104c`
- `0x140001248`
- `0x1400093d8`

## pseudocode

```c
void __fastcall TelemetryWriter::Write(TelemetryWriter *this, const char *a2, int a3)
{
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+60h] [rbp+18h]
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  if ( (unsigned int)dword_140011000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140011000, 0x400000000000LL) )
  {
    v8 = a3;
    v7 = v6;
    v9 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)byte_14000E931,
      (__int64)this + 12,
      v6,
      (__int64)&v9,
      &v7);
  }
  if ( a3 < 0 )
    *(_DWORD *)this = a3;
}

```

## disassembly

```asm
0x1400093d8  mov     [rsp+arg_8], rbx
0x1400093dd  push    rdi
0x1400093de  sub     rsp, 40h
0x1400093e2  mov     eax, cs:dword_140011000
0x1400093e8  mov     ebx, r8d
0x1400093eb  mov     r9, rdx
0x1400093ee  mov     rdi, rcx
0x1400093f1  cmp     eax, 5
0x1400093f4  jbe     short loc_140009450
0x1400093f6  mov     rdx, 400000000000h
0x140009400  lea     rcx, dword_140011000
0x140009407  call    _tlgKeywordOn
0x14000940c  test    al, al
0x14000940e  jz      short loc_140009450
0x140009410  lea     rax, [rsp+48h+arg_10]
0x140009415  mov     [rsp+48h+arg_10], ebx
0x140009419  mov     [rsp+48h+var_18], rax
0x14000941e  lea     r8, [rdi+0Ch]
0x140009422  lea     rax, [rsp+48h+arg_0]
0x140009427  mov     [rsp+48h+arg_0], r9
0x14000942c  mov     [rsp+48h+var_20], rax
0x140009431  lea     rdx, byte_14000E931
0x140009438  lea     rax, [rsp+48h+arg_18]
0x14000943d  mov     [rsp+48h+arg_18], 1000000h
0x140009446  mov     [rsp+48h+var_28], rax
0x14000944b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140009450  test    ebx, ebx
0x140009452  jns     short loc_140009456
0x140009454  mov     [rdi], ebx
0x140009456  mov     rbx, [rsp+48h+arg_8]
0x14000945b  add     rsp, 40h
0x14000945f  pop     rdi
0x140009460  retn
```
