# EnumeratePlatformInfo(mlib::XmlStream &)

- ea: `0x1400297f4`
- end: `0x140029bf5`
- name: `?EnumeratePlatformInfo@@YAHAEAVXmlStream@mlib@@@Z`
- size: `1025`
- prototype: `__int64 __fastcall(struct mlib::XmlStream *this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d91c`
- `0x14002b890`

## callees

- `0x140004348`
- `0x14000449c`
- `0x140005d78`
- `0x140008064`
- `0x14000a664`
- `0x14000a6a4`
- `0x14000db70`
- `0x140016d04`
- `0x1400297f4`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140029890`
- `KERNEL32!GetProcAddress` at `0x140029890`
- `KERNEL32!LoadLibraryW` at `0x14002987b`
- `KERNEL32!LoadLibraryW` at `0x14002987b`
- `KERNEL32!GetLastError` at `0x14002989b`
- `KERNEL32!GetLastError` at `0x14002989b`
- `KERNEL32!SetLastError` at `0x1400298ac`
- `KERNEL32!SetLastError` at `0x1400298ac`

## string_xrefs

- `0x140029874`: `powrprof.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EnumeratePlatformInfo(struct mlib::XmlStream *this)
{
  __int64 v2; // rax
  HMODULE LibraryW; // rax
  __int64 (*ProcAddress)(void); // rax
  unsigned int v5; // esi
  __int64 v6; // rax
  const wchar_t *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  const wchar_t *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  const wchar_t *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  const wchar_t *v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  char v24; // [rsp+50h] [rbp+30h] BYREF
  char v25; // [rsp+58h] [rbp+38h] BYREF
  char v26; // [rsp+60h] [rbp+40h] BYREF

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v24,
    L"Platform");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v2, &v24);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
  LibraryW = LoadLibraryW(L"powrprof.dll");
  if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "PowerDeterminePlatformRole")) != 0 )
  {
    v5 = ProcAddress();
  }
  else
  {
    if ( GetLastError() )
      goto LABEL_43;
    SetLastError(0x32u);
    v5 = 0;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v25,
    L"IsMobile");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v6, &v25);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  mlib::XmlStream::BeforeText(this);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)this, v5 == 2);
  mlib::XmlStream::AfterText(this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v24,
    L"IsMobile");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent(this);
    *((_BYTE *)this + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v9, &v24);
    v8 = v10;
    v7 = L">";
  }
  else
  {
    if ( *((_DWORD *)this + 2) != 2 )
      goto LABEL_17;
    v7 = L"/>";
    v8 = *(_QWORD *)this;
  }
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, v7);
LABEL_17:
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v25);
  if ( v5 )
  {
    switch ( v5 )
    {
      case 1u:
        v11 = L"Desktop";
        goto LABEL_33;
      case 2u:
        v11 = L"Mobile";
        goto LABEL_33;
      case 3u:
        v11 = L"Workstation";
        goto LABEL_33;
      case 4u:
        v11 = L"Enterprise Server";
        goto LABEL_33;
      case 5u:
        v11 = L"SOHO Server";
        goto LABEL_33;
      case 6u:
        v11 = L"Appliance PC";
        goto LABEL_33;
      case 7u:
        v11 = L"Performance Server";
        goto LABEL_33;
    }
  }
  v11 = L"Unknown";
  v5 = 0;
LABEL_33:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v26,
    L"PlatformRole");
  if ( *((_DWORD *)this + 2) == 2 )
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L">");
  *((_DWORD *)this + 2) = 2;
  mlib::XmlStream::Indent(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"<");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v12, &v26);
  ++*((_DWORD *)this + 3);
  *((_BYTE *)this + 17) = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v25,
    L"desc");
  *((_DWORD *)this + 2) = 3;
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L" ");
  mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v13, &v25);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v14, L"=");
  mlib::XmlStream::BeforeText(this);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, v11);
  mlib::XmlStream::AfterText(this);
  mlib::XmlStream::BeforeText(this);
  std::basic_ostream<unsigned short>::operator<<(*(_QWORD *)this, v5);
  mlib::XmlStream::AfterText(this);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v24,
    L"PlatformRole");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent(this);
    *((_BYTE *)this + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v17, &v24);
    v16 = v18;
    v15 = L">";
    goto LABEL_41;
  }
  if ( *((_DWORD *)this + 2) == 2 )
  {
    v15 = L"/>";
    v16 = *(_QWORD *)this;
LABEL_41:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v16, v15);
  }
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v25);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v26);
LABEL_43:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v24,
    L"Platform");
  --*((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == 1 )
  {
    if ( !*((_BYTE *)this + 17) )
      mlib::XmlStream::Indent(this);
    *((_BYTE *)this + 17) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(*(_QWORD *)this, L"</");
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v21, &v24);
    v20 = v22;
    v19 = L">";
    goto LABEL_49;
  }
  if ( *((_DWORD *)this + 2) == 2 )
  {
    v19 = L"/>";
    v20 = *(_QWORD *)this;
LABEL_49:
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, v19);
  }
  *((_DWORD *)this + 2) = 1;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
  return 1;
}

