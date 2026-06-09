# CBindingList::Find(CServerContext *,_FILETIME *,ushort const *,void *)

- ea: `0x180024920`
- end: `0x180024b88`
- name: `?Find@CBindingList@@QEAAPEAVCBinding@@PEAVCServerContext@@PEAU_FILETIME@@PEBGPEAX@Z`
- size: `616`
- prototype: `struct CBinding *__fastcall(CBindingList *this, const WCHAR **, struct _FILETIME *, const unsigned __int16 *, PSID pSid2)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001c84c`
- `0x1800247a8`

## callees

- `0x1800016d0`
- `0x18001b1a0`
- `0x1800248b0`
- `0x180024920`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024b09`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024b09`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180024a76`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180024a76`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800249ac`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800249bc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800249ac`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800249bc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180024af7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180024af7`
- `KERNEL32!lstrcmpW` at `0x180024a93`
- `KERNEL32!lstrcmpW` at `0x180024a93`

## pseudocode

```c
struct CBinding *__fastcall CBindingList::Find(
        CBindingList *this,
        const WCHAR **a2,
        struct _FILETIME *a3,
        const unsigned __int16 *a4,
        PSID pSid2)
{
  _UNKNOWN **v8; // rax
  _UNKNOWN **v9; // rcx
  __int64 v10; // rdi
  BOOL v11; // ebx
  struct CBinding *v12; // rbx
  const WCHAR *v13; // r8
  const WCHAR *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r9
  PCNZWCH lpString2; // [rsp+20h] [rbp-60h]
  __int64 cchCount2; // [rsp+28h] [rbp-58h]
  __int64 v20; // [rsp+30h] [rbp-50h]
  __int64 v21; // [rsp+38h] [rbp-48h]
  __int64 v22; // [rsp+40h] [rbp-40h]
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-30h] BYREF
  struct _SYSTEMTIME v24; // [rsp+60h] [rbp-20h] BYREF

  qword_180037508 = qword_180037500;
  v8 = off_1800374F8;
  for ( qword_180037500 = (__int64)off_1800374F8; ; v8 = (_UNKNOWN **)qword_180037500 )
  {
    v9 = 0;
    if ( v8 != &BindingCache )
      v9 = v8;
    v10 = (unsigned __int64)(v9 - 6) & -(__int64)(v9 != 0);
    if ( !v10 )
      return 0;
    SystemTime = 0;
    v24 = 0;
    v11 = FileTimeToSystemTime(a3, &SystemTime);
    if ( FileTimeToSystemTime((const FILETIME *)(v10 + 40), &v24) && v11 )
    {
      if ( gDebug )
      {
        LODWORD(v22) = SystemTime.wSecond;
        LODWORD(v21) = SystemTime.wMinute;
        LODWORD(v20) = SystemTime.wHour;
        LODWORD(cchCount2) = SystemTime.wYear;
        LODWORD(lpString2) = SystemTime.wDay;
        _DebugMsg(4, 0xCA5u, L"Current Time", SystemTime.wMonth, lpString2, cchCount2, v20, v21, v22);
        if ( gDebug )
        {
          LODWORD(v22) = v24.wSecond;
          LODWORD(v21) = v24.wMinute;
          LODWORD(v20) = v24.wHour;
          LODWORD(cchCount2) = v24.wYear;
          LODWORD(lpString2) = v24.wDay;
          _DebugMsg(4, 0xCA5u, L"Expire Time", v24.wMonth, lpString2, cchCount2, v20, v21, v22);
        }
      }
    }
    if ( CompareFileTime(a3, (const FILETIME *)(v10 + 40)) > 0 )
    {
      v12 = (struct CBinding *)v10;
      goto LABEL_23;
    }
    v12 = 0;
    if ( lstrcmpW(*(LPCWSTR *)v10, a4) )
      goto LABEL_23;
    v13 = *(const WCHAR **)(v10 + 8);
    if ( a2 )
      break;
    if ( !v13 )
      goto LABEL_22;
LABEL_23:
    qword_180037500 = *(_QWORD *)(qword_180037500 + 8);
    CBindingList::Delete((CBindingList *)&BindingCache, v12);
  }
  v14 = *a2;
  if ( (*(_QWORD *)(v10 + 8) == 0) != (*a2 == 0) )
    goto LABEL_23;
  if ( v13 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    v16 = -1;
    do
      ++v16;
    while ( v13[v16] );
    if ( CompareStringW(0x7Fu, 1u, v13, v16, v14, v15) != 2 )
      goto LABEL_23;
  }
