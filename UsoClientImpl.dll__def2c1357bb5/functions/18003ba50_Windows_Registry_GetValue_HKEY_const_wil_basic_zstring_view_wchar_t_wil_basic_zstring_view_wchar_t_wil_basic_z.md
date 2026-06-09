# Windows::Registry::GetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18003ba50`
- end: `0x18003bf18`
- name: `?GetValue@Registry@Windows@@QEAA?AU?$pair@JV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11@Z`
- size: `1224`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180023440`
- `0x180033bf0`
- `0x18003cb5c`

## callees

- `0x180009380`
- `0x18002d62c`
- `0x180033b00`
- `0x180035184`
- `0x18003ba50`
- `0x18003c020`
- `0x18003d0c0`
- `0x18003df70`
- `0x180056500`
- `0x180058abc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003baf2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bb8f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bc3b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bd28`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003baf2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bb8f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bc3b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bd28`

## string_xrefs

- `0x18003bb39`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003bde1`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003bef7`: `Registry type unsupported`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Registry::GetValue(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        _OWORD *a5,
        const WCHAR **a6)
{
  const WCHAR *v7; // rsi
  const WCHAR *v8; // rdx
  LSTATUS ValueW; // eax
  int v10; // edx
  LPCWSTR *v11; // rax
  const WCHAR *v12; // rdx
  unsigned int v13; // ebx
  const WCHAR *v14; // rdx
  DWORD *v15; // rax
  const WCHAR *v16; // rdx
  DWORD *v17; // rax
  unsigned __int64 v18; // rdx
  DWORD *v19; // rax
  LPCWSTR *v20; // rax
  _QWORD *v21; // rbx
  bool v22; // zf
  unsigned int v23; // eax
  DWORD pdwType; // [rsp+44h] [rbp-75h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-71h] BYREF
  DWORD pExceptionObject[4]; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v28; // [rsp+60h] [rbp-59h]
  unsigned __int64 v29; // [rsp+68h] [rbp-51h]
  __int128 pvData; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v31[4]; // [rsp+80h] [rbp-39h] BYREF
  char v32; // [rsp+A0h] [rbp-19h]
  char v33; // [rsp+A8h] [rbp-11h]
  LPCWSTR lpSubKey[3]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int64 v35; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]

  *(_QWORD *)pExceptionObject = a2;
  v33 = 0;
  *(_OWORD *)pExceptionObject = *a5;
  pvData = *a4;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &pvData, pExceptionObject);
  pdwType = 0;
  pcbData = 0;
  v7 = *a6;
  v8 = (const WCHAR *)lpSubKey;
  if ( v35 > 7 )
    v8 = lpSubKey[0];
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v8, v7, 0xFFFFu, &pdwType, 0, &pcbData);
  v10 = ValueW;
  if ( ValueW != 2 && ValueW != 1018 )
  {
    v11 = lpSubKey;
    if ( v35 > 7 )
      v11 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x46,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      (const char *)(unsigned int)v10,
      (unsigned int)"%ws[%ws]",
      (const char *)v11,
      v7);
    switch ( pdwType )
    {
      case 4u:
        LODWORD(pvData) = 0;
        pExceptionObject[0] = 4;
        v12 = (const WCHAR *)lpSubKey;
        if ( v35 > 7 )
          v12 = lpSubKey[0];
        v13 = RegGetValueW(HKEY_LOCAL_MACHINE, v12, v7, 0x10u, &pdwType, &pvData, pExceptionObject);
        if ( !v13 )
        {
          if ( v33 )
          {
            if ( v32 )
            {
              if ( v32 != -1 && (unsigned __int64)v32 >= 2 )
                std::wstring::~wstring(v31);
              LODWORD(v31[0]) = pvData;
              v32 = 0;
            }
            else
            {
              LODWORD(v31[0]) = pvData;
            }
            goto LABEL_56;
          }
          LODWORD(v31[0]) = pvData;
          v32 = 0;
          goto LABEL_31;
        }
        break;
      case 0xBu:
        *(_QWORD *)&pvData = 0;
        pExceptionObject[0] = 8;
        v14 = (const WCHAR *)lpSubKey;
        if ( v35 > 7 )
          v14 = lpSubKey[0];
        v13 = RegGetValueW(HKEY_LOCAL_MACHINE, v14, v7, 0x40u, &pdwType, &pvData, pExceptionObject);
        if ( !v13 )
        {
          if ( v33 )
          {
            if ( v32 == 1 )
            {
              v31[0] = pvData;
            }
            else
            {
              if ( v32 != -1 && (unsigned __int64)v32 >= 2 )
                std::wstring::~wstring(v31);
              v31[0] = pvData;
              v32 = 1;
            }
            goto LABEL_56;
          }
          v31[0] = pvData;
          v32 = 1;
LABEL_31:
          v33 = 1;
          goto LABEL_56;
        }
        break;
      case 1u:
        *(_OWORD *)pExceptionObject = 0;
        v28 = 0;
        v29 = 7;
        LOWORD(pExceptionObject[0]) = 0;
        if ( (unsigned __int64)pcbData >> 1 )
        {
          std::wstring::append(pExceptionObject);
        }
        else
        {
          v28 = 0;
          LOWORD(pExceptionObject[0]) = 0;
        }
        v15 = pExceptionObject;
        if ( v29 > 7 )
          v15 = *(DWORD **)pExceptionObject;
        v16 = (const WCHAR *)lpSubKey;
        if ( v35 > 7 )
          v16 = lpSubKey[0];
        v13 = RegGetValueW(HKEY_LOCAL_MACHINE, v16, v7, 2u, &pdwType, v15, &pcbData);
        if ( !v13 )
        {
          while ( v28 )
          {
            v17 = pExceptionObject;
            if ( v29 > 7 )
              v17 = *(DWORD **)pExceptionObject;
            v18 = v28 - 1;
            if ( *((_WORD *)v17 + v28 - 1) )
              break;
            if ( v18 > v28 )
            {
              std::wstring::append(pExceptionObject);
            }
            else
            {
              --v28;
              v19 = pExceptionObject;
              if ( v29 > 7 )
                v19 = *(DWORD **)pExceptionObject;
              *((_WORD *)v19 + v18) = 0;
            }
          }
          std::optional<std::variant<unsigned int,unsigned __int64,std::wstring>>::operator=<std::wstring &,0>(v31);
        }
        std::wstring::~wstring(pExceptionObject);
        break;
      default:
        std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Registry type unsupported");
        throw (std::logic_error *)pExceptionObject;
    }
    if ( v13 == 2 || v13 == 1018 || v13 == 1168 )
    {
      *(_DWORD *)a2 = (unsigned __int16)v13 | 0x80070000;
      *(_BYTE *)(a2 + 48) = 0;
LABEL_66:
      std::wstring::~wstring(lpSubKey);
      if ( !v33 || v32 == -1 || !v32 )
        return a2;
      v22 = v32 == 1;
      goto LABEL_77;
    }
