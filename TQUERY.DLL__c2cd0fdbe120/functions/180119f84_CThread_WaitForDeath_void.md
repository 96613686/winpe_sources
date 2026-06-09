# CThread::WaitForDeath(void)

- ea: `0x180119f84`
- end: `0x18011a06c`
- name: `?WaitForDeath@CThread@@QEAAXXZ`
- size: `232`
- prototype: `void __fastcall(CThread *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180177c78`
- `0x180293f70`

## callees

- `0x180096740`
- `0x180119f84`
- `0x18015aa68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180119ff7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180119ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011a00a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011a00a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180119fa2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180119fa2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180119fda`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18011a03b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180119fda`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18011a03b`

## string_xrefs

- `0x18011a013`: `[Query] Wait result %d and error %d waiting for thread %d to die`
- `0x18011a047`: `[Query] Waited 1 second for thread %d to die`
- `0x180119fb6`: `[Query] ResumeThread result 0xffffffff and error %d waiting for thread %d to die`

## pseudocode

```c
void __fastcall CThread::WaitForDeath(CThread *this)
{
  void *v2; // rcx
  DWORD LastError; // eax
  DWORD v4; // eax
  DWORD v5; // edi
  DWORD v6; // eax
  __int64 v7; // [rsp+20h] [rbp-18h]
  __int64 v8; // [rsp+28h] [rbp-10h]

  while ( *((_DWORD *)this + 8) )
  {
    v2 = *(void **)this;
    *((_QWORD *)this + 2) = 0;
    if ( ResumeThread(v2) == -1 )
    {
      LastError = GetLastError();
      LODWORD(v7) = *((_DWORD *)this + 2);
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\tquery\\internal\\include\\thrd32.hxx",
        (const wchar_t *)0xF9,
        (unsigned int)L"[Query] ResumeThread result 0xffffffff and error %d waiting for thread %d to die",
        (const wchar_t *)LastError,
        v7);
      Sleep(0x3E8u);
    }
    else
    {
      *((_DWORD *)this + 8) = 0;
    }
  }
  while ( 1 )
  {
    v4 = WaitForSingleObject(*(HANDLE *)this, 0x3E8u);
    v5 = v4;
    if ( !v4 )
      break;
    if ( v4 == 258 )
    {
      SearchIndexerDebug::Warning(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\tquery\\internal\\include\\thrd32.hxx",
        (const wchar_t *)0x113,
        (unsigned int)L"[Query] Waited 1 second for thread %d to die",
        (const wchar_t *)*((unsigned int *)this + 2));
    }
    else
    {
      v6 = GetLastError();
      LODWORD(v8) = *((_DWORD *)this + 2);
      LODWORD(v7) = v6;
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\tquery\\internal\\include\\thrd32.hxx",
        (const wchar_t *)0x118,
        (unsigned int)L"[Query] Wait result %d and error %d waiting for thread %d to die",
        (const wchar_t *)v5,
        v7,
        v8);
      Sleep(0x3E8u);
    }
  }
}

```

## disassembly

```asm
0x180119f84  mov     [rsp+arg_0], rbx
0x180119f89  push    rdi
0x180119f8a  sub     rsp, 30h
0x180119f8e  cmp     dword ptr [rcx+20h], 0
0x180119f92  mov     rbx, rcx
0x180119f95  jz      short loc_180119FEF
0x180119f97  mov     rcx, [rbx]; hThread
0x180119f9a  mov     qword ptr [rbx+10h], 0
0x180119fa2  call    cs:__imp_ResumeThread
0x180119fa8  cmp     eax, 0FFFFFFFFh
0x180119fab  jnz     short loc_180119FE2
0x180119fad  call    cs:__imp_GetLastError
0x180119fb3  mov     ecx, [rbx+8]
0x180119fb6  lea     r8, aQueryResumethr; "[Query] ResumeThread result 0xffffffff "...
0x180119fbd  mov     dword ptr [rsp+38h+var_18], ecx
0x180119fc1  mov     r9d, eax; wchar_t *
0x180119fc4  lea     rcx, aOnecoreuapBase_139; "onecoreuap\\base\\appmodel\\Search\\tqu"...
0x180119fcb  mov     edx, 0F9h; wchar_t *
0x180119fd0  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180119fd5  mov     ecx, 3E8h; dwMilliseconds
0x180119fda  call    cs:__imp_Sleep
0x180119fe0  jmp     short loc_180119FE9
0x180119fe2  mov     dword ptr [rbx+20h], 0
0x180119fe9  cmp     dword ptr [rbx+20h], 0
0x180119fed  jnz     short loc_180119F97
0x180119fef  mov     rcx, [rbx]; hHandle
0x180119ff2  mov     edx, 3E8h; dwMilliseconds
0x180119ff7  call    cs:__imp_WaitForSingleObject
0x180119ffd  mov     edi, eax
0x180119fff  test    eax, eax
0x18011a001  jz      short loc_18011A061
0x18011a003  cmp     eax, 102h
0x18011a008  jz      short loc_18011A043
0x18011a00a  call    cs:__imp_GetLastError
0x18011a010  mov     ecx, [rbx+8]
0x18011a013  lea     r8, aQueryWaitResul; "[Query] Wait result %d and error %d wai"...
0x18011a01a  mov     [rsp+38h+var_10], ecx
0x18011a01e  mov     r9d, edi; wchar_t *
0x18011a021  lea     rcx, aOnecoreuapBase_139; "onecoreuap\\base\\appmodel\\Search\\tqu"...
0x18011a028  mov     dword ptr [rsp+38h+var_18], eax
0x18011a02c  mov     edx, 118h; wchar_t *
0x18011a031  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18011a036  mov     ecx, 3E8h; dwMilliseconds
0x18011a03b  call    cs:__imp_Sleep
0x18011a041  jmp     short loc_180119FEF
0x18011a043  mov     r9d, [rbx+8]; wchar_t *
0x18011a047  lea     r8, aQueryWaited1Se; "[Query] Waited 1 second for thread %d t"...
0x18011a04e  mov     edx, 113h; wchar_t *
0x18011a053  lea     rcx, aOnecoreuapBase_139; "onecoreuap\\base\\appmodel\\Search\\tqu"...
0x18011a05a  call    ?Warning@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Warning(wchar_t const *,uint,wchar_t const *,...)
0x18011a05f  jmp     short loc_180119FEF
0x18011a061  mov     rbx, [rsp+38h+arg_0]
0x18011a066  add     rsp, 30h
0x18011a06a  pop     rdi
0x18011a06b  retn
```
