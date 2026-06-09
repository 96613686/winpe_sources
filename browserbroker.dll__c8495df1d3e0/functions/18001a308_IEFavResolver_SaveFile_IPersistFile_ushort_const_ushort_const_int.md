# IEFavResolver::SaveFile(IPersistFile *,ushort const *,ushort const *,int)

- ea: `0x18001a308`
- end: `0x18001a407`
- name: `?SaveFile@IEFavResolver@@AEAAJPEAUIPersistFile@@PEBG1H@Z`
- size: `255`
- prototype: `__int64 __usercall@<rax>(IEFavResolver *__hidden this@<rcx>, struct IPersistFile *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016a9c`

## callees

- `0x180002ce0`
- `0x180016e70`
- `0x180017ba0`
- `0x18001a308`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001a38d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001a38d`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18001a344`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18001a344`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x18001a3da`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x18001a3da`

## pseudocode

```c
__int64 __fastcall IEFavResolver::SaveFile(
        HDPA *this,
        struct IPersistFile *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  int v9; // eax
  IEFavResolver *v10; // rcx
  int CompleteItemPathFromTitle; // ebx
  unsigned int v13; // [rsp+28h] [rbp-250h]
  WCHAR pszPath[264]; // [rsp+30h] [rbp-248h] BYREF

  IEFavResolver::AddToSyncList(this, a3);
  v9 = SHCreateDirectoryExW(0, a3, 0);
  CompleteItemPathFromTitle = v9;
  if ( !v9 || v9 == 183 )
  {
    CompleteItemPathFromTitle = IEFavResolver::GetCompleteItemPathFromTitle(v10, a3, a4, 0, pszPath, v13);
    if ( CompleteItemPathFromTitle >= 0 )
    {
      if ( PathFileExistsW(pszPath) )
      {
        return (unsigned int)-2147467259;
      }
      else
      {
        IEFavResolver::AddToSyncList(this, pszPath);
        CompleteItemPathFromTitle = ((__int64 (__fastcall *)(struct IPersistFile *, WCHAR *, _QWORD))a2->lpVtbl->Save)(
                                      a2,
                                      pszPath,
                                      0);
        if ( CompleteItemPathFromTitle >= 0 && !a5 )
          SHChangeNotify(2, 5u, pszPath, 0);
      }
    }
  }
  else if ( v9 > 0 )
  {
    return (unsigned __int16)v9 | 0x80070000;
  }
  return (unsigned int)CompleteItemPathFromTitle;
}

```

## disassembly

```asm
0x18001a308  push    rbx
0x18001a30a  push    rbp
0x18001a30b  push    rsi
0x18001a30c  push    rdi
0x18001a30d  push    r14
0x18001a30f  sub     rsp, 250h
0x18001a316  mov     rax, cs:__security_cookie
0x18001a31d  xor     rax, rsp
0x18001a320  mov     [rsp+278h+var_38], rax
0x18001a328  mov     rsi, rdx
0x18001a32b  mov     rbp, r9
0x18001a32e  mov     rdx, r8; unsigned __int16 *
0x18001a331  mov     rdi, r8
0x18001a334  mov     r14, rcx
0x18001a337  call    ?AddToSyncList@IEFavResolver@@AEAAJPEAG@Z; IEFavResolver::AddToSyncList(ushort *)
0x18001a33c  xor     r8d, r8d; psa
0x18001a33f  mov     rdx, rdi; pszPath
0x18001a342  xor     ecx, ecx; hwnd
0x18001a344  call    cs:__imp_SHCreateDirectoryExW
0x18001a34a  mov     ebx, eax
0x18001a34c  test    eax, eax
0x18001a34e  jz      short loc_18001A36A
0x18001a350  cmp     eax, 0B7h
0x18001a355  jz      short loc_18001A36A
0x18001a357  test    eax, eax
0x18001a359  jle     loc_18001A3E7
0x18001a35f  movzx   ebx, ax
0x18001a362  or      ebx, 80070000h
0x18001a368  jmp     short loc_18001A3E7
0x18001a36a  lea     rax, [rsp+278h+pszPath]
0x18001a36f  xor     r9d, r9d; bool
0x18001a372  mov     r8, rbp; unsigned __int16 *
0x18001a375  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18001a37a  mov     rdx, rdi; unsigned __int16 *
0x18001a37d  call    ?GetCompleteItemPathFromTitle@IEFavResolver@@AEAAJPEBG0_NPEAGI@Z; IEFavResolver::GetCompleteItemPathFromTitle(ushort const *,ushort const *,bool,ushort *,uint)
0x18001a382  mov     ebx, eax
0x18001a384  test    eax, eax
0x18001a386  js      short loc_18001A3E7
0x18001a388  lea     rcx, [rsp+278h+pszPath]; pszPath
0x18001a38d  call    cs:__imp_PathFileExistsW
0x18001a393  test    eax, eax
0x18001a395  jnz     short loc_18001A3E2
0x18001a397  lea     rdx, [rsp+278h+pszPath]; unsigned __int16 *
0x18001a39c  mov     rcx, r14; this
0x18001a39f  call    ?AddToSyncList@IEFavResolver@@AEAAJPEAG@Z; IEFavResolver::AddToSyncList(ushort *)
0x18001a3a4  mov     rax, [rsi]
0x18001a3a7  lea     rdx, [rsp+278h+pszPath]
0x18001a3ac  xor     r8d, r8d
0x18001a3af  mov     rcx, rsi
0x18001a3b2  mov     rax, [rax+30h]
0x18001a3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3bb  mov     ebx, eax
0x18001a3bd  test    eax, eax
0x18001a3bf  js      short loc_18001A3E7
0x18001a3c1  cmp     [rsp+278h+arg_20], 0
0x18001a3c9  jnz     short loc_18001A3E7
0x18001a3cb  xor     r9d, r9d; dwItem2
0x18001a3ce  lea     r8, [rsp+278h+pszPath]; dwItem1
0x18001a3d3  lea     edx, [r9+5]; uFlags
0x18001a3d7  lea     ecx, [rdx-3]; wEventId
0x18001a3da  call    cs:__imp_SHChangeNotify
0x18001a3e0  jmp     short loc_18001A3E7
0x18001a3e2  mov     ebx, 80004005h
0x18001a3e7  mov     eax, ebx
0x18001a3e9  mov     rcx, [rsp+278h+var_38]
0x18001a3f1  xor     rcx, rsp; StackCookie
0x18001a3f4  call    __security_check_cookie
0x18001a3f9  add     rsp, 250h
0x18001a400  pop     r14
0x18001a402  pop     rdi
0x18001a403  pop     rsi
0x18001a404  pop     rbp
0x18001a405  pop     rbx
0x18001a406  retn
```
