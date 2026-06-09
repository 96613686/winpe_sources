# ResumeKeyManager::CreateNewResumeKeyLocked(unsigned __int64 *)

- ea: `0x14003c280`
- end: `0x14003c387`
- name: `?CreateNewResumeKeyLocked@ResumeKeyManager@@AEAAPEAU_TE_ENUM_INTERNAL_RESUME_KEY@@PEA_K@Z`
- size: `263`
- prototype: `struct _TE_ENUM_INTERNAL_RESUME_KEY *__fastcall(ResumeKeyManager *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14003c390`

## callees

- `0x140002323`
- `0x14003bf40`
- `0x14003c178`
- `0x14003c280`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14003c342`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14003c342`

## pseudocode

```c
struct _TE_ENUM_INTERNAL_RESUME_KEY *__fastcall ResumeKeyManager::CreateNewResumeKeyLocked(
        ResumeKeyManager *this,
        unsigned __int64 *a2)
{
  __int64 v2; // rdi
  __int64 v5; // rsi
  ResumeKeyManager *v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-29h] BYREF
  __int64 v9; // [rsp+28h] [rbp-21h] BYREF
  char v10; // [rsp+30h] [rbp-19h]
  _BYTE v11[8]; // [rsp+38h] [rbp-11h] BYREF
  HANDLE hFindFile; // [rsp+40h] [rbp-9h]
  int v13; // [rsp+78h] [rbp+2Fh]

  v2 = *((_QWORD *)this + 6);
  if ( !v2 )
  {
    *((_QWORD *)this + 6) = 1;
    v2 = 1;
  }
  while ( 1 )
  {
    v5 = v2 ^ 0x5A5A5A5A5A5A5A5ALL;
    v8 = v2++ ^ 0x5A5A5A5A5A5A5A5ALL;
    v6 = *(ResumeKeyManager **)utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::find<void>(
                                 this,
                                 &v9,
                                 &v8);
    *((_QWORD *)this + 6) = v2;
    if ( v6 == this )
      break;
    if ( !v2 )
      return 0;
  }
  v8 = v5;
  memset_0(v11, 0, 0x40u);
  v13 = 0;
  utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::_TryEmplace<unsigned __int64 const &,TieringResumeKey>(
    this,
    &v9,
    &v8,
    v11);
  if ( (v11[0] & 1) != 0 && (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    FindClose(hFindFile);
  if ( !v10 )
  {
    --*((_QWORD *)this + 6);
    return 0;
  }
  *a2 = v8;
  return (struct _TE_ENUM_INTERNAL_RESUME_KEY *)(v9 + 32);
}

```

## disassembly

```asm
0x14003c280  mov     [rsp-8+arg_10], rbx
0x14003c285  mov     [rsp-8+arg_18], rsi
0x14003c28a  push    rbp
0x14003c28b  push    rdi
0x14003c28c  push    r14
0x14003c28e  lea     rbp, [rsp-47h]
0x14003c293  sub     rsp, 90h
0x14003c29a  mov     rax, cs:__security_cookie
0x14003c2a1  xor     rax, rsp
0x14003c2a4  mov     [rbp+57h+var_20], rax
0x14003c2a8  mov     rdi, [rcx+30h]
0x14003c2ac  mov     r14, rdx
0x14003c2af  mov     rbx, rcx
0x14003c2b2  test    rdi, rdi
0x14003c2b5  jnz     short loc_14003C2C4
0x14003c2b7  mov     qword ptr [rcx+30h], 1
0x14003c2bf  mov     edi, 1
0x14003c2c4  mov     rax, 5A5A5A5A5A5A5A5Ah
0x14003c2ce  lea     r8, [rbp+57h+var_80]
0x14003c2d2  mov     rsi, rdi
0x14003c2d5  lea     rdx, [rbp+57h+var_78]
0x14003c2d9  xor     rsi, rax
0x14003c2dc  mov     rcx, rbx
0x14003c2df  mov     [rbp+57h+var_80], rsi
0x14003c2e3  call    ??$find@X@?$_HashTable@_KU?$pair@$$CB_KVTieringResumeKey@@@utl@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@2@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@utl@@U?$pair@$$CB_KVTieringResumeKey@@@2@@1@AEB_K@Z; utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::find<void>(unsigned __int64 const &)
0x14003c2e8  inc     rdi
0x14003c2eb  mov     rcx, [rax]
0x14003c2ee  mov     [rbx+30h], rdi
0x14003c2f2  cmp     rcx, rbx
0x14003c2f5  jz      short loc_14003C300
0x14003c2f7  test    rdi, rdi
0x14003c2fa  jnz     short loc_14003C2C4
0x14003c2fc  xor     eax, eax
0x14003c2fe  jmp     short loc_14003C363
0x14003c300  xor     edx, edx; Val
0x14003c302  mov     [rbp+57h+var_80], rsi
0x14003c306  lea     rcx, [rbp+57h+var_68]; void *
0x14003c30a  lea     r8d, [rdx+40h]; Size
0x14003c30e  call    memset_0
0x14003c313  lea     r9, [rbp+57h+var_68]
0x14003c317  mov     [rbp+57h+var_28], 0
0x14003c31e  lea     r8, [rbp+57h+var_80]
0x14003c322  mov     rcx, rbx
0x14003c325  lea     rdx, [rbp+57h+var_78]
0x14003c329  call    ??$_TryEmplace@AEB_KVTieringResumeKey@@@?$_HashTable@_KU?$pair@$$CB_KVTieringResumeKey@@@utl@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@2@$0A@@utl@@IEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@utl@@U?$pair@$$CB_KVTieringResumeKey@@@2@@utl@@_N@1@AEB_K$$QEAVTieringResumeKey@@@Z; utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::_TryEmplace<unsigned __int64 const &,TieringResumeKey>(unsigned __int64 const &,TieringResumeKey &&)
0x14003c32e  test    [rbp+57h+var_68], 1
0x14003c332  jz      short loc_14003C348
0x14003c334  mov     rcx, [rbp+57h+hFindFile]; hFindFile
0x14003c338  lea     rax, [rcx-1]
0x14003c33c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003c340  ja      short loc_14003C348
0x14003c342  call    cs:__imp_FindClose
0x14003c348  cmp     [rbp+57h+var_70], 0
0x14003c34c  jnz     short loc_14003C354
0x14003c34e  dec     qword ptr [rbx+30h]
0x14003c352  jmp     short loc_14003C2FC
0x14003c354  mov     rax, [rbp+57h+var_80]
0x14003c358  mov     [r14], rax
0x14003c35b  mov     rax, [rbp+57h+var_78]
0x14003c35f  add     rax, 20h ; ' '
0x14003c363  mov     rcx, [rbp+57h+var_20]
0x14003c367  xor     rcx, rsp; StackCookie
0x14003c36a  call    __security_check_cookie
0x14003c36f  lea     r11, [rsp+0A0h+var_10]
0x14003c377  mov     rbx, [r11+30h]
0x14003c37b  mov     rsi, [r11+38h]
0x14003c37f  mov     rsp, r11
0x14003c382  pop     r14
0x14003c384  pop     rdi
0x14003c385  pop     rbp
0x14003c386  retn
```
