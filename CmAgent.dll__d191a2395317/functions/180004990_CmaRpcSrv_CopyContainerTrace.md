# CmaRpcSrv_CopyContainerTrace

- ea: `0x180004990`
- end: `0x180004b1e`
- name: `CmaRpcSrv_CopyContainerTrace`
- size: `398`
- prototype: `__int64 __fastcall(__int64, int, const WCHAR *, const char *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task`

## callees

- `0x180002534`
- `0x180002c48`
- `0x180002f1c`
- `0x180003ce4`
- `0x1800045e4`
- `0x180004990`
- `0x180007b2c`
- `0x180007b4c`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180004a49`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180004a49`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180004a82`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180004a82`

## string_xrefs

- `0x180004af1`: `onecore\base\gendrv\silos\clem\agent\service\api.cpp`
- `0x180004a61`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180004a97`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180004ad8`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180004b0b`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall CmaRpcSrv_CopyContainerTrace(__int64 a1, int a2, const WCHAR *a3, const char *a4)
{
  const WCHAR *v5; // rsi
  const WCHAR *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  ULONG v9; // r12d
  ULONG v10; // r14d
  struct _EVENT_TRACE_PROPERTIES *v11; // rax
  struct _EVENT_TRACE_PROPERTIES *v12; // rdi
  ULONG v13; // eax
  int LastError; // eax
  const struct std::nothrow_t *v15; // rdx
  int v16; // ebx
  const char *v17; // r9
  unsigned int v19; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a2 )
  {
    if ( a2 != 1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x64D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        a4);
    v5 = L"ContainerSystemCollector";
    v6 = L"C:\\Windows\\Logs\\Containers\\ContainerTraceSystem.etl";
  }
  else
  {
    v5 = L"ContainerUserLogger";
    v6 = L"C:\\Windows\\Logs\\Containers\\ContainerTraceUser.etl";
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v5[v8] );
  v9 = 2 * v8 + 122;
  do
    ++v7;
  while ( v6[v7] );
  v10 = v9 + 2 * (v7 + 1);
  v11 = (struct _EVENT_TRACE_PROPERTIES *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
  {
    v16 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)0x8007000ELL,
      v19);
    goto LABEL_19;
  }
  memset_0(v11, 0, v10);
  v12->Wnode.BufferSize = v10;
  v12->Wnode.Flags = 0x20000;
  v12->LoggerNameOffset = 120;
  v12->LogFileNameOffset = v9;
  v13 = ControlTraceW(0, v5, v12, 3u);
  if ( v13 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x669,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
                  (const char *)v13,
                  v19);
LABEL_12:
    v16 = LastError;
    goto LABEL_16;
  }
  if ( !CopyFileW(v6, a3, 1) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x66E,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
                  v17);
    goto LABEL_12;
  }
  v16 = 0;
LABEL_16:
  operator delete(v12, v15);
  if ( v16 >= 0 )
    return 0;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16E,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\service\\api.cpp",
    (const char *)(unsigned int)v16,
    v19);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180004990  push    rbx
0x180004992  push    rsi
0x180004993  push    rdi
0x180004994  push    r12
0x180004996  push    r13
0x180004998  push    r14
0x18000499a  push    r15; int
0x18000499c  sub     rsp, 20h
0x1800049a0  mov     r13, r8
0x1800049a3  xor     r8d, r8d
0x1800049a6  test    edx, edx
0x1800049a8  jz      short loc_1800049C3
0x1800049aa  cmp     edx, 1
0x1800049ad  jnz     loc_180004B06
0x1800049b3  lea     rsi, InstanceName; "ContainerSystemCollector"
0x1800049ba  lea     rbx, ExistingFileName; "C:\\Windows\\Logs\\Containers\\Containe"...
0x1800049c1  jmp     short loc_1800049D1
0x1800049c3  lea     rsi, aContaineruserl; "ContainerUserLogger"
0x1800049ca  lea     rbx, aCWindowsLogsCo; "C:\\Windows\\Logs\\Containers\\Containe"...
0x1800049d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800049d5  mov     rcx, rax
0x1800049d8  inc     rcx
0x1800049db  cmp     [rsi+rcx*2], r8w
0x1800049e0  jnz     short loc_1800049D8
0x1800049e2  lea     r12d, ds:7Ah[rcx*2]
0x1800049ea  inc     rax
0x1800049ed  cmp     [rbx+rax*2], r8w
0x1800049f2  jnz     short loc_1800049EA
0x1800049f4  lea     eax, [rax+1]
0x1800049f7  lea     r14d, [r12+rax*2]
0x1800049fb  mov     r15d, r14d
0x1800049fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004a05  mov     ecx, r14d; unsigned __int64
0x180004a08  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004a0d  mov     rdi, rax
0x180004a10  test    rax, rax
0x180004a13  jz      loc_180004ACB
0x180004a19  mov     r8d, r15d; Size
0x180004a1c  xor     edx, edx; Val
0x180004a1e  mov     rcx, rax; void *
0x180004a21  call    memset_0
0x180004a26  mov     [rdi], r14d
0x180004a29  mov     dword ptr [rdi+2Ch], 20000h
0x180004a30  mov     dword ptr [rdi+74h], 78h ; 'x'
0x180004a37  mov     [rdi+70h], r12d
0x180004a3b  mov     r9d, 3; ControlCode
0x180004a41  mov     r8, rdi; Properties
0x180004a44  mov     rdx, rsi; InstanceName
0x180004a47  xor     ecx, ecx; TraceHandle
0x180004a49  call    cs:__imp_ControlTraceW
0x180004a50  nop     dword ptr [rax+rax+00h]
0x180004a55  test    eax, eax
0x180004a57  jz      short loc_180004A76
0x180004a59  mov     rcx, [rsp+58h]; this
0x180004a5e  mov     r9d, eax; char *
0x180004a61  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180004a68  mov     edx, 669h; void *
0x180004a6d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180004a72  mov     ebx, eax
0x180004a74  jmp     short loc_180004AAC
0x180004a76  mov     r8d, 1; bFailIfExists
0x180004a7c  mov     rdx, r13; lpNewFileName
0x180004a7f  mov     rcx, rbx; lpExistingFileName
0x180004a82  call    cs:__imp_CopyFileW
0x180004a89  nop     dword ptr [rax+rax+00h]
0x180004a8e  test    eax, eax
0x180004a90  jnz     short loc_180004AAA
0x180004a92  mov     rcx, [rsp+58h]; this
0x180004a97  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180004a9e  mov     edx, 66Eh; void *
0x180004aa3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180004aa8  jmp     short loc_180004A72
0x180004aaa  xor     ebx, ebx
0x180004aac  mov     rcx, rdi; void *
0x180004aaf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004ab4  test    ebx, ebx
0x180004ab6  js      short loc_180004AE9
0x180004ab8  xor     eax, eax
0x180004aba  add     rsp, 20h
0x180004abe  pop     r15
0x180004ac0  pop     r14
0x180004ac2  pop     r13
0x180004ac4  pop     r12
0x180004ac6  pop     rdi
0x180004ac7  pop     rsi
0x180004ac8  pop     rbx
0x180004ac9  retn
0x180004acb  mov     rcx, [rsp+58h]; this
0x180004ad0  mov     ebx, 8007000Eh
0x180004ad5  mov     r9d, ebx; char *
0x180004ad8  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180004adf  mov     edx, 65Dh; void *
0x180004ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ae9  mov     rcx, [rsp+58h]; this
0x180004aee  mov     r9d, ebx; char *
0x180004af1  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180004af8  mov     edx, 16Eh; void *
0x180004afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b02  mov     eax, ebx
0x180004b04  jmp     short loc_180004ABA
0x180004b06  mov     rcx, [rsp+58h]; this
0x180004b0b  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180004b12  mov     edx, 64Dh; void *
0x180004b17  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
