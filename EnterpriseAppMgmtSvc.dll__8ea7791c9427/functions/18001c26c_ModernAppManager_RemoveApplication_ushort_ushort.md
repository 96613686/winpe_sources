# ModernAppManager::RemoveApplication(ushort *,ushort *)

- ea: `0x18001c26c`
- end: `0x18001c448`
- name: `?RemoveApplication@ModernAppManager@@QEAAJPEAG0@Z`
- size: `476`
- prototype: `int(ModernAppManager *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ce70`

## callees

- `0x180001bf4`
- `0x18000cfe8`
- `0x180011f54`
- `0x18001c26c`
- `0x18001cb78`
- `0x18002d838`
- `0x180065a64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001c3c7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001c3c7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001c430`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001c430`

## string_xrefs

- `0x18001c418`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\modernappmanager.cpp`
- `0x18001c295`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001c32d`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001c38b`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001c39f`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001c3f3`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ModernAppManager::RemoveApplication(
        ModernAppManager *this,
        EnterpriseModernAppManagement *a2,
        unsigned __int16 *a3)
{
  int *v5; // r9
  signed int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  _DWORD *v10; // rax
  _DWORD *v11; // rdi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int LastError; // eax
  const unsigned __int16 **v17; // [rsp+20h] [rbp-18h]
  int v18; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int16 *v20; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *Src; // [rsp+48h] [rbp+10h] BYREF
  _DWORD *v22; // [rsp+58h] [rbp+20h]

  v20 = (unsigned __int16 *)this;
  tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get();
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 2147942487LL;
    v8 = 1919;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)v7,
      (int)v17);
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\modernappmanager.cpp",
      (const char *)(unsigned int)v6,
      (int)v17);
    return (unsigned int)v6;
  }
  Src = 0;
  LODWORD(v20) = 0;
  v9 = EnterpriseModernAppManagement::ParseRemovePackageParameterString(
         a2,
         (unsigned __int16 *)&Src,
         (const unsigned __int16 **)&v20,
         v5,
         v17);
  v6 = v9;
  if ( v9 < 0 )
  {
    v7 = (unsigned int)v9;
    v8 = 1924;
    goto LABEL_3;
  }
  v10 = operator new(0x38u);
  v11 = v10;
  if ( v10 )
  {
    *((_QWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 3) = 0;
    *((_QWORD *)v10 + 6) = 0;
    *(_OWORD *)v10 = 0;
    *((_OWORD *)v10 + 2) = 0;
  }
  else
  {
    v11 = 0;
  }
  v22 = v11;
  if ( !v11 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x787,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)0x8007000ELL,
      (int)v17);
    v12 = 0;
LABEL_11:
    Common::AutoPtrDeallocate<RemovePackageForAllUsersParameters>(v12);
    goto LABEL_23;
  }
  v6 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v11, Src);
  if ( v6 < 0 )
  {
    v13 = 1828;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v6,
      (int)v17);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v6,
      v18);
    v12 = v11;
    goto LABEL_11;
  }
  v11[6] = (_DWORD)v20;
  v6 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)(v11 + 8), a3);
  if ( v6 < 0 )
  {
    v13 = 1832;
    goto LABEL_16;
  }
  ThreadpoolWork = CreateThreadpoolWork(DoRemovePackageForAllUsers, v11, &g_provisioningCallbackEnvironment);
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    Common::AutoPtrDeallocate<RemovePackageForAllUsersParameters>(0);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x790,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v6,
        (int)v17);
    Common::AutoPtrDeallocate<RemovePackageForAllUsersParameters>(0);
    if ( v6 < 0 )
      goto LABEL_23;
  }
  return 0;
}

