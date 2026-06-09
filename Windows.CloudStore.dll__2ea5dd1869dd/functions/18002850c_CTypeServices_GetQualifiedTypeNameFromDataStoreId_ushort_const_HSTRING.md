# CTypeServices::GetQualifiedTypeNameFromDataStoreId(ushort const *,HSTRING__ * *)

- ea: `0x18002850c`
- end: `0x180028639`
- name: `?GetQualifiedTypeNameFromDataStoreId@CTypeServices@@AEAAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `301`
- prototype: `int(CTypeServices *__hidden this, const unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180065d40`

## callees

- `0x18002850c`
- `0x180028640`
- `0x1800c8458`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028582`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028600`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028582`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028600`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002853a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800285ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800285d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028624`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002862f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002853a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800285ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800285d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028624`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002862f`

## string_xrefs

- `0x18002860e`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CTypeServices::GetQualifiedTypeNameFromDataStoreId(
        CTypeServices *this,
        const unsigned __int16 *a2,
        HSTRING *a3)
{
  unsigned __int64 v6; // rdx
  HRESULT v7; // eax
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-50h]
  int v12; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v13; // [rsp+38h] [rbp-38h] BYREF
  HSTRING v14; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v12 = 0;
  WindowsDeleteString(0);
  v13 = 0;
  WindowsDeleteString(0);
  v14 = 0;
  string = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 > 0xFFFFFFFF || (int)v6 + 1 < (unsigned int)v6 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v7 = WindowsCreateStringReference(a2, v6, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    __debugbreak();
  }
  v8 = CTypeServices::ParseDataStoreId(
         this,
         string,
         (enum Windows::Internal::Storage::Cloud::PartitionKind *)&v12,
         &v14,
         a3,
         &v13);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x476,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
      (const char *)(unsigned int)v8,
      v11);
    WindowsDeleteString(v13);
    WindowsDeleteString(v14);
    return v9;
  }
  else
  {
    WindowsDeleteString(v13);
    WindowsDeleteString(v14);
    return 0;
  }
}

```

## disassembly

```asm
0x18002850c  push    rbp
0x18002850e  push    rbx
0x18002850f  push    rsi
0x180028510  push    rdi
0x180028511  push    r14
0x180028513  mov     rbp, rsp
0x180028516  sub     rsp, 70h
0x18002851a  mov     rax, cs:__security_cookie
0x180028521  xor     rax, rsp
0x180028524  mov     [rbp+var_8], rax
0x180028528  mov     rsi, r8
0x18002852b  mov     rbx, rdx
0x18002852e  mov     rdi, rcx
0x180028531  xor     r14d, r14d
0x180028534  mov     [rbp+var_40], r14d
0x180028538  xor     ecx, ecx; string
0x18002853a  call    cs:__imp_WindowsDeleteString
0x180028540  mov     [rbp+var_38], r14
0x180028544  xor     ecx, ecx; string
0x180028546  call    cs:__imp_WindowsDeleteString
0x18002854c  mov     [rbp+var_30], r14
0x180028550  mov     [rbp+string], r14
0x180028554  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180028558  inc     rdx; length
0x18002855b  cmp     [rbx+rdx*2], r14w
0x180028560  jnz     short loc_180028558
0x180028562  mov     eax, 0FFFFFFFFh
0x180028567  cmp     rdx, rax
0x18002856a  ja      short loc_180028573
0x18002856c  lea     eax, [rdx+1]
0x18002856f  cmp     eax, edx
0x180028571  jnb     short loc_180028589
0x180028573  xor     r9d, r9d; lpArguments
0x180028576  xor     r8d, r8d; nNumberOfArguments
0x180028579  lea     edx, [r9+1]; dwExceptionFlags
0x18002857d  mov     ecx, 80070216h; dwExceptionCode
0x180028582  call    cs:__imp_RaiseException
0x180028588  int     3; Trap to Debugger
0x180028589  lea     r9, [rbp+string]; string
0x18002858d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180028591  mov     rcx, rbx; sourceString
0x180028594  call    cs:__imp_WindowsCreateStringReference
0x18002859a  test    eax, eax
0x18002859c  js      short loc_1800285F4
0x18002859e  lea     rax, [rbp+var_38]
0x1800285a2  mov     [rsp+70h+var_48], rax; HSTRING *
0x1800285a7  mov     [rsp+70h+var_50], rsi; int
0x1800285ac  lea     r9, [rbp+var_30]; HSTRING *
0x1800285b0  lea     r8, [rbp+var_40]; enum Windows::Internal::Storage::Cloud::PartitionKind *
0x1800285b4  mov     rdx, [rbp+string]; HSTRING
0x1800285b8  mov     rcx, rdi; this
0x1800285bb  call    ?ParseDataStoreId@CTypeServices@@UEAAJPEAUHSTRING__@@PEAW4PartitionKind@Cloud@Storage@Internal@Windows@@PEAPEAU2@22@Z; CTypeServices::ParseDataStoreId(HSTRING__ *,Windows::Internal::Storage::Cloud::PartitionKind *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800285c0  mov     ebx, eax
0x1800285c2  test    eax, eax
0x1800285c4  js      short loc_180028607
0x1800285c6  mov     rcx, [rbp+var_38]; string
0x1800285ca  call    cs:__imp_WindowsDeleteString
0x1800285d0  nop
0x1800285d1  mov     rcx, [rbp+var_30]; string
0x1800285d5  call    cs:__imp_WindowsDeleteString
0x1800285db  xor     eax, eax
0x1800285dd  mov     rcx, [rbp+var_8]
0x1800285e1  xor     rcx, rsp; StackCookie
0x1800285e4  call    __security_check_cookie
0x1800285e9  add     rsp, 70h
0x1800285ed  pop     r14
0x1800285ef  pop     rdi
0x1800285f0  pop     rsi
0x1800285f1  pop     rbx
0x1800285f2  pop     rbp
0x1800285f3  retn
0x1800285f4  xor     r9d, r9d; lpArguments
0x1800285f7  xor     r8d, r8d; nNumberOfArguments
0x1800285fa  lea     edx, [r9+1]; dwExceptionFlags
0x1800285fe  mov     ecx, eax; dwExceptionCode
0x180028600  call    cs:__imp_RaiseException
0x180028606  int     3; Trap to Debugger
0x180028607  mov     rcx, [rbp+28h]; this
0x18002860b  mov     r9d, ebx; char *
0x18002860e  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x180028615  mov     edx, 476h; void *
0x18002861a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002861f  nop
0x180028620  mov     rcx, [rbp+var_38]; string
0x180028624  call    cs:__imp_WindowsDeleteString
0x18002862a  nop
0x18002862b  mov     rcx, [rbp+var_30]; string
0x18002862f  call    cs:__imp_WindowsDeleteString
0x180028635  mov     eax, ebx
0x180028637  jmp     short loc_1800285DD
```
