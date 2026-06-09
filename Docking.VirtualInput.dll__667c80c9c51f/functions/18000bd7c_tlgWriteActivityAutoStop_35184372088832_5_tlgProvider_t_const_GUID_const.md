# _tlgWriteActivityAutoStop<35184372088832,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x18000bd7c`
- end: `0x18000bdff`
- name: `??$_tlgWriteActivityAutoStop@$0CAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000caa8`

## callees

- `0x180001c6c`
- `0x180002900`
- `0x18000bd7c`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<35184372088832,5>(_DWORD *a1, __int64 a2)
{
  __int64 v3; // [rsp+20h] [rbp-28h]

  LODWORD(v3) = *a1;
  HIDWORD(v3) = *a1;
  if ( *a1 > 5u && (unsigned __int8)tlgKeywordOn(a1, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      a1,
      byte_180020F0C,
      a2,
      0,
      v3);
  return 0;
}

```

## disassembly

```asm
0x18000bd7c  mov     [rsp+arg_8], rdx
0x18000bd81  mov     [rsp+arg_0], rcx
0x18000bd86  sub     rsp, 48h
0x18000bd8a  mov     rax, [rsp+48h+arg_0]
0x18000bd8f  mov     [rsp+48h+var_20], rax
0x18000bd94  mov     rax, [rsp+48h+var_20]
0x18000bd99  mov     [rsp+48h+var_18], rax
0x18000bd9e  mov     [rsp+48h+var_28], 0
0x18000bda6  mov     rax, [rsp+48h+var_18]
0x18000bdab  mov     eax, [rax]
0x18000bdad  mov     [rsp+48h+var_28], eax
0x18000bdb1  mov     eax, [rsp+48h+var_28]
0x18000bdb5  mov     [rsp+48h+var_24], eax
0x18000bdb9  mov     eax, [rsp+48h+var_24]
0x18000bdbd  cmp     eax, 5
0x18000bdc0  jbe     short loc_18000BDF4
0x18000bdc2  mov     rdx, cs:qword_180020F0F
0x18000bdc9  mov     rcx, [rsp+48h+var_20]
0x18000bdce  call    _tlgKeywordOn
0x18000bdd3  movzx   eax, al
0x18000bdd6  test    eax, eax
0x18000bdd8  jz      short loc_18000BDF4
0x18000bdda  xor     r9d, r9d
0x18000bddd  mov     r8, [rsp+48h+arg_8]
0x18000bde2  lea     rdx, byte_180020F0C
0x18000bde9  mov     rcx, [rsp+48h+var_20]
0x18000bdee  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000bdf3  nop
0x18000bdf4  xor     eax, eax
0x18000bdf6  test    eax, eax
0x18000bdf8  jnz     short loc_18000BD8A
0x18000bdfa  add     rsp, 48h
0x18000bdfe  retn
```
