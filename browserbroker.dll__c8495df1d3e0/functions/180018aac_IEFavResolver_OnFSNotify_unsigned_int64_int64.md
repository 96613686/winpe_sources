# IEFavResolver::OnFSNotify(unsigned __int64,__int64)

- ea: `0x180018aac`
- end: `0x180018c08`
- name: `?OnFSNotify@IEFavResolver@@AEAAX_K_J@Z`
- size: `348`
- prototype: `void __fastcall(IEFavResolver *__hidden this, HANDLE hChange, DWORD dwProcId)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001ad80`

## callees

- `0x180018aac`
- `0x180018c10`
- `0x180018d94`
- `0x180018f0c`
- `0x180019088`
- `0x1800192f8`
- `0x18001947c`
- `0x180019984`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018b61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018b61`
- `ext-ms-win-shell-shell32-l1-2-1!SHChangeNotification_Unlock` at `0x180018bf9`
- `ext-ms-win-shell-shell32-l1-2-1!SHChangeNotification_Unlock` at `0x180018bf9`
- `ext-ms-win-shell-shell32-l1-2-1!SHChangeNotification_Lock` at `0x180018adb`
- `ext-ms-win-shell-shell32-l1-2-1!SHChangeNotification_Lock` at `0x180018adb`

## pseudocode

```c
void __fastcall IEFavResolver::OnFSNotify(WCHAR *this, HANDLE hChange, DWORD dwProcId)
{
  IEFavResolver *v4; // rcx
  HANDLE v5; // rsi
  LPITEMIDLIST *v6; // rdx
  LPITEMIDLIST v7; // rbx
  int v8; // ebx
  char v9; // r9
  char v10; // r8
  LPITEMIDLIST *pppidl; // [rsp+20h] [rbp-18h] BYREF
  LONG plEvent; // [rsp+78h] [rbp+40h] BYREF

  plEvent = 0;
  pppidl = 0;
  v5 = SHChangeNotification_Lock(hChange, dwProcId, &pppidl, &plEvent);
  if ( v5 )
  {
    if ( plEvent != 1 )
    {
      switch ( plEvent )
      {
        case 2:
          IEFavResolver::OnIEFavAdded(this, *pppidl);
          goto LABEL_27;
        case 4:
          v10 = 0;
          break;
        case 8:
          IEFavResolver::OnIEFavFolderAdded(this, *pppidl);
          goto LABEL_27;
        case 0x10:
          v10 = 1;
          break;
        case 0x1000:
          IEFavResolver::OnIEFolderUpdated(v4, *pppidl);
          goto LABEL_27;
        case 0x2000:
          IEFavResolver::OnIEFavUpdated(this, *pppidl);
          goto LABEL_27;
        case 0x20000:
          v9 = 1;
LABEL_26:
          IEFavResolver::OnIEFavRenamed(this, *pppidl, pppidl[1], v9);
          goto LABEL_27;
        case 0x4000000:
          v6 = pppidl;
          v7 = *pppidl;
          if ( *(_DWORD *)(*pppidl)->mkid.abID != 2 )
            goto LABEL_27;
          if ( v7->mkid.cb >= 0x12u && *(WCHAR **)&v7[2].mkid.cb == this )
          {
            v8 = *(_DWORD *)v7[4].mkid.abID;
            if ( v8 == GetCurrentProcessId() )
            {
LABEL_27:
              SHChangeNotification_Unlock(v5);
              return;
            }
            v6 = pppidl;
          }
          IEFavResolver::PostOrderChangedEventToEdge((IEFavResolver *)this, v6[1]);
          goto LABEL_27;
        default:
          goto LABEL_27;
      }
      IEFavResolver::OnIEFavDeleted(this, *pppidl, v10);
      goto LABEL_27;
    }
    v9 = 0;
    goto LABEL_26;
  }
}

