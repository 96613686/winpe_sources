# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180017c70`
- end: `0x180018156`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `1254`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b1b0`

## callees

- `0x1800017b0`
- `0x180010460`
- `0x180013ad0`
- `0x180013af0`
- `0x180017c70`
- `0x1800187f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017d97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017ea4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017d97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017ea4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017d75`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017f60`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017d75`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017f60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180017ddd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180017e06`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180017e41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180017e74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180017ddd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180017e06`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180017e41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180017e74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001808d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001808d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018001`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018079`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018001`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018079`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rbp
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v10; // rcx
  WCHAR *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  const wchar_t *v14; // r8
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // rcx
  WCHAR *v18; // rdx
  WCHAR *v19; // rcx
  HANDLE v20; // rax
  void *v21; // rdi
  DWORD v22; // eax
  unsigned int v23; // r8d
  const char *v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rdx
  DWORD v27; // eax
  unsigned int LastError; // ebx
  unsigned int v29; // r8d
  int v30; // r14d
  __int64 v31; // rcx
  WCHAR *v32; // rax
  WCHAR *v33; // rax
  const wchar_t *v34; // rdx
  __int64 v35; // rsi
  WCHAR *v36; // rdx
  HANDLE v37; // rax
  unsigned int v38; // r8d
  const char *v39; // r9
  void *v40; // rbx
  int ValueFromSemaphore; // eax
  unsigned int v42; // r8d
  unsigned int v43; // esi
  unsigned int v44; // r8d
  const char *v45; // r9
  unsigned int v46; // r8d
  const char *v47; // r9
  unsigned int v49; // r8d
  const char *v50; // r9
  unsigned int v51; // r8d
  const char *v52; // r9
  unsigned int v53; // r8d
  const char *v54; // r9
  unsigned int v55; // r8d
  const char *v56; // r9
  unsigned int v57; // r8d
  const char *v58; // r9
  int PreviousCount; // [rsp+20h] [rbp-258h] BYREF
  int v60; // [rsp+24h] [rbp-254h] BYREF
  int v61; // [rsp+28h] [rbp-250h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v10 = v4 - 1;
  if ( v7 )
    v10 = v4;
  v11 = Name;
  *v10 = 0;
  v12 = 260;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v12;
  }
  while ( v12 );
  v13 = 260 - v12;
  if ( v12 )
  {
    v14 = L"_p0";
    v16 = v12;
    v15 = v13 == 260;
    v17 = 2147483646;
    v18 = &Name[v13];
    if ( !v15 )
    {
      do
      {
        if ( !v17 )
          break;
        if ( !*v14 )
          break;
        *v18++ = *v14++;
        --v17;
        --v16;
      }
      while ( v16 );
    }
    v19 = v18 - 1;
    if ( v16 )
      v19 = v18;
    *v19 = 0;
  }
  v20 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v20;
  if ( !v20 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v57, v58);
    return 0;
  }
  v61 = 0;
  v22 = WaitForSingleObject(v20, 0);
  if ( v22 == -1 )
  {
    v25 = 156;
    goto LABEL_38;
  }
  if ( v22 && v22 != 258 )
  {
    v26 = 157;
LABEL_65:
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v26, v23, (const char *)0x8000FFFFLL, PreviousCount);
    goto LABEL_66;
  }
  PreviousCount = 0;
  if ( !v22 )
  {
    if ( !ReleaseSemaphore(v21, 1, &PreviousCount) )
    {
      v25 = 165;
      goto LABEL_38;
    }
    ++PreviousCount;
    if ( ReleaseSemaphore(v21, 1, 0) || GetLastError() != 298 )
    {
      v26 = 170;
      goto LABEL_65;
    }
LABEL_42:
    v30 = PreviousCount;
    goto LABEL_43;
  }
  v60 = 0;
  if ( ReleaseSemaphore(v21, 1, &v60) )
  {
    if ( v60 )
    {
      v26 = 181;
      goto LABEL_65;
    }
    if ( ReleaseSemaphore(v21, 1, 0) || GetLastError() != 298 )
    {
      v26 = 184;
      goto LABEL_65;
    }
    v27 = WaitForSingleObject(v21, 0);
    if ( v27 != -1 )
    {
      if ( v27 )
      {
        v26 = 188;
        goto LABEL_65;
      }
      goto LABEL_42;
    }
    v25 = 187;
  }
  else
  {
    v25 = 180;
  }
LABEL_38:
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)v25, v23, v24);
  v30 = 0;
  if ( (LastError & 0x80000000) != 0 )
  {
LABEL_66:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v29, (const char *)LastError, PreviousCount);
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v55, v56);
    return LastError;
  }
LABEL_43:
  v31 = 260;
  v32 = Name;
  do
  {
    if ( !*v32 )
      break;
    ++v32;
    --v31;
  }
  while ( v31 );
  if ( v31 )
  {
    v33 = &Name[260 - v31];
    v34 = L"h";
    v35 = v31;
    do
    {
      if ( !v5 )
        break;
      if ( !*v34 )
        break;
      *v33++ = *v34++;
      --v5;
      --v35;
    }
    while ( v35 );
    v36 = v33 - 1;
    if ( v35 )
      v36 = v33;
    *v36 = 0;
  }
  v37 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v40 = v37;
  if ( !v37 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v38, v39);
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v53, v54);
    return LastError;
  }
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v37, &v61);
  v43 = ValueFromSemaphore;
  if ( ValueFromSemaphore >= 0 )
  {
    if ( !CloseHandle(v40) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v49, v50);
    *a3 = v30 | (unsigned __int64)((__int64)v61 << 31);
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v51, v52);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDE,
    v42,
    (const char *)(unsigned int)ValueFromSemaphore,
    PreviousCount);
  if ( !CloseHandle(v40) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v44, v45);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v46, v47);
  return v43;
}

```

