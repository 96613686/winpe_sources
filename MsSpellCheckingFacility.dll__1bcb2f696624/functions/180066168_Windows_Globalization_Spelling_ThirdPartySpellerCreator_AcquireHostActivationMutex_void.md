# Windows::Globalization::Spelling::ThirdPartySpellerCreator::AcquireHostActivationMutex(void *)

- ea: `0x180066168`
- end: `0x18006628a`
- name: `?AcquireHostActivationMutex@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAX@Z`
- size: `290`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003912c`

## callees

- `0x180066168`
- `0x1800664b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006625a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006625a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800661cd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800661cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066220`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180066220`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180066236`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180066236`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006618e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006618e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066213`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180066213`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::ThirdPartySpellerCreator::AcquireHostActivationMutex(PSID Sid)
{
  signed int v2; // ebx
  HANDLE v3; // rcx
  DWORD v4; // ecx
  signed int v5; // eax
  DWORD v6; // eax
  signed int LastError; // eax
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  v3 = Windows::Globalization::Spelling::g_hActivationMutex;
  if ( Windows::Globalization::Spelling::g_hActivationMutex )
  {
LABEL_12:
    v6 = WaitForSingleObject(v3, 0x1388u);
    if ( v6 )
    {
      switch ( v6 )
      {
        case 0x80u:
          v2 = -2147024161;
          break;
        case 0x102u:
          v2 = -2147023436;
          break;
        case 0xFFFFFFFF:
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
          break;
        default:
          v2 = -2147418113;
          break;
      }
    }
    return (unsigned int)v2;
  }
  AcquireSRWLockExclusive(&Windows::Globalization::Spelling::ThirdPartySpellerCreator::activationMutexLock);
  if ( !Windows::Globalization::Spelling::g_hActivationMutex )
  {
    memset(&MutexAttributes, 0, sizeof(MutexAttributes));
    v2 = ACUtil::CreateSecurityAttributesForAppContainer(Sid, &MutexAttributes);
    if ( v2 >= 0 )
    {
      Windows::Globalization::Spelling::g_hActivationMutex = CreateMutexW(
                                                               &MutexAttributes,
                                                               0,
                                                               L"SpellingHostActivationMutex");
      v4 = GetLastError();
      if ( Windows::Globalization::Spelling::g_hActivationMutex )
      {
        if ( v4 == 183 )
          v2 = 0;
      }
      else
      {
        v5 = GetLastError();
        v2 = v5;
        if ( v5 > 0 )
          v2 = (unsigned __int16)v5 | 0x80070000;
      }
    }
    LocalFree(MutexAttributes.lpSecurityDescriptor);
  }
  ReleaseSRWLockExclusive(&Windows::Globalization::Spelling::ThirdPartySpellerCreator::activationMutexLock);
  if ( v2 >= 0 )
  {
    v3 = Windows::Globalization::Spelling::g_hActivationMutex;
    goto LABEL_12;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180066168  mov     [rsp+arg_0], rbx
0x18006616d  push    rdi
0x18006616e  sub     rsp, 40h
0x180066172  mov     rdi, rcx
0x180066175  xor     ebx, ebx
0x180066177  mov     rcx, cs:?g_hActivationMutex@Spelling@Globalization@Windows@@3PEAXEA; void * Windows::Globalization::Spelling::g_hActivationMutex
0x18006617e  test    rcx, rcx
0x180066181  jnz     loc_180066231
0x180066187  lea     rcx, ?activationMutexLock@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@0VReaderWriterLock@@A; SRWLock
0x18006618e  call    cs:__imp_AcquireSRWLockExclusive
0x180066194  cmp     cs:?g_hActivationMutex@Spelling@Globalization@Windows@@3PEAXEA, rbx; void * Windows::Globalization::Spelling::g_hActivationMutex
0x18006619b  jnz     short loc_180066219
0x18006619d  xorps   xmm0, xmm0
0x1800661a0  lea     rdx, [rsp+48h+MutexAttributes]; struct _SECURITY_ATTRIBUTES *
0x1800661a5  xor     eax, eax
0x1800661a7  mov     rcx, rdi; Sid
0x1800661aa  movups  xmmword ptr [rsp+48h+MutexAttributes.nLength], xmm0
0x1800661af  mov     qword ptr [rsp+48h+MutexAttributes.bInheritHandle], rax
0x1800661b4  call    ?CreateSecurityAttributesForAppContainer@ACUtil@@SAJPEAXPEAU_SECURITY_ATTRIBUTES@@@Z; ACUtil::CreateSecurityAttributesForAppContainer(void *,_SECURITY_ATTRIBUTES *)
0x1800661b9  mov     ebx, eax
0x1800661bb  test    eax, eax
0x1800661bd  js      short loc_18006620E
0x1800661bf  lea     r8, Name; "SpellingHostActivationMutex"
0x1800661c6  xor     edx, edx; bInitialOwner
0x1800661c8  lea     rcx, [rsp+48h+MutexAttributes]; lpMutexAttributes
0x1800661cd  call    cs:__imp_CreateMutexW
0x1800661d3  mov     cs:?g_hActivationMutex@Spelling@Globalization@Windows@@3PEAXEA, rax; void * Windows::Globalization::Spelling::g_hActivationMutex
0x1800661da  call    cs:__imp_GetLastError
0x1800661e0  cmp     cs:?g_hActivationMutex@Spelling@Globalization@Windows@@3PEAXEA, 0; void * Windows::Globalization::Spelling::g_hActivationMutex
0x1800661e8  mov     ecx, eax
0x1800661ea  jnz     short loc_180066203
0x1800661ec  call    cs:__imp_GetLastError
0x1800661f2  mov     ebx, eax
0x1800661f4  test    eax, eax
0x1800661f6  jle     short loc_18006620E
0x1800661f8  movzx   ebx, ax
0x1800661fb  or      ebx, 80070000h
0x180066201  jmp     short loc_18006620E
0x180066203  xor     eax, eax
0x180066205  cmp     ecx, 0B7h
0x18006620b  cmovz   ebx, eax
0x18006620e  mov     rcx, [rsp+48h+MutexAttributes.lpSecurityDescriptor]; hMem
0x180066213  call    cs:__imp_LocalFree
0x180066219  lea     rcx, ?activationMutexLock@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@0VReaderWriterLock@@A; SRWLock
0x180066220  call    cs:__imp_ReleaseSRWLockExclusive
0x180066226  test    ebx, ebx
0x180066228  js      short loc_18006627D
0x18006622a  mov     rcx, cs:?g_hActivationMutex@Spelling@Globalization@Windows@@3PEAXEA; hHandle
0x180066231  mov     edx, 1388h; dwMilliseconds
0x180066236  call    cs:__imp_WaitForSingleObject
0x18006623c  test    eax, eax
0x18006623e  jz      short loc_18006627D
0x180066240  cmp     eax, 80h
0x180066245  jz      short loc_180066278
0x180066247  cmp     eax, 102h
0x18006624c  jz      short loc_180066271
0x18006624e  cmp     eax, 0FFFFFFFFh
0x180066251  jz      short loc_18006625A
0x180066253  mov     ebx, 8000FFFFh
0x180066258  jmp     short loc_18006627D
0x18006625a  call    cs:__imp_GetLastError
0x180066260  mov     ebx, eax
0x180066262  test    eax, eax
0x180066264  jle     short loc_18006627D
0x180066266  movzx   ebx, ax
0x180066269  or      ebx, 80070000h
0x18006626f  jmp     short loc_18006627D
0x180066271  mov     ebx, 800705B4h
0x180066276  jmp     short loc_18006627D
0x180066278  mov     ebx, 800702DFh
0x18006627d  mov     eax, ebx
0x18006627f  mov     rbx, [rsp+48h+arg_0]
0x180066284  add     rsp, 40h
0x180066288  pop     rdi
0x180066289  retn
```
