# Streaming::StreamFaultWriter::Execute(void)

- ea: `0x14000f244`
- end: `0x14000f6e1`
- name: `?Execute@StreamFaultWriter@Streaming@@QEAAJXZ`
- size: `1181`
- prototype: `__int64 __fastcall(Streaming::StreamFaultWriter *this, const wchar_t *, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x140006c08`
- `0x140006fe0`

## callees

- `0x1400030b8`
- `0x140004ab8`
- `0x14000984c`
- `0x14000b448`
- `0x14000f244`
- `0x140010f38`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000f2c2`
- `ntoskrnl!ZwClose` at `0x14000f346`
- `ntoskrnl!ZwClose` at `0x14000f2c2`
- `ntoskrnl!ZwClose` at `0x14000f346`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f310`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f310`
- `ntoskrnl!KeSetEvent` at `0x14000f688`
- `ntoskrnl!KeSetEvent` at `0x14000f688`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f6b6`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f6b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f2ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f331`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f2ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f331`
- `FLTMGR!FltFlushBuffers` at `0x14000f53d`
- `FLTMGR!FltFlushBuffers` at `0x14000f53d`
- `FLTMGR!FltClose` at `0x14000f69d`
- `FLTMGR!FltClose` at `0x14000f69d`

## string_xrefs

