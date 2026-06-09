# NgcFirst::GetSwitchCountsHelper

- ea: `0x1800856b8`
- end: `0x180085985`
- name: `NgcFirst::GetSwitchCountsHelper`
- size: `717`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpSubKey@<rcx>, LPCWSTR lpValue@<rdx>, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042a1c`
- `0x180042e40`

## callees

- `0x18000782c`
- `0x180032b6c`
- `0x180032c20`
- `0x1800856b8`
- `0x180085ba0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085717`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085717`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800857ac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180085866`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800857ac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180085866`

## string_xrefs

- `0x1800857d2`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x1800858a0`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`

## pseudocode

```c
__int64 __fastcall NgcFirst::GetSwitchCountsHelper(
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        int *a3,
        const WCHAR *a4,
        int *a5,
        int a6)
{
  char v9; // si
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  bool v12; // sf
  __int64 v13; // rdx
  bool v14; // r14
  LSTATUS ValueW; // eax
  signed int v16; // edi
  bool v17; // di
  LSTATUS v18; // eax
  unsigned __int64 v19; // r9
  int v21; // eax
  int phkResult; // [rsp+20h] [rbp-40h]
  DWORD pdwType; // [rsp+40h] [rbp-20h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-1Ch] BYREF
  int pvData; // [rsp+48h] [rbp-18h] BYREF
  int v26; // [rsp+4Ch] [rbp-14h] BYREF
  int v27; // [rsp+50h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v9 = 1;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hkey);
  v11 = v10;
  if ( (v10 & 0xFFFFFFFD) != 0 )
  {
    v12 = v10 < 0;
    if ( v10 > 0 )
    {
      v11 = (unsigned __int16)v10 | 0x80070000;
      v12 = 1;
    }
    if ( v12 )
    {
      v13 = 583;
LABEL_30:
      v19 = v11;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
        (const char *)v19,
        phkResult);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  v26 = 0;
  v27 = 0;
  v14 = v10 == 2;
  pdwType = 0;
  pvData = 0;
  pcbData = 4;
  if ( !a3 || v10 == 2 )
  {
LABEL_19:
    v17 = v11 == 2;
    goto LABEL_20;
  }
  ValueW = RegGetValueW(hkey, 0, lpValue, 0x10u, &pdwType, &pvData, &pcbData);
  v16 = ValueW;
  if ( !ValueW )
  {
    if ( pdwType != 4 || pcbData != 4 )
    {
      v13 = 615;
      goto LABEL_29;
    }
    v26 = pvData;
    goto LABEL_19;
  }
  if ( ValueW != 2 )
  {
    if ( ValueW > 0 )
      v16 = (unsigned __int16)ValueW | 0x80070000;
    if ( v16 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x260,
        (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
        (const char *)(unsigned int)v16,
        phkResult);
    v11 = v16;
    goto LABEL_44;
  }
  v17 = 1;
LABEL_20:
  pcbData = 4;
  pdwType = 0;
  pvData = 0;
  if ( !a5 || v11 == 2 )
  {
LABEL_36:
    v9 = v14;
LABEL_37:
    if ( !v17 )
    {
      if ( !v9 )
      {
LABEL_39:
        if ( a3 )
          *a3 = v26;
        if ( a5 )
          *a5 = v27;
        v11 = 0;
        goto LABEL_44;
      }
LABEL_47:
      v27 = a6;
LABEL_48:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      v21 = NgcFirst::SetSwitchCountsHelper(
              lpSubKey,
              lpValue,
              (const BYTE *)((unsigned __int64)&v26 & -(__int64)v17),
              a4,
              (BYTE *)((unsigned __int64)&v27 & -(__int64)(v9 != 0)));
      v11 = v21;
      if ( v21 < 0 )
      {
        v19 = (unsigned int)v21;
        v13 = 677;
        goto LABEL_31;
      }
      goto LABEL_39;
    }
LABEL_46:
    v26 = 0;
    if ( !v9 )
      goto LABEL_48;
    goto LABEL_47;
  }
  v18 = RegGetValueW(hkey, 0, a4, 0x10u, &pdwType, &pvData, &pcbData);
  v11 = v18;
  if ( !v18 )
  {
    if ( pdwType == 4 && pcbData == 4 )
    {
      if ( pvData != a6 )
      {
        v17 = 1;
        goto LABEL_46;
      }
      v27 = pvData;
      goto LABEL_36;
    }
    v13 = 642;
LABEL_29:
    v11 = -2147418113;
    goto LABEL_30;
  }
  if ( v18 == 2 )
    goto LABEL_37;
  if ( v18 > 0 )
    v11 = (unsigned __int16)v18 | 0x80070000;
  if ( (v11 & 0x80000000) != 0 )
  {
    v13 = 635;
    goto LABEL_30;
  }
LABEL_44:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v11;
}

```

