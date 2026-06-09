# EnableRedirectionGuard

- ea: `0x1400059bc`
- end: `0x140005a81`
- name: `EnableRedirectionGuard`
- size: `197`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140005cb8`

## callees

- `0x140001008`
- `0x1400059bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059e7`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x1400059d9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x1400059d9`

## pseudocode

```c
__int64 EnableRedirectionGuard()
{
  signed int LastError; // ebx
  __int64 v1; // r8
  __int64 v2; // r9
  int v4; // [rsp+50h] [rbp+8h] BYREF
  signed int v5; // [rsp+58h] [rbp+10h] BYREF
  int v6; // [rsp+60h] [rbp+18h] BYREF
  const char *v7; // [rsp+68h] [rbp+20h] BYREF

  v4 = 1;
  if ( (unsigned int)SetProcessMitigationPolicy(16, &v4) )
    return 0;
  LastError = GetLastError();
  if ( (unsigned int)dword_14000E000 > 2
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    v5 = LastError;
    v7 = "onecore\\xbox\\gameinput\\published\\svc\\winmain.cpp";
    v6 = 115;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_14000E018,
      (int)&dword_14000B7A4,
      v1,
      v2,
      (__int64 **)&v7,
      (__int64)&v6,
      (__int64)&v5);
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

```

## disassembly

```asm
0x1400059bc  push    rbx
0x1400059be  sub     rsp, 40h
0x1400059c2  mov     r8d, 4
0x1400059c8  mov     [rsp+48h+arg_0], 1
0x1400059d0  lea     rdx, [rsp+48h+arg_0]
0x1400059d5  lea     ecx, [r8+0Ch]
0x1400059d9  call    cs:__imp_SetProcessMitigationPolicy
0x1400059df  test    eax, eax
0x1400059e1  jnz     loc_140005A79
0x1400059e7  call    cs:__imp_GetLastError
0x1400059ed  mov     ebx, eax
0x1400059ef  mov     eax, cs:dword_14000E000
0x1400059f5  cmp     eax, 2
0x1400059f8  jbe     short loc_140005A5F
0x1400059fa  mov     rcx, cs:qword_14000E018
0x140005a01  mov     edx, 800h
0x140005a06  mov     rax, cs:qword_14000E010
0x140005a0d  test    rdx, rax
0x140005a10  jz      short loc_140005A5F
0x140005a12  mov     rax, rcx
0x140005a15  and     rax, rdx
0x140005a18  cmp     rax, rcx
0x140005a1b  jnz     short loc_140005A5F
0x140005a1d  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\published\\sv"...
0x140005a24  mov     [rsp+48h+arg_8], ebx
0x140005a28  mov     [rsp+48h+arg_18], rax
0x140005a2d  lea     rdx, dword_14000B7A4
0x140005a34  lea     rax, [rsp+48h+arg_8]
0x140005a39  mov     [rsp+48h+arg_10], 73h ; 's'
0x140005a41  mov     [rsp+48h+var_18], rax
0x140005a46  lea     rax, [rsp+48h+arg_10]
0x140005a4b  mov     [rsp+48h+var_20], rax
0x140005a50  lea     rax, [rsp+48h+arg_18]
0x140005a55  mov     [rsp+48h+var_28], rax
0x140005a5a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140005a5f  test    ebx, ebx
0x140005a61  jnz     short loc_140005A6A
0x140005a63  mov     ebx, 8000FFFFh
0x140005a68  jmp     short loc_140005A75
0x140005a6a  jle     short loc_140005A75
0x140005a6c  movzx   ebx, bx
0x140005a6f  or      ebx, 80070000h
0x140005a75  mov     eax, ebx
0x140005a77  jmp     short loc_140005A7B
0x140005a79  xor     eax, eax
0x140005a7b  add     rsp, 40h
0x140005a7f  pop     rbx
0x140005a80  retn
```
