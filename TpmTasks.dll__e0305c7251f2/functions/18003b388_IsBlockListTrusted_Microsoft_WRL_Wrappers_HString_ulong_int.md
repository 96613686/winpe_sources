# IsBlockListTrusted(Microsoft::WRL::Wrappers::HString &,ulong,int *)

- ea: `0x18003b388`
- end: `0x18003b4a4`
- name: `?IsBlockListTrusted@@YAJAEAVHString@Wrappers@WRL@Microsoft@@KPEAH@Z`
- size: `284`
- prototype: `__int64 __fastcall(HSTRING *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003ad04`

## callees

- `0x1800078b0`
- `0x18001a40c`
- `0x18001a42c`
- `0x18003b388`
- `0x18003b4c4`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003b472`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003b472`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b421`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003b421`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003b3f6`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003b3f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b3c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b3c2`

## string_xrefs

- `0x18003b3d8`: `Failed to convert lastUpdatedTime to SystemTime\n`
- `0x18003b47c`: `BlockList is NOT trusted as lastUpdatedFileTime + blockListFreshWindowInHours is less than currentFileTime\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IsBlockListTrusted(HSTRING *a1, unsigned int a2, int *a3)
{
  HSTRING v3; // rcx
  __int64 v4; // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  const char *v8; // r9
  FILETIME FileTime1; // [rsp+20h] [rbp-30h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-20h] BYREF
  SYSTEMTIME SystemTime; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  v3 = *a1;
  v4 = a2;
  FileTime = 0;
  SystemTime = 0;
  FileTime1 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v3, 0);
  if ( (unsigned int)StringTimeToSystemTime(StringRawBuffer, &SystemTime) )
  {
    if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( *(_QWORD *)&FileTime + 36000000000LL * v4 >= *(unsigned __int64 *)&FileTime )
      {
        FileTime1 = (FILETIME)(*(_QWORD *)&FileTime + 36000000000LL * v4);
        if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) < 0 )
        {
          *a3 = 0;
          SBServicingLogMessage((wchar_t *)L"BlockList is NOT trusted as lastUpdatedFileTime + blockListFreshWindowInHours"
                                            " is less than currentFileTime\n");
        }
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
          (const char *)0x80070216LL,
          FileTime1.dwLowDateTime);
        return 2147942934LL;
      }
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x6D,
               (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
               v8);
    }
  }
  else
  {
    SBServicingLogMessage((wchar_t *)L"Failed to convert lastUpdatedTime to SystemTime\n");
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18003b388  push    rbp
0x18003b38a  push    rbx
0x18003b38b  push    rdi
0x18003b38c  mov     rbp, rsp
0x18003b38f  sub     rsp, 50h
0x18003b393  mov     rax, cs:__security_cookie
0x18003b39a  xor     rax, rsp
0x18003b39d  mov     [rbp+var_8], rax
0x18003b3a1  mov     rcx, [rcx]; string
0x18003b3a4  xorps   xmm0, xmm0
0x18003b3a7  mov     edi, edx
0x18003b3a9  mov     rbx, r8
0x18003b3ac  xor     edx, edx; length
0x18003b3ae  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18003b3b6  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18003b3ba  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x18003b3c2  call    cs:__imp_WindowsGetStringRawBuffer
0x18003b3c8  mov     rcx, rax; unsigned __int16 *
0x18003b3cb  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x18003b3cf  call    ?StringTimeToSystemTime@@YAHPEBGPEAU_SYSTEMTIME@@@Z; StringTimeToSystemTime(ushort const *,_SYSTEMTIME *)
0x18003b3d4  test    eax, eax
0x18003b3d6  jnz     short loc_18003B3EE
0x18003b3d8  lea     rcx, aFailedToConver_0; "Failed to convert lastUpdatedTime to Sy"...
0x18003b3df  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003b3e4  mov     eax, 80004005h
0x18003b3e9  jmp     loc_18003B490
0x18003b3ee  lea     rdx, [rbp+FileTime]; lpFileTime
0x18003b3f2  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18003b3f6  call    cs:__imp_SystemTimeToFileTime
0x18003b3fc  test    eax, eax
0x18003b3fe  jnz     short loc_18003B415
0x18003b400  mov     rcx, [rbp+18h]; this
0x18003b404  lea     r8, aOnecoreBaseSec_1; "onecore\\base\\secureboot\\servicing\\l"...
0x18003b40b  lea     edx, [rax+6Dh]; void *
0x18003b40e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b413  jmp     short loc_18003B490
0x18003b415  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003b419  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003b421  call    cs:__imp_GetSystemTimeAsFileTime
0x18003b427  mov     rdx, 861C46800h
0x18003b431  imul    rdx, rdi
0x18003b435  add     rdx, qword ptr [rbp+FileTime.dwLowDateTime]
0x18003b439  cmp     rdx, qword ptr [rbp+FileTime.dwLowDateTime]
0x18003b43d  jnb     short loc_18003B460
0x18003b43f  mov     rcx, [rbp+18h]; this
0x18003b443  lea     r8, aOnecoreBaseSec_1; "onecore\\base\\secureboot\\servicing\\l"...
0x18003b44a  mov     ebx, 80070216h
0x18003b44f  mov     edx, 81h; void *
0x18003b454  mov     r9d, ebx; char *
0x18003b457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b45c  mov     eax, ebx
0x18003b45e  jmp     short loc_18003B490
0x18003b460  mov     [rbp+FileTime1.dwLowDateTime], edx
0x18003b463  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18003b467  shr     rdx, 20h
0x18003b46b  mov     [rbp+FileTime1.dwHighDateTime], edx
0x18003b46e  lea     rdx, [rbp+SystemTimeAsFileTime]; lpFileTime2
0x18003b472  call    cs:__imp_CompareFileTime
0x18003b478  test    eax, eax
0x18003b47a  jns     short loc_18003B48E
0x18003b47c  lea     rcx, aBlocklistIsNot; "BlockList is NOT trusted as lastUpdated"...
0x18003b483  mov     dword ptr [rbx], 0
0x18003b489  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003b48e  xor     eax, eax
0x18003b490  mov     rcx, [rbp+var_8]
0x18003b494  xor     rcx, rsp; StackCookie
0x18003b497  call    __security_check_cookie
0x18003b49c  add     rsp, 50h
0x18003b4a0  pop     rdi
0x18003b4a1  pop     rbx
0x18003b4a2  pop     rbp
0x18003b4a3  retn
```
