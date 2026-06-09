# CompareStringInternal(ushort const *,int,ushort const *,int,ulong,COMPARE_STR_RESULT *)

- ea: `0x1800859bc`
- end: `0x180085acf`
- name: `?CompareStringInternal@@YAJPEBGH0HKPEAW4COMPARE_STR_RESULT@@@Z`
- size: `275`
- prototype: `__int64 __usercall@<rax>(LPCWCH lpString1@<rcx>, int@<edx>, const unsigned __int16 *@<r8>, int@<r9d>, unsigned int, enum COMPARE_STR_RESULT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800873bc`
- `0x180090ae4`

## callees

- `0x1800859bc`
- `0x18008aa28`
- `0x18008aecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085a56`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180085a4a`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180085a4a`

## string_xrefs

- `0x1800859df`: `CompareStringInternal`
- `0x1800859f9`: `CompareStringInternal`
- `0x180085a6a`: `CompareStringInternal`
- `0x180085a5e`: `CompareStringEx`

## pseudocode

```c
__int64 __fastcall CompareStringInternal(
        LPCWCH lpString1,
        __int64 a2,
        const unsigned __int16 *lpString2,
        __int64 a4,
        DWORD dwCmpFlags,
        enum COMPARE_STR_RESULT *a6)
{
  DWORD LastError; // ebx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx

  if ( !a6 )
  {
    LastError = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CompareStringInternal", L"result");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CompareStringInternal", L"result");
    return LastError;
  }
  *(_DWORD *)a6 = 0;
  v7 = CompareStringEx(&base, dwCmpFlags, lpString1, -1, lpString2, -1, 0, 0, 0);
  if ( v7 )
  {
    LastError = 0;
    v8 = v7 - 1;
    if ( !v8 )
    {
      *(_DWORD *)a6 = 1;
      return LastError;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      *(_DWORD *)a6 = 2;
      return LastError;
    }
    if ( v9 == 1 )
    {
      *(_DWORD *)a6 = 3;
      return LastError;
    }
    LOWORD(LastError) = 1359;
    return (unsigned __int16)LastError | 0x80070000;
  }
  LastError = GetLastError();
  if ( !LastError )
    LastError = 1359;
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"CompareStringInternal",
    L"CompareStringEx",
    LastError);
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x1800859bc  mov     [rsp+arg_0], rbx
0x1800859c1  push    rdi
0x1800859c2  sub     rsp, 50h
0x1800859c6  mov     rdi, [rsp+58h+arg_28]
0x1800859ce  test    rdi, rdi
0x1800859d1  jnz     short loc_180085A0A
0x1800859d3  lea     r8, aResult_0; "result"
0x1800859da  mov     ebx, 80070057h
0x1800859df  lea     rdx, aComparestringi; "CompareStringInternal"
0x1800859e6  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800859ed  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800859f2  lea     rdx, aResult_0; "result"
0x1800859f9  lea     rcx, aComparestringi; "CompareStringInternal"
0x180085a00  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180085a05  jmp     loc_180085AC2
0x180085a0a  mov     edx, [rsp+58h+dwCmpFlags]; dwCmpFlags
0x180085a11  or      r9d, 0FFFFFFFFh; cchCount1
0x180085a15  mov     [rsp+58h+lParam], 0; lParam
0x180085a1e  mov     [rsp+58h+lpReserved], 0; lpReserved
0x180085a27  mov     [rsp+58h+lpVersionInformation], 0; lpVersionInformation
0x180085a30  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x180085a35  mov     [rsp+58h+lpString2], r8; lpString2
0x180085a3a  mov     r8, rcx; lpString1
0x180085a3d  lea     rcx, base; lpLocaleName
0x180085a44  mov     dword ptr [rdi], 0
0x180085a4a  call    cs:__imp_CompareStringEx
0x180085a50  mov     ecx, eax
0x180085a52  test    eax, eax
0x180085a54  jnz     short loc_180085A8B
0x180085a56  call    cs:__imp_GetLastError
0x180085a5c  mov     ebx, eax
0x180085a5e  lea     r8, aComparestringe; "CompareStringEx"
0x180085a65  mov     eax, 54Fh
0x180085a6a  lea     rdx, aComparestringi; "CompareStringInternal"
0x180085a71  test    ebx, ebx
0x180085a73  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180085a7a  cmovz   ebx, eax
0x180085a7d  mov     r9d, ebx
0x180085a80  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180085a85  test    ebx, ebx
0x180085a87  jle     short loc_180085AC2
0x180085a89  jmp     short loc_180085AA1
0x180085a8b  xor     ebx, ebx
0x180085a8d  sub     ecx, 1
0x180085a90  jz      short loc_180085ABC
0x180085a92  sub     ecx, 1
0x180085a95  jz      short loc_180085AB4
0x180085a97  cmp     ecx, 1
0x180085a9a  jz      short loc_180085AAC
0x180085a9c  mov     ebx, 54Fh
0x180085aa1  movzx   ebx, bx
0x180085aa4  or      ebx, 80070000h
0x180085aaa  jmp     short loc_180085AC2
0x180085aac  mov     dword ptr [rdi], 3
0x180085ab2  jmp     short loc_180085AC2
0x180085ab4  mov     dword ptr [rdi], 2
0x180085aba  jmp     short loc_180085AC2
0x180085abc  mov     dword ptr [rdi], 1
0x180085ac2  mov     eax, ebx
0x180085ac4  mov     rbx, [rsp+58h+arg_0]
0x180085ac9  add     rsp, 50h
0x180085acd  pop     rdi
0x180085ace  retn
```
