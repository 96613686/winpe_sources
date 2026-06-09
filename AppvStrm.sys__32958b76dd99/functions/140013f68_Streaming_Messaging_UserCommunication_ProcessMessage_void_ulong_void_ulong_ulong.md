# Streaming::Messaging::UserCommunication::ProcessMessage(void *,ulong,void *,ulong,ulong *)

- ea: `0x140013f68`
- end: `0x14001435e`
- name: `?ProcessMessage@UserCommunication@Messaging@Streaming@@QEAAJPEAXK0KPEAK@Z`
- size: `1014`
- prototype: `__int64 __fastcall(Streaming::Messaging::UserCommunication *this, Streaming::staging_operations *, unsigned int, _DWORD *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140013f40`

## callees

- `0x14000a1ac`
- `0x140010c64`
- `0x140010df4`
- `0x14001104c`
- `0x140011154`
- `0x140011384`
- `0x140011928`
- `0x140013f68`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015b30`

## string_xrefs

- `0x140013fe0`: `UserCommunication::ProcessMessage() - The streaming filter received a corrupted message, you system might be running a malicious application. Failure status 0x%08X.`
- `0x140014240`: `UserCommunication::ProcessMessage() - A create package file request is received.`
- `0x1400142dc`: `UserCommunication::ProcessMessage() - A create package file message failed. Failure Status 0x%08X.`
- `0x140014131`: `UserCommunication::ProcessMessage() - Streaming Filter received a write request.`
- `0x1400141cd`: `UserCommunication::ProcessMessage() - Streaming Filter failed the write request received from the streaming manager. Failure status 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Messaging::UserCommunication::ProcessMessage(
        Streaming::Messaging::UserCommunication *this,
        Streaming::staging_operations *a2,
        unsigned int a3,
        _DWORD *a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned int v6; // r14d
  _QWORD *CurrentActivityID; // rax
  unsigned int file; // edi
  volatile signed __int32 *v11; // rsi
  __int64 *v13; // rdx
  _QWORD *v14; // rax
  volatile signed __int32 *v15; // rdi
  _QWORD *v16; // rax
  volatile signed __int32 *v17; // rsi
  _QWORD *v18; // rax
  volatile signed __int32 *v19; // rdi
  _QWORD *v20; // rax
  volatile signed __int32 *v21; // rsi
  unsigned int v23; // [rsp+20h] [rbp-20h]
  unsigned int *v24; // [rsp+28h] [rbp-18h]
  _BYTE v25[8]; // [rsp+30h] [rbp-10h] BYREF
  volatile signed __int32 *v26; // [rsp+38h] [rbp-8h]

  v6 = (unsigned int)a4;
  *a6 = 0;
  if ( a3 < 8 )
  {
LABEL_9:
    CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v25);
    file = -1073741811;
    LogWrite(
      1,
      *CurrentActivityID,
      L"UserCommunication::ProcessMessage() - The streaming filter received a corrupted message, you system might be runni"
       "ng a malicious application. Failure status 0x%08X.",
      3221225485LL);
    v11 = v26;
    if ( v26 )
    {
      if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
    return file;
  }
  switch ( *(_DWORD *)a2 )
  {
    case 1:
      v18 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v25);
      LogWrite(3, *v18, L"UserCommunication::ProcessMessage() - A create package file request is received.");
      v19 = v26;
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 16LL))(v19);
        }
      }
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McTemplateK0_EtwWriteTransfer(
          PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
          StrmFlt_CREATE_MESSAGE_START,
          0);
      file = Streaming::staging_operations::create_file(
               a2,
               (const void *)a3,
               v6,
               (void *)a5,
               (union _LARGE_INTEGER)a6,
               v24);
      if ( (file & 0x80000000) != 0 )
      {
        v20 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v25);
        LogWrite(
          1,
          *v20,
          L"UserCommunication::ProcessMessage() - A create package file message failed. Failure Status 0x%08X.",
          file);
        v21 = v26;
        if ( v26 )
        {
          if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
            if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 16LL))(v21);
          }
        }
      }
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) == 0 )
        return file;
      v13 = StrmFlt_CREATE_MESSAGE_STOP;
