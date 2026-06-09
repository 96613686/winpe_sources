# UniDrvUI::LoadDriverDllAsDatafile(UniDrvUI::_COMMONINFO *,ushort const *)

- ea: `0x180113ea4`
- end: `0x180113fdb`
- name: `?LoadDriverDllAsDatafile@UniDrvUI@@YAPEAUHINSTANCE__@@PEAU_COMMONINFO@1@PEBG@Z`
- size: `311`
- prototype: `HINSTANCE __fastcall(UniDrvUI *this, struct UniDrvUI::_COMMONINFO *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180113d84`

## callees

- `0x18010b1e4`
- `0x180113ea4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180113f0c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180113f40`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180113f0c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180113f40`
- `KERNEL32!LocalFree` at `0x180113f9d`
- `KERNEL32!LocalFree` at `0x180113f9d`
- `KERNEL32!LoadLibraryExW` at `0x180113f8b`
- `KERNEL32!LoadLibraryExW` at `0x180113fbb`
- `KERNEL32!LoadLibraryExW` at `0x180113f8b`
- `KERNEL32!LoadLibraryExW` at `0x180113fbb`
- `KERNEL32!LocalAlloc` at `0x180113f61`
- `KERNEL32!LocalAlloc` at `0x180113f61`

## pseudocode

```c
HINSTANCE __fastcall UniDrvUI::LoadDriverDllAsDatafile(
        UniDrvUI *this,
        struct UniDrvUI::_COMMONINFO *a2,
        const unsigned __int16 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rbx
  const WCHAR *v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // rdx
  unsigned int v9; // esi
  HMODULE Library; // rbx
  wchar_t *v11; // rax
  WCHAR *v12; // rdi
  const WCHAR *v13; // rcx

  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)a2 + v3) );
  if ( this )
  {
    v5 = *((_QWORD *)this + 7);
    if ( v5 )
    {
      v6 = *(const WCHAR **)(v5 + 56);
      if ( v6 )
      {
        if ( *v6 )
        {
          while ( 1 )
          {
            v7 = -1;
            do
              ++v7;
            while ( v6[v7] );
            if ( (unsigned int)v7 > (int)v3 + 1 )
            {
              v8 = (unsigned int)(v7 - v3);
              if ( v6[(unsigned int)(v8 - 1)] == 92 && !(unsigned int)_o__wcsicmp(a2, &v6[v8]) )
                break;
            }
            v6 += (unsigned int)(v7 + 1);
            if ( !*v6 )
              goto LABEL_13;
          }
          v13 = v6;
          return LoadLibraryExW(v13, 0, 2u);
        }
      }
    }
  }
LABEL_13:
  if ( (unsigned int)v3 <= 5 || (unsigned int)_o__wcsicmp(L".mui", (char *)a2 + 2 * (unsigned int)(v3 - 4)) )
  {
    v13 = (const WCHAR *)a2;
    return LoadLibraryExW(v13, 0, 2u);
  }
  v9 = v3 - 3;
  Library = 0;
  v11 = (wchar_t *)LocalAlloc(0x40u, 2LL * (unsigned int)(v3 - 3));
  v12 = v11;
  if ( v11 )
  {
    StringCchCopyW(v11, v9, (STRSAFE_LPCWSTR)a2);
    Library = LoadLibraryExW(v12, 0, 2u);
    LocalFree(v12);
  }
  return Library;
}

