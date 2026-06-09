# CancellableWait(void *,void *,ulong)

- ea: `0x180035ce4`
- end: `0x180035db4`
- name: `?CancellableWait@@YAXPEAX0K@Z`
- size: `208`
- prototype: `void __fastcall(void *, void *, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800487d4`
- `0x180049308`
- `0x180049d70`
- `0x18004f528`

## callees

- `0x180003a00`
- `0x180006b8c`
- `0x180011318`
- `0x180011334`
- `0x180012a98`
- `0x180035ce4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180035d10`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180035d10`

## string_xrefs

- `0x180035d4e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180035d68`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180035d7f`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180035d9c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
void __fastcall CancellableWait(void *a1, void *a2, DWORD a3)
{
  DWORD v3; // eax
  const char *v4; // r9
  unsigned int v5; // eax
  HANDLE Handles[2]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Handles[0] = a1;
  Handles[1] = a2;
  v3 = WaitForMultipleObjects(2u, Handles, 0, a3);
  if ( v3 )
  {
    if ( v3 != 1 )
    {
      if ( v3 != 258 )
      {
        if ( v3 != -1 )
        {
          v5 = wil::verify_hresult<long>(2147500037LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x97,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
            (const char *)v5,
            (int)Handles[0]);
        }
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x94,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
          v4);
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        (const char *)0x5B4,
        (unsigned int)Handles[0]);
    }
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      (const char *)0x4C7,
      (unsigned int)Handles[0]);
  }
}

```

## disassembly

```asm
0x180035ce4  sub     rsp, 48h
0x180035ce8  mov     rax, cs:__security_cookie
0x180035cef  xor     rax, rsp
0x180035cf2  mov     [rsp+48h+var_18], rax
0x180035cf7  mov     r9d, r8d; dwMilliseconds
0x180035cfa  mov     [rsp+48h+Handles], rcx; unsigned int
0x180035cff  xor     r8d, r8d; bWaitAll
0x180035d02  mov     [rsp+48h+var_20], rdx
0x180035d07  lea     rdx, [rsp+48h+Handles]; lpHandles
0x180035d0c  lea     ecx, [r8+2]; nCount
0x180035d10  call    cs:__imp_WaitForMultipleObjects
0x180035d16  test    eax, eax
0x180035d18  jz      short loc_180035D2D
0x180035d1a  cmp     eax, 1
0x180035d1d  jz      short loc_180035D97
0x180035d1f  cmp     eax, 102h
0x180035d24  jz      short loc_180035D7A
0x180035d26  cmp     eax, 0FFFFFFFFh
0x180035d29  jz      short loc_180035D63
0x180035d2b  jmp     short loc_180035D3F
0x180035d2d  mov     rcx, [rsp+48h+var_18]
0x180035d32  xor     rcx, rsp; StackCookie
0x180035d35  call    __security_check_cookie
0x180035d3a  add     rsp, 48h
0x180035d3e  retn
0x180035d3f  mov     ecx, 80004005h
0x180035d44  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180035d49  mov     rcx, [rsp+48h]; this
0x180035d4e  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180035d55  mov     r9d, eax; char *
0x180035d58  mov     edx, 97h; void *
0x180035d5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035d63  mov     rcx, [rsp+48h]; this
0x180035d68  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180035d6f  mov     edx, 94h; void *
0x180035d74  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180035d7a  mov     rcx, [rsp+48h]; this
0x180035d7f  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180035d86  mov     r9d, 5B4h; char *
0x180035d8c  mov     edx, 91h; void *
0x180035d91  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180035d97  mov     rcx, [rsp+48h]; this
0x180035d9c  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180035da3  mov     r9d, 4C7h; char *
0x180035da9  mov     edx, 8Eh; void *
0x180035dae  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