LABEL_56:
    v20 = lpSubKey;
    if ( v35 > 7 )
      v20 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x8B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      (const char *)v13,
      (unsigned int)"%ws[%ws]",
      (const char *)v20,
      v7);
    *(_DWORD *)a2 = 0;
    v21 = (_QWORD *)(a2 + 8);
    *(_QWORD *)pExceptionObject = a2 + 8;
    *(_BYTE *)(a2 + 48) = 0;
    if ( v33 )
    {
      *(_QWORD *)&pvData = a2 + 8;
      *(_BYTE *)(a2 + 40) = -1;
      if ( v32 != -1 )
      {
        if ( v32 )
        {
          if ( v32 == 1 )
          {
            *v21 = v31[0];
            *(_BYTE *)(a2 + 40) = 1;
          }
          else
          {
            std::wstring::wstring(a2 + 8, v31);
            *(_BYTE *)(a2 + 40) = 2;
          }
        }
        else
        {
          *(_DWORD *)v21 = v31[0];
          *(_BYTE *)(a2 + 40) = 0;
        }
      }
      *(_BYTE *)(a2 + 48) = 1;
    }
    goto LABEL_66;
  }
  v23 = (unsigned __int16)ValueW | 0x80070000;
  if ( v10 <= 0 )
    v23 = v10;
  *(_DWORD *)a2 = v23;
  *(_BYTE *)(a2 + 48) = 0;
  std::wstring::~wstring(lpSubKey);
  if ( v33 && v32 != -1 && v32 )
  {
    v22 = v32 == 1;
LABEL_77:
    if ( !v22 )
      std::wstring::~wstring(v31);
  }
  return a2;
}

