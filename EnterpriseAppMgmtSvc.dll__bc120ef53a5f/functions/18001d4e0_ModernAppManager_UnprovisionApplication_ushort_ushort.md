# ModernAppManager::UnprovisionApplication(ushort *,ushort *)

- ea: `0x18001d4e0`
- end: `0x18001d654`
- name: `?UnprovisionApplication@ModernAppManager@@QEAAJPEAG0@Z`
- size: `372`
- prototype: `__int64 __fastcall(ModernAppManager *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000df50`

## callees

- `0x180001c24`
- `0x1800127c8`
- `0x18001d4e0`
- `0x18001d65c`
- `0x18001dc84`
- `0x18003442c`
- `0x18006b444`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5ed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001d5dc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001d5dc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001d60d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001d60d`

## string_xrefs

- `0x18001d630`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\modernappmanager.cpp`
- `0x18001d59f`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001d5b7`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ModernAppManager::UnprovisionApplication(
        ModernAppManager *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  char *v6; // rax
  __int64 v7; // rcx
  char *v8; // rdi
  int v9; // eax
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int LastError; // eax
  int v15; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(
    this,
    a2);
  if ( !a2 )
  {
    v5 = -2147024809;
LABEL_23:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\modernappmanager.cpp",
      (const char *)v5,
      v15);
    return v5;
  }
  v6 = (char *)operator new(0x30u);
  v8 = v6;
  if ( v6 )
  {
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 5) = 0;
    *(_OWORD *)v6 = 0;
    *(_OWORD *)(v6 + 24) = 0;
  }
  else
  {
    v8 = 0;
  }
  if ( !v8 )
  {
    Common::AutoPtrDeallocate<UnprovisionPackageParameters>(0);
    v5 = -2147024882;
    goto LABEL_23;
  }
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  v9 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v8, a2);
  v5 = v9;
  v10 = retaddr;
  if ( v9 >= 0 )
  {
    v9 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)(v8 + 24), a3);
    v5 = v9;
    v10 = retaddr;
    if ( v9 >= 0 )
      goto LABEL_15;
    v11 = 1714;
  }
  else
  {
    v11 = 1712;
  }
  wil::details::in1diag3::_Log_Hr(
    v10,
    (void *)v11,
    (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
    (const char *)(unsigned int)v9,
    v15);
LABEL_15:
  if ( (v5 & 0x80000000) == 0 )
  {
    ThreadpoolWork = CreateThreadpoolWork(DoUnprovisionPackage, v8, &g_provisioningCallbackEnvironment);
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    v8 = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x705,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)v5,
      v15);
  }
  Common::AutoPtrDeallocate<UnprovisionPackageParameters>(v8);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_23;
  return v5;
}

```

## disassembly

