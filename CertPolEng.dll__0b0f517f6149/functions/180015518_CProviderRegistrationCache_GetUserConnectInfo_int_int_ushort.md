# CProviderRegistrationCache::GetUserConnectInfo(int *,int *,ushort * *)

- ea: `0x180015518`
- end: `0x1800157cb`
- name: `?GetUserConnectInfo@CProviderRegistrationCache@@QEAAJPEAH0PEAPEAG@Z`
- size: `691`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *__hidden this, int *, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000caa0`

## callees

- `0x18000e8d6`
- `0x180013ec8`
- `0x180015518`
- `0x18001a342`
- `0x18001a380`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001569e`
- `msvcrt!_wcsnicmp` at `0x18001569e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015767`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015767`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015726`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015726`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015777`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015785`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015795`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015777`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015785`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015795`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180015668`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180015668`
- `ntdll!RtlEqualSid` at `0x180015610`
- `ntdll!RtlEqualSid` at `0x180015610`
- `ntdll!NtQueryInformationToken` at `0x1800155f8`
- `ntdll!NtQueryInformationToken` at `0x1800155f8`
- `ntdll!NtOpenProcessToken` at `0x1800155ce`
- `ntdll!NtOpenProcessToken` at `0x1800155ce`
- `ntdll!NtOpenThreadToken` at `0x1800155a9`
- `ntdll!NtOpenThreadToken` at `0x1800155a9`
- `samcli!NetUserGetInfo` at `0x1800156c2`
- `samcli!NetUserGetInfo` at `0x1800156c2`
- `netutils!NetApiBufferFree` at `0x1800157a5`
- `netutils!NetApiBufferFree` at `0x1800157a5`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::GetUserConnectInfo(
        CProviderRegistrationCache *this,
        int *a2,
        int *a3,
        unsigned __int16 **a4)
{
  HLOCAL v7; // rdi
  NTSTATUS v8; // eax
  int v9; // ebx
  CProviderRegistrationCache *v10; // rcx
  int v11; // eax
  signed int LastError; // eax
  const WCHAR *v13; // rdx
  signed int Info; // eax
  LPBYTE v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  size_t v18; // rsi
  const void *v19; // rdx
  DWORD nSize; // [rsp+30h] [rbp-A9h] BYREF
  ULONG TokenInformationLength; // [rsp+34h] [rbp-A5h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-A1h] BYREF
  LPBYTE bufptr; // [rsp+40h] [rbp-99h] BYREF
  LPCWSTR username; // [rsp+48h] [rbp-91h] BYREF
  wchar_t *String2; // [rsp+50h] [rbp-89h] BYREF
  void *TokenInformation[12]; // [rsp+60h] [rbp-79h] BYREF
  _DWORD Sid2[4]; // [rsp+C0h] [rbp-19h] BYREF
  WCHAR Buffer[16]; // [rsp+D0h] [rbp-9h] BYREF

  Sid2[0] = 257;
  TokenHandle = 0;
  username = 0;
  String2 = 0;
  bufptr = 0;
  nSize = 0;
  Sid2[1] = 83886080;
  Sid2[2] = 18;
  v7 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  *a3 = 0;
  *a2 = 0;
  *a4 = 0;
  TokenInformationLength = 88;
  v8 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( v8 == -1073741700 )
      v9 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    goto LABEL_29;
  }
  v9 = NtQueryInformationToken(
         TokenHandle,
         TokenUser,
         TokenInformation,
         TokenInformationLength,
         &TokenInformationLength);
  if ( v9 < 0 )
    goto LABEL_29;
  if ( RtlEqualSid(TokenInformation[0], Sid2) )
  {
    *a3 = 0;
    *a2 = 1;
    *a4 = 0;
    goto LABEL_29;
  }
  v11 = CProviderRegistrationCache::CallADVAPILookupSids(
          v10,
          TokenInformation[0],
          (unsigned __int16 **)&username,
          &String2);
  v9 = v11;
  if ( v11 > 0 )
    v9 = (unsigned __int16)v11 | 0xC0070000;
  if ( v9 >= 0 )
  {
    nSize = 16;
    if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0xC0070000;
      goto LABEL_29;
    }
    if ( _wcsnicmp(Buffer, String2, nSize) )
    {
      *a2 = 0;
      goto LABEL_28;
    }
    v13 = username;
    *a2 = 1;
    Info = NetUserGetInfo(0, v13, 0x18u, &bufptr);
    v9 = Info;
    if ( Info > 0 )
      v9 = (unsigned __int16)Info | 0xC0070000;
    if ( v9 >= 0 )
    {
      v15 = bufptr;
      if ( bufptr )
      {
        *a3 = *(_DWORD *)bufptr;
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(*((_QWORD *)v15 + 1) + 2 * v16) );
        if ( (int)v16 + 1 < (unsigned int)v16 || (v17 = 2LL * (unsigned int)(v16 + 1), v17 > 0xFFFFFFFF) )
        {
          v9 = -1073741675;
          goto LABEL_29;
        }
        v18 = (unsigned int)v17;
        v7 = LocalAlloc(0x40u, (unsigned int)v17);
        if ( !v7 )
        {
          v9 = -1073741801;
          goto LABEL_29;
        }
        v19 = (const void *)*((_QWORD *)bufptr + 1);
        if ( v19 )
        {
          memcpy_0(v7, v19, v18);
LABEL_28:
          *a4 = (unsigned __int16 *)v7;
          v9 = 0;
          v7 = 0;
        }
      }
    }
  }
LABEL_29:
  CloseHandle(TokenHandle);
  if ( username )
    LocalFree((HLOCAL)username);
  if ( v7 )
    LocalFree(v7);
  if ( String2 )
    LocalFree(String2);
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180015518  push    rbp
0x18001551a  push    rbx
0x18001551b  push    rsi
0x18001551c  push    rdi
0x18001551d  push    r12
0x18001551f  push    r14
0x180015521  push    r15
0x180015523  lea     rbp, [rsp-27h]
0x180015528  sub     rsp, 100h
0x18001552f  mov     rax, cs:__security_cookie
0x180015536  xor     rax, rsp
0x180015539  mov     [rbp+57h+var_40], rax
0x18001553d  xor     r12d, r12d
0x180015540  mov     [rbp+57h+Sid2], 101h
0x180015547  mov     r14, r8
0x18001554a  mov     [rsp+130h+TokenHandle], r12
0x18001554f  mov     rsi, rdx
0x180015552  mov     [rsp+130h+username], r12
0x180015557  xor     edx, edx; Val
0x180015559  mov     [rsp+130h+String2], r12
0x18001555e  lea     ebx, [r12+58h]
0x180015563  mov     [rsp+130h+bufptr], r12
0x180015568  mov     r8d, ebx; Size
0x18001556b  mov     [rsp+130h+nSize], r12d
0x180015570  lea     rcx, [rbp+57h+TokenInformation]; void *
0x180015574  mov     [rbp+57h+var_6C], 5000000h
0x18001557b  mov     r15, r9
0x18001557e  mov     [rbp+57h+var_68], 12h
0x180015585  mov     edi, r12d
0x180015588  call    memset_0
0x18001558d  mov     [r14], r12d
0x180015590  lea     r9, [rsp+130h+TokenHandle]; TokenHandle
0x180015595  mov     [rsi], r12d
0x180015598  lea     edx, [rbx-50h]; DesiredAccess
0x18001559b  mov     r8b, 1; OpenAsSelf
0x18001559e  mov     [r15], r12
0x1800155a1  lea     rcx, [rbx-5Ah]; ThreadHandle
0x1800155a5  mov     [rsp+130h+TokenInformationLength], ebx
0x1800155a9  call    cs:__imp_NtOpenThreadToken
0x1800155af  mov     ebx, eax
0x1800155b1  test    eax, eax
0x1800155b3  jns     short loc_1800155DB
0x1800155b5  cmp     eax, 0C000007Ch
0x1800155ba  jnz     loc_180015762
0x1800155c0  lea     r8, [rsp+130h+TokenHandle]; TokenHandle
0x1800155c5  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800155c9  lea     edx, [r12+8]; DesiredAccess
0x1800155ce  call    cs:__imp_NtOpenProcessToken
0x1800155d4  mov     ebx, eax
0x1800155d6  jmp     loc_180015762
0x1800155db  mov     r9d, [rsp+130h+TokenInformationLength]; TokenInformationLength
0x1800155e0  lea     rax, [rsp+130h+TokenInformationLength]
0x1800155e5  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x1800155ea  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800155ee  mov     edx, 1; TokenInformationClass
0x1800155f3  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x1800155f8  call    cs:__imp_NtQueryInformationToken
0x1800155fe  mov     ebx, eax
0x180015600  test    eax, eax
0x180015602  js      loc_180015762
0x180015608  mov     rcx, [rbp+57h+TokenInformation]; Sid1
0x18001560c  lea     rdx, [rbp+57h+Sid2]; Sid2
0x180015610  call    cs:__imp_RtlEqualSid
0x180015616  test    al, al
0x180015618  jz      short loc_18001562B
0x18001561a  mov     [r14], r12d
0x18001561d  mov     dword ptr [rsi], 1
0x180015623  mov     [r15], r12
0x180015626  jmp     loc_180015762
0x18001562b  mov     rdx, [rbp+57h+TokenInformation]; void *
0x18001562f  lea     r9, [rsp+130h+String2]; unsigned __int16 **
0x180015634  lea     r8, [rsp+130h+username]; unsigned __int16 **
0x180015639  call    ?CallADVAPILookupSids@CProviderRegistrationCache@@AEAAKPEAXPEAPEAG1@Z; CProviderRegistrationCache::CallADVAPILookupSids(void *,ushort * *,ushort * *)
0x18001563e  mov     ebx, eax
0x180015640  test    eax, eax
0x180015642  jle     short loc_18001564D
0x180015644  movzx   ebx, ax
0x180015647  or      ebx, 0C0070000h
0x18001564d  test    ebx, ebx
0x18001564f  js      loc_180015762
0x180015655  lea     r8, [rsp+130h+nSize]; nSize
0x18001565a  mov     [rsp+130h+nSize], 10h
0x180015662  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180015666  xor     ecx, ecx; NameType
0x180015668  call    cs:__imp_GetComputerNameExW
0x18001566e  test    eax, eax
0x180015670  jnz     short loc_180015690
0x180015672  call    cs:__imp_GetLastError
0x180015678  mov     ebx, eax
0x18001567a  test    eax, eax
0x18001567c  jle     loc_180015762
0x180015682  movzx   ebx, ax
0x180015685  or      ebx, 0C0070000h
0x18001568b  jmp     loc_180015762
0x180015690  mov     r8d, [rsp+130h+nSize]; MaxCount
0x180015695  lea     rcx, [rbp+57h+Buffer]; String1
0x180015699  mov     rdx, [rsp+130h+String2]; String2
0x18001569e  call    cs:__imp__wcsnicmp
0x1800156a4  test    eax, eax
0x1800156a6  jnz     loc_180015756
0x1800156ac  mov     rdx, [rsp+130h+username]; username
0x1800156b1  lea     r9, [rsp+130h+bufptr]; bufptr
0x1800156b6  lea     r8d, [rax+18h]; level
0x1800156ba  mov     dword ptr [rsi], 1
0x1800156c0  xor     ecx, ecx; servername
0x1800156c2  call    cs:__imp_NetUserGetInfo
0x1800156c8  mov     ebx, eax
0x1800156ca  test    eax, eax
0x1800156cc  jle     short loc_1800156D7
0x1800156ce  movzx   ebx, ax
0x1800156d1  or      ebx, 0C0070000h
0x1800156d7  test    ebx, ebx
0x1800156d9  js      loc_180015762
0x1800156df  mov     rcx, [rsp+130h+bufptr]
0x1800156e4  test    rcx, rcx
0x1800156e7  jz      short loc_180015762
0x1800156e9  mov     eax, [rcx]
0x1800156eb  mov     [r14], eax
0x1800156ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800156f2  mov     rdx, [rcx+8]
0x1800156f6  inc     rax
0x1800156f9  cmp     [rdx+rax*2], r12w
0x1800156fe  jnz     short loc_1800156F6
0x180015700  lea     ecx, [rax+1]
0x180015703  cmp     ecx, eax
0x180015705  jnb     short loc_18001570E
0x180015707  mov     ebx, 0C0000095h
0x18001570c  jmp     short loc_180015762
0x18001570e  mov     eax, ecx
0x180015710  mov     ecx, 0FFFFFFFFh
0x180015715  add     rax, rax
0x180015718  cmp     rax, rcx
0x18001571b  ja      short loc_180015707
0x18001571d  mov     edx, eax; uBytes
0x18001571f  mov     ecx, 40h ; '@'; uFlags
0x180015724  mov     esi, eax
0x180015726  call    cs:__imp_LocalAlloc
0x18001572c  mov     rdi, rax
0x18001572f  test    rax, rax
0x180015732  jnz     short loc_18001573B
0x180015734  mov     ebx, 0C0000017h
0x180015739  jmp     short loc_180015762
0x18001573b  mov     rax, [rsp+130h+bufptr]
0x180015740  mov     rdx, [rax+8]; Src
0x180015744  test    rdx, rdx
0x180015747  jz      short loc_180015762
0x180015749  mov     r8, rsi; Size
0x18001574c  mov     rcx, rdi; void *
0x18001574f  call    memcpy_0
0x180015754  jmp     short loc_180015759
0x180015756  mov     [rsi], r12d
0x180015759  mov     [r15], rdi
0x18001575c  mov     ebx, r12d
0x18001575f  mov     rdi, r12
0x180015762  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x180015767  call    cs:__imp_CloseHandle
0x18001576d  mov     rcx, [rsp+130h+username]; hMem
0x180015772  test    rcx, rcx
0x180015775  jz      short loc_18001577D
0x180015777  call    cs:__imp_LocalFree
0x18001577d  test    rdi, rdi
0x180015780  jz      short loc_18001578B
0x180015782  mov     rcx, rdi; hMem
0x180015785  call    cs:__imp_LocalFree
0x18001578b  mov     rcx, [rsp+130h+String2]; hMem
0x180015790  test    rcx, rcx
0x180015793  jz      short loc_18001579B
0x180015795  call    cs:__imp_LocalFree
0x18001579b  mov     rcx, [rsp+130h+bufptr]; Buffer
0x1800157a0  test    rcx, rcx
0x1800157a3  jz      short loc_1800157AB
0x1800157a5  call    cs:__imp_NetApiBufferFree
0x1800157ab  mov     eax, ebx
0x1800157ad  mov     rcx, [rbp+57h+var_40]
0x1800157b1  xor     rcx, rsp; StackCookie
0x1800157b4  call    __security_check_cookie
0x1800157b9  add     rsp, 100h
0x1800157c0  pop     r15
0x1800157c2  pop     r14
0x1800157c4  pop     r12
0x1800157c6  pop     rdi
0x1800157c7  pop     rsi
0x1800157c8  pop     rbx
0x1800157c9  pop     rbp
0x1800157ca  retn
```
