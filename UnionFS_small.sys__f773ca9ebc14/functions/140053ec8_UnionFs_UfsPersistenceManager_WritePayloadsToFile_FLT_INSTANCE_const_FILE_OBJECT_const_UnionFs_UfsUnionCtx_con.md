# UnionFs::UfsPersistenceManager::WritePayloadsToFile(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsUnionCtx const &,utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>> const &,bool *,UnionFs::UfsPersistenceManager::WritePayloadRecordCtx &,UnionFs::StackEventTracer &)

- ea: `0x140053ec8`
- end: `0x1400541cb`
- name: `?WritePayloadsToFile@UfsPersistenceManager@UnionFs@@IEBAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEBVUfsUnionCtx@2@AEBV?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@PEA_NAEAUWritePayloadRecordCtx@12@AEAVStackEventTracer@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140050744`
- `0x140052fdc`

## callees

- `0x140053d90`
- `0x140053ec8`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14007b8b0`
- `0x14007b900`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14005404c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400540e1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005404c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400540e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054058`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400540ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140054058`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400540ed`
- `FLTMGR!FltWriteFile` at `0x140053fe7`
- `FLTMGR!FltWriteFile` at `0x140054142`
- `FLTMGR!FltWriteFile` at `0x140053fe7`
- `FLTMGR!FltWriteFile` at `0x140054142`

## string_xrefs

- `0x14005418e`: `ORIGIN: Write offset not aligned to chunk size`
- `0x140054089`: `UnionFs::UfsPersistenceManager::WritePayloadsToFile`
- `0x1400540b2`: `UnionFs::UfsPersistenceManager::WritePayloadsToFile`
- `0x140054165`: `UnionFs::UfsPersistenceManager::WritePayloadsToFile`
- `0x1400541a1`: `UnionFs::UfsPersistenceManager::WritePayloadsToFile`

## pseudocode