```

## disassembly

```asm
0x1400297f4  mov     [rsp-28h+arg_18], rbx
0x1400297f9  push    rbp
0x1400297fa  push    rsi
0x1400297fb  push    rdi
0x1400297fc  push    r12
0x1400297fe  push    r15
0x140029800  mov     rbp, rsp
0x140029803  sub     rsp, 20h
0x140029807  mov     rbx, rcx
0x14002980a  lea     rdx, aPlatform; "Platform"
0x140029811  lea     rcx, [rbp+arg_0]
0x140029815  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002981a  nop
0x14002981b  lea     r12, asc_14012B480; ">"
0x140029822  cmp     dword ptr [rbx+8], 2
0x140029826  jnz     short loc_140029833
0x140029828  mov     rdx, r12
0x14002982b  mov     rcx, [rbx]
0x14002982e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029833  mov     dword ptr [rbx+8], 2
0x14002983a  mov     rcx, rbx; this
0x14002983d  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140029842  lea     rdx, asc_14012B484; "<"
0x140029849  mov     rcx, [rbx]
0x14002984c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029851  mov     rcx, rax
0x140029854  lea     rdx, [rbp+arg_0]
0x140029858  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002985d  mov     r15d, 1
0x140029863  add     [rbx+0Ch], r15d
0x140029867  mov     byte ptr [rbx+11h], 0
0x14002986b  lea     rcx, [rbp+arg_0]
0x14002986f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140029874  lea     rcx, aPowrprofDll; "powrprof.dll"
0x14002987b  call    cs:__imp_LoadLibraryW
0x140029881  test    rax, rax
0x140029884  jz      short loc_14002989B
0x140029886  lea     rdx, ProcName; "PowerDeterminePlatformRole"
0x14002988d  mov     rcx, rax; hModule
0x140029890  call    cs:__imp_GetProcAddress
0x140029896  test    rax, rax
0x140029899  jnz     short loc_1400298B6
0x14002989b  call    cs:__imp_GetLastError
0x1400298a1  test    eax, eax
0x1400298a3  jnz     loc_140029B6F
0x1400298a9  lea     ecx, [rax+32h]; dwErrCode
0x1400298ac  call    cs:__imp_SetLastError
0x1400298b2  xor     esi, esi
0x1400298b4  jmp     short loc_1400298BD
0x1400298b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400298bb  mov     esi, eax
0x1400298bd  lea     rdx, aIsmobile; "IsMobile"
0x1400298c4  lea     rcx, [rbp+arg_8]
0x1400298c8  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x1400298cd  nop
0x1400298ce  cmp     dword ptr [rbx+8], 2
0x1400298d2  jnz     short loc_1400298DF
0x1400298d4  mov     rdx, r12
0x1400298d7  mov     rcx, [rbx]
0x1400298da  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400298df  mov     dword ptr [rbx+8], 2
0x1400298e6  mov     rcx, rbx; this
0x1400298e9  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x1400298ee  lea     rdx, asc_14012B484; "<"
0x1400298f5  mov     rcx, [rbx]
0x1400298f8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400298fd  mov     rcx, rax
0x140029900  lea     rdx, [rbp+arg_8]
0x140029904  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140029909  add     [rbx+0Ch], r15d
0x14002990d  mov     byte ptr [rbx+11h], 0
0x140029911  mov     rcx, rbx; this
0x140029914  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140029919  xor     edx, edx
0x14002991b  cmp     esi, 2
0x14002991e  setz    dl
0x140029921  mov     rcx, [rbx]
0x140029924  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x140029929  mov     rcx, rbx; this
0x14002992c  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140029931  lea     rdx, aIsmobile; "IsMobile"
0x140029938  lea     rcx, [rbp+arg_0]
0x14002993c  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140029941  nop
0x140029942  dec     dword ptr [rbx+0Ch]
0x140029945  mov     ecx, [rbx+8]
0x140029948  sub     ecx, 1
0x14002994b  jz      short loc_14002995E
0x14002994d  cmp     ecx, 1
0x140029950  jnz     short loc_140029996
0x140029952  lea     rdx, asc_14012B488; "/>"
0x140029959  mov     rcx, [rbx]
0x14002995c  jmp     short loc_140029991
0x14002995e  cmp     byte ptr [rbx+11h], 0
0x140029962  jnz     short loc_14002996C
0x140029964  mov     rcx, rbx; this
0x140029967  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x14002996c  mov     byte ptr [rbx+11h], 0
0x140029970  lea     rdx, asc_14012B490; "</"
0x140029977  mov     rcx, [rbx]
0x14002997a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002997f  mov     rcx, rax
0x140029982  lea     rdx, [rbp+arg_0]
0x140029986  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14002998b  mov     rcx, rax
0x14002998e  mov     rdx, r12
0x140029991  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029996  mov     [rbx+8], r15d
0x14002999a  lea     rcx, [rbp+arg_0]
0x14002999e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400299a3  nop
0x1400299a4  lea     rcx, [rbp+arg_8]
0x1400299a8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400299ad  mov     ecx, esi
0x1400299af  test    esi, esi
0x1400299b1  jz      short loc_140029A15
0x1400299b3  sub     ecx, 1
0x1400299b6  jz      short loc_140029A0C
0x1400299b8  sub     ecx, 1
0x1400299bb  jz      short loc_140029A03
0x1400299bd  sub     ecx, 1
0x1400299c0  jz      short loc_1400299FA
0x1400299c2  sub     ecx, 1
0x1400299c5  jz      short loc_1400299F1
0x1400299c7  sub     ecx, 1
0x1400299ca  jz      short loc_1400299E8
0x1400299cc  sub     ecx, 1
0x1400299cf  jz      short loc_1400299DF
0x1400299d1  cmp     ecx, 1
0x1400299d4  jnz     short loc_140029A15
0x1400299d6  lea     rdi, aPerformanceSer; "Performance Server"
0x1400299dd  jmp     short loc_140029A1E
0x1400299df  lea     rdi, aAppliancePc; "Appliance PC"
0x1400299e6  jmp     short loc_140029A1E
0x1400299e8  lea     rdi, aSohoServer; "SOHO Server"
0x1400299ef  jmp     short loc_140029A1E
0x1400299f1  lea     rdi, aEnterpriseServ; "Enterprise Server"
0x1400299f8  jmp     short loc_140029A1E
0x1400299fa  lea     rdi, aWorkstation; "Workstation"
0x140029a01  jmp     short loc_140029A1E
0x140029a03  lea     rdi, aMobile; "Mobile"
0x140029a0a  jmp     short loc_140029A1E
0x140029a0c  lea     rdi, aDesktop; "Desktop"
0x140029a13  jmp     short loc_140029A1E
0x140029a15  lea     rdi, aUnknown_1; "Unknown"
0x140029a1c  xor     esi, esi
0x140029a1e  lea     rdx, aPlatformrole; "PlatformRole"
0x140029a25  lea     rcx, [rbp+arg_10]
0x140029a29  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140029a2e  nop
0x140029a2f  cmp     dword ptr [rbx+8], 2
0x140029a33  jnz     short loc_140029A40
0x140029a35  mov     rdx, r12
0x140029a38  mov     rcx, [rbx]
0x140029a3b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029a40  mov     dword ptr [rbx+8], 2
0x140029a47  mov     rcx, rbx; this
0x140029a4a  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140029a4f  lea     rdx, asc_14012B484; "<"
0x140029a56  mov     rcx, [rbx]
0x140029a59  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029a5e  mov     rcx, rax
0x140029a61  lea     rdx, [rbp+arg_10]
0x140029a65  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140029a6a  add     [rbx+0Ch], r15d
0x140029a6e  mov     byte ptr [rbx+11h], 0
0x140029a72  lea     rdx, aDesc; "desc"
0x140029a79  lea     rcx, [rbp+arg_8]
0x140029a7d  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140029a82  nop
0x140029a83  mov     dword ptr [rbx+8], 3
0x140029a8a  lea     rdx, asc_14012B49C; " "
0x140029a91  mov     rcx, [rbx]
0x140029a94  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029a99  mov     rcx, rax
0x140029a9c  lea     rdx, [rbp+arg_8]
0x140029aa0  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140029aa5  mov     rcx, rax
0x140029aa8  lea     rdx, asc_14012B498; "="
0x140029aaf  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029ab4  mov     rcx, rbx; this
0x140029ab7  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140029abc  mov     rdx, rdi
0x140029abf  mov     rcx, [rbx]
0x140029ac2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029ac7  mov     rcx, rbx; this
0x140029aca  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140029acf  mov     rcx, rbx; this
0x140029ad2  call    ?BeforeText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::BeforeText(void)
0x140029ad7  mov     edx, esi
0x140029ad9  mov     rcx, [rbx]
0x140029adc  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x140029ae1  mov     rcx, rbx; this
0x140029ae4  call    ?AfterText@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::AfterText(void)
0x140029ae9  lea     rdx, aPlatformrole; "PlatformRole"
0x140029af0  lea     rcx, [rbp+arg_0]
0x140029af4  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140029af9  nop
0x140029afa  dec     dword ptr [rbx+0Ch]
0x140029afd  mov     ecx, [rbx+8]
0x140029b00  sub     ecx, 1
0x140029b03  jz      short loc_140029B16
0x140029b05  cmp     ecx, 1
0x140029b08  jnz     short loc_140029B4E
0x140029b0a  lea     rdx, asc_14012B488; "/>"
0x140029b11  mov     rcx, [rbx]
0x140029b14  jmp     short loc_140029B49
0x140029b16  cmp     byte ptr [rbx+11h], 0
0x140029b1a  jnz     short loc_140029B24
0x140029b1c  mov     rcx, rbx; this
0x140029b1f  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140029b24  mov     byte ptr [rbx+11h], 0
0x140029b28  lea     rdx, asc_14012B490; "</"
0x140029b2f  mov     rcx, [rbx]
0x140029b32  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029b37  mov     rcx, rax
0x140029b3a  lea     rdx, [rbp+arg_0]
0x140029b3e  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140029b43  mov     rcx, rax
0x140029b46  mov     rdx, r12
0x140029b49  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029b4e  mov     [rbx+8], r15d
0x140029b52  lea     rcx, [rbp+arg_0]
0x140029b56  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140029b5b  nop
0x140029b5c  lea     rcx, [rbp+arg_8]
0x140029b60  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140029b65  nop
0x140029b66  lea     rcx, [rbp+arg_10]
0x140029b6a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140029b6f  lea     rdx, aPlatform; "Platform"
0x140029b76  lea     rcx, [rbp+arg_0]
0x140029b7a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140029b7f  nop
0x140029b80  dec     dword ptr [rbx+0Ch]
0x140029b83  mov     ecx, [rbx+8]
0x140029b86  sub     ecx, 1
0x140029b89  jz      short loc_140029B9C
0x140029b8b  cmp     ecx, 1
0x140029b8e  jnz     short loc_140029BD4
0x140029b90  lea     rdx, asc_14012B488; "/>"
0x140029b97  mov     rcx, [rbx]
0x140029b9a  jmp     short loc_140029BCF
0x140029b9c  cmp     byte ptr [rbx+11h], 0
0x140029ba0  jnz     short loc_140029BAA
0x140029ba2  mov     rcx, rbx; this
0x140029ba5  call    ?Indent@XmlStream@mlib@@AEAAXXZ; mlib::XmlStream::Indent(void)
0x140029baa  mov     byte ptr [rbx+11h], 0
0x140029bae  lea     rdx, asc_14012B490; "</"
0x140029bb5  mov     rcx, [rbx]
0x140029bb8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029bbd  mov     rcx, rax
0x140029bc0  lea     rdx, [rbp+arg_0]
0x140029bc4  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140029bc9  mov     rcx, rax
0x140029bcc  mov     rdx, r12
0x140029bcf  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140029bd4  mov     [rbx+8], r15d
0x140029bd8  lea     rcx, [rbp+arg_0]
0x140029bdc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140029be1  mov     eax, r15d
0x140029be4  mov     rbx, [rsp+20h+arg_18]
0x140029be9  add     rsp, 20h
0x140029bed  pop     r15
0x140029bef  pop     r12
0x140029bf1  pop     rdi
0x140029bf2  pop     rsi
0x140029bf3  pop     rbp
0x140029bf4  retn
```
