# InitializeServiceThreadSecurityInfo(_SERVICE_THREAD_SECURITY_INFO * *)

- ea: `0x1800188fc`
- end: `0x180018a61`
- name: `?InitializeServiceThreadSecurityInfo@@YAKPEAPEAU_SERVICE_THREAD_SECURITY_INFO@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(struct _SERVICE_THREAD_SECURITY_INFO **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800186d0`

## callees

- `0x1800188fc`
- `0x18002f80c`
- `0x18002f96c`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001893c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001893c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001892c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001892c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a1e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180018988`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800189c1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800189ff`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180018988`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800189c1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800189ff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180018a14`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180018a14`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitializeServiceThreadSecurityInfo(struct _SERVICE_THREAD_SECURITY_INFO **a1)
{
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v3; // rax
  LPVOID pSid; // rdi
  struct _SERVICE_THREAD_SECURITY_INFO *v6; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-20h] BYREF

  LastError = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  qword_18004BFA0 = 0;
  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 8u, 0x28u);
  v6 = (struct _SERVICE_THREAD_SECURITY_INFO *)v3;
  pSid = v3;
  if ( !v3 )
    return 2148532230LL;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, (PSID *)v3 + 1)
    && AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 6u, 0, 0, 0, 0, 0, 0, 0, (PSID *)pSid)
    && AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, (PSID *)pSid + 2)
    && ConvertStringSidToSidW(L"S-1-5-80-242729624-280608522-2219052887-3187409060-2225943459", (PSID *)pSid + 3) )
  {
    *((_BYTE *)pSid + 32) = DisconnectedLocalSessionsAreAllowed();
    qword_18004BFA0 = (struct _SERVICE_THREAD_SECURITY_INFO *)pSid;
  }
  else
  {
    LastError = GetLastError();
    FreeServiceThreadSecurityInfo(&v6);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800188fc  mov     [rsp+arg_0], rbx
0x180018901  push    rdi
0x180018902  sub     rsp, 80h
0x180018909  mov     rax, cs:__security_cookie
0x180018910  xor     rax, rsp
0x180018913  mov     [rsp+88h+var_18], rax
0x180018918  xor     ebx, ebx
0x18001891a  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 500h
0x180018921  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], ebx
0x180018925  mov     cs:qword_18004BFA0, rbx
0x18001892c  call    cs:__imp_GetProcessHeap
0x180018932  mov     rcx, rax; hHeap
0x180018935  lea     edx, [rbx+8]; dwFlags
0x180018938  lea     r8d, [rbx+28h]; dwBytes
0x18001893c  call    cs:__imp_HeapAlloc
0x180018942  mov     [rsp+88h+var_28], rax
0x180018947  mov     rdi, rax
0x18001894a  test    rax, rax
0x18001894d  jnz     short loc_180018959
0x18001894f  mov     eax, 80100006h
0x180018954  jmp     loc_180018A43
0x180018959  add     rax, 8
0x18001895d  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x180018962  mov     [rsp+88h+pSid], rax; pSid
0x180018967  xor     r9d, r9d; nSubAuthority1
0x18001896a  mov     [rsp+88h+nSubAuthority7], ebx; nSubAuthority7
0x18001896e  mov     dl, 1; nSubAuthorityCount
0x180018970  mov     [rsp+88h+nSubAuthority6], ebx; nSubAuthority6
0x180018974  mov     [rsp+88h+nSubAuthority5], ebx; nSubAuthority5
0x180018978  mov     [rsp+88h+nSubAuthority4], ebx; nSubAuthority4
0x18001897c  lea     r8d, [r9+12h]; nSubAuthority0
0x180018980  mov     [rsp+88h+nSubAuthority3], ebx; nSubAuthority3
0x180018984  mov     [rsp+88h+nSubAuthority2], ebx; nSubAuthority2
0x180018988  call    cs:__imp_AllocateAndInitializeSid
0x18001898e  test    eax, eax
0x180018990  jz      loc_180018A1E
0x180018996  mov     [rsp+88h+pSid], rdi; pSid
0x18001899b  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x1800189a0  mov     [rsp+88h+nSubAuthority7], ebx; nSubAuthority7
0x1800189a4  xor     r9d, r9d; nSubAuthority1
0x1800189a7  mov     [rsp+88h+nSubAuthority6], ebx; nSubAuthority6
0x1800189ab  mov     dl, 1; nSubAuthorityCount
0x1800189ad  mov     [rsp+88h+nSubAuthority5], ebx; nSubAuthority5
0x1800189b1  mov     [rsp+88h+nSubAuthority4], ebx; nSubAuthority4
0x1800189b5  mov     [rsp+88h+nSubAuthority3], ebx; nSubAuthority3
0x1800189b9  lea     r8d, [r9+6]; nSubAuthority0
0x1800189bd  mov     [rsp+88h+nSubAuthority2], ebx; nSubAuthority2
0x1800189c1  call    cs:__imp_AllocateAndInitializeSid
0x1800189c7  test    eax, eax
0x1800189c9  jz      short loc_180018A1E
0x1800189cb  lea     rax, [rdi+10h]
0x1800189cf  mov     r9d, 220h; nSubAuthority1
0x1800189d5  mov     [rsp+88h+pSid], rax; pSid
0x1800189da  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x1800189df  mov     [rsp+88h+nSubAuthority7], ebx; nSubAuthority7
0x1800189e3  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800189e9  mov     [rsp+88h+nSubAuthority6], ebx; nSubAuthority6
0x1800189ed  mov     dl, 2; nSubAuthorityCount
0x1800189ef  mov     [rsp+88h+nSubAuthority5], ebx; nSubAuthority5
0x1800189f3  mov     [rsp+88h+nSubAuthority4], ebx; nSubAuthority4
0x1800189f7  mov     [rsp+88h+nSubAuthority3], ebx; nSubAuthority3
0x1800189fb  mov     [rsp+88h+nSubAuthority2], ebx; nSubAuthority2
0x1800189ff  call    cs:__imp_AllocateAndInitializeSid
0x180018a05  test    eax, eax
0x180018a07  jz      short loc_180018A1E
0x180018a09  lea     rdx, [rdi+18h]; Sid
0x180018a0d  lea     rcx, aS1580242729624; "S-1-5-80-242729624-280608522-2219052887"...
0x180018a14  call    cs:__imp_ConvertStringSidToSidW
0x180018a1a  test    eax, eax
0x180018a1c  jnz     short loc_180018A32
0x180018a1e  call    cs:__imp_GetLastError
0x180018a24  lea     rcx, [rsp+88h+var_28]; struct _SERVICE_THREAD_SECURITY_INFO **
0x180018a29  mov     ebx, eax
0x180018a2b  call    ?FreeServiceThreadSecurityInfo@@YAKPEAPEAU_SERVICE_THREAD_SECURITY_INFO@@@Z; FreeServiceThreadSecurityInfo(_SERVICE_THREAD_SECURITY_INFO * *)
0x180018a30  jmp     short loc_180018A41
0x180018a32  call    ?DisconnectedLocalSessionsAreAllowed@@YA_NXZ; DisconnectedLocalSessionsAreAllowed(void)
0x180018a37  mov     [rdi+20h], al
0x180018a3a  mov     cs:qword_18004BFA0, rdi
0x180018a41  mov     eax, ebx
0x180018a43  mov     rcx, [rsp+88h+var_18]
0x180018a48  xor     rcx, rsp; StackCookie
0x180018a4b  call    __security_check_cookie
0x180018a50  mov     rbx, [rsp+88h+arg_0]
0x180018a58  add     rsp, 80h
0x180018a5f  pop     rdi
0x180018a60  retn
```
