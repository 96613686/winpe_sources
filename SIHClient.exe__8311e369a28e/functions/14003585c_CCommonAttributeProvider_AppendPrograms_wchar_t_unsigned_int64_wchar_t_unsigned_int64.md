# CCommonAttributeProvider::AppendPrograms(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)

- ea: `0x14003585c`
- end: `0x140035bda`
- name: `?AppendPrograms@CCommonAttributeProvider@@AEAAJPEA_W_KPEAPEA_WPEA_K@Z`
- size: `894`
- prototype: `__int64 __fastcall(CCommonAttributeProvider *this, wchar_t *, unsigned __int64, wchar_t **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140034ccc`

## callees

- `0x1400154b4`
- `0x140018394`
- `0x1400326d0`
- `0x140033160`
- `0x14003585c`
- `0x140045a68`
- `0x140045a8c`
- `0x140045dc0`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035ba8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035ba8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400358f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400358f7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14003594e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14003594e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400359de`
- `OLEAUT32!__imp_SysFreeString` at `0x140035a58`
- `OLEAUT32!__imp_SysFreeString` at `0x140035a72`
- `OLEAUT32!__imp_SysFreeString` at `0x140035b8b`
- `OLEAUT32!__imp_SysFreeString` at `0x1400359de`
- `OLEAUT32!__imp_SysFreeString` at `0x140035a58`
- `OLEAUT32!__imp_SysFreeString` at `0x140035a72`
- `OLEAUT32!__imp_SysFreeString` at `0x140035b8b`
- `OLEAUT32!__imp_SysStringLen` at `0x140035afb`
- `OLEAUT32!__imp_SysStringLen` at `0x140035afb`

## string_xrefs

- `0x140035b6d`: `CCommonAttributeProvider::AppendPrograms`

## pseudocode

```c
__int64 __fastcall CCommonAttributeProvider::AppendPrograms(
        CCommonAttributeProvider *this,
        wchar_t *a2,
        unsigned __int64 a3,
        wchar_t **a4,
        unsigned __int64 *a5)
{
  unsigned __int64 v6; // r13
  wchar_t *v7; // r12
  signed int v8; // esi
  size_t v9; // r14
  unsigned __int64 v10; // r15
  __int64 v11; // rdx
  __int64 v12; // r8
  wchar_t **v13; // r9
  const WCHAR *RegKeyPath; // rax
  DWORD v15; // edx
  LSTATUS v16; // ecx
  unsigned __int64 i; // rbx
  wint_t v18; // cx
  __int64 v19; // r8
  OLECHAR *v20; // rcx
  unsigned int v21; // ebx
  __int64 v22; // rax
  OLECHAR *v23; // rdi
  UINT v24; // eax
  size_t j; // rbx
  OLECHAR *v26; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  WCHAR *lpcchClass; // [rsp+30h] [rbp-D0h]
  DWORD dwIndex; // [rsp+40h] [rbp-C0h]
  OLECHAR *v31; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v32; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _QWORD Base[16]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[256]; // [rsp+F0h] [rbp-10h] BYREF

  v6 = a3;
  v7 = a2;
  v32 = a2;
  v34 = a3;
  v8 = 0;
  hKey = 0;
  v9 = 0;
  v10 = 0;
  dwIndex = 0;
  memset(Base, 0, sizeof(Base));
  *a4 = v7;
  *a5 = v6;
  RegKeyPath = (const WCHAR *)GetRegKeyPath(18, v11, v12, v13);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, RegKeyPath, 0, 0x20019u, &hKey) )
    goto LABEL_37;
  while ( 1 )
  {
    memset(Name, 0, sizeof(Name));
    cchName = 256;
    v15 = dwIndex++;
    v16 = RegEnumKeyExW(hKey, v15, Name, &cchName, 0, 0, 0, 0);
    if ( ((v16 - 2) & 0xFFFFFEFE) == 0 && v16 != 258 )
      break;
    if ( v16 )
    {
      v8 = (unsigned __int16)v16 | 0x80070000;
      if ( v16 <= 0 )
        v8 = v16;
    }
    else
    {
      if ( cchName <= 0x18 )
      {
        for ( i = 0; i < 0x100; ++i )
        {
          v18 = Name[i];
          if ( !v18 )
            break;
          if ( !o_iswalnum_0(v18) )
          {
            ++v10;
            lpcchClass = Name;
            WUTrace(0, 0, 4, 3, 0, L"Program name invalid, invalid char: %ws");
            goto LABEL_20;
          }
        }
        SysFreeString(0);
        v31 = 0;
        v19 = -1;
        do
          ++v19;
        while ( Name[v19] );
        v8 = CSusBSTR::Append((CSusBSTR *)&v31, Name, v19);
        if ( v8 < 0 )
        {
          ++v10;
          v20 = v31;
          goto LABEL_21;
        }
        Base[v9++] = v31;
        goto LABEL_20;
      }
      lpcchClass = Name;
      WUTrace(0, 0, 4, 3, 0, L"Program name invalid, exceeded max length: %ws");
    }
    ++v10;
LABEL_20:
    v20 = 0;
LABEL_21:
    SysFreeString(v20);
    if ( v9 >= 0x10 || v10 >= 0x40 )
      goto LABEL_25;
  }
  SysFreeString(0);
