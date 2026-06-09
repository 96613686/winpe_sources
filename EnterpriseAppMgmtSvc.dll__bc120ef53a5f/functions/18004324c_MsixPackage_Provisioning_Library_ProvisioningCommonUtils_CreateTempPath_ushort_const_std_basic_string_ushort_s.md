# MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateTempPath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18004324c`
- end: `0x1800435eb`
- name: `?CreateTempPath@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `927`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180042244`

## callees

- `0x18000d3bc`
- `0x18000d3dc`
- `0x18001d050`
- `0x18001d160`
- `0x18003e50c`
- `0x18004324c`
- `0x180064654`
- `0x180064da0`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180043411`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800434ff`
- `msvcrt!??3@YAXPEAX@Z` at `0x180043574`
- `msvcrt!??3@YAXPEAX@Z` at `0x180043411`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800434ff`
- `msvcrt!??3@YAXPEAX@Z` at `0x180043574`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043330`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043437`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043525`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004359a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043330`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043437`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043525`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004359a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043344`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004344b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043539`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800435ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043344`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004344b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043539`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800435ae`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800433d5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800433d5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004346e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004346e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432e3`

## string_xrefs

- `0x180043314`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x1800433f2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`
- `0x1800434e1`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateTempPath(_WORD *Src, void **a2)
{
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  unsigned int v7; // ebx
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  HRESULT v13; // eax
  unsigned int v14; // ebx
  void *v15; // rdi
  HANDLE v16; // rax
  __int64 v17; // r8
  unsigned __int16 *v18; // rcx
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
  std::wstring::assign(Srca, Src);
  v12 = -1;
  do
    ++v12;
  while ( Src[v12] );
  if ( Src[v12 - 1] != 92 )
    std::wstring::append(Srca, (void *)L"\\");
  v13 = CoCreateGuid(&pguid);
  v14 = v13;
  if ( v13 >= 0 )
  {
    StringFromGUID2(&pguid, sz, 40);
    std::wstring::append(Srca, L"appxStage-");
    if ( sz[0] )
    {
      v17 = -1;
      do
        ++v17;
      while ( sz[v17] );
    }
    std::wstring::append(Srca, sz);
    v18 = (unsigned __int16 *)Srca;
    if ( v29 >= 8 )
      v18 = (unsigned __int16 *)Srca[0];
    if ( CreatePath(v18) )
    {
      if ( a2 != Srca )
        std::wstring::assign(a2);
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
0x18004324c  mov     [rsp+arg_10], rbx
0x180043251  push    rsi
0x180043252  push    rdi
0x180043253  push    r12
0x180043255  push    r14
0x180043257  push    r15
0x180043259  sub     rsp, 0D0h
0x180043260  mov     rax, cs:__security_cookie
0x180043267  xor     rax, rsp
0x18004326a  mov     [rsp+0F8h+var_38], rax
0x180043272  mov     r14, rdx
0x180043275  mov     rdi, rcx
0x180043278  xorps   xmm0, xmm0
0x18004327b  movups  xmmword ptr [rsp+0F8h+pguid.Data1], xmm0
0x180043280  xor     r15d, r15d
0x180043283  mov     [rsp+0F8h+lpMem], r15; int
0x180043288  xor     edx, edx; Val
0x18004328a  lea     r8d, [r15+50h]; Size
0x18004328e  lea     rcx, [rsp+0F8h+sz]; void *
0x180043293  call    memset_0
0x180043298  lea     rax, [rsp+0F8h+lpMem]
0x18004329d  mov     [rsp+0F8h+var_D0], rax
0x1800432a2  mov     [rsp+0F8h+var_C8], 1
0x1800432a7  test    rdi, rdi
0x1800432aa  jz      short loc_1800432B6
0x1800432ac  cmp     [rdi], r15w
0x1800432b0  jnz     loc_18004335C
0x1800432b6  call    GetTempDirectory
0x1800432bb  mov     rdi, rax
0x1800432be  test    rax, rax
0x1800432c1  jnz     loc_180043357
0x1800432c7  call    cs:__imp_GetLastError
0x1800432ce  nop     dword ptr [rax+rax+00h]
0x1800432d3  test    eax, eax
0x1800432d5  jle     short loc_1800432E1
0x1800432d7  movzx   eax, ax
0x1800432da  or      eax, 80070000h
0x1800432df  test    eax, eax
0x1800432e1  jns     short loc_180043304
0x1800432e3  call    cs:__imp_GetLastError
0x1800432ea  nop     dword ptr [rax+rax+00h]
0x1800432ef  mov     ebx, eax
0x1800432f1  test    eax, eax
0x1800432f3  jle     short loc_1800432FE
0x1800432f5  movzx   ebx, ax
0x1800432f8  or      ebx, 80070000h
0x1800432fe  test    ebx, ebx
0x180043300  jns     short loc_180043357
0x180043302  jmp     short loc_180043309
0x180043304  mov     ebx, 80004005h
0x180043309  mov     rcx, [rsp+0F8h]; this
0x180043311  mov     r9d, ebx; char *
0x180043314  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004331b  mov     edx, 2Fh ; '/'; void *
0x180043320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043325  nop
0x180043326  mov     rdi, [rsp+0F8h+lpMem]
0x18004332b  test    rdi, rdi
0x18004332e  jz      short loc_180043350
0x180043330  call    cs:__imp_GetProcessHeap
0x180043337  nop     dword ptr [rax+rax+00h]
0x18004333c  mov     r8, rdi; lpMem
0x18004333f  xor     edx, edx; dwFlags
0x180043341  mov     rcx, rax; hHeap
0x180043344  call    cs:__imp_HeapFree
0x18004334b  nop     dword ptr [rax+rax+00h]
0x180043350  mov     eax, ebx
0x180043352  jmp     loc_1800435C2
0x180043357  mov     [rsp+0F8h+lpMem], rdi; int
0x18004335c  mov     r12d, 7
0x180043362  mov     [rsp+0F8h+var_A8], r12
0x180043367  mov     [rsp+0F8h+var_B0], r15
0x18004336c  mov     word ptr [rsp+0F8h+Src], r15w
0x180043372  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180043376  cmp     [rdi], r15w
0x18004337a  jnz     short loc_180043381
0x18004337c  mov     r8, r15
0x18004337f  jmp     short loc_18004338E
0x180043381  mov     r8, rsi
0x180043384  inc     r8
0x180043387  cmp     [rdi+r8*2], r15w
0x18004338c  jnz     short loc_180043384
0x18004338e  mov     rdx, rdi; Src
0x180043391  lea     rcx, [rsp+0F8h+Src]; void *
0x180043396  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004339b  mov     rax, rsi
0x18004339e  inc     rax
0x1800433a1  cmp     [rdi+rax*2], r15w
0x1800433a6  jnz     short loc_18004339E
0x1800433a8  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x1800433ae  jz      short loc_1800433D0
0x1800433b0  mov     r8, r15
0x1800433b3  cmp     word ptr cs:pszSrc, r15w; "\\"
0x1800433bb  setnz   r8b
0x1800433bf  lea     rdx, pszSrc; "\\"
0x1800433c6  lea     rcx, [rsp+0F8h+Src]; Src
0x1800433cb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800433d0  lea     rcx, [rsp+0F8h+pguid]; pguid
0x1800433d5  call    cs:__imp_CoCreateGuid
0x1800433dc  nop     dword ptr [rax+rax+00h]
0x1800433e1  mov     ebx, eax
0x1800433e3  test    eax, eax
0x1800433e5  jns     short loc_18004345E
0x1800433e7  mov     rcx, [rsp+0F8h]; this
0x1800433ef  mov     r9d, eax; char *
0x1800433f2  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800433f9  mov     edx, 3Ah ; ':'; void *
0x1800433fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043403  nop
0x180043404  cmp     [rsp+0F8h+var_A8], 8
0x18004340a  jb      short loc_18004341D
0x18004340c  mov     rcx, [rsp+0F8h+Src]
0x180043411  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180043418  nop     dword ptr [rax+rax+00h]
0x18004341d  mov     [rsp+0F8h+var_A8], r12
0x180043422  mov     [rsp+0F8h+var_B0], r15
0x180043427  mov     word ptr [rsp+0F8h+Src], r15w
0x18004342d  mov     rdi, [rsp+0F8h+lpMem]
0x180043432  test    rdi, rdi
0x180043435  jz      short loc_180043457
0x180043437  call    cs:__imp_GetProcessHeap
0x18004343e  nop     dword ptr [rax+rax+00h]
0x180043443  mov     r8, rdi; lpMem
0x180043446  xor     edx, edx; dwFlags
0x180043448  mov     rcx, rax; hHeap
0x18004344b  call    cs:__imp_HeapFree
0x180043452  nop     dword ptr [rax+rax+00h]
0x180043457  mov     eax, ebx
0x180043459  jmp     loc_1800435C2
0x18004345e  mov     r8d, 28h ; '('; cchMax
0x180043464  lea     rdx, [rsp+0F8h+sz]; lpsz
0x180043469  lea     rcx, [rsp+0F8h+pguid]; rguid
0x18004346e  call    cs:__imp_StringFromGUID2
0x180043475  nop     dword ptr [rax+rax+00h]
0x18004347a  mov     r8d, 0Ah
0x180043480  lea     rdx, aAppxstage; "appxStage-"
0x180043487  lea     rcx, [rsp+0F8h+Src]; Src
0x18004348c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180043491  cmp     [rsp+0F8h+sz], r15w
0x180043497  jnz     short loc_18004349E
0x180043499  mov     r8, r15
0x18004349c  jmp     short loc_1800434B0
0x18004349e  lea     rax, [rsp+0F8h+sz]
0x1800434a3  mov     r8, rsi
0x1800434a6  inc     r8
0x1800434a9  cmp     [rax+r8*2], r15w
0x1800434ae  jnz     short loc_1800434A6
0x1800434b0  lea     rdx, [rsp+0F8h+sz]; void *
0x1800434b5  lea     rcx, [rsp+0F8h+Src]; Src
0x1800434ba  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800434bf  lea     rcx, [rsp+0F8h+Src]
0x1800434c4  cmp     [rsp+0F8h+var_A8], 8
0x1800434ca  cmovnb  rcx, [rsp+0F8h+Src]
0x1800434d0  call    CreatePath
0x1800434d5  test    eax, eax
0x1800434d7  jnz     short loc_180043549
0x1800434d9  mov     rcx, [rsp+0F8h]; this
0x1800434e1  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800434e8  lea     edx, [rax+41h]; void *
0x1800434eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800434f0  mov     edi, eax
0x1800434f2  cmp     [rsp+0F8h+var_A8], 8
0x1800434f8  jb      short loc_18004350B
0x1800434fa  mov     rcx, [rsp+0F8h+Src]
0x1800434ff  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180043506  nop     dword ptr [rax+rax+00h]
0x18004350b  mov     [rsp+0F8h+var_A8], r12
0x180043510  mov     [rsp+0F8h+var_B0], r15
0x180043515  mov     word ptr [rsp+0F8h+Src], r15w
0x18004351b  mov     rbx, [rsp+0F8h+lpMem]
0x180043520  test    rbx, rbx
0x180043523  jz      short loc_180043545
0x180043525  call    cs:__imp_GetProcessHeap
0x18004352c  nop     dword ptr [rax+rax+00h]
0x180043531  mov     r8, rbx; lpMem
0x180043534  xor     edx, edx; dwFlags
0x180043536  mov     rcx, rax; hHeap
0x180043539  call    cs:__imp_HeapFree
0x180043540  nop     dword ptr [rax+rax+00h]
0x180043545  mov     eax, edi
0x180043547  jmp     short loc_1800435C2
0x180043549  lea     rax, [rsp+0F8h+Src]
0x18004354e  cmp     r14, rax
0x180043551  jz      short loc_180043567
0x180043553  mov     r9, rsi
0x180043556  xor     r8d, r8d
0x180043559  lea     rdx, [rsp+0F8h+Src]
0x18004355e  mov     rcx, r14; void *
0x180043561  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180043566  nop
0x180043567  cmp     [rsp+0F8h+var_A8], 8
0x18004356d  jb      short loc_180043580
0x18004356f  mov     rcx, [rsp+0F8h+Src]
0x180043574  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004357b  nop     dword ptr [rax+rax+00h]
0x180043580  mov     [rsp+0F8h+var_A8], r12
0x180043585  mov     [rsp+0F8h+var_B0], r15
0x18004358a  mov     word ptr [rsp+0F8h+Src], r15w
0x180043590  mov     rbx, [rsp+0F8h+lpMem]
0x180043595  test    rbx, rbx
0x180043598  jz      short loc_1800435BA
0x18004359a  call    cs:__imp_GetProcessHeap
0x1800435a1  nop     dword ptr [rax+rax+00h]
0x1800435a6  mov     r8, rbx; lpMem
0x1800435a9  xor     edx, edx; dwFlags
0x1800435ab  mov     rcx, rax; hHeap
0x1800435ae  call    cs:__imp_HeapFree
0x1800435b5  nop     dword ptr [rax+rax+00h]
0x1800435ba  xor     eax, eax
0x1800435bc  jmp     short loc_1800435C2
0x1800435be  mov     eax, dword ptr [rsp+0F8h+lpMem]
0x1800435c2  mov     rcx, [rsp+0F8h+var_38]
0x1800435ca  xor     rcx, rsp; StackCookie
0x1800435cd  call    __security_check_cookie
0x1800435d2  mov     rbx, [rsp+0F8h+arg_10]
0x1800435da  add     rsp, 0D0h
0x1800435e1  pop     r15
0x1800435e3  pop     r14
0x1800435e5  pop     r12
0x1800435e7  pop     rdi
0x1800435e8  pop     rsi
0x1800435e9  retn
```
