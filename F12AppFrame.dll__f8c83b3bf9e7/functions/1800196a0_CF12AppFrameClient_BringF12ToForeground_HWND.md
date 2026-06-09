# CF12AppFrameClient::BringF12ToForeground(HWND__ *)

- ea: `0x1800196a0`
- end: `0x18001992d`
- name: `?BringF12ToForeground@CF12AppFrameClient@@UEAAJPEAUHWND__@@@Z`
- size: `653`
- prototype: `int __fastcall(CF12AppFrameClient *this, HWND)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180003858`
- `0x1800042a4`
- `0x1800196a0`
- `0x180019ec4`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001982d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001982d`
- `KERNEL32!CloseHandle` at `0x1800198bb`
- `KERNEL32!CloseHandle` at `0x180019918`
- `KERNEL32!CloseHandle` at `0x1800198bb`
- `KERNEL32!CloseHandle` at `0x180019918`
- `KERNEL32!GetLastError` at `0x1800196fa`
- `KERNEL32!GetLastError` at `0x18001972e`
- `KERNEL32!GetLastError` at `0x1800198dc`
- `KERNEL32!GetLastError` at `0x1800196fa`
- `KERNEL32!GetLastError` at `0x18001972e`
- `KERNEL32!GetLastError` at `0x1800198dc`
- `KERNEL32!OpenProcess` at `0x18001971c`
- `KERNEL32!OpenProcess` at `0x18001971c`
- `KERNEL32!QueryFullProcessImageNameW` at `0x180019796`
- `KERNEL32!QueryFullProcessImageNameW` at `0x180019796`
- `USER32!IsIconic` at `0x18001983a`
- `USER32!IsIconic` at `0x18001983a`
- `USER32!ShowWindow` at `0x18001984c`
- `USER32!ShowWindow` at `0x18001984c`
- `USER32!GetWindowThreadProcessId` at `0x1800196eb`
- `USER32!GetWindowThreadProcessId` at `0x1800196eb`
- `USER32!SetForegroundWindow` at `0x180019855`
- `USER32!SetForegroundWindow` at `0x180019855`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x1800196c5`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x1800196c5`

## pseudocode

```c
int __fastcall CF12AppFrameClient::BringF12ToForeground(CF12AppFrameClient *this, HWND a2)
{
  signed int v3; // r14d
  int result; // eax
  HANDLE v5; // rbx
  __int64 v6; // rax
  WCHAR *v7; // rsi
  BOOL v8; // ecx
  __int64 v9; // rax
  int F12ChooserPath; // eax
  __int64 v11; // rdi
  signed int LastError; // eax
  unsigned int v13; // edi
  DWORD dwProcessId; // [rsp+20h] [rbp-20h] BYREF
  WCHAR *v15; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v16[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD dwSize; // [rsp+90h] [rbp+50h] BYREF
  int v18; // [rsp+98h] [rbp+58h] BYREF

  v18 = 0;
  v3 = IsDeveloperModeEnabled(&v18);
  if ( v3 < 0 || !v18 )
    return v3;
  dwProcessId = 0;
  GetWindowThreadProcessId(a2, &dwProcessId);
  if ( !dwProcessId )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v5 = OpenProcess(0x1000u, 0, dwProcessId);
  v16[1] = v5;
  if ( !v5 )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v6 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v7 = (WCHAR *)(v6 + 24);
  v15 = (WCHAR *)(v6 + 24);
  dwSize = 260;
  if ( ((*(_DWORD *)(v6 + 12) - 260) | (1 - *(_DWORD *)(v6 + 16))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v15);
    v7 = v15;
  }
  v8 = QueryFullProcessImageNameW(v5, 0, v7, &dwSize);
  if ( v8 )
  {
    LODWORD(v9) = dwSize;
    if ( dwSize == -1 )
    {
      if ( v7 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v7[v9] );
      }
      else
      {
        LODWORD(v9) = 0;
      }
    }
    if ( (int)v9 < 0 )
LABEL_42:
      ATL::AtlThrowImpl(-2147024809);
  }
  else
  {
    LODWORD(v9) = 0;
  }
  if ( (int)v9 > *((_DWORD *)v7 - 3) )
    goto LABEL_42;
  *((_DWORD *)v7 - 4) = v9;
  v7[(unsigned int)v9] = 0;
  if ( v8 && dwSize )
  {
    v16[0] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    F12ChooserPath = GetF12ChooserPath(v16);
    v11 = v16[0];
    if ( F12ChooserPath || (unsigned int)_o__wcsicmp(v7, v16[0]) )
    {
      v3 = -2147024891;
    }
    else
    {
      if ( IsIconic(a2) )
        ShowWindow(a2, 9);
      v3 = !SetForegroundWindow(a2) ? 0x80004005 : 0;
    }
    if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 - 24) + 8LL))(*(_QWORD *)(v11 - 24));
    if ( _InterlockedDecrement((volatile signed __int32 *)v7 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
    CloseHandle(v5);
    return v3;
  }
  LastError = GetLastError();
  v13 = LastError;
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  if ( _InterlockedDecrement((volatile signed __int32 *)v7 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
  CloseHandle(v5);
  return v13;
}

```

## disassembly

```asm
0x1800196a0  mov     [rsp-38h+arg_0], rbx
0x1800196a5  push    rbp
0x1800196a6  push    rsi
0x1800196a7  push    rdi
0x1800196a8  push    r12
0x1800196aa  push    r13
0x1800196ac  push    r14
0x1800196ae  push    r15
0x1800196b0  mov     rbp, rsp
0x1800196b3  sub     rsp, 40h
0x1800196b7  mov     r15, rdx
0x1800196ba  xor     r12d, r12d
0x1800196bd  mov     [rbp+arg_18], r12d
0x1800196c1  lea     rcx, [rbp+arg_18]
0x1800196c5  call    cs:__imp_IsDeveloperModeEnabled
0x1800196cb  mov     r14d, eax
0x1800196ce  test    eax, eax
0x1800196d0  js      loc_1800198C1
0x1800196d6  cmp     [rbp+arg_18], r12d
0x1800196da  jz      loc_1800198C1
0x1800196e0  mov     [rbp+dwProcessId], r12d
0x1800196e4  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1800196e8  mov     rcx, r15; hWnd
0x1800196eb  call    cs:__imp_GetWindowThreadProcessId
0x1800196f1  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x1800196f5  test    r8d, r8d
0x1800196f8  jnz     short loc_180019715
0x1800196fa  call    cs:__imp_GetLastError
0x180019700  test    eax, eax
0x180019702  jle     loc_1800198C4
0x180019708  movzx   eax, ax
0x18001970b  or      eax, 80070000h
0x180019710  jmp     loc_1800198C4
0x180019715  xor     edx, edx; bInheritHandle
0x180019717  mov     ecx, 1000h; dwDesiredAccess
0x18001971c  call    cs:__imp_OpenProcess
0x180019722  mov     rbx, rax
0x180019725  mov     [rbp+var_8], rax
0x180019729  test    rax, rax
0x18001972c  jnz     short loc_180019745
0x18001972e  call    cs:__imp_GetLastError
0x180019734  test    eax, eax
0x180019736  jle     short loc_180019740
0x180019738  movzx   eax, ax
0x18001973b  or      eax, 80070000h
0x180019740  jmp     loc_1800198C4
0x180019745  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001974c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180019753  mov     rax, [rax+18h]
0x180019757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001975c  lea     rsi, [rax+18h]
0x180019760  mov     [rbp+var_18], rsi
0x180019764  mov     edx, 104h
0x180019769  mov     [rbp+dwSize], edx
0x18001976c  mov     ecx, 1
0x180019771  sub     ecx, [rsi-8]
0x180019774  mov     eax, [rsi-0Ch]
0x180019777  sub     eax, edx
0x180019779  or      ecx, eax
0x18001977b  jge     short loc_18001978A
0x18001977d  lea     rcx, [rbp+var_18]
0x180019781  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180019786  mov     rsi, [rbp+var_18]
0x18001978a  lea     r9, [rbp+dwSize]; lpdwSize
0x18001978e  mov     r8, rsi; lpExeName
0x180019791  xor     edx, edx; dwFlags
0x180019793  mov     rcx, rbx; hProcess
0x180019796  call    cs:__imp_QueryFullProcessImageNameW
0x18001979c  mov     ecx, eax
0x18001979e  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800197a2  test    eax, eax
0x1800197a4  jz      short loc_1800197CF
0x1800197a6  mov     eax, [rbp+dwSize]
0x1800197a9  cmp     eax, r13d
0x1800197ac  jnz     short loc_1800197C5
0x1800197ae  test    rsi, rsi
0x1800197b1  jnz     short loc_1800197B8
0x1800197b3  mov     eax, r12d
0x1800197b6  jmp     short loc_1800197C5
0x1800197b8  mov     rax, r13
0x1800197bb  inc     rax
0x1800197be  cmp     [rsi+rax*2], r12w
0x1800197c3  jnz     short loc_1800197BB
0x1800197c5  test    eax, eax
0x1800197c7  js      loc_180019922
0x1800197cd  jmp     short loc_1800197D2
0x1800197cf  mov     eax, r12d
0x1800197d2  cmp     eax, [rsi-0Ch]
0x1800197d5  jg      loc_180019922
0x1800197db  mov     [rsi-10h], eax
0x1800197de  mov     edx, eax
0x1800197e0  mov     [rsi+rdx*2], r12w
0x1800197e5  test    ecx, ecx
0x1800197e7  jz      loc_1800198DC
0x1800197ed  cmp     [rbp+dwSize], r12d
0x1800197f1  jbe     loc_1800198DC
0x1800197f7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800197fe  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180019805  mov     rax, [rax+18h]
0x180019809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001980e  add     rax, 18h
0x180019812  mov     [rbp+var_10], rax
0x180019816  lea     rcx, [rbp+var_10]
0x18001981a  call    ?GetF12ChooserPath@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetF12ChooserPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001981f  mov     rdi, [rbp+var_10]
0x180019823  test    eax, eax
0x180019825  jnz     short loc_18001986C
0x180019827  mov     rdx, rdi
0x18001982a  mov     rcx, rsi
0x18001982d  call    cs:__imp__o__wcsicmp
0x180019833  test    eax, eax
0x180019835  jnz     short loc_18001986C
0x180019837  mov     rcx, r15; hWnd
0x18001983a  call    cs:__imp_IsIconic
0x180019840  test    eax, eax
0x180019842  jz      short loc_180019852
0x180019844  mov     edx, 9; nCmdShow
0x180019849  mov     rcx, r15; hWnd
0x18001984c  call    cs:__imp_ShowWindow
0x180019852  mov     rcx, r15; hWnd
0x180019855  call    cs:__imp_SetForegroundWindow
0x18001985b  neg     eax
0x18001985d  sbb     r14d, r14d
0x180019860  not     r14d
0x180019863  and     r14d, 80004005h
0x18001986a  jmp     short loc_180019872
0x18001986c  mov     r14d, 80070005h
0x180019872  lea     rdx, [rdi-18h]
0x180019876  mov     eax, r13d
0x180019879  lock xadd [rdx+10h], eax
0x18001987e  add     eax, r13d
0x180019881  test    eax, eax
0x180019883  jg      short loc_180019895
0x180019885  mov     rcx, [rdx]
0x180019888  mov     rax, [rcx]
0x18001988b  mov     rax, [rax+8]
0x18001988f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019894  nop
0x180019895  lea     rdx, [rsi-18h]
0x180019899  mov     eax, r13d
0x18001989c  lock xadd [rdx+10h], eax
0x1800198a1  add     eax, r13d
0x1800198a4  test    eax, eax
0x1800198a6  jg      short loc_1800198B8
0x1800198a8  mov     rcx, [rdx]
0x1800198ab  mov     rax, [rcx]
0x1800198ae  mov     rax, [rax+8]
0x1800198b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198b7  nop
0x1800198b8  mov     rcx, rbx; hObject
0x1800198bb  call    cs:__imp_CloseHandle
0x1800198c1  mov     eax, r14d
0x1800198c4  mov     rbx, [rsp+40h+arg_0]
0x1800198cc  add     rsp, 40h
0x1800198d0  pop     r15
0x1800198d2  pop     r14
0x1800198d4  pop     r13
0x1800198d6  pop     r12
0x1800198d8  pop     rdi
0x1800198d9  pop     rsi
0x1800198da  pop     rbp
0x1800198db  retn
0x1800198dc  call    cs:__imp_GetLastError
0x1800198e2  nop
0x1800198e3  mov     edi, eax
0x1800198e5  test    eax, eax
0x1800198e7  jle     short loc_1800198F2
0x1800198e9  movzx   edi, ax
0x1800198ec  or      edi, 80070000h
0x1800198f2  lea     rdx, [rsi-18h]
0x1800198f6  mov     eax, r13d
0x1800198f9  lock xadd [rdx+10h], eax
0x1800198fe  add     eax, r13d
0x180019901  test    eax, eax
0x180019903  jg      short loc_180019915
0x180019905  mov     rcx, [rdx]
0x180019908  mov     rax, [rcx]
0x18001990b  mov     rax, [rax+8]
0x18001990f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019914  nop
0x180019915  mov     rcx, rbx; hObject
0x180019918  call    cs:__imp_CloseHandle
0x18001991e  mov     eax, edi
0x180019920  jmp     short loc_1800198C4
0x180019922  mov     ecx, 80070057h; int
0x180019927  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
