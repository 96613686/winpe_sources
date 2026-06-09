# TelemetryWriter::Write(char const *,long)

- ea: `0x140009a08`
- end: `0x140009a92`
- name: `?Write@TelemetryWriter@@QEAAXPEBDJ@Z`
- size: `138`
- prototype: `void __fastcall(TelemetryWriter *__hidden this, const char *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140008694`
- `0x14000a3eb`

## callees

- `0x14000104c`
- `0x140001258`
- `0x140009a08`

## pseudocode

```c
void __fastcall TelemetryWriter::Write(TelemetryWriter *this, const char *a2, __int64 a3)
{
  int v3; // ebx
  int v5; // ecx
  __int64 v6; // r9
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+60h] [rbp+18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  v3 = a3;
  if ( (unsigned int)dword_140012000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140012000, 0x400000000000LL, a3, a2) )
  {
    v8 = v3;
    v7 = v6;
    v9 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_14000F931,
      (_DWORD)this + 12,
      v6,
      (__int64)&v9,
      (__int64)&v7,
      (__int64)&v8);
  }
  if ( v3 < 0 )
    *(_DWORD *)this = v3;
}

```

## disassembly

```asm
0x140009a08  mov     [rsp+arg_8], rbx
0x140009a0d  push    rdi
0x140009a0e  sub     rsp, 40h
0x140009a12  mov     eax, cs:dword_140012000
0x140009a18  mov     ebx, r8d
0x140009a1b  mov     r9, rdx
0x140009a1e  mov     rdi, rcx
0x140009a21  cmp     eax, 5
0x140009a24  jbe     short loc_140009A80
0x140009a26  mov     rdx, 400000000000h
0x140009a30  lea     rcx, dword_140012000
0x140009a37  call    _tlgKeywordOn
0x140009a3c  test    al, al
0x140009a3e  jz      short loc_140009A80
0x140009a40  lea     rax, [rsp+48h+arg_10]
0x140009a45  mov     [rsp+48h+arg_10], ebx
0x140009a49  mov     [rsp+48h+var_18], rax
0x140009a4e  lea     r8, [rdi+0Ch]
0x140009a52  lea     rax, [rsp+48h+arg_0]
0x140009a57  mov     [rsp+48h+arg_0], r9
0x140009a5c  mov     [rsp+48h+var_20], rax
0x140009a61  lea     rdx, byte_14000F931
0x140009a68  lea     rax, [rsp+48h+arg_18]
0x140009a6d  mov     [rsp+48h+arg_18], 1000000h
0x140009a76  mov     [rsp+48h+var_28], rax
0x140009a7b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140009a80  test    ebx, ebx
0x140009a82  jns     short loc_140009A86
0x140009a84  mov     [rdi], ebx
0x140009a86  mov     rbx, [rsp+48h+arg_8]
0x140009a8b  add     rsp, 40h
0x140009a8f  pop     rdi
0x140009a90  retn
```
