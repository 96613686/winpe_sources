# GetStoragePath(bool,ShaderCacheDiskMode,ShaderCacheCreateFlags,ushort *,uint,_GUID,ushort const *)

- ea: `0x18003d734`
- end: `0x18003da87`
- name: `?GetStoragePath@@YAJ_NW4ShaderCacheDiskMode@@W4ShaderCacheCreateFlags@@PEAGIU_GUID@@PEBG@Z`
- size: `851`
- prototype: `__int64 __fastcall(char, int, __int16, unsigned __int16 *, __int64, unsigned int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f410`

## callees

- `0x180003210`
- `0x180003350`
- `0x180003710`
- `0x18003d734`
- `0x1800449f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003d7f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003d7f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003d7e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003d7e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003d83b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003d83b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d909`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d909`

## string_xrefs

- `0x18003d79b`: `.dxcache`
- `0x18003d8d9`: `%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX%s.dxcache`
- `0x18003d999`: `%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX%s.dxcache`
- `0x18003da31`: `%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX%s.dxcache`

## pseudocode

```c
__int64 __fastcall GetStoragePath(
        char a1,
        int a2,
        __int16 a3,
        unsigned __int16 *a4,
        __int64 a5,
        unsigned int *a6,
        const unsigned __int16 *a7)
{
  char v8; // bl
  const unsigned __int16 *v10; // r15
  const char *v11; // rax
  HANDLE CurrentProcess; // rax
  unsigned int v13; // ebx
  unsigned int FilenameInAppContainerStorage; // eax
  PDWORD ReturnLength; // [rsp+20h] [rbp-F8h]
  DWORD v16; // [rsp+80h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-90h] BYREF
  PSID TokenInformation[10]; // [rsp+90h] [rbp-88h] BYREF

  v8 = a3;
  if ( a2 != 1 )
    return 2147942487LL;
  v10 = &qword_1800ACF70;
  if ( a7 )
    v10 = a7;
  if ( (a3 & 0x100) != 0 )
  {
    v11 = (const char *)&Src;
    if ( (a3 & 0x80u) == 0 )
      v11 = ".dxcache";
    return StringCchPrintfW(a4, 0x104u, L"%s%S", v10, v11);
  }
  else if ( a1 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      v16 = 76;
      if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, TokenInformation, 0x4Cu, &v16) )
      {
        if ( v8 >= 0 )
        {
          LODWORD(ReturnLength) = *a6;
          FilenameInAppContainerStorage = GetFilenameInAppContainerStorage(
                                            a4,
                                            0x104u,
                                            TokenInformation[0],
                                            L"%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX%s.dxcache",
                                            ReturnLength,
                                            *((unsigned __int16 *)a6 + 2),
                                            *((unsigned __int16 *)a6 + 3),
                                            *((unsigned __int8 *)a6 + 8),
                                            *((unsigned __int8 *)a6 + 9),
                                            *((unsigned __int8 *)a6 + 10),
                                            *((unsigned __int8 *)a6 + 11),
                                            *((unsigned __int8 *)a6 + 12),
                                            *((unsigned __int8 *)a6 + 13),
                                            *((unsigned __int8 *)a6 + 14),
                                            *((unsigned __int8 *)a6 + 15),
                                            v10);
        }
        else
        {
          FilenameInAppContainerStorage = GetFilenameInAppContainerStorage(a4, 0x104u, TokenInformation[0], L"%s", v10);
        }
        v13 = FilenameInAppContainerStorage;
      }
      else
      {
        v13 = -2147467259;
      }
      CloseHandle(TokenHandle);
      return v13;
    }
    else
    {
      return 2147500037LL;
    }
  }
  else if ( (a3 & 0x10) != 0 )
  {
    if ( (a3 & 0x80) != 0 )
      return GetFilenameInAppDataStorageForCurrentApp(a4, 0x104u, L"%s", v10);
    else
      return GetFilenameInAppDataStorageForCurrentApp(
               a4,
               0x104u,
               L"%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX%s.dxcache",
               *a6,
               *((unsigned __int16 *)a6 + 2),
               *((unsigned __int16 *)a6 + 3),
               *((unsigned __int8 *)a6 + 8),
               *((unsigned __int8 *)a6 + 9),
               *((unsigned __int8 *)a6 + 10),
               *((unsigned __int8 *)a6 + 11),
               *((unsigned __int8 *)a6 + 12),
               *((unsigned __int8 *)a6 + 13),
               *((unsigned __int8 *)a6 + 14),
               *((unsigned __int8 *)a6 + 15),
               v10);
  }
  else if ( (a3 & 0x80) != 0 )
  {
    return StringCchPrintfW(a4, 0x104u, L"%s", v10);
  }
  else
  {
    return StringCchPrintfW(
             a4,
             0x104u,
             L"%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX%s.dxcache",
             *a6,
             *((unsigned __int16 *)a6 + 2),
             *((unsigned __int16 *)a6 + 3),
             *((unsigned __int8 *)a6 + 8),
             *((unsigned __int8 *)a6 + 9),
             *((unsigned __int8 *)a6 + 10),
             *((unsigned __int8 *)a6 + 11),
             *((unsigned __int8 *)a6 + 12),
             *((unsigned __int8 *)a6 + 13),
             *((unsigned __int8 *)a6 + 14),
             *((unsigned __int8 *)a6 + 15),
             v10);
  }
}

