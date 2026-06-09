# RfbFileFolderWmiQuery::CreatePidl(_MI_Instance const *,wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &)

- ea: `0x180014570`
- end: `0x180014908`
- name: `?CreatePidl@RfbFileFolderWmiQuery@@MEAAXPEBU_MI_Instance@@AEAV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(__int64, const struct _MI_Instance *, void **)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002030`
- `0x18000591c`
- `0x180007150`
- `0x180007c70`
- `0x1800092f0`
- `0x18000937c`
- `0x1800095d4`
- `0x180010a80`
- `0x180010bec`
- `0x180010d00`
- `0x1800135b0`
- `0x1800144c0`
- `0x180014570`
- `0x180019010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014616`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014616`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800145aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800145aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148ae`

## string_xrefs

- `0x1800146df`: `Compressed`
- `0x18001460c`: `Win32_Directory`
- `0x180014652`: `Extension`
- `0x180014729`: `Writeable`
- `0x180014808`: `LastAccessed`

## pseudocode

```c
__int64 __fastcall RfbFileFolderWmiQuery::CreatePidl(__int64 a1, const struct _MI_Instance *a2, void **a3)
{
  void *v6; // rcx
  enum _MI_Result v7; // eax
  int v8; // eax
  __int64 v9; // r8
  int v10; // esi
  __int128 *v11; // rcx
  char v12; // al
  int v13; // ecx
  __int64 result; // rax
  const char *v15; // r9
  _QWORD *v16; // rax
  char *Pidl; // rax
  void *v18; // rcx
  int v19; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+28h] [rbp-A0h] BYREF
  __int128 v21; // [rsp+30h] [rbp-98h] BYREF
  __int64 v22; // [rsp+40h] [rbp-88h]
  unsigned __int64 v23; // [rsp+48h] [rbp-80h]
  unsigned __int64 v24[2]; // [rsp+50h] [rbp-78h] BYREF
  __int128 v25; // [rsp+60h] [rbp-68h] BYREF
  __int128 v26; // [rsp+70h] [rbp-58h] BYREF
  _OWORD Src[2]; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v6 = *a3;
  *a3 = 0;
  if ( v6 )
    CoTaskMemFree(v6);
  try
  {
    *(_OWORD *)v24 = 0;
    v25 = 0;
    v26 = 0;
    v20 = 0;
    if ( a2 && a2->ft )
      v7 = ((unsigned int (__fastcall *)(const struct _MI_Instance *, __int64 *))a2->ft->GetClassNameA)(a2, &v20);
    else
      v7 = MI_RESULT_INVALID_PARAMETER;
    v8 = MiResultToHRESULT(v7);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbfilefolderwmiquery.cpp",
        (const char *)(unsigned int)v8,
        v19);
    v10 = _o__wcsicmp(v9, L"Win32_Directory");
    LODWORD(v24[0]) = (v10 != 0) + 2;
    v21 = 0;
    v22 = 0;
    v23 = 7;
    LOWORD(v21) = 0;
    if ( !(unsigned __int8)RfbWmiQuery::GetNullableProperty(a2, L"Extension", &v21) )
    {
      v11 = &v21;
      if ( v23 > 7 )
        v11 = (__int128 *)v21;
      v22 = 0;
      *(_WORD *)v11 = 0;
    }
    if ( !v10 )
      LODWORD(v25) = v25 | 0x10;
    LOBYTE(v19) = 0;
    if ( RfbWmiQuery::GetNullableProperty(a2, L"Hidden", (bool *)&v19) && (_BYTE)v19 )
      LODWORD(v25) = v25 | 2;
    if ( RfbWmiQuery::GetNullableProperty(a2, L"Archive", (bool *)&v19) && (_BYTE)v19 )
      LODWORD(v25) = v25 | 0x20;
    if ( RfbWmiQuery::GetNullableProperty(a2, L"Compressed", (bool *)&v19) && (_BYTE)v19 )
      LODWORD(v25) = v25 | 0x800;
    if ( RfbWmiQuery::GetNullableProperty(a2, L"Encrypted", (bool *)&v19) && (_BYTE)v19 )
      LODWORD(v25) = v25 | 0x4000;
    if ( RfbWmiQuery::GetNullableProperty(a2, L"Writeable", (bool *)&v19) && !(_BYTE)v19 )
      LODWORD(v25) = v25 | 1;
    if ( RfbWmiQuery::GetNullableProperty(a2, L"System", (bool *)&v19) && (_BYTE)v19 )
    {
      v12 = v25 | 4;
      LODWORD(v25) = v25 | 4;
    }
    else
    {
      v12 = v25;
    }
    v13 = *(_DWORD *)(a1 + 64);
    if ( (v12 & 0x10) != 0 )
    {
      if ( (v13 & 0x820) == 0 )
        return std::wstring::~wstring((char **)&v21);
    }
    else if ( (v13 & 0x40) == 0 )
    {
      return std::wstring::~wstring((char **)&v21);
    }
    if ( (v12 & 6) != 0 && (v13 & 0x10000) == 0 || (v12 & 2) != 0 && (v13 & 0x80u) == 0 )
      return std::wstring::~wstring((char **)&v21);
    RfbWmiQuery::GetNullableProperty(a2, L"FileSize", &v24[1]);
    RfbWmiQuery::GetProperty<_FILETIME>(a2, L"CreationDate", (char *)&v25 + 4);
    RfbWmiQuery::GetProperty<_FILETIME>(a2, L"LastAccessed", (char *)&v25 + 12);
    RfbWmiQuery::GetProperty<_FILETIME>(a2, L"LastModified", (char *)&v26 + 4);
    Src[0] = 0;
    Src[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src[0]) = 0;
    RfbWmiQuery::GetProperty<std::wstring>(a2, L"FileName", Src);
    if ( v22 )
    {
      v16 = std::wstring::append(Src, L".");
      std::wstring::append(v16, &v21);
    }
    Pidl = RfbPidlHelper<FileFixedData>::CreatePidl(Src, v24);
    v18 = *a3;
    *a3 = Pidl;
    if ( v18 )
      CoTaskMemFree(v18);
    std::wstring::~wstring((char **)Src);
    result = std::wstring::~wstring((char **)&v21);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0xDE,
             (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbfilefolderwmiquery.cpp",
             v15);
  }
  return result;
}

```