LABEL_52:
      McTemplateK0_EtwWriteTransfer(PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context, v13, 0);
      return file;
    case 2:
      v14 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v25);
      LogWrite(3, *v14, L"UserCommunication::ProcessMessage() - Streaming Filter received a write request.");
      v15 = v26;
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McTemplateK0_EtwWriteTransfer(
          PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
          StrmFlt_WRITE_MESSAGE_START,
          0);
      file = Streaming::staging_operations::write_file(a2, (const void *)a3, v6, (void *)a5, (unsigned int)a6, v24);
      if ( (file & 0x80000000) != 0 )
      {
        v16 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v25);
        LogWrite(
          1,
          *v16,
          L"UserCommunication::ProcessMessage() - Streaming Filter failed the write request received from the streaming ma"
           "nager. Failure status 0x%08X.",
          file);
        v17 = v26;
        if ( v26 )
        {
          if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
            if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
          }
        }
      }
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) == 0 )
        return file;
      v13 = StrmFlt_WRITE_MESSAGE_STOP;
      goto LABEL_52;
    case 3:
      return (unsigned int)Streaming::staging_operations::request_mdl(
                             a2,
                             (const void *)a3,
                             (unsigned int)a4,
                             (void *)a5,
                             (unsigned int)a6,
                             v24);
    case 6:
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McTemplateK0_EtwWriteTransfer(
          PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
          StrmFlt_QUERY_FILE_START,
          0);
      file = Streaming::staging_operations::query_sparse_file(a2, (void *)a3, v6, (void *)a5, v23, v24);
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) == 0 )
        return file;
      v13 = StrmFlt_QUERY_FILE_STOP;
      goto LABEL_52;
    case 7:
      return (unsigned int)Streaming::staging_operations::create_hard_link(
                             a2,
                             (void *)a3,
                             (unsigned int)a4,
                             (void *)a5,
                             (unsigned int)a6,
                             v24);
  }
  if ( *(_DWORD *)a2 != 8 )
  {
    if ( *(_DWORD *)a2 != 9 )
      goto LABEL_9;
    return (unsigned int)Streaming::staging_operations::set_directory_DACL(
                           a2,
                           (const void *)a3,
                           (unsigned int)a4,
                           (void *)a5,
                           (unsigned int)a6,
                           v24);
  }
  if ( a3 >= 0xC && (*((_BYTE *)Streaming::gStrmFltData + 48) = *((_BYTE *)a2 + 8) & 1, a5 == 4) && a4 )
  {
    *a4 = 0;
    file = 0;
    *a6 = 4;
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return file;
}

