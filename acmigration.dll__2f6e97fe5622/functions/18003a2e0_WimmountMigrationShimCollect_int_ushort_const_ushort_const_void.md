# WimmountMigrationShimCollect(int *,ushort const *,ushort const *,void *)

- ea: `0x18003a2e0`
- end: `0x18003a4ed`
- name: `?WimmountMigrationShimCollect@@YAJPEAHPEBG1PEAX@Z`
- size: `525`
- prototype: `__int64 __fastcall(int *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x180001cf0`
- `0x18003a248`
- `0x18003a2e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18003a3db`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18003a3db`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003a40d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003a40d`
- `KERNEL32!GetFileAttributesW` at `0x18003a421`
- `KERNEL32!GetFileAttributesW` at `0x18003a458`
- `KERNEL32!GetFileAttributesW` at `0x18003a421`
- `KERNEL32!GetFileAttributesW` at `0x18003a458`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003a440`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003a440`
- `ADVAPI32!RegQueryValueExW` at `0x18003a38f`
- `ADVAPI32!RegQueryValueExW` at `0x18003a38f`
- `ADVAPI32!RegCloseKey` at `0x18003a4ac`
- `ADVAPI32!RegCloseKey` at `0x18003a4ac`
- `ADVAPI32!RegSetValueExW` at `0x18003a497`
- `ADVAPI32!RegSetValueExW` at `0x18003a497`
- `ADVAPI32!RegOpenKeyExW` at `0x18003a351`
- `ADVAPI32!RegOpenKeyExW` at `0x18003a351`

## string_xrefs

- `0x18003a388`: `ImagePath`
- `0x18003a483`: `ImagePath`
- `0x18003a401`: `\WIMMOUNT.SYS`

## pseudocode

```c
__int64 __fastcall WimmountMigrationShimCollect(
        int *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4)
{
  __int64 v5; // rdi
  unsigned int v6; // esi
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-C0h] BYREF

  v5 = -1;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Type = 0;
  cbData = 0;
  WimmountLogMsg(0, "*Collect*");
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Bu, &hKey) )
  {
    cbData = 518;
    if ( !RegQueryValueExW(hKey, L"ImagePath", 0, &Type, (LPBYTE)Data, &cbData) && cbData < 0x208 && Type - 1 <= 1 )
    {
      v6 = 0;
      v7 = -1;
      do
        ++v7;
      while ( Data[v7] );
      if ( v7 )
      {
        do
        {
          Data[v6] = towupper(Data[v6]);
          ++v6;
          v8 = -1;
          do
            ++v8;
          while ( Data[v8] );
        }
        while ( v6 < v8 );
      }
      if ( wcsstr(Data, L"\\WIMMOUNT.SYS") && GetFileAttributesW(Data) == -1 )
      {
        if ( ExpandEnvironmentStringsW(lpSrc, Data, 0x104u) - 1 > 0x102 )
        {
          WimmountLogMsg(0x6Fu, "ExpandEnvironmentStrings Failed");
          goto LABEL_19;
        }
        if ( GetFileAttributesW(Data) != -1 )
        {
          do
            ++v5;
          while ( *(_WORD *)&lpData[2 * v5] );
          RegSetValueExW(hKey, L"ImagePath", 0, Type, lpData, 2 * v5 + 2);
        }
      }
    }
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
LABEL_19:
  *a1 = 1;
  return 0;
}

```

## disassembly

