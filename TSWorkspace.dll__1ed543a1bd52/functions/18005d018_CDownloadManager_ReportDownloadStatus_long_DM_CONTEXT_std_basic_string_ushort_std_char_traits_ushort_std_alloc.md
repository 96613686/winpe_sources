# CDownloadManager::ReportDownloadStatus(long,_DM_CONTEXT *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18005d018`
- end: `0x18005d3b7`
- name: `?ReportDownloadStatus@CDownloadManager@@IEAAXJPEAU_DM_CONTEXT@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `927`
- prototype: `void __fastcall(CDownloadManager *this, int, __int64, void *, void *)`
- caller_count: `9`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180059c40`
- `0x18005a284`
- `0x18005aaa0`
- `0x18005ab90`
- `0x18005af00`
- `0x18005b420`
- `0x18005b590`
- `0x18005bc40`
- `0x18005bd30`

## callees

- `0x180003108`
- `0x1800044bf`
- `0x180004970`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ec54`
- `0x18000ec94`
- `0x180058f88`
- `0x18005d018`
- `0x18005d3c0`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18005d1eb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18005d1eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d13d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d2e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d13d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d1a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d2e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d254`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d254`
- `KERNEL32!DeleteFileW` at `0x18005d2be`
- `KERNEL32!DeleteFileW` at `0x18005d2be`
- `WINHTTP!WinHttpQueryOption` at `0x18005d135`
- `WINHTTP!WinHttpQueryOption` at `0x18005d185`
- `WINHTTP!WinHttpQueryOption` at `0x18005d135`
- `WINHTTP!WinHttpQueryOption` at `0x18005d185`

## pseudocode

```c
void __fastcall CDownloadManager::ReportDownloadStatus(CDownloadManager *this, int a2, __int64 a3, void *a4, void *a5)
{
  void *v5; // rbx
  unsigned int v9; // r14d
  unsigned int v10; // edx
  __int64 v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rdx
  void *v14; // rcx
  BOOL v15; // ebx
  DWORD LastError; // eax
  DWORD v17; // r14d
  void *v18; // r14
  DWORD v19; // ebx
  unsigned int v20; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v22; // rcx
  DWORD v23; // ebx
  unsigned int v24; // eax
  const WCHAR *v25; // rax
  DWORD v26; // ebx
  unsigned int v27; // eax
  __int64 v28; // rcx
  DWORD dwBufferLength; // [rsp+40h] [rbp-41h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-3Dh]
  void *v31; // [rsp+48h] [rbp-39h]
  __int64 v32; // [rsp+50h] [rbp-31h]
  void *v33; // [rsp+58h] [rbp-29h]
  void *v34; // [rsp+60h] [rbp-21h]
  _BYTE v35[32]; // [rsp+68h] [rbp-19h] BYREF

  v32 = -2;
  v5 = a4;
  v31 = a4;
  v33 = a4;
  v34 = a5;
  v9 = 0;
  v30 = 0;
  std::wstring::wstring(v35);
  v11 = *((_QWORD *)this + 258);
  if ( v11 )
  {
    if ( a3 == v11 )
    {
      v14 = *(void **)(a3 + 40);
      if ( v14 )
      {
        dwBufferLength = 0;
        v15 = WinHttpQueryOption(v14, 0x22u, 0, &dwBufferLength);
        LastError = GetLastError();
        v17 = LastError;
        if ( v15 || LastError != 122 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              112,
              &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
              CurrentThreadActivityIdPrefix,
              v17);
          }
        }
        else
        {
          v18 = operator new[](dwBufferLength, (const struct std::nothrow_t *)&std::nothrow);
          memset_0(v18, 0, dwBufferLength);
          if ( !WinHttpQueryOption(*(HINTERNET *)(a3 + 40), 0x22u, v18, &dwBufferLength)
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = GetLastError();
            v20 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              111,
              &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
              v20,
              v19);
          }
          if ( v18 )
          {
            std::wstring::assign(v35, v18);
            operator delete[](v18);
            dwBufferLength = 0;
          }
        }
        CDownloadManager::RequestSafeShutdown(this);
        v9 = v30;
      }
      v22 = *(void **)(a3 + 112);
      if ( v22 )
      {
        if ( !CloseHandle(v22)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v23 = GetLastError();
          v24 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            113,
            &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v24,
            v23);
        }
        *(_QWORD *)(a3 + 112) = 0;
        if ( a2 < 0 )
        {
          v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
          if ( !DeleteFileW(v25)
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v26 = GetLastError();
            v27 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              114,
              &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
              v27,
              v26);
          }
        }
      }
      if ( a2 == -2147012721 )
      {
        v9 = *(_DWORD *)(a3 + 32);
      }
      else if ( a2 == -2147220987 || a2 == -2147012868 )
      {
        v9 = *(_DWORD *)(a3 + 156);
      }
      _DM_CONTEXT::`scalar deleting destructor'((_DM_CONTEXT *)a3, v10);
      *((_QWORD *)this + 258) = 0;
      v5 = v31;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 110;
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 109;
LABEL_6:
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v12);
  }
  v28 = *((_QWORD *)this + 15);
  if ( v28 )
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, void *, void *, _BYTE *))(*(_QWORD *)v28 + 24LL))(
      v28,
      (unsigned int)a2,
      v9,
      v5,
      a5,
      v35);
  std::wstring::~wstring(v35);
  std::wstring::~wstring(v5);
  std::wstring::~wstring(a5);
}

```

