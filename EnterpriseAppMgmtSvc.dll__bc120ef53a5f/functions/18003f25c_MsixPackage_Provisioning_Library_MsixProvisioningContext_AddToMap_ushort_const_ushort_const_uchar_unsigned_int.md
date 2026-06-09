# MsixPackage::Provisioning::Library::MsixProvisioningContext::AddToMap(ushort const *,ushort const *,uchar *,unsigned __int64,ushort const *,AppxAllUserStore::Flags,Common::GenericMap<ushort *,MsixPackage::Provisioning::Library::HardlinkTarget *> *)

- ea: `0x18003f25c`
- end: `0x18003f677`
- name: `?AddToMap@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBG0PEAE_K0W4Flags@AppxAllUserStore@@PEAV?$GenericMap@PEAGPEAVHardlinkTarget@Library@Provisioning@MsixPackage@@@Common@@@Z`
- size: `1051`
- prototype: `__int64 __usercall@<rax>(PRTL_AVL_TABLE Table@<rcx>, void *Src@<rdx>, char *@<r8>, __int64, int, __int64, PRTL_AVL_TABLE)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800422cc`

## callees

- `0x180002398`
- `0x18000d3dc`
- `0x18001d160`
- `0x18003d4ec`
- `0x18003e50c`
- `0x18003f25c`
- `0x18006c910`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003f495`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003f55e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003f5c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003f642`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003f495`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003f55e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003f5c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003f642`
- `OLEAUT32!__imp_SysAllocString` at `0x18003f2fe`
- `OLEAUT32!__imp_SysAllocString` at `0x18003f452`
- `OLEAUT32!__imp_SysAllocString` at `0x18003f2fe`
- `OLEAUT32!__imp_SysAllocString` at `0x18003f452`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18003f2b4`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18003f2b4`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003f359`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003f532`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003f359`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18003f532`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003f4f2`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18003f4f2`

## string_xrefs

