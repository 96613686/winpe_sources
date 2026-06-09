# GameInputServerManager::WaitForStopOnEvent(ushort const *)

- ea: `0x140001d80`
- end: `0x140001e55`
- name: `?WaitForStopOnEvent@GameInputServerManager@@QEAAJPEBG@Z`
- size: `213`
- prototype: `__int64 __fastcall(GameInputServerManager *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005a88`

## callees

- `0x140001008`
- `0x140001d80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140001d94`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140001d94`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140001e3e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140001e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001da6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001e47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001e47`

## pseudocode

```c
__int64 __fastcall GameInputServerManager::WaitForStopOnEvent(GameInputServerManager *this, const unsigned __int16 *a2)
{
  HANDLE v2; // rax
  void *v3; // rbx
  signed int LastError; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  GameInputServerManager *v8; // [rsp+50h] [rbp+8h] BYREF
  int v9; // [rsp+60h] [rbp+18h] BYREF
  const char *v10; // [rsp+68h] [rbp+20h] BYREF

  v8 = this;
  v2 = OpenEventW(0x100000u, 0, a2);
  v3 = v2;
  if ( v2 )
  {
    WaitForSingleObject(v2, 0xFFFFFFFF);
    CloseHandle(v3);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      LODWORD(v8) = LastError;
      v10 = "onecore\\xbox\\gameinput\\published\\svc\\gameinputservermanager.cpp";
      v9 = 23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (int)byte_14000A4B5,
        v5,
        v6,
        (__int64 **)&v10,
        (__int64)&v9,
        (__int64)&v8);
    }
    if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147418113;
    }
    return (unsigned int)LastError;
  }
}

```

## disassembly

```asm
0x140001d80  mov     [rsp+arg_0], rcx
0x140001d85  push    rbx
0x140001d86  sub     rsp, 40h
0x140001d8a  mov     r8, rdx; lpName
0x140001d8d  mov     ecx, 100000h; dwDesiredAccess
0x140001d92  xor     edx, edx; bInheritHandle
0x140001d94  call    cs:__imp_OpenEventW
0x140001d9a  mov     rbx, rax
0x140001d9d  test    rax, rax
0x140001da0  jnz     loc_140001E38
0x140001da6  call    cs:__imp_GetLastError
0x140001dac  mov     ebx, eax
0x140001dae  mov     eax, cs:dword_14000E000
0x140001db4  cmp     eax, 2
0x140001db7  jbe     short loc_140001E1E
0x140001db9  mov     rcx, cs:qword_14000E018
0x140001dc0  mov     edx, 800h
0x140001dc5  mov     rax, cs:qword_14000E010
0x140001dcc  test    rdx, rax
0x140001dcf  jz      short loc_140001E1E
0x140001dd1  mov     rax, rcx
0x140001dd4  and     rax, rdx
0x140001dd7  cmp     rax, rcx
0x140001dda  jnz     short loc_140001E1E
0x140001ddc  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\published\\sv"...
0x140001de3  mov     dword ptr [rsp+48h+arg_0], ebx
0x140001de7  mov     [rsp+48h+arg_18], rax
0x140001dec  lea     rdx, byte_14000A4B5
0x140001df3  lea     rax, [rsp+48h+arg_0]
0x140001df8  mov     [rsp+48h+arg_10], 17h
0x140001e00  mov     [rsp+48h+var_18], rax
0x140001e05  lea     rax, [rsp+48h+arg_10]
0x140001e0a  mov     [rsp+48h+var_20], rax
0x140001e0f  lea     rax, [rsp+48h+arg_18]
0x140001e14  mov     [rsp+48h+var_28], rax
0x140001e19  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140001e1e  test    ebx, ebx
0x140001e20  jnz     short loc_140001E29
0x140001e22  mov     ebx, 8000FFFFh
0x140001e27  jmp     short loc_140001E34
0x140001e29  jle     short loc_140001E34
0x140001e2b  movzx   ebx, bx
0x140001e2e  or      ebx, 80070000h
0x140001e34  mov     eax, ebx
0x140001e36  jmp     short loc_140001E4F
0x140001e38  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140001e3b  mov     rcx, rbx; hHandle
0x140001e3e  call    cs:__imp_WaitForSingleObject
0x140001e44  mov     rcx, rbx; hObject
0x140001e47  call    cs:__imp_CloseHandle
0x140001e4d  xor     eax, eax
0x140001e4f  add     rsp, 40h
0x140001e53  pop     rbx
0x140001e54  retn
```
