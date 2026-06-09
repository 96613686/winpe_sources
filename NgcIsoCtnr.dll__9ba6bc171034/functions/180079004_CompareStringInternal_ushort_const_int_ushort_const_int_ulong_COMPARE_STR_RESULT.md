# CompareStringInternal(ushort const *,int,ushort const *,int,ulong,COMPARE_STR_RESULT *)

- ea: `0x180079004`
- end: `0x180079114`
- name: `?CompareStringInternal@@YAJPEBGH0HKPEAW4COMPARE_STR_RESULT@@@Z`
- size: `272`
- prototype: `__int64 __usercall@<rax>(LPCWCH lpString1@<rcx>, int@<edx>, const unsigned __int16 *@<r8>, int@<r9d>, unsigned int, enum COMPARE_STR_RESULT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180079fac`
- `0x180080874`

## callees

- `0x180079004`
- `0x18007d1b8`
- `0x18007d2a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007909b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007909b`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18007908f`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18007908f`

## string_xrefs

- `0x180079027`: `CompareStringInternal`
- `0x180079041`: `CompareStringInternal`
- `0x1800790af`: `CompareStringInternal`
- `0x1800790a3`: `CompareStringEx`

## pseudocode

```c
__int64 __fastcall CompareStringInternal(
        LPCWCH lpString1,
        __int64 a2,
        const unsigned __int16 *lpString2,
        __int64 a4,
        unsigned int a5,
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
  v7 = CompareStringEx(&LocaleName, 1u, lpString1, -1, lpString2, -1, 0, 0, 0);
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
0x180079004  mov     [rsp+arg_0], rbx
0x180079009  push    rdi
0x18007900a  sub     rsp, 50h
0x18007900e  mov     rdi, [rsp+58h+arg_28]
0x180079016  test    rdi, rdi
0x180079019  jnz     short loc_180079052
0x18007901b  lea     r8, aResult; "result"
0x180079022  mov     ebx, 80070057h
0x180079027  lea     rdx, aComparestringi; "CompareStringInternal"
0x18007902e  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180079035  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007903a  lea     rdx, aResult; "result"
0x180079041  lea     rcx, aComparestringi; "CompareStringInternal"
0x180079048  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007904d  jmp     loc_180079107
0x180079052  mov     [rsp+58h+lParam], 0; lParam
0x18007905b  or      r9d, 0FFFFFFFFh; cchCount1
0x18007905f  mov     [rsp+58h+lpReserved], 0; lpReserved
0x180079068  mov     [rsp+58h+lpVersionInformation], 0; lpVersionInformation
0x180079071  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x180079076  mov     [rsp+58h+lpString2], r8; lpString2
0x18007907b  lea     edx, [r9+2]; dwCmpFlags
0x18007907f  mov     r8, rcx; lpString1
0x180079082  mov     dword ptr [rdi], 0
0x180079088  lea     rcx, LocaleName; lpLocaleName
0x18007908f  call    cs:__imp_CompareStringEx
0x180079095  mov     ecx, eax
0x180079097  test    eax, eax
0x180079099  jnz     short loc_1800790D0
0x18007909b  call    cs:__imp_GetLastError
0x1800790a1  mov     ebx, eax
0x1800790a3  lea     r8, aComparestringe; "CompareStringEx"
0x1800790aa  mov     eax, 54Fh
0x1800790af  lea     rdx, aComparestringi; "CompareStringInternal"
0x1800790b6  test    ebx, ebx
0x1800790b8  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800790bf  cmovz   ebx, eax
0x1800790c2  mov     r9d, ebx
0x1800790c5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800790ca  test    ebx, ebx
0x1800790cc  jle     short loc_180079107
0x1800790ce  jmp     short loc_1800790E6
0x1800790d0  xor     ebx, ebx
0x1800790d2  sub     ecx, 1
0x1800790d5  jz      short loc_180079101
0x1800790d7  sub     ecx, 1
0x1800790da  jz      short loc_1800790F9
0x1800790dc  cmp     ecx, 1
0x1800790df  jz      short loc_1800790F1
0x1800790e1  mov     ebx, 54Fh
0x1800790e6  movzx   ebx, bx
0x1800790e9  or      ebx, 80070000h
0x1800790ef  jmp     short loc_180079107
0x1800790f1  mov     dword ptr [rdi], 3
0x1800790f7  jmp     short loc_180079107
0x1800790f9  mov     dword ptr [rdi], 2
0x1800790ff  jmp     short loc_180079107
0x180079101  mov     dword ptr [rdi], 1
0x180079107  mov     eax, ebx
0x180079109  mov     rbx, [rsp+58h+arg_0]
0x18007910e  add     rsp, 50h
0x180079112  pop     rdi
0x180079113  retn
```
