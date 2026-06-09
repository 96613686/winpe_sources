# ExpandAndResolveCondition(ICondition *,IPropertyKeyStore *,int,int,int,ushort const *,_GUID const &,void * *)

- ea: `0x180032340`
- end: `0x1800327ce`
- name: `?ExpandAndResolveCondition@@YAJPEAUICondition@@PEAUIPropertyKeyStore@@HHHPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `1166`
- prototype: `int(struct ICondition *, struct IPropertyKeyStore *, int, int, int, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031ef8`

## callees

- `0x180032340`
- `0x180032c40`
- `0x18004c12c`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18003278e`
- `SHCORE!IUnknown_Set` at `0x18003278e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032653`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800326d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032653`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800326d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800324d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800325fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800324d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800325fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003256e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003256e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800326ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800326ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800323dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800323dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180032467`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180032467`
- `PROPSYS!PSGetPropertyDescriptionListFromString` at `0x180032518`
- `PROPSYS!PSGetPropertyDescriptionListFromString` at `0x180032518`

## pseudocode

```c
__int64 __fastcall ExpandAndResolveCondition(
        IUnknown *a1,
        struct IPropertyKeyStore *a2,
        int a3,
        __int64 a4,
        int a5,
        const unsigned __int16 *lpSubKey,
        const struct _GUID *a7,
        void **a8)
{
  unsigned int v8; // esi
  IUnknown *v9; // rdi
  void *v10; // r15
  int v11; // r12d
  LSTATUS ValueW; // eax
  int Instance; // ebx
  WCHAR *v14; // rdx
  WCHAR *v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rax
  WCHAR *v18; // rdx
  __int64 *v20; // rsi
  HLOCAL v21; // r14
  __int64 v22; // rdi
  __int64 v23; // rax
  __int64 v24; // rcx
  int KeyArrayFromPropertyKeyStore; // eax
  int pvData; // [rsp+28h] [rbp-D8h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR pszStr2; // [rsp+60h] [rbp-A0h]
  _QWORD v31[7]; // [rsp+68h] [rbp-98h]
  _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszPropList[264]; // [rsp+B0h] [rbp-50h] BYREF

  v8 = 0;
  *(_QWORD *)&SystemTime.wYear = a1;
  v9 = a1;
  ppv = 0;
  v10 = 0;
  *a8 = 0;
  v11 = 0;
  pcbData[0] = 0;
  if ( a3 )
  {
    Instance = 0;
    if ( !a2 )
      goto LABEL_32;
    KeyArrayFromPropertyKeyStore = GetKeyArrayFromPropertyKeyStore(a2, (struct _tagpropertykey **)&ppv, pcbData);
    v10 = ppv;
    Instance = KeyArrayFromPropertyKeyStore;
    v11 = pcbData[0];
LABEL_31:
    if ( Instance < 0 )
      goto LABEL_16;
LABEL_32:
    *(_QWORD *)pcbData = 0;
    if ( v11 )
    {
      ppv = 0;
      Instance = CoCreateInstance(
                   &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
                   0,
                   1u,
                   &GUID_71d222e1_432f_429e_8c13_b6dafde5077a,
                   &ppv);
      if ( Instance < 0 )
      {
LABEL_40:
        v24 = *(_QWORD *)pcbData;
        *(_QWORD *)pcbData = 0;
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        goto LABEL_16;
      }
      Instance = ExpandWordWheelCondition((int)v10, v11, (int)v9, (int)ppv, 1, pvData, (void **)pcbData);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else
    {
      IUnknown_Set((IUnknown **)pcbData, v9);
    }
    if ( Instance >= 0 )
    {
      SystemTime = 0;
      GetLocalTime(&SystemTime);
      v29[0] = 0;
      Instance = CoCreateInstance(
                   &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
                   0,
                   1u,
                   &GUID_71d222e1_432f_429e_8c13_b6dafde5077a,
                   v29);
      if ( Instance >= 0 )
      {
        ppv = 0;
        Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, _SYSTEMTIME *, void **))(*(_QWORD *)v29[0] + 48LL))(
                     v29[0],
                     *(_QWORD *)pcbData,
                     128,
                     &SystemTime,
                     &ppv);
        if ( Instance >= 0 )
        {
          Instance = (**(__int64 (__fastcall ***)(void *, GUID *, void **))ppv)(
                       ppv,
                       &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                       a8);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
      }
    }
    goto LABEL_40;
  }
  pcbData[0] = 520;
  ValueW = RegGetValueW(HKEY_CURRENT_USER, lpSubKey, L"PropertyList", 2u, 0, pszPropList, pcbData);
  Instance = ValueW;
  if ( ValueW )
  {
    pszPropList[0] = 0;
    if ( ValueW > 0 )
      Instance = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( Instance >= 0 )
  {
LABEL_17:
    ppv = 0;
    Instance = PSGetPropertyDescriptionListFromString(pszPropList, &GUID_1f9fc1d0_c39b_4b26_817f_011967d3440e, &ppv);
    if ( Instance < 0 )
      goto LABEL_16;
    v20 = (__int64 *)ppv;
    pcbData[0] = 0;
    Instance = (*(__int64 (__fastcall **)(void *, DWORD *))(*(_QWORD *)ppv + 24LL))(ppv, pcbData);
    if ( Instance >= 0 )
    {
      v29[0] = 0;
      if ( is_mul_ok(pcbData[0], 0x14u) )
      {
        v21 = LocalAlloc(0x40u, 20LL * pcbData[0]);
        Instance = 0;
        if ( v21 )
        {
          v22 = 0;
          while ( (unsigned int)v22 < pcbData[0] )
          {
            v23 = *v20;
            v29[0] = 0;
            Instance = (*(__int64 (__fastcall **)(__int64 *, _QWORD, GUID *, LPVOID *))(v23 + 32))(
                         v20,
                         (unsigned int)v22,
                         &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
                         v29);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v29[0] + 24LL))(
                           v29[0],
                           (__int64)v21 + 20 * v22);
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
            }
            v22 = (unsigned int)(v22 + 1);
            if ( Instance < 0 )
              goto LABEL_29;
          }
          v10 = v21;
          v11 = pcbData[0];
          v21 = 0;
LABEL_29:
          LocalFree(v21);
        }
        else
        {
          Instance = -2147024882;
        }
      }
      else
      {
        Instance = -2147024362;
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    v9 = *(IUnknown **)&SystemTime.wYear;
    goto LABEL_31;
  }
  pszStr2 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Search\\PrimaryProperties\\UnindexedLocations";
  v31[0] = L"prop:System.ItemNameDisplay;System.Size;System.DateModified";
  v31[1] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Search\\PrimaryProperties\\IndexedLocations";
  v31[3] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Search\\PrimaryProperties\\PCSettings";
  v31[4] = L"prop:System.ItemNameDisplay;System.HighKeywords;System.MediumKeywords;System.LowKeywords";
  v31[5] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Search\\PrimaryProperties\\HighPCSettings";
  v31[6] = L"prop:System.ItemNameDisplay;System.HighKeywords";
  v31[2] = L"prop:System.ItemNameDisplay;System.Size;System.DateModified";
  while ( v8 < 4 )
  {
    if ( !StrCmpICW(lpSubKey, (LPCWSTR)v31[2 * v8 - 1]) )
    {
      _mm_lfence();
      v14 = (WCHAR *)v31[2 * v8];
      v15 = pszPropList;
      v16 = 2147483646;
      v17 = 260;
      do
      {
        if ( !v16 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v16;
        --v17;
      }
      while ( v17 );
      v18 = v15 - 1;
      Instance = -2147024774;
      if ( v17 )
      {
        v18 = v15;
        Instance = 0;
      }
      *v18 = 0;
      if ( v17 )
        goto LABEL_17;
      break;
    }
    ++v8;
  }
LABEL_16:
  LocalFree(v10);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180032340  mov     [rsp-8+arg_10], rbx
0x180032345  push    rbp
0x180032346  push    rsi
0x180032347  push    rdi
0x180032348  push    r12
0x18003234a  push    r13
0x18003234c  push    r14
0x18003234e  push    r15
0x180032350  lea     rbp, [rsp-1D0h]
0x180032358  sub     rsp, 2D0h
0x18003235f  mov     rax, cs:__security_cookie
0x180032366  xor     rax, rsp
0x180032369  mov     [rbp+200h+var_40], rax
0x180032370  mov     r13, [rbp+200h+arg_38]
0x180032377  xor     esi, esi
0x180032379  mov     r14, [rbp+200h+lpSubKey]
0x180032380  mov     rax, rdx
0x180032383  mov     qword ptr [rbp+200h+SystemTime.wYear], rcx
0x180032387  mov     rdi, rcx
0x18003238a  mov     [rsp+300h+ppv], rsi
0x18003238f  mov     r15d, esi
0x180032392  mov     [r13+0], rsi
0x180032396  mov     r12d, esi
0x180032399  mov     [rsp+300h+var_2C0], esi
0x18003239d  test    r8d, r8d
0x1800323a0  jnz     loc_180032799
0x1800323a6  lea     rax, [rsp+300h+var_2C0]
0x1800323ab  mov     [rsp+300h+var_2C0], 208h
0x1800323b3  mov     [rsp+300h+pcbData], rax; pcbData
0x1800323b8  lea     r8, aPropertylist; "PropertyList"
0x1800323bf  lea     rax, [rbp+200h+pszPropList]
0x1800323c3  mov     r9d, 2; dwFlags
0x1800323c9  mov     [rsp+300h+pvData], rax; int
0x1800323ce  mov     rdx, r14; lpSubKey
0x1800323d1  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800323d8  mov     [rsp+300h+pdwType], rsi; pdwType
0x1800323dd  call    cs:__imp_RegGetValueW
0x1800323e3  mov     ebx, eax
0x1800323e5  test    eax, eax
0x1800323e7  jz      short loc_1800323F8
0x1800323e9  mov     [rbp+200h+pszPropList], si
0x1800323ed  jle     short loc_1800323F8
0x1800323ef  movzx   ebx, ax
0x1800323f2  or      ebx, 80070000h
0x1800323f8  test    ebx, ebx
0x1800323fa  jns     loc_180032503
0x180032400  lea     rax, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180032407  mov     [rsp+300h+pszStr2], rax
0x18003240c  lea     rcx, aPropSystemItem_1; "prop:System.ItemNameDisplay;System.Size"...
0x180032413  lea     rax, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003241a  mov     [rsp+300h+var_298], rcx
0x18003241f  mov     [rsp+300h+var_290], rax
0x180032424  lea     rax, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003242b  mov     [rbp+200h+var_280], rax
0x18003242f  lea     rax, aPropSystemItem_0; "prop:System.ItemNameDisplay;System.High"...
0x180032436  mov     [rbp+200h+var_278], rax
0x18003243a  lea     rax, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180032441  mov     [rbp+200h+var_270], rax
0x180032445  lea     rax, aPropSystemItem; "prop:System.ItemNameDisplay;System.High"...
0x18003244c  mov     [rbp+200h+var_268], rax
0x180032450  mov     [rsp+300h+var_288], rcx
0x180032455  cmp     esi, 4
0x180032458  jnb     short loc_1800324CE
0x18003245a  mov     edi, esi
0x18003245c  mov     rcx, r14; pszStr1
0x18003245f  add     rdi, rdi
0x180032462  mov     rdx, [rsp+rdi*8+300h+pszStr2]; pszStr2
0x180032467  call    cs:__imp_StrCmpICW
0x18003246d  test    eax, eax
0x18003246f  jnz     loc_1800327C7
0x180032475  lfence
0x180032478  mov     rdx, [rsp+rdi*8+300h+var_298]
0x18003247d  lea     r8, [rbp+200h+pszPropList]
0x180032481  mov     ecx, 7FFFFFFEh
0x180032486  mov     eax, 104h
0x18003248b  nop     dword ptr [rax+rax+00h]
0x180032490  test    rcx, rcx
0x180032493  jz      short loc_1800324B4
0x180032495  movzx   r9d, word ptr [rdx]
0x180032499  test    r9w, r9w
0x18003249d  jz      short loc_1800324B4
0x18003249f  mov     [r8], r9w
0x1800324a3  add     rdx, 2
0x1800324a7  add     r8, 2
0x1800324ab  dec     rcx
0x1800324ae  sub     rax, 1
0x1800324b2  jnz     short loc_180032490
0x1800324b4  xor     esi, esi
0x1800324b6  lea     rdx, [r8-2]
0x1800324ba  test    rax, rax
0x1800324bd  mov     ebx, 8007007Ah
0x1800324c2  cmovnz  rdx, r8
0x1800324c6  cmovnz  ebx, esi
0x1800324c9  mov     [rdx], si
0x1800324cc  jnz     short loc_180032503
0x1800324ce  mov     rcx, r15; hMem
0x1800324d1  call    cs:__imp_LocalFree
0x1800324d7  mov     eax, ebx
0x1800324d9  mov     rcx, [rbp+200h+var_40]
0x1800324e0  xor     rcx, rsp; StackCookie
0x1800324e3  call    __security_check_cookie
0x1800324e8  mov     rbx, [rsp+300h+arg_10]
0x1800324f0  add     rsp, 2D0h
0x1800324f7  pop     r15
0x1800324f9  pop     r14
0x1800324fb  pop     r13
0x1800324fd  pop     r12
0x1800324ff  pop     rdi
0x180032500  pop     rsi
0x180032501  pop     rbp
0x180032502  retn
0x180032503  lea     r8, [rsp+300h+ppv]; ppv
0x180032508  mov     [rsp+300h+ppv], rsi
0x18003250d  lea     rdx, _GUID_1f9fc1d0_c39b_4b26_817f_011967d3440e; riid
0x180032514  lea     rcx, [rbp+200h+pszPropList]; pszPropList
0x180032518  call    cs:__imp_PSGetPropertyDescriptionListFromString
0x18003251e  mov     ebx, eax
0x180032520  test    eax, eax
0x180032522  js      short loc_1800324CE
0x180032524  mov     rsi, [rsp+300h+ppv]
0x180032529  lea     rdx, [rsp+300h+var_2C0]
0x18003252e  mov     rcx, rsi
0x180032531  mov     [rsp+300h+var_2C0], r12d
0x180032536  mov     rax, [rsi]
0x180032539  mov     rax, [rax+18h]
0x18003253d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032542  mov     ebx, eax
0x180032544  test    eax, eax
0x180032546  js      loc_180032601
0x18003254c  mov     ecx, [rsp+300h+var_2C0]
0x180032550  mov     eax, 14h
0x180032555  mul     rcx
0x180032558  mov     [rsp+300h+var_2B0], r12
0x18003255d  test    rdx, rdx
0x180032560  jnz     loc_18003277C
0x180032566  mov     rdx, rax; uBytes
0x180032569  mov     ecx, 40h ; '@'; uFlags
0x18003256e  call    cs:__imp_LocalAlloc
0x180032574  mov     r14, rax
0x180032577  xor     ebx, ebx
0x180032579  test    r14, r14
0x18003257c  mov     eax, 8007000Eh
0x180032581  cmovz   ebx, eax
0x180032584  jz      short loc_180032601
0x180032586  xor     edi, edi
0x180032588  mov     eax, [rsp+300h+var_2C0]
0x18003258c  cmp     edi, eax
0x18003258e  jnb     short loc_1800325EF
0x180032590  mov     rax, [rsi]
0x180032593  lea     r9, [rsp+300h+var_2B0]
0x180032598  lea     r8, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814
0x18003259f  mov     [rsp+300h+var_2B0], r12
0x1800325a4  mov     edx, edi
0x1800325a6  mov     rcx, rsi
0x1800325a9  mov     rax, [rax+20h]
0x1800325ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325b2  mov     ebx, eax
0x1800325b4  test    eax, eax
0x1800325b6  js      short loc_1800325E7
0x1800325b8  mov     r9, [rsp+300h+var_2B0]
0x1800325bd  lea     rcx, [rdi+rdi*4]
0x1800325c1  lea     rdx, [r14+rcx*4]
0x1800325c5  mov     rcx, r9
0x1800325c8  mov     r8, [r9]
0x1800325cb  mov     rax, [r8+18h]
0x1800325cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325d4  mov     rcx, [rsp+300h+var_2B0]
0x1800325d9  mov     ebx, eax
0x1800325db  mov     rax, [rcx]
0x1800325de  mov     rax, [rax+10h]
0x1800325e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325e7  inc     edi
0x1800325e9  test    ebx, ebx
0x1800325eb  jns     short loc_180032588
0x1800325ed  jmp     short loc_1800325F8
0x1800325ef  mov     r15, r14
0x1800325f2  mov     r12d, eax
0x1800325f5  xor     r14d, r14d
0x1800325f8  mov     rcx, r14; hMem
0x1800325fb  call    cs:__imp_LocalFree
0x180032601  mov     rcx, [rsp+300h+ppv]
0x180032606  mov     rax, [rcx]
0x180032609  mov     rax, [rax+10h]
0x18003260d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032612  mov     rdi, qword ptr [rbp+200h+SystemTime.wYear]
0x180032616  xor     esi, esi
0x180032618  test    ebx, ebx
0x18003261a  js      loc_1800324CE
0x180032620  mov     qword ptr [rsp+300h+var_2C0], rsi
0x180032625  test    r12d, r12d
0x180032628  jz      loc_180032786
0x18003262e  lea     rax, [rsp+300h+ppv]
0x180032633  mov     [rsp+300h+ppv], rsi
0x180032638  lea     r9, _GUID_71d222e1_432f_429e_8c13_b6dafde5077a; riid
0x18003263f  mov     [rsp+300h+pdwType], rax; ppv
0x180032644  xor     edx, edx; pUnkOuter
0x180032646  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x18003264d  mov     r8d, 1; dwClsContext
0x180032653  call    cs:__imp_CoCreateInstance
0x180032659  mov     ebx, eax
0x18003265b  test    eax, eax
0x18003265d  js      loc_180032758
0x180032663  mov     r9, [rsp+300h+ppv]; int
0x180032668  lea     rax, [rsp+300h+var_2C0]
0x18003266d  mov     [rsp+300h+pcbData], rax; void **
0x180032672  mov     r8, rdi; int
0x180032675  mov     edx, r12d; int
0x180032678  mov     dword ptr [rsp+300h+pdwType], 1; int
0x180032680  mov     rcx, r15; int
0x180032683  call    ExpandWordWheelCondition
0x180032688  mov     rcx, [rsp+300h+ppv]
0x18003268d  mov     ebx, eax
0x18003268f  mov     rax, [rcx]
0x180032692  mov     rax, [rax+10h]
0x180032696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003269b  test    ebx, ebx
0x18003269d  js      loc_180032758
0x1800326a3  xorps   xmm0, xmm0
0x1800326a6  lea     rcx, [rbp+200h+SystemTime]; lpSystemTime
0x1800326aa  movups  xmmword ptr [rbp+200h+SystemTime.wYear], xmm0
0x1800326ae  call    cs:__imp_GetLocalTime
0x1800326b4  lea     rax, [rsp+300h+var_2B0]
0x1800326b9  mov     [rsp+300h+var_2B0], rsi
0x1800326be  lea     r9, _GUID_71d222e1_432f_429e_8c13_b6dafde5077a; riid
0x1800326c5  mov     [rsp+300h+pdwType], rax; ppv
0x1800326ca  xor     edx, edx; pUnkOuter
0x1800326cc  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x1800326d3  mov     r8d, 1; dwClsContext
0x1800326d9  call    cs:__imp_CoCreateInstance
0x1800326df  mov     ebx, eax
0x1800326e1  test    eax, eax
0x1800326e3  js      short loc_180032758
0x1800326e5  mov     rcx, [rsp+300h+var_2B0]
0x1800326ea  lea     rdx, [rsp+300h+ppv]
0x1800326ef  mov     [rsp+300h+ppv], rsi
0x1800326f4  lea     r9, [rbp+200h+SystemTime]
0x1800326f8  mov     [rsp+300h+pdwType], rdx
0x1800326fd  mov     r8d, 80h
0x180032703  mov     rdx, qword ptr [rsp+300h+var_2C0]
0x180032708  mov     rax, [rcx]
0x18003270b  mov     rax, [rax+30h]
0x18003270f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032714  mov     ebx, eax
0x180032716  test    eax, eax
0x180032718  js      short loc_180032747
0x18003271a  mov     rcx, [rsp+300h+ppv]
0x18003271f  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x180032726  mov     r8, r13
0x180032729  mov     rax, [rcx]
0x18003272c  mov     rax, [rax]
0x18003272f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032734  mov     rcx, [rsp+300h+ppv]
0x180032739  mov     ebx, eax
0x18003273b  mov     rax, [rcx]
0x18003273e  mov     rax, [rax+10h]
0x180032742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032747  mov     rcx, [rsp+300h+var_2B0]
0x18003274c  mov     rax, [rcx]
0x18003274f  mov     rax, [rax+10h]
0x180032753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032758  mov     rcx, qword ptr [rsp+300h+var_2C0]
0x18003275d  mov     qword ptr [rsp+300h+var_2C0], rsi
0x180032762  test    rcx, rcx
0x180032765  jz      loc_1800324CE
0x18003276b  mov     rax, [rcx]
0x18003276e  mov     rax, [rax+10h]
0x180032772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032777  jmp     loc_1800324CE
0x18003277c  mov     ebx, 80070216h
0x180032781  jmp     loc_180032601
0x180032786  mov     rdx, rdi; punk
0x180032789  lea     rcx, [rsp+300h+var_2C0]; ppunk
0x18003278e  call    cs:__imp_IUnknown_Set
0x180032794  jmp     loc_18003269B
0x180032799  mov     ebx, esi
0x18003279b  test    rax, rax
0x18003279e  jz      loc_180032620
0x1800327a4  lea     r8, [rsp+300h+var_2C0]; unsigned int *
0x1800327a9  mov     rcx, rax; struct IPropertyKeyStore *
0x1800327ac  lea     rdx, [rsp+300h+ppv]; struct _tagpropertykey **
0x1800327b1  call    ?GetKeyArrayFromPropertyKeyStore@@YAJPEAUIPropertyKeyStore@@PEAPEAU_tagpropertykey@@PEAI@Z; GetKeyArrayFromPropertyKeyStore(IPropertyKeyStore *,_tagpropertykey * *,uint *)
0x1800327b6  mov     r15, [rsp+300h+ppv]
0x1800327bb  mov     ebx, eax
0x1800327bd  mov     r12d, [rsp+300h+var_2C0]
0x1800327c2  jmp     loc_180032618
0x1800327c7  inc     esi
0x1800327c9  jmp     loc_180032455
```
