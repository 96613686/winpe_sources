# SyncEngineHelper::ReportSyncResult(Sid const &,long,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,char const *,TimeSpan const &)

- ea: `0x18007c27c`
- end: `0x18007c6a6`
- name: `?ReportSyncResult@SyncEngineHelper@@YAXAEBVSid@@JKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1PEBDAEBVTimeSpan@@@Z`
- size: `1066`
- prototype: `__int64 __usercall@<rax>(wpcplugs::Sync::UserSync::Desktop *this@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180076364`

## callees

- `0x1800010fc`
- `0x1800060a0`
- `0x1800082bc`
- `0x180008d50`
- `0x180009a80`
- `0x18000bba8`
- `0x18001484c`
- `0x180014928`
- `0x18002aae4`
- `0x18002cad8`
- `0x180035240`
- `0x180035340`
- `0x18003547c`
- `0x1800356c8`
- `0x1800623f0`
- `0x180065a18`
- `0x1800717b8`
- `0x18007c27c`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18007c2e3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18007c2e3`
- `DiagnosticDataSettings!TelIsTelemetryTypeAllowed` at `0x18007c2fa`
- `DiagnosticDataSettings!TelIsTelemetryTypeAllowed` at `0x18007c2fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SyncEngineHelper::ReportSyncResult(
        wpcplugs::Sync::UserSync::Desktop *this,
        unsigned int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 *a6,
        _QWORD *a7)
{
  BOOL v11; // r15d
  const struct Sid *v12; // rdx
  BOOL IsActiveUserAdministrator; // r14d
  _QWORD *v14; // rax
  _DWORD *v15; // r10
  const WCHAR *v16; // rax
  const WCHAR *v17; // rdx
  __int64 v18; // rcx
  const unsigned __int16 *v19; // r9
  __int64 v20; // r8
  int v21; // r8d
  __int64 v22; // r8
  int v23; // r8d
  __int64 v24; // rax
  int v25; // ecx
  int v26; // eax
  Private::Format *v27; // rbx
  Private::Format *v28; // rbx
  Private::Format *v29; // rax
  Private::Format *v30; // rax
  Private::Format *v31; // rax
  Private::Format *v32; // rax
  Private::Format *v33; // rbx
  __int64 v34; // rax
  const unsigned __int16 *v35; // rdx
  int v37; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v38; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v39; // [rsp+48h] [rbp-B8h] BYREF
  DWORD nSize; // [rsp+50h] [rbp-B0h] BYREF
  BOOL v41; // [rsp+54h] [rbp-ACh] BYREF
  BOOL v42; // [rsp+58h] [rbp-A8h] BYREF
  int v43; // [rsp+5Ch] [rbp-A4h] BYREF
  _QWORD *v44; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v45[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h]
  unsigned __int64 v47; // [rsp+80h] [rbp-80h]
  _BYTE v48[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v49[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v50[40]; // [rsp+C8h] [rbp-38h] BYREF
  char v51[32]; // [rsp+F0h] [rbp-10h] BYREF
  wpcplugs::Sync::UserSync::Desktop *v52; // [rsp+110h] [rbp+10h]
  int v53; // [rsp+118h] [rbp+18h]
  int v54; // [rsp+11Ch] [rbp+1Ch]
  int *v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+128h] [rbp+28h]
  const WCHAR *v57; // [rsp+130h] [rbp+30h]
  int v58; // [rsp+138h] [rbp+38h]
  int v59; // [rsp+13Ch] [rbp+3Ch]
  int *v60; // [rsp+140h] [rbp+40h]
  __int64 v61; // [rsp+148h] [rbp+48h]
  BOOL *v62; // [rsp+150h] [rbp+50h]
  __int64 v63; // [rsp+158h] [rbp+58h]
  WCHAR *v64; // [rsp+160h] [rbp+60h]
  int v65; // [rsp+168h] [rbp+68h]
  int v66; // [rsp+16Ch] [rbp+6Ch]
  const WCHAR *v67; // [rsp+170h] [rbp+70h]
  int v68; // [rsp+178h] [rbp+78h]
  int v69; // [rsp+17Ch] [rbp+7Ch]
  BOOL *v70; // [rsp+180h] [rbp+80h]
  __int64 v71; // [rsp+188h] [rbp+88h]
  unsigned __int64 *v72; // [rsp+190h] [rbp+90h]
  __int64 v73; // [rsp+198h] [rbp+98h]
  const unsigned __int16 *v74; // [rsp+1A0h] [rbp+A0h]
  int v75; // [rsp+1A8h] [rbp+A8h]
  int v76; // [rsp+1ACh] [rbp+ACh]
  WCHAR Buffer[16]; // [rsp+1B0h] [rbp+B0h] BYREF

  v37 = a3;
  v44 = a7;
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
    Buffer[0] = 0;
  v11 = TelIsTelemetryTypeAllowed(2) != 0;
  IsActiveUserAdministrator = wpcplugs::Sync::UserSync::Desktop::IsActiveUserAdministrator(this, v12);
  v14 = (_QWORD *)Global<_tlgProvider_t const *>::Get((Globals *)&off_1800F0690);
  v15 = (_DWORD *)*v14;
  if ( *(_DWORD *)*v14 > 4u
    && (*((_QWORD *)v15 + 2) & 0x800000000000LL) != 0
    && (*((_QWORD *)v15 + 3) & 0x800000000000LL) == *((_QWORD *)v15 + 3) )
  {
    v39 = *v44 / 0x2710uLL;
    v41 = IsActiveUserAdministrator;
    v16 = (const WCHAR *)a5;
    if ( *(_QWORD *)(a5 + 24) > 7u )
      v16 = *(const WCHAR **)a5;
    v42 = v11;
    v43 = a3;
    if ( *(_QWORD *)(a4 + 24) <= 7u )
      v17 = (const WCHAR *)a4;
    else
      v17 = *(const WCHAR **)a4;
    v38 = a2;
    v18 = -1;
    if ( a6 )
    {
      v19 = a6;
      v20 = -1;
      do
        ++v20;
      while ( *((_BYTE *)a6 + v20) );
      v21 = v20 + 1;
    }
    else
    {
      v19 = &qword_1800B7CB8;
      v21 = 1;
    }
    v74 = v19;
    v75 = v21;
    v76 = 0;
    v72 = &v39;
    v73 = 8;
    v70 = &v41;
    v71 = 4;
    if ( v16 )
    {
      v22 = -1;
      do
        ++v22;
      while ( v16[v22] );
      v23 = 2 * v22 + 2;
    }
    else
    {
      v16 = &SubKey;
      v23 = 2;
    }
    v67 = v16;
    v68 = v23;
    v69 = 0;
    v24 = -1;
    do
      ++v24;
    while ( Buffer[v24] );
    v64 = Buffer;
    v65 = 2 * v24 + 2;
    v66 = 0;
    v62 = &v42;
    v63 = 4;
    v60 = &v43;
    v61 = 4;
    if ( v17 )
    {
      do
        ++v18;
      while ( v17[v18] );
      v25 = 2 * v18 + 2;
    }
    else
    {
      v17 = &SubKey;
      v25 = 2;
    }
    v57 = v17;
    v58 = v25;
    v59 = 0;
    v55 = (int *)&v38;
    v56 = 4;
    v26 = 4 * *((unsigned __int8 *)this + 1) + 8;
    v52 = this;
    v53 = v26;
    v54 = 0;
    tlgWriteTransfer_EventWriteTransfer(v15, &unk_1800D6700, 0, 0, 12, v51);
  }
  *(_OWORD *)v45 = 0;
  v46 = 0;
  v47 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    v45,
    L"UserWebSyncResult: {0} Result:{1} WAM:{2} ResultText:{3} Admin:{4} DurationMS:{5} Device:{6} cV: {7}",
    100);
  v27 = (Private::Format *)StringAlgo::FormatString(v50, v45);
  Sid::AbbrevString(this, v49);
  v28 = (Private::Format *)Private::Format::operator%<std::wstring>(v27);
  StringAlgo::Format(v48, L"%X", a2);
  v29 = (Private::Format *)Private::Format::operator%<std::wstring>(v28);
  v30 = (Private::Format *)Private::Format::operator%<unsigned long>(v29);
  v31 = (Private::Format *)Private::Format::operator%<std::wstring>(v30);
  v32 = (Private::Format *)Private::Format::operator%<bool>(v31);
  v39 = *v44 / 0x2710uLL;
  v33 = (Private::Format *)Private::Format::operator%<unsigned __int64>(v32);
  v34 = StringAlgo::ToString(v45, Buffer);
  if ( *(_QWORD *)(v34 + 24) > 7u )
    v34 = *(_QWORD *)v34;
  Private::Format::Replace(v33, (const unsigned __int16 *)v34);
  std::wstring::~wstring(v45);
  StringAlgo::ToUnicode(v45, a6);
  v35 = (const unsigned __int16 *)v45;
  if ( v47 > 7 )
    v35 = v45[0];
  Private::Format::Replace(v33, v35);
  std::wstring::~wstring(v45);
  v37 = 2;
  wpc::Sync::Internal::SyncLogger::LogMessage(&v37, v33);
  std::wstring::~wstring(v48);
  std::wstring::~wstring(v49);
  return std::wstring::~wstring(v50);
}

