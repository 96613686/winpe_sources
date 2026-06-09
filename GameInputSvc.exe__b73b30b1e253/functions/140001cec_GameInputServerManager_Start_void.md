# GameInputServerManager::Start(void)

- ea: `0x140001cec`
- end: `0x140001d7a`
- name: `?Start@GameInputServerManager@@QEAAJXZ`
- size: `142`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION **this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005a88`

## callees

- `0x140001008`
- `0x14000199c`
- `0x140001cec`

## pseudocode

```c
__int64 __fastcall GameInputServerManager::Start(struct _RTL_CRITICAL_SECTION **this)
{
  int GameInput; // ebx
  __int64 v2; // r9
  int v4; // [rsp+58h] [rbp+10h] BYREF
  int v5; // [rsp+60h] [rbp+18h] BYREF
  const char *v6; // [rsp+68h] [rbp+20h] BYREF

  GameInput = GameInputServerManager::LoadGameInput(this);
  if ( GameInput >= 0 )
    return 0;
  if ( (unsigned int)dword_14000E000 > 2
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    v4 = GameInput;
    v6 = "onecore\\xbox\\gameinput\\published\\svc\\gameinputservermanager.cpp";
    v5 = 15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_14000E010,
      (int)byte_14000A4F5,
      2048,
      v2,
      (__int64 **)&v6,
      (__int64)&v5,
      (__int64)&v4);
  }
  return (unsigned int)GameInput;
}

```

## disassembly

```asm
0x140001cec  push    rbx
0x140001cee  sub     rsp, 40h
0x140001cf2  call    ?LoadGameInput@GameInputServerManager@@AEAAJXZ; GameInputServerManager::LoadGameInput(void)
0x140001cf7  mov     ebx, eax
0x140001cf9  test    eax, eax
0x140001cfb  jns     short loc_140001D72
0x140001cfd  mov     ecx, cs:dword_14000E000
0x140001d03  cmp     ecx, 2
0x140001d06  jbe     short loc_140001D6E
0x140001d08  mov     rdx, cs:qword_14000E018
0x140001d0f  mov     r8d, 800h
0x140001d15  mov     rcx, cs:qword_14000E010
0x140001d1c  test    r8, rcx
0x140001d1f  jz      short loc_140001D6E
0x140001d21  mov     rax, rdx
0x140001d24  and     rax, r8
0x140001d27  cmp     rax, rdx
0x140001d2a  jnz     short loc_140001D6E
0x140001d2c  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\published\\sv"...
0x140001d33  mov     [rsp+48h+arg_8], ebx
0x140001d37  mov     [rsp+48h+arg_18], rax
0x140001d3c  lea     rdx, byte_14000A4F5
0x140001d43  lea     rax, [rsp+48h+arg_8]
0x140001d48  mov     [rsp+48h+arg_10], 0Fh
0x140001d50  mov     [rsp+48h+var_18], rax
0x140001d55  lea     rax, [rsp+48h+arg_10]
0x140001d5a  mov     [rsp+48h+var_20], rax
0x140001d5f  lea     rax, [rsp+48h+arg_18]
0x140001d64  mov     [rsp+48h+var_28], rax
0x140001d69  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140001d6e  mov     eax, ebx
0x140001d70  jmp     short loc_140001D74
0x140001d72  xor     eax, eax
0x140001d74  add     rsp, 40h
0x140001d78  pop     rbx
0x140001d79  retn
```
