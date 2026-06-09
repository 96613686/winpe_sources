# CRepubCacheBackingStore::MoveFileStore(void *,CRepubFileStore *,ushort *,ushort *)

- ea: `0x18004a140`
- end: `0x18004a419`
- name: `?MoveFileStore@CRepubCacheBackingStore@@AEAAKPEAXPEAVCRepubFileStore@@PEAG2@Z`
- size: `729`
- prototype: `__int64 __fastcall(CRepubCacheBackingStore *this, char *, struct CRepubFileStore *, unsigned __int16 *, unsigned __int16 *String2)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800420ec`

## callees

- `0x1800024f0`
- `0x1800094d4`
- `0x18000cf48`
- `0x18000cfc0`
- `0x180018340`
- `0x18003da94`
- `0x18004a140`
- `0x180060fa0`
- `0x180116428`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004a17f`
- `msvcrt!_wcsicmp` at `0x18004a17f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2d9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004a2c8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004a2c8`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x18004a2bb`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x18004a2bb`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::MoveFileStore(
        CRepubCacheBackingStore *this,
        char *a2,
        struct CRepubFileStore *a3,
        unsigned __int16 *a4,
        unsigned __int16 *String2)
{
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // rbx
  const unsigned __int16 *v10; // r12
  DWORD LastError; // esi
  unsigned int v12; // eax
  CHostedCacheMsgEncoding *v13; // rcx
  int v14; // edx
  int v15; // r9d
  BOOL DirectoryW; // eax
  DWORD v17; // eax
  int v18; // eax
  LPCWSTR lpNewDirectory; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 *v21; // [rsp+38h] [rbp-20h]
  LPCWSTR v22; // [rsp+40h] [rbp-18h]
  unsigned __int64 v23; // [rsp+48h] [rbp-10h] BYREF
  unsigned __int16 *v24; // [rsp+A0h] [rbp+48h] BYREF

  v8 = 0;
  v21 = 0;
  v9 = 0;
  v22 = 0;
  v24 = 0;
  lpNewDirectory = 0;
  v10 = String2;
  if ( !_wcsicmp(a4, String2) )
  {
    LastError = 0;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 440, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, a4);
    }
    goto LABEL_42;
  }
  CRepubFileStore::Close(a3);
  v12 = ConstructRepubBlockFolderRoot(a4, &v24, &v23);
  LastError = v12;
  if ( v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_42;
    }
    v14 = 441;
    v15 = (int)a4;
    goto LABEL_11;
  }
  operator delete(0);
  v8 = v24;
  v21 = v24;
  v12 = ConstructRepubBlockFolderRoot(v10, (unsigned __int16 **)&lpNewDirectory, (unsigned __int64 *)&v24);
  LastError = v12;
  if ( v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_42;
    }
    v14 = 442;
    v15 = (int)v10;
LABEL_11:
    WPP_SF_Sd(*((_QWORD *)v13 + 12), v14, (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v15, v12);
    goto LABEL_42;
  }
  operator delete(0);
  v9 = (unsigned __int16 *)lpNewDirectory;
  v22 = lpNewDirectory;
  if ( (unsigned __int64)(a2 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    DirectoryW = CreateDirectoryW(lpNewDirectory, 0);
  else
    DirectoryW = CreateDirectoryTransactedW(0, lpNewDirectory, 0, a2);
  if ( DirectoryW )
    goto LABEL_27;
  LastError = GetLastError();
  if ( LastError == 183 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        443,
        (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
        (_DWORD)v9,
        183);
    }
    goto LABEL_27;
  }
  if ( !LastError )
  {
LABEL_27:
    v17 = MoveCacheStore(v8, 1, v9, a2, 0x10u);
    LastError = v17;
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          445,
          (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
          (_DWORD)v8,
          (__int64)v9,
          v17);
      }
    }
    else
    {
      v18 = StringCchCopyW(a4, 0x104u, v10);
      if ( v18 < 0 )
      {
        LastError = (unsigned __int16)v18;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            446,
            (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
            (_DWORD)a4,
            (__int64)v10,
            v18);
        }
      }
    }
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      444,
      (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
      (_DWORD)v9,
      LastError);
  }
LABEL_42:
  operator delete(v9);
  operator delete(v8);
  return LastError;
}

```

## disassembly

