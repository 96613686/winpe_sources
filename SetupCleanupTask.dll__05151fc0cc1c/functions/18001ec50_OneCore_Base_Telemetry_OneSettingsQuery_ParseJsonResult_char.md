# OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(char *)

- ea: `0x18001ec50`
- end: `0x18001ef07`
- name: `?ParseJsonResult@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAD@Z`
- size: `695`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *this, char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001ef10`
- `0x180021ca8`

## callees

- `0x18001a124`
- `0x18001a3d0`
- `0x18001a5b4`
- `0x18001ec50`
- `0x18001faec`
- `0x1800322de`

## import_xrefs

- `msvcrt!_wtoi` at `0x18001ee3a`
- `msvcrt!_wtoi` at `0x18001ee3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ecbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ecbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ecaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ecf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ed30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001edbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ecaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ecf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ed30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001edbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ed03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ed3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ed8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001edab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ed03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ed3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ed8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001edab`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ec9e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001eceb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ec9e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001eceb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        char *a2)
{
  unsigned __int64 *v4; // rsi
  unsigned int cchWideChar; // edi
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  WCHAR *v8; // rbx
  int JsonObjectAlloc; // ebx
  HANDLE v10; // rax
  void *v11; // rbx
  HANDLE v12; // rax
  HANDLE *v13; // rdi
  void *v14; // r8
  void *v15; // r8
  HANDLE v16; // rax
  unsigned __int64 v17; // r15
  const wchar_t ***v18; // rax
  const wchar_t **v19; // rbx
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rax
  unsigned __int64 *v22; // r13
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // r14
  __int64 *v25; // rdx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v31; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-8h]
  unsigned __int64 *v33; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int64 *v34; // [rsp+98h] [rbp+58h] BYREF

  v34 = 0;
  lpMem = 0;
  v33 = 0;
  v31 = 0;
  v4 = 0;
  cchWideChar = MultiByteToWideChar(0xFDE9u, 0, a2, -1, 0, 0);
  if ( !cchWideChar )
  {
LABEL_6:
    JsonObjectAlloc = -2147024883;
    goto LABEL_11;
  }
  ProcessHeap = GetProcessHeap();
  lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 0, 2LL * cchWideChar);
  v8 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    if ( MultiByteToWideChar(0xFDE9u, 0, a2, -1, lpWideCharStr, cchWideChar) )
    {
      lpMem = v8;
      JsonObjectAlloc = JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc((JsonHelpersInternal::JsonReader *)&v31);
      if ( JsonObjectAlloc >= 0 )
      {
        v11 = lpMem;
        if ( lpMem )
        {
          v12 = GetProcessHeap();
          HeapFree(v12, 0, v11);
          lpMem = 0;
        }
        v4 = v33;
        JsonObjectAlloc = 0;
        v34 = v33;
        v31 = 0;
        v33 = 0;
      }
      goto LABEL_11;
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v8);
    goto LABEL_6;
  }
  JsonObjectAlloc = -2147024882;
LABEL_11:
  CleanupJsonObject((__int64 *)&v33);
  if ( JsonObjectAlloc < 0 )
    goto LABEL_37;
  v13 = (HANDLE *)((char *)this + 1608);
  RtlNameValueArray::Clear((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1608));
  v14 = (void *)*((_QWORD *)this + 206);
  if ( v14 )
    HeapFree(*v13, 0, v14);
  *(_OWORD *)v13 = 0;
  *(_OWORD *)((char *)this + 1624) = 0;
  *(_OWORD *)((char *)this + 1640) = 0;
  v15 = (void *)*((_QWORD *)this + 206);
  if ( v15 )
    HeapFree(0, 0, v15);
  *(_OWORD *)v13 = 0;
  *(_OWORD *)((char *)this + 1624) = 0;
  *(_OWORD *)((char *)this + 1640) = 0;
  v16 = GetProcessHeap();
  *((_QWORD *)this + 205) = 16;
  v17 = 0;
  *v13 = v16;
  *((_QWORD *)this + 203) = 0;
  *((_QWORD *)this + 204) = 0;
  *((_QWORD *)this + 206) = 0;
  *((_QWORD *)this + 202) = 8;
  if ( !v4[2] )
  {
LABEL_36:
    JsonObjectAlloc = 0;
    goto LABEL_37;
  }
  while ( 1 )
  {
    v18 = 0;
    if ( v17 < v4[2] )
    {
      if ( !is_mul_ok(v4[1], v17) || (v18 = (const wchar_t ***)(v4[5] + v4[1] * v17), (unsigned __int64)v18 < v4[5]) )
        v18 = 0;
    }
    v19 = *v18;
    if ( !wcscmp_0(**v18, L"refreshInterval") )
    {
      v20 = v19[1];
      if ( !*(_DWORD *)v20 )
        *((_DWORD *)this + 6) = _wtoi(*((const wchar_t **)v20 + 1));
      goto LABEL_35;
    }
    if ( !wcscmp_0(*v19, L"settings") )
    {
      v21 = v19[1];
      if ( *(_DWORD *)v21 != 5 )
      {
        JsonObjectAlloc = -2147418113;
        goto LABEL_37;
      }
      v22 = (unsigned __int64 *)*((_QWORD *)v21 + 1);
      v23 = v22[2];
      if ( v23 )
        break;
    }
LABEL_35:
    if ( ++v17 >= v4[2] )
      goto LABEL_36;
  }
  v24 = 0;
  while ( 1 )
  {
    v25 = 0;
    if ( v24 < v23 )
    {
      v26 = v22[1] * v24;
      if ( !is_mul_ok(v22[1], v24) || (v27 = v22[5], v25 = (__int64 *)(v27 + v26), v27 + v26 < v27) )
        v25 = 0;
    }
    v28 = *v25;
    v29 = *(_QWORD *)(v28 + 8);
    if ( !*(_DWORD *)v29 )
    {
      JsonObjectAlloc = RtlNameValueArray::Append(
                          (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1608),
                          *(const unsigned __int16 **)v28,
                          *(const unsigned __int16 **)(v29 + 8));
      if ( JsonObjectAlloc < 0 )
        break;
    }
    v23 = v22[2];
    if ( ++v24 >= v23 )
      goto LABEL_35;
  }
LABEL_37:
  CleanupJsonObject((__int64 *)&v34);
  return (unsigned int)JsonObjectAlloc;
}

```