```asm
0x18001d4e0  mov     [rsp+arg_8], rbx
0x18001d4e5  mov     [rsp+arg_10], rsi
0x18001d4ea  mov     [rsp+arg_0], rcx
0x18001d4ef  push    rdi; int
0x18001d4f0  sub     rsp, 20h
0x18001d4f4  mov     rsi, r8
0x18001d4f7  mov     rbx, rdx
0x18001d4fa  call    ?get@?$_LazyImpl@VPackageManagerWrapper@@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@V?$static_lazy@VPackageManagerWrapper@@$0A@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@@3@@tlx@@QEAAAEAVPackageManagerWrapper@@XZ; tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(void)
0x18001d4ff  test    rbx, rbx
0x18001d502  jnz     short loc_18001D50E
0x18001d504  mov     ebx, 80070057h
0x18001d509  jmp     loc_18001D628
0x18001d50e  mov     ecx, 30h ; '0'; Size
0x18001d513  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d518  mov     rdi, rax
0x18001d51b  test    rax, rax
0x18001d51e  jz      short loc_18001D53C
0x18001d520  mov     qword ptr [rax+10h], 0
0x18001d528  mov     qword ptr [rax+28h], 0
0x18001d530  xorps   xmm0, xmm0
0x18001d533  movups  xmmword ptr [rax], xmm0
0x18001d536  movups  xmmword ptr [rax+18h], xmm0
0x18001d53a  jmp     short loc_18001D53E
0x18001d53c  xor     edi, edi
0x18001d53e  mov     [rsp+28h+arg_0], rdi
0x18001d543  test    rdi, rdi
0x18001d546  jnz     short loc_18001D559
0x18001d548  xor     ecx, ecx
0x18001d54a  call    ??$AutoPtrDeallocate@VUnprovisionPackageParameters@@@Common@@YAXPEAVUnprovisionPackageParameters@@@Z; Common::AutoPtrDeallocate<UnprovisionPackageParameters>(UnprovisionPackageParameters *)
0x18001d54f  mov     ebx, 8007000Eh
0x18001d554  jmp     loc_18001D628
0x18001d559  test    rsi, rsi
0x18001d55c  jnz     short loc_18001D563
0x18001d55e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d563  mov     rdx, rbx; Src
0x18001d566  mov     rcx, rdi; this
0x18001d569  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001d56e  mov     ebx, eax
0x18001d570  mov     rcx, [rsp+28h]
0x18001d575  test    eax, eax
0x18001d577  jns     short loc_18001D580
0x18001d579  mov     edx, 6B0h
0x18001d57e  jmp     short loc_18001D59C
0x18001d580  lea     rcx, [rdi+18h]; this
0x18001d584  mov     rdx, rsi; Src
0x18001d587  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001d58c  mov     ebx, eax
0x18001d58e  mov     rcx, [rsp+28h]; this
0x18001d593  test    eax, eax
0x18001d595  jns     short loc_18001D5AB
0x18001d597  mov     edx, 6B2h; void *
0x18001d59c  mov     r9d, eax; char *
0x18001d59f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001d5a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d5ab  mov     rcx, [rsp+28h]; this
0x18001d5b0  test    ebx, ebx
0x18001d5b2  jns     short loc_18001D5CB
0x18001d5b4  mov     r9d, ebx; char *
0x18001d5b7  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001d5be  mov     edx, 705h; void *
0x18001d5c3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d5c8  nop
0x18001d5c9  jmp     short loc_18001D61C
0x18001d5cb  lea     r8, ?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001d5d2  mov     rdx, rdi; pv
0x18001d5d5  lea     rcx, ?DoUnprovisionPackage@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001d5dc  call    cs:__imp_CreateThreadpoolWork
0x18001d5e3  nop     dword ptr [rax+rax+00h]
0x18001d5e8  test    rax, rax
0x18001d5eb  jnz     short loc_18001D60A
0x18001d5ed  call    cs:__imp_GetLastError
0x18001d5f4  nop     dword ptr [rax+rax+00h]
0x18001d5f9  mov     ebx, eax
0x18001d5fb  test    eax, eax
0x18001d5fd  jle     short loc_18001D61A
0x18001d5ff  movzx   ebx, ax
0x18001d602  or      ebx, 80070000h
0x18001d608  jmp     short loc_18001D61A
0x18001d60a  mov     rcx, rax; pwk
0x18001d60d  call    cs:__imp_SubmitThreadpoolWork
0x18001d614  nop     dword ptr [rax+rax+00h]
0x18001d619  nop
0x18001d61a  xor     edi, edi
0x18001d61c  mov     rcx, rdi
0x18001d61f  call    ??$AutoPtrDeallocate@VUnprovisionPackageParameters@@@Common@@YAXPEAVUnprovisionPackageParameters@@@Z; Common::AutoPtrDeallocate<UnprovisionPackageParameters>(UnprovisionPackageParameters *)
0x18001d624  test    ebx, ebx
0x18001d626  jns     short loc_18001D641
0x18001d628  mov     rcx, [rsp+28h]; this
0x18001d62d  mov     r9d, ebx; char *
0x18001d630  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001d637  mov     edx, 4Bh ; 'K'; void *
0x18001d63c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d641  mov     eax, ebx
0x18001d643  mov     rbx, [rsp+28h+arg_8]
0x18001d648  mov     rsi, [rsp+28h+arg_10]
0x18001d64d  add     rsp, 20h
0x18001d651  pop     rdi
0x18001d652  retn
```
