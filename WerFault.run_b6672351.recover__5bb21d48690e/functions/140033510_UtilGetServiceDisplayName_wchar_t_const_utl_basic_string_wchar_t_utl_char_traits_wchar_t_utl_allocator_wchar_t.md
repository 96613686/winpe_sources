# UtilGetServiceDisplayName(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140033510`
- end: `0x14003378f`
- name: `?UtilGetServiceDisplayName@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x140033798`

## callees

- `0x140002490`
- `0x14000ca20`
- `0x140012784`
- `0x140014ee4`
- `0x140014f14`
- `0x140033510`
- `0x14005f510`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140033594`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140033759`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140033594`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140033759`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400335b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400335b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400335e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003366c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400335e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003366c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400335d5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400335d5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14003370f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14003370f`

## string_xrefs

- `0x14003356e`: `advapi32.dll`
- `0x1400335af`: `GetServiceDisplayNameW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetServiceDisplayName(__int64 a1, __int64 a2)
{
  HMODULE v4; // rdi
  _WORD *v5; // rcx
  HMODULE *v6; // rax
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
  HMODULE hLibModule; // [rsp+40h] [rbp-2048h] BYREF
  _WORD v21[4096]; // [rsp+50h] [rbp-2038h] BYREF

  v4 = 0;
  v19 = 0;
  v18 = 0;
  if ( a1 && a2 )
  {
    v5 = *(_WORD **)a2;
    *(_QWORD *)(a2 + 8) = *(_QWORD *)a2;
    *v5 = 0;
    v6 = UtilLoadModFromSystem(&hLibModule, (__int64)L"advapi32.dll");
    v4 = *v6;
    *v6 = 0;
    v19 = v4;
    if ( hLibModule )
      FreeLibrary(hLibModule);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v7);
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
                              v21) )
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
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v15);
LABEL_28:
    CloseServiceHandle(v10);
    goto LABEL_32;
  }
  v7 = -2147024809;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
  }
LABEL_32:
  if ( v4 )
    FreeLibrary(v4);
  return v7;
}

