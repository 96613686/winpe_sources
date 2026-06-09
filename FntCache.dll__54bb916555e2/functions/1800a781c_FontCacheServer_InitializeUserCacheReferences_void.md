# FontCacheServer::InitializeUserCacheReferences(void)

- ea: `0x1800a781c`
- end: `0x1800a7a3c`
- name: `?InitializeUserCacheReferences@FontCacheServer@@AEAAXXZ`
- size: `544`
- prototype: `void __fastcall(FontCacheServer *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x1800a7190`

## callees

- `0x18000bc70`
- `0x18000e920`
- `0x180028c50`
- `0x18002bcb8`
- `0x18002bf90`
- `0x1800688d0`
- `0x180076ca4`
- `0x180095fd8`
- `0x1800964cc`
- `0x180099b28`
- `0x18009b3b0`
- `0x1800a781c`
- `0x1800a7a44`
- `0x1800a7c6c`
- `0x1800aa650`
- `0x1800aaa58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7a13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a7a13`

## string_xrefs

- `0x1800a7883`: `FontCache-S-*.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall FontCacheServer::InitializeUserCacheReferences(FontCacheServer *this)
{
  __int64 v2; // rcx
  struct DWrite::RefString::Data *v3; // rsi
  const struct LockHolder *v4; // rdx
  unsigned __int64 v5; // rdx
  struct DWrite::RefString::Data *v6; // rax
  struct DWrite::RefString::Data *v7; // rbx
  _OWORD *v8; // r15
  unsigned __int64 v9; // rcx
  _QWORD *i; // rdi
  unsigned int HashCode; // eax
  _QWORD *v12; // rax
  struct DWrite::RefString::Data *v13; // [rsp+20h] [rbp-E0h] BYREF
  struct DWrite::RefString::Data *v14; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v15; // [rsp+30h] [rbp-D0h]
  struct DWrite::RefString::Data *v16; // [rsp+38h] [rbp-C8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v18[5]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h] BYREF
  char v20; // [rsp+78h] [rbp-88h]
  unsigned __int64 v21; // [rsp+84h] [rbp-7Ch]
  wchar_t v22[10]; // [rsp+A4h] [rbp-5Ch]
  wchar_t Src[268]; // [rsp+B8h] [rbp-48h] BYREF

  LockHolder::LockHolder((LockHolder *)&lpCriticalSection, (FontCacheServer *)((char *)this + 264));
  v2 = *(_QWORD *)FontCacheServer::GetCacheFolderPath((__int64)this, (__int64)&v14);
  v18[0] = v2 + 8;
  v18[1] = *(unsigned int *)(v2 + 4);
  v18[2] = L"FontCache-S-*.dat";
  v18[3] = 17;
  DWrite::RefString::RefString(&v16, (__int64)v18);
  DWrite::RefString::DecrementRef(v14);
  v3 = v16;
  FileEnumerator::FileEnumerator((FileEnumerator *)&v19, (const wchar_t *)v16 + 4);
  if ( v19 != -1 )
  {
    do
    {
      if ( (v20 & 0x10) == 0 )
      {
        v5 = -1;
        do
          ++v5;
        while ( v22[v5] );
        if ( v5 < 0xE )
        {
          v7 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
          v13 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
          v6 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
        }
        else
        {
          v6 = DWrite::RefString::NewData(Src, v5 - 14);
          v7 = v6;
          v13 = v6;
        }
        if ( *((_DWORD *)v6 + 1) )
        {
          v15 = v21;
          v8 = operator new(0x30u);
          *v8 = 0;
          v8[1] = 0;
          v8[2] = 0;
          *((_QWORD *)v8 + 3) = &DWrite::RefString::empty_;
          v14 = (struct DWrite::RefString::Data *)v8;
          DWrite::RefString::operator=((char *)v8 + 24, &v13);
          v9 = v15;
          *((_QWORD *)v8 + 5) = v15;
          for ( i = (_QWORD *)*((_QWORD *)this + 46); (_QWORD *)((char *)this + 368) != i && v9 > i[5]; i = (_QWORD *)*i )
            ;
          HashCode = DWrite::RefString::GetHashCode((DWrite::RefString *)&v13);
          HashTableImpl::Add((char *)this + 304, v18, HashCode, v8);
          v14 = 0;
          v12 = (_QWORD *)i[1];
          *(_QWORD *)v8 = i;
          *((_QWORD *)v8 + 1) = v12;
          i[1] = v8;
          *v12 = v8;
          *((_BYTE *)v8 + 16) = 1;
          ScopedPtr<FontCacheServer::UserCacheReference>::~ScopedPtr<FontCacheServer::UserCacheReference>(&v14);
        }
        DWrite::RefString::DecrementRef(v7);
      }
    }
    while ( FileEnumerator::MoveNext((FileEnumerator *)&v19) );
    v3 = v16;
  }
  FontCacheServer::DeleteLeftOverUserFontSetCaches(this, v4);
  FileEnumerator::~FileEnumerator((FileEnumerator *)&v19);
  DWrite::RefString::DecrementRef(v3);
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800a781c  push    rbp
0x1800a781e  push    rbx
0x1800a781f  push    rsi
0x1800a7820  push    rdi
0x1800a7821  push    r12
0x1800a7823  push    r13
0x1800a7825  push    r14
0x1800a7827  push    r15
0x1800a7829  lea     rbp, [rsp-1E8h]
0x1800a7831  sub     rsp, 2E8h
0x1800a7838  mov     rax, cs:__security_cookie
0x1800a783f  xor     rax, rsp
0x1800a7842  mov     [rbp+220h+var_50], rax
0x1800a7849  mov     r13, rcx
0x1800a784c  xor     r12d, r12d
0x1800a784f  lea     rdx, [rcx+108h]; struct Lock *
0x1800a7856  lea     rcx, [rsp+320h+lpCriticalSection]; this
0x1800a785b  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x1800a7860  nop
0x1800a7861  lea     rdx, [rsp+320h+var_2F8]
0x1800a7866  mov     rcx, r13
0x1800a7869  call    ?GetCacheFolderPath@FontCacheServer@@QEBA?AVRefString@DWrite@@XZ; FontCacheServer::GetCacheFolderPath(void)
0x1800a786e  nop
0x1800a786f  mov     rcx, [rax]
0x1800a7872  lea     rax, [rcx+8]
0x1800a7876  mov     [rsp+320h+var_2D8], rax
0x1800a787b  mov     eax, [rcx+4]
0x1800a787e  mov     [rsp+320h+var_2D0], rax
0x1800a7883  lea     rax, aFontcacheSDat; "FontCache-S-*.dat"
0x1800a788a  mov     [rsp+320h+var_2C8], rax
0x1800a788f  mov     [rsp+320h+var_2C0], 11h
0x1800a7898  lea     rdx, [rsp+320h+var_2D8]
0x1800a789d  lea     rcx, [rsp+320h+var_2E8]
0x1800a78a2  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x1800a78a7  nop
0x1800a78a8  mov     rcx, [rsp+320h+var_2F8]; struct DWrite::RefString::Data *
0x1800a78ad  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a78b2  mov     rsi, [rsp+320h+var_2E8]
0x1800a78b7  lea     rdx, [rsi+8]; wchar_t *
0x1800a78bb  lea     rcx, [rsp+320h+var_2B0]; this
0x1800a78c0  call    ??0FileEnumerator@@QEAA@PEB_W@Z; FileEnumerator::FileEnumerator(wchar_t const *)
0x1800a78c5  nop
0x1800a78c6  cmp     [rsp+320h+var_2B0], 0FFFFFFFFFFFFFFFFh
0x1800a78cc  jz      loc_1800A79F1
0x1800a78d2  lea     rsi, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x1800a78d9  test    [rsp+320h+var_2A8], 10h
0x1800a78de  jnz     loc_1800A79DA
0x1800a78e4  lea     rax, [rbp+220h+var_27C]
0x1800a78e8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a78ec  inc     rdx
0x1800a78ef  cmp     [rax+rdx*2], r12w
0x1800a78f4  jnz     short loc_1800A78EC
0x1800a78f6  cmp     rdx, 0Eh
0x1800a78fa  jb      short loc_1800A7913
0x1800a78fc  add     rdx, 0FFFFFFFFFFFFFFF2h; unsigned __int64
0x1800a7900  lea     rcx, [rbp+220h+Src]; Src
0x1800a7904  call    ?NewData@RefString@DWrite@@CAPEAUData@12@PEB_W_K@Z; DWrite::RefString::NewData(wchar_t const *,unsigned __int64)
0x1800a7909  mov     rbx, rax
0x1800a790c  mov     [rsp+320h+var_300], rax
0x1800a7911  jmp     short loc_1800A791E
0x1800a7913  mov     rbx, rsi
0x1800a7916  mov     [rsp+320h+var_300], rbx
0x1800a791b  mov     rax, rsi
0x1800a791e  cmp     [rax+4], r12d
0x1800a7922  jz      loc_1800A79D2
0x1800a7928  mov     eax, dword ptr [rbp+220h+var_29C+4]
0x1800a792b  mov     dword ptr [rsp+320h+var_2F0+4], eax
0x1800a792f  mov     eax, dword ptr [rbp+220h+var_29C]
0x1800a7932  mov     dword ptr [rsp+320h+var_2F0], eax
0x1800a7936  mov     ecx, 30h ; '0'; Size
0x1800a793b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a7940  mov     r15, rax
0x1800a7943  xorps   xmm0, xmm0
0x1800a7946  movups  xmmword ptr [rax], xmm0
0x1800a7949  movups  xmmword ptr [rax+10h], xmm0
0x1800a794d  movups  xmmword ptr [rax+20h], xmm0
0x1800a7951  lea     rcx, [rax+18h]
0x1800a7955  mov     [rcx], rsi
0x1800a7958  mov     [rsp+320h+var_2F8], rax
0x1800a795d  lea     rdx, [rsp+320h+var_300]
0x1800a7962  call    ??4RefString@DWrite@@QEAAAEAV01@AEBV01@@Z; DWrite::RefString::operator=(DWrite::RefString const &)
0x1800a7967  mov     rcx, [rsp+320h+var_2F0]
0x1800a796c  mov     [r15+28h], rcx
0x1800a7970  lea     rax, [r13+170h]
0x1800a7977  mov     rdi, [rax]
0x1800a797a  cmp     rax, rdi
0x1800a797d  jz      short loc_1800A798A
0x1800a797f  cmp     rcx, [rdi+28h]
0x1800a7983  jbe     short loc_1800A798A
0x1800a7985  mov     rdi, [rdi]
0x1800a7988  jmp     short loc_1800A797A
0x1800a798a  lea     rcx, [rsp+320h+var_300]; this
0x1800a798f  call    ?GetHashCode@RefString@DWrite@@QEBAIXZ; DWrite::RefString::GetHashCode(void)
0x1800a7994  mov     r8d, eax
0x1800a7997  mov     r9, r15
0x1800a799a  lea     rdx, [rsp+320h+var_2D8]
0x1800a799f  lea     rcx, [r13+130h]
0x1800a79a6  call    ?Add@HashTableImpl@@QEAA?AViterator@1@_KPEAX@Z; HashTableImpl::Add(unsigned __int64,void *)
0x1800a79ab  mov     [rsp+320h+var_2F8], r12
0x1800a79b0  mov     rax, [rdi+8]
0x1800a79b4  mov     [r15], rdi
0x1800a79b7  mov     [r15+8], rax
0x1800a79bb  mov     [rdi+8], r15
0x1800a79bf  mov     [rax], r15
0x1800a79c2  mov     byte ptr [r15+10h], 1
0x1800a79c7  lea     rcx, [rsp+320h+var_2F8]
0x1800a79cc  call    ??1?$ScopedPtr@UUserCacheReference@FontCacheServer@@@@QEAA@XZ; ScopedPtr<FontCacheServer::UserCacheReference>::~ScopedPtr<FontCacheServer::UserCacheReference>(void)
0x1800a79d1  nop
0x1800a79d2  mov     rcx, rbx; struct DWrite::RefString::Data *
0x1800a79d5  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a79da  lea     rcx, [rsp+320h+var_2B0]; this
0x1800a79df  call    ?MoveNext@FileEnumerator@@QEAA_NXZ; FileEnumerator::MoveNext(void)
0x1800a79e4  test    al, al
0x1800a79e6  jnz     loc_1800A78D9
0x1800a79ec  mov     rsi, [rsp+320h+var_2E8]
0x1800a79f1  mov     rcx, r13; this
0x1800a79f4  call    ?DeleteLeftOverUserFontSetCaches@FontCacheServer@@AEAAXAEBVLockHolder@@@Z; FontCacheServer::DeleteLeftOverUserFontSetCaches(LockHolder const &)
0x1800a79f9  nop
0x1800a79fa  lea     rcx, [rsp+320h+var_2B0]; this
0x1800a79ff  call    ??1FileEnumerator@@QEAA@XZ; FileEnumerator::~FileEnumerator(void)
0x1800a7a04  nop
0x1800a7a05  mov     rcx, rsi; struct DWrite::RefString::Data *
0x1800a7a08  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800a7a0d  nop
0x1800a7a0e  mov     rcx, [rsp+320h+lpCriticalSection]; lpCriticalSection
0x1800a7a13  call    cs:__imp_LeaveCriticalSection
0x1800a7a19  mov     rcx, [rbp+220h+var_50]
0x1800a7a20  xor     rcx, rsp; StackCookie
0x1800a7a23  call    __security_check_cookie
0x1800a7a28  add     rsp, 2E8h
0x1800a7a2f  pop     r15
0x1800a7a31  pop     r14
0x1800a7a33  pop     r13
0x1800a7a35  pop     r12
0x1800a7a37  pop     rdi
0x1800a7a38  pop     rsi
0x1800a7a39  pop     rbx
0x1800a7a3a  pop     rbp
0x1800a7a3b  retn
```
