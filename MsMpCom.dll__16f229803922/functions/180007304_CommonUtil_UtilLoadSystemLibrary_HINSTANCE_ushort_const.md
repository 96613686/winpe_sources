# CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,ushort const *)

- ea: `0x180007304`
- end: `0x1800074f3`
- name: `?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBG@Z`
- size: `495`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, HINSTANCE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008a6c`

## callees

- `0x1800070b8`
- `0x180007148`
- `0x18000726c`
- `0x180007304`
- `0x180007a44`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180007347`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007377`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800073c0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800073f4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000740b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007439`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000746c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000749d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800074ab`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800074bd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800074d8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007347`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007377`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800073c0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800073f4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000740b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007439`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000746c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000749d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800074ab`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800074bd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800074d8`
- `KERNEL32!GetSystemDirectoryW` at `0x18000732a`
- `KERNEL32!GetSystemDirectoryW` at `0x180007355`
- `KERNEL32!GetSystemDirectoryW` at `0x180007419`
- `KERNEL32!GetSystemDirectoryW` at `0x180007447`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilLoadSystemLibrary(CommonUtil *this, HINSTANCE *a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v5; // rdx
  const unsigned __int16 *v6; // r8
  int WindowsPath; // ebx
  HINSTANCE *v9; // rbx
  const unsigned __int16 *v10; // r8
  unsigned int v11; // r9d
  int Library; // edi
  void *v13; // rdi
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // rdx
  int IsFileExists; // esi
  HINSTANCE *v18; // [rsp+50h] [rbp+30h] BYREF
  void *v19; // [rsp+58h] [rbp+38h] BYREF

  v18 = 0;
  if ( (int)CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v18, a2) < 0 )
  {
    if ( v18 )
    {
      operator delete[](v18);
      v18 = 0;
    }
    WindowsPath = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v18, a2);
    if ( WindowsPath < 0 )
      goto LABEL_5;
  }
  v9 = v18;
  if ( CommonUtil::UtilIsFileExists((CommonUtil *)v18, v5, v6) >= 0 )
    goto LABEL_32;
  v19 = 0;
  if ( (int)CommonUtil::NewSprintfW(
              (CommonUtil *)&v19,
              (unsigned __int16 **)L"forwarders\\%ws",
              (const unsigned __int16 *)a2) < 0 )
  {
    if ( v19 )
    {
      operator delete[](v19);
      v19 = 0;
    }
    Library = CommonUtil::NewSprintfW(
                (CommonUtil *)&v19,
                (unsigned __int16 **)L"forwarders\\%ws",
                (const unsigned __int16 *)a2);
    if ( Library < 0 )
    {
      if ( v19 )
        operator delete[](v19);
      goto LABEL_33;
    }
  }
  v13 = v19;
  if ( v9 )
  {
    operator delete[](v9);
    v18 = 0;
  }
  if ( (int)CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v18, v13) < 0 )
  {
    if ( v18 )
    {
      operator delete[](v18);
      v18 = 0;
    }
    WindowsPath = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &v18, v13);
    if ( WindowsPath < 0 )
    {
      if ( v13 )
        operator delete[](v13);
LABEL_5:
      if ( v18 )
        operator delete[](v18);
      return (unsigned int)WindowsPath;
    }
  }
  v9 = v18;
  if ( CommonUtil::UtilIsFileExists((CommonUtil *)v18, v14, v15) >= 0
    || (IsFileExists = CommonUtil::UtilIsFileExists((CommonUtil *)v9, v16, v10), IsFileExists >= 0) )
  {
    if ( v13 )
      operator delete[](v13);
LABEL_32:
    Library = CommonUtil::UtilLoadLibraryEx(this, v9, v10, v11);
LABEL_33:
    if ( v9 )
      operator delete[](v9);
    return (unsigned int)Library;
  }
  if ( v13 )
    operator delete[](v13);
  if ( v9 )
    operator delete[](v9);
  return (unsigned int)IsFileExists;
}

