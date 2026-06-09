# GetModuleProc<long (*)(HINSTANCE__ *,ulong,_GUID const &,void * *,IUnknown *)>(HINSTANCE__ *,char const *,long (**)(HINSTANCE__ *,ulong,_GUID const &,void * *,IUnknown *))

- ea: `0x18000da08`
- end: `0x18000dacf`
- name: `??$GetModuleProc@P6AJPEAUHINSTANCE__@@KAEBU_GUID@@PEAPEAXPEAUIUnknown@@@Z@@YAJPEAUHINSTANCE__@@PEBDPEAP6AJ0KAEBU_GUID@@PEAPEAXPEAUIUnknown@@@Z@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800169fc`

## callees

- `0x180001304`
- `0x18000da08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000da1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000da1c`

## string_xrefs

- `0x18000da12`: `DirectInput8Create`

## pseudocode

```c
__int64 __fastcall GetModuleProc<long (*)(HINSTANCE__ *,unsigned long,_GUID const &,void * *,IUnknown *)>(
        HMODULE a1,
        __int64 a2,
        FARPROC *a3)
{
  FARPROC ProcAddress; // rax
  signed int LastError; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v9; // [rsp+58h] [rbp+10h] BYREF
  int v10; // [rsp+60h] [rbp+18h] BYREF
  const char *v11; // [rsp+68h] [rbp+20h] BYREF

  v9 = a2;
  ProcAddress = GetProcAddress(a1, "DirectInput8Create");
  *a3 = ProcAddress;
  if ( ProcAddress )
    return 0;
  LastError = GetLastError();
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    LODWORD(v9) = LastError;
    v11 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackUtil.h";
    v10 = 14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned __int8 *)&unk_18005AAB8,
      v6,
      v7,
      (__int64 **)&v11,
      (__int64)&v10,
      (__int64)&v9);
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
0x18000da08  mov     [rsp+arg_8], rdx
0x18000da0d  push    rbx
0x18000da0e  sub     rsp, 40h
0x18000da12  lea     rdx, aDirectinput8cr; "DirectInput8Create"
0x18000da19  mov     rbx, r8
0x18000da1c  call    cs:__imp_GetProcAddress
0x18000da23  nop     dword ptr [rax+rax+00h]
0x18000da28  mov     [rbx], rax
0x18000da2b  test    rax, rax
0x18000da2e  jnz     loc_18000DAC6
0x18000da34  call    cs:__imp_GetLastError
0x18000da3b  nop     dword ptr [rax+rax+00h]
0x18000da40  mov     ebx, eax
0x18000da42  mov     eax, cs:dword_180069000
0x18000da48  cmp     eax, 2
0x18000da4b  jbe     short loc_18000DAAC
0x18000da4d  mov     rcx, cs:qword_180069018
0x18000da54  mov     rax, cs:qword_180069010
0x18000da5b  test    al, 8
0x18000da5d  jz      short loc_18000DAAC
0x18000da5f  mov     rax, rcx
0x18000da62  and     eax, 8
0x18000da65  cmp     rax, rcx
0x18000da68  jnz     short loc_18000DAAC
0x18000da6a  lea     rax, aOnecoreXboxGam_42; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x18000da71  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000da75  mov     [rsp+48h+arg_18], rax
0x18000da7a  lea     rdx, unk_18005AAB8
0x18000da81  lea     rax, [rsp+48h+arg_8]
0x18000da86  mov     [rsp+48h+arg_10], 0Eh
0x18000da8e  mov     [rsp+48h+var_18], rax
0x18000da93  lea     rax, [rsp+48h+arg_10]
0x18000da98  mov     [rsp+48h+var_20], rax
0x18000da9d  lea     rax, [rsp+48h+arg_18]
0x18000daa2  mov     [rsp+48h+var_28], rax
0x18000daa7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000daac  test    ebx, ebx
0x18000daae  jnz     short loc_18000DAB7
0x18000dab0  mov     ebx, 8000FFFFh
0x18000dab5  jmp     short loc_18000DAC2
0x18000dab7  jle     short loc_18000DAC2
0x18000dab9  movzx   ebx, bx
0x18000dabc  or      ebx, 80070000h
0x18000dac2  mov     eax, ebx
0x18000dac4  jmp     short loc_18000DAC8
0x18000dac6  xor     eax, eax
0x18000dac8  add     rsp, 40h
0x18000dacc  pop     rbx
0x18000dacd  retn
```
