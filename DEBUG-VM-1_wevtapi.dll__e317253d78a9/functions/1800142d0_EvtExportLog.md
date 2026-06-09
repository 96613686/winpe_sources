# EvtExportLog

- ea: `0x1800142d0`
- end: `0x180014620`
- name: `EvtExportLog`
- size: `848`
- prototype: `BOOL __stdcall(EVT_HANDLE Session, LPCWSTR Path, LPCWSTR Query, LPCWSTR TargetFilePath, DWORD Flags)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180007940`
- `0x18000a100`
- `0x18000bf84`
- `0x18000c404`
- `0x180013f6c`
- `0x1800142d0`
- `0x180014938`
- `0x180023548`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014600`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014600`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
BOOL __stdcall EvtExportLog(EVT_HANDLE Session, LPCWSTR Path, LPCWSTR Query, LPCWSTR TargetFilePath, DWORD Flags)
{
  BOOL v8; // ebx
  const wchar_t *v9; // r12
  __int64 v10; // r8
  DWORD v11; // edi
  wmi::RefBase *v13; // [rsp+30h] [rbp-128h] BYREF
  wchar_t *v14[2]; // [rsp+38h] [rbp-120h] BYREF
  char v15; // [rsp+48h] [rbp-110h] BYREF
  __int128 pExceptionObject; // [rsp+58h] [rbp-100h] BYREF
  __int64 v17; // [rsp+68h] [rbp-F0h]
  int v18; // [rsp+70h] [rbp-E8h]
  int v19; // [rsp+74h] [rbp-E4h]
  int v20; // [rsp+78h] [rbp-E0h]
  __int128 v21; // [rsp+80h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+90h] [rbp-C8h]
  int v23; // [rsp+98h] [rbp-C0h]
  int v24; // [rsp+9Ch] [rbp-BCh]
  int v25; // [rsp+A0h] [rbp-B8h]
  __int128 v26; // [rsp+A8h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+B8h] [rbp-A0h]
  int v28; // [rsp+C0h] [rbp-98h]
  int v29; // [rsp+C4h] [rbp-94h]
  int v30; // [rsp+C8h] [rbp-90h]
  __int128 v31; // [rsp+D0h] [rbp-88h] BYREF
  __int64 v32; // [rsp+E0h] [rbp-78h]
  int v33; // [rsp+E8h] [rbp-70h]
  int v34; // [rsp+ECh] [rbp-6Ch]
  int v35; // [rsp+F0h] [rbp-68h]
  void *v36[2]; // [rsp+F8h] [rbp-60h] BYREF
  char v37; // [rsp+108h] [rbp-50h] BYREF
  EvtException *v38; // [rsp+118h] [rbp-40h] BYREF

  LastErrInfo::Reset((LastErrInfo *)Session);
  try
  {
    v8 = 0;
    if ( !Flags || (Flags & 0xFFFFCEFC) != 0 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      v31 = 0;
      v32 = 0;
      v33 = 87;
      v34 = -1;
      v35 = 1216;
      throw (EvtException *)&v31;
    }
    if ( !TargetFilePath )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v17 = 0;
      v18 = 87;
      v19 = -1;
      v20 = 1221;
      throw (EvtException *)&pExceptionObject;
    }
    v9 = L"*";
    if ( Query )
      v9 = Query;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v36);
    if ( (Flags & 2) != 0 )
    {
      if ( !Path )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
        }
        v21 = 0;
        v22 = 0;
        v23 = 87;
        v24 = -1;
        v25 = 1239;
        throw (EvtException *)&v21;
      }
      FullyQualifyFilePath((__int64)v36, Path);
      Path = (LPCWSTR)v36[0];
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v14);
    v10 = -1;
    do
      ++v10;
    while ( TargetFilePath[v10] );
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v14,
                             TargetFilePath,
                             v10) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 14);
      }
      v26 = 0;
      v27 = 0;
      v28 = 14;
      v29 = -1;
      v30 = 1249;
      throw (EvtException *)&v26;
    }
    FullyQualifyFilePath((__int64)v14, TargetFilePath);
    GetSession(&v13);
    LogHandle::ExportLog(v13, Path, v9, v14[0], Flags);
    v11 = 0;
    if ( v13 )
      wmi::RefBase::Release(v13);
    v13 = 0;
    if ( (char *)v14[0] != &v15 )
      operator delete(v14[0]);
    if ( v36[0] != &v37 )
      operator delete(v36[0]);
  }
  catch ( EvtException *v38 )
  {
    v8 = 0;
    v11 = *((_DWORD *)v38 + 6);
  }
  SetLastError(v11);
  LOBYTE(v8) = v11 == 0;
  return v8;
}

