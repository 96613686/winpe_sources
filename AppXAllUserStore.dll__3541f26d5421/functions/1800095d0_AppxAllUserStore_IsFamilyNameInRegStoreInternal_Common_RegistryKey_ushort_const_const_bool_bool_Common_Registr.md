# AppxAllUserStore::IsFamilyNameInRegStoreInternal(Common::RegistryKey *,ushort const * const,bool,bool *,Common::RegistryKey *)

- ea: `0x1800095d0`
- end: `0x1800099e4`
- name: `?IsFamilyNameInRegStoreInternal@AppxAllUserStore@@YAJPEAVRegistryKey@Common@@QEBG_NPEA_N0@Z`
- size: `1044`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, struct Common::RegistryKey *, const unsigned __int16 *const, bool, bool *, struct Common::RegistryKey *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800095d0`
- `0x18000bae8`

## callees

- `0x180004940`
- `0x180004968`
- `0x180007a10`
- `0x1800095d0`
- `0x1800099f0`
- `0x18000a600`
- `0x18000ce40`
- `0x18000d6a0`
- `0x180018248`
- `0x18004c98a`
- `0x18004c9d0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180009764`
- `ntdll!RtlFreeHeap` at `0x180009764`
- `ntdll!RtlAllocateHeap` at `0x1800096bb`
- `ntdll!RtlAllocateHeap` at `0x1800096bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009687`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000973f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009687`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000973f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009660`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009660`

## string_xrefs

- `0x180009948`: `onecore\admin\appmodel\appxalluserstore\src\commonutilities.cpp`

## pseudocode

