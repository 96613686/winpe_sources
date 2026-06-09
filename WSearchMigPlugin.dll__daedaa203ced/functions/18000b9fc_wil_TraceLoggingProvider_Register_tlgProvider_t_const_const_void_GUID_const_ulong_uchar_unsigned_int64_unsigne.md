# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18000b9fc`
- end: `0x18000bb23`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `295`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b93c`
- `0x18001177c`

## callees

- `0x1800026f0`
- `0x18000b9fc`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000bae9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000bae9`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18000ba98`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18000bab0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18000ba98`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18000bab0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000bac6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000bac6`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000ba70`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000ba70`

## string_xrefs

- `0x18000ba8f`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x18000baa7`: `advapi32.dll`

## pseudocode

```c
void __fastcall wil::TraceLoggingProvider::Register(
        wil::TraceLoggingProvider *this,
        const struct _tlgProvider_t *const a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  _QWORD *v5; // rsi
  unsigned __int16 *v6; // rbx
  unsigned int v7; // ebp
  FARPROC ProcAddress; // rax
  HMODULE phModule[2]; // [rsp+30h] [rbp-48h] BYREF
  GUID ProviderId; // [rsp+40h] [rbp-38h] BYREF

  phModule[1] = (HMODULE)-2LL;
  *((_QWORD *)this + 1) = a2;
  *((_BYTE *)this + 16) = 1;
  ProviderId = *(GUID *)(*((_QWORD *)a2 + 1) - 16LL);
  v5 = (_QWORD *)((char *)a2 + 32);
  if ( *((_QWORD *)a2 + 4) )
    __fastfail(5u);
  *((_QWORD *)a2 + 5) = 0;
  *((_QWORD *)a2 + 6) = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, a2, (PREGHANDLE)a2 + 4) )
  {
    v6 = (unsigned __int16 *)*((_QWORD *)a2 + 1);
    v7 = *v6;
    phModule[0] = 0;
    if ( GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0.dll", phModule)
      || GetModuleHandleExW(0, L"advapi32.dll", phModule) )
    {
      ProcAddress = GetProcAddress(phModule[0], "EventSetInformation");
      if ( ProcAddress )
        ((void (__fastcall *)(_QWORD, __int64, unsigned __int16 *, _QWORD))ProcAddress)(*v5, 2, v6, v7);
      FreeLibrary(phModule[0]);
    }
  }
  *((_DWORD *)this + 5) = 1;
  (*(void (__fastcall **)(wil::TraceLoggingProvider *))(*(_QWORD *)this + 8LL))(this);
}

```

## disassembly

```asm
0x18000b9fc  mov     rax, rsp
0x18000b9ff  push    rbp
0x18000ba00  push    rsi
0x18000ba01  push    rdi
0x18000ba02  sub     rsp, 60h
0x18000ba06  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x18000ba0e  mov     [rax+18h], rbx
0x18000ba12  mov     rax, cs:__security_cookie
0x18000ba19  xor     rax, rsp
0x18000ba1c  mov     [rsp+78h+var_28], rax
0x18000ba21  mov     rbx, rdx
0x18000ba24  mov     rdi, rcx
0x18000ba27  mov     [rcx+8], rdx
0x18000ba2b  mov     byte ptr [rcx+10h], 1
0x18000ba2f  mov     rax, [rdx+8]
0x18000ba33  movups  xmm0, xmmword ptr [rax-10h]
0x18000ba37  movdqu  xmmword ptr [rsp+78h+ProviderId.Data1], xmm0
0x18000ba3d  lea     rsi, [rdx+20h]
0x18000ba41  cmp     qword ptr [rsi], 0
0x18000ba45  jz      short loc_18000BA4E
0x18000ba47  mov     ecx, 5
0x18000ba4c  int     29h; Win8: RtlFailFast(ecx)
0x18000ba4e  mov     qword ptr [rdx+28h], 0
0x18000ba56  mov     qword ptr [rdx+30h], 0
0x18000ba5e  mov     r9, rsi; RegHandle
0x18000ba61  mov     r8, rbx; CallbackContext
0x18000ba64  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000ba6b  lea     rcx, [rsp+78h+ProviderId]; ProviderId
0x18000ba70  call    cs:__imp_EventRegister
0x18000ba76  test    eax, eax
0x18000ba78  jnz     short loc_18000BAEF
0x18000ba7a  mov     rbx, [rbx+8]
0x18000ba7e  movzx   ebp, word ptr [rbx]
0x18000ba81  mov     [rsp+78h+phModule], 0
0x18000ba8a  lea     r8, [rsp+78h+phModule]; phModule
0x18000ba8f  lea     rdx, aApiMsWinEventi_0; "api-ms-win-eventing-provider-l1-1-0.dll"
0x18000ba96  xor     ecx, ecx; dwFlags
0x18000ba98  call    cs:__imp_GetModuleHandleExW
0x18000ba9e  test    eax, eax
0x18000baa0  jnz     short loc_18000BABA
0x18000baa2  lea     r8, [rsp+78h+phModule]; phModule
0x18000baa7  lea     rdx, LibFileName; "advapi32.dll"
0x18000baae  xor     ecx, ecx; dwFlags
0x18000bab0  call    cs:__imp_GetModuleHandleExW
0x18000bab6  test    eax, eax
0x18000bab8  jz      short loc_18000BAEF
0x18000baba  lea     rdx, aEventsetinform; "EventSetInformation"
0x18000bac1  mov     rcx, [rsp+78h+phModule]; hModule
0x18000bac6  call    cs:__imp_GetProcAddress
0x18000bacc  test    rax, rax
0x18000bacf  jz      short loc_18000BAE4
0x18000bad1  mov     r9d, ebp
0x18000bad4  mov     r8, rbx
0x18000bad7  mov     edx, 2
0x18000badc  mov     rcx, [rsi]
0x18000badf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bae4  mov     rcx, [rsp+78h+phModule]; hLibModule
0x18000bae9  call    cs:__imp_FreeLibrary
0x18000baef  mov     dword ptr [rdi+14h], 1
0x18000baf6  mov     rax, [rdi]
0x18000baf9  mov     rcx, rdi
0x18000bafc  mov     rax, [rax+8]
0x18000bb00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb05  nop
0x18000bb06  mov     rcx, [rsp+78h+var_28]
0x18000bb0b  xor     rcx, rsp; StackCookie
0x18000bb0e  call    __security_check_cookie
0x18000bb13  mov     rbx, [rsp+78h+arg_10]
0x18000bb1b  add     rsp, 60h
0x18000bb1f  pop     rdi
0x18000bb20  pop     rsi
0x18000bb21  pop     rbp
0x18000bb22  retn
```
