# L32pNotifyMpr

- ea: `0x18005d758`
- end: `0x18005dabf`
- name: `L32pNotifyMpr`
- size: `871`
- prototype: `char __fastcall(void *Src, _WORD *, const void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800380f8`

## callees

- `0x18005d5e8`
- `0x18005d648`
- `0x18005d758`
- `0x180072042`
- `0x1800720b0`
- `0x180074010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18005da92`
- `ntdll!RtlFreeHeap` at `0x18005da92`
- `ntdll!RtlAllocateHeap` at `0x18005d8d6`
- `ntdll!RtlAllocateHeap` at `0x18005d8d6`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d9da`
- `ntdll!RtlLeaveCriticalSection` at `0x18005d9da`
- `ntdll!RtlEnterCriticalSection` at `0x18005d97a`
- `ntdll!RtlEnterCriticalSection` at `0x18005d97a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005d7f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005d7f0`
- `KERNEL32!LocalFree` at `0x18005da62`
- `KERNEL32!LocalFree` at `0x18005da62`
- `KERNEL32!GetProcAddress` at `0x18005d9c0`
- `KERNEL32!GetProcAddress` at `0x18005d9c0`
- `KERNEL32!LoadLibraryExA` at `0x18005d99e`
- `KERNEL32!LoadLibraryExA` at `0x18005d99e`

## string_xrefs

- `0x18005d991`: `mpr.dll`

## pseudocode

```c
char __fastcall L32pNotifyMpr(void *Src, _WORD *a2, const void *a3, void *a4)
{
  char *DefaultDomainName; // rax
  unsigned __int16 v8; // r15
  unsigned __int16 v9; // r12
  const void *v10; // rdi
  unsigned int v11; // r13d
  _QWORD *v12; // rbx
  size_t v13; // r8
  void *v14; // rcx
  void *v15; // rcx
  HMODULE Library; // rax
  __int64 v17; // rcx
  _BYTE *v18; // rax
  _WORD v20[2]; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int16 v21; // [rsp+54h] [rbp-75h] BYREF
  _WORD v22[2]; // [rsp+58h] [rbp-71h] BYREF
  DWORD ReturnLength; // [rsp+5Ch] [rbp-6Dh] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-69h] BYREF
  __int128 v25; // [rsp+68h] [rbp-61h] BYREF
  __int128 v26; // [rsp+78h] [rbp-51h]
  __int128 v27; // [rsp+88h] [rbp-41h]
  __int64 v28; // [rsp+98h] [rbp-31h]
  _OWORD TokenInformation[3]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v30; // [rsp+D0h] [rbp+7h]

  LOBYTE(DefaultDomainName) = 0;
  hMem = 0;
  LODWORD(v28) = 0;
  v20[0] = 0;
  v21 = 0;
  v22[0] = 0;
  ReturnLength = 0;
  v8 = 0;
  v30 = 0;
  v9 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( Src )
  {
    LODWORD(DefaultDomainName) = GetTokenInformation(a4, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
    if ( (_DWORD)DefaultDomainName )
    {
      LOBYTE(DefaultDomainName) = BYTE12(TokenInformation[0]);
      if ( *((_QWORD *)&TokenInformation[0] + 1) != 997 && *((_QWORD *)&TokenInformation[0] + 1) != 996 )
      {
        v10 = 0;
        if ( a2 && *a2 )
        {
          if ( *a2 != 46 || a2[1] )
          {
            v10 = a2;
          }
          else
          {
            DefaultDomainName = (char *)L32GetDefaultDomainName();
            v10 = DefaultDomainName;
            if ( !DefaultDomainName )
              return (char)DefaultDomainName;
          }
        }
        LODWORD(DefaultDomainName) = GetUshortStringSize(Src, v20);
        if ( (int)DefaultDomainName >= 0 )
        {
          if ( v10 )
          {
            LODWORD(DefaultDomainName) = GetUshortStringSize(v10, &v21);
            if ( (int)DefaultDomainName < 0 )
              return (char)DefaultDomainName;
            v8 = v21;
          }
          if ( a3 )
          {
            LODWORD(DefaultDomainName) = GetUshortStringSize(a3, v22);
            if ( (int)DefaultDomainName < 0 )
              return (char)DefaultDomainName;
            v9 = v22[0];
          }
          v11 = v8 + v9 + v20[0] + 56;
          DefaultDomainName = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v11);
          v12 = DefaultDomainName;
          if ( DefaultDomainName )
          {
            v13 = v20[0];
            *((_WORD *)DefaultDomainName + 12) = v20[0];
            *((_WORD *)DefaultDomainName + 13) = v13;
            *((_QWORD *)DefaultDomainName + 4) = DefaultDomainName + 56;
            *(_DWORD *)DefaultDomainName = 2;
            memcpy_0(DefaultDomainName + 56, Src, v13);
            if ( v10 )
            {
              v14 = (void *)(v12[4] + *((unsigned __int16 *)v12 + 13));
              v12[2] = v14;
              *((_WORD *)v12 + 4) = v8;
              *((_WORD *)v12 + 5) = v8;
              memcpy_0(v14, v10, v8);
            }
            if ( a3 )
            {
              v15 = (void *)(v12[4] + *((unsigned __int16 *)v12 + 5) + (unsigned __int64)*((unsigned __int16 *)v12 + 13));
              v12[6] = v15;
              *((_WORD *)v12 + 20) = v9;
              *((_WORD *)v12 + 21) = v9;
              memcpy_0(v15, a3, v9);
            }
            if ( !Logon32MprHandle )
            {
              RtlEnterCriticalSection(&Logon32Lock);
              if ( !Logon32MprHandle )
              {
                Library = LoadLibraryExA("mpr.dll", 0, 0x800u);
                Logon32MprHandle = (__int64)Library;
                if ( Library )
                  Logon32LogonNotify = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(Library, "WNetLogonNotify");
              }
              RtlLeaveCriticalSection(&Logon32Lock);
            }
            if ( Logon32LogonNotify )
            {
              v25 = *(_OWORD *)v12;
              v26 = *((_OWORD *)v12 + 1);
              v27 = *((_OWORD *)v12 + 2);
              v28 = v12[6];
              if ( !(unsigned int)Logon32LogonNotify(
                                    L"Windows NT Network Provider",
                                    (char *)TokenInformation + 8,
                                    L"MSV1_0:Interactive",
                                    v12,
                                    L"MSV1_0:Interactive",
                                    &v25,
                                    L"SvcCtl",
                                    0,
                                    &hMem) )
              {
                if ( hMem )
                  LocalFree(hMem);
              }
            }
            v17 = v11;
            v18 = v12;
            do
            {
              *v18++ = 0;
              --v17;
            }
            while ( v17 );
            LOBYTE(DefaultDomainName) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
          }
        }
      }
    }
  }
  return (char)DefaultDomainName;
}

