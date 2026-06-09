# ipx::mtf::CMtfSuggestionClient::RepairServerConnection(void)

- ea: `0x180019b00`
- end: `0x18001a143`
- name: `?RepairServerConnection@CMtfSuggestionClient@mtf@ipx@@IEAAJXZ`
- size: `1603`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this)`
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016cf0`
- `0x180017a40`
- `0x180019a28`

## callees

- `0x180003ab4`
- `0x180006074`
- `0x180013b90`
- `0x180014848`
- `0x180016b18`
- `0x180016cc0`
- `0x180019b00`
- `0x18001cdd4`
- `0x18001cf68`
- `0x18001d1f4`
- `0x18001e1f4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019cca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019cca`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::RepairServerConnection(ipx::mtf::CMtfSuggestionClient *this)
{
  _BYTE *v2; // rbx
  int v3; // ecx
  int v4; // ecx
  char *v5; // rax
  int (__fastcall ****v6)(__int64, GUID *, struct IMtfPropertyBag **); // r14
  __int64 (__fastcall ***v7)(_QWORD, GUID *, struct IMtfPropertyBag **); // rcx
  __int64 (__fastcall **v8)(_QWORD, GUID *, struct IMtfPropertyBag **); // rax
  int v9; // eax
  _BYTE *v10; // r15
  struct IMtfPropertyBag *v11; // r15
  __int64 (__fastcall *v12)(struct IMtfPropertyBag *, char *, _QWORD **); // r12
  _QWORD *v13; // rcx
  int v14; // eax
  unsigned int v15; // r15d
  int (__fastcall ***v17)(__int64, GUID *, struct IMtfPropertyBag **); // rcx
  const char *v18; // r9
  int v19; // ebx
  int (__fastcall ***v20)(__int64, GUID *, struct IMtfPropertyBag **); // rcx
  int (__fastcall **v21)(__int64, GUID *, struct IMtfPropertyBag **); // rax
  char *v22; // r15
  int v23; // eax
  unsigned int v24; // ebx
  int v25; // eax
  struct IMtfPropertyBag *v26; // rcx
  int v27; // eax
  int v28; // eax
  struct IMtfPropertyBag *v29; // rcx
  struct IMtfPropertyBag *v30; // rcx
  unsigned __int64 v31; // r15
  __int64 v32; // rbx
  int v33; // eax
  unsigned int v34; // r14d
  __int64 v35; // rax
  int v36; // eax
  int v37; // eax
  unsigned int v38; // eax
  void *v39; // rdx
  unsigned int v40; // r8d
  unsigned int v41; // [rsp+20h] [rbp-58h]
  unsigned int v42; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  struct IMtfPropertyBag *v44; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v45; // [rsp+88h] [rbp+10h] BYREF
  ipx::mtf::CMtfSuggestionClient *v46; // [rsp+90h] [rbp+18h]

  v2 = (char *)this + 145;
  v3 = *((unsigned __int8 *)this + 145);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 1 )
        v5 = "InProc";
      else
        v5 = "Unknown";
    }
    else
    {
      v5 = "DCOM";
    }
  }
  else
  {
    v5 = "CoreUI";
  }
  v44 = (struct IMtfPropertyBag *)v5;
  MtfPlatformTelemetry::RepairMtfConnection<char const *>(&v44);
  v45 = 0;
  if ( *v2 )
  {
    v6 = (int (__fastcall ****)(__int64, GUID *, struct IMtfPropertyBag **))((char *)this + 112);
    v10 = v2;
  }
  else
  {
    v44 = 0;
    v6 = (int (__fastcall ****)(__int64, GUID *, struct IMtfPropertyBag **))((char *)this + 112);
    v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IMtfPropertyBag **))*((_QWORD *)this + 14);
    v8 = *v7;
    v44 = 0;
    v9 = (*v8)(v7, &GUID_c44e8e9c_08ec_4acd_b1cd_f5430416fb32, &v44);
    if ( v9 >= 0 )
    {
      v11 = v44;
      v12 = *(__int64 (__fastcall **)(struct IMtfPropertyBag *, char *, _QWORD **))(*(_QWORD *)v44 + 24LL);
      v13 = v45;
      v45 = 0;
      if ( v13 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v13 + 16LL))(v13, *v13);
      v14 = v12(v11, (char *)this + 48, &v45);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x919,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v14,
          v41);
        if ( v44 )
          (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v44 + 16LL))(v44);
        if ( v45 )
          (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x917,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v9,
        v41);
    }
    if ( v44 )
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v44 + 16LL))(v44);
    v10 = (char *)this + 145;
  }
  v17 = *v6;
  *v6 = 0;
  if ( v17 )
    ((void (__fastcall *)(int (__fastcall ***)(__int64, GUID *, struct IMtfPropertyBag **)))(*v17)[2])(v17);
  try
  {
    LOBYTE(v17) = *v10;
    ipx::mtf::CMtfSuggestionClient::EstablishServerConnectionInternal(v17, v6);
  }
  catch ( ... )
  {
    LODWORD(v44) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x928,
                     (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                     v18);
    if ( v45 )
      (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
    return (unsigned int)v44;
  }
  if ( *v2 || (v19 = *((_DWORD *)this + 50), v19 == GetCurrentThreadId()) || !v45 )
  {
    v22 = (char *)this + 48;
    v27 = (**v6)[3]((__int64)*v6, *((GUID **)this + 17), (struct IMtfPropertyBag **)this + 6);
    v24 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x93E,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v27,
        v41);
      if ( v45 )
        (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
      return v24;
    }
  }
  else
  {
    v44 = 0;
    v20 = *v6;
    v21 = **v6;
    v44 = 0;
    if ( (*v21)((__int64)v20, &GUID_c44e8e9c_08ec_4acd_b1cd_f5430416fb32, &v44) < 0 )
    {
      v38 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::FailFast_Hr(retaddr, v39, v40, (const char *)v38, v41);
    }
    v22 = (char *)this + 48;
    v23 = (*(__int64 (__fastcall **)(struct IMtfPropertyBag *, char *, _QWORD *))(*(_QWORD *)v44 + 32LL))(
            v44,
            (char *)this + 48,
            v45);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x935,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
        (const char *)(unsigned int)v23,
        v41);
      if ( v44 )
        (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v44 + 16LL))(v44);
      if ( v45 )
        (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
      return v24;
    }
    if ( v44 )
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v44 + 16LL))(v44);
  }
  if ( *((_BYTE *)this + 144) )
  {
LABEL_65:
    if ( v45 )
      (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
    return 0;
  }
  *((_BYTE *)this + 147) = 1;
  v46 = this;
  v44 = 0;
  v25 = ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(
          this,
          1u,
          0,
          0,
          0,
          0,
          *((struct IMtfSuggestionContextProperty **)this + 19),
          0,
          &v44);
  v24 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94F,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v25,
      v42);
    v26 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v26 + 16LL))(v26);
    }
    *((_BYTE *)this + 147) = 0;
    if ( v45 )
      (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
    return v24;
  }
  v28 = ((__int64 (__fastcall *)(int (__fastcall ***)(__int64, GUID *, struct IMtfPropertyBag **), char *, _QWORD, struct IMtfPropertyBag *))(**v6)[5])(
          *v6,
          v22,
          *((unsigned __int16 *)this + 102),
          v44);
  v24 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x951,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
      (const char *)(unsigned int)v28,
      v42);
    v29 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    *((_BYTE *)this + 147) = 0;
    if ( v45 )
      (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
    return v24;
  }
  v30 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(struct IMtfPropertyBag *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = *((_QWORD *)this + 24);
  v32 = 0;
  if ( !v31 )
  {
LABEL_64:
    *((_BYTE *)this + 147) = 0;
    goto LABEL_65;
  }
  while ( 1 )
  {
    v33 = ipx::mtf::CMtfSuggestionClient::_ApplyDataSourceState(this, v32, 1);
    v34 = v33;
    if ( v33 < 0 )
      break;
    v35 = std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::operator[]((char *)this + 160, v32);
    if ( *(_QWORD *)(*(_QWORD *)v35 + 16LL) )
    {
      if ( *(_DWORD *)(*(_QWORD *)v35 + 24LL) )
      {
        v36 = ipx::mtf::CMtfSuggestionClient::_ApplyDataSourceCustomData(this, v32);
        v34 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x963,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
            (const char *)(unsigned int)v36,
            v42);
          *((_BYTE *)this + 147) = 0;
          if ( v45 )
            (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
          return v34;
        }
      }
    }
    if ( !*(_BYTE *)(*(_QWORD *)std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::operator[](
                                  (char *)this + 160,
                                  v32)
                   + 32LL) )
    {
      v37 = ipx::mtf::CMtfSuggestionClient::_ApplyDataSourceState(this, v32, 0);
      v34 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x968,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
          (const char *)(unsigned int)v37,
          v42);
        *((_BYTE *)this + 147) = 0;
        if ( v45 )
          (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
        return v34;
      }
    }
    if ( ++v32 >= v31 )
      goto LABEL_64;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x959,
    (unsigned int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
    (const char *)(unsigned int)v33,
    v42);
  *((_BYTE *)this + 147) = 0;
  if ( v45 )
    (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
  return v34;
}

