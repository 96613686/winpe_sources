# CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,ushort const *)

- ea: `0x14000ed24`
- end: `0x14000ef0e`
- name: `?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBG@Z`
- size: `490`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, HINSTANCE *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400102f0`

## callees

- `0x1400015f4`
- `0x14000eb7c`
- `0x14000ec0c`
- `0x14000ec7c`
- `0x14000ed24`
- `0x14000f3ac`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x14000ed4a`
- `KERNEL32!GetSystemDirectoryW` at `0x14000ed74`
- `KERNEL32!GetSystemDirectoryW` at `0x14000ee34`
- `KERNEL32!GetSystemDirectoryW` at `0x14000ee61`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilLoadSystemLibrary(CommonUtil *this, HINSTANCE *a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v5; // rdx
  int WindowsPath; // ebx
  HINSTANCE *v8; // rbx
  unsigned __int64 v9; // rdx
  int Library; // edi
  void *v11; // rdi
  const unsigned __int16 *v12; // rdx
  int IsFileExists; // esi
  HINSTANCE *v14; // [rsp+50h] [rbp+30h] BYREF
  void *v15; // [rsp+58h] [rbp+38h] BYREF

  v14 = 0;
  if ( (int)CommonUtil::UtilGetWindowsPath((__int64)GetSystemDirectoryW, (CommonUtil *)&v14, (__int64)a2) < 0 )
  {
    if ( v14 )
    {
      operator delete(v14, (unsigned __int64)v5);
      v14 = 0;
    }
    WindowsPath = CommonUtil::UtilGetWindowsPath((__int64)GetSystemDirectoryW, (CommonUtil *)&v14, (__int64)a2);
    if ( WindowsPath < 0 )
      goto LABEL_5;
  }
  v8 = v14;
  if ( (int)CommonUtil::UtilIsFileExists((CommonUtil *)v14, v5) >= 0 )
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
  if ( (int)CommonUtil::UtilGetWindowsPath((__int64)GetSystemDirectoryW, (CommonUtil *)&v14, (__int64)v11) < 0 )
  {
    if ( v14 )
    {
      operator delete(v14, (unsigned __int64)v5);
      v14 = 0;
    }
    WindowsPath = CommonUtil::UtilGetWindowsPath((__int64)GetSystemDirectoryW, (CommonUtil *)&v14, (__int64)v11);
    if ( WindowsPath < 0 )
    {
      if ( v11 )
        operator delete(v11, (unsigned __int64)v5);
LABEL_5:
      if ( v14 )
        operator delete(v14, (unsigned __int64)v5);
      return (unsigned int)WindowsPath;
    }
  }
  v8 = v14;
  if ( (int)CommonUtil::UtilIsFileExists((CommonUtil *)v14, v5) >= 0
    || (IsFileExists = CommonUtil::UtilIsFileExists((CommonUtil *)v8, v12), IsFileExists >= 0) )
  {
    if ( v11 )
      operator delete(v11, (unsigned __int64)v12);
LABEL_32:
    Library = CommonUtil::UtilLoadLibraryEx(this, v8, (const unsigned __int16 *)8);
LABEL_33:
    if ( v8 )
      operator delete(v8, v9);
    return (unsigned int)Library;
  }
  if ( v11 )
    operator delete(v11, (unsigned __int64)v12);
  if ( v8 )
    operator delete(v8, (unsigned __int64)v12);
  return (unsigned int)IsFileExists;
}

