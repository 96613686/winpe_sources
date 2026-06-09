# WinSAT::EncryptionWorkload::SetupWorkload(void)

- ea: `0x140076410`
- end: `0x140076b0b`
- name: `?SetupWorkload@EncryptionWorkload@WinSAT@@MEAAKXZ`
- size: `1787`
- prototype: `unsigned int __fastcall(WinSAT::EncryptionWorkload *__hidden this)`
- caller_count: `0`
- callee_count: `25`
- tags: `installer_update`

## callees

- `0x1400040d0`
- `0x140004348`
- `0x14000449c`
- `0x140005cf4`
- `0x140005f10`
- `0x140005f4c`
- `0x14000695c`
- `0x140008178`
- `0x1400085b4`
- `0x140011f58`
- `0x140016d04`
- `0x140017af0`
- `0x14001827c`
- `0x140019a1c`
- `0x1400219d0`
- `0x14003a150`
- `0x14003ec14`
- `0x1400530a8`
- `0x1400584b0`
- `0x14005ef98`
- `0x140074140`
- `0x14007625c`
- `0x140076410`
- `0x1400796f8`
- `0x140113220`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400764a4`
- `KERNEL32!EnterCriticalSection` at `0x14007660c`
- `KERNEL32!EnterCriticalSection` at `0x1400767e5`
- `KERNEL32!EnterCriticalSection` at `0x1400764a4`
- `KERNEL32!EnterCriticalSection` at `0x14007660c`
- `KERNEL32!EnterCriticalSection` at `0x1400767e5`
- `KERNEL32!LeaveCriticalSection` at `0x140076523`
- `KERNEL32!LeaveCriticalSection` at `0x14007668b`
- `KERNEL32!LeaveCriticalSection` at `0x140076add`
- `KERNEL32!LeaveCriticalSection` at `0x140076523`
- `KERNEL32!LeaveCriticalSection` at `0x14007668b`
- `KERNEL32!LeaveCriticalSection` at `0x140076add`
- `KERNEL32!GetCurrentThreadId` at `0x140076844`
- `KERNEL32!GetCurrentThreadId` at `0x140076844`
- `KERNEL32!GetThreadPriority` at `0x14007644b`
- `KERNEL32!GetThreadPriority` at `0x140076586`
- `KERNEL32!GetThreadPriority` at `0x14007644b`
- `KERNEL32!GetThreadPriority` at `0x140076586`
- `KERNEL32!GetCurrentThread` at `0x140076442`
- `KERNEL32!GetCurrentThread` at `0x140076459`
- `KERNEL32!GetCurrentThread` at `0x14007657d`
- `KERNEL32!GetCurrentThread` at `0x140076442`
- `KERNEL32!GetCurrentThread` at `0x140076459`
- `KERNEL32!GetCurrentThread` at `0x14007657d`
- `KERNEL32!GetLastError` at `0x140076472`
- `KERNEL32!GetLastError` at `0x140076472`
- `KERNEL32!Sleep` at `0x140076577`
- `KERNEL32!Sleep` at `0x140076577`
- `KERNEL32!SetThreadPriority` at `0x140076464`
- `KERNEL32!SetThreadPriority` at `0x140076464`
- `KERNEL32!SetLastError` at `0x14007654a`
- `KERNEL32!SetLastError` at `0x1400766ad`
- `KERNEL32!SetLastError` at `0x14007654a`
- `KERNEL32!SetLastError` at `0x1400766ad`

## string_xrefs

- `0x14007658f`: `CPU Encryption thread priority changed to %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
DWORD __fastcall WinSAT::EncryptionWorkload::SetupWorkload(WinSAT::EncryptionWorkload *this)
{
  int v2; // ebx
  HANDLE CurrentThread; // rax
  HANDLE v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  DWORD v9; // ebx
  HANDLE v11; // rax
  int ThreadPriority; // eax
  unsigned int v13; // ecx
  unsigned int v14; // eax
  DWORD v15; // eax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  DWORD flProtect; // esi
  int RB; // eax
  int v22; // edx
  int v23; // ebx
  __int64 v24; // rax
  int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v32; // rax
  __int64 v33; // rax
  const wchar_t *v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rbx
  mlib *v57; // rcx
  unsigned __int64 PerformanceFrequency64; // rax
  int v59; // [rsp+28h] [rbp-D8h]
  int v60; // [rsp+28h] [rbp-D8h]
  __int64 v61; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v62; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v63[48]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[256]; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwErrCode; // [rsp+280h] [rbp+180h]
  char v66; // [rsp+284h] [rbp+184h]
  __int64 v67; // [rsp+288h] [rbp+188h]

  v2 = *((_DWORD *)this + 192);
  CurrentThread = GetCurrentThread();
  if ( GetThreadPriority(CurrentThread) != v2 )
  {
    v4 = GetCurrentThread();
    if ( !SetThreadPriority(v4, v2) )
    {
      dwErrCode = GetLastError();
      v66 = 1;
      v67 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      _InterlockedIncrement(*((volatile signed __int32 **)this + 4));
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
      v5 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v63, 0x1F4u);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v62,
        v5);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v61,
        1024);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
        &v61,
        *(_QWORD *)(v62 + 24),
        *((unsigned int *)this + 22));
      v6 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             *((_QWORD *)this + 2) + 240LL,
             &v61);
      v7 = std::endl(v6);
      v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, Buffer);
      std::endl(v8);
      LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
      WinSAT::OpStatus::SetResult((char *)this + 96, 5, *(_QWORD *)(v61 + 24), Buffer);
      SetLastError(dwErrCode);
      v9 = dwErrCode;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v61);
