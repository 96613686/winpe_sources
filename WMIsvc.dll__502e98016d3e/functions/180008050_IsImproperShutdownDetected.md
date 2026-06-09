# IsImproperShutdownDetected

- ea: `0x180008050`
- end: `0x180008504`
- name: `IsImproperShutdownDetected`
- size: `1204`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008050`
- `0x18000c910`
- `0x18000c9bc`
- `0x18001d377`
- `0x18001d3a0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800080a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800080a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008101`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008114`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008127`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008101`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008114`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008127`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800080b7`

## string_xrefs

- `0x18000809b`: `Wevtapi.dll`
- `0x18000811d`: `EvtCreateRenderContext`
- `0x18000814f`: `<QueryList> <Query Id="0" Path="System"> <Select Path="System">*[System[Provider[@Name='eventlog'] and (EventID=6005 or EventID=6006)]]</Select> </Query></QueryList>`
- `0x180008300`: `<QueryList> <Query Id="1" Path="Application"> <Select Path="Application">*[System[Provider[@Name='Microsoft-Windows-WMI'] and (EventID=5615 )]]</Select> </Query></QueryList>`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 IsImproperShutdownDetected()
{
  HMODULE Library; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // r14
  FARPROC v3; // rdi
  FARPROC v4; // rsi
  FARPROC v5; // r13
  FARPROC v6; // rax
  __int64 (__fastcall *v7)(_QWORD, _QWORD, _QWORD); // r12
  __int64 v8; // rax
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // r15
  __int64 v13; // rdi
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // r15
  __int64 v17; // rax
  __int64 v18; // r14
  _BYTE *v19; // rcx
  int i; // edi
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  int v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v26[2]; // [rsp+60h] [rbp-A0h]
  _BYTE v27[8]; // [rsp+70h] [rbp-90h] BYREF
  void (__fastcall *v28)(__int64); // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  _BYTE v30[8]; // [rsp+88h] [rbp-78h] BYREF
  void (__fastcall *v31)(__int64); // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  unsigned int (__fastcall *v33)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // [rsp+A0h] [rbp-60h]
  unsigned int (__fastcall *v34)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // [rsp+A8h] [rbp-58h]
  _BYTE v35[8]; // [rsp+B0h] [rbp-50h] BYREF
  void (__fastcall *v36)(__int64); // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  _BYTE v38[8]; // [rsp+C8h] [rbp-38h] BYREF
  void (__fastcall *v39)(__int64); // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  _QWORD v41[2]; // [rsp+E8h] [rbp-18h]
  _BYTE v42[24]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v43[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v44; // [rsp+130h] [rbp+30h] BYREF
  int v45; // [rsp+13Ch] [rbp+3Ch]
  __int64 v46; // [rsp+140h] [rbp+40h]
  int v47; // [rsp+14Ch] [rbp+4Ch]

  LOWORD(v44) = 0;
  memset_0((char *)&v44 + 2, 0, 0x7FEu);
  Library = LoadLibraryExW(L"Wevtapi.dll", 0, 0);
  v1 = Library;
  if ( !Library )
    return 0;
  MakeGuard<int (*)(void *),void *>(v27, FreeLibrary, Library);
  ProcAddress = GetProcAddress(v1, "EvtRender");
  v34 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
  v3 = GetProcAddress(v1, "EvtNext");
  v33 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))v3;
  v4 = GetProcAddress(v1, "EvtClose");
  v5 = GetProcAddress(v1, "EvtQuery");
  v6 = GetProcAddress(v1, "EvtCreateRenderContext");
  v7 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v6;
  if ( !v5
    || !v4
    || !v3
    || !ProcAddress
    || !v6
    || (v8 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, const wchar_t *, __int64))v5)(
               0,
               L"System",
               L"<QueryList> <Query Id=\"0\" Path=\"System\"> <Select Path=\"System\">*[System[Provider[@Name='eventlog'] "
                "and (EventID=6005 or EventID=6006)]]</Select> </Query></QueryList>",
               513),
        (v9 = v8) == 0) )
  {
LABEL_10:
    ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v27);
    return 0;
  }
  MakeGuard<int (*)(void *),void *>(v35, v4, v8);
  v24 = 0;
  v23 = 0;
  v10 = v7(2, off_180032020, 0);
  v11 = v10;
  if ( !v10 )
  {
LABEL_9:
    ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v35);
    goto LABEL_10;
  }
  MakeGuard<int (*)(void *),void *>(v38, v4, v10);
  v13 = 0;
  v14 = 1;
  while ( 1 )
  {
    if ( !v33(v9, 1, &v24, 5000, 0, &v23) )
    {
LABEL_44:
      if ( !v38[0] )
        v39(v40);
      if ( !v35[0] )
        v36(v37);
      if ( !v27[0] )
        v28(v29);
      return 0;
    }
    MakeGuard<int (*)(void *),void *>(v30, v4, v24);
    v22 = 0;
    v21 = 0;
    if ( !v34(v11, v24, 0, 2048, &v44, &v22, &v21)
      || v21 != 2
      || v45 != 6
      || (*((_DWORD *)v26 + v13) = (unsigned __int16)v44, v47 != 17) )
    {
      v19 = v30;
LABEL_27:
      ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v19);
LABEL_24:
      ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v38);
      goto LABEL_9;
    }
    v41[v13] = v46;
    v13 = (unsigned int)(v13 + 1);
    if ( (_DWORD)v13 == 2 )
      break;
    ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v30);
  }
  if ( !v30[0] )
    v31(v32);
  if ( v26[0] == 0x177500001775LL )
  {
    v15 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, const wchar_t *, __int64))v5)(
            0,
            L"Application",
            L"<QueryList> <Query Id=\"1\" Path=\"Application\"> <Select Path=\"Application\">*[System[Provider[@Name='Micr"
             "osoft-Windows-WMI'] and (EventID=5615 )]]</Select> </Query></QueryList>",
            513);
    v16 = v15;
    if ( !v15 )
      goto LABEL_24;
    MakeGuard<int (*)(void *),void *>(v42, v4, v15);
    v25 = 0;
    v17 = v7(1, off_180032018, 0);
    v18 = v17;
    if ( !v17 )
    {
      v19 = v42;
      goto LABEL_27;
    }
    MakeGuard<int (*)(void *),void *>(v43, v4, v17);
    for ( i = 0; i != 2; ++i )
    {
      if ( !v33(v16, 1, &v25, 5000, 0, &v23) )
      {
        if ( i != 1 || v26[0] <= v41[0] )
          goto LABEL_36;
        goto LABEL_40;
      }
      MakeGuard<int (*)(void *),void *>(v30, v4, v25);
      v22 = 0;
      v21 = 0;
      if ( !v34(v18, v25, 0, 2048, &v44, &v22, &v21) || v21 != 1 || v45 != 17 )
      {
        ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v30);
        v14 = 0;
        goto LABEL_40;
      }
      v26[i] = v44;
      ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v30);
    }
    if ( v26[0] <= v41[0] || v26[1] >= v41[0] )
    {
LABEL_36:
      ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v43);
      ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v42);
      goto LABEL_44;
    }
LABEL_40:
    ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v43);
    ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v42);
  }
  else
  {
    v14 = 0;
  }
  ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v38);
  ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v35);
  ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(v27);
  return v14;
}

```

