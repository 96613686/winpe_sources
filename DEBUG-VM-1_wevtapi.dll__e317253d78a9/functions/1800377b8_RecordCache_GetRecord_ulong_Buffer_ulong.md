# RecordCache::GetRecord(ulong,Buffer &,ulong &)

- ea: `0x1800377b8`
- end: `0x180037a0d`
- name: `?GetRecord@RecordCache@@QEAA_NKAEAVBuffer@@AEAK@Z`
- size: `597`
- prototype: `bool __fastcall(RecordCache *__hidden this, unsigned int, struct Buffer *, unsigned int *)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x18003733c`
- `0x180037510`
- `0x1800381f0`
- `0x180038364`

## callees

- `0x180009d80`
- `0x18000a2d0`
- `0x18000a558`
- `0x180012cb0`
- `0x1800169e8`
- `0x180023548`
- `0x1800377b8`
- `0x1800384f8`
- `0x1800385ec`
- `0x18003872c`
- `0x18003882c`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003782a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003782a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003786a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800379e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003786a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800379e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall RecordCache::GetRecord(RecordCache *this, unsigned int a2, struct Buffer *a3, unsigned int *a4)
{
  int v8; // r15d
  char v9; // si
  __int64 v11; // rbx
  unsigned int v12; // edx
  _BYTE v13[32]; // [rsp+20h] [rbp-50h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h]
  int v16; // [rsp+58h] [rbp-18h]
  int v17; // [rsp+5Ch] [rbp-14h]
  int v18; // [rsp+60h] [rbp-10h]
  int v19; // [rsp+B8h] [rbp+48h]

  v8 = *((_DWORD *)a3 + 5);
  v19 = *((_DWORD *)a3 + 4);
  v9 = 1;
  Buffer::Buffer((Buffer *)v13, 0, 0, 1);
  Buffer::Set((Buffer *)v13, (const unsigned __int8 *)this + 968, 8u);
  Buffer::SetCurrentIndex((Buffer *)v13, 8u);
  AcquireSRWLockExclusive((PSRWLOCK)this + 8);
  *a4 = 0;
  if ( (a2 / 0x64 == *((_DWORD *)this + 36) || RecordCache::SeekToBlock(this, a2))
    && RecordCache::SeekToRecord(this, a2) )
  {
    v11 = *((_QWORD *)this + 2);
    if ( (unsigned __int64)(v11 + 8) > *((_QWORD *)this + 1) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      pExceptionObject = 0;
      v15 = 0;
      v16 = 13;
      v17 = -1;
      v18 = 259;
      throw (EvtException *)&pExceptionObject;
    }
    RecordCache::ReadBytes((HANDLE *)this, (struct Buffer *)v13);
    if ( *((_QWORD *)this + 2) + (unsigned __int64)*((unsigned int *)this + 243) > *((_QWORD *)this + 1) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 13);
      }
      pExceptionObject = 0;
      v15 = 0;
      v16 = 13;
      v17 = -1;
      v18 = 268;
      throw (EvtException *)&pExceptionObject;
    }
    *a4 = *((_DWORD *)this + 243);
    v12 = *((_DWORD *)this + 243);
    if ( v8 - v19 < v12 )
    {
      v9 = 0;
      RecordCache::Seek(this, v11 - *((_QWORD *)this + 122));
    }
    else
    {
      Buffer::SetCurrentIndex((RecordCache *)((char *)this + 992), v12);
      RecordCache::ReadBytes((HANDLE *)this, (RecordCache *)((char *)this + 992));
      Buffer::Write(a3, *((const void *const *)this + 125), *((_DWORD *)this + 252));
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 8);
    Buffer::~Buffer((Buffer *)v13);
    return v9;
  }
  else
  {
    ReleaseSRWLockExclusive((PSRWLOCK)this + 8);
    Buffer::~Buffer((Buffer *)v13);
    return 0;
  }
}

