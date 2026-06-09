# Streaming::Reader::ReadFile(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)

- ea: `0x140009d98`
- end: `0x14000a144`
- name: `?ReadFile@Reader@Streaming@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z`
- size: `940`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140001ce0`

## callees

- `0x140005e3c`
- `0x140009d98`
- `0x14000a1ac`
- `0x14000db88`
- `0x14000fab8`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015af0`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140009e88`
- `ntoskrnl!DbgPrint` at `0x140009ebd`
- `ntoskrnl!DbgPrint` at `0x140009e88`
- `ntoskrnl!DbgPrint` at `0x140009ebd`
- `ntoskrnl!EtwActivityIdControl` at `0x140009dd9`
- `ntoskrnl!EtwActivityIdControl` at `0x140009dd9`
- `FLTMGR!FltReleaseContext` at `0x14000a0b6`
- `FLTMGR!FltReleaseContext` at `0x14000a0f2`
- `FLTMGR!FltReleaseContext` at `0x14000a0b6`
- `FLTMGR!FltReleaseContext` at `0x14000a0f2`

## string_xrefs

- `0x140009e81`: `safe to read file %wZ , offset = %x, Length = %x \n`
- `0x140009ef8`: `Reader::ReadFile() - New stream fault requested. File name: %s, Offset: %lld , Length %ld, Status 0x%08X.`
- `0x14000a004`: `Reader::ReadFile() - Failed to create a stream fault request. File name: %s, Offset: %lld , Length %ld, Status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Reader::ReadFile(struct _FLT_INSTANCE *a1, __int64 a2, __int64 a3, __int64 a4)
{
  union _LARGE_INTEGER *v8; // rax
  unsigned int LowPart; // r8d
  union _LARGE_INTEGER v10; // rdx
  unsigned __int8 v11; // al
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // edi
  __int64 v18; // rsi
  __int64 v19; // rbx
  _QWORD *CurrentActivityID; // rax
  Streaming::InstanceContextFactory *v21; // rcx
  volatile signed __int32 *v22; // rbx
  volatile signed __int32 *v23; // rbx
  int StreamFault; // r12d
  __int64 v25; // rcx
  int v26; // edi
  __int64 v27; // rsi
  __int64 v28; // rbx
  _QWORD *v29; // rax
  volatile signed __int32 *v30; // rbx
  volatile signed __int32 *v31; // rbx
  PFLT_CONTEXT v32; // rcx
  int v33; // [rsp+28h] [rbp-61h]
  __int64 v34; // [rsp+28h] [rbp-61h]
  int v35; // [rsp+30h] [rbp-59h]
  __int64 v36; // [rsp+30h] [rbp-59h]
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v38[8]; // [rsp+48h] [rbp-41h] BYREF
  volatile signed __int32 *v39; // [rsp+50h] [rbp-39h]
  _OWORD v40[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v41; // [rsp+80h] [rbp-9h]
  GUID ActivityId; // [rsp+88h] [rbp-1h] BYREF

  v41 = a2;
  EtwActivityIdControl(3u, &ActivityId);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      StrmFlt_IRP_READ_START,
      &ActivityId);
  if ( (*(_DWORD *)a3 & 2) != 0 )
  {
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McTemplateK0_EtwWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        StrmFlt_IRP_READ_STOP,
        &ActivityId);
    return 3;
  }
  v8 = *(union _LARGE_INTEGER **)(a3 + 16);
  LowPart = v8[3].LowPart;
  if ( !LowPart )
    goto LABEL_11;
  v10 = v8[5];
  if ( v10.QuadPart >= *(_QWORD *)(*(_QWORD *)a4 + 80LL) )
    goto LABEL_11;
  v11 = Streaming::Context::StreamingBitMap::IsSafeToRead(*(PRTL_BITMAP *)(*(_QWORD *)a4 + 88LL), v10, LowPart);
  v12 = *(_QWORD *)a4;
  v13 = *(_QWORD *)(a3 + 16);
  v14 = *(unsigned int *)(v13 + 24);
  v15 = *(unsigned int *)(v13 + 40);
  v40[0] = *(_OWORD *)(*(_QWORD *)a4 + 48LL);
  v40[1] = *(_OWORD *)(v12 + 64);
  if ( v11 )
  {
    DbgPrint("safe to read file %wZ , offset = %x, Length = %x \n", v40, v15, v14);
LABEL_11:
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McTemplateK0_EtwWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        StrmFlt_IRP_READ_STOP,
        &ActivityId);
    return 1;
  }
  DbgPrint("start stream fault file %wZ , offset = %x, Length = %x \n", v40, v15, v14);
  v16 = *(_QWORD *)(a3 + 16);
  v17 = *(_DWORD *)(v16 + 24);
  v18 = *(_QWORD *)(v16 + 40);
  v19 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v40, *(_QWORD *)a4 + 32LL);
  CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v38);
  v35 = 0;
  v33 = v17;
  LogWrite(
    3,
    *CurrentActivityID,
    L"Reader::ReadFile() - New stream fault requested. File name: %s, Offset: %lld , Length %ld, Status 0x%08X.",
    v19,
    v18,
    v33,
    v35);
  v22 = v39;
  if ( v39 )
  {
    if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 16LL))(v22);
    }
  }
  v23 = (volatile signed __int32 *)*((_QWORD *)&v40[0] + 1);
  if ( *((_QWORD *)&v40[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v40[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 16LL))(v23);
    }
  }
  Context = 0;
  StreamFault = Streaming::InstanceContextFactory::GetContext(v21, a1, (struct Streaming::InstanceContext *)&Context);
  if ( StreamFault >= 0
    && (StreamFault = Streaming::StreamFaultManager::CreateStreamFault(
                        *((_QWORD *)Context + 31),
                        (_DWORD)a1,
                        v41,
                        a3,
                        a4),
        StreamFault >= 0) )
  {
    if ( Context )
      FltReleaseContext(Context);
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McTemplateK0_EtwWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        StrmFlt_IRP_READ_STOP,
        &ActivityId);
    return 2;
  }
  else
  {
    v25 = *(_QWORD *)(a3 + 16);
    v26 = *(_DWORD *)(v25 + 24);
    v27 = *(_QWORD *)(v25 + 40);
    v28 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v38, *(_QWORD *)a4 + 32LL);
    v29 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v40);
    LODWORD(v36) = StreamFault;
    LODWORD(v34) = v26;
    LogWrite(
      1,
      *v29,
      L"Reader::ReadFile() - Failed to create a stream fault request. File name: %s, Offset: %lld , Length %ld, Status 0x%08X.",
      v28,
      v27,
      v34,
      v36);
    v30 = (volatile signed __int32 *)*((_QWORD *)&v40[0] + 1);
    if ( *((_QWORD *)&v40[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v40[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 16LL))(v30);
      }
    }
    v31 = v39;
    if ( v39 )
    {
      if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 16LL))(v31);
      }
    }
    v32 = Context;
    *(_QWORD *)(a3 + 32) = 0;
    *(_DWORD *)(a3 + 24) = StreamFault;
    if ( v32 )
      FltReleaseContext(v32);
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McTemplateK0_EtwWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        StrmFlt_IRP_READ_STOP,
        &ActivityId);
    return 4;
  }
}

