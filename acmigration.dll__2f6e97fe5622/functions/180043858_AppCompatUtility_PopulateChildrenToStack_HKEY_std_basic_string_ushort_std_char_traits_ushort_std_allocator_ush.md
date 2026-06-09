# AppCompatUtility::PopulateChildrenToStack(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::stack<AppCompatUtility::_SubkeyNode,std::deque<AppCompatUtility::_SubkeyNode,std::allocator<AppCompatUtility::_SubkeyNode>>> *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,unsigned __int64)

- ea: `0x180043858`
- end: `0x180043d3f`
- name: `?PopulateChildrenToStack@AppCompatUtility@@YA_NPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$stack@U_SubkeyNode@AppCompatUtility@@V?$deque@U_SubkeyNode@AppCompatUtility@@V?$allocator@U_SubkeyNode@AppCompatUtility@@@std@@@std@@@4@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@_K@Z`
- size: `1255`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040854`

## callees

- `0x180001cf0`
- `0x180002120`
- `0x180002874`
- `0x18000b720`
- `0x18000bbbc`
- `0x18000c190`
- `0x18000dfd8`
- `0x18000e428`
- `0x18000e504`
- `0x1800118f4`
- `0x180011d40`
- `0x180016a20`
- `0x180043858`
- `0x1800543c0`
- `0x180054d1c`
- `0x180054d54`
- `0x180065150`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180043ced`
- `ADVAPI32!RegCloseKey` at `0x180043ced`
- `ADVAPI32!RegEnumKeyExW` at `0x180043931`
- `ADVAPI32!RegEnumKeyExW` at `0x180043b26`
- `ADVAPI32!RegEnumKeyExW` at `0x180043931`
- `ADVAPI32!RegEnumKeyExW` at `0x180043b26`
- `ADVAPI32!RegOpenKeyExW` at `0x180043ba7`
- `ADVAPI32!RegOpenKeyExW` at `0x180043ba7`

## string_xrefs

