# GetLockAppAndAppType(ushort const *,bool,HKEY__ *,bool,LockAppType *,ushort * *)

- ea: `0x180033480`
- end: `0x180033aa7`
- name: `?GetLockAppAndAppType@@YAJPEBG_NPEAUHKEY__@@1PEAW4LockAppType@@PEAPEAG@Z`
- size: `1575`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char, HKEY, char, enum LockAppType *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005b5a0`
- `0x18008d6bc`

## callees

- `0x180008094`
- `0x18002bc20`
- `0x1800328e0`
- `0x180033480`
- `0x180033ab0`
- `0x180033d20`
- `0x180033e90`
- `0x1800478e4`
- `0x18005d488`
- `0x18006c000`
- `0x18009b79c`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180033583`
- `KERNEL32!CompareStringOrdinal` at `0x180033640`
- `KERNEL32!CompareStringOrdinal` at `0x1800339df`
- `KERNEL32!CompareStringOrdinal` at `0x180033583`
- `KERNEL32!CompareStringOrdinal` at `0x180033640`
- `KERNEL32!CompareStringOrdinal` at `0x1800339df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800336eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003392e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800336eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003392e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800335ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003378f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800335ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003378f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800336b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800336b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003385c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003398e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003385c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003398e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003353a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003353a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003387c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003395b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800339a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003387c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003395b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800339a0`

## string_xrefs

- `0x180033909`: `Microsoft.Windows.AssignedAccessLockApp_cw5n1h2txyewy!App`
- `0x1800339d3`: `Microsoft.Windows.PPIWelcome_cw5n1h2txyewy!App`

## pseudocode