LABEL_25:
  if ( v9 )
  {
    if ( v9 >= 2 )
      qsort(Base, v9, 8u, CompareLexographically);
    v21 = 0;
    v22 = 0;
    while ( 1 )
    {
      v23 = (OLECHAR *)Base[v22];
      if ( v21 )
      {
        v8 = StringCchCatNExW(v7, v6, L";", 1u, &v32, &v34, (unsigned int)lpcchClass);
        if ( v8 < 0 )
          break;
        v7 = v32;
        v6 = v34;
      }
      v24 = SysStringLen(v23);
      v8 = StringCchCatNExW(v7, v6, v23, v24, &v32, &v34, (unsigned int)lpcchClass);
      if ( v8 < 0 )
        break;
      v22 = ++v21;
      if ( v21 >= v9 )
        goto LABEL_35;
      v7 = v32;
      v6 = v34;
    }
LABEL_36:
    LODWORD(phkResult) = v8;
    WUTrace("CCommonAttributeProvider::AppendPrograms", 549, 4, 1, phkResult, L"Method failed");
  }
  else
  {
LABEL_35:
    if ( v8 < 0 )
      goto LABEL_36;
  }
LABEL_37:
  for ( j = 0; j < v9; ++j )
  {
    v26 = (OLECHAR *)Base[j];
    if ( v26 )
    {
      SysFreeString(v26);
      Base[j] = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14003585c  mov     [rsp-8+arg_0], rbx
0x140035861  push    rbp
0x140035862  push    rsi
0x140035863  push    rdi
0x140035864  push    r12
0x140035866  push    r13
0x140035868  push    r14
0x14003586a  push    r15
0x14003586c  lea     rbp, [rsp-200h]
0x140035874  sub     rsp, 300h
0x14003587b  mov     rax, cs:__security_cookie
0x140035882  xor     rax, rsp
0x140035885  mov     [rbp+230h+var_40], rax
0x14003588c  mov     rdi, r9
0x14003588f  mov     r13, r8
0x140035892  mov     r12, rdx
0x140035895  mov     [rsp+330h+var_2E0], rdx
0x14003589a  mov     [rsp+330h+var_2D0], r8
0x14003589f  mov     rbx, [rbp+230h+arg_20]
0x1400358a6  xor     eax, eax
0x1400358a8  mov     esi, eax
0x1400358aa  mov     [rsp+330h+hKey], rax
0x1400358af  mov     r14d, eax
0x1400358b2  mov     r15d, eax
0x1400358b5  mov     [rsp+330h+dwIndex], eax
0x1400358b9  xor     edx, edx; Val
0x1400358bb  mov     r8d, 80h; Size
0x1400358c1  lea     rcx, [rsp+330h+Base]; void *
0x1400358c6  call    memset
0x1400358cb  mov     [rdi], r12
0x1400358ce  mov     [rbx], r13
0x1400358d1  lea     ecx, [r15+12h]
0x1400358d5  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x1400358da  lea     rcx, [rsp+330h+hKey]
0x1400358df  mov     [rsp+330h+phkResult], rcx; phkResult
0x1400358e4  mov     r9d, 20019h; samDesired
0x1400358ea  xor     r8d, r8d; ulOptions
0x1400358ed  mov     rdx, rax; lpSubKey
0x1400358f0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400358f7  call    cs:__imp_RegOpenKeyExW
0x1400358fd  xor     edi, edi
0x1400358ff  test    eax, eax
0x140035901  jnz     loc_140035B79
0x140035907  xor     edx, edx; Val
0x140035909  mov     r8d, 200h; Size
0x14003590f  lea     rcx, [rbp+230h+Name]; void *
0x140035913  call    memset
0x140035918  mov     [rsp+330h+cchName], 100h
0x140035920  mov     eax, [rsp+330h+dwIndex]
0x140035924  mov     edx, eax; dwIndex
0x140035926  inc     eax
0x140035928  mov     [rsp+330h+dwIndex], eax
0x14003592c  mov     [rsp+330h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x140035931  mov     [rsp+330h+lpcchClass], rdi; unsigned int
0x140035936  mov     [rsp+330h+lpClass], rdi; lpClass
0x14003593b  mov     [rsp+330h+phkResult], rdi; lpReserved
0x140035940  lea     r9, [rsp+330h+cchName]; lpcchName
0x140035945  lea     r8, [rbp+230h+Name]; lpName
0x140035949  mov     rcx, [rsp+330h+hKey]; hKey
0x14003594e  call    cs:__imp_RegEnumKeyExW
0x140035954  mov     ecx, eax
0x140035956  add     eax, 0FFFFFFFEh
0x140035959  test    eax, 0FFFFFEFEh
0x14003595e  jnz     short loc_14003596C
0x140035960  cmp     ecx, 102h
0x140035966  jnz     loc_140035A70
0x14003596c  test    ecx, ecx
0x14003596e  jz      short loc_140035986
0x140035970  movzx   esi, cx
0x140035973  or      esi, 80070000h
0x140035979  test    ecx, ecx
0x14003597b  cmovle  esi, ecx
0x14003597e  inc     r15
0x140035981  jmp     loc_140035A56
0x140035986  cmp     [rsp+330h+cchName], 18h
0x14003598b  jbe     short loc_1400359BA
0x14003598d  lea     rax, [rbp+230h+Name]
0x140035991  mov     [rsp+330h+lpcchClass], rax
0x140035996  lea     rax, aProgramNameInv; "Program name invalid, exceeded max leng"...
0x14003599d  mov     [rsp+330h+lpClass], rax
0x1400359a2  mov     [rsp+330h+phkResult], rdi
0x1400359a7  xor     edx, edx
0x1400359a9  xor     ecx, ecx
0x1400359ab  lea     r9d, [rdx+3]
0x1400359af  lea     r8d, [rdx+4]
0x1400359b3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400359b8  jmp     short loc_14003597E
0x1400359ba  mov     rbx, rdi
0x1400359bd  movzx   ecx, [rbp+rbx*2+230h+Name]; C
0x1400359c2  cmp     di, cx
0x1400359c5  jz      short loc_1400359DC
0x1400359c7  call    _o_iswalnum_0
0x1400359cc  test    eax, eax
0x1400359ce  jz      short loc_140035A19
0x1400359d0  inc     rbx
0x1400359d3  cmp     rbx, 100h
0x1400359da  jb      short loc_1400359BD
0x1400359dc  xor     ecx, ecx; bstrString
0x1400359de  call    cs:__imp_SysFreeString
0x1400359e4  mov     [rsp+330h+var_2E8], rdi
0x1400359e9  lea     rax, [rbp+230h+Name]
0x1400359ed  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400359f1  inc     r8; unsigned int
0x1400359f4  cmp     [rax+r8*2], di
0x1400359f9  jnz     short loc_1400359F1
0x1400359fb  lea     rdx, [rbp+230h+Name]; wchar_t *
0x1400359ff  lea     rcx, [rsp+330h+var_2E8]; this
0x140035a04  call    ?Append@CSusBSTR@@QEAAJPEB_WK@Z; CSusBSTR::Append(wchar_t const *,ulong)
0x140035a09  mov     esi, eax
0x140035a0b  test    eax, eax
0x140035a0d  jns     short loc_140035A49
0x140035a0f  inc     r15
0x140035a12  mov     rcx, [rsp+330h+var_2E8]
0x140035a17  jmp     short loc_140035A58
0x140035a19  inc     r15
0x140035a1c  lea     rax, [rbp+230h+Name]
0x140035a20  mov     [rsp+330h+lpcchClass], rax
0x140035a25  lea     rax, aProgramNameInv_0; "Program name invalid, invalid char: %ws"
0x140035a2c  mov     [rsp+330h+lpClass], rax
0x140035a31  mov     [rsp+330h+phkResult], rdi
0x140035a36  xor     edx, edx
0x140035a38  xor     ecx, ecx
0x140035a3a  lea     r9d, [rdx+3]
0x140035a3e  lea     r8d, [rdx+4]
0x140035a42  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140035a47  jmp     short loc_140035A56
0x140035a49  mov     rax, [rsp+330h+var_2E8]
0x140035a4e  mov     [rsp+r14*8+330h+Base], rax
0x140035a53  inc     r14
0x140035a56  xor     ecx, ecx; bstrString
0x140035a58  call    cs:__imp_SysFreeString
0x140035a5e  cmp     r14, 10h
0x140035a62  jnb     short loc_140035A78
0x140035a64  cmp     r15, 40h ; '@'
0x140035a68  jb      loc_140035907
0x140035a6e  jmp     short loc_140035A78
0x140035a70  xor     ecx, ecx; bstrString
0x140035a72  call    cs:__imp_SysFreeString
0x140035a78  test    r14, r14
0x140035a7b  jz      loc_140035B46
0x140035a81  cmp     r14, 2
0x140035a85  jb      short loc_140035AA5
0x140035a87  lea     r9, CompareLexographically; CompareFunction
0x140035a8e  mov     r8d, 8; SizeOfElements
0x140035a94  mov     rdx, r14; NumOfElements
0x140035a97  lea     rcx, [rsp+330h+Base]; Base
0x140035a9c  call    qsort
0x140035aa1  mov     ebx, edi
0x140035aa3  jmp     short loc_140035AB0
0x140035aa5  mov     ebx, edi
0x140035aa7  test    r14, r14
0x140035aaa  jz      loc_140035B46
0x140035ab0  mov     rax, rdi
0x140035ab3  mov     rdi, [rsp+rax*8+330h+Base]
0x140035ab8  test    ebx, ebx
0x140035aba  jz      short loc_140035AF8
0x140035abc  lea     rax, [rsp+330h+var_2D0]
0x140035ac1  mov     [rsp+330h+lpClass], rax; unsigned __int64 *
0x140035ac6  lea     rax, [rsp+330h+var_2E0]
0x140035acb  mov     [rsp+330h+phkResult], rax; wchar_t **
0x140035ad0  mov     r9d, 1; unsigned __int64
0x140035ad6  lea     r8, asc_1400569A4; ";"
0x140035add  mov     rdx, r13; unsigned __int64
0x140035ae0  mov     rcx, r12; wchar_t *
0x140035ae3  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140035ae8  mov     esi, eax
0x140035aea  test    eax, eax
0x140035aec  js      short loc_140035B4C
0x140035aee  mov     r12, [rsp+330h+var_2E0]
0x140035af3  mov     r13, [rsp+330h+var_2D0]
0x140035af8  mov     rcx, rdi; pbstr
0x140035afb  call    cs:__imp_SysStringLen
0x140035b01  mov     r9d, eax; unsigned __int64
0x140035b04  lea     rax, [rsp+330h+var_2D0]
0x140035b09  mov     [rsp+330h+lpClass], rax; unsigned __int64 *
0x140035b0e  lea     rax, [rsp+330h+var_2E0]
0x140035b13  mov     [rsp+330h+phkResult], rax; wchar_t **
0x140035b18  mov     r8, rdi; wchar_t *
0x140035b1b  mov     rdx, r13; unsigned __int64
0x140035b1e  mov     rcx, r12; wchar_t *
0x140035b21  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140035b26  mov     esi, eax
0x140035b28  xor     edi, edi
0x140035b2a  test    eax, eax
0x140035b2c  js      short loc_140035B4E
0x140035b2e  inc     ebx
0x140035b30  mov     eax, ebx
0x140035b32  cmp     rax, r14
0x140035b35  jnb     short loc_140035B46
0x140035b37  mov     r12, [rsp+330h+var_2E0]
0x140035b3c  mov     r13, [rsp+330h+var_2D0]
0x140035b41  jmp     loc_140035AB3
0x140035b46  test    esi, esi
0x140035b48  jns     short loc_140035B79
0x140035b4a  jmp     short loc_140035B4E
0x140035b4c  xor     edi, edi
0x140035b4e  lea     rax, aMethodFailed; "Method failed"
0x140035b55  mov     [rsp+330h+lpClass], rax
0x140035b5a  mov     dword ptr [rsp+330h+phkResult], esi
0x140035b5e  mov     edx, 225h
0x140035b63  mov     r9d, 1
0x140035b69  lea     r8d, [r9+3]
0x140035b6d  lea     rcx, aCcommonattribu_10; "CCommonAttributeProvider::AppendProgram"...
0x140035b74  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140035b79  mov     rbx, rdi
0x140035b7c  test    r14, r14
0x140035b7f  jz      short loc_140035B9E
0x140035b81  mov     rcx, [rsp+rbx*8+330h+Base]; bstrString
0x140035b86  test    rcx, rcx
0x140035b89  jz      short loc_140035B96
0x140035b8b  call    cs:__imp_SysFreeString
0x140035b91  mov     [rsp+rbx*8+330h+Base], rdi
0x140035b96  inc     rbx
0x140035b99  cmp     rbx, r14
0x140035b9c  jb      short loc_140035B81
0x140035b9e  mov     rcx, [rsp+330h+hKey]; hKey
0x140035ba3  test    rcx, rcx
0x140035ba6  jz      short loc_140035BAE
0x140035ba8  call    cs:__imp_RegCloseKey
0x140035bae  mov     eax, esi
0x140035bb0  mov     rcx, [rbp+230h+var_40]
0x140035bb7  xor     rcx, rsp; StackCookie
0x140035bba  call    __security_check_cookie
0x140035bbf  mov     rbx, [rsp+330h+arg_0]
0x140035bc7  add     rsp, 300h
0x140035bce  pop     r15
0x140035bd0  pop     r14
0x140035bd2  pop     r13
0x140035bd4  pop     r12
0x140035bd6  pop     rdi
0x140035bd7  pop     rsi
0x140035bd8  pop     rbp
0x140035bd9  retn
```
