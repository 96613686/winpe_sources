# CDiskProtection::VcfWriteTrackedRegKeys(CDiskProtection::SCacheFileData *,unsigned __int64)

- ea: `0x14000e318`
- end: `0x14000e6a7`
- name: `?VcfWriteTrackedRegKeys@CDiskProtection@@IEAAJPEAUSCacheFileData@1@_K@Z`
- size: `911`
- prototype: `__int64 __fastcall(CDiskProtection *__hidden this, struct CDiskProtection::SCacheFileData *, unsigned __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x14000dc30`

## callees

- `0x14000e318`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400689d4`
- `0x14007cb9e`
- `0x14007cbd0`
- `0x14007cc60`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x14000e469`
- `KERNEL32!SetFilePointerEx` at `0x14000e508`
- `KERNEL32!SetFilePointerEx` at `0x14000e5b3`
- `KERNEL32!SetFilePointerEx` at `0x14000e469`
- `KERNEL32!SetFilePointerEx` at `0x14000e508`
- `KERNEL32!SetFilePointerEx` at `0x14000e5b3`
- `KERNEL32!WriteFile` at `0x14000e57b`
- `KERNEL32!WriteFile` at `0x14000e57b`
- `KERNEL32!GetLastError` at `0x14000e477`
- `KERNEL32!GetLastError` at `0x14000e512`
- `KERNEL32!GetLastError` at `0x14000e585`
- `KERNEL32!GetLastError` at `0x14000e5c1`
- `KERNEL32!GetLastError` at `0x14000e477`
- `KERNEL32!GetLastError` at `0x14000e512`
- `KERNEL32!GetLastError` at `0x14000e585`
- `KERNEL32!GetLastError` at `0x14000e5c1`
- `KERNEL32!IsDebuggerPresent` at `0x14000e4d2`
- `KERNEL32!IsDebuggerPresent` at `0x14000e627`
- `KERNEL32!IsDebuggerPresent` at `0x14000e4d2`
- `KERNEL32!IsDebuggerPresent` at `0x14000e627`

## string_xrefs

- `0x14000e37a`: `CDiskProtection::VcfWriteTrackedRegKeys - %d tracked registry keys.\n`
- `0x14000e497`: `CDiskProtection::VcfWriteTrackedRegKeys`
- `0x14000e5fb`: `CDiskProtection::VcfWriteTrackedRegKeys`

## pseudocode