```

## disassembly

```asm
0x140033510  mov     [rsp+arg_10], rbx
0x140033515  push    rbp
0x140033516  push    rsi
0x140033517  push    rdi
0x140033518  push    r14
0x14003351a  push    r15
0x14003351c  mov     eax, 2060h
0x140033521  call    _alloca_probe
0x140033526  sub     rsp, rax
0x140033529  mov     rax, cs:__security_cookie
0x140033530  xor     rax, rsp
0x140033533  mov     [rsp+2088h+var_38], rax
0x14003353b  mov     rbx, rdx
0x14003353e  mov     r14, rcx
0x140033541  xor     r15d, r15d
0x140033544  mov     edi, r15d
0x140033547  mov     [rsp+2088h+var_2050], r15
0x14003354c  mov     [rsp+2088h+var_2058], r15d
0x140033551  test    rcx, rcx
0x140033554  jz      loc_14003371D
0x14003355a  test    rdx, rdx
0x14003355d  jz      loc_14003371D
0x140033563  mov     rcx, [rdx]
0x140033566  mov     [rdx+8], rcx
0x14003356a  mov     [rcx], r15w
0x14003356e  lea     rdx, aAdvapi32Dll; "advapi32.dll"
0x140033575  lea     rcx, [rsp+2088h+hLibModule]
0x14003357a  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x14003357f  mov     rdi, [rax]
0x140033582  mov     [rax], r15
0x140033585  mov     [rsp+2088h+var_2050], rdi
0x14003358a  mov     rcx, [rsp+2088h+hLibModule]; hLibModule
0x14003358f  test    rcx, rcx
0x140033592  jz      short loc_1400335A0
0x140033594  call    cs:__imp_FreeLibrary
0x14003359b  nop     dword ptr [rax+rax+00h]
0x1400335a0  test    rdi, rdi
0x1400335a3  jnz     short loc_1400335AF
0x1400335a5  mov     ebx, 80070032h
0x1400335aa  jmp     loc_140033751
0x1400335af  lea     rdx, aGetservicedisp; "GetServiceDisplayNameW"
0x1400335b6  mov     rcx, rdi; hModule
0x1400335b9  call    cs:__imp_GetProcAddress
0x1400335c0  nop     dword ptr [rax+rax+00h]
0x1400335c5  mov     rsi, rax
0x1400335c8  test    rax, rax
0x1400335cb  jz      short loc_1400335A5
0x1400335cd  xor     edx, edx; lpDatabaseName
0x1400335cf  xor     ecx, ecx; lpMachineName
0x1400335d1  lea     r8d, [rdx+1]; dwDesiredAccess
0x1400335d5  call    cs:__imp_OpenSCManagerW
0x1400335dc  nop     dword ptr [rax+rax+00h]
0x1400335e1  mov     rbp, rax
0x1400335e4  test    rax, rax
0x1400335e7  jnz     short loc_140033642
0x1400335e9  call    cs:__imp_GetLastError
0x1400335f0  nop     dword ptr [rax+rax+00h]
0x1400335f5  mov     ebx, eax
0x1400335f7  test    eax, eax
0x1400335f9  jle     short loc_140033604
0x1400335fb  movzx   ebx, ax
0x1400335fe  or      ebx, 80070000h
0x140033604  lea     rax, WPP_GLOBAL_Control
0x14003360b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033612  cmp     rcx, rax
0x140033615  jz      loc_140033751
0x14003361b  test    byte ptr [rcx+1Ch], 1
0x14003361f  jz      loc_140033751
0x140033625  mov     edx, 60h ; '`'
0x14003362a  mov     r9d, ebx
0x14003362d  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140033634  mov     rcx, [rcx+10h]
0x140033638  call    WPP_SF_d
0x14003363d  jmp     loc_140033751
0x140033642  mov     [rsp+2088h+var_2038], r15w
0x140033648  mov     [rsp+2088h+var_2058], 1000h
0x140033650  lea     r9, [rsp+2088h+var_2058]
0x140033655  lea     r8, [rsp+2088h+var_2038]
0x14003365a  mov     rdx, r14
0x14003365d  mov     rcx, rbp
0x140033660  mov     rax, rsi
0x140033663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033668  test    eax, eax
0x14003366a  jnz     short loc_1400336BA
0x14003366c  call    cs:__imp_GetLastError
0x140033673  nop     dword ptr [rax+rax+00h]
0x140033678  mov     ebx, eax
0x14003367a  test    eax, eax
0x14003367c  jle     short loc_140033687
0x14003367e  movzx   ebx, ax
0x140033681  or      ebx, 80070000h
0x140033687  lea     rax, WPP_GLOBAL_Control
0x14003368e  mov     rcx, cs:WPP_GLOBAL_Control
0x140033695  cmp     rcx, rax
0x140033698  jz      short loc_14003370C
0x14003369a  test    byte ptr [rcx+1Ch], 1
0x14003369e  jz      short loc_14003370C
0x1400336a0  mov     edx, 61h ; 'a'
0x1400336a5  mov     r9d, ebx
0x1400336a8  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1400336af  mov     rcx, [rcx+10h]
0x1400336b3  call    WPP_SF_d
0x1400336b8  jmp     short loc_14003370C
0x1400336ba  lea     rax, [rsp+2088h+var_2038]
0x1400336bf  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400336c3  inc     r8
0x1400336c6  cmp     [rax+r8*2], r15w
0x1400336cb  jnz     short loc_1400336C3
0x1400336cd  lea     rdx, [rsp+2088h+var_2038]
0x1400336d2  mov     rcx, rbx
0x1400336d5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400336da  test    al, al
0x1400336dc  jnz     short loc_140033709
0x1400336de  mov     ebx, 8007000Eh
0x1400336e3  lea     rax, WPP_GLOBAL_Control
0x1400336ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400336f1  cmp     rcx, rax
0x1400336f4  jz      short loc_14003370C
0x1400336f6  test    byte ptr [rcx+1Ch], 1
0x1400336fa  jz      short loc_14003370C
0x1400336fc  mov     edx, 62h ; 'b'
0x140033701  mov     r9d, 8007000Eh
0x140033707  jmp     short loc_1400336A8
0x140033709  mov     ebx, r15d
0x14003370c  mov     rcx, rbp; hSCObject
0x14003370f  call    cs:__imp_CloseServiceHandle
0x140033716  nop     dword ptr [rax+rax+00h]
0x14003371b  jmp     short loc_140033751
0x14003371d  mov     ebx, 80070057h
0x140033722  lea     rax, WPP_GLOBAL_Control
0x140033729  mov     rcx, cs:WPP_GLOBAL_Control
0x140033730  cmp     rcx, rax
0x140033733  jz      short loc_140033751
0x140033735  test    byte ptr [rcx+1Ch], 1
0x140033739  jz      short loc_140033751
0x14003373b  mov     edx, 5Fh ; '_'
0x140033740  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140033747  mov     rcx, [rcx+10h]
0x14003374b  call    WPP_SF_
0x140033750  nop
0x140033751  test    rdi, rdi
0x140033754  jz      short loc_140033765
0x140033756  mov     rcx, rdi; hLibModule
0x140033759  call    cs:__imp_FreeLibrary
0x140033760  nop     dword ptr [rax+rax+00h]
0x140033765  mov     eax, ebx
0x140033767  mov     rcx, [rsp+2088h+var_38]
0x14003376f  xor     rcx, rsp; StackCookie
0x140033772  call    __security_check_cookie
0x140033777  mov     rbx, [rsp+2088h+arg_10]
0x14003377f  add     rsp, 2060h
0x140033786  pop     r15
0x140033788  pop     r14
0x14003378a  pop     rdi
0x14003378b  pop     rsi
0x14003378c  pop     rbp
0x14003378d  retn
```