```

## disassembly

```asm
0x18007c27c  push    rbp
0x18007c27e  push    rbx
0x18007c27f  push    rsi
0x18007c280  push    rdi
0x18007c281  push    r12
0x18007c283  push    r13
0x18007c285  push    r14
0x18007c287  push    r15
0x18007c289  lea     rbp, [rsp-0E8h]
0x18007c291  sub     rsp, 1E8h
0x18007c298  mov     rax, cs:__security_cookie
0x18007c29f  xor     rax, rsp
0x18007c2a2  mov     [rbp+120h+var_50], rax
0x18007c2a9  mov     rsi, r9
0x18007c2ac  mov     ebx, r8d
0x18007c2af  mov     r13d, edx
0x18007c2b2  mov     r12, rcx
0x18007c2b5  mov     [rsp+220h+var_1E8], ebx
0x18007c2b9  mov     rdi, [rbp+120h+arg_28]
0x18007c2c0  mov     rax, [rbp+120h+arg_30]
0x18007c2c7  mov     [rsp+220h+var_1C0], rax
0x18007c2cc  xor     r14d, r14d
0x18007c2cf  mov     [rsp+220h+nSize], 10h
0x18007c2d7  lea     rdx, [rsp+220h+nSize]; nSize
0x18007c2dc  lea     rcx, [rbp+120h+Buffer]; lpBuffer
0x18007c2e3  call    cs:__imp_GetComputerNameW
0x18007c2e9  test    eax, eax
0x18007c2eb  jnz     short loc_18007C2F5
0x18007c2ed  mov     [rbp+120h+Buffer], r14w
0x18007c2f5  mov     ecx, 2
0x18007c2fa  call    cs:__imp_TelIsTelemetryTypeAllowed
0x18007c300  mov     r15d, r14d
0x18007c303  test    eax, eax
0x18007c305  setnz   r15b
0x18007c309  mov     rcx, r12; this
0x18007c30c  call    ?IsActiveUserAdministrator@Desktop@UserSync@Sync@wpcplugs@@YA_NAEBVSid@@@Z; wpcplugs::Sync::UserSync::Desktop::IsActiveUserAdministrator(Sid const &)
0x18007c311  movzx   r14d, al
0x18007c315  mov     [rsp+220h+var_1F0], r14b
0x18007c31a  lea     rcx, off_1800F0690; this
0x18007c321  call    ?Get@?$Global@PEBU_tlgProvider_t@@@@QEAAAEAPEBU_tlgProvider_t@@XZ; Global<_tlgProvider_t const *>::Get(void)
0x18007c326  mov     r10, [rax]
0x18007c329  mov     ecx, [r10]
0x18007c32c  mov     r9, 346DC5D63886594Bh
0x18007c336  cmp     ecx, 4
0x18007c339  jbe     loc_18007C522
0x18007c33f  mov     rdx, [r10+18h]
0x18007c343  mov     rcx, [r10+10h]
0x18007c347  mov     r8, 800000000000h
0x18007c351  test    r8, rcx
0x18007c354  jz      loc_18007C522
0x18007c35a  mov     rax, rdx
0x18007c35d  and     rax, r8
0x18007c360  cmp     rax, rdx
0x18007c363  jnz     loc_18007C522
0x18007c369  mov     rax, r9
0x18007c36c  mov     rcx, [rsp+220h+var_1C0]
0x18007c371  mul     qword ptr [rcx]
0x18007c374  shr     rdx, 0Bh
0x18007c378  mov     [rsp+220h+var_1D8], rdx
0x18007c37d  mov     [rsp+220h+var_1CC], r14d
0x18007c382  mov     rax, [rbp+120h+arg_20]
0x18007c389  cmp     qword ptr [rax+18h], 7
0x18007c38e  jbe     short loc_18007C393
0x18007c390  mov     rax, [rax]
0x18007c393  mov     [rsp+220h+var_1C8], r15d
0x18007c398  mov     [rsp+220h+var_1C4], ebx
0x18007c39c  cmp     qword ptr [rsi+18h], 7
0x18007c3a1  jbe     short loc_18007C3A8
0x18007c3a3  mov     rdx, [rsi]
0x18007c3a6  jmp     short loc_18007C3AB
0x18007c3a8  mov     rdx, rsi
0x18007c3ab  mov     [rsp+220h+var_1E0], r13d
0x18007c3b0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007c3b4  xor     r11d, r11d
0x18007c3b7  test    rdi, rdi
0x18007c3ba  jz      short loc_18007C3D0
0x18007c3bc  mov     r9, rdi
0x18007c3bf  mov     r8, rcx
0x18007c3c2  inc     r8
0x18007c3c5  cmp     [rdi+r8], r11b
0x18007c3c9  jnz     short loc_18007C3C2
0x18007c3cb  inc     r8d
0x18007c3ce  jmp     short loc_18007C3DD
0x18007c3d0  lea     r9, qword_1800B7CB8
0x18007c3d7  mov     r8d, 1
0x18007c3dd  mov     [rbp+120h+var_80], r9
0x18007c3e4  mov     [rbp+120h+var_78], r8d
0x18007c3eb  mov     [rbp+120h+var_74], r11d
0x18007c3f2  lea     r8, [rsp+220h+var_1D8]
0x18007c3f7  mov     [rbp+120h+var_90], r8
0x18007c3fe  mov     [rbp+120h+var_88], 8
0x18007c409  lea     r8, [rsp+220h+var_1CC]
0x18007c40e  mov     [rbp+120h+var_A0], r8
0x18007c415  mov     [rbp+120h+var_98], 4
0x18007c420  test    rax, rax
0x18007c423  jz      short loc_18007C43C
0x18007c425  mov     r8, rcx
0x18007c428  inc     r8
0x18007c42b  cmp     [rax+r8*2], r11w
0x18007c430  jnz     short loc_18007C428
0x18007c432  lea     r8d, ds:2[r8*2]
0x18007c43a  jmp     short loc_18007C449
0x18007c43c  lea     rax, SubKey
0x18007c443  mov     r8d, 2
0x18007c449  mov     [rbp+120h+var_B0], rax
0x18007c44d  mov     [rbp+120h+var_A8], r8d
0x18007c451  mov     [rbp+120h+var_A4], r11d
0x18007c455  lea     r8, [rbp+120h+Buffer]
0x18007c45c  mov     rax, rcx
0x18007c45f  inc     rax
0x18007c462  cmp     [r8+rax*2], r11w
0x18007c467  jnz     short loc_18007C45F
0x18007c469  lea     r8, [rbp+120h+Buffer]
0x18007c470  mov     [rbp+120h+var_C0], r8
0x18007c474  lea     eax, ds:2[rax*2]
0x18007c47b  mov     [rbp+120h+var_B8], eax
0x18007c47e  mov     [rbp+120h+var_B4], r11d
0x18007c482  lea     rax, [rsp+220h+var_1C8]
0x18007c487  mov     [rbp+120h+var_D0], rax
0x18007c48b  mov     [rbp+120h+var_C8], 4
0x18007c493  lea     rax, [rsp+220h+var_1C4]
0x18007c498  mov     [rbp+120h+var_E0], rax
0x18007c49c  mov     [rbp+120h+var_D8], 4
0x18007c4a4  test    rdx, rdx
0x18007c4a7  jz      short loc_18007C4BC
0x18007c4a9  inc     rcx
0x18007c4ac  cmp     [rdx+rcx*2], r11w
0x18007c4b1  jnz     short loc_18007C4A9
0x18007c4b3  lea     ecx, ds:2[rcx*2]
0x18007c4ba  jmp     short loc_18007C4C8
0x18007c4bc  lea     rdx, SubKey
0x18007c4c3  mov     ecx, 2
0x18007c4c8  mov     [rbp+120h+var_F0], rdx
0x18007c4cc  mov     [rbp+120h+var_E8], ecx
0x18007c4cf  mov     [rbp+120h+var_E4], r11d
0x18007c4d3  lea     rax, [rsp+220h+var_1E0]
0x18007c4d8  mov     [rbp+120h+var_100], rax
0x18007c4dc  mov     [rbp+120h+var_F8], 4
0x18007c4e4  movzx   eax, byte ptr [r12+1]
0x18007c4ea  lea     eax, ds:8[rax*4]
0x18007c4f1  mov     [rbp+120h+var_110], r12
0x18007c4f5  mov     [rbp+120h+var_108], eax
0x18007c4f8  mov     [rbp+120h+var_104], r11d
0x18007c4fc  lea     rax, [rbp+120h+var_130]
0x18007c500  mov     [rsp+220h+var_1F8], rax
0x18007c505  mov     [rsp+220h+var_200], 0Ch
0x18007c50d  xor     r9d, r9d
0x18007c510  xor     r8d, r8d
0x18007c513  lea     rdx, unk_1800D6700
0x18007c51a  mov     rcx, r10
0x18007c51d  call    _tlgWriteTransfer_EventWriteTransfer
0x18007c522  xorps   xmm0, xmm0
0x18007c525  movups  xmmword ptr [rsp+220h+var_1B8], xmm0
0x18007c52a  mov     [rsp+220h+var_1A8], 0
0x18007c533  mov     [rbp+120h+var_1A0], 0
0x18007c53b  mov     r8d, 64h ; 'd'
0x18007c541  lea     rdx, aUserwebsyncres; "UserWebSyncResult: {0} Result:{1} WAM:{"...
0x18007c548  lea     rcx, [rsp+220h+var_1B8]
0x18007c54d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007c552  lea     rdx, [rsp+220h+var_1B8]
0x18007c557  lea     rcx, [rbp+120h+var_158]
0x18007c55b  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18007c560  mov     rbx, rax
0x18007c563  lea     rdx, [rbp+120h+var_178]
0x18007c567  mov     rcx, r12
0x18007c56a  call    ?AbbrevString@Sid@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Sid::AbbrevString(void)
0x18007c56f  nop
0x18007c570  mov     rdx, rax
0x18007c573  mov     rcx, rbx; this
0x18007c576  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18007c57b  mov     rbx, rax
0x18007c57e  mov     r8d, r13d
0x18007c581  lea     rdx, asc_1800BC5EC; "%X"
0x18007c588  lea     rcx, [rbp+120h+var_198]
0x18007c58c  call    ?Format@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; StringAlgo::Format(ushort const *,...)
0x18007c591  nop
0x18007c592  mov     rdx, rax
0x18007c595  mov     rcx, rbx; this
0x18007c598  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18007c59d  lea     rdx, [rsp+220h+var_1E8]
0x18007c5a2  mov     rcx, rax; this
0x18007c5a5  call    ??$?LK@Format@Private@@QEAAAEAV01@AEBK@Z; Private::Format::operator%<ulong>(ulong const &)
0x18007c5aa  mov     rdx, rsi
0x18007c5ad  mov     rcx, rax; this
0x18007c5b0  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18007c5b5  lea     rdx, [rsp+220h+var_1F0]
0x18007c5ba  mov     rcx, rax; this
0x18007c5bd  call    ??$?L_N@Format@Private@@QEAAAEAV01@AEB_N@Z; Private::Format::operator%<bool>(bool const &)
0x18007c5c2  mov     rcx, rax; this
0x18007c5c5  mov     rax, 346DC5D63886594Bh
0x18007c5cf  mov     rdx, [rsp+220h+var_1C0]
0x18007c5d4  mul     qword ptr [rdx]
0x18007c5d7  shr     rdx, 0Bh
0x18007c5db  mov     [rsp+220h+var_1D8], rdx
0x18007c5e0  lea     rdx, [rsp+220h+var_1D8]
0x18007c5e5  call    ??$?L_K@Format@Private@@QEAAAEAV01@AEB_K@Z; Private::Format::operator%<unsigned __int64>(unsigned __int64 const &)
0x18007c5ea  mov     rbx, rax
0x18007c5ed  lea     rdx, [rbp+120h+Buffer]
0x18007c5f4  lea     rcx, [rsp+220h+var_1B8]
0x18007c5f9  call    ?ToString@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; StringAlgo::ToString(ushort const *)
0x18007c5fe  nop
0x18007c5ff  cmp     qword ptr [rax+18h], 7
0x18007c604  jbe     short loc_18007C609
0x18007c606  mov     rax, [rax]
0x18007c609  mov     rdx, rax; unsigned __int16 *
0x18007c60c  mov     rcx, rbx; this
0x18007c60f  call    ?Replace@Format@Private@@AEAAXPEBG@Z; Private::Format::Replace(ushort const *)
0x18007c614  nop
0x18007c615  lea     rcx, [rsp+220h+var_1B8]
0x18007c61a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007c61f  mov     rdx, rdi
0x18007c622  lea     rcx, [rsp+220h+var_1B8]
0x18007c627  call    ?ToUnicode@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; StringAlgo::ToUnicode(char const *)
0x18007c62c  nop
0x18007c62d  lea     rdx, [rsp+220h+var_1B8]
0x18007c632  cmp     [rbp+120h+var_1A0], 7
0x18007c637  cmova   rdx, [rsp+220h+var_1B8]; unsigned __int16 *
0x18007c63d  mov     rcx, rbx; this
0x18007c640  call    ?Replace@Format@Private@@AEAAXPEBG@Z; Private::Format::Replace(ushort const *)
0x18007c645  nop
0x18007c646  lea     rcx, [rsp+220h+var_1B8]
0x18007c64b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007c650  mov     [rsp+220h+var_1E8], 2
0x18007c658  mov     rdx, rbx
0x18007c65b  lea     rcx, [rsp+220h+var_1E8]
0x18007c660  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18007c665  nop
0x18007c666  lea     rcx, [rbp+120h+var_198]
0x18007c66a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007c66f  nop
0x18007c670  lea     rcx, [rbp+120h+var_178]
0x18007c674  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007c679  nop
0x18007c67a  lea     rcx, [rbp+120h+var_158]
0x18007c67e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007c683  mov     rcx, [rbp+120h+var_50]
0x18007c68a  xor     rcx, rsp; StackCookie
0x18007c68d  call    __security_check_cookie
0x18007c692  add     rsp, 1E8h
0x18007c699  pop     r15
0x18007c69b  pop     r14
0x18007c69d  pop     r13
0x18007c69f  pop     r12
0x18007c6a1  pop     rdi
0x18007c6a2  pop     rsi
0x18007c6a3  pop     rbx
0x18007c6a4  pop     rbp
0x18007c6a5  retn
```
