# mkl_serv_get_ncorespercpu

- ea: `0x18000d570`
- end: `0x18000d9c0`
- name: `mkl_serv_get_ncorespercpu`
- size: `1104`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180042130`

## callees

- `0x18000c300`
- `0x18000ca80`
- `0x18000d570`
- `0x18003cec0`
- `0x18003eb20`
- `0x180054070`
- `0x180054080`
- `0x1832ce3b0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d836`
- `KERNEL32!GetProcAddress` at `0x18000d84e`
- `KERNEL32!GetProcAddress` at `0x18000d836`
- `KERNEL32!GetProcAddress` at `0x18000d84e`
- `KERNEL32!VerifyVersionInfoA` at `0x18000d687`
- `KERNEL32!VerifyVersionInfoA` at `0x18000d749`
- `KERNEL32!VerifyVersionInfoA` at `0x18000d7f8`
- `KERNEL32!VerifyVersionInfoA` at `0x18000d687`
- `KERNEL32!VerifyVersionInfoA` at `0x18000d749`
- `KERNEL32!VerifyVersionInfoA` at `0x18000d7f8`
- `KERNEL32!VerSetConditionMask` at `0x18000d671`
- `KERNEL32!VerSetConditionMask` at `0x18000d733`
- `KERNEL32!VerSetConditionMask` at `0x18000d7e5`
- `KERNEL32!VerSetConditionMask` at `0x18000d671`
- `KERNEL32!VerSetConditionMask` at `0x18000d733`
- `KERNEL32!VerSetConditionMask` at `0x18000d7e5`
- `KERNEL32!GetLastError` at `0x18000d90a`
- `KERNEL32!GetLastError` at `0x18000d90a`
- `KERNEL32!LoadLibraryA` at `0x18000d81e`
- `KERNEL32!LoadLibraryA` at `0x18000d81e`

## string_xrefs

- `0x18000d805`: `kernel32.dll`

## pseudocode

```c
__int64 mkl_serv_get_ncorespercpu()
{
  int v0; // r15d
  unsigned __int64 v1; // rdi
  ULONGLONG v2; // rax
  unsigned __int64 v3; // rdi
  ULONGLONG v4; // rax
  __int64 v5; // rdi
  ULONGLONG v6; // rax
  int v7; // r14d
  int v8; // r13d
  HMODULE LibraryA; // rax
  HMODULE v10; // rdi
  FARPROC ProcAddress; // rsi
  FARPROC v12; // r12
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rdi
  _DWORD *v16; // rsi
  unsigned __int64 v17; // rax
  int v18; // eax
  _OWORD v19[3]; // [rsp+0h] [rbp-258h]
  unsigned int v20; // [rsp+30h] [rbp-228h] BYREF
  _BYTE v21[12]; // [rsp+34h] [rbp-224h] BYREF
  struct _OSVERSIONINFOEXA v22; // [rsp+40h] [rbp-218h] BYREF
  struct _OSVERSIONINFOEXA v23; // [rsp+E0h] [rbp-178h] BYREF
  _OSVERSIONINFOEXA VersionInformation; // [rsp+180h] [rbp-D8h] BYREF

  if ( dword_1836D0DB4 )
  {
    mkl_serv_lock(&unk_1836E89AC);
    if ( dword_1836D0DB4 )
    {
      sub_18000C300();
      v0 = 1;
      v1 = 128;
      *(_QWORD *)v21 = 0x100000001LL;
      *(_DWORD *)&v21[8] = 1;
      memset(&VersionInformation.szCSDVersion[108], 0, 28);
      do
      {
        *(_OWORD *)&v23.szCSDVersion[v1 + 124] = xmmword_1833ECDF0[v1 / 0x10];
        *(_OWORD *)&v23.szCSDVersion[v1 + 108] = *(_OWORD *)&aMklVerboseSS[v1 + 4];
        *(_OWORD *)&v23.szCSDVersion[v1 + 92] = *(_OWORD *)&aPardisoD[v1];
        *(_OWORD *)&v23.szCSDVersion[v1 + 76] = *(_OWORD *)&aFftD[v1];
        v1 -= 64LL;
      }
      while ( v1 );
      VersionInformation.dwMajorVersion = 7;
      v2 = VerSetConditionMask(0, 2u, 3u);
      if ( VerifyVersionInfoA(&VersionInformation, 2u, v2) )
        goto LABEL_12;
      v3 = 128;
      memset(&v23.szCSDVersion[108], 0, 28);
      do
      {
        *(_OWORD *)&v22.szCSDVersion[v3 + 124] = xmmword_1833ECDF0[v3 / 0x10];
        *(_OWORD *)&v22.szCSDVersion[v3 + 108] = *(_OWORD *)&aMklVerboseSS[v3 + 4];
        *(_OWORD *)&v22.szCSDVersion[v3 + 92] = *(_OWORD *)&aPardisoD[v3];
        *(_OWORD *)&v22.szCSDVersion[v3 + 76] = *(_OWORD *)&aFftD[v3];
        v3 -= 64LL;
      }
      while ( v3 );
      v23.dwMajorVersion = 6;
      v4 = VerSetConditionMask(0, 2u, 3u);
      if ( !VerifyVersionInfoA(&v23, 2u, v4) )
        goto LABEL_17;
      v5 = 8;
      memset(&v22.szCSDVersion[108], 0, 28);
      do
      {
        *(_OWORD *)&v21[v5 * 16 - 4] = xmmword_1833ECDF0[v5];
        v19[v5 + 2] = *(_OWORD *)&aMklVerboseSS[v5 * 16 + 4];
        v19[v5 + 1] = *(_OWORD *)&aPardisoD[v5 * 16];
        v19[v5] = *(_OWORD *)&aFftD[v5 * 16];
        v5 -= 4;
      }
      while ( v5 * 16 );
      v22.dwMinorVersion = 1;
      v6 = VerSetConditionMask(0, 1u, 3u);
      if ( VerifyVersionInfoA(&v22, 1u, v6) )
      {
LABEL_12:
        v7 = 0;
        v8 = 0;
        *(_QWORD *)&v21[4] = 0x100000001LL;
        *(_DWORD *)v21 = 1;
        LibraryA = LoadLibraryA("kernel32.dll");
        v10 = LibraryA;
        if ( LibraryA )
        {
          ProcAddress = GetProcAddress(LibraryA, "GetLogicalProcessorInformationEx");
          if ( ProcAddress )
          {
            v12 = GetProcAddress(v10, "GetActiveProcessorCount");
            if ( v12 )
            {
              v20 = 0;
              if ( !((unsigned int (__fastcall *)(__int64, _QWORD, unsigned int *))ProcAddress)(0xFFFF, 0, &v20)
                && GetLastError() == 122 )
              {
                v14 = mkl_serv_malloc(v20, 0);
                v15 = v14;
                if ( v14 )
                {
                  if ( ((unsigned int (__fastcall *)(__int64, unsigned __int64, unsigned int *))ProcAddress)(
                         0xFFFF,
                         v14,
                         &v20) )
                  {
                    v16 = (_DWORD *)v15;
                    v17 = v15 + v20;
                    if ( v15 >= v17 )
                    {
LABEL_31:
                      v18 = ((__int64 (__fastcall *)(__int64))v12)(0xFFFF);
                      *(_DWORD *)&v21[4] = v8;
                      if ( v7 )
                        v0 = v7;
                      *(_DWORD *)v21 = v0;
                      *(_DWORD *)&v21[8] = v18;
                    }
                    else
                    {
                      while ( v16 )
                      {
                        if ( *v16 )
                        {
                          if ( *v16 == 1 )
                            ++v7;
                        }
                        else
                        {
                          ++v8;
                        }
                        v16 = (_DWORD *)((char *)v16 + (unsigned int)v16[1]);
                        if ( (unsigned __int64)v16 >= v17 )
                          goto LABEL_31;
                      }
                    }
                  }
                  mkl_serv_free(v15);
                }
              }
            }
          }
        }
      }
      else
      {
LABEL_17:
        sub_18000CA80((int *)v21, &v21[4], (unsigned int *)&v21[8]);
      }
      dword_1836D0DB8 = *(_DWORD *)&v21[8];
      dword_1836D0DBC = *(_DWORD *)&v21[4];
      dword_1836D0DC0 = *(_DWORD *)v21;
      dword_1836D0DC4 = *(_DWORD *)&v21[4] / *(_DWORD *)v21;
      dword_1836D0DC8 = *(_DWORD *)&v21[4] != *(_DWORD *)&v21[8];
      dword_1836D0DB4 = 0;
    }
    mkl_serv_unlock(&unk_1836E89AC);
  }
  return (unsigned int)dword_1836D0DC4;
}

