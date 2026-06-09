# CProfilesHandler::_GetSoftwareInstallationDirectory(ushort const *,ushort * *)

- ea: `0x18001a468`
- end: `0x18001a551`
- name: `?_GetSoftwareInstallationDirectory@CProfilesHandler@@AEAAJPEBGPEAPEAG@Z`
- size: `233`
- prototype: `__int64 __fastcall(CProfilesHandler *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001a140`

## callees

- `0x18000cc10`
- `0x180013368`
- `0x18001a468`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a4ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a53b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a53b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4c3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a499`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a4e5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a499`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001a4e5`

## string_xrefs

- `0x18001a48d`: `%systemroot%\system32\appmgmt`
- `0x18001a4db`: `%systemroot%\system32\appmgmt`

## pseudocode

```c
__int64 __fastcall CProfilesHandler::_GetSoftwareInstallationDirectory(
        CProfilesHandler *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  DWORD v6; // ecx
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned __int16 *v9; // rax
  signed int v10; // ebx
  signed int LastError; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = ExpandEnvironmentStringsW(L"%systemroot%\\system32\\appmgmt", 0, 0);
  if ( !v6 )
    goto LABEL_9;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = (unsigned int)v7 + v6 + 2;
  v9 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v8);
  *a3 = v9;
  if ( !v9 )
  {
    v10 = -2147024882;
    goto LABEL_15;
  }
  if ( ExpandEnvironmentStringsW(L"%systemroot%\\system32\\appmgmt", v9, v8) )
  {
    if ( !CheckSlashEx(*a3, v8, 0) )
    {
      v10 = -2147024774;
      goto LABEL_15;
    }
    v10 = StringCchCatW(*a3, (unsigned int)v8, a2);
  }
  else
  {
LABEL_9:
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v10 < 0 )
  {
LABEL_15:
    if ( *a3 )
    {
      LocalFree(*a3);
      *a3 = 0;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001a468  push    rbx
0x18001a46a  push    rbp
0x18001a46b  push    rsi
0x18001a46c  push    rdi
0x18001a46d  push    r14
0x18001a46f  sub     rsp, 20h
0x18001a473  xor     ebp, ebp
0x18001a475  mov     rdi, r8
0x18001a478  mov     rsi, rdx
0x18001a47b  test    r8, r8
0x18001a47e  jnz     short loc_18001A48A
0x18001a480  mov     eax, 80004003h
0x18001a485  jmp     loc_18001A546
0x18001a48a  mov     [r8], rbp
0x18001a48d  lea     rcx, Src; "%systemroot%\\system32\\appmgmt"
0x18001a494  xor     r8d, r8d; nSize
0x18001a497  xor     edx, edx; lpDst
0x18001a499  call    cs:__imp_ExpandEnvironmentStringsW
0x18001a49f  mov     ecx, eax
0x18001a4a1  test    eax, eax
0x18001a4a3  jz      short loc_18001A4EF
0x18001a4a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a4a9  inc     rax
0x18001a4ac  cmp     [rsi+rax*2], bp
0x18001a4b0  jnz     short loc_18001A4A9
0x18001a4b2  lea     ebx, [rcx+2]
0x18001a4b5  mov     ecx, 40h ; '@'; uFlags
0x18001a4ba  add     ebx, eax
0x18001a4bc  mov     r14d, ebx
0x18001a4bf  lea     rdx, [rbx+rbx]; uBytes
0x18001a4c3  call    cs:__imp_LocalAlloc
0x18001a4c9  mov     [rdi], rax
0x18001a4cc  test    rax, rax
0x18001a4cf  jnz     short loc_18001A4D8
0x18001a4d1  mov     ebx, 8007000Eh
0x18001a4d6  jmp     short loc_18001A533
0x18001a4d8  mov     r8d, ebx; nSize
0x18001a4db  lea     rcx, Src; "%systemroot%\\system32\\appmgmt"
0x18001a4e2  mov     rdx, rax; lpDst
0x18001a4e5  call    cs:__imp_ExpandEnvironmentStringsW
0x18001a4eb  test    eax, eax
0x18001a4ed  jnz     short loc_18001A506
0x18001a4ef  call    cs:__imp_GetLastError
0x18001a4f5  mov     ebx, eax
0x18001a4f7  test    eax, eax
0x18001a4f9  jle     short loc_18001A52F
0x18001a4fb  movzx   ebx, ax
0x18001a4fe  or      ebx, 80070000h
0x18001a504  jmp     short loc_18001A52F
0x18001a506  mov     rcx, [rdi]; unsigned __int16 *
0x18001a509  xor     r8d, r8d; unsigned int *
0x18001a50c  mov     edx, ebx; unsigned int
0x18001a50e  call    ?CheckSlashEx@@YAPEAGPEAGIPEAI@Z; CheckSlashEx(ushort *,uint,uint *)
0x18001a513  test    rax, rax
0x18001a516  jnz     short loc_18001A51F
0x18001a518  mov     ebx, 8007007Ah
0x18001a51d  jmp     short loc_18001A533
0x18001a51f  mov     rcx, [rdi]; unsigned __int16 *
0x18001a522  mov     r8, rsi; unsigned __int16 *
0x18001a525  mov     rdx, r14; unsigned __int64
0x18001a528  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a52d  mov     ebx, eax
0x18001a52f  test    ebx, ebx
0x18001a531  jns     short loc_18001A544
0x18001a533  mov     rcx, [rdi]; hMem
0x18001a536  test    rcx, rcx
0x18001a539  jz      short loc_18001A544
0x18001a53b  call    cs:__imp_LocalFree
0x18001a541  mov     [rdi], rbp
0x18001a544  mov     eax, ebx
0x18001a546  add     rsp, 20h
0x18001a54a  pop     r14
0x18001a54c  pop     rdi
0x18001a54d  pop     rsi
0x18001a54e  pop     rbp
0x18001a54f  pop     rbx
0x18001a550  retn
```
