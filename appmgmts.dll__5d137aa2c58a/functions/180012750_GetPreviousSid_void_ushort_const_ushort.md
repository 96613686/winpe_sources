# GetPreviousSid(void *,ushort const *,ushort * *)

- ea: `0x180012750`
- end: `0x1800129bc`
- name: `?GetPreviousSid@@YAKPEAXPEBGPEAPEAG@Z`
- size: `620`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e8e8`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180012750`
- `0x18002ada8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800127b7`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800127c8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800127b7`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800127c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001297f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001297f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001292a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001292a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001287b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012952`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001287b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012952`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012802`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012802`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001286f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001286f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001296b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001296b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001298a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001298a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800128f4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800128f4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012945`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012945`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180012913`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180012913`
- `KERNEL32!lstrcmpW` at `0x1800128a8`
- `KERNEL32!lstrcmpW` at `0x1800128c2`
- `KERNEL32!lstrcmpW` at `0x1800128a8`
- `KERNEL32!lstrcmpW` at `0x1800128c2`

## pseudocode

```c
__int64 __fastcall GetPreviousSid(void *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  HANDLE v5; // rbx
  wchar_t *v6; // r15
  wchar_t *v7; // r12
  __int64 v8; // rdi
  SIZE_T v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rsi
  HANDLE FirstFileW; // rdi
  DWORD LastError; // esi
  BOOL v15; // ebx
  WINBOOL IsMember; // [rsp+30h] [rbp-D0h] BYREF
  PSID Sid; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  TokenHandle = a1;
  v5 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  Sid = 0;
  IsMember = 0;
  *a3 = 0;
  v6 = wcsrchr(a2, 0x5Cu);
  *v6 = 0;
  v7 = wcsrchr(a2, 0x5Cu);
  *v7 = 0;
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  v9 = 2LL * (unsigned int)(v8 + 3);
  if ( !is_mul_ok((unsigned int)(v8 + 3), 2u) )
    v9 = -1;
  v10 = (WCHAR *)LocalAlloc(0, v9);
  v11 = v10;
  if ( v10 )
  {
    memcpy_0(v10, a2, 2LL * (unsigned int)v8);
    v11[(unsigned int)v8] = 92;
    v5 = TokenHandle;
    v11[(unsigned int)(v8 + 1)] = 42;
    v11[(unsigned int)(v8 + 2)] = 0;
  }
  *v7 = 92;
  *v6 = 92;
  if ( !v11 )
    return 14;
  FirstFileW = FindFirstFileW(v11, &FindFileData);
  LocalFree(v11);
  if ( FirstFileW == (HANDLE)-1LL )
    return 0;
  LastError = 0;
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0
      || !lstrcmpW(FindFileData.cFileName, L".")
      || !lstrcmpW(FindFileData.cFileName, L"..")
      || CompareStringW(0x7Fu, 1u, FindFileData.cFileName, -1, L"MACHINE", -1) == 2 )
    {
      goto LABEL_24;
    }
    IsMember = 0;
    Sid = 0;
    if ( !ConvertStringSidToSidW(FindFileData.cFileName, &Sid) )
      break;
    v15 = CheckTokenMembership(v5, Sid, &IsMember);
    if ( v15 )
    {
      if ( IsMember )
        v15 = ConvertSidToStringSidW(Sid, a3);
    }
    LocalFree(Sid);
    if ( !v15 )
      break;
    if ( IsMember )
      goto LABEL_27;
LABEL_24:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_27;
    v5 = TokenHandle;
  }
  LastError = GetLastError();
LABEL_27:
  FindClose(FirstFileW);
  return LastError;
}