```

## disassembly

```asm
0x180018aac  push    rbp
0x180018aae  push    rbx
0x180018aaf  push    rsi
0x180018ab0  push    rdi
0x180018ab1  mov     rbp, rsp
0x180018ab4  sub     rsp, 38h
0x180018ab8  mov     rax, rdx
0x180018abb  mov     [rbp+plEvent], 0
0x180018ac2  mov     edx, r8d; dwProcId
0x180018ac5  mov     [rbp+pppidl], 0
0x180018acd  mov     rdi, rcx
0x180018ad0  lea     r8, [rbp+pppidl]; pppidl
0x180018ad4  mov     rcx, rax; hChange
0x180018ad7  lea     r9, [rbp+plEvent]; plEvent
0x180018adb  call    cs:__imp_SHChangeNotification_Lock
0x180018ae1  mov     rsi, rax
0x180018ae4  test    rax, rax
0x180018ae7  jz      loc_180018BFF
0x180018aed  mov     edx, [rbp+plEvent]
0x180018af0  sub     edx, 1
0x180018af3  jz      loc_180018BE0
0x180018af9  sub     edx, 1
0x180018afc  jz      loc_180018BCF
0x180018b02  sub     edx, 2
0x180018b05  jz      loc_180018BCA
0x180018b0b  sub     edx, 4
0x180018b0e  jz      loc_180018BB9
0x180018b14  sub     edx, 8
0x180018b17  jz      loc_180018BA5
0x180018b1d  sub     edx, 0FF0h
0x180018b23  jz      short loc_180018B97
0x180018b25  sub     edx, 1000h
0x180018b2b  jz      short loc_180018B86
0x180018b2d  sub     edx, 1E000h
0x180018b33  jz      short loc_180018B81
0x180018b35  cmp     edx, 3FE0000h
0x180018b3b  jnz     loc_180018BF6
0x180018b41  mov     rdx, [rbp+pppidl]
0x180018b45  mov     rbx, [rdx]
0x180018b48  cmp     dword ptr [rbx+2], 2
0x180018b4c  jnz     loc_180018BF6
0x180018b52  cmp     word ptr [rbx], 12h
0x180018b56  jb      short loc_180018B73
0x180018b58  cmp     [rbx+6], rdi
0x180018b5c  jnz     short loc_180018B73
0x180018b5e  mov     ebx, [rbx+0Eh]
0x180018b61  call    cs:__imp_GetCurrentProcessId
0x180018b67  cmp     ebx, eax
0x180018b69  jz      loc_180018BF6
0x180018b6f  mov     rdx, [rbp+pppidl]
0x180018b73  mov     rdx, [rdx+8]; struct _ITEMIDLIST *
0x180018b77  mov     rcx, rdi; this
0x180018b7a  call    ?PostOrderChangedEventToEdge@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@@Z; IEFavResolver::PostOrderChangedEventToEdge(_ITEMIDLIST const *)
0x180018b7f  jmp     short loc_180018BF6
0x180018b81  mov     r9b, 1
0x180018b84  jmp     short loc_180018BE3
0x180018b86  mov     rdx, [rbp+pppidl]
0x180018b8a  mov     rcx, rdi; this
0x180018b8d  mov     rdx, [rdx]; pidl
0x180018b90  call    ?OnIEFavUpdated@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@@Z; IEFavResolver::OnIEFavUpdated(_ITEMIDLIST const *)
0x180018b95  jmp     short loc_180018BF6
0x180018b97  mov     rdx, [rbp+pppidl]
0x180018b9b  mov     rdx, [rdx]; struct _ITEMIDLIST *
0x180018b9e  call    ?OnIEFolderUpdated@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@@Z; IEFavResolver::OnIEFolderUpdated(_ITEMIDLIST const *)
0x180018ba3  jmp     short loc_180018BF6
0x180018ba5  mov     r8b, 1; bool
0x180018ba8  mov     rdx, [rbp+pppidl]
0x180018bac  mov     rcx, rdi; this
0x180018baf  mov     rdx, [rdx]; pidl
0x180018bb2  call    ?OnIEFavDeleted@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@_N@Z; IEFavResolver::OnIEFavDeleted(_ITEMIDLIST const *,bool)
0x180018bb7  jmp     short loc_180018BF6
0x180018bb9  mov     rdx, [rbp+pppidl]
0x180018bbd  mov     rcx, rdi; this
0x180018bc0  mov     rdx, [rdx]; pidl
0x180018bc3  call    ?OnIEFavFolderAdded@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@@Z; IEFavResolver::OnIEFavFolderAdded(_ITEMIDLIST const *)
0x180018bc8  jmp     short loc_180018BF6
0x180018bca  xor     r8d, r8d
0x180018bcd  jmp     short loc_180018BA8
0x180018bcf  mov     rdx, [rbp+pppidl]
0x180018bd3  mov     rcx, rdi; this
0x180018bd6  mov     rdx, [rdx]; pidl
0x180018bd9  call    ?OnIEFavAdded@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@@Z; IEFavResolver::OnIEFavAdded(_ITEMIDLIST const *)
0x180018bde  jmp     short loc_180018BF6
0x180018be0  xor     r9d, r9d; bool
0x180018be3  mov     rdx, [rbp+pppidl]
0x180018be7  mov     rcx, rdi; this
0x180018bea  mov     r8, [rdx+8]; struct _ITEMIDLIST *
0x180018bee  mov     rdx, [rdx]; struct _ITEMIDLIST *
0x180018bf1  call    ?OnIEFavRenamed@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@0_N@Z; IEFavResolver::OnIEFavRenamed(_ITEMIDLIST const *,_ITEMIDLIST const *,bool)
0x180018bf6  mov     rcx, rsi; hLock
0x180018bf9  call    cs:__imp_SHChangeNotification_Unlock
0x180018bff  add     rsp, 38h
0x180018c03  pop     rdi
0x180018c04  pop     rsi
0x180018c05  pop     rbx
0x180018c06  pop     rbp
0x180018c07  retn
```
