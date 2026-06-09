# ept_map_auth_sd

- ea: `0x180003a1c`
- end: `0x180003f71`
- name: `ept_map_auth_sd`
- size: `1365`
- prototype: `void __fastcall(PRPC_ASYNC_STATE pAsync, __int64, UUID *, UUID *, PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64 *, unsigned int, unsigned int *, __int64, RPC_STATUS *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003810`

## callees

- `0x1800013f8`
- `0x180002a88`
- `0x180002ae0`
- `0x180002bc0`
- `0x18000359c`
- `0x180003a1c`
- `0x180003f78`
- `0x1800046d8`
- `0x180004f94`
- `0x180005080`
- `0x1800051bc`
- `0x18000a89c`
- `0x18000a8b4`
- `0x18000a980`

## import_xrefs

- `RPCRT4!TowerExplode` at `0x180003b0f`
- `RPCRT4!TowerExplode` at `0x180003b0f`
- `RPCRT4!RpcRaiseException` at `0x180003f43`
- `RPCRT4!RpcRaiseException` at `0x180003f43`
- `RPCRT4!UuidIsNil` at `0x180003b5c`
- `RPCRT4!UuidIsNil` at `0x180003d31`
- `RPCRT4!UuidIsNil` at `0x180003b5c`
- `RPCRT4!UuidIsNil` at `0x180003d31`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180003f32`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180003f32`
- `RPCRT4!I_RpcFree` at `0x180003f0b`
- `RPCRT4!I_RpcFree` at `0x180003f0b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180003c83`
- `ntdll!RtlReleaseSRWLockShared` at `0x180003c83`
- `ntdll!RtlAcquireSRWLockShared` at `0x180003bfe`
- `ntdll!RtlAcquireSRWLockShared` at `0x180003bfe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003cca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003dfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003cca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003dfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f22`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180003ab1`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180003ab1`

## pseudocode