```

## disassembly

```asm
0x180007304  mov     [rsp-18h+arg_0], rbx
0x180007309  mov     [rsp-18h+arg_8], rsi
0x18000730e  push    rbp
0x18000730f  push    rdi
0x180007310  push    r14
0x180007312  mov     rbp, rsp
0x180007315  sub     rsp, 20h
0x180007319  mov     rdi, rdx
0x18000731c  mov     [rbp+arg_10], 0
0x180007324  mov     r14, rcx
0x180007327  mov     r8, rdx
0x18000732a  mov     rcx, cs:__imp_GetSystemDirectoryW
0x180007331  lea     rdx, [rbp+arg_10]
0x180007335  call    CommonUtil__UtilGetWindowsPath
0x18000733a  test    eax, eax
0x18000733c  jns     short loc_180007384
0x18000733e  mov     rcx, [rbp+arg_10]
0x180007342  test    rcx, rcx
0x180007345  jz      short loc_180007355
0x180007347  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000734d  mov     [rbp+arg_10], 0
0x180007355  mov     rcx, cs:__imp_GetSystemDirectoryW
0x18000735c  lea     rdx, [rbp+arg_10]
0x180007360  mov     r8, rdi
0x180007363  call    CommonUtil__UtilGetWindowsPath
0x180007368  mov     ebx, eax
0x18000736a  test    eax, eax
0x18000736c  jns     short loc_180007384
0x18000736e  mov     rcx, [rbp+arg_10]
0x180007372  test    rcx, rcx
0x180007375  jz      short loc_18000737D
0x180007377  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000737d  mov     eax, ebx
0x18000737f  jmp     loc_1800074E0
0x180007384  mov     rbx, [rbp+arg_10]
0x180007388  mov     rcx, rbx; this
0x18000738b  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x180007390  test    eax, eax
0x180007392  jns     loc_1800074C3
0x180007398  mov     r8, rdi; unsigned __int16 *
0x18000739b  mov     [rbp+arg_18], 0
0x1800073a3  lea     rdx, aForwardersWs; "forwarders\\%ws"
0x1800073aa  lea     rcx, [rbp+arg_18]; this
0x1800073ae  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800073b3  test    eax, eax
0x1800073b5  jns     short loc_1800073FF
0x1800073b7  mov     rcx, [rbp+arg_18]
0x1800073bb  test    rcx, rcx
0x1800073be  jz      short loc_1800073CE
0x1800073c0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800073c6  mov     [rbp+arg_18], 0
0x1800073ce  mov     r8, rdi; unsigned __int16 *
0x1800073d1  lea     rdx, aForwardersWs; "forwarders\\%ws"
0x1800073d8  lea     rcx, [rbp+arg_18]; this
0x1800073dc  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800073e1  mov     edi, eax
0x1800073e3  test    eax, eax
0x1800073e5  jns     short loc_1800073FF
0x1800073e7  mov     rcx, [rbp+arg_18]
0x1800073eb  test    rcx, rcx
0x1800073ee  jz      loc_1800074D0
0x1800073f4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800073fa  jmp     loc_1800074D0
0x1800073ff  mov     rdi, [rbp+arg_18]
0x180007403  test    rbx, rbx
0x180007406  jz      short loc_180007419
0x180007408  mov     rcx, rbx
0x18000740b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007411  mov     [rbp+arg_10], 0
0x180007419  mov     rcx, cs:__imp_GetSystemDirectoryW
0x180007420  lea     rdx, [rbp+arg_10]
0x180007424  mov     r8, rdi
0x180007427  call    CommonUtil__UtilGetWindowsPath
0x18000742c  test    eax, eax
0x18000742e  jns     short loc_180007477
0x180007430  mov     rcx, [rbp+arg_10]
0x180007434  test    rcx, rcx
0x180007437  jz      short loc_180007447
0x180007439  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000743f  mov     [rbp+arg_10], 0
0x180007447  mov     rcx, cs:__imp_GetSystemDirectoryW
0x18000744e  lea     rdx, [rbp+arg_10]
0x180007452  mov     r8, rdi
0x180007455  call    CommonUtil__UtilGetWindowsPath
0x18000745a  mov     ebx, eax
0x18000745c  test    eax, eax
0x18000745e  jns     short loc_180007477
0x180007460  test    rdi, rdi
0x180007463  jz      loc_18000736E
0x180007469  mov     rcx, rdi
0x18000746c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007472  jmp     loc_18000736E
0x180007477  mov     rbx, [rbp+arg_10]
0x18000747b  mov     rcx, rbx; this
0x18000747e  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x180007483  test    eax, eax
0x180007485  jns     short loc_1800074B5
0x180007487  mov     rcx, rbx; this
0x18000748a  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x18000748f  mov     esi, eax
0x180007491  test    eax, eax
0x180007493  jns     short loc_1800074B5
0x180007495  test    rdi, rdi
0x180007498  jz      short loc_1800074A3
0x18000749a  mov     rcx, rdi
0x18000749d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800074a3  test    rbx, rbx
0x1800074a6  jz      short loc_1800074B1
0x1800074a8  mov     rcx, rbx
0x1800074ab  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800074b1  mov     eax, esi
0x1800074b3  jmp     short loc_1800074E0
0x1800074b5  test    rdi, rdi
0x1800074b8  jz      short loc_1800074C3
0x1800074ba  mov     rcx, rdi
0x1800074bd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800074c3  mov     rdx, rbx; HINSTANCE *
0x1800074c6  mov     rcx, r14; this
0x1800074c9  call    ?UtilLoadLibraryEx@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBGK@Z; CommonUtil::UtilLoadLibraryEx(HINSTANCE__ * *,ushort const *,ulong)
0x1800074ce  mov     edi, eax
0x1800074d0  test    rbx, rbx
0x1800074d3  jz      short loc_1800074DE
0x1800074d5  mov     rcx, rbx
0x1800074d8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800074de  mov     eax, edi
0x1800074e0  mov     rbx, [rsp+20h+arg_0]
0x1800074e5  mov     rsi, [rsp+20h+arg_8]
0x1800074ea  add     rsp, 20h
0x1800074ee  pop     r14
0x1800074f0  pop     rdi
0x1800074f1  pop     rbp
0x1800074f2  retn
```
