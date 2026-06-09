# SpSignIsFileHashInCatalog

- ea: `0x14002eaa0`
- end: `0x14002ed79`
- name: `SpSignIsFileHashInCatalog`
- size: `729`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140014e08`

## callees

- `0x14000f96c`
- `0x14002eaa0`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002ebfb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002ebfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002ec41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002ed20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002ed37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002ec41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002ed20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002ed37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eb72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ec29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002eb72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ec29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002ed4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002ed4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002ed46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002ed46`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002eb64`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14002eb64`
- `WINTRUST!CryptCATOpen` at `0x14002eb9a`
- `WINTRUST!CryptCATOpen` at `0x14002eb9a`
- `WINTRUST!CryptCATClose` at `0x14002ed09`
- `WINTRUST!CryptCATClose` at `0x14002ed09`
- `WINTRUST!CryptCATAdminAcquireContext2` at `0x14002ebdd`
- `WINTRUST!CryptCATAdminAcquireContext2` at `0x14002ebdd`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x14002ec1f`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x14002ec1f`
- `WINTRUST!CryptCATStoreFromHandle` at `0x14002ebaf`
- `WINTRUST!CryptCATStoreFromHandle` at `0x14002ebaf`
- `WINTRUST!CryptCATGetMemberInfo` at `0x14002eccb`
- `WINTRUST!CryptCATGetMemberInfo` at `0x14002eccb`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x14002ecfa`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x14002ecfa`

## pseudocode

