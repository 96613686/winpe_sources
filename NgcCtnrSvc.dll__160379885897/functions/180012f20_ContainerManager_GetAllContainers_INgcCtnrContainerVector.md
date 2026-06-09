# ContainerManager::GetAllContainers(INgcCtnrContainerVector * *)

- ea: `0x180012f20`
- end: `0x18001348c`
- name: `?GetAllContainers@ContainerManager@@QEAAJPEAPEAUINgcCtnrContainerVector@@@Z`
- size: `1388`
- prototype: `__int64 __fastcall(ContainerManager *__hidden this, struct INgcCtnrContainerVector **)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180012e5c`
- `0x180026514`
- `0x180026624`
- `0x180033b94`

## callees

- `0x180012f20`
- `0x180013588`
- `0x18002bc90`
- `0x18002c640`
- `0x18002cae0`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001306c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001306c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001313c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001313c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013031`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013228`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001338c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013031`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013228`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001338c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012f79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012f79`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ContainerManager::GetAllContainers(RTL_SRWLOCK *this, struct INgcCtnrContainerVector **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // esi
  RTL_SRWLOCK *v6; // r14
  __int64 *v7; // rbx
  __int64 *v8; // rdi
  __int64 *v9; // r8
  __int64 v10; // rcx
  __int64 **v11; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v14; // rbx
  int v15; // eax
  struct INgcCtnrContainerVector *v16; // rax
  LPVOID v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 *v19; // rcx
  char *v20; // rbx
  char *v21; // rdi
  unsigned __int64 v22; // rdx
  char *v23; // rcx
  unsigned int v25; // [rsp+30h] [rbp-79h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-71h] BYREF
  void *v27[2]; // [rsp+40h] [rbp-69h] BYREF
  __int64 *v28; // [rsp+50h] [rbp-59h]
  RTL_SRWLOCK *v29; // [rsp+58h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-49h] BYREF
  __int128 v31; // [rsp+70h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-29h] BYREF
  char *v33; // [rsp+90h] [rbp-19h]
  int v34; // [rsp+98h] [rbp-11h]
  int v35; // [rsp+9Ch] [rbp-Dh]
  unsigned int *v36; // [rsp+A0h] [rbp-9h]
  __int64 v37; // [rsp+A8h] [rbp-1h]
  __int128 *v38; // [rsp+B0h] [rbp+7h]
  __int64 v39; // [rsp+B8h] [rbp+Fh]

  *a2 = 0;
  ppv = 0;
  v4 = CoCreateInstance(
         &GUID_11962d33_dedc_457b_8d75_b3dad1f202b9,
         0,
         1u,
         &GUID_13ed66c7_bf9f_48f4_9b32_a3c72336e4ca,
         &ppv);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v25 = v4;
      v36 = &v25;
      v37 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v33 = byte_1800A7005;
      v34 = 41;
      v35 = 1;
      LODWORD(v29) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v5;
  }
  *(_OWORD *)v27 = 0;
  v28 = 0;
  v6 = this + 5;
  AcquireSRWLockShared(this + 5);
  v29 = this + 5;
  std::vector<wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>>::reserve(v27, this[7].Ptr);
  v7 = *(__int64 **)this[6].Ptr;
  v8 = (__int64 *)v27[1];
  while ( !*((_BYTE *)v7 + 25) )
  {
    v9 = v7 + 6;
    if ( v8 == v28 )
    {
      std::vector<wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy> const &>(
        (__int64 **)v27,
        v8,
        (__int64)v9);
      v8 = (__int64 *)v27[1];
    }
    else
    {
      v10 = *v9;
      *v8 = *v9;
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
      v8 = (__int64 *)((char *)v27[1] + 8);
      v27[1] = (char *)v27[1] + 8;
    }
    v11 = (__int64 **)v7[2];
    if ( *((_BYTE *)v11 + 25) )
    {
      for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
      {
        if ( v7 != (__int64 *)i[2] )
          break;
        v7 = i;
      }
      v7 = i;
    }
    else
    {
      v7 = (__int64 *)v7[2];
      for ( j = *v11; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v7 = j;
    }
  }
  if ( v6 )
  {
    ReleaseSRWLockShared(v6);
    v8 = (__int64 *)v27[1];
  }
  v14 = (__int64 *)v27[0];
  if ( v27[0] != v8 )
  {
    while ( 1 )
    {
      v31 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)*v14 + 64LL))(*v14, &v31);
      if ( v15 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 40LL))(ppv, *v14);
        if ( (v5 & 0x80000000) != 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 2 )
          {
            LODWORD(v29) = v5;
            v38 = &v31;
            v39 = 16;
            v36 = (unsigned int *)&v29;
            v37 = 4;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            *(_DWORD *)&EventDescriptor.Level = 2;
            EventDescriptor.Keyword = 0;
            UserData.Ptr = (ULONGLONG)off_1800BE0C0;
            UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
            UserData.Reserved = 2;
            v33 = byte_1800A6FA5;
            v34 = 46;
            v35 = 1;
            v25 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
          }
          v20 = (char *)v27[0];
          if ( v27[0] )
          {
            v21 = (char *)v27[1];
            if ( v27[0] != v27[1] )
            {
              do
              {
                if ( *(_QWORD *)v20 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 16LL))(*(_QWORD *)v20);
                v20 += 8;
              }
              while ( v20 != v21 );
              v20 = (char *)v27[0];
            }
            v22 = 8 * (((char *)v28 - v20) >> 3);
            if ( v22 >= 0x1000 )
            {
              v23 = (char *)*((_QWORD *)v20 - 1);
              if ( (unsigned __int64)(v20 - v23 - 8) <= 0x1F )
              {
                v22 += 39LL;
                goto LABEL_53;
              }
LABEL_57:
              __fastfail(5u);
            }
            v23 = v20;
LABEL_53:
            operator delete(v23, v22);
            *(_OWORD *)v27 = 0;
            v28 = 0;
          }
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          return v5;
        }
      }
      else
      {
        if ( (unsigned int)dword_1800BE0B8 > 3 )
        {
          LODWORD(v29) = v15;
          v36 = (unsigned int *)&v29;
          v37 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          *(_DWORD *)&EventDescriptor.Level = 3;
          EventDescriptor.Keyword = 0;
          UserData.Ptr = (ULONGLONG)off_1800BE0C0;
          UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
          UserData.Reserved = 2;
          v33 = &byte_1800A6FDF;
          v34 = 26;
          v35 = 1;
          v25 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
        }
        v5 = 0;
      }
      if ( ++v14 == v8 )
      {
        v8 = (__int64 *)v27[1];
        v14 = (__int64 *)v27[0];
        break;
      }
    }
  }
  v16 = (struct INgcCtnrContainerVector *)ppv;
  v17 = 0;
  ppv = 0;
  *a2 = v16;
  if ( v14 )
  {
    if ( v14 != v8 )
    {
      do
      {
        if ( *v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)*v14 + 16LL))(*v14);
        ++v14;
      }
      while ( v14 != v8 );
      v14 = (__int64 *)v27[0];
    }
    v18 = 8 * (v28 - v14);
    if ( v18 < 0x1000 )
    {
      v19 = v14;
    }
    else
    {
      v19 = (__int64 *)*(v14 - 1);
      if ( (unsigned __int64)((char *)v14 - (char *)v19 - 8) > 0x1F )
        goto LABEL_57;
      v18 += 39LL;
    }
    operator delete(v19, v18);
    *(_OWORD *)v27 = 0;
    v28 = 0;
    v17 = ppv;
  }
  if ( v17 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  return v5;
}

```

