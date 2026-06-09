# CExec::MakeAttributeList(ulong)

- ea: `0x1400187e0`
- end: `0x1400188c3`
- name: `?MakeAttributeList@CExec@@YA?AV?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@K@Z`
- size: `227`
- prototype: `struct _PROC_THREAD_ATTRIBUTE_LIST **__fastcall(struct _PROC_THREAD_ATTRIBUTE_LIST **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140016cc0`

## callees

- `0x140002310`
- `0x140007a18`
- `0x14000e828`
- `0x1400126b0`
- `0x1400187e0`
- `0x14001a970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018826`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018826`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14001881c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x140018862`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x14001881c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x140018862`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140018838`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140018838`

## string_xrefs

- `0x140018887`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400188ab`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
struct _PROC_THREAD_ATTRIBUTE_LIST **__fastcall CExec::MakeAttributeList(struct _PROC_THREAD_ATTRIBUTE_LIST **a1)
{
  __int64 v2; // rdx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v3; // rax
  void *v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  const char *v7; // r9
  unsigned int v9; // eax
  ULONG_PTR Size; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Size = 0;
  if ( InitializeProcThreadAttributeList(0, 3u, 0, &Size) || GetLastError() != 122 )
  {
    v9 = wil::verify_hresult<long>(2147549183LL, v2);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)v9,
      0);
  }
  v3 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)LocalAlloc(0, Size);
  *a1 = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v4, v5, v6);
  if ( !InitializeProcThreadAttributeList(v3, 3u, 0, &Size) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v7);
  return a1;
}

```

## disassembly

```asm
0x1400187e0  push    rbx
0x1400187e2  sub     rsp, 40h
0x1400187e6  mov     rax, cs:__security_cookie
0x1400187ed  xor     rax, rsp
0x1400187f0  mov     [rsp+48h+var_10], rax
0x1400187f5  mov     rbx, rcx
0x1400187f8  mov     [rsp+48h+var_20], rcx
0x1400187fd  mov     [rsp+48h+var_28], 0; int
0x140018805  mov     [rsp+48h+Size], 0
0x14001880e  lea     r9, [rsp+48h+Size]; lpSize
0x140018813  xor     r8d, r8d; dwFlags
0x140018816  lea     edx, [r8+3]; dwAttributeCount
0x14001881a  xor     ecx, ecx; lpAttributeList
0x14001881c  call    cs:__imp_InitializeProcThreadAttributeList
0x140018822  test    eax, eax
0x140018824  jnz     short loc_140018899
0x140018826  call    cs:__imp_GetLastError
0x14001882c  cmp     eax, 7Ah ; 'z'
0x14001882f  jnz     short loc_140018899
0x140018831  mov     rdx, [rsp+48h+Size]; uBytes
0x140018836  xor     ecx, ecx; uFlags
0x140018838  call    cs:__imp_LocalAlloc
0x14001883e  mov     [rbx], rax
0x140018841  mov     [rsp+48h+var_28], 1
0x140018849  mov     rcx, [rsp+48h]; this
0x14001884e  test    rax, rax
0x140018851  jz      short loc_1400188BD
0x140018853  lea     r9, [rsp+48h+Size]; lpSize
0x140018858  xor     r8d, r8d; dwFlags
0x14001885b  lea     edx, [r8+3]; dwAttributeCount
0x14001885f  mov     rcx, rax; lpAttributeList
0x140018862  call    cs:__imp_InitializeProcThreadAttributeList
0x140018868  test    eax, eax
0x14001886a  jz      short loc_140018882
0x14001886c  mov     rax, rbx
0x14001886f  mov     rcx, [rsp+48h+var_10]
0x140018874  xor     rcx, rsp; StackCookie
0x140018877  call    __security_check_cookie
0x14001887c  add     rsp, 40h
0x140018880  pop     rbx
0x140018881  retn
0x140018882  mov     rcx, [rsp+48h]; this
0x140018887  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001888e  mov     edx, 58h ; 'X'; void *
0x140018893  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140018899  mov     ecx, 8000FFFFh
0x14001889e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400188a3  mov     r9d, eax; char *
0x1400188a6  mov     rcx, [rsp+48h]; this
0x1400188ab  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400188b2  mov     edx, 51h ; 'Q'; void *
0x1400188b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400188bd  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
