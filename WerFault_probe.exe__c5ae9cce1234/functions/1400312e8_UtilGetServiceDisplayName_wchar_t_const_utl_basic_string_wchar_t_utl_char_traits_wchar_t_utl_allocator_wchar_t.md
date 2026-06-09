# UtilGetServiceDisplayName(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1400312e8`
- end: `0x14003153c`
- name: `?UtilGetServiceDisplayName@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x140031544`

## callees

- `0x140002470`
- `0x14000c8a0`
- `0x140011f24`
- `0x14001444c`
- `0x140014474`
- `0x1400312e8`
- `0x14005b770`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003136c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003150d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003136c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003150d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003138b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003138b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400313af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003142c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400313af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003142c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400313a1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400313a1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400314c9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400314c9`

## string_xrefs

- `0x140031346`: `advapi32.dll`
- `0x140031381`: `GetServiceDisplayNameW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetServiceDisplayName(__int64 a1, __int64 a2)
{
  HMODULE v4; // rdi
  _WORD *v5; // rcx
  HMODULE *ModFromSystem; // rax
  unsigned int v7; // ebx
  FARPROC ProcAddress; // rsi
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rbp
  signed int LastError; // eax
  signed int v12; // eax
  CUserModeHangReport *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // r8
  int v18; // [rsp+30h] [rbp-2058h] BYREF
  HMODULE v19; // [rsp+38h] [rbp-2050h]
  HMODULE hLibModule[2]; // [rsp+40h] [rbp-2048h] BYREF
  _WORD v21[4096]; // [rsp+50h] [rbp-2038h] BYREF

  v4 = 0;
  v19 = 0;
  v18 = 0;
  if ( a1 && a2 )
  {
    v5 = *(_WORD **)a2;
    *(_QWORD *)(a2 + 8) = *(_QWORD *)a2;
    *v5 = 0;
    ModFromSystem = (HMODULE *)UtilLoadModFromSystem(hLibModule, L"advapi32.dll");
    v4 = *ModFromSystem;
    *ModFromSystem = 0;
    v19 = v4;
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    if ( !v4 || (ProcAddress = GetProcAddress(v4, "GetServiceDisplayNameW")) == 0 )
    {
      v7 = -2147024846;
      goto LABEL_32;
    }
    v9 = OpenSCManagerW(0, 0, 1u);
    v10 = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v7);
      }
      goto LABEL_32;
    }
    v21[0] = 0;
    v18 = 4096;
    if ( ((unsigned int (__fastcall *)(SC_HANDLE, __int64, _WORD *, int *))ProcAddress)(v9, a1, v21, &v18) )
    {
      v16 = -1;
      do
        ++v16;
      while ( v21[v16] );
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              a2,
                              v21,
                              v16) )
      {
        v7 = 0;
        goto LABEL_28;
      }
      v7 = -2147024882;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_28;
      }
      v14 = 98;
      v15 = 2147942414LL;
    }
    else
    {
      v12 = GetLastError();
      v7 = v12;
      if ( v12 > 0 )
        v7 = (unsigned __int16)v12 | 0x80070000;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_28;
      }
      v14 = 97;
      v15 = v7;
    }
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v15);
LABEL_28:
    CloseServiceHandle(v10);
    goto LABEL_32;
  }
  v7 = -2147024809;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
  }
LABEL_32:
  if ( v4 )
    FreeLibrary(v4);
  return v7;
}

