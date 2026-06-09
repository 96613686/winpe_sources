# AppxAllUserStore::RemoveDownlevelInstalledPackagesFromRegistryStoreImplementation(HKEY__ *,ushort const *,ushort const *,AppxAllUserStore::_PackageInfo * *)

- ea: `0x180019604`
- end: `0x180019875`
- name: `?RemoveDownlevelInstalledPackagesFromRegistryStoreImplementation@AppxAllUserStore@@YAJPEAUHKEY__@@PEBG1PEAPEAU_PackageInfo@1@@Z`
- size: `625`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct AppxAllUserStore::_PackageInfo **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f5f0`

## callees

- `0x180004920`
- `0x180004968`
- `0x180006c00`
- `0x180006d40`
- `0x180007860`
- `0x180007a10`
- `0x18000d6a0`
- `0x18000d710`
- `0x180018248`
- `0x180019604`
- `0x18002341c`
- `0x1800279a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800197c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800197c3`

## string_xrefs

- `0x180019623`: `DownlevelInstalled`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::RemoveDownlevelInstalledPackagesFromRegistryStoreImplementation(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct Common::StringBuffer *a4)
{
  int AllUserChildStorePath; // eax
  unsigned int v9; // ebx
  int appended; // eax
  __int64 v12; // rdx
  LSTATUS v13; // eax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  int v16; // eax
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  LSTATUS v19; // eax
  void *v20; // rcx
  void *v21; // rax
  HKEY phkResult; // [rsp+20h] [rbp-58h] BYREF
  void *v23; // [rsp+28h] [rbp-50h] BYREF
  void *v24; // [rsp+30h] [rbp-48h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-40h] BYREF
  int v26; // [rsp+48h] [rbp-30h]
  _QWORD v27[5]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v26 = 0;
  *(_OWORD *)lpSubKey = 0;
  AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                            (AppxAllUserStore *)L"DownlevelInstalled",
                            0,
                            (unsigned int *)lpSubKey,
                            a4);
  v9 = AllUserChildStorePath;
  if ( AllUserChildStorePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61C,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)(unsigned int)AllUserChildStorePath,
      (int)phkResult);
    if ( lpSubKey[1] )
      Common::GlobalHeap::Free((void *)lpSubKey[1]);
    return v9;
  }
  v27[1] = lpSubKey;
  v27[0] = &Common::StringBufferBuilder::`vftable';
  v27[2] = lpSubKey;
  appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v27, a2);
  v9 = appended;
  if ( appended < 0 )
  {
    v12 = 1566;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
      (const char *)(unsigned int)appended,
      (int)phkResult);
LABEL_31:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
    return v9;
  }
  appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v27, L"\\");
  v9 = appended;
  if ( appended < 0 )
  {
    v12 = 1567;
    goto LABEL_9;
  }
  appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v27, a3);
  v9 = appended;
  if ( appended < 0 )
  {
    v12 = 1568;
    goto LABEL_9;
  }
  phkResult = 0;
  v13 = Common::RegistryKey::Open(&phkResult, hKey, lpSubKey[1], 0x20019u);
  v9 = v13;
  if ( (unsigned int)(v13 + 2147024894) > 1 )
  {
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x628,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
        (const char *)(unsigned int)v13,
        (int)phkResult);
LABEL_30:
      Common::RegistryKey::~RegistryKey(&phkResult);
      goto LABEL_31;
    }
    v24 = 0;
    Common::GlobalHeap::Alloc(0x18u, &v24);
    v14 = v24;
    if ( v24 )
    {
      *(_QWORD *)v24 = 0;
      v14[1] = 0;
      v14[2] = 0;
      v23 = v14;
      v15 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
              &v24,
              (__int64)&v23);
      v16 = AppxAllUserStore::EnumKeyAndDoActionForAllSubkeys__lambda_a6bfdad390e659db89e095e9dd5f98a7___(
              &phkResult,
              *v15);
      v9 = v16;
      if ( v16 < 0 )
      {
        v17 = (unsigned int)v16;
        v18 = 1591;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
          (const char *)v17,
          (int)phkResult);
        Common::GlobalHeap::Free(v23);
        goto LABEL_30;
      }
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      phkResult = 0;
      v19 = RegDeleteTreeW(hKey, lpSubKey[1]);
      v9 = v19;
      if ( v19 > 0 )
        v9 = (unsigned __int16)v19 | 0x80070000;
      if ( (int)v9 > -2147024895 && v9 + 2147024892 > 0x7FF8FFFB )
      {
        v20 = v23;
        if ( *(_QWORD *)v23 )
        {
          v21 = v23;
          v20 = 0;
          v23 = 0;
          *(_QWORD *)a4 = v21;
        }
        Common::GlobalHeap::Free(v20);
        goto LABEL_25;
      }
      v18 = 1599;
    }
    else
    {
      v23 = 0;
      v9 = -2147024882;
      v18 = 1579;
    }
    v17 = v9;
    goto LABEL_29;
  }
