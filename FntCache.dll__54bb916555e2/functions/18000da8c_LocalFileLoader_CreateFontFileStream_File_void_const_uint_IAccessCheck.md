# LocalFileLoader::CreateFontFileStream(File &&,void const *,uint,IAccessCheck *)

- ea: `0x18000da8c`
- end: `0x18000dd08`
- name: `?CreateFontFileStream@LocalFileLoader@@CA?AV?$ComPtr@UIDWriteFontFileStreamInternal@@@@$$QEAVFile@@PEBXIPEAVIAccessCheck@@@Z`
- size: `636`
- prototype: `struct DWrite::RefString **__fastcall(struct DWrite::RefString **, _QWORD *, const void *, unsigned int, struct IAccessCheck *)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d9d0`
- `0x18006bedc`
- `0x1800a2a40`
- `0x1800a596c`

## callees

- `0x18000da8c`
- `0x18000dd10`
- `0x18000ddac`
- `0x18000de84`
- `0x18000df40`
- `0x18000e0ac`
- `0x18000e334`
- `0x18000e3d0`
- `0x18000efac`
- `0x18000f034`
- `0x1800213d8`
- `0x180028c50`
- `0x18002b670`
- `0x1800aaa58`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000db2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000db2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dafd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dc15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dafd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dc15`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000db1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000db1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct DWrite::RefString **__fastcall LocalFileLoader::CreateFontFileStream(
        struct DWrite::RefString **a1,
        _QWORD *a2,
        const void *a3,
        unsigned int a4,
        struct IAccessCheck *a5)
{
  unsigned int v9; // edi
  struct LocalFileLoader::BucketList near **v10; // r13
  DWORD TickCount; // eax
  LocalFileLoader::FreeList *v12; // rcx
  struct DWrite::RefString *v13; // rbx
  struct DWrite::RefString::Data *v14; // rbx
  int v15; // eax
  int v16; // edi
  void *v17; // rax
  struct DWrite::RefString *v18; // rcx
  struct LocalFileLoader::BucketList near *v19; // r8
  __int64 v20; // rdx
  _QWORD *v21; // rax
  LocalFileLoader::FontFileStream *v22; // rdi
  unsigned int v23; // edx
  struct DWrite::RefString *v25; // [rsp+30h] [rbp-41h] BYREF
  struct DWrite::RefString::Data *v26; // [rsp+38h] [rbp-39h] BYREF
  struct DWrite::RefString::Data *v27; // [rsp+40h] [rbp-31h] BYREF
  int v28; // [rsp+48h] [rbp-29h]
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+50h] [rbp-21h]
  int v30; // [rsp+58h] [rbp-19h] BYREF
  struct DWrite::RefString::Data *v31; // [rsp+60h] [rbp-11h]
  int v32; // [rsp+68h] [rbp-9h]
  void *v33; // [rsp+70h] [rbp-1h]
  struct DWrite::RefString::Data **v34; // [rsp+78h] [rbp+7h]
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+80h] [rbp+Fh]
  unsigned int v36; // [rsp+E8h] [rbp+77h]

  v28 = 0;
  v25 = 0;
  v9 = HashBlob(a3, a4, 0);
  v36 = v9;
  v10 = &LocalFileLoader::g_buckets + 3 * (v9 & 0xF);
  v29 = &g_localFileLoaderLock;
  EnterCriticalSection(&g_localFileLoaderLock);
  LocalFileLoader::BucketList::Find(v10, v9, a3, a4, &v25);
  TickCount = GetTickCount();
  LocalFileLoader::FreeList::Cleanup(v12, TickCount);
  LeaveCriticalSection(&g_localFileLoaderLock);
  v13 = v25;
  if ( !v25 )
  {
    v27 = 0;
    v26 = (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
    LocalFileLoader::DeserializeReferenceKeyFrom(a3, a4, (struct DWrite::RefString *)&v26, (struct DateTime *)&v27, 0);
    v14 = v27;
    if ( !*a2 )
    {
      v15 = LocalFileLoader::OpenFontFile(a3, a4, &v26, v27, a2);
      v16 = v15;
      if ( v15 < 0 )
      {
        v30 = v15;
        CaptureStack(v15, v15);
        v31 = v26;
        _InterlockedIncrement((volatile signed __int32 *)v26);
        v32 = v16;
        LogAndThrow<IOException>(&v30, 0x72646C6C636CLL, 559);
      }
      v9 = v36;
    }
    v17 = operator new(0xD0u);
    v33 = v17;
    v34 = &v27;
    v27 = v26;
    _InterlockedIncrement((volatile signed __int32 *)v26);
    v13 = (struct DWrite::RefString *)LocalFileLoader::FontFileStream::FontFileStream(v17, v9, a2, &v27, v14);
    v29 = (struct _RTL_CRITICAL_SECTION *)v13;
    v35 = &g_localFileLoaderLock;
    EnterCriticalSection(&g_localFileLoaderLock);
    if ( (unsigned __int8)LocalFileLoader::BucketList::Find(v10, v9, a3, a4, &v25) )
    {
      v22 = v13;
      v13 = v25;
    }
    else
    {
      LocalFileLoader::FontFileStream::AddRefAndActivate(v13);
      v29 = 0;
      v18 = v25;
      v25 = v13;
      if ( v18 )
        (*(void (__fastcall **)(struct DWrite::RefString *))(*(_QWORD *)v18 + 16LL))(v18);
      v19 = *v10;
      v20 = ((unsigned __int64)v13 + 40) & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64);
      v21 = (_QWORD *)*((_QWORD *)*v10 + 1);
      *(_QWORD *)v20 = *v10;
      *(_QWORD *)(v20 + 8) = v21;
      *((_QWORD *)v19 + 1) = v20;
      *v21 = v20;
      *(_BYTE *)(v20 + 16) = 1;
      v22 = 0;
    }
    LeaveCriticalSection(&g_localFileLoaderLock);
    if ( v22 )
      LocalFileLoader::FontFileStream::`scalar deleting destructor'(v22, v23);
    DWrite::RefString::DecrementRef(v26);
  }
  if ( a5 )
    LocalFileLoader::FontFileStream::CheckReadAccess(v13, a5);
  v25 = 0;
  *a1 = v13;
  v28 = 1;
  return a1;
}