## disassembly

```asm
0x180008050  push    rbp
0x180008052  push    rbx
0x180008053  push    rsi
0x180008054  push    rdi
0x180008055  push    r12
0x180008057  push    r13
0x180008059  push    r14
0x18000805b  push    r15
0x18000805d  lea     rbp, [rsp-848h]
0x180008065  sub     rsp, 948h
0x18000806c  mov     rax, cs:__security_cookie
0x180008073  xor     rax, rsp
0x180008076  mov     [rbp+880h+var_50], rax
0x18000807d  xor     r15d, r15d
0x180008080  mov     word ptr [rbp+880h+var_850], r15w
0x180008085  xor     edx, edx; Val
0x180008087  mov     r8d, 7FEh; Size
0x18000808d  lea     rcx, [rbp+880h+var_850+2]; void *
0x180008091  call    memset_0
0x180008096  xor     r8d, r8d; dwFlags
0x180008099  xor     edx, edx; hFile
0x18000809b  lea     rcx, LibFileName; "Wevtapi.dll"
0x1800080a2  call    cs:__imp_LoadLibraryExW
0x1800080a8  mov     rbx, rax
0x1800080ab  test    rax, rax
0x1800080ae  jz      loc_1800081BB
0x1800080b4  mov     r8, rax
0x1800080b7  mov     rdx, cs:__imp_FreeLibrary
0x1800080be  lea     rcx, [rsp+980h+var_910]
0x1800080c3  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x1800080c8  nop
0x1800080c9  lea     rdx, aEvtrender; "EvtRender"
0x1800080d0  mov     rcx, rbx; hModule
0x1800080d3  call    cs:__imp_GetProcAddress
0x1800080d9  mov     r14, rax
0x1800080dc  mov     [rbp+880h+var_8D8], rax
0x1800080e0  lea     rdx, aEvtnext; "EvtNext"
0x1800080e7  mov     rcx, rbx; hModule
0x1800080ea  call    cs:__imp_GetProcAddress
0x1800080f0  mov     rdi, rax
0x1800080f3  mov     [rbp+880h+var_8E0], rax
0x1800080f7  lea     rdx, aEvtclose; "EvtClose"
0x1800080fe  mov     rcx, rbx; hModule
0x180008101  call    cs:__imp_GetProcAddress
0x180008107  mov     rsi, rax
0x18000810a  lea     rdx, aEvtquery; "EvtQuery"
0x180008111  mov     rcx, rbx; hModule
0x180008114  call    cs:__imp_GetProcAddress
0x18000811a  mov     r13, rax
0x18000811d  lea     rdx, aEvtcreaterende; "EvtCreateRenderContext"
0x180008124  mov     rcx, rbx; hModule
0x180008127  call    cs:__imp_GetProcAddress
0x18000812d  mov     r12, rax
0x180008130  test    r13, r13
0x180008133  jz      short loc_1800081B1
0x180008135  test    rsi, rsi
0x180008138  jz      short loc_1800081B1
0x18000813a  test    rdi, rdi
0x18000813d  jz      short loc_1800081B1
0x18000813f  test    r14, r14
0x180008142  jz      short loc_1800081B1
0x180008144  test    rax, rax
0x180008147  jz      short loc_1800081B1
0x180008149  mov     r9d, 201h
0x18000814f  lea     r8, aQuerylistQuery_0; "<QueryList> <Query Id=\"0\" Path=\"Syst"...
0x180008156  lea     rdx, aSystem; "System"
0x18000815d  xor     ecx, ecx
0x18000815f  mov     rax, r13
0x180008162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008167  mov     r14, rax
0x18000816a  test    rax, rax
0x18000816d  jz      short loc_1800081B1
0x18000816f  mov     r8, rax
0x180008172  mov     rdx, rsi
0x180008175  lea     rcx, [rbp+880h+var_8D0]
0x180008179  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x18000817e  nop
0x18000817f  mov     [rsp+980h+var_930], r15
0x180008184  mov     [rsp+980h+var_938], r15d
0x180008189  xor     r8d, r8d
0x18000818c  lea     rdx, off_180032020; "Event/System/EventID"
0x180008193  lea     ecx, [r15+2]
0x180008197  mov     rax, r12
0x18000819a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000819f  mov     r15, rax
0x1800081a2  test    rax, rax
0x1800081a5  jnz     short loc_1800081E0
0x1800081a7  lea     rcx, [rbp+880h+var_8D0]
0x1800081ab  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x1800081b0  nop
0x1800081b1  lea     rcx, [rsp+980h+var_910]
0x1800081b6  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x1800081bb  xor     eax, eax
0x1800081bd  mov     rcx, [rbp+880h+var_50]
0x1800081c4  xor     rcx, rsp; StackCookie
0x1800081c7  call    __security_check_cookie
0x1800081cc  add     rsp, 948h
0x1800081d3  pop     r15
0x1800081d5  pop     r14
0x1800081d7  pop     r13
0x1800081d9  pop     r12
0x1800081db  pop     rdi
0x1800081dc  pop     rsi
0x1800081dd  pop     rbx
0x1800081de  pop     rbp
0x1800081df  retn
0x1800081e0  mov     r8, r15
0x1800081e3  mov     rdx, rsi
0x1800081e6  lea     rcx, [rbp+880h+var_8B8]
0x1800081ea  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x1800081ef  nop
0x1800081f0  xor     edi, edi
0x1800081f2  lea     ebx, [rdi+1]
0x1800081f5  lea     rax, [rsp+980h+var_938]
0x1800081fa  mov     [rsp+980h+var_958], rax
0x1800081ff  mov     dword ptr [rsp+980h+var_960], 0
0x180008207  mov     r9d, 1388h
0x18000820d  lea     r8, [rsp+980h+var_930]
0x180008212  mov     edx, ebx
0x180008214  mov     rcx, r14
0x180008217  mov     rax, [rbp+880h+var_8E0]
0x18000821b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008220  test    eax, eax
0x180008222  jz      loc_1800084BB
0x180008228  mov     r8, [rsp+980h+var_930]
0x18000822d  mov     rdx, rsi
0x180008230  lea     rcx, [rbp+880h+var_8F8]
0x180008234  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x180008239  nop
0x18000823a  mov     [rsp+980h+var_93C], 0
0x180008242  mov     [rsp+980h+var_940], 0
0x18000824a  lea     rax, [rsp+980h+var_940]
0x18000824f  mov     [rsp+980h+var_950], rax
0x180008254  lea     rax, [rsp+980h+var_93C]
0x180008259  mov     [rsp+980h+var_958], rax
0x18000825e  lea     rax, [rbp+880h+var_850]
0x180008262  mov     [rsp+980h+var_960], rax
0x180008267  mov     r9d, 800h
0x18000826d  xor     r8d, r8d
0x180008270  mov     rdx, [rsp+980h+var_930]
0x180008275  mov     rcx, r15
0x180008278  mov     rax, [rbp+880h+var_8D8]
0x18000827c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008281  test    eax, eax
0x180008283  jz      loc_1800084B2
0x180008289  cmp     [rsp+980h+var_940], 2
0x18000828e  jnz     loc_1800084B2
0x180008294  cmp     [rbp+880h+var_844], 6
0x180008298  jnz     loc_1800084B2
0x18000829e  movzx   eax, word ptr [rbp+880h+var_850]
0x1800082a2  mov     dword ptr [rsp+rdi*4+980h+var_920], eax
0x1800082a6  cmp     [rbp+880h+var_834], 11h
0x1800082aa  jnz     loc_1800084B2
0x1800082b0  mov     rax, [rbp+880h+var_840]
0x1800082b4  mov     [rbp+rdi*8+880h+var_898], rax
0x1800082b9  add     edi, ebx
0x1800082bb  cmp     edi, 2
0x1800082be  jz      short loc_1800082CE
0x1800082c0  lea     rcx, [rbp+880h+var_8F8]
0x1800082c4  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x1800082c9  jmp     loc_1800081F5
0x1800082ce  cmp     [rbp+880h+var_8F8], 0
0x1800082d2  jnz     short loc_1800082E1
0x1800082d4  mov     rcx, [rbp+880h+var_8E8]
0x1800082d8  mov     rax, [rbp+880h+var_8F0]
0x1800082dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082e1  mov     eax, 1775h
0x1800082e6  cmp     dword ptr [rsp+980h+var_920], eax
0x1800082ea  jnz     loc_18000848B
0x1800082f0  cmp     dword ptr [rsp+980h+var_920+4], eax
0x1800082f4  jnz     loc_18000848B
0x1800082fa  mov     r9d, 201h
0x180008300  lea     r8, aQuerylistQuery; "<QueryList> <Query Id=\"1\" Path=\"Appl"...
0x180008307  lea     rdx, aApplication; "Application"
0x18000830e  xor     ecx, ecx
0x180008310  mov     rax, r13
0x180008313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008318  mov     r15, rax
0x18000831b  xor     r13d, r13d
0x18000831e  test    rax, rax
0x180008321  jnz     short loc_180008331
0x180008323  lea     rcx, [rbp+880h+var_8B8]
0x180008327  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x18000832c  jmp     loc_1800081A7
0x180008331  mov     r8, r15
0x180008334  mov     rdx, rsi
0x180008337  lea     rcx, [rbp+880h+var_888]
0x18000833b  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x180008340  nop
0x180008341  mov     [rsp+980h+var_928], r13
0x180008346  xor     r8d, r8d
0x180008349  lea     rdx, off_180032018; "Event/System/TimeCreated/@SystemTime"
0x180008350  mov     ecx, ebx
0x180008352  mov     rax, r12
0x180008355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000835a  mov     r14, rax
0x18000835d  test    rax, rax
0x180008360  jnz     short loc_18000836D
0x180008362  lea     rcx, [rbp+880h+var_888]
0x180008366  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x18000836b  jmp     short loc_180008323
0x18000836d  mov     r8, r14
0x180008370  mov     rdx, rsi
0x180008373  lea     rcx, [rbp+880h+var_870]
0x180008377  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x18000837c  nop
0x18000837d  mov     edi, r13d
0x180008380  lea     rax, [rsp+980h+var_938]
0x180008385  mov     [rsp+980h+var_958], rax
0x18000838a  mov     dword ptr [rsp+980h+var_960], r13d
0x18000838f  mov     r9d, 1388h
0x180008395  lea     r8, [rsp+980h+var_928]
0x18000839a  mov     edx, ebx
0x18000839c  mov     rcx, r15
0x18000839f  mov     rax, [rbp+880h+var_8E0]
0x1800083a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083a8  test    eax, eax
0x1800083aa  jz      loc_180008467
0x1800083b0  mov     r8, [rsp+980h+var_928]
0x1800083b5  mov     rdx, rsi
0x1800083b8  lea     rcx, [rbp+880h+var_8F8]
0x1800083bc  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x1800083c1  nop
0x1800083c2  mov     [rsp+980h+var_93C], r13d
0x1800083c7  mov     [rsp+980h+var_940], r13d
0x1800083cc  lea     rax, [rsp+980h+var_940]
0x1800083d1  mov     [rsp+980h+var_950], rax
0x1800083d6  lea     rax, [rsp+980h+var_93C]
0x1800083db  mov     [rsp+980h+var_958], rax
0x1800083e0  lea     rax, [rbp+880h+var_850]
0x1800083e4  mov     [rsp+980h+var_960], rax
0x1800083e9  mov     r9d, 800h
0x1800083ef  xor     r8d, r8d
0x1800083f2  mov     rdx, [rsp+980h+var_928]
0x1800083f7  mov     rcx, r14
0x1800083fa  mov     rax, [rbp+880h+var_8D8]
0x1800083fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008403  test    eax, eax
0x180008405  jz      short loc_180008459
0x180008407  cmp     [rsp+980h+var_940], ebx
0x18000840b  jnz     short loc_180008459
0x18000840d  cmp     [rbp+880h+var_844], 11h
0x180008411  jnz     short loc_180008459
0x180008413  mov     ecx, edi
0x180008415  mov     rax, [rbp+880h+var_850]
0x180008419  mov     [rsp+rcx*8+980h+var_920], rax
0x18000841e  add     edi, ebx
0x180008420  lea     rcx, [rbp+880h+var_8F8]
0x180008424  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180008429  cmp     edi, 2
0x18000842c  jnz     loc_180008380
0x180008432  mov     rax, [rbp+880h+var_898]
0x180008436  cmp     [rsp+980h+var_920], rax
0x18000843b  jbe     short loc_180008444
0x18000843d  cmp     [rsp+980h+var_918], rax
0x180008442  jb      short loc_180008476
0x180008444  lea     rcx, [rbp+880h+var_870]
0x180008448  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x18000844d  nop
0x18000844e  lea     rcx, [rbp+880h+var_888]
0x180008452  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180008457  jmp     short loc_1800084BE
0x180008459  lea     rcx, [rbp+880h+var_8F8]
0x18000845d  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180008462  mov     ebx, r13d
0x180008465  jmp     short loc_180008476
0x180008467  cmp     edi, ebx
0x180008469  jnz     short loc_180008444
0x18000846b  mov     rax, [rbp+880h+var_898]
0x18000846f  cmp     [rsp+980h+var_920], rax
0x180008474  jbe     short loc_180008444
0x180008476  lea     rcx, [rbp+880h+var_870]
0x18000847a  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x18000847f  nop
0x180008480  lea     rcx, [rbp+880h+var_888]
0x180008484  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180008489  jmp     short loc_18000848D
0x18000848b  xor     ebx, ebx
0x18000848d  lea     rcx, [rbp+880h+var_8B8]
0x180008491  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x180008496  nop
0x180008497  lea     rcx, [rbp+880h+var_8D0]
0x18000849b  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x1800084a0  nop
0x1800084a1  lea     rcx, [rsp+980h+var_910]
0x1800084a6  call    ??1?$ScopeGuardImpl1@P6AJPEAUtagSAFEARRAY@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>::~ScopeGuardImpl1<long (*)(tagSAFEARRAY *),tagSAFEARRAY *>(void)
0x1800084ab  mov     eax, ebx
0x1800084ad  jmp     loc_1800081BD
0x1800084b2  lea     rcx, [rbp+880h+var_8F8]
0x1800084b6  jmp     loc_180008366
0x1800084bb  xor     r13d, r13d
0x1800084be  cmp     [rbp+880h+var_8B8], r13b
0x1800084c2  jnz     short loc_1800084D2
0x1800084c4  mov     rcx, [rbp+880h+var_8A8]
0x1800084c8  mov     rax, [rbp+880h+var_8B0]
0x1800084cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084d1  nop
0x1800084d2  cmp     [rbp+880h+var_8D0], r13b
0x1800084d6  jnz     short loc_1800084E6
0x1800084d8  mov     rcx, [rbp+880h+var_8C0]
  ... truncated ...
```
