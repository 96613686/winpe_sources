# CPropStoreBinaryWriter::Serialize(IPropertyStore *)

- ea: `0x180054a10`
- end: `0x18005501f`
- name: `?Serialize@CPropStoreBinaryWriter@@QEAAJPEAUIPropertyStore@@@Z`
- size: `1551`
- prototype: `__int64 __fastcall(CPropStoreBinaryWriter *__hidden this, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180033df0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x18001a320`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180050750`
- `0x180052f78`
- `0x180054a10`
- `0x180055028`
- `0x180055294`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054be0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054fe6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054be0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180054fe6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054aa9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054b50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054d0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054d9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054e2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054ebb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054f4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054aa9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054b50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054d0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054d9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054e2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054ebb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054f4a`

## string_xrefs

- `0x180054a3f`: `CPropStoreBinaryWriter::Serialize`
- `0x180054d65`: `CPropStoreBinaryWriter::Serialize`
- `0x180054df4`: `CPropStoreBinaryWriter::Serialize`
- `0x180054e83`: `CPropStoreBinaryWriter::Serialize`
- `0x180054f12`: `CPropStoreBinaryWriter::Serialize`
- `0x180054fa1`: `CPropStoreBinaryWriter::Serialize`

## pseudocode

```c
__int64 __fastcall CPropStoreBinaryWriter::Serialize(CPropStoreBinaryWriter *this, struct IPropertyStore *a2)
{
  int v4; // edx
  __int64 v5; // rdx
  int v6; // edi
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  unsigned int i; // r15d
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  const struct _tagpropertykey *v19; // rdx
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  _BYTE v37[4]; // [rsp+60h] [rbp-9h] BYREF
  int v38; // [rsp+64h] [rbp-5h] BYREF
  PROPVARIANT pvar; // [rsp+68h] [rbp-1h] BYREF
  struct _GUID v40; // [rsp+80h] [rbp+17h] BYREF
  int v41; // [rsp+90h] [rbp+27h]

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v37, "CPropStoreBinaryWriter::Serialize", 311);
  v4 = 0;
  v38 = 0;
  v41 = 0;
  v40 = 0;
  memset(&pvar, 0, sizeof(pvar));
  if ( a2 )
  {
    v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, int *))a2->lpVtbl->GetCount)(a2, &v38);
    if ( v6 < 0 )
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CPropStoreBinaryWriter::Serialize", 323, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 47;
LABEL_85:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_363825162bad371b7f2cc59a20a496c3_Traceguids, this, v6);
        goto LABEL_86;
      }
      goto LABEL_86;
    }
    v4 = v38;
  }
  v6 = CBinaryWriter::WriteBool((CPropStoreBinaryWriter *)((char *)this + 520), v4);
  if ( v6 >= 0 )
  {
    for ( i = 0; i < v38; ++i )
    {
      PropVariantClear(&pvar);
      v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, _QWORD, struct _GUID *))a2->lpVtbl->GetAt)(a2, i, &v40);
      if ( v6 < 0 )
      {
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)v35 + 499) != v6 )
            CallStackContext::TraceFailure(v35, "CPropStoreBinaryWriter::Serialize", 337, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 49;
          goto LABEL_85;
        }
        break;
      }
      v6 = CBinaryReader::ReadGuid((CPropStoreBinaryWriter *)((char *)this + 520), &v40);
      if ( v6 < 0 )
      {
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != v6 )
            CallStackContext::TraceFailure(v32, "CPropStoreBinaryWriter::Serialize", 339, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 50;
          goto LABEL_85;
        }
        break;
      }
      v6 = CBinaryWriter::WriteBool((CPropStoreBinaryWriter *)((char *)this + 520), v41);
      if ( v6 < 0 )
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != v6 )
            CallStackContext::TraceFailure(v29, "CPropStoreBinaryWriter::Serialize", 340, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 51;
          goto LABEL_85;
        }
        break;
      }
      v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, struct _GUID *, PROPVARIANT *))a2->lpVtbl->GetValue)(
             a2,
             &v40,
             &pvar);
      if ( v6 < 0 )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v26 + 499) != v6 )
            CallStackContext::TraceFailure(v26, "CPropStoreBinaryWriter::Serialize", 343, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 52;
          goto LABEL_85;
        }
        break;
      }
      v6 = CPropStoreBinaryWriter::WriteVariant(this, v19, &pvar);
      if ( v6 < 0 )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != v6 )
            CallStackContext::TraceFailure(v23, "CPropStoreBinaryWriter::Serialize", 345, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 53;
          goto LABEL_85;
        }
        break;
      }
      if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() >= 0x10u )
        WPP_SF_DDDDDDDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          v40.Data2,
          v40.Data4[1] | (v40.Data4[0] << 8),
          v40.Data1,
          v40.Data2,
          v40.Data3,
          v40.Data4[1] | (v40.Data4[0] << 8),
          v40.Data4[3] | (v40.Data4[2] << 8),
          v40.Data4[5] | (v40.Data4[4] << 8),
          v40.Data4[7] | (v40.Data4[6] << 8),
          v41,
          pvar.vt);
    }
  }
  else
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != v6 )
        CallStackContext::TraceFailure(v14, "CPropStoreBinaryWriter::Serialize", 330, v6);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 48;
      goto LABEL_85;
    }
  }
LABEL_86:
  PropVariantClear(&pvar);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v37);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180054a10  mov     [rsp-8+arg_10], rbx
0x180054a15  mov     [rsp-8+arg_18], rsi
0x180054a1a  push    rbp
0x180054a1b  push    rdi
0x180054a1c  push    r12
0x180054a1e  push    r14
0x180054a20  push    r15
0x180054a22  lea     rbp, [rsp-37h]
0x180054a27  sub     rsp, 0A0h
0x180054a2e  mov     rax, cs:__security_cookie
0x180054a35  xor     rax, rsp
0x180054a38  mov     [rbp+57h+var_28], rax
0x180054a3c  mov     r14, rdx
0x180054a3f  lea     rbx, aCpropstorebina; "CPropStoreBinaryWriter::Serialize"
0x180054a46  mov     rsi, rcx
0x180054a49  mov     rdx, rbx; char *
0x180054a4c  mov     r8d, 137h; int
0x180054a52  lea     rcx, [rbp+57h+var_60]; this
0x180054a56  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180054a5b  xor     eax, eax
0x180054a5d  xor     edx, edx
0x180054a5f  mov     [rbp+57h+var_5C], edx
0x180054a62  xorps   xmm0, xmm0
0x180054a65  mov     [rbp+57h+var_30], eax
0x180054a68  xorps   xmm1, xmm1
0x180054a6b  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180054a6f  movups  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x180054a73  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x180054a77  test    r14, r14
0x180054a7a  jz      loc_180054B2B
0x180054a80  mov     rax, [r14]
0x180054a83  lea     rdx, [rbp+57h+var_5C]
0x180054a87  mov     rcx, r14
0x180054a8a  mov     rax, [rax+18h]
0x180054a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a93  mov     edi, eax
0x180054a95  test    eax, eax
0x180054a97  jns     loc_180054B28
0x180054a9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054aa4  test    rcx, rcx
0x180054aa7  jnz     short loc_180054AEA
0x180054aa9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054aaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054ab6  mov     rcx, rax
0x180054ab9  test    rax, rax
0x180054abc  jz      short loc_180054ADC
0x180054abe  mov     rax, [rax]
0x180054ac1  mov     edx, 7F0h
0x180054ac6  mov     rax, [rax+8]
0x180054aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054acf  test    eax, eax
0x180054ad1  jz      short loc_180054ADC
0x180054ad3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054ada  jmp     short loc_180054AEA
0x180054adc  lea     rcx, qword_180069A90; this
0x180054ae3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054aea  cmp     byte ptr [rcx+8], 0
0x180054aee  jz      short loc_180054B11
0x180054af0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054af5  cmp     [rax+7CCh], edi
0x180054afb  jz      short loc_180054B11
0x180054afd  mov     r9d, edi; int
0x180054b00  mov     r8d, 143h; int
0x180054b06  mov     rdx, rbx; char *
0x180054b09  mov     rcx, rax; this
0x180054b0c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054b11  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054b16  cmp     al, 1
0x180054b18  jb      loc_180054FE2
0x180054b1e  mov     edx, 2Fh ; '/'
0x180054b23  jmp     loc_180054FC4
0x180054b28  mov     edx, [rbp+57h+var_5C]; int
0x180054b2b  lea     r12, [rsi+208h]
0x180054b32  mov     rcx, r12; this
0x180054b35  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x180054b3a  mov     edi, eax
0x180054b3c  test    eax, eax
0x180054b3e  jns     loc_180054BCF
0x180054b44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054b4b  test    rcx, rcx
0x180054b4e  jnz     short loc_180054B91
0x180054b50  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054b56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054b5d  mov     rcx, rax
0x180054b60  test    rax, rax
0x180054b63  jz      short loc_180054B83
0x180054b65  mov     rax, [rax]
0x180054b68  mov     edx, 7F0h
0x180054b6d  mov     rax, [rax+8]
0x180054b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b76  test    eax, eax
0x180054b78  jz      short loc_180054B83
0x180054b7a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054b81  jmp     short loc_180054B91
0x180054b83  lea     rcx, qword_180069A90; this
0x180054b8a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054b91  cmp     byte ptr [rcx+8], 0
0x180054b95  jz      short loc_180054BB8
0x180054b97  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054b9c  cmp     [rax+7CCh], edi
0x180054ba2  jz      short loc_180054BB8
0x180054ba4  mov     r9d, edi; int
0x180054ba7  mov     r8d, 14Ah; int
0x180054bad  mov     rdx, rbx; char *
0x180054bb0  mov     rcx, rax; this
0x180054bb3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054bb8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054bbd  cmp     al, 1
0x180054bbf  jb      loc_180054FE2
0x180054bc5  mov     edx, 30h ; '0'
0x180054bca  jmp     loc_180054FC4
0x180054bcf  xor     r15d, r15d
0x180054bd2  cmp     r15d, [rbp+57h+var_5C]
0x180054bd6  jnb     loc_180054FE2
0x180054bdc  lea     rcx, [rbp+57h+pvar]; pvar
0x180054be0  call    cs:__imp_PropVariantClear
0x180054be6  mov     rax, [r14]
0x180054be9  lea     r8, [rbp+57h+var_40]
0x180054bed  mov     edx, r15d
0x180054bf0  mov     rcx, r14
0x180054bf3  mov     rax, [rax+20h]
0x180054bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bfc  mov     edi, eax
0x180054bfe  test    eax, eax
0x180054c00  js      loc_180054F3E
0x180054c06  lea     rdx, [rbp+57h+var_40]; struct _GUID *
0x180054c0a  mov     rcx, r12; this
0x180054c0d  call    ?ReadGuid@CBinaryReader@@QEAAJAEAU_GUID@@@Z; CBinaryReader::ReadGuid(_GUID &)
0x180054c12  mov     edi, eax
0x180054c14  test    eax, eax
0x180054c16  js      loc_180054EAF
0x180054c1c  mov     edx, [rbp+57h+var_30]; int
0x180054c1f  mov     rcx, r12; this
0x180054c22  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x180054c27  mov     edi, eax
0x180054c29  test    eax, eax
0x180054c2b  js      loc_180054E20
0x180054c31  mov     rax, [r14]
0x180054c34  lea     r8, [rbp+57h+pvar]
0x180054c38  lea     rdx, [rbp+57h+var_40]
0x180054c3c  mov     rcx, r14
0x180054c3f  mov     rax, [rax+28h]
0x180054c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c48  mov     edi, eax
0x180054c4a  test    eax, eax
0x180054c4c  js      loc_180054D91
0x180054c52  lea     r8, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180054c56  mov     rcx, rsi; this
0x180054c59  call    ?WriteVariant@CPropStoreBinaryWriter@@IEAAJAEBU_tagpropertykey@@PEBUtagPROPVARIANT@@@Z; CPropStoreBinaryWriter::WriteVariant(_tagpropertykey const &,tagPROPVARIANT const *)
0x180054c5e  mov     edi, eax
0x180054c60  test    eax, eax
0x180054c62  js      loc_180054D02
0x180054c68  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x180054c6d  cmp     al, 10h
0x180054c6f  jb      loc_180054CFA
0x180054c75  movzx   eax, [rbp+57h+var_40.Data4+7]
0x180054c79  movzx   ecx, [rbp+57h+var_40.Data3]
0x180054c7d  movzx   ebx, [rbp+57h+var_40.Data4+6]
0x180054c81  movzx   r10d, [rbp+57h+var_40.Data4+4]
0x180054c86  movzx   r9d, [rbp+57h+var_40.Data4+2]
0x180054c8b  movzx   r8d, [rbp+57h+var_40.Data4]
0x180054c90  movzx   r11d, word ptr [rbp+57h+pvar]
0x180054c95  movzx   edx, [rbp+57h+var_40.Data2]
0x180054c99  mov     [rsp+0C0h+var_68], r11d
0x180054c9e  shl     r9d, 8
0x180054ca2  shl     ebx, 8
0x180054ca5  or      ebx, eax
0x180054ca7  shl     r10d, 8
0x180054cab  movzx   eax, [rbp+57h+var_40.Data4+5]
0x180054caf  or      r10d, eax
0x180054cb2  shl     r8d, 8
0x180054cb6  movzx   eax, [rbp+57h+var_40.Data4+3]
0x180054cba  or      r9d, eax
0x180054cbd  movzx   eax, [rbp+57h+var_40.Data4+1]
0x180054cc1  or      r8d, eax
0x180054cc4  mov     eax, [rbp+57h+var_30]
0x180054cc7  mov     [rsp+0C0h+var_70], eax
0x180054ccb  mov     [rsp+0C0h+var_78], ebx
0x180054ccf  mov     [rsp+0C0h+var_80], r10d
0x180054cd4  mov     [rsp+0C0h+var_88], r9d
0x180054cd9  mov     r9d, [rbp+57h+var_40.Data1]
0x180054cdd  mov     [rsp+0C0h+var_90], r8d
0x180054ce2  mov     [rsp+0C0h+var_98], ecx
0x180054ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ced  mov     [rsp+0C0h+var_A0], edx
0x180054cf1  mov     rcx, [rcx+38h]
0x180054cf5  call    WPP_SF_DDDDDDDDD
0x180054cfa  inc     r15d
0x180054cfd  jmp     loc_180054BD2
0x180054d02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054d09  test    rcx, rcx
0x180054d0c  jnz     short loc_180054D4F
0x180054d0e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054d14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054d1b  mov     rcx, rax
0x180054d1e  test    rax, rax
0x180054d21  jz      short loc_180054D41
0x180054d23  mov     rax, [rax]
0x180054d26  mov     edx, 7F0h
0x180054d2b  mov     rax, [rax+8]
0x180054d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d34  test    eax, eax
0x180054d36  jz      short loc_180054D41
0x180054d38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054d3f  jmp     short loc_180054D4F
0x180054d41  lea     rcx, qword_180069A90; this
0x180054d48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054d4f  cmp     byte ptr [rcx+8], 0
0x180054d53  jz      short loc_180054D7A
0x180054d55  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054d5a  cmp     [rax+7CCh], edi
0x180054d60  jz      short loc_180054D7A
0x180054d62  mov     r9d, edi; int
0x180054d65  lea     rdx, aCpropstorebina; "CPropStoreBinaryWriter::Serialize"
0x180054d6c  mov     r8d, 159h; int
0x180054d72  mov     rcx, rax; this
0x180054d75  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054d7a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054d7f  cmp     al, 1
0x180054d81  jb      loc_180054FE2
0x180054d87  mov     edx, 35h ; '5'
0x180054d8c  jmp     loc_180054FC4
0x180054d91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054d98  test    rcx, rcx
0x180054d9b  jnz     short loc_180054DDE
0x180054d9d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054da3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054daa  mov     rcx, rax
0x180054dad  test    rax, rax
0x180054db0  jz      short loc_180054DD0
0x180054db2  mov     rax, [rax]
0x180054db5  mov     edx, 7F0h
0x180054dba  mov     rax, [rax+8]
0x180054dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054dc3  test    eax, eax
0x180054dc5  jz      short loc_180054DD0
0x180054dc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054dce  jmp     short loc_180054DDE
0x180054dd0  lea     rcx, qword_180069A90; this
0x180054dd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054dde  cmp     byte ptr [rcx+8], 0
0x180054de2  jz      short loc_180054E09
0x180054de4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054de9  cmp     [rax+7CCh], edi
0x180054def  jz      short loc_180054E09
0x180054df1  mov     r9d, edi; int
0x180054df4  lea     rdx, aCpropstorebina; "CPropStoreBinaryWriter::Serialize"
0x180054dfb  mov     r8d, 157h; int
0x180054e01  mov     rcx, rax; this
0x180054e04  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054e09  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054e0e  cmp     al, 1
0x180054e10  jb      loc_180054FE2
0x180054e16  mov     edx, 34h ; '4'
0x180054e1b  jmp     loc_180054FC4
0x180054e20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054e27  test    rcx, rcx
0x180054e2a  jnz     short loc_180054E6D
0x180054e2c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054e32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054e39  mov     rcx, rax
0x180054e3c  test    rax, rax
0x180054e3f  jz      short loc_180054E5F
0x180054e41  mov     rax, [rax]
0x180054e44  mov     edx, 7F0h
0x180054e49  mov     rax, [rax+8]
0x180054e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e52  test    eax, eax
0x180054e54  jz      short loc_180054E5F
0x180054e56  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054e5d  jmp     short loc_180054E6D
0x180054e5f  lea     rcx, qword_180069A90; this
0x180054e66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054e6d  cmp     byte ptr [rcx+8], 0
0x180054e71  jz      short loc_180054E98
0x180054e73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054e78  cmp     [rax+7CCh], edi
0x180054e7e  jz      short loc_180054E98
0x180054e80  mov     r9d, edi; int
0x180054e83  lea     rdx, aCpropstorebina; "CPropStoreBinaryWriter::Serialize"
0x180054e8a  mov     r8d, 154h; int
0x180054e90  mov     rcx, rax; this
0x180054e93  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054e98  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054e9d  cmp     al, 1
0x180054e9f  jb      loc_180054FE2
0x180054ea5  mov     edx, 33h ; '3'
0x180054eaa  jmp     loc_180054FC4
0x180054eaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054eb6  test    rcx, rcx
0x180054eb9  jnz     short loc_180054EFC
0x180054ebb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054ec1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054ec8  mov     rcx, rax
0x180054ecb  test    rax, rax
0x180054ece  jz      short loc_180054EEE
0x180054ed0  mov     rax, [rax]
0x180054ed3  mov     edx, 7F0h
0x180054ed8  mov     rax, [rax+8]
0x180054edc  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