LABEL_4:
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v62);
      return v9;
    }
    Sleep(1u);
    v11 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v11);
    Log_Text_F("base\\winsat\\cpu\\encryption.cpp", 164, "CPU Encryption thread priority changed to %d", ThreadPriority);
  }
  v13 = *(_DWORD *)(*((_QWORD *)this + 106) + 8432LL);
  if ( !v13 )
    return 160;
  v14 = *((_DWORD *)this + 250) / v13;
  *((_DWORD *)this + 244) = v14;
  v15 = WinSAT::EncryptionWorkload::SetupCryptoContext(this, v14);
  v9 = v15;
  if ( v15 )
  {
    dwErrCode = v15;
    v66 = 1;
    v67 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    _InterlockedIncrement(*((volatile signed __int32 **)this + 4));
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
    v16 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v63, 0x212u);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v62,
      v16);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v61,
      1024);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
      &v61,
      *(_QWORD *)(v62 + 24),
      *((unsigned int *)this + 22));
    v17 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            *((_QWORD *)this + 2) + 240LL,
            &v61);
    v18 = std::endl(v17);
    v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, Buffer);
    std::endl(v19);
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
    WinSAT::OpStatus::SetResult((char *)this + 96, 5, *(_QWORD *)(v61 + 24), v9);
    SetLastError(v9);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v61);
    goto LABEL_4;
  }
  flProtect = *(_BYTE *)(*((_QWORD *)this + 106) + 8377LL) != 0 ? 4 : 516;
  RB = RotatingBuffer::CreateRB(
         (WinSAT::EncryptionWorkload *)((char *)this + 856),
         (__int64)this + 1016,
         v59,
         *((_DWORD *)this + 256),
         flProtect);
  if ( RB < 0 )
  {
    v22 = RB;
    return WinSAT::EncryptionWorkload::DumpCreateRBError(this, v22);
  }
  *((_QWORD *)this + 123) = *((_QWORD *)this + 110) + (unsigned int)(*((_DWORD *)this + 215) * *((_DWORD *)this + 222));
  v23 = *((_DWORD *)this + 256);
  v24 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v62);
  v25 = RotatingBuffer::CreateRB((WinSAT::EncryptionWorkload *)((char *)this + 904), v24, v60, v23, flProtect);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v62);
  if ( v25 < 0 )
  {
    v22 = v25;
    return WinSAT::EncryptionWorkload::DumpCreateRBError(this, v22);
  }
  *((_QWORD *)this + 124) = *((_QWORD *)this + 116) + (unsigned int)(*((_DWORD *)this + 227) * *((_DWORD *)this + 234));
  *((_QWORD *)this + 105) = *(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(*((_QWORD *)this + 106) + 40LL);
  if ( *((_BYTE *)this + 24) )
  {
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
    v26 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(*((_QWORD *)this + 1) + 240LL, L"> CPU(");
    v27 = std::basic_ostream<unsigned short>::operator<<(v26, *((unsigned int *)this + 22));
    v28 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, L")  ");
    v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v28, L"TID: ");
    LODWORD(v61) = 4;
    v30 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, &v61);
    CurrentThreadId = GetCurrentThreadId();
    v32 = std::basic_ostream<unsigned short>::operator<<(v30, CurrentThreadId);
    *(_DWORD *)(*(int *)(*(_QWORD *)v32 + 4LL) + v32 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v32 + 4LL) + v32 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v32 + 4LL) + v32 + 40) = 0;
    v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, L"\n  -- Running at ");
    v34 = L"NORMAL";
    if ( !*(_BYTE *)(*((_QWORD *)this + 106) + 8376LL) )
      v34 = L"HIGH";
    v35 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, v34);
    v36 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, L" priority");
    v37 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v36, L"\n  -- Input Buffer Size =");
    v38 = std::basic_ostream<unsigned short>::operator<<(v37, *((unsigned int *)this + 250));
    v39 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v38, L" (0x");
    LODWORD(v61) = 4;
    v40 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v39, &v61);
    v41 = std::basic_ostream<unsigned short>::operator<<(v40, *((unsigned int *)this + 250));
    *(_DWORD *)(*(int *)(*(_QWORD *)v41 + 4LL) + v41 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v41 + 4LL) + v41 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v41 + 4LL) + v41 + 40) = 0;
    v42 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v41, L") bytes");
    v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, L"\n  -- Cypher Block Size =");
    v44 = std::basic_ostream<unsigned short>::operator<<(v43, *((unsigned int *)this + 251));
    v45 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v44, L"\n  -- Num regions = ");
    v46 = std::basic_ostream<unsigned short>::operator<<(v45, *(unsigned int *)(*((_QWORD *)this + 106) + 8432LL));
    v47 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v46, L"   region size= ");
    v48 = std::basic_ostream<unsigned short>::operator<<(
            v47,
            (unsigned int)(*((_DWORD *)this + 250) / *(_DWORD *)(*((_QWORD *)this + 106) + 8432LL)));
    v49 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, L"\n  -- Block Size = ");
    v50 = std::basic_ostream<unsigned short>::operator<<(v49, *((unsigned int *)this + 244));
    v51 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v50, L"\n  -- Affinity Mask ");
    LODWORD(v61) = 8;
    v52 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v51, &v61);
    v53 = std::basic_ostream<unsigned short>::operator<<(v52, *((unsigned int *)this + 194));
    *(_DWORD *)(*(int *)(*(_QWORD *)v53 + 4LL) + v53 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v53 + 4LL) + v53 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v53 + 4LL) + v53 + 40) = 0;
    v54 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            *((_QWORD *)this + 1) + 240LL,
            L"> Populate From '");
    v55 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v54,
            (char *)this + 1016);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, L"'\n");
    v56 = *((_QWORD *)this + 1);
    PerformanceFrequency64 = mlib::QueryPerformanceFrequency64(v57);
    mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>::pfx(
      v56,
      L"\n  -- Performance Counter Frequency     = %11I64u",
      PerformanceFrequency64);
    mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>::pfx(
      *((_QWORD *)this + 1),
      L"\n  -- CPU Time Stamp Freq               = %11I64u",
      *((_QWORD *)this + 105));
    mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>::pfx(
      *((_QWORD *)this + 1),
      L"\n  -- Time Stamp Counts Per millisecond = %11I64u\n",
      *((_QWORD *)this + 105) / 0x3E8uLL);
    std::basic_ostream<unsigned short>::flush(*((_QWORD *)this + 1) + 240LL);
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  }
  return 0;
}

