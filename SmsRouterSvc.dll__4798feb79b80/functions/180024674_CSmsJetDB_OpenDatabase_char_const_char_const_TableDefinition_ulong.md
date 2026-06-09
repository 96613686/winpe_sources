# CSmsJetDB::OpenDatabase(char const *,char const *,TableDefinition *,ulong)

- ea: `0x180024674`
- end: `0x180024d9d`
- name: `?OpenDatabase@CSmsJetDB@@QEAAJPEBD0PEAUTableDefinition@@K@Z`
- size: `1833`
- prototype: `__int64 __fastcall(CSmsJetDB *__hidden this, JET_PCSTR szParam, const char *, struct TableDefinition *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d80c`

## callees

- `0x180003a60`
- `0x18001446c`
- `0x1800183c8`
- `0x18001b820`
- `0x180021d40`
- `0x180022768`
- `0x180024674`
- `0x180024da4`
- `0x180025b04`
- `0x18006f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800248a6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024958`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024a5c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024aee`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024b74`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024c22`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024c84`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024cfb`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024d46`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800248a6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024958`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024a5c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024aee`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024b74`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024c22`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024c84`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024cfb`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180024d46`
- `ESENT!JetCreateInstanceA` at `0x1800246d9`
- `ESENT!JetCreateInstanceA` at `0x1800246d9`
- `ESENT!JetCreateDatabaseA` at `0x180024914`
- `ESENT!JetCreateDatabaseA` at `0x180024914`
- `ESENT!JetAttachDatabaseA` at `0x1800248eb`
- `ESENT!JetAttachDatabaseA` at `0x180024b30`
- `ESENT!JetAttachDatabaseA` at `0x1800248eb`
- `ESENT!JetAttachDatabaseA` at `0x180024b30`
- `ESENT!JetBeginSessionA` at `0x180024862`
- `ESENT!JetBeginSessionA` at `0x180024862`
- `ESENT!JetOpenDatabaseA` at `0x180024bc4`
- `ESENT!JetOpenDatabaseA` at `0x180024bc4`
- `ESENT!JetInit` at `0x180024818`
- `ESENT!JetInit` at `0x180024818`
- `ESENT!JetSetSystemParameterA` at `0x18002472e`
- `ESENT!JetSetSystemParameterA` at `0x18002474b`
- `ESENT!JetSetSystemParameterA` at `0x18002476c`
- `ESENT!JetSetSystemParameterA` at `0x18002478e`
- `ESENT!JetSetSystemParameterA` at `0x1800247b6`
- `ESENT!JetSetSystemParameterA` at `0x1800247df`
- `ESENT!JetSetSystemParameterA` at `0x180024805`
- `ESENT!JetSetSystemParameterA` at `0x180024a18`
- `ESENT!JetSetSystemParameterA` at `0x180024aaa`
- `ESENT!JetSetSystemParameterA` at `0x18002472e`
- `ESENT!JetSetSystemParameterA` at `0x18002474b`
- `ESENT!JetSetSystemParameterA` at `0x18002476c`
- `ESENT!JetSetSystemParameterA` at `0x18002478e`
- `ESENT!JetSetSystemParameterA` at `0x1800247b6`
- `ESENT!JetSetSystemParameterA` at `0x1800247df`
- `ESENT!JetSetSystemParameterA` at `0x180024805`
- `ESENT!JetSetSystemParameterA` at `0x180024a18`
- `ESENT!JetSetSystemParameterA` at `0x180024aaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSmsJetDB::OpenDatabase(
        CSmsJetDB *this,
        JET_PCSTR szParam,
        const char *a3,
        struct TableDefinition *a4)
{
  JET_ERR InstanceA; // eax
  JET_ERR v8; // ecx
  unsigned int v9; // ebx
  int v10; // eax
  JET_SESID *v11; // rsi
  JET_ERR v12; // eax
  JET_ERR v13; // ecx
  int v14; // eax
  _BYTE *v15; // rdx
  JET_ERR v16; // eax
  unsigned int v17; // edi
  JET_ERR DatabaseA; // eax
  JET_ERR v19; // ecx
  int v20; // eax
  _BYTE *v21; // rdx
  unsigned int v22; // ebx
  unsigned __int64 v23; // rsi
  const struct TableDefinition *v24; // r15
  int v25; // r12d
  JET_ERR v26; // eax
  JET_ERR v27; // ecx
  int v28; // eax
  _BYTE *v29; // rdx
  JET_ERR v30; // eax
  JET_ERR v31; // ecx
  int v32; // eax
  _BYTE *v33; // rdx
  JET_ERR v34; // eax
  JET_ERR v35; // ecx
  int v36; // eax
  _BYTE *v37; // rdx
  JET_ERR v38; // eax
  JET_ERR v39; // ecx
  int v40; // eax
  _BYTE *v41; // rdx
  int v42; // eax
  _BYTE *v43; // rdx
  _BYTE *v44; // rdx
  _BYTE *v45; // rdx
  __int64 v46[9]; // [rsp+38h] [rbp-C8h] BYREF
  void **v47; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v48[56]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE *v49; // [rsp+C0h] [rbp-40h]
  char szFilename[272]; // [rsp+D0h] [rbp-30h] BYREF