```

## disassembly

```asm
0x1800377b8  mov     [rsp-38h+arg_10], rbx
0x1800377bd  push    rbp
0x1800377be  push    rsi
0x1800377bf  push    rdi
0x1800377c0  push    r12
0x1800377c2  push    r13
0x1800377c4  push    r14
0x1800377c6  push    r15
0x1800377c8  mov     rbp, rsp
0x1800377cb  sub     rsp, 70h
0x1800377cf  mov     r12, r9
0x1800377d2  mov     r13, r8
0x1800377d5  mov     ebx, edx
0x1800377d7  mov     rdi, rcx
0x1800377da  mov     r15d, [r8+14h]
0x1800377de  mov     eax, [r8+10h]
0x1800377e2  mov     [rbp+arg_8], eax
0x1800377e5  mov     sil, 1
0x1800377e8  mov     r9b, sil; bool
0x1800377eb  xor     r8d, r8d; unsigned int
0x1800377ee  xor     edx, edx; unsigned __int8 *
0x1800377f0  lea     rcx, [rbp+var_50]; this
0x1800377f4  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x1800377f9  nop
0x1800377fa  lea     rdx, [rdi+3C8h]; unsigned __int8 *
0x180037801  mov     r14d, 8
0x180037807  mov     r8d, r14d; unsigned int
0x18003780a  lea     rcx, [rbp+var_50]; this
0x18003780e  call    ?Set@Buffer@@QEAAXPEBEK@Z; Buffer::Set(uchar const *,ulong)
0x180037813  mov     edx, r14d; unsigned int
0x180037816  lea     rcx, [rbp+var_50]; this
0x18003781a  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x18003781f  lea     r14, [rdi+40h]
0x180037823  mov     [rbp+arg_0], r14
0x180037827  mov     rcx, r14; SRWLock
0x18003782a  call    cs:__imp_AcquireSRWLockExclusive
0x180037830  nop
0x180037831  mov     dword ptr [r12], 0
0x180037839  mov     eax, 51EB851Fh
0x18003783e  mul     ebx
0x180037840  shr     edx, 5
0x180037843  cmp     edx, [rdi+90h]
0x180037849  jz      short loc_180037859
0x18003784b  mov     edx, ebx; unsigned int
0x18003784d  mov     rcx, rdi; this
0x180037850  call    ?SeekToBlock@RecordCache@@AEAA_NK@Z; RecordCache::SeekToBlock(ulong)
0x180037855  test    al, al
0x180037857  jz      short loc_180037867
0x180037859  mov     edx, ebx; unsigned int
0x18003785b  mov     rcx, rdi; this
0x18003785e  call    ?SeekToRecord@RecordCache@@AEAA_NK@Z; RecordCache::SeekToRecord(ulong)
0x180037863  test    al, al
0x180037865  jnz     short loc_180037881
0x180037867  mov     rcx, r14; SRWLock
0x18003786a  call    cs:__imp_ReleaseSRWLockExclusive
0x180037870  nop
0x180037871  lea     rcx, [rbp+var_50]; this
0x180037875  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18003787a  xor     al, al
0x18003787c  jmp     loc_1800379F5
0x180037881  mov     rbx, [rdi+10h]
0x180037885  lea     rax, [rbx+8]
0x180037889  cmp     rax, [rdi+8]
0x18003788d  jbe     short loc_1800378FA
0x18003788f  lea     rax, WPP_GLOBAL_Control
0x180037896  mov     ebx, 0Dh
0x18003789b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800378a2  cmp     rcx, rax
0x1800378a5  jz      short loc_1800378C8
0x1800378a7  test    [rcx+1Ch], sil
0x1800378ab  jz      short loc_1800378C8
0x1800378ad  cmp     byte ptr [rcx+19h], 2
0x1800378b1  jb      short loc_1800378C8
0x1800378b3  mov     edx, ebx
0x1800378b5  mov     r9d, ebx
0x1800378b8  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800378bf  mov     rcx, [rcx+10h]
0x1800378c3  call    WPP_SF_D
0x1800378c8  xorps   xmm0, xmm0
0x1800378cb  movdqu  [rbp+pExceptionObject], xmm0
0x1800378d0  mov     [rbp+var_20], 0
0x1800378d8  mov     [rbp+var_18], ebx
0x1800378db  mov     [rbp+var_14], 0FFFFFFFFh
0x1800378e2  mov     [rbp+var_10], 103h
0x1800378e9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800378f0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800378f4  call    _CxxThrowException_0
0x1800378fa  lea     rdx, [rbp+var_50]; struct Buffer *
0x1800378fe  mov     rcx, rdi; this
0x180037901  call    ?ReadBytes@RecordCache@@IEAAKAEAVBuffer@@@Z; RecordCache::ReadBytes(Buffer &)
0x180037906  mov     ecx, [rdi+3CCh]
0x18003790c  mov     eax, ecx
0x18003790e  add     rax, [rdi+10h]
0x180037912  cmp     rax, [rdi+8]
0x180037916  jbe     short loc_180037984
0x180037918  lea     rax, WPP_GLOBAL_Control
0x18003791f  mov     ebx, 0Dh
0x180037924  mov     rcx, cs:WPP_GLOBAL_Control
0x18003792b  cmp     rcx, rax
0x18003792e  jz      short loc_180037952
0x180037930  test    [rcx+1Ch], sil
0x180037934  jz      short loc_180037952
0x180037936  cmp     byte ptr [rcx+19h], 2
0x18003793a  jb      short loc_180037952
0x18003793c  lea     edx, [rbx+1]
0x18003793f  mov     r9d, ebx
0x180037942  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037949  mov     rcx, [rcx+10h]
0x18003794d  call    WPP_SF_D
0x180037952  xorps   xmm0, xmm0
0x180037955  movdqu  [rbp+pExceptionObject], xmm0
0x18003795a  mov     [rbp+var_20], 0
0x180037962  mov     [rbp+var_18], ebx
0x180037965  mov     [rbp+var_14], 0FFFFFFFFh
0x18003796c  mov     [rbp+var_10], 10Ch
0x180037973  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003797a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003797e  call    _CxxThrowException_0
0x180037984  mov     [r12], ecx
0x180037988  mov     edx, [rdi+3CCh]; unsigned int
0x18003798e  sub     r15d, [rbp+arg_8]
0x180037992  cmp     r15d, edx
0x180037995  jb      short loc_1800379C9
0x180037997  lea     rbx, [rdi+3E0h]
0x18003799e  mov     rcx, rbx; this
0x1800379a1  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x1800379a6  mov     rdx, rbx; struct Buffer *
0x1800379a9  mov     rcx, rdi; this
0x1800379ac  call    ?ReadBytes@RecordCache@@IEAAKAEAVBuffer@@@Z; RecordCache::ReadBytes(Buffer &)
0x1800379b1  mov     r8d, [rdi+3F0h]; unsigned int
0x1800379b8  mov     rdx, [rdi+3E8h]; void *
0x1800379bf  mov     rcx, r13; this
0x1800379c2  call    ?Write@Buffer@@UEAAXQEBXK@Z; Buffer::Write(void const * const,ulong)
0x1800379c7  jmp     short loc_1800379DF
0x1800379c9  xor     sil, sil
0x1800379cc  sub     rbx, [rdi+3D0h]
0x1800379d3  mov     rdx, rbx; unsigned __int64
0x1800379d6  mov     rcx, rdi; this
0x1800379d9  call    ?Seek@RecordCache@@IEAAX_K@Z; RecordCache::Seek(unsigned __int64)
0x1800379de  nop
0x1800379df  mov     rcx, r14; SRWLock
0x1800379e2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800379e8  nop
0x1800379e9  lea     rcx, [rbp+var_50]; this
0x1800379ed  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800379f2  mov     al, sil
0x1800379f5  mov     rbx, [rsp+70h+arg_10]
0x1800379fd  add     rsp, 70h
0x180037a01  pop     r15
0x180037a03  pop     r14
0x180037a05  pop     r13
0x180037a07  pop     r12
0x180037a09  pop     rdi
0x180037a0a  pop     rsi
0x180037a0b  pop     rbp
0x180037a0c  retn
```
