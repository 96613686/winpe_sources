# ModernAppManager::UnprovisionApplication(ushort *,ushort *)

- ea: `0x18001c450`
- end: `0x18001c5b1`
- name: `?UnprovisionApplication@ModernAppManager@@QEAAJPEAG0@Z`
- size: `353`
- prototype: `__int64 __fastcall(ModernAppManager *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d9d0`

## callees

- `0x180001bf4`
- `0x180011f54`
- `0x18001c450`
- `0x18001c5b8`
- `0x18001cbb8`
- `0x1800315d4`
- `0x180065a64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c557`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001c54c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001c54c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001c571`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001c571`

## string_xrefs

- `0x18001c58e`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\modernappmanager.cpp`
- `0x18001c50f`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001c527`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

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
  __int64 v7; // rdx
  __int64 v8; // rcx
  char *v9; // rdi
  int v10; // eax
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int LastError; // eax
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
      (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\modernappmanager.cpp",
      (const char *)v5);
    return v5;
  }
  v6 = (char *)operator new(0x30u);
  v9 = v6;
  if ( v6 )
  {
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 5) = 0;
    *(_OWORD *)v6 = 0;
    *(_OWORD *)(v6 + 24) = 0;
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
  {
    Common::AutoPtrDeallocate<UnprovisionPackageParameters>(0);
    v5 = -2147024882;
    goto LABEL_23;
  }
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7);
  v10 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v9, a2);
  v5 = v10;
  v11 = retaddr;
  if ( v10 >= 0 )
  {
    v10 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)(v9 + 24), a3);
    v5 = v10;
    v11 = retaddr;
    if ( v10 >= 0 )
      goto LABEL_15;
    v12 = 1714;
  }
  else
  {
    v12 = 1712;
  }
  wil::details::in1diag3::_Log_Hr(
    v11,
    (void *)v12,
    (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
    (const char *)(unsigned int)v10);
LABEL_15:
  if ( (v5 & 0x80000000) == 0 )
  {
    ThreadpoolWork = CreateThreadpoolWork(DoUnprovisionPackage, v9, &g_provisioningCallbackEnvironment);
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
    v9 = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x705,
      (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)v5);
  }
  Common::AutoPtrDeallocate<UnprovisionPackageParameters>(v9);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_23;
  return v5;
}

```

## disassembly

```asm
0x18001c450  mov     [rsp+arg_8], rbx
0x18001c455  mov     [rsp+arg_10], rsi
0x18001c45a  mov     [rsp+arg_0], rcx
0x18001c45f  push    rdi; int
0x18001c460  sub     rsp, 20h
0x18001c464  mov     rsi, r8
0x18001c467  mov     rbx, rdx
0x18001c46a  call    ?get@?$_LazyImpl@VPackageManagerWrapper@@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@V?$static_lazy@VPackageManagerWrapper@@$0A@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@@3@@tlx@@QEAAAEAVPackageManagerWrapper@@XZ; tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(void)
0x18001c46f  test    rbx, rbx
0x18001c472  jnz     short loc_18001C47E
0x18001c474  mov     ebx, 80070057h
0x18001c479  jmp     loc_18001C586
0x18001c47e  mov     ecx, 30h ; '0'; Size
0x18001c483  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c488  mov     rdi, rax
0x18001c48b  test    rax, rax
0x18001c48e  jz      short loc_18001C4AC
0x18001c490  mov     qword ptr [rax+10h], 0
0x18001c498  mov     qword ptr [rax+28h], 0
0x18001c4a0  xorps   xmm0, xmm0
0x18001c4a3  movups  xmmword ptr [rax], xmm0
0x18001c4a6  movups  xmmword ptr [rax+18h], xmm0
0x18001c4aa  jmp     short loc_18001C4AE
0x18001c4ac  xor     edi, edi
0x18001c4ae  mov     [rsp+28h+arg_0], rdi
0x18001c4b3  test    rdi, rdi
0x18001c4b6  jnz     short loc_18001C4C9
0x18001c4b8  xor     ecx, ecx
0x18001c4ba  call    ??$AutoPtrDeallocate@VUnprovisionPackageParameters@@@Common@@YAXPEAVUnprovisionPackageParameters@@@Z; Common::AutoPtrDeallocate<UnprovisionPackageParameters>(UnprovisionPackageParameters *)
0x18001c4bf  mov     ebx, 8007000Eh
0x18001c4c4  jmp     loc_18001C586
0x18001c4c9  test    rsi, rsi
0x18001c4cc  jnz     short loc_18001C4D3
0x18001c4ce  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c4d3  mov     rdx, rbx; Src
0x18001c4d6  mov     rcx, rdi; this
0x18001c4d9  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001c4de  mov     ebx, eax
0x18001c4e0  mov     rcx, [rsp+28h]
0x18001c4e5  test    eax, eax
0x18001c4e7  jns     short loc_18001C4F0
0x18001c4e9  mov     edx, 6B0h
0x18001c4ee  jmp     short loc_18001C50C
0x18001c4f0  lea     rcx, [rdi+18h]; this
0x18001c4f4  mov     rdx, rsi; Src
0x18001c4f7  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001c4fc  mov     ebx, eax
0x18001c4fe  mov     rcx, [rsp+28h]; this
0x18001c503  test    eax, eax
0x18001c505  jns     short loc_18001C51B
0x18001c507  mov     edx, 6B2h; void *
0x18001c50c  mov     r9d, eax; char *
0x18001c50f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001c516  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c51b  mov     rcx, [rsp+28h]; this
0x18001c520  test    ebx, ebx
0x18001c522  jns     short loc_18001C53B
0x18001c524  mov     r9d, ebx; char *
0x18001c527  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001c52e  mov     edx, 705h; void *
0x18001c533  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c538  nop
0x18001c539  jmp     short loc_18001C57A
0x18001c53b  lea     r8, ?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001c542  mov     rdx, rdi; pv
0x18001c545  lea     rcx, ?DoUnprovisionPackage@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001c54c  call    cs:__imp_CreateThreadpoolWork
0x18001c552  test    rax, rax
0x18001c555  jnz     short loc_18001C56E
0x18001c557  call    cs:__imp_GetLastError
0x18001c55d  mov     ebx, eax
0x18001c55f  test    eax, eax
0x18001c561  jle     short loc_18001C578
0x18001c563  movzx   ebx, ax
0x18001c566  or      ebx, 80070000h
0x18001c56c  jmp     short loc_18001C578
0x18001c56e  mov     rcx, rax; pwk
0x18001c571  call    cs:__imp_SubmitThreadpoolWork
0x18001c577  nop
0x18001c578  xor     edi, edi
0x18001c57a  mov     rcx, rdi
0x18001c57d  call    ??$AutoPtrDeallocate@VUnprovisionPackageParameters@@@Common@@YAXPEAVUnprovisionPackageParameters@@@Z; Common::AutoPtrDeallocate<UnprovisionPackageParameters>(UnprovisionPackageParameters *)
0x18001c582  test    ebx, ebx
0x18001c584  jns     short loc_18001C59F
0x18001c586  mov     rcx, [rsp+28h]; this
0x18001c58b  mov     r9d, ebx; char *
0x18001c58e  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001c595  mov     edx, 4Bh ; 'K'; void *
0x18001c59a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c59f  mov     eax, ebx
0x18001c5a1  mov     rbx, [rsp+28h+arg_8]
0x18001c5a6  mov     rsi, [rsp+28h+arg_10]
0x18001c5ab  add     rsp, 20h
0x18001c5af  pop     rdi
0x18001c5b0  retn
```
