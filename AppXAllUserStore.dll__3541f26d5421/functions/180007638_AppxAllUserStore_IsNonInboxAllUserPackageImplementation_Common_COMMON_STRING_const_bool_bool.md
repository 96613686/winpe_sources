# AppxAllUserStore::IsNonInboxAllUserPackageImplementation(Common::COMMON_STRING const *,bool,bool *)

- ea: `0x180007638`
- end: `0x180007856`
- name: `?IsNonInboxAllUserPackageImplementation@AppxAllUserStore@@YAJPEBUCOMMON_STRING@Common@@_NPEA_N@Z`
- size: `542`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, const struct Common::COMMON_STRING *, bool, bool *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013370`
- `0x1800134d0`

## callees

- `0x180004920`
- `0x180004968`
- `0x180006d40`
- `0x180007278`
- `0x180007638`
- `0x180007860`
- `0x180007a10`
- `0x180008780`
- `0x18000bae8`
- `0x180018248`
- `0x18002b018`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800076b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800076b8`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::IsNonInboxAllUserPackageImplementation(
        AppxAllUserStore *this,
        const struct Common::COMMON_STRING *a2,
        unsigned __int16 *a3,
        struct Common::StringBuffer *a4)
{
  unsigned int v5; // r14d
  int AllUserChildStorePath; // eax
  int IsPresentInRegStore; // ebx
  const WCHAR *v9; // rbx
  LSTATUS v10; // eax
  bool *v11; // r9
  const wchar_t *v12; // rsi
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  int IsPackageOnPreinstalledVolumeImplementation; // eax
  int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  int phkResultb; // [rsp+20h] [rbp-30h]
  struct Common::RegistryKey *v22; // [rsp+28h] [rbp-28h]
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-20h] BYREF
  int v24; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  bool v26; // [rsp+90h] [rbp+40h] BYREF
  HKEY v27; // [rsp+98h] [rbp+48h] BYREF

  v5 = (unsigned __int8)a2;
  *(_BYTE *)a3 = 0;
  v24 = 0;
  LOBYTE(a2) = 1;
  *(_OWORD *)lpSubKey = 0;
  AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                            (AppxAllUserStore *)L"Applications",
                            (const unsigned __int16 *)a2,
                            (unsigned int *)lpSubKey,
                            a4);
  IsPresentInRegStore = AllUserChildStorePath;
  if ( AllUserChildStorePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)(unsigned int)AllUserChildStorePath,
      phkResult);
    goto LABEL_15;
  }
  v9 = lpSubKey[1];
  v27 = 0;
  Common::AutoHandleCloseHKEY<HKEY__ *>(0);
  v27 = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &v27);
  IsPresentInRegStore = v10;
  if ( v10 > 0 )
    IsPresentInRegStore = (unsigned __int16)v10 | 0x80070000;
  if ( IsPresentInRegStore < 0 )
  {
    v16 = (unsigned int)IsPresentInRegStore;
    v17 = 296;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)v16,
      phkResulta);
    Common::RegistryKey::~RegistryKey(&v27);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
    return (unsigned int)IsPresentInRegStore;
  }
  v12 = (const wchar_t *)*((_QWORD *)this + 1);
  *(_BYTE *)a3 = 0;
  IsPresentInRegStore = AppxAllUserStore::IsPresentInRegStore(&v27, v12, a3, v11);
  if ( IsPresentInRegStore < 0 )
  {
    v14 = 344;
    goto LABEL_20;
  }
  if ( !*(_BYTE *)a3 )
  {
    if ( (_BYTE)v5 )
    {
      IsPresentInRegStore = AppxAllUserStore::IsFamilyNameInRegStore((AppxAllUserStore *)&v27, v12, 0, (bool)a3, 0, v22);
      if ( IsPresentInRegStore < 0 )
      {
        v14 = 354;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
          (const char *)(unsigned int)IsPresentInRegStore,
          phkResulta);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14B,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
          (const char *)(unsigned int)IsPresentInRegStore,
          phkResultb);
        v15 = 298;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
          (const char *)(unsigned int)IsPresentInRegStore,
          phkResulta);
        Common::AutoHandleCloseHKEY<HKEY__ *>(v27);