```c
void __fastcall ept_map_auth_sd(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        UUID *a3,
        UUID *a4,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        __int64 *a6,
        unsigned int a7,
        unsigned int *a8,
        __int64 a9,
        RPC_STATUS *a10)
{
  RPC_STATUS v10; // r15d
  struct _RPC_ASYNC_STATE *v11; // rdi
  UUID *v12; // rax
  unsigned __int16 *v14; // r14
  int v15; // r12d
  UUID *v16; // rdi
  RPC_STATUS v17; // eax
  int v18; // r13d
  void *v19; // rbx
  char *v20; // rbx
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  RPC_STATUS EntriesNoLock; // eax
  __int64 v27; // rcx
  char *v28; // rax
  RPC_STATUS v29; // eax
  __int64 v30; // r8
  int v32; // [rsp+88h] [rbp-78h] BYREF
  int v33; // [rsp+8Ch] [rbp-74h] BYREF
  RPC_STATUS Status; // [rsp+90h] [rbp-70h] BYREF
  void *Object; // [rsp+98h] [rbp-68h] BYREF
  unsigned int *v36; // [rsp+A0h] [rbp-60h]
  __int64 *v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  RPC_STATUS v40[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-38h]
  __int128 Buf1; // [rsp+D0h] [rbp-30h] BYREF
  int v43; // [rsp+E0h] [rbp-20h]
  __int128 v44; // [rsp+E8h] [rbp-18h] BYREF
  int v45; // [rsp+F8h] [rbp-8h]

  v10 = 0;
  v11 = pAsync;
  v12 = a4;
  v37 = a6;
  v38 = a9;
  v14 = 0;
  *(_QWORD *)v40 = a4;
  v39 = (__int64)pSecurityDescriptor;
  v36 = a8;
  v43 = 0;
  v45 = 0;
  v32 = 0;
  Status = 0;
  Object = 0;
  Buf1 = 0;
  v44 = 0;
  if ( pSecurityDescriptor )
  {
    if ( !IsValidSecurityDescriptor(pSecurityDescriptor) )
    {
      v10 = 87;
      v15 = 0;
      goto LABEL_46;
    }
    v12 = *(UUID **)v40;
  }
  v16 = (UUID *)&LocalNullUuid;
  if ( a3 )
    v16 = a3;
  if ( v16 != v12 )
  {
    v15 = 1;
    v17 = TowerExplode(v12, &Buf1, &v44, &Object, 0, 0);
    *a10 = v17;
    if ( v17 )
    {
      *a8 = 0;
      goto LABEL_45;
    }
    v18 = HIWORD(v43) | ((unsigned __int16)v43 << 16);
    if ( !memcmp_0(&Buf1, &MgmtIf, 0x10u) )
    {
      Status = 0;
      if ( UuidIsNil(v16, &Status) )
      {
        *v36 = 0;
        *a10 = 1819;
      }
      else
      {
        *a10 = GetEntries(
                 (__int64)v16,
                 (__int64)&Buf1,
                 v18,
                 (__int64)Object,
                 v39,
                 v37,
                 v38,
                 8 * a7,
                 2u,
                 a7,
                 v36,
                 2,
                 1,
                 (__int64)SearchIFObjNode,
                 0);
      }
      goto LABEL_45;
    }
    v33 = 0;
    v19 = Object;
    RtlAcquireSRWLockShared(&EpMapRWLock);
    v41 = 8 * a7;
    LODWORD(v19) = GetEntriesNoLock(
                     (__int64)v16,
                     (__int64)&Buf1,
                     v18,
                     (__int64)v19,
                     v39,
                     v37,
                     v38,
                     8 * a7,
                     2u,
                     a7,
                     v36,
                     0,
                     0,
                     (__int64)WildCardMatch,
                     &v33);
    RtlReleaseSRWLockShared(&EpMapRWLock);
    *a10 = (int)v19;
    if ( (_DWORD)v19 != 382312662 )
      goto LABEL_45;
    v20 = 0;
    if ( *v37 || v33 || g_TriggersDisabled )
      goto LABEL_45;
    v21 = (unsigned __int16 *)HeapAlloc(hEpMapperHeap, 0, 0x94u);
    v14 = v21;
    if ( v21 )
    {
      v22 = RPC_UUID::ConvertToString((RPC_UUID *)&Buf1, v21);
      if ( v16->Data1 || *(_DWORD *)&v16->Data2 || *(_DWORD *)v16->Data4 || *(_DWORD *)&v16->Data4[4] )
      {
        *v22 = 58;
        RPC_UUID::ConvertToString((RPC_UUID *)v16, v22 + 1);
      }
      *a10 = 0;
      if ( !(unsigned int)RtdsTriggerExists(v23, v14, &v32) )
      {
        if ( v32 )
          goto LABEL_31;
        v40[0] = 0;
        if ( UuidIsNil(v16, v40) )
        {
LABEL_30:
          *a10 = 382312662;
          goto LABEL_45;
        }
        v14[36] = 0;
        if ( !(unsigned int)RtdsTriggerExists(v25, v14, &v32) )
        {
          if ( !v32 )
            goto LABEL_30;
LABEL_31:
          RPC_SRWLOCK::Request(v24, 1);
          EntriesNoLock = GetEntriesNoLock(
                            (__int64)v16,
                            (__int64)&Buf1,
                            v18,
                            (__int64)Object,
                            v39,
                            v37,
                            v38,
                            v41,
                            2u,
                            a7,
                            v36,
                            0,
                            0,
                            (__int64)WildCardMatch,
                            &v33);
          *a10 = EntriesNoLock;
          if ( EntriesNoLock == 382312662 && !v33 )
          {
            v28 = (char *)HeapAlloc(hEpMapperHeap, 0, 0x68u);
            v20 = v28;
            if ( v28 )
            {
              memset_0(v28, 0, 0x68u);
              v29 = InitializeBufferedRequest(v20, v39, &Buf1, v16, a7, Object, v18, v38, v37, v36, a10, pAsync);
              *a10 = v29;
              if ( !v29 )
              {
                Object = 0;
                if ( (unsigned int)NtrbEnqueueRequest(v20 + 8, v20, &Status) )
                {
                  *a10 = 14;
                }
                else
                {
                  v20 = 0;
                  v15 = 0;
                  if ( Status )
                  {
                    if ( (Microsoft_Windows_EndpointTriggerProviderEnableBits & 1) != 0 )
                      McTemplateU0zz_EtwEventWriteTransfer(&EndpointTriggerGuid_Context, &ClientConnect, v30, v14);
                    if ( (Microsoft_Windows_ServiceTriggerPerfEventProviderEnableBits & 1) != 0 )
                      McTemplateU0zz_EtwEventWriteTransfer(
                        &SERVICE_TRIGGER_PERF_EVENT_GUID_Context,
                        &ServiceTriggerPerfServiceTriggered,
                        v30,
                        v14);
                  }
                }
              }
            }
          }
          RPC_SRWLOCK::Clear(v27, 1);
          if ( v20 )
            BufferedRequestCleanup(v20);
          goto LABEL_45;
        }
      }
    }
    *a10 = 14;
    goto LABEL_45;
  }
  v10 = 1752;
  v15 = 0;
LABEL_45:
  v11 = pAsync;
LABEL_46:
  if ( Object )
    I_RpcFree(Object);
  if ( v14 )
    HeapFree(hEpMapperHeap, 0, v14);
  if ( v15 )
    v10 = RpcAsyncCompleteCall(v11, 0);
  if ( v10 )
    RpcRaiseException(v10);
}

```

