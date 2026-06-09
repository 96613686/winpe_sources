# CFavoritesEnumerator::EnumerateFavorites(ushort const *,ulong,tagEDGE_FAV_ITEM * *,uint *,ushort const *)

- ea: `0x18001af10`
- end: `0x18001b0c9`
- name: `?EnumerateFavorites@CFavoritesEnumerator@@UEAAJPEBGKPEAPEAUtagEDGE_FAV_ITEM@@PEAI0@Z`
- size: `441`
- prototype: `int(CFavoritesEnumerator *__hidden this, const unsigned __int16 *, unsigned int, struct tagEDGE_FAV_ITEM **, unsigned int *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000d17c`
- `0x18001af10`
- `0x18001b470`

## import_xrefs

- `iertutil!__imp_DSA_Create` at `0x18001afc7`
- `iertutil!__imp_DSA_Create` at `0x18001afc7`
- `iertutil!__imp_DSA_Destroy` at `0x18001b092`
- `iertutil!__imp_DSA_Destroy` at `0x18001b092`
- `iertutil!__imp_DSA_GetItem` at `0x18001b05b`
- `iertutil!__imp_DSA_GetItem` at `0x18001b05b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b01b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b01b`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x18001afac`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x18001afac`

## pseudocode

```c
__int64 __fastcall CFavoritesEnumerator::EnumerateFavorites(
        CFavoritesEnumerator *this,
        const unsigned __int16 *a2,
        int a3,
        struct tagEDGE_FAV_ITEM **a4,
        unsigned int *a5)
{
  int v6; // edi
  signed int v7; // ebx
  SIZE_T v8; // rbx
  struct tagEDGE_FAV_ITEM *v9; // rax
  struct tagEDGE_FAV_ITEM *v10; // rdi
  unsigned int v11; // eax
  int v12; // r15d
  BOOL Item; // eax
  bool v14; // cf
  BOOL v15; // edx
  unsigned int v17; // [rsp+40h] [rbp-C0h] BYREF
  HDSA hdsa; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( !a4 || !a5 )
    return (unsigned int)-2147024809;
  *a4 = 0;
  if ( (a3 & 0x10) != 0 )
    *((_DWORD *)this + 3) = *a5;
  *a5 = 0;
  v6 = (_DWORD)this - 16;
  *((_DWORD *)this + 2) = a3;
  if ( a2 && *a2 )
  {
    v7 = StringCchCopyW(pszPath, 0x104u, a2);
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  else if ( !SHGetSpecialFolderPathW(0, pszPath, 6, 1) )
  {
    return (unsigned int)-2147467259;
  }
  v17 = 0;
  hdsa = DSA_Create(24, 10);
  v7 = CFavoritesEnumerator::_EnumFolder(v6, (int)pszPath, 0, 0, 0, (__int64)&hdsa, &v17);
  if ( v7 >= 0 && v17 )
  {
    v8 = 24LL * v17;
    v9 = (struct tagEDGE_FAV_ITEM *)CoTaskMemAlloc(v8);
    v10 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, v8);
      v11 = v17;
      v7 = 0;
      v12 = 0;
      if ( (int)v17 <= 0 )
      {
LABEL_17:
        *a4 = v10;
        *a5 = v11;
      }
      else
      {
        while ( v7 >= 0 )
        {
          Item = DSA_GetItem(hdsa, v12, (char *)v10 + 24 * v12);
          ++v12;
          v14 = Item;
          v15 = Item;
          v11 = v17;
          v7 = v14 ? 0 : 0x80004005;
          if ( v12 >= (int)v17 )
          {
            if ( !v15 )
              break;
            goto LABEL_17;
          }
        }
      }
    }
    else
    {
      v7 = -2147024882;
    }
  }
  DSA_Destroy(hdsa);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001af10  push    rbp
0x18001af12  push    rbx
0x18001af13  push    rsi
0x18001af14  push    rdi
0x18001af15  push    r12
0x18001af17  push    r14
0x18001af19  push    r15
0x18001af1b  lea     rbp, [rsp-170h]
0x18001af23  sub     rsp, 270h
0x18001af2a  mov     rax, cs:__security_cookie
0x18001af31  xor     rax, rsp
0x18001af34  mov     [rbp+1A0h+var_40], rax
0x18001af3b  mov     rsi, [rbp+1A0h+arg_20]
0x18001af42  xor     r12d, r12d
0x18001af45  mov     r14, r9
0x18001af48  test    r9, r9
0x18001af4b  jz      loc_18001B0A1
0x18001af51  test    rsi, rsi
0x18001af54  jz      loc_18001B0A1
0x18001af5a  mov     [r9], r12
0x18001af5d  test    r8b, 10h
0x18001af61  jz      short loc_18001AF68
0x18001af63  mov     eax, [rsi]
0x18001af65  mov     [rcx+0Ch], eax
0x18001af68  mov     [rsi], r12d
0x18001af6b  lea     rdi, [rcx-10h]
0x18001af6f  mov     [rdi+18h], r8d
0x18001af73  test    rdx, rdx
0x18001af76  jz      short loc_18001AF9B
0x18001af78  cmp     [rdx], r12w
0x18001af7c  jz      short loc_18001AF9B
0x18001af7e  mov     r8, rdx; unsigned __int16 *
0x18001af81  lea     rcx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x18001af86  mov     edx, 104h; unsigned __int64
0x18001af8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001af90  mov     ebx, eax
0x18001af92  test    eax, eax
0x18001af94  jns     short loc_18001AFBA
0x18001af96  jmp     loc_18001B0A6
0x18001af9b  mov     r9d, 1; fCreate
0x18001afa1  lea     rdx, [rsp+2A0h+pszPath]; pszPath
0x18001afa6  xor     ecx, ecx; hwnd
0x18001afa8  lea     r8d, [r9+5]; csidl
0x18001afac  call    cs:__imp_SHGetSpecialFolderPathW
0x18001afb2  test    eax, eax
0x18001afb4  jz      loc_18001B09A
0x18001afba  mov     edx, 0Ah; cItemGrow
0x18001afbf  mov     [rsp+2A0h+var_260], r12d
0x18001afc4  lea     ecx, [rdx+0Eh]; cbItem
0x18001afc7  call    cs:__imp_DSA_Create
0x18001afcd  mov     [rsp+2A0h+hdsa], rax
0x18001afd2  xor     r9d, r9d; int
0x18001afd5  xor     r8d, r8d; int
0x18001afd8  lea     rdx, [rsp+2A0h+pszPath]; int
0x18001afdd  lea     rax, [rsp+2A0h+var_260]
0x18001afe2  mov     rcx, rdi; int
0x18001afe5  mov     [rsp+2A0h+var_270], rax; unsigned int *
0x18001afea  lea     rax, [rsp+2A0h+hdsa]
0x18001afef  mov     [rsp+2A0h+var_278], rax; __int64
0x18001aff4  mov     [rsp+2A0h+var_280], r12; __int64
0x18001aff9  call    ?_EnumFolder@CFavoritesEnumerator@@AEAAJPEBGIPEFBU_ITEMIDLIST@@PEAUIShellFolder@@PEAV?$CDSA@UtagEDGE_FAV_ITEM@@@@PEAI@Z; CFavoritesEnumerator::_EnumFolder(ushort const *,uint,_ITEMIDLIST const *,IShellFolder *,CDSA<tagEDGE_FAV_ITEM> *,uint *)
0x18001affe  mov     ebx, eax
0x18001b000  test    eax, eax
0x18001b002  js      loc_18001B08D
0x18001b008  mov     eax, [rsp+2A0h+var_260]
0x18001b00c  test    eax, eax
0x18001b00e  jz      short loc_18001B08D
0x18001b010  lea     rbx, [rax+rax*2]
0x18001b014  shl     rbx, 3
0x18001b018  mov     rcx, rbx; cb
0x18001b01b  call    cs:__imp_CoTaskMemAlloc
0x18001b021  mov     rdi, rax
0x18001b024  test    rax, rax
0x18001b027  jz      short loc_18001B088
0x18001b029  mov     r8, rbx; Size
0x18001b02c  xor     edx, edx; Val
0x18001b02e  mov     rcx, rax; void *
0x18001b031  call    memset_0
0x18001b036  mov     eax, [rsp+2A0h+var_260]
0x18001b03a  mov     ebx, r12d
0x18001b03d  mov     r15d, r12d
0x18001b040  test    eax, eax
0x18001b042  jle     short loc_18001B081
0x18001b044  test    ebx, ebx
0x18001b046  js      short loc_18001B08D
0x18001b048  movsxd  rax, r15d
0x18001b04b  mov     edx, r15d; i
0x18001b04e  lea     rcx, [rax+rax*2]
0x18001b052  lea     r8, [rdi+rcx*8]; pitem
0x18001b056  mov     rcx, [rsp+2A0h+hdsa]; hdsa
0x18001b05b  call    cs:__imp_DSA_GetItem
0x18001b061  mov     ecx, eax
0x18001b063  inc     r15d
0x18001b066  neg     ecx
0x18001b068  mov     edx, eax
0x18001b06a  mov     eax, [rsp+2A0h+var_260]
0x18001b06e  sbb     ebx, ebx
0x18001b070  not     ebx
0x18001b072  and     ebx, 80004005h
0x18001b078  cmp     r15d, eax
0x18001b07b  jl      short loc_18001B044
0x18001b07d  test    edx, edx
0x18001b07f  jz      short loc_18001B08D
0x18001b081  mov     [r14], rdi
0x18001b084  mov     [rsi], eax
0x18001b086  jmp     short loc_18001B08D
0x18001b088  mov     ebx, 8007000Eh
0x18001b08d  mov     rcx, [rsp+2A0h+hdsa]; hdsa
0x18001b092  call    cs:__imp_DSA_Destroy
0x18001b098  jmp     short loc_18001B0A6
0x18001b09a  mov     ebx, 80004005h
0x18001b09f  jmp     short loc_18001B0A6
0x18001b0a1  mov     ebx, 80070057h
0x18001b0a6  mov     eax, ebx
0x18001b0a8  mov     rcx, [rbp+1A0h+var_40]
0x18001b0af  xor     rcx, rsp; StackCookie
0x18001b0b2  call    __security_check_cookie
0x18001b0b7  add     rsp, 270h
0x18001b0be  pop     r15
0x18001b0c0  pop     r14
0x18001b0c2  pop     r12
0x18001b0c4  pop     rdi
0x18001b0c5  pop     rsi
0x18001b0c6  pop     rbx
0x18001b0c7  pop     rbp
0x18001b0c8  retn
```