```c
LSTATUS __fastcall AppxAllUserStore::IsFamilyNameInRegStoreInternal(
        HKEY *this,
        WCHAR *a2,
        const unsigned __int16 *const a3,
        __int64 a4,
        bool *a5)
{
  char v5; // r12
  DWORD v7; // esi
  HKEY v9; // rcx
  LSTATUS result; // eax
  PVOID ProcessHeap; // rcx
  PVOID Heap; // rdi
  __int64 v13; // rdx
  int v14; // r14d
  void *v15; // rbx
  HKEY v16; // rdx
  LSTATUS IsFamilyNameInRegStoreInternal; // edi
  _BYTE *v18; // r14
  __int64 v19; // rdx
  int v20; // eax
  int v21; // edi
  struct Common::AutoHandleHKEY *v22; // rbx
  int v23; // eax
  int v24; // ebx
  int lpReserved; // [rsp+28h] [rbp-E0h]
  int lpReserveda; // [rsp+28h] [rbp-E0h]
  struct Common::RegistryKey *lpClass; // [rsp+30h] [rbp-D8h]
  HKEY phkResult; // [rsp+48h] [rbp-C0h] BYREF
  PVOID v29; // [rsp+50h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v31; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v32; // [rsp+60h] [rbp-A8h] BYREF
  bool v33[8]; // [rsp+68h] [rbp-A0h]
  struct Common::AutoHandleHKEY *v34; // [rsp+70h] [rbp-98h]
  WCHAR Name[128]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v36[30]; // [rsp+178h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B0h] [rbp+1A8h]

  v5 = (char)a3;
  v34 = (struct Common::AutoHandleHKEY *)a5;
  v7 = 0;
  *(_QWORD *)v33 = a4;
  while ( 1 )
  {
    memset_0(Name, 0, sizeof(Name));
    v9 = *this;
    cchName = 128;
    result = RegEnumKeyExW(v9, v7, Name, &cchName, 0, 0, 0, 0);
    if ( result )
    {
      if ( result != 259 )
      {
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
        return result;
      }
      return 0;
    }
    if ( CompareStringOrdinal(a2, -1, Name, -1, 1) == 2 )
    {
      v22 = v34;
      **(_BYTE **)v33 = 1;
      if ( v22 )
      {
        v23 = Common::RegistryKey::OpenSubKey((Common::RegistryKey *)this, Name, 0x20019u, v22);
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC1,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
            (const char *)(unsigned int)v23,
            lpReserved);
          return v24;
        }
      }
      return 0;
    }
    ProcessHeap = ReservedForLocalUse::g_heap;
    v29 = 0;
    LODWORD(v32) = 65;
    if ( !ReservedForLocalUse::g_heap )
    {
      ProcessHeap = NtCurrentPeb()->ProcessHeap;
      ReservedForLocalUse::g_heap = ProcessHeap;
    }
    Heap = RtlAllocateHeap(ProcessHeap, 0, 0x82u);
    if ( !Heap )
      break;
    memset_0(v36, 0, sizeof(v36));
    v31 = 240;
    v14 = ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageIdBasicFromFullName(
            Name,
            v13,
            &v31,
            (__int64)v36);
    if ( v14
      || (v14 = ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageFamilyNameFromId(
                  v36,
                  &v32,
                  Heap)) != 0 )
    {
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      Common::GlobalHeap::Free(Heap);
      if ( v14 != -2147024809 )
        goto LABEL_35;
      Common::GlobalHeap::Free(0);
      ++v7;
    }
    else
    {
      v15 = Heap;
      v29 = Heap;
      if ( CompareStringOrdinal(a2, -1, (LPCWCH)Heap, -1, 1) == 2 )
      {
        **(_BYTE **)v33 = 1;
        if ( v34 )
        {
          v20 = Common::RegistryKey::OpenSubKey((Common::RegistryKey *)this, Name, 0x20019u, v34);
          v21 = v20;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xDB,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
              (const char *)(unsigned int)v20,
              lpReserveda);
            Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(&v29);
            return v21;
          }
        }
        Common::GlobalHeap::Free(v15);
        return 0;
      }
      if ( !v5 )
        goto LABEL_11;
      v16 = *this;
      phkResult = 0;
      IsFamilyNameInRegStoreInternal = Common::RegistryKey::Open(&phkResult, v16, Name, 0x20019u);
      if ( IsFamilyNameInRegStoreInternal < 0 )
      {
        v19 = 228;
        goto LABEL_31;
      }
      v18 = *(_BYTE **)v33;
      IsFamilyNameInRegStoreInternal = AppxAllUserStore::IsFamilyNameInRegStoreInternal(
                                         (AppxAllUserStore *)&phkResult,
                                         (struct Common::RegistryKey *)a2,
                                         0,
                                         v33[0],
                                         (bool *)v34,
                                         lpClass);
      if ( IsFamilyNameInRegStoreInternal < 0 )
      {
        v19 = 234;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
          (const char *)(unsigned int)IsFamilyNameInRegStoreInternal,
          lpReserveda);
        Common::RegistryKey::~RegistryKey(&phkResult);
        Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(&v29);
        return IsFamilyNameInRegStoreInternal;
      }
      if ( *v18 )
      {
        Common::RegistryKey::~RegistryKey(&phkResult);
        Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(&v29);
        return 0;
      }
      Common::RegistryKey::~RegistryKey(&phkResult);
LABEL_11:
      RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v15);
      ++v7;
    }
  }
  v14 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1C,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\commonutilities.cpp",
    (const char *)0x8007000ELL,
    lpReserved);
LABEL_35:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD2,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\deploymentutilities.cpp",
    (const char *)(unsigned int)v14,
    lpReserved);
  Common::GlobalHeap::Free(0);
  return v14;
}

```

## disassembly