  if ( (int)StringCchPrintfA(szFilename, 0x104u, "%s\\%s", szParam, a3) < 0 )
    return 2147942414LL;
  InstanceA = JetCreateInstanceA((JET_INSTANCE *)this + 7, 0);
  v8 = InstanceA;
  if ( InstanceA < 0 )
    goto LABEL_4;
  InstanceA = JetSetSystemParameterA((JET_INSTANCE *)this + 7, 0xFFFFFFFFFFFFFFFFuLL, 0x81u, 0xD4u, 0);
  v8 = InstanceA;
  if ( InstanceA < 0 )
    goto LABEL_4;
  InstanceA = JetSetSystemParameterA((JET_INSTANCE *)this + 7, 0xFFFFFFFFFFFFFFFFuLL, 0, 0, szParam);
  v8 = InstanceA;
  if ( InstanceA < 0 )
    goto LABEL_4;
  InstanceA = JetSetSystemParameterA((JET_INSTANCE *)this + 7, 0xFFFFFFFFFFFFFFFFuLL, 1u, 0, szParam);
  v8 = InstanceA;
  if ( InstanceA < 0 )
    goto LABEL_4;
  InstanceA = JetSetSystemParameterA((JET_INSTANCE *)this + 7, 0xFFFFFFFFFFFFFFFFuLL, 2u, 0, szParam);
  v8 = InstanceA;
  if ( InstanceA < 0 )
    goto LABEL_4;
  InstanceA = JetSetSystemParameterA((JET_INSTANCE *)this + 7, 0xFFFFFFFFFFFFFFFFuLL, 0x9Cu, 1u, 0);
  v8 = InstanceA;
  if ( InstanceA < 0
    || (InstanceA = JetSetSystemParameterA((JET_INSTANCE *)this + 7, 0xFFFFFFFFFFFFFFFFuLL, 0x2Du, 1u, 0),
        v8 = InstanceA,
        InstanceA < 0)
    || (InstanceA = JetSetSystemParameterA((JET_INSTANCE *)this + 7, 0xFFFFFFFFFFFFFFFFuLL, 0x36u, 1u, 0),
        v8 = InstanceA,
        InstanceA < 0)
    || (InstanceA = JetInit((JET_INSTANCE *)this + 7), v8 = InstanceA, InstanceA < 0) )
  {
LABEL_4:
    if ( v8 == -1011 )
    {
      return (unsigned int)-2147024882;
    }
    else
    {
      v10 = -InstanceA;
      if ( v10 < 0 )
        LOWORD(v10) = v8;
      return v8 & 0x8E5E0000 | (unsigned __int16)v10 | 0xE5E0000;
    }
  }
  v46[0] = (__int64)off_1800703C8;
  v46[1] = (__int64)this;
  v46[7] = (__int64)v46;
  Windows::Sms::Common::undo_action::undo_action(&v47, v46);
  v11 = (JET_SESID *)((char *)this + 48);
  v12 = JetBeginSessionA(*((_QWORD *)this + 7), (JET_SESID *)this + 6, 0, 0);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( v12 == -1011 )
    {
      v9 = -2147024882;
    }
    else
    {
      v14 = -v12;
      if ( v14 < 0 )
        LOWORD(v14) = v13;
      v9 = v13 & 0x8E5E0000 | (unsigned __int16)v14 | 0xE5E0000;
    }
    v47 = &Windows::Sms::Common::undo_action::`vftable';
    if ( !v49 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v49 + 16LL))(v49);
    if ( v49 )
    {
      v15 = v48;
      LOBYTE(v15) = v49 != v48;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v15);
    }
    return v9;
  }
  v16 = JetAttachDatabaseA(*v11, szFilename, 0x10u);
  v17 = v16;
  if ( v16 == -1811 )
  {
    DatabaseA = JetCreateDatabaseA(*v11, szFilename, 0, (JET_DBID *)this + 16, 0);
    v19 = DatabaseA;
    if ( DatabaseA < 0 )
    {
      if ( DatabaseA == -1011 )
      {
        v9 = -2147024882;
      }
      else
      {
        v20 = -DatabaseA;
        if ( v20 < 0 )
          LOWORD(v20) = v19;
        v9 = v19 & 0x8E5E0000 | (unsigned __int16)v20 | 0xE5E0000;
      }
      v47 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v49 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v49 + 16LL))(v49);
      if ( v49 )
      {
        v21 = v48;
        LOBYTE(v21) = v49 != v48;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v21);
      }
      return v9;
    }
    v17 = 0;
  }
  else
  {
    if ( v16 == -1413 )
    {
      v26 = JetSetSystemParameterA((JET_INSTANCE *)this + 7, 0xFFFFFFFFFFFFFFFFuLL, 0x2Du, 0, 0);
      v27 = v26;
      if ( v26 < 0 )
      {
        if ( v26 == -1011 )
        {
          v9 = -2147024882;
        }
        else
        {
          v28 = -v26;
          if ( v28 < 0 )
            LOWORD(v28) = v27;
          v9 = v27 & 0x8E5E0000 | (unsigned __int16)v28 | 0xE5E0000;
        }
        v47 = &Windows::Sms::Common::undo_action::`vftable';
        if ( !v49 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v49 + 16LL))(v49);
        if ( v49 )
        {
          v29 = v48;
          LOBYTE(v29) = v49 != v48;
          (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v29);
        }
        return v9;
      }
      v30 = JetSetSystemParameterA((JET_INSTANCE *)this + 7, 0xFFFFFFFFFFFFFFFFuLL, 0x36u, 0, 0);
      v31 = v30;
      if ( v30 < 0 )
      {
        if ( v30 == -1011 )
        {
          v9 = -2147024882;
        }
        else
        {
          v32 = -v30;
          if ( v32 < 0 )
            LOWORD(v32) = v31;
          v9 = v31 & 0x8E5E0000 | (unsigned __int16)v32 | 0xE5E0000;
        }
        v47 = &Windows::Sms::Common::undo_action::`vftable';
        if ( !v49 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v49 + 16LL))(v49);
        if ( v49 )
        {
          v33 = v48;
          LOBYTE(v33) = v49 != v48;
          (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v33);
        }
        return v9;
      }
      v34 = JetAttachDatabaseA(*v11, szFilename, 0);
      v35 = v34;
      if ( v34 < 0 )
      {
        if ( v34 == -1011 )
        {
          v9 = -2147024882;
        }
        else
        {
          v36 = -v34;
          if ( v36 < 0 )
            LOWORD(v36) = v35;
          v9 = v35 & 0x8E5E0000 | (unsigned __int16)v36 | 0xE5E0000;
        }
        v47 = &Windows::Sms::Common::undo_action::`vftable';
        if ( !v49 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v49 + 16LL))(v49);
        if ( v49 )
        {
          v37 = v48;
          LOBYTE(v37) = v49 != v48;
          (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v37);
        }
        return v9;
      }
      v17 = 0;
    }
    else if ( v16 < 0 )
    {
      if ( v16 == -1011 )
      {
        v9 = -2147024882;
      }
      else
      {
        v40 = -v16;
        if ( v40 < 0 )
          LOWORD(v40) = v17;
        v9 = v17 & 0x8E5E0000 | (unsigned __int16)v40 | 0xE5E0000;
      }
      v47 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v49 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v49 + 16LL))(v49);
      if ( v49 )
      {
        v41 = v48;
        LOBYTE(v41) = v49 != v48;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v41);
      }
      return v9;
    }
    v38 = JetOpenDatabaseA(*v11, szFilename, 0, (JET_DBID *)this + 16, 0);
    v39 = v38;
    if ( v38 < 0 )
    {
      if ( v38 == -1011 )
      {
        v9 = -2147024882;
      }
      else
      {
        v42 = -v38;
        if ( v42 < 0 )
          LOWORD(v42) = v39;
        v9 = v39 & 0x8E5E0000 | (unsigned __int16)v42 | 0xE5E0000;
      }
      v47 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v49 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v49 + 16LL))(v49);
      if ( v49 )
      {
        v43 = v48;
        LOBYTE(v43) = v49 != v48;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v43);
      }
      return v9;
    }
  }
  v22 = 0;
  while ( 1 )
  {
    v23 = (unsigned __int64)v22 << 7;
    v24 = (const struct TableDefinition *)((char *)qword_18008D760 + v23);
    v25 = CSmsJetDB::PrepareTable(this, (struct TableDefinition *)((char *)qword_18008D760 + v23));
    if ( v25 < 0 )
      break;
    *(_DWORD *)std::map<std::string,unsigned long>::operator[]((char *)this + 32, (char *)&qword_18008D760[1] + v23) = v22;
    if ( *((_QWORD *)this + 2) == *((_QWORD *)this + 3) )
    {
      std::vector<TableDefinition>::_Emplace_reallocate<TableDefinition const &>(
        (char *)this + 8,
        *((_QWORD *)this + 2),
        v24);
    }
    else
    {
      TableDefinition::TableDefinition(*((TableDefinition **)this + 2), v24);
      *((_QWORD *)this + 2) += 128LL;
    }
    if ( ++v22 >= 3 )
    {
      Windows::Sms::Common::undo_action::release((Windows::Sms::Common::undo_action *)&v47);
      v47 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v49 )
      {
        std::_Xbad_function_call();
        __debugbreak();
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v49 + 16LL))(v49);
      if ( v49 )
      {
        v44 = v48;
        LOBYTE(v44) = v49 != v48;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v44);
      }
      return v17;
    }
  }
  v47 = &Windows::Sms::Common::undo_action::`vftable';
  if ( !v49 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v49 + 16LL))(v49);
  if ( v49 )
  {
    v45 = v48;
    LOBYTE(v45) = v49 != v48;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v49 + 32LL))(v49, v45);
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x180024674  push    rbp
0x180024676  push    rbx
0x180024677  push    rsi
0x180024678  push    rdi
0x180024679  push    r12
0x18002467b  push    r14
0x18002467d  push    r15
0x18002467f  lea     rbp, [rsp-0F0h]
0x180024687  sub     rsp, 1F0h
0x18002468e  mov     rax, cs:__security_cookie
0x180024695  xor     rax, rsp
0x180024698  mov     [rbp+120h+var_40], rax
0x18002469f  mov     rdi, rdx
0x1800246a2  mov     r14, rcx
0x1800246a5  mov     [rsp+220h+szParam], r8
0x1800246aa  mov     r9, rdx
0x1800246ad  lea     r8, aSS; "%s\\%s"
0x1800246b4  mov     edx, 104h; unsigned __int64
0x1800246b9  lea     rcx, [rbp+120h+szFilename]; char *
0x1800246bd  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800246c2  test    eax, eax
0x1800246c4  jns     short loc_1800246D0
0x1800246c6  mov     eax, 8007000Eh
0x1800246cb  jmp     loc_180024D7C
0x1800246d0  lea     rbx, [r14+38h]
0x1800246d4  xor     edx, edx; szInstanceName
0x1800246d6  mov     rcx, rbx; pinstance
0x1800246d9  call    cs:__imp_JetCreateInstanceA
0x1800246df  mov     ecx, eax
0x1800246e1  test    eax, eax
0x1800246e3  jns     short loc_180024711
0x1800246e5  cmp     ecx, 0FFFFFC0Dh
0x1800246eb  jnz     short loc_1800246F4
0x1800246ed  mov     ebx, 8007000Eh
0x1800246f2  jmp     short loc_18002470A
0x1800246f4  neg     eax
0x1800246f6  cmovs   eax, ecx
0x1800246f9  movzx   ebx, ax
0x1800246fc  and     ecx, 8E5E0000h
0x180024702  or      ebx, ecx
0x180024704  or      ebx, 0E5E0000h
0x18002470a  mov     eax, ebx
0x18002470c  jmp     loc_180024D7C
0x180024711  mov     [rsp+220h+szParam], 0; szParam
0x18002471a  mov     r9d, 0D4h; lParam
0x180024720  lea     r8d, [r9-53h]; paramid
0x180024724  or      r15, 0FFFFFFFFFFFFFFFFh
0x180024728  mov     rdx, r15; sesid
0x18002472b  mov     rcx, rbx; pinstance
0x18002472e  call    cs:__imp_JetSetSystemParameterA
0x180024734  mov     ecx, eax
0x180024736  test    eax, eax
0x180024738  js      short loc_1800246E5
0x18002473a  mov     [rsp+220h+szParam], rdi; szParam
0x18002473f  xor     r9d, r9d; lParam
0x180024742  xor     r8d, r8d; paramid
0x180024745  mov     rdx, r15; sesid
0x180024748  mov     rcx, rbx; pinstance
0x18002474b  call    cs:__imp_JetSetSystemParameterA
0x180024751  mov     ecx, eax
0x180024753  test    eax, eax
0x180024755  js      short loc_1800246E5
0x180024757  mov     [rsp+220h+szParam], rdi; szParam
0x18002475c  xor     r9d, r9d; lParam
0x18002475f  lea     esi, [r15+2]
0x180024763  mov     r8d, esi; paramid
0x180024766  mov     rdx, r15; sesid
0x180024769  mov     rcx, rbx; pinstance
0x18002476c  call    cs:__imp_JetSetSystemParameterA
0x180024772  mov     ecx, eax
0x180024774  test    eax, eax
0x180024776  js      loc_1800246E5
0x18002477c  mov     [rsp+220h+szParam], rdi; szParam
0x180024781  xor     r9d, r9d; lParam
0x180024784  lea     r8d, [r15+3]; paramid
0x180024788  mov     rdx, r15; sesid
0x18002478b  mov     rcx, rbx; pinstance
0x18002478e  call    cs:__imp_JetSetSystemParameterA
0x180024794  mov     ecx, eax
0x180024796  test    eax, eax
0x180024798  js      loc_1800246E5
0x18002479e  mov     [rsp+220h+szParam], 0; szParam
0x1800247a7  mov     r9d, esi; lParam
0x1800247aa  mov     r8d, 9Ch; paramid
0x1800247b0  mov     rdx, r15; sesid
0x1800247b3  mov     rcx, rbx; pinstance
0x1800247b6  call    cs:__imp_JetSetSystemParameterA
0x1800247bc  mov     ecx, eax
0x1800247be  test    eax, eax
0x1800247c0  js      loc_1800246E5
0x1800247c6  mov     [rsp+220h+szParam], 0; szParam
0x1800247cf  mov     r9d, esi; lParam
0x1800247d2  lea     r12d, [r15+2Eh]
0x1800247d6  mov     r8d, r12d; paramid
0x1800247d9  mov     rdx, r15; sesid
0x1800247dc  mov     rcx, rbx; pinstance
0x1800247df  call    cs:__imp_JetSetSystemParameterA
0x1800247e5  mov     ecx, eax
0x1800247e7  test    eax, eax
0x1800247e9  js      loc_1800246E5
0x1800247ef  mov     [rsp+220h+szParam], 0; szParam
0x1800247f8  mov     r9d, esi; lParam
0x1800247fb  lea     r8d, [r15+37h]; paramid
0x1800247ff  mov     rdx, r15; sesid
0x180024802  mov     rcx, rbx; pinstance
0x180024805  call    cs:__imp_JetSetSystemParameterA
0x18002480b  mov     ecx, eax
0x18002480d  test    eax, eax
0x18002480f  js      loc_1800246E5
0x180024815  mov     rcx, rbx; pinstance
0x180024818  call    cs:__imp_JetInit
0x18002481e  mov     ecx, eax
0x180024820  test    eax, eax
0x180024822  js      loc_1800246E5
0x180024828  lea     rax, off_1800703C8
0x18002482f  mov     [rsp+220h+var_1E8], rax
0x180024834  mov     [rsp+220h+var_1E0], r14
0x180024839  lea     rax, [rsp+220h+var_1E8]
0x18002483e  mov     [rsp+220h+var_1B0], rax
0x180024843  lea     rdx, [rsp+220h+var_1E8]
0x180024848  lea     rcx, [rbp+120h+var_1A0]
0x18002484c  call    ??0undo_action@Common@Sms@Windows@@QEAA@V?$function@$$A6AXXZ@std@@@Z; Windows::Sms::Common::undo_action::undo_action(std::function<void (void)>)
0x180024851  nop
0x180024852  lea     rsi, [r14+30h]
0x180024856  xor     r9d, r9d; szPassword
0x180024859  xor     r8d, r8d; szUserName
0x18002485c  mov     rdx, rsi; psesid
0x18002485f  mov     rcx, [rbx]; instance
0x180024862  call    cs:__imp_JetBeginSessionA
0x180024868  mov     ecx, eax
0x18002486a  test    eax, eax
0x18002486c  jns     short loc_1800248DE
0x18002486e  cmp     eax, 0FFFFFC0Dh
0x180024873  jnz     short loc_18002487C
0x180024875  mov     ebx, 8007000Eh
0x18002487a  jmp     short loc_180024892
0x18002487c  neg     eax
0x18002487e  cmovs   eax, ecx
0x180024881  movzx   ebx, ax
0x180024884  and     ecx, 8E5E0000h
0x18002488a  or      ebx, ecx
0x18002488c  or      ebx, 0E5E0000h
0x180024892  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180024899  mov     [rbp+120h+var_1A0], rax
0x18002489d  mov     rcx, [rbp+120h+var_160]
0x1800248a1  test    rcx, rcx
0x1800248a4  jnz     short loc_1800248AD
0x1800248a6  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800248ac  int     3; Trap to Debugger
0x1800248ad  mov     rax, [rcx]
0x1800248b0  mov     rax, [rax+10h]
0x1800248b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248b9  mov     rcx, [rbp+120h+var_160]
0x1800248bd  test    rcx, rcx
0x1800248c0  jz      short loc_1800248D9
0x1800248c2  mov     rax, [rcx]
0x1800248c5  lea     rdx, [rbp+120h+var_198]
0x1800248c9  cmp     rcx, rdx
0x1800248cc  setnz   dl
0x1800248cf  mov     rax, [rax+20h]
0x1800248d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248d8  nop
0x1800248d9  jmp     loc_18002470A
0x1800248de  mov     r8d, 10h; grbit
0x1800248e4  lea     rdx, [rbp+120h+szFilename]; szFilename
0x1800248e8  mov     rcx, [rsi]; sesid
0x1800248eb  call    cs:__imp_JetAttachDatabaseA
0x1800248f1  mov     edi, eax
0x1800248f3  cmp     eax, 0FFFFF8EDh
0x1800248f8  jnz     loc_1800249F7
0x1800248fe  lea     r9, [r14+40h]; pdbid
0x180024902  mov     dword ptr [rsp+220h+szParam], 0; grbit
0x18002490a  xor     r8d, r8d; szConnect
0x18002490d  lea     rdx, [rbp+120h+szFilename]; szFilename
0x180024911  mov     rcx, [rsi]; sesid
0x180024914  call    cs:__imp_JetCreateDatabaseA
0x18002491a  mov     ecx, eax
0x18002491c  test    eax, eax
0x18002491e  jns     short loc_180024990
0x180024920  cmp     eax, 0FFFFFC0Dh
0x180024925  jnz     short loc_18002492E
0x180024927  mov     ebx, 8007000Eh
0x18002492c  jmp     short loc_180024944
0x18002492e  neg     eax
0x180024930  cmovs   eax, ecx
0x180024933  movzx   ebx, ax
0x180024936  and     ecx, 8E5E0000h
0x18002493c  or      ebx, ecx
0x18002493e  or      ebx, 0E5E0000h
0x180024944  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x18002494b  mov     [rbp+120h+var_1A0], rax
0x18002494f  mov     rcx, [rbp+120h+var_160]
0x180024953  test    rcx, rcx
0x180024956  jnz     short loc_18002495F
0x180024958  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18002495e  int     3; Trap to Debugger
0x18002495f  mov     rax, [rcx]
0x180024962  mov     rax, [rax+10h]
0x180024966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002496b  mov     rcx, [rbp+120h+var_160]
0x18002496f  test    rcx, rcx
0x180024972  jz      short loc_18002498B
0x180024974  mov     rax, [rcx]
0x180024977  lea     rdx, [rbp+120h+var_198]
0x18002497b  cmp     rcx, rdx
0x18002497e  setnz   dl
0x180024981  mov     rax, [rax+20h]
0x180024985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002498a  nop
0x18002498b  jmp     loc_18002470A
0x180024990  xor     edi, edi
0x180024992  xor     ebx, ebx
0x180024994  lea     rax, qword_18008D760
0x18002499b  mov     esi, ebx
0x18002499d  shl     rsi, 7
0x1800249a1  lea     r15, [rsi+rax]
0x1800249a5  mov     rdx, r15; struct TableDefinition *
0x1800249a8  mov     rcx, r14; this
0x1800249ab  call    ?PrepareTable@CSmsJetDB@@AEAAJPEAUTableDefinition@@@Z; CSmsJetDB::PrepareTable(TableDefinition *)
0x1800249b0  mov     r12d, eax
0x1800249b3  test    eax, eax
0x1800249b5  js      loc_180024D32
0x1800249bb  lea     rdx, qword_18008D760
0x1800249c2  add     rdx, 8
0x1800249c6  add     rdx, rsi
0x1800249c9  lea     rcx, [r14+20h]
0x1800249cd  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@KU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@@2@@std@@QEAAAEAKAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,ulong>::operator[](std::string const &)
0x1800249d2  mov     [rax], ebx
0x1800249d4  mov     rax, [r14+10h]
0x1800249d8  cmp     rax, [r14+18h]
0x1800249dc  jz      loc_180024CBC
0x1800249e2  mov     rdx, r15; struct TableDefinition *
0x1800249e5  mov     rcx, rax; this
0x1800249e8  call    ??0TableDefinition@@QEAA@AEBU0@@Z; TableDefinition::TableDefinition(TableDefinition const &)
0x1800249ed  sub     qword ptr [r14+10h], 0FFFFFFFFFFFFFF80h
0x1800249f2  jmp     loc_180024CCB
0x1800249f7  cmp     edi, 0FFFFFA7Bh
0x1800249fd  jnz     loc_180024BE5
0x180024a03  mov     [rsp+220h+szParam], 0; szParam
0x180024a0c  xor     r9d, r9d; lParam
0x180024a0f  mov     r8d, r12d; paramid
0x180024a12  mov     rdx, r15; sesid
0x180024a15  mov     rcx, rbx; pinstance
0x180024a18  call    cs:__imp_JetSetSystemParameterA
0x180024a1e  mov     ecx, eax
0x180024a20  test    eax, eax
0x180024a22  jns     short loc_180024A94
0x180024a24  cmp     eax, 0FFFFFC0Dh
0x180024a29  jnz     short loc_180024A32
0x180024a2b  mov     ebx, 8007000Eh
0x180024a30  jmp     short loc_180024A48
0x180024a32  neg     eax
0x180024a34  cmovs   eax, ecx
0x180024a37  movzx   ebx, ax
0x180024a3a  and     ecx, 8E5E0000h
0x180024a40  or      ebx, ecx
0x180024a42  or      ebx, 0E5E0000h
0x180024a48  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180024a4f  mov     [rbp+120h+var_1A0], rax
0x180024a53  mov     rcx, [rbp+120h+var_160]
0x180024a57  test    rcx, rcx
0x180024a5a  jnz     short loc_180024A63
0x180024a5c  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180024a62  int     3; Trap to Debugger
0x180024a63  mov     rax, [rcx]
0x180024a66  mov     rax, [rax+10h]
0x180024a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a6f  mov     rcx, [rbp+120h+var_160]
0x180024a73  test    rcx, rcx
0x180024a76  jz      short loc_180024A8F
0x180024a78  mov     rax, [rcx]
0x180024a7b  lea     rdx, [rbp+120h+var_198]
0x180024a7f  cmp     rcx, rdx
0x180024a82  setnz   dl
0x180024a85  mov     rax, [rax+20h]
0x180024a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a8e  nop
0x180024a8f  jmp     loc_18002470A
0x180024a94  mov     [rsp+220h+szParam], 0; szParam
0x180024a9d  xor     r9d, r9d; lParam
0x180024aa0  lea     r8d, [r9+36h]; paramid
0x180024aa4  mov     rdx, r15; sesid
0x180024aa7  mov     rcx, rbx; pinstance
0x180024aaa  call    cs:__imp_JetSetSystemParameterA
0x180024ab0  mov     ecx, eax
0x180024ab2  test    eax, eax
0x180024ab4  jns     short loc_180024B26
0x180024ab6  cmp     eax, 0FFFFFC0Dh
0x180024abb  jnz     short loc_180024AC4
0x180024abd  mov     ebx, 8007000Eh
0x180024ac2  jmp     short loc_180024ADA
0x180024ac4  neg     eax
0x180024ac6  cmovs   eax, ecx
0x180024ac9  movzx   ebx, ax
0x180024acc  and     ecx, 8E5E0000h
0x180024ad2  or      ebx, ecx
0x180024ad4  or      ebx, 0E5E0000h
0x180024ada  lea     rax, ??_7undo_action@Common@Sms@Windows@@6B@; const Windows::Sms::Common::undo_action::`vftable'
0x180024ae1  mov     [rbp+120h+var_1A0], rax
0x180024ae5  mov     rcx, [rbp+120h+var_160]
  ... truncated ...
```
