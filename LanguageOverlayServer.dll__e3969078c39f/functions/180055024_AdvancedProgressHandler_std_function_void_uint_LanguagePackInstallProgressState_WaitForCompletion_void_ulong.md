# AdvancedProgressHandler<std::function<void (uint,LanguagePackInstallProgressState)>>::WaitForCompletion(void *,ulong)

- ea: `0x180055024`
- end: `0x180055155`
- name: `?WaitForCompletion@?$AdvancedProgressHandler@V?$function@$$A6AXIW4LanguagePackInstallProgressState@@@Z@std@@@@QEAAXPEAXK@Z`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180050f50`

## callees

- `0x180003a00`
- `0x1800120b0`
- `0x180012a98`
- `0x180055024`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800550b7`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x1800550b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005508c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005508c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180055069`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180055069`

## string_xrefs

- `0x1800550c6`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x1800550ef`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180055106`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180055120`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x18005513d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`

## pseudocode

```c
void __fastcall AdvancedProgressHandler<std::function<void (unsigned int,enum LanguagePackInstallProgressState)>>::WaitForCompletion(
        __int64 a1,
        void *a2)
{
  void *v3; // rax
  DWORD v4; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  signed int LastError; // eax
  bool v8; // sf
  const char *v9; // r9
  const char *v10; // r9
  HANDLE v11[3]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v11[0] = *(HANDLE *)(a1 + 184);
  v3 = *(void **)(a1 + 192);
  v11[2] = a2;
  v11[1] = v3;
  v4 = WaitForMultipleObjects(3u, v11, 0, 0x1B7740u);
  if ( v4 && (v5 = v4 - 1) != 0 )
  {
    v6 = v5 - 1;
    if ( !v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)0x800704C7LL,
        (int)v11[0]);
    if ( v6 == 256 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)0x800705B4LL,
        (int)v11[0]);
    LastError = GetLastError();
    v8 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = LastError < 0;
    }
    if ( v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)LastError,
        (int)v11[0]);
  }
  else
  {
    v9 = (const char *)*(unsigned int *)(a1 + 200);
    if ( (int)v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        v9,
        (int)v11[0]);
  }
  if ( !CancelWaitableTimer(*(HANDLE *)(a1 + 192)) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
      v10);
}

```

## disassembly

```asm
0x180055024  mov     r11, rsp
0x180055027  push    rbx
0x180055028  sub     rsp, 40h
0x18005502c  mov     rax, cs:__security_cookie
0x180055033  xor     rax, rsp
0x180055036  mov     [rsp+48h+var_10], rax
0x18005503b  mov     rax, [rcx+0B8h]
0x180055042  xor     r8d, r8d; bWaitAll
0x180055045  mov     [r11-28h], rax
0x180055049  mov     rbx, rcx
0x18005504c  mov     rax, [rcx+0C0h]
0x180055053  mov     r9d, 1B7740h; dwMilliseconds
0x180055059  mov     [r11-18h], rdx
0x18005505d  lea     rdx, [r11-28h]; lpHandles
0x180055061  lea     ecx, [r8+3]; nCount
0x180055065  mov     [r11-20h], rax
0x180055069  call    cs:__imp_WaitForMultipleObjects
0x18005506f  test    eax, eax
0x180055071  jz      short loc_1800550A4
0x180055073  sub     eax, 1
0x180055076  jz      short loc_1800550A4
0x180055078  sub     eax, 1
0x18005507b  jz      loc_180055138
0x180055081  cmp     eax, 100h
0x180055086  jz      loc_18005511B
0x18005508c  call    cs:__imp_GetLastError
0x180055092  test    eax, eax
0x180055094  jle     short loc_1800550A0
0x180055096  movzx   eax, ax
0x180055099  or      eax, 80070000h
0x18005509e  test    eax, eax
0x1800550a0  js      short loc_180055101
0x1800550a2  jmp     short loc_1800550B0
0x1800550a4  mov     r9d, [rbx+0C8h]; char *
0x1800550ab  test    r9d, r9d
0x1800550ae  js      short loc_1800550EA
0x1800550b0  mov     rcx, [rbx+0C0h]; hTimer
0x1800550b7  call    cs:__imp_CancelWaitableTimer
0x1800550bd  test    eax, eax
0x1800550bf  jnz     short loc_1800550D7
0x1800550c1  mov     rcx, [rsp+48h]; this
0x1800550c6  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x1800550cd  mov     edx, 0A8h; void *
0x1800550d2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800550d7  mov     rcx, [rsp+48h+var_10]
0x1800550dc  xor     rcx, rsp; StackCookie
0x1800550df  call    __security_check_cookie
0x1800550e4  add     rsp, 40h
0x1800550e8  pop     rbx
0x1800550e9  retn
0x1800550ea  mov     rcx, [rsp+48h]; this
0x1800550ef  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x1800550f6  mov     edx, 98h; void *
0x1800550fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055101  mov     rcx, [rsp+48h]; this
0x180055106  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x18005510d  mov     r9d, eax; char *
0x180055110  mov     edx, 0A4h; void *
0x180055115  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005511b  mov     rcx, [rsp+48h]; this
0x180055120  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180055127  mov     r9d, 800705B4h; char *
0x18005512d  mov     edx, 0A0h; void *
0x180055132  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180055138  mov     rcx, [rsp+48h]; this
0x18005513d  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180055144  mov     r9d, 800704C7h; char *
0x18005514a  mov     edx, 9Ch; void *
0x18005514f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