## disassembly

```asm
0x180012f20  mov     [rsp-8+arg_10], rbx
0x180012f25  push    rbp
0x180012f26  push    rsi
0x180012f27  push    rdi
0x180012f28  push    r12
0x180012f2a  push    r13
0x180012f2c  push    r14
0x180012f2e  push    r15
0x180012f30  lea     rbp, [rsp-27h]
0x180012f35  sub     rsp, 0D0h
0x180012f3c  mov     rax, cs:__security_cookie
0x180012f43  xor     rax, rsp
0x180012f46  mov     [rbp+57h+var_40], rax
0x180012f4a  mov     r12, rdx
0x180012f4d  mov     rbx, rcx
0x180012f50  xor     r13d, r13d
0x180012f53  mov     [rdx], r13
0x180012f56  mov     [rbp+57h+var_C8], r13
0x180012f5a  lea     rax, [rbp+57h+var_C8]
0x180012f5e  mov     [rsp+100h+ppv], rax; ppv
0x180012f63  lea     r9, _GUID_13ed66c7_bf9f_48f4_9b32_a3c72336e4ca; riid
0x180012f6a  xor     edx, edx; pUnkOuter
0x180012f6c  mov     r8d, 1; dwClsContext
0x180012f72  lea     rcx, _GUID_11962d33_dedc_457b_8d75_b3dad1f202b9; rclsid
0x180012f79  call    cs:__imp_CoCreateInstance
0x180012f80  nop     dword ptr [rax+rax+00h]
0x180012f85  mov     esi, eax
0x180012f87  test    eax, eax
0x180012f89  jns     loc_180013059
0x180012f8f  mov     ecx, cs:dword_1800BE0B8
0x180012f95  cmp     ecx, 2
0x180012f98  jbe     loc_18001303E
0x180012f9e  mov     [rbp+57h+var_D0], eax
0x180012fa1  lea     rax, [rbp+57h+var_D0]
0x180012fa5  mov     [rbp+57h+var_60], rax
0x180012fa9  mov     [rbp+57h+var_58], 4
0x180012fb1  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180012fb8  movzx   eax, cs:word_1800A6FFB
0x180012fbf  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180012fc2  mov     [rbp+57h+EventDescriptor.Keyword], r13
0x180012fc6  mov     rax, cs:off_1800BE0C0
0x180012fcd  mov     [rbp+57h+var_80.Ptr], rax
0x180012fd1  movzx   eax, word ptr [rax]
0x180012fd4  mov     [rbp+57h+var_80.Size], eax
0x180012fd7  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180012fde  lea     rax, byte_1800A7005
0x180012fe5  mov     [rbp+57h+var_70], rax
0x180012fe9  mov     [rbp+57h+var_68], 29h ; ')'
0x180012ff0  mov     [rbp+57h+var_64], 1
0x180012ff7  lea     r14, _TraceLoggingMetadataEnd
0x180012ffe  lea     r15, _TraceLoggingMetadata
0x180013005  sub     r14d, r15d
0x180013008  mov     dword ptr [rbp+57h+var_A8], r14d
0x18001300c  mov     eax, dword ptr [rbp+57h+var_A8]
0x18001300f  lea     rax, [rbp+57h+var_80]
0x180013013  mov     [rsp+100h+UserData], rax; UserData
0x180013018  mov     dword ptr [rsp+100h+ppv], 3; UserDataCount
0x180013020  xor     r9d, r9d; RelatedActivityId
0x180013023  xor     r8d, r8d; ActivityId
0x180013026  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001302a  mov     rcx, cs:RegHandle; RegHandle
0x180013031  call    cs:__imp_EventWriteTransfer
0x180013038  nop     dword ptr [rax+rax+00h]
0x18001303d  nop
0x18001303e  mov     rcx, [rbp+57h+var_C8]
0x180013042  test    rcx, rcx
0x180013045  jz      short loc_180013054
0x180013047  mov     rax, [rcx]
0x18001304a  mov     rax, [rax+10h]
0x18001304e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013053  nop
0x180013054  jmp     loc_180013462
0x180013059  xorps   xmm0, xmm0
0x18001305c  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x180013061  mov     [rbp+57h+var_B0], r13
0x180013065  lea     r14, [rbx+28h]
0x180013069  mov     rcx, r14; SRWLock
0x18001306c  call    cs:__imp_AcquireSRWLockShared
0x180013073  nop     dword ptr [rax+rax+00h]
0x180013078  mov     [rbp+57h+var_A8], r14
0x18001307c  mov     rdx, [rbx+38h]
0x180013080  lea     rcx, [rbp+57h+var_C0]
0x180013084  call    ?reserve@?$vector@V?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAAX_K@Z; std::vector<wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>>::reserve(unsigned __int64)
0x180013089  mov     rbx, [rbx+30h]
0x18001308d  mov     rbx, [rbx]
0x180013090  mov     rdi, [rbp+57h+var_C0+8]
0x180013094  cmp     byte ptr [rbx+19h], 0
0x180013098  jnz     loc_180013134
0x18001309e  lea     r8, [rbx+30h]
0x1800130a2  cmp     rdi, [rbp+57h+var_B0]
0x1800130a6  jz      short loc_1800130CE
0x1800130a8  mov     rcx, [r8]
0x1800130ab  mov     [rdi], rcx
0x1800130ae  test    rcx, rcx
0x1800130b1  jz      short loc_1800130C0
0x1800130b3  mov     rax, [rcx]
0x1800130b6  mov     rax, [rax+8]
0x1800130ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130bf  nop
0x1800130c0  mov     rdi, [rbp+57h+var_C0+8]
0x1800130c4  add     rdi, 8
0x1800130c8  mov     [rbp+57h+var_C0+8], rdi
0x1800130cc  jmp     short loc_1800130DE
0x1800130ce  mov     rdx, rdi
0x1800130d1  lea     rcx, [rbp+57h+var_C0]
0x1800130d5  call    ??$_Emplace_reallocate@AEBV?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAV23@AEBV23@@Z; std::vector<wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy> const &>(wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy> * const,wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy> const &)
0x1800130da  mov     rdi, [rbp+57h+var_C0+8]
0x1800130de  mov     rcx, [rbx+10h]
0x1800130e2  cmp     byte ptr [rcx+19h], 0
0x1800130e6  jz      short loc_18001310A
0x1800130e8  mov     rax, [rbx+8]
0x1800130ec  cmp     byte ptr [rax+19h], 0
0x1800130f0  jnz     short loc_180013105
0x1800130f2  cmp     rbx, [rax+10h]
0x1800130f6  jnz     short loc_180013105
0x1800130f8  mov     rbx, rax
0x1800130fb  mov     rax, [rax+8]
0x1800130ff  cmp     byte ptr [rax+19h], 0
0x180013103  jz      short loc_1800130F2
0x180013105  mov     rbx, rax
0x180013108  jmp     short loc_180013094
0x18001310a  mov     rbx, rcx
0x18001310d  mov     rcx, [rcx]
0x180013110  cmp     byte ptr [rcx+19h], 0
0x180013114  jnz     loc_180013094
0x18001311a  nop     word ptr [rax+rax+00h]
0x180013120  mov     rbx, rcx
0x180013123  mov     rax, [rcx]
0x180013126  mov     rcx, rax
0x180013129  cmp     byte ptr [rax+19h], 0
0x18001312d  jz      short loc_180013120
0x18001312f  jmp     loc_180013094
0x180013134  test    r14, r14
0x180013137  jz      short loc_18001314C
0x180013139  mov     rcx, r14; SRWLock
0x18001313c  call    cs:__imp_ReleaseSRWLockShared
0x180013143  nop     dword ptr [rax+rax+00h]
0x180013148  mov     rdi, [rbp+57h+var_C0+8]
0x18001314c  mov     rbx, [rbp+57h+var_C0]
0x180013150  cmp     rbx, rdi
0x180013153  jz      loc_18001326B
0x180013159  lea     r14, _TraceLoggingMetadataEnd
0x180013160  lea     r15, _TraceLoggingMetadata
0x180013167  nop     word ptr [rax+rax+00000000h]
0x180013170  lea     rsi, byte_1800A6FDF
0x180013177  xorps   xmm0, xmm0
0x18001317a  movups  [rbp+57h+var_90], xmm0
0x18001317e  mov     rcx, [rbx]
0x180013181  mov     rax, [rcx]
0x180013184  lea     rdx, [rbp+57h+var_90]
0x180013188  mov     rax, [rax+40h]
0x18001318c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013191  test    eax, eax
0x180013193  jns     loc_180013239
0x180013199  mov     ecx, cs:dword_1800BE0B8
0x18001319f  cmp     ecx, 3
0x1800131a2  jbe     loc_180013234
0x1800131a8  mov     dword ptr [rbp+57h+var_A8], eax
0x1800131ab  lea     rax, [rbp+57h+var_A8]
0x1800131af  mov     [rbp+57h+var_60], rax
0x1800131b3  mov     [rbp+57h+var_58], 4
0x1800131bb  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800131c2  movzx   eax, cs:word_1800A6FD5
0x1800131c9  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800131cc  mov     [rbp+57h+EventDescriptor.Keyword], r13
0x1800131d0  mov     rax, cs:off_1800BE0C0
0x1800131d7  mov     [rbp+57h+var_80.Ptr], rax
0x1800131db  movzx   eax, word ptr [rax]
0x1800131de  mov     [rbp+57h+var_80.Size], eax
0x1800131e1  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x1800131e8  mov     [rbp+57h+var_70], rsi
0x1800131ec  mov     [rbp+57h+var_68], 1Ah
0x1800131f3  mov     [rbp+57h+var_64], 1
0x1800131fa  mov     rax, r14
0x1800131fd  sub     eax, r15d
0x180013200  mov     [rbp+57h+var_D0], eax
0x180013203  mov     eax, [rbp+57h+var_D0]
0x180013206  lea     rax, [rbp+57h+var_80]
0x18001320a  mov     [rsp+100h+UserData], rax; UserData
0x18001320f  mov     dword ptr [rsp+100h+ppv], 3; UserDataCount
0x180013217  xor     r9d, r9d; RelatedActivityId
0x18001321a  xor     r8d, r8d; ActivityId
0x18001321d  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180013221  mov     rcx, cs:RegHandle; RegHandle
0x180013228  call    cs:__imp_EventWriteTransfer
0x18001322f  nop     dword ptr [rax+rax+00h]
0x180013234  mov     esi, r13d
0x180013237  jmp     short loc_180013256
0x180013239  mov     rcx, [rbp+57h+var_C8]
0x18001323d  mov     rax, [rcx]
0x180013240  mov     rdx, [rbx]
0x180013243  mov     rax, [rax+28h]
0x180013247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001324c  mov     esi, eax
0x18001324e  test    eax, eax
0x180013250  js      loc_1800132E8
0x180013256  add     rbx, 8
0x18001325a  cmp     rbx, rdi
0x18001325d  jnz     loc_180013170
0x180013263  mov     rdi, [rbp+57h+var_C0+8]
0x180013267  mov     rbx, [rbp+57h+var_C0]
0x18001326b  mov     rax, [rbp+57h+var_C8]
0x18001326f  mov     rcx, r13
0x180013272  mov     [rbp+57h+var_C8], rcx
0x180013276  mov     [r12], rax
0x18001327a  test    rbx, rbx
0x18001327d  jz      loc_180013450
0x180013283  cmp     rbx, rdi
0x180013286  jz      short loc_1800132AA
0x180013288  mov     rcx, [rbx]
0x18001328b  test    rcx, rcx
0x18001328e  jz      short loc_18001329D
0x180013290  mov     rax, [rcx]
0x180013293  mov     rax, [rax+10h]
0x180013297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001329c  nop
0x18001329d  add     rbx, 8
0x1800132a1  cmp     rbx, rdi
0x1800132a4  jnz     short loc_180013288
0x1800132a6  mov     rbx, [rbp+57h+var_C0]
0x1800132aa  mov     rax, [rbp+57h+var_B0]
0x1800132ae  sub     rax, rbx
0x1800132b1  sar     rax, 3
0x1800132b5  lea     rdx, ds:0[rax*8]; unsigned __int64
0x1800132bd  cmp     rdx, 1000h
0x1800132c4  jb      loc_180013438
0x1800132ca  mov     rcx, [rbx-8]
0x1800132ce  sub     rbx, rcx
0x1800132d1  sub     rbx, 8
0x1800132d5  cmp     rbx, 1Fh
0x1800132d9  ja      loc_180013431
0x1800132df  add     rdx, 27h ; '''
0x1800132e3  jmp     loc_18001343B
0x1800132e8  mov     eax, cs:dword_1800BE0B8
0x1800132ee  cmp     eax, 2
0x1800132f1  jbe     loc_180013399
0x1800132f7  mov     dword ptr [rbp+57h+var_A8], esi
0x1800132fa  lea     rax, [rbp+57h+var_90]
0x1800132fe  mov     [rbp+57h+var_50], rax
0x180013302  mov     [rbp+57h+var_48], 10h
0x18001330a  lea     rax, [rbp+57h+var_A8]
0x18001330e  mov     [rbp+57h+var_60], rax
0x180013312  mov     [rbp+57h+var_58], 4
0x18001331a  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180013321  movzx   eax, cs:word_1800A6F9B
0x180013328  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18001332b  mov     [rbp+57h+EventDescriptor.Keyword], r13
0x18001332f  mov     rax, cs:off_1800BE0C0
0x180013336  mov     [rbp+57h+var_80.Ptr], rax
0x18001333a  movzx   eax, word ptr [rax]
0x18001333d  mov     [rbp+57h+var_80.Size], eax
0x180013340  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180013347  lea     rax, byte_1800A6FA5
0x18001334e  mov     [rbp+57h+var_70], rax
0x180013352  mov     [rbp+57h+var_68], 2Eh ; '.'
0x180013359  mov     [rbp+57h+var_64], 1
0x180013360  sub     r14d, r15d
0x180013363  mov     [rbp+57h+var_D0], r14d
0x180013367  mov     eax, [rbp+57h+var_D0]
0x18001336a  lea     rax, [rbp+57h+var_80]
0x18001336e  mov     [rsp+100h+UserData], rax; UserData
0x180013373  mov     dword ptr [rsp+100h+ppv], 4; UserDataCount
0x18001337b  xor     r9d, r9d; RelatedActivityId
0x18001337e  xor     r8d, r8d; ActivityId
0x180013381  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180013385  mov     rcx, cs:RegHandle; RegHandle
0x18001338c  call    cs:__imp_EventWriteTransfer
0x180013393  nop     dword ptr [rax+rax+00h]
0x180013398  nop
0x180013399  mov     rbx, [rbp+57h+var_C0]
0x18001339d  test    rbx, rbx
0x1800133a0  jz      short loc_180013419
0x1800133a2  mov     rdi, [rbp+57h+var_C0+8]
0x1800133a6  cmp     rbx, rdi
0x1800133a9  jz      short loc_1800133D2
0x1800133ab  nop     dword ptr [rax+rax+00h]
0x1800133b0  mov     rcx, [rbx]
0x1800133b3  test    rcx, rcx
0x1800133b6  jz      short loc_1800133C5
0x1800133b8  mov     rax, [rcx]
0x1800133bb  mov     rax, [rax+10h]
0x1800133bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c4  nop
0x1800133c5  add     rbx, 8
0x1800133c9  cmp     rbx, rdi
0x1800133cc  jnz     short loc_1800133B0
0x1800133ce  mov     rbx, [rbp+57h+var_C0]
0x1800133d2  mov     rax, [rbp+57h+var_B0]
0x1800133d6  sub     rax, rbx
0x1800133d9  sar     rax, 3
0x1800133dd  lea     rdx, ds:0[rax*8]; unsigned __int64
0x1800133e5  cmp     rdx, 1000h
0x1800133ec  jb      short loc_180013405
0x1800133ee  mov     rcx, [rbx-8]
0x1800133f2  sub     rbx, rcx
0x1800133f5  sub     rbx, 8
0x1800133f9  cmp     rbx, 1Fh
0x1800133fd  ja      short loc_180013431
0x1800133ff  add     rdx, 27h ; '''
0x180013403  jmp     short loc_180013408
  ... truncated ...
```