## disassembly

```asm
0x180003a1c  mov     [rsp-8+arg_8], rbx
0x180003a21  push    rbp
0x180003a22  push    rsi
0x180003a23  push    rdi
0x180003a24  push    r12
0x180003a26  push    r13
0x180003a28  push    r14
0x180003a2a  push    r15
0x180003a2c  lea     rbp, [rsp-10h]
0x180003a31  sub     rsp, 110h
0x180003a38  mov     rax, cs:__security_cookie
0x180003a3f  xor     rax, rsp
0x180003a42  mov     [rbp+40h+var_40], rax
0x180003a46  mov     rdx, [rbp+40h+arg_28]
0x180003a4a  xor     r15d, r15d
0x180003a4d  mov     r13, [rbp+40h+arg_38]
0x180003a54  mov     rdi, rcx
0x180003a57  mov     rsi, [rbp+40h+arg_48]
0x180003a5e  mov     rax, r9
0x180003a61  mov     [rbp+40h+var_98], rdx
0x180003a65  xorps   xmm0, xmm0
0x180003a68  mov     rdx, [rbp+40h+arg_40]
0x180003a6f  xorps   xmm1, xmm1
0x180003a72  mov     [rbp+40h+var_90], rdx
0x180003a76  mov     rbx, r8
0x180003a79  xor     edx, edx
0x180003a7b  mov     [rbp+40h+var_C0], rcx
0x180003a7f  mov     rcx, [rbp+40h+pSecurityDescriptor]; pSecurityDescriptor
0x180003a83  mov     r14d, r15d
0x180003a86  mov     qword ptr [rbp+40h+var_80], rax
0x180003a8a  mov     [rbp+40h+var_88], rcx
0x180003a8e  mov     [rbp+40h+var_A0], r13
0x180003a92  mov     [rbp+40h+var_60], edx
0x180003a95  mov     [rbp+40h+var_48], edx
0x180003a98  mov     [rbp+40h+var_B8], r15d
0x180003a9c  mov     [rbp+40h+Status], r15d
0x180003aa0  mov     [rbp+40h+Object], r15
0x180003aa4  movups  [rbp+40h+Buf1], xmm0
0x180003aa8  movups  [rbp+40h+var_58], xmm1
0x180003aac  test    rcx, rcx
0x180003aaf  jz      short loc_180003ACD
0x180003ab1  call    cs:__imp_IsValidSecurityDescriptor
0x180003ab7  test    eax, eax
0x180003ab9  jnz     short loc_180003AC9
0x180003abb  xor     ebx, ebx
0x180003abd  lea     r15d, [r14+57h]
0x180003ac1  mov     r12d, ebx
0x180003ac4  jmp     loc_180003F02
0x180003ac9  mov     rax, qword ptr [rbp+40h+var_80]
0x180003acd  test    rbx, rbx
0x180003ad0  lea     rdi, LocalNullUuid
0x180003ad7  cmovnz  rdi, rbx
0x180003adb  xor     ebx, ebx
0x180003add  cmp     rdi, rax
0x180003ae0  jnz     short loc_180003AF0
0x180003ae2  mov     r15d, 6D8h
0x180003ae8  mov     r12d, ebx
0x180003aeb  jmp     loc_180003EFE
0x180003af0  mov     [rsp+140h+var_118], rbx
0x180003af5  lea     r9, [rbp+40h+Object]
0x180003af9  lea     r8, [rbp+40h+var_58]
0x180003afd  mov     [rsp+140h+var_120], rbx
0x180003b02  lea     rdx, [rbp+40h+Buf1]
0x180003b06  mov     rcx, rax
0x180003b09  mov     r12d, 1
0x180003b0f  call    cs:__imp_TowerExplode
0x180003b15  mov     [rsi], eax
0x180003b17  test    eax, eax
0x180003b19  jz      short loc_180003B24
0x180003b1b  mov     [r13+0], ebx
0x180003b1f  jmp     loc_180003EFE
0x180003b24  movzx   eax, word ptr [rbp+40h+var_60+2]
0x180003b28  lea     rdx, MgmtIf; Buf2
0x180003b2f  movzx   r13d, word ptr [rbp+40h+var_60]
0x180003b34  lea     rcx, [rbp+40h+Buf1]; Buf1
0x180003b38  shl     r13d, 10h
0x180003b3c  mov     r8d, 10h; Size
0x180003b42  or      r13d, eax
0x180003b45  call    memcmp_0
0x180003b4a  test    eax, eax
0x180003b4c  jnz     loc_180003BF0
0x180003b52  lea     rdx, [rbp+40h+Status]; Status
0x180003b56  mov     [rbp+40h+Status], ebx
0x180003b59  mov     rcx, rdi; Uuid
0x180003b5c  call    cs:__imp_UuidIsNil
0x180003b62  test    eax, eax
0x180003b64  jz      short loc_180003B77
0x180003b66  mov     rdx, [rbp+40h+var_A0]
0x180003b6a  mov     [rdx], ebx
0x180003b6c  mov     dword ptr [rsi], 71Bh
0x180003b72  jmp     loc_180003EFE
0x180003b77  mov     eax, [rbp+40h+arg_30]
0x180003b7d  lea     rdx, SearchIFObjNode
0x180003b84  mov     r9, [rbp+40h+Object]
0x180003b88  mov     r8d, 2
0x180003b8e  mov     [rsp+140h+var_D0], rbx
0x180003b93  mov     [rsp+140h+var_D8], rdx
0x180003b98  mov     rdx, [rbp+40h+var_A0]
0x180003b9c  lea     ecx, ds:0[rax*8]
0x180003ba3  mov     [rsp+140h+var_E0], r12d
0x180003ba8  mov     dword ptr [rsp+140h+var_E8], r8d
0x180003bad  mov     [rsp+140h+var_F0], rdx
0x180003bb2  lea     rdx, [rbp+40h+Buf1]
0x180003bb6  mov     dword ptr [rsp+140h+var_F8], eax
0x180003bba  mov     rax, [rbp+40h+var_90]
0x180003bbe  mov     dword ptr [rsp+140h+var_100], r8d
0x180003bc3  mov     r8d, r13d
0x180003bc6  mov     dword ptr [rsp+140h+var_108], ecx
0x180003bca  mov     rcx, rdi
0x180003bcd  mov     [rsp+140h+var_110], rax
0x180003bd2  mov     rax, [rbp+40h+var_98]
0x180003bd6  mov     [rsp+140h+var_118], rax
0x180003bdb  mov     rax, [rbp+40h+var_88]
0x180003bdf  mov     [rsp+140h+var_120], rax
0x180003be4  call    GetEntries
0x180003be9  mov     [rsi], eax
0x180003beb  jmp     loc_180003EFE
0x180003bf0  mov     [rbp+40h+var_B4], ebx
0x180003bf3  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x180003bfa  mov     rbx, [rbp+40h+Object]
0x180003bfe  call    cs:__imp_RtlAcquireSRWLockShared
0x180003c04  mov     eax, [rbp+40h+arg_30]
0x180003c0a  lea     rdx, [rbp+40h+var_B4]
0x180003c0e  mov     [rsp+140h+var_D0], rdx
0x180003c13  mov     r9, rbx
0x180003c16  lea     rdx, WildCardMatch
0x180003c1d  mov     r8d, r13d
0x180003c20  mov     [rsp+140h+var_D8], rdx
0x180003c25  mov     rdx, [rbp+40h+var_A0]
0x180003c29  lea     ecx, ds:0[rax*8]
0x180003c30  mov     [rsp+140h+var_E0], r14d
0x180003c35  mov     dword ptr [rsp+140h+var_E8], r14d
0x180003c3a  mov     [rsp+140h+var_F0], rdx
0x180003c3f  lea     rdx, [rbp+40h+Buf1]
0x180003c43  mov     dword ptr [rsp+140h+var_F8], eax
0x180003c47  mov     rax, [rbp+40h+var_90]
0x180003c4b  mov     dword ptr [rsp+140h+var_100], 2
0x180003c53  mov     dword ptr [rsp+140h+var_108], ecx
0x180003c57  mov     [rsp+140h+var_110], rax
0x180003c5c  mov     rax, [rbp+40h+var_98]
0x180003c60  mov     [rsp+140h+var_118], rax
0x180003c65  mov     rax, [rbp+40h+var_88]
0x180003c69  mov     [rbp+40h+var_78], rcx
0x180003c6d  mov     rcx, rdi
0x180003c70  mov     [rsp+140h+var_120], rax
0x180003c75  call    GetEntriesNoLock
0x180003c7a  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x180003c81  mov     ebx, eax
0x180003c83  call    cs:__imp_RtlReleaseSRWLockShared
0x180003c89  mov     [rsi], ebx
0x180003c8b  cmp     ebx, 16C9A0D6h
0x180003c91  jnz     loc_180003EFE
0x180003c97  mov     rax, [rbp+40h+var_98]
0x180003c9b  xor     ebx, ebx
0x180003c9d  cmp     [rax], rbx
0x180003ca0  jnz     loc_180003EFE
0x180003ca6  cmp     [rbp+40h+var_B4], ebx
0x180003ca9  jnz     loc_180003EFE
0x180003caf  cmp     cs:g_TriggersDisabled, ebx
0x180003cb5  jnz     loc_180003EFE
0x180003cbb  mov     rcx, cs:hEpMapperHeap; hHeap
0x180003cc2  xor     edx, edx; dwFlags
0x180003cc4  mov     r8d, 94h; dwBytes
0x180003cca  call    cs:__imp_HeapAlloc
0x180003cd0  mov     r14, rax
0x180003cd3  test    rax, rax
0x180003cd6  jz      loc_180003EF8
0x180003cdc  mov     rdx, rax; unsigned __int16 *
0x180003cdf  lea     rcx, [rbp+40h+Buf1]; this
0x180003ce3  call    ?ConvertToString@RPC_UUID@@QEAAPEAGPEAG@Z; RPC_UUID::ConvertToString(ushort *)
0x180003ce8  cmp     [rdi], ebx
0x180003cea  jnz     short loc_180003CFB
0x180003cec  cmp     [rdi+4], ebx
0x180003cef  jnz     short loc_180003CFB
0x180003cf1  cmp     [rdi+8], ebx
0x180003cf4  jnz     short loc_180003CFB
0x180003cf6  cmp     [rdi+0Ch], ebx
0x180003cf9  jz      short loc_180003D0C
0x180003cfb  lea     rdx, [rax+2]; unsigned __int16 *
0x180003cff  mov     word ptr [rax], 3Ah ; ':'
0x180003d04  mov     rcx, rdi; this
0x180003d07  call    ?ConvertToString@RPC_UUID@@QEAAPEAGPEAG@Z; RPC_UUID::ConvertToString(ushort *)
0x180003d0c  lea     r8, [rbp+40h+var_B8]
0x180003d10  mov     [rsi], ebx
0x180003d12  mov     rdx, r14
0x180003d15  call    RtdsTriggerExists
0x180003d1a  test    eax, eax
0x180003d1c  jnz     loc_180003EF8
0x180003d22  cmp     [rbp+40h+var_B8], ebx
0x180003d25  jnz     short loc_180003D64
0x180003d27  lea     rdx, [rbp+40h+var_80]; Status
0x180003d2b  mov     [rbp+40h+var_80], ebx
0x180003d2e  mov     rcx, rdi; Uuid
0x180003d31  call    cs:__imp_UuidIsNil
0x180003d37  test    eax, eax
0x180003d39  jnz     short loc_180003D59
0x180003d3b  lea     r8, [rbp+40h+var_B8]
0x180003d3f  mov     [r14+48h], bx
0x180003d44  mov     rdx, r14
0x180003d47  call    RtdsTriggerExists
0x180003d4c  test    eax, eax
0x180003d4e  jnz     loc_180003EF8
0x180003d54  cmp     [rbp+40h+var_B8], ebx
0x180003d57  jnz     short loc_180003D64
0x180003d59  mov     dword ptr [rsi], 16C9A0D6h
0x180003d5f  jmp     loc_180003EFE
0x180003d64  mov     edx, r12d
0x180003d67  call    ?Request@RPC_SRWLOCK@@QEAAXW4LockMode@1@@Z; RPC_SRWLOCK::Request(RPC_SRWLOCK::LockMode)
0x180003d6c  mov     r9, [rbp+40h+Object]
0x180003d70  lea     rax, [rbp+40h+var_B4]
0x180003d74  mov     [rsp+140h+var_D0], rax
0x180003d79  lea     rdx, [rbp+40h+Buf1]
0x180003d7d  lea     rax, WildCardMatch
0x180003d84  mov     r8d, r13d
0x180003d87  mov     [rsp+140h+var_D8], rax
0x180003d8c  mov     rcx, rdi
0x180003d8f  mov     rax, [rbp+40h+var_A0]
0x180003d93  mov     [rsp+140h+var_E0], ebx
0x180003d97  mov     dword ptr [rsp+140h+var_E8], ebx
0x180003d9b  mov     [rsp+140h+var_F0], rax
0x180003da0  mov     eax, [rbp+40h+arg_30]
0x180003da6  mov     dword ptr [rsp+140h+var_F8], eax
0x180003daa  mov     rax, [rbp+40h+var_78]
0x180003dae  mov     dword ptr [rsp+140h+var_100], 2
0x180003db6  mov     dword ptr [rsp+140h+var_108], eax
0x180003dba  mov     rax, [rbp+40h+var_90]
0x180003dbe  mov     [rsp+140h+var_110], rax
0x180003dc3  mov     rax, [rbp+40h+var_98]
0x180003dc7  mov     [rsp+140h+var_118], rax
0x180003dcc  mov     rax, [rbp+40h+var_88]
0x180003dd0  mov     [rsp+140h+var_120], rax
0x180003dd5  call    GetEntriesNoLock
0x180003dda  mov     [rsi], eax
0x180003ddc  cmp     eax, 16C9A0D6h
0x180003de1  jnz     loc_180003EDF
0x180003de7  cmp     [rbp+40h+var_B4], ebx
0x180003dea  jnz     loc_180003EDF
0x180003df0  mov     rcx, cs:hEpMapperHeap; hHeap
0x180003df7  xor     edx, edx; dwFlags
0x180003df9  lea     r8d, [rdx+68h]; dwBytes
0x180003dfd  call    cs:__imp_HeapAlloc
0x180003e03  mov     rbx, rax
0x180003e06  test    rax, rax
0x180003e09  jz      loc_180003EDF
0x180003e0f  xor     edx, edx; Val
0x180003e11  mov     rcx, rax; void *
0x180003e14  lea     r8d, [rdx+68h]; Size
0x180003e18  call    memset_0
0x180003e1d  mov     rcx, [rbp+40h+Object]
0x180003e21  lea     r8, [rbp+40h+Buf1]
0x180003e25  mov     rax, [rbp+40h+var_C0]
0x180003e29  mov     r9, rdi
0x180003e2c  mov     rdx, [rbp+40h+var_88]
0x180003e30  mov     [rsp+140h+var_E8], rax
0x180003e35  mov     rax, [rbp+40h+var_A0]
0x180003e39  mov     [rsp+140h+var_F0], rsi
0x180003e3e  mov     [rsp+140h+var_F8], rax
0x180003e43  mov     rax, [rbp+40h+var_98]
0x180003e47  mov     [rsp+140h+var_100], rax
0x180003e4c  mov     rax, [rbp+40h+var_90]
0x180003e50  mov     [rsp+140h+var_108], rax
0x180003e55  mov     eax, [rbp+40h+arg_30]
0x180003e5b  mov     dword ptr [rsp+140h+var_110], r13d
0x180003e60  mov     [rsp+140h+var_118], rcx
0x180003e65  mov     rcx, rbx
0x180003e68  mov     dword ptr [rsp+140h+var_120], eax
0x180003e6c  call    InitializeBufferedRequest
0x180003e71  mov     [rsi], eax
0x180003e73  test    eax, eax
0x180003e75  jnz     short loc_180003EDF
0x180003e77  lea     rcx, [rbx+8]
0x180003e7b  mov     [rbp+40h+Object], r15
0x180003e7f  lea     r8, [rbp+40h+Status]
0x180003e83  mov     rdx, rbx
0x180003e86  call    NtrbEnqueueRequest
0x180003e8b  test    eax, eax
0x180003e8d  jz      short loc_180003E97
0x180003e8f  mov     dword ptr [rsi], 0Eh
0x180003e95  jmp     short loc_180003EDF
0x180003e97  xor     ebx, ebx
0x180003e99  xor     r12d, r12d
0x180003e9c  cmp     [rbp+40h+Status], ebx
0x180003e9f  jz      short loc_180003EDF
0x180003ea1  test    cs:Microsoft_Windows_EndpointTriggerProviderEnableBits, 1
0x180003ea8  jz      short loc_180003EC0
0x180003eaa  mov     r9, r14
0x180003ead  lea     rdx, ClientConnect
0x180003eb4  lea     rcx, EndpointTriggerGuid_Context
0x180003ebb  call    McTemplateU0zz_EtwEventWriteTransfer
0x180003ec0  test    cs:Microsoft_Windows_ServiceTriggerPerfEventProviderEnableBits, 1
0x180003ec7  jz      short loc_180003EDF
0x180003ec9  mov     r9, r14
0x180003ecc  lea     rdx, ServiceTriggerPerfServiceTriggered
0x180003ed3  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID_Context
0x180003eda  call    McTemplateU0zz_EtwEventWriteTransfer
0x180003edf  mov     edx, 1
0x180003ee4  call    ?Clear@RPC_SRWLOCK@@QEAAXW4LockMode@1@@Z; RPC_SRWLOCK::Clear(RPC_SRWLOCK::LockMode)
0x180003ee9  test    rbx, rbx
0x180003eec  jz      short loc_180003EFE
0x180003eee  mov     rcx, rbx
  ... truncated ...
```