## disassembly

```asm
0x180017c70  push    rbp
0x180017c72  push    rsi
0x180017c73  push    rdi
0x180017c74  push    r12
0x180017c76  push    r15
0x180017c78  sub     rsp, 250h
0x180017c7f  mov     rax, cs:__security_cookie
0x180017c86  xor     rax, rsp
0x180017c89  mov     [rsp+278h+var_38], rax
0x180017c91  xor     r12d, r12d
0x180017c94  lea     rax, [rsp+278h+Name]
0x180017c99  mov     ebp, 7FFFFFFEh
0x180017c9e  mov     [r8], r12
0x180017ca1  mov     esi, 104h
0x180017ca6  mov     edx, ebp
0x180017ca8  mov     r9d, esi
0x180017cab  mov     r15, r8
0x180017cae  mov     r10, rcx
0x180017cb1  test    rdx, rdx
0x180017cb4  jz      short loc_180017CD3
0x180017cb6  movzx   ecx, word ptr [r10]
0x180017cba  test    cx, cx
0x180017cbd  jz      short loc_180017CD3
0x180017cbf  mov     [rax], cx
0x180017cc2  add     r10, 2
0x180017cc6  add     rax, 2
0x180017cca  dec     rdx
0x180017ccd  sub     r9, 1
0x180017cd1  jnz     short loc_180017CB1
0x180017cd3  lea     rcx, [rax-2]
0x180017cd7  test    r9, r9
0x180017cda  cmovnz  rcx, rax
0x180017cde  lea     rax, [rsp+278h+Name]
0x180017ce3  mov     [rcx], r12w
0x180017ce7  mov     rcx, rsi
0x180017cea  nop     word ptr [rax+rax+00h]
0x180017cf0  cmp     [rax], r12w
0x180017cf4  jz      short loc_180017D00
0x180017cf6  add     rax, 2
0x180017cfa  sub     rcx, 1
0x180017cfe  jnz     short loc_180017CF0
0x180017d00  mov     rdx, rsi
0x180017d03  sub     rdx, rcx
0x180017d06  test    rcx, rcx
0x180017d09  cmovz   rdx, r12
0x180017d0d  jz      short loc_180017D59
0x180017d0f  mov     rax, rsi
0x180017d12  lea     r8, aP0; "_p0"
0x180017d19  sub     rax, rdx
0x180017d1c  mov     rcx, rbp
0x180017d1f  lea     rdx, [rsp+rdx*2+278h+Name]
0x180017d24  jz      short loc_180017D4A
0x180017d26  test    rcx, rcx
0x180017d29  jz      short loc_180017D4A
0x180017d2b  movzx   r9d, word ptr [r8]
0x180017d2f  test    r9w, r9w
0x180017d33  jz      short loc_180017D4A
0x180017d35  mov     [rdx], r9w
0x180017d39  add     r8, 2
0x180017d3d  add     rdx, 2
0x180017d41  dec     rcx
0x180017d44  sub     rax, 1
0x180017d48  jnz     short loc_180017D26
0x180017d4a  test    rax, rax
0x180017d4d  lea     rcx, [rdx-2]
0x180017d51  cmovnz  rcx, rdx
0x180017d55  mov     [rcx], r12w
0x180017d59  mov     [rsp+278h+arg_0], rbx
0x180017d61  lea     r8, [rsp+278h+Name]; lpName
0x180017d66  xor     edx, edx; bInheritHandle
0x180017d68  mov     [rsp+278h+arg_8], r14
0x180017d70  mov     ecx, 1F0003h; dwDesiredAccess
0x180017d75  call    cs:__imp_OpenSemaphoreW
0x180017d7c  nop     dword ptr [rax+rax+00h]
0x180017d81  mov     rdi, rax
0x180017d84  test    rax, rax
0x180017d87  jz      loc_18001808D
0x180017d8d  xor     edx, edx; dwMilliseconds
0x180017d8f  mov     [rsp+278h+var_250], r12d
0x180017d94  mov     rcx, rax; hHandle
0x180017d97  call    cs:__imp_WaitForSingleObject
0x180017d9e  nop     dword ptr [rax+rax+00h]
0x180017da3  cmp     eax, 0FFFFFFFFh
0x180017da6  jnz     short loc_180017DB2
0x180017da8  mov     edx, 9Ch
0x180017dad  jmp     loc_180017EBA
0x180017db2  test    eax, eax
0x180017db4  jz      short loc_180017DC7
0x180017db6  cmp     eax, 102h
0x180017dbb  jz      short loc_180017DC7
0x180017dbd  mov     edx, 9Dh
0x180017dc2  jmp     loc_18001804C
0x180017dc7  mov     [rsp+278h+PreviousCount], r12d; int
0x180017dcc  mov     edx, 1; lReleaseCount
0x180017dd1  mov     rcx, rdi; hSemaphore
0x180017dd4  test    eax, eax
0x180017dd6  jnz     short loc_180017E37
0x180017dd8  lea     r8, [rsp+278h+PreviousCount]; lpPreviousCount
0x180017ddd  call    cs:__imp_ReleaseSemaphore
0x180017de4  nop     dword ptr [rax+rax+00h]
0x180017de9  test    eax, eax
0x180017deb  jnz     short loc_180017DF7
0x180017ded  mov     edx, 0A5h
0x180017df2  jmp     loc_180017EBA
0x180017df7  inc     [rsp+278h+PreviousCount]
0x180017dfb  xor     r8d, r8d; lpPreviousCount
0x180017dfe  mov     edx, 1; lReleaseCount
0x180017e03  mov     rcx, rdi; hSemaphore
0x180017e06  call    cs:__imp_ReleaseSemaphore
0x180017e0d  nop     dword ptr [rax+rax+00h]
0x180017e12  test    eax, eax
0x180017e14  jnz     short loc_180017E2D
0x180017e16  call    cs:__imp_GetLastError
0x180017e1d  nop     dword ptr [rax+rax+00h]
0x180017e22  cmp     eax, 12Ah
0x180017e27  jz      loc_180017EE3
0x180017e2d  mov     edx, 0AAh
0x180017e32  jmp     loc_18001804C
0x180017e37  lea     r8, [rsp+278h+var_254]; lpPreviousCount
0x180017e3c  mov     [rsp+278h+var_254], r12d
0x180017e41  call    cs:__imp_ReleaseSemaphore
0x180017e48  nop     dword ptr [rax+rax+00h]
0x180017e4d  test    eax, eax
0x180017e4f  jnz     short loc_180017E58
0x180017e51  mov     edx, 0B4h
0x180017e56  jmp     short loc_180017EBA
0x180017e58  cmp     [rsp+278h+var_254], r12d
0x180017e5d  jz      short loc_180017E69
0x180017e5f  mov     edx, 0B5h
0x180017e64  jmp     loc_18001804C
0x180017e69  xor     r8d, r8d; lpPreviousCount
0x180017e6c  mov     edx, 1; lReleaseCount
0x180017e71  mov     rcx, rdi; hSemaphore
0x180017e74  call    cs:__imp_ReleaseSemaphore
0x180017e7b  nop     dword ptr [rax+rax+00h]
0x180017e80  test    eax, eax
0x180017e82  jnz     loc_180018047
0x180017e88  call    cs:__imp_GetLastError
0x180017e8f  nop     dword ptr [rax+rax+00h]
0x180017e94  cmp     eax, 12Ah
0x180017e99  jnz     loc_180018047
0x180017e9f  xor     edx, edx; dwMilliseconds
0x180017ea1  mov     rcx, rdi; hHandle
0x180017ea4  call    cs:__imp_WaitForSingleObject
0x180017eab  nop     dword ptr [rax+rax+00h]
0x180017eb0  cmp     eax, 0FFFFFFFFh
0x180017eb3  jnz     short loc_180017ED5
0x180017eb5  mov     edx, 0BBh; void *
0x180017eba  mov     rcx, [rsp+278h]; this
0x180017ec2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017ec7  mov     ebx, eax
0x180017ec9  mov     r14d, r12d
0x180017ecc  test    eax, eax
0x180017ece  jns     short loc_180017EE8
0x180017ed0  jmp     loc_180018061
0x180017ed5  test    eax, eax
0x180017ed7  jz      short loc_180017EE3
0x180017ed9  mov     edx, 0BCh
0x180017ede  jmp     loc_18001804C
0x180017ee3  mov     r14d, [rsp+278h+PreviousCount]
0x180017ee8  mov     rcx, rsi
0x180017eeb  lea     rax, [rsp+278h+Name]
0x180017ef0  cmp     [rax], r12w
0x180017ef4  jz      short loc_180017F00
0x180017ef6  add     rax, 2
0x180017efa  sub     rcx, 1
0x180017efe  jnz     short loc_180017EF0
0x180017f00  mov     r8, rsi
0x180017f03  sub     r8, rcx
0x180017f06  test    rcx, rcx
0x180017f09  cmovz   r8, r12
0x180017f0d  jz      short loc_180017F54
0x180017f0f  lea     rax, [rsp+278h+Name]
0x180017f14  lea     rax, [rax+r8*2]
0x180017f18  lea     rdx, asc_18008D2B8; "h"
0x180017f1f  sub     rsi, r8
0x180017f22  jz      short loc_180017F45
0x180017f24  test    rbp, rbp
0x180017f27  jz      short loc_180017F45
0x180017f29  movzx   ecx, word ptr [rdx]
0x180017f2c  test    cx, cx
0x180017f2f  jz      short loc_180017F45
0x180017f31  mov     [rax], cx
0x180017f34  add     rdx, 2
0x180017f38  add     rax, 2
0x180017f3c  dec     rbp
0x180017f3f  sub     rsi, 1
0x180017f43  jnz     short loc_180017F24
0x180017f45  test    rsi, rsi
0x180017f48  lea     rdx, [rax-2]
0x180017f4c  cmovnz  rdx, rax
0x180017f50  mov     [rdx], r12w
0x180017f54  lea     r8, [rsp+278h+Name]; lpName
0x180017f59  xor     edx, edx; bInheritHandle
0x180017f5b  mov     ecx, 1F0003h; dwDesiredAccess
0x180017f60  call    cs:__imp_OpenSemaphoreW
0x180017f67  nop     dword ptr [rax+rax+00h]
0x180017f6c  mov     rbx, rax
0x180017f6f  test    rax, rax
0x180017f72  jz      loc_18001801A
0x180017f78  lea     rdx, [rsp+278h+var_250]; int *
0x180017f7d  mov     rcx, rax; hHandle
0x180017f80  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180017f85  mov     esi, eax
0x180017f87  test    eax, eax
0x180017f89  jns     short loc_180017FD5
0x180017f8b  mov     rcx, [rsp+278h]; this
0x180017f93  mov     r9d, eax; char *
0x180017f96  mov     edx, 0DEh; void *
0x180017f9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017fa0  mov     rcx, rbx; hObject
0x180017fa3  call    cs:__imp_CloseHandle
0x180017faa  nop     dword ptr [rax+rax+00h]
0x180017faf  test    eax, eax
0x180017fb1  jz      loc_18001811D
0x180017fb7  mov     rcx, rdi; hObject
0x180017fba  call    cs:__imp_CloseHandle
0x180017fc1  nop     dword ptr [rax+rax+00h]
0x180017fc6  test    eax, eax
0x180017fc8  jz      loc_180018130
0x180017fce  mov     eax, esi
0x180017fd0  jmp     loc_1800180B4
0x180017fd5  mov     rcx, rbx; hObject
0x180017fd8  call    cs:__imp_CloseHandle
0x180017fdf  nop     dword ptr [rax+rax+00h]
0x180017fe4  test    eax, eax
0x180017fe6  jz      loc_180018143
0x180017fec  movsxd  rcx, [rsp+278h+var_250]
0x180017ff1  shl     rcx, 1Fh
0x180017ff5  movsxd  rax, r14d
0x180017ff8  or      rcx, rax
0x180017ffb  mov     [r15], rcx
0x180017ffe  mov     rcx, rdi; hObject
0x180018001  call    cs:__imp_CloseHandle
0x180018008  nop     dword ptr [rax+rax+00h]
0x18001800d  test    eax, eax
0x18001800f  jz      loc_1800180F7
0x180018015  jmp     loc_18001809E
0x18001801a  mov     rcx, [rsp+278h]; this
0x180018022  mov     edx, 0DCh; void *
0x180018027  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001802c  mov     rcx, rdi; hObject
0x18001802f  mov     ebx, eax
0x180018031  call    cs:__imp_CloseHandle
0x180018038  nop     dword ptr [rax+rax+00h]
0x18001803d  test    eax, eax
0x18001803f  jz      loc_18001810A
0x180018045  jmp     short loc_180018089
0x180018047  mov     edx, 0B8h; void *
0x18001804c  mov     rcx, [rsp+278h]; this
0x180018054  mov     ebx, 8000FFFFh
0x180018059  mov     r9d, ebx; char *
0x18001805c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018061  mov     rcx, [rsp+278h]; this
0x180018069  mov     r9d, ebx; char *
0x18001806c  mov     edx, 0D6h; void *
0x180018071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018076  mov     rcx, rdi; hObject
0x180018079  call    cs:__imp_CloseHandle
0x180018080  nop     dword ptr [rax+rax+00h]
0x180018085  test    eax, eax
0x180018087  jz      short loc_1800180E4
0x180018089  mov     eax, ebx
0x18001808b  jmp     short loc_1800180B4
0x18001808d  call    cs:__imp_GetLastError
0x180018094  nop     dword ptr [rax+rax+00h]
0x180018099  cmp     eax, 2
0x18001809c  jnz     short loc_1800180A2
0x18001809e  xor     eax, eax
0x1800180a0  jmp     short loc_1800180B4
0x1800180a2  mov     rcx, [rsp+278h]; this
0x1800180aa  mov     edx, 0D0h; void *
0x1800180af  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800180b4  mov     r14, [rsp+278h+arg_8]
0x1800180bc  mov     rbx, [rsp+278h+arg_0]
0x1800180c4  mov     rcx, [rsp+278h+var_38]
0x1800180cc  xor     rcx, rsp; StackCookie
0x1800180cf  call    __security_check_cookie
0x1800180d4  add     rsp, 250h
0x1800180db  pop     r15
0x1800180dd  pop     r12
0x1800180df  pop     rdi
0x1800180e0  pop     rsi
0x1800180e1  pop     rbp
0x1800180e2  retn
0x1800180e4  mov     rcx, [rsp+278h]; this
0x1800180ec  mov     edx, 0A0Bh; void *
0x1800180f1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800180f7  mov     rcx, [rsp+278h]; this
0x1800180ff  mov     edx, 0A0Bh; void *
0x180018104  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001810a  mov     rcx, [rsp+278h]; this
0x180018112  mov     edx, 0A0Bh; void *
0x180018117  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001811d  mov     rcx, [rsp+278h]; this
0x180018125  mov     edx, 0A0Bh; void *
0x18001812a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018130  mov     rcx, [rsp+278h]; this
0x180018138  mov     edx, 0A0Bh; void *
0x18001813d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
  ... truncated ...
```
