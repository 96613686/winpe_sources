# Microsoft::EventTrace::GetAvailableProfileSources(std::vector<Microsoft::EventTrace::ProfileSourceDetails,std::allocator<Microsoft::EventTrace::ProfileSourceDetails>> &)

- ea: `0x1800491d8`
- end: `0x1800494f3`
- name: `?GetAvailableProfileSources@EventTrace@Microsoft@@YAJAEAV?$vector@UProfileSourceDetails@EventTrace@Microsoft@@V?$allocator@UProfileSourceDetails@EventTrace@Microsoft@@@std@@@std@@@Z`
- size: `795`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e7b0`
- `0x18001e940`
- `0x18001eaf0`

## callees

- `0x180002604`
- `0x1800491d8`
- `0x1800495bc`
- `0x180049b50`
- `0x180049bac`
- `0x180049c18`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180049279`
- `KERNEL32!LoadLibraryExW` at `0x180049297`
- `KERNEL32!LoadLibraryExW` at `0x180049279`
- `KERNEL32!LoadLibraryExW` at `0x180049297`
- `KERNEL32!GetLastError` at `0x1800492c5`
- `KERNEL32!GetLastError` at `0x1800492c5`
- `KERNEL32!GetProcAddress` at `0x1800492b3`
- `KERNEL32!GetProcAddress` at `0x1800492b3`
- `OLEAUT32!__imp_SysAllocString` at `0x180049412`
- `OLEAUT32!__imp_SysAllocString` at `0x180049412`
- `OLEAUT32!__imp_SysFreeString` at `0x180049409`
- `OLEAUT32!__imp_SysFreeString` at `0x180049485`
- `OLEAUT32!__imp_SysFreeString` at `0x1800494a6`
- `OLEAUT32!__imp_SysFreeString` at `0x180049409`
- `OLEAUT32!__imp_SysFreeString` at `0x180049485`
- `OLEAUT32!__imp_SysFreeString` at `0x1800494a6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004934b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180049392`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180049496`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004934b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180049392`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180049496`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180049336`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180049336`

## string_xrefs

- `0x180049272`: `Sechost.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::EventTrace::GetAvailableProfileSources(__int64 a1)
{
  HMODULE Library; // rax
  int v3; // ecx
  __int64 result; // rax
  OLECHAR *v5; // rax
  OLECHAR *v6; // rbx
  OLECHAR *v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  const OLECHAR *v10; // r14
  unsigned int v11; // r12d
  OLECHAR *v12; // rax
  int v13; // r8d
  unsigned int v14; // r9d
  unsigned int v15; // r10d
  __int64 v16; // rdx
  OLECHAR *v17; // rcx
  __int64 v18; // rdi
  BSTR bstrString; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-50h]
  __int64 v21; // [rsp+3Ch] [rbp-4Ch]
  unsigned int v22; // [rsp+44h] [rbp-44h]
  OLECHAR *v23; // [rsp+48h] [rbp-40h]
  size_t Size; // [rsp+50h] [rbp-38h]
  unsigned int v25; // [rsp+58h] [rbp-30h] BYREF
  int v26; // [rsp+5Ch] [rbp-2Ch]

  if ( dword_180077B30 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180077B30);
    if ( dword_180077B30 == -1 )
    {
      qword_180077B44 = 0;
      dword_180077B4C = 0;
      qword_180077B38 = 0;
      dword_180077B40 = 0;
      Library = LoadLibraryExW(L"Sechost.dll", 0, 0x800u);
      *(__int64 *)((char *)&qword_180077B44 + 4) = (__int64)Library;
      if ( !Library
        && (Library = LoadLibraryExW(L"api-ms-win-eventing-controller-l1-1-0", 0, 0x800u),
            (*(__int64 *)((char *)&qword_180077B44 + 4) = (__int64)Library) == 0)
        || (qword_180077B38 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                Library,
                                                                                "TraceQueryInformation")) == 0 )
      {
        dword_180077B40 = GetLastError();
      }
      Init_thread_footer(&dword_180077B30);
    }
  }
  v3 = dword_180077B40;
  if ( !dword_180077B40 && qword_180077B38 && (v3 = qword_180077B38(0, 7, 0), v3 == 24) )
  {
    if ( !(_DWORD)Size )
      return 0;
    v5 = (OLECHAR *)malloc((unsigned int)Size);
    v6 = v5;
    v23 = v5;
    if ( !v5 )
    {
      v7 = 0;
      goto LABEL_15;
    }
    v8 = qword_180077B38(0, 7, v5);
    if ( !v8 )
    {
      v10 = v6;
      do
      {
        v25 = *((_DWORD *)v10 + 1);
        v26 = 0;
        v8 = qword_180077B38(0, 5, &v25);
        if ( v8 )
          goto LABEL_17;
        bstrString = 0;
        v21 = 0;
        v22 = 0;
        v11 = *((_DWORD *)v10 + 1);
        v20 = v11;
        v12 = 0;
        if ( v10 != (const OLECHAR *)-24LL )
        {
          SysFreeString(0);
          v12 = SysAllocString(v10 + 12);
          bstrString = v12;
          if ( !v12 )
            ATL::AtlThrowImpl(-2147024882);
        }
        v13 = v26;
        LODWORD(v21) = v26;
        v14 = *((_DWORD *)v10 + 2);
        HIDWORD(v21) = v14;
        v15 = *((_DWORD *)v10 + 3);
        v22 = v15;
        v16 = *(_QWORD *)(a1 + 8);
        if ( v16 == *(_QWORD *)(a1 + 16) )
        {
          try
          {
            std::vector<Microsoft::EventTrace::ProfileSourceDetails>::_Emplace_reallocate<Microsoft::EventTrace::ProfileSourceDetails>(
              a1,
              v16,
              &bstrString);
            v17 = bstrString;
          }
          catch ( std::bad_alloc )
          {
            SysFreeString(bstrString);
            v7 = v23;
LABEL_15:
            free(v7);
            return 2147942414LL;
          }
        }
        else
        {
          *(_QWORD *)v16 = v12;
          v17 = 0;
          bstrString = 0;
          *(_DWORD *)(v16 + 8) = v11;
          *(_DWORD *)(v16 + 12) = v13;
          *(_DWORD *)(v16 + 16) = v14;
          *(_DWORD *)(v16 + 20) = v15;
          *(_QWORD *)(a1 + 8) += 24LL;
        }
        v18 = *(unsigned int *)v10;
        v10 = (const OLECHAR *)((char *)v10 + v18);
        SysFreeString(v17);
      }
      while ( (_DWORD)v18 );
      free(v6);
      return 0;
    }
LABEL_17:
    v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v9 = v8;
    free(v6);
    return v9;
  }
  else
  {
    result = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800491d8  mov     [rsp+arg_8], rbx
0x1800491dd  mov     [rsp+arg_10], rdi
0x1800491e2  push    r12
0x1800491e4  push    r14
0x1800491e6  push    r15
0x1800491e8  sub     rsp, 70h
0x1800491ec  mov     rax, cs:__security_cookie
0x1800491f3  xor     rax, rsp
0x1800491f6  mov     [rsp+88h+var_28], rax
0x1800491fb  mov     r15, rcx
0x1800491fe  mov     edx, cs:_tls_index
0x180049204  mov     rax, gs:58h
0x18004920d  mov     ecx, 4
0x180049212  mov     rax, [rax+rdx*8]
0x180049216  mov     edx, [rcx+rax]
0x180049219  cmp     cs:dword_180077B30, edx
0x18004921f  jle     loc_1800492DD
0x180049225  lea     rcx, dword_180077B30
0x18004922c  call    _Init_thread_header
0x180049231  cmp     cs:dword_180077B30, 0FFFFFFFFh
0x180049238  jnz     loc_1800492DD
0x18004923e  mov     cs:qword_180077B44, 0
0x180049249  mov     cs:dword_180077B4C, 0
0x180049253  mov     cs:qword_180077B38, 0
0x18004925e  mov     cs:dword_180077B40, 0
0x180049268  mov     ebx, 800h
0x18004926d  mov     r8d, ebx; dwFlags
0x180049270  xor     edx, edx; hFile
0x180049272  lea     rcx, aSechostDll; "Sechost.dll"
0x180049279  call    cs:__imp_LoadLibraryExW
0x18004927f  mov     cs:qword_180077B44+4, rax
0x180049286  test    rax, rax
0x180049289  jnz     short loc_1800492A9
0x18004928b  mov     r8d, ebx; dwFlags
0x18004928e  xor     edx, edx; hFile
0x180049290  lea     rcx, aApiMsWinEventi_0; "api-ms-win-eventing-controller-l1-1-0"
0x180049297  call    cs:__imp_LoadLibraryExW
0x18004929d  mov     cs:qword_180077B44+4, rax
0x1800492a4  test    rax, rax
0x1800492a7  jz      short loc_1800492C5
0x1800492a9  lea     rdx, aTracequeryinfo; "TraceQueryInformation"
0x1800492b0  mov     rcx, rax; hModule
0x1800492b3  call    cs:__imp_GetProcAddress
0x1800492b9  test    rax, rax
0x1800492bc  mov     cs:qword_180077B38, rax
0x1800492c3  jnz     short loc_1800492D1
0x1800492c5  call    cs:__imp_GetLastError
0x1800492cb  mov     cs:dword_180077B40, eax
0x1800492d1  lea     rcx, dword_180077B30
0x1800492d8  call    _Init_thread_footer
0x1800492dd  mov     ecx, cs:dword_180077B40
0x1800492e3  test    ecx, ecx
0x1800492e5  jnz     loc_1800494B7
0x1800492eb  mov     rax, cs:qword_180077B38
0x1800492f2  test    rax, rax
0x1800492f5  jz      loc_1800494B7
0x1800492fb  lea     rcx, [rsp+88h+Size]
0x180049300  mov     [rsp+88h+var_68], rcx
0x180049305  xor     r9d, r9d
0x180049308  xor     r8d, r8d
0x18004930b  lea     edi, [r9+7]
0x18004930f  mov     edx, edi
0x180049311  xor     ecx, ecx
0x180049313  call    cs:__guard_dispatch_icall_fptr
0x180049319  mov     ecx, eax
0x18004931b  cmp     eax, 18h
0x18004931e  jnz     loc_1800494B7
0x180049324  cmp     dword ptr [rsp+88h+Size], 0
0x180049329  jnz     short loc_180049332
0x18004932b  xor     eax, eax
0x18004932d  jmp     loc_1800494C4
0x180049332  mov     ecx, dword ptr [rsp+88h+Size]; Size
0x180049336  call    cs:__imp_malloc
0x18004933c  mov     rbx, rax
0x18004933f  mov     [rsp+88h+var_40], rax
0x180049344  test    rax, rax
0x180049347  jnz     short loc_18004935B
0x180049349  xor     ecx, ecx; Block
0x18004934b  call    cs:__imp_free
0x180049351  mov     eax, 8007000Eh
0x180049356  jmp     loc_1800494C4
0x18004935b  mov     [rsp+88h+var_68], 0
0x180049364  mov     r9d, dword ptr [rsp+88h+Size]
0x180049369  mov     r8, rbx
0x18004936c  mov     edx, edi
0x18004936e  xor     ecx, ecx
0x180049370  mov     rax, cs:qword_180077B38
0x180049377  call    cs:__guard_dispatch_icall_fptr
0x18004937d  test    eax, eax
0x18004937f  jz      short loc_18004939F
0x180049381  movzx   edi, ax
0x180049384  or      edi, 80070000h
0x18004938a  test    eax, eax
0x18004938c  cmovle  edi, eax
0x18004938f  mov     rcx, rbx; Block
0x180049392  call    cs:__imp_free
0x180049398  mov     eax, edi
0x18004939a  jmp     loc_1800494C4
0x18004939f  mov     r14, rbx
0x1800493a2  mov     eax, [r14+4]
0x1800493a6  mov     [rsp+88h+var_30], eax
0x1800493aa  mov     [rsp+88h+var_2C], 0
0x1800493b2  mov     [rsp+88h+var_68], 0
0x1800493bb  mov     r9d, 8
0x1800493c1  lea     r8, [rsp+88h+var_30]
0x1800493c6  lea     edx, [r9-3]
0x1800493ca  xor     ecx, ecx
0x1800493cc  mov     rax, cs:qword_180077B38
0x1800493d3  call    cs:__guard_dispatch_icall_fptr
0x1800493d9  test    eax, eax
0x1800493db  jnz     short loc_180049381
0x1800493dd  mov     [rsp+88h+bstrString], 0
0x1800493e6  mov     [rsp+88h+var_4C], 0
0x1800493ef  mov     [rsp+88h+var_44], eax
0x1800493f3  mov     r12d, [r14+4]
0x1800493f7  mov     [rsp+88h+var_50], r12d
0x1800493fc  lea     rdi, [r14+18h]
0x180049400  xor     eax, eax
0x180049402  test    rdi, rdi
0x180049405  jz      short loc_180049426
0x180049407  xor     ecx, ecx; bstrString
0x180049409  call    cs:__imp_SysFreeString
0x18004940f  mov     rcx, rdi; psz
0x180049412  call    cs:__imp_SysAllocString
0x180049418  mov     [rsp+88h+bstrString], rax
0x18004941d  test    rax, rax
0x180049420  jz      loc_1800494E8
0x180049426  mov     r8d, [rsp+88h+var_2C]
0x18004942b  mov     dword ptr [rsp+88h+var_4C], r8d
0x180049430  mov     r9d, [r14+8]
0x180049434  mov     dword ptr [rsp+88h+var_4C+4], r9d
0x180049439  mov     r10d, [r14+0Ch]
0x18004943d  mov     [rsp+88h+var_44], r10d
0x180049442  mov     rdx, [r15+8]
0x180049446  cmp     rdx, [r15+10h]
0x18004944a  jz      short loc_18004946D
0x18004944c  mov     [rdx], rax
0x18004944f  xor     ecx, ecx
0x180049451  mov     [rsp+88h+bstrString], rcx
0x180049456  mov     [rdx+8], r12d
0x18004945a  mov     [rdx+0Ch], r8d
0x18004945e  mov     [rdx+10h], r9d
0x180049462  mov     [rdx+14h], r10d
0x180049466  add     qword ptr [r15+8], 18h
0x18004946b  jmp     short loc_18004947F
0x18004946d  lea     r8, [rsp+88h+bstrString]
0x180049472  mov     rcx, r15
0x180049475  call    ??$_Emplace_reallocate@UProfileSourceDetails@EventTrace@Microsoft@@@?$vector@UProfileSourceDetails@EventTrace@Microsoft@@V?$allocator@UProfileSourceDetails@EventTrace@Microsoft@@@std@@@std@@AEAAPEAUProfileSourceDetails@EventTrace@Microsoft@@QEAU234@$$QEAU234@@Z; std::vector<Microsoft::EventTrace::ProfileSourceDetails>::_Emplace_reallocate<Microsoft::EventTrace::ProfileSourceDetails>(Microsoft::EventTrace::ProfileSourceDetails * const,Microsoft::EventTrace::ProfileSourceDetails &&)
0x18004947a  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18004947f  mov     edi, [r14]
0x180049482  add     r14, rdi
0x180049485  call    cs:__imp_SysFreeString
0x18004948b  test    edi, edi
0x18004948d  jnz     loc_1800493A2
0x180049493  mov     rcx, rbx; Block
0x180049496  call    cs:__imp_free
0x18004949c  jmp     loc_18004932B
0x1800494a1  mov     rcx, [rsp+88h+bstrString]; bstrString
0x1800494a6  call    cs:__imp_SysFreeString
0x1800494ac  nop
0x1800494ad  mov     rcx, [rsp+88h+var_40]
0x1800494b2  jmp     loc_18004934B
0x1800494b7  movzx   eax, cx
0x1800494ba  or      eax, 80070000h
0x1800494bf  test    ecx, ecx
0x1800494c1  cmovle  eax, ecx
0x1800494c4  mov     rcx, [rsp+88h+var_28]
0x1800494c9  xor     rcx, rsp; StackCookie
0x1800494cc  call    __security_check_cookie
0x1800494d1  lea     r11, [rsp+88h+var_18]
0x1800494d6  mov     rbx, [r11+28h]
0x1800494da  mov     rdi, [r11+30h]
0x1800494de  mov     rsp, r11
0x1800494e1  pop     r15
0x1800494e3  pop     r14
0x1800494e5  pop     r12
0x1800494e7  retn
0x1800494e8  mov     ecx, 8007000Eh; int
0x1800494ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