- `0x18003f31f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f39d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f476`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f5a3`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f623`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003f614`: `Failed creating hardlinktarget for %ws`
- `0x18003f38e`: `Failed inserting %ws to hardlink targets map`
- `0x18003f5e5`: `onecore\admin\appmodel\utilities\provisionhelper\hardlinktarget.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18003f25c  push    rbx
0x18003f25e  push    rsi
0x18003f25f  push    rdi
0x18003f260  push    r12
0x18003f262  push    r13
0x18003f264  push    r14
0x18003f266  push    r15
0x18003f268  sub     rsp, 80h
0x18003f26f  mov     rax, cs:__security_cookie
0x18003f276  xor     rax, rsp
0x18003f279  mov     [rsp+0B8h+var_48], rax
0x18003f27e  mov     r13, r9
0x18003f281  mov     rsi, r8
0x18003f284  mov     r14, rdx
0x18003f287  mov     rdi, rcx
0x18003f28a  mov     r12, [rsp+0B8h+Table]
0x18003f292  mov     r15, [rsp+0B8h+arg_20]
0x18003f29a  add     [rcx+288h], r15
0x18003f2a1  mov     [rsp+0B8h+Buffer], r9
0x18003f2a6  mov     [rsp+0B8h+var_78], 0
0x18003f2af  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x18003f2b4  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18003f2bb  nop     dword ptr [rax+rax+00h]
0x18003f2c0  test    rax, rax
0x18003f2c3  jz      loc_18003F3B5
0x18003f2c9  mov     rbx, [rax+8]
0x18003f2cd  test    rbx, rbx
0x18003f2d0  jz      loc_18003F3B5
0x18003f2d6  mov     cl, [rbx+80h]
0x18003f2dc  shr     cl, 3
0x18003f2df  mov     al, byte ptr [rsp+0B8h+arg_30]
0x18003f2e6  shr     al, 3
0x18003f2e9  xor     cl, al
0x18003f2eb  test    cl, 1
0x18003f2ee  jnz     loc_18003F56A
0x18003f2f4  add     [rdi+290h], r15
0x18003f2fb  mov     rcx, rsi; psz
0x18003f2fe  call    cs:__imp_SysAllocString
0x18003f305  nop     dword ptr [rax+rax+00h]
0x18003f30a  test    rax, rax
0x18003f30d  jnz     short loc_18003F337
0x18003f30f  mov     rcx, [rsp+0B8h]; this
0x18003f317  mov     ebx, 8007000Eh
0x18003f31c  mov     r9d, ebx; char *
0x18003f31f  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f326  mov     edx, 330h; void *
0x18003f32b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f330  mov     eax, ebx
0x18003f332  jmp     loc_18003F656
0x18003f337  mov     [rsp+0B8h+Buffer], rax
0x18003f33c  mov     [rsp+0B8h+var_78], rbx
0x18003f341  mov     [rsp+0B8h+NewElement], 0
0x18003f346  lea     r9, [rsp+0B8h+NewElement]; NewElement
0x18003f34b  mov     r8d, 10h; BufferSize
0x18003f351  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x18003f356  mov     rcx, r12; Table
0x18003f359  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18003f360  nop     dword ptr [rax+rax+00h]
0x18003f365  test    rax, rax
0x18003f368  jz      short loc_18003F37C
0x18003f36a  cmp     [rsp+0B8h+NewElement], 0
0x18003f36f  jnz     loc_18003F56A
0x18003f375  mov     ebx, 800702BAh
0x18003f37a  jmp     short loc_18003F381
0x18003f37c  mov     ebx, 8007000Eh
0x18003f381  mov     rcx, [rsp+0B8h]; this
0x18003f389  mov     [rsp+0B8h+var_90], rsi; char *
0x18003f38e  lea     rax, aFailedInsertin; "Failed inserting %ws to hardlink target"...
0x18003f395  mov     [rsp+0B8h+TableContext], rax; int
0x18003f39a  mov     r9d, ebx; char *
0x18003f39d  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f3a4  mov     edx, 334h; void *
0x18003f3a9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f3ae  mov     eax, ebx
0x18003f3b0  jmp     loc_18003F656
0x18003f3b5  mov     [rsp+0B8h+var_50], 7
0x18003f3be  xor     r12d, r12d
0x18003f3c1  mov     [rsp+0B8h+var_58], r12
0x18003f3c6  mov     word ptr [rsp+0B8h+psz], r12w
0x18003f3cc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003f3d0  cmp     [r14], r12w
0x18003f3d4  jnz     short loc_18003F3DB
0x18003f3d6  mov     r8d, r12d
0x18003f3d9  jmp     short loc_18003F3E8
0x18003f3db  mov     r8, rbx
0x18003f3de  inc     r8
0x18003f3e1  cmp     [r14+r8*2], r12w
0x18003f3e6  jnz     short loc_18003F3DE
0x18003f3e8  mov     rdx, r14; Src
0x18003f3eb  lea     rcx, [rsp+0B8h+psz]; void *
0x18003f3f0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003f3f5  mov     r8, r12
0x18003f3f8  cmp     word ptr cs:pszSrc, r12w; "\\"
0x18003f400  setnz   r8b
0x18003f404  lea     rdx, pszSrc; "\\"
0x18003f40b  lea     rcx, [rsp+0B8h+psz]; Src
0x18003f410  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003f415  cmp     [rsi], r12w
0x18003f419  jnz     short loc_18003F420
0x18003f41b  mov     rbx, r12
0x18003f41e  jmp     short loc_18003F42A
0x18003f420  inc     rbx
0x18003f423  cmp     [rsi+rbx*2], r12w
0x18003f428  jnz     short loc_18003F420
0x18003f42a  mov     r8, rbx
0x18003f42d  mov     rdx, rsi; void *
0x18003f430  lea     rcx, [rsp+0B8h+psz]; Src
0x18003f435  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003f43a  add     [rdi+298h], r15
0x18003f441  lea     rcx, [rsp+0B8h+psz]
0x18003f446  cmp     [rsp+0B8h+var_50], 8
0x18003f44c  cmovnb  rcx, [rsp+0B8h+psz]; psz
0x18003f452  call    cs:__imp_SysAllocString
0x18003f459  nop     dword ptr [rax+rax+00h]
0x18003f45e  mov     rbx, rax
0x18003f461  test    rax, rax
0x18003f464  jnz     short loc_18003F4A8
0x18003f466  mov     rcx, [rsp+0B8h]; this
0x18003f46e  mov     ebx, 8007000Eh
0x18003f473  mov     r9d, ebx; char *
0x18003f476  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f47d  mov     edx, 312h; void *
0x18003f482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f487  nop
0x18003f488  cmp     [rsp+0B8h+var_50], 8
0x18003f48e  jb      short loc_18003F4A1
0x18003f490  mov     rcx, [rsp+0B8h+psz]
0x18003f495  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003f49c  nop     dword ptr [rax+rax+00h]
0x18003f4a1  mov     eax, ebx
0x18003f4a3  jmp     loc_18003F656
0x18003f4a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003f4af  mov     ecx, 88h; unsigned __int64
0x18003f4b4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003f4b9  mov     rsi, rax
0x18003f4bc  test    rax, rax
0x18003f4bf  jz      loc_18003F5D5
0x18003f4c5  lea     rcx, [rax+8]; Table
0x18003f4c9  lea     rax, ??$DeallocateCoTaskMemAlloc@PEBG@Common@@YAXPEBG@Z; Common::DeallocateCoTaskMemAlloc<ushort const *>(ushort const *)
0x18003f4d0  mov     [rcx+68h], rax
0x18003f4d4  mov     [rcx+70h], r12
0x18003f4d8  mov     [rsp+0B8h+TableContext], r12; TableContext
0x18003f4dd  lea     r9, ?GenericMapFree@?$GenericMap@PEAGPEAVHardlinkTarget@Library@Provisioning@MsixPackage@@@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18003f4e4  lea     r8, ?GenericMapAllocate@?$GenericMap@PEBGPEBG@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18003f4eb  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18003f4f2  call    cs:__imp_RtlInitializeGenericTableAvl
0x18003f4f9  nop     dword ptr [rax+rax+00h]
0x18003f4fe  mov     [rsi], rbx
0x18003f501  mov     rax, [rsp+0B8h+arg_30]
0x18003f509  mov     [rsi+80h], rax
0x18003f510  mov     [rsp+0B8h+Buffer], r13
0x18003f515  mov     [rsp+0B8h+var_78], rsi
0x18003f51a  mov     [rsp+0B8h+NewElement], r12b
0x18003f51f  lea     r9, [rsp+0B8h+NewElement]; NewElement
0x18003f524  mov     r8d, 10h; BufferSize
0x18003f52a  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x18003f52f  mov     rcx, rdi; Table
0x18003f532  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18003f539  nop     dword ptr [rax+rax+00h]
0x18003f53e  test    rax, rax
0x18003f541  jz      short loc_18003F571
0x18003f543  cmp     [rsp+0B8h+NewElement], r12b
0x18003f548  jnz     short loc_18003F551
0x18003f54a  mov     ebx, 800702BAh
0x18003f54f  jmp     short loc_18003F576
0x18003f551  cmp     [rsp+0B8h+var_50], 8
0x18003f557  jb      short loc_18003F56A
0x18003f559  mov     rcx, [rsp+0B8h+psz]
0x18003f55e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003f565  nop     dword ptr [rax+rax+00h]
0x18003f56a  xor     eax, eax
0x18003f56c  jmp     loc_18003F656
0x18003f571  mov     ebx, 8007000Eh
0x18003f576  lea     rax, [rsp+0B8h+psz]
0x18003f57b  cmp     [rsp+0B8h+var_50], 8
0x18003f581  cmovnb  rax, [rsp+0B8h+psz]
0x18003f587  mov     rcx, [rsp+0B8h]; this
0x18003f58f  mov     [rsp+0B8h+var_90], rax; char *
0x18003f594  lea     rax, aFailedInsertin_0; "Failed inserting %ws to digest map"
0x18003f59b  mov     [rsp+0B8h+TableContext], rax; int
0x18003f5a0  mov     r9d, ebx; char *
0x18003f5a3  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f5aa  mov     edx, 320h; void *
0x18003f5af  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f5b4  nop
0x18003f5b5  cmp     [rsp+0B8h+var_50], 8
0x18003f5bb  jb      short loc_18003F5CE
0x18003f5bd  mov     rcx, [rsp+0B8h+psz]
0x18003f5c2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003f5c9  nop     dword ptr [rax+rax+00h]
0x18003f5ce  mov     eax, ebx
0x18003f5d0  jmp     loc_18003F656
0x18003f5d5  mov     rcx, [rsp+0B8h]; this
0x18003f5dd  mov     ebx, 8007000Eh
0x18003f5e2  mov     r9d, ebx; char *
0x18003f5e5  lea     r8, aOnecoreAdminAp_16; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f5ec  mov     edx, 10h; void *
0x18003f5f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f5f6  lea     rax, [rsp+0B8h+psz]
0x18003f5fb  cmp     [rsp+0B8h+var_50], 8
0x18003f601  cmovnb  rax, [rsp+0B8h+psz]
0x18003f607  mov     rcx, [rsp+0B8h]; this
0x18003f60f  mov     [rsp+0B8h+var_90], rax; char *
0x18003f614  lea     rax, aFailedCreating; "Failed creating hardlinktarget for %ws"
0x18003f61b  mov     [rsp+0B8h+TableContext], rax; int
0x18003f620  mov     r9d, ebx; char *
0x18003f623  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f62a  mov     edx, 31Bh; void *
0x18003f62f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f634  nop
0x18003f635  cmp     [rsp+0B8h+var_50], 8
0x18003f63b  jb      short loc_18003F64E
0x18003f63d  mov     rcx, [rsp+0B8h+psz]
0x18003f642  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003f649  nop     dword ptr [rax+rax+00h]
0x18003f64e  mov     eax, ebx
0x18003f650  jmp     short loc_18003F656
0x18003f652  mov     eax, [rsp+0B8h+var_70]
0x18003f656  mov     rcx, [rsp+0B8h+var_48]
0x18003f65b  xor     rcx, rsp; StackCookie
0x18003f65e  call    __security_check_cookie
0x18003f663  add     rsp, 80h
0x18003f66a  pop     r15
0x18003f66c  pop     r14
0x18003f66e  pop     r13
0x18003f670  pop     r12
0x18003f672  pop     rdi
0x18003f673  pop     rsi
0x18003f674  pop     rbx
0x18003f675  retn
```