```asm
0x18003a2e0  push    rbp
0x18003a2e2  push    rbx
0x18003a2e3  push    rsi
0x18003a2e4  push    rdi
0x18003a2e5  push    r14
0x18003a2e7  push    r15
0x18003a2e9  lea     rbp, [rsp-168h]
0x18003a2f1  sub     rsp, 268h
0x18003a2f8  mov     rax, cs:__security_cookie
0x18003a2ff  xor     rax, rsp
0x18003a302  mov     [rbp+190h+var_40], rax
0x18003a309  mov     r14, rcx
0x18003a30c  lea     rdx, aCollect_1; "*Collect*"
0x18003a313  xor     r15d, r15d
0x18003a316  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003a31a  xor     ecx, ecx; unsigned int
0x18003a31c  mov     [rsp+290h+hKey], rdi
0x18003a321  mov     [rsp+290h+Type], r15d
0x18003a326  mov     [rsp+290h+cbData], r15d
0x18003a32b  call    ?WimmountLogMsg@@YAXKPEAD@Z; WimmountLogMsg(ulong,char *)
0x18003a330  mov     rdx, cs:lpSubKey; lpSubKey
0x18003a337  lea     rax, [rsp+290h+hKey]
0x18003a33c  mov     r9d, 2001Bh; samDesired
0x18003a342  mov     [rsp+290h+phkResult], rax; phkResult
0x18003a347  xor     r8d, r8d; ulOptions
0x18003a34a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a351  call    cs:__imp_RegOpenKeyExW
0x18003a357  test    eax, eax
0x18003a359  jnz     loc_18003A49D
0x18003a35f  mov     rcx, [rsp+290h+hKey]; hKey
0x18003a364  lea     rax, [rsp+290h+cbData]
0x18003a369  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18003a36e  lea     r9, [rsp+290h+Type]; lpType
0x18003a373  lea     rax, [rsp+290h+Data]
0x18003a378  mov     [rsp+290h+cbData], 206h
0x18003a380  xor     r8d, r8d; lpReserved
0x18003a383  mov     [rsp+290h+phkResult], rax; lpData
0x18003a388  lea     rdx, aImagepath; "ImagePath"
0x18003a38f  call    cs:__imp_RegQueryValueExW
0x18003a395  test    eax, eax
0x18003a397  jnz     loc_18003A49D
0x18003a39d  cmp     [rsp+290h+cbData], 208h
0x18003a3a5  jnb     loc_18003A49D
0x18003a3ab  mov     eax, [rsp+290h+Type]
0x18003a3af  dec     eax
0x18003a3b1  cmp     eax, 1
0x18003a3b4  ja      loc_18003A49D
0x18003a3ba  mov     esi, r15d
0x18003a3bd  lea     rcx, [rsp+290h+Data]
0x18003a3c2  mov     rax, rdi
0x18003a3c5  inc     rax
0x18003a3c8  cmp     [rcx+rax*2], r15w
0x18003a3cd  jnz     short loc_18003A3C5
0x18003a3cf  test    rax, rax
0x18003a3d2  jz      short loc_18003A401
0x18003a3d4  mov     ebx, esi
0x18003a3d6  movzx   ecx, [rsp+rbx*2+290h+Data]; C
0x18003a3db  call    cs:__imp_towupper
0x18003a3e1  mov     [rsp+rbx*2+290h+Data], ax
0x18003a3e6  inc     esi
0x18003a3e8  lea     rax, [rsp+290h+Data]
0x18003a3ed  mov     rcx, rdi
0x18003a3f0  inc     rcx
0x18003a3f3  cmp     [rax+rcx*2], r15w
0x18003a3f8  jnz     short loc_18003A3F0
0x18003a3fa  mov     eax, esi
0x18003a3fc  cmp     rax, rcx
0x18003a3ff  jb      short loc_18003A3D4
0x18003a401  lea     rdx, aWimmountSys; "\\WIMMOUNT.SYS"
0x18003a408  lea     rcx, [rsp+290h+Data]; Str
0x18003a40d  call    cs:__imp_wcsstr
0x18003a413  test    rax, rax
0x18003a416  jz      loc_18003A49D
0x18003a41c  lea     rcx, [rsp+290h+Data]; lpFileName
0x18003a421  call    cs:__imp_GetFileAttributesW
0x18003a427  or      ebx, 0FFFFFFFFh
0x18003a42a  cmp     eax, ebx
0x18003a42c  jnz     short loc_18003A49D
0x18003a42e  mov     rcx, cs:lpSrc; lpSrc
0x18003a435  lea     rdx, [rsp+290h+Data]; lpDst
0x18003a43a  mov     r8d, 104h; nSize
0x18003a440  call    cs:__imp_ExpandEnvironmentStringsW
0x18003a446  dec     eax
0x18003a448  cmp     eax, 102h
0x18003a44d  ja      loc_18003A4DA
0x18003a453  lea     rcx, [rsp+290h+Data]; lpFileName
0x18003a458  call    cs:__imp_GetFileAttributesW
0x18003a45e  cmp     eax, ebx
0x18003a460  jz      short loc_18003A49D
0x18003a462  mov     rcx, cs:lpData
0x18003a469  inc     rdi
0x18003a46c  cmp     [rcx+rdi*2], r15w
0x18003a471  jnz     short loc_18003A469
0x18003a473  mov     r9d, [rsp+290h+Type]; dwType
0x18003a478  lea     eax, ds:2[rdi*2]
0x18003a47f  mov     dword ptr [rsp+290h+lpcbData], eax; cbData
0x18003a483  lea     rdx, aImagepath; "ImagePath"
0x18003a48a  mov     [rsp+290h+phkResult], rcx; lpData
0x18003a48f  xor     r8d, r8d; Reserved
0x18003a492  mov     rcx, [rsp+290h+hKey]; hKey
0x18003a497  call    cs:__imp_RegSetValueExW
0x18003a49d  mov     rcx, [rsp+290h+hKey]; hKey
0x18003a4a2  lea     rax, [rcx-1]
0x18003a4a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003a4aa  ja      short loc_18003A4B2
0x18003a4ac  call    cs:__imp_RegCloseKey
0x18003a4b2  mov     dword ptr [r14], 1
0x18003a4b9  xor     eax, eax
0x18003a4bb  mov     rcx, [rbp+190h+var_40]
0x18003a4c2  xor     rcx, rsp; StackCookie
0x18003a4c5  call    __security_check_cookie
0x18003a4ca  add     rsp, 268h
0x18003a4d1  pop     r15
0x18003a4d3  pop     r14
0x18003a4d5  pop     rdi
0x18003a4d6  pop     rsi
0x18003a4d7  pop     rbx
0x18003a4d8  pop     rbp
0x18003a4d9  retn
0x18003a4da  lea     rdx, aExpandenvironm_0; "ExpandEnvironmentStrings Failed"
0x18003a4e1  mov     ecx, 6Fh ; 'o'; unsigned int
0x18003a4e6  call    ?WimmountLogMsg@@YAXKPEAD@Z; WimmountLogMsg(ulong,char *)
0x18003a4eb  jmp     short loc_18003A4B2
```