```

## disassembly

```asm
0x18000da8c  mov     [rsp-8+arg_8], rbx
0x18000da91  mov     [rsp-8+arg_0], rcx
0x18000da96  push    rbp
0x18000da97  push    rsi
0x18000da98  push    rdi
0x18000da99  push    r12
0x18000da9b  push    r13
0x18000da9d  push    r14
0x18000da9f  push    r15
0x18000daa1  lea     rbp, [rsp-1Fh]
0x18000daa6  sub     rsp, 90h
0x18000daad  mov     esi, r9d
0x18000dab0  mov     r14, r8
0x18000dab3  mov     r12, rdx
0x18000dab6  mov     r15, rcx
0x18000dab9  mov     [rbp+4Fh+var_78], 0
0x18000dac0  mov     [rbp+4Fh+var_90], 0
0x18000dac8  mov     edx, r9d; unsigned __int64
0x18000dacb  xor     r8d, r8d; unsigned int
0x18000dace  mov     rcx, r14; void *
0x18000dad1  call    ?HashBlob@@YAIPEBX_KI@Z; HashBlob(void const *,unsigned __int64,uint)
0x18000dad6  mov     edi, eax
0x18000dad8  mov     [rbp+4Fh+arg_18], eax
0x18000dadb  mov     edx, eax
0x18000dadd  and     edx, 0Fh
0x18000dae0  lea     rcx, [rdx+rdx*2]
0x18000dae4  lea     rax, ?g_buckets@LocalFileLoader@@0PAVBucketList@1@A; LocalFileLoader::BucketList near * LocalFileLoader::g_buckets
0x18000daeb  lea     r13, [rax+rcx*8]
0x18000daef  lea     rbx, ?g_localFileLoaderLock@@3VLock@@A; Lock g_localFileLoaderLock
0x18000daf6  mov     [rbp+4Fh+var_70], rbx
0x18000dafa  mov     rcx, rbx; lpCriticalSection
0x18000dafd  call    cs:__imp_EnterCriticalSection
0x18000db03  nop
0x18000db04  lea     rax, [rbp+4Fh+var_90]
0x18000db08  mov     [rsp+0C0h+var_A0], rax
0x18000db0d  mov     r9d, esi
0x18000db10  mov     r8, r14
0x18000db13  mov     edx, edi
0x18000db15  mov     rcx, r13
0x18000db18  call    ?Find@BucketList@LocalFileLoader@@QEBA_NIPEBXIAEAV?$ComPtr@VFontFileStream@LocalFileLoader@@@@@Z; LocalFileLoader::BucketList::Find(uint,void const *,uint,ComPtr<LocalFileLoader::FontFileStream> &)
0x18000db1d  call    cs:__imp_GetTickCount
0x18000db23  mov     edx, eax; unsigned int
0x18000db25  call    ?Cleanup@FreeList@LocalFileLoader@@QEAAII@Z; LocalFileLoader::FreeList::Cleanup(uint)
0x18000db2a  nop
0x18000db2b  mov     rcx, rbx; lpCriticalSection
0x18000db2e  call    cs:__imp_LeaveCriticalSection
0x18000db34  nop
0x18000db35  mov     rbx, [rbp+4Fh+var_90]
0x18000db39  test    rbx, rbx
0x18000db3c  jnz     loc_18000DCA2
0x18000db42  mov     [rbp+4Fh+var_80], rbx
0x18000db46  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x18000db4d  mov     [rbp+4Fh+var_88], rax
0x18000db51  mov     [rsp+0C0h+var_A0], rbx; struct DWrite::RefString *
0x18000db56  lea     r9, [rbp+4Fh+var_80]; struct DateTime *
0x18000db5a  lea     r8, [rbp+4Fh+var_88]; struct DWrite::RefString *
0x18000db5e  mov     edx, esi; unsigned int
0x18000db60  mov     rcx, r14; void *
0x18000db63  call    ?DeserializeReferenceKeyFrom@LocalFileLoader@@SAXPEBXIPEAVRefString@DWrite@@PEAVDateTime@@1@Z; LocalFileLoader::DeserializeReferenceKeyFrom(void const *,uint,DWrite::RefString *,DateTime *,DWrite::RefString *)
0x18000db68  mov     rbx, [rbp+4Fh+var_80]
0x18000db6c  cmp     qword ptr [r12], 0
0x18000db71  jnz     short loc_18000DBC9
0x18000db73  mov     [rsp+0C0h+var_A0], r12
0x18000db78  mov     r9, rbx
0x18000db7b  lea     r8, [rbp+4Fh+var_88]
0x18000db7f  mov     edx, esi
0x18000db81  mov     rcx, r14
0x18000db84  call    ?OpenFontFile@LocalFileLoader@@SAJPEBXIAEBVRefString@DWrite@@VDateTime@@AEAVFile@@@Z; LocalFileLoader::OpenFontFile(void const *,uint,DWrite::RefString const &,DateTime,File &)
0x18000db89  mov     edi, eax
0x18000db8b  test    eax, eax
0x18000db8d  jns     short loc_18000DBC6
0x18000db8f  mov     rbx, 72646C6C636Ch
0x18000db99  mov     [rbp+4Fh+var_68], eax
0x18000db9c  mov     edx, eax; unsigned int
0x18000db9e  mov     ecx, eax; int
0x18000dba0  call    ?CaptureStack@@YAXJI@Z; CaptureStack(long,uint)
0x18000dba5  mov     rcx, [rbp+4Fh+var_88]
0x18000dba9  mov     [rbp+4Fh+var_60], rcx
0x18000dbad  lock inc dword ptr [rcx]
0x18000dbb0  mov     [rbp+4Fh+var_58], edi
0x18000dbb3  mov     r8d, 22Fh
0x18000dbb9  mov     rdx, rbx
0x18000dbbc  lea     rcx, [rbp+4Fh+var_68]
0x18000dbc0  call    ??$LogAndThrow@VIOException@@@@YAXAEBVIOException@@VEventTag@@I@Z; LogAndThrow<IOException>(IOException const &,EventTag,uint)
0x18000dbc6  mov     edi, [rbp+4Fh+arg_18]
0x18000dbc9  mov     ecx, 0D0h; Size
0x18000dbce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dbd3  mov     [rbp+4Fh+var_50], rax
0x18000dbd7  lea     rcx, [rbp+4Fh+var_80]
0x18000dbdb  mov     [rbp+4Fh+var_48], rcx
0x18000dbdf  mov     rcx, [rbp+4Fh+var_88]
0x18000dbe3  mov     [rbp+4Fh+var_80], rcx
0x18000dbe7  lock inc dword ptr [rcx]
0x18000dbea  mov     [rsp+0C0h+var_A0], rbx
0x18000dbef  lea     r9, [rbp+4Fh+var_80]
0x18000dbf3  mov     r8, r12
0x18000dbf6  mov     edx, edi
0x18000dbf8  mov     rcx, rax
0x18000dbfb  call    ??0FontFileStream@LocalFileLoader@@QEAA@I$$QEAVFile@@VRefString@DWrite@@VDateTime@@@Z; LocalFileLoader::FontFileStream::FontFileStream(uint,File &&,DWrite::RefString,DateTime)
0x18000dc00  mov     rbx, rax
0x18000dc03  mov     [rbp+4Fh+var_70], rax
0x18000dc07  lea     r12, ?g_localFileLoaderLock@@3VLock@@A; Lock g_localFileLoaderLock
0x18000dc0e  mov     [rbp+4Fh+var_40], r12
0x18000dc12  mov     rcx, r12; lpCriticalSection
0x18000dc15  call    cs:__imp_EnterCriticalSection
0x18000dc1b  nop
0x18000dc1c  lea     rax, [rbp+4Fh+var_90]
0x18000dc20  mov     [rsp+0C0h+var_A0], rax
0x18000dc25  mov     r9d, esi
0x18000dc28  mov     r8, r14
0x18000dc2b  mov     edx, edi
0x18000dc2d  mov     rcx, r13
0x18000dc30  call    ?Find@BucketList@LocalFileLoader@@QEBA_NIPEBXIAEAV?$ComPtr@VFontFileStream@LocalFileLoader@@@@@Z; LocalFileLoader::BucketList::Find(uint,void const *,uint,ComPtr<LocalFileLoader::FontFileStream> &)
0x18000dc35  test    al, al
0x18000dc37  jnz     loc_18000DCE3
0x18000dc3d  mov     rcx, rbx; this
0x18000dc40  call    ?AddRefAndActivate@FontFileStream@LocalFileLoader@@QEAAKXZ; LocalFileLoader::FontFileStream::AddRefAndActivate(void)
0x18000dc45  mov     [rbp+4Fh+var_70], 0
0x18000dc4d  mov     rcx, [rbp+4Fh+var_90]
0x18000dc51  mov     [rbp+4Fh+var_90], rbx
0x18000dc55  test    rcx, rcx
0x18000dc58  jnz     loc_18000DCEC
0x18000dc5e  mov     r8, [r13+0]
0x18000dc62  mov     rax, rbx
0x18000dc65  lea     rcx, [rbx+28h]
0x18000dc69  neg     rax
0x18000dc6c  sbb     rdx, rdx
0x18000dc6f  and     rdx, rcx
0x18000dc72  mov     rax, [r8+8]
0x18000dc76  mov     [rdx], r8
0x18000dc79  mov     [rdx+8], rax
0x18000dc7d  mov     [r8+8], rdx
0x18000dc81  mov     [rax], rdx
0x18000dc84  mov     byte ptr [rdx+10h], 1
0x18000dc88  xor     edi, edi
0x18000dc8a  mov     rcx, r12; lpCriticalSection
0x18000dc8d  call    cs:__imp_LeaveCriticalSection
0x18000dc93  nop
0x18000dc94  test    rdi, rdi
0x18000dc97  jnz     short loc_18000DCFD
0x18000dc99  mov     rcx, [rbp+4Fh+var_88]; struct DWrite::RefString::Data *
0x18000dc9d  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000dca2  mov     rdx, [rbp+4Fh+arg_20]; struct IAccessCheck *
0x18000dca6  test    rdx, rdx
0x18000dca9  jz      short loc_18000DCB3
0x18000dcab  mov     rcx, rbx; this
0x18000dcae  call    ?CheckReadAccess@FontFileStream@LocalFileLoader@@QEAAXPEAVIAccessCheck@@@Z; LocalFileLoader::FontFileStream::CheckReadAccess(IAccessCheck *)
0x18000dcb3  mov     [rbp+4Fh+var_90], 0
0x18000dcbb  mov     [r15], rbx
0x18000dcbe  mov     [rbp+4Fh+var_78], 1
0x18000dcc5  mov     rax, r15
0x18000dcc8  mov     rbx, [rsp+0C0h+arg_8]
0x18000dcd0  add     rsp, 90h
0x18000dcd7  pop     r15
0x18000dcd9  pop     r14
0x18000dcdb  pop     r13
0x18000dcdd  pop     r12
0x18000dcdf  pop     rdi
0x18000dce0  pop     rsi
0x18000dce1  pop     rbp
0x18000dce2  retn
0x18000dce3  mov     rdi, rbx
0x18000dce6  mov     rbx, [rbp+4Fh+var_90]
0x18000dcea  jmp     short loc_18000DC8A
0x18000dcec  mov     rax, [rcx]
0x18000dcef  mov     rax, [rax+10h]
0x18000dcf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcf8  jmp     loc_18000DC5E
0x18000dcfd  mov     rcx, rdi; this
0x18000dd00  call    ??_GFontFileStream@LocalFileLoader@@QEAAPEAXI@Z; LocalFileLoader::FontFileStream::`scalar deleting destructor'(uint)
0x18000dd05  jmp     short loc_18000DC99
```
