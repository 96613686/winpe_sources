# Windows::Compat::Inventory::MareDataWriter::MareDataWriter(ushort const *)

- ea: `0x180012618`
- end: `0x1800129d3`
- name: `??0MareDataWriter@Inventory@Compat@Windows@@QEAA@PEBG@Z`
- size: `955`
- prototype: `Windows::Compat::Inventory::MareDataWriter *__fastcall(Windows::Compat::Inventory::MareDataWriter *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800172a0`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x180006cec`
- `0x18000712e`
- `0x180007f60`
- `0x18000fb60`
- `0x180010640`
- `0x180012618`
- `0x18001efb4`
- `0x1800256a0`
- `0x180027d3c`
- `0x18002d900`
- `0x180035b98`
- `0x18004c020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128c0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012821`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180012821`

## string_xrefs

- `0x1800128f6`: `Windows::Compat::Inventory::MareDataWriter::MareDataWriter`
- `0x180012947`: `Windows::Compat::Inventory::MareDataWriter::MareDataWriter`
- `0x180012998`: `Windows::Compat::Inventory::MareDataWriter::MareDataWriter`
- `0x180012922`: `base\appcompat\inventory\mare\lib\maredatawriter.cpp`
- `0x180012973`: `base\appcompat\inventory\mare\lib\maredatawriter.cpp`
- `0x1800129c4`: `base\appcompat\inventory\mare\lib\maredatawriter.cpp`
- `0x18001281a`: `%windir%\appcompat\backup`
- `0x180012935`: `TelCacheProvider::Initialize failed [%#x]`
- `0x180012986`: `TelCacheProvider::Initialize failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
Windows::Compat::Inventory::MareDataWriter *__fastcall Windows::Compat::Inventory::MareDataWriter::MareDataWriter(
        Windows::Compat::Inventory::MareDataWriter *this,
        const unsigned __int16 *a2)
{
  _QWORD *v4; // rax
  unsigned __int64 v5; // rbx
  __int64 v6; // r8
  File *v7; // rax
  __int64 *v8; // rdx
  int v9; // eax
  unsigned int v10; // ebp
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ebp
  __int64 v14; // r8
  char *v15; // rbp
  size_t v16; // rbx
  signed int LastError; // eax
  signed int v19; // ebx
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  char *v23; // [rsp+28h] [rbp-280h]
  char *v24; // [rsp+28h] [rbp-280h]
  File *v25; // [rsp+40h] [rbp-268h]
  Windows::Compat::Inventory::MareApplication *v26; // [rsp+40h] [rbp-268h]
  WCHAR Dst[264]; // [rsp+60h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  memset_0((char *)this + 8, 0, 0x4Eu);
  *((_WORD *)this + 48) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_BYTE *)this + 140) = 0;
  *((_QWORD *)this + 11) = 0;
  *(_QWORD *)this = 0;
  memset_0((char *)this + 152, 0, 0x4Eu);
  *((_WORD *)this + 120) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_DWORD *)this + 70) = 0;
  *((_BYTE *)this + 284) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  v4 = operator new(0x48u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  *((_QWORD *)this + 36) = v4;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *(_OWORD *)((char *)this + 328) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  std::wstring::_Construct<1,unsigned short const *>((char *)this + 328, a2);
  v25 = (File *)operator new(0x330u);
  v7 = File::File(v25);
  v8 = &File::FileCacheProviderName;
  if ( (unsigned __int64)qword_18011B968 > 7 )
    v8 = (__int64 *)File::FileCacheProviderName;
  v9 = TelCacheProvider::Initialize(this, v8, ((unsigned __int64)v7 + 8) & -(__int64)(v7 != 0), 0, 3, 3, 100);
  v10 = v9;
  if ( v9 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::MareDataWriter",
      177,
      "TelCacheProvider::Initialize failed [%#x]",
      v9);
    v21 = wil::verify_hresult<long>(v10);
    LODWORD(v23) = v10;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xB1,
      (unsigned int)"base\\appcompat\\inventory\\mare\\lib\\maredatawriter.cpp",
      (const char *)v21,
      (int)"TelCacheProvider::Initialize failed [%#x]",
      v23);
  }
  v26 = (Windows::Compat::Inventory::MareApplication *)operator new(0x110u);
  v11 = Windows::Compat::Inventory::MareApplication::MareApplication(v26);
  v12 = TelCacheProvider::Initialize(
          (char *)this + 144,
          L"MareBackupApps",
          (v11 + 8) & -(__int64)(v11 != 0),
          0,
          3,
          3,
          100);
  v13 = v12;
  if ( v12 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::MareDataWriter",
      178,
      "TelCacheProvider::Initialize failed [%#x]",
      v12);
    v22 = wil::verify_hresult<long>(v13);
    LODWORD(v24) = v13;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xB2,
      (unsigned int)"base\\appcompat\\inventory\\mare\\lib\\maredatawriter.cpp",
      (const char *)v22,
      (int)"TelCacheProvider::Initialize failed [%#x]",
      v24);
  }
  if ( !*((_QWORD *)this + 43) )
  {
    if ( ExpandEnvironmentStringsW(L"%windir%\\appcompat\\backup", Dst, 0x104u) - 1 > 0x103 )
    {
      LastError = GetLastError();
      v19 = LastError;
      if ( LastError > 0 )
        v19 = (unsigned __int16)LastError | 0x80070000;
      if ( v19 >= 0 )
        v19 = -2147467259;
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareDataWriter::MareDataWriter",
        192,
        "ExpandEnvironmentStringsW failed [%#x]",
        v19);
      v20 = wil::verify_hresult<long>((unsigned int)v19);
      LODWORD(v24) = v19;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xC0,
        (unsigned int)"base\\appcompat\\inventory\\mare\\lib\\maredatawriter.cpp",
        (const char *)v20,
        (int)"ExpandEnvironmentStringsW failed [%#x]",
        v24);
    }
    do
      ++v5;
    while ( Dst[v5] );
    if ( v5 > *((_QWORD *)this + 44) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char *)this + 328,
        v5,
        v14,
        Dst);
    }
    else
    {
      if ( *((_QWORD *)this + 44) <= 7u )
        v15 = (char *)this + 328;
      else
        v15 = (char *)*((_QWORD *)this + 41);
      *((_QWORD *)this + 43) = v5;
      v16 = 2 * v5;
      memmove_0(v15, Dst, v16);
      *(_WORD *)&v15[v16] = 0;
    }
  }
  std::wstring::append((char *)this + 328, (void *)L"\\");
  return this;
}

```