## disassembly

```asm
0x18001ec50  mov     [rsp-38h+arg_0], rbx
0x18001ec55  push    rbp
0x18001ec56  push    rsi
0x18001ec57  push    rdi
0x18001ec58  push    r12
0x18001ec5a  push    r13
0x18001ec5c  push    r14
0x18001ec5e  push    r15
0x18001ec60  mov     rbp, rsp
0x18001ec63  sub     rsp, 40h
0x18001ec67  xor     r13d, r13d
0x18001ec6a  mov     r14, rdx
0x18001ec6d  mov     r12, rcx
0x18001ec70  mov     [rsp+40h+cchWideChar], r13d; cchWideChar
0x18001ec75  mov     r8, rdx; lpMultiByteStr
0x18001ec78  mov     [rsp+40h+lpWideCharStr], r13; lpWideCharStr
0x18001ec7d  or      r15d, 0FFFFFFFFh
0x18001ec81  mov     [rbp+arg_18], r13
0x18001ec85  mov     r9d, r15d; cbMultiByte
0x18001ec88  mov     [rbp+lpMem], r13
0x18001ec8c  xor     edx, edx; dwFlags
0x18001ec8e  mov     [rbp+arg_10], r13
0x18001ec92  mov     ecx, 0FDE9h; CodePage
0x18001ec97  mov     [rbp+var_10], r13
0x18001ec9b  mov     esi, r13d
0x18001ec9e  call    cs:__imp_MultiByteToWideChar
0x18001eca4  mov     edi, eax
0x18001eca6  test    eax, eax
0x18001eca8  jz      short loc_18001ED09
0x18001ecaa  mov     ebx, edi
0x18001ecac  add     rbx, rbx
0x18001ecaf  call    cs:__imp_GetProcessHeap
0x18001ecb5  mov     r8, rbx; dwBytes
0x18001ecb8  xor     edx, edx; dwFlags
0x18001ecba  mov     rcx, rax; hHeap
0x18001ecbd  call    cs:__imp_HeapAlloc
0x18001ecc3  mov     rbx, rax
0x18001ecc6  test    rax, rax
0x18001ecc9  jnz     short loc_18001ECD5
0x18001eccb  mov     ebx, 8007000Eh
0x18001ecd0  jmp     loc_18001ED5B
0x18001ecd5  mov     [rsp+40h+cchWideChar], edi; cchWideChar
0x18001ecd9  mov     r9d, r15d; cbMultiByte
0x18001ecdc  mov     r8, r14; lpMultiByteStr
0x18001ecdf  mov     [rsp+40h+lpWideCharStr], rbx; lpWideCharStr
0x18001ece4  xor     edx, edx; dwFlags
0x18001ece6  mov     ecx, 0FDE9h; CodePage
0x18001eceb  call    cs:__imp_MultiByteToWideChar
0x18001ecf1  test    eax, eax
0x18001ecf3  jnz     short loc_18001ED10
0x18001ecf5  call    cs:__imp_GetProcessHeap
0x18001ecfb  mov     r8, rbx; lpMem
0x18001ecfe  xor     edx, edx; dwFlags
0x18001ed00  mov     rcx, rax; hHeap
0x18001ed03  call    cs:__imp_HeapFree
0x18001ed09  mov     ebx, 8007000Dh
0x18001ed0e  jmp     short loc_18001ED5B
0x18001ed10  lea     rdx, [rbp+arg_10]
0x18001ed14  mov     [rbp+lpMem], rbx
0x18001ed18  lea     rcx, [rbp+var_10]; this
0x18001ed1c  call    ?ReadJsonObjectAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(RtlArray<JsonKeyValuePair *> * *)
0x18001ed21  mov     ebx, eax
0x18001ed23  test    eax, eax
0x18001ed25  js      short loc_18001ED5B
0x18001ed27  mov     rbx, [rbp+lpMem]
0x18001ed2b  test    rbx, rbx
0x18001ed2e  jz      short loc_18001ED48
0x18001ed30  call    cs:__imp_GetProcessHeap
0x18001ed36  mov     r8, rbx; lpMem
0x18001ed39  xor     edx, edx; dwFlags
0x18001ed3b  mov     rcx, rax; hHeap
0x18001ed3e  call    cs:__imp_HeapFree
0x18001ed44  mov     [rbp+lpMem], r13
0x18001ed48  mov     rsi, [rbp+arg_10]
0x18001ed4c  mov     ebx, r13d
0x18001ed4f  mov     [rbp+arg_18], rsi
0x18001ed53  mov     [rbp+var_10], r13
0x18001ed57  mov     [rbp+arg_10], r13
0x18001ed5b  lea     rcx, [rbp+arg_10]
0x18001ed5f  call    ?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)
0x18001ed64  test    ebx, ebx
0x18001ed66  js      loc_18001EEDD
0x18001ed6c  lea     rdi, [r12+648h]
0x18001ed74  mov     rcx, rdi; this
0x18001ed77  call    ?Clear@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Clear(void)
0x18001ed7c  mov     r8, [rdi+28h]; lpMem
0x18001ed80  test    r8, r8
0x18001ed83  jz      short loc_18001ED90
0x18001ed85  mov     rcx, [rdi]; hHeap
0x18001ed88  xor     edx, edx; dwFlags
0x18001ed8a  call    cs:__imp_HeapFree
0x18001ed90  xorps   xmm0, xmm0
0x18001ed93  movups  xmmword ptr [rdi], xmm0
0x18001ed96  movups  xmmword ptr [rdi+10h], xmm0
0x18001ed9a  movups  xmmword ptr [rdi+20h], xmm0
0x18001ed9e  mov     r8, [rdi+28h]; lpMem
0x18001eda2  test    r8, r8
0x18001eda5  jz      short loc_18001EDB1
0x18001eda7  xor     edx, edx; dwFlags
0x18001eda9  xor     ecx, ecx; hHeap
0x18001edab  call    cs:__imp_HeapFree
0x18001edb1  xorps   xmm0, xmm0
0x18001edb4  movups  xmmword ptr [rdi], xmm0
0x18001edb7  movups  xmmword ptr [rdi+10h], xmm0
0x18001edbb  movups  xmmword ptr [rdi+20h], xmm0
0x18001edbf  call    cs:__imp_GetProcessHeap
0x18001edc5  mov     qword ptr [rdi+20h], 10h
0x18001edcd  mov     r15, r13
0x18001edd0  mov     [rdi], rax
0x18001edd3  mov     [rdi+10h], r13
0x18001edd7  mov     [rdi+18h], r13
0x18001eddb  mov     [rdi+28h], r13
0x18001eddf  mov     qword ptr [rdi+8], 8
0x18001ede7  cmp     [rsi+10h], r13
0x18001edeb  jbe     loc_18001EEDA
0x18001edf1  mov     rax, r13
0x18001edf4  cmp     r15, [rsi+10h]
0x18001edf8  jnb     short loc_18001EE13
0x18001edfa  mov     rax, r15
0x18001edfd  mul     qword ptr [rsi+8]
0x18001ee01  test    rdx, rdx
0x18001ee04  jnz     short loc_18001EE10
0x18001ee06  add     rax, [rsi+28h]
0x18001ee0a  cmp     rax, [rsi+28h]
0x18001ee0e  jnb     short loc_18001EE13
0x18001ee10  mov     rax, r13
0x18001ee13  mov     rbx, [rax]
0x18001ee16  lea     rdx, aRefreshinterva; "refreshInterval"
0x18001ee1d  mov     rcx, [rbx]; String1
0x18001ee20  call    wcscmp_0
0x18001ee25  test    eax, eax
0x18001ee27  jnz     short loc_18001EE4A
0x18001ee29  mov     rcx, [rbx+8]
0x18001ee2d  cmp     [rcx], r13d
0x18001ee30  jnz     loc_18001EECD
0x18001ee36  mov     rcx, [rcx+8]; String
0x18001ee3a  call    cs:__imp__wtoi
0x18001ee40  mov     [r12+18h], eax
0x18001ee45  jmp     loc_18001EECD
0x18001ee4a  mov     rcx, [rbx]; String1
0x18001ee4d  lea     rdx, aSettings; "settings"
0x18001ee54  call    wcscmp_0
0x18001ee59  test    eax, eax
0x18001ee5b  jnz     short loc_18001EECD
0x18001ee5d  mov     rax, [rbx+8]
0x18001ee61  cmp     dword ptr [rax], 5
0x18001ee64  jnz     loc_18001EF00
0x18001ee6a  mov     r13, [rax+8]
0x18001ee6e  mov     rax, [r13+10h]
0x18001ee72  test    rax, rax
0x18001ee75  jz      short loc_18001EECA
0x18001ee77  xor     r14d, r14d
0x18001ee7a  xor     edx, edx
0x18001ee7c  cmp     r14, rax
0x18001ee7f  jnb     short loc_18001EE9C
0x18001ee81  mov     rax, r14
0x18001ee84  mul     qword ptr [r13+8]
0x18001ee88  test    rdx, rdx
0x18001ee8b  jnz     short loc_18001EE9A
0x18001ee8d  mov     rcx, [r13+28h]
0x18001ee91  lea     rdx, [rcx+rax]
0x18001ee95  cmp     rdx, rcx
0x18001ee98  jnb     short loc_18001EE9C
0x18001ee9a  xor     edx, edx
0x18001ee9c  mov     rdx, [rdx]
0x18001ee9f  mov     r8, [rdx+8]
0x18001eea3  cmp     dword ptr [r8], 0
0x18001eea7  jnz     short loc_18001EEBE
0x18001eea9  mov     r8, [r8+8]; unsigned __int16 *
0x18001eead  mov     rcx, rdi; this
0x18001eeb0  mov     rdx, [rdx]; unsigned __int16 *
0x18001eeb3  call    ?Append@RtlNameValueArray@@QEAAJPEBG0@Z; RtlNameValueArray::Append(ushort const *,ushort const *)
0x18001eeb8  mov     ebx, eax
0x18001eeba  test    eax, eax
0x18001eebc  js      short loc_18001EEDD
0x18001eebe  mov     rax, [r13+10h]
0x18001eec2  inc     r14
0x18001eec5  cmp     r14, rax
0x18001eec8  jb      short loc_18001EE7A
0x18001eeca  xor     r13d, r13d
0x18001eecd  inc     r15
0x18001eed0  cmp     r15, [rsi+10h]
0x18001eed4  jb      loc_18001EDF1
0x18001eeda  mov     ebx, r13d
0x18001eedd  lea     rcx, [rbp+arg_18]
0x18001eee1  call    ?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)
0x18001eee6  mov     eax, ebx
0x18001eee8  mov     rbx, [rsp+40h+arg_0]
0x18001eef0  add     rsp, 40h
0x18001eef4  pop     r15
0x18001eef6  pop     r14
0x18001eef8  pop     r13
0x18001eefa  pop     r12
0x18001eefc  pop     rdi
0x18001eefd  pop     rsi
0x18001eefe  pop     rbp
0x18001eeff  retn
0x18001ef00  mov     ebx, 8000FFFFh
0x18001ef05  jmp     short loc_18001EEDD
```