```

## disassembly

```asm
0x18005d758  push    rbp
0x18005d75a  push    rbx
0x18005d75b  push    rsi
0x18005d75c  push    rdi
0x18005d75d  push    r12
0x18005d75f  push    r13
0x18005d761  push    r14
0x18005d763  push    r15
0x18005d765  lea     rbp, [rsp-1Fh]
0x18005d76a  sub     rsp, 0E8h
0x18005d771  mov     rax, cs:__security_cookie
0x18005d778  xor     rax, rsp
0x18005d77b  mov     [rbp+57h+var_48], rax
0x18005d77f  xor     r13d, r13d
0x18005d782  xorps   xmm0, xmm0
0x18005d785  xor     eax, eax
0x18005d787  mov     [rbp+57h+hMem], r13
0x18005d78b  mov     dword ptr [rbp+57h+var_88], eax
0x18005d78e  mov     r10, r9
0x18005d791  mov     [rbp+57h+var_D0], r13w
0x18005d796  mov     r14, r8
0x18005d799  mov     [rbp+57h+var_CC], r13w
0x18005d79e  mov     rbx, rdx
0x18005d7a1  mov     [rbp+57h+var_C8], r13w
0x18005d7a6  mov     rsi, rcx
0x18005d7a9  mov     [rbp+57h+var_C4], r13d
0x18005d7ad  mov     r15d, r13d
0x18005d7b0  mov     [rbp+57h+var_50], rax
0x18005d7b4  mov     r12d, r13d
0x18005d7b7  movups  [rbp+57h+var_B8], xmm0
0x18005d7bb  movups  [rbp+57h+var_A8], xmm0
0x18005d7bf  movups  [rbp+57h+var_98], xmm0
0x18005d7c3  movups  [rbp+57h+TokenInformation], xmm0
0x18005d7c7  movups  [rbp+57h+var_70], xmm0
0x18005d7cb  movups  [rbp+57h+var_60], xmm0
0x18005d7cf  test    rcx, rcx
0x18005d7d2  jz      loc_18005DA9E
0x18005d7d8  lea     rax, [rbp+57h+var_C4]
0x18005d7dc  mov     rcx, r10; TokenHandle
0x18005d7df  lea     r9d, [r13+38h]; TokenInformationLength
0x18005d7e3  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18005d7e8  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18005d7ec  lea     edx, [r13+0Ah]; TokenInformationClass
0x18005d7f0  call    cs:__imp_GetTokenInformation
0x18005d7f7  nop     dword ptr [rax+rax+00h]
0x18005d7fc  test    eax, eax
0x18005d7fe  jz      loc_18005DA9E
0x18005d804  cmp     dword ptr [rbp+57h+TokenInformation+8], 3E5h
0x18005d80b  mov     rax, qword ptr [rbp+57h+TokenInformation+0Ch]
0x18005d80f  jnz     short loc_18005D819
0x18005d811  test    eax, eax
0x18005d813  jz      loc_18005DA9E
0x18005d819  cmp     dword ptr [rbp+57h+TokenInformation+8], 3E4h
0x18005d820  jnz     short loc_18005D82A
0x18005d822  test    eax, eax
0x18005d824  jz      loc_18005DA9E
0x18005d82a  mov     rdi, r13
0x18005d82d  test    rbx, rbx
0x18005d830  jz      short loc_18005D85B
0x18005d832  cmp     [rbx], r13w
0x18005d836  jz      short loc_18005D85B
0x18005d838  cmp     word ptr [rbx], 2Eh ; '.'
0x18005d83c  jnz     short loc_18005D858
0x18005d83e  cmp     [rbx+2], r13w
0x18005d843  jnz     short loc_18005D858
0x18005d845  call    L32GetDefaultDomainName
0x18005d84a  mov     rdi, rax
0x18005d84d  test    rax, rax
0x18005d850  jz      loc_18005DA9E
0x18005d856  jmp     short loc_18005D85B
0x18005d858  mov     rdi, rbx
0x18005d85b  lea     rdx, [rbp+57h+var_D0]
0x18005d85f  mov     rcx, rsi
0x18005d862  call    GetUshortStringSize
0x18005d867  test    eax, eax
0x18005d869  js      loc_18005DA9E
0x18005d86f  test    rdi, rdi
0x18005d872  jz      short loc_18005D88D
0x18005d874  lea     rdx, [rbp+57h+var_CC]
0x18005d878  mov     rcx, rdi
0x18005d87b  call    GetUshortStringSize
0x18005d880  test    eax, eax
0x18005d882  js      loc_18005DA9E
0x18005d888  movzx   r15d, [rbp+57h+var_CC]
0x18005d88d  test    r14, r14
0x18005d890  jz      short loc_18005D8AB
0x18005d892  lea     rdx, [rbp+57h+var_C8]
0x18005d896  mov     rcx, r14
0x18005d899  call    GetUshortStringSize
0x18005d89e  test    eax, eax
0x18005d8a0  js      loc_18005DA9E
0x18005d8a6  movzx   r12d, [rbp+57h+var_C8]
0x18005d8ab  movzx   r13d, [rbp+57h+var_D0]
0x18005d8b0  mov     edx, 8; Flags
0x18005d8b5  movzx   ecx, r12w
0x18005d8b9  add     r13d, 38h ; '8'
0x18005d8bd  movzx   eax, r15w
0x18005d8c1  add     ecx, eax
0x18005d8c3  add     r13d, ecx
0x18005d8c6  mov     rcx, gs:60h
0x18005d8cf  mov     r8d, r13d; Size
0x18005d8d2  mov     rcx, [rcx+30h]; HeapHandle
0x18005d8d6  call    cs:__imp_RtlAllocateHeap
0x18005d8dd  nop     dword ptr [rax+rax+00h]
0x18005d8e2  mov     rbx, rax
0x18005d8e5  test    rax, rax
0x18005d8e8  jz      loc_18005DA9E
0x18005d8ee  movzx   r8d, [rbp+57h+var_D0]; Size
0x18005d8f3  lea     rcx, [rax+38h]; void *
0x18005d8f7  mov     rdx, rsi; Src
0x18005d8fa  mov     [rax+18h], r8w
0x18005d8ff  mov     [rax+1Ah], r8w
0x18005d904  mov     [rax+20h], rcx
0x18005d908  mov     dword ptr [rax], 2
0x18005d90e  call    memcpy_0
0x18005d913  test    rdi, rdi
0x18005d916  jz      short loc_18005D93A
0x18005d918  movzx   ecx, word ptr [rbx+1Ah]
0x18005d91c  mov     rdx, rdi; Src
0x18005d91f  add     rcx, [rbx+20h]; void *
0x18005d923  movzx   r8d, r15w; Size
0x18005d927  mov     [rbx+10h], rcx
0x18005d92b  mov     [rbx+8], r8w
0x18005d930  mov     [rbx+0Ah], r8w
0x18005d935  call    memcpy_0
0x18005d93a  xor     edi, edi
0x18005d93c  test    r14, r14
0x18005d93f  jz      short loc_18005D96A
0x18005d941  movzx   ecx, word ptr [rbx+1Ah]
0x18005d945  mov     rdx, r14; Src
0x18005d948  movzx   eax, word ptr [rbx+0Ah]
0x18005d94c  movzx   r8d, r12w; Size
0x18005d950  add     rcx, rax
0x18005d953  add     rcx, [rbx+20h]; void *
0x18005d957  mov     [rbx+30h], rcx
0x18005d95b  mov     [rbx+28h], r8w
0x18005d960  mov     [rbx+2Ah], r8w
0x18005d965  call    memcpy_0
0x18005d96a  cmp     cs:Logon32MprHandle, rdi
0x18005d971  jnz     short loc_18005D9E6
0x18005d973  lea     rcx, Logon32Lock; CriticalSection
0x18005d97a  call    cs:__imp_RtlEnterCriticalSection
0x18005d981  nop     dword ptr [rax+rax+00h]
0x18005d986  cmp     cs:Logon32MprHandle, rdi
0x18005d98d  jnz     short loc_18005D9D3
0x18005d98f  xor     edx, edx; hFile
0x18005d991  lea     rcx, aMprDll; "mpr.dll"
0x18005d998  mov     r8d, 800h; dwFlags
0x18005d99e  call    cs:__imp_LoadLibraryExA
0x18005d9a5  nop     dword ptr [rax+rax+00h]
0x18005d9aa  mov     cs:Logon32MprHandle, rax
0x18005d9b1  test    rax, rax
0x18005d9b4  jz      short loc_18005D9D3
0x18005d9b6  lea     rdx, aWnetlogonnotif; "WNetLogonNotify"
0x18005d9bd  mov     rcx, rax; hModule
0x18005d9c0  call    cs:__imp_GetProcAddress
0x18005d9c7  nop     dword ptr [rax+rax+00h]
0x18005d9cc  mov     cs:Logon32LogonNotify, rax
0x18005d9d3  lea     rcx, Logon32Lock; CriticalSection
0x18005d9da  call    cs:__imp_RtlLeaveCriticalSection
0x18005d9e1  nop     dword ptr [rax+rax+00h]
0x18005d9e6  mov     rax, cs:Logon32LogonNotify
0x18005d9ed  test    rax, rax
0x18005d9f0  jz      short loc_18005DA6E
0x18005d9f2  movups  xmm0, xmmword ptr [rbx]
0x18005d9f5  lea     rcx, [rbp+57h+hMem]
0x18005d9f9  mov     r9, rbx
0x18005d9fc  mov     [rsp+120h+var_E0], rcx
0x18005da01  lea     r8, aMsv10Interacti; "MSV1_0:Interactive"
0x18005da08  movups  [rbp+57h+var_B8], xmm0
0x18005da0c  mov     [rsp+120h+var_E8], rdi
0x18005da11  lea     rcx, aSvcctl; "SvcCtl"
0x18005da18  movups  xmm1, xmmword ptr [rbx+10h]
0x18005da1c  mov     [rsp+120h+var_F0], rcx
0x18005da21  lea     rdx, [rbp+57h+TokenInformation+8]
0x18005da25  lea     rcx, [rbp+57h+var_B8]
0x18005da29  movups  [rbp+57h+var_A8], xmm1
0x18005da2d  mov     [rsp+120h+var_F8], rcx
0x18005da32  lea     rcx, aWindowsNtNetwo; "Windows NT Network Provider"
0x18005da39  movups  xmm0, xmmword ptr [rbx+20h]
0x18005da3d  mov     [rsp+120h+ReturnLength], r8
0x18005da42  movups  [rbp+57h+var_98], xmm0
0x18005da46  movsd   xmm1, qword ptr [rbx+30h]
0x18005da4b  movsd   [rbp+57h+var_88], xmm1
0x18005da50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da55  test    eax, eax
0x18005da57  jnz     short loc_18005DA6E
0x18005da59  mov     rcx, [rbp+57h+hMem]; hMem
0x18005da5d  test    rcx, rcx
0x18005da60  jz      short loc_18005DA6E
0x18005da62  call    cs:__imp_LocalFree
0x18005da69  nop     dword ptr [rax+rax+00h]
0x18005da6e  mov     ecx, r13d
0x18005da71  mov     rax, rbx
0x18005da74  mov     [rax], dil
0x18005da77  inc     rax
0x18005da7a  sub     rcx, 1
0x18005da7e  jnz     short loc_18005DA74
0x18005da80  mov     rcx, gs:60h
0x18005da89  mov     r8, rbx; P
0x18005da8c  xor     edx, edx; Flags
0x18005da8e  mov     rcx, [rcx+30h]; HeapHandle
0x18005da92  call    cs:__imp_RtlFreeHeap
0x18005da99  nop     dword ptr [rax+rax+00h]
0x18005da9e  mov     rcx, [rbp+57h+var_48]
0x18005daa2  xor     rcx, rsp; StackCookie
0x18005daa5  call    __security_check_cookie
0x18005daaa  add     rsp, 0E8h
0x18005dab1  pop     r15
0x18005dab3  pop     r14
0x18005dab5  pop     r13
0x18005dab7  pop     r12
0x18005dab9  pop     rdi
0x18005daba  pop     rsi
0x18005dabb  pop     rbx
0x18005dabc  pop     rbp
0x18005dabd  retn
```
