# OneCore::Base::Telemetry::OneSettingsQuery::HaveQueryParametersChanged(bool &)

- ea: `0x1800421b4`
- end: `0x18004254b`
- name: `?HaveQueryParametersChanged@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEA_N@Z`
- size: `919`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180046b54`

## callees

- `0x18001c5bc`
- `0x180042108`
- `0x1800421b4`
- `0x1800502ce`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800423bb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800423bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042273`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042273`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004250c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004250c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800422e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800422e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042315`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042346`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800424d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800424ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042315`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042346`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800424d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800424ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004232a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042356`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004232a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042356`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800424e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800424fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800424e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800424fd`

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
0x1800421b4  mov     [rsp-8+arg_10], rbx
0x1800421b9  push    rbp
0x1800421ba  push    rsi
0x1800421bb  push    rdi
0x1800421bc  push    r12
0x1800421be  push    r13
0x1800421c0  push    r14
0x1800421c2  push    r15
0x1800421c4  lea     rbp, [rsp-1B0h]
0x1800421cc  sub     rsp, 2B0h
0x1800421d3  mov     rax, cs:__security_cookie
0x1800421da  xor     rax, rsp
0x1800421dd  mov     [rbp+1E0h+var_40], rax
0x1800421e4  xor     r12d, r12d
0x1800421e7  lea     rax, [rcx+230h]
0x1800421ee  mov     r15, rcx
0x1800421f1  mov     [rsp+2E0h+cValues], r12d
0x1800421f6  mov     rdi, rdx
0x1800421f9  mov     [rsp+2E0h+cchValueName], r12d
0x1800421fe  add     rcx, 28h ; '('
0x180042202  mov     [rsp+2E0h+cbData], r12d
0x180042207  lea     rdx, aQueryparameter; "QueryParameters"
0x18004220e  mov     [rsp+2E0h+cbMaxValueNameLen], r12d
0x180042213  mov     [rsp+2E0h+lpcbMaxClassLen], rdx
0x180042218  lea     r9, [r15+438h]
0x18004221f  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rax
0x180042224  lea     r8, aLsLsLsLs; "%ls\\%ls\\%ls\\%ls"
0x18004222b  mov     [rsp+2E0h+phkResult], rcx
0x180042230  mov     edx, 104h; unsigned __int64
0x180042235  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x180042239  mov     [rsp+2E0h+cbMaxValueLen], r12d
0x18004223e  mov     [rsp+2E0h+Type], r12d
0x180042243  mov     [rbp+1E0h+hKey], r12
0x180042247  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004224c  mov     ebx, eax
0x18004224e  test    eax, eax
0x180042250  js      loc_180042503
0x180042256  lea     rax, [rbp+1E0h+hKey]
0x18004225a  mov     r9d, 20019h; samDesired
0x180042260  xor     r8d, r8d; ulOptions
0x180042263  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180042268  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x18004226c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042273  call    cs:__imp_RegOpenKeyExW
0x180042279  mov     ebx, eax
0x18004227b  test    eax, eax
0x18004227d  jz      short loc_1800422A5
0x18004227f  cmp     eax, 2
0x180042282  jnz     short loc_18004228F
0x180042284  mov     byte ptr [rdi], 1
0x180042287  mov     ebx, r12d
0x18004228a  jmp     loc_180042503
0x18004228f  test    eax, eax
0x180042291  jle     loc_180042503
0x180042297  movzx   ebx, ax
0x18004229a  or      ebx, 80070000h
0x1800422a0  jmp     loc_180042503
0x1800422a5  mov     rcx, [rbp+1E0h+hKey]; hKey
0x1800422a9  lea     rax, [rsp+2E0h+cbMaxValueLen]
0x1800422ae  mov     [rsp+2E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800422b3  xor     r9d, r9d; lpReserved
0x1800422b6  mov     [rsp+2E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800422bb  xor     r8d, r8d; lpcchClass
0x1800422be  mov     [rsp+2E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800422c3  xor     edx, edx; lpClass
0x1800422c5  lea     rax, [rsp+2E0h+cbMaxValueNameLen]
0x1800422ca  mov     [rsp+2E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800422cf  lea     rax, [rsp+2E0h+cValues]
0x1800422d4  mov     [rsp+2E0h+lpcValues], rax; lpcValues
0x1800422d9  mov     [rsp+2E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800422de  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800422e3  mov     [rsp+2E0h+phkResult], r12; lpcSubKeys
0x1800422e8  call    cs:__imp_RegQueryInfoKeyW
0x1800422ee  mov     ebx, eax
0x1800422f0  test    eax, eax
0x1800422f2  jnz     short loc_180042291
0x1800422f4  mov     eax, [r15+6B8h]
0x1800422fb  add     eax, [r15+688h]
0x180042302  cmp     eax, [rsp+2E0h+cValues]
0x180042306  jnz     loc_180042284
0x18004230c  mov     ebx, [rsp+2E0h+cbMaxValueNameLen]
0x180042310  inc     ebx
0x180042312  add     rbx, rbx
0x180042315  call    cs:__imp_GetProcessHeap
0x18004231b  mov     r14d, 8
0x180042321  mov     r8, rbx; dwBytes
0x180042324  mov     edx, r14d; dwFlags
0x180042327  mov     rcx, rax; hHeap
0x18004232a  call    cs:__imp_HeapAlloc
0x180042330  mov     rsi, rax
0x180042333  test    rax, rax
0x180042336  jnz     short loc_180042342
0x180042338  mov     ebx, 8007000Eh
0x18004233d  jmp     loc_180042503
0x180042342  mov     ebx, [rsp+2E0h+cbMaxValueLen]
0x180042346  call    cs:__imp_GetProcessHeap
0x18004234c  lea     r8, [rbx+2]; dwBytes
0x180042350  mov     edx, r14d; dwFlags
0x180042353  mov     rcx, rax; hHeap
0x180042356  call    cs:__imp_HeapAlloc
0x18004235c  mov     r14, rax
0x18004235f  test    rax, rax
0x180042362  jnz     short loc_18004236E
0x180042364  mov     ebx, 8007000Eh
0x180042369  jmp     loc_1800424D6
0x18004236e  mov     r13d, r12d
0x180042371  cmp     [rsp+2E0h+cValues], r12d
0x180042376  jbe     loc_1800424D0
0x18004237c  mov     eax, [rsp+2E0h+cbMaxValueNameLen]
0x180042380  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x180042385  mov     rcx, [rbp+1E0h+hKey]; hKey
0x180042389  inc     eax
0x18004238b  mov     [rsp+2E0h+cchValueName], eax
0x18004238f  mov     r8, rsi; lpValueName
0x180042392  mov     eax, [rsp+2E0h+cbMaxValueLen]
0x180042396  mov     edx, r13d; dwIndex
0x180042399  mov     [rsp+2E0h+cbData], eax
0x18004239d  lea     rax, [rsp+2E0h+cbData]
0x1800423a2  mov     [rsp+2E0h+lpcValues], rax; lpcbData
0x1800423a7  lea     rax, [rsp+2E0h+Type]
0x1800423ac  mov     [rsp+2E0h+lpcbMaxClassLen], r14; lpData
0x1800423b1  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rax; lpType
0x1800423b6  mov     [rsp+2E0h+phkResult], r12; lpReserved
0x1800423bb  call    cs:__imp_RegEnumValueW
0x1800423c1  mov     ebx, eax
0x1800423c3  test    eax, eax
0x1800423c5  jnz     loc_18004253E
0x1800423cb  mov     ecx, [rsp+2E0h+cbData]
0x1800423cf  shr     rcx, 1
0x1800423d2  mov     [r14+rcx*2], r12w
0x1800423d7  cmp     [rsp+2E0h+Type], 1
0x1800423dc  jnz     loc_1800424BA
0x1800423e2  lea     rbx, [r15+678h]
0x1800423e9  mov     rdx, rsi; unsigned __int16 *
0x1800423ec  mov     rcx, rbx; this
0x1800423ef  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x1800423f4  test    rax, rax
0x1800423f7  jz      short loc_180042429
0x1800423f9  mov     rdx, rsi; unsigned __int16 *
0x1800423fc  mov     rcx, rbx; this
0x1800423ff  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x180042404  mov     rcx, r14
0x180042407  sub     rax, r14
0x18004240a  movzx   edx, word ptr [rcx]
0x18004240d  movzx   r8d, word ptr [rcx+rax]
0x180042412  sub     edx, r8d
0x180042415  jnz     short loc_180042420
0x180042417  add     rcx, 2
0x18004241b  test    r8d, r8d
0x18004241e  jnz     short loc_18004240A
0x180042420  mov     [rsp+2E0h+var_280], 1
0x180042425  test    edx, edx
0x180042427  jz      short loc_18004242E
0x180042429  mov     [rsp+2E0h+var_280], r12b
0x18004242e  lea     rbx, [r15+6A8h]
0x180042435  mov     rdx, rsi; unsigned __int16 *
0x180042438  mov     rcx, rbx; this
0x18004243b  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x180042440  test    rax, rax
0x180042443  jz      short loc_180042473
0x180042445  mov     rdx, rsi; unsigned __int16 *
0x180042448  mov     rcx, rbx; this
0x18004244b  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x180042450  mov     rcx, r14
0x180042453  sub     rax, r14
0x180042456  movzx   edx, word ptr [rcx]
0x180042459  movzx   r8d, word ptr [rcx+rax]
0x18004245e  sub     edx, r8d
0x180042461  jnz     short loc_18004246C
0x180042463  add     rcx, 2
0x180042467  test    r8d, r8d
0x18004246a  jnz     short loc_180042456
0x18004246c  test    edx, edx
0x18004246e  jnz     short loc_180042473
0x180042470  mov     r12b, 1
0x180042473  mov     rdx, rsi; unsigned __int16 *
0x180042476  mov     rcx, rbx; this
0x180042479  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x18004247e  test    rax, rax
0x180042481  jz      short loc_1800424A5
0x180042483  mov     rdx, rsi; unsigned __int16 *
0x180042486  mov     rcx, rbx; this
0x180042489  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x18004248e  mov     rdx, rax; String2
0x180042491  lea     rcx, aFalse_0; "FALSE"
0x180042498  call    wcscmp_0
0x18004249d  test    eax, eax
0x18004249f  jnz     short loc_1800424A5
0x1800424a1  mov     al, 1
0x1800424a3  jmp     short loc_1800424A7
0x1800424a5  xor     al, al
0x1800424a7  cmp     [rsp+2E0h+var_280], 0
0x1800424ac  jnz     short loc_1800424BF
0x1800424ae  test    r12b, r12b
0x1800424b1  jnz     short loc_1800424BF
0x1800424b3  xor     r12d, r12d
0x1800424b6  test    al, al
0x1800424b8  jnz     short loc_1800424C2
0x1800424ba  mov     byte ptr [rdi], 1
0x1800424bd  jmp     short loc_1800424D3
0x1800424bf  xor     r12d, r12d
0x1800424c2  inc     r13d
0x1800424c5  cmp     r13d, [rsp+2E0h+cValues]
0x1800424ca  jb      loc_18004237C
0x1800424d0  mov     [rdi], r12b
0x1800424d3  mov     ebx, r12d
0x1800424d6  call    cs:__imp_GetProcessHeap
0x1800424dc  mov     r8, rsi; lpMem
0x1800424df  xor     edx, edx; dwFlags
0x1800424e1  mov     rcx, rax; hHeap
0x1800424e4  call    cs:__imp_HeapFree
0x1800424ea  test    r14, r14
0x1800424ed  jz      short loc_180042503
0x1800424ef  call    cs:__imp_GetProcessHeap
0x1800424f5  mov     r8, r14; lpMem
0x1800424f8  xor     edx, edx; dwFlags
0x1800424fa  mov     rcx, rax; hHeap
0x1800424fd  call    cs:__imp_HeapFree
0x180042503  mov     rcx, [rbp+1E0h+hKey]; hKey
0x180042507  test    rcx, rcx
0x18004250a  jz      short loc_180042512
0x18004250c  call    cs:__imp_RegCloseKey
0x180042512  mov     eax, ebx
0x180042514  mov     rcx, [rbp+1E0h+var_40]
0x18004251b  xor     rcx, rsp; StackCookie
0x18004251e  call    __security_check_cookie
0x180042523  mov     rbx, [rsp+2E0h+arg_10]
0x18004252b  add     rsp, 2B0h
0x180042532  pop     r15
0x180042534  pop     r14
0x180042536  pop     r13
0x180042538  pop     r12
0x18004253a  pop     rdi
0x18004253b  pop     rsi
0x18004253c  pop     rbp
0x18004253d  retn
0x18004253e  jle     short loc_1800424D6
0x180042540  movzx   ebx, ax
0x180042543  or      ebx, 80070000h
0x180042549  jmp     short loc_1800424D6
```
