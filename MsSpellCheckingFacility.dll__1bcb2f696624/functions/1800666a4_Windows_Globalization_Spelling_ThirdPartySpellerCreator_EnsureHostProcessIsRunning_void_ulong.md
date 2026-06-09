# Windows::Globalization::Spelling::ThirdPartySpellerCreator::EnsureHostProcessIsRunning(void *,ulong *)

- ea: `0x1800666a4`
- end: `0x18006676b`
- name: `?EnsureHostProcessIsRunning@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAXPEAK@Z`
- size: `199`
- prototype: `__int64 __fastcall(void *, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003912c`

## callees

- `0x180061320`
- `0x1800666a4`
- `0x180066f20`
- `0x180067048`
- `0x180067928`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800666fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800666fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006671e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006671e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800666f1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800666f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Globalization::Spelling::ThirdPartySpellerCreator::EnsureHostProcessIsRunning(
        void *a1,
        unsigned int *a2,
        unsigned int a3)
{
  int FullAppContainerNamedObjectPath; // ebx
  HANDLE MutexW; // rbp
  signed int LastError; // eax
  const unsigned __int16 *v8; // rdx
  const unsigned __int16 *v9; // r8
  WCHAR Name[264]; // [rsp+20h] [rbp-238h] BYREF

  *a2 = 0;
  FullAppContainerNamedObjectPath = ACUtil::GetFullAppContainerNamedObjectPath(
                                      a1,
                                      L"SpellingHostSingletonMutex",
                                      a3,
                                      Name);
  if ( FullAppContainerNamedObjectPath < 0 )
    return (unsigned int)FullAppContainerNamedObjectPath;
  MutexW = CreateMutexW(0, 0, Name);
  LastError = GetLastError();
  FullAppContainerNamedObjectPath = LastError;
  if ( MutexW )
  {
    CloseHandle(MutexW);
    if ( FullAppContainerNamedObjectPath == 183 )
      return (unsigned int)Windows::Globalization::Spelling::ThirdPartySpellerCreator::GetHostPIDFromSharedMemory(
                             a1,
                             a2);
    return (unsigned int)Windows::Globalization::Spelling::ThirdPartySpellerCreator::LaunchProcessUnderAppContainer(
                           (unsigned __int64)a1,
                           v8,
                           v9,
                           a2);
  }
  if ( LastError == 3 )
    return (unsigned int)Windows::Globalization::Spelling::ThirdPartySpellerCreator::LaunchProcessUnderAppContainer(
                           (unsigned __int64)a1,
                           v8,
                           v9,
                           a2);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)FullAppContainerNamedObjectPath;
}

```

## disassembly

```asm
0x1800666a4  mov     [rsp+arg_10], rbx
0x1800666a9  push    rbp
0x1800666aa  push    rsi
0x1800666ab  push    rdi
0x1800666ac  sub     rsp, 240h
0x1800666b3  mov     rax, cs:__security_cookie
0x1800666ba  xor     rax, rsp
0x1800666bd  mov     [rsp+258h+var_28], rax
0x1800666c5  mov     rsi, rdx
0x1800666c8  mov     dword ptr [rdx], 0
0x1800666ce  lea     rdx, aSpellinghostsi; "SpellingHostSingletonMutex"
0x1800666d5  mov     rdi, rcx
0x1800666d8  lea     r9, [rsp+258h+Name]; unsigned __int16 *
0x1800666dd  call    ?GetFullAppContainerNamedObjectPath@ACUtil@@SAJPEAXPEBGKPEAG@Z; ACUtil::GetFullAppContainerNamedObjectPath(void *,ushort const *,ulong,ushort *)
0x1800666e2  mov     ebx, eax
0x1800666e4  test    eax, eax
0x1800666e6  js      short loc_180066746
0x1800666e8  lea     r8, [rsp+258h+Name]; lpName
0x1800666ed  xor     edx, edx; bInitialOwner
0x1800666ef  xor     ecx, ecx; lpMutexAttributes
0x1800666f1  call    cs:__imp_CreateMutexW
0x1800666f7  mov     rbp, rax
0x1800666fa  call    cs:__imp_GetLastError
0x180066700  mov     ebx, eax
0x180066702  test    rbp, rbp
0x180066705  jnz     short loc_18006671B
0x180066707  cmp     eax, 3
0x18006670a  jz      short loc_180066739
0x18006670c  test    eax, eax
0x18006670e  jle     short loc_180066746
0x180066710  movzx   ebx, bx
0x180066713  or      ebx, 80070000h
0x180066719  jmp     short loc_180066746
0x18006671b  mov     rcx, rbp; hObject
0x18006671e  call    cs:__imp_CloseHandle
0x180066724  cmp     ebx, 0B7h
0x18006672a  jnz     short loc_180066739
0x18006672c  mov     rdx, rsi; unsigned int *
0x18006672f  mov     rcx, rdi; void *
0x180066732  call    ?GetHostPIDFromSharedMemory@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAXPEAK@Z; Windows::Globalization::Spelling::ThirdPartySpellerCreator::GetHostPIDFromSharedMemory(void *,ulong *)
0x180066737  jmp     short loc_180066744
0x180066739  mov     r9, rsi; unsigned int *
0x18006673c  mov     rcx, rdi; void *
0x18006673f  call    ?LaunchProcessUnderAppContainer@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAXPEBG1PEAK@Z; Windows::Globalization::Spelling::ThirdPartySpellerCreator::LaunchProcessUnderAppContainer(void *,ushort const *,ushort const *,ulong *)
0x180066744  mov     ebx, eax
0x180066746  mov     eax, ebx
0x180066748  mov     rcx, [rsp+258h+var_28]
0x180066750  xor     rcx, rsp; StackCookie
0x180066753  call    __security_check_cookie
0x180066758  mov     rbx, [rsp+258h+arg_10]
0x180066760  add     rsp, 240h
0x180066767  pop     rdi
0x180066768  pop     rsi
0x180066769  pop     rbp
0x18006676a  retn
```
