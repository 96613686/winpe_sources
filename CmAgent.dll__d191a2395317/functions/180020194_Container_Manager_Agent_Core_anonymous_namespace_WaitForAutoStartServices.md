# Container::Manager::Agent::Core::_anonymous_namespace_::WaitForAutoStartServices

- ea: `0x180020194`
- end: `0x1800202ff`
- name: `Container::Manager::Agent::Core::_anonymous_namespace_::WaitForAutoStartServices`
- size: `363`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005050`
- `0x180005400`

## callees

- `0x180003ce4`
- `0x1800045e4`
- `0x1800067fc`
- `0x180007b4c`
- `0x180009518`
- `0x180020194`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002020b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002020b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800201b4`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800201b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020249`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020249`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800202b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800201f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020226`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800201f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020226`

## string_xrefs

- `0x1800202ed`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800201d8`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180020293`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x1800201a6`: `Global\SC_AutoStartComplete`
- `0x180020271`: `onecore\base\gendrv\silos\clem\agent\core\lib\Utils.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::_anonymous_namespace_::WaitForAutoStartServices(DWORD *a1)
{
  wil::details *v2; // rcx
  HANDLE v3; // rbx
  int LastErrorFailHr; // eax
  unsigned int v5; // edi
  int TickCount64; // edi
  DWORD v8; // eax
  const char *v9; // r9
  DWORD v10; // eax
  DWORD v11; // ecx
  __int64 v12; // r8
  const char *v13; // r9
  int v14; // eax
  __int64 v15; // r8
  const char *v16; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
  if ( !v3 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v2);
    v5 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE3,
        (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)(unsigned int)LastErrorFailHr);
      return v5;
    }
  }
  TickCount64 = GetTickCount64();
  if ( !*a1 || (v8 = WaitForSingleObjectEx(v3, *a1, 0), v8 == 258) )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x3F,
            (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\Utils.h",
            (const char *)0x5B4);
    v5 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE5,
        (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)(unsigned int)v14);
      if ( v3 && !CloseHandle(v3) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
      return v5;
    }
  }
  else
  {
    if ( v8 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    v10 = GetTickCount64() - TickCount64;
    v11 = *a1;
    if ( *a1 >= v10 )
      v11 = v10;
    *a1 -= v11;
  }
  if ( v3 )
  {
    if ( !CloseHandle(v3) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
  }
  return 0;
}

```

## disassembly

```asm
0x180020194  mov     [rsp+arg_0], rbx
0x180020199  mov     [rsp+arg_8], rsi
0x18002019e  push    rdi; int
0x18002019f  sub     rsp, 20h
0x1800201a3  mov     rsi, rcx
0x1800201a6  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x1800201ad  mov     ecx, 100000h; dwDesiredAccess
0x1800201b2  xor     edx, edx; bInheritHandle
0x1800201b4  call    cs:__imp_OpenEventW
0x1800201bb  nop     dword ptr [rax+rax+00h]
0x1800201c0  mov     rbx, rax
0x1800201c3  test    rax, rax
0x1800201c6  jnz     short loc_1800201F0
0x1800201c8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800201cd  mov     edi, eax
0x1800201cf  test    eax, eax
0x1800201d1  jns     short loc_1800201F0
0x1800201d3  mov     rcx, [rsp+28h]; this
0x1800201d8  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800201df  mov     r9d, eax; char *
0x1800201e2  mov     edx, 0E3h; void *
0x1800201e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800201ec  mov     eax, edi
0x1800201ee  jmp     short loc_18002025B
0x1800201f0  call    cs:__imp_GetTickCount64
0x1800201f7  nop     dword ptr [rax+rax+00h]
0x1800201fc  mov     edx, [rsi]; dwMilliseconds
0x1800201fe  mov     rdi, rax
0x180020201  test    edx, edx
0x180020203  jz      short loc_18002026C
0x180020205  xor     r8d, r8d; bAlertable
0x180020208  mov     rcx, rbx; hHandle
0x18002020b  call    cs:__imp_WaitForSingleObjectEx
0x180020212  nop     dword ptr [rax+rax+00h]
0x180020217  cmp     eax, 102h
0x18002021c  jz      short loc_18002026C
0x18002021e  test    eax, eax
0x180020220  jnz     loc_1800202E8
0x180020226  call    cs:__imp_GetTickCount64
0x18002022d  nop     dword ptr [rax+rax+00h]
0x180020232  mov     edx, [rsi]
0x180020234  sub     eax, edi
0x180020236  cmp     edx, eax
0x180020238  mov     ecx, edx
0x18002023a  cmovnb  ecx, eax
0x18002023d  sub     edx, ecx
0x18002023f  mov     [rsi], edx
0x180020241  test    rbx, rbx
0x180020244  jz      short loc_180020259
0x180020246  mov     rcx, rbx; hObject
0x180020249  call    cs:__imp_CloseHandle
0x180020250  nop     dword ptr [rax+rax+00h]
0x180020255  test    eax, eax
0x180020257  jz      short loc_1800202C8
0x180020259  xor     eax, eax
0x18002025b  mov     rbx, [rsp+28h+arg_0]
0x180020260  mov     rsi, [rsp+28h+arg_8]
0x180020265  add     rsp, 20h
0x180020269  pop     rdi
0x18002026a  retn
0x18002026c  mov     rcx, [rsp+28h]; this
0x180020271  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180020278  mov     r9d, 5B4h; char *
0x18002027e  mov     edx, 3Fh ; '?'; void *
0x180020283  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180020288  mov     edi, eax
0x18002028a  test    eax, eax
0x18002028c  jns     short loc_180020241
0x18002028e  mov     rcx, [rsp+28h]; this
0x180020293  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18002029a  mov     r9d, eax; char *
0x18002029d  mov     edx, 0E5h; void *
0x1800202a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800202a7  test    rbx, rbx
0x1800202aa  jz      loc_1800201EC
0x1800202b0  mov     rcx, rbx; hObject
0x1800202b3  call    cs:__imp_CloseHandle
0x1800202ba  nop     dword ptr [rax+rax+00h]
0x1800202bf  test    eax, eax
0x1800202c1  jz      short loc_1800202D8
0x1800202c3  jmp     loc_1800201EC
0x1800202c8  mov     rcx, [rsp+28h]; this
0x1800202cd  mov     edx, 0A0Bh; void *
0x1800202d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800202d8  mov     rcx, [rsp+28h]; this
0x1800202dd  mov     edx, 0A0Bh; void *
0x1800202e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800202e8  mov     rcx, [rsp+28h]; this
0x1800202ed  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800202f4  mov     edx, 0B0Fh; void *
0x1800202f9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