LABEL_25:
  Common::RegistryKey::~RegistryKey(&phkResult);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x180019604  push    rbp
0x180019606  push    rbx
0x180019607  push    rsi
0x180019608  push    rdi
0x180019609  push    r14
0x18001960b  push    r15
0x18001960d  mov     rbp, rsp
0x180019610  sub     rsp, 78h
0x180019614  mov     rsi, r8
0x180019617  mov     r14, rdx
0x18001961a  mov     rdi, rcx
0x18001961d  lea     r8, [rbp+lpSubKey]; bool
0x180019621  xor     eax, eax
0x180019623  lea     rcx, ?downlevelInstalledApplicationsString@AppxAllUserStore@@3QBGB; "DownlevelInstalled"
0x18001962a  xorps   xmm0, xmm0
0x18001962d  mov     [rbp+var_30], eax
0x180019630  xor     edx, edx; unsigned __int16 *
0x180019632  mov     r15, r9
0x180019635  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180019639  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x18001963e  mov     ebx, eax
0x180019640  test    eax, eax
0x180019642  jns     short loc_180019671
0x180019644  mov     rcx, [rbp+30h]; this
0x180019648  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x18001964f  mov     r9d, eax; char *
0x180019652  mov     edx, 61Ch; void *
0x180019657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001965c  mov     rcx, [rbp+lpSubKey+8]; void *
0x180019660  test    rcx, rcx
0x180019663  jz      short loc_18001966A
0x180019665  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18001966a  mov     eax, ebx
0x18001966c  jmp     loc_18001981C
0x180019671  lea     rax, [rbp+lpSubKey]
0x180019675  mov     rdx, r14; unsigned __int16 *
0x180019678  mov     [rbp+var_20], rax
0x18001967c  lea     rcx, [rbp+var_28]; this
0x180019680  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180019687  mov     [rbp+var_28], rax
0x18001968b  lea     rax, [rbp+lpSubKey]
0x18001968f  mov     [rbp+var_18], rax
0x180019693  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180019698  mov     ebx, eax
0x18001969a  test    eax, eax
0x18001969c  jns     short loc_1800196A5
0x18001969e  mov     edx, 61Eh
0x1800196a3  jmp     short loc_1800196C0
0x1800196a5  lea     rdx, asc_18004F868; "\\"
0x1800196ac  lea     rcx, [rbp+var_28]; this
0x1800196b0  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800196b5  mov     ebx, eax
0x1800196b7  test    eax, eax
0x1800196b9  jns     short loc_1800196D8
0x1800196bb  mov     edx, 61Fh; void *
0x1800196c0  mov     rcx, [rbp+30h]; this
0x1800196c4  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800196cb  mov     r9d, eax; char *
0x1800196ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800196d3  jmp     loc_180019867
0x1800196d8  mov     rdx, rsi; unsigned __int16 *
0x1800196db  lea     rcx, [rbp+var_28]; this
0x1800196df  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800196e4  mov     ebx, eax
0x1800196e6  test    eax, eax
0x1800196e8  jns     short loc_1800196F1
0x1800196ea  mov     edx, 620h
0x1800196ef  jmp     short loc_1800196C0
0x1800196f1  mov     r8, [rbp+lpSubKey+8]; lpSubKey
0x1800196f5  lea     rcx, [rbp+phkResult]; phkResult
0x1800196f9  mov     r9d, 20019h; samDesired
0x1800196ff  mov     [rbp+phkResult], 0
0x180019707  mov     rdx, rdi; hKey
0x18001970a  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18001970f  mov     ebx, eax
0x180019711  lea     ecx, [rax+7FF8FFFEh]
0x180019717  cmp     ecx, 1
0x18001971a  jbe     loc_180019808
0x180019720  test    eax, eax
0x180019722  jns     short loc_180019741
0x180019724  mov     rcx, [rbp+30h]; this
0x180019728  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x18001972f  mov     r9d, eax; char *
0x180019732  mov     edx, 628h; void *
0x180019737  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001973c  jmp     loc_18001985E
0x180019741  lea     rdx, [rbp+var_48]; void **
0x180019745  mov     [rbp+var_48], 0
0x18001974d  mov     ecx, 18h; Size
0x180019752  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x180019757  mov     rax, [rbp+var_48]
0x18001975b  test    rax, rax
0x18001975e  jz      loc_180019830
0x180019764  mov     qword ptr [rax], 0
0x18001976b  lea     rdx, [rbp+var_50]
0x18001976f  mov     qword ptr [rax+8], 0
0x180019777  lea     rcx, [rbp+var_48]
0x18001977b  mov     qword ptr [rax+10h], 0
0x180019783  mov     [rbp+var_50], rax
0x180019787  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001978c  lea     rcx, [rbp+phkResult]
0x180019790  mov     rdx, [rax]
0x180019793  call    AppxAllUserStore__EnumKeyAndDoActionForAllSubkeys__lambda_a6bfdad390e659db89e095e9dd5f98a7___
0x180019798  mov     ebx, eax
0x18001979a  test    eax, eax
0x18001979c  jns     short loc_1800197AB
0x18001979e  mov     r9d, eax
0x1800197a1  mov     edx, 637h
0x1800197a6  jmp     loc_180019845
0x1800197ab  mov     rcx, [rbp+phkResult]
0x1800197af  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800197b4  mov     rdx, [rbp+lpSubKey+8]; lpSubKey
0x1800197b8  mov     rcx, rdi; hKey
0x1800197bb  mov     [rbp+phkResult], 0
0x1800197c3  call    cs:__imp_RegDeleteTreeW
0x1800197c9  mov     ebx, eax
0x1800197cb  test    eax, eax
0x1800197cd  jle     short loc_1800197D8
0x1800197cf  movzx   ebx, ax
0x1800197d2  or      ebx, 80070000h
0x1800197d8  cmp     ebx, 80070001h
0x1800197de  jle     short loc_180019829
0x1800197e0  lea     eax, [rbx+7FF8FFFCh]
0x1800197e6  cmp     eax, 7FF8FFFBh
0x1800197eb  jbe     short loc_180019829
0x1800197ed  mov     rcx, [rbp+var_50]
0x1800197f1  cmp     qword ptr [rcx], 0
0x1800197f5  jz      short loc_180019803
0x1800197f7  mov     rax, rcx
0x1800197fa  xor     ecx, ecx; void *
0x1800197fc  mov     [rbp+var_50], rcx
0x180019800  mov     [r15], rax
0x180019803  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180019808  lea     rcx, [rbp+phkResult]; this
0x18001980c  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180019811  lea     rcx, [rbp+lpSubKey]; this
0x180019815  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18001981a  xor     eax, eax
0x18001981c  add     rsp, 78h
0x180019820  pop     r15
0x180019822  pop     r14
0x180019824  pop     rdi
0x180019825  pop     rsi
0x180019826  pop     rbx
0x180019827  pop     rbp
0x180019828  retn
0x180019829  mov     edx, 63Fh
0x18001982e  jmp     short loc_180019842
0x180019830  mov     [rbp+var_50], 0
0x180019838  mov     ebx, 8007000Eh
0x18001983d  mov     edx, 62Bh; void *
0x180019842  mov     r9d, ebx; char *
0x180019845  mov     rcx, [rbp+30h]; this
0x180019849  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x180019850  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019855  mov     rcx, [rbp+var_50]; void *
0x180019859  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18001985e  lea     rcx, [rbp+phkResult]; this
0x180019862  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180019867  lea     rcx, [rbp+lpSubKey]; this
0x18001986b  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180019870  jmp     loc_18001966A
```