```c
__int64 __fastcall CDiskProtection::VcfWriteTrackedRegKeys(
        CDiskProtection *this,
        struct CDiskProtection::SCacheFileData *a2,
        __int64 a3)
{
  int v5; // r12d
  unsigned __int64 v6; // rcx
  __int64 v7; // rsi
  struct CDiskProtection::STrackedRegKey near **v8; // r15
  signed int v9; // ebx
  const unsigned __int16 *v10; // r13
  unsigned int v11; // r12d
  void *v12; // rcx
  signed int v13; // eax
  unsigned int v14; // r12d
  signed int v15; // eax
  unsigned int v16; // edx
  int *p_Buffer; // r9
  __int64 v18; // rax
  void *v19; // rcx
  signed int v20; // eax
  signed int LastError; // eax
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v26; // [rsp+58h] [rbp-A8h] BYREF
  int Buffer; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[8184]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v29; // [rsp+205Ch] [rbp+1F5Ch]

  NewFilePointer.QuadPart = 0;
  NumberOfBytesWritten = 0;
  v5 = 8188;
  memset_0(v28, 0, 0x1FFCu);
  DEBUGMSG(L"CDiskProtection::VcfWriteTrackedRegKeys - %d tracked registry keys.\n", 26);
  v6 = 8188;
  Buffer = 26;
  v23 = 8188;
  v26 = v28;
  v7 = 0;
  while ( 1 )
  {
    v8 = &CDiskProtection::s_rgszTrackedRegKey + 2 * v7;
    if ( (unsigned __int64)*(unsigned __int16 *)v8 + 2 > v6 )
    {
      v10 = L"s_rgszTrackedRegKey[idx].cbName + sizeof (s_rgszTrackedRegKey[idx].cbName) <= cbRemaining";
      v11 = 3253;
LABEL_33:
      v9 = -2147024774;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v11,
        L"CDiskProtection::VcfWriteTrackedRegKeys",
        L"CBRAEx",
        v10,
        -2147024774);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          v11,
          L"CDiskProtection::VcfWriteTrackedRegKeys",
          L"CBRAEx",
          v10,
          -2147024774);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          v11,
          L"CDiskProtection::VcfWriteTrackedRegKeys",
          L"CBRAEx",
          v10,
          -2147024774);
      return (unsigned int)v9;
    }
    v9 = Serialize(&v26, &v23, v8, 2u);
    if ( v9 < 0 )
      return (unsigned int)v9;
    v9 = Serialize(&v26, &v23, (&off_1400EE0E8)[2 * v7], *(unsigned __int16 *)v8);
    if ( v9 < 0 )
      return (unsigned int)v9;
    if ( (unsigned __int64)++v7 >= 0x1A )
      break;
    v6 = v23;
  }
  if ( v23 < 4 )
  {
    v10 = L"cbRemaining >= sizeof (*pCheckSum)";
    v11 = 3274;
    goto LABEL_33;
  }
  v12 = *(void **)a2;
  *((_DWORD *)a2 + 50) = 0x2000 - v23;
  *((_QWORD *)a2 + 24) = a3 + 56;
  if ( SetFilePointerEx(v12, 0, &NewFilePointer, 1u) )
  {
    if ( SetFilePointerEx(*(HANDLE *)a2, (LARGE_INTEGER)(56LL * *((unsigned int *)a2 + 12)), 0, 0) )
    {
      v16 = -559038737;
      p_Buffer = &Buffer;
      do
      {
        v18 = (unsigned __int8)(v16 ^ *(_BYTE *)p_Buffer);
        p_Buffer = (int *)((char *)p_Buffer + 1);
        v16 = dword_1400D78D0[v18] ^ (v16 >> 8);
        --v5;
      }
      while ( v5 );
      v19 = *(void **)a2;
      v29 = v16;
      if ( WriteFile(v19, &Buffer, 0x2000u, &NumberOfBytesWritten, 0) )
      {
        if ( SetFilePointerEx(*(HANDLE *)a2, NewFilePointer, 0, 0) )
          return (unsigned int)v9;
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        v14 = 3326;
      }
      else
      {
        v20 = GetLastError();
        v9 = v20;
        if ( v20 > 0 )
          v9 = (unsigned __int16)v20 | 0x80070000;
        v14 = 3319;
      }
    }
    else
    {
      v15 = GetLastError();
      v9 = v15;
      if ( v15 > 0 )
        v9 = (unsigned __int16)v15 | 0x80070000;
      v14 = 3305;
    }
  }
  else
  {
    v13 = GetLastError();
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    v14 = 3296;
  }
  if ( v9 >= 0 )
    v9 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
    v14,
    L"CDiskProtection::VcfWriteTrackedRegKeys",
    L"CBRAEx",
    L"fSuccess",
    v9);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v14,
      L"CDiskProtection::VcfWriteTrackedRegKeys",
      L"CBRAEx",
      L"fSuccess",
      v9);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v14,
      L"CDiskProtection::VcfWriteTrackedRegKeys",
      L"CBRAEx",
      L"fSuccess",
      v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000e318  push    rbp
0x14000e31a  push    rbx
0x14000e31b  push    rsi
0x14000e31c  push    rdi
0x14000e31d  push    r12
0x14000e31f  push    r13
0x14000e321  push    r14
0x14000e323  push    r15
0x14000e325  lea     rbp, [rsp-1F78h]
0x14000e32d  mov     eax, 2078h
0x14000e332  call    _alloca_probe
0x14000e337  sub     rsp, rax
0x14000e33a  mov     rax, cs:__security_cookie
0x14000e341  xor     rax, rsp
0x14000e344  mov     [rbp+1FB0h+var_50], rax
0x14000e34b  xor     ebx, ebx
0x14000e34d  lea     rcx, [rsp+20B0h+var_204C]; void *
0x14000e352  mov     r13, r8
0x14000e355  mov     qword ptr [rsp+20B0h+NewFilePointer], rbx
0x14000e35a  mov     rdi, rdx
0x14000e35d  mov     [rsp+20B0h+NumberOfBytesWritten], ebx
0x14000e361  mov     r12d, 1FFCh
0x14000e367  mov     [rsp+20B0h+Buffer], ebx
0x14000e36b  mov     r8d, r12d; Size
0x14000e36e  xor     edx, edx; Val
0x14000e370  call    memset_0
0x14000e375  lea     esi, [rbx+1Ah]
0x14000e378  mov     edx, esi
0x14000e37a  lea     rcx, aCdiskprotectio_132; "CDiskProtection::VcfWriteTrackedRegKeys"...
0x14000e381  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000e386  mov     ecx, r12d
0x14000e389  mov     [rsp+20B0h+Buffer], esi
0x14000e38d  lea     rax, [rsp+20B0h+var_204C]
0x14000e392  mov     [rsp+20B0h+var_2070], rcx
0x14000e397  mov     [rsp+20B0h+var_2058], rax
0x14000e39c  lea     r15, __ImageBase
0x14000e3a3  mov     esi, ebx
0x14000e3a5  mov     r14, rsi
0x14000e3a8  lea     r15, rva ?s_rgszTrackedRegKey@CDiskProtection@@1PAUSTrackedRegKey@1@A[r15]; CDiskProtection::STrackedRegKey near * CDiskProtection::s_rgszTrackedRegKey ...
0x14000e3af  shl     r14, 4
0x14000e3b3  add     r15, r14
0x14000e3b6  movzx   eax, word ptr [r15]
0x14000e3ba  add     rax, 2
0x14000e3be  cmp     rax, rcx
0x14000e3c1  ja      loc_14000E5E1
0x14000e3c7  mov     r9d, 2; unsigned __int64
0x14000e3cd  lea     rdx, [rsp+20B0h+var_2070]; unsigned __int64 *
0x14000e3d2  mov     r8, r15; void *
0x14000e3d5  lea     rcx, [rsp+20B0h+var_2058]; unsigned __int8 **
0x14000e3da  call    ?Serialize@@YAJPEAPEAEPEA_KPEBX_K@Z; Serialize(uchar * *,unsigned __int64 *,void const *,unsigned __int64)
0x14000e3df  mov     ebx, eax
0x14000e3e1  test    eax, eax
0x14000e3e3  js      loc_14000E682
0x14000e3e9  movzx   r9d, word ptr [r15]; unsigned __int64
0x14000e3ed  lea     rdx, [rsp+20B0h+var_2070]; unsigned __int64 *
0x14000e3f2  lea     r15, __ImageBase
0x14000e3f9  mov     r8, [r14+r15+0EE0E8h]; void *
0x14000e401  lea     rcx, [rsp+20B0h+var_2058]; unsigned __int8 **
0x14000e406  call    ?Serialize@@YAJPEAPEAEPEA_KPEBX_K@Z; Serialize(uchar * *,unsigned __int64 *,void const *,unsigned __int64)
0x14000e40b  mov     ebx, eax
0x14000e40d  test    eax, eax
0x14000e40f  js      loc_14000E682
0x14000e415  inc     rsi
0x14000e418  cmp     rsi, 1Ah
0x14000e41c  jnb     short loc_14000E425
0x14000e41e  mov     rcx, [rsp+20B0h+var_2070]
0x14000e423  jmp     short loc_14000E3A5
0x14000e425  cmp     [rsp+20B0h+var_2070], 4
0x14000e42b  jnb     short loc_14000E43F
0x14000e42d  lea     r13, aCbremainingSiz; "cbRemaining >= sizeof (*pCheckSum)"
0x14000e434  mov     r12d, 0CCAh
0x14000e43a  jmp     loc_14000E5EE
0x14000e43f  mov     rcx, [rdi]; hFile
0x14000e442  lea     r8, [rsp+20B0h+NewFilePointer]; lpNewFilePointer
0x14000e447  xor     edx, edx; liDistanceToMove
0x14000e449  mov     esi, 2000h
0x14000e44e  mov     eax, esi
0x14000e450  sub     eax, dword ptr [rsp+20B0h+var_2070]
0x14000e454  mov     [rdi+0C8h], eax
0x14000e45a  lea     rax, [r13+38h]
0x14000e45e  lea     r9d, [rdx+1]; dwMoveMethod
0x14000e462  mov     [rdi+0C0h], rax
0x14000e469  call    cs:__imp_SetFilePointerEx
0x14000e46f  test    eax, eax
0x14000e471  jnz     loc_14000E4F8
0x14000e477  call    cs:__imp_GetLastError
0x14000e47d  mov     ebx, eax
0x14000e47f  test    eax, eax
0x14000e481  jle     short loc_14000E48C
0x14000e483  movzx   ebx, ax
0x14000e486  or      ebx, 80070000h
0x14000e48c  mov     r12d, 0CE0h
0x14000e492  mov     eax, 80004005h
0x14000e497  lea     rsi, aCdiskprotectio_48; "CDiskProtection::VcfWriteTrackedRegKeys"
0x14000e49e  test    ebx, ebx
0x14000e4a0  lea     r14, aCbraex; "CBRAEx"
0x14000e4a7  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000e4ae  mov     r8, rsi; unsigned __int16 *
0x14000e4b1  cmovns  ebx, eax
0x14000e4b4  lea     r15, aFsuccess; "fSuccess"
0x14000e4bb  mov     [rsp+20B0h+var_2088], ebx; int
0x14000e4bf  mov     r9, r14; unsigned __int16 *
0x14000e4c2  mov     edx, r12d; unsigned int
0x14000e4c5  mov     [rsp+20B0h+lpOverlapped], r15; unsigned __int16 *
0x14000e4ca  mov     rcx, rdi; unsigned __int16 *
0x14000e4cd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000e4d2  call    cs:__imp_IsDebuggerPresent
0x14000e4d8  test    eax, eax
0x14000e4da  jz      short loc_14000E4EA
0x14000e4dc  mov     [rsp+20B0h+var_2078], ebx
0x14000e4e0  mov     [rsp+20B0h+var_2080], r15
0x14000e4e5  jmp     loc_14000E63B
0x14000e4ea  mov     dword ptr [rsp+20B0h+var_2080], ebx
0x14000e4ee  mov     qword ptr [rsp+20B0h+var_2088], r15
0x14000e4f3  jmp     loc_14000E668
0x14000e4f8  mov     eax, [rdi+30h]
0x14000e4fb  xor     r9d, r9d; dwMoveMethod
0x14000e4fe  mov     rcx, [rdi]; hFile
0x14000e501  xor     r8d, r8d; lpNewFilePointer
0x14000e504  imul    rdx, rax, 38h ; '8'; liDistanceToMove
0x14000e508  call    cs:__imp_SetFilePointerEx
0x14000e50e  test    eax, eax
0x14000e510  jnz     short loc_14000E532
0x14000e512  call    cs:__imp_GetLastError
0x14000e518  mov     ebx, eax
0x14000e51a  test    eax, eax
0x14000e51c  jle     short loc_14000E527
0x14000e51e  movzx   ebx, ax
0x14000e521  or      ebx, 80070000h
0x14000e527  mov     r12d, 0CE9h
0x14000e52d  jmp     loc_14000E492
0x14000e532  mov     edx, 0DEADBEEFh
0x14000e537  lea     r9, [rsp+20B0h+Buffer]
0x14000e53c  movzx   ecx, byte ptr [r9]
0x14000e540  mov     eax, edx
0x14000e542  xor     rcx, rax
0x14000e545  shr     edx, 8
0x14000e548  movzx   eax, cl
0x14000e54b  inc     r9
0x14000e54e  xor     edx, ds:rva dword_1400D78D0[r15+rax*4]
0x14000e556  add     r12d, 0FFFFFFFFh
0x14000e55a  jnz     short loc_14000E53C
0x14000e55c  mov     rcx, [rdi]; hFile
0x14000e55f  lea     r9, [rsp+20B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000e564  mov     [rbp+1FB0h+var_54], edx
0x14000e56a  mov     r8d, esi; nNumberOfBytesToWrite
0x14000e56d  lea     rdx, [rsp+20B0h+Buffer]; lpBuffer
0x14000e572  mov     [rsp+20B0h+lpOverlapped], 0; lpOverlapped
0x14000e57b  call    cs:__imp_WriteFile
0x14000e581  test    eax, eax
0x14000e583  jnz     short loc_14000E5A5
0x14000e585  call    cs:__imp_GetLastError
0x14000e58b  mov     ebx, eax
0x14000e58d  test    eax, eax
0x14000e58f  jle     short loc_14000E59A
0x14000e591  movzx   ebx, ax
0x14000e594  or      ebx, 80070000h
0x14000e59a  mov     r12d, 0CF7h
0x14000e5a0  jmp     loc_14000E492
0x14000e5a5  mov     rdx, qword ptr [rsp+20B0h+NewFilePointer]; liDistanceToMove
0x14000e5aa  xor     r9d, r9d; dwMoveMethod
0x14000e5ad  mov     rcx, [rdi]; hFile
0x14000e5b0  xor     r8d, r8d; lpNewFilePointer
0x14000e5b3  call    cs:__imp_SetFilePointerEx
0x14000e5b9  test    eax, eax
0x14000e5bb  jnz     loc_14000E682
0x14000e5c1  call    cs:__imp_GetLastError
0x14000e5c7  mov     ebx, eax
0x14000e5c9  test    eax, eax
0x14000e5cb  jle     short loc_14000E5D6
0x14000e5cd  movzx   ebx, ax
0x14000e5d0  or      ebx, 80070000h
0x14000e5d6  mov     r12d, 0CFEh
0x14000e5dc  jmp     loc_14000E492
0x14000e5e1  lea     r13, aSRgsztrackedre; "s_rgszTrackedRegKey[idx].cbName + sizeo"...
0x14000e5e8  mov     r12d, 0CB5h
0x14000e5ee  mov     r15d, 8007007Ah
0x14000e5f4  lea     r14, aCbraex; "CBRAEx"
0x14000e5fb  lea     rsi, aCdiskprotectio_48; "CDiskProtection::VcfWriteTrackedRegKeys"
0x14000e602  mov     [rsp+20B0h+var_2088], r15d; int
0x14000e607  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000e60e  mov     [rsp+20B0h+lpOverlapped], r13; unsigned __int16 *
0x14000e613  mov     r9, r14; unsigned __int16 *
0x14000e616  mov     r8, rsi; unsigned __int16 *
0x14000e619  mov     rcx, rdi; unsigned __int16 *
0x14000e61c  mov     edx, r12d; unsigned int
0x14000e61f  mov     ebx, r15d
0x14000e622  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000e627  call    cs:__imp_IsDebuggerPresent
0x14000e62d  test    eax, eax
0x14000e62f  jz      short loc_14000E65E
0x14000e631  mov     [rsp+20B0h+var_2078], r15d
0x14000e636  mov     [rsp+20B0h+var_2080], r13
0x14000e63b  mov     qword ptr [rsp+20B0h+var_2088], r14
0x14000e640  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000e647  mov     r9d, r12d
0x14000e64a  mov     [rsp+20B0h+lpOverlapped], rsi
0x14000e64f  mov     r8, rdi
0x14000e652  mov     ecx, 2; unsigned __int8
0x14000e657  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000e65c  jmp     short loc_14000E682
0x14000e65e  mov     dword ptr [rsp+20B0h+var_2080], r15d
0x14000e663  mov     qword ptr [rsp+20B0h+var_2088], r13
0x14000e668  mov     r9, rsi
0x14000e66b  mov     [rsp+20B0h+lpOverlapped], r14
0x14000e670  mov     r8d, r12d
0x14000e673  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000e67a  mov     rdx, rdi
0x14000e67d  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000e682  mov     eax, ebx
0x14000e684  mov     rcx, [rbp+1FB0h+var_50]
0x14000e68b  xor     rcx, rsp; StackCookie
0x14000e68e  call    __security_check_cookie
0x14000e693  add     rsp, 2078h
0x14000e69a  pop     r15
0x14000e69c  pop     r14
0x14000e69e  pop     r13
0x14000e6a0  pop     r12
0x14000e6a2  pop     rdi
0x14000e6a3  pop     rsi
0x14000e6a4  pop     rbx
0x14000e6a5  pop     rbp
0x14000e6a6  retn
```