```

## disassembly

```asm
0x18001c26c  mov     [rsp+arg_0], rcx
0x18001c271  push    rbx
0x18001c272  push    rsi
0x18001c273  push    rdi; int
0x18001c274  sub     rsp, 20h
0x18001c278  mov     rsi, r8
0x18001c27b  mov     rbx, rdx
0x18001c27e  call    ?get@?$_LazyImpl@VPackageManagerWrapper@@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@V?$static_lazy@VPackageManagerWrapper@@$0A@V?$lazy_construct@VPackageManagerWrapper@@@tlx@@@3@@tlx@@QEAAAEAVPackageManagerWrapper@@XZ; tlx::_LazyImpl<PackageManagerWrapper,tlx::lazy_construct<PackageManagerWrapper>,tlx::static_lazy<PackageManagerWrapper,0,tlx::lazy_construct<PackageManagerWrapper>>>::get(void)
0x18001c283  test    rbx, rbx
0x18001c286  jnz     short loc_18001C2AB
0x18001c288  mov     ebx, 80070057h
0x18001c28d  mov     r9d, ebx; char *
0x18001c290  mov     edx, 77Fh; void *
0x18001c295  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001c29c  mov     rcx, [rsp+38h]; this
0x18001c2a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2a6  jmp     loc_18001C410
0x18001c2ab  mov     [rsp+38h+Src], 0
0x18001c2b4  mov     dword ptr [rsp+38h+arg_0], 0
0x18001c2bc  lea     r8, [rsp+38h+arg_0]; unsigned __int16 **
0x18001c2c1  lea     rdx, [rsp+38h+Src]; unsigned __int16 *
0x18001c2c6  mov     rcx, rbx; this
0x18001c2c9  call    ?ParseRemovePackageParameterString@EnterpriseModernAppManagement@@YAJPEAGPEAPEBGPEAH1@Z; EnterpriseModernAppManagement::ParseRemovePackageParameterString(ushort *,ushort const * *,int *,ushort const * *)
0x18001c2ce  mov     ebx, eax
0x18001c2d0  test    eax, eax
0x18001c2d2  jns     short loc_18001C2DE
0x18001c2d4  mov     r9d, eax
0x18001c2d7  mov     edx, 784h
0x18001c2dc  jmp     short loc_18001C295
0x18001c2de  mov     ecx, 38h ; '8'; Size
0x18001c2e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c2e8  mov     rdi, rax
0x18001c2eb  test    rax, rax
0x18001c2ee  jz      short loc_18001C314
0x18001c2f0  mov     qword ptr [rax+10h], 0
0x18001c2f8  mov     qword ptr [rax+18h], 0
0x18001c300  mov     qword ptr [rax+30h], 0
0x18001c308  xorps   xmm0, xmm0
0x18001c30b  movups  xmmword ptr [rax], xmm0
0x18001c30e  movups  xmmword ptr [rax+20h], xmm0
0x18001c312  jmp     short loc_18001C316
0x18001c314  xor     edi, edi
0x18001c316  mov     [rsp+38h+arg_18], rdi
0x18001c31b  test    rdi, rdi
0x18001c31e  jnz     short loc_18001C34B
0x18001c320  mov     rcx, [rsp+38h]; this
0x18001c325  mov     ebx, 8007000Eh
0x18001c32a  mov     r9d, ebx; char *
0x18001c32d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001c334  mov     edx, 787h; void *
0x18001c339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c33e  nop
0x18001c33f  xor     ecx, ecx
0x18001c341  call    ??$AutoPtrDeallocate@VRemovePackageForAllUsersParameters@@@Common@@YAXPEAVRemovePackageForAllUsersParameters@@@Z; Common::AutoPtrDeallocate<RemovePackageForAllUsersParameters>(RemovePackageForAllUsersParameters *)
0x18001c346  jmp     loc_18001C410
0x18001c34b  mov     rdx, [rsp+38h+Src]; Src
0x18001c350  mov     rcx, rdi; this
0x18001c353  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001c358  mov     ebx, eax
0x18001c35a  test    eax, eax
0x18001c35c  jns     short loc_18001C365
0x18001c35e  mov     edx, 724h
0x18001c363  jmp     short loc_18001C383
0x18001c365  mov     eax, dword ptr [rsp+38h+arg_0]
0x18001c369  mov     [rdi+18h], eax
0x18001c36c  lea     rcx, [rdi+20h]; this
0x18001c370  mov     rdx, rsi; Src
0x18001c373  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18001c378  mov     ebx, eax
0x18001c37a  test    eax, eax
0x18001c37c  jns     short loc_18001C3B6
0x18001c37e  mov     edx, 728h; void *
0x18001c383  mov     r9d, ebx; char *
0x18001c386  mov     rcx, [rsp+38h]; this
0x18001c38b  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001c392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c397  mov     rcx, [rsp+38h]; this
0x18001c39c  mov     r9d, ebx; char *
0x18001c39f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001c3a6  mov     edx, 788h; void *
0x18001c3ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c3b0  nop
0x18001c3b1  mov     rcx, rdi
0x18001c3b4  jmp     short loc_18001C341
0x18001c3b6  lea     r8, ?g_provisioningCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001c3bd  mov     rdx, rdi; pv
0x18001c3c0  lea     rcx, ?DoRemovePackageForAllUsers@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001c3c7  call    cs:__imp_CreateThreadpoolWork
0x18001c3cd  test    rax, rax
0x18001c3d0  jnz     short loc_18001C42D
0x18001c3d2  call    cs:__imp_GetLastError
0x18001c3d8  mov     ebx, eax
0x18001c3da  test    eax, eax
0x18001c3dc  jle     short loc_18001C3E7
0x18001c3de  movzx   ebx, ax
0x18001c3e1  or      ebx, 80070000h
0x18001c3e7  test    ebx, ebx
0x18001c3e9  jns     short loc_18001C405
0x18001c3eb  mov     rcx, [rsp+38h]; this
0x18001c3f0  mov     r9d, ebx; char *
0x18001c3f3  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001c3fa  mov     edx, 790h; void *
0x18001c3ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c404  nop
0x18001c405  xor     ecx, ecx
0x18001c407  call    ??$AutoPtrDeallocate@VRemovePackageForAllUsersParameters@@@Common@@YAXPEAVRemovePackageForAllUsersParameters@@@Z; Common::AutoPtrDeallocate<RemovePackageForAllUsersParameters>(RemovePackageForAllUsersParameters *)
0x18001c40c  test    ebx, ebx
0x18001c40e  jns     short loc_18001C43E
0x18001c410  mov     rcx, [rsp+38h]; this
0x18001c415  mov     r9d, ebx; char *
0x18001c418  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001c41f  mov     edx, 59h ; 'Y'; void *
0x18001c424  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c429  mov     eax, ebx
0x18001c42b  jmp     short loc_18001C440
0x18001c42d  mov     rcx, rax; pwk
0x18001c430  call    cs:__imp_SubmitThreadpoolWork
0x18001c436  nop
0x18001c437  xor     ecx, ecx
0x18001c439  call    ??$AutoPtrDeallocate@VRemovePackageForAllUsersParameters@@@Common@@YAXPEAVRemovePackageForAllUsersParameters@@@Z; Common::AutoPtrDeallocate<RemovePackageForAllUsersParameters>(RemovePackageForAllUsersParameters *)
0x18001c43e  xor     eax, eax
0x18001c440  add     rsp, 20h
0x18001c444  pop     rdi
0x18001c445  pop     rsi
0x18001c446  pop     rbx
0x18001c447  retn
```
