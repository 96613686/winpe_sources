# CImpTipConnection::Init(CImpTipConnectionMgr *,ITipConnection *,ITcpConnection *,char *,ushort)

- ea: `0x1800af334`
- end: `0x1800af5cd`
- name: `?Init@CImpTipConnection@@QEAAJPEAVCImpTipConnectionMgr@@PEAUITipConnection@@PEAUITcpConnection@@PEADG@Z`
- size: `665`
- prototype: `__int64 __fastcall(CImpTipConnection *__hidden this, struct CImpTipConnectionMgr *, struct ITipConnection *, struct ITcpConnection *, char *Source, unsigned __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ae090`

## callees

- `0x1800063b0`
- `0x1800af334`
- `0x1800b0f00`
- `0x1800b0f94`
- `0x1800b1f04`
- `0x1800b83ee`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af39c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af3f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af39c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af3f9`
- `msvcrt!_strdup` at `0x1800af484`
- `msvcrt!_strdup` at `0x1800af484`

## string_xrefs

- `0x1800af5a3`: `com\complus\dtc\dtc\tipgw\tipconn\src\tipconnection.cpp`
- `0x1800af410`: `failed CoTaskMemAlloc (m_cbInputBuffer + 1)`
- `0x1800af3b0`: `failed CoTaskMemAlloc (m_cbOutputBuffer)d`

## pseudocode

```c
__int64 __fastcall CImpTipConnection::Init(
        CImpTipConnection *this,
        struct CImpTipConnectionMgr *a2,
        struct ITipConnection *a3,
        struct ITcpConnection *a4,
        char *Source,
        unsigned __int16 a6)
{
  void *v10; // rax
  int *v11; // rdi
  unsigned int v12; // edi
  void *v13; // rcx
  _DWORD *v14; // rdi
  LPVOID v15; // rax
  const char *v16; // rcx
  char *v17; // rax
  const wchar_t *v18; // rax
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v23; // [rsp+28h] [rbp-30h]
  __int64 v24; // [rsp+68h] [rbp+10h] BYREF

  v24 = 0;
  if ( !a2 || !a3 || !a4 || !Source )
  {
    v12 = -2147467261;
    v18 = L"param validation failed";
    v19 = 253;
    goto LABEL_19;
  }
  v10 = (void *)*((_QWORD *)this + 21);
  v11 = (int *)((char *)this + 176);
  if ( v10 || (v10 = CoTaskMemAlloc(*v11), (*((_QWORD *)this + 21) = v10) != 0) )
  {
    memset_0(v10, 0, *v11);
    v13 = (void *)*((_QWORD *)this + 17);
    v14 = (_DWORD *)((char *)this + 144);
    if ( !v13 )
    {
      v15 = CoTaskMemAlloc(*v14 + 1);
      *((_QWORD *)this + 17) = v15;
      v13 = v15;
      if ( !v15 )
      {
        *v14 = 0;
        *((_DWORD *)this + 37) = 0;
        v12 = -2147467259;
        LODWORD(v23) = -2147467259;
        TraceStringInline(
          10,
          1,
          L"com\\complus\\dtc\\dtc\\tipgw\\tipconn\\src\\tipconnection.cpp",
          280,
          L"CImpTipConnection::Init",
          v23,
          L"failed CoTaskMemAlloc (m_cbInputBuffer + 1)");
        return v12;
      }
    }
    memset_0(v13, 0, *v14 + 1);
    *((_QWORD *)this + 13) = a2;
    *((_DWORD *)this + 18) = 2;
    *((_DWORD *)this + 19) = 2;
    (*(void (__fastcall **)(struct CImpTipConnectionMgr *))(*(_QWORD *)a2 + 8LL))(a2);
    *((_QWORD *)this + 12) = a4;
    (*(void (__fastcall **)(struct ITcpConnection *))(*(_QWORD *)a4 + 8LL))(a4);
    v16 = Source;
    *((_QWORD *)this + 15) = a3;
    v17 = _strdup(v16);
    *((_QWORD *)this + 33) = v17;
    if ( !v17 )
    {
      v12 = -2147467259;
      LODWORD(v23) = -2147467259;
      TraceStringInline(
        10,
        1,
        L"com\\complus\\dtc\\dtc\\tipgw\\tipconn\\src\\tipconnection.cpp",
        304,
        L"CImpTipConnection::Init",
        v23,
        L"m_pszHostname == NULL");
      return v12;
    }
    *((_WORD *)this + 136) = a6;
    v12 = (**(__int64 (__fastcall ***)(struct ITipConnection *, GUID *, __int64 *))a3)(
            a3,
            &IID_ITcpConnectionSink,
            &v24);
    if ( (v12 & 0x80000000) == 0 )
    {
      v20 = *((_QWORD *)this + 12);
      v21 = v24;
      *((_DWORD *)this + 32) = 1;
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 40LL))(v20, v21);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( (v12 & 0x80000000) == 0 )
      {
        CImpTipConnection::SetState(this, 327, 3, "CImpTipConnection::Init");
        CImpTipConnection::SetConnectedSubState(this, 328, 33, "CImpTipConnection::Init");
        CImpTipConnection::hangReadIfNeeded(this);
        return v12;
      }
      v18 = L"failed m_pTcpConn->RegisterSink";
      v19 = 324;
    }
    else
    {
      v18 = L"failed i_pWrappedITipConnection->QueryInterface(IID_ITcpConnectionSink)";
      v19 = 315;
    }
