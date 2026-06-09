# L32pNotifyMpr

- ea: `0x180051e8c`
- end: `0x1800521c2`
- name: `L32pNotifyMpr`
- size: `822`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800344c4`

## callees

- `0x180051d44`
- `0x180051d90`
- `0x180051e8c`
- `0x180065042`
- `0x180065090`
- `0x180066010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18005219c`
- `ntdll!RtlFreeHeap` at `0x18005219c`
- `ntdll!RtlAllocateHeap` at `0x180052004`
- `ntdll!RtlAllocateHeap` at `0x180052004`
- `ntdll!RtlLeaveCriticalSection` at `0x1800520f0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800520f0`
- `ntdll!RtlEnterCriticalSection` at `0x1800520a2`
- `ntdll!RtlEnterCriticalSection` at `0x1800520a2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051f24`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180051f24`
- `KERNEL32!LocalFree` at `0x180052172`
- `KERNEL32!LocalFree` at `0x180052172`
- `KERNEL32!GetProcAddress` at `0x1800520dc`
- `KERNEL32!GetProcAddress` at `0x1800520dc`
- `KERNEL32!LoadLibraryExA` at `0x1800520c0`
- `KERNEL32!LoadLibraryExA` at `0x1800520c0`

## string_xrefs

- `0x1800520b3`: `mpr.dll`

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
0x180051e8c  push    rbp
0x180051e8e  push    rbx
0x180051e8f  push    rsi
0x180051e90  push    rdi
0x180051e91  push    r12
0x180051e93  push    r13
0x180051e95  push    r14
0x180051e97  push    r15
0x180051e99  lea     rbp, [rsp-1Fh]
0x180051e9e  sub     rsp, 0E8h
0x180051ea5  mov     rax, cs:__security_cookie
0x180051eac  xor     rax, rsp
0x180051eaf  mov     [rbp+57h+var_48], rax
0x180051eb3  xor     r13d, r13d
0x180051eb6  xorps   xmm0, xmm0
0x180051eb9  xor     eax, eax
0x180051ebb  mov     [rbp+57h+hMem], r13
0x180051ebf  mov     dword ptr [rbp+57h+var_88], eax
0x180051ec2  mov     r10, r9
0x180051ec5  mov     [rbp+57h+var_D0], r13w
0x180051eca  mov     r14, r8
0x180051ecd  mov     [rbp+57h+var_CC], r13w
0x180051ed2  mov     rbx, rdx
0x180051ed5  mov     [rbp+57h+var_C8], r13w
0x180051eda  mov     rsi, rcx
0x180051edd  mov     [rbp+57h+var_C4], r13d
0x180051ee1  mov     r15d, r13d
0x180051ee4  mov     [rbp+57h+var_50], rax
0x180051ee8  mov     r12d, r13d
0x180051eeb  movups  [rbp+57h+var_B8], xmm0
0x180051eef  movups  [rbp+57h+var_A8], xmm0
0x180051ef3  movups  [rbp+57h+var_98], xmm0
0x180051ef7  movups  [rbp+57h+TokenInformation], xmm0
0x180051efb  movups  [rbp+57h+var_70], xmm0
0x180051eff  movups  [rbp+57h+var_60], xmm0
0x180051f03  test    rcx, rcx
0x180051f06  jz      loc_1800521A2
0x180051f0c  lea     rax, [rbp+57h+var_C4]
0x180051f10  mov     rcx, r10; TokenHandle
0x180051f13  lea     r9d, [r13+38h]; TokenInformationLength
0x180051f17  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x180051f1c  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180051f20  lea     edx, [r13+0Ah]; TokenInformationClass
0x180051f24  call    cs:__imp_GetTokenInformation
0x180051f2a  test    eax, eax
0x180051f2c  jz      loc_1800521A2
0x180051f32  cmp     dword ptr [rbp+57h+TokenInformation+8], 3E5h
0x180051f39  mov     rax, qword ptr [rbp+57h+TokenInformation+0Ch]
0x180051f3d  jnz     short loc_180051F47
0x180051f3f  test    eax, eax
0x180051f41  jz      loc_1800521A2
0x180051f47  cmp     dword ptr [rbp+57h+TokenInformation+8], 3E4h
0x180051f4e  jnz     short loc_180051F58
0x180051f50  test    eax, eax
0x180051f52  jz      loc_1800521A2
0x180051f58  mov     rdi, r13
0x180051f5b  test    rbx, rbx
0x180051f5e  jz      short loc_180051F89
0x180051f60  cmp     [rbx], r13w
0x180051f64  jz      short loc_180051F89
0x180051f66  cmp     word ptr [rbx], 2Eh ; '.'
0x180051f6a  jnz     short loc_180051F86
0x180051f6c  cmp     [rbx+2], r13w
0x180051f71  jnz     short loc_180051F86
0x180051f73  call    L32GetDefaultDomainName
0x180051f78  mov     rdi, rax
0x180051f7b  test    rax, rax
0x180051f7e  jz      loc_1800521A2
0x180051f84  jmp     short loc_180051F89
0x180051f86  mov     rdi, rbx
0x180051f89  lea     rdx, [rbp+57h+var_D0]
0x180051f8d  mov     rcx, rsi
0x180051f90  call    GetUshortStringSize
0x180051f95  test    eax, eax
0x180051f97  js      loc_1800521A2
0x180051f9d  test    rdi, rdi
0x180051fa0  jz      short loc_180051FBB
0x180051fa2  lea     rdx, [rbp+57h+var_CC]
0x180051fa6  mov     rcx, rdi
0x180051fa9  call    GetUshortStringSize
0x180051fae  test    eax, eax
0x180051fb0  js      loc_1800521A2
0x180051fb6  movzx   r15d, [rbp+57h+var_CC]
0x180051fbb  test    r14, r14
0x180051fbe  jz      short loc_180051FD9
0x180051fc0  lea     rdx, [rbp+57h+var_C8]
0x180051fc4  mov     rcx, r14
0x180051fc7  call    GetUshortStringSize
0x180051fcc  test    eax, eax
0x180051fce  js      loc_1800521A2
0x180051fd4  movzx   r12d, [rbp+57h+var_C8]
0x180051fd9  movzx   r13d, [rbp+57h+var_D0]
0x180051fde  mov     edx, 8; Flags
0x180051fe3  movzx   ecx, r12w
0x180051fe7  add     r13d, 38h ; '8'
0x180051feb  movzx   eax, r15w
0x180051fef  add     ecx, eax
0x180051ff1  add     r13d, ecx
0x180051ff4  mov     rcx, gs:60h
0x180051ffd  mov     r8d, r13d; Size
0x180052000  mov     rcx, [rcx+30h]; HeapHandle
0x180052004  call    cs:__imp_RtlAllocateHeap
0x18005200a  mov     rbx, rax
0x18005200d  test    rax, rax
0x180052010  jz      loc_1800521A2
0x180052016  movzx   r8d, [rbp+57h+var_D0]; Size
0x18005201b  lea     rcx, [rax+38h]; void *
0x18005201f  mov     rdx, rsi; Src
0x180052022  mov     [rax+18h], r8w
0x180052027  mov     [rax+1Ah], r8w
0x18005202c  mov     [rax+20h], rcx
0x180052030  mov     dword ptr [rax], 2
0x180052036  call    memcpy_0
0x18005203b  test    rdi, rdi
0x18005203e  jz      short loc_180052062
0x180052040  movzx   ecx, word ptr [rbx+1Ah]
0x180052044  mov     rdx, rdi; Src
0x180052047  add     rcx, [rbx+20h]; void *
0x18005204b  movzx   r8d, r15w; Size
0x18005204f  mov     [rbx+10h], rcx
0x180052053  mov     [rbx+8], r8w
0x180052058  mov     [rbx+0Ah], r8w
0x18005205d  call    memcpy_0
0x180052062  xor     edi, edi
0x180052064  test    r14, r14
0x180052067  jz      short loc_180052092
0x180052069  movzx   ecx, word ptr [rbx+1Ah]
0x18005206d  mov     rdx, r14; Src
0x180052070  movzx   eax, word ptr [rbx+0Ah]
0x180052074  movzx   r8d, r12w; Size
0x180052078  add     rcx, rax
0x18005207b  add     rcx, [rbx+20h]; void *
0x18005207f  mov     [rbx+30h], rcx
0x180052083  mov     [rbx+28h], r8w
0x180052088  mov     [rbx+2Ah], r8w
0x18005208d  call    memcpy_0
0x180052092  cmp     cs:Logon32MprHandle, rdi
0x180052099  jnz     short loc_1800520F6
0x18005209b  lea     rcx, Logon32Lock; CriticalSection
0x1800520a2  call    cs:__imp_RtlEnterCriticalSection
0x1800520a8  cmp     cs:Logon32MprHandle, rdi
0x1800520af  jnz     short loc_1800520E9
0x1800520b1  xor     edx, edx; hFile
0x1800520b3  lea     rcx, aMprDll; "mpr.dll"
0x1800520ba  mov     r8d, 800h; dwFlags
0x1800520c0  call    cs:__imp_LoadLibraryExA
0x1800520c6  mov     cs:Logon32MprHandle, rax
0x1800520cd  test    rax, rax
0x1800520d0  jz      short loc_1800520E9
0x1800520d2  lea     rdx, aWnetlogonnotif; "WNetLogonNotify"
0x1800520d9  mov     rcx, rax; hModule
0x1800520dc  call    cs:__imp_GetProcAddress
0x1800520e2  mov     cs:Logon32LogonNotify, rax
0x1800520e9  lea     rcx, Logon32Lock; CriticalSection
0x1800520f0  call    cs:__imp_RtlLeaveCriticalSection
0x1800520f6  mov     rax, cs:Logon32LogonNotify
0x1800520fd  test    rax, rax
0x180052100  jz      short loc_180052178
0x180052102  movups  xmm0, xmmword ptr [rbx]
0x180052105  lea     rcx, [rbp+57h+hMem]
0x180052109  mov     r9, rbx
0x18005210c  mov     [rsp+120h+var_E0], rcx
0x180052111  lea     r8, aMsv10Interacti; "MSV1_0:Interactive"
0x180052118  movups  [rbp+57h+var_B8], xmm0
0x18005211c  mov     [rsp+120h+var_E8], rdi
0x180052121  lea     rcx, aSvcctl; "SvcCtl"
0x180052128  movups  xmm1, xmmword ptr [rbx+10h]
0x18005212c  mov     [rsp+120h+var_F0], rcx
0x180052131  lea     rdx, [rbp+57h+TokenInformation+8]
0x180052135  lea     rcx, [rbp+57h+var_B8]
0x180052139  movups  [rbp+57h+var_A8], xmm1
0x18005213d  mov     [rsp+120h+var_F8], rcx
0x180052142  lea     rcx, aWindowsNtNetwo; "Windows NT Network Provider"
0x180052149  movups  xmm0, xmmword ptr [rbx+20h]
0x18005214d  mov     [rsp+120h+ReturnLength], r8
0x180052152  movups  [rbp+57h+var_98], xmm0
0x180052156  movsd   xmm1, qword ptr [rbx+30h]
0x18005215b  movsd   [rbp+57h+var_88], xmm1
0x180052160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052165  test    eax, eax
0x180052167  jnz     short loc_180052178
0x180052169  mov     rcx, [rbp+57h+hMem]; hMem
0x18005216d  test    rcx, rcx
0x180052170  jz      short loc_180052178
0x180052172  call    cs:__imp_LocalFree
0x180052178  mov     ecx, r13d
0x18005217b  mov     rax, rbx
0x18005217e  mov     [rax], dil
0x180052181  inc     rax
0x180052184  sub     rcx, 1
0x180052188  jnz     short loc_18005217E
0x18005218a  mov     rcx, gs:60h
0x180052193  mov     r8, rbx; P
0x180052196  xor     edx, edx; Flags
0x180052198  mov     rcx, [rcx+30h]; HeapHandle
0x18005219c  call    cs:__imp_RtlFreeHeap
0x1800521a2  mov     rcx, [rbp+57h+var_48]
0x1800521a6  xor     rcx, rsp; StackCookie
0x1800521a9  call    __security_check_cookie
0x1800521ae  add     rsp, 0E8h
0x1800521b5  pop     r15
0x1800521b7  pop     r14
0x1800521b9  pop     r13
0x1800521bb  pop     r12
0x1800521bd  pop     rdi
0x1800521be  pop     rsi
0x1800521bf  pop     rbx
0x1800521c0  pop     rbp
0x1800521c1  retn
```