```

## disassembly

```asm
0x18003ba50  mov     [rsp-8+arg_0], rbx
0x18003ba55  push    rbp
0x18003ba56  push    rsi
0x18003ba57  push    rdi
0x18003ba58  push    r13
0x18003ba5a  push    r14
0x18003ba5c  lea     rbp, [rsp-27h]
0x18003ba61  sub     rsp, 0E0h
0x18003ba68  mov     rax, cs:__security_cookie
0x18003ba6f  xor     rax, rsp
0x18003ba72  mov     [rbp+47h+var_30], rax
0x18003ba76  mov     rdi, rdx
0x18003ba79  mov     qword ptr [rbp+47h+pExceptionObject], rdx
0x18003ba7d  mov     rax, [rbp+47h+arg_20]
0x18003ba81  mov     rbx, [rbp+47h+arg_28]
0x18003ba85  xor     r14d, r14d
0x18003ba88  mov     [rbp+47h+var_58], r14b
0x18003ba8c  movaps  xmm0, xmmword ptr [rax]
0x18003ba8f  movdqa  xmmword ptr [rbp+47h+pExceptionObject], xmm0
0x18003ba94  movaps  xmm1, xmmword ptr [r9]
0x18003ba98  movdqa  [rbp+47h+var_90], xmm1
0x18003ba9d  lea     r9, [rbp+47h+pExceptionObject]
0x18003baa1  lea     r8, [rbp+47h+var_90]
0x18003baa5  lea     rdx, [rbp+47h+lpSubKey]
0x18003baa9  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18003baae  nop
0x18003baaf  mov     [rbp+47h+var_BC], r14d
0x18003bab3  mov     [rbp+47h+var_B8], r14d
0x18003bab7  mov     rsi, [rbx]
0x18003baba  lea     rdx, [rbp+47h+lpSubKey]
0x18003babe  cmp     [rbp+47h+var_38], 7
0x18003bac3  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18003bac8  lea     rax, [rbp+47h+var_B8]
0x18003bacc  mov     [rsp+100h+pcbData], rax; pcbData
0x18003bad1  mov     [rsp+100h+pvData], r14; pvData
0x18003bad6  lea     rax, [rbp+47h+var_BC]
0x18003bada  mov     [rsp+100h+pdwType], rax; pdwType
0x18003badf  mov     r9d, 0FFFFh; dwFlags
0x18003bae5  mov     r8, rsi; lpValue
0x18003bae8  mov     rbx, 0FFFFFFFF80000002h
0x18003baef  mov     rcx, rbx; hkey
0x18003baf2  call    cs:__imp_RegGetValueW
0x18003baf8  mov     edx, eax
0x18003bafa  cmp     eax, 2
0x18003bafd  jz      loc_18003BE8E
0x18003bb03  cmp     eax, 3FAh
0x18003bb08  jz      loc_18003BE8E
0x18003bb0e  lea     rax, [rbp+47h+lpSubKey]
0x18003bb12  cmp     [rbp+47h+var_38], 7
0x18003bb17  cmova   rax, [rbp+47h+lpSubKey]
0x18003bb1c  mov     rcx, [rbp+4Fh]; this
0x18003bb20  mov     [rsp+100h+pcbData], rsi
0x18003bb25  mov     [rsp+100h+pvData], rax; char *
0x18003bb2a  lea     r13, aWsWs_0; "%ws[%ws]"
0x18003bb31  mov     [rsp+100h+pdwType], r13; unsigned int
0x18003bb36  mov     r9d, edx; char *
0x18003bb39  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003bb40  lea     edx, [r14+46h]; void *
0x18003bb44  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003bb49  mov     eax, [rbp+47h+var_BC]
0x18003bb4c  cmp     eax, 4
0x18003bb4f  jnz     loc_18003BBF2
0x18003bb55  mov     dword ptr [rbp+47h+var_90], r14d
0x18003bb59  mov     [rbp+47h+pExceptionObject], eax
0x18003bb5c  lea     rdx, [rbp+47h+lpSubKey]
0x18003bb60  cmp     [rbp+47h+var_38], 7
0x18003bb65  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18003bb6a  lea     rax, [rbp+47h+pExceptionObject]
0x18003bb6e  mov     [rsp+100h+pcbData], rax; pcbData
0x18003bb73  lea     rax, [rbp+47h+var_90]
0x18003bb77  mov     [rsp+100h+pvData], rax; pvData
0x18003bb7c  lea     rax, [rbp+47h+var_BC]
0x18003bb80  mov     [rsp+100h+pdwType], rax; pdwType
0x18003bb85  lea     r9d, [r14+10h]; dwFlags
0x18003bb89  mov     r8, rsi; lpValue
0x18003bb8c  mov     rcx, rbx; hkey
0x18003bb8f  call    cs:__imp_RegGetValueW
0x18003bb95  mov     ebx, eax
0x18003bb97  test    eax, eax
0x18003bb99  jnz     loc_18003BD9C
0x18003bb9f  cmp     [rbp+47h+var_58], r14b
0x18003bba3  jz      short loc_18003BBE3
0x18003bba5  movsx   rax, [rbp+47h+var_60]
0x18003bbaa  test    al, al
0x18003bbac  jnz     short loc_18003BBB9
0x18003bbae  mov     eax, dword ptr [rbp+47h+var_90]
0x18003bbb1  mov     dword ptr [rbp+47h+var_80], eax
0x18003bbb4  jmp     loc_18003BDBD
0x18003bbb9  add     rax, 1
0x18003bbbd  jz      short loc_18003BBD4
0x18003bbbf  sub     rax, 1
0x18003bbc3  jz      short loc_18003BBD4
0x18003bbc5  cmp     rax, 1
0x18003bbc9  jz      short loc_18003BBD4
0x18003bbcb  lea     rcx, [rbp+47h+var_80]; void *
0x18003bbcf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bbd4  mov     eax, dword ptr [rbp+47h+var_90]
0x18003bbd7  mov     dword ptr [rbp+47h+var_80], eax
0x18003bbda  mov     [rbp+47h+var_60], r14b
0x18003bbde  jmp     loc_18003BDBD
0x18003bbe3  mov     eax, dword ptr [rbp+47h+var_90]
0x18003bbe6  mov     dword ptr [rbp+47h+var_80], eax
0x18003bbe9  mov     [rbp+47h+var_60], r14b
0x18003bbed  jmp     loc_18003BC9F
0x18003bbf2  cmp     eax, 0Bh
0x18003bbf5  jnz     loc_18003BCA8
0x18003bbfb  mov     qword ptr [rbp+47h+var_90], r14
0x18003bbff  mov     [rbp+47h+pExceptionObject], 8
0x18003bc06  lea     rdx, [rbp+47h+lpSubKey]
0x18003bc0a  cmp     [rbp+47h+var_38], 7
0x18003bc0f  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18003bc14  lea     rax, [rbp+47h+pExceptionObject]
0x18003bc18  mov     [rsp+100h+pcbData], rax; pcbData
0x18003bc1d  lea     rax, [rbp+47h+var_90]
0x18003bc21  mov     [rsp+100h+pvData], rax; pvData
0x18003bc26  lea     rax, [rbp+47h+var_BC]
0x18003bc2a  mov     [rsp+100h+pdwType], rax; pdwType
0x18003bc2f  mov     r9d, 40h ; '@'; dwFlags
0x18003bc35  mov     r8, rsi; lpValue
0x18003bc38  mov     rcx, rbx; hkey
0x18003bc3b  call    cs:__imp_RegGetValueW
0x18003bc41  mov     ebx, eax
0x18003bc43  test    eax, eax
0x18003bc45  jnz     loc_18003BD9C
0x18003bc4b  cmp     [rbp+47h+var_58], r14b
0x18003bc4f  jz      short loc_18003BC93
0x18003bc51  movsx   rax, [rbp+47h+var_60]
0x18003bc56  cmp     al, 1
0x18003bc58  jnz     short loc_18003BC67
0x18003bc5a  mov     rax, qword ptr [rbp+47h+var_90]
0x18003bc5e  mov     [rbp+47h+var_80], rax
0x18003bc62  jmp     loc_18003BDBD
0x18003bc67  add     rax, 1
0x18003bc6b  jz      short loc_18003BC82
0x18003bc6d  sub     rax, 1
0x18003bc71  jz      short loc_18003BC82
0x18003bc73  cmp     rax, 1
0x18003bc77  jz      short loc_18003BC82
0x18003bc79  lea     rcx, [rbp+47h+var_80]; void *
0x18003bc7d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bc82  mov     rax, qword ptr [rbp+47h+var_90]
0x18003bc86  mov     [rbp+47h+var_80], rax
0x18003bc8a  mov     [rbp+47h+var_60], 1
0x18003bc8e  jmp     loc_18003BDBD
0x18003bc93  mov     rax, qword ptr [rbp+47h+var_90]
0x18003bc97  mov     [rbp+47h+var_80], rax
0x18003bc9b  mov     [rbp+47h+var_60], 1
0x18003bc9f  mov     [rbp+47h+var_58], 1
0x18003bca3  jmp     loc_18003BDBD
0x18003bca8  cmp     eax, 1
0x18003bcab  jnz     loc_18003BEF7
0x18003bcb1  xorps   xmm0, xmm0
0x18003bcb4  movups  xmmword ptr [rbp+47h+pExceptionObject], xmm0
0x18003bcb8  mov     [rbp+47h+var_A0], r14
0x18003bcbc  mov     [rbp+47h+var_98], 7
0x18003bcc4  mov     word ptr [rbp+47h+pExceptionObject], r14w
0x18003bcc9  mov     edx, [rbp+47h+var_B8]
0x18003bccc  shr     rdx, 1
0x18003bccf  jnz     short loc_18003BCDD
0x18003bcd1  mov     [rbp+47h+var_A0], rdx
0x18003bcd5  mov     word ptr [rbp+rdx*2+47h+pExceptionObject], r14w
0x18003bcdb  jmp     short loc_18003BCE9
0x18003bcdd  xor     r8d, r8d
0x18003bce0  lea     rcx, [rbp+47h+pExceptionObject]; Src
0x18003bce4  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x18003bce9  lea     rax, [rbp+47h+pExceptionObject]
0x18003bced  cmp     [rbp+47h+var_98], 7
0x18003bcf2  cmova   rax, qword ptr [rbp+47h+pExceptionObject]
0x18003bcf7  lea     rdx, [rbp+47h+lpSubKey]
0x18003bcfb  cmp     [rbp+47h+var_38], 7
0x18003bd00  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18003bd05  lea     rcx, [rbp+47h+var_B8]
0x18003bd09  mov     [rsp+100h+pcbData], rcx; pcbData
0x18003bd0e  mov     [rsp+100h+pvData], rax; pvData
0x18003bd13  lea     rax, [rbp+47h+var_BC]
0x18003bd17  mov     [rsp+100h+pdwType], rax; pdwType
0x18003bd1c  mov     r9d, 2; dwFlags
0x18003bd22  mov     r8, rsi; lpValue
0x18003bd25  mov     rcx, rbx; hkey
0x18003bd28  call    cs:__imp_RegGetValueW
0x18003bd2e  mov     ebx, eax
0x18003bd30  test    eax, eax
0x18003bd32  jnz     short loc_18003BD93
0x18003bd34  jmp     short loc_18003BD7C
0x18003bd36  lea     rax, [rbp+47h+pExceptionObject]
0x18003bd3a  cmp     [rbp+47h+var_98], 7
0x18003bd3f  cmova   rax, qword ptr [rbp+47h+pExceptionObject]
0x18003bd44  lea     rdx, [rcx-1]
0x18003bd48  cmp     [rax+rdx*2], r14w
0x18003bd4d  jnz     short loc_18003BD85
0x18003bd4f  cmp     rdx, rcx
0x18003bd52  ja      short loc_18003BD6D
0x18003bd54  mov     [rbp+47h+var_A0], rdx
0x18003bd58  lea     rax, [rbp+47h+pExceptionObject]
0x18003bd5c  cmp     [rbp+47h+var_98], 7
0x18003bd61  cmova   rax, qword ptr [rbp+47h+pExceptionObject]
0x18003bd66  mov     [rax+rdx*2], r14w
0x18003bd6b  jmp     short loc_18003BD7C
0x18003bd6d  xor     r8d, r8d
0x18003bd70  sub     rdx, rcx
0x18003bd73  lea     rcx, [rbp+47h+pExceptionObject]; Src
0x18003bd77  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x18003bd7c  mov     rcx, [rbp+47h+var_A0]
0x18003bd80  test    rcx, rcx
0x18003bd83  jnz     short loc_18003BD36
0x18003bd85  lea     rdx, [rbp+47h+pExceptionObject]
0x18003bd89  lea     rcx, [rbp+47h+var_80]
0x18003bd8d  call    ??$?4AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAAEAV01@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::optional<std::variant<uint,unsigned __int64,std::wstring>>::operator=<std::wstring &,0>(std::wstring &)
0x18003bd92  nop
0x18003bd93  lea     rcx, [rbp+47h+pExceptionObject]; void *
0x18003bd97  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bd9c  cmp     ebx, 2
0x18003bd9f  jz      loc_18003BE79
0x18003bda5  cmp     ebx, 3FAh
0x18003bdab  jz      loc_18003BE79
0x18003bdb1  cmp     ebx, 490h
0x18003bdb7  jz      loc_18003BE79
0x18003bdbd  lea     rax, [rbp+47h+lpSubKey]
0x18003bdc1  cmp     [rbp+47h+var_38], 7
0x18003bdc6  cmova   rax, [rbp+47h+lpSubKey]
0x18003bdcb  mov     rcx, [rbp+4Fh]; this
0x18003bdcf  mov     [rsp+100h+pcbData], rsi
0x18003bdd4  mov     [rsp+100h+pvData], rax; char *
0x18003bdd9  mov     [rsp+100h+pdwType], r13; unsigned int
0x18003bdde  mov     r9d, ebx; char *
0x18003bde1  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003bde8  mov     edx, 8Bh; void *
0x18003bded  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003bdf2  mov     [rdi], r14d
0x18003bdf5  lea     rbx, [rdi+8]
0x18003bdf9  mov     qword ptr [rbp+47h+pExceptionObject], rbx
0x18003bdfd  mov     [rbx+28h], r14b
0x18003be01  cmp     [rbp+47h+var_58], r14b
0x18003be05  jz      short loc_18003BE52
0x18003be07  mov     qword ptr [rbp+47h+var_90], rbx
0x18003be0b  mov     byte ptr [rbx+20h], 0FFh
0x18003be0f  movsx   rax, [rbp+47h+var_60]
0x18003be14  add     rax, 1
0x18003be18  jz      short loc_18003BE4E
0x18003be1a  sub     rax, 1
0x18003be1e  jz      short loc_18003BE45
0x18003be20  cmp     rax, 1
0x18003be24  jz      short loc_18003BE38
0x18003be26  lea     rdx, [rbp+47h+var_80]
0x18003be2a  mov     rcx, rbx
0x18003be2d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003be32  mov     byte ptr [rbx+20h], 2
0x18003be36  jmp     short loc_18003BE4E
0x18003be38  mov     rax, [rbp+47h+var_80]
0x18003be3c  mov     [rbx], rax
0x18003be3f  mov     byte ptr [rbx+20h], 1
0x18003be43  jmp     short loc_18003BE4E
0x18003be45  mov     eax, dword ptr [rbp+47h+var_80]
0x18003be48  mov     [rbx], eax
0x18003be4a  mov     [rbx+20h], r14b
0x18003be4e  mov     byte ptr [rbx+28h], 1
0x18003be52  lea     rcx, [rbp+47h+lpSubKey]; void *
0x18003be56  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003be5b  nop
0x18003be5c  cmp     [rbp+47h+var_58], r14b
0x18003be60  jz      short loc_18003BED1
0x18003be62  movsx   rax, [rbp+47h+var_60]
0x18003be67  add     rax, 1
0x18003be6b  jz      short loc_18003BED1
0x18003be6d  sub     rax, 1
0x18003be71  jz      short loc_18003BED1
0x18003be73  cmp     rax, 1
0x18003be77  jmp     short loc_18003BEC6
0x18003be79  movzx   eax, bx
0x18003be7c  or      eax, 80070000h
0x18003be81  test    ebx, ebx
0x18003be83  cmovle  eax, ebx
0x18003be86  mov     [rdi], eax
0x18003be88  mov     [rdi+30h], r14b
0x18003be8c  jmp     short loc_18003BE52
0x18003be8e  movzx   eax, dx
0x18003be91  or      eax, 80070000h
0x18003be96  test    edx, edx
0x18003be98  cmovle  eax, edx
0x18003be9b  mov     [rdi], eax
0x18003be9d  mov     [rdi+30h], r14b
0x18003bea1  lea     rcx, [rbp+47h+lpSubKey]; void *
0x18003bea5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003beaa  nop
0x18003beab  cmp     [rbp+47h+var_58], r14b
0x18003beaf  jz      short loc_18003BED1
0x18003beb1  movsx   rcx, [rbp+47h+var_60]
0x18003beb6  add     rcx, 1
0x18003beba  jz      short loc_18003BED1
0x18003bebc  sub     rcx, 1
0x18003bec0  jz      short loc_18003BED1
0x18003bec2  cmp     rcx, 1
0x18003bec6  jz      short loc_18003BED1
0x18003bec8  lea     rcx, [rbp+47h+var_80]; void *
0x18003becc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bed1  mov     rax, rdi
0x18003bed4  mov     rcx, [rbp+47h+var_30]
0x18003bed8  xor     rcx, rsp; StackCookie
0x18003bedb  call    __security_check_cookie
0x18003bee0  mov     rbx, [rsp+100h+arg_0]
  ... truncated ...
```
