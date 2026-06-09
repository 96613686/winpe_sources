# ComputeFontCacheDirectoryFromProfile(void)

- ea: `0x1800a9538`
- end: `0x1800a9780`
- name: `?ComputeFontCacheDirectoryFromProfile@@YA?AVRefString@DWrite@@XZ`
- size: `584`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800a92ec`

## callees

- `0x18000d7ec`
- `0x1800103f0`
- `0x1800217ac`
- `0x18002faf0`
- `0x1800a9538`
- `0x1800aa650`
- `0x1800aaab0`
- `0x1800ab168`
- `0x1800b0a5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9650`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a9642`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a9642`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a9589`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a9589`

## pseudocode

```c
__int64 __fastcall ComputeFontCacheDirectoryFromProfile(__int64 a1)
{
  int BasicProfileFolderPath; // eax
  __int64 v3; // rdi
  __int64 *i; // r14
  _WORD *v5; // rdx
  unsigned __int64 v6; // rsi
  signed int LastError; // eax
  unsigned int v8; // ecx
  __int128 v10; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B0h]
  WCHAR *v13; // [rsp+58h] [rbp-A8h]
  __int64 v14; // [rsp+60h] [rbp-A0h]
  int v15; // [rsp+68h] [rbp-98h]
  int v16; // [rsp+6Ch] [rbp-94h]
  int v17; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+74h] [rbp-8Ch]
  WCHAR PathName[264]; // [rsp+80h] [rbp-80h] BYREF

  *(_QWORD *)&v10 = a1;
  BasicProfileFolderPath = GetBasicProfileFolderPath(5, 0, PathName, 260);
  LogAndThrowIfFailed<OSException>(BasicProfileFolderPath);
  v3 = -1;
  do
    ++v3;
  while ( PathName[v3] );
  for ( i = (__int64 *)off_1800E8F40; i != &qword_1800E8F58; ++i )
  {
    if ( (unsigned __int64)(v3 - 1) <= 0x101 && PathName[v3 - 1] != 92 )
    {
      PathName[v3++] = 92;
      if ( (unsigned __int64)(2 * v3) >= 0x208 )
        _report_rangecheckfailure();
      PathName[v3] = 0;
    }
    v5 = (_WORD *)*i;
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    if ( v6 >= 260 - v3 )
    {
      Exception::Exception((Exception *)&v10, -2147418113, 0);
      LogAndThrow<OSException>(&v10, 0x687461706366LL, 406);
    }
    memcpy_0(&PathName[v3], v5, 2 * v6 + 2);
    v3 += v6;
    if ( !CreateDirectoryW(PathName, 0) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError != 183 )
      {
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v12 = v8;
        v10 = 0;
        v16 = 0;
        v18 = 0;
        v11 = 1;
        v13 = 0;
        v14 = 0x687461706366LL;
        v15 = 1;
        v17 = 421;
        EventLogger::LogGenericEvent(0, 0, 0x726F727265LL, &v11, 3);
      }
    }
  }
  v12 = 4;
  v11 = (__int64)L"\\\\?\\";
  v14 = v3;
  v13 = PathName;
  LOWORD(v15) = 92;
  DWrite::RefString::RefString(a1, &v11);
  return a1;
}