```

## disassembly

```asm
0x18003d734  mov     [rsp+arg_0], rbx
0x18003d739  mov     [rsp+arg_8], rbp
0x18003d73e  push    rsi
0x18003d73f  push    rdi
0x18003d740  push    r12
0x18003d742  push    r14
0x18003d744  push    r15
0x18003d746  sub     rsp, 0F0h
0x18003d74d  mov     rax, cs:__security_cookie
0x18003d754  xor     rax, rsp
0x18003d757  mov     [rsp+118h+var_38], rax
0x18003d75f  mov     rax, [rsp+118h+arg_30]
0x18003d767  mov     r12, r9
0x18003d76a  mov     r14, [rsp+118h+arg_28]
0x18003d772  mov     ebx, r8d
0x18003d775  cmp     edx, 1
0x18003d778  jz      short loc_18003D784
0x18003d77a  mov     eax, 80070057h
0x18003d77f  jmp     loc_18003DA5B
0x18003d784  test    rax, rax
0x18003d787  lea     r15, qword_1800ACF70
0x18003d78e  cmovnz  r15, rax
0x18003d792  bt      ebx, 8
0x18003d796  jnb     short loc_18003D7CE
0x18003d798  test    bl, 80h
0x18003d79b  lea     rcx, aDxcache; ".dxcache"
0x18003d7a2  lea     rax, Src
0x18003d7a9  mov     r9, r15
0x18003d7ac  cmovz   rax, rcx
0x18003d7b0  lea     r8, aSS_1; "%s%S"
0x18003d7b7  mov     rcx, r12; unsigned __int16 *
0x18003d7ba  mov     [rsp+118h+ReturnLength], rax
0x18003d7bf  mov     edx, 104h; unsigned __int64
0x18003d7c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d7c9  jmp     loc_18003DA5B
0x18003d7ce  test    cl, cl
0x18003d7d0  jz      loc_18003D916
0x18003d7d6  mov     [rsp+118h+TokenHandle], 0
0x18003d7e2  call    cs:__imp_GetCurrentProcess
0x18003d7e8  lea     r8, [rsp+118h+TokenHandle]; TokenHandle
0x18003d7f0  mov     edx, 8; DesiredAccess
0x18003d7f5  mov     rcx, rax; ProcessHandle
0x18003d7f8  call    cs:__imp_OpenProcessToken
0x18003d7fe  test    eax, eax
0x18003d800  jnz     short loc_18003D80C
0x18003d802  mov     eax, 80004005h
0x18003d807  jmp     loc_18003DA5B
0x18003d80c  mov     rcx, [rsp+118h+TokenHandle]; TokenHandle
0x18003d814  lea     rax, [rsp+118h+var_98]
0x18003d81c  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18003d822  mov     [rsp+118h+ReturnLength], rax; ReturnLength
0x18003d827  lea     r8, [rsp+118h+TokenInformation]; TokenInformation
0x18003d82f  mov     [rsp+118h+var_98], r9d
0x18003d837  lea     edx, [r9-2Dh]; TokenInformationClass
0x18003d83b  call    cs:__imp_GetTokenInformation
0x18003d841  test    eax, eax
0x18003d843  jnz     short loc_18003D84F
0x18003d845  mov     ebx, 80004005h
0x18003d84a  jmp     loc_18003D901
0x18003d84f  test    bl, bl
0x18003d851  jns     short loc_18003D879
0x18003d853  mov     r8, [rsp+118h+TokenInformation]; Sid
0x18003d85b  lea     r9, aS_1; "%s"
0x18003d862  mov     edx, 104h; unsigned int
0x18003d867  mov     [rsp+118h+ReturnLength], r15
0x18003d86c  mov     rcx, r12; unsigned __int16 *
0x18003d86f  call    ?GetFilenameInAppContainerStorage@@YAJPEAGIPEAXPEBGZZ; GetFilenameInAppContainerStorage(ushort *,uint,void *,ushort const *,...)
0x18003d874  jmp     loc_18003D8FF
0x18003d879  movzx   eax, byte ptr [r14+0Fh]
0x18003d87e  movzx   edx, byte ptr [r14+0Dh]
0x18003d883  movzx   ecx, byte ptr [r14+0Eh]
0x18003d888  movzx   r8d, byte ptr [r14+0Ch]
0x18003d88d  movzx   r9d, byte ptr [r14+0Bh]
0x18003d892  movzx   r10d, byte ptr [r14+0Ah]
0x18003d897  movzx   r11d, byte ptr [r14+9]
0x18003d89c  movzx   ebx, byte ptr [r14+8]
0x18003d8a1  movzx   edi, word ptr [r14+6]
0x18003d8a6  movzx   esi, word ptr [r14+4]
0x18003d8ab  mov     [rsp+118h+var_A0], r15
0x18003d8b0  mov     dword ptr [rsp+118h+var_A8], eax
0x18003d8b4  mov     eax, [r14]
0x18003d8b7  mov     [rsp+118h+var_B0], ecx
0x18003d8bb  mov     rcx, r12; unsigned __int16 *
0x18003d8be  mov     [rsp+118h+var_B8], edx
0x18003d8c2  mov     edx, 104h; unsigned int
0x18003d8c7  mov     [rsp+118h+var_C0], r8d
0x18003d8cc  mov     r8, [rsp+118h+TokenInformation]; Sid
0x18003d8d4  mov     [rsp+118h+var_C8], r9d
0x18003d8d9  lea     r9, a08lx04hx04hx02; "%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%0"...
0x18003d8e0  mov     [rsp+118h+var_D0], r10d
0x18003d8e5  mov     [rsp+118h+var_D8], r11d
0x18003d8ea  mov     [rsp+118h+var_E0], ebx
0x18003d8ee  mov     [rsp+118h+var_E8], edi
0x18003d8f2  mov     [rsp+118h+var_F0], esi
0x18003d8f6  mov     dword ptr [rsp+118h+ReturnLength], eax
0x18003d8fa  call    ?GetFilenameInAppContainerStorage@@YAJPEAGIPEAXPEBGZZ; GetFilenameInAppContainerStorage(ushort *,uint,void *,ushort const *,...)
0x18003d8ff  mov     ebx, eax
0x18003d901  mov     rcx, [rsp+118h+TokenHandle]; hObject
0x18003d909  call    cs:__imp_CloseHandle
0x18003d90f  mov     eax, ebx
0x18003d911  jmp     loc_18003DA5B
0x18003d916  mov     eax, ebx
0x18003d918  and     eax, 80h
0x18003d91d  test    bl, 10h
0x18003d920  jz      loc_18003D9C4
0x18003d926  test    eax, eax
0x18003d928  jz      short loc_18003D946
0x18003d92a  mov     r9, r15
0x18003d92d  lea     r8, aS_1; "%s"
0x18003d934  mov     edx, 104h; unsigned int
0x18003d939  mov     rcx, r12; unsigned __int16 *
0x18003d93c  call    ?GetFilenameInAppDataStorageForCurrentApp@@YAJPEAGIPEBGZZ; GetFilenameInAppDataStorageForCurrentApp(ushort *,uint,ushort const *,...)
0x18003d941  jmp     loc_18003DA5B
0x18003d946  movzx   edx, byte ptr [r14+0Dh]
0x18003d94b  movzx   eax, byte ptr [r14+0Fh]
0x18003d950  movzx   ecx, byte ptr [r14+0Eh]
0x18003d955  movzx   r8d, byte ptr [r14+0Ch]
0x18003d95a  movzx   r10d, byte ptr [r14+0Bh]
0x18003d95f  movzx   r11d, byte ptr [r14+0Ah]
0x18003d964  movzx   ebx, byte ptr [r14+9]
0x18003d969  movzx   edi, byte ptr [r14+8]
0x18003d96e  movzx   esi, word ptr [r14+6]
0x18003d973  movzx   ebp, word ptr [r14+4]
0x18003d978  mov     r9d, [r14]
0x18003d97b  mov     [rsp+118h+var_A8], r15
0x18003d980  mov     [rsp+118h+var_B0], eax
0x18003d984  mov     [rsp+118h+var_B8], ecx
0x18003d988  mov     rcx, r12; unsigned __int16 *
0x18003d98b  mov     [rsp+118h+var_C0], edx
0x18003d98f  mov     edx, 104h; unsigned int
0x18003d994  mov     [rsp+118h+var_C8], r8d
0x18003d999  lea     r8, a08lx04hx04hx02; "%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%0"...
0x18003d9a0  mov     [rsp+118h+var_D0], r10d
0x18003d9a5  mov     [rsp+118h+var_D8], r11d
0x18003d9aa  mov     [rsp+118h+var_E0], ebx
0x18003d9ae  mov     [rsp+118h+var_E8], edi
0x18003d9b2  mov     [rsp+118h+var_F0], esi
0x18003d9b6  mov     dword ptr [rsp+118h+ReturnLength], ebp
0x18003d9ba  call    ?GetFilenameInAppDataStorageForCurrentApp@@YAJPEAGIPEBGZZ; GetFilenameInAppDataStorageForCurrentApp(ushort *,uint,ushort const *,...)
0x18003d9bf  jmp     loc_18003DA5B
0x18003d9c4  test    eax, eax
0x18003d9c6  jz      short loc_18003D9E1
0x18003d9c8  mov     r9, r15
0x18003d9cb  lea     r8, aS_1; "%s"
0x18003d9d2  mov     edx, 104h; unsigned __int64
0x18003d9d7  mov     rcx, r12; unsigned __int16 *
0x18003d9da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d9df  jmp     short loc_18003DA5B
0x18003d9e1  movzx   r9d, byte ptr [r14+0Bh]
0x18003d9e6  movzx   eax, byte ptr [r14+0Fh]
0x18003d9eb  movzx   ecx, byte ptr [r14+0Eh]
0x18003d9f0  movzx   edx, byte ptr [r14+0Dh]
0x18003d9f5  movzx   r8d, byte ptr [r14+0Ch]
0x18003d9fa  movzx   r10d, byte ptr [r14+0Ah]
0x18003d9ff  movzx   r11d, byte ptr [r14+9]
0x18003da04  movzx   ebx, byte ptr [r14+8]
0x18003da09  movzx   edi, word ptr [r14+6]
0x18003da0e  movzx   esi, word ptr [r14+4]
0x18003da13  mov     [rsp+118h+var_A8], r15
0x18003da18  mov     [rsp+118h+var_B0], eax
0x18003da1c  mov     [rsp+118h+var_B8], ecx
0x18003da20  mov     rcx, r12; unsigned __int16 *
0x18003da23  mov     [rsp+118h+var_C0], edx
0x18003da27  mov     edx, 104h; unsigned __int64
0x18003da2c  mov     [rsp+118h+var_C8], r8d
0x18003da31  lea     r8, a08lx04hx04hx02; "%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%0"...
0x18003da38  mov     [rsp+118h+var_D0], r9d
0x18003da3d  mov     r9d, [r14]
0x18003da40  mov     [rsp+118h+var_D8], r10d
0x18003da45  mov     [rsp+118h+var_E0], r11d
0x18003da4a  mov     [rsp+118h+var_E8], ebx
0x18003da4e  mov     [rsp+118h+var_F0], edi
0x18003da52  mov     dword ptr [rsp+118h+ReturnLength], esi
0x18003da56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003da5b  mov     rcx, [rsp+118h+var_38]
0x18003da63  xor     rcx, rsp; StackCookie
0x18003da66  call    __security_check_cookie
0x18003da6b  lea     r11, [rsp+118h+var_28]
0x18003da73  mov     rbx, [r11+30h]
0x18003da77  mov     rbp, [r11+38h]
0x18003da7b  mov     rsp, r11
0x18003da7e  pop     r15
0x18003da80  pop     r14
0x18003da82  pop     r12
0x18003da84  pop     rdi
0x18003da85  pop     rsi
0x18003da86  retn
```