## disassembly

```asm
0x18005d018  push    rbp
0x18005d01a  push    rbx
0x18005d01b  push    rsi
0x18005d01c  push    rdi
0x18005d01d  push    r12
0x18005d01f  push    r13
0x18005d021  push    r14
0x18005d023  push    r15
0x18005d025  lea     rbp, [rsp-17h]
0x18005d02a  sub     rsp, 98h
0x18005d031  mov     [rbp+4Fh+var_80], 0FFFFFFFFFFFFFFFEh
0x18005d039  mov     rax, cs:__security_cookie
0x18005d040  xor     rax, rsp
0x18005d043  mov     [rbp+4Fh+var_48], rax
0x18005d047  mov     rbx, r9
0x18005d04a  mov     [rbp+4Fh+var_88], rbx
0x18005d04e  mov     rsi, r8
0x18005d051  mov     r15d, edx
0x18005d054  mov     r13, rcx
0x18005d057  mov     [rbp+4Fh+var_78], rbx
0x18005d05b  mov     r12, [rbp+4Fh+arg_20]
0x18005d05f  mov     [rbp+4Fh+var_70], r12
0x18005d063  xor     r14d, r14d
0x18005d066  mov     [rbp+4Fh+var_8C], r14d
0x18005d06a  lea     rcx, [rbp+4Fh+var_68]
0x18005d06e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005d073  nop
0x18005d074  mov     rax, [r13+810h]
0x18005d07b  test    rax, rax
0x18005d07e  jnz     short loc_18005D0D3
0x18005d080  lea     rdi, WPP_GLOBAL_Control
0x18005d087  mov     rax, cs:WPP_GLOBAL_Control
0x18005d08e  cmp     rax, rdi
0x18005d091  jz      loc_18005D34F
0x18005d097  test    byte ptr [rax+1Ch], 1
0x18005d09b  jz      loc_18005D34F
0x18005d0a1  cmp     byte ptr [rax+19h], 2
0x18005d0a5  jb      loc_18005D34F
0x18005d0ab  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d0b0  lea     edx, [r14+6Dh]
0x18005d0b4  mov     r9d, eax
0x18005d0b7  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d0be  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d0c5  mov     rcx, [rcx+10h]
0x18005d0c9  call    WPP_SF_D
0x18005d0ce  jmp     loc_18005D34F
0x18005d0d3  cmp     rsi, rax
0x18005d0d6  jz      short loc_18005D10F
0x18005d0d8  lea     rdi, WPP_GLOBAL_Control
0x18005d0df  mov     rax, cs:WPP_GLOBAL_Control
0x18005d0e6  cmp     rax, rdi
0x18005d0e9  jz      loc_18005D34F
0x18005d0ef  test    byte ptr [rax+1Ch], 1
0x18005d0f3  jz      loc_18005D34F
0x18005d0f9  cmp     byte ptr [rax+19h], 2
0x18005d0fd  jb      loc_18005D34F
0x18005d103  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d108  mov     edx, 6Eh ; 'n'
0x18005d10d  jmp     short loc_18005D0B4
0x18005d10f  mov     rcx, [rsi+28h]; hInternet
0x18005d113  lea     rdi, WPP_GLOBAL_Control
0x18005d11a  test    rcx, rcx
0x18005d11d  jz      loc_18005D247
0x18005d123  mov     [rbp+4Fh+dwBufferLength], 0
0x18005d12a  lea     r9, [rbp+4Fh+dwBufferLength]; lpdwBufferLength
0x18005d12e  xor     r8d, r8d; lpBuffer
0x18005d131  lea     edx, [r8+22h]; dwOption
0x18005d135  call    cs:__imp_WinHttpQueryOption
0x18005d13b  mov     ebx, eax
0x18005d13d  call    cs:__imp_GetLastError
0x18005d143  mov     r14d, eax
0x18005d146  test    ebx, ebx
0x18005d148  jnz     loc_18005D1FA
0x18005d14e  cmp     eax, 7Ah ; 'z'
0x18005d151  jnz     loc_18005D1FA
0x18005d157  mov     ecx, [rbp+4Fh+dwBufferLength]; unsigned __int64
0x18005d15a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005d161  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005d166  mov     r14, rax
0x18005d169  mov     r8d, [rbp+4Fh+dwBufferLength]; Size
0x18005d16d  xor     edx, edx; Val
0x18005d16f  mov     rcx, rax; void *
0x18005d172  call    memset_0
0x18005d177  lea     r9, [rbp+4Fh+dwBufferLength]; lpdwBufferLength
0x18005d17b  mov     r8, r14; lpBuffer
0x18005d17e  lea     edx, [rbx+22h]; dwOption
0x18005d181  mov     rcx, [rsi+28h]; hInternet
0x18005d185  call    cs:__imp_WinHttpQueryOption
0x18005d18b  test    eax, eax
0x18005d18d  jnz     short loc_18005D1D7
0x18005d18f  mov     rax, cs:WPP_GLOBAL_Control
0x18005d196  cmp     rax, rdi
0x18005d199  jz      short loc_18005D1D7
0x18005d19b  test    byte ptr [rax+1Ch], 1
0x18005d19f  jz      short loc_18005D1D7
0x18005d1a1  cmp     byte ptr [rax+19h], 2
0x18005d1a5  jb      short loc_18005D1D7
0x18005d1a7  call    cs:__imp_GetLastError
0x18005d1ad  mov     ebx, eax
0x18005d1af  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d1b4  mov     edx, 6Fh ; 'o'
0x18005d1b9  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18005d1bd  mov     r9d, eax
0x18005d1c0  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d1c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d1ce  mov     rcx, [rcx+10h]
0x18005d1d2  call    WPP_SF_Dd
0x18005d1d7  test    r14, r14
0x18005d1da  jz      short loc_18005D23B
0x18005d1dc  mov     rdx, r14
0x18005d1df  lea     rcx, [rbp+4Fh+var_68]
0x18005d1e3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18005d1e8  mov     rcx, r14
0x18005d1eb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18005d1f1  mov     [rbp+4Fh+dwBufferLength], 0
0x18005d1f8  jmp     short loc_18005D23B
0x18005d1fa  mov     rax, cs:WPP_GLOBAL_Control
0x18005d201  cmp     rax, rdi
0x18005d204  jz      short loc_18005D23B
0x18005d206  test    byte ptr [rax+1Ch], 1
0x18005d20a  jz      short loc_18005D23B
0x18005d20c  cmp     byte ptr [rax+19h], 2
0x18005d210  jb      short loc_18005D23B
0x18005d212  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d217  mov     edx, 70h ; 'p'
0x18005d21c  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x18005d221  mov     r9d, eax
0x18005d224  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d22b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d232  mov     rcx, [rcx+10h]
0x18005d236  call    WPP_SF_Dd
0x18005d23b  mov     rcx, r13; this
0x18005d23e  call    ?RequestSafeShutdown@CDownloadManager@@IEAAJXZ; CDownloadManager::RequestSafeShutdown(void)
0x18005d243  mov     r14d, [rbp+4Fh+var_8C]
0x18005d247  mov     rcx, [rsi+70h]; hObject
0x18005d24b  test    rcx, rcx
0x18005d24e  jz      loc_18005D310
0x18005d254  call    cs:__imp_CloseHandle
0x18005d25a  test    eax, eax
0x18005d25c  jnz     short loc_18005D2A6
0x18005d25e  mov     rax, cs:WPP_GLOBAL_Control
0x18005d265  cmp     rax, rdi
0x18005d268  jz      short loc_18005D2A6
0x18005d26a  test    byte ptr [rax+1Ch], 1
0x18005d26e  jz      short loc_18005D2A6
0x18005d270  cmp     byte ptr [rax+19h], 2
0x18005d274  jb      short loc_18005D2A6
0x18005d276  call    cs:__imp_GetLastError
0x18005d27c  mov     ebx, eax
0x18005d27e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d283  mov     edx, 71h ; 'q'
0x18005d288  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18005d28c  mov     r9d, eax
0x18005d28f  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d296  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d29d  mov     rcx, [rcx+10h]
0x18005d2a1  call    WPP_SF_Dd
0x18005d2a6  mov     qword ptr [rsi+70h], 0
0x18005d2ae  test    r15d, r15d
0x18005d2b1  jns     short loc_18005D310
0x18005d2b3  mov     rcx, r12
0x18005d2b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005d2bb  mov     rcx, rax; lpFileName
0x18005d2be  call    cs:__imp_DeleteFileW
0x18005d2c4  test    eax, eax
0x18005d2c6  jnz     short loc_18005D310
0x18005d2c8  mov     rax, cs:WPP_GLOBAL_Control
0x18005d2cf  cmp     rax, rdi
0x18005d2d2  jz      short loc_18005D310
0x18005d2d4  test    byte ptr [rax+1Ch], 1
0x18005d2d8  jz      short loc_18005D310
0x18005d2da  cmp     byte ptr [rax+19h], 2
0x18005d2de  jb      short loc_18005D310
0x18005d2e0  call    cs:__imp_GetLastError
0x18005d2e6  mov     ebx, eax
0x18005d2e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d2ed  mov     edx, 72h ; 'r'
0x18005d2f2  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18005d2f6  mov     r9d, eax
0x18005d2f9  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d300  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d307  mov     rcx, [rcx+10h]
0x18005d30b  call    WPP_SF_Dd
0x18005d310  cmp     r15d, 80072F8Fh
0x18005d317  jnz     short loc_18005D31F
0x18005d319  mov     r14d, [rsi+20h]
0x18005d31d  jmp     short loc_18005D338
0x18005d31f  cmp     r15d, 80040205h
0x18005d326  jz      short loc_18005D331
0x18005d328  cmp     r15d, 80072EFCh
0x18005d32f  jnz     short loc_18005D338
0x18005d331  mov     r14d, [rsi+9Ch]
0x18005d338  mov     rcx, rsi; this
0x18005d33b  call    ??_G_DM_CONTEXT@@QEAAPEAXI@Z; _DM_CONTEXT::`scalar deleting destructor'(uint)
0x18005d340  mov     qword ptr [r13+810h], 0
0x18005d34b  mov     rbx, [rbp+4Fh+var_88]
0x18005d34f  mov     rcx, [r13+78h]
0x18005d353  test    rcx, rcx
0x18005d356  jz      short loc_18005D37C
0x18005d358  mov     rax, [rcx]
0x18005d35b  lea     r8, [rbp+4Fh+var_68]
0x18005d35f  mov     [rsp+0D0h+var_A8], r8
0x18005d364  mov     [rsp+0D0h+var_B0], r12
0x18005d369  mov     r9, rbx
0x18005d36c  mov     r8d, r14d
0x18005d36f  mov     edx, r15d
0x18005d372  mov     rax, [rax+18h]
0x18005d376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d37b  nop
0x18005d37c  lea     rcx, [rbp+4Fh+var_68]; void *
0x18005d380  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d385  nop
0x18005d386  mov     rcx, rbx; void *
0x18005d389  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d38e  nop
0x18005d38f  mov     rcx, r12; void *
0x18005d392  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005d397  mov     rcx, [rbp+4Fh+var_48]
0x18005d39b  xor     rcx, rsp; StackCookie
0x18005d39e  call    __security_check_cookie
0x18005d3a3  add     rsp, 98h
0x18005d3aa  pop     r15
0x18005d3ac  pop     r14
0x18005d3ae  pop     r13
0x18005d3b0  pop     r12
0x18005d3b2  pop     rdi
0x18005d3b3  pop     rsi
0x18005d3b4  pop     rbx
0x18005d3b5  pop     rbp
0x18005d3b6  retn
```