```

## disassembly

```asm
0x1800a9538  push    rbp
0x1800a953a  push    rbx
0x1800a953b  push    rsi
0x1800a953c  push    rdi
0x1800a953d  push    r12
0x1800a953f  push    r13
0x1800a9541  push    r14
0x1800a9543  push    r15
0x1800a9545  lea     rbp, [rsp-1A8h]
0x1800a954d  sub     rsp, 2A8h
0x1800a9554  mov     rax, cs:__security_cookie
0x1800a955b  xor     rax, rsp
0x1800a955e  mov     [rbp+1E0h+var_50], rax
0x1800a9565  xor     edx, edx
0x1800a9567  mov     qword ptr [rsp+2E0h+var_2B0], rcx
0x1800a956c  mov     r15, rcx
0x1800a956f  lea     r8, [rbp+1E0h+PathName]
0x1800a9573  mov     r9d, 104h
0x1800a9579  xor     r12d, r12d
0x1800a957c  mov     rbx, 687461706366h
0x1800a9586  lea     ecx, [rdx+5]
0x1800a9589  call    cs:__imp_GetBasicProfileFolderPath
0x1800a958f  mov     r8d, 182h
0x1800a9595  mov     rdx, rbx
0x1800a9598  mov     ecx, eax; int
0x1800a959a  call    ??$LogAndThrowIfFailed@VOSException@@@@YAXJVEventTag@@I@Z; LogAndThrowIfFailed<OSException>(long,EventTag,uint)
0x1800a959f  lea     rax, [rbp+1E0h+PathName]
0x1800a95a3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a95a7  inc     rdi
0x1800a95aa  cmp     [rax+rdi*2], r12w
0x1800a95af  jnz     short loc_1800A95A7
0x1800a95b1  lea     r14, off_1800E8F40; "AppData"
0x1800a95b8  mov     r13d, 5Ch ; '\'
0x1800a95be  lea     rax, qword_1800E8F58
0x1800a95c5  cmp     r14, rax
0x1800a95c8  jz      loc_1800A9724
0x1800a95ce  lea     rax, [rdi-1]
0x1800a95d2  cmp     rax, 101h
0x1800a95d8  ja      short loc_1800A9602
0x1800a95da  cmp     [rsp+rdi*2+2E0h+var_262], r13w
0x1800a95e0  jz      short loc_1800A9602
0x1800a95e2  mov     [rbp+rdi*2+1E0h+PathName], r13w
0x1800a95e8  inc     rdi
0x1800a95eb  lea     rcx, [rdi+rdi]
0x1800a95ef  cmp     rcx, 208h
0x1800a95f6  jnb     loc_1800A96F8
0x1800a95fc  mov     [rbp+rcx+1E0h+PathName], r12w
0x1800a9602  mov     rdx, [r14]; Src
0x1800a9605  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800a9609  inc     rsi
0x1800a960c  cmp     [rdx+rsi*2], r12w
0x1800a9611  jnz     short loc_1800A9609
0x1800a9613  mov     eax, 104h
0x1800a9618  sub     rax, rdi
0x1800a961b  cmp     rsi, rax
0x1800a961e  jnb     loc_1800A96FE
0x1800a9624  lea     rcx, [rbp+1E0h+PathName]
0x1800a9628  lea     rcx, [rcx+rdi*2]; void *
0x1800a962c  lea     r8, ds:2[rsi*2]; Size
0x1800a9634  call    memcpy_0
0x1800a9639  xor     edx, edx; lpSecurityAttributes
0x1800a963b  lea     rcx, [rbp+1E0h+PathName]; lpPathName
0x1800a963f  add     rdi, rsi
0x1800a9642  call    cs:__imp_CreateDirectoryW
0x1800a9648  test    eax, eax
0x1800a964a  jnz     loc_1800A96EF
0x1800a9650  call    cs:__imp_GetLastError
0x1800a9656  mov     ecx, eax
0x1800a9658  cmp     eax, 0B7h
0x1800a965d  jz      loc_1800A96EF
0x1800a9663  test    eax, eax
0x1800a9665  jle     short loc_1800A9670
0x1800a9667  movzx   ecx, ax
0x1800a966a  or      ecx, 80070000h
0x1800a9670  xorps   xmm0, xmm0
0x1800a9673  mov     dword ptr [rsp+2E0h+var_290], ecx
0x1800a9677  movups  [rsp+2E0h+var_2B0], xmm0
0x1800a967c  mov     eax, dword ptr [rsp+2E0h+var_2B0+4]
0x1800a9680  lea     r9, [rsp+2E0h+var_298]
0x1800a9685  mov     dword ptr [rsp+2E0h+var_298+4], eax
0x1800a9689  mov     esi, 1
0x1800a968e  mov     eax, dword ptr [rsp+2E0h+var_2B0+0Ch]
0x1800a9692  mov     r8, 726F727265h
0x1800a969c  mov     dword ptr [rsp+2E0h+var_290+4], eax
0x1800a96a0  mov     rdx, r12
0x1800a96a3  movups  [rsp+2E0h+var_2B0], xmm0
0x1800a96a8  mov     eax, dword ptr [rsp+2E0h+var_2B0+4]
0x1800a96ac  xor     ecx, ecx
0x1800a96ae  mov     dword ptr [rsp+2E0h+var_288+4], eax
0x1800a96b2  movups  [rsp+2E0h+var_2B0], xmm0
0x1800a96b7  mov     eax, dword ptr [rsp+2E0h+var_2B0+4]
0x1800a96bb  mov     [rsp+2E0h+var_274], eax
0x1800a96bf  mov     eax, dword ptr [rsp+2E0h+var_2B0+0Ch]
0x1800a96c3  mov     [rsp+2E0h+var_26C], eax
0x1800a96c7  mov     dword ptr [rsp+2E0h+var_298], esi
0x1800a96cb  mov     dword ptr [rsp+2E0h+var_288], r12d
0x1800a96d0  mov     [rsp+2E0h+var_280], rbx
0x1800a96d5  mov     [rsp+2E0h+var_278], esi
0x1800a96d9  mov     [rsp+2E0h+var_270], 1A5h
0x1800a96e1  mov     [rsp+2E0h+var_2C0], 3
0x1800a96ea  call    ?LogGenericEvent@EventLogger@@SAXIVEventTag@@0PEBU__MIDL___MIDL_itf_serverinterface_0000_0000_0002@@_K@Z; EventLogger::LogGenericEvent(uint,EventTag,EventTag,__MIDL___MIDL_itf_serverinterface_0000_0000_0002 const *,unsigned __int64)
0x1800a96ef  add     r14, 8
0x1800a96f3  jmp     loc_1800A95BE
0x1800a96f8  call    __report_rangecheckfailure
0x1800a96fe  xor     r8d, r8d; unsigned int
0x1800a9701  lea     rcx, [rsp+2E0h+var_2B0]; this
0x1800a9706  mov     edx, 8000FFFFh; int
0x1800a970b  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x1800a9710  mov     r8d, 196h
0x1800a9716  lea     rcx, [rsp+2E0h+var_2B0]
0x1800a971b  mov     rdx, rbx
0x1800a971e  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x1800a9724  lea     rax, asc_1800EAEB8; "\\\\?\\"
0x1800a972b  mov     [rsp+2E0h+var_290], 4
0x1800a9734  mov     [rsp+2E0h+var_298], rax
0x1800a9739  lea     rdx, [rsp+2E0h+var_298]
0x1800a973e  lea     rax, [rbp+1E0h+PathName]
0x1800a9742  mov     [rsp+2E0h+var_280], rdi
0x1800a9747  mov     rcx, r15
0x1800a974a  mov     [rsp+2E0h+var_288], rax
0x1800a974f  mov     word ptr [rsp+2E0h+var_278], r13w
0x1800a9755  call    ??$?0V?$StringSum@V?$StringSum@PEB_WPEB_W@@_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@V?$StringSum@PEB_WPEB_W@@_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<StringSum<wchar_t const *,wchar_t const *>,wchar_t>> const &)
0x1800a975a  mov     rax, r15
0x1800a975d  mov     rcx, [rbp+1E0h+var_50]
0x1800a9764  xor     rcx, rsp; StackCookie
0x1800a9767  call    __security_check_cookie
0x1800a976c  add     rsp, 2A8h
0x1800a9773  pop     r15
0x1800a9775  pop     r14
0x1800a9777  pop     r13
0x1800a9779  pop     r12
0x1800a977b  pop     rdi
0x1800a977c  pop     rsi
0x1800a977d  pop     rbx
0x1800a977e  pop     rbp
0x1800a977f  retn
```
