# CPubCacheBackingStore::OpenPersistedPublication(ushort const *,TnoHash *,TnoHash *,void * *,unsigned __int64 *)

- ea: `0x18005b100`
- end: `0x18005b424`
- name: `?OpenPersistedPublication@CPubCacheBackingStore@@AEAAKPEBGPEAVTnoHash@@1PEAPEAXPEA_K@Z`
- size: `804`
- prototype: `unsigned int(CPubCacheBackingStore *__hidden this, const unsigned __int16 *, struct TnoHash *, struct TnoHash *, void **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180053014`

## callees

- `0x180008290`
- `0x18000cf48`
- `0x18000ecf4`
- `0x180018efc`
- `0x180018f48`
- `0x180052eb8`
- `0x180055370`
- `0x18005b100`
- `0x180087a40`
- `0x1801386e4`
- `0x180138cb4`
- `0x1801390d8`
- `0x18013937c`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b297`
- `KERNEL32!CreateFileW` at `0x18005b288`
- `KERNEL32!CreateFileW` at `0x18005b288`

## pseudocode

```c
__int64 __fastcall CPubCacheBackingStore::OpenPersistedPublication(
        CPubCacheBackingStore *this,
        unsigned __int16 *a2,
        struct TnoHash *a3,
        struct TnoHash *a4,
        void **a5,
        unsigned __int64 *a6)
{
  unsigned int NameHash; // ebx
  CHostedCacheMsgEncoding *v10; // rax
  __int64 v11; // rdx
  HANDLE FileW; // rdi
  CPubCacheFileName *v14; // [rsp+40h] [rbp-79h] BYREF
  int v15; // [rsp+48h] [rbp-71h] BYREF
  int v16; // [rsp+4Ch] [rbp-6Dh] BYREF
  __int64 v17; // [rsp+50h] [rbp-69h] BYREF
  void **v18; // [rsp+58h] [rbp-61h] BYREF
  HANDLE v19; // [rsp+60h] [rbp-59h]
  unsigned __int64 v20; // [rsp+68h] [rbp-51h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v22; // [rsp+80h] [rbp-39h]
  void **v23; // [rsp+88h] [rbp-31h] BYREF
  int v24; // [rsp+90h] [rbp-29h]
  __int64 v25; // [rsp+98h] [rbp-21h]
  char v26; // [rsp+A0h] [rbp-19h]
  void **v27; // [rsp+A8h] [rbp-11h] BYREF
  int v28; // [rsp+B0h] [rbp-9h]
  __int64 v29; // [rsp+B8h] [rbp-1h]
  char v30; // [rsp+C0h] [rbp+7h]

  *(_OWORD *)lpFileName = 0;
  v22 = 0;
  v14 = 0;
  v18 = &ObjectHandle::`vftable';
  v19 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 1;
  v27 = &TnoHash::`vftable';
  v24 = 0;
  v25 = 0;
  v26 = 1;
  v23 = &TnoHash::`vftable';
  v17 = 0;
  v16 = 0;
  v15 = 0;
  v20 = 0;
  NameHash = CPubCacheFileName::Create(a2);
  if ( NameHash )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v11 = 306;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v10 + 12), v11, WPP_817cd87503153d87380e6127cb13644a_Traceguids, NameHash);
    }
  }
  else
  {
    NameHash = CPubCacheFileName::GetNameHash(v14, (struct TnoHash *)&v27);
    if ( NameHash )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v11 = 307;
        goto LABEL_6;
      }
    }
    else
    {
      NameHash = CPubCacheBackingStore::ConstructPublicationFilePaths((__int64)this, &v14, (void **)lpFileName);
      if ( NameHash )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v11 = 308;
          goto LABEL_6;
        }
      }
      else
      {
        FileW = CreateFileW(lpFileName[0], 0x80000000, 5u, 0, 3u, 0, 0);
        if ( FileW == (HANDLE)-1LL )
        {
          NameHash = GetLastError();
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              309,
              (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
              lpFileName[0],
              NameHash);
          }
        }
        else
        {
          ObjectHandle::Close((ObjectHandle *)&v18);
          v19 = FileW;
          NameHash = ICachePublicationFileHelper::Create(FileW, &v17);
          if ( NameHash )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v11 = 310;
              goto LABEL_6;
            }
          }
          else
          {
            NameHash = (*(__int64 (__fastcall **)(__int64, void ***, int *, int *, _QWORD, unsigned __int64 *))(*(_QWORD *)v17 + 56LL))(
                         v17,
                         &v23,
                         &v16,
                         &v15,
                         0,
                         &v20);
            if ( !NameHash )
            {
              TnoBaseHash::operator=(a3, &v27);
              TnoBaseHash::operator=(a4, &v23);
              v19 = 0;
              *a5 = FileW;
              *a6 = v20;
              goto LABEL_33;
            }
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v11 = 311;
              goto LABEL_6;
            }
          }
        }
      }
    }
  }
LABEL_33:
  SmartPointer<CRepubJetSessionContext>::Release(&v17);
  v23 = &TnoHash::`vftable';
  TnoBaseHash::ReleaseHash((TnoBaseHash *)&v23);
  v27 = &TnoHash::`vftable';
  TnoBaseHash::ReleaseHash((TnoBaseHash *)&v27);
  v18 = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((ObjectHandle *)&v18);
  SmartPointer<CRepubJetSessionContext>::Release(&v14);
  _PublicationCacheFilePaths::~_PublicationCacheFilePaths((void **)lpFileName);
  return NameHash;
}

```

## disassembly

```asm
0x18005b100  push    rbp
0x18005b102  push    rbx
0x18005b103  push    rsi
0x18005b104  push    rdi
0x18005b105  push    r13
0x18005b107  push    r14
0x18005b109  push    r15
0x18005b10b  lea     rbp, [rsp-17h]
0x18005b110  sub     rsp, 0D0h
0x18005b117  mov     rsi, r9
0x18005b11a  mov     r14, r8
0x18005b11d  mov     rax, rdx
0x18005b120  mov     rdi, rcx
0x18005b123  xorps   xmm0, xmm0
0x18005b126  movdqu  xmmword ptr [rbp+47h+lpFileName], xmm0
0x18005b12b  xor     r15d, r15d
0x18005b12e  mov     [rbp+47h+var_80], r15
0x18005b132  mov     [rbp+47h+var_C0], r15
0x18005b136  lea     r13, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18005b13d  mov     [rbp+47h+var_A8], r13
0x18005b141  mov     [rbp+47h+var_A0], r15
0x18005b145  mov     [rbp+47h+var_50], r15d
0x18005b149  mov     [rbp+47h+var_48], r15
0x18005b14d  mov     [rbp+47h+var_40], 1
0x18005b151  lea     rcx, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x18005b158  mov     [rbp+47h+var_58], rcx
0x18005b15c  mov     [rbp+47h+var_70], r15d
0x18005b160  mov     [rbp+47h+var_68], r15
0x18005b164  mov     [rbp+47h+var_60], 1
0x18005b168  mov     [rbp+47h+var_78], rcx
0x18005b16c  mov     [rbp+47h+var_B0], r15
0x18005b170  mov     [rbp+47h+var_B4], r15d
0x18005b174  mov     [rbp+47h+var_B8], r15d
0x18005b178  mov     [rbp+47h+var_98], r15
0x18005b17c  lea     rdx, [rbp+47h+var_C0]
0x18005b180  mov     rcx, rax; unsigned __int16 *
0x18005b183  call    ?Create@CPubCacheFileName@@SAKPEBGPEAV?$SmartPointer@VCPubCacheFileName@@@@@Z; CPubCacheFileName::Create(ushort const *,SmartPointer<CPubCacheFileName> *)
0x18005b188  mov     ebx, eax
0x18005b18a  test    eax, eax
0x18005b18c  jz      short loc_18005B1D6
0x18005b18e  lea     rcx, WPP_GLOBAL_Control
0x18005b195  mov     rax, cs:WPP_GLOBAL_Control
0x18005b19c  cmp     rax, rcx
0x18005b19f  jz      loc_18005B3C7
0x18005b1a5  test    byte ptr [rax+6Ch], 4
0x18005b1a9  jz      loc_18005B3C7
0x18005b1af  cmp     byte ptr [rax+69h], 1
0x18005b1b3  jb      loc_18005B3C7
0x18005b1b9  mov     edx, 132h
0x18005b1be  mov     r9d, ebx
0x18005b1c1  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005b1c8  mov     rcx, [rax+60h]
0x18005b1cc  call    WPP_SF_d
0x18005b1d1  jmp     loc_18005B3C7
0x18005b1d6  lea     rdx, [rbp+47h+var_58]; struct TnoHash *
0x18005b1da  mov     rcx, [rbp+47h+var_C0]; this
0x18005b1de  call    ?GetNameHash@CPubCacheFileName@@QEAAKAEAVTnoHash@@@Z; CPubCacheFileName::GetNameHash(TnoHash &)
0x18005b1e3  mov     ebx, eax
0x18005b1e5  test    eax, eax
0x18005b1e7  jz      short loc_18005B21B
0x18005b1e9  lea     rcx, WPP_GLOBAL_Control
0x18005b1f0  mov     rax, cs:WPP_GLOBAL_Control
0x18005b1f7  cmp     rax, rcx
0x18005b1fa  jz      loc_18005B3C7
0x18005b200  test    byte ptr [rax+6Ch], 4
0x18005b204  jz      loc_18005B3C7
0x18005b20a  cmp     byte ptr [rax+69h], 1
0x18005b20e  jb      loc_18005B3C7
0x18005b214  mov     edx, 133h
0x18005b219  jmp     short loc_18005B1BE
0x18005b21b  lea     r8, [rbp+47h+lpFileName]
0x18005b21f  lea     rdx, [rbp+47h+var_C0]
0x18005b223  mov     rcx, rdi
0x18005b226  call    ?ConstructPublicationFilePaths@CPubCacheBackingStore@@QEAAKAEBV?$SmartPointer@VCPubCacheFileName@@@@AEAU_PublicationCacheFilePaths@@@Z; CPubCacheBackingStore::ConstructPublicationFilePaths(SmartPointer<CPubCacheFileName> const &,_PublicationCacheFilePaths &)
0x18005b22b  mov     ebx, eax
0x18005b22d  test    eax, eax
0x18005b22f  jz      short loc_18005B266
0x18005b231  lea     rcx, WPP_GLOBAL_Control
0x18005b238  mov     rax, cs:WPP_GLOBAL_Control
0x18005b23f  cmp     rax, rcx
0x18005b242  jz      loc_18005B3C7
0x18005b248  test    byte ptr [rax+6Ch], 4
0x18005b24c  jz      loc_18005B3C7
0x18005b252  cmp     byte ptr [rax+69h], 1
0x18005b256  jb      loc_18005B3C7
0x18005b25c  mov     edx, 134h
0x18005b261  jmp     loc_18005B1BE
0x18005b266  mov     [rsp+100h+hTemplateFile], r15; hTemplateFile
0x18005b26b  mov     [rsp+100h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18005b270  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x18005b278  xor     r9d, r9d; lpSecurityAttributes
0x18005b27b  mov     edx, 80000000h; dwDesiredAccess
0x18005b280  lea     r8d, [r9+5]; dwShareMode
0x18005b284  mov     rcx, [rbp+47h+lpFileName]; lpFileName
0x18005b288  call    cs:__imp_CreateFileW
0x18005b28e  mov     rdi, rax
0x18005b291  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b295  jnz     short loc_18005B2EC
0x18005b297  call    cs:__imp_GetLastError
0x18005b29d  mov     ebx, eax
0x18005b29f  lea     rcx, WPP_GLOBAL_Control
0x18005b2a6  mov     rax, cs:WPP_GLOBAL_Control
0x18005b2ad  cmp     rax, rcx
0x18005b2b0  jz      loc_18005B3C7
0x18005b2b6  test    byte ptr [rax+6Ch], 4
0x18005b2ba  jz      loc_18005B3C7
0x18005b2c0  cmp     byte ptr [rax+69h], 1
0x18005b2c4  jb      loc_18005B3C7
0x18005b2ca  mov     edx, 135h
0x18005b2cf  mov     [rsp+100h+dwCreationDisposition], ebx
0x18005b2d3  mov     r9, [rbp+47h+lpFileName]
0x18005b2d7  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005b2de  mov     rcx, [rax+60h]
0x18005b2e2  call    WPP_SF_Sd
0x18005b2e7  jmp     loc_18005B3C7
0x18005b2ec  lea     rcx, [rbp+47h+var_A8]; this
0x18005b2f0  call    ?Close@ObjectHandle@@QEAAXXZ; ObjectHandle::Close(void)
0x18005b2f5  mov     [rbp+47h+var_A0], rdi
0x18005b2f9  lea     rdx, [rbp+47h+var_B0]
0x18005b2fd  mov     rcx, rdi
0x18005b300  call    ?Create@ICachePublicationFileHelper@@SAKPEAXPEAV?$SmartPointer@VICachePublicationFileHelper@@@@@Z; ICachePublicationFileHelper::Create(void *,SmartPointer<ICachePublicationFileHelper> *)
0x18005b305  mov     ebx, eax
0x18005b307  test    eax, eax
0x18005b309  jz      short loc_18005B340
0x18005b30b  lea     rcx, WPP_GLOBAL_Control
0x18005b312  mov     rax, cs:WPP_GLOBAL_Control
0x18005b319  cmp     rax, rcx
0x18005b31c  jz      loc_18005B3C7
0x18005b322  test    byte ptr [rax+6Ch], 4
0x18005b326  jz      loc_18005B3C7
0x18005b32c  cmp     byte ptr [rax+69h], 1
0x18005b330  jb      loc_18005B3C7
0x18005b336  mov     edx, 136h
0x18005b33b  jmp     loc_18005B1BE
0x18005b340  mov     rcx, [rbp+47h+var_B0]
0x18005b344  mov     rax, [rcx]
0x18005b347  lea     rdx, [rbp+47h+var_98]
0x18005b34b  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rdx
0x18005b350  mov     qword ptr [rsp+100h+dwCreationDisposition], r15
0x18005b355  lea     r9, [rbp+47h+var_B8]
0x18005b359  lea     r8, [rbp+47h+var_B4]
0x18005b35d  lea     rdx, [rbp+47h+var_78]
0x18005b361  mov     rax, [rax+38h]
0x18005b365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b36a  mov     ebx, eax
0x18005b36c  test    eax, eax
0x18005b36e  jz      short loc_18005B399
0x18005b370  lea     rcx, WPP_GLOBAL_Control
0x18005b377  mov     rax, cs:WPP_GLOBAL_Control
0x18005b37e  cmp     rax, rcx
0x18005b381  jz      short loc_18005B3C7
0x18005b383  test    byte ptr [rax+6Ch], 4
0x18005b387  jz      short loc_18005B3C7
0x18005b389  cmp     byte ptr [rax+69h], 1
0x18005b38d  jb      short loc_18005B3C7
0x18005b38f  mov     edx, 137h
0x18005b394  jmp     loc_18005B1BE
0x18005b399  lea     rdx, [rbp+47h+var_58]
0x18005b39d  mov     rcx, r14
0x18005b3a0  call    ??4TnoBaseHash@@QEAAAEAV0@AEBV0@@Z; TnoBaseHash::operator=(TnoBaseHash const &)
0x18005b3a5  lea     rdx, [rbp+47h+var_78]
0x18005b3a9  mov     rcx, rsi
0x18005b3ac  call    ??4TnoBaseHash@@QEAAAEAV0@AEBV0@@Z; TnoBaseHash::operator=(TnoBaseHash const &)
0x18005b3b1  mov     [rbp+47h+var_A0], r15
0x18005b3b5  mov     rax, [rbp+47h+arg_20]
0x18005b3b9  mov     [rax], rdi
0x18005b3bc  mov     rcx, [rbp+47h+var_98]
0x18005b3c0  mov     rax, [rbp+47h+arg_28]
0x18005b3c4  mov     [rax], rcx
0x18005b3c7  lea     rcx, [rbp+47h+var_B0]
0x18005b3cb  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18005b3d0  lea     rdi, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x18005b3d7  mov     [rbp+47h+var_78], rdi
0x18005b3db  lea     rcx, [rbp+47h+var_78]; this
0x18005b3df  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x18005b3e4  mov     [rbp+47h+var_58], rdi
0x18005b3e8  lea     rcx, [rbp+47h+var_58]; this
0x18005b3ec  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x18005b3f1  mov     [rbp+47h+var_A8], r13
0x18005b3f5  lea     rcx, [rbp+47h+var_A8]; this
0x18005b3f9  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x18005b3fe  lea     rcx, [rbp+47h+var_C0]
0x18005b402  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18005b407  lea     rcx, [rbp+47h+lpFileName]; this
0x18005b40b  call    ??1_PublicationCacheFilePaths@@QEAA@XZ; _PublicationCacheFilePaths::~_PublicationCacheFilePaths(void)
0x18005b410  mov     eax, ebx
0x18005b412  add     rsp, 0D0h
0x18005b419  pop     r15
0x18005b41b  pop     r14
0x18005b41d  pop     r13
0x18005b41f  pop     rdi
0x18005b420  pop     rsi
0x18005b421  pop     rbx
0x18005b422  pop     rbp
0x18005b423  retn
```