```

## disassembly

```asm
0x180012750  mov     [rsp-8+arg_18], rbx
0x180012755  push    rbp
0x180012756  push    rsi
0x180012757  push    rdi
0x180012758  push    r12
0x18001275a  push    r13
0x18001275c  push    r14
0x18001275e  push    r15
0x180012760  lea     rbp, [rsp-1B0h]
0x180012768  sub     rsp, 2B0h
0x18001276f  mov     rax, cs:__security_cookie
0x180012776  xor     rax, rsp
0x180012779  mov     [rbp+1E0h+var_40], rax
0x180012780  mov     r13, r8
0x180012783  mov     [rsp+2E0h+TokenHandle], rcx
0x180012788  mov     r14, rdx
0x18001278b  mov     rbx, rcx
0x18001278e  xor     edx, edx; Val
0x180012790  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x180012795  mov     r8d, 250h; Size
0x18001279b  call    memset_0
0x1800127a0  xor     esi, esi
0x1800127a2  mov     rcx, r14; Str
0x1800127a5  mov     [rsp+2E0h+Sid], rsi
0x1800127aa  mov     [rsp+2E0h+IsMember], esi
0x1800127ae  mov     [r13+0], rsi
0x1800127b2  lea     edi, [rsi+5Ch]
0x1800127b5  mov     edx, edi; Ch
0x1800127b7  call    cs:__imp_wcsrchr
0x1800127bd  mov     edx, edi; Ch
0x1800127bf  mov     rcx, r14; Str
0x1800127c2  mov     r15, rax
0x1800127c5  mov     [rax], si
0x1800127c8  call    cs:__imp_wcsrchr
0x1800127ce  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800127d2  mov     r12, rax
0x1800127d5  mov     [rax], si
0x1800127d8  test    r14, r14
0x1800127db  jnz     short loc_1800127E1
0x1800127dd  mov     edi, esi
0x1800127df  jmp     short loc_1800127EE
0x1800127e1  mov     rdi, r8
0x1800127e4  inc     rdi
0x1800127e7  cmp     [r14+rdi*2], si
0x1800127ec  jnz     short loc_1800127E4
0x1800127ee  lea     ecx, [rdi+3]
0x1800127f1  mov     eax, 2
0x1800127f6  mul     rcx
0x1800127f9  cmovb   rax, r8
0x1800127fd  xor     ecx, ecx; uFlags
0x1800127ff  mov     rdx, rax; uBytes
0x180012802  call    cs:__imp_LocalAlloc
0x180012808  mov     rsi, rax
0x18001280b  test    rax, rax
0x18001280e  jz      short loc_18001284A
0x180012810  mov     ecx, edi
0x180012812  mov     rdx, r14; Src
0x180012815  lea     rbx, [rcx+rcx]
0x180012819  mov     rcx, rax; void *
0x18001281c  mov     r8, rbx; Size
0x18001281f  call    memcpy_0
0x180012824  mov     r8d, 5Ch ; '\'
0x18001282a  lea     ecx, [rdi+1]
0x18001282d  lea     eax, [rdi+2]
0x180012830  mov     [rbx+rsi], r8w
0x180012835  mov     rbx, [rsp+2E0h+TokenHandle]
0x18001283a  xor     r14d, r14d
0x18001283d  mov     word ptr [rsi+rcx*2], 2Ah ; '*'
0x180012843  mov     [rsi+rax*2], r14w
0x180012848  jmp     short loc_180012851
0x18001284a  xor     r14d, r14d
0x18001284d  lea     r8d, [r14+5Ch]
0x180012851  mov     [r12], r8w
0x180012856  mov     [r15], r8w
0x18001285a  test    rsi, rsi
0x18001285d  jnz     short loc_180012867
0x18001285f  lea     eax, [rsi+0Eh]
0x180012862  jmp     loc_180012992
0x180012867  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18001286c  mov     rcx, rsi; lpFileName
0x18001286f  call    cs:__imp_FindFirstFileW
0x180012875  mov     rcx, rsi; hMem
0x180012878  mov     rdi, rax
0x18001287b  call    cs:__imp_LocalFree
0x180012881  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180012885  jnz     short loc_18001288E
0x180012887  xor     eax, eax
0x180012889  jmp     loc_180012992
0x18001288e  mov     esi, r14d
0x180012891  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x180012896  jz      loc_180012963
0x18001289c  lea     rdx, String2; "."
0x1800128a3  lea     rcx, [rsp+2E0h+FindFileData.cFileName]; lpString1
0x1800128a8  call    cs:__imp_lstrcmpW
0x1800128ae  test    eax, eax
0x1800128b0  jz      loc_180012963
0x1800128b6  lea     rdx, asc_180030090; ".."
0x1800128bd  lea     rcx, [rsp+2E0h+FindFileData.cFileName]; lpString1
0x1800128c2  call    cs:__imp_lstrcmpW
0x1800128c8  test    eax, eax
0x1800128ca  jz      loc_180012963
0x1800128d0  or      r9d, 0FFFFFFFFh; cchCount1
0x1800128d4  mov     [rsp+2E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800128dc  lea     rax, SourceString; "MACHINE"
0x1800128e3  lea     r8, [rsp+2E0h+FindFileData.cFileName]; lpString1
0x1800128e8  mov     [rsp+2E0h+lpString2], rax; lpString2
0x1800128ed  lea     edx, [r9+2]; dwCmpFlags
0x1800128f1  lea     ecx, [rdx+7Eh]; Locale
0x1800128f4  call    cs:__imp_CompareStringW
0x1800128fa  cmp     eax, 2
0x1800128fd  jz      short loc_180012963
0x1800128ff  lea     rdx, [rsp+2E0h+Sid]; Sid
0x180012904  mov     [rsp+2E0h+IsMember], r14d
0x180012909  lea     rcx, [rsp+2E0h+FindFileData.cFileName]; StringSid
0x18001290e  mov     [rsp+2E0h+Sid], r14
0x180012913  call    cs:__imp_ConvertStringSidToSidW
0x180012919  test    eax, eax
0x18001291b  jz      short loc_18001297F
0x18001291d  mov     rdx, [rsp+2E0h+Sid]; SidToCheck
0x180012922  lea     r8, [rsp+2E0h+IsMember]; IsMember
0x180012927  mov     rcx, rbx; TokenHandle
0x18001292a  call    cs:__imp_CheckTokenMembership
0x180012930  mov     ebx, eax
0x180012932  test    eax, eax
0x180012934  jz      short loc_18001294D
0x180012936  cmp     [rsp+2E0h+IsMember], r14d
0x18001293b  jz      short loc_18001294D
0x18001293d  mov     rcx, [rsp+2E0h+Sid]; Sid
0x180012942  mov     rdx, r13; StringSid
0x180012945  call    cs:__imp_ConvertSidToStringSidW
0x18001294b  mov     ebx, eax
0x18001294d  mov     rcx, [rsp+2E0h+Sid]; hMem
0x180012952  call    cs:__imp_LocalFree
0x180012958  test    ebx, ebx
0x18001295a  jz      short loc_18001297F
0x18001295c  cmp     [rsp+2E0h+IsMember], r14d
0x180012961  jnz     short loc_180012987
0x180012963  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x180012968  mov     rcx, rdi; hFindFile
0x18001296b  call    cs:__imp_FindNextFileW
0x180012971  test    eax, eax
0x180012973  jz      short loc_180012987
0x180012975  mov     rbx, [rsp+2E0h+TokenHandle]
0x18001297a  jmp     loc_180012891
0x18001297f  call    cs:__imp_GetLastError
0x180012985  mov     esi, eax
0x180012987  mov     rcx, rdi; hFindFile
0x18001298a  call    cs:__imp_FindClose
0x180012990  mov     eax, esi
0x180012992  mov     rcx, [rbp+1E0h+var_40]
0x180012999  xor     rcx, rsp; StackCookie
0x18001299c  call    __security_check_cookie
0x1800129a1  mov     rbx, [rsp+2E0h+arg_18]
0x1800129a9  add     rsp, 2B0h
0x1800129b0  pop     r15
0x1800129b2  pop     r14
0x1800129b4  pop     r13
0x1800129b6  pop     r12
0x1800129b8  pop     rdi
0x1800129b9  pop     rsi
0x1800129ba  pop     rbp
0x1800129bb  retn
```