```

## disassembly

```asm
0x18000d570  push    rsi
0x18000d571  push    rdi
0x18000d572  push    r12
0x18000d574  push    r13
0x18000d576  push    r14
0x18000d578  push    r15
0x18000d57a  sub     rsp, 218h
0x18000d581  mov     rax, cs:__security_cookie
0x18000d588  xor     rax, rsp
0x18000d58b  mov     [rsp+248h+var_38], rax
0x18000d593  cmp     cs:dword_1836D0DB4, 0
0x18000d59a  jz      loc_18000D8E0
0x18000d5a0  lea     rcx, unk_1836E89AC
0x18000d5a7  call    mkl_serv_lock
0x18000d5ac  cmp     cs:dword_1836D0DB4, 0
0x18000d5b3  jz      loc_18000D8D4
0x18000d5b9  call    sub_18000C300
0x18000d5be  mov     r15d, 1
0x18000d5c4  mov     edi, 80h
0x18000d5c9  mov     dword ptr [rsp+248h+var_228+4], r15d
0x18000d5ce  mov     dword ptr [rsp+248h+var_228+8], r15d
0x18000d5d3  mov     dword ptr [rsp+248h+var_228+0Ch], r15d
0x18000d5d8  movaps  xmm0, cs:xmmword_1833ECE80
0x18000d5df  movaps  xmmword ptr [rsp+248h+VersionInformation.szCSDVersion+6Ch], xmm0
0x18000d5e7  mov     rax, cs:qword_1833ECE90
0x18000d5ee  mov     qword ptr [rsp+248h+VersionInformation.szCSDVersion+7Ch], rax
0x18000d5f6  mov     edx, cs:dword_1833ECE98
0x18000d5fc  mov     dword ptr [rsp+248h+VersionInformation.wSuiteMask], edx
0x18000d603  lea     rax, cs:180000000h
0x18000d60a  mov     rdx, rax
0x18000d60d  mov     rcx, rax
0x18000d610  mov     rsi, rax
0x18000d613  movaps  xmm0, ds:rva xmmword_1833ECDF0[rax+rdi]
0x18000d61b  movaps  xmmword ptr [rsp+rdi+248h+var_178.szCSDVersion+7Ch], xmm0
0x18000d623  movaps  xmm1, xmmword ptr [rdx+rdi+33ECDE0h]
0x18000d62b  movaps  xmmword ptr [rsp+rdi+248h+var_178.szCSDVersion+6Ch], xmm1
0x18000d633  movaps  xmm2, xmmword ptr [rcx+rdi+33ECDD0h]
0x18000d63b  movaps  xmmword ptr [rsp+rdi+248h+var_178.szCSDVersion+5Ch], xmm2
0x18000d643  movaps  xmm3, xmmword ptr [rsi+rdi+33ECDC0h]
0x18000d64b  movaps  xmmword ptr [rsp+rdi+248h+var_178.szCSDVersion+4Ch], xmm3
0x18000d653  sub     rdi, 40h ; '@'
0x18000d657  jnz     short loc_18000D603
0x18000d659  xor     ecx, ecx; ConditionMask
0x18000d65b  mov     edx, 2; TypeMask
0x18000d660  mov     r8d, 3; Condition
0x18000d666  mov     [rsp+248h+VersionInformation.dwMajorVersion], 7
0x18000d671  call    cs:__imp_VerSetConditionMask
0x18000d677  mov     edx, 2; dwTypeMask
0x18000d67c  lea     rcx, [rsp+248h+VersionInformation]; lpVersionInformation
0x18000d684  mov     r8, rax; dwlConditionMask
0x18000d687  call    cs:__imp_VerifyVersionInfoA
0x18000d68d  test    eax, eax
0x18000d68f  jnz     loc_18000D802
0x18000d695  movaps  xmm0, cs:xmmword_1833ECE80
0x18000d69c  mov     edi, 80h
0x18000d6a1  movaps  xmmword ptr [rsp+248h+var_178.szCSDVersion+6Ch], xmm0
0x18000d6a9  mov     rax, cs:qword_1833ECE90
0x18000d6b0  mov     qword ptr [rsp+248h+var_178.szCSDVersion+7Ch], rax
0x18000d6b8  mov     edx, cs:dword_1833ECE98
0x18000d6be  mov     dword ptr [rsp+248h+var_178.wSuiteMask], edx
0x18000d6c5  lea     rax, cs:180000000h
0x18000d6cc  mov     rdx, rax
0x18000d6cf  mov     rcx, rax
0x18000d6d2  mov     rsi, rax
0x18000d6d5  movaps  xmm0, ds:rva xmmword_1833ECDF0[rax+rdi]
0x18000d6dd  movaps  xmmword ptr [rsp+rdi+248h+var_218.szCSDVersion+7Ch], xmm0
0x18000d6e5  movaps  xmm1, xmmword ptr [rdx+rdi+33ECDE0h]
0x18000d6ed  movaps  xmmword ptr [rsp+rdi+248h+var_218.szCSDVersion+6Ch], xmm1
0x18000d6f5  movaps  xmm2, xmmword ptr [rcx+rdi+33ECDD0h]
0x18000d6fd  movaps  xmmword ptr [rsp+rdi+248h+var_218.szCSDVersion+5Ch], xmm2
0x18000d705  movaps  xmm3, xmmword ptr [rsi+rdi+33ECDC0h]
0x18000d70d  movaps  xmmword ptr [rsp+rdi+248h+var_218.szCSDVersion+4Ch], xmm3
0x18000d715  sub     rdi, 40h ; '@'
0x18000d719  jnz     short loc_18000D6C5
0x18000d71b  xor     ecx, ecx; ConditionMask
0x18000d71d  mov     edx, 2; TypeMask
0x18000d722  mov     r8d, 3; Condition
0x18000d728  mov     [rsp+248h+var_178.dwMajorVersion], 6
0x18000d733  call    cs:__imp_VerSetConditionMask
0x18000d739  mov     edx, 2; dwTypeMask
0x18000d73e  lea     rcx, [rsp+248h+var_178]; lpVersionInformation
0x18000d746  mov     r8, rax; dwlConditionMask
0x18000d749  call    cs:__imp_VerifyVersionInfoA
0x18000d74f  test    eax, eax
0x18000d751  jz      loc_18000D87B
0x18000d757  movaps  xmm0, cs:xmmword_1833ECE80
0x18000d75e  mov     edi, 80h
0x18000d763  movaps  xmmword ptr [rsp+248h+var_218.szCSDVersion+6Ch], xmm0
0x18000d76b  mov     rax, cs:qword_1833ECE90
0x18000d772  mov     qword ptr [rsp+248h+var_218.szCSDVersion+7Ch], rax
0x18000d77a  mov     edx, cs:dword_1833ECE98
0x18000d780  mov     dword ptr [rsp+248h+var_218.wSuiteMask], edx
0x18000d787  lea     rax, cs:180000000h
0x18000d78e  mov     rdx, rax
0x18000d791  mov     rcx, rax
0x18000d794  mov     rsi, rax
0x18000d797  movaps  xmm0, ds:rva xmmword_1833ECDF0[rax+rdi]
0x18000d79f  movaps  [rsp+rdi+248h+var_228], xmm0
0x18000d7a4  movaps  xmm1, xmmword ptr [rdx+rdi+33ECDE0h]
0x18000d7ac  movaps  [rsp+rdi+248h+var_238], xmm1
0x18000d7b1  movaps  xmm2, xmmword ptr [rcx+rdi+33ECDD0h]
0x18000d7b9  movaps  [rsp+rdi+248h+var_248], xmm2
0x18000d7bd  movaps  xmm3, xmmword ptr [rsi+rdi+33ECDC0h]
0x18000d7c5  movaps  [rsp+rdi+248h+var_258], xmm3
0x18000d7ca  sub     rdi, 40h ; '@'
0x18000d7ce  jnz     short loc_18000D787
0x18000d7d0  xor     ecx, ecx; ConditionMask
0x18000d7d2  mov     edx, 1; TypeMask
0x18000d7d7  mov     r8d, 3; Condition
0x18000d7dd  mov     [rsp+248h+var_218.dwMinorVersion], 1
0x18000d7e5  call    cs:__imp_VerSetConditionMask
0x18000d7eb  mov     edx, 1; dwTypeMask
0x18000d7f0  lea     rcx, [rsp+248h+var_218]; lpVersionInformation
0x18000d7f5  mov     r8, rax; dwlConditionMask
0x18000d7f8  call    cs:__imp_VerifyVersionInfoA
0x18000d7fe  test    eax, eax
0x18000d800  jz      short loc_18000D87B
0x18000d802  xor     r14d, r14d
0x18000d805  lea     rcx, LibFileName; "kernel32.dll"
0x18000d80c  mov     dword ptr [rsp+248h+var_228+0Ch], r15d
0x18000d811  xor     r13d, r13d
0x18000d814  mov     dword ptr [rsp+248h+var_228+8], r15d
0x18000d819  mov     dword ptr [rsp+248h+var_228+4], r15d
0x18000d81e  call    cs:__imp_LoadLibraryA
0x18000d824  mov     rdi, rax
0x18000d827  test    rdi, rdi
0x18000d82a  jz      short loc_18000D88F
0x18000d82c  mov     rcx, rdi; hModule
0x18000d82f  lea     rdx, ProcName; "GetLogicalProcessorInformationEx"
0x18000d836  call    cs:__imp_GetProcAddress
0x18000d83c  mov     rsi, rax
0x18000d83f  test    rsi, rsi
0x18000d842  jz      short loc_18000D88F
0x18000d844  mov     rcx, rdi; hModule
0x18000d847  lea     rdx, aGetactiveproce; "GetActiveProcessorCount"
0x18000d84e  call    cs:__imp_GetProcAddress
0x18000d854  mov     r12, rax
0x18000d857  test    r12, r12
0x18000d85a  jz      short loc_18000D88F
0x18000d85c  mov     ecx, 0FFFFh
0x18000d861  xor     edx, edx
0x18000d863  mov     dword ptr [rsp+248h+var_228], 0
0x18000d86b  lea     r8, [rsp+248h+var_228]
0x18000d870  call    rsi
0x18000d872  test    eax, eax
0x18000d874  jnz     short loc_18000D88F
0x18000d876  jmp     loc_18000D90A
0x18000d87b  lea     rcx, [rsp+248h+var_228+4]
0x18000d880  lea     rdx, [rsp+248h+var_228+8]
0x18000d885  lea     r8, [rsp+248h+var_228+0Ch]
0x18000d88a  call    sub_18000CA80
0x18000d88f  mov     esi, dword ptr [rsp+248h+var_228+8]
0x18000d893  mov     eax, esi
0x18000d895  cdq
0x18000d896  mov     ecx, dword ptr [rsp+248h+var_228+4]
0x18000d89a  idiv    ecx
0x18000d89c  mov     edi, dword ptr [rsp+248h+var_228+0Ch]
0x18000d8a0  cmp     esi, edi
0x18000d8a2  mov     cs:dword_1836D0DB8, edi
0x18000d8a8  mov     cs:dword_1836D0DBC, esi
0x18000d8ae  mov     cs:dword_1836D0DC0, ecx
0x18000d8b4  mov     cs:dword_1836D0DC4, eax
0x18000d8ba  jnz     loc_18000D9A6
0x18000d8c0  mov     cs:dword_1836D0DC8, 0
0x18000d8ca  mov     cs:dword_1836D0DB4, 0
0x18000d8d4  lea     rcx, unk_1836E89AC
0x18000d8db  call    mkl_serv_unlock
0x18000d8e0  mov     rcx, [rsp+248h+var_38]
0x18000d8e8  xor     rcx, rsp; StackCookie
0x18000d8eb  mov     esi, cs:dword_1836D0DC4
0x18000d8f1  call    __security_check_cookie
0x18000d8f6  mov     eax, esi
0x18000d8f8  add     rsp, 218h
0x18000d8ff  pop     r15
0x18000d901  pop     r14
0x18000d903  pop     r13
0x18000d905  pop     r12
0x18000d907  pop     rdi
0x18000d908  pop     rsi
0x18000d909  retn
0x18000d90a  call    cs:__imp_GetLastError
0x18000d910  cmp     eax, 7Ah ; 'z'
0x18000d913  jnz     loc_18000D88F
0x18000d919  xor     edx, edx
0x18000d91b  mov     ecx, dword ptr [rsp+248h+var_228]
0x18000d91f  call    mkl_serv_malloc
0x18000d924  mov     rdi, rax
0x18000d927  test    rdi, rdi
0x18000d92a  jz      loc_18000D88F
0x18000d930  mov     ecx, 0FFFFh
0x18000d935  mov     rdx, rdi
0x18000d938  lea     r8, [rsp+248h+var_228]
0x18000d93d  call    rsi
0x18000d93f  test    eax, eax
0x18000d941  jz      short loc_18000D999
0x18000d943  mov     eax, dword ptr [rsp+248h+var_228]
0x18000d947  mov     rsi, rdi
0x18000d94a  add     rax, rdi
0x18000d94d  cmp     rdi, rax
0x18000d950  jnb     short loc_18000D97C
0x18000d952  test    rsi, rsi
0x18000d955  jz      short loc_18000D999
0x18000d957  mov     r8d, [rsi]
0x18000d95a  test    r8d, r8d
0x18000d95d  jnz     short loc_18000D964
0x18000d95f  inc     r13d
0x18000d962  jmp     short loc_18000D970
0x18000d964  cmp     r8d, 1
0x18000d968  lea     r9d, [r14+1]
0x18000d96c  cmovz   r14d, r9d
0x18000d970  mov     r8d, [rsi+4]
0x18000d974  add     rsi, r8
0x18000d977  cmp     rsi, rax
0x18000d97a  jb      short loc_18000D952
0x18000d97c  mov     ecx, 0FFFFh
0x18000d981  call    r12
0x18000d984  test    r14d, r14d
0x18000d987  mov     dword ptr [rsp+248h+var_228+8], r13d
0x18000d98c  cmovnz  r15d, r14d
0x18000d990  mov     dword ptr [rsp+248h+var_228+4], r15d
0x18000d995  mov     dword ptr [rsp+248h+var_228+0Ch], eax
0x18000d999  mov     rcx, rdi
0x18000d99c  call    mkl_serv_free
0x18000d9a1  jmp     loc_18000D88F
0x18000d9a6  mov     cs:dword_1836D0DC8, 1
0x18000d9b0  jmp     loc_18000D8CA
```
