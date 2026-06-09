# UnionFs::UfsPersistenceManager::WritePayloadsToFile(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsUnionCtx const &,utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>> const &,bool *,UnionFs::UfsPersistenceManager::WritePayloadRecordCtx &,UnionFs::StackEventTracer &)

- ea: `0x140054048`
- end: `0x14005434b`
- name: `?WritePayloadsToFile@UfsPersistenceManager@UnionFs@@IEBAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEBVUfsUnionCtx@2@AEBV?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@PEA_NAEAUWritePayloadRecordCtx@12@AEAVStackEventTracer@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1400508c4`
- `0x14005315c`

## callees

- `0x140053f10`
- `0x140054048`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14007bbd0`
- `0x14007bc40`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1400541cc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054261`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400541cc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140054261`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400541d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005426d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400541d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005426d`
- `FLTMGR!FltWriteFile` at `0x140054167`
- `FLTMGR!FltWriteFile` at `0x1400542c2`
- `FLTMGR!FltWriteFile` at `0x140054167`
- `FLTMGR!FltWriteFile` at `0x1400542c2`

## string_xrefs

- `0x14005430e`: `ORIGIN: Write offset not aligned to chunk size`
- `0x140054209`: `UnionFs::UfsPersistenceManager::WritePayloadsToFile`
- `0x140054232`: `UnionFs::UfsPersistenceManager::WritePayloadsToFile`
- `0x1400542e5`: `UnionFs::UfsPersistenceManager::WritePayloadsToFile`
- `0x140054321`: `UnionFs::UfsPersistenceManager::WritePayloadsToFile`

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
0x140054048  mov     r11, rsp
0x14005404b  mov     [r11+20h], r9
0x14005404f  mov     [r11+18h], r8
0x140054053  mov     [r11+10h], rdx
0x140054057  mov     [r11+8], rcx
0x14005405b  push    rbx
0x14005405c  push    rbp
0x14005405d  push    rsi
0x14005405e  push    rdi
0x14005405f  push    r12
0x140054061  push    r13
0x140054063  push    r14
0x140054065  push    r15
0x140054067  sub     rsp, 68h
0x14005406b  mov     rsi, [rsp+0A8h+Resource]
0x140054073  xor     r8d, r8d
0x140054076  mov     r13, [rsp+0A8h+arg_28]
0x14005407e  mov     rbp, r9
0x140054081  lea     r12, [rsi+8]
0x140054085  mov     [r13+0], r8b
0x140054089  mov     ecx, [r9+12Ch]
0x140054090  mov     rax, [r12]
0x140054094  cqo
0x140054096  mov     [rsp+0A8h+Length], ecx
0x14005409a  idiv    rcx
0x14005409d  mov     [rsp+0A8h+Size], rcx
0x1400540a2  test    rdx, rdx
0x1400540a5  jnz     loc_140054306
0x1400540ab  mov     rdi, [rsp+0A8h+arg_20]
0x1400540b3  mov     r15b, r8b
0x1400540b6  mov     r14, [rsp+0A8h+arg_38]
0x1400540be  mov     [r11+30h], r8d
0x1400540c2  mov     rbx, [rdi]
0x1400540c5  mov     rdi, [rdi+8]
0x1400540c9  cmp     rbx, rdi
0x1400540cc  jz      loc_140054280
0x1400540d2  mov     rcx, [rbx]
0x1400540d5  lea     rdx, [rsp+0A8h+Resource]
0x1400540dd  mov     rax, [rcx]
0x1400540e0  mov     rax, [rax+8]
0x1400540e4  call    _guard_dispatch_icall
0x1400540e9  mov     r8, [rbx]; struct UnionFs::UfsTablePayload *
0x1400540ec  mov     r9, rsi; struct UnionFs::UfsPersistenceManager::WritePayloadRecordCtx *
0x1400540ef  mov     rcx, [rsp+0A8h+arg_0]; this
0x1400540f7  mov     rdx, rbp; struct UnionFs::UfsUnionCtx *
0x1400540fa  mov     [rsp+0A8h+Buffer], r14; struct UnionFs::StackEventTracer *
0x1400540ff  call    ?WritePayloadToBuffer@UfsPersistenceManager@UnionFs@@IEBAJAEBVUfsUnionCtx@2@AEAVUfsTablePayload@2@AEAUWritePayloadRecordCtx@12@AEAVStackEventTracer@2@@Z; UnionFs::UfsPersistenceManager::WritePayloadToBuffer(UnionFs::UfsUnionCtx const &,UnionFs::UfsTablePayload &,UnionFs::UfsPersistenceManager::WritePayloadRecordCtx &,UnionFs::StackEventTracer &)
0x140054104  xor     r8d, r8d
0x140054107  mov     ebp, eax
0x140054109  test    eax, eax
0x14005410b  js      loc_140054221
0x140054111  mov     eax, [rsi]
0x140054113  test    al, 4
0x140054115  jz      loc_1400541B7
0x14005411b  mov     eax, [rsp+0A8h+Length]
0x14005411f  mov     r15b, 1
0x140054122  cmp     [rsi+14h], eax
0x140054125  jb      loc_1400541B7
0x14005412b  mov     r9d, [rsi+10h]; Length
0x14005412f  lea     rax, [rsp+0A8h+arg_28]
0x140054137  mov     rdx, [rsp+0A8h+FileObject]; FileObject
0x14005413f  mov     rcx, [rsp+0A8h+InitiatingInstance]; InitiatingInstance
0x140054147  mov     [rsp+0A8h+CallbackContext], r8; CallbackContext
0x14005414c  mov     [rsp+0A8h+CallbackRoutine], r8; CallbackRoutine
0x140054151  mov     [rsp+0A8h+BytesWritten], rax; BytesWritten
0x140054156  mov     rax, [rsi+18h]
0x14005415a  mov     dword ptr [rsp+0A8h+Flags], r8d; char *
0x14005415f  mov     r8, r12; ByteOffset
0x140054162  mov     [rsp+0A8h+Buffer], rax; Buffer
0x140054167  call    cs:__imp_FltWriteFile
0x14005416e  nop     dword ptr [rax+rax+00h]
0x140054173  mov     ebp, eax
0x140054175  test    eax, eax
0x140054177  js      short loc_1400541F8
0x140054179  mov     rcx, [rsi+18h]; void *
0x14005417d  mov     rbp, [rsp+0A8h+Size]
0x140054182  mov     r8, rbp; Size
0x140054185  lea     rdx, [rcx+rbp]; Src
0x140054189  call    memmove
0x14005418e  mov     rcx, [rsi+18h]
0x140054192  mov     r8, rbp; Size
0x140054195  add     rcx, rbp; void *
0x140054198  xor     edx, edx; Val
0x14005419a  call    memset
0x14005419f  mov     eax, [rsi+20h]
0x1400541a2  xor     r8d, r8d
0x1400541a5  add     [r12], rbp
0x1400541a9  mov     [rsi+4], r8d
0x1400541ad  mov     [rsi+14h], eax
0x1400541b0  mov     [r13+0], r15b
0x1400541b4  mov     r15b, r8b
0x1400541b7  mov     rcx, [rsp+0A8h+Resource]; Resource
0x1400541bf  mov     [rsp+0A8h+Resource], r8
0x1400541c7  test    rcx, rcx
0x1400541ca  jz      short loc_1400541E7
0x1400541cc  call    cs:__imp_ExReleaseResourceLite
0x1400541d3  nop     dword ptr [rax+rax+00h]
0x1400541d8  call    cs:__imp_KeLeaveCriticalRegion
0x1400541df  nop     dword ptr [rax+rax+00h]
0x1400541e4  xor     r8d, r8d
0x1400541e7  mov     rbp, [rsp+0A8h+arg_18]
0x1400541ef  add     rbx, 10h
0x1400541f3  jmp     loc_1400540C9
0x1400541f8  lea     rax, aApiWritingPayl; "API: Writing payload record"
0x1400541ff  mov     r8, 4B600170631h; struct UnionFs::StackEventTracer *
0x140054209  lea     r9, aUnionfsUfspers_23; "UnionFs::UfsPersistenceManager::WritePa"...
0x140054210  mov     [rsp+0A8h+Buffer], rax; char *
0x140054215  mov     rdx, r14; int
0x140054218  mov     ecx, ebp; this
0x14005421a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005421f  jmp     short loc_140054248
0x140054221  lea     rax, aPushWritingPay; "PUSH: Writing payload record"
0x140054228  mov     r8, 4B50017061Ch; struct UnionFs::StackEventTracer *
0x140054232  lea     r9, aUnionfsUfspers_23; "UnionFs::UfsPersistenceManager::WritePa"...
0x140054239  mov     [rsp+0A8h+Buffer], rax; char *
0x14005423e  mov     rdx, r14; int
0x140054241  mov     ecx, ebp; this
0x140054243  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140054248  mov     rcx, [rsp+0A8h+Resource]; Resource
0x140054250  mov     [rsp+0A8h+Resource], 0
0x14005425c  test    rcx, rcx
0x14005425f  jz      short loc_140054279
0x140054261  call    cs:__imp_ExReleaseResourceLite
0x140054268  nop     dword ptr [rax+rax+00h]
0x14005426d  call    cs:__imp_KeLeaveCriticalRegion
0x140054274  nop     dword ptr [rax+rax+00h]
0x140054279  mov     eax, ebp
0x14005427b  jmp     loc_140054339
0x140054280  test    r15b, r15b
0x140054283  jz      short loc_140054302
0x140054285  mov     r9d, [rsp+0A8h+Length]; Length
0x14005428a  lea     rax, [rsp+0A8h+arg_28]
0x140054292  mov     rdx, [rsp+0A8h+FileObject]; FileObject
0x14005429a  mov     rcx, [rsp+0A8h+InitiatingInstance]; InitiatingInstance
0x1400542a2  mov     [rsp+0A8h+CallbackContext], r8; CallbackContext
0x1400542a7  mov     [rsp+0A8h+CallbackRoutine], r8; CallbackRoutine
0x1400542ac  mov     [rsp+0A8h+BytesWritten], rax; BytesWritten
0x1400542b1  mov     rax, [rsi+18h]
0x1400542b5  mov     dword ptr [rsp+0A8h+Flags], r8d; char *
0x1400542ba  mov     r8, r12; ByteOffset
0x1400542bd  mov     [rsp+0A8h+Buffer], rax; Buffer
0x1400542c2  call    cs:__imp_FltWriteFile
0x1400542c9  nop     dword ptr [rax+rax+00h]
0x1400542ce  mov     ebx, eax
0x1400542d0  test    eax, eax
0x1400542d2  jns     short loc_1400542FD
0x1400542d4  lea     rax, aApiWritingPayl; "API: Writing payload record"
0x1400542db  mov     r8, 4B700170658h; struct UnionFs::StackEventTracer *
0x1400542e5  lea     r9, aUnionfsUfspers_23; "UnionFs::UfsPersistenceManager::WritePa"...
0x1400542ec  mov     [rsp+0A8h+Buffer], rax; char *
0x1400542f1  mov     rdx, r14; int
0x1400542f4  mov     ecx, ebx; this
0x1400542f6  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400542fb  jmp     short loc_140054337
0x1400542fd  mov     byte ptr [r13+0], 1
0x140054302  xor     eax, eax
0x140054304  jmp     short loc_140054339
0x140054306  mov     rdx, [rsp+0A8h+arg_38]; int
0x14005430e  lea     rax, aOriginWriteOff; "ORIGIN: Write offset not aligned to chu"...
0x140054315  mov     ebx, 0C000000Dh
0x14005431a  mov     [rsp+0A8h+Buffer], rax; char *
0x14005431f  mov     ecx, ebx; this
0x140054321  lea     r9, aUnionfsUfspers_23; "UnionFs::UfsPersistenceManager::WritePa"...
0x140054328  mov     r8, 32C00170610h; struct UnionFs::StackEventTracer *
0x140054332  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140054337  mov     eax, ebx
0x140054339  add     rsp, 68h
0x14005433d  pop     r15
0x14005433f  pop     r14
0x140054341  pop     r13
0x140054343  pop     r12
0x140054345  pop     rdi
0x140054346  pop     rsi
0x140054347  pop     rbp
0x140054348  pop     rbx
0x140054349  retn
```
