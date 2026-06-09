# Windows::Globalization::Spelling::ThirdPartySpellerCreator::CreateHostRegisteredEvent(void *,void * *)

- ea: `0x180066418`
- end: `0x1800664ac`
- name: `?CreateHostRegisteredEvent@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAXPEAPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(void *, void **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003912c`

## callees

- `0x180061320`
- `0x180066418`
- `0x180066f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066474`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180066466`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180066466`

## string_xrefs

- `0x180066441`: `SpellingHostRegistrationComplete`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::ThirdPartySpellerCreator::CreateHostRegisteredEvent(
        void *a1,
        void **a2,
        __int64 a3)
{
  int FullAppContainerNamedObjectPath; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  WCHAR Name[264]; // [rsp+20h] [rbp-228h] BYREF

  *a2 = 0;
  FullAppContainerNamedObjectPath = ACUtil::GetFullAppContainerNamedObjectPath(
                                      a1,
                                      L"SpellingHostRegistrationComplete",
                                      a3,
                                      Name);
  if ( FullAppContainerNamedObjectPath >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, Name);
    *a2 = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      FullAppContainerNamedObjectPath = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)FullAppContainerNamedObjectPath;
}

```

## disassembly

```asm
0x180066418  mov     [rsp+arg_10], rbx
0x18006641d  push    rdi
0x18006641e  sub     rsp, 240h
0x180066425  mov     rax, cs:__security_cookie
0x18006642c  xor     rax, rsp
0x18006642f  mov     [rsp+248h+var_18], rax
0x180066437  mov     rdi, rdx
0x18006643a  mov     qword ptr [rdx], 0
0x180066441  lea     rdx, aSpellinghostre; "SpellingHostRegistrationComplete"
0x180066448  lea     r9, [rsp+248h+Name]; unsigned __int16 *
0x18006644d  call    ?GetFullAppContainerNamedObjectPath@ACUtil@@SAJPEAXPEBGKPEAG@Z; ACUtil::GetFullAppContainerNamedObjectPath(void *,ushort const *,ulong,ushort *)
0x180066452  mov     ebx, eax
0x180066454  test    eax, eax
0x180066456  js      short loc_180066489
0x180066458  xor     r8d, r8d; bInitialState
0x18006645b  lea     r9, [rsp+248h+Name]; lpName
0x180066460  xor     ecx, ecx; lpEventAttributes
0x180066462  lea     edx, [r8+1]; bManualReset
0x180066466  call    cs:__imp_CreateEventW
0x18006646c  mov     [rdi], rax
0x18006646f  test    rax, rax
0x180066472  jnz     short loc_180066489
0x180066474  call    cs:__imp_GetLastError
0x18006647a  mov     ebx, eax
0x18006647c  test    eax, eax
0x18006647e  jle     short loc_180066489
0x180066480  movzx   ebx, ax
0x180066483  or      ebx, 80070000h
0x180066489  mov     eax, ebx
0x18006648b  mov     rcx, [rsp+248h+var_18]
0x180066493  xor     rcx, rsp; StackCookie
0x180066496  call    __security_check_cookie
0x18006649b  mov     rbx, [rsp+248h+arg_10]
0x1800664a3  add     rsp, 240h
0x1800664aa  pop     rdi
0x1800664ab  retn
```
