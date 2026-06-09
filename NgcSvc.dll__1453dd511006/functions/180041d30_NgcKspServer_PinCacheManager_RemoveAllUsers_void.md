# NgcKspServer::PinCacheManager::RemoveAllUsers(void)

- ea: `0x180041d30`
- end: `0x180042459`
- name: `?RemoveAllUsers@PinCacheManager@NgcKspServer@@QEAAXXZ`
- size: `1833`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180073b1c`
- `0x18007faac`

## callees

- `0x180010990`
- `0x1800386f0`
- `0x18004176c`
- `0x180041d30`
- `0x18004d408`
- `0x18005cee0`
- `0x18005d290`
- `0x18005d2b0`
- `0x18005d2ec`
- `0x18005d48c`
- `0x18005d4f4`
- `0x180069398`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041e02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004220e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041e02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004220e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800421c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042267`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800421c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042267`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180041df9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180041df9`
- `RPCRT4!UuidCreate` at `0x180042429`
- `RPCRT4!UuidCreate` at `0x180042429`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NgcKspServer::PinCacheManager::RemoveAllUsers(PSRWLOCK SRWLock)
{
  __int64 *j; // rcx
  __int64 *v3; // rbx
  __int64 v4; // r8
  char *v5; // rdx
  char *v6; // r15
  _BYTE *v7; // r13
  __int64 v8; // rax
  char *v9; // rsi
  __int64 v10; // rdi
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  __int64 v13; // r15
  unsigned __int64 v14; // r12
  size_t v15; // r12
  void *v16; // rax
  _QWORD *v17; // rdx
  __int64 v18; // rax
  char *v19; // r14
  _QWORD *v20; // rcx
  char *v21; // rdi
  _QWORD *v22; // rcx
  volatile signed __int32 *v23; // rsi
  unsigned __int64 v24; // rdx
  char *v25; // rcx
  __int64 *i; // rax
  RTL_SRWLOCK *v27; // rsi
  _QWORD *Ptr; // r15
  __int64 *v29; // rdi
  _QWORD *v30; // rsi
  volatile signed __int32 *v31; // rbx
  RTL_SRWLOCK **v32; // rsi
  RTL_SRWLOCK **v33; // r14
  char *v34; // r12
  RTL_SRWLOCK *v35; // r15
  _QWORD *v36; // rdi
  _QWORD *k; // rbx
  volatile signed __int32 *v38; // rbx
  volatile signed __int32 *v39; // rbx
  unsigned __int64 v40; // rdx
  RTL_SRWLOCK **v41; // rcx
  _QWORD *v42; // rax
  void *v43[2]; // [rsp+30h] [rbp-59h]
  char *v44; // [rsp+40h] [rbp-49h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-31h] BYREF
  RTL_SRWLOCK *v47; // [rsp+68h] [rbp-21h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-19h] BYREF
  __int16 *v49; // [rsp+80h] [rbp-9h]
  int v50; // [rsp+88h] [rbp-1h]
  int v51; // [rsp+8Ch] [rbp+3h]

  *(_OWORD *)v43 = 0;
  v44 = 0;
  if ( (unsigned int)dword_180122070 > 4 )
  {
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 4;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180122078;
    UserData.Size = *(unsigned __int16 *)off_180122078;
    UserData.Reserved = 2;
    v49 = word_180104C92;
    v50 = 35;
    v51 = 1;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  AcquireSRWLockExclusive(SRWLock);
  v3 = *(__int64 **)SRWLock[1].Ptr;
  v4 = 0xFFFFFFFFFFFFFFFLL;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  while ( !*((_BYTE *)v3 + 25) )
  {
    if ( v6 != v5 )
    {
      *(_QWORD *)v6 = 0;
      *((_QWORD *)v6 + 1) = 0;
      v8 = v3[8];
      if ( v8 )
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
      *(_QWORD *)v6 = v3[7];
      *((_QWORD *)v6 + 1) = v3[8];
      v6 = (char *)v43[1] + 16;
      v5 = v44;
      v7 = v43[0];
      goto LABEL_47;
    }
    v9 = v6;
    v10 = (v6 - v7) >> 4;
    if ( v10 == 0xFFFFFFFFFFFFFFFLL )
      std::vector<std::shared_ptr<NgcKspServer::PinCacheManager::UserCacheEntry>>::_Xlength(j, v5, 0xFFFFFFFFFFFFFFFLL);
    v11 = (v5 - v7) >> 4;
    v12 = v11 >> 1;
    if ( v11 > 0xFFFFFFFFFFFFFFFLL - (v11 >> 1) )
      goto LABEL_98;
    v13 = v10 + 1;
    v14 = v10 + 1;
    if ( v12 + v11 >= v10 + 1 )
      v14 = v12 + v11;
    if ( v14 > 0xFFFFFFFFFFFFFFFLL )
LABEL_98:
      std::_Throw_bad_array_new_length();
    v15 = 16 * v14;
    if ( v15 )
    {
      if ( v15 < 0x1000 )
      {
        v7 = operator new(v15);
      }
      else
      {
        if ( v15 + 39 < v15 )
          goto LABEL_98;
        v16 = operator new(v15 + 39);
        if ( !v16 )
LABEL_55:
          __fastfail(5u);
        v7 = (_BYTE *)(((unsigned __int64)v16 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v7 - 1) = v16;
      }
    }
    else
    {
      v7 = 0;
    }
    v17 = &v7[16 * v10];
    *v17 = 0;
    v17[1] = 0;
    v18 = v3[8];
    if ( v18 )
      _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
    *v17 = v3[7];
    v17[1] = v3[8];
    v19 = (char *)v43[1];
    v20 = v7;
    v21 = (char *)v43[0];
    if ( v9 != v43[1] )
    {
      if ( v43[0] != v9 )
      {
        do
        {
          *v20 = 0;
          v20[1] = 0;
          *v20 = *(_QWORD *)v21;
          v20[1] = *((_QWORD *)v21 + 1);
          *(_QWORD *)v21 = 0;
          *((_QWORD *)v21 + 1) = 0;
          v20 += 2;
          v21 += 16;
        }
        while ( v21 != v9 );
        v19 = (char *)v43[1];
        v21 = (char *)v43[0];
      }
      v22 = v17 + 2;
      if ( v9 == v19 )
        goto LABEL_33;
      do
      {
        *v22 = 0;
        v22[1] = 0;
        *v22 = *(_QWORD *)v9;
        v22[1] = *((_QWORD *)v9 + 1);
        *(_QWORD *)v9 = 0;
        *((_QWORD *)v9 + 1) = 0;
        v22 += 2;
        v9 += 16;
      }
      while ( v9 != v19 );
      goto LABEL_32;
    }
    if ( v43[0] != v43[1] )
    {
      do
      {
        *v20 = 0;
        v20[1] = 0;
        *v20 = *(_QWORD *)v21;
        v20[1] = *((_QWORD *)v21 + 1);
        *(_QWORD *)v21 = 0;
        *((_QWORD *)v21 + 1) = 0;
        v20 += 2;
        v21 += 16;
      }
      while ( v21 != v43[1] );
LABEL_32:
      v19 = (char *)v43[1];
      v21 = (char *)v43[0];
    }
LABEL_33:
    if ( v21 )
    {
      if ( v21 != v19 )
      {
        do
        {
          v23 = (volatile signed __int32 *)*((_QWORD *)v21 + 1);
          if ( v23 )
          {
            if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
              if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
            }
          }
          v21 += 16;
        }
        while ( v21 != v19 );
        v21 = (char *)v43[0];
      }
      v24 = (v44 - v21) & 0xFFFFFFFFFFFFFFF0uLL;
      if ( v24 < 0x1000 )
      {
        v25 = v21;
      }
      else
      {
        v25 = (char *)*((_QWORD *)v21 - 1);
        if ( (unsigned __int64)(v21 - v25 - 8) > 0x1F )
          goto LABEL_55;
        v24 += 39LL;
      }
      operator delete(v25, v24);
    }
    v43[0] = v7;
    v6 = &v7[16 * v13];
    v5 = &v7[v15];
    v44 = &v7[v15];
    v4 = 0xFFFFFFFFFFFFFFFLL;
LABEL_47:
    v43[1] = v6;
    j = (__int64 *)v3[2];
    if ( *((_BYTE *)j + 25) )
    {
      for ( i = (__int64 *)v3[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
      {
        if ( v3 != (__int64 *)i[2] )
          break;
        v3 = i;
      }
      v3 = i;
    }
    else
    {
      v3 = (__int64 *)v3[2];
      for ( j = (__int64 *)*j; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v3 = j;
    }
  }
  v27 = SRWLock;
  Ptr = SRWLock[1].Ptr;
  v29 = (__int64 *)Ptr[1];
  if ( !*((_BYTE *)v29 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<unsigned char> const,std::shared_ptr<NgcKspServer::PinCacheManager::UserCacheEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::vector<unsigned char> const,std::shared_ptr<NgcKspServer::PinCacheManager::UserCacheEntry>>,void *>>>(
        (__int64)&SRWLock[1],
        (__int64)&SRWLock[1],
        (__int64 *)v29[2]);
      v30 = v29;
      v29 = (__int64 *)*v29;
      v31 = (volatile signed __int32 *)v30[8];
      if ( v31 )
      {
        if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
          if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
        }
      }
      std::vector<unsigned char>::_Tidy(v30 + 4);
      operator delete(v30, 0x48u);
    }
    while ( !*((_BYTE *)v29 + 25) );
    v27 = SRWLock;
  }
  Ptr[1] = Ptr;
  *Ptr = Ptr;
  Ptr[2] = Ptr;
  SRWLock[2].Ptr = 0;
  if ( v27 )
    ReleaseSRWLockExclusive(v27);
  v33 = (RTL_SRWLOCK **)v43[1];
  v32 = (RTL_SRWLOCK **)v43[0];
  if ( v43[0] != v43[1] )
  {
    v34 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer + 8 * (unsigned int)tls_index;
    do
    {
      v35 = *v32 + 7;
      AcquireSRWLockExclusive(v35);
      v47 = v35;
      v36 = (*v32)[8].Ptr;
      for ( k = (_QWORD *)*v36; k != v36; k = (_QWORD *)*k )
      {
        if ( __TSS0__1__Instance_PinCacheManager_NgcKspServer__SAAEAV23_XZ_4HA > *(_DWORD *)(*(_QWORD *)v34 + 4LL) )
        {
          Init_thread_header(&__TSS0__1__Instance_PinCacheManager_NgcKspServer__SAAEAV23_XZ_4HA);
          if ( __TSS0__1__Instance_PinCacheManager_NgcKspServer__SAAEAV23_XZ_4HA == -1 )
          {
            `NgcKspServer::PinCacheManager::Instance'::`2'::pinCacheManager = 0;
            qword_180123078 = 0;
            qword_180123080 = 0;
            v42 = operator new(0x48u);
            *v42 = v42;
            v42[1] = v42;
            v42[2] = v42;
            *((_WORD *)v42 + 12) = 257;
            qword_180123078 = (__int64)v42;
            qword_180123090 = 0;
            qword_180123098 = 0;
            Uuid = 0;
            qword_1801230B0 = 0;
            qword_1801230B8 = 0;
            qword_1801230C0 = 0;
            dword_1801230C8 = 0;
            UuidCreate(&Uuid);
            atexit(`NgcKspServer::PinCacheManager::Instance'::`2'::`dynamic atexit destructor for 'pinCacheManager'');
            Init_thread_footer(&__TSS0__1__Instance_PinCacheManager_NgcKspServer__SAAEAV23_XZ_4HA);
          }
        }
        NgcKspServer::PinCacheManager::Deauthenticate(k[2], 2, 0);
      }
      if ( v35 )
        ReleaseSRWLockExclusive(v35);
      v32 += 2;
    }
    while ( v32 != v43[1] );
    v33 = (RTL_SRWLOCK **)v43[1];
    v32 = (RTL_SRWLOCK **)v43[0];
    if ( v43[0] != v43[1] )
    {
      do
      {
        v38 = (volatile signed __int32 *)v32[1];
        if ( v38 )
        {
          if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
            if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
          }
        }
        v32 += 2;
      }
      while ( v32 != v43[1] );
      v32 = (RTL_SRWLOCK **)v43[0];
      v33 = (RTL_SRWLOCK **)v43[0];
    }
  }
  if ( v32 )
  {
    if ( v32 != v33 )
    {
      do
      {
        v39 = (volatile signed __int32 *)v32[1];
        if ( v39 )
        {
          if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *, char *, __int64))v39)(v39, v5, v4);
            if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
          }
        }
        v32 += 2;
      }
      while ( v32 != v33 );
      v32 = (RTL_SRWLOCK **)v43[0];
    }
    v40 = (v44 - (char *)v32) & 0xFFFFFFFFFFFFFFF0uLL;
    if ( v40 < 0x1000 )
    {
      v41 = v32;
    }
    else
    {
      v41 = (RTL_SRWLOCK **)*(v32 - 1);
      if ( (unsigned __int64)((char *)v32 - (char *)v41 - 8) > 0x1F )
        __fastfail(5u);
      v40 += 39LL;
    }
    operator delete(v41, v40);
  }
}

