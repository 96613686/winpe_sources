# OneCore::Base::Telemetry::OneSettingsQuery::HaveQueryParametersChanged(bool &)

- ea: `0x18001c738`
- end: `0x18001cacf`
- name: `?HaveQueryParametersChanged@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEA_N@Z`
- size: `919`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180022a14`

## callees

- `0x180003850`
- `0x18001c540`
- `0x18001c738`
- `0x1800322de`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001c93f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001c93f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c86c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c86c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c7f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c7f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ca90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ca90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c8ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c8da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c8ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c8da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c8ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ca5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ca73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c899`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c8ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ca5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ca73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ca68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ca81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ca68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ca81`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::HaveQueryParametersChanged(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        bool *a2)
{
  char v2; // r12
  signed int v5; // ebx
  LSTATUS v6; // eax
  bool v7; // cc
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rsi
  __int64 v11; // rbx
  HANDLE v12; // rax
  BYTE *v13; // r14
  DWORD v14; // r13d
  LSTATUS v15; // eax
  const unsigned __int16 *Value; // rax
  BYTE *v17; // rcx
  signed __int64 v18; // rax
  int v19; // r8d
  int v20; // edx
  const unsigned __int16 *v21; // rax
  BYTE *v22; // rcx
  signed __int64 v23; // rax
  int v24; // r8d
  int v25; // edx
  const wchar_t *v26; // rax
  bool v27; // al
  HANDLE v28; // rax
  HANDLE v29; // rax
  char v31; // [rsp+60h] [rbp-A0h]
  DWORD cValues; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD Type; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  v2 = 0;
  cValues = 0;
  cchValueName = 0;
  cbData = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  Type = 0;
  hKey = 0;
  v5 = StringCchPrintfW(
         SubKey,
         0x104u,
         L"%ls\\%ls\\%ls\\%ls",
         (char *)this + 1080,
         (char *)this + 40,
         (char *)this + 560,
         L"QueryParameters");
  if ( v5 < 0 )
    goto LABEL_43;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v5 = v6;
  if ( v6 )
  {
    if ( v6 == 2 )
    {
LABEL_4:
      *a2 = 1;
      v5 = 0;
      goto LABEL_43;
    }
    v7 = v6 <= 0;
    goto LABEL_6;
  }
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v5 = v6;
  v7 = v6 <= 0;
  if ( v6 )
  {
LABEL_6:
    if ( !v7 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_43;
  }
  if ( *((_DWORD *)this + 418) + *((_DWORD *)this + 430) != cValues )
    goto LABEL_4;
  v8 = 2LL * (cbMaxValueNameLen + 1);
  ProcessHeap = GetProcessHeap();
  v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v8);
  if ( v10 )
  {
    v11 = cbMaxValueLen;
    v12 = GetProcessHeap();
    v13 = (BYTE *)HeapAlloc(v12, 8u, v11 + 2);
    if ( v13 )
    {
      v14 = 0;
      if ( cValues )
      {
        while ( 1 )
        {
          cchValueName = cbMaxValueNameLen + 1;
          cbData = cbMaxValueLen;
          v15 = RegEnumValueW(hKey, v14, v10, &cchValueName, 0, &Type, v13, &cbData);
          v5 = v15;
          if ( v15 )
            break;
          *(_WORD *)&v13[2 * ((unsigned __int64)cbData >> 1)] = 0;
          if ( Type != 1 )
            goto LABEL_36;
          if ( !RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1656), v10) )
            goto LABEL_22;
          Value = RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1656), v10);
          v17 = v13;
          v18 = (char *)Value - (char *)v13;
          do
          {
            v19 = *(unsigned __int16 *)&v17[v18];
            v20 = *(unsigned __int16 *)v17 - v19;
            if ( v20 )
              break;
            v17 += 2;
          }
          while ( v19 );
          v31 = 1;
          if ( v20 )
LABEL_22:
            v31 = 0;
          if ( RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704), v10) )
          {
            v21 = RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704), v10);
            v22 = v13;
            v23 = (char *)v21 - (char *)v13;
            do
            {
              v24 = *(unsigned __int16 *)&v22[v23];
              v25 = *(unsigned __int16 *)v22 - v24;
              if ( v25 )
                break;
              v22 += 2;
            }
            while ( v24 );
            if ( !v25 )
              v2 = 1;
          }
          v27 = 0;
          if ( RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704), v10) )
          {
            v26 = RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704), v10);
            if ( !wcscmp_0(L"FALSE", v26) )
              v27 = 1;
          }
          if ( v31 || v2 )
          {
            v2 = 0;
          }
          else
          {
            v2 = 0;
            if ( !v27 )
            {
LABEL_36:
              *a2 = 1;
              goto LABEL_40;
            }
          }
          if ( ++v14 >= cValues )
            goto LABEL_39;
        }
        if ( v15 > 0 )
          v5 = (unsigned __int16)v15 | 0x80070000;
      }
      else
      {
LABEL_39:
        *a2 = 0;
LABEL_40:
        v5 = 0;
      }
    }
    else
    {
      v5 = -2147024882;
    }
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v10);
    if ( v13 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v13);
    }
  }
  else
  {
    v5 = -2147024882;
  }
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001c738  mov     [rsp-8+arg_10], rbx
0x18001c73d  push    rbp
0x18001c73e  push    rsi
0x18001c73f  push    rdi
0x18001c740  push    r12
0x18001c742  push    r13
0x18001c744  push    r14
0x18001c746  push    r15
0x18001c748  lea     rbp, [rsp-1B0h]
0x18001c750  sub     rsp, 2B0h
0x18001c757  mov     rax, cs:__security_cookie
0x18001c75e  xor     rax, rsp
0x18001c761  mov     [rbp+1E0h+var_40], rax
0x18001c768  xor     r12d, r12d
0x18001c76b  lea     rax, [rcx+230h]
0x18001c772  mov     r15, rcx
0x18001c775  mov     [rsp+2E0h+cValues], r12d
0x18001c77a  mov     rdi, rdx
0x18001c77d  mov     [rsp+2E0h+cchValueName], r12d
0x18001c782  add     rcx, 28h ; '('
0x18001c786  mov     [rsp+2E0h+cbData], r12d
0x18001c78b  lea     rdx, aQueryparameter; "QueryParameters"
0x18001c792  mov     [rsp+2E0h+cbMaxValueNameLen], r12d
0x18001c797  mov     [rsp+2E0h+lpcbMaxClassLen], rdx
0x18001c79c  lea     r9, [r15+438h]
0x18001c7a3  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rax
0x18001c7a8  lea     r8, aLsLsLsLs; "%ls\\%ls\\%ls\\%ls"
0x18001c7af  mov     [rsp+2E0h+phkResult], rcx
0x18001c7b4  mov     edx, 104h; unsigned __int64
0x18001c7b9  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x18001c7bd  mov     [rsp+2E0h+cbMaxValueLen], r12d
0x18001c7c2  mov     [rsp+2E0h+Type], r12d
0x18001c7c7  mov     [rbp+1E0h+hKey], r12
0x18001c7cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c7d0  mov     ebx, eax
0x18001c7d2  test    eax, eax
0x18001c7d4  js      loc_18001CA87
0x18001c7da  lea     rax, [rbp+1E0h+hKey]
0x18001c7de  mov     r9d, 20019h; samDesired
0x18001c7e4  xor     r8d, r8d; ulOptions
0x18001c7e7  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18001c7ec  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x18001c7f0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c7f7  call    cs:__imp_RegOpenKeyExW
0x18001c7fd  mov     ebx, eax
0x18001c7ff  test    eax, eax
0x18001c801  jz      short loc_18001C829
0x18001c803  cmp     eax, 2
0x18001c806  jnz     short loc_18001C813
0x18001c808  mov     byte ptr [rdi], 1
0x18001c80b  mov     ebx, r12d
0x18001c80e  jmp     loc_18001CA87
0x18001c813  test    eax, eax
0x18001c815  jle     loc_18001CA87
0x18001c81b  movzx   ebx, ax
0x18001c81e  or      ebx, 80070000h
0x18001c824  jmp     loc_18001CA87
0x18001c829  mov     rcx, [rbp+1E0h+hKey]; hKey
0x18001c82d  lea     rax, [rsp+2E0h+cbMaxValueLen]
0x18001c832  mov     [rsp+2E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18001c837  xor     r9d, r9d; lpReserved
0x18001c83a  mov     [rsp+2E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18001c83f  xor     r8d, r8d; lpcchClass
0x18001c842  mov     [rsp+2E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18001c847  xor     edx, edx; lpClass
0x18001c849  lea     rax, [rsp+2E0h+cbMaxValueNameLen]
0x18001c84e  mov     [rsp+2E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18001c853  lea     rax, [rsp+2E0h+cValues]
0x18001c858  mov     [rsp+2E0h+lpcValues], rax; lpcValues
0x18001c85d  mov     [rsp+2E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18001c862  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18001c867  mov     [rsp+2E0h+phkResult], r12; lpcSubKeys
0x18001c86c  call    cs:__imp_RegQueryInfoKeyW
0x18001c872  mov     ebx, eax
0x18001c874  test    eax, eax
0x18001c876  jnz     short loc_18001C815
0x18001c878  mov     eax, [r15+6B8h]
0x18001c87f  add     eax, [r15+688h]
0x18001c886  cmp     eax, [rsp+2E0h+cValues]
0x18001c88a  jnz     loc_18001C808
0x18001c890  mov     ebx, [rsp+2E0h+cbMaxValueNameLen]
0x18001c894  inc     ebx
0x18001c896  add     rbx, rbx
0x18001c899  call    cs:__imp_GetProcessHeap
0x18001c89f  mov     r14d, 8
0x18001c8a5  mov     r8, rbx; dwBytes
0x18001c8a8  mov     edx, r14d; dwFlags
0x18001c8ab  mov     rcx, rax; hHeap
0x18001c8ae  call    cs:__imp_HeapAlloc
0x18001c8b4  mov     rsi, rax
0x18001c8b7  test    rax, rax
0x18001c8ba  jnz     short loc_18001C8C6
0x18001c8bc  mov     ebx, 8007000Eh
0x18001c8c1  jmp     loc_18001CA87
0x18001c8c6  mov     ebx, [rsp+2E0h+cbMaxValueLen]
0x18001c8ca  call    cs:__imp_GetProcessHeap
0x18001c8d0  lea     r8, [rbx+2]; dwBytes
0x18001c8d4  mov     edx, r14d; dwFlags
0x18001c8d7  mov     rcx, rax; hHeap
0x18001c8da  call    cs:__imp_HeapAlloc
0x18001c8e0  mov     r14, rax
0x18001c8e3  test    rax, rax
0x18001c8e6  jnz     short loc_18001C8F2
0x18001c8e8  mov     ebx, 8007000Eh
0x18001c8ed  jmp     loc_18001CA5A
0x18001c8f2  mov     r13d, r12d
0x18001c8f5  cmp     [rsp+2E0h+cValues], r12d
0x18001c8fa  jbe     loc_18001CA54
0x18001c900  mov     eax, [rsp+2E0h+cbMaxValueNameLen]
0x18001c904  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x18001c909  mov     rcx, [rbp+1E0h+hKey]; hKey
0x18001c90d  inc     eax
0x18001c90f  mov     [rsp+2E0h+cchValueName], eax
0x18001c913  mov     r8, rsi; lpValueName
0x18001c916  mov     eax, [rsp+2E0h+cbMaxValueLen]
0x18001c91a  mov     edx, r13d; dwIndex
0x18001c91d  mov     [rsp+2E0h+cbData], eax
0x18001c921  lea     rax, [rsp+2E0h+cbData]
0x18001c926  mov     [rsp+2E0h+lpcValues], rax; lpcbData
0x18001c92b  lea     rax, [rsp+2E0h+Type]
0x18001c930  mov     [rsp+2E0h+lpcbMaxClassLen], r14; lpData
0x18001c935  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rax; lpType
0x18001c93a  mov     [rsp+2E0h+phkResult], r12; lpReserved
0x18001c93f  call    cs:__imp_RegEnumValueW
0x18001c945  mov     ebx, eax
0x18001c947  test    eax, eax
0x18001c949  jnz     loc_18001CAC2
0x18001c94f  mov     ecx, [rsp+2E0h+cbData]
0x18001c953  shr     rcx, 1
0x18001c956  mov     [r14+rcx*2], r12w
0x18001c95b  cmp     [rsp+2E0h+Type], 1
0x18001c960  jnz     loc_18001CA3E
0x18001c966  lea     rbx, [r15+678h]
0x18001c96d  mov     rdx, rsi; unsigned __int16 *
0x18001c970  mov     rcx, rbx; this
0x18001c973  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x18001c978  test    rax, rax
0x18001c97b  jz      short loc_18001C9AD
0x18001c97d  mov     rdx, rsi; unsigned __int16 *
0x18001c980  mov     rcx, rbx; this
0x18001c983  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x18001c988  mov     rcx, r14
0x18001c98b  sub     rax, r14
0x18001c98e  movzx   edx, word ptr [rcx]
0x18001c991  movzx   r8d, word ptr [rcx+rax]
0x18001c996  sub     edx, r8d
0x18001c999  jnz     short loc_18001C9A4
0x18001c99b  add     rcx, 2
0x18001c99f  test    r8d, r8d
0x18001c9a2  jnz     short loc_18001C98E
0x18001c9a4  mov     [rsp+2E0h+var_280], 1
0x18001c9a9  test    edx, edx
0x18001c9ab  jz      short loc_18001C9B2
0x18001c9ad  mov     [rsp+2E0h+var_280], r12b
0x18001c9b2  lea     rbx, [r15+6A8h]
0x18001c9b9  mov     rdx, rsi; unsigned __int16 *
0x18001c9bc  mov     rcx, rbx; this
0x18001c9bf  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x18001c9c4  test    rax, rax
0x18001c9c7  jz      short loc_18001C9F7
0x18001c9c9  mov     rdx, rsi; unsigned __int16 *
0x18001c9cc  mov     rcx, rbx; this
0x18001c9cf  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x18001c9d4  mov     rcx, r14
0x18001c9d7  sub     rax, r14
0x18001c9da  movzx   edx, word ptr [rcx]
0x18001c9dd  movzx   r8d, word ptr [rcx+rax]
0x18001c9e2  sub     edx, r8d
0x18001c9e5  jnz     short loc_18001C9F0
0x18001c9e7  add     rcx, 2
0x18001c9eb  test    r8d, r8d
0x18001c9ee  jnz     short loc_18001C9DA
0x18001c9f0  test    edx, edx
0x18001c9f2  jnz     short loc_18001C9F7
0x18001c9f4  mov     r12b, 1
0x18001c9f7  mov     rdx, rsi; unsigned __int16 *
0x18001c9fa  mov     rcx, rbx; this
0x18001c9fd  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x18001ca02  test    rax, rax
0x18001ca05  jz      short loc_18001CA29
0x18001ca07  mov     rdx, rsi; unsigned __int16 *
0x18001ca0a  mov     rcx, rbx; this
0x18001ca0d  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x18001ca12  mov     rdx, rax; String2
0x18001ca15  lea     rcx, aFalse_0; "FALSE"
0x18001ca1c  call    wcscmp_0
0x18001ca21  test    eax, eax
0x18001ca23  jnz     short loc_18001CA29
0x18001ca25  mov     al, 1
0x18001ca27  jmp     short loc_18001CA2B
0x18001ca29  xor     al, al
0x18001ca2b  cmp     [rsp+2E0h+var_280], 0
0x18001ca30  jnz     short loc_18001CA43
0x18001ca32  test    r12b, r12b
0x18001ca35  jnz     short loc_18001CA43
0x18001ca37  xor     r12d, r12d
0x18001ca3a  test    al, al
0x18001ca3c  jnz     short loc_18001CA46
0x18001ca3e  mov     byte ptr [rdi], 1
0x18001ca41  jmp     short loc_18001CA57
0x18001ca43  xor     r12d, r12d
0x18001ca46  inc     r13d
0x18001ca49  cmp     r13d, [rsp+2E0h+cValues]
0x18001ca4e  jb      loc_18001C900
0x18001ca54  mov     [rdi], r12b
0x18001ca57  mov     ebx, r12d
0x18001ca5a  call    cs:__imp_GetProcessHeap
0x18001ca60  mov     r8, rsi; lpMem
0x18001ca63  xor     edx, edx; dwFlags
0x18001ca65  mov     rcx, rax; hHeap
0x18001ca68  call    cs:__imp_HeapFree
0x18001ca6e  test    r14, r14
0x18001ca71  jz      short loc_18001CA87
0x18001ca73  call    cs:__imp_GetProcessHeap
0x18001ca79  mov     r8, r14; lpMem
0x18001ca7c  xor     edx, edx; dwFlags
0x18001ca7e  mov     rcx, rax; hHeap
0x18001ca81  call    cs:__imp_HeapFree
0x18001ca87  mov     rcx, [rbp+1E0h+hKey]; hKey
0x18001ca8b  test    rcx, rcx
0x18001ca8e  jz      short loc_18001CA96
0x18001ca90  call    cs:__imp_RegCloseKey
0x18001ca96  mov     eax, ebx
0x18001ca98  mov     rcx, [rbp+1E0h+var_40]
0x18001ca9f  xor     rcx, rsp; StackCookie
0x18001caa2  call    __security_check_cookie
0x18001caa7  mov     rbx, [rsp+2E0h+arg_10]
0x18001caaf  add     rsp, 2B0h
0x18001cab6  pop     r15
0x18001cab8  pop     r14
0x18001caba  pop     r13
0x18001cabc  pop     r12
0x18001cabe  pop     rdi
0x18001cabf  pop     rsi
0x18001cac0  pop     rbp
0x18001cac1  retn
0x18001cac2  jle     short loc_18001CA5A
0x18001cac4  movzx   ebx, ax
0x18001cac7  or      ebx, 80070000h
0x18001cacd  jmp     short loc_18001CA5A
```