```

## disassembly

```asm
0x180019b00  mov     [rsp+arg_18], rbx
0x180019b05  push    rsi
0x180019b06  push    rdi
0x180019b07  push    r12
0x180019b09  push    r14
0x180019b0b  push    r15
0x180019b0d  sub     rsp, 50h
0x180019b11  mov     rsi, rcx
0x180019b14  lea     rbx, [rcx+91h]
0x180019b1b  movzx   ecx, byte ptr [rbx]
0x180019b1e  xor     edi, edi
0x180019b20  test    ecx, ecx
0x180019b22  jz      short loc_180019B49
0x180019b24  sub     ecx, 1
0x180019b27  jz      short loc_180019B40
0x180019b29  cmp     ecx, 1
0x180019b2c  jz      short loc_180019B37
0x180019b2e  lea     rax, aUnknown; "Unknown"
0x180019b35  jmp     short loc_180019B50
0x180019b37  lea     rax, aInproc; "InProc"
0x180019b3e  jmp     short loc_180019B50
0x180019b40  lea     rax, aDcom; "DCOM"
0x180019b47  jmp     short loc_180019B50
0x180019b49  lea     rax, aCoreui; "CoreUI"
0x180019b50  mov     [rsp+78h+arg_0], rax
0x180019b58  lea     rcx, [rsp+78h+arg_0]
0x180019b60  call    ??$RepairMtfConnection@PEBD@MtfPlatformTelemetry@@SAX$$QEAPEBD@Z; MtfPlatformTelemetry::RepairMtfConnection<char const *>(char const * &&)
0x180019b65  mov     [rsp+78h+arg_8], rdi
0x180019b6d  cmp     [rbx], dil
0x180019b70  jnz     loc_180019C90
0x180019b76  mov     [rsp+78h+arg_0], rdi
0x180019b7e  lea     r14, [rsi+70h]
0x180019b82  mov     rcx, [r14]
0x180019b85  mov     rax, [rcx]
0x180019b88  mov     [rsp+78h+arg_0], rdi
0x180019b90  lea     r8, [rsp+78h+arg_0]
0x180019b98  lea     rdx, _GUID_c44e8e9c_08ec_4acd_b1cd_f5430416fb32
0x180019b9f  mov     rax, [rax]
0x180019ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ba7  mov     rcx, [rsp+78h]; this
0x180019bac  test    eax, eax
0x180019bae  jns     short loc_180019BEB
0x180019bb0  mov     r9d, eax; char *
0x180019bb3  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180019bba  mov     edx, 917h; void *
0x180019bbf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019bc4  nop
0x180019bc5  mov     rcx, [rsp+78h+arg_0]
0x180019bcd  test    rcx, rcx
0x180019bd0  jz      short loc_180019BDF
0x180019bd2  mov     rax, [rcx]
0x180019bd5  mov     rax, [rax+10h]
0x180019bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bde  nop
0x180019bdf  lea     r15, [rsi+91h]
0x180019be6  jmp     loc_180019C97
0x180019beb  mov     r15, [rsp+78h+arg_0]
0x180019bf3  mov     rax, [r15]
0x180019bf6  mov     r12, [rax+18h]
0x180019bfa  mov     rcx, [rsp+78h+arg_8]
0x180019c02  mov     [rsp+78h+arg_8], rdi
0x180019c0a  test    rcx, rcx
0x180019c0d  jz      short loc_180019C1C
0x180019c0f  mov     rdx, [rcx]
0x180019c12  mov     rax, [rdx+10h]
0x180019c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c1b  nop
0x180019c1c  lea     rdx, [rsi+30h]
0x180019c20  lea     r8, [rsp+78h+arg_8]
0x180019c28  mov     rcx, r15
0x180019c2b  mov     rax, r12
0x180019c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c33  mov     r15d, eax
0x180019c36  test    eax, eax
0x180019c38  jns     short loc_180019BC5
0x180019c3a  mov     rcx, [rsp+78h]; this
0x180019c3f  mov     r9d, eax; char *
0x180019c42  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180019c49  mov     edx, 919h; void *
0x180019c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c53  nop
0x180019c54  mov     rcx, [rsp+78h+arg_0]
0x180019c5c  test    rcx, rcx
0x180019c5f  jz      short loc_180019C6E
0x180019c61  mov     rax, [rcx]
0x180019c64  mov     rax, [rax+10h]
0x180019c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c6d  nop
0x180019c6e  mov     rcx, [rsp+78h+arg_8]
0x180019c76  test    rcx, rcx
0x180019c79  jz      short loc_180019C88
0x180019c7b  mov     rax, [rcx]
0x180019c7e  mov     rax, [rax+10h]
0x180019c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c87  nop
0x180019c88  mov     eax, r15d
0x180019c8b  jmp     loc_18001A116
0x180019c90  lea     r14, [rsi+70h]
0x180019c94  mov     r15, rbx
0x180019c97  mov     rcx, [r14]
0x180019c9a  mov     [r14], rdi
0x180019c9d  test    rcx, rcx
0x180019ca0  jz      short loc_180019CAF
0x180019ca2  mov     rax, [rcx]
0x180019ca5  mov     rax, [rax+10h]
0x180019ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cae  nop
0x180019caf  mov     rdx, r14
0x180019cb2  mov     cl, [r15]
0x180019cb5  call    ?EstablishServerConnectionInternal@CMtfSuggestionClient@mtf@ipx@@KAXW4MTFServerConnection@23@PEAPEAUIMtfTransportServer@@@Z; ipx::mtf::CMtfSuggestionClient::EstablishServerConnectionInternal(ipx::mtf::MTFServerConnection,IMtfTransportServer * *)
0x180019cba  nop
0x180019cbb  cmp     [rbx], dil
0x180019cbe  jnz     loc_180019E7C
0x180019cc4  mov     ebx, [rsi+0C8h]
0x180019cca  call    cs:__imp_GetCurrentThreadId
0x180019cd0  cmp     ebx, eax
0x180019cd2  jz      loc_180019E7C
0x180019cd8  cmp     [rsp+78h+arg_8], rdi
0x180019ce0  jz      loc_180019E7C
0x180019ce6  mov     [rsp+78h+arg_0], rdi
0x180019cee  mov     rcx, [r14]
0x180019cf1  mov     rax, [rcx]
0x180019cf4  mov     [rsp+78h+arg_0], rdi
0x180019cfc  lea     r8, [rsp+78h+arg_0]
0x180019d04  lea     rdx, _GUID_c44e8e9c_08ec_4acd_b1cd_f5430416fb32
0x180019d0b  mov     rax, [rax]
0x180019d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d13  test    eax, eax
0x180019d15  js      loc_18001A12B
0x180019d1b  mov     rcx, [rsp+78h+arg_0]
0x180019d23  lea     r15, [rsi+30h]
0x180019d27  mov     rax, [rcx]
0x180019d2a  mov     r8, [rsp+78h+arg_8]
0x180019d32  mov     rdx, r15
0x180019d35  mov     rax, [rax+20h]
0x180019d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d3e  mov     ebx, eax
0x180019d40  test    eax, eax
0x180019d42  jns     short loc_180019D99
0x180019d44  mov     rcx, [rsp+78h]; this
0x180019d49  mov     r9d, eax; char *
0x180019d4c  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180019d53  mov     edx, 935h; void *
0x180019d58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019d5d  nop
0x180019d5e  mov     rcx, [rsp+78h+arg_0]
0x180019d66  test    rcx, rcx
0x180019d69  jz      short loc_180019D78
0x180019d6b  mov     rax, [rcx]
0x180019d6e  mov     rax, [rax+10h]
0x180019d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d77  nop
0x180019d78  mov     rcx, [rsp+78h+arg_8]
0x180019d80  test    rcx, rcx
0x180019d83  jz      short loc_180019D92
0x180019d85  mov     rax, [rcx]
0x180019d88  mov     rax, [rax+10h]
0x180019d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d91  nop
0x180019d92  mov     eax, ebx
0x180019d94  jmp     loc_18001A116
0x180019d99  mov     rcx, [rsp+78h+arg_0]
0x180019da1  test    rcx, rcx
0x180019da4  jz      short loc_180019DB3
0x180019da6  mov     rax, [rcx]
0x180019da9  mov     rax, [rax+10h]
0x180019dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019db2  nop
0x180019db3  cmp     [rsi+90h], dil
0x180019dba  jnz     loc_18001A01A
0x180019dc0  mov     byte ptr [rsi+93h], 1
0x180019dc7  mov     [rsp+78h+arg_10], rsi
0x180019dcf  mov     [rsp+78h+arg_0], rdi
0x180019dd7  lea     rax, [rsp+78h+arg_0]
0x180019ddf  mov     [rsp+78h+var_38], rax; struct IMtfPropertyBag **
0x180019de4  mov     [rsp+78h+var_40], rdi; struct IMtfSuggestionInputQuery *
0x180019de9  mov     rax, [rsi+98h]
0x180019df0  mov     [rsp+78h+var_48], rax; struct IMtfSuggestionContextProperty *
0x180019df5  mov     [rsp+78h+var_50], rdi; struct IMtfSuggestionCandidatePrimitive *
0x180019dfa  mov     [rsp+78h+var_58], edi; int
0x180019dfe  xor     r9d, r9d; unsigned __int8 *
0x180019e01  xor     r8d, r8d; struct MTFCORE_SIMPLEPARAM *
0x180019e04  lea     edx, [r9+1]; unsigned int
0x180019e08  mov     rcx, rsi; this
0x180019e0b  call    ?_CreateRequestBag@CMtfSuggestionClient@mtf@ipx@@IEAAJKPEBUMTFCORE_SIMPLEPARAM@@PEBEKPEAUIMtfSuggestionCandidatePrimitive@@PEAUIMtfSuggestionContextProperty@@PEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfPropertyBag@@@Z; ipx::mtf::CMtfSuggestionClient::_CreateRequestBag(ulong,MTFCORE_SIMPLEPARAM const *,uchar const *,ulong,IMtfSuggestionCandidatePrimitive *,IMtfSuggestionContextProperty *,IMtfSuggestionInputQuery *,IMtfPropertyBag * *)
0x180019e10  mov     ebx, eax
0x180019e12  test    eax, eax
0x180019e14  jns     loc_180019EDC
0x180019e1a  mov     rcx, [rsp+78h]; this
0x180019e1f  mov     r9d, eax; char *
0x180019e22  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180019e29  mov     edx, 94Fh; void *
0x180019e2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019e33  nop
0x180019e34  mov     rcx, [rsp+78h+arg_0]
0x180019e3c  test    rcx, rcx
0x180019e3f  jz      short loc_180019E56
0x180019e41  mov     [rsp+78h+arg_0], rdi
0x180019e49  mov     rax, [rcx]
0x180019e4c  mov     rax, [rax+10h]
0x180019e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e55  nop
0x180019e56  mov     [rsi+93h], dil
0x180019e5d  mov     rcx, [rsp+78h+arg_8]
0x180019e65  test    rcx, rcx
0x180019e68  jz      short loc_180019E77
0x180019e6a  mov     rax, [rcx]
0x180019e6d  mov     rax, [rax+10h]
0x180019e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e76  nop
0x180019e77  jmp     loc_180019D92
0x180019e7c  mov     rcx, [r14]
0x180019e7f  lea     r15, [rsi+30h]
0x180019e83  mov     rax, [rcx]
0x180019e86  mov     r8, r15
0x180019e89  mov     rdx, [rsi+88h]
0x180019e90  mov     rax, [rax+18h]
0x180019e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e99  mov     ebx, eax
0x180019e9b  test    eax, eax
0x180019e9d  jns     loc_180019DB3
0x180019ea3  mov     rcx, [rsp+78h]; this
0x180019ea8  mov     r9d, eax; char *
0x180019eab  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180019eb2  mov     edx, 93Eh; void *
0x180019eb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ebc  nop
0x180019ebd  mov     rcx, [rsp+78h+arg_8]
0x180019ec5  test    rcx, rcx
0x180019ec8  jz      short loc_180019ED7
0x180019eca  mov     rax, [rcx]
0x180019ecd  mov     rax, [rax+10h]
0x180019ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ed6  nop
0x180019ed7  jmp     loc_180019D92
0x180019edc  mov     rcx, [r14]
0x180019edf  mov     rax, [rcx]
0x180019ee2  movzx   r8d, word ptr [rsi+0CCh]
0x180019eea  mov     r9, [rsp+78h+arg_0]
0x180019ef2  mov     rdx, r15
0x180019ef5  mov     rax, [rax+28h]
0x180019ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019efe  mov     ebx, eax
0x180019f00  test    eax, eax
0x180019f02  jns     short loc_180019F66
0x180019f04  mov     rcx, [rsp+78h]; this
0x180019f09  mov     r9d, eax; char *
0x180019f0c  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x180019f13  mov     edx, 951h; void *
0x180019f18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f1d  nop
0x180019f1e  mov     rcx, [rsp+78h+arg_0]
0x180019f26  test    rcx, rcx
0x180019f29  jz      short loc_180019F40
0x180019f2b  mov     [rsp+78h+arg_0], rdi
0x180019f33  mov     rax, [rcx]
0x180019f36  mov     rax, [rax+10h]
0x180019f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f3f  nop
0x180019f40  mov     [rsi+93h], dil
0x180019f47  mov     rcx, [rsp+78h+arg_8]
0x180019f4f  test    rcx, rcx
0x180019f52  jz      short loc_180019F61
0x180019f54  mov     rax, [rcx]
0x180019f57  mov     rax, [rax+10h]
0x180019f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f60  nop
0x180019f61  jmp     loc_180019D92
0x180019f66  mov     rcx, [rsp+78h+arg_0]
0x180019f6e  test    rcx, rcx
0x180019f71  jz      short loc_180019F88
0x180019f73  mov     [rsp+78h+arg_0], rdi
0x180019f7b  mov     rax, [rcx]
0x180019f7e  mov     rax, [rax+10h]
0x180019f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f87  nop
0x180019f88  mov     r15, [rsi+0C0h]
0x180019f8f  mov     rbx, rdi
0x180019f92  test    r15, r15
0x180019f95  jz      short loc_18001A013
0x180019f97  mov     r8b, 1; bool
0x180019f9a  movzx   edx, bx; unsigned __int16
0x180019f9d  mov     rcx, rsi; this
0x180019fa0  call    ?_ApplyDataSourceState@CMtfSuggestionClient@mtf@ipx@@IEAAJG_N@Z; ipx::mtf::CMtfSuggestionClient::_ApplyDataSourceState(ushort,bool)
0x180019fa5  mov     r14d, eax
0x180019fa8  test    eax, eax
0x180019faa  js      loc_18001A0B5
0x180019fb0  lea     r12, [rsi+0A0h]
0x180019fb7  mov     rdx, rbx
0x180019fba  mov     rcx, r12
0x180019fbd  call    ??A?$deque@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@V?$allocator@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@1@_K@Z; std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::operator[](unsigned __int64)
0x180019fc2  mov     rdx, [rax]
0x180019fc5  cmp     [rdx+10h], rdi
0x180019fc9  jz      short loc_180019FE2
0x180019fcb  cmp     [rdx+18h], edi
0x180019fce  jbe     short loc_180019FE2
0x180019fd0  movzx   edx, bx; unsigned __int16
0x180019fd3  mov     rcx, rsi; this
0x180019fd6  call    ?_ApplyDataSourceCustomData@CMtfSuggestionClient@mtf@ipx@@IEAAJG@Z; ipx::mtf::CMtfSuggestionClient::_ApplyDataSourceCustomData(ushort)
0x180019fdb  mov     r14d, eax
  ... truncated ...
```