## disassembly

```asm
0x180012618  mov     [rsp+arg_10], rbx
0x18001261d  push    rbp
0x18001261e  push    rsi
0x18001261f  push    rdi
0x180012620  push    r14
0x180012622  push    r15
0x180012624  sub     rsp, 280h
0x18001262b  mov     rax, cs:__security_cookie
0x180012632  xor     rax, rsp
0x180012635  mov     [rsp+2A8h+var_38], rax
0x18001263d  mov     rbp, rdx
0x180012640  mov     rsi, rcx
0x180012643  mov     [rsp+2A8h+var_258], rcx
0x180012648  add     rcx, 8; void *
0x18001264c  mov     ebx, 4Eh ; 'N'
0x180012651  mov     r8d, ebx; Size
0x180012654  xor     edx, edx; Val
0x180012656  call    memset_0
0x18001265b  xor     r15d, r15d
0x18001265e  mov     [rsi+60h], r15w
0x180012663  mov     [rsi+68h], r15
0x180012667  mov     [rsi+70h], r15
0x18001266b  mov     [rsi+78h], r15
0x18001266f  mov     [rsi+80h], r15
0x180012676  mov     [rsi+88h], r15d
0x18001267d  mov     [rsi+8Ch], r15b
0x180012684  mov     [rsi+58h], r15
0x180012688  mov     [rsi], r15
0x18001268b  lea     r14, [rsi+90h]
0x180012692  lea     rcx, [r14+8]; void *
0x180012696  mov     r8d, ebx; Size
0x180012699  xor     edx, edx; Val
0x18001269b  call    memset_0
0x1800126a0  mov     [r14+60h], r15w
0x1800126a5  mov     [r14+68h], r15
0x1800126a9  mov     [r14+70h], r15
0x1800126ad  mov     [r14+78h], r15
0x1800126b1  mov     [r14+80h], r15
0x1800126b8  mov     [r14+88h], r15d
0x1800126bf  mov     [r14+8Ch], r15b
0x1800126c6  mov     [r14+58h], r15
0x1800126ca  mov     [r14], r15
0x1800126cd  lea     rbx, [rsi+120h]
0x1800126d4  mov     [rbx], r15
0x1800126d7  mov     [rbx+8], r15
0x1800126db  lea     ecx, [r15+48h]; Size
0x1800126df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800126e4  mov     [rax], rax
0x1800126e7  mov     [rax+8], rax
0x1800126eb  mov     [rax+10h], rax
0x1800126ef  mov     word ptr [rax+18h], 101h
0x1800126f5  mov     [rbx], rax
0x1800126f8  mov     [rsi+130h], r15
0x1800126ff  mov     [rsi+138h], r15
0x180012706  mov     [rsi+140h], r15
0x18001270d  lea     rdi, [rsi+148h]
0x180012714  xorps   xmm0, xmm0
0x180012717  movups  xmmword ptr [rdi], xmm0
0x18001271a  mov     [rdi+10h], r15
0x18001271e  mov     [rdi+18h], r15
0x180012722  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012726  mov     r8, rbx
0x180012729  inc     r8
0x18001272c  cmp     [rbp+r8*2+0], r15w
0x180012732  jnz     short loc_180012729
0x180012734  mov     rdx, rbp
0x180012737  mov     rcx, rdi
0x18001273a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001273f  nop
0x180012740  mov     ecx, 330h; Size
0x180012745  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001274a  mov     [rsp+2A8h+var_268], rax
0x18001274f  mov     rcx, rax; this
0x180012752  call    ??0File@@QEAA@XZ; File::File(void)
0x180012757  mov     rcx, rax
0x18001275a  add     rax, 8
0x18001275e  neg     rcx
0x180012761  sbb     r8, r8
0x180012764  and     r8, rax
0x180012767  lea     rdx, ?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x18001276e  cmp     cs:qword_18011B968, 7
0x180012776  cmova   rdx, cs:?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x18001277e  mov     [rsp+2A8h+var_278], 64h ; 'd'
0x180012786  mov     dword ptr [rsp+2A8h+var_280], 3
0x18001278e  mov     [rsp+2A8h+var_288], 3
0x180012796  xor     r9d, r9d
0x180012799  mov     rcx, rsi
0x18001279c  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x1800127a1  mov     ebp, eax
0x1800127a3  test    eax, eax
0x1800127a5  js      loc_180012931
0x1800127ab  mov     ecx, 110h; Size
0x1800127b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800127b5  mov     [rsp+2A8h+var_268], rax
0x1800127ba  mov     rcx, rax; this
0x1800127bd  call    ??0MareApplication@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::MareApplication::MareApplication(void)
0x1800127c2  mov     rdx, rax
0x1800127c5  add     rax, 8
0x1800127c9  neg     rdx
0x1800127cc  sbb     r8, r8
0x1800127cf  and     r8, rax
0x1800127d2  mov     [rsp+2A8h+var_278], 64h ; 'd'
0x1800127da  mov     dword ptr [rsp+2A8h+var_280], 3
0x1800127e2  mov     [rsp+2A8h+var_288], 3
0x1800127ea  xor     r9d, r9d
0x1800127ed  lea     rdx, aMarebackupapps; "MareBackupApps"
0x1800127f4  mov     rcx, r14
0x1800127f7  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x1800127fc  mov     ebp, eax
0x1800127fe  test    eax, eax
0x180012800  js      loc_180012982
0x180012806  cmp     [rsi+158h], r15
0x18001280d  jnz     short loc_180012886
0x18001280f  mov     r8d, 104h; nSize
0x180012815  lea     rdx, [rsp+2A8h+Dst]; lpDst
0x18001281a  lea     rcx, Src; "%windir%\\appcompat\\backup"
0x180012821  call    cs:__imp_ExpandEnvironmentStringsW
0x180012827  dec     eax
0x180012829  cmp     eax, 103h
0x18001282e  ja      loc_1800128C0
0x180012834  lea     rax, [rsp+2A8h+Dst]
0x180012839  inc     rbx
0x18001283c  cmp     [rax+rbx*2], r15w
0x180012841  jnz     short loc_180012839
0x180012843  cmp     rbx, [rdi+18h]
0x180012847  ja      short loc_180012876
0x180012849  cmp     qword ptr [rdi+18h], 7
0x18001284e  jbe     short loc_180012855
0x180012850  mov     rbp, [rdi]
0x180012853  jmp     short loc_180012858
0x180012855  mov     rbp, rdi
0x180012858  mov     [rdi+10h], rbx
0x18001285c  add     rbx, rbx
0x18001285f  mov     r8, rbx; Size
0x180012862  lea     rdx, [rsp+2A8h+Dst]; Src
0x180012867  mov     rcx, rbp; void *
0x18001286a  call    memmove_0
0x18001286f  mov     [rbx+rbp], r15w
0x180012874  jmp     short loc_180012886
0x180012876  lea     r9, [rsp+2A8h+Dst]
0x18001287b  mov     rdx, rbx
0x18001287e  mov     rcx, rdi
0x180012881  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180012886  lea     rdx, SubBlock; "\\"
0x18001288d  mov     rcx, rdi; Src
0x180012890  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180012895  nop
0x180012896  mov     rax, rsi
0x180012899  mov     rcx, [rsp+2A8h+var_38]
0x1800128a1  xor     rcx, rsp; StackCookie
0x1800128a4  call    __security_check_cookie
0x1800128a9  mov     rbx, [rsp+2A8h+arg_10]
0x1800128b1  add     rsp, 280h
0x1800128b8  pop     r15
0x1800128ba  pop     r14
0x1800128bc  pop     rdi
0x1800128bd  pop     rsi
0x1800128be  pop     rbp
0x1800128bf  retn
0x1800128c0  call    cs:__imp_GetLastError
0x1800128c6  nop
0x1800128c7  mov     ebx, eax
0x1800128c9  test    eax, eax
0x1800128cb  jle     short loc_1800128D6
0x1800128cd  movzx   ebx, ax
0x1800128d0  or      ebx, 80070000h
0x1800128d6  mov     eax, 80004005h
0x1800128db  test    ebx, ebx
0x1800128dd  cmovns  ebx, eax
0x1800128e0  mov     [rsp+2A8h+var_288], ebx
0x1800128e4  lea     rdi, aExpandenvironm; "ExpandEnvironmentStringsW failed [%#x]"
0x1800128eb  mov     r9, rdi
0x1800128ee  mov     esi, 0C0h
0x1800128f3  mov     r8d, esi
0x1800128f6  lea     rdx, aWindowsCompatI_51; "Windows::Compat::Inventory::MareDataWri"...
0x1800128fd  mov     ecx, 1
0x180012902  call    AslLogCallPrintf
0x180012907  mov     ecx, ebx
0x180012909  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001290e  mov     r9d, eax; char *
0x180012911  mov     rcx, [rsp+2A8h]; this
0x180012919  mov     dword ptr [rsp+2A8h+var_280], ebx; char *
0x18001291d  mov     qword ptr [rsp+2A8h+var_288], rdi; int
0x180012922  lea     r8, aBaseAppcompatI; "base\\appcompat\\inventory\\mare\\lib\\"...
0x180012929  mov     edx, esi; void *
0x18001292b  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180012931  mov     [rsp+2A8h+var_288], ebp
0x180012935  lea     rbx, aTelcacheprovid_16; "TelCacheProvider::Initialize failed [%#"...
0x18001293c  mov     r9, rbx
0x18001293f  mov     edi, 0B1h
0x180012944  mov     r8d, edi
0x180012947  lea     rdx, aWindowsCompatI_51; "Windows::Compat::Inventory::MareDataWri"...
0x18001294e  mov     ecx, 1
0x180012953  call    AslLogCallPrintf
0x180012958  mov     ecx, ebp
0x18001295a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001295f  mov     r9d, eax; char *
0x180012962  mov     rcx, [rsp+2A8h]; this
0x18001296a  mov     dword ptr [rsp+2A8h+var_280], ebp; char *
0x18001296e  mov     qword ptr [rsp+2A8h+var_288], rbx; int
0x180012973  lea     r8, aBaseAppcompatI; "base\\appcompat\\inventory\\mare\\lib\\"...
0x18001297a  mov     edx, edi; void *
0x18001297c  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180012982  mov     [rsp+2A8h+var_288], ebp
0x180012986  lea     rbx, aTelcacheprovid_16; "TelCacheProvider::Initialize failed [%#"...
0x18001298d  mov     r9, rbx
0x180012990  mov     edi, 0B2h
0x180012995  mov     r8d, edi
0x180012998  lea     rdx, aWindowsCompatI_51; "Windows::Compat::Inventory::MareDataWri"...
0x18001299f  mov     ecx, 1
0x1800129a4  call    AslLogCallPrintf
0x1800129a9  mov     ecx, ebp
0x1800129ab  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800129b0  mov     r9d, eax; char *
0x1800129b3  mov     rcx, [rsp+2A8h]; this
0x1800129bb  mov     dword ptr [rsp+2A8h+var_280], ebp; char *
0x1800129bf  mov     qword ptr [rsp+2A8h+var_288], rbx; int
0x1800129c4  lea     r8, aBaseAppcompatI; "base\\appcompat\\inventory\\mare\\lib\\"...
0x1800129cb  mov     edx, edi; void *
0x1800129cd  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