LABEL_22:
  if ( !EqualSid(*(PSID *)(v10 + 32), pSid2) )
    goto LABEL_23;
  if ( gDebug )
    _DebugMsg(2, 0xC84u, a4);
  return (struct CBinding *)v10;
}

```

## disassembly

```asm
0x180024920  mov     [rsp-38h+arg_0], rbx
0x180024925  push    rbp
0x180024926  push    rsi
0x180024927  push    rdi
0x180024928  push    r12
0x18002492a  push    r13
0x18002492c  push    r14
0x18002492e  push    r15
0x180024930  mov     rbp, rsp
0x180024933  sub     rsp, 80h
0x18002493a  mov     rax, cs:__security_cookie
0x180024941  xor     rax, rsp
0x180024944  mov     [rbp+var_10], rax
0x180024948  mov     rax, cs:qword_180037500
0x18002494f  mov     r14, r9
0x180024952  mov     r13, [rbp+pSid2]
0x180024956  mov     r12, r8
0x180024959  mov     cs:qword_180037508, rax
0x180024960  mov     r15, rdx
0x180024963  mov     rax, cs:off_1800374F8
0x18002496a  xor     esi, esi
0x18002496c  mov     cs:qword_180037500, rax
0x180024973  lea     rdx, ?BindingCache@@3VCBindingList@@A; CBindingList BindingCache
0x18002497a  mov     rcx, rsi
0x18002497d  cmp     rax, rdx
0x180024980  cmovnz  rcx, rax
0x180024984  lea     rax, [rcx-30h]
0x180024988  neg     rcx
0x18002498b  sbb     rdi, rdi
0x18002498e  and     rdi, rax
0x180024991  jz      loc_180024B5F
0x180024997  xorps   xmm0, xmm0
0x18002499a  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18002499e  xorps   xmm1, xmm1
0x1800249a1  mov     rcx, r12; lpFileTime
0x1800249a4  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800249a8  movups  xmmword ptr [rbp+var_20.wYear], xmm1
0x1800249ac  call    cs:__imp_FileTimeToSystemTime
0x1800249b2  lea     rdx, [rbp+var_20]; lpSystemTime
0x1800249b6  mov     ebx, eax
0x1800249b8  lea     rcx, [rdi+28h]; lpFileTime
0x1800249bc  call    cs:__imp_FileTimeToSystemTime
0x1800249c2  test    ebx, eax
0x1800249c4  jz      loc_180024A6F
0x1800249ca  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x1800249d1  jz      loc_180024A6F
0x1800249d7  movzx   ecx, [rbp+SystemTime.wMinute]
0x1800249db  mov     ebx, 0CA5h
0x1800249e0  movzx   edx, [rbp+SystemTime.wHour]
0x1800249e4  movzx   r8d, [rbp+SystemTime.wYear]
0x1800249e9  movzx   eax, [rbp+SystemTime.wSecond]
0x1800249ed  movzx   r10d, [rbp+SystemTime.wDay]
0x1800249f2  movzx   r9d, [rbp+SystemTime.wMonth]
0x1800249f7  mov     [rsp+80h+var_40], eax
0x1800249fb  mov     dword ptr [rsp+80h+var_48], ecx
0x1800249ff  mov     ecx, 4; unsigned int
0x180024a04  mov     dword ptr [rsp+80h+var_50], edx
0x180024a08  mov     edx, ebx; unsigned int
0x180024a0a  mov     dword ptr [rsp+80h+cchCount2], r8d
0x180024a0f  lea     r8, aCurrentTime; "Current Time"
0x180024a16  mov     dword ptr [rsp+80h+lpString2], r10d
0x180024a1b  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180024a20  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x180024a27  jz      short loc_180024A6F
0x180024a29  movzx   ecx, [rbp+var_20.wMinute]
0x180024a2d  mov     edx, ebx; unsigned int
0x180024a2f  movzx   r8d, [rbp+var_20.wHour]
0x180024a34  movzx   eax, [rbp+var_20.wSecond]
0x180024a38  movzx   r10d, [rbp+var_20.wYear]
0x180024a3d  movzx   r11d, [rbp+var_20.wDay]
0x180024a42  movzx   r9d, [rbp+var_20.wMonth]
0x180024a47  mov     [rsp+80h+var_40], eax
0x180024a4b  mov     dword ptr [rsp+80h+var_48], ecx
0x180024a4f  mov     ecx, 4; unsigned int
0x180024a54  mov     dword ptr [rsp+80h+var_50], r8d
0x180024a59  lea     r8, aExpireTime; "Expire Time"
0x180024a60  mov     dword ptr [rsp+80h+cchCount2], r10d
0x180024a65  mov     dword ptr [rsp+80h+lpString2], r11d
0x180024a6a  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180024a6f  lea     rdx, [rdi+28h]; lpFileTime2
0x180024a73  mov     rcx, r12; lpFileTime1
0x180024a76  call    cs:__imp_CompareFileTime
0x180024a7c  xor     esi, esi
0x180024a7e  test    eax, eax
0x180024a80  jle     short loc_180024A8A
0x180024a82  mov     rbx, rdi
0x180024a85  jmp     loc_180024B13
0x180024a8a  mov     rcx, [rdi]; lpString1
0x180024a8d  mov     rdx, r14; lpString2
0x180024a90  mov     rbx, rsi
0x180024a93  call    cs:__imp_lstrcmpW
0x180024a99  test    eax, eax
0x180024a9b  jnz     short loc_180024B13
0x180024a9d  mov     r8, [rdi+8]; lpString1
0x180024aa1  test    r15, r15
0x180024aa4  jnz     short loc_180024AAD
0x180024aa6  test    r8, r8
0x180024aa9  jz      short loc_180024B02
0x180024aab  jmp     short loc_180024B13
0x180024aad  mov     rdx, [r15]
0x180024ab0  mov     ecx, esi
0x180024ab2  test    rdx, rdx
0x180024ab5  mov     eax, esi
0x180024ab7  setz    cl
0x180024aba  test    r8, r8
0x180024abd  setz    al
0x180024ac0  cmp     eax, ecx
0x180024ac2  jnz     short loc_180024B13
0x180024ac4  test    r8, r8
0x180024ac7  jz      short loc_180024B02
0x180024ac9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180024acd  mov     rax, rcx
0x180024ad0  inc     rax
0x180024ad3  cmp     [rdx+rax*2], si
0x180024ad7  jnz     short loc_180024AD0
0x180024ad9  mov     r9, rcx
0x180024adc  inc     r9; cchCount1
0x180024adf  cmp     [r8+r9*2], si
0x180024ae4  jnz     short loc_180024ADC
0x180024ae6  mov     dword ptr [rsp+80h+cchCount2], eax; cchCount2
0x180024aea  mov     [rsp+80h+lpString2], rdx; lpString2
0x180024aef  mov     edx, 1; dwCmpFlags
0x180024af4  lea     ecx, [rdx+7Eh]; Locale
0x180024af7  call    cs:__imp_CompareStringW
0x180024afd  cmp     eax, 2
0x180024b00  jnz     short loc_180024B13
0x180024b02  mov     rcx, [rdi+20h]; pSid1
0x180024b06  mov     rdx, r13; pSid2
0x180024b09  call    cs:__imp_EqualSid
0x180024b0f  test    eax, eax
0x180024b11  jnz     short loc_180024B40
0x180024b13  mov     rax, cs:qword_180037500
0x180024b1a  mov     rdx, rbx; struct CBinding *
0x180024b1d  mov     rcx, [rax+8]
0x180024b21  mov     cs:qword_180037500, rcx
0x180024b28  lea     rcx, ?BindingCache@@3VCBindingList@@A; this
0x180024b2f  call    ?Delete@CBindingList@@AEAAXPEAVCBinding@@@Z; CBindingList::Delete(CBinding *)
0x180024b34  mov     rax, cs:qword_180037500
0x180024b3b  jmp     loc_180024973
0x180024b40  cmp     cs:?gDebug@@3KA, esi; ulong gDebug
0x180024b46  jz      short loc_180024B5A
0x180024b48  mov     r8, r14
0x180024b4b  mov     edx, 0C84h; unsigned int
0x180024b50  mov     ecx, 2; unsigned int
0x180024b55  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180024b5a  mov     rax, rdi
0x180024b5d  jmp     short loc_180024B61
0x180024b5f  xor     eax, eax
0x180024b61  mov     rcx, [rbp+var_10]
0x180024b65  xor     rcx, rsp; StackCookie
0x180024b68  call    __security_check_cookie
0x180024b6d  mov     rbx, [rsp+80h+arg_0]
0x180024b75  add     rsp, 80h
0x180024b7c  pop     r15
0x180024b7e  pop     r14
0x180024b80  pop     r13
0x180024b82  pop     r12
0x180024b84  pop     rdi
0x180024b85  pop     rsi
0x180024b86  pop     rbp
0x180024b87  retn
```