```

## disassembly

```asm
0x140013f68  push    rbp
0x140013f6a  push    rbx
0x140013f6b  push    rsi
0x140013f6c  push    rdi
0x140013f6d  push    r12
0x140013f6f  push    r14
0x140013f71  push    r15
0x140013f73  mov     rbp, rsp
0x140013f76  sub     rsp, 40h
0x140013f7a  mov     r12, qword ptr [rbp+arg_28]
0x140013f7e  mov     r14, r9
0x140013f81  mov     r15d, r8d
0x140013f84  mov     rsi, rdx
0x140013f87  mov     dword ptr [r12], 0
0x140013f8f  cmp     r8d, 8
0x140013f93  jb      short loc_140013FD2
0x140013f95  mov     ecx, [rdx]
0x140013f97  sub     ecx, 1
0x140013f9a  jz      loc_140014237
0x140013fa0  sub     ecx, 1
0x140013fa3  jz      loc_140014128
0x140013fa9  sub     ecx, 1
0x140013fac  jz      loc_14001410A
0x140013fb2  sub     ecx, 3
0x140013fb5  jz      loc_1400140BE
0x140013fbb  sub     ecx, 1
0x140013fbe  jz      loc_1400140A5
0x140013fc4  sub     ecx, 1
0x140013fc7  jz      loc_140014064
0x140013fcd  cmp     ecx, 1
0x140013fd0  jz      short loc_140014048
0x140013fd2  lea     rcx, [rbp+var_10]
0x140013fd6  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140013fdb  mov     edi, 0C000000Dh
0x140013fe0  lea     r8, aUsercommunicat_0; "UserCommunication::ProcessMessage() - T"...
0x140013fe7  mov     r9d, edi
0x140013fea  mov     ecx, 1
0x140013fef  mov     rdx, [rax]
0x140013ff2  call    LogWrite
0x140013ff7  mov     rsi, [rbp+var_8]
0x140013ffb  test    rsi, rsi
0x140013ffe  jz      loc_14001434C
0x140014004  or      ebx, 0FFFFFFFFh
0x140014007  mov     eax, ebx
0x140014009  lock xadd [rsi+8], eax
0x14001400e  add     eax, ebx
0x140014010  jnz     loc_14001434C
0x140014016  mov     rax, [rsi]
0x140014019  mov     rcx, rsi
0x14001401c  mov     rax, [rax+8]
0x140014020  call    _guard_dispatch_icall
0x140014025  mov     eax, ebx
0x140014027  lock xadd [rsi+0Ch], eax
0x14001402c  add     eax, ebx
0x14001402e  jnz     loc_14001434C
0x140014034  mov     rax, [rsi]
0x140014037  mov     rcx, rsi
0x14001403a  mov     rax, [rax+10h]
0x14001403e  call    _guard_dispatch_icall
0x140014043  jmp     loc_14001434C
0x140014048  mov     r9d, dword ptr [rbp+arg_20]; void *
0x14001404c  mov     r8, r14; unsigned int
0x14001404f  mov     edx, r15d; void *
0x140014052  mov     qword ptr [rsp+40h+var_20], r12; unsigned int
0x140014057  mov     rcx, rsi; this
0x14001405a  call    ?set_directory_DACL@staging_operations@Streaming@@YAJPEBXKPEAXKAEAK@Z; Streaming::staging_operations::set_directory_DACL(void const *,ulong,void *,ulong,ulong &)
0x14001405f  jmp     loc_140014121
0x140014064  cmp     r15d, 0Ch
0x140014068  jb      short loc_14001409B
0x14001406a  mov     cl, [rdx+8]
0x14001406d  mov     rax, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140014074  and     cl, 1
0x140014077  cmp     dword ptr [rbp+arg_20], 4
0x14001407b  mov     [rax+30h], cl
0x14001407e  jnz     short loc_14001409B
0x140014080  test    r14, r14
0x140014083  jz      short loc_14001409B
0x140014085  mov     dword ptr [r9], 0
0x14001408c  xor     edi, edi
0x14001408e  mov     dword ptr [r12], 4
0x140014096  jmp     loc_14001434C
0x14001409b  mov     edi, 0C000000Dh
0x1400140a0  jmp     loc_14001434C
0x1400140a5  mov     r9d, dword ptr [rbp+arg_20]; void *
0x1400140a9  mov     r8, r14; unsigned int
0x1400140ac  mov     edx, r15d; void *
0x1400140af  mov     qword ptr [rsp+40h+var_20], r12; unsigned int
0x1400140b4  mov     rcx, rsi; this
0x1400140b7  call    ?create_hard_link@staging_operations@Streaming@@YAJPEAXK0KAEAK@Z; Streaming::staging_operations::create_hard_link(void *,ulong,void *,ulong,ulong &)
0x1400140bc  jmp     short loc_140014121
0x1400140be  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x1400140c5  jz      short loc_1400140DD
0x1400140c7  xor     r8d, r8d
0x1400140ca  lea     rdx, StrmFlt_QUERY_FILE_START
0x1400140d1  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x1400140d8  call    McTemplateK0_EtwWriteTransfer
0x1400140dd  mov     r9d, dword ptr [rbp+arg_20]; void *
0x1400140e1  mov     r8, r14; unsigned int
0x1400140e4  mov     edx, r15d; void *
0x1400140e7  mov     rcx, rsi; this
0x1400140ea  call    ?query_sparse_file@staging_operations@Streaming@@YAJPEAXK0KAEAK@Z; Streaming::staging_operations::query_sparse_file(void *,ulong,void *,ulong,ulong &)
0x1400140ef  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x1400140f6  mov     edi, eax
0x1400140f8  jz      loc_14001434C
0x1400140fe  lea     rdx, StrmFlt_QUERY_FILE_STOP
0x140014105  jmp     loc_14001433D
0x14001410a  mov     r9d, dword ptr [rbp+arg_20]; void *
0x14001410e  mov     r8, r14; unsigned int
0x140014111  mov     edx, r15d; void *
0x140014114  mov     qword ptr [rsp+40h+var_20], r12; unsigned int
0x140014119  mov     rcx, rsi; this
0x14001411c  call    ?request_mdl@staging_operations@Streaming@@YAJPEBXKPEAXKAEAK@Z; Streaming::staging_operations::request_mdl(void const *,ulong,void *,ulong,ulong &)
0x140014121  mov     edi, eax
0x140014123  jmp     loc_14001434C
0x140014128  lea     rcx, [rbp+var_10]
0x14001412c  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140014131  lea     r8, aUsercommunicat; "UserCommunication::ProcessMessage() - S"...
0x140014138  mov     ecx, 3
0x14001413d  mov     rdx, [rax]
0x140014140  call    LogWrite
0x140014145  mov     rdi, [rbp+var_8]
0x140014149  or      ebx, 0FFFFFFFFh
0x14001414c  test    rdi, rdi
0x14001414f  jz      short loc_140014185
0x140014151  mov     eax, ebx
0x140014153  lock xadd [rdi+8], eax
0x140014158  add     eax, ebx
0x14001415a  jnz     short loc_140014185
0x14001415c  mov     rax, [rdi]
0x14001415f  mov     rcx, rdi
0x140014162  mov     rax, [rax+8]
0x140014166  call    _guard_dispatch_icall
0x14001416b  mov     eax, ebx
0x14001416d  lock xadd [rdi+0Ch], eax
0x140014172  add     eax, ebx
0x140014174  jnz     short loc_140014185
0x140014176  mov     rax, [rdi]
0x140014179  mov     rcx, rdi
0x14001417c  mov     rax, [rax+10h]
0x140014180  call    _guard_dispatch_icall
0x140014185  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14001418c  jz      short loc_1400141A4
0x14001418e  xor     r8d, r8d
0x140014191  lea     rdx, StrmFlt_WRITE_MESSAGE_START
0x140014198  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x14001419f  call    McTemplateK0_EtwWriteTransfer
0x1400141a4  mov     r9d, dword ptr [rbp+arg_20]; void *
0x1400141a8  mov     r8, r14; unsigned int
0x1400141ab  mov     edx, r15d; void *
0x1400141ae  mov     qword ptr [rsp+40h+var_20], r12; unsigned int
0x1400141b3  mov     rcx, rsi; this
0x1400141b6  call    ?write_file@staging_operations@Streaming@@YAJPEBXKPEAXKAEAK@Z; Streaming::staging_operations::write_file(void const *,ulong,void *,ulong,ulong &)
0x1400141bb  mov     edi, eax
0x1400141bd  test    eax, eax
0x1400141bf  jns     short loc_14001421E
0x1400141c1  lea     rcx, [rbp+var_10]
0x1400141c5  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400141ca  mov     r9d, edi
0x1400141cd  lea     r8, aUsercommunicat_1; "UserCommunication::ProcessMessage() - S"...
0x1400141d4  mov     ecx, 1
0x1400141d9  mov     rdx, [rax]
0x1400141dc  call    LogWrite
0x1400141e1  mov     rsi, [rbp+var_8]
0x1400141e5  test    rsi, rsi
0x1400141e8  jz      short loc_14001421E
0x1400141ea  mov     eax, ebx
0x1400141ec  lock xadd [rsi+8], eax
0x1400141f1  add     eax, ebx
0x1400141f3  jnz     short loc_14001421E
0x1400141f5  mov     rax, [rsi]
0x1400141f8  mov     rcx, rsi
0x1400141fb  mov     rax, [rax+8]
0x1400141ff  call    _guard_dispatch_icall
0x140014204  mov     eax, ebx
0x140014206  lock xadd [rsi+0Ch], eax
0x14001420b  add     eax, ebx
0x14001420d  jnz     short loc_14001421E
0x14001420f  mov     rax, [rsi]
0x140014212  mov     rcx, rsi
0x140014215  mov     rax, [rax+10h]
0x140014219  call    _guard_dispatch_icall
0x14001421e  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140014225  jz      loc_14001434C
0x14001422b  lea     rdx, StrmFlt_WRITE_MESSAGE_STOP
0x140014232  jmp     loc_14001433D
0x140014237  lea     rcx, [rbp+var_10]
0x14001423b  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140014240  lea     r8, aUsercommunicat_2; "UserCommunication::ProcessMessage() - A"...
0x140014247  mov     ecx, 3
0x14001424c  mov     rdx, [rax]
0x14001424f  call    LogWrite
0x140014254  mov     rdi, [rbp+var_8]
0x140014258  or      ebx, 0FFFFFFFFh
0x14001425b  test    rdi, rdi
0x14001425e  jz      short loc_140014294
0x140014260  mov     eax, ebx
0x140014262  lock xadd [rdi+8], eax
0x140014267  add     eax, ebx
0x140014269  jnz     short loc_140014294
0x14001426b  mov     rax, [rdi]
0x14001426e  mov     rcx, rdi
0x140014271  mov     rax, [rax+8]
0x140014275  call    _guard_dispatch_icall
0x14001427a  mov     eax, ebx
0x14001427c  lock xadd [rdi+0Ch], eax
0x140014281  add     eax, ebx
0x140014283  jnz     short loc_140014294
0x140014285  mov     rax, [rdi]
0x140014288  mov     rcx, rdi
0x14001428b  mov     rax, [rax+10h]
0x14001428f  call    _guard_dispatch_icall
0x140014294  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14001429b  jz      short loc_1400142B3
0x14001429d  xor     r8d, r8d
0x1400142a0  lea     rdx, StrmFlt_CREATE_MESSAGE_START
0x1400142a7  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x1400142ae  call    McTemplateK0_EtwWriteTransfer
0x1400142b3  mov     r9d, dword ptr [rbp+arg_20]; void *
0x1400142b7  mov     r8, r14; unsigned int
0x1400142ba  mov     edx, r15d; void *
0x1400142bd  mov     qword ptr [rsp+40h+var_20], r12; union _LARGE_INTEGER
0x1400142c2  mov     rcx, rsi; this
0x1400142c5  call    ?create_file@staging_operations@Streaming@@YAJPEBXKPEAXKAEAK@Z; Streaming::staging_operations::create_file(void const *,ulong,void *,ulong,ulong &)
0x1400142ca  mov     edi, eax
0x1400142cc  test    eax, eax
0x1400142ce  jns     short loc_14001432D
0x1400142d0  lea     rcx, [rbp+var_10]
0x1400142d4  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400142d9  mov     r9d, edi
0x1400142dc  lea     r8, aUsercommunicat_5; "UserCommunication::ProcessMessage() - A"...
0x1400142e3  mov     ecx, 1
0x1400142e8  mov     rdx, [rax]
0x1400142eb  call    LogWrite
0x1400142f0  mov     rsi, [rbp+var_8]
0x1400142f4  test    rsi, rsi
0x1400142f7  jz      short loc_14001432D
0x1400142f9  mov     eax, ebx
0x1400142fb  lock xadd [rsi+8], eax
0x140014300  add     eax, ebx
0x140014302  jnz     short loc_14001432D
0x140014304  mov     rax, [rsi]
0x140014307  mov     rcx, rsi
0x14001430a  mov     rax, [rax+8]
0x14001430e  call    _guard_dispatch_icall
0x140014313  mov     eax, ebx
0x140014315  lock xadd [rsi+0Ch], eax
0x14001431a  add     eax, ebx
0x14001431c  jnz     short loc_14001432D
0x14001431e  mov     rax, [rsi]
0x140014321  mov     rcx, rsi
0x140014324  mov     rax, [rax+10h]
0x140014328  call    _guard_dispatch_icall
0x14001432d  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140014334  jz      short loc_14001434C
0x140014336  lea     rdx, StrmFlt_CREATE_MESSAGE_STOP
0x14001433d  xor     r8d, r8d
0x140014340  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140014347  call    McTemplateK0_EtwWriteTransfer
0x14001434c  mov     eax, edi
0x14001434e  add     rsp, 40h
0x140014352  pop     r15
0x140014354  pop     r14
0x140014356  pop     r12
0x140014358  pop     rdi
0x140014359  pop     rsi
0x14001435a  pop     rbx
0x14001435b  pop     rbp
0x14001435c  retn
```
