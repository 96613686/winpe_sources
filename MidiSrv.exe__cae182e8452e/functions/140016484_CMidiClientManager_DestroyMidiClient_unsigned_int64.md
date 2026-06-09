# CMidiClientManager::DestroyMidiClient(unsigned __int64)

- ea: `0x140016484`
- end: `0x140016b64`
- name: `?DestroyMidiClient@CMidiClientManager@@QEAAJ_K@Z`
- size: `1760`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, unsigned __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14001470c`
- `0x14003bc20`
- `0x14003dae0`

## callees

- `0x140001ad4`
- `0x1400054c0`
- `0x140005868`
- `0x140007c20`
- `0x14000984c`
- `0x14000a6b4`
- `0x1400130cc`
- `0x140013a38`
- `0x140016484`
- `0x14001e17c`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400165e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400165e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016aa7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016b35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016aa7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140016b35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400165d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400165d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001651c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001651c`

## string_xrefs

- `0x140016b1b`: `avcore\midi2\service\exe\midiclientmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CMidiClientManager::DestroyMidiClient(PSRWLOCK SRWLock, __int64 *a2)
{
  __int64 *v2; // r13
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *Ptr; // rcx
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  __int64 *v10; // rbx
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 *v13; // r14
  __int64 v14; // r15
  PVOID v15; // rdi
  void (__fastcall *v16)(PVOID, _OWORD *, _QWORD, char **, __int64 *); // rbx
  char **v17; // r9
  PSRWLOCK v18; // r12
  _QWORD *v19; // rdi
  __int64 v20; // rcx
  __int64 *v21; // rbx
  __int64 **v22; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  __int64 *v25; // rbx
  __int64 **v26; // rcx
  __int64 *n; // rax
  __int64 *ii; // rcx
  __int64 *jj; // rbx
  _QWORD *v30; // rax
  __int64 *v31; // rcx
  __int64 v32; // rdi
  __int64 v33; // rdx
  __int64 **v34; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  _QWORD *v37; // rbx
  __int64 v38; // r14
  __int64 *mm; // rdi
  _QWORD *v40; // rax
  __int64 *v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rdx
  _BYTE *v44; // rax
  __int64 kk; // rax
  __int64 *v46; // rcx
  _DWORD *v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  int v51; // [rsp+20h] [rbp-79h]
  const char *v52; // [rsp+40h] [rbp-59h] BYREF
  __int64 *v53; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v54[2]; // [rsp+50h] [rbp-49h] BYREF
  _OWORD v55[2]; // [rsp+60h] [rbp-39h] BYREF
  __int64 *v56[2]; // [rsp+80h] [rbp-19h] BYREF
  char *v57[4]; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v2 = a2;
  v56[0] = a2;
  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v53 = v2;
    v52 = (const char *)L"Enter";
    *(_QWORD *)&v55[0] = SRWLock;
    v54[0] = "CMidiClientManager::DestroyMidiClient";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (__int64)v4,
      (__int64)byte_140087913,
      v5,
      v6,
      v54,
      (__int64)v55,
      &v52);
  }
  AcquireSRWLockShared(SRWLock);
  v54[0] = SRWLock;
  Ptr = SRWLock[9].Ptr;
  v8 = (_QWORD *)Ptr[1];
  HIDWORD(v55[0]) = 0;
  v9 = Ptr;
  while ( !*((_BYTE *)v8 + 25) )
  {
    if ( v8[4] >= (unsigned __int64)v2 )
    {
      v9 = v8;
      v8 = (_QWORD *)*v8;
    }
    else
    {
      v8 = (_QWORD *)v8[2];
    }
  }
  if ( !*((_BYTE *)v9 + 25) && (unsigned __int64)v2 >= v9[4] && v9 != Ptr )
  {
    v10 = (__int64 *)v9[5];
    v53 = v10;
    if ( v10 )
      (*(void (__fastcall **)(__int64 *))(*v10 + 8))(v10);
    v52 = (const char *)v10;
    if ( v10 )
      (*(void (__fastcall **)(__int64 *))(*v10 + 8))(v10);
    (*(void (__fastcall **)(__int64 *))(*v10 + 48))(v10);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
      (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
    }
  }
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  AcquireSRWLockExclusive(SRWLock);
  v54[0] = SRWLock;
  v11 = (__int64 *)SRWLock[9].Ptr;
  v12 = v11[1];
  HIDWORD(v55[0]) = 0;
  v13 = v11;
  v53 = v11;
  if ( !*(_BYTE *)(v12 + 25) )
  {
    do
    {
      if ( *(_QWORD *)(v12 + 32) >= (unsigned __int64)v2 )
      {
        v13 = (__int64 *)v12;
        v12 = *(_QWORD *)v12;
      }
      else
      {
        v12 = *(_QWORD *)(v12 + 16);
      }
    }
    while ( !*(_BYTE *)(v12 + 25) );
    v53 = v13;
  }
  if ( *((_BYTE *)v13 + 25) || (unsigned __int64)v2 < v13[4] || v13 == v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56C,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientmanager.cpp",
      (const char *)0x80070057LL,
      v51);
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 2147942487LL;
  }
  else
  {
    v14 = v13[5];
    v56[1] = (__int64 *)v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v52 = (const char *)v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v15 = SRWLock[7].Ptr;
    v16 = *(void (__fastcall **)(PVOID, _OWORD *, _QWORD, char **, __int64 *))(*(_QWORD *)v15 + 48LL);
    std::wstring::wstring((__int64)v57, v13[5] + 16);
    v17 = v57;
    if ( v57[3] > (char *)7 )
      v17 = (char **)v57[0];
    v55[0] = *(_OWORD *)(v14 + 144);
    v16(v15, v55, *(unsigned int *)(v14 + 160), v17, v2);
    std::wstring::~wstring(v57);
    v18 = SRWLock + 13;
    v19 = *(_QWORD **)SRWLock[13].Ptr;
    while ( v19 != v18->Ptr )
    {
      v20 = v19[8];
      *(_QWORD *)&v55[0] = v20;
      if ( v20 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        v20 = *(_QWORD *)&v55[0];
      }
      (*(void (__fastcall **)(__int64, const char **))(*(_QWORD *)v20 + 64LL))(v20, &v52);
      (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)&v55[0] + 128LL))(*(_QWORD *)&v55[0], v2);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&v55[0] + 112LL))(*(_QWORD *)&v55[0]) )
      {
        v34 = (__int64 **)v19[2];
        if ( *((_BYTE *)v34 + 25) )
        {
          for ( i = v19[1]; !*(_BYTE *)(i + 25) && v19 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
            v19 = (_QWORD *)i;
          v19 = (_QWORD *)i;
        }
        else
        {
          v19 = (_QWORD *)v19[2];
          for ( j = *v34; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v19 = j;
        }
      }
      else
      {
        v21 = *(__int64 **)SRWLock[11].Ptr;
        while ( v21 != SRWLock[11].Ptr )
        {
          (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v21[8] + 64LL))(v21[8], v55);
          v22 = (__int64 **)v21[2];
          if ( *((_BYTE *)v22 + 25) )
          {
            for ( k = (__int64 *)v21[1]; !*((_BYTE *)k + 25) && v21 == (__int64 *)k[2]; k = (__int64 *)k[1] )
              v21 = k;
            v21 = k;
          }
          else
          {
            v21 = (__int64 *)v21[2];
            for ( m = *v22; !*((_BYTE *)m + 25); m = (__int64 *)*m )
              v21 = m;
          }
        }
        v25 = *(__int64 **)v18->Ptr;
        while ( v25 != v18->Ptr )
        {
          (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v25[8] + 64LL))(v25[8], v55);
          v26 = (__int64 **)v25[2];
          if ( *((_BYTE *)v26 + 25) )
          {
            for ( n = (__int64 *)v25[1]; !*((_BYTE *)n + 25) && v25 == (__int64 *)n[2]; n = (__int64 *)n[1] )
              v25 = n;
            v25 = n;
          }
          else
          {
            v25 = (__int64 *)v25[2];
            for ( ii = *v26; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
              v25 = ii;
          }
        }
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v55[0] + 48LL))(*(_QWORD *)&v55[0]);
        jj = (__int64 *)v19[2];
        if ( *((_BYTE *)jj + 25) )
        {
          v30 = v19;
          for ( jj = (__int64 *)v19[1]; !*((_BYTE *)jj + 25) && v30 == (_QWORD *)jj[2]; jj = (__int64 *)jj[1] )
            v30 = jj;
        }
        else
        {
          v31 = (__int64 *)*jj;
          if ( !*(_BYTE *)(*jj + 25) )
          {
            do
            {
              jj = v31;
              v31 = (__int64 *)*v31;
            }
            while ( !*((_BYTE *)v31 + 25) );
          }
        }
        v32 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,MidiSessionConnectionEntry>>>::_Extract(
                &SRWLock[13],
                v19);
        v33 = *(_QWORD *)(v32 + 64);
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        std::wstring::~wstring((char **)(v32 + 32));
        operator delete((void *)v32);
        v19 = jj;
      }
      if ( *(_QWORD *)&v55[0] )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v55[0] + 16LL))(*(_QWORD *)&v55[0]);
    }
    v37 = *(_QWORD **)SRWLock[11].Ptr;
    while ( v37 != SRWLock[11].Ptr )
    {
      v38 = v37[8];
      *(_QWORD *)&v55[0] = v38;
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
      (*(void (__fastcall **)(__int64, const char **))(*(_QWORD *)v38 + 64LL))(v38, &v52);
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 128LL))(v38, v2);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v38 + 112LL))(v38) )
      {
        v44 = (_BYTE *)v37[2];
        if ( v44[25] )
        {
          for ( kk = v37[1]; !*(_BYTE *)(kk + 25) && v37 == *(_QWORD **)(kk + 16); kk = *(_QWORD *)(kk + 8) )
            v37 = (_QWORD *)kk;
          v37 = (_QWORD *)kk;
        }
        else
        {
          v37 = (_QWORD *)v37[2];
          if ( !*(_BYTE *)(*(_QWORD *)v44 + 25LL) )
          {
            v46 = (__int64 *)*v37;
            do
            {
              v37 = v46;
              v46 = (__int64 *)*v46;
            }
            while ( !*((_BYTE *)v46 + 25) );
          }
        }
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 48LL))(v38);
        mm = (__int64 *)v37[2];
        if ( *((_BYTE *)mm + 25) )
        {
          v40 = v37;
          for ( mm = (__int64 *)v37[1]; !*((_BYTE *)mm + 25) && v40 == (_QWORD *)mm[2]; mm = (__int64 *)mm[1] )
            v40 = mm;
        }
        else
        {
          v41 = (__int64 *)*mm;
          if ( !*(_BYTE *)(*mm + 25) )
          {
            do
            {
              mm = v41;
              v41 = (__int64 *)*v41;
            }
            while ( !*((_BYTE *)v41 + 25) );
          }
        }
        v42 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,MidiSessionConnectionEntry>>>::_Extract(
                &SRWLock[11],
                v37);
        v43 = *(_QWORD *)(v42 + 64);
        if ( v43 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        std::wstring::~wstring((char **)(v42 + 32));
        operator delete((void *)v42);
        v37 = mm;
        v2 = v56[0];
      }
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    std::_Tree<std::_Tmap_traits<unsigned __int64,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,wil::com_ptr_t<CMidiPipe,wil::err_returncode_policy>>>>>,0>(
      (__int64)&SRWLock[9],
      v56,
      v53);
    if ( v52 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v52 + 16LL))(v52);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    ReleaseSRWLockExclusive(SRWLock);
    v47 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v47 > 4u )
    {
      v56[0] = v2;
      v54[0] = L"Exit success";
      v53 = (__int64 *)SRWLock;
      v52 = "CMidiClientManager::DestroyMidiClient";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        (__int64)v47,
        (__int64)qword_140087E08,
        v48,
        v49,
        &v52,
        (__int64)&v53,
        v54);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140016484  mov     [rsp-8+arg_10], rbx
0x140016489  push    rbp
0x14001648a  push    rsi
0x14001648b  push    rdi
0x14001648c  push    r12
0x14001648e  push    r13
0x140016490  push    r14
0x140016492  push    r15
0x140016494  lea     rbp, [rsp-27h]
0x140016499  sub     rsp, 0C0h
0x1400164a0  mov     rax, cs:__security_cookie
0x1400164a7  xor     rax, rsp
0x1400164aa  mov     [rbp+57h+var_40], rax
0x1400164ae  mov     r13, rdx
0x1400164b1  mov     [rbp+57h+var_70], rdx
0x1400164b5  mov     rsi, rcx
0x1400164b8  xor     r12d, r12d
0x1400164bb  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400164c0  mov     rcx, [rax+8]
0x1400164c4  mov     eax, [rcx]
0x1400164c6  lea     rdx, aCmidiclientman_6; "CMidiClientManager::DestroyMidiClient"
0x1400164cd  cmp     eax, 4
0x1400164d0  jbe     short loc_140016519
0x1400164d2  mov     [rbp+57h+var_A8], r13
0x1400164d6  lea     rax, aEnter; "Enter"
0x1400164dd  mov     [rbp+57h+var_B0], rax
0x1400164e1  mov     qword ptr [rbp+57h+var_90], rsi
0x1400164e5  mov     [rbp+57h+var_A0], rdx
0x1400164e9  lea     rax, [rbp+57h+var_A8]
0x1400164ed  mov     [rsp+0F0h+var_B8], rax
0x1400164f2  lea     rax, [rbp+57h+var_B0]
0x1400164f6  mov     [rsp+0F0h+var_C0], rax
0x1400164fb  lea     rax, [rbp+57h+var_90]
0x1400164ff  mov     [rsp+0F0h+var_C8], rax
0x140016504  lea     rax, [rbp+57h+var_A0]
0x140016508  mov     [rsp+0F0h+var_D0], rax
0x14001650d  lea     rdx, byte_140087913
0x140016514  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x140016519  mov     rcx, rsi; SRWLock
0x14001651c  call    cs:__imp_AcquireSRWLockShared
0x140016522  mov     [rbp+57h+var_A0], rsi
0x140016526  mov     rcx, [rsi+48h]
0x14001652a  mov     rax, [rcx+8]
0x14001652e  xor     edx, edx
0x140016530  mov     dword ptr [rbp+57h+var_90+0Ch], edx
0x140016533  mov     rbx, rcx
0x140016536  jmp     short loc_14001654A
0x140016538  cmp     [rax+20h], r13
0x14001653c  jnb     short loc_140016544
0x14001653e  mov     rax, [rax+10h]
0x140016542  jmp     short loc_14001654A
0x140016544  mov     rbx, rax
0x140016547  mov     rax, [rax]
0x14001654a  cmp     [rax+19h], r12b
0x14001654e  jz      short loc_140016538
0x140016550  cmp     [rbx+19h], r12b
0x140016554  jnz     short loc_1400165D1
0x140016556  cmp     r13, [rbx+20h]
0x14001655a  jb      short loc_1400165D1
0x14001655c  cmp     rbx, rcx
0x14001655f  jz      short loc_1400165D1
0x140016561  mov     rbx, [rbx+28h]
0x140016565  mov     [rbp+57h+var_A8], rbx
0x140016569  test    rbx, rbx
0x14001656c  jz      short loc_14001657E
0x14001656e  mov     rax, [rbx]
0x140016571  mov     rcx, rbx
0x140016574  mov     rax, [rax+8]
0x140016578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001657d  nop
0x14001657e  mov     [rbp+57h+var_B0], rbx
0x140016582  test    rbx, rbx
0x140016585  jz      short loc_140016597
0x140016587  mov     rax, [rbx]
0x14001658a  mov     rcx, rbx
0x14001658d  mov     rax, [rax+8]
0x140016591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016596  nop
0x140016597  mov     rax, [rbx]
0x14001659a  mov     rcx, rbx
0x14001659d  mov     rax, [rax+30h]
0x1400165a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400165a6  nop
0x1400165a7  test    rbx, rbx
0x1400165aa  jz      short loc_1400165BC
0x1400165ac  mov     rax, [rbx]
0x1400165af  mov     rcx, rbx
0x1400165b2  mov     rax, [rax+10h]
0x1400165b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400165bb  nop
0x1400165bc  test    rbx, rbx
0x1400165bf  jz      short loc_1400165D1
0x1400165c1  mov     rax, [rbx]
0x1400165c4  mov     rcx, rbx
0x1400165c7  mov     rax, [rax+10h]
0x1400165cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400165d0  nop
0x1400165d1  test    rsi, rsi
0x1400165d4  jz      short loc_1400165DF
0x1400165d6  mov     rcx, rsi; SRWLock
0x1400165d9  call    cs:__imp_ReleaseSRWLockShared
0x1400165df  mov     rcx, rsi; SRWLock
0x1400165e2  call    cs:__imp_AcquireSRWLockExclusive
0x1400165e8  mov     [rbp+57h+var_A0], rsi
0x1400165ec  mov     rcx, [rsi+48h]
0x1400165f0  mov     rax, [rcx+8]
0x1400165f4  xor     edx, edx
0x1400165f6  mov     dword ptr [rbp+57h+var_90+0Ch], edx
0x1400165f9  mov     r14, rcx
0x1400165fc  mov     [rbp+57h+var_A8], rcx
0x140016600  cmp     [rax+19h], r12b
0x140016604  jnz     short loc_140016622
0x140016606  cmp     [rax+20h], r13
0x14001660a  jnb     short loc_140016612
0x14001660c  mov     rax, [rax+10h]
0x140016610  jmp     short loc_140016618
0x140016612  mov     r14, rax
0x140016615  mov     rax, [rax]
0x140016618  cmp     [rax+19h], r12b
0x14001661c  jz      short loc_140016606
0x14001661e  mov     [rbp+57h+var_A8], r14
0x140016622  cmp     [r14+19h], r12b
0x140016626  jnz     loc_140016B0F
0x14001662c  cmp     r13, [r14+20h]
0x140016630  jb      loc_140016B0F
0x140016636  cmp     r14, rcx
0x140016639  jz      loc_140016B0F
0x14001663f  mov     r15, [r14+28h]
0x140016643  mov     [rbp+57h+var_68], r15
0x140016647  test    r15, r15
0x14001664a  jz      short loc_14001665C
0x14001664c  mov     rax, [r15]
0x14001664f  mov     rcx, r15
0x140016652  mov     rax, [rax+8]
0x140016656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001665b  nop
0x14001665c  mov     [rbp+57h+var_B0], r15
0x140016660  test    r15, r15
0x140016663  jz      short loc_140016675
0x140016665  mov     rax, [r15]
0x140016668  mov     rcx, r15
0x14001666b  mov     rax, [rax+8]
0x14001666f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016674  nop
0x140016675  mov     rdi, [rsi+38h]
0x140016679  mov     rax, [rdi]
0x14001667c  mov     rbx, [rax+30h]
0x140016680  mov     rdx, [r14+28h]
0x140016684  add     rdx, 10h
0x140016688  lea     rcx, [rbp+57h+var_60]
0x14001668c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140016691  nop
0x140016692  lea     r9, [rbp+57h+var_60]
0x140016696  cmp     [rbp+57h+var_48], 7
0x14001669b  cmova   r9, [rbp+57h+var_60]
0x1400166a0  movups  xmm0, xmmword ptr [r15+90h]
0x1400166a8  movdqu  [rbp+57h+var_90], xmm0
0x1400166ad  mov     [rsp+0F0h+var_D0], r13
0x1400166b2  mov     r8d, [r15+0A0h]
0x1400166b9  lea     rdx, [rbp+57h+var_90]
0x1400166bd  mov     rcx, rdi
0x1400166c0  mov     rax, rbx
0x1400166c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400166c8  nop
0x1400166c9  lea     rcx, [rbp+57h+var_60]; void *
0x1400166cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400166d2  lea     r12, [rsi+68h]
0x1400166d6  mov     rdi, [r12]
0x1400166da  mov     rdi, [rdi]
0x1400166dd  xor     r14d, r14d
0x1400166e0  cmp     rdi, [r12]
0x1400166e4  jz      loc_140016904
0x1400166ea  mov     rcx, [rdi+40h]
0x1400166ee  mov     qword ptr [rbp+57h+var_90], rcx
0x1400166f2  test    rcx, rcx
0x1400166f5  jz      short loc_140016707
0x1400166f7  mov     rax, [rcx]
0x1400166fa  mov     rax, [rax+8]
0x1400166fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016703  mov     rcx, qword ptr [rbp+57h+var_90]
0x140016707  mov     rax, [rcx]
0x14001670a  lea     rdx, [rbp+57h+var_B0]
0x14001670e  mov     rax, [rax+40h]
0x140016712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016717  mov     rcx, qword ptr [rbp+57h+var_90]
0x14001671b  mov     rax, [rcx]
0x14001671e  mov     rdx, r13
0x140016721  mov     rax, [rax+80h]
0x140016728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001672d  mov     rcx, qword ptr [rbp+57h+var_90]
0x140016731  mov     rax, [rcx]
0x140016734  mov     rax, [rax+70h]
0x140016738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001673d  test    eax, eax
0x14001673f  jnz     loc_1400168A6
0x140016745  mov     rbx, [rsi+58h]
0x140016749  mov     rbx, [rbx]
0x14001674c  cmp     rbx, [rsi+58h]
0x140016750  jz      short loc_1400167AB
0x140016752  mov     rcx, [rbx+40h]
0x140016756  mov     rax, [rcx]
0x140016759  lea     rdx, [rbp+57h+var_90]
0x14001675d  mov     rax, [rax+40h]
0x140016761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016766  mov     rcx, [rbx+10h]
0x14001676a  cmp     [rcx+19h], r14b
0x14001676e  jz      short loc_14001678E
0x140016770  mov     rax, [rbx+8]
0x140016774  jmp     short loc_140016783
0x140016776  cmp     rbx, [rax+10h]
0x14001677a  jnz     short loc_140016789
0x14001677c  mov     rbx, rax
0x14001677f  mov     rax, [rax+8]
0x140016783  cmp     [rax+19h], r14b
0x140016787  jz      short loc_140016776
0x140016789  mov     rbx, rax
0x14001678c  jmp     short loc_14001674C
0x14001678e  mov     rbx, rcx
0x140016791  mov     rcx, [rcx]
0x140016794  cmp     [rcx+19h], r14b
0x140016798  jnz     short loc_14001674C
0x14001679a  mov     rbx, rcx
0x14001679d  mov     rax, [rcx]
0x1400167a0  mov     rcx, rax
0x1400167a3  cmp     [rax+19h], r14b
0x1400167a7  jz      short loc_14001679A
0x1400167a9  jmp     short loc_14001674C
0x1400167ab  mov     rbx, [r12]
0x1400167af  mov     rbx, [rbx]
0x1400167b2  cmp     rbx, [r12]
0x1400167b6  jz      short loc_140016811
0x1400167b8  mov     rcx, [rbx+40h]
0x1400167bc  mov     rax, [rcx]
0x1400167bf  lea     rdx, [rbp+57h+var_90]
0x1400167c3  mov     rax, [rax+40h]
0x1400167c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400167cc  mov     rcx, [rbx+10h]
0x1400167d0  cmp     [rcx+19h], r14b
0x1400167d4  jz      short loc_1400167F4
0x1400167d6  mov     rax, [rbx+8]
0x1400167da  jmp     short loc_1400167E9
0x1400167dc  cmp     rbx, [rax+10h]
0x1400167e0  jnz     short loc_1400167EF
0x1400167e2  mov     rbx, rax
0x1400167e5  mov     rax, [rax+8]
0x1400167e9  cmp     [rax+19h], r14b
0x1400167ed  jz      short loc_1400167DC
0x1400167ef  mov     rbx, rax
0x1400167f2  jmp     short loc_1400167B2
0x1400167f4  mov     rbx, rcx
0x1400167f7  mov     rcx, [rcx]
0x1400167fa  cmp     [rcx+19h], r14b
0x1400167fe  jnz     short loc_1400167B2
0x140016800  mov     rbx, rcx
0x140016803  mov     rax, [rcx]
0x140016806  mov     rcx, rax
0x140016809  cmp     [rax+19h], r14b
0x14001680d  jz      short loc_140016800
0x14001680f  jmp     short loc_1400167B2
0x140016811  mov     rcx, qword ptr [rbp+57h+var_90]
0x140016815  mov     rax, [rcx]
0x140016818  mov     rax, [rax+30h]
0x14001681c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016821  mov     rbx, [rdi+10h]
0x140016825  cmp     [rbx+19h], r14b
0x140016829  jz      short loc_140016849
0x14001682b  mov     rax, rdi
0x14001682e  mov     rbx, [rdi+8]
0x140016832  jmp     short loc_140016841
0x140016834  cmp     rax, [rbx+10h]
0x140016838  jnz     short loc_140016861
0x14001683a  mov     rax, rbx
0x14001683d  mov     rbx, [rbx+8]
0x140016841  cmp     [rbx+19h], r14b
0x140016845  jz      short loc_140016834
0x140016847  jmp     short loc_140016861
0x140016849  mov     rcx, [rbx]
0x14001684c  cmp     [rcx+19h], r14b
0x140016850  jnz     short loc_140016861
0x140016852  mov     rbx, rcx
0x140016855  mov     rax, [rcx]
0x140016858  mov     rcx, rax
0x14001685b  cmp     [rax+19h], r14b
0x14001685f  jz      short loc_140016852
0x140016861  mov     rdx, rdi
0x140016864  mov     rcx, r12
0x140016867  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiSessionConnectionEntry@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,MidiSessionConnectionEntry>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,MidiSessionConnectionEntry>>>,std::_Iterator_base0>)
0x14001686c  mov     rdi, rax
0x14001686f  mov     rdx, [rax+40h]
0x140016873  test    rdx, rdx
0x140016876  jz      short loc_140016888
0x140016878  mov     rcx, [rdx]
0x14001687b  mov     rax, [rcx+10h]
0x14001687f  mov     rcx, rdx
0x140016882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016887  nop
0x140016888  lea     rcx, [rdi+20h]; void *
0x14001688c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016891  mov     edx, 48h ; 'H'
0x140016896  mov     rcx, rdi; Block
  ... truncated ...
```