```c
__int64 __fastcall GetLockAppAndAppType(
        const unsigned __int16 *a1,
        char a2,
        HKEY a3,
        char a4,
        enum LockAppType *a5,
        unsigned __int16 **a6)
{
  enum LockAppType *v6; // rsi
  int v7; // r14d
  unsigned __int16 **v8; // rdi
  unsigned __int64 v11; // rsi
  int v12; // edi
  WCHAR *v13; // r13
  __int64 v14; // rbx
  int v15; // r14d
  unsigned int v16; // edi
  const WCHAR *v17; // r15
  unsigned __int64 v19; // rdi
  const WCHAR *v20; // rax
  const WCHAR *v21; // rax
  unsigned int v22; // edi
  __int64 v23; // rcx
  const WCHAR *v24; // rdx
  WCHAR *v25; // r9
  WCHAR *v26; // rcx
  WCHAR *v27; // rcx
  int v28; // eax
  const WCHAR *v29; // rdx
  WCHAR *v30; // r8
  __int64 v31; // rcx
  __int64 v32; // r9
  WCHAR *v33; // rcx
  LSTATUS ValueW; // eax
  int v35; // eax
  WCHAR *pvData; // rax
  int v37; // eax
  unsigned int v38; // ebx
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR v41; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h]
  __int64 v43; // [rsp+58h] [rbp-A8h]
  HKEY hkey[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 **v45; // [rsp+70h] [rbp-90h]
  enum LockAppType *v46; // [rsp+78h] [rbp-88h]
  PCWSTR sourceString; // [rsp+80h] [rbp-80h]
  _BYTE Src[256]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v6 = a5;
  v7 = 0;
  v8 = a6;
  sourceString = a1;
  v46 = a5;
  *(_DWORD *)a5 = 0;
  v45 = a6;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( a6 )
    *a6 = 0;
  if ( !a2 )
  {
    v42 = -1;
    v11 = -1;
    v43 = -1;
    hkey[0] = a3;
    v12 = RegOpenKeyExW(a3, L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen", 0, 1u, hkey);
    if ( !v12 )
    {
      pcbData = 256;
      ValueW = RegGetValueW(hkey[0], 0, L"LockAppAumId", 2u, 0, Src, &pcbData);
      v12 = ValueW;
      if ( !ValueW || ValueW == 234 )
      {
        pvData = (WCHAR *)CoTaskMemAlloc(pcbData);
        v41 = pvData;
        v13 = pvData;
        if ( pvData )
        {
          if ( !v12 )
          {
            memcpy_0(pvData, Src, pcbData);
            RegCloseKey(hkey[0]);
            goto LABEL_7;
          }
          if ( !RegGetValueW(hkey[0], 0, L"LockAppAumId", 2u, 0, pvData, &pcbData) )
          {
            v12 = 0;
            RegCloseKey(hkey[0]);
            goto LABEL_7;
          }
          v12 = 1003;
          CoTaskMemFree(v13);
        }
        else
        {
          v12 = 14;
        }
      }
      RegCloseKey(hkey[0]);
    }
    v41 = 0;
    v13 = 0;
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
LABEL_7:
    v14 = 57;
    if ( v12 < 0 )
    {
      v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
              &v41,
              56);
      v22 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x64,
          (unsigned int)"shell\\lib\\lockapphostdata\\lockapptype.cpp",
          (const char *)(unsigned int)v28,
          phkResult);
        v27 = (WCHAR *)v41;
        if ( !v41 )
          return v22;
        goto LABEL_42;
      }
      v13 = (WCHAR *)v41;
      v29 = L"Microsoft.LockApp_cw5n1h2txyewy!WindowsDefaultLockScreen";
      v30 = (WCHAR *)v41;
      v31 = 56;
      v32 = 57;
      do
      {
        if ( !v31 )
          break;
        if ( !*v29 )
          break;
        *v30++ = *v29++;
        --v31;
        --v32;
      }
      while ( v32 );
      v11 = v43;
      v33 = v30 - 1;
      v42 = 56;
      if ( v32 )
        v33 = v30;
      *v33 = 0;
    }
    else if ( CompareStringOrdinal(v13, -1, L"Microsoft.LockApp_cw5n1h2txyewy!WindowsDefaultLockScreen", -1, 1) != 2 )
    {
      LOBYTE(v7) = CompareStringOrdinal(v13, -1, L"Microsoft.Windows.PPIWelcome_cw5n1h2txyewy!App", -1, 1) == 2;
      v15 = v7 + 3;
      goto LABEL_10;
    }
    v15 = 1;
LABEL_10:
    v16 = 0;
    hkey[0] = (HKEY)L"Microsoft.WindowsDefaultLockScreen_8wekyb3d8bbwe!LockApp";
    hkey[1] = (HKEY)L"Microsoft.WindowsDefaultLockScreen_cw5n1h2txyewy!LockApp";
    while ( 1 )
    {
      if ( v16 >= 2 )
        goto LABEL_12;
      if ( CompareStringOrdinal((LPCWCH)hkey[v16], -1, v13, -1, 1) == 2 )
        break;
      ++v16;
    }
    if ( a4 )
    {
      v35 = SHRegSetString(
              a3,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
              L"LockAppAumId",
              L"Microsoft.LockApp_cw5n1h2txyewy!WindowsDefaultLockScreen");
      if ( v35 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x79,
          (unsigned int)"shell\\lib\\lockapphostdata\\lockapptype.cpp",
          (const char *)(unsigned int)v35,
          phkResult);
    }
    if ( v11 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&v41);
      v13 = (WCHAR *)v41;
      if ( v41 )
        v11 = v42 + 1;
      else
        v11 = 0;
      v43 = v11;
    }
    if ( v11 )
    {
      if ( v11 >= 0x39 )
        goto LABEL_32;
      hkey[0] = 0;
      v19 = 2 * v11;
      if ( is_mul_ok(v11, 2u) )
      {
        if ( v19 < 0x39 )
          v19 = 57;
        v20 = (const WCHAR *)CoTaskMemRealloc(v13, 2 * v19);
        if ( v20 )
        {
          v43 = v19;
          v13 = (WCHAR *)v20;
          v41 = v20;
LABEL_32:
          v23 = 56;
          v24 = L"Microsoft.LockApp_cw5n1h2txyewy!WindowsDefaultLockScreen";
          v25 = v13;
          do
          {
            if ( !v23 )
              break;
            if ( !*v24 )
              break;
            *v25++ = *v24++;
            --v23;
            --v14;
          }
          while ( v14 );
          v42 = 56;
          v26 = v25 - 1;
          v15 = 1;
          if ( v14 )
            v26 = v25;
          *v26 = 0;
LABEL_12:
          v6 = v46;
          v8 = v45;
          goto LABEL_13;
        }
        v22 = -2147024882;
        goto LABEL_40;
      }
    }
    else
    {
      hkey[0] = 0;
      if ( is_mul_ok(0x39u, 2u) )
      {
        v21 = (const WCHAR *)CoTaskMemAlloc(0x72u);
        if ( v21 )
        {
          v22 = 0;
          v43 = 57;
          v41 = v21;
          *v21 = 0;
          v13 = (WCHAR *)v21;
        }
        else
        {
          v22 = -2147024882;
        }
        if ( (v22 & 0x80000000) == 0 )
          goto LABEL_32;
        goto LABEL_40;
      }
    }
    v22 = -2147024362;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"shell\\lib\\lockapphostdata\\lockapptype.cpp",
      (const char *)v22,
      phkResult);
    if ( !v13 )
      return v22;
    v27 = v13;
LABEL_42:
    CoTaskMemFree(v27);
    return v22;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
    (__int64)&v41,
    L"Microsoft.Windows.AssignedAccessLockApp_cw5n1h2txyewy!App",
    0xFFFFFFFFFFFFFFFFuLL);
  v13 = (WCHAR *)v41;
  v15 = 2;
LABEL_13:
  v17 = sourceString;
  if ( (int)ValidateLockAppHasExtension(sourceString, v13) < 0 )
  {
    v37 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            (__int64)&v41,
            L"Microsoft.LockApp_cw5n1h2txyewy!WindowsDefaultLockScreen",
            0xFFFFFFFFFFFFFFFFuLL);
    v38 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"shell\\lib\\lockapphostdata\\lockapptype.cpp",
        (const char *)(unsigned int)v37,
        phkResult);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v41);
      return v38;
    }
    v13 = (WCHAR *)v41;
    ValidateLockAppHasExtension(v17, v41);
    v15 = 1;
  }
  *(_DWORD *)v6 = v15;
  if ( v8 )
  {
    *v8 = v13;
  }
  else if ( v13 )
  {
    CoTaskMemFree(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x180033480  push    rbp
0x180033482  push    rsi
0x180033483  push    rdi
0x180033484  push    r12
0x180033486  push    r14
0x180033488  push    r15
0x18003348a  lea     rbp, [rsp-0A8h]
0x180033492  sub     rsp, 1A8h
0x180033499  mov     rax, cs:__security_cookie
0x1800334a0  xor     rax, rsp
0x1800334a3  mov     [rbp+0D0h+var_40], rax
0x1800334aa  mov     rsi, [rbp+0D0h+arg_20]
0x1800334b1  xor     r14d, r14d
0x1800334b4  mov     rdi, [rbp+0D0h+arg_28]
0x1800334bb  movzx   r12d, r9b
0x1800334bf  mov     [rbp+0D0h+sourceString], rcx
0x1800334c3  mov     r15, r8
0x1800334c6  mov     [rsp+1D0h+var_158], rsi
0x1800334cb  mov     [rsi], r14d
0x1800334ce  mov     [rsp+1D0h+var_160], rdi
0x1800334d3  mov     [rsp+1D0h+var_188], r14
0x1800334d8  mov     [rsp+1D0h+var_180], r14
0x1800334dd  mov     [rsp+1D0h+var_178], r14
0x1800334e2  test    rdi, rdi
0x1800334e5  jnz     loc_1800338FA
0x1800334eb  mov     [rsp+1D0h+arg_8], rbx
0x1800334f3  mov     [rsp+1D0h+var_30], r13
0x1800334fb  test    dl, dl
0x1800334fd  jnz     loc_180033902
0x180033503  lea     rax, [rsp+1D0h+hkey]
0x180033508  mov     [rsp+1D0h+var_180], 0FFFFFFFFFFFFFFFFh
0x180033511  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180033518  mov     [rsp+1D0h+phkResult], rax; int
0x18003351d  mov     r9d, 1; samDesired
0x180033523  mov     [rsp+1D0h+var_178], rsi
0x180033528  xor     r8d, r8d; ulOptions
0x18003352b  mov     [rsp+1D0h+hkey], r15
0x180033530  lea     rdx, aSoftwareMicros_27; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180033537  mov     rcx, r15; hKey
0x18003353a  call    cs:__imp_RegOpenKeyExW
0x180033540  mov     edi, eax
0x180033542  test    eax, eax
0x180033544  jz      loc_180033828
0x18003354a  mov     [rsp+1D0h+var_188], r14
0x18003354f  mov     r13, r14
0x180033552  test    edi, edi
0x180033554  jle     short loc_18003355F
0x180033556  movzx   edi, di
0x180033559  or      edi, 80070000h
0x18003355f  mov     ebx, 39h ; '9'
0x180033564  test    edi, edi
0x180033566  js      loc_18003379C
0x18003356c  mov     r9d, esi; cchCount2
0x18003356f  mov     dword ptr [rsp+1D0h+phkResult], 1; int
0x180033577  lea     r8, aMicrosoftLocka; "Microsoft.LockApp_cw5n1h2txyewy!Windows"...
0x18003357e  mov     edx, esi; cchCount1
0x180033580  mov     rcx, r13; lpString1
0x180033583  call    cs:__imp_CompareStringOrdinal
0x180033589  cmp     eax, 2
0x18003358c  jnz     loc_1800339C8
0x180033592  mov     r14d, 1
0x180033598  lea     rax, aMicrosoftWindo_3; "Microsoft.WindowsDefaultLockScreen_8wek"...
0x18003359f  xor     edi, edi
0x1800335a1  mov     [rsp+1D0h+hkey], rax
0x1800335a6  lea     rax, aMicrosoftWindo; "Microsoft.WindowsDefaultLockScreen_cw5n"...
0x1800335ad  mov     [rsp+1D0h+var_168], rax
0x1800335b2  cmp     edi, 2
0x1800335b5  jb      short loc_180033624
0x1800335b7  mov     rsi, [rsp+1D0h+var_158]
0x1800335bc  mov     rdi, [rsp+1D0h+var_160]
0x1800335c1  mov     r15, [rbp+0D0h+sourceString]
0x1800335c5  mov     rdx, r13; PCWSTR
0x1800335c8  mov     rcx, r15; sourceString
0x1800335cb  call    ?ValidateLockAppHasExtension@@YAJPEBG0@Z; ValidateLockAppHasExtension(ushort const *,ushort const *)
0x1800335d0  test    eax, eax
0x1800335d2  js      loc_180033A3A
0x1800335d8  mov     [rsi], r14d
0x1800335db  test    rdi, rdi
0x1800335de  jnz     loc_180033A9F
0x1800335e4  test    r13, r13
0x1800335e7  jz      short loc_1800335F2
0x1800335e9  mov     rcx, r13; pv
0x1800335ec  call    cs:__imp_CoTaskMemFree
0x1800335f2  xor     eax, eax
0x1800335f4  mov     r13, [rsp+1D0h+var_30]
0x1800335fc  mov     rbx, [rsp+1D0h+arg_8]
0x180033604  mov     rcx, [rbp+0D0h+var_40]
0x18003360b  xor     rcx, rsp; StackCookie
0x18003360e  call    __security_check_cookie
0x180033613  add     rsp, 1A8h
0x18003361a  pop     r15
0x18003361c  pop     r14
0x18003361e  pop     r12
0x180033620  pop     rdi
0x180033621  pop     rsi
0x180033622  pop     rbp
0x180033623  retn
0x180033624  mov     r9d, 0FFFFFFFFh; cchCount2
0x18003362a  movsxd  rcx, edi
0x18003362d  mov     r8, r13; lpString2
0x180033630  mov     dword ptr [rsp+1D0h+phkResult], 1; int
0x180033638  mov     edx, r9d; cchCount1
0x18003363b  mov     rcx, [rsp+rcx*8+1D0h+hkey]; lpString1
0x180033640  call    cs:__imp_CompareStringOrdinal
0x180033646  cmp     eax, 2
0x180033649  jnz     loc_1800339F5
0x18003364f  test    r12b, r12b
0x180033652  jnz     loc_1800338B5
0x180033658  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18003365c  jz      loc_1800339FC
0x180033662  test    rsi, rsi
0x180033665  jz      short loc_1800336CE
0x180033667  cmp     rsi, rbx
0x18003366a  jnb     loc_180033712
0x180033670  mov     eax, 2
0x180033675  mov     [rsp+1D0h+hkey], 0
0x18003367e  mul     rsi
0x180033681  mov     rdi, rax
0x180033684  test    rdx, rdx
0x180033687  jnz     loc_180033767
0x18003368d  mov     rcx, rax
0x180033690  sub     rcx, rsi
0x180033693  cmp     rcx, 800h
0x18003369a  ja      loc_180033A26
0x1800336a0  cmp     rdi, rbx
0x1800336a3  jb      loc_180033A32
0x1800336a9  lea     rdx, [rdi+rdi]; cb
0x1800336ad  mov     rcx, r13; pv
0x1800336b0  call    cs:__imp_CoTaskMemRealloc
0x1800336b6  test    rax, rax
0x1800336b9  jz      loc_18003381E
0x1800336bf  mov     [rsp+1D0h+var_178], rdi
0x1800336c4  mov     r13, rax
0x1800336c7  mov     [rsp+1D0h+var_188], rax
0x1800336cc  jmp     short loc_180033712
0x1800336ce  mov     eax, 2
0x1800336d3  mov     [rsp+1D0h+hkey], 0
0x1800336dc  mul     rbx
0x1800336df  test    rdx, rdx
0x1800336e2  jnz     loc_180033767
0x1800336e8  mov     rcx, rax; cb
0x1800336eb  call    cs:__imp_CoTaskMemAlloc
0x1800336f1  test    rax, rax
0x1800336f4  jz      loc_180033814
0x1800336fa  xor     edi, edi
0x1800336fc  mov     [rsp+1D0h+var_178], rbx
0x180033701  xor     ecx, ecx
0x180033703  mov     [rsp+1D0h+var_188], rax
0x180033708  mov     [rax], cx
0x18003370b  mov     r13, rax
0x18003370e  test    edi, edi
0x180033710  js      short loc_18003376C
0x180033712  mov     ecx, 38h ; '8'
0x180033717  lea     rdx, aMicrosoftLocka; "Microsoft.LockApp_cw5n1h2txyewy!Windows"...
0x18003371e  mov     r9, r13
0x180033721  test    rcx, rcx
0x180033724  jz      short loc_180033743
0x180033726  movzx   eax, word ptr [rdx]
0x180033729  test    ax, ax
0x18003372c  jz      short loc_180033743
0x18003372e  mov     [r9], ax
0x180033732  add     rdx, 2
0x180033736  add     r9, 2
0x18003373a  dec     rcx
0x18003373d  sub     rbx, 1
0x180033741  jnz     short loc_180033721
0x180033743  test    rbx, rbx
0x180033746  mov     [rsp+1D0h+var_180], 38h ; '8'
0x18003374f  lea     rcx, [r9-2]
0x180033753  mov     r14d, 1
0x180033759  cmovnz  rcx, r9
0x18003375d  xor     eax, eax
0x18003375f  mov     [rcx], ax
0x180033762  jmp     loc_1800335B7
0x180033767  mov     edi, 80070216h
0x18003376c  mov     rcx, [rbp+0D8h]; this
0x180033773  lea     r8, aShellLibLockap; "shell\\lib\\lockapphostdata\\lockapptyp"...
0x18003377a  mov     r9d, edi; char *
0x18003377d  mov     edx, 7Ch ; '|'; void *
0x180033782  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033787  test    r13, r13
0x18003378a  jz      short loc_180033795
0x18003378c  mov     rcx, r13; pv
0x18003378f  call    cs:__imp_CoTaskMemFree
0x180033795  mov     eax, edi
0x180033797  jmp     loc_1800335F4
0x18003379c  mov     edx, 38h ; '8'
0x1800337a1  lea     rcx, [rsp+1D0h+var_188]
0x1800337a6  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800337ab  mov     edi, eax
0x1800337ad  test    eax, eax
0x1800337af  js      loc_180033887
0x1800337b5  mov     r13, [rsp+1D0h+var_188]
0x1800337ba  lea     rdx, aMicrosoftLocka; "Microsoft.LockApp_cw5n1h2txyewy!Windows"...
0x1800337c1  mov     r8, r13
0x1800337c4  mov     ecx, 38h ; '8'
0x1800337c9  mov     r9, rbx
0x1800337cc  nop     dword ptr [rax+00h]
0x1800337d0  test    rcx, rcx
0x1800337d3  jz      short loc_1800337F2
0x1800337d5  movzx   eax, word ptr [rdx]
0x1800337d8  test    ax, ax
0x1800337db  jz      short loc_1800337F2
0x1800337dd  mov     [r8], ax
0x1800337e1  add     rdx, 2
0x1800337e5  add     r8, 2
0x1800337e9  dec     rcx
0x1800337ec  sub     r9, 1
0x1800337f0  jnz     short loc_1800337D0
0x1800337f2  mov     rsi, [rsp+1D0h+var_178]
0x1800337f7  lea     rcx, [r8-2]
0x1800337fb  test    r9, r9
0x1800337fe  mov     [rsp+1D0h+var_180], 38h ; '8'
0x180033807  cmovnz  rcx, r8
0x18003380b  mov     [rcx], r14w
0x18003380f  jmp     loc_180033592
0x180033814  mov     edi, 8007000Eh
0x180033819  jmp     loc_18003370E
0x18003381e  mov     edi, 8007000Eh
0x180033823  jmp     loc_18003376C
0x180033828  mov     rcx, [rsp+1D0h+hkey]; hkey
0x18003382d  lea     rax, [rsp+1D0h+var_190]
0x180033832  mov     [rsp+1D0h+pcbData], rax; pcbData
0x180033837  lea     r8, aLockappaumid; "LockAppAumId"
0x18003383e  lea     rax, [rbp+0D0h+Src]
0x180033842  mov     [rsp+1D0h+var_190], 100h
0x18003384a  mov     [rsp+1D0h+pvData], rax; pvData
0x18003384f  mov     r9d, 2; dwFlags
0x180033855  xor     edx, edx; lpSubKey
0x180033857  mov     [rsp+1D0h+phkResult], r14; pdwType
0x18003385c  call    cs:__imp_RegGetValueW
0x180033862  mov     edi, eax
0x180033864  test    eax, eax
0x180033866  jz      loc_18003392A
0x18003386c  cmp     eax, 0EAh
0x180033871  jz      loc_18003392A
0x180033877  mov     rcx, [rsp+1D0h+hkey]; hKey
0x18003387c  call    cs:__imp_RegCloseKey
0x180033882  jmp     loc_18003354A
0x180033887  mov     rcx, [rbp+0D8h]; this
0x18003388e  lea     r8, aShellLibLockap; "shell\\lib\\lockapphostdata\\lockapptyp"...
0x180033895  mov     r9d, edi; char *
0x180033898  mov     edx, 64h ; 'd'; void *
0x18003389d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800338a2  mov     rcx, [rsp+1D0h+var_188]
0x1800338a7  test    rcx, rcx
0x1800338aa  jnz     loc_18003378F
0x1800338b0  jmp     loc_180033795
0x1800338b5  lea     r9, aMicrosoftLocka; "Microsoft.LockApp_cw5n1h2txyewy!Windows"...
0x1800338bc  mov     rcx, r15; hKey
0x1800338bf  lea     r8, aLockappaumid; "LockAppAumId"
0x1800338c6  lea     rdx, aSoftwareMicros_27; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800338cd  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800338d2  test    eax, eax
0x1800338d4  jns     loc_180033658
0x1800338da  mov     rcx, [rbp+0D8h]; this
0x1800338e1  lea     r8, aShellLibLockap; "shell\\lib\\lockapphostdata\\lockapptyp"...
0x1800338e8  mov     r9d, eax; char *
0x1800338eb  mov     edx, 79h ; 'y'; void *
0x1800338f0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800338f5  jmp     loc_180033658
0x1800338fa  mov     [rdi], r14
0x1800338fd  jmp     loc_1800334EB
0x180033902  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180033909  lea     rdx, aMicrosoftWindo_2; "Microsoft.Windows.AssignedAccessLockApp"...
0x180033910  lea     rcx, [rsp+1D0h+var_188]
0x180033915  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003391a  mov     r13, [rsp+1D0h+var_188]
0x18003391f  mov     r14d, 2
0x180033925  jmp     loc_1800335C1
0x18003392a  mov     ecx, [rsp+1D0h+var_190]; cb
0x18003392e  call    cs:__imp_CoTaskMemAlloc
0x180033934  mov     [rsp+1D0h+var_188], rax
0x180033939  mov     r13, rax
0x18003393c  test    rax, rax
0x18003393f  jz      short loc_1800339BE
0x180033941  test    edi, edi
0x180033943  jnz     short loc_180033966
0x180033945  mov     r8d, [rsp+1D0h+var_190]; Size
0x18003394a  lea     rdx, [rbp+0D0h+Src]; Src
0x18003394e  mov     rcx, rax; void *
0x180033951  call    memcpy_0
0x180033956  mov     rcx, [rsp+1D0h+hkey]; hKey
0x18003395b  call    cs:__imp_RegCloseKey
0x180033961  jmp     loc_18003355F
0x180033966  mov     rcx, [rsp+1D0h+hkey]; hkey
0x18003396b  lea     rax, [rsp+1D0h+var_190]
0x180033970  mov     [rsp+1D0h+pcbData], rax; pcbData
0x180033975  lea     r8, aLockappaumid; "LockAppAumId"
0x18003397c  mov     [rsp+1D0h+pvData], r13; pvData
0x180033981  mov     r9d, 2; dwFlags
0x180033987  xor     edx, edx; lpSubKey
0x180033989  mov     [rsp+1D0h+phkResult], r14; pdwType
0x18003398e  call    cs:__imp_RegGetValueW
0x180033994  test    eax, eax
0x180033996  jnz     short loc_1800339AB
0x180033998  mov     rcx, [rsp+1D0h+hkey]; hKey
0x18003399d  mov     edi, r14d
0x1800339a0  call    cs:__imp_RegCloseKey
0x1800339a6  jmp     loc_18003355F
  ... truncated ...
```