## disassembly

```asm
0x180014570  mov     [rsp+arg_0], rbx
0x180014575  push    rsi
0x180014576  push    rdi
0x180014577  push    r14
0x180014579  sub     rsp, 0B0h
0x180014580  mov     rax, cs:__security_cookie
0x180014587  xor     rax, rsp
0x18001458a  mov     [rsp+0C8h+var_28], rax
0x180014592  mov     rdi, r8
0x180014595  mov     rbx, rdx
0x180014598  mov     r14, rcx
0x18001459b  mov     rcx, [r8]; pv
0x18001459e  mov     qword ptr [r8], 0
0x1800145a5  test    rcx, rcx
0x1800145a8  jz      short loc_1800145B1
0x1800145aa  call    cs:__imp_CoTaskMemFree
0x1800145b0  nop
0x1800145b1  xorps   xmm0, xmm0
0x1800145b4  movups  xmmword ptr [rsp+0C8h+var_78], xmm0
0x1800145b9  movups  [rsp+0C8h+var_68], xmm0
0x1800145be  movups  [rsp+0C8h+var_58], xmm0
0x1800145c3  xor     r8d, r8d
0x1800145c6  mov     [rsp+0C8h+var_A0], r8
0x1800145cb  test    rbx, rbx
0x1800145ce  jz      short loc_1800145F0
0x1800145d0  mov     rax, [rbx]
0x1800145d3  test    rax, rax
0x1800145d6  jz      short loc_1800145F0
0x1800145d8  lea     rdx, [rsp+0C8h+var_A0]
0x1800145dd  mov     rcx, rbx
0x1800145e0  mov     rax, [rax+20h]
0x1800145e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145e9  mov     r8, [rsp+0C8h+var_A0]
0x1800145ee  jmp     short loc_1800145F5
0x1800145f0  mov     eax, 4
0x1800145f5  mov     ecx, eax; enum _MI_Result
0x1800145f7  call    ?MiResultToHRESULT@@YAJW4_MI_Result@@@Z; MiResultToHRESULT(_MI_Result)
0x1800145fc  mov     rcx, [rsp+0C8h]; this
0x180014604  test    eax, eax
0x180014606  js      loc_1800148F2
0x18001460c  lea     rdx, aWin32Directory; "Win32_Directory"
0x180014613  mov     rcx, r8
0x180014616  call    cs:__imp__o__wcsicmp
0x18001461c  mov     esi, eax
0x18001461e  xor     ecx, ecx
0x180014620  test    eax, eax
0x180014622  setnz   cl
0x180014625  add     ecx, 2
0x180014628  mov     dword ptr [rsp+0C8h+var_78], ecx
0x18001462c  xorps   xmm0, xmm0
0x18001462f  movups  [rsp+0C8h+var_98], xmm0
0x180014634  mov     [rsp+0C8h+var_88], 0
0x18001463d  mov     [rsp+0C8h+var_80], 7
0x180014646  xor     ecx, ecx
0x180014648  mov     word ptr [rsp+0C8h+var_98], cx
0x18001464d  lea     r8, [rsp+0C8h+var_98]
0x180014652  lea     rdx, aExtension; "Extension"
0x180014659  mov     rcx, rbx
0x18001465c  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,std::wstring *)
0x180014661  test    al, al
0x180014663  jnz     short loc_180014684
0x180014665  lea     rcx, [rsp+0C8h+var_98]
0x18001466a  cmp     [rsp+0C8h+var_80], 7
0x180014670  cmova   rcx, qword ptr [rsp+0C8h+var_98]
0x180014676  mov     [rsp+0C8h+var_88], 0
0x18001467f  xor     eax, eax
0x180014681  mov     [rcx], ax
0x180014684  test    esi, esi
0x180014686  jnz     short loc_18001468D
0x180014688  or      dword ptr [rsp+0C8h+var_68], 10h
0x18001468d  mov     byte ptr [rsp+0C8h+var_A8], 0
0x180014692  lea     r8, [rsp+0C8h+var_A8]; bool *
0x180014697  lea     rdx, aHidden; "Hidden"
0x18001469e  mov     rcx, rbx; struct _MI_Instance *
0x1800146a1  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEA_N@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,bool *)
0x1800146a6  test    al, al
0x1800146a8  jz      short loc_1800146B6
0x1800146aa  cmp     byte ptr [rsp+0C8h+var_A8], 0
0x1800146af  jz      short loc_1800146B6
0x1800146b1  or      dword ptr [rsp+0C8h+var_68], 2
0x1800146b6  lea     r8, [rsp+0C8h+var_A8]; bool *
0x1800146bb  lea     rdx, aArchive; "Archive"
0x1800146c2  mov     rcx, rbx; struct _MI_Instance *
0x1800146c5  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEA_N@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,bool *)
0x1800146ca  test    al, al
0x1800146cc  jz      short loc_1800146DA
0x1800146ce  cmp     byte ptr [rsp+0C8h+var_A8], 0
0x1800146d3  jz      short loc_1800146DA
0x1800146d5  or      dword ptr [rsp+0C8h+var_68], 20h
0x1800146da  lea     r8, [rsp+0C8h+var_A8]; bool *
0x1800146df  lea     rdx, aCompressed; "Compressed"
0x1800146e6  mov     rcx, rbx; struct _MI_Instance *
0x1800146e9  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEA_N@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,bool *)
0x1800146ee  test    al, al
0x1800146f0  jz      short loc_1800146FF
0x1800146f2  cmp     byte ptr [rsp+0C8h+var_A8], 0
0x1800146f7  jz      short loc_1800146FF
0x1800146f9  bts     dword ptr [rsp+0C8h+var_68], 0Bh
0x1800146ff  lea     r8, [rsp+0C8h+var_A8]; bool *
0x180014704  lea     rdx, aEncrypted; "Encrypted"
0x18001470b  mov     rcx, rbx; struct _MI_Instance *
0x18001470e  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEA_N@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,bool *)
0x180014713  test    al, al
0x180014715  jz      short loc_180014724
0x180014717  cmp     byte ptr [rsp+0C8h+var_A8], 0
0x18001471c  jz      short loc_180014724
0x18001471e  bts     dword ptr [rsp+0C8h+var_68], 0Eh
0x180014724  lea     r8, [rsp+0C8h+var_A8]; bool *
0x180014729  lea     rdx, aWriteable; "Writeable"
0x180014730  mov     rcx, rbx; struct _MI_Instance *
0x180014733  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEA_N@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,bool *)
0x180014738  test    al, al
0x18001473a  jz      short loc_180014748
0x18001473c  cmp     byte ptr [rsp+0C8h+var_A8], 0
0x180014741  jnz     short loc_180014748
0x180014743  or      dword ptr [rsp+0C8h+var_68], 1
0x180014748  lea     r8, [rsp+0C8h+var_A8]; bool *
0x18001474d  lea     rdx, aSystem; "System"
0x180014754  mov     rcx, rbx; struct _MI_Instance *
0x180014757  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEA_N@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,bool *)
0x18001475c  test    al, al
0x18001475e  jz      short loc_180014774
0x180014760  cmp     byte ptr [rsp+0C8h+var_A8], 0
0x180014765  jz      short loc_180014774
0x180014767  mov     eax, dword ptr [rsp+0C8h+var_68]
0x18001476b  or      eax, 4
0x18001476e  mov     dword ptr [rsp+0C8h+var_68], eax
0x180014772  jmp     short loc_180014778
0x180014774  mov     eax, dword ptr [rsp+0C8h+var_68]
0x180014778  mov     ecx, [r14+40h]
0x18001477c  test    al, 10h
0x18001477e  jz      short loc_180014797
0x180014780  test    ecx, 820h
0x180014786  jnz     short loc_1800147AB
0x180014788  lea     rcx, [rsp+0C8h+var_98]
0x18001478d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014792  jmp     loc_1800148CE
0x180014797  test    cl, 40h
0x18001479a  jnz     short loc_1800147AB
0x18001479c  lea     rcx, [rsp+0C8h+var_98]
0x1800147a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800147a6  jmp     loc_1800148CE
0x1800147ab  test    al, 6
0x1800147ad  jz      short loc_1800147C4
0x1800147af  bt      ecx, 10h
0x1800147b3  jb      short loc_1800147C4
0x1800147b5  lea     rcx, [rsp+0C8h+var_98]
0x1800147ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800147bf  jmp     loc_1800148CE
0x1800147c4  test    al, 2
0x1800147c6  jz      short loc_1800147DB
0x1800147c8  test    cl, cl
0x1800147ca  js      short loc_1800147DB
0x1800147cc  lea     rcx, [rsp+0C8h+var_98]
0x1800147d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800147d6  jmp     loc_1800148CE
0x1800147db  lea     r8, [rsp+0C8h+var_78+8]; unsigned __int64 *
0x1800147e0  lea     rdx, aFilesize; "FileSize"
0x1800147e7  mov     rcx, rbx; struct _MI_Instance *
0x1800147ea  call    ?GetNullableProperty@RfbWmiQuery@@KA_NPEBU_MI_Instance@@PEBGPEA_K@Z; RfbWmiQuery::GetNullableProperty(_MI_Instance const *,ushort const *,unsigned __int64 *)
0x1800147ef  lea     r8, [rsp+0C8h+var_68+4]
0x1800147f4  lea     rdx, aCreationdate; "CreationDate"
0x1800147fb  mov     rcx, rbx
0x1800147fe  call    ??$GetProperty@U_FILETIME@@@RfbWmiQuery@@KAXPEBU_MI_Instance@@PEBGPEAU_FILETIME@@@Z; RfbWmiQuery::GetProperty<_FILETIME>(_MI_Instance const *,ushort const *,_FILETIME *)
0x180014803  lea     r8, [rsp+0C8h+var_68+0Ch]
0x180014808  lea     rdx, aLastaccessed; "LastAccessed"
0x18001480f  mov     rcx, rbx
0x180014812  call    ??$GetProperty@U_FILETIME@@@RfbWmiQuery@@KAXPEBU_MI_Instance@@PEBGPEAU_FILETIME@@@Z; RfbWmiQuery::GetProperty<_FILETIME>(_MI_Instance const *,ushort const *,_FILETIME *)
0x180014817  lea     r8, [rsp+0C8h+var_58+4]
0x18001481c  lea     rdx, aLastmodified; "LastModified"
0x180014823  mov     rcx, rbx
0x180014826  call    ??$GetProperty@U_FILETIME@@@RfbWmiQuery@@KAXPEBU_MI_Instance@@PEBGPEAU_FILETIME@@@Z; RfbWmiQuery::GetProperty<_FILETIME>(_MI_Instance const *,ushort const *,_FILETIME *)
0x18001482b  xorps   xmm0, xmm0
0x18001482e  movups  [rsp+0C8h+Src], xmm0
0x180014836  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001483e  movdqu  [rsp+0C8h+var_38], xmm1
0x180014847  xor     eax, eax
0x180014849  mov     word ptr [rsp+0C8h+Src], ax
0x180014851  lea     r8, [rsp+0C8h+Src]
0x180014859  lea     rdx, aFilename; "FileName"
0x180014860  mov     rcx, rbx
0x180014863  call    ??$GetProperty@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@RfbWmiQuery@@KAXPEBU_MI_Instance@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RfbWmiQuery::GetProperty<std::wstring>(_MI_Instance const *,ushort const *,std::wstring *)
0x180014868  cmp     [rsp+0C8h+var_88], 0
0x18001486e  jz      short loc_180014891
0x180014870  lea     rdx, asc_18001D0B4; "."
0x180014877  lea     rcx, [rsp+0C8h+Src]; Src
0x18001487f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180014884  lea     rdx, [rsp+0C8h+var_98]
0x180014889  mov     rcx, rax; Src
0x18001488c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180014891  lea     rdx, [rsp+0C8h+var_78]
0x180014896  lea     rcx, [rsp+0C8h+Src]; Src
0x18001489e  call    ?CreatePidl@?$RfbPidlHelper@UFileFixedData@@@@SAPEFBU_ITEMIDLIST@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUFileFixedData@@@Z; RfbPidlHelper<FileFixedData>::CreatePidl(std::wstring const &,FileFixedData const &)
0x1800148a3  mov     rcx, [rdi]; pv
0x1800148a6  mov     [rdi], rax
0x1800148a9  test    rcx, rcx
0x1800148ac  jz      short loc_1800148B5
0x1800148ae  call    cs:__imp_CoTaskMemFree
0x1800148b4  nop
0x1800148b5  lea     rcx, [rsp+0C8h+Src]
0x1800148bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800148c2  nop
0x1800148c3  lea     rcx, [rsp+0C8h+var_98]
0x1800148c8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800148cd  nop
0x1800148ce  mov     rcx, [rsp+0C8h+var_28]
0x1800148d6  xor     rcx, rsp; StackCookie
0x1800148d9  call    __security_check_cookie
0x1800148de  mov     rbx, [rsp+0C8h+arg_0]
0x1800148e6  add     rsp, 0B0h
0x1800148ed  pop     r14
0x1800148ef  pop     rdi
0x1800148f0  pop     rsi
0x1800148f1  retn
0x1800148f2  mov     r9d, eax; char *
0x1800148f5  lea     r8, aVmUxUiRemotefi_0; "vm\\ux\\ui\\remotefilebrowse\\rfbfilefo"...
0x1800148fc  mov     edx, 6Bh ; 'k'; void *
0x180014901  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
