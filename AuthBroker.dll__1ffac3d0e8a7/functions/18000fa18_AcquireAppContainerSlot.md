# _AcquireAppContainerSlot

- ea: `0x18000fa18`
- end: `0x18000fbca`
- name: `_AcquireAppContainerSlot`
- size: `434`
- prototype: `unsigned int __fastcall()`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000fcfc`

## callees

- `0x180003f40`
- `0x1800053f8`
- `0x18000737c`
- `0x18000fa18`
- `0x180011210`
- `0x180011b58`
- `0x180011d74`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000fab7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000fab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fad9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fad9`

## pseudocode

```c
__int64 __fastcall AcquireAppContainerSlot()
{
  unsigned int i; // ebx
  signed int v1; // eax
  HANDLE MutexW; // rdi
  signed int Logger; // eax
  const _GUID *v4; // r8
  wchar_t slotString[4]; // [rsp+30h] [rbp-78h] BYREF
  wchar_t mutexName[32]; // [rsp+38h] [rbp-70h] BYREF

  for ( i = 2; i < 0xC; ++i )
  {
    if ( !_InterlockedExchange(&AppContainerSlots[i], 1) )
    {
      v1 = StringCchCopyW(mutexName, 0x1Du, L"AuthHostAppContainerMutex.");
      if ( v1 < 0
        || (slotString[0] = i + 95, slotString[1] = 0, v1 = StringCchCatW(mutexName, 0x1Du, slotString), v1 < 0) )
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x34u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v1);
        }
      }
      else
      {
        MutexW = CreateMutexW(0, 0, mutexName);
        if ( MutexW )
        {
          if ( GetLastError() != 183 )
          {
            AppContainerMutexes[i] = MutexW;
            return i;
          }
          CloseHandle(MutexW);
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 4u )
          {
            WPP_SF_S(
              WPP_GLOBAL_Control[1].Control.Logger,
              0x32u,
              WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
              mutexName);
          }
        }
        else
        {
          Logger = GetLastError();
          if ( Logger > 0 )
            Logger = (unsigned __int16)Logger | 0x80070000;
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            WPP_SF_Sd(WPP_GLOBAL_Control[1].Control.Logger, 0x33u, v4, mutexName, Logger);
          }
        }
      }
      ReleaseAppContainerSlot(i);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000fa18  push    rbx
0x18000fa1a  push    rsi
0x18000fa1b  push    rdi
0x18000fa1c  push    r14
0x18000fa1e  push    r15
0x18000fa20  sub     rsp, 80h
0x18000fa27  mov     rax, cs:__security_cookie
0x18000fa2e  xor     rax, rsp
0x18000fa31  mov     [rsp+0A8h+var_30], rax
0x18000fa36  mov     ebx, 2
0x18000fa3b  lea     r14, __ImageBase
0x18000fa42  lea     r15, WPP_GLOBAL_Control
0x18000fa49  cmp     ebx, 0Ch
0x18000fa4c  jnb     loc_18000FBAC
0x18000fa52  mov     esi, ebx
0x18000fa54  mov     eax, 1
0x18000fa59  xchg    eax, rva _AppContainerSlots[r14+rsi*4]
0x18000fa61  test    eax, eax
0x18000fa63  jnz     loc_18000FB99
0x18000fa69  lea     r8, aAuthhostappcon; "AuthHostAppContainerMutex."
0x18000fa70  lea     edx, [rax+1Dh]; cchDest
0x18000fa73  lea     rcx, [rsp+0A8h+mutexName]; pszDest
0x18000fa78  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fa7d  test    eax, eax
0x18000fa7f  js      loc_18000FB62
0x18000fa85  lea     eax, [rbx+5Fh]
0x18000fa88  mov     [rsp+0A8h+slotString], ax
0x18000fa8d  lea     r8, [rsp+0A8h+slotString]; pszSrc
0x18000fa92  xor     eax, eax
0x18000fa94  lea     rcx, [rsp+0A8h+mutexName]; pszDest
0x18000fa99  mov     [rsp+0A8h+slotString+2], ax
0x18000fa9e  lea     edx, [rax+1Dh]; cchDest
0x18000faa1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000faa6  test    eax, eax
0x18000faa8  js      loc_18000FB62
0x18000faae  lea     r8, [rsp+0A8h+mutexName]; lpName
0x18000fab3  xor     edx, edx; bInitialOwner
0x18000fab5  xor     ecx, ecx; lpMutexAttributes
0x18000fab7  call    cs:__imp_CreateMutexW
0x18000fabd  mov     rdi, rax
0x18000fac0  test    rax, rax
0x18000fac3  jz      short loc_18000FB1F
0x18000fac5  call    cs:__imp_GetLastError
0x18000facb  cmp     eax, 0B7h
0x18000fad0  jnz     loc_18000FBA0
0x18000fad6  mov     rcx, rdi; hObject
0x18000fad9  call    cs:__imp_CloseHandle
0x18000fadf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000fae6  cmp     rcx, r15
0x18000fae9  jz      loc_18000FB92
0x18000faef  test    byte ptr [rcx+44h], 10h
0x18000faf3  jz      loc_18000FB92
0x18000faf9  cmp     byte ptr [rcx+41h], 4
0x18000fafd  jb      loc_18000FB92
0x18000fb03  mov     rcx, [rcx+38h]; Logger
0x18000fb07  lea     r9, [rsp+0A8h+mutexName]; _a1
0x18000fb0c  mov     edx, 32h ; '2'; id
0x18000fb11  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000fb18  call    WPP_SF_S
0x18000fb1d  jmp     short loc_18000FB92
0x18000fb1f  call    cs:__imp_GetLastError
0x18000fb25  test    eax, eax
0x18000fb27  jle     short loc_18000FB31
0x18000fb29  movzx   eax, ax
0x18000fb2c  or      eax, 80070000h
0x18000fb31  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000fb38  cmp     rcx, r15
0x18000fb3b  jz      short loc_18000FB92
0x18000fb3d  test    byte ptr [rcx+44h], 10h
0x18000fb41  jz      short loc_18000FB92
0x18000fb43  cmp     byte ptr [rcx+41h], 2
0x18000fb47  jb      short loc_18000FB92
0x18000fb49  mov     rcx, [rcx+38h]; Logger
0x18000fb4d  lea     r9, [rsp+0A8h+mutexName]; _a2
0x18000fb52  mov     edx, 33h ; '3'; id
0x18000fb57  mov     [rsp+0A8h+Logger], eax; Logger
0x18000fb5b  call    WPP_SF_Sd
0x18000fb60  jmp     short loc_18000FB92
0x18000fb62  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000fb69  cmp     rcx, r15
0x18000fb6c  jz      short loc_18000FB92
0x18000fb6e  test    byte ptr [rcx+44h], 10h
0x18000fb72  jz      short loc_18000FB92
0x18000fb74  cmp     byte ptr [rcx+41h], 2
0x18000fb78  jb      short loc_18000FB92
0x18000fb7a  mov     rcx, [rcx+38h]; Logger
0x18000fb7e  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000fb85  mov     edx, 34h ; '4'; id
0x18000fb8a  mov     r9d, eax; _a1
0x18000fb8d  call    WPP_SF_d
0x18000fb92  mov     ecx, ebx; index
0x18000fb94  call    _ReleaseAppContainerSlot
0x18000fb99  inc     ebx
0x18000fb9b  jmp     loc_18000FA49
0x18000fba0  mov     rva _AppContainerMutexes[r14+rsi*8], rdi
0x18000fba8  mov     eax, ebx
0x18000fbaa  jmp     short loc_18000FBAE
0x18000fbac  xor     eax, eax
0x18000fbae  mov     rcx, [rsp+0A8h+var_30]
0x18000fbb3  xor     rcx, rsp; StackCookie
0x18000fbb6  call    __security_check_cookie
0x18000fbbb  add     rsp, 80h
0x18000fbc2  pop     r15
0x18000fbc4  pop     r14
0x18000fbc6  pop     rdi
0x18000fbc7  pop     rsi
0x18000fbc8  pop     rbx
0x18000fbc9  retn
```