```

## disassembly

```asm
0x180041d30  push    rbp
0x180041d32  push    rbx
0x180041d33  push    rsi
0x180041d34  push    rdi
0x180041d35  push    r12
0x180041d37  push    r13
0x180041d39  push    r14
0x180041d3b  push    r15
0x180041d3d  lea     rbp, [rsp-1Fh]
0x180041d42  sub     rsp, 0A8h
0x180041d49  mov     rax, cs:__security_cookie
0x180041d50  xor     rax, rsp
0x180041d53  mov     [rbp+57h+var_50], rax
0x180041d57  mov     rsi, rcx
0x180041d5a  mov     [rbp+57h+SRWLock], rcx
0x180041d5e  xorps   xmm0, xmm0
0x180041d61  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x180041d66  xor     edi, edi
0x180041d68  mov     [rbp+57h+var_A0], rdi
0x180041d6c  mov     eax, cs:dword_180122070
0x180041d72  cmp     eax, 4
0x180041d75  jbe     loc_180041DFF
0x180041d7b  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180041d82  movzx   eax, cs:word_180104C88
0x180041d89  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180041d8c  mov     [rbp+57h+EventDescriptor.Keyword], rdi
0x180041d90  mov     rax, cs:off_180122078
0x180041d97  mov     [rbp+57h+var_70.Ptr], rax
0x180041d9b  movzx   eax, word ptr [rax]
0x180041d9e  mov     [rbp+57h+var_70.Size], eax
0x180041da1  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x180041da8  lea     rax, word_180104C92
0x180041daf  mov     [rbp+57h+var_60], rax
0x180041db3  mov     [rbp+57h+var_58], 23h ; '#'
0x180041dba  mov     [rbp+57h+var_54], 1
0x180041dc1  lea     rax, _TraceLoggingMetadataEnd
0x180041dc8  lea     rcx, _TraceLoggingMetadata
0x180041dcf  sub     eax, ecx
0x180041dd1  mov     dword ptr [rbp+57h+var_98], eax
0x180041dd4  mov     eax, dword ptr [rbp+57h+var_98]
0x180041dd7  lea     rax, [rbp+57h+var_70]
0x180041ddb  mov     [rsp+0E0h+UserData], rax; UserData
0x180041de0  mov     [rsp+0E0h+UserDataCount], 2; UserDataCount
0x180041de8  xor     r9d, r9d; RelatedActivityId
0x180041deb  xor     r8d, r8d; ActivityId
0x180041dee  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180041df2  mov     rcx, cs:RegHandle; RegHandle
0x180041df9  call    cs:__imp_EventWriteTransfer
0x180041dff  mov     rcx, rsi; SRWLock
0x180041e02  call    cs:__imp_AcquireSRWLockExclusive
0x180041e08  mov     [rbp+57h+var_98], rsi
0x180041e0c  mov     rbx, [rsi+8]
0x180041e10  mov     rbx, [rbx]
0x180041e13  mov     r8, 0FFFFFFFFFFFFFFFh
0x180041e1d  mov     rdx, [rbp+57h+var_A0]
0x180041e21  mov     r15, [rbp+57h+var_B0+8]
0x180041e25  mov     r13, [rbp+57h+var_B0]
0x180041e29  nop     dword ptr [rax+00000000h]
0x180041e30  cmp     byte ptr [rbx+19h], 0
0x180041e34  jnz     loc_18004211B
0x180041e3a  cmp     r15, rdx
0x180041e3d  jz      short loc_180041E77
0x180041e3f  mov     [r15], rdi
0x180041e42  mov     [r15+8], rdi
0x180041e46  mov     rax, [rbx+40h]
0x180041e4a  test    rax, rax
0x180041e4d  jz      short loc_180041E53
0x180041e4f  lock inc dword ptr [rax+8]
0x180041e53  mov     rax, [rbx+38h]
0x180041e57  mov     [r15], rax
0x180041e5a  mov     rax, [rbx+40h]
0x180041e5e  mov     [r15+8], rax
0x180041e62  mov     r15, [rbp+57h+var_B0+8]
0x180041e66  add     r15, 10h
0x180041e6a  mov     rdx, [rbp+57h+var_A0]
0x180041e6e  mov     r13, [rbp+57h+var_B0]
0x180041e72  jmp     loc_1800420B7
0x180041e77  mov     rsi, r15
0x180041e7a  mov     rdi, r15
0x180041e7d  sub     rdi, r13
0x180041e80  sar     rdi, 4
0x180041e84  cmp     rdi, r8
0x180041e87  jz      loc_180042453
0x180041e8d  sub     rdx, r13
0x180041e90  sar     rdx, 4
0x180041e94  mov     rcx, rdx
0x180041e97  shr     rcx, 1
0x180041e9a  mov     rax, r8
0x180041e9d  sub     rax, rcx
0x180041ea0  cmp     rdx, rax
0x180041ea3  ja      loc_18004244D
0x180041ea9  lea     r15, [rdi+1]
0x180041ead  lea     rax, [rcx+rdx]
0x180041eb1  mov     r12, r15
0x180041eb4  cmp     rax, r15
0x180041eb7  cmovnb  r12, rax
0x180041ebb  cmp     r12, r8
0x180041ebe  ja      loc_18004244D
0x180041ec4  shl     r12, 4
0x180041ec8  test    r12, r12
0x180041ecb  jnz     short loc_180041ED5
0x180041ecd  xor     r8d, r8d
0x180041ed0  mov     r13d, r8d
0x180041ed3  jmp     short loc_180041F16
0x180041ed5  cmp     r12, 1000h
0x180041edc  jb      short loc_180041F08
0x180041ede  lea     rcx, [r12+27h]; Size
0x180041ee3  cmp     rcx, r12
0x180041ee6  jbe     loc_18004244D
0x180041eec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041ef1  test    rax, rax
0x180041ef4  jz      loc_180042114
0x180041efa  lea     r13, [rax+27h]
0x180041efe  and     r13, 0FFFFFFFFFFFFFFE0h
0x180041f02  mov     [r13-8], rax
0x180041f06  jmp     short loc_180041F13
0x180041f08  mov     rcx, r12; Size
0x180041f0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041f10  mov     r13, rax
0x180041f13  xor     r8d, r8d
0x180041f16  add     rdi, rdi
0x180041f19  lea     rdx, ds:0[rdi*8]
0x180041f21  add     rdx, r13
0x180041f24  mov     [rdx], r8
0x180041f27  mov     [rdx+8], r8
0x180041f2b  mov     rax, [rbx+40h]
0x180041f2f  test    rax, rax
0x180041f32  jz      short loc_180041F38
0x180041f34  lock inc dword ptr [rax+8]
0x180041f38  mov     rax, [rbx+38h]
0x180041f3c  mov     [rdx], rax
0x180041f3f  mov     rax, [rbx+40h]
0x180041f43  mov     [rdx+8], rax
0x180041f47  mov     r14, [rbp+57h+var_B0+8]
0x180041f4b  mov     rcx, r13
0x180041f4e  mov     rdi, [rbp+57h+var_B0]
0x180041f52  cmp     rsi, r14
0x180041f55  jnz     short loc_180041F8B
0x180041f57  cmp     rdi, r14
0x180041f5a  jz      loc_180042001
0x180041f60  mov     [rcx], r8
0x180041f63  mov     [rcx+8], r8
0x180041f67  mov     rax, [rdi]
0x180041f6a  mov     [rcx], rax
0x180041f6d  mov     rax, [rdi+8]
0x180041f71  mov     [rcx+8], rax
0x180041f75  mov     [rdi], r8
0x180041f78  mov     [rdi+8], r8
0x180041f7c  lea     rcx, [rcx+10h]
0x180041f80  add     rdi, 10h
0x180041f84  cmp     rdi, r14
0x180041f87  jnz     short loc_180041F60
0x180041f89  jmp     short loc_180041FF9
0x180041f8b  cmp     rdi, rsi
0x180041f8e  jz      short loc_180041FC1
0x180041f90  mov     [rcx], r8
0x180041f93  mov     [rcx+8], r8
0x180041f97  mov     rax, [rdi]
0x180041f9a  mov     [rcx], rax
0x180041f9d  mov     rax, [rdi+8]
0x180041fa1  mov     [rcx+8], rax
0x180041fa5  mov     [rdi], r8
0x180041fa8  mov     [rdi+8], r8
0x180041fac  lea     rcx, [rcx+10h]
0x180041fb0  add     rdi, 10h
0x180041fb4  cmp     rdi, rsi
0x180041fb7  jnz     short loc_180041F90
0x180041fb9  mov     r14, [rbp+57h+var_B0+8]
0x180041fbd  mov     rdi, [rbp+57h+var_B0]
0x180041fc1  lea     rcx, [rdx+10h]
0x180041fc5  cmp     rsi, r14
0x180041fc8  jz      short loc_180042001
0x180041fca  nop     word ptr [rax+rax+00h]
0x180041fd0  mov     [rcx], r8
0x180041fd3  mov     [rcx+8], r8
0x180041fd7  mov     rax, [rsi]
0x180041fda  mov     [rcx], rax
0x180041fdd  mov     rax, [rsi+8]
0x180041fe1  mov     [rcx+8], rax
0x180041fe5  mov     [rsi], r8
0x180041fe8  mov     [rsi+8], r8
0x180041fec  lea     rcx, [rcx+10h]
0x180041ff0  add     rsi, 10h
0x180041ff4  cmp     rsi, r14
0x180041ff7  jnz     short loc_180041FD0
0x180041ff9  mov     rdi, [rbp+57h+var_B0]
0x180041ffd  mov     r14, [rbp+57h+var_B0+8]
0x180042001  test    rdi, rdi
0x180042004  jz      loc_180042098
0x18004200a  cmp     rdi, r14
0x18004200d  jz      short loc_180042061
0x18004200f  nop
0x180042010  mov     rsi, [rdi+8]
0x180042014  test    rsi, rsi
0x180042017  jz      short loc_180042054
0x180042019  mov     eax, 0FFFFFFFFh
0x18004201e  lock xadd [rsi+8], eax
0x180042023  cmp     eax, 1
0x180042026  jnz     short loc_180042054
0x180042028  mov     rax, [rsi]
0x18004202b  mov     rcx, rsi
0x18004202e  mov     rax, [rax]
0x180042031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042036  mov     eax, 0FFFFFFFFh
0x18004203b  lock xadd [rsi+0Ch], eax
0x180042040  cmp     eax, 1
0x180042043  jnz     short loc_180042054
0x180042045  mov     rax, [rsi]
0x180042048  mov     rcx, rsi
0x18004204b  mov     rax, [rax+8]
0x18004204f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042054  add     rdi, 10h
0x180042058  cmp     rdi, r14
0x18004205b  jnz     short loc_180042010
0x18004205d  mov     rdi, [rbp+57h+var_B0]
0x180042061  mov     rdx, [rbp+57h+var_A0]
0x180042065  sub     rdx, rdi
0x180042068  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x18004206c  cmp     rdx, 1000h
0x180042073  jb      short loc_180042090
0x180042075  mov     rcx, [rdi-8]
0x180042079  sub     rdi, rcx
0x18004207c  sub     rdi, 8
0x180042080  cmp     rdi, 1Fh
0x180042084  ja      loc_180042114
0x18004208a  add     rdx, 27h ; '''
0x18004208e  jmp     short loc_180042093
0x180042090  mov     rcx, rdi; void *
0x180042093  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180042098  mov     [rbp+57h+var_B0], r13
0x18004209c  shl     r15, 4
0x1800420a0  add     r15, r13
0x1800420a3  lea     rdx, [r12+r13]
0x1800420a7  mov     [rbp+57h+var_A0], rdx
0x1800420ab  xor     edi, edi
0x1800420ad  mov     r8, 0FFFFFFFFFFFFFFFh
0x1800420b7  mov     [rbp+57h+var_B0+8], r15
0x1800420bb  mov     rcx, [rbx+10h]
0x1800420bf  cmp     byte ptr [rcx+19h], 0
0x1800420c3  jz      short loc_1800420EB
0x1800420c5  mov     rax, [rbx+8]
0x1800420c9  cmp     byte ptr [rax+19h], 0
0x1800420cd  jnz     short loc_1800420E3
0x1800420cf  nop
0x1800420d0  cmp     rbx, [rax+10h]
0x1800420d4  jnz     short loc_1800420E3
0x1800420d6  mov     rbx, rax
0x1800420d9  mov     rax, [rax+8]
0x1800420dd  cmp     byte ptr [rax+19h], 0
0x1800420e1  jz      short loc_1800420D0
0x1800420e3  mov     rbx, rax
0x1800420e6  jmp     loc_180041E30
0x1800420eb  mov     rbx, rcx
0x1800420ee  mov     rcx, [rcx]
0x1800420f1  cmp     byte ptr [rcx+19h], 0
0x1800420f5  jnz     loc_180041E30
0x1800420fb  nop     dword ptr [rax+rax+00h]
0x180042100  mov     rbx, rcx
0x180042103  mov     rax, [rcx]
0x180042106  mov     rcx, rax
0x180042109  cmp     byte ptr [rax+19h], 0
0x18004210d  jz      short loc_180042100
0x18004210f  jmp     loc_180041E30
0x180042114  mov     ecx, 5
0x180042119  int     29h; Win8: RtlFailFast(ecx)
0x18004211b  mov     rsi, [rbp+57h+SRWLock]
0x18004211f  lea     r12, [rsi+8]
0x180042123  mov     r15, [r12]
0x180042127  mov     rdi, [r15+8]
0x18004212b  cmp     byte ptr [rdi+19h], 0
0x18004212f  jnz     short loc_1800421AA
0x180042131  mov     r8, [rdi+10h]
0x180042135  mov     rdx, r12
0x180042138  mov     rcx, r12
0x18004213b  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VUserCacheEntry@PinCacheManager@NgcKspServer@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VUserCacheEntry@PinCacheManager@NgcKspServer@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VUserCacheEntry@PinCacheManager@NgcKspServer@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VUserCacheEntry@PinCacheManager@NgcKspServer@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<uchar> const,std::shared_ptr<NgcKspServer::PinCacheManager::UserCacheEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::vector<uchar> const,std::shared_ptr<NgcKspServer::PinCacheManager::UserCacheEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::vector<uchar> const,std::shared_ptr<NgcKspServer::PinCacheManager::UserCacheEntry>>,void *>> &,std::_Tree_node<std::pair<std::vector<uchar> const,std::shared_ptr<NgcKspServer::PinCacheManager::UserCacheEntry>>,void *> *)
0x180042140  mov     rsi, rdi
0x180042143  mov     rdi, [rdi]
0x180042146  mov     rbx, [rsi+40h]
0x18004214a  test    rbx, rbx
0x18004214d  jz      short loc_18004218A
0x18004214f  mov     eax, 0FFFFFFFFh
0x180042154  lock xadd [rbx+8], eax
0x180042159  cmp     eax, 1
0x18004215c  jnz     short loc_18004218A
0x18004215e  mov     rax, [rbx]
0x180042161  mov     rcx, rbx
0x180042164  mov     rax, [rax]
0x180042167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004216c  mov     eax, 0FFFFFFFFh
0x180042171  lock xadd [rbx+0Ch], eax
0x180042176  cmp     eax, 1
0x180042179  jnz     short loc_18004218A
0x18004217b  mov     rax, [rbx]
0x18004217e  mov     rcx, rbx
0x180042181  mov     rax, [rax+8]
0x180042185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004218a  lea     rcx, [rsi+20h]
0x18004218e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180042193  mov     edx, 48h ; 'H'; unsigned __int64
0x180042198  mov     rcx, rsi; void *
  ... truncated ...
```
