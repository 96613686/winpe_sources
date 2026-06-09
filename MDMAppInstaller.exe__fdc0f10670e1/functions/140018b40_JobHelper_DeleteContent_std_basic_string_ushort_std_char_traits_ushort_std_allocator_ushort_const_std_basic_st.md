# JobHelper::DeleteContent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140018b40`
- end: `0x140018d02`
- name: `?DeleteContent@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `450`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d470`
- `0x14000e6cc`
- `0x140018d08`

## callees

- `0x1400036ac`
- `0x1400055f8`
- `0x140006480`
- `0x140006604`
- `0x1400068c8`
- `0x14000740c`
- `0x14000775c`
- `0x140017fbc`
- `0x140018520`
- `0x140018b40`
- `0x140019750`
- `0x14001a8aa`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140018cb6`
- `KERNEL32!LeaveCriticalSection` at `0x140018cb6`
- `KERNEL32!EnterCriticalSection` at `0x140018bb5`
- `KERNEL32!EnterCriticalSection` at `0x140018bb5`
- `KERNEL32!DeleteFileW` at `0x140018c48`
- `KERNEL32!DeleteFileW` at `0x140018c48`

## string_xrefs

- `0x140018c6b`: `Failed to delete file %1 hr=0x%2!x!`

## pseudocode

```c
__int64 __fastcall JobHelper::DeleteContent(__int64 a1, __int64 a2)
{
  int JobRegPath; // ebx
  HKEY v5; // r8
  const unsigned __int16 *v6; // r9
  int RegSZValue; // eax
  __int64 v8; // rax
  const WCHAR *v9; // rcx
  HKEY v10; // rcx
  unsigned int Error; // eax
  LPCWSTR *v12; // rdx
  const unsigned __int16 *v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  struct _SECURITY_ATTRIBUTES *v18; // [rsp+20h] [rbp-E0h]
  unsigned int *v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v23; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v24[3]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v25; // [rsp+68h] [rbp-98h]
  BYTE Data[528]; // [rsp+70h] [rbp-90h] BYREF

  std::wstring::wstring(v24, &word_14001E5B4);
  v23 = 7;
  v22 = 0;
  LOWORD(lpFileName[0]) = 0;
  memset_0(Data, 0, 0x20Au);
  EnterCriticalSection(&JobHelper::m_critSec);
  JobRegPath = JobHelper::GetJobRegPath(a1, a2, v24);
  if ( JobRegPath >= 0 )
  {
    v6 = (const unsigned __int16 *)v24;
    if ( v25 >= 8 )
      v6 = v24[0];
    RegSZValue = ReadRegSZValue(Data, 0x105u, v5, v6, (const unsigned __int16 *)&stru_140026260, v19);
    JobRegPath = RegSZValue;
    if ( RegSZValue >= 0 )
    {
      v8 = std::char_traits<unsigned short>::length(Data);
      std::wstring::assign(lpFileName, Data, v8);
      if ( v22 )
      {
        v9 = (const WCHAR *)lpFileName;
        if ( v23 >= 8 )
          v9 = lpFileName[0];
        if ( !DeleteFileW(v9) )
        {
          Error = ResultFromLastError();
          v12 = lpFileName;
          if ( v23 >= 8 )
            v12 = (LPCWSTR *)lpFileName[0];
          LogWarn(L"Failed to delete file %1 hr=0x%2!x!", v12, Error);
        }
        v13 = (const unsigned __int16 *)v24;
        if ( v25 >= 8 )
          v13 = v24[0];
        v14 = WriteRegSZValue(v10, v13, (const unsigned __int16 *)&stru_140026260, &word_14001E5B4, v18, v20);
        JobRegPath = v14;
        if ( v14 < 0 )
          LogError(L"failed to set %1 ,0x%2!x!", &stru_140026260, (unsigned int)v14);
      }
    }
    else
    {
      LogError(L"failed to get %1 ,0x%2!x!", &stru_140026260, (unsigned int)RegSZValue);
    }
  }
  LeaveCriticalSection(&JobHelper::m_critSec);
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(lpFileName, v15, 0);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(v24, v16, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x140018b40  mov     [rsp-8+arg_10], rbx
0x140018b45  mov     [rsp-8+arg_18], rdi
0x140018b4a  push    rbp
0x140018b4b  lea     rbp, [rsp-190h]
0x140018b53  sub     rsp, 290h
0x140018b5a  mov     rax, cs:__security_cookie
0x140018b61  xor     rax, rsp
0x140018b64  mov     [rbp+190h+var_10], rax
0x140018b6b  mov     rdi, rdx
0x140018b6e  mov     rbx, rcx
0x140018b71  lea     rdx, word_14001E5B4
0x140018b78  lea     rcx, [rsp+290h+var_240]
0x140018b7d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140018b82  nop
0x140018b83  mov     [rsp+290h+var_248], 7
0x140018b8c  mov     [rsp+290h+var_250], 0
0x140018b95  xor     eax, eax
0x140018b97  mov     word ptr [rsp+290h+lpFileName], ax
0x140018b9c  xor     edx, edx; Val
0x140018b9e  mov     r8d, 20Ah; Size
0x140018ba4  lea     rcx, [rsp+290h+Data]; void *
0x140018ba9  call    memset_0
0x140018bae  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140018bb5  call    cs:__imp_EnterCriticalSection
0x140018bbb  lea     r8, [rsp+290h+var_240]
0x140018bc0  mov     rdx, rdi
0x140018bc3  mov     rcx, rbx
0x140018bc6  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x140018bcb  mov     ebx, eax
0x140018bcd  test    eax, eax
0x140018bcf  js      loc_140018CAF
0x140018bd5  lea     r9, [rsp+290h+var_240]
0x140018bda  cmp     [rsp+290h+var_228], 8
0x140018be0  cmovnb  r9, [rsp+290h+var_240]; unsigned __int16 *
0x140018be6  lea     rdi, stru_140026260
0x140018bed  mov     [rsp+290h+var_270], rdi; struct _SECURITY_ATTRIBUTES *
0x140018bf2  mov     edx, 105h; unsigned __int64
0x140018bf7  lea     rcx, [rsp+290h+Data]; lpData
0x140018bfc  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x140018c01  mov     ebx, eax
0x140018c03  test    eax, eax
0x140018c05  jns     short loc_140018C13
0x140018c07  lea     rcx, aFailedToGet10x; "failed to get %1 ,0x%2!x!"
0x140018c0e  jmp     loc_140018CA4
0x140018c13  lea     rcx, [rsp+290h+Data]
0x140018c18  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140018c1d  mov     r8, rax
0x140018c20  lea     rdx, [rsp+290h+Data]
0x140018c25  lea     rcx, [rsp+290h+lpFileName]
0x140018c2a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140018c2f  cmp     [rsp+290h+var_250], 0
0x140018c35  jz      short loc_140018CAF
0x140018c37  lea     rcx, [rsp+290h+lpFileName]
0x140018c3c  cmp     [rsp+290h+var_248], 8
0x140018c42  cmovnb  rcx, [rsp+290h+lpFileName]; lpFileName
0x140018c48  call    cs:__imp_DeleteFileW
0x140018c4e  test    eax, eax
0x140018c50  jnz     short loc_140018C77
0x140018c52  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140018c57  lea     rdx, [rsp+290h+lpFileName]
0x140018c5c  cmp     [rsp+290h+var_248], 8
0x140018c62  cmovnb  rdx, [rsp+290h+lpFileName]
0x140018c68  mov     r8d, eax
0x140018c6b  lea     rcx, aFailedToDelete_0; "Failed to delete file %1 hr=0x%2!x!"
0x140018c72  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x140018c77  lea     rdx, [rsp+290h+var_240]
0x140018c7c  cmp     [rsp+290h+var_228], 8
0x140018c82  cmovnb  rdx, [rsp+290h+var_240]; unsigned __int16 *
0x140018c88  lea     r9, word_14001E5B4; unsigned __int16 *
0x140018c8f  mov     r8, rdi; unsigned __int16 *
0x140018c92  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x140018c97  mov     ebx, eax
0x140018c99  test    eax, eax
0x140018c9b  jns     short loc_140018CAF
0x140018c9d  lea     rcx, aFailedToSet10x; "failed to set %1 ,0x%2!x!"
0x140018ca4  mov     r8d, eax
0x140018ca7  mov     rdx, rdi
0x140018caa  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140018caf  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140018cb6  call    cs:__imp_LeaveCriticalSection
0x140018cbc  nop
0x140018cbd  xor     r8d, r8d
0x140018cc0  mov     dl, 1
0x140018cc2  lea     rcx, [rsp+290h+lpFileName]
0x140018cc7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140018ccc  nop
0x140018ccd  xor     r8d, r8d
0x140018cd0  mov     dl, 1
0x140018cd2  lea     rcx, [rsp+290h+var_240]
0x140018cd7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140018cdc  mov     eax, ebx
0x140018cde  mov     rcx, [rbp+190h+var_10]
0x140018ce5  xor     rcx, rsp; StackCookie
0x140018ce8  call    __security_check_cookie
0x140018ced  lea     r11, [rsp+290h+var_s0]
0x140018cf5  mov     rbx, [r11+20h]
0x140018cf9  mov     rdi, [r11+28h]
0x140018cfd  mov     rsp, r11
0x140018d00  pop     rbp
0x140018d01  retn
```
