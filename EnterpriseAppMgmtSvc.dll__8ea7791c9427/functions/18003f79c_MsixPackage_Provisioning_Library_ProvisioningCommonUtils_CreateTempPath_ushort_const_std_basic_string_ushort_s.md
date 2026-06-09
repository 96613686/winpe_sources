# MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateTempPath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18003f79c`
- end: `0x18003fadd`
- name: `?CreateTempPath@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `833`
- prototype: `__int64 __fastcall(_WORD *Src, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18003e894`

## callees

- `0x18000cfc8`
- `0x18000cfe8`
- `0x18001bdfc`
- `0x18001bf0c`
- `0x18003ae3c`
- `0x18003f79c`
- `0x18005f684`
- `0x18005fc68`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003f93f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003fa15`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003fa78`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003f93f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003fa15`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003fa78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f870`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f95f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003fa35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003fa98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f870`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f95f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003fa35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003fa98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f87e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f96d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fa43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003faa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f87e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f96d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003fa43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003faa6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003f909`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003f909`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003f98a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003f98a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f829`

## string_xrefs

- `0x18003f854`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x18003f920`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x18003f9f7`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateTempPath(_WORD *Src, void **a2)
{
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  unsigned int v7; // ebx
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v11; // r8
  __int64 v12; // rax
  HRESULT v13; // eax
  unsigned int v14; // ebx
  void *v15; // rdi
  HANDLE v16; // rax
  unsigned __int64 v17; // r8
  void **v18; // rcx
  const char *v19; // r9
  unsigned int v20; // edi
  void *v21; // rbx
  HANDLE v22; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  LPVOID lpMem[2]; // [rsp+20h] [rbp-D8h] BYREF
  char v26; // [rsp+30h] [rbp-C8h]
  void *Srca[2]; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B0h]
  unsigned __int64 v29; // [rsp+50h] [rbp-A8h]
  GUID pguid; // [rsp+58h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  pguid = 0;
  lpMem[0] = 0;
  memset_0(sz, 0, sizeof(sz));
  lpMem[1] = lpMem;
  v26 = 1;
  if ( !Src || !*Src )
  {
    Src = (_WORD *)GetTempDirectory();
    if ( !Src )
    {
      LastError = GetLastError();
      v5 = LastError < 0;
      if ( LastError > 0 )
        v5 = 1;
      if ( !v5 )
      {
        v7 = -2147467259;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2F,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
          (const char *)v7,
          (int)lpMem[0]);
        v8 = lpMem[0];
        if ( lpMem[0] )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v8);
        }
        return v7;
      }
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      if ( (v7 & 0x80000000) != 0 )
        goto LABEL_12;
    }
    lpMem[0] = Src;
  }
  v29 = 7;
  v28 = 0;
  LOWORD(Srca[0]) = 0;
  if ( *Src )
  {
    v11 = -1;
    do
      ++v11;
    while ( Src[v11] );
  }
  else
  {
    v11 = 0;
  }
  std::wstring::assign(Srca, (char *)Src, v11);
  v12 = -1;
  do
    ++v12;
  while ( Src[v12] );
  if ( Src[v12 - 1] != 92 )
    std::wstring::append(Srca, (char *)L"\\", pszSrc[0] != 0);
  v13 = CoCreateGuid(&pguid);
  v14 = v13;
  if ( v13 >= 0 )
  {
    StringFromGUID2(&pguid, sz, 40);
    std::wstring::append(Srca, (char *)L"appxStage-", 0xAu);
    if ( sz[0] )
    {
      v17 = -1;
      do
        ++v17;
      while ( sz[v17] );
    }
    else
    {
      v17 = 0;
    }
    std::wstring::append(Srca, (char *)sz, v17);
    v18 = Srca;
    if ( v29 >= 8 )
      v18 = (void **)Srca[0];
    if ( (unsigned int)CreatePath(v18) )
    {
      if ( a2 != Srca )
        std::wstring::assign(a2, Srca, 0, 0xFFFFFFFFFFFFFFFFuLL);
      if ( v29 >= 8 )
        operator delete(Srca[0]);
      v29 = 7;
      v28 = 0;
      LOWORD(Srca[0]) = 0;
      v23 = lpMem[0];
      if ( lpMem[0] )
      {
        v24 = GetProcessHeap();
        HeapFree(v24, 0, v23);
      }
      return 0;
    }
    else
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x41,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
              v19);
      if ( v29 >= 8 )
        operator delete(Srca[0]);
      v29 = 7;
      v28 = 0;
      LOWORD(Srca[0]) = 0;
      v21 = lpMem[0];
      if ( lpMem[0] )
      {
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v21);
      }
      return v20;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningutils.cpp",
      (const char *)(unsigned int)v13,
      (int)lpMem[0]);
    if ( v29 >= 8 )
      operator delete(Srca[0]);
    v29 = 7;
    v28 = 0;
    LOWORD(Srca[0]) = 0;
    v15 = lpMem[0];
    if ( lpMem[0] )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v15);
    }
    return v14;
  }
}

```

## disassembly

```asm
0x18003f79c  mov     [rsp+arg_10], rbx
0x18003f7a1  push    rsi
0x18003f7a2  push    rdi
0x18003f7a3  push    r12
0x18003f7a5  push    r14
0x18003f7a7  push    r15
0x18003f7a9  sub     rsp, 0D0h
0x18003f7b0  mov     rax, cs:__security_cookie
0x18003f7b7  xor     rax, rsp
0x18003f7ba  mov     [rsp+0F8h+var_38], rax
0x18003f7c2  mov     r14, rdx
0x18003f7c5  mov     rdi, rcx
0x18003f7c8  xorps   xmm0, xmm0
0x18003f7cb  movups  xmmword ptr [rsp+0F8h+pguid.Data1], xmm0
0x18003f7d0  xor     r15d, r15d
0x18003f7d3  mov     [rsp+0F8h+lpMem], r15; int
0x18003f7d8  xor     edx, edx; Val
0x18003f7da  lea     r8d, [r15+50h]; Size
0x18003f7de  lea     rcx, [rsp+0F8h+sz]; void *
0x18003f7e3  call    memset_0
0x18003f7e8  lea     rax, [rsp+0F8h+lpMem]
0x18003f7ed  mov     [rsp+0F8h+var_D0], rax
0x18003f7f2  mov     [rsp+0F8h+var_C8], 1
0x18003f7f7  test    rdi, rdi
0x18003f7fa  jz      short loc_18003F806
0x18003f7fc  cmp     [rdi], r15w
0x18003f800  jnz     loc_18003F890
0x18003f806  call    GetTempDirectory
0x18003f80b  mov     rdi, rax
0x18003f80e  test    rax, rax
0x18003f811  jnz     short loc_18003F88B
0x18003f813  call    cs:__imp_GetLastError
0x18003f819  test    eax, eax
0x18003f81b  jle     short loc_18003F827
0x18003f81d  movzx   eax, ax
0x18003f820  or      eax, 80070000h
0x18003f825  test    eax, eax
0x18003f827  jns     short loc_18003F844
0x18003f829  call    cs:__imp_GetLastError
0x18003f82f  mov     ebx, eax
0x18003f831  test    eax, eax
0x18003f833  jle     short loc_18003F83E
0x18003f835  movzx   ebx, ax
0x18003f838  or      ebx, 80070000h
0x18003f83e  test    ebx, ebx
0x18003f840  jns     short loc_18003F88B
0x18003f842  jmp     short loc_18003F849
0x18003f844  mov     ebx, 80004005h
0x18003f849  mov     rcx, [rsp+0F8h]; this
0x18003f851  mov     r9d, ebx; char *
0x18003f854  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f85b  mov     edx, 2Fh ; '/'; void *
0x18003f860  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f865  nop
0x18003f866  mov     rdi, [rsp+0F8h+lpMem]
0x18003f86b  test    rdi, rdi
0x18003f86e  jz      short loc_18003F884
0x18003f870  call    cs:__imp_GetProcessHeap
0x18003f876  mov     r8, rdi; lpMem
0x18003f879  xor     edx, edx; dwFlags
0x18003f87b  mov     rcx, rax; hHeap
0x18003f87e  call    cs:__imp_HeapFree
0x18003f884  mov     eax, ebx
0x18003f886  jmp     loc_18003FAB4
0x18003f88b  mov     [rsp+0F8h+lpMem], rdi; int
0x18003f890  mov     r12d, 7
0x18003f896  mov     [rsp+0F8h+var_A8], r12
0x18003f89b  mov     [rsp+0F8h+var_B0], r15
0x18003f8a0  mov     word ptr [rsp+0F8h+Src], r15w
0x18003f8a6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003f8aa  cmp     [rdi], r15w
0x18003f8ae  jnz     short loc_18003F8B5
0x18003f8b0  mov     r8, r15
0x18003f8b3  jmp     short loc_18003F8C2
0x18003f8b5  mov     r8, rsi
0x18003f8b8  inc     r8
0x18003f8bb  cmp     [rdi+r8*2], r15w
0x18003f8c0  jnz     short loc_18003F8B8
0x18003f8c2  mov     rdx, rdi; Src
0x18003f8c5  lea     rcx, [rsp+0F8h+Src]; void *
0x18003f8ca  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003f8cf  mov     rax, rsi
0x18003f8d2  inc     rax
0x18003f8d5  cmp     [rdi+rax*2], r15w
0x18003f8da  jnz     short loc_18003F8D2
0x18003f8dc  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18003f8e2  jz      short loc_18003F904
0x18003f8e4  mov     r8, r15
0x18003f8e7  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18003f8ef  setnz   r8b
0x18003f8f3  lea     rdx, pszSrc; "\\"
0x18003f8fa  lea     rcx, [rsp+0F8h+Src]; Src
0x18003f8ff  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003f904  lea     rcx, [rsp+0F8h+pguid]; pguid
0x18003f909  call    cs:__imp_CoCreateGuid
0x18003f90f  mov     ebx, eax
0x18003f911  test    eax, eax
0x18003f913  jns     short loc_18003F97A
0x18003f915  mov     rcx, [rsp+0F8h]; this
0x18003f91d  mov     r9d, eax; char *
0x18003f920  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f927  mov     edx, 3Ah ; ':'; void *
0x18003f92c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f931  nop
0x18003f932  cmp     [rsp+0F8h+var_A8], 8
0x18003f938  jb      short loc_18003F945
0x18003f93a  mov     rcx, [rsp+0F8h+Src]
0x18003f93f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003f945  mov     [rsp+0F8h+var_A8], r12
0x18003f94a  mov     [rsp+0F8h+var_B0], r15
0x18003f94f  mov     word ptr [rsp+0F8h+Src], r15w
0x18003f955  mov     rdi, [rsp+0F8h+lpMem]
0x18003f95a  test    rdi, rdi
0x18003f95d  jz      short loc_18003F973
0x18003f95f  call    cs:__imp_GetProcessHeap
0x18003f965  mov     r8, rdi; lpMem
0x18003f968  xor     edx, edx; dwFlags
0x18003f96a  mov     rcx, rax; hHeap
0x18003f96d  call    cs:__imp_HeapFree
0x18003f973  mov     eax, ebx
0x18003f975  jmp     loc_18003FAB4
0x18003f97a  mov     r8d, 28h ; '('; cchMax
0x18003f980  lea     rdx, [rsp+0F8h+sz]; lpsz
0x18003f985  lea     rcx, [rsp+0F8h+pguid]; rguid
0x18003f98a  call    cs:__imp_StringFromGUID2
0x18003f990  mov     r8d, 0Ah
0x18003f996  lea     rdx, aAppxstage; "appxStage-"
0x18003f99d  lea     rcx, [rsp+0F8h+Src]; Src
0x18003f9a2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003f9a7  cmp     [rsp+0F8h+sz], r15w
0x18003f9ad  jnz     short loc_18003F9B4
0x18003f9af  mov     r8, r15
0x18003f9b2  jmp     short loc_18003F9C6
0x18003f9b4  lea     rax, [rsp+0F8h+sz]
0x18003f9b9  mov     r8, rsi
0x18003f9bc  inc     r8
0x18003f9bf  cmp     [rax+r8*2], r15w
0x18003f9c4  jnz     short loc_18003F9BC
0x18003f9c6  lea     rdx, [rsp+0F8h+sz]; void *
0x18003f9cb  lea     rcx, [rsp+0F8h+Src]; Src
0x18003f9d0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003f9d5  lea     rcx, [rsp+0F8h+Src]
0x18003f9da  cmp     [rsp+0F8h+var_A8], 8
0x18003f9e0  cmovnb  rcx, [rsp+0F8h+Src]
0x18003f9e6  call    CreatePath
0x18003f9eb  test    eax, eax
0x18003f9ed  jnz     short loc_18003FA4D
0x18003f9ef  mov     rcx, [rsp+0F8h]; this
0x18003f9f7  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f9fe  lea     edx, [rax+41h]; void *
0x18003fa01  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003fa06  mov     edi, eax
0x18003fa08  cmp     [rsp+0F8h+var_A8], 8
0x18003fa0e  jb      short loc_18003FA1B
0x18003fa10  mov     rcx, [rsp+0F8h+Src]
0x18003fa15  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003fa1b  mov     [rsp+0F8h+var_A8], r12
0x18003fa20  mov     [rsp+0F8h+var_B0], r15
0x18003fa25  mov     word ptr [rsp+0F8h+Src], r15w
0x18003fa2b  mov     rbx, [rsp+0F8h+lpMem]
0x18003fa30  test    rbx, rbx
0x18003fa33  jz      short loc_18003FA49
0x18003fa35  call    cs:__imp_GetProcessHeap
0x18003fa3b  mov     r8, rbx; lpMem
0x18003fa3e  xor     edx, edx; dwFlags
0x18003fa40  mov     rcx, rax; hHeap
0x18003fa43  call    cs:__imp_HeapFree
0x18003fa49  mov     eax, edi
0x18003fa4b  jmp     short loc_18003FAB4
0x18003fa4d  lea     rax, [rsp+0F8h+Src]
0x18003fa52  cmp     r14, rax
0x18003fa55  jz      short loc_18003FA6B
0x18003fa57  mov     r9, rsi
0x18003fa5a  xor     r8d, r8d
0x18003fa5d  lea     rdx, [rsp+0F8h+Src]
0x18003fa62  mov     rcx, r14; void *
0x18003fa65  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18003fa6a  nop
0x18003fa6b  cmp     [rsp+0F8h+var_A8], 8
0x18003fa71  jb      short loc_18003FA7E
0x18003fa73  mov     rcx, [rsp+0F8h+Src]
0x18003fa78  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003fa7e  mov     [rsp+0F8h+var_A8], r12
0x18003fa83  mov     [rsp+0F8h+var_B0], r15
0x18003fa88  mov     word ptr [rsp+0F8h+Src], r15w
0x18003fa8e  mov     rbx, [rsp+0F8h+lpMem]
0x18003fa93  test    rbx, rbx
0x18003fa96  jz      short loc_18003FAAC
0x18003fa98  call    cs:__imp_GetProcessHeap
0x18003fa9e  mov     r8, rbx; lpMem
0x18003faa1  xor     edx, edx; dwFlags
0x18003faa3  mov     rcx, rax; hHeap
0x18003faa6  call    cs:__imp_HeapFree
0x18003faac  xor     eax, eax
0x18003faae  jmp     short loc_18003FAB4
0x18003fab0  mov     eax, dword ptr [rsp+0F8h+lpMem]
0x18003fab4  mov     rcx, [rsp+0F8h+var_38]
0x18003fabc  xor     rcx, rsp; StackCookie
0x18003fabf  call    __security_check_cookie
0x18003fac4  mov     rbx, [rsp+0F8h+arg_10]
0x18003facc  add     rsp, 0D0h
0x18003fad3  pop     r15
0x18003fad5  pop     r14
0x18003fad7  pop     r12
0x18003fad9  pop     rdi
0x18003fada  pop     rsi
0x18003fadb  retn
```
