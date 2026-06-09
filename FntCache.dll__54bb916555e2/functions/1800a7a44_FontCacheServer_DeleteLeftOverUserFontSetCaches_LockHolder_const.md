# FontCacheServer::DeleteLeftOverUserFontSetCaches(LockHolder const &)

- ea: `0x1800a7a44`
- end: `0x1800a7c63`
- name: `?DeleteLeftOverUserFontSetCaches@FontCacheServer@@AEAAXAEBVLockHolder@@@Z`
- size: `543`
- prototype: `void __fastcall(FontCacheServer *__hidden this, const struct LockHolder *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1800a781c`

## callees

- `0x18000e920`
- `0x180028c50`
- `0x18002bcb8`
- `0x18002bd5c`
- `0x18002bf90`
- `0x180095fd8`
- `0x1800964cc`
- `0x180099b28`
- `0x18009b3b0`
- `0x1800a7a44`
- `0x1800aa650`
- `0x1800ab15c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a7c08`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a7c08`

## string_xrefs

- `0x1800a7b0e`: `FontCache-FontSet-`
- `0x1800a7a92`: `FontCache-FontSet-*.dat`

## pseudocode

```c
void __fastcall FontCacheServer::DeleteLeftOverUserFontSetCaches(FontCacheServer *this, const struct LockHolder *a2)
{
  __int64 v3; // rcx
  struct DWrite::RefString::Data *v4; // rdi
  unsigned __int64 v5; // rbx
  struct DWrite::RefString::Data *v6; // rax
  unsigned int HashCode; // eax
  __int64 v8; // rbx
  __int64 v9; // rcx
  struct DWrite::RefString::Data *v10; // rbx
  struct DWrite::RefString::Data *v11; // [rsp+20h] [rbp-E0h] BYREF
  struct DWrite::RefString::Data *v12; // [rsp+28h] [rbp-D8h] BYREF
  struct DWrite::RefString::Data *v13; // [rsp+30h] [rbp-D0h] BYREF
  struct DWrite::RefString::Data *v14; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v15[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v16[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h] BYREF
  char v18; // [rsp+88h] [rbp-78h]
  _WORD v19[4]; // [rsp+ACh] [rbp-54h] BYREF
  wchar_t Buf1[18]; // [rsp+B4h] [rbp-4Ch] BYREF
  wchar_t Src[260]; // [rsp+D8h] [rbp-28h] BYREF

  v3 = *(_QWORD *)FontCacheServer::GetCacheFolderPath((__int64)this, (__int64)&v11);
  v15[0] = v3 + 8;
  v15[1] = *(unsigned int *)(v3 + 4);
  v15[2] = L"FontCache-FontSet-*.dat";
  v15[3] = 23;
  DWrite::RefString::RefString(&v12, v15);
  DWrite::RefString::DecrementRef(v11);
  v4 = v12;
  FileEnumerator::FileEnumerator((FileEnumerator *)&v17, (const wchar_t *)v12 + 4);
  if ( v17 != -1 )
  {
    do
    {
      if ( (v18 & 0x10) == 0 )
      {
        v5 = -1;
        do
          ++v5;
        while ( Buf1[v5] );
        if ( v5 > 0x16 && !memcmp_0(Buf1, L"FontCache-FontSet-", 0x24u) && !memcmp_0(&v19[v5], L".dat", 8u) )
        {
          v6 = DWrite::RefString::NewData(Src, v5 - 22);
          v11 = v6;
        }
        else
        {
          v11 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
          v6 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
        }
        if ( *((_DWORD *)v6 + 1) )
        {
          HashCode = DWrite::RefString::GetHashCode((DWrite::RefString *)&v11);
          HashTable<DWrite::RefString,FontCacheServer::UserCacheReference>::Find(
            (char *)this + 304,
            v15,
            HashCode,
            &v11);
          if ( v15[0] == *((_QWORD *)this + 40) + 24LL * *((unsigned int *)this + 82) )
          {
            v8 = -1;
            do
              ++v8;
            while ( Buf1[v8] );
            v9 = *(_QWORD *)FontCacheServer::GetCacheFolderPath((__int64)this, (__int64)&v13);
            v16[0] = v9 + 8;
            v16[1] = *(unsigned int *)(v9 + 4);
            v16[2] = Buf1;
            v16[3] = v8;
            DWrite::RefString::RefString(&v14, v16);
            DWrite::RefString::DecrementRef(v13);
            v10 = v14;
            DeleteFileW((LPCWSTR)v14 + 4);
            DWrite::RefString::DecrementRef(v10);
          }
        }
        DWrite::RefString::DecrementRef(v11);
      }
    }
    while ( FileEnumerator::MoveNext((FileEnumerator *)&v17) );
  }
  FileEnumerator::~FileEnumerator((FileEnumerator *)&v17);
  DWrite::RefString::DecrementRef(v4);
}

```

## disassembly

```asm
0x1800a7a44  push    rbp
0x1800a7a46  push    rbx
0x1800a7a47  push    rsi
0x1800a7a48  push    rdi
0x1800a7a49  push    r14
0x1800a7a4b  push    r15
0x1800a7a4d  lea     rbp, [rsp-1F8h]
0x1800a7a55  sub     rsp, 2F8h
0x1800a7a5c  mov     rax, cs:__security_cookie
0x1800a7a63  xor     rax, rsp
0x1800a7a66  mov     [rbp+220h+var_40], rax
0x1800a7a6d  mov     rsi, rcx
0x1800a7a70  xor     r14d, r14d
0x1800a7a73  lea     rdx, [rsp+320h+var_300]
0x1800a7a78  call    ?GetCacheFolderPath@FontCacheServer@@QEBA?AVRefString@DWrite@@XZ; FontCacheServer::GetCacheFolderPath(void)
0x1800a7a7d  nop
0x1800a7a7e  mov     rcx, [rax]
0x1800a7a81  lea     rax, [rcx+8]
0x1800a7a85  mov     [rsp+320h+var_2E0], rax
0x1800a7a8a  mov     eax, [rcx+4]
0x1800a7a8d  mov     [rsp+320h+var_2D8], rax
0x1800a7a92  lea     rax, aFontcacheFonts_0; "FontCache-FontSet-*.dat"
0x1800a7a99  mov     [rsp+320h+var_2D0], rax
0x1800a7a9e  mov     [rsp+320h+var_2C8], 17h
0x1800a7aa7  lea     rdx, [rsp+320h+var_2E0]
0x1800a7aac  lea     rcx, [rsp+320h+var_2F8]
0x1800a7ab1  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x1800a7ab6  nop
0x1800a7ab7  mov     rcx, [rsp+320h+var_300]; struct DWrite::RefString::Data *
0x1800a7abc  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a7ac1  mov     rdi, [rsp+320h+var_2F8]
0x1800a7ac6  lea     rdx, [rdi+8]; wchar_t *
0x1800a7aca  lea     rcx, [rbp+220h+var_2A0]; this
0x1800a7ace  call    ??0FileEnumerator@@QEAA@PEB_W@Z; FileEnumerator::FileEnumerator(wchar_t const *)
0x1800a7ad3  nop
0x1800a7ad4  cmp     [rbp+220h+var_2A0], 0FFFFFFFFFFFFFFFFh
0x1800a7ad9  jz      loc_1800A7C32
0x1800a7adf  lea     r15, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x1800a7ae6  test    [rbp+220h+var_298], 10h
0x1800a7aea  jnz     loc_1800A7C21
0x1800a7af0  lea     rax, [rbp+220h+Buf1]
0x1800a7af4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a7af8  inc     rbx
0x1800a7afb  cmp     [rax+rbx*2], r14w
0x1800a7b00  jnz     short loc_1800A7AF8
0x1800a7b02  cmp     rbx, 16h
0x1800a7b06  jbe     short loc_1800A7B52
0x1800a7b08  mov     r8d, 24h ; '$'; Size
0x1800a7b0e  lea     rdx, aFontcacheFonts; "FontCache-FontSet-"
0x1800a7b15  lea     rcx, [rbp+220h+Buf1]; Buf1
0x1800a7b19  call    memcmp_0
0x1800a7b1e  test    eax, eax
0x1800a7b20  jnz     short loc_1800A7B52
0x1800a7b22  lea     rcx, [rbp+220h+var_274]
0x1800a7b26  lea     rcx, [rcx+rbx*2]; Buf1
0x1800a7b2a  lea     r8d, [rax+8]; Size
0x1800a7b2e  lea     rdx, aDat_1; ".dat"
0x1800a7b35  call    memcmp_0
0x1800a7b3a  test    eax, eax
0x1800a7b3c  jnz     short loc_1800A7B52
0x1800a7b3e  lea     rdx, [rbx-16h]; unsigned __int64
0x1800a7b42  lea     rcx, [rbp+220h+Src]; Src
0x1800a7b46  call    ?NewData@RefString@DWrite@@CAPEAUData@12@PEB_W_K@Z; DWrite::RefString::NewData(wchar_t const *,unsigned __int64)
0x1800a7b4b  mov     [rsp+320h+var_300], rax
0x1800a7b50  jmp     short loc_1800A7B5A
0x1800a7b52  mov     [rsp+320h+var_300], r15
0x1800a7b57  mov     rax, r15
0x1800a7b5a  cmp     [rax+4], r14d
0x1800a7b5e  jz      loc_1800A7C17
0x1800a7b64  lea     rcx, [rsp+320h+var_300]; this
0x1800a7b69  call    ?GetHashCode@RefString@DWrite@@QEBAIXZ; DWrite::RefString::GetHashCode(void)
0x1800a7b6e  mov     r8d, eax
0x1800a7b71  lea     rcx, [rsi+130h]
0x1800a7b78  lea     r9, [rsp+320h+var_300]
0x1800a7b7d  lea     rdx, [rsp+320h+var_2E0]
0x1800a7b82  call    ?Find@?$HashTable@VRefString@DWrite@@UUserCacheReference@FontCacheServer@@@@QEBA?AViterator@1@_KAEBVRefString@DWrite@@@Z; HashTable<DWrite::RefString,FontCacheServer::UserCacheReference>::Find(unsigned __int64,DWrite::RefString const &)
0x1800a7b87  mov     eax, [rsi+148h]
0x1800a7b8d  lea     rcx, [rax+rax*2]
0x1800a7b91  mov     rax, [rsi+140h]
0x1800a7b98  lea     rcx, [rax+rcx*8]
0x1800a7b9c  cmp     [rsp+320h+var_2E0], rcx
0x1800a7ba1  jnz     short loc_1800A7C17
0x1800a7ba3  lea     rax, [rbp+220h+Buf1]
0x1800a7ba7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a7bab  inc     rbx
0x1800a7bae  cmp     [rax+rbx*2], r14w
0x1800a7bb3  jnz     short loc_1800A7BAB
0x1800a7bb5  lea     rdx, [rsp+320h+var_2F0]
0x1800a7bba  mov     rcx, rsi
0x1800a7bbd  call    ?GetCacheFolderPath@FontCacheServer@@QEBA?AVRefString@DWrite@@XZ; FontCacheServer::GetCacheFolderPath(void)
0x1800a7bc2  nop
0x1800a7bc3  mov     rcx, [rax]
0x1800a7bc6  lea     rax, [rcx+8]
0x1800a7bca  mov     [rsp+320h+var_2C0], rax
0x1800a7bcf  mov     eax, [rcx+4]
0x1800a7bd2  mov     [rsp+320h+var_2B8], rax
0x1800a7bd7  lea     rax, [rbp+220h+Buf1]
0x1800a7bdb  mov     [rsp+320h+var_2B0], rax
0x1800a7be0  mov     [rsp+320h+var_2A8], rbx
0x1800a7be5  lea     rdx, [rsp+320h+var_2C0]
0x1800a7bea  lea     rcx, [rsp+320h+var_2E8]
0x1800a7bef  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x1800a7bf4  nop
0x1800a7bf5  mov     rcx, [rsp+320h+var_2F0]; struct DWrite::RefString::Data *
0x1800a7bfa  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a7bff  mov     rbx, [rsp+320h+var_2E8]
0x1800a7c04  lea     rcx, [rbx+8]; lpFileName
0x1800a7c08  call    cs:__imp_DeleteFileW
0x1800a7c0e  mov     rcx, rbx; struct DWrite::RefString::Data *
0x1800a7c11  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a7c16  nop
0x1800a7c17  mov     rcx, [rsp+320h+var_300]; struct DWrite::RefString::Data *
0x1800a7c1c  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a7c21  lea     rcx, [rbp+220h+var_2A0]; this
0x1800a7c25  call    ?MoveNext@FileEnumerator@@QEAA_NXZ; FileEnumerator::MoveNext(void)
0x1800a7c2a  test    al, al
0x1800a7c2c  jnz     loc_1800A7AE6
0x1800a7c32  lea     rcx, [rbp+220h+var_2A0]; this
0x1800a7c36  call    ??1FileEnumerator@@QEAA@XZ; FileEnumerator::~FileEnumerator(void)
0x1800a7c3b  nop
0x1800a7c3c  mov     rcx, rdi; struct DWrite::RefString::Data *
0x1800a7c3f  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a7c44  mov     rcx, [rbp+220h+var_40]
0x1800a7c4b  xor     rcx, rsp; StackCookie
0x1800a7c4e  call    __security_check_cookie
0x1800a7c53  add     rsp, 2F8h
0x1800a7c5a  pop     r15
0x1800a7c5c  pop     r14
0x1800a7c5e  pop     rdi
0x1800a7c5f  pop     rsi
0x1800a7c60  pop     rbx
0x1800a7c61  pop     rbp
0x1800a7c62  retn
```