LABEL_19:
    LODWORD(v23) = v12;
    TraceStringInline(
      10,
      1,
      L"com\\complus\\dtc\\dtc\\tipgw\\tipconn\\src\\tipconnection.cpp",
      v19,
      L"CImpTipConnection::Init",
      v23,
      v18);
    return v12;
  }
  *v11 = 0;
  v12 = -2147467259;
  LODWORD(v23) = -2147467259;
  TraceStringInline(
    10,
    1,
    L"com\\complus\\dtc\\dtc\\tipgw\\tipconn\\src\\tipconnection.cpp",
    265,
    L"CImpTipConnection::Init",
    v23,
    L"failed CoTaskMemAlloc (m_cbOutputBuffer)d");
  return v12;
}

```

## disassembly

```asm
0x1800af334  mov     [rsp+arg_0], rbx
0x1800af339  mov     [rsp+arg_10], rbp
0x1800af33e  push    rdi
0x1800af33f  push    r14
0x1800af341  push    r15
0x1800af343  sub     rsp, 40h
0x1800af347  mov     [rsp+58h+arg_8], 0
0x1800af350  mov     r15, r9
0x1800af353  mov     r14, r8
0x1800af356  mov     rbp, rdx
0x1800af359  mov     rbx, rcx
0x1800af35c  test    rdx, rdx
0x1800af35f  jz      loc_1800AF57C
0x1800af365  test    r8, r8
0x1800af368  jz      loc_1800AF57C
0x1800af36e  test    r9, r9
0x1800af371  jz      loc_1800AF57C
0x1800af377  cmp     [rsp+58h+Source], 0
0x1800af380  jz      loc_1800AF57C
0x1800af386  mov     rax, [rcx+0A8h]
0x1800af38d  lea     rdi, [rcx+0B0h]
0x1800af394  test    rax, rax
0x1800af397  jnz     short loc_1800AF3D2
0x1800af399  movsxd  rcx, dword ptr [rdi]; cb
0x1800af39c  call    cs:__imp_CoTaskMemAlloc
0x1800af3a2  mov     [rbx+0A8h], rax
0x1800af3a9  test    rax, rax
0x1800af3ac  jnz     short loc_1800AF3D2
0x1800af3ae  mov     [rdi], eax
0x1800af3b0  lea     rcx, aFailedCotaskme; "failed CoTaskMemAlloc (m_cbOutputBuffer"...
0x1800af3b7  mov     eax, 80004005h
0x1800af3bc  mov     [rsp+58h+var_28], rcx
0x1800af3c1  mov     edi, eax
0x1800af3c3  mov     dword ptr [rsp+58h+var_30], eax
0x1800af3c7  mov     r9d, 109h
0x1800af3cd  jmp     loc_1800AF597
0x1800af3d2  movsxd  r8, dword ptr [rdi]; Size
0x1800af3d5  xor     edx, edx; Val
0x1800af3d7  mov     rcx, rax; void *
0x1800af3da  call    memset_0
0x1800af3df  mov     rcx, [rbx+88h]; void *
0x1800af3e6  lea     rdi, [rbx+90h]
0x1800af3ed  test    rcx, rcx
0x1800af3f0  jnz     short loc_1800AF438
0x1800af3f2  mov     eax, [rdi]
0x1800af3f4  inc     eax
0x1800af3f6  movsxd  rcx, eax; cb
0x1800af3f9  call    cs:__imp_CoTaskMemAlloc
0x1800af3ff  mov     [rbx+88h], rax
0x1800af406  mov     rcx, rax
0x1800af409  test    rax, rax
0x1800af40c  jnz     short loc_1800AF438
0x1800af40e  mov     [rdi], eax
0x1800af410  lea     rcx, aFailedCotaskme_0; "failed CoTaskMemAlloc (m_cbInputBuffer "...
0x1800af417  mov     [rbx+94h], eax
0x1800af41d  mov     r9d, 118h
0x1800af423  mov     eax, 80004005h
0x1800af428  mov     [rsp+58h+var_28], rcx
0x1800af42d  mov     edi, eax
0x1800af42f  mov     dword ptr [rsp+58h+var_30], eax
0x1800af433  jmp     loc_1800AF597
0x1800af438  mov     eax, [rdi]
0x1800af43a  xor     edx, edx; Val
0x1800af43c  inc     eax
0x1800af43e  movsxd  r8, eax; Size
0x1800af441  call    memset_0
0x1800af446  mov     eax, 2
0x1800af44b  mov     [rbx+68h], rbp
0x1800af44f  mov     [rbx+48h], eax
0x1800af452  mov     rcx, rbp
0x1800af455  mov     [rbx+4Ch], eax
0x1800af458  mov     rax, [rbp+0]
0x1800af45c  mov     rax, [rax+8]
0x1800af460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af465  mov     [rbx+60h], r15
0x1800af469  mov     rcx, r15
0x1800af46c  mov     rax, [r15]
0x1800af46f  mov     rax, [rax+8]
0x1800af473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af478  mov     rcx, [rsp+58h+Source]; Source
0x1800af480  mov     [rbx+78h], r14
0x1800af484  call    cs:__imp__strdup
0x1800af48a  mov     [rbx+108h], rax
0x1800af491  test    rax, rax
0x1800af494  jnz     short loc_1800AF4B8
0x1800af496  mov     eax, 80004005h
0x1800af49b  lea     rcx, aMPszhostnameNu; "m_pszHostname == NULL"
0x1800af4a2  mov     [rsp+58h+var_28], rcx
0x1800af4a7  mov     edi, eax
0x1800af4a9  mov     dword ptr [rsp+58h+var_30], eax
0x1800af4ad  mov     r9d, 130h
0x1800af4b3  jmp     loc_1800AF597
0x1800af4b8  movzx   eax, [rsp+58h+arg_28]
0x1800af4c0  lea     r8, [rsp+58h+arg_8]
0x1800af4c5  mov     [rbx+110h], ax
0x1800af4cc  lea     rdx, IID_ITcpConnectionSink
0x1800af4d3  mov     rax, [r14]
0x1800af4d6  mov     rcx, r14
0x1800af4d9  mov     rax, [rax]
0x1800af4dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af4e1  mov     edi, eax
0x1800af4e3  test    eax, eax
0x1800af4e5  jns     short loc_1800AF4F9
0x1800af4e7  lea     rax, aFailedIPwrappe; "failed i_pWrappedITipConnection->QueryI"...
0x1800af4ee  mov     r9d, 13Bh
0x1800af4f4  jmp     loc_1800AF58E
0x1800af4f9  mov     rcx, [rbx+60h]
0x1800af4fd  mov     rdx, [rsp+58h+arg_8]
0x1800af502  mov     dword ptr [rbx+80h], 1
0x1800af50c  mov     rax, [rcx]
0x1800af50f  mov     rax, [rax+28h]
0x1800af513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af518  mov     rcx, [rsp+58h+arg_8]
0x1800af51d  mov     edi, eax
0x1800af51f  mov     rax, [rcx]
0x1800af522  mov     rax, [rax+10h]
0x1800af526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af52b  test    edi, edi
0x1800af52d  jns     short loc_1800AF53E
0x1800af52f  lea     rax, aFailedMPtcpcon; "failed m_pTcpConn->RegisterSink"
0x1800af536  mov     r9d, 144h
0x1800af53c  jmp     short loc_1800AF58E
0x1800af53e  lea     r9, aCimptipconnect_13; "CImpTipConnection::Init"
0x1800af545  mov     edx, 147h
0x1800af54a  mov     r8d, 3
0x1800af550  mov     rcx, rbx
0x1800af553  call    ?SetState@CImpTipConnection@@AEAAXHW4ETipConnectionState@@PEAD@Z; CImpTipConnection::SetState(int,ETipConnectionState,char *)
0x1800af558  lea     r9, aCimptipconnect_13; "CImpTipConnection::Init"
0x1800af55f  mov     edx, 148h
0x1800af564  mov     r8d, 21h ; '!'
0x1800af56a  mov     rcx, rbx
0x1800af56d  call    ?SetConnectedSubState@CImpTipConnection@@AEAAXHW4ETipConnectionConnectedSubState@@PEAD@Z; CImpTipConnection::SetConnectedSubState(int,ETipConnectionConnectedSubState,char *)
0x1800af572  mov     rcx, rbx; this
0x1800af575  call    ?hangReadIfNeeded@CImpTipConnection@@AEAAXXZ; CImpTipConnection::hangReadIfNeeded(void)
0x1800af57a  jmp     short loc_1800AF5B7
0x1800af57c  mov     edi, 80004003h
0x1800af581  lea     rax, aParamValidatio; "param validation failed"
0x1800af588  mov     r9d, 0FDh
0x1800af58e  mov     [rsp+58h+var_28], rax
0x1800af593  mov     dword ptr [rsp+58h+var_30], edi
0x1800af597  mov     edx, 1
0x1800af59c  lea     rax, aCimptipconnect_39; "CImpTipConnection::Init"
0x1800af5a3  lea     r8, aComComplusDtcD_30; "com\\complus\\dtc\\dtc\\tipgw\\tipconn"...
0x1800af5aa  mov     [rsp+58h+var_38], rax
0x1800af5af  lea     ecx, [rdx+9]
0x1800af5b2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800af5b7  mov     rbx, [rsp+58h+arg_0]
0x1800af5bc  mov     eax, edi
0x1800af5be  mov     rbp, [rsp+58h+arg_10]
0x1800af5c3  add     rsp, 40h
0x1800af5c7  pop     r15
0x1800af5c9  pop     r14
0x1800af5cb  pop     rdi
0x1800af5cc  retn
```