```c
_BOOL8 __fastcall SpSignIsFileHashInCatalog(const WCHAR *a1, WCHAR *a2, void *a3)
{
  unsigned __int8 *v3; // rdi
  WCHAR *v5; // rsi
  __int64 v7; // r15
  __int64 FileW; // r14
  unsigned int LastError; // ebx
  HANDLE v10; // rax
  CRYPTCATSTORE *v11; // rax
  const wchar_t *v12; // r8
  unsigned int v13; // eax
  unsigned __int8 *v14; // rax
  unsigned int v15; // ebx
  WCHAR *v16; // rax
  __int64 j; // r10
  __int64 v18; // r9
  unsigned __int8 v19; // r8
  unsigned int i; // [rsp+40h] [rbp-29h] BYREF
  _DWORD v22[8]; // [rsp+48h] [rbp-21h]
  HCATADMIN hCatAdmin; // [rsp+68h] [rbp-1h] BYREF
  _DWORD v24[4]; // [rsp+70h] [rbp+7h] BYREF

  v3 = 0;
  hCatAdmin = 0;
  v24[0] = -145692989;
  v24[1] = 298924270;
  v5 = 0;
  v24[2] = -1073683067;
  v24[3] = -292175281;
  v22[0] = 3211312;
  v7 = -1;
  v22[1] = 3342386;
  v22[2] = 3473460;
  v22[3] = 3604534;
  v22[4] = 3735608;
  v22[5] = 4325441;
  v22[6] = 4456515;
  v22[7] = 4587589;
  i = 0;
  if ( a1 && a2 )
  {
    FileW = (__int64)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
    if ( FileW == -1 )
    {
LABEL_4:
      LastError = GetLastError();
      goto LABEL_25;
    }
    if ( (((unsigned __int64)a3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v10 = CryptCATOpen(a2, 0, 0, 0, 0);
      v7 = (__int64)v10;
      if ( v10 == (HANDLE)-1LL )
        goto LABEL_4;
      a3 = v10;
    }
    v11 = CryptCATStoreFromHandle(a3);
    v12 = L"SHA256";
    if ( v11->dwPublicVersion != 512 )
      v12 = L"SHA1";
    if ( !(unsigned int)CryptCATAdminAcquireContext2(&hCatAdmin, v24, v12, 0, 0) )
      goto LABEL_4;
    LastError = 0;
    v13 = 100;
    for ( i = 100; ; v13 = i )
    {
      v14 = (unsigned __int8 *)HeapAlloc(hHeap, 0, v13);
      v3 = v14;
      if ( !v14 )
      {
        LastError = 8;
        goto LABEL_25;
      }
      if ( !(unsigned int)CryptCATAdminCalcHashFromFileHandle2(hCatAdmin, FileW, &i, v14, 0) )
        LastError = GetLastError();
      if ( !LastError )
        break;
      HeapFree(hHeap, 0, v3);
      v3 = 0;
      if ( LastError != 122 )
        goto LABEL_25;
    }
    v15 = 2 * i + 1;
    v16 = (WCHAR *)SpUtilsMallocElements(v15);
    v5 = v16;
    if ( v16 )
    {
      memset_0(v16, 0, 2LL * v15);
      for ( j = 0; (unsigned int)j < i; v5[(unsigned int)(v18 + 1)] = *((_WORD *)v22 + (v19 & 0xF)) )
      {
        v18 = (unsigned int)(2 * j);
        v5[v18] = *((_WORD *)v22 + ((unsigned __int64)v3[j] >> 4));
        v19 = v3[j];
        j = (unsigned int)(j + 1);
      }
      LastError = CryptCATGetMemberInfo(a3, v5) == 0 ? 0xE000024B : 0;
    }
    else
    {
      LastError = 122;
    }
  }
  else
  {
    FileW = -1;
    LastError = 87;
  }
LABEL_25:
  if ( hCatAdmin )
    CryptCATAdminReleaseContext(hCatAdmin, 0);
  if ( v7 != -1 )
    CryptCATClose((HANDLE)v7);
  if ( v5 )
    HeapFree(hHeap, 0, v5);
  if ( v3 )
    HeapFree(hHeap, 0, v3);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x14002eaa0  push    rbp
0x14002eaa2  push    rbx
0x14002eaa3  push    rsi
0x14002eaa4  push    rdi
0x14002eaa5  push    r13
0x14002eaa7  push    r14
0x14002eaa9  push    r15
0x14002eaab  lea     rbp, [rsp-27h]
0x14002eab0  sub     rsp, 90h
0x14002eab7  mov     rax, cs:__security_cookie
0x14002eabe  xor     rax, rsp
0x14002eac1  mov     [rbp+57h+var_40], rax
0x14002eac5  xor     edi, edi
0x14002eac7  mov     [rbp+57h+hCatAdmin], 0
0x14002eacf  mov     rbx, rdx
0x14002ead2  mov     [rbp+57h+var_50], 0F750E6C3h
0x14002ead9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14002eadd  mov     [rbp+57h+var_4C], 11D138EEh
0x14002eae4  xor     esi, esi
0x14002eae6  mov     [rbp+57h+var_48], 0C000E585h
0x14002eaed  mov     [rbp+57h+var_44], 0EE95C24Fh
0x14002eaf4  mov     r13, r8
0x14002eaf7  mov     [rbp+57h+var_78], 310030h
0x14002eafe  mov     r15, rdx
0x14002eb01  mov     [rbp+57h+var_74], 330032h
0x14002eb08  mov     [rbp+57h+var_70], 350034h
0x14002eb0f  mov     [rbp+57h+var_6C], 370036h
0x14002eb16  mov     [rbp+57h+var_68], 390038h
0x14002eb1d  mov     [rbp+57h+var_64], 420041h
0x14002eb24  mov     [rbp+57h+var_60], 440043h
0x14002eb2b  mov     [rbp+57h+var_5C], 460045h
0x14002eb32  mov     [rbp+57h+var_80], edi
0x14002eb35  test    rcx, rcx
0x14002eb38  jz      loc_14002ECE7
0x14002eb3e  test    rbx, rbx
0x14002eb41  jz      loc_14002ECE7
0x14002eb47  mov     [rsp+0C0h+hTemplateFile], rsi; hTemplateFile
0x14002eb4c  lea     r8d, [r15+2]; dwShareMode
0x14002eb50  mov     [rsp+0C0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x14002eb54  xor     r9d, r9d; lpSecurityAttributes
0x14002eb57  mov     edx, 80000000h; dwDesiredAccess
0x14002eb5c  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x14002eb64  call    cs:__imp_CreateFileW
0x14002eb6a  mov     r14, rax
0x14002eb6d  cmp     rax, r15
0x14002eb70  jnz     short loc_14002EB7F
0x14002eb72  call    cs:__imp_GetLastError
0x14002eb78  mov     ebx, eax
0x14002eb7a  jmp     loc_14002ECEF
0x14002eb7f  lea     rax, [r13+1]
0x14002eb83  test    rax, 0FFFFFFFFFFFFFFFEh
0x14002eb89  jnz     short loc_14002EBAC
0x14002eb8b  xor     r9d, r9d; dwPublicVersion
0x14002eb8e  mov     [rsp+0C0h+dwCreationDisposition], esi; dwEncodingType
0x14002eb92  xor     r8d, r8d; hProv
0x14002eb95  xor     edx, edx; fdwOpenFlags
0x14002eb97  mov     rcx, rbx; pwszFileName
0x14002eb9a  call    cs:__imp_CryptCATOpen
0x14002eba0  mov     r15, rax
0x14002eba3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002eba7  jz      short loc_14002EB72
0x14002eba9  mov     r13, rax
0x14002ebac  mov     rcx, r13; hCatalog
0x14002ebaf  call    cs:__imp_CryptCATStoreFromHandle
0x14002ebb5  lea     rcx, aSha1; "SHA1"
0x14002ebbc  mov     [rsp+0C0h+dwCreationDisposition], esi
0x14002ebc0  lea     r8, aSha256; "SHA256"
0x14002ebc7  lea     rdx, [rbp+57h+var_50]
0x14002ebcb  cmp     dword ptr [rax+4], 200h
0x14002ebd2  cmovnz  r8, rcx
0x14002ebd6  xor     r9d, r9d
0x14002ebd9  lea     rcx, [rbp+57h+hCatAdmin]
0x14002ebdd  call    cs:__imp_CryptCATAdminAcquireContext2
0x14002ebe3  test    eax, eax
0x14002ebe5  jz      short loc_14002EB72
0x14002ebe7  xor     ebx, ebx
0x14002ebe9  lea     eax, [rbx+64h]
0x14002ebec  mov     [rbp+57h+var_80], eax
0x14002ebef  mov     rcx, cs:hHeap; hHeap
0x14002ebf6  xor     edx, edx; dwFlags
0x14002ebf8  mov     r8d, eax; dwBytes
0x14002ebfb  call    cs:__imp_HeapAlloc
0x14002ec01  mov     rdi, rax
0x14002ec04  test    rax, rax
0x14002ec07  jz      loc_14002ECE0
0x14002ec0d  mov     rcx, [rbp+57h+hCatAdmin]
0x14002ec11  lea     r8, [rbp+57h+var_80]
0x14002ec15  mov     r9, rax
0x14002ec18  mov     [rsp+0C0h+dwCreationDisposition], esi
0x14002ec1c  mov     rdx, r14
0x14002ec1f  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle2
0x14002ec25  test    eax, eax
0x14002ec27  jnz     short loc_14002EC31
0x14002ec29  call    cs:__imp_GetLastError
0x14002ec2f  mov     ebx, eax
0x14002ec31  test    ebx, ebx
0x14002ec33  jz      short loc_14002EC57
0x14002ec35  mov     rcx, cs:hHeap; hHeap
0x14002ec3c  mov     r8, rdi; lpMem
0x14002ec3f  xor     edx, edx; dwFlags
0x14002ec41  call    cs:__imp_HeapFree
0x14002ec47  xor     edi, edi
0x14002ec49  cmp     ebx, 7Ah ; 'z'
0x14002ec4c  jnz     loc_14002ECEF
0x14002ec52  mov     eax, [rbp+57h+var_80]
0x14002ec55  jmp     short loc_14002EBEF
0x14002ec57  mov     eax, [rbp+57h+var_80]
0x14002ec5a  lea     ebx, ds:1[rax*2]
0x14002ec61  mov     ecx, ebx
0x14002ec63  call    SpUtilsMallocElements
0x14002ec68  mov     rsi, rax
0x14002ec6b  test    rax, rax
0x14002ec6e  jnz     short loc_14002EC75
0x14002ec70  lea     ebx, [rax+7Ah]
0x14002ec73  jmp     short loc_14002ECEF
0x14002ec75  mov     r8d, ebx
0x14002ec78  xor     edx, edx; Val
0x14002ec7a  add     r8, r8; Size
0x14002ec7d  mov     rcx, rsi; void *
0x14002ec80  call    memset_0
0x14002ec85  xor     r10d, r10d
0x14002ec88  cmp     [rbp+57h+var_80], r10d
0x14002ec8c  jbe     short loc_14002ECC5
0x14002ec8e  movzx   eax, byte ptr [r10+rdi]
0x14002ec93  lea     r9d, [r10+r10]
0x14002ec97  shr     rax, 4
0x14002ec9b  lea     edx, [r9+1]
0x14002ec9f  movzx   eax, word ptr [rbp+rax*2+57h+var_78]
0x14002eca4  mov     [rsi+r9*2], ax
0x14002eca9  movzx   r8d, byte ptr [r10+rdi]
0x14002ecae  inc     r10d
0x14002ecb1  and     r8d, 0Fh
0x14002ecb5  movzx   eax, word ptr [rbp+r8*2+57h+var_78]
0x14002ecbb  mov     [rsi+rdx*2], ax
0x14002ecbf  cmp     r10d, [rbp+57h+var_80]
0x14002ecc3  jb      short loc_14002EC8E
0x14002ecc5  mov     rdx, rsi; pwszReferenceTag
0x14002ecc8  mov     rcx, r13; hCatalog
0x14002eccb  call    cs:__imp_CryptCATGetMemberInfo
0x14002ecd1  neg     rax
0x14002ecd4  sbb     ebx, ebx
0x14002ecd6  not     ebx
0x14002ecd8  and     ebx, 0E000024Bh
0x14002ecde  jmp     short loc_14002ECEF
0x14002ece0  mov     ebx, 8
0x14002ece5  jmp     short loc_14002ECEF
0x14002ece7  mov     r14, rdx
0x14002ecea  mov     ebx, 57h ; 'W'
0x14002ecef  mov     rcx, [rbp+57h+hCatAdmin]; hCatAdmin
0x14002ecf3  test    rcx, rcx
0x14002ecf6  jz      short loc_14002ED00
0x14002ecf8  xor     edx, edx; dwFlags
0x14002ecfa  call    cs:__imp_CryptCATAdminReleaseContext
0x14002ed00  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x14002ed04  jz      short loc_14002ED0F
0x14002ed06  mov     rcx, r15; hCatalog
0x14002ed09  call    cs:__imp_CryptCATClose
0x14002ed0f  test    rsi, rsi
0x14002ed12  jz      short loc_14002ED26
0x14002ed14  mov     rcx, cs:hHeap; hHeap
0x14002ed1b  mov     r8, rsi; lpMem
0x14002ed1e  xor     edx, edx; dwFlags
0x14002ed20  call    cs:__imp_HeapFree
0x14002ed26  test    rdi, rdi
0x14002ed29  jz      short loc_14002ED3D
0x14002ed2b  mov     rcx, cs:hHeap; hHeap
0x14002ed32  mov     r8, rdi; lpMem
0x14002ed35  xor     edx, edx; dwFlags
0x14002ed37  call    cs:__imp_HeapFree
0x14002ed3d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14002ed41  jz      short loc_14002ED4C
0x14002ed43  mov     rcx, r14; hObject
0x14002ed46  call    cs:__imp_CloseHandle
0x14002ed4c  mov     ecx, ebx; dwErrCode
0x14002ed4e  call    cs:__imp_SetLastError
0x14002ed54  xor     eax, eax
0x14002ed56  test    ebx, ebx
0x14002ed58  setz    al
0x14002ed5b  mov     rcx, [rbp+57h+var_40]
0x14002ed5f  xor     rcx, rsp; StackCookie
0x14002ed62  call    __security_check_cookie
0x14002ed67  add     rsp, 90h
0x14002ed6e  pop     r15
0x14002ed70  pop     r14
0x14002ed72  pop     r13
0x14002ed74  pop     rdi
0x14002ed75  pop     rsi
0x14002ed76  pop     rbx
0x14002ed77  pop     rbp
0x14002ed78  retn
```