```asm
0x1800095d0  mov     r11, rsp
0x1800095d3  push    rbp
0x1800095d4  push    rbx
0x1800095d5  push    rsi
0x1800095d6  push    r12
0x1800095d8  push    r13
0x1800095da  push    r15
0x1800095dc  lea     rbp, [r11-1A8h]
0x1800095e3  sub     rsp, 278h
0x1800095ea  mov     rax, cs:__security_cookie
0x1800095f1  xor     rax, rsp
0x1800095f4  mov     [rbp+1A0h+var_40], rax
0x1800095fb  mov     rbx, [rbp+1A0h+arg_20]
0x180009602  movzx   r12d, r8b
0x180009606  mov     [rsp+2A0h+var_238], rbx
0x18000960b  mov     r15, rdx
0x18000960e  xor     ebx, ebx
0x180009610  mov     [r11+18h], rdi
0x180009614  mov     esi, ebx
0x180009616  mov     qword ptr [rsp+2A0h+var_240], r9
0x18000961b  mov     r13, rcx
0x18000961e  mov     [r11-38h], r14
0x180009622  xor     edx, edx; Val
0x180009624  lea     rcx, [rsp+2A0h+Name]; void *
0x180009629  mov     r8d, 100h; Size
0x18000962f  call    memset_0
0x180009634  mov     rcx, [r13+0]; hKey
0x180009638  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x18000963d  mov     [rsp+2A0h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180009642  lea     r8, [rsp+2A0h+Name]; lpName
0x180009647  mov     [rsp+2A0h+lpcchClass], rbx; lpcchClass
0x18000964c  mov     edx, esi; dwIndex
0x18000964e  mov     [rsp+2A0h+lpClass], rbx; struct Common::RegistryKey *
0x180009653  mov     [rsp+2A0h+lpReserved], rbx; lpReserved
0x180009658  mov     [rsp+2A0h+cchName], 80h
0x180009660  call    cs:__imp_RegEnumKeyExW
0x180009666  test    eax, eax
0x180009668  jnz     loc_18000978C
0x18000966e  mov     r9d, 0FFFFFFFFh; cchCount2
0x180009674  mov     dword ptr [rsp+2A0h+lpReserved], 1; int
0x18000967c  mov     edx, r9d; cchCount1
0x18000967f  lea     r8, [rsp+2A0h+Name]; lpString2
0x180009684  mov     rcx, r15; lpString1
0x180009687  call    cs:__imp_CompareStringOrdinal
0x18000968d  cmp     eax, 2
0x180009690  jz      loc_18000998C
0x180009696  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18000969d  mov     qword ptr [rsp+2A0h+var_258], rbx
0x1800096a2  mov     dword ptr [rsp+2A0h+var_248], 41h ; 'A'
0x1800096aa  test    rcx, rcx
0x1800096ad  jz      loc_180009773
0x1800096b3  xor     edx, edx; Flags
0x1800096b5  mov     r8d, 82h; Size
0x1800096bb  call    cs:__imp_RtlAllocateHeap
0x1800096c1  mov     rdi, rax
0x1800096c4  test    rax, rax
0x1800096c7  jz      loc_180009941
0x1800096cd  xor     edx, edx; Val
0x1800096cf  lea     rcx, [rbp+1A0h+var_130]; void *
0x1800096d3  mov     r8d, 0F0h; Size
0x1800096d9  call    memset_0
0x1800096de  lea     r9, [rbp+1A0h+var_130]
0x1800096e2  mov     [rsp+2A0h+var_24C], 0F0h
0x1800096ea  lea     r8, [rsp+2A0h+var_24C]
0x1800096ef  lea     rcx, [rsp+2A0h+Name]; lpString1
0x1800096f4  call    ?PackageIdBasicFromFullName@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBGIPEAIPEAE@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageIdBasicFromFullName(ushort const *,uint,uint *,uchar *)
0x1800096f9  mov     r14d, eax
0x1800096fc  test    eax, eax
0x1800096fe  jnz     loc_18000982D
0x180009704  mov     r8, rdi
0x180009707  lea     rdx, [rsp+2A0h+var_248]
0x18000970c  lea     rcx, [rbp+1A0h+var_130]
0x180009710  call    ?PackageFamilyNameFromId@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBUPACKAGE_ID@@PEAIPEAG@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageFamilyNameFromId(PACKAGE_ID const *,uint *,ushort *)
0x180009715  mov     r14d, eax
0x180009718  test    eax, eax
0x18000971a  jnz     loc_18000982D
0x180009720  mov     rbx, rdi
0x180009723  mov     qword ptr [rsp+2A0h+var_258], rbx
0x180009728  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000972e  mov     dword ptr [rsp+2A0h+lpReserved], 1; int
0x180009736  mov     edx, r9d; cchCount1
0x180009739  mov     r8, rbx; lpString2
0x18000973c  mov     rcx, r15; lpString1
0x18000973f  call    cs:__imp_CompareStringOrdinal
0x180009745  cmp     eax, 2
0x180009748  jz      short loc_1800097C9
0x18000974a  test    r12b, r12b
0x18000974d  jnz     loc_18000983F
0x180009753  test    rbx, rbx
0x180009756  jz      short loc_18000976A
0x180009758  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18000975f  mov     r8, rbx; P
0x180009762  xor     edx, edx; Flags
0x180009764  call    cs:__imp_RtlFreeHeap
0x18000976a  inc     esi
0x18000976c  xor     ebx, ebx
0x18000976e  jmp     loc_180009622
0x180009773  mov     rax, gs:60h
0x18000977c  mov     rcx, [rax+30h]
0x180009780  mov     cs:?g_heap@ReservedForLocalUse@@3PEAXEA, rcx; void * ReservedForLocalUse::g_heap
0x180009787  jmp     loc_1800096B3
0x18000978c  cmp     eax, 103h
0x180009791  jnz     loc_180009818
0x180009797  xor     eax, eax
0x180009799  mov     r14, [rsp+270h]
0x1800097a1  mov     rdi, [rsp+2A0h+arg_10]
0x1800097a9  mov     rcx, [rbp+1A0h+var_40]
0x1800097b0  xor     rcx, rsp; StackCookie
0x1800097b3  call    __security_check_cookie
0x1800097b8  add     rsp, 278h
0x1800097bf  pop     r15
0x1800097c1  pop     r13
0x1800097c3  pop     r12
0x1800097c5  pop     rsi
0x1800097c6  pop     rbx
0x1800097c7  pop     rbp
0x1800097c8  retn
0x1800097c9  mov     rax, qword ptr [rsp+2A0h+var_240]
0x1800097ce  mov     byte ptr [rax], 1
0x1800097d1  mov     rax, [rsp+2A0h+var_238]
0x1800097d6  test    rax, rax
0x1800097d9  jnz     loc_1800098F5
0x1800097df  mov     rcx, rbx; void *
0x1800097e2  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800097e7  jmp     short loc_180009797
0x1800097e9  test    r14d, r14d
0x1800097ec  jns     loc_180009728
0x1800097f2  jmp     loc_180009962
0x1800097f7  mov     rcx, rdi; void *
0x1800097fa  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800097ff  cmp     r14d, 80070057h
0x180009806  jnz     short loc_1800097E9
0x180009808  xor     ecx, ecx; void *
0x18000980a  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000980f  inc     esi
0x180009811  xor     ebx, ebx
0x180009813  jmp     loc_180009622
0x180009818  test    eax, eax
0x18000981a  jle     loc_180009799
0x180009820  movzx   eax, ax
0x180009823  or      eax, 80070000h
0x180009828  jmp     loc_180009799
0x18000982d  test    r14d, r14d
0x180009830  jle     short loc_1800097F7
0x180009832  movzx   r14d, r14w
0x180009836  or      r14d, 80070000h
0x18000983d  jmp     short loc_1800097F7
0x18000983f  mov     rdx, [r13+0]; hKey
0x180009843  lea     r8, [rsp+2A0h+Name]; lpSubKey
0x180009848  mov     r9d, 20019h; samDesired
0x18000984e  mov     [rsp+2A0h+phkResult], 0
0x180009857  lea     rcx, [rsp+2A0h+phkResult]; phkResult
0x18000985c  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180009861  mov     edi, eax
0x180009863  test    eax, eax
0x180009865  js      short loc_1800098BF
0x180009867  mov     rax, [rsp+2A0h+var_238]
0x18000986c  lea     rcx, [rsp+2A0h+phkResult]; this
0x180009871  mov     r14, qword ptr [rsp+2A0h+var_240]
0x180009876  xor     r8d, r8d; unsigned __int16 *
0x180009879  mov     r9, r14; bool
0x18000987c  mov     [rsp+2A0h+lpReserved], rax; bool *
0x180009881  mov     rdx, r15; struct Common::RegistryKey *
0x180009884  call    ?IsFamilyNameInRegStoreInternal@AppxAllUserStore@@YAJPEAVRegistryKey@Common@@QEBG_NPEA_N0@Z; AppxAllUserStore::IsFamilyNameInRegStoreInternal(Common::RegistryKey *,ushort const * const,bool,bool *,Common::RegistryKey *)
0x180009889  mov     edi, eax
0x18000988b  test    eax, eax
0x18000988d  js      short loc_1800098B8
0x18000988f  cmp     byte ptr [r14], 0
0x180009893  lea     rcx, [rsp+2A0h+phkResult]; this
0x180009898  jnz     short loc_1800098A4
0x18000989a  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18000989f  jmp     loc_180009753
0x1800098a4  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800098a9  lea     rcx, [rsp+2A0h+var_258]
0x1800098ae  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x1800098b3  jmp     loc_180009797
0x1800098b8  mov     edx, 0EAh
0x1800098bd  jmp     short loc_1800098C4
0x1800098bf  mov     edx, 0E4h; void *
0x1800098c4  mov     rcx, [rbp+1A8h]; this
0x1800098cb  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800098d2  mov     r9d, edi; char *
0x1800098d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098da  lea     rcx, [rsp+2A0h+phkResult]; this
0x1800098df  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800098e4  lea     rcx, [rsp+2A0h+var_258]
0x1800098e9  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x1800098ee  mov     eax, edi
0x1800098f0  jmp     loc_180009799
0x1800098f5  mov     r9, rax; struct Common::AutoHandleHKEY *
0x1800098f8  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x1800098fd  mov     r8d, 20019h; unsigned int
0x180009903  mov     rcx, r13; this
0x180009906  call    ?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)
0x18000990b  mov     edi, eax
0x18000990d  test    eax, eax
0x18000990f  jns     loc_1800097DF
0x180009915  mov     rcx, [rbp+1A8h]; this
0x18000991c  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x180009923  mov     r9d, eax; char *
0x180009926  mov     edx, 0DBh; void *
0x18000992b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009930  lea     rcx, [rsp+2A0h+var_258]
0x180009935  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x18000993a  mov     eax, edi
0x18000993c  jmp     loc_180009799
0x180009941  mov     rcx, [rbp+1A8h]; this
0x180009948  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000994f  mov     r14d, 8007000Eh
0x180009955  mov     edx, 1Ch; void *
0x18000995a  mov     r9d, r14d; char *
0x18000995d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009962  mov     rcx, [rbp+1A8h]; this
0x180009969  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x180009970  mov     r9d, r14d; char *
0x180009973  mov     edx, 0D2h; void *
0x180009978  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000997d  xor     ecx, ecx; void *
0x18000997f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180009984  mov     eax, r14d
0x180009987  jmp     loc_180009799
0x18000998c  mov     rax, qword ptr [rsp+2A0h+var_240]
0x180009991  mov     rbx, [rsp+2A0h+var_238]
0x180009996  mov     byte ptr [rax], 1
0x180009999  test    rbx, rbx
0x18000999c  jz      loc_180009797
0x1800099a2  mov     r9, rbx; struct Common::AutoHandleHKEY *
0x1800099a5  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x1800099aa  mov     r8d, 20019h; unsigned int
0x1800099b0  mov     rcx, r13; this
0x1800099b3  call    ?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)
0x1800099b8  mov     ebx, eax
0x1800099ba  test    eax, eax
0x1800099bc  jns     loc_180009797
0x1800099c2  mov     rcx, [rbp+1A8h]; this
0x1800099c9  lea     r8, aOnecoreAdminAp_18; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800099d0  mov     r9d, eax; char *
0x1800099d3  mov     edx, 0C1h; void *
0x1800099d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800099dd  mov     eax, ebx
0x1800099df  jmp     loc_180009799
```
