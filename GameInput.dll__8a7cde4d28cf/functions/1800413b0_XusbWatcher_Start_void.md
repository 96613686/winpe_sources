# XusbWatcher::Start(void)

- ea: `0x1800413b0`
- end: `0x18004147c`
- name: `?Start@XusbWatcher@@QEAAXXZ`
- size: `204`
- prototype: `void __fastcall(XusbWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003ee94`

## callees

- `0x180001304`
- `0x1800413b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800413e3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800413e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800413f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800413f8`

## pseudocode

```c
void __fastcall XusbWatcher::Start(XusbWatcher *this)
{
  HANDLE Thread; // rax
  DWORD LastError; // eax
  int v4; // r9d
  DWORD v5; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+58h] [rbp+10h] BYREF
  const char *v7; // [rsp+60h] [rbp+18h] BYREF

  if ( !*((_QWORD *)this + 4) )
  {
    Thread = CreateThread(0, 0, XusbWatcher::WorkerThreadProc, this, 0, 0);
    *((_QWORD *)this + 4) = Thread;
    if ( !Thread )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 > 2
        && (qword_180069010 & 0x400) != 0
        && (qword_180069018 & 0x400) == qword_180069018 )
      {
        v5 = LastError;
        v6 = 111;
        v7 = "onecore\\xbox\\gameinput\\server\\XusbWatcher.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069018 & 0x400,
          (unsigned int)byte_18005F62B,
          1024,
          v4,
          (__int64)&v7,
          (__int64)&v6,
          (__int64)&v5);
      }
    }
  }
}

```

## disassembly

```asm
0x1800413b0  push    rbx
0x1800413b2  sub     rsp, 40h
0x1800413b6  cmp     qword ptr [rcx+20h], 0
0x1800413bb  mov     rbx, rcx
0x1800413be  jnz     loc_180041475
0x1800413c4  mov     r9, rcx; lpParameter
0x1800413c7  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x1800413d0  xor     ecx, ecx; lpThreadAttributes
0x1800413d2  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800413da  lea     r8, ?WorkerThreadProc@XusbWatcher@@CAKPEAX@Z; lpStartAddress
0x1800413e1  xor     edx, edx; dwStackSize
0x1800413e3  call    cs:__imp_CreateThread
0x1800413ea  nop     dword ptr [rax+rax+00h]
0x1800413ef  mov     [rbx+20h], rax
0x1800413f3  test    rax, rax
0x1800413f6  jnz     short loc_180041475
0x1800413f8  call    cs:__imp_GetLastError
0x1800413ff  nop     dword ptr [rax+rax+00h]
0x180041404  mov     ecx, cs:dword_180069000
0x18004140a  cmp     ecx, 2
0x18004140d  jbe     short loc_180041475
0x18004140f  mov     rdx, cs:qword_180069018
0x180041416  mov     r8d, 400h
0x18004141c  mov     rcx, cs:qword_180069010
0x180041423  test    r8, rcx
0x180041426  jz      short loc_180041475
0x180041428  mov     rcx, rdx
0x18004142b  and     rcx, r8
0x18004142e  cmp     rcx, rdx
0x180041431  jnz     short loc_180041475
0x180041433  mov     [rsp+48h+arg_0], eax
0x180041437  lea     rdx, byte_18005F62B
0x18004143e  lea     rax, aOnecoreXboxGam_4; "onecore\\xbox\\gameinput\\server\\XusbW"...
0x180041445  mov     [rsp+48h+arg_8], 6Fh ; 'o'
0x18004144d  mov     [rsp+48h+arg_10], rax
0x180041452  lea     rax, [rsp+48h+arg_0]
0x180041457  mov     [rsp+48h+var_18], rax
0x18004145c  lea     rax, [rsp+48h+arg_8]
0x180041461  mov     [rsp+48h+lpThreadId], rax
0x180041466  lea     rax, [rsp+48h+arg_10]
0x18004146b  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x180041470  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041475  add     rsp, 40h
0x180041479  pop     rbx
0x18004147a  retn
```
