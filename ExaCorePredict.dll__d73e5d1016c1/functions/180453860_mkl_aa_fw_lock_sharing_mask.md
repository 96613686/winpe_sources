# mkl_aa_fw_lock_sharing_mask

- ea: `0x180453860`
- end: `0x180453d40`
- name: `mkl_aa_fw_lock_sharing_mask`
- size: `1248`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18012bf20`
- `0x18012d750`

## callees

- `0x180056020`
- `0x1804537f0`
- `0x180453810`
- `0x180453860`
- `0x1832ce3b0`

## import_xrefs

- `KERNEL32!FormatMessageA` at `0x180453b03`
- `KERNEL32!FormatMessageA` at `0x180453c30`
- `KERNEL32!FormatMessageA` at `0x180453ca3`
- `KERNEL32!FormatMessageA` at `0x180453d04`
- `KERNEL32!FormatMessageA` at `0x180453b03`
- `KERNEL32!FormatMessageA` at `0x180453c30`
- `KERNEL32!FormatMessageA` at `0x180453ca3`
- `KERNEL32!FormatMessageA` at `0x180453d04`
- `KERNEL32!CloseHandle` at `0x1804539e1`
- `KERNEL32!CloseHandle` at `0x180453b1b`
- `KERNEL32!CloseHandle` at `0x180453c4d`
- `KERNEL32!CloseHandle` at `0x180453c56`
- `KERNEL32!CloseHandle` at `0x180453cc0`
- `KERNEL32!CloseHandle` at `0x1804539e1`
- `KERNEL32!CloseHandle` at `0x180453b1b`
- `KERNEL32!CloseHandle` at `0x180453c4d`
- `KERNEL32!CloseHandle` at `0x180453c56`
- `KERNEL32!CloseHandle` at `0x180453cc0`
- `KERNEL32!WaitForSingleObject` at `0x1804538c8`
- `KERNEL32!WaitForSingleObject` at `0x1804539d6`
- `KERNEL32!WaitForSingleObject` at `0x1804538c8`
- `KERNEL32!WaitForSingleObject` at `0x1804539d6`
- `KERNEL32!ReleaseMutex` at `0x180453c44`
- `KERNEL32!ReleaseMutex` at `0x180453cb7`
- `KERNEL32!ReleaseMutex` at `0x180453c44`
- `KERNEL32!ReleaseMutex` at `0x180453cb7`
- `KERNEL32!MapViewOfFile` at `0x180453bc8`
- `KERNEL32!MapViewOfFile` at `0x180453bc8`
- `KERNEL32!CreateFileMappingA` at `0x180453b96`
- `KERNEL32!CreateFileMappingA` at `0x180453b96`
- `KERNEL32!CreateMutexA` at `0x180453b37`
- `KERNEL32!CreateMutexA` at `0x180453b37`
- `KERNEL32!OpenProcess` at `0x1804539c8`
- `KERNEL32!OpenProcess` at `0x1804539c8`
- `KERNEL32!GetLastError` at `0x180453ac7`
- `KERNEL32!GetLastError` at `0x180453b5a`
- `KERNEL32!GetLastError` at `0x180453bf4`
- `KERNEL32!GetLastError` at `0x180453c67`
- `KERNEL32!GetLastError` at `0x180453cc8`
- `KERNEL32!GetLastError` at `0x180453ac7`
- `KERNEL32!GetLastError` at `0x180453b5a`
- `KERNEL32!GetLastError` at `0x180453bf4`
- `KERNEL32!GetLastError` at `0x180453c67`
- `KERNEL32!GetLastError` at `0x180453cc8`

## pseudocode

```c
__int64 __fastcall mkl_aa_fw_lock_sharing_mask(_DWORD *a1, int *a2)
{
  __int64 v2; // rsi
  _DWORD *v3; // r12
  __int64 v5; // rdi
  int v6; // edx
  unsigned int v7; // r13d
  __int64 v8; // r14
  __int64 v9; // r15
  __int64 v10; // r13
  bool v11; // cc
  int v12; // ecx
  __int64 v13; // rcx
  int *v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r13
  __int64 v17; // rax
  __int64 v18; // rsi
  char *v19; // r14
  DWORD v20; // ebx
  HANDLE v21; // r12
  DWORD v22; // edi
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // r10
  _DWORD *v26; // r11
  __int64 v27; // r9
  _DWORD *v28; // rdi
  __int64 v29; // rcx
  DWORD v31; // r8d
  void *v32; // rsp
  HANDLE MutexA; // rax
  void *v34; // r14
  HANDLE FileMappingA; // rax
  void *v36; // r13
  LPVOID v37; // rax
  DWORD LastError; // r8d
  void *v39; // rsp
  DWORD v40; // r8d
  void *v41; // rsp
  DWORD v42; // r8d
  void *v43; // rsp
  CHAR v44[256]; // [rsp+0h] [rbp-100h] BYREF
  __int64 v45; // [rsp+100h] [rbp+0h]
  _DWORD *v46; // [rsp+110h] [rbp+10h]
  __int64 v47; // [rsp+118h] [rbp+18h]
  __int64 v48; // [rsp+120h] [rbp+20h]
  char v49[8]; // [rsp+128h] [rbp+28h] BYREF

  v3 = a1;
  if ( !a1 || !a2 )
    return 0xFFFFFFFFLL;
  v5 = (int)mkl_ueaa_get_phy_device_count() - 1LL;
  *a2 = 0;
  dword_183728FE8 = 0;
  if ( !dword_183728FEC )
  {
    MutexA = CreateMutexA(0, 1, "mkl.mic.sharing.mutex");
    v34 = MutexA;
    if ( MutexA )
    {
      hMutex = MutexA;
      dword_183728FE8 = 1;
      if ( GetLastError() != 183 )
        *a2 = 1;
      FileMappingA = CreateFileMappingA((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x2108Cu, "mkl.mic.sharing.memory");
      v36 = FileMappingA;
      if ( FileMappingA )
      {
        qword_183728FF8 = (__int64)FileMappingA;
        v37 = MapViewOfFile(FileMappingA, 0xF001Fu, 0, 0, 0x2108Cu);
        if ( v37 )
        {
          mkl_aa_fw_lock_params = (__int64)v37;
          dword_183728FEC = 1;
          v6 = *a2;
          if ( *a2 )
            goto LABEL_6;
          goto LABEL_4;
        }
        LastError = GetLastError();
        v39 = alloca(256);
        FormatMessageA(0x1000u, 0, LastError, 0x400u, v44, 0x100u, 0);
        ReleaseMutex(v34);
        CloseHandle(v34);
        CloseHandle(v36);
      }
      else
      {
        v40 = GetLastError();
        v41 = alloca(256);
        FormatMessageA(0x1000u, 0, v40, 0x400u, v44, 0x100u, 0);
        ReleaseMutex(v34);
        CloseHandle(v34);
      }
    }
    else
    {
      v42 = GetLastError();
      v43 = alloca(256);
      FormatMessageA(0x1000u, 0, v42, 0x400u, v44, 0x100u, 0);
    }
    return (unsigned int)-1;
  }
LABEL_4:
  if ( WaitForSingleObject(hMutex, 0xFFFFFFFF) == -1 )
  {
    v31 = GetLastError();
    v32 = alloca(256);
    FormatMessageA(0x1000u, 0, v31, 0x400u, v44, 0x100u, 0);
    CloseHandle(hMutex);
    return (unsigned int)-1;
  }
  dword_183728FE8 = 1;
  v6 = *a2;
LABEL_6:
  v7 = 0;
  if ( v6 )
    return v7;
  v8 = mkl_aa_fw_lock_params;
  v9 = 1;
  v10 = 1025;
  v11 = v5 <= 0;
  v12 = *(_DWORD *)(mkl_aa_fw_lock_params + 4);
  *v3 = *(_DWORD *)mkl_aa_fw_lock_params;
  v3[1] = v12;
  if ( v5 > 0 )
  {
    v45 = v2;
    do
    {
      mkl_ueaa_get_phy_device_mask((unsigned int)v9, v49);
      v13 = (__int64)&v3[v10 - 1022];
      v14 = (int *)(v8 + 4100LL * (_DWORD)v9 - 4092);
      v15 = *v14;
      *(_DWORD *)(v13 - 4) = v15;
      mkl_serv_memcpy_s(v13, 4 * v15, v14 + 1, 4 * v15);
      ++v9;
      v10 += 1025;
    }
    while ( v9 <= v5 );
    v2 = v45;
    v11 = v5 <= 0;
  }
  v16 = 1;
  v17 = 4100;
  if ( !v11 )
  {
    v45 = v2;
    do
    {
      v18 = 0;
      if ( *(int *)((char *)v3 + v17 - 4092) > 0 )
      {
        v19 = (char *)v3 + v17;
        v47 = v17;
        v48 = v5;
        v46 = v3;
        do
        {
          v20 = *(_DWORD *)&v19[4 * v18 - 4088];
          if ( v20 )
          {
            v21 = OpenProcess(0x100000u, 0, v20);
            v22 = WaitForSingleObject(v21, 0);
            CloseHandle(v21);
            if ( v22 != 258 )
            {
              v23 = (int)v16;
              v24 = 1025LL * (int)v16;
              if ( v16 <= v48 )
              {
                v25 = v48;
                v26 = v46;
                do
                {
                  v27 = 0;
                  if ( (int)v26[v24 - 1023] > 0 )
                  {
                    v28 = &v26[v24];
                    v29 = (int)v26[v24 - 1023];
                    do
                    {
                      if ( v20 == v28[v27 - 1022] )
                        v28[v27 - 1022] = 0;
                      ++v27;
                    }
                    while ( v27 < v29 );
                  }
                  ++v23;
                  v24 += 1025;
                }
                while ( v23 <= v25 );
              }
            }
          }
          ++v18;
        }
        while ( v18 < *((int *)v19 - 1023) );
        v17 = v47;
        v5 = v48;
        v3 = v46;
      }
      ++v16;
      v17 += 4100;
    }
    while ( v16 <= v5 );
  }
  return 0;
}

```

## disassembly

```asm
0x180453860  push    rbp
0x180453861  push    rdi
0x180453862  push    r12
0x180453864  push    r13
0x180453866  push    r14
0x180453868  push    r15
0x18045386a  sub     rsp, 78h
0x18045386e  lea     rbp, [rsp+40h]
0x180453873  mov     r12, rcx
0x180453876  mov     rax, cs:__security_cookie
0x18045387d  mov     r15, rdx
0x180453880  xor     rax, rbp
0x180453883  mov     [rbp+60h+var_30], rax
0x180453887  test    r12, r12
0x18045388a  jz      loc_180453D1A
0x180453890  test    r15, r15
0x180453893  jz      loc_180453D1A
0x180453899  call    mkl_ueaa_get_phy_device_count
0x18045389e  movsxd  rdi, eax
0x1804538a1  xor     edx, edx
0x1804538a3  dec     rdi
0x1804538a6  mov     [r15], edx
0x1804538a9  mov     cs:dword_183728FE8, edx
0x1804538af  cmp     cs:dword_183728FEC, 0
0x1804538b6  jz      loc_180453B29
0x1804538bc  mov     rcx, cs:hMutex; hHandle
0x1804538c3  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1804538c8  call    cs:__imp_WaitForSingleObject
0x1804538ce  cmp     eax, 0FFFFFFFFh
0x1804538d1  jz      loc_180453AC7
0x1804538d7  mov     cs:dword_183728FE8, 1
0x1804538e1  mov     edx, [r15]
0x1804538e4  xor     eax, eax
0x1804538e6  xor     r13d, r13d
0x1804538e9  test    edx, edx
0x1804538eb  jnz     loc_180453AA9
0x1804538f1  mov     r14, cs:mkl_aa_fw_lock_params
0x1804538f8  mov     r15d, 1
0x1804538fe  mov     r13d, 1004h
0x180453904  test    rdi, rdi
0x180453907  mov     edx, [r14]
0x18045390a  mov     ecx, [r14+4]
0x18045390e  mov     [r12], edx
0x180453912  mov     [r12+4], ecx
0x180453917  jle     short loc_180453971
0x180453919  mov     [rbp+60h+var_60], rsi
0x18045391d  mov     esi, r15d
0x180453920  lea     rdx, [rbp+60h+var_38]
0x180453924  mov     ecx, esi
0x180453926  call    mkl_ueaa_get_phy_device_mask
0x18045392b  mov     eax, esi
0x18045392d  lea     rcx, [r13+r12-0FF8h]
0x180453935  shl     eax, 0Ah
0x180453938  add     eax, esi
0x18045393a  movsxd  rax, eax
0x18045393d  lea     r8, [r14+rax*4-0FFCh]
0x180453945  movsxd  rdx, dword ptr [r8]
0x180453948  add     r8, 4
0x18045394c  mov     [rcx-4], edx
0x18045394f  shl     rdx, 2
0x180453953  mov     r9, rdx
0x180453956  call    mkl_serv_memcpy_s
0x18045395b  inc     r15
0x18045395e  add     r13, 1004h
0x180453965  cmp     r15, rdi
0x180453968  jle     short loc_18045391D
0x18045396a  mov     rsi, [rbp+60h+var_60]
0x18045396e  test    rdi, rdi
0x180453971  mov     r13d, 1
0x180453977  mov     eax, 1004h
0x18045397c  jle     loc_180453A8C
0x180453982  mov     [rbp+60h+var_58], rbx
0x180453986  mov     [rbp+60h+var_60], rsi
0x18045398a  xor     esi, esi
0x18045398c  cmp     dword ptr [rax+r12-0FFCh], 0
0x180453995  jle     loc_180453A72
0x18045399b  movsxd  r15, r13d
0x18045399e  lea     r14, [r12+rax]
0x1804539a2  mov     [rbp+60h+var_48], rax
0x1804539a6  mov     [rbp+60h+var_40], rdi
0x1804539aa  mov     [rbp+60h+var_50], r12
0x1804539ae  mov     ebx, [r14+rsi*4-0FF8h]
0x1804539b6  test    ebx, ebx
0x1804539b8  jz      loc_180453A52
0x1804539be  mov     ecx, 100000h; dwDesiredAccess
0x1804539c3  xor     edx, edx; bInheritHandle
0x1804539c5  mov     r8d, ebx; dwProcessId
0x1804539c8  call    cs:__imp_OpenProcess
0x1804539ce  mov     r12, rax
0x1804539d1  mov     rcx, r12; hHandle
0x1804539d4  xor     edx, edx; dwMilliseconds
0x1804539d6  call    cs:__imp_WaitForSingleObject
0x1804539dc  mov     edi, eax
0x1804539de  mov     rcx, r12; hObject
0x1804539e1  call    cs:__imp_CloseHandle
0x1804539e7  cmp     edi, 102h
0x1804539ed  jz      short loc_180453A52
0x1804539ef  mov     rax, r15
0x1804539f2  mov     rdx, r15
0x1804539f5  shl     rax, 0Ch
0x1804539f9  cmp     r13, [rbp+60h+var_40]
0x1804539fd  lea     rax, [rax+r15*4]
0x180453a01  jg      short loc_180453A52
0x180453a03  mov     r10, [rbp+60h+var_40]
0x180453a07  mov     r11, [rbp+60h+var_50]
0x180453a0b  xor     r9d, r9d
0x180453a0e  cmp     dword ptr [rax+r11-0FFCh], 0
0x180453a17  jle     short loc_180453A42
0x180453a19  lea     rdi, [r11+rax]
0x180453a1d  movsxd  rcx, dword ptr [rdi-0FFCh]
0x180453a24  cmp     ebx, [rdi+r9*4-0FF8h]
0x180453a2c  jnz     short loc_180453A3A
0x180453a2e  mov     dword ptr [rdi+r9*4-0FF8h], 0
0x180453a3a  inc     r9
0x180453a3d  cmp     r9, rcx
0x180453a40  jl      short loc_180453A24
0x180453a42  xchg    ax, ax
0x180453a44  inc     rdx
0x180453a47  add     rax, 1004h
0x180453a4d  cmp     rdx, r10
0x180453a50  jle     short loc_180453A0B
0x180453a52  nop
0x180453a53  inc     rsi
0x180453a56  movsxd  rax, dword ptr [r14-0FFCh]
0x180453a5d  cmp     rsi, rax
0x180453a60  jl      loc_1804539AE
0x180453a66  mov     rax, [rbp+60h+var_48]
0x180453a6a  mov     rdi, [rbp+60h+var_40]
0x180453a6e  mov     r12, [rbp+60h+var_50]
0x180453a72  inc     r13
0x180453a75  add     rax, 1004h
0x180453a7b  cmp     r13, rdi
0x180453a7e  jle     loc_18045398A
0x180453a84  mov     rbx, [rbp+60h+var_58]
0x180453a88  mov     rsi, [rbp+60h+var_60]
0x180453a8c  mov     rcx, [rbp+60h+var_30]
0x180453a90  xor     rcx, rbp; StackCookie
0x180453a93  call    __security_check_cookie
0x180453a98  xor     eax, eax
0x180453a9a  lea     rsp, [rbp+38h]
0x180453a9e  pop     r15
0x180453aa0  pop     r14
0x180453aa2  pop     r13
0x180453aa4  pop     r12
0x180453aa6  pop     rdi
0x180453aa7  pop     rbp
0x180453aa8  retn
0x180453aa9  mov     rcx, [rbp+60h+var_30]
0x180453aad  xor     rcx, rbp; StackCookie
0x180453ab0  call    __security_check_cookie
0x180453ab5  mov     eax, r13d
0x180453ab8  lea     rsp, [rbp+38h]
0x180453abc  pop     r15
0x180453abe  pop     r14
0x180453ac0  pop     r13
0x180453ac2  pop     r12
0x180453ac4  pop     rdi
0x180453ac5  pop     rbp
0x180453ac6  retn
0x180453ac7  call    cs:__imp_GetLastError
0x180453acd  mov     r8d, eax; dwMessageId
0x180453ad0  mov     eax, 100h
0x180453ad5  sub     rsp, rax
0x180453ad8  lea     rax, [rsp+1A0h+var_160]
0x180453add  mov     rdi, rax
0x180453ae0  mov     rax, rsp
0x180453ae3  mov     ecx, 1000h; dwFlags
0x180453ae8  xor     edx, edx; lpSource
0x180453aea  mov     r9d, 400h; dwLanguageId
0x180453af0  mov     [rax+20h], rdi
0x180453af4  mov     dword ptr [rax+28h], 100h
0x180453afb  mov     qword ptr [rax+30h], 0
0x180453b03  call    cs:__imp_FormatMessageA
0x180453b09  mov     rdx, rdi
0x180453b0c  mov     eax, 100h
0x180453b11  add     rsp, rax
0x180453b14  mov     rcx, cs:hMutex; hObject
0x180453b1b  call    cs:__imp_CloseHandle
0x180453b21  mov     r13d, 0FFFFFFFFh
0x180453b27  jmp     short loc_180453AA9
0x180453b29  xor     ecx, ecx; lpMutexAttributes
0x180453b2b  mov     edx, 1; bInitialOwner
0x180453b30  lea     r8, Name; "mkl.mic.sharing.mutex"
0x180453b37  call    cs:__imp_CreateMutexA
0x180453b3d  mov     r14, rax
0x180453b40  test    r14, r14
0x180453b43  jz      loc_180453CC8
0x180453b49  mov     cs:hMutex, r14
0x180453b50  mov     cs:dword_183728FE8, 1
0x180453b5a  call    cs:__imp_GetLastError
0x180453b60  cmp     eax, 0B7h
0x180453b65  jz      short loc_180453B6E
0x180453b67  mov     dword ptr [r15], 1
0x180453b6e  mov     r11, rsp
0x180453b71  mov     rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180453b78  xor     edx, edx; lpFileMappingAttributes
0x180453b7a  mov     r8d, 4; flProtect
0x180453b80  xor     r9d, r9d; dwMaximumSizeHigh
0x180453b83  lea     r10, aMklMicSharingM_0; "mkl.mic.sharing.memory"
0x180453b8a  mov     dword ptr [r11+20h], 2108Ch
0x180453b92  mov     [r11+28h], r10
0x180453b96  call    cs:__imp_CreateFileMappingA
0x180453b9c  mov     r13, rax
0x180453b9f  test    r13, r13
0x180453ba2  jz      loc_180453C67
0x180453ba8  mov     r10, rsp
0x180453bab  xor     r8d, r8d; dwFileOffsetHigh
0x180453bae  mov     rcx, r13; hFileMappingObject
0x180453bb1  mov     edx, 0F001Fh; dwDesiredAccess
0x180453bb6  xor     r9d, r9d; dwFileOffsetLow
0x180453bb9  mov     cs:qword_183728FF8, r13
0x180453bc0  mov     qword ptr [r10+20h], 2108Ch
0x180453bc8  call    cs:__imp_MapViewOfFile
0x180453bce  test    rax, rax
0x180453bd1  jz      short loc_180453BF4
0x180453bd3  mov     cs:mkl_aa_fw_lock_params, rax
0x180453bda  mov     cs:dword_183728FEC, 1
0x180453be4  mov     edx, [r15]
0x180453be7  test    edx, edx
0x180453be9  jz      loc_1804538BC
0x180453bef  jmp     loc_1804538E4
0x180453bf4  call    cs:__imp_GetLastError
0x180453bfa  mov     r8d, eax; dwMessageId
0x180453bfd  mov     eax, 100h
0x180453c02  sub     rsp, rax
0x180453c05  lea     rax, [rsp+1A0h+var_160]
0x180453c0a  mov     rdi, rax
0x180453c0d  mov     rax, rsp
0x180453c10  mov     ecx, 1000h; dwFlags
0x180453c15  xor     edx, edx; lpSource
0x180453c17  mov     r9d, 400h; dwLanguageId
0x180453c1d  mov     [rax+20h], rdi
0x180453c21  mov     dword ptr [rax+28h], 100h
0x180453c28  mov     qword ptr [rax+30h], 0
0x180453c30  call    cs:__imp_FormatMessageA
0x180453c36  mov     rdx, rdi
0x180453c39  mov     eax, 100h
0x180453c3e  add     rsp, rax
0x180453c41  mov     rcx, r14; hMutex
0x180453c44  call    cs:__imp_ReleaseMutex
0x180453c4a  mov     rcx, r14; hObject
0x180453c4d  call    cs:__imp_CloseHandle
0x180453c53  mov     rcx, r13; hObject
0x180453c56  call    cs:__imp_CloseHandle
0x180453c5c  mov     r13d, 0FFFFFFFFh
0x180453c62  jmp     loc_180453AA9
0x180453c67  call    cs:__imp_GetLastError
0x180453c6d  mov     r8d, eax; dwMessageId
0x180453c70  mov     eax, 100h
0x180453c75  sub     rsp, rax
0x180453c78  lea     rax, [rsp+1A0h+var_160]
0x180453c7d  mov     rdi, rax
0x180453c80  mov     rax, rsp
0x180453c83  mov     ecx, 1000h; dwFlags
0x180453c88  xor     edx, edx; lpSource
0x180453c8a  mov     r9d, 400h; dwLanguageId
0x180453c90  mov     [rax+20h], rdi
0x180453c94  mov     dword ptr [rax+28h], 100h
0x180453c9b  mov     qword ptr [rax+30h], 0
0x180453ca3  call    cs:__imp_FormatMessageA
0x180453ca9  mov     rdx, rdi
0x180453cac  mov     eax, 100h
0x180453cb1  add     rsp, rax
0x180453cb4  mov     rcx, r14; hMutex
0x180453cb7  call    cs:__imp_ReleaseMutex
0x180453cbd  mov     rcx, r14; hObject
0x180453cc0  call    cs:__imp_CloseHandle
0x180453cc6  jmp     short loc_180453C5C
0x180453cc8  call    cs:__imp_GetLastError
0x180453cce  mov     r8d, eax; dwMessageId
0x180453cd1  mov     eax, 100h
0x180453cd6  sub     rsp, rax
0x180453cd9  lea     rax, [rsp+1A0h+var_160]
0x180453cde  mov     rdi, rax
0x180453ce1  mov     rax, rsp
0x180453ce4  mov     ecx, 1000h; dwFlags
0x180453ce9  xor     edx, edx; lpSource
0x180453ceb  mov     r9d, 400h; dwLanguageId
0x180453cf1  mov     [rax+20h], rdi
0x180453cf5  mov     dword ptr [rax+28h], 100h
0x180453cfc  mov     qword ptr [rax+30h], 0
0x180453d04  call    cs:__imp_FormatMessageA
0x180453d0a  mov     rdx, rdi
0x180453d0d  mov     eax, 100h
0x180453d12  add     rsp, rax
0x180453d15  jmp     loc_180453C5C
0x180453d1a  mov     rcx, [rbp+60h+var_30]
0x180453d1e  xor     rcx, rbp; StackCookie
0x180453d21  call    __security_check_cookie
0x180453d26  mov     eax, 0FFFFFFFFh
0x180453d2b  lea     rsp, [rbp+38h]
0x180453d2f  pop     r15
0x180453d31  pop     r14
0x180453d33  pop     r13
0x180453d35  pop     r12
0x180453d37  pop     rdi
0x180453d38  pop     rbp
0x180453d39  retn
```
