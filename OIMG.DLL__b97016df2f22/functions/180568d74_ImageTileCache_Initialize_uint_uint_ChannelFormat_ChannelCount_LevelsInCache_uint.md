# ImageTileCache::Initialize(uint,uint,ChannelFormat,ChannelCount,LevelsInCache,uint)

- ea: `0x180568d74`
- end: `0x18056915c`
- name: `?Initialize@ImageTileCache@@IEAAXIIW4ChannelFormat@@W4ChannelCount@@W4LevelsInCache@@I@Z`
- size: `1000`
- prototype: `void *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x180567a74`

## callees

- `0x18001397c`
- `0x1801985ac`
- `0x1801a9adc`
- `0x180226944`
- `0x1804c6944`
- `0x1805657b8`
- `0x180567484`
- `0x180568d74`
- `0x180569d00`
- `0x18056ca40`
- `0x18056d14c`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18056901d`
- `KERNEL32!GetLastError` at `0x18056901d`
- `KERNEL32!CloseHandle` at `0x18056903f`
- `KERNEL32!CloseHandle` at `0x18056905d`
- `KERNEL32!CloseHandle` at `0x1805690ea`
- `KERNEL32!CloseHandle` at `0x18056903f`
- `KERNEL32!CloseHandle` at `0x18056905d`
- `KERNEL32!CloseHandle` at `0x1805690ea`
- `KERNEL32!DeleteFileW` at `0x180569087`
- `KERNEL32!DeleteFileW` at `0x180569087`
- `KERNEL32!CreateFileMappingW` at `0x18056900f`
- `KERNEL32!CreateFileMappingW` at `0x18056900f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180568e79`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180568ea1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180568ef1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180568f63`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180568e79`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180568ea1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180568ef1`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180568f63`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall ImageTileCache::Initialize(__int64 a1)
{
  __int64 v2; // rax
  unsigned int v3; // esi
  unsigned int v4; // edx
  unsigned int v5; // eax
  unsigned int OffsetFromLevel; // r8d
  unsigned int v7; // r8d
  unsigned int v8; // eax
  unsigned __int64 v9; // r14
  unsigned int v10; // esi
  unsigned int v11; // r15d
  __int64 v12; // rax
  bool v13; // cf
  size_t v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  unsigned __int64 v17; // r15
  size_t v18; // rax
  __int64 v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // rsi
  _QWORD *v22; // rdi
  const wchar_t *v23; // rdx
  _QWORD *v24; // rcx
  HANDLE FileMappingW; // rax
  HANDLE v26; // rdi
  DWORD LastError; // eax
  HANDLE v28; // rcx
  _QWORD *v29; // rdi
  _QWORD *v30; // rdx
  void **v32; // [rsp+40h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-28h]
  __int64 v34; // [rsp+50h] [rbp-20h]
  __int16 v35; // [rsp+58h] [rbp-18h]

  v2 = ImageLevelInfo::ImageLevelInfo(&v32);
  *(_OWORD *)(a1 + 16) = *(_OWORD *)v2;
  *(_OWORD *)(a1 + 32) = *(_OWORD *)(v2 + 16);
  *(_QWORD *)(a1 + 48) = *(_QWORD *)(v2 + 32);
  *(_DWORD *)(a1 + 56) = *(_DWORD *)(v2 + 40);
  *(_DWORD *)(a1 + 60) = *(_DWORD *)(a1 + 44) * *(_DWORD *)(a1 + 48) * *(_DWORD *)(a1 + 56);
  v3 = *(_DWORD *)(a1 + 16);
  if ( *(_DWORD *)(a1 + 40) == 1 )
  {
    v7 = (*(_DWORD *)(a1 + 44) + v3 - 1) / *(_DWORD *)(a1 + 44);
    if ( !v7 )
      v7 = 1;
    v8 = (unsigned int)(*(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 20) - 1) / *(_DWORD *)(a1 + 48);
    if ( !v8 )
      v8 = 1;
    OffsetFromLevel = v8 * v7;
  }
  else
  {
    v4 = 1;
    v5 = *(_DWORD *)(a1 + 16);
    if ( v3 <= *(_DWORD *)(a1 + 20) )
      v5 = *(_DWORD *)(a1 + 20);
    while ( v5 > 1 )
    {
      v5 = (v5 + 1) >> 1;
      ++v4;
    }
    OffsetFromLevel = ImageLevelInfo::GetOffsetFromLevel((ImageLevelInfo *)(a1 + 16), v4);
  }
  v9 = 1;
  if ( OffsetFromLevel > 1 )
    v9 = OffsetFromLevel;
  v10 = (v3 + *(_DWORD *)(a1 + 44) - 1) / *(_DWORD *)(a1 + 44);
  if ( !v10 )
    v10 = 1;
  v11 = (unsigned int)(*(_DWORD *)(a1 + 48) + *(_DWORD *)(a1 + 20) - 1) / *(_DWORD *)(a1 + 48);
  if ( !v11 )
    v11 = 1;
  *(_QWORD *)(a1 + 72) = malloc((unsigned int)v9);
  v12 = 16 * v9;
  if ( !is_mul_ok(v9, 0x10u) )
    v12 = -1;
  v13 = __CFADD__(v12, 8);
  v14 = v12 + 8;
  if ( v13 )
    v14 = -1;
  v15 = malloc(v14);
  if ( v15 )
  {
    *v15 = v9;
    v16 = v15 + 1;
    `eh vector constructor iterator'(
      v15 + 1,
      0x10u,
      (unsigned int)v9,
      (void (*)(void *))CutoutAPI::GridGraph8::NodeStack::NodeStack,
      Base::PtrRef<MemoryPointer>::~PtrRef<MemoryPointer>);
  }
  else
  {
    v16 = 0;
  }
  *(_QWORD *)(a1 + 88) = v16;
  v17 = v10 * v11;
  v18 = 8 * v17;
  if ( !is_mul_ok(v17, 8u) )
    v18 = -1;
  *(_QWORD *)(a1 + 96) = malloc(v18);
  v19 = 0xFFFFFFFF % *(_DWORD *)(a1 + 60);
  v20 = (0xFFFFFFFF / *(_DWORD *)(a1 + 60)) >> 3;
  *(_DWORD *)(a1 + 152) = (unsigned int)v9 <= v20;
  if ( (unsigned int)v9 > v20 )
  {
    v32 = &Base::File::`vftable';
    hObject = (HANDLE)-1LL;
    v34 = ((__int64 (__fastcall *)(void ***, __int64))g_stringCRTMgr[3])(&g_stringCRTMgr, v19) + 24;
    v32 = &Base::TempFile::`vftable';
    v35 = 0;
    v21 = a1 + 64;
    v22 = malloc(0x18u);
    if ( !v22 )
      ThrowOOM();
    v23 = *(const wchar_t **)Base::TempFile::GeneratePath((Base::TempFile *)&v32);
    *v22 = &Base::File::`vftable';
    v22[1] = -1;
    Base::String::String((Base::String *)(v22 + 2), v23);
    v24 = *(_QWORD **)v21;
    if ( *(_QWORD **)v21 != v22 )
    {
      Base::Ptr<Renderer>::Release(a1 + 64);
      *(_QWORD *)v21 = v22;
      v24 = v22;
    }
    (*(void (__fastcall **)(_QWORD *, __int64, _QWORD, _QWORD, int, int, _QWORD))(*v24 + 24LL))(
      v24,
      3221225472LL,
      0,
      0,
      3,
      67109120,
      0);
    HIBYTE(v35) = 1;
    FileMappingW = CreateFileMappingW(
                     *(HANDLE *)(*(_QWORD *)v21 + 8LL),
                     0,
                     4u,
                     (v9 * *(unsigned int *)(a1 + 60)) >> 32,
                     (int)v9 * *(_DWORD *)(a1 + 60),
                     0);
    v26 = FileMappingW;
    if ( !FileMappingW )
    {
      LastError = GetLastError();
      if ( LastError != 112 )
        ATL::BaseAtlThrow((unsigned __int16)LastError | 0x80070000);
      ATL::BaseAtlThrow(-2045181439);
    }
    v28 = *(HANDLE *)(a1 + 80);
    if ( FileMappingW != v28 )
    {
      if ( v28 != (HANDLE)-1LL )
        CloseHandle(v28);
      *(_QWORD *)(a1 + 80) = v26;
    }
    v32 = &Base::TempFile::`vftable';
    if ( hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    if ( !HIBYTE(v35) )
    {
      if ( (_BYTE)v35 )
      {
        v29 = (_QWORD *)ATL::CSimpleStringT<wchar_t,0>::CloneData(v34 - 24);
        DeleteFileW((LPCWSTR)v29 + 12);
        if ( _InterlockedDecrement((volatile signed __int32 *)v29 + 4) <= 0 )
          (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v29 + 8LL))(*v29, v29);
      }
    }
    v32 = &Base::File::`vftable';
    v30 = (_QWORD *)(v34 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v34 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 8LL))(*v30);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
  }
  memset_0(*(void **)(a1 + 72), 0, v9);
  memset_0(*(void **)(a1 + 88), 0, 8 * v9);
  return memset_0(*(void **)(a1 + 96), 0, 8 * v17);
}

```

## disassembly

```asm
0x180568d74  mov     [rsp-28h+arg_8], rbx
0x180568d79  mov     [rsp-28h+arg_10], rsi
0x180568d7e  push    rbp
0x180568d7f  push    rdi
0x180568d80  push    r12
0x180568d82  push    r14
0x180568d84  push    r15
0x180568d86  mov     rbp, rsp
0x180568d89  sub     rsp, 70h
0x180568d8d  mov     rbx, rcx
0x180568d90  mov     eax, [rbp+arg_30]
0x180568d93  mov     dword ptr [rsp+70h+var_40], eax
0x180568d97  mov     eax, [rbp+arg_28]
0x180568d9a  mov     dword ptr [rsp+70h+lpName], eax
0x180568d9e  mov     eax, [rbp+arg_20]
0x180568da1  mov     [rsp+70h+dwMaximumSizeLow], eax
0x180568da5  lea     rcx, [rbp+var_30]
0x180568da9  call    ??0ImageLevelInfo@@QEAA@IIW4ChannelFormat@@W4ChannelCount@@W4LevelsInCache@@I@Z; ImageLevelInfo::ImageLevelInfo(uint,uint,ChannelFormat,ChannelCount,LevelsInCache,uint)
0x180568dae  lea     rdi, [rbx+10h]
0x180568db2  movups  xmm0, xmmword ptr [rax]
0x180568db5  movups  xmmword ptr [rdi], xmm0
0x180568db8  movups  xmm1, xmmword ptr [rax+10h]
0x180568dbc  movups  xmmword ptr [rdi+10h], xmm1
0x180568dc0  movsd   xmm0, qword ptr [rax+20h]
0x180568dc5  movsd   qword ptr [rdi+20h], xmm0
0x180568dca  mov     eax, [rax+28h]
0x180568dcd  mov     [rdi+28h], eax
0x180568dd0  mov     eax, [rbx+38h]
0x180568dd3  imul    eax, [rbx+30h]
0x180568dd7  imul    eax, [rbx+2Ch]
0x180568ddb  mov     [rbx+3Ch], eax
0x180568dde  mov     r12d, 1
0x180568de4  mov     esi, [rdi]
0x180568de6  cmp     [rdi+18h], r12d
0x180568dea  jz      short loc_180568E13
0x180568dec  mov     edx, r12d
0x180568def  mov     eax, esi
0x180568df1  cmp     esi, [rdi+4]
0x180568df4  cmovbe  eax, [rdi+4]
0x180568df8  jmp     short loc_180568E01
0x180568dfa  inc     eax
0x180568dfc  shr     eax, 1
0x180568dfe  add     edx, r12d; unsigned int
0x180568e01  cmp     eax, r12d
0x180568e04  ja      short loc_180568DFA
0x180568e06  mov     rcx, rdi; this
0x180568e09  call    ?GetOffsetFromLevel@ImageLevelInfo@@AEBAII@Z; ImageLevelInfo::GetOffsetFromLevel(uint)
0x180568e0e  mov     r8d, eax
0x180568e11  jmp     short loc_180568E40
0x180568e13  lea     eax, [rsi-1]
0x180568e16  add     eax, [rdi+1Ch]
0x180568e19  xor     edx, edx
0x180568e1b  div     dword ptr [rdi+1Ch]
0x180568e1e  mov     r8d, eax
0x180568e21  cmp     eax, r12d
0x180568e24  cmovb   r8d, r12d
0x180568e28  mov     eax, [rdi+4]
0x180568e2b  dec     eax
0x180568e2d  add     eax, [rdi+20h]
0x180568e30  xor     edx, edx
0x180568e32  div     dword ptr [rdi+20h]
0x180568e35  cmp     eax, r12d
0x180568e38  cmovb   eax, r12d
0x180568e3c  imul    r8d, eax
0x180568e40  mov     r14d, r12d
0x180568e43  cmp     r8d, r12d
0x180568e46  cmova   r14d, r8d
0x180568e4a  mov     ecx, [rdi+1Ch]
0x180568e4d  lea     eax, [rcx-1]
0x180568e50  add     eax, esi
0x180568e52  xor     edx, edx
0x180568e54  div     ecx
0x180568e56  mov     esi, eax
0x180568e58  cmp     eax, r12d
0x180568e5b  cmovb   esi, r12d
0x180568e5f  mov     eax, [rdi+4]
0x180568e62  dec     eax
0x180568e64  add     eax, [rdi+20h]
0x180568e67  xor     edx, edx
0x180568e69  div     dword ptr [rdi+20h]
0x180568e6c  mov     r15d, eax
0x180568e6f  cmp     eax, r12d
0x180568e72  cmovb   r15d, r12d
0x180568e76  mov     ecx, r14d; Size
0x180568e79  call    cs:__imp_malloc
0x180568e7f  mov     [rbx+48h], rax
0x180568e83  mov     eax, 10h
0x180568e88  mul     r14
0x180568e8b  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180568e92  cmovb   rax, r12
0x180568e96  add     rax, 8
0x180568e9a  cmovb   rax, r12
0x180568e9e  mov     rcx, rax; Size
0x180568ea1  call    cs:__imp_malloc
0x180568ea7  test    rax, rax
0x180568eaa  jz      short loc_180568ED8
0x180568eac  mov     [rax], r14
0x180568eaf  lea     rdi, [rax+8]
0x180568eb3  lea     rax, ??1?$PtrRef@VMemoryPointer@@@Base@@QEAA@XZ; Base::PtrRef<MemoryPointer>::~PtrRef<MemoryPointer>(void)
0x180568eba  mov     qword ptr [rsp+70h+dwMaximumSizeLow], rax; void (*)(void *)
0x180568ebf  lea     r9, ??0NodeStack@GridGraph8@CutoutAPI@@QEAA@XZ; void (*)(void *)
0x180568ec6  mov     r8d, r14d; unsigned __int64
0x180568ec9  lea     edx, [r12+11h]; unsigned __int64
0x180568ece  mov     rcx, rdi; void *
0x180568ed1  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180568ed6  jmp     short loc_180568EDA
0x180568ed8  xor     edi, edi
0x180568eda  mov     [rbx+58h], rdi
0x180568ede  imul    r15d, esi
0x180568ee2  mov     eax, 8
0x180568ee7  mul     r15
0x180568eea  cmovb   rax, r12
0x180568eee  mov     rcx, rax; Size
0x180568ef1  call    cs:__imp_malloc
0x180568ef7  mov     [rbx+60h], rax
0x180568efb  xor     edx, edx
0x180568efd  or      eax, 0FFFFFFFFh
0x180568f00  div     dword ptr [rbx+3Ch]
0x180568f03  shr     eax, 3
0x180568f06  xor     ecx, ecx
0x180568f08  cmp     r14d, eax
0x180568f0b  setbe   cl
0x180568f0e  mov     [rbx+98h], ecx
0x180568f14  jbe     loc_1805690F0
0x180568f1a  lea     rax, ??_7File@Base@@6B@; const Base::File::`vftable'
0x180568f21  mov     [rbp+var_30], rax
0x180568f25  mov     [rbp+hObject], r12
0x180568f29  mov     rax, cs:?g_stringCRTMgr@@3VCAtlStringMgr@ATL@@A; ATL::CAtlStringMgr g_stringCRTMgr
0x180568f30  lea     rcx, ?g_stringCRTMgr@@3VCAtlStringMgr@ATL@@A; ATL::CAtlStringMgr g_stringCRTMgr
0x180568f37  mov     rax, [rax+18h]
0x180568f3b  call    cs:__guard_dispatch_icall_fptr
0x180568f41  add     rax, 18h
0x180568f45  mov     [rbp+var_20], rax
0x180568f49  lea     rax, ??_7TempFile@Base@@6B@; const Base::TempFile::`vftable'
0x180568f50  mov     [rbp+var_30], rax
0x180568f54  mov     [rbp+var_18], 0
0x180568f5a  lea     rsi, [rbx+40h]
0x180568f5e  mov     ecx, 18h; Size
0x180568f63  call    cs:__imp_malloc
0x180568f69  mov     rdi, rax
0x180568f6c  test    rax, rax
0x180568f6f  jz      loc_180569156
0x180568f75  mov     [rbp+arg_0], rax
0x180568f79  lea     rcx, [rbp+var_30]; this
0x180568f7d  call    ?GeneratePath@TempFile@Base@@QEAAAEBVPath@2@XZ; Base::TempFile::GeneratePath(void)
0x180568f82  mov     rdx, [rax]; wchar_t *
0x180568f85  lea     rax, ??_7File@Base@@6B@; const Base::File::`vftable'
0x180568f8c  mov     [rdi], rax
0x180568f8f  mov     [rdi+8], r12
0x180568f93  lea     rcx, [rdi+10h]; this
0x180568f97  call    ??0String@Base@@QEAA@PEB_W@Z; Base::String::String(wchar_t const *)
0x180568f9c  mov     rcx, [rsi]
0x180568f9f  cmp     rcx, rdi
0x180568fa2  jz      short loc_180568FB2
0x180568fa4  mov     rcx, rsi
0x180568fa7  call    ?Release@?$Ptr@VRenderer@@@Base@@QEAAXXZ; Base::Ptr<Renderer>::Release(void)
0x180568fac  mov     [rsi], rdi
0x180568faf  mov     rcx, rdi
0x180568fb2  mov     rax, [rcx]
0x180568fb5  mov     [rsp+70h+var_40], 0
0x180568fbe  mov     dword ptr [rsp+70h+lpName], 4000100h
0x180568fc6  mov     [rsp+70h+dwMaximumSizeLow], 3
0x180568fce  xor     r9d, r9d
0x180568fd1  xor     r8d, r8d
0x180568fd4  mov     edx, 0C0000000h
0x180568fd9  mov     rax, [rax+18h]
0x180568fdd  call    cs:__guard_dispatch_icall_fptr
0x180568fe3  mov     byte ptr [rbp+var_18+1], 1
0x180568fe7  mov     eax, [rbx+3Ch]
0x180568fea  imul    rax, r14
0x180568fee  mov     r9, rax
0x180568ff1  shr     r9, 20h; dwMaximumSizeHigh
0x180568ff5  mov     rcx, [rsi]
0x180568ff8  mov     [rsp+70h+lpName], 0; lpName
0x180569001  mov     [rsp+70h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x180569005  xor     edx, edx; lpFileMappingAttributes
0x180569007  lea     r8d, [rdx+4]; flProtect
0x18056900b  mov     rcx, [rcx+8]; hFile
0x18056900f  call    cs:__imp_CreateFileMappingW
0x180569015  mov     rdi, rax
0x180569018  test    rax, rax
0x18056901b  jnz     short loc_180569031
0x18056901d  call    cs:__imp_GetLastError
0x180569023  cmp     eax, 70h ; 'p'
0x180569026  jz      loc_18056914B
0x18056902c  jmp     loc_18056913C
0x180569031  mov     rcx, [rbx+50h]; hObject
0x180569035  cmp     rdi, rcx
0x180569038  jz      short loc_180569049
0x18056903a  cmp     rcx, r12
0x18056903d  jz      short loc_180569045
0x18056903f  call    cs:__imp_CloseHandle
0x180569045  mov     [rbx+50h], rdi
0x180569049  lea     rax, ??_7TempFile@Base@@6B@; const Base::TempFile::`vftable'
0x180569050  mov     [rbp+var_30], rax
0x180569054  mov     rcx, [rbp+hObject]; hObject
0x180569058  cmp     rcx, r12
0x18056905b  jz      short loc_180569067
0x18056905d  call    cs:__imp_CloseHandle
0x180569063  mov     [rbp+hObject], r12
0x180569067  cmp     byte ptr [rbp+var_18+1], 0
0x18056906b  jnz     short loc_1805690AF
0x18056906d  cmp     byte ptr [rbp+var_18], 0
0x180569071  jz      short loc_1805690AF
0x180569073  mov     rcx, [rbp+var_20]
0x180569077  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18056907b  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x180569080  mov     rdi, rax
0x180569083  lea     rcx, [rax+18h]; lpFileName
0x180569087  call    cs:__imp_DeleteFileW
0x18056908d  mov     ecx, r12d
0x180569090  lock xadd [rdi+10h], ecx
0x180569095  add     ecx, r12d
0x180569098  test    ecx, ecx
0x18056909a  jg      short loc_1805690AF
0x18056909c  mov     rcx, [rdi]
0x18056909f  mov     rax, [rcx]
0x1805690a2  mov     rdx, rdi
0x1805690a5  mov     rax, [rax+8]
0x1805690a9  call    cs:__guard_dispatch_icall_fptr
0x1805690af  lea     rax, ??_7File@Base@@6B@; const Base::File::`vftable'
0x1805690b6  mov     [rbp+var_30], rax
0x1805690ba  mov     rdx, [rbp+var_20]
0x1805690be  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1805690c2  mov     eax, r12d
0x1805690c5  lock xadd [rdx+10h], eax
0x1805690ca  add     eax, r12d
0x1805690cd  test    eax, eax
0x1805690cf  jg      short loc_1805690E1
0x1805690d1  mov     rcx, [rdx]
0x1805690d4  mov     rax, [rcx]
0x1805690d7  mov     rax, [rax+8]
0x1805690db  call    cs:__guard_dispatch_icall_fptr
0x1805690e1  mov     rcx, [rbp+hObject]; hObject
0x1805690e5  cmp     rcx, r12
0x1805690e8  jz      short loc_1805690F0
0x1805690ea  call    cs:__imp_CloseHandle
0x1805690f0  mov     r8, r14; Size
0x1805690f3  xor     edx, edx; Val
0x1805690f5  mov     rcx, [rbx+48h]; void *
0x1805690f9  call    memset_0
0x1805690fe  lea     r8, ds:0[r14*8]; Size
0x180569106  xor     edx, edx; Val
0x180569108  mov     rcx, [rbx+58h]; void *
0x18056910c  call    memset_0
0x180569111  lea     r8, ds:0[r15*8]; Size
0x180569119  xor     edx, edx; Val
0x18056911b  mov     rcx, [rbx+60h]; void *
0x18056911f  lea     r11, [rsp+70h+var_s0]
0x180569124  mov     rbx, [r11+38h]
0x180569128  mov     rsi, [r11+40h]
0x18056912c  mov     rsp, r11
0x18056912f  pop     r15
0x180569131  pop     r14
0x180569133  pop     r12
0x180569135  pop     rdi
0x180569136  pop     rbp
0x180569137  jmp     memset_0
0x18056913c  movzx   ecx, ax
0x18056913f  or      ecx, 80070000h; int
0x180569145  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18056914b  mov     ecx, 86190201h; int
0x180569150  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180569156  call    ?ThrowOOM@@YAXXZ; ThrowOOM(void)
```
