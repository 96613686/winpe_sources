# _RenameLink(tagCREATELINKDATA *,HWND__ *)

- ea: `0x18002e764`
- end: `0x18002e8fa`
- name: `?_RenameLink@@YAJPEAUtagCREATELINKDATA@@PEAUHWND__@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(const WCHAR *, HWND)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002e2d0`
- `0x18002e9ac`

## callees

- `0x18002e530`
- `0x18002e764`
- `0x180059010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x18002e810`
- `SHELL32!SHCreateItemFromIDList` at `0x18002e810`
- `SHELL32!SHChangeNotify` at `0x18002e7ba`
- `SHELL32!SHChangeNotify` at `0x18002e8d0`
- `SHELL32!SHChangeNotify` at `0x18002e7ba`
- `SHELL32!SHChangeNotify` at `0x18002e8d0`
- `SHELL32!__imp_SHILCreateFromPath` at `0x18002e7d3`
- `SHELL32!__imp_SHILCreateFromPath` at `0x18002e7d3`
- `SHELL32!__imp_ILFree` at `0x18002e8da`
- `SHELL32!__imp_ILFree` at `0x18002e8e3`
- `SHELL32!__imp_ILFree` at `0x18002e8da`
- `SHELL32!__imp_ILFree` at `0x18002e8e3`
- `SHELL32!__imp_ILCreateFromPathW` at `0x18002e89f`
- `SHELL32!__imp_ILCreateFromPathW` at `0x18002e89f`
- `SHLWAPI!PathFindFileNameW` at `0x18002e82a`
- `SHLWAPI!PathFindFileNameW` at `0x18002e82a`
- `SHLWAPI!PathFileExistsW` at `0x18002e797`
- `SHLWAPI!PathFileExistsW` at `0x18002e868`
- `SHLWAPI!PathFileExistsW` at `0x18002e797`
- `SHLWAPI!PathFileExistsW` at `0x18002e868`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002e7a4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002e7a4`

## pseudocode

```c
__int64 __fastcall _RenameLink(const WCHAR *a1, HWND a2)
{
  const WCHAR *v2; // rdi
  HRESULT v4; // ebx
  const WCHAR *v5; // r14
  ITEMIDLIST *v6; // rsi
  unsigned int v7; // edx
  const struct _GUID *v8; // r8
  __int64 (__fastcall *v9)(void *, void *, LPWSTR, _QWORD); // rbx
  LPWSTR FileNameW; // rax
  LPITEMIDLIST v11; // rax
  LPITEMIDLIST v12; // r8
  LPITEMIDLIST v13; // r9
  UINT v14; // edx
  void *v16; // [rsp+70h] [rbp+40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+80h] [rbp+50h] BYREF
  void *ppv; // [rsp+88h] [rbp+58h] BYREF

  v2 = a1 + 1042;
  v4 = 0;
  if ( a1[1042] )
  {
    v5 = a1 + 2;
    if ( PathFileExistsW(a1 + 2) )
    {
      DeleteFileW(v2);
      SHChangeNotify(4, 0x1005u, v2, 0);
    }
    else
    {
      ppidl = 0;
      v6 = 0;
      v4 = SHILCreateFromPath(v2, &ppidl, 0);
      if ( v4 >= 0 )
      {
        v16 = 0;
        v4 = SHCreateFileOperation(a2, v7, v8, &v16);
        if ( v4 >= 0 )
        {
          ppv = 0;
          v4 = SHCreateItemFromIDList(ppidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
          if ( v4 >= 0 )
          {
            v9 = *(__int64 (__fastcall **)(void *, void *, LPWSTR, _QWORD))(*(_QWORD *)v16 + 96LL);
            FileNameW = PathFindFileNameW(v5);
            v4 = v9(v16, ppv, FileNameW, 0);
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v16 + 168LL))(v16);
              if ( v4 >= 0 && !PathFileExistsW(v5) )
                v4 = -2147467259;
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
          if ( v4 >= 0 )
          {
            v11 = ILCreateFromPathW(v5);
            v12 = ppidl;
            v6 = v11;
            if ( ppidl && v11 )
            {
              v13 = v11;
              v14 = 4096;
            }
            else
            {
              v13 = (LPITEMIDLIST)v5;
              v12 = (LPITEMIDLIST)v2;
              v14 = 4101;
            }
            SHChangeNotify(1, v14, v12, v13);
          }
        }
      }
      ILFree(ppidl);
      ILFree(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002e764  push    rbp
0x18002e766  push    rbx
0x18002e767  push    rsi
0x18002e768  push    rdi
0x18002e769  push    r12
0x18002e76b  push    r14
0x18002e76d  push    r15
0x18002e76f  mov     rbp, rsp
0x18002e772  sub     rsp, 30h
0x18002e776  xor     r12d, r12d
0x18002e779  lea     rdi, [rcx+824h]
0x18002e780  mov     r15, rdx
0x18002e783  mov     ebx, r12d
0x18002e786  cmp     [rdi], r12w
0x18002e78a  jz      loc_18002E8E9
0x18002e790  lea     r14, [rcx+4]
0x18002e794  mov     rcx, r14; pszPath
0x18002e797  call    cs:__imp_PathFileExistsW
0x18002e79d  mov     rcx, rdi; pszPath
0x18002e7a0  test    eax, eax
0x18002e7a2  jz      short loc_18002E7C5
0x18002e7a4  call    cs:__imp_DeleteFileW
0x18002e7aa  xor     r9d, r9d; dwItem2
0x18002e7ad  lea     ecx, [r12+4]; wEventId
0x18002e7b2  mov     r8, rdi; dwItem1
0x18002e7b5  mov     edx, 1005h; uFlags
0x18002e7ba  call    cs:__imp_SHChangeNotify
0x18002e7c0  jmp     loc_18002E8E9
0x18002e7c5  xor     r8d, r8d; rgfInOut
0x18002e7c8  mov     [rbp+ppidl], r12
0x18002e7cc  lea     rdx, [rbp+ppidl]; ppidl
0x18002e7d0  mov     rsi, r12
0x18002e7d3  call    cs:__imp_SHILCreateFromPath
0x18002e7d9  mov     ebx, eax
0x18002e7db  test    eax, eax
0x18002e7dd  js      loc_18002E8D6
0x18002e7e3  lea     r9, [rbp+arg_0]; void **
0x18002e7e7  mov     [rbp+arg_0], r12
0x18002e7eb  mov     rcx, r15; HWND
0x18002e7ee  call    ?SHCreateFileOperation@@YAJPEAUHWND__@@KAEBU_GUID@@PEAPEAX@Z; SHCreateFileOperation(HWND__ *,ulong,_GUID const &,void * *)
0x18002e7f3  mov     ebx, eax
0x18002e7f5  test    eax, eax
0x18002e7f7  js      loc_18002E8D6
0x18002e7fd  mov     rcx, [rbp+ppidl]; pidl
0x18002e801  lea     r8, [rbp+ppv]; ppv
0x18002e805  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002e80c  mov     [rbp+ppv], r12
0x18002e810  call    cs:__imp_SHCreateItemFromIDList
0x18002e816  mov     ebx, eax
0x18002e818  test    eax, eax
0x18002e81a  js      short loc_18002E888
0x18002e81c  mov     rax, [rbp+arg_0]
0x18002e820  mov     rcx, [rax]
0x18002e823  mov     rbx, [rcx+60h]
0x18002e827  mov     rcx, r14; pszPath
0x18002e82a  call    cs:__imp_PathFindFileNameW
0x18002e830  mov     rdx, [rbp+ppv]
0x18002e834  xor     r9d, r9d
0x18002e837  mov     rcx, [rbp+arg_0]
0x18002e83b  mov     r8, rax
0x18002e83e  mov     rax, rbx
0x18002e841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e846  mov     ebx, eax
0x18002e848  test    eax, eax
0x18002e84a  js      short loc_18002E878
0x18002e84c  mov     rcx, [rbp+arg_0]
0x18002e850  mov     rax, [rcx]
0x18002e853  mov     rax, [rax+0A8h]
0x18002e85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e85f  mov     ebx, eax
0x18002e861  test    eax, eax
0x18002e863  js      short loc_18002E878
0x18002e865  mov     rcx, r14; pszPath
0x18002e868  call    cs:__imp_PathFileExistsW
0x18002e86e  test    eax, eax
0x18002e870  mov     ecx, 80004005h
0x18002e875  cmovz   ebx, ecx
0x18002e878  mov     rcx, [rbp+ppv]
0x18002e87c  mov     rax, [rcx]
0x18002e87f  mov     rax, [rax+10h]
0x18002e883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e888  mov     rcx, [rbp+arg_0]
0x18002e88c  mov     rax, [rcx]
0x18002e88f  mov     rax, [rax+10h]
0x18002e893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e898  test    ebx, ebx
0x18002e89a  js      short loc_18002E8D6
0x18002e89c  mov     rcx, r14; pszPath
0x18002e89f  call    cs:__imp_ILCreateFromPathW
0x18002e8a5  mov     r8, [rbp+ppidl]
0x18002e8a9  mov     rsi, rax
0x18002e8ac  test    r8, r8
0x18002e8af  jz      short loc_18002E8C0
0x18002e8b1  test    rax, rax
0x18002e8b4  jz      short loc_18002E8C0
0x18002e8b6  mov     r9, rax
0x18002e8b9  mov     edx, 1000h
0x18002e8be  jmp     short loc_18002E8CB
0x18002e8c0  mov     r9, r14; dwItem2
0x18002e8c3  mov     r8, rdi; dwItem1
0x18002e8c6  mov     edx, 1005h; uFlags
0x18002e8cb  mov     ecx, 1; wEventId
0x18002e8d0  call    cs:__imp_SHChangeNotify
0x18002e8d6  mov     rcx, [rbp+ppidl]; pidl
0x18002e8da  call    cs:__imp_ILFree
0x18002e8e0  mov     rcx, rsi; pidl
0x18002e8e3  call    cs:__imp_ILFree
0x18002e8e9  mov     eax, ebx
0x18002e8eb  add     rsp, 30h
0x18002e8ef  pop     r15
0x18002e8f1  pop     r14
0x18002e8f3  pop     r12
0x18002e8f5  pop     rdi
0x18002e8f6  pop     rsi
0x18002e8f7  pop     rbx
0x18002e8f8  pop     rbp
0x18002e8f9  retn
```
