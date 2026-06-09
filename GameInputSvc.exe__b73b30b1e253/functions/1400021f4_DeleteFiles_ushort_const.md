# DeleteFiles(ushort const *)

- ea: `0x1400021f4`
- end: `0x140002339`
- name: `?DeleteFiles@@YAJPEBG@Z`
- size: `325`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140002ac0`

## callees

- `0x140001008`
- `0x1400021f4`
- `0x140004c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002210`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140002202`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140002202`

## pseudocode

```c
__int64 __fastcall DeleteFiles(LPCWSTR lpFileName)
{
  DWORD LastError; // eax
  int v3; // r8d
  int v4; // r9d
  int v5; // ebx
  int v6; // r9d
  DWORD v8; // [rsp+68h] [rbp+28h] BYREF
  int v9; // [rsp+70h] [rbp+30h] BYREF
  const char *v10; // [rsp+78h] [rbp+38h] BYREF

  if ( !DeleteFileW(lpFileName) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 2 )
    {
      if ( LastError != 5 )
      {
        if ( LastError )
        {
          if ( (unsigned int)dword_14000E000 > 2
            && (qword_14000E010 & 0x800) != 0
            && (qword_14000E018 & 0x800) == qword_14000E018 )
          {
            v8 = LastError;
            v10 = "onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
            v9 = 141;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              qword_14000E018,
              (unsigned int)word_14000A5C2,
              v3,
              v4,
              (__int64)&v10,
              (__int64)&v9,
              (__int64)&v8);
          }
          if ( v5 > 0 )
            return (unsigned __int16)v5 | 0x80070000;
        }
        return (unsigned int)v5;
      }
      v5 = ModifySystemFile(0, lpFileName);
      if ( v5 < 0 )
      {
        if ( (unsigned int)dword_14000E000 > 2
          && (qword_14000E010 & 0x800) != 0
          && (qword_14000E018 & 0x800) == qword_14000E018 )
        {
          v8 = v5;
          v10 = "onecore\\xbox\\gameinput\\published\\svc\\util.cpp";
          v9 = 137;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_14000E010,
            (unsigned int)word_14000A602,
            qword_14000E018,
            v6,
            (__int64)&v10,
            (__int64)&v9,
            (__int64)&v8);
        }
        return (unsigned int)v5;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400021f4  push    rbp
0x1400021f6  push    rbx
0x1400021f7  push    rdi
0x1400021f8  mov     rbp, rsp
0x1400021fb  sub     rsp, 40h
0x1400021ff  mov     rdi, rcx
0x140002202  call    cs:__imp_DeleteFileW
0x140002208  test    eax, eax
0x14000220a  jnz     loc_14000232F
0x140002210  call    cs:__imp_GetLastError
0x140002216  mov     ebx, eax
0x140002218  cmp     eax, 2
0x14000221b  jz      loc_14000232F
0x140002221  cmp     eax, 5
0x140002224  jnz     loc_1400022AF
0x14000222a  mov     rdx, rdi; lpFileName
0x14000222d  xor     ecx, ecx; lpExistingFileName
0x14000222f  call    ?ModifySystemFile@@YAJPEBG0@Z; ModifySystemFile(ushort const *,ushort const *)
0x140002234  mov     ebx, eax
0x140002236  test    eax, eax
0x140002238  jns     loc_14000232F
0x14000223e  mov     ecx, cs:dword_14000E000
0x140002244  cmp     ecx, 2
0x140002247  jbe     short loc_1400022A8
0x140002249  mov     r8, cs:qword_14000E018
0x140002250  mov     edx, 800h
0x140002255  mov     rcx, cs:qword_14000E010
0x14000225c  test    rdx, rcx
0x14000225f  jz      short loc_1400022A8
0x140002261  mov     rax, r8
0x140002264  and     rax, rdx
0x140002267  cmp     rax, r8
0x14000226a  jnz     short loc_1400022A8
0x14000226c  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x140002273  mov     [rbp+arg_8], ebx
0x140002276  mov     [rbp+arg_18], rax
0x14000227a  lea     rdx, word_14000A602
0x140002281  lea     rax, [rbp+arg_8]
0x140002285  mov     [rbp+arg_10], 89h
0x14000228c  mov     [rsp+40h+var_10], rax
0x140002291  lea     rax, [rbp+arg_10]
0x140002295  mov     [rsp+40h+var_18], rax
0x14000229a  lea     rax, [rbp+arg_18]
0x14000229e  mov     [rsp+40h+var_20], rax
0x1400022a3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400022a8  mov     eax, ebx
0x1400022aa  jmp     loc_140002331
0x1400022af  test    ebx, ebx
0x1400022b1  jz      short loc_1400022A8
0x1400022b3  mov     eax, cs:dword_14000E000
0x1400022b9  cmp     eax, 2
0x1400022bc  jbe     short loc_14000231D
0x1400022be  mov     rcx, cs:qword_14000E018
0x1400022c5  mov     edx, 800h
0x1400022ca  mov     rax, cs:qword_14000E010
0x1400022d1  test    rdx, rax
0x1400022d4  jz      short loc_14000231D
0x1400022d6  mov     rax, rcx
0x1400022d9  and     rax, rdx
0x1400022dc  cmp     rax, rcx
0x1400022df  jnz     short loc_14000231D
0x1400022e1  lea     rax, aOnecoreXboxGam_1; "onecore\\xbox\\gameinput\\published\\sv"...
0x1400022e8  mov     [rbp+arg_8], ebx
0x1400022eb  mov     [rbp+arg_18], rax
0x1400022ef  lea     rdx, word_14000A5C2
0x1400022f6  lea     rax, [rbp+arg_8]
0x1400022fa  mov     [rbp+arg_10], 8Dh
0x140002301  mov     [rsp+40h+var_10], rax
0x140002306  lea     rax, [rbp+arg_10]
0x14000230a  mov     [rsp+40h+var_18], rax
0x14000230f  lea     rax, [rbp+arg_18]
0x140002313  mov     [rsp+40h+var_20], rax
0x140002318  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000231d  test    ebx, ebx
0x14000231f  jle     short loc_1400022A8
0x140002321  movzx   ebx, bx
0x140002324  or      ebx, 80070000h
0x14000232a  jmp     loc_1400022A8
0x14000232f  xor     eax, eax
0x140002331  add     rsp, 40h
0x140002335  pop     rdi
0x140002336  pop     rbx
0x140002337  pop     rbp
0x140002338  retn
```
