# SetFileAttributesAndAcl(ushort const *,ulong,void *)

- ea: `0x14000563c`
- end: `0x140005783`
- name: `?SetFileAttributesAndAcl@@YAJPEBGKPEAX@Z`
- size: `327`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, DWORD, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x140004abc`
- `0x140004c20`

## callees

- `0x140001008`
- `0x14000563c`
- `0x14000578c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005662`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140005654`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140005654`

## pseudocode

```c
__int64 __fastcall SetFileAttributesAndAcl(LPWSTR pObjectName, DWORD a2, void *a3)
{
  enum _SE_OBJECT_TYPE v5; // edx
  signed int LastError; // ebx
  int v7; // r8d
  int v8; // r9d
  int v10; // r9d
  int v11; // [rsp+40h] [rbp-10h] BYREF
  const char *v12; // [rsp+48h] [rbp-8h] BYREF
  signed int v13; // [rsp+78h] [rbp+28h] BYREF

  if ( !SetFileAttributesW(pObjectName, a2) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v13 = LastError;
      v12 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
      v11 = 93;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (unsigned int)&byte_14000B6E7,
        v7,
        v8,
        (__int64)&v12,
        (__int64)&v11,
        (__int64)&v13);
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
  LastError = SetObjectSD(pObjectName, v5, a3);
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v13 = LastError;
      v12 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
      v11 = 98;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E010,
        (unsigned int)word_14000B6AA,
        qword_14000E018,
        v10,
        (__int64)&v12,
        (__int64)&v11,
        (__int64)&v13);
    }
    return (unsigned int)LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x14000563c  mov     [rsp-8+arg_0], rbx
0x140005641  mov     [rsp-8+arg_8], rdi
0x140005646  push    rbp
0x140005647  mov     rbp, rsp
0x14000564a  sub     rsp, 50h
0x14000564e  mov     rdi, r8
0x140005651  mov     rbx, rcx
0x140005654  call    cs:__imp_SetFileAttributesW
0x14000565a  test    eax, eax
0x14000565c  jnz     loc_1400056F1
0x140005662  call    cs:__imp_GetLastError
0x140005668  mov     ebx, eax
0x14000566a  mov     eax, cs:dword_14000E000
0x140005670  cmp     eax, 2
0x140005673  jbe     short loc_1400056D4
0x140005675  mov     rcx, cs:qword_14000E018
0x14000567c  mov     edx, 800h
0x140005681  mov     rax, cs:qword_14000E010
0x140005688  test    rdx, rax
0x14000568b  jz      short loc_1400056D4
0x14000568d  mov     rax, rcx
0x140005690  and     rax, rdx
0x140005693  cmp     rax, rcx
0x140005696  jnz     short loc_1400056D4
0x140005698  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x14000569f  mov     [rbp+arg_18], ebx
0x1400056a2  mov     [rbp+var_8], rax
0x1400056a6  lea     rdx, byte_14000B6E7
0x1400056ad  lea     rax, [rbp+arg_18]
0x1400056b1  mov     [rbp+var_10], 5Dh ; ']'
0x1400056b8  mov     [rsp+50h+var_20], rax
0x1400056bd  lea     rax, [rbp+var_10]
0x1400056c1  mov     [rsp+50h+var_28], rax
0x1400056c6  lea     rax, [rbp+var_8]
0x1400056ca  mov     [rsp+50h+var_30], rax
0x1400056cf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400056d4  test    ebx, ebx
0x1400056d6  jnz     short loc_1400056DF
0x1400056d8  mov     ebx, 8000FFFFh
0x1400056dd  jmp     short loc_1400056EA
0x1400056df  jle     short loc_1400056EA
0x1400056e1  movzx   ebx, bx
0x1400056e4  or      ebx, 80070000h
0x1400056ea  mov     eax, ebx
0x1400056ec  jmp     loc_140005773
0x1400056f1  mov     r8, rdi; void *
0x1400056f4  mov     rcx, rbx; pObjectName
0x1400056f7  call    ?SetObjectSD@@YAJPEBGW4_SE_OBJECT_TYPE@@PEAX@Z; SetObjectSD(ushort const *,_SE_OBJECT_TYPE,void *)
0x1400056fc  mov     ebx, eax
0x1400056fe  test    eax, eax
0x140005700  jns     short loc_140005771
0x140005702  mov     ecx, cs:dword_14000E000
0x140005708  cmp     ecx, 2
0x14000570b  jbe     short loc_1400056EA
0x14000570d  mov     r8, cs:qword_14000E018
0x140005714  mov     edx, 800h
0x140005719  mov     rcx, cs:qword_14000E010
0x140005720  test    rdx, rcx
0x140005723  jz      short loc_1400056EA
0x140005725  mov     rax, r8
0x140005728  and     rax, rdx
0x14000572b  cmp     rax, r8
0x14000572e  jnz     short loc_1400056EA
0x140005730  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x140005737  mov     [rbp+arg_18], ebx
0x14000573a  mov     [rbp+var_8], rax
0x14000573e  lea     rdx, word_14000B6AA
0x140005745  lea     rax, [rbp+arg_18]
0x140005749  mov     [rbp+var_10], 62h ; 'b'
0x140005750  mov     [rsp+50h+var_20], rax
0x140005755  lea     rax, [rbp+var_10]
0x140005759  mov     [rsp+50h+var_28], rax
0x14000575e  lea     rax, [rbp+var_8]
0x140005762  mov     [rsp+50h+var_30], rax
0x140005767  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000576c  jmp     loc_1400056EA
0x140005771  xor     eax, eax
0x140005773  mov     rbx, [rsp+50h+arg_0]
0x140005778  mov     rdi, [rsp+50h+arg_8]
0x14000577d  add     rsp, 50h
0x140005781  pop     rbp
0x140005782  retn
```
