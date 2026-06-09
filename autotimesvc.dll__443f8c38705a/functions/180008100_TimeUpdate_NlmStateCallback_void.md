# TimeUpdate::NlmStateCallback(void *)

- ea: `0x180008100`
- end: `0x1800081a6`
- name: `?NlmStateCallback@TimeUpdate@@CAXPEAX@Z`
- size: `166`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180001218`
- `0x1800012f0`
- `0x180008100`

## pseudocode

```c
void __fastcall TimeUpdate::NlmStateCallback(void *a1)
{
  __int16 *v1; // rdx

  if ( *((_DWORD *)a1 + 6) )
  {
    if ( (unsigned int)dword_18001C010 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 0x400000000200LL) )
    {
      v1 = word_18001672A;
LABEL_8:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18001C010,
        (__int64)v1,
        0,
        0);
    }
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)(*((_QWORD *)a1 + 2) + 576LL), *((_DWORD *)a1 + 8));
    if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 0x400000000200LL) )
    {
      v1 = (__int16 *)byte_1800167B5;
      goto LABEL_8;
    }
  }
}

```

## disassembly

```asm
0x180008100  sub     rsp, 38h
0x180008104  cmp     dword ptr [rcx+18h], 0
0x180008108  mov     r8, rcx
0x18000810b  jz      short loc_180008143
0x18000810d  mov     eax, cs:dword_18001C010
0x180008113  cmp     eax, 2
0x180008116  jbe     loc_1800081A1
0x18000811c  mov     rdx, 400000000200h
0x180008126  lea     rcx, dword_18001C010
0x18000812d  call    _tlgKeywordOn
0x180008132  test    al, al
0x180008134  jz      short loc_1800081A1
0x180008136  mov     eax, [r8+18h]
0x18000813a  lea     rdx, word_18001672A
0x180008141  jmp     short loc_180008181
0x180008143  mov     rcx, [rcx+10h]
0x180008147  mov     eax, [r8+20h]
0x18000814b  xchg    eax, [rcx+240h]
0x180008151  mov     eax, cs:dword_18001C010
0x180008157  cmp     eax, 4
0x18000815a  jbe     short loc_1800081A1
0x18000815c  mov     rdx, 400000000200h
0x180008166  lea     rcx, dword_18001C010
0x18000816d  call    _tlgKeywordOn
0x180008172  test    al, al
0x180008174  jz      short loc_1800081A1
0x180008176  mov     eax, [r8+20h]
0x18000817a  lea     rdx, byte_1800167B5
0x180008181  mov     [rsp+38h+arg_0], eax
0x180008185  lea     rcx, dword_18001C010
0x18000818c  lea     rax, [rsp+38h+arg_0]
0x180008191  xor     r9d, r9d
0x180008194  xor     r8d, r8d
0x180008197  mov     [rsp+38h+var_18], rax
0x18000819c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800081a1  add     rsp, 38h
0x1800081a5  retn
```
