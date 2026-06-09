# MsixPackage::Provisioning::Library::MsixProvisioningContext::AddToMap(ushort const *,ushort const *,uchar *,unsigned __int64,ushort const *,AppxAllUserStore::Flags,Common::GenericMap<ushort *,MsixPackage::Provisioning::Library::HardlinkTarget *> *)

- ea: `0x18003bb3c`
- end: `0x18003bf18`
- name: `?AddToMap@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBG0PEAE_K0W4Flags@AppxAllUserStore@@PEAV?$GenericMap@PEAGPEAVHardlinkTarget@Library@Provisioning@MsixPackage@@@Common@@@Z`
- size: `988`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, _WORD *Src, OLECHAR *, OLECHAR *, __int64, int, OLECHAR *, PRTL_AVL_TABLE Tablea)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003e91c`

## callees

- `0x180002368`
- `0x18000cfe8`
- `0x18001bf0c`
- `0x180039e9c`
- `0x18003ae3c`
- `0x18003bb3c`
- `0x180066df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003bd5d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003be14`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003be72`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bee9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bd5d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003be14`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003be72`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bee9`
- `OLEAUT32!__imp_SysAllocString` at `0x18003bbd8`
- `OLEAUT32!__imp_SysAllocString` at `0x18003bd20`
- `OLEAUT32!__imp_SysAllocString` at `0x18003bbd8`
- `OLEAUT32!__imp_SysAllocString` at `0x18003bd20`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18003bb94`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18003bb94`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003bc2d`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003bdee`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003bc2d`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003bdee`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003bdb4`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003bdb4`

## string_xrefs

- `0x18003bbf3`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003bc6b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003bd3e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003be53`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003beca`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003bebb`: `Failed creating hardlinktarget for %ws`
- `0x18003bc5c`: `Failed inserting %ws to hardlink targets map`
- `0x18003be8c`: `onecore\admin\appmodel\utilities\provisionhelper\hardlinktarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningContext::AddToMap(
        PRTL_AVL_TABLE Table,
        _WORD *Src,
        OLECHAR *a3,
        OLECHAR *a4,
        __int64 a5,
        int a6,
        OLECHAR *a7,
        PRTL_AVL_TABLE Tablea)
{
  _QWORD *v12; // rax
  const char *v13; // r9
  __int64 v14; // rbx
  BSTR v15; // rax
  __int64 result; // rax
  unsigned int v17; // ebx
  __int64 v18; // rbx
  __int64 v19; // r8
  const OLECHAR *v20; // rcx
  BSTR v21; // rbx
  char *v22; // rax
  BSTR *v23; // rsi
  unsigned int v24; // ebx
  OLECHAR **v25; // rax
  OLECHAR **v26; // rax
  int TableContext; // [rsp+20h] [rbp-98h]
  unsigned __int8 NewElement[8]; // [rsp+30h] [rbp-88h] BYREF
  BSTR Buffer; // [rsp+38h] [rbp-80h] BYREF
  BSTR *v30; // [rsp+40h] [rbp-78h]
  OLECHAR *psz[3]; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int64 v32; // [rsp+68h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  *(_QWORD *)&Table[6].BalancedRoot.Balance += a5;
  Buffer = a4;
  v30 = 0;
  v12 = RtlLookupElementGenericTableAvl(Table, &Buffer);
  try
  {
    if ( v12 )
    {
      v14 = v12[1];
      if ( v14 )
      {
        if ( ((((unsigned __int8)a7 >> 3) ^ (*(_BYTE *)(v14 + 128) >> 3)) & 1) == 0 )
        {
          Table[6].OrderedPointer = (char *)Table[6].OrderedPointer + a5;
          v15 = SysAllocString(a3);
          if ( !v15 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x330,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
              (const char *)0x8007000ELL,
              TableContext);
            return 2147942414LL;
          }
          Buffer = v15;
          v30 = (BSTR *)v14;
          NewElement[0] = 0;
          if ( !RtlInsertElementGenericTableAvl(Tablea, &Buffer, 0x10u, NewElement) )
          {
            v17 = -2147024882;
            goto LABEL_11;
          }
          if ( !NewElement[0] )
          {
            v17 = -2147024198;
LABEL_11:
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x334,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
              (const char *)v17,
              (int)"Failed inserting %ws to hardlink targets map",
              (const char *)a3);
            return v17;
          }
        }
        return 0;
      }
    }
    v32 = 7;
    psz[2] = 0;
    LOWORD(psz[0]) = 0;
    v18 = -1;
    if ( *Src )
    {
      v19 = -1;
      do
        ++v19;
      while ( Src[v19] );
    }
    std::wstring::assign(psz, Src);
    std::wstring::append(psz, (void *)L"\\");
    if ( *a3 )
    {
      do
        ++v18;
      while ( a3[v18] );
    }
    std::wstring::append(psz, a3);
    *(_QWORD *)&Table[6].WhichOrderedElement += a5;
    v20 = (const OLECHAR *)psz;
    if ( v32 >= 8 )
      v20 = psz[0];
    v21 = SysAllocString(v20);
    if ( v21 )
    {
      v22 = (char *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
      v23 = (BSTR *)v22;
      if ( v22 )
      {
        *((_QWORD *)v22 + 14) = Common::DeallocateCoTaskMemAlloc<unsigned short const *>;
        *((_QWORD *)v22 + 15) = 0;
        RtlInitializeGenericTableAvl(
          (PRTL_AVL_TABLE)(v22 + 8),
          Common::GenericMapCaseInsensitiveCompare,
          Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapAllocate,
          Common::GenericMap<unsigned short *,MsixPackage::Provisioning::Library::HardlinkTarget *>::GenericMapFree,
          0);
        *v23 = v21;
        v23[16] = a7;
        Buffer = a4;
        v30 = v23;
        NewElement[0] = 0;
        if ( RtlInsertElementGenericTableAvl(Table, &Buffer, 0x10u, NewElement) )
        {
          if ( NewElement[0] )
          {
            if ( v32 >= 8 )
              operator delete(psz[0]);
            return 0;
          }
          v24 = -2147024198;
        }
        else
        {
          v24 = -2147024882;
        }
        v25 = psz;
        if ( v32 >= 8 )
          v25 = (OLECHAR **)psz[0];
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x320,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)v24,
          (int)"Failed inserting %ws to digest map",
          (const char *)v25);
        if ( v32 >= 8 )
          operator delete(psz[0]);
        result = v24;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\hardlinktarget.cpp",
          (const char *)0x8007000ELL,
          TableContext);
        v26 = psz;
        if ( v32 >= 8 )
          v26 = (OLECHAR **)psz[0];
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x31B,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)0x8007000ELL,
          (int)"Failed creating hardlinktarget for %ws",
          (const char *)v26);
        if ( v32 >= 8 )
          operator delete(psz[0]);
        result = 2147942414LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x312,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
        (const char *)0x8007000ELL,
        TableContext);
      if ( v32 >= 8 )
        operator delete(psz[0]);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x339,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x18003bb3c  push    rbx
0x18003bb3e  push    rsi
0x18003bb3f  push    rdi
0x18003bb40  push    r12
0x18003bb42  push    r13
0x18003bb44  push    r14
0x18003bb46  push    r15
0x18003bb48  sub     rsp, 80h
0x18003bb4f  mov     rax, cs:__security_cookie
0x18003bb56  xor     rax, rsp
0x18003bb59  mov     [rsp+0B8h+var_48], rax
0x18003bb5e  mov     r13, r9
0x18003bb61  mov     rsi, r8
0x18003bb64  mov     r14, rdx
0x18003bb67  mov     rdi, rcx
0x18003bb6a  mov     r12, [rsp+0B8h+Table]
0x18003bb72  mov     r15, [rsp+0B8h+arg_20]
0x18003bb7a  add     [rcx+288h], r15
0x18003bb81  mov     [rsp+0B8h+Buffer], r9
0x18003bb86  mov     [rsp+0B8h+var_78], 0
0x18003bb8f  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x18003bb94  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18003bb9a  test    rax, rax
0x18003bb9d  jz      loc_18003BC83
0x18003bba3  mov     rbx, [rax+8]
0x18003bba7  test    rbx, rbx
0x18003bbaa  jz      loc_18003BC83
0x18003bbb0  mov     cl, [rbx+80h]
0x18003bbb6  shr     cl, 3
0x18003bbb9  mov     al, byte ptr [rsp+0B8h+arg_30]
0x18003bbc0  shr     al, 3
0x18003bbc3  xor     cl, al
0x18003bbc5  test    cl, 1
0x18003bbc8  jnz     loc_18003BE1A
0x18003bbce  add     [rdi+290h], r15
0x18003bbd5  mov     rcx, rsi; psz
0x18003bbd8  call    cs:__imp_SysAllocString
0x18003bbde  test    rax, rax
0x18003bbe1  jnz     short loc_18003BC0B
0x18003bbe3  mov     rcx, [rsp+0B8h]; this
0x18003bbeb  mov     ebx, 8007000Eh
0x18003bbf0  mov     r9d, ebx; char *
0x18003bbf3  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003bbfa  mov     edx, 330h; void *
0x18003bbff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bc04  mov     eax, ebx
0x18003bc06  jmp     loc_18003BEF7
0x18003bc0b  mov     [rsp+0B8h+Buffer], rax
0x18003bc10  mov     [rsp+0B8h+var_78], rbx
0x18003bc15  mov     [rsp+0B8h+NewElement], 0
0x18003bc1a  lea     r9, [rsp+0B8h+NewElement]; NewElement
0x18003bc1f  mov     r8d, 10h; BufferSize
0x18003bc25  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x18003bc2a  mov     rcx, r12; Table
0x18003bc2d  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18003bc33  test    rax, rax
0x18003bc36  jz      short loc_18003BC4A
0x18003bc38  cmp     [rsp+0B8h+NewElement], 0
0x18003bc3d  jnz     loc_18003BE1A
0x18003bc43  mov     ebx, 800702BAh
0x18003bc48  jmp     short loc_18003BC4F
0x18003bc4a  mov     ebx, 8007000Eh
0x18003bc4f  mov     rcx, [rsp+0B8h]; this
0x18003bc57  mov     [rsp+0B8h+var_90], rsi; char *
0x18003bc5c  lea     rax, aFailedInsertin; "Failed inserting %ws to hardlink target"...
0x18003bc63  mov     [rsp+0B8h+TableContext], rax; int
0x18003bc68  mov     r9d, ebx; char *
0x18003bc6b  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003bc72  mov     edx, 334h; void *
0x18003bc77  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003bc7c  mov     eax, ebx
0x18003bc7e  jmp     loc_18003BEF7
0x18003bc83  mov     [rsp+0B8h+var_50], 7
0x18003bc8c  xor     r12d, r12d
0x18003bc8f  mov     [rsp+0B8h+var_58], r12
0x18003bc94  mov     word ptr [rsp+0B8h+psz], r12w
0x18003bc9a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003bc9e  cmp     [r14], r12w
0x18003bca2  jnz     short loc_18003BCA9
0x18003bca4  mov     r8d, r12d
0x18003bca7  jmp     short loc_18003BCB6
0x18003bca9  mov     r8, rbx
0x18003bcac  inc     r8
0x18003bcaf  cmp     [r14+r8*2], r12w
0x18003bcb4  jnz     short loc_18003BCAC
0x18003bcb6  mov     rdx, r14; Src
0x18003bcb9  lea     rcx, [rsp+0B8h+psz]; void *
0x18003bcbe  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003bcc3  mov     r8, r12
0x18003bcc6  cmp     word ptr cs:pszSrc, r12w; "\\"
0x18003bcce  setnz   r8b
0x18003bcd2  lea     rdx, pszSrc; "\\"
0x18003bcd9  lea     rcx, [rsp+0B8h+psz]; Src
0x18003bcde  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003bce3  cmp     [rsi], r12w
0x18003bce7  jnz     short loc_18003BCEE
0x18003bce9  mov     rbx, r12
0x18003bcec  jmp     short loc_18003BCF8
0x18003bcee  inc     rbx
0x18003bcf1  cmp     [rsi+rbx*2], r12w
0x18003bcf6  jnz     short loc_18003BCEE
0x18003bcf8  mov     r8, rbx
0x18003bcfb  mov     rdx, rsi; void *
0x18003bcfe  lea     rcx, [rsp+0B8h+psz]; Src
0x18003bd03  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003bd08  add     [rdi+298h], r15
0x18003bd0f  lea     rcx, [rsp+0B8h+psz]
0x18003bd14  cmp     [rsp+0B8h+var_50], 8
0x18003bd1a  cmovnb  rcx, [rsp+0B8h+psz]; psz
0x18003bd20  call    cs:__imp_SysAllocString
0x18003bd26  mov     rbx, rax
0x18003bd29  test    rax, rax
0x18003bd2c  jnz     short loc_18003BD6A
0x18003bd2e  mov     rcx, [rsp+0B8h]; this
0x18003bd36  mov     ebx, 8007000Eh
0x18003bd3b  mov     r9d, ebx; char *
0x18003bd3e  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003bd45  mov     edx, 312h; void *
0x18003bd4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bd4f  nop
0x18003bd50  cmp     [rsp+0B8h+var_50], 8
0x18003bd56  jb      short loc_18003BD63
0x18003bd58  mov     rcx, [rsp+0B8h+psz]
0x18003bd5d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003bd63  mov     eax, ebx
0x18003bd65  jmp     loc_18003BEF7
0x18003bd6a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003bd71  mov     ecx, 88h; unsigned __int64
0x18003bd76  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003bd7b  mov     rsi, rax
0x18003bd7e  test    rax, rax
0x18003bd81  jz      loc_18003BE7C
0x18003bd87  lea     rcx, [rax+8]; Table
0x18003bd8b  lea     rax, ??$DeallocateCoTaskMemAlloc@PEBG@Common@@YAXPEBG@Z; Common::DeallocateCoTaskMemAlloc<ushort const *>(ushort const *)
0x18003bd92  mov     [rcx+68h], rax
0x18003bd96  mov     [rcx+70h], r12
0x18003bd9a  mov     [rsp+0B8h+TableContext], r12; TableContext
0x18003bd9f  lea     r9, ?GenericMapFree@?$GenericMap@PEAGPEAVHardlinkTarget@Library@Provisioning@MsixPackage@@@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18003bda6  lea     r8, ?GenericMapAllocate@?$GenericMap@PEBGPEBG@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18003bdad  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18003bdb4  call    cs:__imp_RtlInitializeGenericTableAvl
0x18003bdba  mov     [rsi], rbx
0x18003bdbd  mov     rax, [rsp+0B8h+arg_30]
0x18003bdc5  mov     [rsi+80h], rax
0x18003bdcc  mov     [rsp+0B8h+Buffer], r13
0x18003bdd1  mov     [rsp+0B8h+var_78], rsi
0x18003bdd6  mov     [rsp+0B8h+NewElement], r12b
0x18003bddb  lea     r9, [rsp+0B8h+NewElement]; NewElement
0x18003bde0  mov     r8d, 10h; BufferSize
0x18003bde6  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x18003bdeb  mov     rcx, rdi; Table
0x18003bdee  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18003bdf4  test    rax, rax
0x18003bdf7  jz      short loc_18003BE21
0x18003bdf9  cmp     [rsp+0B8h+NewElement], r12b
0x18003bdfe  jnz     short loc_18003BE07
0x18003be00  mov     ebx, 800702BAh
0x18003be05  jmp     short loc_18003BE26
0x18003be07  cmp     [rsp+0B8h+var_50], 8
0x18003be0d  jb      short loc_18003BE1A
0x18003be0f  mov     rcx, [rsp+0B8h+psz]
0x18003be14  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003be1a  xor     eax, eax
0x18003be1c  jmp     loc_18003BEF7
0x18003be21  mov     ebx, 8007000Eh
0x18003be26  lea     rax, [rsp+0B8h+psz]
0x18003be2b  cmp     [rsp+0B8h+var_50], 8
0x18003be31  cmovnb  rax, [rsp+0B8h+psz]
0x18003be37  mov     rcx, [rsp+0B8h]; this
0x18003be3f  mov     [rsp+0B8h+var_90], rax; char *
0x18003be44  lea     rax, aFailedInsertin_0; "Failed inserting %ws to digest map"
0x18003be4b  mov     [rsp+0B8h+TableContext], rax; int
0x18003be50  mov     r9d, ebx; char *
0x18003be53  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003be5a  mov     edx, 320h; void *
0x18003be5f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003be64  nop
0x18003be65  cmp     [rsp+0B8h+var_50], 8
0x18003be6b  jb      short loc_18003BE78
0x18003be6d  mov     rcx, [rsp+0B8h+psz]
0x18003be72  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003be78  mov     eax, ebx
0x18003be7a  jmp     short loc_18003BEF7
0x18003be7c  mov     rcx, [rsp+0B8h]; this
0x18003be84  mov     ebx, 8007000Eh
0x18003be89  mov     r9d, ebx; char *
0x18003be8c  lea     r8, aOnecoreAdminAp_16; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003be93  mov     edx, 10h; void *
0x18003be98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003be9d  lea     rax, [rsp+0B8h+psz]
0x18003bea2  cmp     [rsp+0B8h+var_50], 8
0x18003bea8  cmovnb  rax, [rsp+0B8h+psz]
0x18003beae  mov     rcx, [rsp+0B8h]; this
0x18003beb6  mov     [rsp+0B8h+var_90], rax; char *
0x18003bebb  lea     rax, aFailedCreating; "Failed creating hardlinktarget for %ws"
0x18003bec2  mov     [rsp+0B8h+TableContext], rax; int
0x18003bec7  mov     r9d, ebx; char *
0x18003beca  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003bed1  mov     edx, 31Bh; void *
0x18003bed6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003bedb  nop
0x18003bedc  cmp     [rsp+0B8h+var_50], 8
0x18003bee2  jb      short loc_18003BEEF
0x18003bee4  mov     rcx, [rsp+0B8h+psz]
0x18003bee9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003beef  mov     eax, ebx
0x18003bef1  jmp     short loc_18003BEF7
0x18003bef3  mov     eax, [rsp+0B8h+var_70]
0x18003bef7  mov     rcx, [rsp+0B8h+var_48]
0x18003befc  xor     rcx, rsp; StackCookie
0x18003beff  call    __security_check_cookie
0x18003bf04  add     rsp, 80h
0x18003bf0b  pop     r15
0x18003bf0d  pop     r14
0x18003bf0f  pop     r13
0x18003bf11  pop     r12
0x18003bf13  pop     rdi
0x18003bf14  pop     rsi
0x18003bf15  pop     rbx
0x18003bf16  retn
```