```

## disassembly

```asm
0x140009d98  push    rbp
0x140009d9a  push    rbx
0x140009d9b  push    rsi
0x140009d9c  push    rdi
0x140009d9d  push    r12
0x140009d9f  push    r13
0x140009da1  push    r14
0x140009da3  push    r15
0x140009da5  lea     rbp, [rsp-1Fh]
0x140009daa  sub     rsp, 0A8h
0x140009db1  mov     rax, cs:__security_cookie
0x140009db8  xor     rax, rsp
0x140009dbb  mov     [rbp+57h+var_48], rax
0x140009dbf  mov     [rbp+57h+var_60], rdx
0x140009dc3  mov     r13, rcx
0x140009dc6  mov     r12d, 3
0x140009dcc  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x140009dd0  mov     ecx, r12d; ControlCode
0x140009dd3  mov     r15, r9
0x140009dd6  mov     r14, r8
0x140009dd9  call    cs:__imp_EtwActivityIdControl
0x140009de0  nop     dword ptr [rax+rax+00h]
0x140009de5  lea     ebx, [r12-2]
0x140009dea  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, bl
0x140009df0  lea     rdi, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140009df7  jz      short loc_140009E0C
0x140009df9  lea     r8, [rbp+57h+ActivityId]
0x140009dfd  mov     rcx, rdi
0x140009e00  lea     rdx, StrmFlt_IRP_READ_START
0x140009e07  call    McTemplateK0_EtwWriteTransfer
0x140009e0c  mov     edx, [r14]
0x140009e0f  test    dl, 2
0x140009e12  jz      short loc_140009E37
0x140009e14  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, bl
0x140009e1a  jz      short loc_140009E2F
0x140009e1c  lea     r8, [rbp+57h+ActivityId]
0x140009e20  mov     rcx, rdi
0x140009e23  lea     rdx, StrmFlt_IRP_READ_STOP
0x140009e2a  call    McTemplateK0_EtwWriteTransfer
0x140009e2f  mov     eax, r12d
0x140009e32  jmp     loc_14000A123
0x140009e37  mov     rax, [r14+10h]
0x140009e3b  mov     r8d, [rax+18h]; unsigned int
0x140009e3f  test    r8d, r8d
0x140009e42  jz      short loc_140009E94
0x140009e44  mov     rcx, [r15]
0x140009e47  mov     rdx, [rax+28h]; union _LARGE_INTEGER
0x140009e4b  cmp     rdx, [rcx+50h]
0x140009e4f  jge     short loc_140009E94
0x140009e51  mov     rcx, [rcx+58h]; BitMapHeader
0x140009e55  call    ?IsSafeToRead@StreamingBitMap@Context@Streaming@@QEAAET_LARGE_INTEGER@@K@Z; Streaming::Context::StreamingBitMap::IsSafeToRead(_LARGE_INTEGER,ulong)
0x140009e5a  mov     rcx, [r15]
0x140009e5d  lea     rdx, [rbp+57h+var_80]
0x140009e61  mov     r8, [r14+10h]
0x140009e65  movups  xmm0, xmmword ptr [rcx+30h]
0x140009e69  mov     r9d, [r8+18h]
0x140009e6d  mov     r8d, [r8+28h]
0x140009e71  movaps  [rbp+57h+var_80], xmm0
0x140009e75  movups  xmm1, xmmword ptr [rcx+40h]
0x140009e79  movaps  [rbp+57h+var_70], xmm1
0x140009e7d  test    al, al
0x140009e7f  jz      short loc_140009EB6
0x140009e81  lea     rcx, Format; "safe to read file %wZ , offset = %x, Le"...
0x140009e88  call    cs:__imp_DbgPrint
0x140009e8f  nop     dword ptr [rax+rax+00h]
0x140009e94  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, bl
0x140009e9a  jz      short loc_140009EAF
0x140009e9c  lea     r8, [rbp+57h+ActivityId]
0x140009ea0  mov     rcx, rdi
0x140009ea3  lea     rdx, StrmFlt_IRP_READ_STOP
0x140009eaa  call    McTemplateK0_EtwWriteTransfer
0x140009eaf  mov     eax, ebx
0x140009eb1  jmp     loc_14000A123
0x140009eb6  lea     rcx, aStartStreamFau; "start stream fault file %wZ , offset = "...
0x140009ebd  call    cs:__imp_DbgPrint
0x140009ec4  nop     dword ptr [rax+rax+00h]
0x140009ec9  mov     rax, [r14+10h]
0x140009ecd  lea     rcx, [rbp+57h+var_80]
0x140009ed1  mov     rdx, [r15]
0x140009ed4  add     rdx, 20h ; ' '
0x140009ed8  mov     edi, [rax+18h]
0x140009edb  mov     rsi, [rax+28h]
0x140009edf  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140009ee4  lea     rcx, [rbp+57h+var_98]
0x140009ee8  mov     rbx, [rax]
0x140009eeb  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140009ef0  mov     [rsp+0E0h+var_B0], 0
0x140009ef8  lea     r8, aReaderReadfile; "Reader::ReadFile() - New stream fault r"...
0x140009eff  mov     dword ptr [rsp+0E0h+var_B8], edi
0x140009f03  mov     r9, rbx
0x140009f06  mov     ecx, r12d
0x140009f09  mov     [rsp+0E0h+var_C0], rsi
0x140009f0e  mov     rdx, [rax]
0x140009f11  call    LogWrite
0x140009f16  mov     rbx, [rbp+57h+var_90]
0x140009f1a  or      edi, 0FFFFFFFFh
0x140009f1d  test    rbx, rbx
0x140009f20  jz      short loc_140009F56
0x140009f22  mov     eax, edi
0x140009f24  lock xadd [rbx+8], eax
0x140009f29  add     eax, edi
0x140009f2b  jnz     short loc_140009F56
0x140009f2d  mov     rax, [rbx]
0x140009f30  mov     rcx, rbx
0x140009f33  mov     rax, [rax+8]
0x140009f37  call    _guard_dispatch_icall
0x140009f3c  mov     eax, edi
0x140009f3e  lock xadd [rbx+0Ch], eax
0x140009f43  add     eax, edi
0x140009f45  jnz     short loc_140009F56
0x140009f47  mov     rax, [rbx]
0x140009f4a  mov     rcx, rbx
0x140009f4d  mov     rax, [rax+10h]
0x140009f51  call    _guard_dispatch_icall
0x140009f56  mov     rbx, qword ptr [rbp+57h+var_80+8]
0x140009f5a  test    rbx, rbx
0x140009f5d  jz      short loc_140009F93
0x140009f5f  mov     eax, edi
0x140009f61  lock xadd [rbx+8], eax
0x140009f66  add     eax, edi
0x140009f68  jnz     short loc_140009F93
0x140009f6a  mov     rax, [rbx]
0x140009f6d  mov     rcx, rbx
0x140009f70  mov     rax, [rax+8]
0x140009f74  call    _guard_dispatch_icall
0x140009f79  mov     eax, edi
0x140009f7b  lock xadd [rbx+0Ch], eax
0x140009f80  add     eax, edi
0x140009f82  jnz     short loc_140009F93
0x140009f84  mov     rax, [rbx]
0x140009f87  mov     rcx, rbx
0x140009f8a  mov     rax, [rax+10h]
0x140009f8e  call    _guard_dispatch_icall
0x140009f93  lea     r8, [rbp+57h+Context]; struct Streaming::InstanceContext *
0x140009f97  mov     [rbp+57h+Context], 0
0x140009f9f  mov     rdx, r13; struct _FLT_INSTANCE *
0x140009fa2  call    ?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)
0x140009fa7  mov     r12d, eax
0x140009faa  test    eax, eax
0x140009fac  js      short loc_140009FD8
0x140009fae  mov     rcx, [rbp+57h+Context]
0x140009fb2  mov     r9, r14
0x140009fb5  mov     r8, [rbp+57h+var_60]
0x140009fb9  mov     rdx, r13
0x140009fbc  mov     [rsp+0E0h+var_C0], r15
0x140009fc1  mov     rcx, [rcx+0F8h]
0x140009fc8  call    ?CreateStreamFault@StreamFaultManager@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::StreamFaultManager::CreateStreamFault(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x140009fcd  mov     r12d, eax
0x140009fd0  test    eax, eax
0x140009fd2  jns     loc_14000A0E9
0x140009fd8  mov     rcx, [r14+10h]
0x140009fdc  mov     rdx, [r15]
0x140009fdf  add     rdx, 20h ; ' '
0x140009fe3  mov     edi, [rcx+18h]
0x140009fe6  mov     rsi, [rcx+28h]
0x140009fea  lea     rcx, [rbp+57h+var_98]
0x140009fee  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140009ff3  lea     rcx, [rbp+57h+var_80]
0x140009ff7  mov     rbx, [rax]
0x140009ffa  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140009fff  mov     [rsp+0E0h+var_B0], r12d
0x14000a004  lea     r8, aReaderReadfile_0; "Reader::ReadFile() - Failed to create a"...
0x14000a00b  mov     dword ptr [rsp+0E0h+var_B8], edi
0x14000a00f  mov     r9, rbx
0x14000a012  mov     ecx, 1
0x14000a017  mov     [rsp+0E0h+var_C0], rsi
0x14000a01c  mov     rdx, [rax]
0x14000a01f  call    LogWrite
0x14000a024  mov     rbx, qword ptr [rbp+57h+var_80+8]
0x14000a028  or      edi, 0FFFFFFFFh
0x14000a02b  test    rbx, rbx
0x14000a02e  jz      short loc_14000A064
0x14000a030  mov     eax, edi
0x14000a032  lock xadd [rbx+8], eax
0x14000a037  add     eax, edi
0x14000a039  jnz     short loc_14000A064
0x14000a03b  mov     rax, [rbx]
0x14000a03e  mov     rcx, rbx
0x14000a041  mov     rax, [rax+8]
0x14000a045  call    _guard_dispatch_icall
0x14000a04a  mov     eax, edi
0x14000a04c  lock xadd [rbx+0Ch], eax
0x14000a051  add     eax, edi
0x14000a053  jnz     short loc_14000A064
0x14000a055  mov     rax, [rbx]
0x14000a058  mov     rcx, rbx
0x14000a05b  mov     rax, [rax+10h]
0x14000a05f  call    _guard_dispatch_icall
0x14000a064  mov     rbx, [rbp+57h+var_90]
0x14000a068  test    rbx, rbx
0x14000a06b  jz      short loc_14000A0A1
0x14000a06d  mov     eax, edi
0x14000a06f  lock xadd [rbx+8], eax
0x14000a074  add     eax, edi
0x14000a076  jnz     short loc_14000A0A1
0x14000a078  mov     rax, [rbx]
0x14000a07b  mov     rcx, rbx
0x14000a07e  mov     rax, [rax+8]
0x14000a082  call    _guard_dispatch_icall
0x14000a087  mov     eax, edi
0x14000a089  lock xadd [rbx+0Ch], eax
0x14000a08e  add     eax, edi
0x14000a090  jnz     short loc_14000A0A1
0x14000a092  mov     rax, [rbx]
0x14000a095  mov     rcx, rbx
0x14000a098  mov     rax, [rax+10h]
0x14000a09c  call    _guard_dispatch_icall
0x14000a0a1  mov     rcx, [rbp+57h+Context]; Context
0x14000a0a5  mov     qword ptr [r14+20h], 0
0x14000a0ad  mov     [r14+18h], r12d
0x14000a0b1  test    rcx, rcx
0x14000a0b4  jz      short loc_14000A0C2
0x14000a0b6  call    cs:__imp_FltReleaseContext
0x14000a0bd  nop     dword ptr [rax+rax+00h]
0x14000a0c2  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14000a0c9  jz      short loc_14000A0E2
0x14000a0cb  lea     r8, [rbp+57h+ActivityId]
0x14000a0cf  lea     rdx, StrmFlt_IRP_READ_STOP
0x14000a0d6  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x14000a0dd  call    McTemplateK0_EtwWriteTransfer
0x14000a0e2  mov     eax, 4
0x14000a0e7  jmp     short loc_14000A123
0x14000a0e9  mov     rcx, [rbp+57h+Context]; Context
0x14000a0ed  test    rcx, rcx
0x14000a0f0  jz      short loc_14000A0FE
0x14000a0f2  call    cs:__imp_FltReleaseContext
0x14000a0f9  nop     dword ptr [rax+rax+00h]
0x14000a0fe  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14000a105  jz      short loc_14000A11E
0x14000a107  lea     r8, [rbp+57h+ActivityId]
0x14000a10b  lea     rdx, StrmFlt_IRP_READ_STOP
0x14000a112  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x14000a119  call    McTemplateK0_EtwWriteTransfer
0x14000a11e  mov     eax, 2
0x14000a123  mov     rcx, [rbp+57h+var_48]
0x14000a127  xor     rcx, rsp; StackCookie
0x14000a12a  call    __security_check_cookie
0x14000a12f  add     rsp, 0A8h
0x14000a136  pop     r15
0x14000a138  pop     r14
0x14000a13a  pop     r13
0x14000a13c  pop     r12
0x14000a13e  pop     rdi
0x14000a13f  pop     rsi
0x14000a140  pop     rbx
0x14000a141  pop     rbp
0x14000a142  retn
```