```c
__int64 UnionFs::UfsPersistenceManager::WritePayloadsToFile(
        UnionFs::UfsPersistenceManager *a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        ULONG *a4,
        struct UnionFs::UfsTablePayload ***a5,
        ...)
{
  PERESOURCE v5; // rsi
  _BYTE *v6; // r13
  const struct UnionFs::UfsUnionCtx *v7; // rbp
  struct _LIST_ENTRY **p_Blink; // r12
  char v9; // r15
  struct UnionFs::StackEventTracer *v10; // r14
  struct UnionFs::UfsTablePayload **v11; // rbx
  struct UnionFs::UfsTablePayload **v12; // rdi
  int v13; // eax
  NTSTATUS v14; // ebp
  int SharedWaiters; // eax
  struct _ERESOURCE *v16; // rcx
  struct _ERESOURCE *v17; // rcx
  unsigned int v19; // ebx
  const char *Flags; // [rsp+28h] [rbp-80h]
  const char *Flagsa; // [rsp+28h] [rbp-80h]
  ULONG Length; // [rsp+50h] [rbp-58h]
  _BYTE *BytesWritten; // [rsp+D8h] [rbp+30h] BYREF
  va_list va; // [rsp+D8h] [rbp+30h]
  PERESOURCE Resource; // [rsp+E0h] [rbp+38h] BYREF
  va_list Resourcea; // [rsp+E0h] [rbp+38h]
  struct UnionFs::StackEventTracer *v31; // [rsp+E8h] [rbp+40h]
  va_list va2; // [rsp+F0h] [rbp+48h] BYREF

  va_start(va2, a5);
  va_start(Resourcea, a5);
  va_start(va, a5);
  BytesWritten = va_arg(Resourcea, _BYTE *);
  va_copy(va2, Resourcea);
  Resource = va_arg(va2, PERESOURCE);
  v31 = va_arg(va2, struct UnionFs::StackEventTracer *);
  v5 = Resource;
  v6 = BytesWritten;
  v7 = (const struct UnionFs::UfsUnionCtx *)a4;
  p_Blink = &Resource->SystemResourcesList.Blink;
  *BytesWritten = 0;
  Length = a4[75];
  if ( (__int64)*p_Blink % Length )
  {
    v19 = -1073741811;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      (int)v31,
      (struct UnionFs::StackEventTracer *)0x32C00170610LL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::WritePayloadsToFile",
      "ORIGIN: Write offset not aligned to chunk size",
      Flags);
    return v19;
  }
  else
  {
    v9 = 0;
    v10 = v31;
    LODWORD(BytesWritten) = 0;
    v11 = *a5;
    v12 = a5[1];
    while ( v11 != v12 )
    {
      (*(void (__fastcall **)(struct UnionFs::UfsTablePayload *, PERESOURCE *))(*(_QWORD *)*v11 + 8LL))(
        *v11,
        (PERESOURCE *)Resourcea);
      v13 = UnionFs::UfsPersistenceManager::WritePayloadToBuffer(
              a1,
              v7,
              *v11,
              (struct UnionFs::UfsPersistenceManager::WritePayloadRecordCtx *)v5,
              v10);
      v14 = v13;
      if ( v13 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v13,
          (int)v10,
          (struct UnionFs::StackEventTracer *)0x4B50017061CLL,
          (unsigned __int64)"UnionFs::UfsPersistenceManager::WritePayloadsToFile",
          "PUSH: Writing payload record",
          Flags);
        goto LABEL_14;
      }
      if ( ((__int64)v5->SystemResourcesList.Flink & 4) != 0 )
      {
        v9 = 1;
        if ( HIDWORD(v5->OwnerTable) >= Length )
        {
          v14 = FltWriteFile(
                  a2,
                  a3,
                  (PLARGE_INTEGER)p_Blink,
                  (ULONG)v5->OwnerTable,
                  *(PVOID *)&v5->ActiveCount,
                  0,
                  (PULONG)va,
                  0,
                  0);
          if ( v14 < 0 )
          {
            UnionFs::ProcessTraceStatusFromApi(
              (UnionFs *)(unsigned int)v14,
              (int)v10,
              (struct UnionFs::StackEventTracer *)0x4B600170631LL,
              (unsigned __int64)"UnionFs::UfsPersistenceManager::WritePayloadsToFile",
              "API: Writing payload record",
              Flags);
LABEL_14:
            v17 = Resource;
            Resource = 0;
            if ( v17 )
            {
              ExReleaseResourceLite(v17);
              KeLeaveCriticalRegion();
            }
            return (unsigned int)v14;
          }
          memmove(*(void **)&v5->ActiveCount, (const void *)(*(_QWORD *)&v5->ActiveCount + Length), Length);
          memset((void *)(Length + *(_QWORD *)&v5->ActiveCount), 0, Length);
          SharedWaiters = (int)v5->SharedWaiters;
          *p_Blink = (struct _LIST_ENTRY *)((char *)*p_Blink + Length);
          HIDWORD(v5->SystemResourcesList.Flink) = 0;
          HIDWORD(v5->OwnerTable) = SharedWaiters;
          *v6 = 1;
          v9 = 0;
        }
      }
      v16 = Resource;
      Resource = 0;
      if ( v16 )
      {
        ExReleaseResourceLite(v16);
        KeLeaveCriticalRegion();
      }
      v7 = (const struct UnionFs::UfsUnionCtx *)a4;
      v11 += 2;
    }
    if ( v9 )
    {
      v19 = FltWriteFile(a2, a3, (PLARGE_INTEGER)p_Blink, Length, *(PVOID *)&v5->ActiveCount, 0, (PULONG)va, 0, 0);
      if ( (v19 & 0x80000000) != 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)v19,
          (int)v10,
          (struct UnionFs::StackEventTracer *)0x4B700170658LL,
          (unsigned __int64)"UnionFs::UfsPersistenceManager::WritePayloadsToFile",
          "API: Writing payload record",
          Flagsa);
        return v19;
      }
      *v6 = 1;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140053ec8  mov     r11, rsp
0x140053ecb  mov     [r11+20h], r9
0x140053ecf  mov     [r11+18h], r8
0x140053ed3  mov     [r11+10h], rdx
0x140053ed7  mov     [r11+8], rcx
0x140053edb  push    rbx
0x140053edc  push    rbp
0x140053edd  push    rsi
0x140053ede  push    rdi
0x140053edf  push    r12
0x140053ee1  push    r13
0x140053ee3  push    r14
0x140053ee5  push    r15
0x140053ee7  sub     rsp, 68h
0x140053eeb  mov     rsi, [rsp+0A8h+Resource]
0x140053ef3  xor     r8d, r8d
0x140053ef6  mov     r13, [rsp+0A8h+arg_28]
0x140053efe  mov     rbp, r9
0x140053f01  lea     r12, [rsi+8]
0x140053f05  mov     [r13+0], r8b
0x140053f09  mov     ecx, [r9+12Ch]
0x140053f10  mov     rax, [r12]
0x140053f14  cqo
0x140053f16  mov     [rsp+0A8h+Length], ecx
0x140053f1a  idiv    rcx
0x140053f1d  mov     [rsp+0A8h+Size], rcx
0x140053f22  test    rdx, rdx
0x140053f25  jnz     loc_140054186
0x140053f2b  mov     rdi, [rsp+0A8h+arg_20]
0x140053f33  mov     r15b, r8b
0x140053f36  mov     r14, [rsp+0A8h+arg_38]
0x140053f3e  mov     [r11+30h], r8d
0x140053f42  mov     rbx, [rdi]
0x140053f45  mov     rdi, [rdi+8]
0x140053f49  cmp     rbx, rdi
0x140053f4c  jz      loc_140054100
0x140053f52  mov     rcx, [rbx]
0x140053f55  lea     rdx, [rsp+0A8h+Resource]
0x140053f5d  mov     rax, [rcx]
0x140053f60  mov     rax, [rax+8]
0x140053f64  call    _guard_dispatch_icall
0x140053f69  mov     r8, [rbx]; struct UnionFs::UfsTablePayload *
0x140053f6c  mov     r9, rsi; struct UnionFs::UfsPersistenceManager::WritePayloadRecordCtx *
0x140053f6f  mov     rcx, [rsp+0A8h+arg_0]; this
0x140053f77  mov     rdx, rbp; struct UnionFs::UfsUnionCtx *
0x140053f7a  mov     [rsp+0A8h+Buffer], r14; struct UnionFs::StackEventTracer *
0x140053f7f  call    ?WritePayloadToBuffer@UfsPersistenceManager@UnionFs@@IEBAJAEBVUfsUnionCtx@2@AEAVUfsTablePayload@2@AEAUWritePayloadRecordCtx@12@AEAVStackEventTracer@2@@Z; UnionFs::UfsPersistenceManager::WritePayloadToBuffer(UnionFs::UfsUnionCtx const &,UnionFs::UfsTablePayload &,UnionFs::UfsPersistenceManager::WritePayloadRecordCtx &,UnionFs::StackEventTracer &)
0x140053f84  xor     r8d, r8d
0x140053f87  mov     ebp, eax
0x140053f89  test    eax, eax
0x140053f8b  js      loc_1400540A1
0x140053f91  mov     eax, [rsi]
0x140053f93  test    al, 4
0x140053f95  jz      loc_140054037
0x140053f9b  mov     eax, [rsp+0A8h+Length]
0x140053f9f  mov     r15b, 1
0x140053fa2  cmp     [rsi+14h], eax
0x140053fa5  jb      loc_140054037
0x140053fab  mov     r9d, [rsi+10h]; Length
0x140053faf  lea     rax, [rsp+0A8h+arg_28]
0x140053fb7  mov     rdx, [rsp+0A8h+FileObject]; FileObject
0x140053fbf  mov     rcx, [rsp+0A8h+InitiatingInstance]; InitiatingInstance
0x140053fc7  mov     [rsp+0A8h+CallbackContext], r8; CallbackContext
0x140053fcc  mov     [rsp+0A8h+CallbackRoutine], r8; CallbackRoutine
0x140053fd1  mov     [rsp+0A8h+BytesWritten], rax; BytesWritten
0x140053fd6  mov     rax, [rsi+18h]
0x140053fda  mov     dword ptr [rsp+0A8h+Flags], r8d; char *
0x140053fdf  mov     r8, r12; ByteOffset
0x140053fe2  mov     [rsp+0A8h+Buffer], rax; Buffer
0x140053fe7  call    cs:__imp_FltWriteFile
0x140053fee  nop     dword ptr [rax+rax+00h]
0x140053ff3  mov     ebp, eax
0x140053ff5  test    eax, eax
0x140053ff7  js      short loc_140054078
0x140053ff9  mov     rcx, [rsi+18h]; void *
0x140053ffd  mov     rbp, [rsp+0A8h+Size]
0x140054002  mov     r8, rbp; Size
0x140054005  lea     rdx, [rcx+rbp]; Src
0x140054009  call    memmove
0x14005400e  mov     rcx, [rsi+18h]
0x140054012  mov     r8, rbp; Size
0x140054015  add     rcx, rbp; void *
0x140054018  xor     edx, edx; Val
0x14005401a  call    memset
0x14005401f  mov     eax, [rsi+20h]
0x140054022  xor     r8d, r8d
0x140054025  add     [r12], rbp
0x140054029  mov     [rsi+4], r8d
0x14005402d  mov     [rsi+14h], eax
0x140054030  mov     [r13+0], r15b
0x140054034  mov     r15b, r8b
0x140054037  mov     rcx, [rsp+0A8h+Resource]; Resource
0x14005403f  mov     [rsp+0A8h+Resource], r8
0x140054047  test    rcx, rcx
0x14005404a  jz      short loc_140054067
0x14005404c  call    cs:__imp_ExReleaseResourceLite
0x140054053  nop     dword ptr [rax+rax+00h]
0x140054058  call    cs:__imp_KeLeaveCriticalRegion
0x14005405f  nop     dword ptr [rax+rax+00h]
0x140054064  xor     r8d, r8d
0x140054067  mov     rbp, [rsp+0A8h+arg_18]
0x14005406f  add     rbx, 10h
0x140054073  jmp     loc_140053F49
0x140054078  lea     rax, aApiWritingPayl; "API: Writing payload record"
0x14005407f  mov     r8, 4B600170631h; struct UnionFs::StackEventTracer *
0x140054089  lea     r9, aUnionfsUfspers_23; "UnionFs::UfsPersistenceManager::WritePa"...
0x140054090  mov     [rsp+0A8h+Buffer], rax; char *
0x140054095  mov     rdx, r14; int
0x140054098  mov     ecx, ebp; this
0x14005409a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005409f  jmp     short loc_1400540C8
0x1400540a1  lea     rax, aPushWritingPay; "PUSH: Writing payload record"
0x1400540a8  mov     r8, 4B50017061Ch; struct UnionFs::StackEventTracer *
0x1400540b2  lea     r9, aUnionfsUfspers_23; "UnionFs::UfsPersistenceManager::WritePa"...
0x1400540b9  mov     [rsp+0A8h+Buffer], rax; char *
0x1400540be  mov     rdx, r14; int
0x1400540c1  mov     ecx, ebp; this
0x1400540c3  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400540c8  mov     rcx, [rsp+0A8h+Resource]; Resource
0x1400540d0  mov     [rsp+0A8h+Resource], 0
0x1400540dc  test    rcx, rcx
0x1400540df  jz      short loc_1400540F9
0x1400540e1  call    cs:__imp_ExReleaseResourceLite
0x1400540e8  nop     dword ptr [rax+rax+00h]
0x1400540ed  call    cs:__imp_KeLeaveCriticalRegion
0x1400540f4  nop     dword ptr [rax+rax+00h]
0x1400540f9  mov     eax, ebp
0x1400540fb  jmp     loc_1400541B9
0x140054100  test    r15b, r15b
0x140054103  jz      short loc_140054182
0x140054105  mov     r9d, [rsp+0A8h+Length]; Length
0x14005410a  lea     rax, [rsp+0A8h+arg_28]
0x140054112  mov     rdx, [rsp+0A8h+FileObject]; FileObject
0x14005411a  mov     rcx, [rsp+0A8h+InitiatingInstance]; InitiatingInstance
0x140054122  mov     [rsp+0A8h+CallbackContext], r8; CallbackContext
0x140054127  mov     [rsp+0A8h+CallbackRoutine], r8; CallbackRoutine
0x14005412c  mov     [rsp+0A8h+BytesWritten], rax; BytesWritten
0x140054131  mov     rax, [rsi+18h]
0x140054135  mov     dword ptr [rsp+0A8h+Flags], r8d; char *
0x14005413a  mov     r8, r12; ByteOffset
0x14005413d  mov     [rsp+0A8h+Buffer], rax; Buffer
0x140054142  call    cs:__imp_FltWriteFile
0x140054149  nop     dword ptr [rax+rax+00h]
0x14005414e  mov     ebx, eax
0x140054150  test    eax, eax
0x140054152  jns     short loc_14005417D
0x140054154  lea     rax, aApiWritingPayl; "API: Writing payload record"
0x14005415b  mov     r8, 4B700170658h; struct UnionFs::StackEventTracer *
0x140054165  lea     r9, aUnionfsUfspers_23; "UnionFs::UfsPersistenceManager::WritePa"...
0x14005416c  mov     [rsp+0A8h+Buffer], rax; char *
0x140054171  mov     rdx, r14; int
0x140054174  mov     ecx, ebx; this
0x140054176  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005417b  jmp     short loc_1400541B7
0x14005417d  mov     byte ptr [r13+0], 1
0x140054182  xor     eax, eax
0x140054184  jmp     short loc_1400541B9
0x140054186  mov     rdx, [rsp+0A8h+arg_38]; int
0x14005418e  lea     rax, aOriginWriteOff; "ORIGIN: Write offset not aligned to chu"...
0x140054195  mov     ebx, 0C000000Dh
0x14005419a  mov     [rsp+0A8h+Buffer], rax; char *
0x14005419f  mov     ecx, ebx; this
0x1400541a1  lea     r9, aUnionfsUfspers_23; "UnionFs::UfsPersistenceManager::WritePa"...
0x1400541a8  mov     r8, 32C00170610h; struct UnionFs::StackEventTracer *
0x1400541b2  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400541b7  mov     eax, ebx
0x1400541b9  add     rsp, 68h
0x1400541bd  pop     r15
0x1400541bf  pop     r14
0x1400541c1  pop     r13
0x1400541c3  pop     r12
0x1400541c5  pop     rdi
0x1400541c6  pop     rsi
0x1400541c7  pop     rbp
0x1400541c8  pop     rbx
0x1400541c9  retn
```
