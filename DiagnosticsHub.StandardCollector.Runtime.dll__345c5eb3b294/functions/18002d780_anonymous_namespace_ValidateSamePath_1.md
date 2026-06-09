# _anonymous_namespace_::ValidateSamePath_1

- ea: `0x18002d780`
- end: `0x18002d9a1`
- name: `_anonymous_namespace_::ValidateSamePath_1`
- size: `545`
- prototype: `__int64 __fastcall(wchar_t *String1, HANDLE hFile)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x18002da4c`

## callees

- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x18000856c`
- `0x18000a17c`
- `0x18002d698`
- `0x18002d780`
- `0x18002f17c`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002d7a3`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002d7f4`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002d7a3`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002d7f4`
- `KERNEL32!GetLongPathNameW` at `0x18002d8c5`
- `KERNEL32!GetLongPathNameW` at `0x18002d910`
- `KERNEL32!GetLongPathNameW` at `0x18002d8c5`
- `KERNEL32!GetLongPathNameW` at `0x18002d910`
- `KERNEL32!GetLastError` at `0x18002d7af`
- `KERNEL32!GetLastError` at `0x18002d801`
- `KERNEL32!GetLastError` at `0x18002d91a`
- `KERNEL32!GetLastError` at `0x18002d7af`
- `KERNEL32!GetLastError` at `0x18002d801`
- `KERNEL32!GetLastError` at `0x18002d91a`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002d848`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002d892`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002d848`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002d892`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::ValidateSamePath_1(wchar_t *String1, HANDLE hFile)
{
  DWORD FinalPathNameByHandleW; // eax
  signed int v5; // ecx
  __int64 result; // rax
  DWORD v7; // eax
  signed int v8; // eax
  unsigned int v9; // edi
  struct ATL::IAtlStringMgr *Instance; // rax
  WCHAR *v11; // rbx
  DWORD LongPathNameW; // eax
  signed int LastError; // eax
  LPCWSTR lpszShortPath; // [rsp+20h] [rbp-40h] BYREF
  LPWSTR lpszFilePath[2]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v16; // [rsp+38h] [rbp-28h]
  LPWSTR lpszLongPath[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v18; // [rsp+50h] [rbp-10h]

  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 0);
  if ( FinalPathNameByHandleW )
  {
    *(_OWORD *)lpszFilePath = 0;
    v16 = 0;
    std::vector<unsigned short>::vector<unsigned short>(lpszFilePath, FinalPathNameByHandleW);
    v7 = GetFinalPathNameByHandleW(hFile, lpszFilePath[0], lpszFilePath[1] - lpszFilePath[0], 0);
    if ( v7 )
    {
      if ( (unsigned __int64)v7 + 1 <= lpszFilePath[1] - lpszFilePath[0] )
      {
        if ( !wcsncmp(lpszFilePath[0], L"\\\\?\\UNC", 7u) )
        {
          v9 = -2147024891;
        }
        else
        {
          Instance = ATL::CAtlStringMgr::GetInstance();
          if ( !Instance )
            ATL::AtlThrowImpl(-2147467259);
          lpszShortPath = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                                  + 24);
          if ( !wcsncmp(String1, L"\\\\?\\", 4u) )
            ATL::CSimpleStringT<unsigned short,0>::Append(&lpszShortPath, String1);
          else
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
              &lpszShortPath,
              L"\\\\?\\%s",
              String1);
          v11 = (WCHAR *)lpszShortPath;
          LongPathNameW = GetLongPathNameW(lpszShortPath, 0, 0);
          if ( LongPathNameW )
          {
            *(_OWORD *)lpszLongPath = 0;
            v18 = 0;
            std::vector<unsigned short>::vector<unsigned short>(lpszLongPath, LongPathNameW);
            if ( GetLongPathNameW(v11, lpszLongPath[0], lpszLongPath[1] - lpszLongPath[0]) )
            {
              if ( (unsigned int)anonymous_namespace_::ValidateSamePath_0(lpszFilePath[0], lpszLongPath[0]) )
                v9 = -518979566;
              else
                v9 = 0;
            }
            else
            {
              LastError = GetLastError();
              v9 = (unsigned __int16)LastError | 0x80070000;
              if ( LastError <= 0 )
                v9 = LastError;
            }
            std::vector<unsigned short>::~vector<unsigned short>(lpszLongPath);
          }
          else
          {
            v9 = (unsigned int)anonymous_namespace_::ValidateSamePath_0(lpszFilePath[0], v11) != 0 ? 0xE1110012 : 0;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 - 2, 0xFFFFFFFF) <= 1 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 - 3) + 8LL))(*((_QWORD *)v11 - 3));
          }
        }
      }
      else
      {
        v9 = -2147418113;
      }
    }
    else
    {
      v8 = GetLastError();
      v9 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        v9 = v8;
    }
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    return v9;
  }
  else
  {
    v5 = GetLastError();
    result = (unsigned __int16)v5 | 0x80070000;
    if ( v5 <= 0 )
      return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002d780  mov     [rsp-8+arg_10], rbx
0x18002d785  mov     [rsp-8+arg_18], rdi
0x18002d78a  push    rbp
0x18002d78b  mov     rbp, rsp
0x18002d78e  sub     rsp, 60h
0x18002d792  mov     rdi, rdx
0x18002d795  mov     rbx, rcx
0x18002d798  xor     r9d, r9d; dwFlags
0x18002d79b  xor     r8d, r8d; cchFilePath
0x18002d79e  xor     edx, edx; lpszFilePath
0x18002d7a0  mov     rcx, rdi; hFile
0x18002d7a3  call    cs:__imp_GetFinalPathNameByHandleW
0x18002d7a9  mov     edx, eax
0x18002d7ab  test    eax, eax
0x18002d7ad  jnz     short loc_18002D7C9
0x18002d7af  call    cs:__imp_GetLastError
0x18002d7b5  mov     ecx, eax
0x18002d7b7  movzx   eax, ax
0x18002d7ba  or      eax, 80070000h
0x18002d7bf  test    ecx, ecx
0x18002d7c1  cmovle  eax, ecx
0x18002d7c4  jmp     loc_18002D984
0x18002d7c9  xorps   xmm0, xmm0
0x18002d7cc  xor     eax, eax
0x18002d7ce  movups  xmmword ptr [rbp+lpszFilePath], xmm0
0x18002d7d2  mov     [rbp+var_28], rax
0x18002d7d6  lea     rcx, [rbp+lpszFilePath]
0x18002d7da  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18002d7df  nop
0x18002d7e0  mov     rdx, [rbp+lpszFilePath]; lpszFilePath
0x18002d7e4  mov     r8, [rbp+lpszFilePath+8]
0x18002d7e8  sub     r8, rdx
0x18002d7eb  sar     r8, 1; cchFilePath
0x18002d7ee  xor     r9d, r9d; dwFlags
0x18002d7f1  mov     rcx, rdi; hFile
0x18002d7f4  call    cs:__imp_GetFinalPathNameByHandleW
0x18002d7fa  mov     eax, eax
0x18002d7fc  test    rax, rax
0x18002d7ff  jnz     short loc_18002D81A
0x18002d801  call    cs:__imp_GetLastError
0x18002d807  movzx   edi, ax
0x18002d80a  or      edi, 80070000h
0x18002d810  test    eax, eax
0x18002d812  cmovle  edi, eax
0x18002d815  jmp     loc_18002D979
0x18002d81a  mov     rcx, [rbp+lpszFilePath+8]
0x18002d81e  sub     rcx, [rbp+lpszFilePath]
0x18002d822  sar     rcx, 1
0x18002d825  inc     rax
0x18002d828  cmp     rax, rcx
0x18002d82b  jbe     short loc_18002D837
0x18002d82d  mov     edi, 8000FFFFh
0x18002d832  jmp     loc_18002D979
0x18002d837  mov     r8d, 7; MaxCount
0x18002d83d  lea     rdx, aUnc; "\\\\?\\UNC"
0x18002d844  mov     rcx, [rbp+lpszFilePath]; String1
0x18002d848  call    cs:__imp_wcsncmp
0x18002d84e  test    eax, eax
0x18002d850  jnz     short loc_18002D85C
0x18002d852  mov     edi, 80070005h
0x18002d857  jmp     loc_18002D979
0x18002d85c  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18002d861  mov     rcx, rax
0x18002d864  test    rax, rax
0x18002d867  jz      loc_18002D996
0x18002d86d  mov     rax, [rax]
0x18002d870  mov     rax, [rax+18h]
0x18002d874  call    cs:__guard_dispatch_icall_fptr
0x18002d87a  add     rax, 18h
0x18002d87e  mov     [rbp+lpszShortPath], rax
0x18002d882  mov     r8d, 4; MaxCount
0x18002d888  lea     rdx, asc_180056FA0; "\\\\?\\"
0x18002d88f  mov     rcx, rbx; String1
0x18002d892  call    cs:__imp_wcsncmp
0x18002d898  lea     rcx, [rbp+lpszShortPath]
0x18002d89c  test    eax, eax
0x18002d89e  jz      short loc_18002D8B1
0x18002d8a0  mov     r8, rbx
0x18002d8a3  lea     rdx, aS; "\\\\?\\%s"
0x18002d8aa  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18002d8af  jmp     short loc_18002D8B9
0x18002d8b1  mov     rdx, rbx
0x18002d8b4  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18002d8b9  xor     r8d, r8d; cchBuffer
0x18002d8bc  xor     edx, edx; lpszLongPath
0x18002d8be  mov     rbx, [rbp+lpszShortPath]
0x18002d8c2  mov     rcx, rbx; lpszShortPath
0x18002d8c5  call    cs:__imp_GetLongPathNameW
0x18002d8cb  test    eax, eax
0x18002d8cd  jnz     short loc_18002D8E7
0x18002d8cf  mov     rdx, rbx; wchar_t *
0x18002d8d2  mov     rcx, [rbp+lpszFilePath]; String1
0x18002d8d6  call    _anonymous_namespace___ValidateSamePath_0
0x18002d8db  neg     eax
0x18002d8dd  sbb     edi, edi
0x18002d8df  and     edi, 0E1110012h
0x18002d8e5  jmp     short loc_18002D954
0x18002d8e7  xorps   xmm0, xmm0
0x18002d8ea  xor     ecx, ecx
0x18002d8ec  movups  xmmword ptr [rbp+lpszLongPath], xmm0
0x18002d8f0  mov     [rbp+var_10], rcx
0x18002d8f4  mov     edx, eax
0x18002d8f6  lea     rcx, [rbp+lpszLongPath]
0x18002d8fa  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18002d8ff  mov     rdx, [rbp+lpszLongPath]; lpszLongPath
0x18002d903  mov     r8, [rbp+lpszLongPath+8]
0x18002d907  sub     r8, rdx
0x18002d90a  sar     r8, 1; cchBuffer
0x18002d90d  mov     rcx, rbx; lpszShortPath
0x18002d910  call    cs:__imp_GetLongPathNameW
0x18002d916  test    eax, eax
0x18002d918  jnz     short loc_18002D930
0x18002d91a  call    cs:__imp_GetLastError
0x18002d920  movzx   edi, ax
0x18002d923  or      edi, 80070000h
0x18002d929  test    eax, eax
0x18002d92b  cmovle  edi, eax
0x18002d92e  jmp     short loc_18002D94A
0x18002d930  mov     rdx, [rbp+lpszLongPath]; wchar_t *
0x18002d934  mov     rcx, [rbp+lpszFilePath]; String1
0x18002d938  call    _anonymous_namespace___ValidateSamePath_0
0x18002d93d  test    eax, eax
0x18002d93f  jz      short loc_18002D948
0x18002d941  mov     edi, 0E1110012h
0x18002d946  jmp     short loc_18002D94A
0x18002d948  xor     edi, edi
0x18002d94a  lea     rcx, [rbp+lpszLongPath]
0x18002d94e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002d953  nop
0x18002d954  lea     rdx, [rbx-18h]
0x18002d958  or      eax, 0FFFFFFFFh
0x18002d95b  lock xadd [rdx+10h], eax
0x18002d960  sub     eax, 1
0x18002d963  jg      short loc_18002D979
0x18002d965  lfence
0x18002d968  mov     rcx, [rdx]
0x18002d96b  mov     r8, [rcx]
0x18002d96e  mov     rax, [r8+8]
0x18002d972  call    cs:__guard_dispatch_icall_fptr
0x18002d978  nop
0x18002d979  lea     rcx, [rbp+lpszFilePath]
0x18002d97d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002d982  mov     eax, edi
0x18002d984  lea     r11, [rsp+60h+var_s0]
0x18002d989  mov     rbx, [r11+20h]
0x18002d98d  mov     rdi, [r11+28h]
0x18002d991  mov     rsp, r11
0x18002d994  pop     rbp
0x18002d995  retn
0x18002d996  mov     ecx, 80004005h; int
0x18002d99b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