```asm
0x18004a140  mov     [rsp-40h+arg_0], rcx
0x18004a145  push    rbp
0x18004a146  push    rbx
0x18004a147  push    rsi
0x18004a148  push    rdi
0x18004a149  push    r12
0x18004a14b  push    r13
0x18004a14d  push    r14
0x18004a14f  push    r15
0x18004a151  mov     rbp, rsp
0x18004a154  sub     rsp, 58h
0x18004a158  mov     r15, r9
0x18004a15b  mov     rsi, r8
0x18004a15e  mov     r13, rdx
0x18004a161  xor     edi, edi
0x18004a163  mov     [rbp+var_20], rdi
0x18004a167  xor     ebx, ebx
0x18004a169  mov     [rbp+var_18], rbx
0x18004a16d  mov     [rbp+arg_0], rbx
0x18004a171  mov     [rbp+lpNewDirectory], rbx
0x18004a175  mov     r12, [rbp+String2]
0x18004a179  mov     rdx, r12; String2
0x18004a17c  mov     rcx, r9; String1
0x18004a17f  call    cs:__imp__wcsicmp
0x18004a185  test    eax, eax
0x18004a187  jnz     short loc_18004A1D3
0x18004a189  xor     esi, esi
0x18004a18b  lea     r14, WPP_GLOBAL_Control
0x18004a192  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a199  cmp     rcx, r14
0x18004a19c  jz      loc_18004A3F5
0x18004a1a2  test    byte ptr [rcx+6Ch], 4
0x18004a1a6  jz      loc_18004A3F5
0x18004a1ac  cmp     byte ptr [rcx+69h], 3
0x18004a1b0  jb      loc_18004A3F5
0x18004a1b6  mov     edx, 1B8h
0x18004a1bb  mov     r9, r15
0x18004a1be  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004a1c5  mov     rcx, [rcx+60h]
0x18004a1c9  call    WPP_SF_S
0x18004a1ce  jmp     loc_18004A3F5
0x18004a1d3  mov     rcx, rsi; this
0x18004a1d6  call    ?Close@CRepubFileStore@@QEAAXXZ; CRepubFileStore::Close(void)
0x18004a1db  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18004a1df  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x18004a1e3  mov     rcx, r15; unsigned __int16 *
0x18004a1e6  call    ?ConstructRepubBlockFolderRoot@@YAKPEBGPEAPEAGPEA_K@Z; ConstructRepubBlockFolderRoot(ushort const *,ushort * *,unsigned __int64 *)
0x18004a1eb  mov     esi, eax
0x18004a1ed  test    eax, eax
0x18004a1ef  jz      short loc_18004A23D
0x18004a1f1  lea     r14, WPP_GLOBAL_Control
0x18004a1f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a1ff  cmp     rcx, r14
0x18004a202  jz      loc_18004A3F5
0x18004a208  test    byte ptr [rcx+6Ch], 4
0x18004a20c  jz      loc_18004A3F5
0x18004a212  cmp     byte ptr [rcx+69h], 1
0x18004a216  jb      loc_18004A3F5
0x18004a21c  mov     edx, 1B9h
0x18004a221  mov     r9, r15
0x18004a224  mov     [rsp+58h+var_38], eax
0x18004a228  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004a22f  mov     rcx, [rcx+60h]
0x18004a233  call    WPP_SF_Sd
0x18004a238  jmp     loc_18004A3F5
0x18004a23d  xor     ecx, ecx; Block
0x18004a23f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a244  mov     rdi, [rbp+arg_0]
0x18004a248  mov     [rbp+var_20], rdi
0x18004a24c  lea     r8, [rbp+arg_0]; unsigned __int64 *
0x18004a250  lea     rdx, [rbp+lpNewDirectory]; unsigned __int16 **
0x18004a254  mov     rcx, r12; unsigned __int16 *
0x18004a257  call    ?ConstructRepubBlockFolderRoot@@YAKPEBGPEAPEAGPEA_K@Z; ConstructRepubBlockFolderRoot(ushort const *,ushort * *,unsigned __int64 *)
0x18004a25c  mov     esi, eax
0x18004a25e  test    eax, eax
0x18004a260  jz      short loc_18004A297
0x18004a262  lea     r14, WPP_GLOBAL_Control
0x18004a269  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a270  cmp     rcx, r14
0x18004a273  jz      loc_18004A3F5
0x18004a279  test    byte ptr [rcx+6Ch], 4
0x18004a27d  jz      loc_18004A3F5
0x18004a283  cmp     byte ptr [rcx+69h], 1
0x18004a287  jb      loc_18004A3F5
0x18004a28d  mov     edx, 1BAh
0x18004a292  mov     r9, r12
0x18004a295  jmp     short loc_18004A224
0x18004a297  xor     ecx, ecx; Block
0x18004a299  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a29e  mov     rbx, [rbp+lpNewDirectory]
0x18004a2a2  mov     [rbp+var_18], rbx
0x18004a2a6  lea     rax, [r13-1]
0x18004a2aa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004a2ae  ja      short loc_18004A2C3
0x18004a2b0  mov     r9, r13; hTransaction
0x18004a2b3  xor     r8d, r8d; lpSecurityAttributes
0x18004a2b6  mov     rdx, rbx; lpNewDirectory
0x18004a2b9  xor     ecx, ecx; lpTemplateDirectory
0x18004a2bb  call    cs:__imp_CreateDirectoryTransactedW
0x18004a2c1  jmp     short loc_18004A2CE
0x18004a2c3  xor     edx, edx; lpSecurityAttributes
0x18004a2c5  mov     rcx, rbx; lpPathName
0x18004a2c8  call    cs:__imp_CreateDirectoryW
0x18004a2ce  lea     r14, WPP_GLOBAL_Control
0x18004a2d5  test    eax, eax
0x18004a2d7  jnz     short loc_18004A322
0x18004a2d9  call    cs:__imp_GetLastError
0x18004a2df  mov     esi, eax
0x18004a2e1  mov     eax, 0B7h
0x18004a2e6  cmp     esi, eax
0x18004a2e8  jnz     loc_18004A377
0x18004a2ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a2f5  cmp     rcx, r14
0x18004a2f8  jz      short loc_18004A322
0x18004a2fa  test    byte ptr [rcx+6Ch], 4
0x18004a2fe  jz      short loc_18004A322
0x18004a300  cmp     byte ptr [rcx+69h], 4
0x18004a304  jb      short loc_18004A322
0x18004a306  mov     edx, 1BBh
0x18004a30b  mov     [rsp+58h+var_38], eax
0x18004a30f  mov     r9, rbx
0x18004a312  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004a319  mov     rcx, [rcx+60h]
0x18004a31d  call    WPP_SF_Sd
0x18004a322  mov     [rsp+58h+var_38], 10h; unsigned int
0x18004a32a  mov     r9, r13; void *
0x18004a32d  mov     r8, rbx; unsigned __int16 *
0x18004a330  mov     dl, 1; bool
0x18004a332  mov     rcx, rdi; unsigned __int16 *
0x18004a335  call    ?MoveCacheStore@@YAKPEBG_N0PEAXK@Z; MoveCacheStore(ushort const *,bool,ushort const *,void *,ulong)
0x18004a33a  mov     esi, eax
0x18004a33c  test    eax, eax
0x18004a33e  jz      short loc_18004A3A4
0x18004a340  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a347  cmp     rcx, r14
0x18004a34a  jz      loc_18004A3F5
0x18004a350  test    byte ptr [rcx+6Ch], 4
0x18004a354  jz      loc_18004A3F5
0x18004a35a  cmp     byte ptr [rcx+69h], 1
0x18004a35e  jb      loc_18004A3F5
0x18004a364  mov     edx, 1BDh
0x18004a369  mov     [rsp+58h+var_30], eax
0x18004a36d  mov     qword ptr [rsp+58h+var_38], rbx
0x18004a372  mov     r9, rdi
0x18004a375  jmp     short loc_18004A3E4
0x18004a377  test    esi, esi
0x18004a379  jz      short loc_18004A322
0x18004a37b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a382  cmp     rcx, r14
0x18004a385  jz      short loc_18004A3F5
0x18004a387  test    byte ptr [rcx+6Ch], 4
0x18004a38b  jz      short loc_18004A3F5
0x18004a38d  cmp     byte ptr [rcx+69h], 1
0x18004a391  jb      short loc_18004A3F5
0x18004a393  mov     edx, 1BCh
0x18004a398  mov     [rsp+58h+var_38], esi
0x18004a39c  mov     r9, rbx
0x18004a39f  jmp     loc_18004A228
0x18004a3a4  mov     r8, r12; unsigned __int16 *
0x18004a3a7  mov     edx, 104h; unsigned __int64
0x18004a3ac  mov     rcx, r15; unsigned __int16 *
0x18004a3af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004a3b4  test    eax, eax
0x18004a3b6  jns     short loc_18004A3F5
0x18004a3b8  movzx   esi, ax
0x18004a3bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a3c2  cmp     rcx, r14
0x18004a3c5  jz      short loc_18004A3F5
0x18004a3c7  test    byte ptr [rcx+6Ch], 4
0x18004a3cb  jz      short loc_18004A3F5
0x18004a3cd  cmp     byte ptr [rcx+69h], 1
0x18004a3d1  jb      short loc_18004A3F5
0x18004a3d3  mov     edx, 1BEh
0x18004a3d8  mov     [rsp+58h+var_30], esi
0x18004a3dc  mov     qword ptr [rsp+58h+var_38], r12
0x18004a3e1  mov     r9, r15
0x18004a3e4  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004a3eb  mov     rcx, [rcx+60h]
0x18004a3ef  call    WPP_SF_SSD
0x18004a3f4  nop
0x18004a3f5  mov     rcx, rbx; Block
0x18004a3f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a3fd  nop
0x18004a3fe  mov     rcx, rdi; Block
0x18004a401  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a406  mov     eax, esi
0x18004a408  add     rsp, 58h
0x18004a40c  pop     r15
0x18004a40e  pop     r14
0x18004a410  pop     r13
0x18004a412  pop     r12
0x18004a414  pop     rdi
0x18004a415  pop     rsi
0x18004a416  pop     rbx
0x18004a417  pop     rbp
0x18004a418  retn
```