- `0x180043b5d`: `AppCompatUtility::PopulateChildrenToStack`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall AppCompatUtility::PopulateChildrenToStack(HKEY hKey, _QWORD *a2, _QWORD *a3, _QWORD *a4, __int64 a5)
{
  HKEY v8; // rdi
  __int64 *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r9
  LSTATUS v12; // eax
  DWORD v13; // ebx
  _QWORD *v14; // rcx
  unsigned __int64 v15; // rdx
  void **v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  _QWORD *v21; // r9
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 v25; // rbx
  char v26; // bl
  const WCHAR *v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdi
  __int64 v34; // rbx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v38; // [rsp+50h] [rbp-B0h]
  __int64 v39; // [rsp+58h] [rbp-A8h]
  HKEY v40; // [rsp+60h] [rbp-A0h]
  __int64 v41; // [rsp+68h] [rbp-98h]
  void *v42[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v43; // [rsp+80h] [rbp-80h]
  unsigned __int64 v44; // [rsp+88h] [rbp-78h]
  __int64 v45; // [rsp+90h] [rbp-70h]
  LPCWSTR lpSubKey[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v47; // [rsp+A8h] [rbp-58h]
  _OWORD Src[2]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v49[40]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR Name[264]; // [rsp+100h] [rbp+0h] BYREF

  v41 = -2;
  v38 = a4;
  v8 = hKey;
  v40 = hKey;
  v39 = a5;
  memset_0(Name, 0, 0x20Au);
  cchName = 261;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  v44 = 7;
  LOWORD(v42[0]) = 0;
  v9 = (__int64 *)(32 * a5 + *a4);
  if ( (unsigned __int64)v9[3] <= 7 )
    v10 = 32 * a5 + *a4;
  else
    v10 = *v9;
  if ( !(unsigned int)AslStringHasWildcard(v10) )
  {
    std::wstring::wstring(lpSubKey, v11);
    phkResult = 0;
    v27 = (const WCHAR *)lpSubKey;
    if ( *((_QWORD *)&v47 + 1) > 7u )
      v27 = lpSubKey[0];
    if ( !RegOpenKeyExW(v8, v27, 0, 0x20019u, &phkResult) )
    {
      std::wstring::operator=(v42, lpSubKey);
      v45 = a5;
      v30 = a2[2];
      if ( v30 )
      {
        if ( 0x7FFFFFFFFFFFFFFELL == v30 )
          std::_Xlen_string();
        if ( a2[3] > 7u )
          a2 = (_QWORD *)*a2;
        std::wstring::wstring(v49, v28, v29, a2);
        v31 = std::wstring::append(v49);
        Src[0] = *(_OWORD *)v31;
        Src[1] = *(_OWORD *)(v31 + 16);
        *(_QWORD *)(v31 + 16) = 0;
        *(_QWORD *)(v31 + 24) = 7;
        *(_WORD *)v31 = 0;
        std::wstring::operator=(v42, Src);
        std::wstring::~wstring(Src);
        std::wstring::~wstring(v49);
      }
      if ( a3[2] <= (unsigned __int64)(a3[4] + 1LL) )
        std::deque<AppCompatUtility::_SubkeyNode>::_Growmap(a3);
      v32 = a3[2] - 1LL;
      a3[3] &= v32;
      v33 = a3[3] + a3[4];
      if ( !*(_QWORD *)(a3[1] + 8 * (v32 & v33)) )
        *(_QWORD *)(a3[1] + 8 * (v32 & v33)) = operator new(0x28u);
      v34 = *(_QWORD *)(a3[1] + 8 * (v33 & (a3[2] - 1LL)));
      std::wstring::wstring(v34, v42);
      *(_QWORD *)(v34 + 32) = v45;
      ++a3[4];
    }
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    std::wstring::~wstring(lpSubKey);
    goto LABEL_46;
  }
  v12 = RegEnumKeyExW(v8, 0, Name, &cchName, 0, 0, 0, 0);
  v13 = 1;
  for ( LODWORD(phkResult) = 1; !v12; LODWORD(phkResult) = v13 )
  {
    v14 = (_QWORD *)(*v38 + 32 * a5);
    if ( v14[3] > 7u )
      v14 = (_QWORD *)*v14;
    if ( (unsigned int)AslStringPatternMatchExW(v14, Name) )
    {
      v15 = -1;
      do
        ++v15;
      while ( Name[v15] );
      if ( v15 > v44 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v42);
      }
      else
      {
        v16 = v42;
        if ( v44 > 7 )
          v16 = (void **)v42[0];
        v43 = v15;
        v17 = 2 * v15;
        memmove_0(v16, Name, 2 * v15);
        *(_WORD *)((char *)v16 + v17) = 0;
      }
      v45 = v39;
      v20 = a2[2];
      if ( v20 )
      {
        if ( 0x7FFFFFFFFFFFFFFELL == v20 )
          std::_Xlen_string();
        if ( a2[3] <= 7u )
          v21 = a2;
        else
          v21 = (_QWORD *)*a2;
        std::wstring::wstring(Src, v18, v19, v21);
        v22 = std::wstring::append(Src);
        *(_OWORD *)lpSubKey = *(_OWORD *)v22;
        v47 = *(_OWORD *)(v22 + 16);
        *(_QWORD *)(v22 + 16) = 0;
        *(_QWORD *)(v22 + 24) = 7;
        *(_WORD *)v22 = 0;
        std::wstring::operator=(v42, lpSubKey);
        std::wstring::~wstring(lpSubKey);
        std::wstring::~wstring(Src);
      }
      if ( a3[2] <= (unsigned __int64)(a3[4] + 1LL) )
        std::deque<AppCompatUtility::_SubkeyNode>::_Growmap(a3);
      v23 = a3[2] - 1LL;
      a3[3] &= v23;
      v24 = a3[3] + a3[4];
      if ( !*(_QWORD *)(a3[1] + 8 * (v23 & v24)) )
        *(_QWORD *)(a3[1] + 8 * (v23 & v24)) = operator new(0x28u);
      v25 = *(_QWORD *)(a3[1] + 8 * (v24 & (a3[2] - 1LL)));
      std::wstring::wstring(v25, v42);
      *(_QWORD *)(v25 + 32) = v45;
      ++a3[4];
      v13 = (unsigned int)phkResult;
      v8 = v40;
    }
    cchName = 261;
    v12 = RegEnumKeyExW(v8, v13++, Name, &cchName, 0, 0, 0, 0);
  }
  if ( v12 == 259 )
  {
LABEL_46:
    v26 = 1;
    goto LABEL_47;
  }
  v26 = 0;
  AslLogCallPrintf(1, "AppCompatUtility::PopulateChildrenToStack", 1833, "RegEnumKeyEx failed, %d", v12);
LABEL_47:
  std::wstring::~wstring(v42);
  return v26;
}

```

## disassembly

```asm
0x180043858  push    rbp
0x18004385a  push    rbx
0x18004385b  push    rsi
0x18004385c  push    rdi
0x18004385d  push    r12
0x18004385f  push    r13
0x180043861  push    r14
0x180043863  push    r15
0x180043865  lea     rbp, [rsp-228h]
0x18004386d  sub     rsp, 328h
0x180043874  mov     [rsp+360h+var_2F8], 0FFFFFFFFFFFFFFFEh
0x18004387d  mov     rax, cs:__security_cookie
0x180043884  xor     rax, rsp
0x180043887  mov     [rbp+260h+var_50], rax
0x18004388e  mov     r14, r9
0x180043891  mov     [rsp+360h+var_310], r9
0x180043896  mov     rsi, r8
0x180043899  mov     r15, rdx
0x18004389c  mov     rdi, rcx
0x18004389f  mov     [rsp+360h+var_300], rcx
0x1800438a4  mov     rbx, [rbp+260h+arg_20]
0x1800438ab  mov     [rsp+360h+var_308], rbx
0x1800438b0  xor     r12d, r12d
0x1800438b3  xor     edx, edx; Val
0x1800438b5  mov     r8d, 20Ah; Size
0x1800438bb  lea     rcx, [rbp+260h+Name]; void *
0x1800438bf  call    memset_0
0x1800438c4  mov     [rsp+360h+cchName], 105h
0x1800438cc  xorps   xmm0, xmm0
0x1800438cf  movups  xmmword ptr [rsp+360h+var_2F0], xmm0
0x1800438d4  mov     [rbp+260h+var_2E0], r12
0x1800438d8  mov     [rbp+260h+var_2D8], 7
0x1800438e0  mov     word ptr [rsp+360h+var_2F0], r12w
0x1800438e6  mov     r13, rbx
0x1800438e9  shl     r13, 5
0x1800438ed  mov     r9, [r14]
0x1800438f0  add     r9, r13
0x1800438f3  cmp     qword ptr [r9+18h], 7
0x1800438f8  jbe     short loc_1800438FF
0x1800438fa  mov     rcx, [r9]
0x1800438fd  jmp     short loc_180043902
0x1800438ff  mov     rcx, r9
0x180043902  call    AslStringHasWildcard
0x180043907  test    eax, eax
0x180043909  jz      loc_180043B71
0x18004390f  mov     [rsp+360h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180043914  mov     [rsp+360h+lpcchClass], r12; lpcchClass
0x180043919  mov     [rsp+360h+lpClass], r12; lpClass
0x18004391e  mov     [rsp+360h+lpReserved], r12; lpReserved
0x180043923  lea     r9, [rsp+360h+cchName]; lpcchName
0x180043928  lea     r8, [rbp+260h+Name]; lpName
0x18004392c  xor     edx, edx; dwIndex
0x18004392e  mov     rcx, rdi; hKey
0x180043931  call    cs:__imp_RegEnumKeyExW
0x180043937  mov     r14d, 1
0x18004393d  mov     ebx, r14d
0x180043940  mov     dword ptr [rsp+360h+phkResult], ebx
0x180043944  test    eax, eax
0x180043946  jnz     loc_180043B3E
0x18004394c  mov     r12, 7FFFFFFFFFFFFFFEh
0x180043956  mov     rax, [rsp+360h+var_310]
0x18004395b  mov     rax, [rax]
0x18004395e  lea     rcx, [rax+r13]
0x180043962  cmp     qword ptr [rax+r13+18h], 7
0x180043968  jbe     short loc_18004396D
0x18004396a  mov     rcx, [rcx]
0x18004396d  lea     rdx, [rbp+260h+Name]
0x180043971  call    AslStringPatternMatchExW
0x180043976  xor     ecx, ecx
0x180043978  test    eax, eax
0x18004397a  jz      loc_180043AFC
0x180043980  lea     rax, [rbp+260h+Name]
0x180043984  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180043988  inc     rdx
0x18004398b  cmp     [rax+rdx*2], cx
0x18004398f  jnz     short loc_180043988
0x180043991  cmp     rdx, [rbp+260h+var_2D8]
0x180043995  ja      short loc_1800439C6
0x180043997  lea     rdi, [rsp+360h+var_2F0]
0x18004399c  cmp     [rbp+260h+var_2D8], 7
0x1800439a1  cmova   rdi, [rsp+360h+var_2F0]
0x1800439a7  mov     [rbp+260h+var_2E0], rdx
0x1800439ab  lea     rbx, [rdx+rdx]
0x1800439af  mov     r8, rbx; Size
0x1800439b2  lea     rdx, [rbp+260h+Name]; Src
0x1800439b6  mov     rcx, rdi; void *
0x1800439b9  call    memmove_0
0x1800439be  xor     eax, eax
0x1800439c0  mov     [rbx+rdi], ax
0x1800439c4  jmp     short loc_1800439D4
0x1800439c6  lea     r9, [rbp+260h+Name]
0x1800439ca  lea     rcx, [rsp+360h+var_2F0]
0x1800439cf  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800439d4  mov     rax, [rsp+360h+var_308]
0x1800439d9  mov     [rbp+260h+var_2D0], rax
0x1800439dd  mov     rcx, [r15+10h]
0x1800439e1  test    rcx, rcx
0x1800439e4  jz      loc_180043A7B
0x1800439ea  mov     rax, r12
0x1800439ed  sub     rax, rcx
0x1800439f0  cmp     rax, r14
0x1800439f3  jb      loc_180043D39
0x1800439f9  cmp     qword ptr [r15+18h], 7
0x1800439fe  jbe     short loc_180043A05
0x180043a00  mov     r9, [r15]
0x180043a03  jmp     short loc_180043A08
0x180043a05  mov     r9, r15
0x180043a08  mov     [rsp+360h+lpcchClass], r14
0x180043a0d  lea     rax, asc_18006E074; "\\"
0x180043a14  mov     [rsp+360h+lpClass], rax
0x180043a19  mov     [rsp+360h+lpReserved], rcx
0x180043a1e  lea     rcx, [rbp+260h+Src]
0x180043a22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180043a27  nop
0x180043a28  lea     rdx, [rsp+360h+var_2F0]
0x180043a2d  lea     rcx, [rbp+260h+Src]; Src
0x180043a31  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180043a36  movups  xmm0, xmmword ptr [rax]
0x180043a39  movups  xmmword ptr [rbp+260h+lpSubKey], xmm0
0x180043a3d  movups  xmm1, xmmword ptr [rax+10h]
0x180043a41  movups  [rbp+260h+var_2B8], xmm1
0x180043a45  mov     qword ptr [rax+10h], 0
0x180043a4d  mov     qword ptr [rax+18h], 7
0x180043a55  xor     ecx, ecx
0x180043a57  mov     [rax], cx
0x180043a5a  lea     rdx, [rbp+260h+lpSubKey]
0x180043a5e  lea     rcx, [rsp+360h+var_2F0]
0x180043a63  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180043a68  lea     rcx, [rbp+260h+lpSubKey]; void *
0x180043a6c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043a71  nop
0x180043a72  lea     rcx, [rbp+260h+Src]; void *
0x180043a76  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043a7b  mov     rax, [rsi+20h]
0x180043a7f  add     rax, r14
0x180043a82  cmp     [rsi+10h], rax
0x180043a86  ja      short loc_180043A90
0x180043a88  mov     rcx, rsi
0x180043a8b  call    ?_Growmap@?$deque@U_SubkeyNode@AppCompatUtility@@V?$allocator@U_SubkeyNode@AppCompatUtility@@@std@@@std@@AEAAX_K@Z; std::deque<AppCompatUtility::_SubkeyNode>::_Growmap(unsigned __int64)
0x180043a90  mov     rdx, [rsi+10h]
0x180043a94  dec     rdx
0x180043a97  and     [rsi+18h], rdx
0x180043a9b  mov     rdi, [rsi+20h]
0x180043a9f  add     rdi, [rsi+18h]
0x180043aa3  mov     rbx, rdi
0x180043aa6  and     rbx, rdx
0x180043aa9  mov     rax, [rsi+8]
0x180043aad  cmp     qword ptr [rax+rbx*8], 0
0x180043ab2  jnz     short loc_180043AC6
0x180043ab4  mov     ecx, 28h ; '('; Size
0x180043ab9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043abe  mov     rcx, [rsi+8]
0x180043ac2  mov     [rcx+rbx*8], rax
0x180043ac6  mov     rcx, [rsi+10h]
0x180043aca  sub     rcx, r14
0x180043acd  and     rcx, rdi
0x180043ad0  mov     rax, [rsi+8]
0x180043ad4  mov     rbx, [rax+rcx*8]
0x180043ad8  lea     rdx, [rsp+360h+var_2F0]
0x180043add  mov     rcx, rbx
0x180043ae0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180043ae5  mov     rax, [rbp+260h+var_2D0]
0x180043ae9  mov     [rbx+20h], rax
0x180043aed  add     [rsi+20h], r14
0x180043af1  mov     ebx, dword ptr [rsp+360h+phkResult]
0x180043af5  mov     rdi, [rsp+360h+var_300]
0x180043afa  xor     ecx, ecx
0x180043afc  mov     [rsp+360h+cchName], 105h
0x180043b04  mov     [rsp+360h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x180043b09  mov     [rsp+360h+lpcchClass], rcx; lpcchClass
0x180043b0e  mov     [rsp+360h+lpClass], rcx; lpClass
0x180043b13  mov     [rsp+360h+lpReserved], rcx; lpReserved
0x180043b18  lea     r9, [rsp+360h+cchName]; lpcchName
0x180043b1d  lea     r8, [rbp+260h+Name]; lpName
0x180043b21  mov     edx, ebx; dwIndex
0x180043b23  mov     rcx, rdi; hKey
0x180043b26  call    cs:__imp_RegEnumKeyExW
0x180043b2c  add     ebx, r14d
0x180043b2f  mov     dword ptr [rsp+360h+phkResult], ebx
0x180043b33  test    eax, eax
0x180043b35  jz      loc_180043956
0x180043b3b  xor     r12d, r12d
0x180043b3e  cmp     eax, 103h
0x180043b43  jz      loc_180043D01
0x180043b49  mov     bl, r12b
0x180043b4c  mov     dword ptr [rsp+360h+lpReserved], eax
0x180043b50  lea     r9, aRegenumkeyexFa; "RegEnumKeyEx failed, %d"
0x180043b57  mov     r8d, 729h
0x180043b5d  lea     rdx, aAppcompatutili_16; "AppCompatUtility::PopulateChildrenToSta"...
0x180043b64  mov     ecx, r14d
0x180043b67  call    AslLogCallPrintf
0x180043b6c  jmp     loc_180043D04
0x180043b71  mov     rdx, r9
0x180043b74  lea     rcx, [rbp+260h+lpSubKey]
0x180043b78  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180043b7d  nop
0x180043b7e  mov     [rsp+360h+phkResult], r12
0x180043b83  lea     rdx, [rbp+260h+lpSubKey]
0x180043b87  cmp     qword ptr [rbp+260h+var_2B8+8], 7
0x180043b8c  cmova   rdx, [rbp+260h+lpSubKey]; lpSubKey
0x180043b91  lea     rax, [rsp+360h+phkResult]
0x180043b96  mov     [rsp+360h+lpReserved], rax; phkResult
0x180043b9b  mov     r9d, 20019h; samDesired
0x180043ba1  xor     r8d, r8d; ulOptions
0x180043ba4  mov     rcx, rdi; hKey
0x180043ba7  call    cs:__imp_RegOpenKeyExW
0x180043bad  mov     r14d, 1
0x180043bb3  test    eax, eax
0x180043bb5  jnz     loc_180043CE3
0x180043bbb  lea     rdx, [rbp+260h+lpSubKey]
0x180043bbf  lea     rcx, [rsp+360h+var_2F0]
0x180043bc4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180043bc9  mov     [rbp+260h+var_2D0], rbx
0x180043bcd  mov     rax, [r15+10h]
0x180043bd1  test    rax, rax
0x180043bd4  jz      loc_180043C6E
0x180043bda  mov     r12, 7FFFFFFFFFFFFFFEh
0x180043be4  sub     r12, rax
0x180043be7  cmp     r12, r14
0x180043bea  jb      loc_180043D33
0x180043bf0  cmp     qword ptr [r15+18h], 7
0x180043bf5  jbe     short loc_180043BFA
0x180043bf7  mov     r15, [r15]
0x180043bfa  mov     [rsp+360h+lpcchClass], r14
0x180043bff  lea     rcx, asc_18006E074; "\\"
0x180043c06  mov     [rsp+360h+lpClass], rcx
0x180043c0b  mov     [rsp+360h+lpReserved], rax
0x180043c10  mov     r9, r15
0x180043c13  lea     rcx, [rbp+260h+var_288]
0x180043c17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180043c1c  nop
0x180043c1d  lea     rdx, [rsp+360h+var_2F0]
0x180043c22  lea     rcx, [rbp+260h+var_288]; Src
0x180043c26  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180043c2b  movups  xmm0, xmmword ptr [rax]
0x180043c2e  movups  [rbp+260h+Src], xmm0
0x180043c32  movups  xmm1, xmmword ptr [rax+10h]
0x180043c36  movups  [rbp+260h+var_298], xmm1
0x180043c3a  xor     r12d, r12d
0x180043c3d  mov     [rax+10h], r12
0x180043c41  mov     qword ptr [rax+18h], 7
0x180043c49  mov     [rax], r12w
0x180043c4d  lea     rdx, [rbp+260h+Src]
0x180043c51  lea     rcx, [rsp+360h+var_2F0]
0x180043c56  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180043c5b  lea     rcx, [rbp+260h+Src]; void *
0x180043c5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043c64  nop
0x180043c65  lea     rcx, [rbp+260h+var_288]; void *
0x180043c69  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043c6e  mov     rax, [rsi+20h]
0x180043c72  add     rax, r14
0x180043c75  cmp     [rsi+10h], rax
0x180043c79  ja      short loc_180043C83
0x180043c7b  mov     rcx, rsi
0x180043c7e  call    ?_Growmap@?$deque@U_SubkeyNode@AppCompatUtility@@V?$allocator@U_SubkeyNode@AppCompatUtility@@@std@@@std@@AEAAX_K@Z; std::deque<AppCompatUtility::_SubkeyNode>::_Growmap(unsigned __int64)
0x180043c83  mov     rdx, [rsi+10h]
0x180043c87  dec     rdx
0x180043c8a  and     [rsi+18h], rdx
0x180043c8e  mov     rdi, [rsi+20h]
0x180043c92  add     rdi, [rsi+18h]
0x180043c96  mov     rbx, rdi
0x180043c99  and     rbx, rdx
0x180043c9c  mov     rax, [rsi+8]
0x180043ca0  cmp     [rax+rbx*8], r12
0x180043ca4  jnz     short loc_180043CB8
0x180043ca6  mov     ecx, 28h ; '('; Size
0x180043cab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043cb0  mov     rcx, [rsi+8]
0x180043cb4  mov     [rcx+rbx*8], rax
0x180043cb8  mov     rcx, [rsi+10h]
0x180043cbc  sub     rcx, r14
0x180043cbf  and     rcx, rdi
0x180043cc2  mov     rax, [rsi+8]
0x180043cc6  mov     rbx, [rax+rcx*8]
0x180043cca  lea     rdx, [rsp+360h+var_2F0]
0x180043ccf  mov     rcx, rbx
0x180043cd2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180043cd7  mov     rax, [rbp+260h+var_2D0]
0x180043cdb  mov     [rbx+20h], rax
0x180043cdf  add     [rsi+20h], r14
0x180043ce3  mov     rcx, [rsp+360h+phkResult]; hKey
0x180043ce8  test    rcx, rcx
0x180043ceb  jz      short loc_180043CF8
0x180043ced  call    cs:__imp_RegCloseKey
0x180043cf3  mov     [rsp+360h+phkResult], r12
0x180043cf8  lea     rcx, [rbp+260h+lpSubKey]; void *
0x180043cfc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043d01  mov     bl, r14b
0x180043d04  lea     rcx, [rsp+360h+var_2F0]; void *
0x180043d09  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043d0e  mov     al, bl
0x180043d10  mov     rcx, [rbp+260h+var_50]
0x180043d17  xor     rcx, rsp; StackCookie
0x180043d1a  call    __security_check_cookie
0x180043d1f  add     rsp, 328h
0x180043d26  pop     r15
0x180043d28  pop     r14
0x180043d2a  pop     r13
0x180043d2c  pop     r12
  ... truncated ...
```
