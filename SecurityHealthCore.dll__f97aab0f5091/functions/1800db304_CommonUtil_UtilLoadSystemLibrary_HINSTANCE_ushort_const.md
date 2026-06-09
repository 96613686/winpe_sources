# CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,ushort const *)

- ea: `0x1800db304`
- end: `0x1800db4ee`
- name: `?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBG@Z`
- size: `490`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, HINSTANCE *, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000f530`
- `0x18001cac0`
- `0x180094504`
- `0x180095370`
- `0x1800966d0`
- `0x1800b0880`
- `0x1800b2890`
- `0x1800b4480`
- `0x1800db6c8`
- `0x1800df798`
- `0x1800e0260`

## callees

- `0x180004ae0`
- `0x1800db0a0`
- `0x1800db1ec`
- `0x1800db25c`
- `0x1800db304`
- `0x1800dc038`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x1800db32a`
- `KERNEL32!GetSystemDirectoryW` at `0x1800db354`
- `KERNEL32!GetSystemDirectoryW` at `0x1800db414`
- `KERNEL32!GetSystemDirectoryW` at `0x1800db441`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilLoadSystemLibrary(CommonUtil *this, HINSTANCE *a2, const unsigned __int16 *a3)
{
  const struct std::nothrow_t *v5; // rdx
  int WindowsPath; // ebx
  HINSTANCE *v8; // rbx
  const struct std::nothrow_t *v9; // rdx
  int Library; // edi
  void *v11; // rdi
  const struct std::nothrow_t *v12; // rdx
  int IsFileExists; // esi
  HINSTANCE *v14; // [rsp+50h] [rbp+30h] BYREF
  void *v15; // [rsp+58h] [rbp+38h] BYREF

  v14 = 0;
  if ( (int)CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v14, a2) < 0 )
  {
    if ( v14 )
    {
      operator delete(v14, v5);
      v14 = 0;
    }
    WindowsPath = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v14, a2);
    if ( WindowsPath < 0 )
      goto LABEL_5;
  }
  v8 = v14;
  if ( (int)CommonUtil::UtilIsFileExists((CommonUtil *)v14, (const unsigned __int16 *)v5) >= 0 )
    goto LABEL_32;
  v15 = 0;
  if ( (int)CommonUtil::NewSprintfW(
              (CommonUtil *)&v15,
              (unsigned __int16 **)L"forwarders\\%ws",
              (const unsigned __int16 *)a2) < 0 )
  {
    if ( v15 )
    {
      operator delete(v15, v9);
      v15 = 0;
    }
    Library = CommonUtil::NewSprintfW(
                (CommonUtil *)&v15,
                (unsigned __int16 **)L"forwarders\\%ws",
                (const unsigned __int16 *)a2);
    if ( Library < 0 )
    {
      if ( v15 )
        operator delete(v15, v9);
      goto LABEL_33;
    }
  }
  v11 = v15;
  if ( v8 )
  {
    operator delete(v8, v9);
    v14 = 0;
  }
  if ( (int)CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v14, v11) < 0 )
  {
    if ( v14 )
    {
      operator delete(v14, v5);
      v14 = 0;
    }
    WindowsPath = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v14, v11);
    if ( WindowsPath < 0 )
    {
      if ( v11 )
        operator delete(v11, v5);
LABEL_5:
      if ( v14 )
        operator delete(v14, v5);
      return (unsigned int)WindowsPath;
    }
  }
  v8 = v14;
  if ( (int)CommonUtil::UtilIsFileExists((CommonUtil *)v14, (const unsigned __int16 *)v5) >= 0
    || (IsFileExists = CommonUtil::UtilIsFileExists((CommonUtil *)v8, (const unsigned __int16 *)v12), IsFileExists >= 0) )
  {
    if ( v11 )
      operator delete(v11, v12);
LABEL_32:
    Library = CommonUtil::UtilLoadLibraryEx(this, v8, (const unsigned __int16 *)8);
LABEL_33:
    if ( v8 )
      operator delete(v8, v9);
    return (unsigned int)Library;
  }
  if ( v11 )
    operator delete(v11, v12);
  if ( v8 )
    operator delete(v8, v12);
  return (unsigned int)IsFileExists;
}