```

## disassembly

```asm
0x14000ed24  mov     [rsp-18h+arg_0], rbx
0x14000ed29  mov     [rsp-18h+arg_8], rsi
0x14000ed2e  push    rbp
0x14000ed2f  push    rdi
0x14000ed30  push    r14
0x14000ed32  mov     rbp, rsp
0x14000ed35  sub     rsp, 20h
0x14000ed39  mov     rdi, rdx
0x14000ed3c  mov     [rbp+arg_10], 0
0x14000ed44  mov     r14, rcx
0x14000ed47  mov     r8, rdx
0x14000ed4a  mov     rcx, cs:__imp_GetSystemDirectoryW
0x14000ed51  lea     rdx, [rbp+arg_10]
0x14000ed55  call    CommonUtil__UtilGetWindowsPath
0x14000ed5a  test    eax, eax
0x14000ed5c  jns     short loc_14000EDA2
0x14000ed5e  mov     rcx, [rbp+arg_10]; void *
0x14000ed62  test    rcx, rcx
0x14000ed65  jz      short loc_14000ED74
0x14000ed67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ed6c  mov     [rbp+arg_10], 0
0x14000ed74  mov     rcx, cs:__imp_GetSystemDirectoryW
0x14000ed7b  lea     rdx, [rbp+arg_10]
0x14000ed7f  mov     r8, rdi
0x14000ed82  call    CommonUtil__UtilGetWindowsPath
0x14000ed87  mov     ebx, eax
0x14000ed89  test    eax, eax
0x14000ed8b  jns     short loc_14000EDA2
0x14000ed8d  mov     rcx, [rbp+arg_10]; void *
0x14000ed91  test    rcx, rcx
0x14000ed94  jz      short loc_14000ED9B
0x14000ed96  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ed9b  mov     eax, ebx
0x14000ed9d  jmp     loc_14000EEFB
0x14000eda2  mov     rbx, [rbp+arg_10]
0x14000eda6  mov     rcx, rbx; this
0x14000eda9  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x14000edae  test    eax, eax
0x14000edb0  jns     loc_14000EED9
0x14000edb6  mov     r8, rdi; unsigned __int16 *
0x14000edb9  mov     [rbp+arg_18], 0
0x14000edc1  lea     rdx, aForwardersWs; "forwarders\\%ws"
0x14000edc8  lea     rcx, [rbp+arg_18]; this
0x14000edcc  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x14000edd1  test    eax, eax
0x14000edd3  jns     short loc_14000EE1B
0x14000edd5  mov     rcx, [rbp+arg_18]; void *
0x14000edd9  test    rcx, rcx
0x14000eddc  jz      short loc_14000EDEB
0x14000edde  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ede3  mov     [rbp+arg_18], 0
0x14000edeb  mov     r8, rdi; unsigned __int16 *
0x14000edee  lea     rdx, aForwardersWs; "forwarders\\%ws"
0x14000edf5  lea     rcx, [rbp+arg_18]; this
0x14000edf9  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x14000edfe  mov     edi, eax
0x14000ee00  test    eax, eax
0x14000ee02  jns     short loc_14000EE1B
0x14000ee04  mov     rcx, [rbp+arg_18]; void *
0x14000ee08  test    rcx, rcx
0x14000ee0b  jz      loc_14000EEEC
0x14000ee11  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ee16  jmp     loc_14000EEEC
0x14000ee1b  mov     rdi, [rbp+arg_18]
0x14000ee1f  test    rbx, rbx
0x14000ee22  jz      short loc_14000EE34
0x14000ee24  mov     rcx, rbx; void *
0x14000ee27  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ee2c  mov     [rbp+arg_10], 0
0x14000ee34  mov     rcx, cs:__imp_GetSystemDirectoryW
0x14000ee3b  lea     rdx, [rbp+arg_10]
0x14000ee3f  mov     r8, rdi
0x14000ee42  call    CommonUtil__UtilGetWindowsPath
0x14000ee47  test    eax, eax
0x14000ee49  jns     short loc_14000EE90
0x14000ee4b  mov     rcx, [rbp+arg_10]; void *
0x14000ee4f  test    rcx, rcx
0x14000ee52  jz      short loc_14000EE61
0x14000ee54  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ee59  mov     [rbp+arg_10], 0
0x14000ee61  mov     rcx, cs:__imp_GetSystemDirectoryW
0x14000ee68  lea     rdx, [rbp+arg_10]
0x14000ee6c  mov     r8, rdi
0x14000ee6f  call    CommonUtil__UtilGetWindowsPath
0x14000ee74  mov     ebx, eax
0x14000ee76  test    eax, eax
0x14000ee78  jns     short loc_14000EE90
0x14000ee7a  test    rdi, rdi
0x14000ee7d  jz      loc_14000ED8D
0x14000ee83  mov     rcx, rdi; void *
0x14000ee86  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000ee8b  jmp     loc_14000ED8D
0x14000ee90  mov     rbx, [rbp+arg_10]
0x14000ee94  mov     rcx, rbx; this
0x14000ee97  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x14000ee9c  test    eax, eax
0x14000ee9e  jns     short loc_14000EECC
0x14000eea0  mov     rcx, rbx; this
0x14000eea3  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x14000eea8  mov     esi, eax
0x14000eeaa  test    eax, eax
0x14000eeac  jns     short loc_14000EECC
0x14000eeae  test    rdi, rdi
0x14000eeb1  jz      short loc_14000EEBB
0x14000eeb3  mov     rcx, rdi; void *
0x14000eeb6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000eebb  test    rbx, rbx
0x14000eebe  jz      short loc_14000EEC8
0x14000eec0  mov     rcx, rbx; void *
0x14000eec3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000eec8  mov     eax, esi
0x14000eeca  jmp     short loc_14000EEFB
0x14000eecc  test    rdi, rdi
0x14000eecf  jz      short loc_14000EED9
0x14000eed1  mov     rcx, rdi; void *
0x14000eed4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000eed9  mov     r8d, 8; unsigned __int16 *
0x14000eedf  mov     rdx, rbx; HINSTANCE *
0x14000eee2  mov     rcx, r14; this
0x14000eee5  call    ?UtilLoadLibraryEx@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEBGK@Z; CommonUtil::UtilLoadLibraryEx(HINSTANCE__ * *,ushort const *,ulong)
0x14000eeea  mov     edi, eax
0x14000eeec  test    rbx, rbx
0x14000eeef  jz      short loc_14000EEF9
0x14000eef1  mov     rcx, rbx; void *
0x14000eef4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000eef9  mov     eax, edi
0x14000eefb  mov     rbx, [rsp+20h+arg_0]
0x14000ef00  mov     rsi, [rsp+20h+arg_8]
0x14000ef05  add     rsp, 20h
0x14000ef09  pop     r14
0x14000ef0b  pop     rdi
0x14000ef0c  pop     rbp
0x14000ef0d  retn
```