- `0x14000f3c0`: `StreamFaultWriter::StreamFaultWriter() - Streaming Filter could not open file for streaming file %s .Failure status 0x%08X.`
- `0x14000f48c`: `StreamFaultWriter::StreamFaultWriter() - StreamFaultWriter successfully wrote file: %s, offset: %lld, length: %ld, status 0x%08X`
- `0x14000f580`: `StreamFaultWriter::StreamFaultWriter() - StreamFaultWriter failed to write file: %s, offset: %lld, length: %ld, status: 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::StreamFaultWriter::Execute(
        Streaming::StreamFaultWriter *this,
        const wchar_t *a2,
        bool a3)
{
  char *v4; // r14
  int v5; // ebx
  NTSTATUS i; // edx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  struct Streaming::Context::StrmStreamContext *v13; // rdx
  NTSTATUS updated; // r15d
  __int64 v15; // rbx
  _QWORD *v16; // rax
  volatile signed __int32 *v17; // rsi
  int v18; // eax
  int v19; // esi
  __int64 v20; // rdx
  __int64 v21; // r12
  __int64 v22; // rbx
  _QWORD *v23; // rax
  volatile signed __int32 *v24; // rsi
  volatile signed __int32 *v25; // rsi
  struct _FILE_OBJECT *v26; // rsi
  __int64 v27; // r13
  struct _FLT_INSTANCE *v28; // r14
  __int64 v29; // rbx
  _QWORD *CurrentActivityID; // rax
  volatile signed __int32 *v31; // rsi
  volatile signed __int32 *v32; // rsi
  unsigned int v33; // esi
  Streaming::staging_operations **NullTerminated; // rax
  volatile signed __int32 *v35; // rsi
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-60h]
  __int64 v37; // [rsp+28h] [rbp-58h]
  __int64 v38; // [rsp+30h] [rbp-50h]
  bool v39; // [rsp+38h] [rbp-48h]
  _BYTE v40[8]; // [rsp+50h] [rbp-30h] BYREF
  volatile signed __int32 *v41; // [rsp+58h] [rbp-28h]
  _BYTE v42[8]; // [rsp+60h] [rbp-20h] BYREF
  PVOID P[3]; // [rsp+68h] [rbp-18h]
  wchar_t *v44; // [rsp+C0h] [rbp+40h] BYREF
  HANDLE FileHandle; // [rsp+C8h] [rbp+48h] BYREF
  PFILE_OBJECT FileObject; // [rsp+D0h] [rbp+50h] BYREF

  if ( (*((_DWORD *)this + 16) & 0x2000000) == 0 )
  {
    v4 = (char *)this + 8;
    goto LABEL_20;
  }
  v42[0] = 0;
  ::Timeout.QuadPart = -20000000;
  *(_OWORD *)P = 0;
  v5 = appv::shared::kernel::event::create((appv::shared::kernel::event *)v42, a2, a3);
  if ( v5 >= 0 )
  {
    v4 = (char *)this + 8;
    for ( i = 258;
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v4 + 248LL) + 208LL) && i == 258;
          i = KeWaitForSingleObject(P[0], Executive, 0, 0, &::Timeout) )
    {
      ;
    }
    if ( P[0] )
    {
      if ( v42[0] )
        ExFreePoolWithTag(P[0], 0);
      if ( P[1] )
        ZwClose(P[1]);
      *(_OWORD *)P = 0;
    }
LABEL_20:
    v8 = *(_QWORD *)v4;
    v9 = *(_QWORD *)this;
    FileObject = 0;
    FileHandle = 0;
    v10 = *(_QWORD *)(v8 + 16);
    v11 = *((_QWORD *)Streaming::gStrmFltData + 1);
    LODWORD(v44) = 0;
    v12 = Streaming::FileOperations::OpenFileForStreaming(v11, v10, (int)v9 + 64, (int)&FileObject, &FileHandle);
    v13 = *(struct Streaming::Context::StrmStreamContext **)this;
    updated = v12;
    if ( v12 >= 0 )
    {
      v18 = Streaming::PackageWriter::WriteToStreamableFile(
              *(struct _FLT_INSTANCE **)(*(_QWORD *)v4 + 16LL),
              v13,
              FileObject,
              *(union _LARGE_INTEGER *)((char *)this + 24),
              *((void **)this + 2),
              *((_DWORD *)this + 8),
              *(_DWORD *)(*(_QWORD *)v4 + 96LL),
              v39,
              (unsigned int *)&v44);
      v19 = *((_DWORD *)this + 8);
      v20 = *(_QWORD *)this + 64LL;
      v21 = *((_QWORD *)this + 3);
      updated = v18;
      if ( v18 < 0 )
      {
        v29 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v40, v20);
        CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v42);
        LODWORD(v38) = updated;
        LODWORD(v37) = v19;
        LogWrite(
          1,
          *CurrentActivityID,
          L"StreamFaultWriter::StreamFaultWriter() - StreamFaultWriter failed to write file: %s, offset: %lld, length: %ld"
           ", status: 0x%08X.",
          v29,
          v21,
          v37,
          v38);
        v31 = (volatile signed __int32 *)P[0];
        if ( P[0] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)P[0] + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
            if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 16LL))(v31);
          }
        }
        v32 = v41;
        if ( v41 )
        {
          if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
            if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 16LL))(v32);
          }
        }
      }
      else
      {
        v22 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v40, v20);
        v23 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v42);
        LODWORD(v38) = updated;
        LODWORD(v37) = v19;
        LogWrite(
          3,
          *v23,
          L"StreamFaultWriter::StreamFaultWriter() - StreamFaultWriter successfully wrote file: %s, offset: %lld, length: "
           "%ld, status 0x%08X",
          v22,
          v21,
          v37,
          v38);
        v24 = (volatile signed __int32 *)P[0];
        if ( P[0] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)P[0] + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
            if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 16LL))(v24);
          }
        }
        v25 = v41;
        if ( v41 )
        {
          if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 16LL))(v25);
          }
        }
        v26 = FileObject;
        v27 = *(_QWORD *)this;
        v28 = *(struct _FLT_INSTANCE **)(*(_QWORD *)v4 + 16LL);
        updated = FltFlushBuffers(v28, FileObject);
        if ( updated >= 0 )
          updated = Streaming::Context::StreamingBitmapBuilder::UpdateStreamingInformation(
                      v28,
                      v26,
                      *(struct Streaming::Context::StreamingBitMap **)(v27 + 88));
      }
      v33 = (unsigned int)v44;
      if ( !(_DWORD)v44 )
        goto LABEL_51;
      NullTerminated = (Streaming::staging_operations **)Streaming::Utils::GetNullTerminated(
                                                           v42,
                                                           *(_QWORD *)this + 32LL);
      Streaming::staging_operations::notify_file_progress(*NullTerminated, (const wchar_t *)v33);
    }
    else
    {
      v15 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v42, (char *)v13 + 64);
      v16 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v40);
      LODWORD(Timeout) = updated;
      LogWrite(
        1,
        *v16,
        L"StreamFaultWriter::StreamFaultWriter() - Streaming Filter could not open file for streaming file %s .Failure status 0x%08X.",
        v15,
        Timeout);
      v17 = v41;
      if ( v41 )
      {
        if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
    }
    v35 = (volatile signed __int32 *)P[0];
    if ( P[0] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)P[0] + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
        if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 16LL))(v35);
      }
    }
LABEL_51:
    *((_DWORD *)this + 9) = updated;
    KeSetEvent(*((PRKEVENT *)this + 6), 0, 0);
    if ( FileHandle )
    {
      FltClose(FileHandle);
      FileHandle = 0;
    }
    if ( FileObject )
      ObfDereferenceObject(FileObject);
    return (unsigned int)updated;
  }
  if ( P[0] )
  {
    if ( v42[0] )
      ExFreePoolWithTag(P[0], 0);
    if ( P[1] )
      ZwClose(P[1]);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000f244  mov     [rsp-38h+arg_18], rbx
0x14000f249  push    rbp
0x14000f24a  push    rsi
0x14000f24b  push    rdi
0x14000f24c  push    r12
0x14000f24e  push    r13
0x14000f250  push    r14
0x14000f252  push    r15
0x14000f254  mov     rbp, rsp
0x14000f257  sub     rsp, 80h
0x14000f25e  xor     r13d, r13d
0x14000f261  mov     rdi, rcx
0x14000f264  test    dword ptr [rcx+40h], 2000000h
0x14000f26b  jnz     short loc_14000F276
0x14000f26d  lea     r14, [rcx+8]
0x14000f271  jmp     loc_14000F35A
0x14000f276  xorps   xmm0, xmm0
0x14000f279  mov     [rbp+var_20], r13b
0x14000f27d  lea     rcx, [rbp+var_20]; this
0x14000f281  mov     qword ptr cs:Timeout, 0FFFFFFFFFECED300h
0x14000f28c  movdqu  xmmword ptr [rbp+P], xmm0
0x14000f291  call    ?create@event@kernel@shared@appv@@QEAAJPEB_W_N@Z; appv::shared::kernel::event::create(wchar_t const *,bool)
0x14000f296  mov     ebx, eax
0x14000f298  test    eax, eax
0x14000f29a  jns     short loc_14000F2D5
0x14000f29c  mov     rcx, [rbp+P]; P
0x14000f2a0  test    rcx, rcx
0x14000f2a3  jz      short loc_14000F2CE
0x14000f2a5  cmp     [rbp+var_20], r13b
0x14000f2a9  jz      short loc_14000F2B9
0x14000f2ab  xor     edx, edx; Tag
0x14000f2ad  call    cs:__imp_ExFreePoolWithTag
0x14000f2b4  nop     dword ptr [rax+rax+00h]
0x14000f2b9  mov     rcx, [rbp+P+8]; Handle
0x14000f2bd  test    rcx, rcx
0x14000f2c0  jz      short loc_14000F2CE
0x14000f2c2  call    cs:__imp_ZwClose
0x14000f2c9  nop     dword ptr [rax+rax+00h]
0x14000f2ce  mov     eax, ebx
0x14000f2d0  jmp     loc_14000F6C5
0x14000f2d5  mov     ebx, 102h
0x14000f2da  lea     r14, [rdi+8]
0x14000f2de  mov     edx, ebx
0x14000f2e0  mov     rax, [r14]
0x14000f2e3  mov     rcx, [rax+0F8h]
0x14000f2ea  mov     eax, [rcx+0D0h]
0x14000f2f0  test    eax, eax
0x14000f2f2  jz      short loc_14000F320
0x14000f2f4  cmp     edx, ebx
0x14000f2f6  jnz     short loc_14000F320
0x14000f2f8  mov     rcx, [rbp+P]; Object
0x14000f2fc  lea     rax, Timeout
0x14000f303  xor     r9d, r9d; Alertable
0x14000f306  mov     [rsp+80h+Timeout], rax; Timeout
0x14000f30b  xor     r8d, r8d; WaitMode
0x14000f30e  xor     edx, edx; WaitReason
0x14000f310  call    cs:__imp_KeWaitForSingleObject
0x14000f317  nop     dword ptr [rax+rax+00h]
0x14000f31c  mov     edx, eax
0x14000f31e  jmp     short loc_14000F2E0
0x14000f320  mov     rcx, [rbp+P]; P
0x14000f324  test    rcx, rcx
0x14000f327  jz      short loc_14000F35A
0x14000f329  cmp     [rbp+var_20], r13b
0x14000f32d  jz      short loc_14000F33D
0x14000f32f  xor     edx, edx; Tag
0x14000f331  call    cs:__imp_ExFreePoolWithTag
0x14000f338  nop     dword ptr [rax+rax+00h]
0x14000f33d  mov     rcx, [rbp+P+8]; Handle
0x14000f341  test    rcx, rcx
0x14000f344  jz      short loc_14000F352
0x14000f346  call    cs:__imp_ZwClose
0x14000f34d  nop     dword ptr [rax+rax+00h]
0x14000f352  xorps   xmm0, xmm0
0x14000f355  movdqu  xmmword ptr [rbp+P], xmm0
0x14000f35a  mov     rdx, [r14]
0x14000f35d  lea     rax, [rbp+FileHandle]
0x14000f361  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x14000f368  lea     r9, [rbp+FileObject]; int
0x14000f36c  mov     r8, [rdi]
0x14000f36f  mov     [rbp+FileObject], r13
0x14000f373  add     r8, 40h ; '@'; int
0x14000f377  mov     [rbp+FileHandle], r13
0x14000f37b  mov     rdx, [rdx+10h]; int
0x14000f37f  mov     rcx, [rcx+8]; int
0x14000f383  mov     dword ptr [rbp+arg_0], r13d
0x14000f387  mov     [rsp+80h+Timeout], rax; FileHandle
0x14000f38c  call    ?OpenFileForStreaming@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEBU_UNICODE_STRING@@AEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@789@@Z; Streaming::FileOperations::OpenFileForStreaming(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &)
0x14000f391  mov     rdx, [rdi]; struct Streaming::Context::StrmStreamContext *
0x14000f394  mov     r15d, eax
0x14000f397  test    eax, eax
0x14000f399  jns     loc_14000F425
0x14000f39f  add     rdx, 40h ; '@'
0x14000f3a3  lea     rcx, [rbp+var_20]
0x14000f3a7  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000f3ac  lea     rcx, [rbp+var_30]
0x14000f3b0  mov     rbx, [rax]
0x14000f3b3  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000f3b8  mov     r9, rbx
0x14000f3bb  mov     dword ptr [rsp+80h+Timeout], r15d
0x14000f3c0  lea     r8, aStreamfaultwri_1; "StreamFaultWriter::StreamFaultWriter() "...
0x14000f3c7  mov     ecx, 1
0x14000f3cc  mov     rdx, [rax]
0x14000f3cf  call    LogWrite
0x14000f3d4  mov     rsi, [rbp+var_28]
0x14000f3d8  or      ebx, 0FFFFFFFFh
0x14000f3db  test    rsi, rsi
0x14000f3de  jz      loc_14000F63E
0x14000f3e4  mov     eax, ebx
0x14000f3e6  lock xadd [rsi+8], eax
0x14000f3eb  add     eax, ebx
0x14000f3ed  jnz     loc_14000F63E
0x14000f3f3  mov     rax, [rsi]
0x14000f3f6  mov     rcx, rsi
0x14000f3f9  mov     rax, [rax+8]
0x14000f3fd  call    _guard_dispatch_icall
0x14000f402  mov     eax, ebx
0x14000f404  lock xadd [rsi+0Ch], eax
0x14000f409  add     eax, ebx
0x14000f40b  jnz     loc_14000F63E
0x14000f411  mov     rax, [rsi]
0x14000f414  mov     rcx, rsi
0x14000f417  mov     rax, [rax+10h]
0x14000f41b  call    _guard_dispatch_icall
0x14000f420  jmp     loc_14000F63E
0x14000f425  mov     rcx, [r14]
0x14000f428  lea     rax, [rbp+arg_0]
0x14000f42c  mov     r9, [rdi+18h]; union _LARGE_INTEGER
0x14000f430  mov     r8, [rbp+FileObject]; struct _FILE_OBJECT *
0x14000f434  mov     [rsp+80h+var_40], rax; unsigned int *
0x14000f439  mov     eax, [rcx+60h]
0x14000f43c  mov     rcx, [rcx+10h]; struct _FLT_INSTANCE *
0x14000f440  mov     dword ptr [rsp+80h+var_50], eax; unsigned int
0x14000f444  mov     eax, [rdi+20h]
0x14000f447  mov     dword ptr [rsp+80h+var_58], eax; unsigned int
0x14000f44b  mov     rax, [rdi+10h]
0x14000f44f  mov     [rsp+80h+Timeout], rax; void *
0x14000f454  call    ?WriteToStreamableFile@PackageWriter@Streaming@@SAJPEAU_FLT_INSTANCE@@PEAUStrmStreamContext@Context@2@AEAU_FILE_OBJECT@@T_LARGE_INTEGER@@PEAXKK_NAEAK@Z; Streaming::PackageWriter::WriteToStreamableFile(_FLT_INSTANCE *,Streaming::Context::StrmStreamContext *,_FILE_OBJECT &,_LARGE_INTEGER,void *,ulong,ulong,bool,ulong &)
0x14000f459  mov     rdx, [rdi]
0x14000f45c  lea     rcx, [rbp+var_30]
0x14000f460  mov     esi, [rdi+20h]
0x14000f463  add     rdx, 40h ; '@'
0x14000f467  mov     r12, [rdi+18h]
0x14000f46b  mov     r15d, eax
0x14000f46e  test    eax, eax
0x14000f470  js      loc_14000F56A
0x14000f476  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000f47b  lea     rcx, [rbp+var_20]
0x14000f47f  mov     rbx, [rax]
0x14000f482  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000f487  mov     dword ptr [rsp+80h+var_50], r15d
0x14000f48c  lea     r8, aStreamfaultwri; "StreamFaultWriter::StreamFaultWriter() "...
0x14000f493  mov     dword ptr [rsp+80h+var_58], esi
0x14000f497  mov     r9, rbx
0x14000f49a  mov     ecx, 3
0x14000f49f  mov     [rsp+80h+Timeout], r12
0x14000f4a4  mov     rdx, [rax]
0x14000f4a7  call    LogWrite
0x14000f4ac  mov     rsi, [rbp+P]
0x14000f4b0  or      ebx, 0FFFFFFFFh
0x14000f4b3  test    rsi, rsi
0x14000f4b6  jz      short loc_14000F4EC
0x14000f4b8  mov     eax, ebx
0x14000f4ba  lock xadd [rsi+8], eax
0x14000f4bf  add     eax, ebx
0x14000f4c1  jnz     short loc_14000F4EC
0x14000f4c3  mov     rax, [rsi]
0x14000f4c6  mov     rcx, rsi
0x14000f4c9  mov     rax, [rax+8]
0x14000f4cd  call    _guard_dispatch_icall
0x14000f4d2  mov     eax, ebx
0x14000f4d4  lock xadd [rsi+0Ch], eax
0x14000f4d9  add     eax, ebx
0x14000f4db  jnz     short loc_14000F4EC
0x14000f4dd  mov     rax, [rsi]
0x14000f4e0  mov     rcx, rsi
0x14000f4e3  mov     rax, [rax+10h]
0x14000f4e7  call    _guard_dispatch_icall
0x14000f4ec  mov     rsi, [rbp+var_28]
0x14000f4f0  test    rsi, rsi
0x14000f4f3  jz      short loc_14000F529
0x14000f4f5  mov     eax, ebx
0x14000f4f7  lock xadd [rsi+8], eax
0x14000f4fc  add     eax, ebx
0x14000f4fe  jnz     short loc_14000F529
0x14000f500  mov     rax, [rsi]
0x14000f503  mov     rcx, rsi
0x14000f506  mov     rax, [rax+8]
0x14000f50a  call    _guard_dispatch_icall
0x14000f50f  mov     eax, ebx
0x14000f511  lock xadd [rsi+0Ch], eax
0x14000f516  add     eax, ebx
0x14000f518  jnz     short loc_14000F529
0x14000f51a  mov     rax, [rsi]
0x14000f51d  mov     rcx, rsi
0x14000f520  mov     rax, [rax+10h]
0x14000f524  call    _guard_dispatch_icall
0x14000f529  mov     rax, [r14]
0x14000f52c  mov     rsi, [rbp+FileObject]
0x14000f530  mov     r13, [rdi]
0x14000f533  mov     rdx, rsi; FileObject
0x14000f536  mov     r14, [rax+10h]
0x14000f53a  mov     rcx, r14; Instance
0x14000f53d  call    cs:__imp_FltFlushBuffers
0x14000f544  nop     dword ptr [rax+rax+00h]
0x14000f549  mov     r15d, eax
0x14000f54c  test    eax, eax
0x14000f54e  js      short loc_14000F562
0x14000f550  mov     r8, [r13+58h]; struct Streaming::Context::StreamingBitMap *
0x14000f554  mov     rdx, rsi; FileObject
0x14000f557  mov     rcx, r14; Instance
0x14000f55a  call    ?UpdateStreamingInformation@StreamingBitmapBuilder@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAVStreamingBitMap@23@@Z; Streaming::Context::StreamingBitmapBuilder::UpdateStreamingInformation(_FLT_INSTANCE *,_FILE_OBJECT &,Streaming::Context::StreamingBitMap &)
0x14000f55f  mov     r15d, eax
0x14000f562  xor     r13d, r13d
0x14000f565  jmp     loc_14000F61D
0x14000f56a  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000f56f  lea     rcx, [rbp+var_20]
0x14000f573  mov     rbx, [rax]
0x14000f576  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000f57b  mov     dword ptr [rsp+80h+var_50], r15d
0x14000f580  lea     r8, aStreamfaultwri_0; "StreamFaultWriter::StreamFaultWriter() "...
0x14000f587  mov     dword ptr [rsp+80h+var_58], esi
0x14000f58b  mov     r9, rbx
0x14000f58e  mov     ecx, 1
0x14000f593  mov     [rsp+80h+Timeout], r12
0x14000f598  mov     rdx, [rax]
0x14000f59b  call    LogWrite
0x14000f5a0  mov     rsi, [rbp+P]
0x14000f5a4  or      ebx, 0FFFFFFFFh
0x14000f5a7  test    rsi, rsi
0x14000f5aa  jz      short loc_14000F5E0
0x14000f5ac  mov     eax, ebx
0x14000f5ae  lock xadd [rsi+8], eax
0x14000f5b3  add     eax, ebx
0x14000f5b5  jnz     short loc_14000F5E0
0x14000f5b7  mov     rax, [rsi]
0x14000f5ba  mov     rcx, rsi
0x14000f5bd  mov     rax, [rax+8]
0x14000f5c1  call    _guard_dispatch_icall
0x14000f5c6  mov     eax, ebx
0x14000f5c8  lock xadd [rsi+0Ch], eax
0x14000f5cd  add     eax, ebx
0x14000f5cf  jnz     short loc_14000F5E0
0x14000f5d1  mov     rax, [rsi]
0x14000f5d4  mov     rcx, rsi
0x14000f5d7  mov     rax, [rax+10h]
0x14000f5db  call    _guard_dispatch_icall
0x14000f5e0  mov     rsi, [rbp+var_28]
0x14000f5e4  test    rsi, rsi
0x14000f5e7  jz      short loc_14000F61D
0x14000f5e9  mov     eax, ebx
0x14000f5eb  lock xadd [rsi+8], eax
0x14000f5f0  add     eax, ebx
0x14000f5f2  jnz     short loc_14000F61D
0x14000f5f4  mov     rax, [rsi]
0x14000f5f7  mov     rcx, rsi
0x14000f5fa  mov     rax, [rax+8]
0x14000f5fe  call    _guard_dispatch_icall
0x14000f603  mov     eax, ebx
0x14000f605  lock xadd [rsi+0Ch], eax
0x14000f60a  add     eax, ebx
0x14000f60c  jnz     short loc_14000F61D
0x14000f60e  mov     rax, [rsi]
0x14000f611  mov     rcx, rsi
0x14000f614  mov     rax, [rax+10h]
0x14000f618  call    _guard_dispatch_icall
0x14000f61d  mov     esi, dword ptr [rbp+arg_0]
0x14000f620  test    esi, esi
0x14000f622  jz      short loc_14000F67B
0x14000f624  mov     rdx, [rdi]
0x14000f627  lea     rcx, [rbp+var_20]
0x14000f62b  add     rdx, 20h ; ' '
0x14000f62f  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000f634  mov     edx, esi; wchar_t *
0x14000f636  mov     rcx, [rax]; this
0x14000f639  call    ?notify_file_progress@staging_operations@Streaming@@YAJPEB_WK@Z; Streaming::staging_operations::notify_file_progress(wchar_t const *,ulong)
0x14000f63e  mov     rsi, [rbp+P]
0x14000f642  test    rsi, rsi
0x14000f645  jz      short loc_14000F67B
0x14000f647  mov     eax, ebx
0x14000f649  lock xadd [rsi+8], eax
0x14000f64e  add     eax, ebx
0x14000f650  jnz     short loc_14000F67B
0x14000f652  mov     rax, [rsi]
0x14000f655  mov     rcx, rsi
0x14000f658  mov     rax, [rax+8]
0x14000f65c  call    _guard_dispatch_icall
0x14000f661  mov     eax, ebx
0x14000f663  lock xadd [rsi+0Ch], eax
0x14000f668  add     eax, ebx
0x14000f66a  jnz     short loc_14000F67B
0x14000f66c  mov     rax, [rsi]
0x14000f66f  mov     rcx, rsi
0x14000f672  mov     rax, [rax+10h]
0x14000f676  call    _guard_dispatch_icall
0x14000f67b  mov     [rdi+24h], r15d
0x14000f67f  xor     r8d, r8d; Wait
0x14000f682  mov     rcx, [rdi+30h]; Event
0x14000f686  xor     edx, edx; Increment
0x14000f688  call    cs:__imp_KeSetEvent
  ... truncated ...
```
