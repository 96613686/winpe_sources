# OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(ushort const *,ushort * *)

- ea: `0x18001a878`
- end: `0x18001aacb`
- name: `?CreateHeaders@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAPEAG@Z`
- size: `595`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001ae7c`
- `0x180021ca8`

## callees

- `0x180003850`
- `0x18001a878`
- `0x180022bd4`
- `0x180022f34`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a92e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a9be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a92e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a9be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a954`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aa69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a954`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aa69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a943`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a9db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aa58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aa8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a943`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a9db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aa58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aa8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a9e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aa98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a9e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aa98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned int v4; // edi
  void *v5; // rbx
  LSTATUS ValueW; // eax
  bool v7; // sf
  bool v8; // cc
  unsigned __int64 v9; // rsi
  HANDLE ProcessHeap; // rax
  const unsigned __int16 *v11; // r8
  unsigned __int64 v12; // rsi
  LSTATUS v13; // eax
  HANDLE v14; // rax
  _WORD *v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  HANDLE v18; // rax
  HANDLE v19; // rax
  unsigned int pvData; // [rsp+28h] [rbp-D8h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  PVOID v24; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  pcbData = 0;
  v23 = 0;
  v24 = 0;
  v4 = 0;
  v5 = 0;
  if ( (int)StringCchPrintfW(
              SubKey,
              0x104u,
              L"%ls\\%ls\\%ls",
              (char *)this + 1080,
              (char *)this + 40,
              (char *)this + 560) >= 0 )
  {
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ETag", 2u, 0, 0, &pcbData);
    v7 = ValueW < 0;
    v8 = ValueW <= 0;
    if ( !ValueW )
    {
      v9 = pcbData + 30;
      ProcessHeap = GetProcessHeap();
      v5 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v9);
      if ( !v5 )
      {
LABEL_4:
        v12 = 0;
        goto LABEL_23;
      }
      if ( (int)StringCbCopyExW((unsigned __int16 *)v5, v9, v11, (unsigned __int16 **)&v24, &v23, pvData) < 0 )
      {
LABEL_11:
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v5);
        v5 = 0;
        goto LABEL_4;
      }
      pcbData = v23;
      v13 = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ETag", 2u, 0, v24, &pcbData);
      v7 = v13 < 0;
      v8 = v13 <= 0;
      if ( !v13 )
        goto LABEL_13;
    }
    if ( !v8 )
      v7 = 1;
    if ( v7 )
    {
      if ( v5 )
        goto LABEL_11;
      goto LABEL_18;
    }
  }
  if ( v5 )
  {
LABEL_13:
    v15 = v5;
    v16 = 0x7FFFFFFF;
    do
    {
      if ( !*v15 )
        break;
      ++v15;
      --v16;
    }
    while ( v16 );
    v4 = v16 == 0 ? 0x80070057 : 0;
    v17 = (0x7FFFFFFF - v16) & ((unsigned __int128)-(__int128)(unsigned __int64)v16 >> 64);
    if ( !v16 )
      goto LABEL_25;
    goto LABEL_19;
  }
LABEL_18:
  v17 = 0;
LABEL_19:
  v12 = v17 + 1;
  if ( !v5 )
    v12 = v17;
  if ( v12 )
  {
    v18 = GetProcessHeap();
    *a3 = (unsigned __int16 *)HeapAlloc(v18, 8u, 2 * v12);
  }
LABEL_23:
  if ( v5 )
  {
    v4 = StringCchCopyW(*a3, v12, (const unsigned __int16 *)v5);
LABEL_25:
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  return v4;
}

```

## disassembly

