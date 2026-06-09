# TimeUpdate::HasNetwork(void)

- ea: `0x180007220`
- end: `0x180007272`
- name: `?HasNetwork@TimeUpdate@@AEBA_NXZ`
- size: `82`
- prototype: `bool __fastcall(TimeUpdate *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800061ac`
- `0x1800064e4`

## callees

- `0x180001010`
- `0x1800012f0`
- `0x180007220`

## pseudocode

```c
bool __fastcall TimeUpdate::HasNetwork(TimeUpdate *this)
{
  char v1; // bl

  v1 = *((_BYTE *)this + 241);
  if ( !v1 && (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)&word_1800165DE,
      0,
      0);
  return v1;
}

```

## disassembly

```asm
0x180007220  push    rbx
0x180007222  sub     rsp, 20h
0x180007226  mov     bl, [rcx+0F1h]
0x18000722c  nop
0x18000722d  test    bl, bl
0x18000722f  jnz     short loc_18000726A
0x180007231  mov     eax, cs:dword_18001C010
0x180007237  cmp     eax, 4
0x18000723a  jbe     short loc_18000726A
0x18000723c  mov     edx, 1
0x180007241  lea     rcx, dword_18001C010
0x180007248  call    _tlgKeywordOn
0x18000724d  test    al, al
0x18000724f  jz      short loc_18000726A
0x180007251  xor     r9d, r9d
0x180007254  lea     rdx, word_1800165DE
0x18000725b  xor     r8d, r8d
0x18000725e  lea     rcx, dword_18001C010
0x180007265  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000726a  mov     al, bl
0x18000726c  add     rsp, 20h
0x180007270  pop     rbx
0x180007271  retn
```