LABEL_15:
        if ( lpSubKey[1] )
          Common::GlobalHeap::Free((void *)lpSubKey[1]);
        return (unsigned int)IsPresentInRegStore;
      }
    }
    if ( !*(_BYTE *)a3 )
    {
      v26 = 0;
      IsPresentInRegStore = Common::StateSeparation::GetIsStateSeparationEnabled(&v26);
      if ( IsPresentInRegStore < 0 )
      {
        v15 = 307;
        goto LABEL_22;
      }
      if ( v26 )
      {
        IsPackageOnPreinstalledVolumeImplementation = AppxAllUserStore::IsPackageOnPreinstalledVolumeImplementation(
                                                        this,
                                                        v5,
                                                        a3);
        IsPresentInRegStore = IsPackageOnPreinstalledVolumeImplementation;
        if ( IsPackageOnPreinstalledVolumeImplementation < 0 )
        {
          v16 = (unsigned int)IsPackageOnPreinstalledVolumeImplementation;
          v17 = 313;
          goto LABEL_27;
        }
      }
    }
  }
  Common::AutoHandleCloseHKEY<HKEY__ *>(v27);
  if ( lpSubKey[1] )
    Common::GlobalHeap::Free((void *)lpSubKey[1]);
  return 0;
}

```

## disassembly

```asm
0x180007638  mov     [rsp-28h+arg_0], rbx
0x18000763d  push    rbp
0x18000763e  push    rsi
0x18000763f  push    rdi
0x180007640  push    r14
0x180007642  push    r15
0x180007644  mov     rbp, rsp
0x180007647  sub     rsp, 50h
0x18000764b  mov     rdi, r8
0x18000764e  movzx   r14d, dl
0x180007652  mov     r15, rcx
0x180007655  mov     byte ptr [r8], 0
0x180007659  xor     eax, eax
0x18000765b  lea     r8, [rbp+lpSubKey]; bool
0x18000765f  xorps   xmm0, xmm0
0x180007662  mov     [rbp+var_10], eax
0x180007665  mov     dl, 1; unsigned __int16 *
0x180007667  lea     rcx, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x18000766e  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180007672  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x180007677  mov     ebx, eax
0x180007679  test    eax, eax
0x18000767b  js      loc_180007752
0x180007681  mov     rbx, [rbp+lpSubKey+8]
0x180007685  xor     ecx, ecx
0x180007687  mov     [rbp+arg_18], 0
0x18000768f  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180007694  lea     rax, [rbp+arg_18]
0x180007698  mov     [rbp+arg_18], 0
0x1800076a0  mov     r9d, 20019h; samDesired
0x1800076a6  mov     [rsp+50h+phkResult], rax; int
0x1800076ab  xor     r8d, r8d; ulOptions
0x1800076ae  mov     rdx, rbx; lpSubKey
0x1800076b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800076b8  call    cs:__imp_RegOpenKeyExW
0x1800076be  mov     ebx, eax
0x1800076c0  test    eax, eax
0x1800076c2  jle     short loc_1800076CD
0x1800076c4  movzx   ebx, ax
0x1800076c7  or      ebx, 80070000h
0x1800076cd  test    ebx, ebx
0x1800076cf  js      loc_1800077FE
0x1800076d5  mov     rsi, [r15+8]
0x1800076d9  lea     rcx, [rbp+arg_18]; this
0x1800076dd  mov     rdx, rsi; struct Common::RegistryKey *
0x1800076e0  mov     byte ptr [rdi], 0
0x1800076e3  mov     r8, rdi; unsigned __int16 *
0x1800076e6  call    ?IsPresentInRegStore@AppxAllUserStore@@YAJPEBVRegistryKey@Common@@QEBGPEA_N@Z; AppxAllUserStore::IsPresentInRegStore(Common::RegistryKey const *,ushort const * const,bool *)
0x1800076eb  mov     ebx, eax
0x1800076ed  test    eax, eax
0x1800076ef  js      loc_180007808
0x1800076f5  cmp     byte ptr [rdi], 0
0x1800076f8  jnz     short loc_180007725
0x1800076fa  test    r14b, r14b
0x1800076fd  jnz     short loc_18000777C
0x1800076ff  cmp     byte ptr [rdi], 0
0x180007702  jnz     short loc_180007725
0x180007704  lea     rcx, [rbp+arg_10]; bool *
0x180007708  mov     [rbp+arg_10], 0
0x18000770c  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x180007711  mov     ebx, eax
0x180007713  test    eax, eax
0x180007715  js      loc_1800077D8
0x18000771b  cmp     [rbp+arg_10], 0
0x18000771f  jnz     loc_18000780F
0x180007725  mov     rcx, [rbp+arg_18]
0x180007729  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000772e  mov     rcx, [rbp+lpSubKey+8]; void *
0x180007732  test    rcx, rcx
0x180007735  jz      short loc_18000773C
0x180007737  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000773c  xor     eax, eax
0x18000773e  mov     rbx, [rsp+50h+arg_0]
0x180007746  add     rsp, 50h
0x18000774a  pop     r15
0x18000774c  pop     r14
0x18000774e  pop     rdi
0x18000774f  pop     rsi
0x180007750  pop     rbp
0x180007751  retn
0x180007752  mov     rcx, [rbp+28h]; this
0x180007756  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000775d  mov     r9d, ebx; char *
0x180007760  mov     edx, 125h; void *
0x180007765  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000776a  mov     rcx, [rbp+lpSubKey+8]; void *
0x18000776e  test    rcx, rcx
0x180007771  jz      short loc_180007778
0x180007773  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180007778  mov     eax, ebx
0x18000777a  jmp     short loc_18000773E
0x18000777c  mov     r9, rdi; bool
0x18000777f  mov     [rsp+50h+phkResult], 0; int
0x180007788  xor     r8d, r8d; unsigned __int16 *
0x18000778b  lea     rcx, [rbp+arg_18]; this
0x18000778f  mov     rdx, rsi; lpString1
0x180007792  call    ?IsFamilyNameInRegStore@AppxAllUserStore@@YAJPEAVRegistryKey@Common@@QEBG_NPEA_N0@Z; AppxAllUserStore::IsFamilyNameInRegStore(Common::RegistryKey *,ushort const * const,bool,bool *,Common::RegistryKey *)
0x180007797  mov     ebx, eax
0x180007799  test    eax, eax
0x18000779b  jns     loc_1800076FF
0x1800077a1  mov     edx, 162h; void *
0x1800077a6  mov     rcx, [rbp+28h]; this
0x1800077aa  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800077b1  mov     r9d, ebx; char *
0x1800077b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077b9  mov     rcx, [rbp+28h]; this
0x1800077bd  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800077c4  mov     r9d, ebx; char *
0x1800077c7  mov     edx, 14Bh; void *
0x1800077cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077d1  mov     edx, 12Ah
0x1800077d6  jmp     short loc_1800077DD
0x1800077d8  mov     edx, 133h; void *
0x1800077dd  mov     rcx, [rbp+28h]; this
0x1800077e1  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800077e8  mov     r9d, ebx; char *
0x1800077eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077f0  mov     rcx, [rbp+arg_18]
0x1800077f4  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800077f9  jmp     loc_18000776A
0x1800077fe  mov     r9d, ebx
0x180007801  mov     edx, 128h
0x180007806  jmp     short loc_18000782F
0x180007808  mov     edx, 158h
0x18000780d  jmp     short loc_1800077A6
0x18000780f  mov     edx, r14d
0x180007812  mov     r8, rdi
0x180007815  mov     rcx, r15
0x180007818  call    ?IsPackageOnPreinstalledVolumeImplementation@AppxAllUserStore@@YAJPEBUCOMMON_STRING@Common@@W4PackageSearchType@1@PEA_N@Z; AppxAllUserStore::IsPackageOnPreinstalledVolumeImplementation(Common::COMMON_STRING const *,AppxAllUserStore::PackageSearchType,bool *)
0x18000781d  mov     ebx, eax
0x18000781f  test    eax, eax
0x180007821  jns     loc_180007725
0x180007827  mov     r9d, eax; char *
0x18000782a  mov     edx, 139h; void *
0x18000782f  mov     rcx, [rbp+28h]; this
0x180007833  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000783a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000783f  lea     rcx, [rbp+arg_18]; this
0x180007843  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180007848  lea     rcx, [rbp+lpSubKey]; this
0x18000784c  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180007851  jmp     loc_180007778
```