```

## disassembly

```asm
0x180113ea4  push    rbx
0x180113ea6  push    rbp
0x180113ea7  push    rsi
0x180113ea8  push    rdi
0x180113ea9  push    r14
0x180113eab  push    r15
0x180113ead  sub     rsp, 28h
0x180113eb1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180113eb5  mov     r14, rdx
0x180113eb8  xor     r15d, r15d
0x180113ebb  inc     rdi
0x180113ebe  cmp     [rdx+rdi*2], r15w
0x180113ec3  jnz     short loc_180113EBB
0x180113ec5  test    rcx, rcx
0x180113ec8  jz      short loc_180113F2D
0x180113eca  mov     rbx, [rcx+38h]
0x180113ece  test    rbx, rbx
0x180113ed1  jz      short loc_180113F2D
0x180113ed3  mov     rbx, [rbx+38h]
0x180113ed7  test    rbx, rbx
0x180113eda  jz      short loc_180113F2D
0x180113edc  cmp     [rbx], r15w
0x180113ee0  jz      short loc_180113F2D
0x180113ee2  lea     ebp, [rdi+1]
0x180113ee5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180113ee9  inc     rsi
0x180113eec  cmp     [rbx+rsi*2], r15w
0x180113ef1  jnz     short loc_180113EE9
0x180113ef3  cmp     esi, ebp
0x180113ef5  jbe     short loc_180113F20
0x180113ef7  mov     edx, esi
0x180113ef9  sub     edx, edi
0x180113efb  lea     eax, [rdx-1]
0x180113efe  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x180113f03  jnz     short loc_180113F20
0x180113f05  lea     rdx, [rbx+rdx*2]
0x180113f09  mov     rcx, r14
0x180113f0c  call    cs:__imp__o__wcsicmp
0x180113f13  nop     dword ptr [rax+rax+00h]
0x180113f18  test    eax, eax
0x180113f1a  jz      loc_180113FAB
0x180113f20  lea     eax, [rsi+1]
0x180113f23  lea     rbx, [rbx+rax*2]
0x180113f27  cmp     [rbx], r15w
0x180113f2b  jnz     short loc_180113EE5
0x180113f2d  cmp     edi, 5
0x180113f30  jbe     short loc_180113FB0
0x180113f32  lea     eax, [rdi-4]
0x180113f35  lea     rdx, [r14+rax*2]
0x180113f39  lea     rcx, aMui; ".mui"
0x180113f40  call    cs:__imp__o__wcsicmp
0x180113f47  nop     dword ptr [rax+rax+00h]
0x180113f4c  test    eax, eax
0x180113f4e  jnz     short loc_180113FB0
0x180113f50  lea     eax, [rdi-3]
0x180113f53  mov     ecx, 40h ; '@'; uFlags
0x180113f58  lea     rdx, [rax+rax]; uBytes
0x180113f5c  mov     esi, eax
0x180113f5e  mov     rbx, r15
0x180113f61  call    cs:__imp_LocalAlloc
0x180113f68  nop     dword ptr [rax+rax+00h]
0x180113f6d  mov     rdi, rax
0x180113f70  test    rax, rax
0x180113f73  jz      short loc_180113FCA
0x180113f75  mov     r8, r14; pszSrc
0x180113f78  mov     edx, esi; cchDest
0x180113f7a  mov     rcx, rax; pszDest
0x180113f7d  call    StringCchCopyW
0x180113f82  xor     edx, edx; hFile
0x180113f84  mov     rcx, rdi; lpLibFileName
0x180113f87  lea     r8d, [rdx+2]; dwFlags
0x180113f8b  call    cs:__imp_LoadLibraryExW
0x180113f92  nop     dword ptr [rax+rax+00h]
0x180113f97  mov     rcx, rdi; hMem
0x180113f9a  mov     rbx, rax
0x180113f9d  call    cs:__imp_LocalFree
0x180113fa4  nop     dword ptr [rax+rax+00h]
0x180113fa9  jmp     short loc_180113FCA
0x180113fab  mov     rcx, rbx
0x180113fae  jmp     short loc_180113FB3
0x180113fb0  mov     rcx, r14; lpLibFileName
0x180113fb3  mov     r8d, 2; dwFlags
0x180113fb9  xor     edx, edx; hFile
0x180113fbb  call    cs:__imp_LoadLibraryExW
0x180113fc2  nop     dword ptr [rax+rax+00h]
0x180113fc7  mov     rbx, rax
0x180113fca  mov     rax, rbx
0x180113fcd  add     rsp, 28h
0x180113fd1  pop     r15
0x180113fd3  pop     r14
0x180113fd5  pop     rdi
0x180113fd6  pop     rsi
0x180113fd7  pop     rbp
0x180113fd8  pop     rbx
0x180113fd9  retn
```