## disassembly

```asm
0x1800856b8  mov     rax, rsp
0x1800856bb  mov     [rax+18h], rbx
0x1800856bf  mov     [rax+20h], r9
0x1800856c3  mov     [rax+10h], rdx
0x1800856c7  mov     [rax+8], rcx
0x1800856cb  push    rbp
0x1800856cc  push    rsi
0x1800856cd  push    rdi
0x1800856ce  push    r12
0x1800856d0  push    r13
0x1800856d2  push    r14
0x1800856d4  push    r15
0x1800856d6  mov     rbp, rsp
0x1800856d9  sub     rsp, 60h
0x1800856dd  mov     rdi, rdx
0x1800856e0  mov     [rbp+hkey], 0
0x1800856e8  mov     rbx, rcx
0x1800856eb  xor     edx, edx
0x1800856ed  lea     rcx, [rbp+hkey]
0x1800856f1  mov     r12, r8
0x1800856f4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800856f9  lea     rax, [rbp+hkey]
0x1800856fd  mov     esi, 1
0x180085702  mov     r9d, esi; samDesired
0x180085705  mov     [rsp+60h+phkResult], rax; phkResult
0x18008570a  xor     r8d, r8d; ulOptions
0x18008570d  mov     rdx, rbx; lpSubKey
0x180085710  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180085717  call    cs:__imp_RegOpenKeyExW
0x18008571d  mov     ebx, eax
0x18008571f  test    eax, 0FFFFFFFDh
0x180085724  jz      short loc_180085745
0x180085726  test    eax, eax
0x180085728  jle     short loc_180085735
0x18008572a  movzx   ebx, bx
0x18008572d  or      ebx, 80070000h
0x180085733  test    ebx, ebx
0x180085735  jns     loc_1800858F3
0x18008573b  mov     edx, 247h
0x180085740  jmp     loc_180085899
0x180085745  cmp     ebx, 2
0x180085748  mov     [rbp+var_14], 0
0x18008574f  mov     r15d, 4
0x180085755  mov     [rbp+var_10], 0
0x18008575c  setz    r14b
0x180085760  mov     [rbp+pdwType], 0
0x180085767  mov     [rbp+var_18], 0
0x18008576e  mov     [rbp+var_1C], r15d
0x180085772  test    r12, r12
0x180085775  jz      loc_18008580C
0x18008577b  cmp     ebx, 2
0x18008577e  jz      loc_18008580C
0x180085784  mov     rcx, [rbp+hkey]; hkey
0x180085788  lea     rax, [rbp+var_1C]
0x18008578c  mov     [rsp+60h+pcbData], rax; pcbData
0x180085791  lea     r9d, [r15+0Ch]; dwFlags
0x180085795  lea     rax, [rbp+var_18]
0x180085799  mov     r8, rdi; lpValue
0x18008579c  mov     [rsp+60h+pvData], rax; pvData
0x1800857a1  xor     edx, edx; lpSubKey
0x1800857a3  lea     rax, [rbp+pdwType]
0x1800857a7  mov     [rsp+60h+phkResult], rax; int
0x1800857ac  call    cs:__imp_RegGetValueW
0x1800857b2  mov     edi, eax
0x1800857b4  test    eax, eax
0x1800857b6  jz      short loc_1800857F2
0x1800857b8  cmp     eax, 2
0x1800857bb  jz      short loc_1800857ED
0x1800857bd  test    eax, eax
0x1800857bf  jle     short loc_1800857CA
0x1800857c1  movzx   edi, ax
0x1800857c4  or      edi, 80070000h
0x1800857ca  test    edi, edi
0x1800857cc  jns     short loc_1800857E6
0x1800857ce  mov     rcx, [rbp+38h]; this
0x1800857d2  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x1800857d9  mov     r9d, edi; char *
0x1800857dc  mov     edx, 260h; void *
0x1800857e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800857e6  mov     ebx, edi
0x1800857e8  jmp     loc_1800858F3
0x1800857ed  mov     dil, sil
0x1800857f0  jmp     short loc_18008580F
0x1800857f2  cmp     [rbp+pdwType], r15d
0x1800857f6  jnz     loc_18008588F
0x1800857fc  cmp     [rbp+var_1C], r15d
0x180085800  jnz     loc_18008588F
0x180085806  mov     eax, [rbp+var_18]
0x180085809  mov     [rbp+var_14], eax
0x18008580c  mov     dil, r14b
0x18008580f  mov     r13d, [rbp+arg_28]
0x180085813  mov     [rbp+var_1C], r15d
0x180085817  mov     r15, [rbp+arg_20]
0x18008581b  mov     [rbp+pdwType], 0
0x180085822  mov     [rbp+var_18], 0
0x180085829  test    r15, r15
0x18008582c  jz      loc_1800858CD
0x180085832  cmp     ebx, 2
0x180085835  jz      loc_1800858CD
0x18008583b  mov     r8, [rbp+lpValue]; lpValue
0x18008583f  lea     rax, [rbp+var_1C]
0x180085843  mov     rcx, [rbp+hkey]; hkey
0x180085847  mov     r9d, 10h; dwFlags
0x18008584d  mov     [rsp+60h+pcbData], rax; pcbData
0x180085852  xor     edx, edx; lpSubKey
0x180085854  lea     rax, [rbp+var_18]
0x180085858  mov     [rsp+60h+pvData], rax; pvData
0x18008585d  lea     rax, [rbp+pdwType]
0x180085861  mov     [rsp+60h+phkResult], rax; pdwType
0x180085866  call    cs:__imp_RegGetValueW
0x18008586c  mov     ebx, eax
0x18008586e  test    eax, eax
0x180085870  jz      short loc_1800858AE
0x180085872  cmp     eax, 2
0x180085875  jz      short loc_1800858D0
0x180085877  test    eax, eax
0x180085879  jle     short loc_180085884
0x18008587b  movzx   ebx, ax
0x18008587e  or      ebx, 80070000h
0x180085884  test    ebx, ebx
0x180085886  jns     short loc_1800858F3
0x180085888  mov     edx, 27Bh
0x18008588d  jmp     short loc_180085899
0x18008588f  mov     edx, 267h; void *
0x180085894  mov     ebx, 8000FFFFh
0x180085899  mov     r9d, ebx; char *
0x18008589c  mov     rcx, [rbp+38h]; this
0x1800858a0  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x1800858a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800858ac  jmp     short loc_1800858F3
0x1800858ae  cmp     [rbp+pdwType], 4
0x1800858b2  jnz     loc_18008597B
0x1800858b8  cmp     [rbp+var_1C], 4
0x1800858bc  jnz     loc_18008597B
0x1800858c2  mov     eax, [rbp+var_18]
0x1800858c5  cmp     eax, r13d
0x1800858c8  jnz     short loc_180085916
0x1800858ca  mov     [rbp+var_10], eax
0x1800858cd  mov     sil, r14b
0x1800858d0  test    dil, dil
0x1800858d3  jnz     short loc_180085919
0x1800858d5  test    sil, sil
0x1800858d8  jnz     short loc_180085925
0x1800858da  test    r12, r12
0x1800858dd  jz      short loc_1800858E6
0x1800858df  mov     eax, [rbp+var_14]
0x1800858e2  mov     [r12], eax
0x1800858e6  test    r15, r15
0x1800858e9  jz      short loc_1800858F1
0x1800858eb  mov     eax, [rbp+var_10]
0x1800858ee  mov     [r15], eax
0x1800858f1  xor     ebx, ebx
0x1800858f3  lea     rcx, [rbp+hkey]
0x1800858f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800858fc  mov     eax, ebx
0x1800858fe  mov     rbx, [rsp+60h+arg_10]
0x180085906  add     rsp, 60h
0x18008590a  pop     r15
0x18008590c  pop     r14
0x18008590e  pop     r13
0x180085910  pop     r12
0x180085912  pop     rdi
0x180085913  pop     rsi
0x180085914  pop     rbp
0x180085915  retn
0x180085916  mov     dil, sil
0x180085919  mov     [rbp+var_14], 0
0x180085920  test    sil, sil
0x180085923  jz      short loc_180085929
0x180085925  mov     [rbp+var_10], r13d
0x180085929  xor     edx, edx
0x18008592b  lea     rcx, [rbp+hkey]
0x18008592f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180085934  mov     r9, [rbp+lpValue]; LPCWSTR
0x180085938  lea     rcx, [rbp+var_10]
0x18008593c  mov     rdx, [rbp+lpValueName]; lpValueName
0x180085940  neg     sil
0x180085943  sbb     rax, rax
0x180085946  and     rax, rcx
0x180085949  lea     rcx, [rbp+var_14]
0x18008594d  neg     dil
0x180085950  mov     [rsp+60h+phkResult], rax; lpData
0x180085955  sbb     r8, r8
0x180085958  and     r8, rcx; unsigned int
0x18008595b  mov     rcx, [rbp+lpSubKey]; lpSubKey
0x18008595f  call    NgcFirst__SetSwitchCountsHelper
0x180085964  mov     ebx, eax
0x180085966  test    eax, eax
0x180085968  jns     loc_1800858DA
0x18008596e  mov     r9d, eax
0x180085971  mov     edx, 2A5h
0x180085976  jmp     loc_18008589C
0x18008597b  mov     edx, 282h
0x180085980  jmp     loc_180085894
```