```

## disassembly

```asm
0x140076410  push    rbp
0x140076412  push    rbx
0x140076413  push    rsi
0x140076414  push    rdi
0x140076415  push    r12
0x140076417  push    r14
0x140076419  lea     rbp, [rsp-1A8h]
0x140076421  sub     rsp, 2A8h
0x140076428  mov     rax, cs:__security_cookie
0x14007642f  xor     rax, rsp
0x140076432  mov     [rbp+1D0h+var_40], rax
0x140076439  mov     rdi, rcx
0x14007643c  mov     ebx, [rcx+300h]
0x140076442  call    cs:__imp_GetCurrentThread
0x140076448  mov     rcx, rax; hThread
0x14007644b  call    cs:__imp_GetThreadPriority
0x140076451  cmp     eax, ebx
0x140076453  jz      loc_1400765A7
0x140076459  call    cs:__imp_GetCurrentThread
0x14007645f  mov     edx, ebx; nPriority
0x140076461  mov     rcx, rax; hThread
0x140076464  call    cs:__imp_SetThreadPriority
0x14007646a  test    eax, eax
0x14007646c  jnz     loc_140076572
0x140076472  call    cs:__imp_GetLastError
0x140076478  mov     [rbp+1D0h+dwErrCode], eax
0x14007647e  mov     [rbp+1D0h+var_4C], 1
0x140076485  mov     [rbp+1D0h+var_48], 0
0x140076490  lea     rcx, [rbp+1D0h+Buffer]; lpBuffer
0x140076494  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140076499  mov     rax, [rdi+20h]
0x14007649d  lock inc dword ptr [rax]
0x1400764a0  mov     rcx, [rdi+50h]; lpCriticalSection
0x1400764a4  call    cs:__imp_EnterCriticalSection
0x1400764aa  mov     edx, 1F4h; unsigned __int16
0x1400764af  lea     rcx, [rsp+2D0h+var_280]; this
0x1400764b4  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x1400764b9  mov     rdx, rax
0x1400764bc  lea     rcx, [rsp+2D0h+var_288]
0x1400764c1  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x1400764c6  nop
0x1400764c7  mov     edx, 400h
0x1400764cc  lea     rcx, [rsp+2D0h+var_290]
0x1400764d1  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x1400764d6  nop
0x1400764d7  mov     r8d, [rdi+58h]
0x1400764db  mov     rdx, [rsp+2D0h+var_288]
0x1400764e0  mov     rdx, [rdx+18h]
0x1400764e4  lea     rcx, [rsp+2D0h+var_290]
0x1400764e9  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x1400764ee  mov     rcx, [rdi+10h]
0x1400764f2  add     rcx, 0F0h
0x1400764f9  lea     rdx, [rsp+2D0h+var_290]
0x1400764fe  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140076503  mov     rcx, rax
0x140076506  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14007650b  lea     rdx, [rbp+1D0h+Buffer]
0x14007650f  mov     rcx, rax
0x140076512  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140076517  mov     rcx, rax
0x14007651a  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14007651f  mov     rcx, [rdi+50h]; lpCriticalSection
0x140076523  call    cs:__imp_LeaveCriticalSection
0x140076529  lea     rcx, [rdi+60h]
0x14007652d  lea     r9, [rbp+1D0h+Buffer]
0x140076531  mov     r8, [rsp+2D0h+var_290]
0x140076536  mov     r8, [r8+18h]
0x14007653a  mov     edx, 5
0x14007653f  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGAEBV?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>> const &)
0x140076544  mov     ecx, [rbp+1D0h+dwErrCode]; dwErrCode
0x14007654a  call    cs:__imp_SetLastError
0x140076550  mov     ebx, [rbp+1D0h+dwErrCode]
0x140076556  lea     rcx, [rsp+2D0h+var_290]
0x14007655b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140076560  nop
0x140076561  lea     rcx, [rsp+2D0h+var_288]
0x140076566  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14007656b  mov     eax, ebx
0x14007656d  jmp     loc_140076AEC
0x140076572  mov     ecx, 1; dwMilliseconds
0x140076577  call    cs:__imp_Sleep
0x14007657d  call    cs:__imp_GetCurrentThread
0x140076583  mov     rcx, rax; hThread
0x140076586  call    cs:__imp_GetThreadPriority
0x14007658c  mov     r9d, eax
0x14007658f  lea     r8, aCpuEncryptionT; "CPU Encryption thread priority changed "...
0x140076596  mov     edx, 0A4h
0x14007659b  lea     rcx, aBaseWinsatCpuE; "base\\winsat\\cpu\\encryption.cpp"
0x1400765a2  call    Log_Text_F
0x1400765a7  mov     rax, [rdi+350h]
0x1400765ae  mov     ecx, [rax+20F0h]
0x1400765b4  test    ecx, ecx
0x1400765b6  jz      loc_140076AE7
0x1400765bc  xor     edx, edx
0x1400765be  mov     eax, [rdi+3E8h]
0x1400765c4  div     ecx
0x1400765c6  mov     [rdi+3D0h], eax
0x1400765cc  mov     edx, eax; unsigned int
0x1400765ce  mov     rcx, rdi; this
0x1400765d1  call    ?SetupCryptoContext@EncryptionWorkload@WinSAT@@AEAAKK@Z; WinSAT::EncryptionWorkload::SetupCryptoContext(ulong)
0x1400765d6  mov     ebx, eax
0x1400765d8  test    eax, eax
0x1400765da  jz      loc_1400766C4
0x1400765e0  mov     [rbp+1D0h+dwErrCode], eax
0x1400765e6  mov     [rbp+1D0h+var_4C], 1
0x1400765ed  mov     [rbp+1D0h+var_48], 0
0x1400765f8  lea     rcx, [rbp+1D0h+Buffer]; lpBuffer
0x1400765fc  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140076601  mov     rcx, [rdi+20h]
0x140076605  lock inc dword ptr [rcx]
0x140076608  mov     rcx, [rdi+50h]; lpCriticalSection
0x14007660c  call    cs:__imp_EnterCriticalSection
0x140076612  mov     edx, 212h; unsigned __int16
0x140076617  lea     rcx, [rsp+2D0h+var_280]; this
0x14007661c  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x140076621  mov     rdx, rax
0x140076624  lea     rcx, [rsp+2D0h+var_288]
0x140076629  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x14007662e  nop
0x14007662f  mov     edx, 400h
0x140076634  lea     rcx, [rsp+2D0h+var_290]
0x140076639  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x14007663e  nop
0x14007663f  mov     r8d, [rdi+58h]
0x140076643  mov     rdx, [rsp+2D0h+var_288]
0x140076648  mov     rdx, [rdx+18h]
0x14007664c  lea     rcx, [rsp+2D0h+var_290]
0x140076651  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x140076656  mov     rcx, [rdi+10h]
0x14007665a  add     rcx, 0F0h
0x140076661  lea     rdx, [rsp+2D0h+var_290]
0x140076666  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007666b  mov     rcx, rax
0x14007666e  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140076673  lea     rdx, [rbp+1D0h+Buffer]
0x140076677  mov     rcx, rax
0x14007667a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007667f  mov     rcx, rax
0x140076682  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140076687  mov     rcx, [rdi+50h]; lpCriticalSection
0x14007668b  call    cs:__imp_LeaveCriticalSection
0x140076691  lea     rcx, [rdi+60h]
0x140076695  mov     r9d, ebx
0x140076698  mov     r8, [rsp+2D0h+var_290]
0x14007669d  mov     r8, [r8+18h]
0x1400766a1  mov     edx, 5
0x1400766a6  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGK@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,ulong)
0x1400766ab  mov     ecx, ebx; dwErrCode
0x1400766ad  call    cs:__imp_SetLastError
0x1400766b3  nop
0x1400766b4  lea     rcx, [rsp+2D0h+var_290]
0x1400766b9  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400766be  nop
0x1400766bf  jmp     loc_140076561
0x1400766c4  mov     r8, [rdi+350h]
0x1400766cb  mov     al, [r8+20B9h]
0x1400766d2  neg     al
0x1400766d4  sbb     esi, esi
0x1400766d6  and     esi, 0FFFFFE00h
0x1400766dc  add     esi, 204h
0x1400766e2  lea     r14, [rdi+3F8h]
0x1400766e9  lea     rcx, [rdi+358h]; this
0x1400766f0  mov     [rsp+2D0h+flProtect], esi; flProtect
0x1400766f4  mov     eax, [rdi+400h]
0x1400766fa  mov     [rsp+2D0h+var_2A0], eax; int
0x1400766fe  mov     [rsp+2D0h+var_2B0], r14; __int64
0x140076703  xor     r9d, r9d
0x140076706  mov     r8d, [r8+20F0h]
0x14007670d  mov     edx, [rdi+3E8h]
0x140076713  call    ?CreateRB@RotatingBuffer@@QEAAJKKKAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@HHK@Z; RotatingBuffer::CreateRB(ulong,ulong,ulong,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,int,int,ulong)
0x140076718  test    eax, eax
0x14007671a  jns     short loc_14007672B
0x14007671c  mov     edx, eax; int
0x14007671e  mov     rcx, rdi; this
0x140076721  call    ?DumpCreateRBError@EncryptionWorkload@WinSAT@@AEAAKJ@Z; WinSAT::EncryptionWorkload::DumpCreateRBError(long)
0x140076726  jmp     loc_140076AEC
0x14007672b  mov     ecx, [rdi+378h]
0x140076731  imul    ecx, [rdi+35Ch]
0x140076738  add     rcx, [rdi+370h]
0x14007673f  mov     [rdi+3D8h], rcx
0x140076746  mov     ebx, [rdi+400h]
0x14007674c  lea     rcx, [rsp+2D0h+var_288]
0x140076751  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x140076756  nop
0x140076757  mov     r8, [rdi+350h]
0x14007675e  lea     rcx, [rdi+388h]; this
0x140076765  mov     [rsp+2D0h+flProtect], esi; flProtect
0x140076769  mov     [rsp+2D0h+var_2A0], ebx; int
0x14007676d  mov     [rsp+2D0h+var_2B0], rax; __int64
0x140076772  mov     r9d, [rdi+3ECh]
0x140076779  mov     r8d, [r8+20F0h]
0x140076780  mov     edx, [rdi+3E8h]
0x140076786  call    ?CreateRB@RotatingBuffer@@QEAAJKKKAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@HHK@Z; RotatingBuffer::CreateRB(ulong,ulong,ulong,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,int,int,ulong)
0x14007678b  mov     ebx, eax
0x14007678d  lea     rcx, [rsp+2D0h+var_288]
0x140076792  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140076797  test    ebx, ebx
0x140076799  jns     short loc_1400767A2
0x14007679b  mov     edx, ebx
0x14007679d  jmp     loc_14007671E
0x1400767a2  mov     ecx, [rdi+3A8h]
0x1400767a8  imul    ecx, [rdi+38Ch]
0x1400767af  add     rcx, [rdi+3A0h]
0x1400767b6  mov     [rdi+3E0h], rcx
0x1400767bd  mov     rcx, [rdi+350h]
0x1400767c4  add     rcx, 28h ; '('
0x1400767c8  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x1400767cd  mov     rax, [rax]
0x1400767d0  mov     [rdi+348h], rax
0x1400767d7  cmp     byte ptr [rdi+18h], 0
0x1400767db  jz      loc_140076AE3
0x1400767e1  mov     rcx, [rdi+50h]; lpCriticalSection
0x1400767e5  call    cs:__imp_EnterCriticalSection
0x1400767eb  mov     rcx, [rdi+8]
0x1400767ef  mov     esi, 0F0h
0x1400767f4  add     rcx, rsi
0x1400767f7  lea     rdx, aCpu; "> CPU("
0x1400767fe  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140076803  mov     edx, [rdi+58h]
0x140076806  mov     rcx, rax
0x140076809  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14007680e  mov     rcx, rax
0x140076811  lea     rdx, asc_140141108; ")  "
0x140076818  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007681d  mov     rcx, rax
0x140076820  lea     rdx, aTid_0; "TID: "
0x140076827  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007682c  mov     dword ptr [rsp+2D0h+var_290], 4
0x140076834  lea     rdx, [rsp+2D0h+var_290]
0x140076839  mov     rcx, rax
0x14007683c  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzrightobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzrightobj const &)
0x140076841  mov     rbx, rax
0x140076844  call    cs:__imp_GetCurrentThreadId
0x14007684a  mov     edx, eax
0x14007684c  mov     rcx, rbx
0x14007684f  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140076854  mov     rcx, [rax]
0x140076857  movsxd  rdx, dword ptr [rcx+4]
0x14007685b  mov     ebx, 201h
0x140076860  or      [rdx+rax+18h], ebx
0x140076864  mov     rcx, [rax]
0x140076867  movsxd  rdx, dword ptr [rcx+4]
0x14007686b  mov     r12d, 20h ; ' '
0x140076871  mov     [rdx+rax+58h], r12w
0x140076877  mov     rcx, [rax]
0x14007687a  movsxd  rdx, dword ptr [rcx+4]
0x14007687e  mov     qword ptr [rdx+rax+28h], 0
0x140076887  lea     rdx, aRunningAt_0; "\n  -- Running at "
0x14007688e  mov     rcx, rax
0x140076891  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140076896  mov     rcx, [rdi+350h]
0x14007689d  lea     r8, aHigh; "HIGH"
0x1400768a4  lea     rdx, aNormal_1; "NORMAL"
0x1400768ab  cmp     byte ptr [rcx+20B8h], 0
0x1400768b2  cmovz   rdx, r8
0x1400768b6  mov     rcx, rax
0x1400768b9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400768be  mov     rcx, rax
0x1400768c1  lea     rdx, aPriority_0; " priority"
0x1400768c8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400768cd  mov     rcx, rax
0x1400768d0  lea     rdx, aInputBufferSiz; "\n  -- Input Buffer Size ="
0x1400768d7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400768dc  mov     edx, [rdi+3E8h]
0x1400768e2  mov     rcx, rax
0x1400768e5  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x1400768ea  mov     rcx, rax
0x1400768ed  lea     rdx, a0x_0; " (0x"
0x1400768f4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400768f9  mov     dword ptr [rsp+2D0h+var_290], 4
0x140076901  lea     rdx, [rsp+2D0h+var_290]
0x140076906  mov     rcx, rax
0x140076909  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzhexobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzhexobj const &)
0x14007690e  mov     edx, [rdi+3E8h]
0x140076914  mov     rcx, rax
0x140076917  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14007691c  mov     rcx, [rax]
0x14007691f  movsxd  rdx, dword ptr [rcx+4]
0x140076923  or      [rdx+rax+18h], ebx
0x140076927  mov     rcx, [rax]
0x14007692a  movsxd  rdx, dword ptr [rcx+4]
0x14007692e  mov     [rdx+rax+58h], r12w
0x140076934  mov     rcx, [rax]
0x140076937  movsxd  rdx, dword ptr [rcx+4]
0x14007693b  mov     qword ptr [rdx+rax+28h], 0
0x140076944  lea     rdx, aBytes_3; ") bytes"
0x14007694b  mov     rcx, rax
0x14007694e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140076953  mov     rcx, rax
0x140076956  lea     rdx, aCypherBlockSiz; "\n  -- Cypher Block Size ="
0x14007695d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140076962  mov     edx, [rdi+3ECh]
0x140076968  mov     rcx, rax
0x14007696b  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140076970  mov     rcx, rax
0x140076973  lea     rdx, aNumRegions; "\n  -- Num regions = "
0x14007697a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007697f  mov     rdx, [rdi+350h]
0x140076986  mov     edx, [rdx+20F0h]
0x14007698c  mov     rcx, rax
  ... truncated ...
```
