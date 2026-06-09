# TimeUpdate::IsRunning(void)

- ea: `0x180007a5c`
- end: `0x180007aab`
- name: `?IsRunning@TimeUpdate@@AEBA_NXZ`
- size: `79`
- prototype: `bool __fastcall(TimeUpdate *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180003b50`
- `0x1800064e4`
- `0x18000743c`
- `0x1800084c4`

## callees

- `0x180001010`
- `0x1800012f0`
- `0x180007a5c`

## pseudocode

```c
bool __fastcall TimeUpdate::IsRunning(TimeUpdate *this)
{
  char v1; // bl

  v1 = *((_BYTE *)this + 56);
  if ( !v1 && (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)byte_180016665,
      0,
      0);
  return v1;
}

```

## disassembly

```asm
0x180007a5c  push    rbx
0x180007a5e  sub     rsp, 20h
0x180007a62  mov     bl, [rcx+38h]
0x180007a65  nop
0x180007a66  test    bl, bl
0x180007a68  jnz     short loc_180007AA3
0x180007a6a  mov     eax, cs:dword_18001C010
0x180007a70  cmp     eax, 4
0x180007a73  jbe     short loc_180007AA3
0x180007a75  mov     edx, 1
0x180007a7a  lea     rcx, dword_18001C010
0x180007a81  call    _tlgKeywordOn
0x180007a86  test    al, al
0x180007a88  jz      short loc_180007AA3
0x180007a8a  xor     r9d, r9d
0x180007a8d  lea     rdx, byte_180016665
0x180007a94  xor     r8d, r8d
0x180007a97  lea     rcx, dword_18001C010
0x180007a9e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180007aa3  mov     al, bl
0x180007aa5  add     rsp, 20h
0x180007aa9  pop     rbx
0x180007aaa  retn
```