```

## disassembly

```asm
0x1400312e8  mov     [rsp+arg_10], rbx
0x1400312ed  push    rbp
0x1400312ee  push    rsi
0x1400312ef  push    rdi
0x1400312f0  push    r14
0x1400312f2  push    r15
0x1400312f4  mov     eax, 2060h
0x1400312f9  call    _alloca_probe
0x1400312fe  sub     rsp, rax
0x140031301  mov     rax, cs:__security_cookie
0x140031308  xor     rax, rsp
0x14003130b  mov     [rsp+2088h+var_38], rax
0x140031313  mov     rbx, rdx
0x140031316  mov     r14, rcx
0x140031319  xor     r15d, r15d
0x14003131c  mov     edi, r15d
0x14003131f  mov     [rsp+2088h+var_2050], r15
0x140031324  mov     [rsp+2088h+var_2058], r15d
0x140031329  test    rcx, rcx
0x14003132c  jz      loc_1400314D1
0x140031332  test    rdx, rdx
0x140031335  jz      loc_1400314D1
0x14003133b  mov     rcx, [rdx]
0x14003133e  mov     [rdx+8], rcx
0x140031342  mov     [rcx], r15w
0x140031346  lea     rdx, aAdvapi32Dll; "advapi32.dll"
0x14003134d  lea     rcx, [rsp+2088h+hLibModule]
0x140031352  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x140031357  mov     rdi, [rax]
0x14003135a  mov     [rax], r15
0x14003135d  mov     [rsp+2088h+var_2050], rdi
0x140031362  mov     rcx, [rsp+2088h+hLibModule]; hLibModule
0x140031367  test    rcx, rcx
0x14003136a  jz      short loc_140031372
0x14003136c  call    cs:__imp_FreeLibrary
0x140031372  test    rdi, rdi
0x140031375  jnz     short loc_140031381
0x140031377  mov     ebx, 80070032h
0x14003137c  jmp     loc_140031505
0x140031381  lea     rdx, aGetservicedisp; "GetServiceDisplayNameW"
0x140031388  mov     rcx, rdi; hModule
0x14003138b  call    cs:__imp_GetProcAddress
0x140031391  mov     rsi, rax
0x140031394  test    rax, rax
0x140031397  jz      short loc_140031377
0x140031399  xor     edx, edx; lpDatabaseName
0x14003139b  xor     ecx, ecx; lpMachineName
0x14003139d  lea     r8d, [rdx+1]; dwDesiredAccess
0x1400313a1  call    cs:__imp_OpenSCManagerW
0x1400313a7  mov     rbp, rax
0x1400313aa  test    rax, rax
0x1400313ad  jnz     short loc_140031402
0x1400313af  call    cs:__imp_GetLastError
0x1400313b5  mov     ebx, eax
0x1400313b7  test    eax, eax
0x1400313b9  jle     short loc_1400313C4
0x1400313bb  movzx   ebx, ax
0x1400313be  or      ebx, 80070000h
0x1400313c4  lea     rax, WPP_GLOBAL_Control
0x1400313cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400313d2  cmp     rcx, rax
0x1400313d5  jz      loc_140031505
0x1400313db  test    byte ptr [rcx+1Ch], 1
0x1400313df  jz      loc_140031505
0x1400313e5  mov     edx, 60h ; '`'
0x1400313ea  mov     r9d, ebx
0x1400313ed  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1400313f4  mov     rcx, [rcx+10h]
0x1400313f8  call    WPP_SF_d
0x1400313fd  jmp     loc_140031505
0x140031402  mov     [rsp+2088h+var_2038], r15w
0x140031408  mov     [rsp+2088h+var_2058], 1000h
0x140031410  lea     r9, [rsp+2088h+var_2058]
0x140031415  lea     r8, [rsp+2088h+var_2038]
0x14003141a  mov     rdx, r14
0x14003141d  mov     rcx, rbp
0x140031420  mov     rax, rsi
0x140031423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031428  test    eax, eax
0x14003142a  jnz     short loc_140031474
0x14003142c  call    cs:__imp_GetLastError
0x140031432  mov     ebx, eax
0x140031434  test    eax, eax
0x140031436  jle     short loc_140031441
0x140031438  movzx   ebx, ax
0x14003143b  or      ebx, 80070000h
0x140031441  lea     rax, WPP_GLOBAL_Control
0x140031448  mov     rcx, cs:WPP_GLOBAL_Control
0x14003144f  cmp     rcx, rax
0x140031452  jz      short loc_1400314C6
0x140031454  test    byte ptr [rcx+1Ch], 1
0x140031458  jz      short loc_1400314C6
0x14003145a  mov     edx, 61h ; 'a'
0x14003145f  mov     r9d, ebx
0x140031462  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140031469  mov     rcx, [rcx+10h]
0x14003146d  call    WPP_SF_d
0x140031472  jmp     short loc_1400314C6
0x140031474  lea     rax, [rsp+2088h+var_2038]
0x140031479  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003147d  inc     r8
0x140031480  cmp     [rax+r8*2], r15w
0x140031485  jnz     short loc_14003147D
0x140031487  lea     rdx, [rsp+2088h+var_2038]
0x14003148c  mov     rcx, rbx
0x14003148f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140031494  test    al, al
0x140031496  jnz     short loc_1400314C3
0x140031498  mov     ebx, 8007000Eh
0x14003149d  lea     rax, WPP_GLOBAL_Control
0x1400314a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400314ab  cmp     rcx, rax
0x1400314ae  jz      short loc_1400314C6
0x1400314b0  test    byte ptr [rcx+1Ch], 1
0x1400314b4  jz      short loc_1400314C6
0x1400314b6  mov     edx, 62h ; 'b'
0x1400314bb  mov     r9d, 8007000Eh
0x1400314c1  jmp     short loc_140031462
0x1400314c3  mov     ebx, r15d
0x1400314c6  mov     rcx, rbp; hSCObject
0x1400314c9  call    cs:__imp_CloseServiceHandle
0x1400314cf  jmp     short loc_140031505
0x1400314d1  mov     ebx, 80070057h
0x1400314d6  lea     rax, WPP_GLOBAL_Control
0x1400314dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400314e4  cmp     rcx, rax
0x1400314e7  jz      short loc_140031505
0x1400314e9  test    byte ptr [rcx+1Ch], 1
0x1400314ed  jz      short loc_140031505
0x1400314ef  mov     edx, 5Fh ; '_'
0x1400314f4  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1400314fb  mov     rcx, [rcx+10h]
0x1400314ff  call    WPP_SF_
0x140031504  nop
0x140031505  test    rdi, rdi
0x140031508  jz      short loc_140031513
0x14003150a  mov     rcx, rdi; hLibModule
0x14003150d  call    cs:__imp_FreeLibrary
0x140031513  mov     eax, ebx
0x140031515  mov     rcx, [rsp+2088h+var_38]
0x14003151d  xor     rcx, rsp; StackCookie
0x140031520  call    __security_check_cookie
0x140031525  mov     rbx, [rsp+2088h+arg_10]
0x14003152d  add     rsp, 2060h
0x140031534  pop     r15
0x140031536  pop     r14
0x140031538  pop     rdi
0x140031539  pop     rsi
0x14003153a  pop     rbp
0x14003153b  retn
```