```

## disassembly

```asm
0x1800142d0  push    rbx
0x1800142d2  push    rsi
0x1800142d3  push    rdi
0x1800142d4  push    r12
0x1800142d6  push    r13
0x1800142d8  push    r14
0x1800142da  push    r15
0x1800142dc  sub     rsp, 120h
0x1800142e3  mov     r14, r9
0x1800142e6  mov     r15, r8
0x1800142e9  mov     rdi, rdx
0x1800142ec  mov     r13, rcx
0x1800142ef  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x1800142f4  mov     esi, [rsp+158h+Flags]
0x1800142fb  xor     ebx, ebx
0x1800142fd  test    esi, esi
0x1800142ff  jz      loc_180014573
0x180014305  test    esi, 0FFFFCEFCh
0x18001430b  jnz     loc_180014573
0x180014311  test    r14, r14
0x180014314  jnz     short loc_180014383
0x180014316  lea     rax, WPP_GLOBAL_Control
0x18001431d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014324  cmp     rcx, rax
0x180014327  jz      short loc_18001434C
0x180014329  test    byte ptr [rcx+1Ch], 1
0x18001432d  jz      short loc_18001434C
0x18001432f  cmp     byte ptr [rcx+19h], 2
0x180014333  jb      short loc_18001434C
0x180014335  lea     edx, [rbx+25h]
0x180014338  lea     r9d, [rbx+57h]
0x18001433c  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x180014343  mov     rcx, [rcx+10h]
0x180014347  call    WPP_SF_D
0x18001434c  xorps   xmm0, xmm0
0x18001434f  movdqu  [rsp+158h+pExceptionObject], xmm0
0x180014355  mov     [rsp+158h+var_F0], rbx
0x18001435a  mov     [rsp+158h+var_E8], 57h ; 'W'
0x180014362  mov     [rsp+158h+var_E4], 0FFFFFFFFh
0x18001436a  mov     [rsp+158h+var_E0], 4C5h
0x180014372  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180014379  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x18001437e  call    _CxxThrowException_0
0x180014383  lea     r12, asc_180040200; "*"
0x18001438a  test    r15, r15
0x18001438d  cmovnz  r12, r15
0x180014391  lea     rcx, [rsp+158h+var_60]
0x180014399  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001439e  nop
0x18001439f  test    sil, 2
0x1800143a3  jz      loc_180014445
0x1800143a9  test    rdi, rdi
0x1800143ac  jnz     short loc_18001442D
0x1800143ae  lea     rax, WPP_GLOBAL_Control
0x1800143b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143bc  cmp     rcx, rax
0x1800143bf  jz      short loc_1800143E4
0x1800143c1  test    byte ptr [rcx+1Ch], 1
0x1800143c5  jz      short loc_1800143E4
0x1800143c7  cmp     byte ptr [rcx+19h], 2
0x1800143cb  jb      short loc_1800143E4
0x1800143cd  lea     edx, [rdi+26h]
0x1800143d0  lea     r9d, [rdi+57h]
0x1800143d4  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x1800143db  mov     rcx, [rcx+10h]
0x1800143df  call    WPP_SF_D
0x1800143e4  xorps   xmm0, xmm0
0x1800143e7  movdqu  [rsp+158h+var_D8], xmm0
0x1800143f0  mov     [rsp+158h+var_C8], rbx
0x1800143f8  mov     [rsp+158h+var_C0], 57h ; 'W'
0x180014403  mov     [rsp+158h+var_BC], 0FFFFFFFFh
0x18001440e  mov     [rsp+158h+var_B8], 4D7h
0x180014419  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180014420  lea     rcx, [rsp+158h+var_D8]; pExceptionObject
0x180014428  call    _CxxThrowException_0
0x18001442d  mov     rdx, rdi
0x180014430  lea     rcx, [rsp+158h+var_60]
0x180014438  call    FullyQualifyFilePath
0x18001443d  mov     rdi, [rsp+158h+var_60]
0x180014445  lea     rcx, [rsp+158h+var_120]
0x18001444a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001444f  nop
0x180014450  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014454  inc     r8
0x180014457  cmp     [r14+r8*2], bx
0x18001445c  jnz     short loc_180014454
0x18001445e  mov     rdx, r14
0x180014461  lea     rcx, [rsp+158h+var_120]
0x180014466  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001446b  test    al, al
0x18001446d  jnz     loc_1800144F4
0x180014473  lea     rax, WPP_GLOBAL_Control
0x18001447a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014481  cmp     rcx, rax
0x180014484  jz      short loc_1800144AB
0x180014486  test    byte ptr [rcx+1Ch], 1
0x18001448a  jz      short loc_1800144AB
0x18001448c  cmp     byte ptr [rcx+19h], 2
0x180014490  jb      short loc_1800144AB
0x180014492  mov     edx, 27h ; '''
0x180014497  lea     r9d, [rdx-19h]
0x18001449b  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x1800144a2  mov     rcx, [rcx+10h]
0x1800144a6  call    WPP_SF_D
0x1800144ab  xorps   xmm0, xmm0
0x1800144ae  movdqu  [rsp+158h+var_B0], xmm0
0x1800144b7  mov     [rsp+158h+var_A0], rbx
0x1800144bf  mov     [rsp+158h+var_98], 0Eh
0x1800144ca  mov     [rsp+158h+var_94], 0FFFFFFFFh
0x1800144d5  mov     [rsp+158h+var_90], 4E1h
0x1800144e0  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800144e7  lea     rcx, [rsp+158h+var_B0]; pExceptionObject
0x1800144ef  call    _CxxThrowException_0
0x1800144f4  mov     rdx, r14
0x1800144f7  lea     rcx, [rsp+158h+var_120]
0x1800144fc  call    FullyQualifyFilePath
0x180014501  mov     rdx, r13
0x180014504  lea     rcx, [rsp+158h+var_128]; void *
0x180014509  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18001450e  nop
0x18001450f  mov     [rsp+158h+var_138], esi; unsigned int
0x180014513  mov     r9, [rsp+158h+var_120]; wchar_t *
0x180014518  mov     r8, r12; wchar_t *
0x18001451b  mov     rdx, rdi; wchar_t *
0x18001451e  mov     rcx, [rsp+158h+var_128]; this
0x180014523  call    ?ExportLog@LogHandle@@SAXPEAVSession@@PEB_W11K@Z; LogHandle::ExportLog(Session *,wchar_t const *,wchar_t const *,wchar_t const *,ulong)
0x180014528  mov     edi, ebx
0x18001452a  mov     rcx, [rsp+158h+var_128]; this
0x18001452f  test    rcx, rcx
0x180014532  jz      short loc_180014539
0x180014534  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x180014539  mov     [rsp+158h+var_128], rbx
0x18001453e  lea     rax, [rsp+158h+var_110]
0x180014543  mov     rcx, [rsp+158h+var_120]; void *
0x180014548  cmp     rcx, rax
0x18001454b  jz      short loc_180014553
0x18001454d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014552  nop
0x180014553  lea     rax, [rsp+158h+var_50]
0x18001455b  mov     rcx, [rsp+158h+var_60]; void *
0x180014563  cmp     rcx, rax
0x180014566  jz      short loc_18001456E
0x180014568  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001456d  nop
0x18001456e  jmp     loc_1800145FE
0x180014573  lea     rax, WPP_GLOBAL_Control
0x18001457a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014581  cmp     rcx, rax
0x180014584  jz      short loc_1800145AB
0x180014586  test    byte ptr [rcx+1Ch], 1
0x18001458a  jz      short loc_1800145AB
0x18001458c  cmp     byte ptr [rcx+19h], 2
0x180014590  jb      short loc_1800145AB
0x180014592  mov     edx, 24h ; '$'
0x180014597  lea     r9d, [rdx+33h]
0x18001459b  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x1800145a2  mov     rcx, [rcx+10h]
0x1800145a6  call    WPP_SF_D
0x1800145ab  xorps   xmm0, xmm0
0x1800145ae  movdqu  [rsp+158h+var_88], xmm0
0x1800145b7  mov     [rsp+158h+var_78], rbx
0x1800145bf  mov     [rsp+158h+var_70], 57h ; 'W'
0x1800145ca  mov     [rsp+158h+var_6C], 0FFFFFFFFh
0x1800145d5  mov     [rsp+158h+var_68], 4C0h
0x1800145e0  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800145e7  lea     rcx, [rsp+158h+var_88]; pExceptionObject
0x1800145ef  call    _CxxThrowException_0
0x1800145f5  xor     ebx, ebx
0x1800145f7  mov     edi, [rsp+158h+Flags]
0x1800145fe  mov     ecx, edi; dwErrCode
0x180014600  call    cs:__imp_SetLastError
0x180014606  test    edi, edi
0x180014608  setz    bl
0x18001460b  mov     eax, ebx
0x18001460d  add     rsp, 120h
0x180014614  pop     r15
0x180014616  pop     r14
0x180014618  pop     r13
0x18001461a  pop     r12
0x18001461c  pop     rdi
0x18001461d  pop     rsi
0x18001461e  pop     rbx
0x18001461f  retn
```