```

## disassembly

```asm
0x1800db304  mov     [rsp-18h+arg_0], rbx
0x1800db309  mov     [rsp-18h+arg_8], rsi
0x1800db30e  push    rbp
0x1800db30f  push    rdi
0x1800db310  push    r14
0x1800db312  mov     rbp, rsp
0x1800db315  sub     rsp, 20h
0x1800db319  mov     rdi, rdx
0x1800db31c  mov     [rbp+arg_10], 0
0x1800db324  mov     r14, rcx
0x1800db327  mov     r8, rdx
0x1800db32a  mov     rcx, cs:__imp_GetSystemDirectoryW
0x1800db331  lea     rdx, [rbp+arg_10]
0x1800db335  call    CommonUtil__UtilGetWindowsPath
0x1800db33a  test    eax, eax
0x1800db33c  jns     short loc_1800DB382
0x1800db33e  mov     rcx, [rbp+arg_10]; void *
0x1800db342  test    rcx, rcx
0x1800db345  jz      short loc_1800DB354
0x1800db347  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db34c  mov     [rbp+arg_10], 0
0x1800db354  mov     rcx, cs:__imp_GetSystemDirectoryW
0x1800db35b  lea     rdx, [rbp+arg_10]
0x1800db35f  mov     r8, rdi
0x1800db362  call    CommonUtil__UtilGetWindowsPath
0x1800db367  mov     ebx, eax
0x1800db369  test    eax, eax
0x1800db36b  jns     short loc_1800DB382
0x1800db36d  mov     rcx, [rbp+arg_10]; void *
0x1800db371  test    rcx, rcx
0x1800db374  jz      short loc_1800DB37B
0x1800db376  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db37b  mov     eax, ebx
0x1800db37d  jmp     loc_1800DB4DB
0x1800db382  mov     rbx, [rbp+arg_10]
0x1800db386  mov     rcx, rbx; this
0x1800db389  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x1800db38e  test    eax, eax
0x1800db390  jns     loc_1800DB4B9
0x1800db396  mov     r8, rdi; unsigned __int16 *
0x1800db399  mov     [rbp+arg_18], 0
0x1800db3a1  lea     rdx, aForwardersWs; "forwarders\\%ws"
0x1800db3a8  lea     rcx, [rbp+arg_18]; this
0x1800db3ac  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800db3b1  test    eax, eax
0x1800db3b3  jns     short loc_1800DB3FB
0x1800db3b5  mov     rcx, [rbp+arg_18]; void *
0x1800db3b9  test    rcx, rcx
0x1800db3bc  jz      short loc_1800DB3CB
0x1800db3be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db3c3  mov     [rbp+arg_18], 0
0x1800db3cb  mov     r8, rdi; unsigned __int16 *
0x1800db3ce  lea     rdx, aForwardersWs; "forwarders\\%ws"
0x1800db3d5  lea     rcx, [rbp+arg_18]; this
0x1800db3d9  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800db3de  mov     edi, eax
0x1800db3e0  test    eax, eax
0x1800db3e2  jns     short loc_1800DB3FB
0x1800db3e4  mov     rcx, [rbp+arg_18]; void *
0x1800db3e8  test    rcx, rcx
0x1800db3eb  jz      loc_1800DB4CC
0x1800db3f1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db3f6  jmp     loc_1800DB4CC
0x1800db3fb  mov     rdi, [rbp+arg_18]
0x1800db3ff  test    rbx, rbx
0x1800db402  jz      short loc_1800DB414
0x1800db404  mov     rcx, rbx; void *
0x1800db407  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db40c  mov     [rbp+arg_10], 0
0x1800db414  mov     rcx, cs:__imp_GetSystemDirectoryW
0x1800db41b  lea     rdx, [rbp+arg_10]
0x1800db41f  mov     r8, rdi
0x1800db422  call    CommonUtil__UtilGetWindowsPath
0x1800db427  test    eax, eax
0x1800db429  jns     short loc_1800DB470
0x1800db42b  mov     rcx, [rbp+arg_10]; void *
0x1800db42f  test    rcx, rcx
0x1800db432  jz      short loc_1800DB441
0x1800db434  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db439  mov     [rbp+arg_10], 0
0x1800db441  mov     rcx, cs:__imp_GetSystemDirectoryW
0x1800db448  lea     rdx, [rbp+arg_10]
0x1800db44c  mov     r8, rdi
0x1800db44f  call    CommonUtil__UtilGetWindowsPath
0x1800db454  mov     ebx, eax
0x1800db456  test    eax, eax
0x1800db458  jns     short loc_1800DB470
0x1800db45a  test    rdi, rdi
0x1800db45d  jz      loc_1800DB36D
0x1800db463  mov     rcx, rdi; void *
0x1800db466  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db46b  jmp     loc_1800DB36D
0x1800db470  mov     rbx, [rbp+arg_10]
0x1800db474  mov     rcx, rbx; this
0x1800db477  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x1800db47c  test    eax, eax
0x1800db47e  jns     short loc_1800DB4AC
0x1800db480  mov     rcx, rbx; this
0x1800db483  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x1800db488  mov     esi, eax
0x1800db48a  test    eax, eax
0x1800db48c  jns     short loc_1800DB4AC
0x1800db48e  test    rdi, rdi
0x1800db491  jz      short loc_1800DB49B
0x1800db493  mov     rcx, rdi; void *
0x1800db496  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db49b  test    rbx, rbx
0x1800db49e  jz      short loc_1800DB4A8
0x1800db4a0  mov     rcx, rbx; void *
0x1800db4a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db4a8  mov     eax, esi
0x1800db4aa  jmp     short loc_1800DB4DB
0x1800db4ac  test    rdi, rdi
0x1800db4af  jz      short loc_1800DB4B9
0x1800db4b1  mov     rcx, rdi; void *
0x1800db4b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db4b9  mov     r8d, 8; unsigned __int16 *
0x1800db4bf  mov     rdx, rbx; HINSTANCE *
0x1800db4c2  mov     rcx, r14; this
0x1800db4c5  call    ?UtilLoadLibraryEx@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBGK@Z; CommonUtil::UtilLoadLibraryEx(HINSTANCE__ * *,ushort const *,ulong)
0x1800db4ca  mov     edi, eax
0x1800db4cc  test    rbx, rbx
0x1800db4cf  jz      short loc_1800DB4D9
0x1800db4d1  mov     rcx, rbx; void *
0x1800db4d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800db4d9  mov     eax, edi
0x1800db4db  mov     rbx, [rsp+20h+arg_0]
0x1800db4e0  mov     rsi, [rsp+20h+arg_8]
0x1800db4e5  add     rsp, 20h
0x1800db4e9  pop     r14
0x1800db4eb  pop     rdi
0x1800db4ec  pop     rbp
0x1800db4ed  retn
```