```asm
0x18001a878  mov     [rsp-8+arg_8], rbx
0x18001a87d  mov     [rsp-8+arg_18], rsi
0x18001a882  push    rbp
0x18001a883  push    rdi
0x18001a884  push    r12
0x18001a886  push    r14
0x18001a888  push    r15
0x18001a88a  lea     rbp, [rsp-180h]
0x18001a892  sub     rsp, 280h
0x18001a899  mov     rax, cs:__security_cookie
0x18001a8a0  xor     rax, rsp
0x18001a8a3  mov     [rbp+1A0h+var_30], rax
0x18001a8aa  xor     r12d, r12d
0x18001a8ad  lea     rdx, [rcx+28h]
0x18001a8b1  lea     rax, [rcx+230h]
0x18001a8b8  mov     [rsp+2A0h+var_260], r12d
0x18001a8bd  mov     [rsp+2A0h+pvData], rax
0x18001a8c2  lea     r9, [rcx+438h]
0x18001a8c9  mov     [rsp+2A0h+pdwType], rdx
0x18001a8ce  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x18001a8d3  mov     r15, r8
0x18001a8d6  mov     [rsp+2A0h+var_258], r12
0x18001a8db  mov     edx, 104h; unsigned __int64
0x18001a8e0  mov     [rsp+2A0h+var_250], r12
0x18001a8e5  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x18001a8ec  mov     edi, r12d
0x18001a8ef  mov     ebx, r12d
0x18001a8f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a8f7  test    eax, eax
0x18001a8f9  js      loc_18001A9F7
0x18001a8ff  lea     rax, [rsp+2A0h+var_260]
0x18001a904  mov     r14, 0FFFFFFFF80000002h
0x18001a90b  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18001a910  lea     r9d, [r12+2]; dwFlags
0x18001a915  mov     [rsp+2A0h+pvData], r12; unsigned int
0x18001a91a  lea     r8, aEtag; "ETag"
0x18001a921  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18001a926  mov     [rsp+2A0h+pdwType], r12; pdwType
0x18001a92b  mov     rcx, r14; hkey
0x18001a92e  call    cs:__imp_RegGetValueW
0x18001a934  test    eax, eax
0x18001a936  jnz     loc_18001A9C8
0x18001a93c  mov     esi, [rsp+2A0h+var_260]
0x18001a940  add     esi, 1Eh
0x18001a943  call    cs:__imp_GetProcessHeap
0x18001a949  mov     r8d, esi; dwBytes
0x18001a94c  lea     edx, [r12+8]; dwFlags
0x18001a951  mov     rcx, rax; hHeap
0x18001a954  call    cs:__imp_HeapAlloc
0x18001a95a  mov     rbx, rax
0x18001a95d  test    rax, rax
0x18001a960  jnz     short loc_18001A96A
0x18001a962  mov     rsi, r12
0x18001a965  jmp     loc_18001AA75
0x18001a96a  lea     rax, [rsp+2A0h+var_258]
0x18001a96f  mov     rdx, rsi; unsigned __int64
0x18001a972  lea     r9, [rsp+2A0h+var_250]; unsigned __int16 **
0x18001a977  mov     [rsp+2A0h+pdwType], rax; unsigned __int64 *
0x18001a97c  mov     rcx, rbx; unsigned __int16 *
0x18001a97f  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001a984  test    eax, eax
0x18001a986  js      short loc_18001A9DB
0x18001a988  mov     eax, dword ptr [rsp+2A0h+var_258]
0x18001a98c  lea     r8, aEtag; "ETag"
0x18001a993  mov     [rsp+2A0h+var_260], eax
0x18001a997  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18001a99c  lea     rax, [rsp+2A0h+var_260]
0x18001a9a1  mov     r9d, 2; dwFlags
0x18001a9a7  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18001a9ac  mov     rcx, r14; hkey
0x18001a9af  mov     rax, [rsp+2A0h+var_250]
0x18001a9b4  mov     [rsp+2A0h+pvData], rax; pvData
0x18001a9b9  mov     [rsp+2A0h+pdwType], r12; pdwType
0x18001a9be  call    cs:__imp_RegGetValueW
0x18001a9c4  test    eax, eax
0x18001a9c6  jz      short loc_18001A9FC
0x18001a9c8  jle     short loc_18001A9D4
0x18001a9ca  movzx   eax, ax
0x18001a9cd  or      eax, 80070000h
0x18001a9d2  test    eax, eax
0x18001a9d4  jns     short loc_18001A9F7
0x18001a9d6  test    rbx, rbx
0x18001a9d9  jz      short loc_18001AA3E
0x18001a9db  call    cs:__imp_GetProcessHeap
0x18001a9e1  mov     r8, rbx; lpMem
0x18001a9e4  xor     edx, edx; dwFlags
0x18001a9e6  mov     rcx, rax; hHeap
0x18001a9e9  call    cs:__imp_HeapFree
0x18001a9ef  mov     rbx, r12
0x18001a9f2  jmp     loc_18001A962
0x18001a9f7  test    rbx, rbx
0x18001a9fa  jz      short loc_18001AA3E
0x18001a9fc  mov     r8d, 7FFFFFFFh
0x18001aa02  mov     rax, rbx
0x18001aa05  mov     ecx, r8d
0x18001aa08  cmp     [rax], r12w
0x18001aa0c  jz      short loc_18001AA18
0x18001aa0e  add     rax, 2
0x18001aa12  sub     rcx, 1
0x18001aa16  jnz     short loc_18001AA08
0x18001aa18  mov     rax, rcx
0x18001aa1b  neg     rax
0x18001aa1e  mov     rax, rcx
0x18001aa21  sbb     edi, edi
0x18001aa23  sub     r8, rcx
0x18001aa26  not     edi
0x18001aa28  and     edi, 80070057h
0x18001aa2e  neg     rax
0x18001aa31  sbb     rdx, rdx
0x18001aa34  and     rdx, r8
0x18001aa37  test    rcx, rcx
0x18001aa3a  jz      short loc_18001AA8A
0x18001aa3c  jmp     short loc_18001AA41
0x18001aa3e  mov     rdx, r12
0x18001aa41  test    rbx, rbx
0x18001aa44  lea     rsi, [rdx+1]
0x18001aa48  mov     r14, rbx
0x18001aa4b  cmovz   rsi, rdx
0x18001aa4f  test    rsi, rsi
0x18001aa52  jz      short loc_18001AA75
0x18001aa54  lea     rbx, [rsi+rsi]
0x18001aa58  call    cs:__imp_GetProcessHeap
0x18001aa5e  mov     r8, rbx; dwBytes
0x18001aa61  mov     edx, 8; dwFlags
0x18001aa66  mov     rcx, rax; hHeap
0x18001aa69  call    cs:__imp_HeapAlloc
0x18001aa6f  mov     [r15], rax
0x18001aa72  mov     rbx, r14
0x18001aa75  test    rbx, rbx
0x18001aa78  jz      short loc_18001AA9E
0x18001aa7a  mov     rcx, [r15]; unsigned __int16 *
0x18001aa7d  mov     r8, rbx; unsigned __int16 *
0x18001aa80  mov     rdx, rsi; unsigned __int64
0x18001aa83  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001aa88  mov     edi, eax
0x18001aa8a  call    cs:__imp_GetProcessHeap
0x18001aa90  mov     r8, rbx; lpMem
0x18001aa93  xor     edx, edx; dwFlags
0x18001aa95  mov     rcx, rax; hHeap
0x18001aa98  call    cs:__imp_HeapFree
0x18001aa9e  mov     eax, edi
0x18001aaa0  mov     rcx, [rbp+1A0h+var_30]
0x18001aaa7  xor     rcx, rsp; StackCookie
0x18001aaaa  call    __security_check_cookie
0x18001aaaf  lea     r11, [rsp+2A0h+var_20]
0x18001aab7  mov     rbx, [r11+38h]
0x18001aabb  mov     rsi, [r11+48h]
0x18001aabf  mov     rsp, r11
0x18001aac2  pop     r15
0x18001aac4  pop     r14
0x18001aac6  pop     r12
0x18001aac8  pop     rdi
0x18001aac9  pop     rbp
0x18001aaca  retn
```
