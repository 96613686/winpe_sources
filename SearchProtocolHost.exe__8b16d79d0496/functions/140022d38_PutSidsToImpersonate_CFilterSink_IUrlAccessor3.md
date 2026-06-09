# PutSidsToImpersonate(CFilterSink &,IUrlAccessor3 *)

- ea: `0x140022d38`
- end: `0x140022f81`
- name: `?PutSidsToImpersonate@@YAJAEAVCFilterSink@@PEAUIUrlAccessor3@@@Z`
- size: `585`
- prototype: `__int64 __fastcall(struct CFilterSink *, struct IUrlAccessor3 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x140005240`
- `0x140006210`
- `0x1400124cc`
- `0x14001d5b4`
- `0x14001ea8c`
- `0x140022d38`
- `0x14003c05c`
- `0x14003c630`
- `0x14004f578`
- `0x140070010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140022ecf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140022ecf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140022e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140022e94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140022e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140022e94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140022f49`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140022f49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022ede`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022ede`

## pseudocode

```c
__int64 __fastcall PutSidsToImpersonate(struct CFilterSink *a1, struct IUrlAccessor3 *a2)
{
  struct IUrlAccessor3Vtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetImpersonationSidBlobs)(IUrlAccessor3 *, LPCWSTR, DWORD *, BLOB **); // rbx
  unsigned int *Path; // rax
  int Error; // esi
  BYTE *v8; // rax
  unsigned int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  int v13; // r14d
  SIZE_T v14; // rcx
  BYTE *pData; // r12
  void *v16; // rax
  DWORD v17; // ecx
  unsigned int v18; // edi
  __int64 v19; // rbx
  unsigned int v21; // [rsp+30h] [rbp-69h] BYREF
  __int64 v22; // [rsp+38h] [rbp-61h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+40h] [rbp-59h] BYREF
  __int64 v24; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v25; // [rsp+60h] [rbp-39h]
  struct tagSTAT_CHUNK v26; // [rsp+70h] [rbp-29h] BYREF

  memset_0(&v26, 0, sizeof(v26));
  v26.attribute.psProperty.ulKind = 1;
  v26.breakType = CHUNK_EOS;
  v26.flags = CHUNK_VALUE;
  lpVtbl = a2->lpVtbl;
  v26.attribute.guidPropSet = GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04;
  LODWORD(v26.attribute.psProperty.propid) = 25;
  v21 = 0;
  GetImpersonationSidBlobs = lpVtbl->GetImpersonationSidBlobs;
  v22 = 0;
  Path = (unsigned int *)CURL::GetPath((char *)a1 + 1072, &v24);
  Error = ((__int64 (__fastcall *)(struct IUrlAccessor3 *, __int64, unsigned int *, __int64 *))GetImpersonationSidBlobs)(
            a2,
            *(_QWORD *)(*((_QWORD *)Path + 1) + 8LL) + 2LL * *Path,
            &v21,
            &v22);
  if ( !v21 )
    SearchIndexerDiagnosticTelemetry::IndexEfsCertificateMapFail();
  memset(&pvar, 0, sizeof(pvar));
  if ( Error < 0 )
    goto LABEL_13;
  v8 = (BYTE *)CoTaskMemAlloc(24LL * v21);
  if ( !v8 )
  {
    Error = -2147024882;
    goto LABEL_22;
  }
  pvar.bstrblobVal.pData = v8;
  pvar.vt = 4108;
  v9 = 0;
  pvar.lVal = v21;
  if ( !v21 )
  {
LABEL_13:
    v12 = 0;
    v13 = 0;
    goto LABEL_18;
  }
  do
  {
    v10 = v9++;
    v11 = 3 * v10;
    *(_WORD *)&pvar.bstrblobVal.pData[8 * v11] = 65;
    *(_DWORD *)&pvar.bstrblobVal.pData[8 * v11 + 8] = 0;
    *(_QWORD *)&pvar.bstrblobVal.pData[8 * v11 + 16] = 0;
  }
  while ( v9 < v21 );
  v12 = 0;
  v13 = 0;
  while ( v12 < pvar.lVal )
  {
    v14 = *(unsigned int *)(v22 + 16LL * v12);
    if ( (_DWORD)v14 )
    {
      pData = pvar.bstrblobVal.pData;
      v16 = CoTaskMemAlloc(v14);
      *(_QWORD *)&pData[24 * v13 + 16] = v16;
      if ( v16 )
      {
        v17 = *(_DWORD *)(v22 + 16LL * v12);
        *(_DWORD *)&pData[24 * v13 + 8] = v17;
        if ( !CopySid(v17, v16, *(PSID *)(v22 + 16LL * v12 + 8)) )
        {
          CoTaskMemFree(*(LPVOID *)&pData[24 * v13 + 16]);
          *(_DWORD *)&pData[24 * v13 + 8] = 0;
          Error = ResultFromLastError();
        }
      }
      else
      {
        Error = -2147024882;
      }
      ++v13;
    }
    ++v12;
LABEL_18:
    if ( Error < 0 )
      goto LABEL_22;
  }
  Error = CFilterSink::AddChunk(a1, &v26);
  if ( Error >= 0 )
    Error = CFilterSink::AddValue(a1, &pvar);
LABEL_22:
  v18 = v21;
  v19 = v22;
  v24 = 0;
  v25 = 0;
  CSidContainer::FreeBlobs((CSidContainer *)&v24);
  v24 = v19;
  v25 = v18;
  PropVariantClear((PROPVARIANT *)&pvar);
  CSidContainer::FreeBlobs((CSidContainer *)&v24);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x140022d38  mov     [rsp-8+arg_10], rbx
0x140022d3d  push    rbp
0x140022d3e  push    rsi
0x140022d3f  push    rdi
0x140022d40  push    r12
0x140022d42  push    r13
0x140022d44  push    r14
0x140022d46  push    r15
0x140022d48  lea     rbp, [rsp-27h]
0x140022d4d  sub     rsp, 0C0h
0x140022d54  mov     rax, cs:__security_cookie
0x140022d5b  xor     rax, rsp
0x140022d5e  mov     [rbp+57h+var_40], rax
0x140022d62  mov     rdi, rdx
0x140022d65  mov     r13, rcx
0x140022d68  xor     edx, edx; Val
0x140022d6a  lea     rcx, [rbp+57h+var_80]; void *
0x140022d6e  lea     r8d, [rdx+40h]; Size
0x140022d72  call    memset_0
0x140022d77  movups  xmm0, xmmword ptr cs:_GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data1
0x140022d7e  mov     eax, 2
0x140022d83  mov     [rbp+57h+var_80.attribute.psProperty.ulKind], 1
0x140022d8a  mov     [rbp+57h+var_80.breakType], eax
0x140022d8d  lea     rcx, [r13+430h]
0x140022d94  mov     [rbp+57h+var_80.flags], eax
0x140022d97  lea     rdx, [rbp+57h+var_98]
0x140022d9b  mov     rax, [rdi]
0x140022d9e  xor     r15d, r15d
0x140022da1  movdqu  xmmword ptr [rbp+57h+var_80.attribute.guidPropSet.Data1], xmm0
0x140022da6  mov     dword ptr [rbp+57h+var_80.attribute.psProperty.8], 19h
0x140022dad  mov     [rbp+57h+var_C0], r15d
0x140022db1  mov     rbx, [rax+98h]
0x140022db8  mov     [rbp+57h+var_B8], r15
0x140022dbc  call    ?GetPath@CURL@@QEAA?AVCLMSubStr@@XZ; CURL::GetPath(void)
0x140022dc1  lea     r9, [rbp+57h+var_B8]
0x140022dc5  lea     r8, [rbp+57h+var_C0]
0x140022dc9  mov     edx, [rax]
0x140022dcb  mov     rax, [rax+8]
0x140022dcf  mov     rcx, [rax+8]
0x140022dd3  mov     rax, rbx
0x140022dd6  lea     rdx, [rcx+rdx*2]
0x140022dda  mov     rcx, rdi
0x140022ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022de2  mov     esi, eax
0x140022de4  cmp     [rbp+57h+var_C0], r15d
0x140022de8  jnz     short loc_140022DEF
0x140022dea  call    ?IndexEfsCertificateMapFail@SearchIndexerDiagnosticTelemetry@@SAXXZ; SearchIndexerDiagnosticTelemetry::IndexEfsCertificateMapFail(void)
0x140022def  xor     eax, eax
0x140022df1  xorps   xmm0, xmm0
0x140022df4  mov     [rbp+57h+var_A0], rax
0x140022df8  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x140022dfc  test    esi, esi
0x140022dfe  js      loc_140022EAE
0x140022e04  mov     ecx, [rbp+57h+var_C0]
0x140022e07  lea     rcx, [rcx+rcx*2]
0x140022e0b  shl     rcx, 3; cb
0x140022e0f  call    cs:__imp_CoTaskMemAlloc
0x140022e15  mov     rcx, rax
0x140022e18  test    rax, rax
0x140022e1b  jnz     short loc_140022E27
0x140022e1d  mov     esi, 8007000Eh
0x140022e22  jmp     loc_140022F26
0x140022e27  mov     eax, 100Ch
0x140022e2c  mov     [rbp+57h+var_A0], rcx
0x140022e30  mov     word ptr [rbp+57h+pvar], ax
0x140022e34  mov     edx, r15d
0x140022e37  mov     eax, [rbp+57h+var_C0]
0x140022e3a  mov     dword ptr [rbp+57h+pvar+8], eax
0x140022e3d  test    eax, eax
0x140022e3f  jz      short loc_140022EAE
0x140022e41  mov     eax, edx
0x140022e43  inc     edx
0x140022e45  lea     rcx, [rax+rax*2]
0x140022e49  mov     rax, [rbp+57h+var_A0]
0x140022e4d  mov     word ptr [rax+rcx*8], 41h ; 'A'
0x140022e53  mov     rax, [rbp+57h+var_A0]
0x140022e57  mov     [rax+rcx*8+8], r15d
0x140022e5c  mov     rax, [rbp+57h+var_A0]
0x140022e60  mov     [rax+rcx*8+10h], r15
0x140022e65  cmp     edx, [rbp+57h+var_C0]
0x140022e68  jb      short loc_140022E41
0x140022e6a  mov     ebx, r15d
0x140022e6d  mov     r14d, r15d
0x140022e70  cmp     ebx, dword ptr [rbp+57h+pvar+8]
0x140022e73  jnb     loc_140022F06
0x140022e79  mov     rax, [rbp+57h+var_B8]
0x140022e7d  mov     edi, ebx
0x140022e7f  add     rdi, rdi
0x140022e82  mov     ecx, [rax+rdi*8]; cb
0x140022e85  test    ecx, ecx
0x140022e87  jz      short loc_140022EFA
0x140022e89  mov     r12, [rbp+57h+var_A0]
0x140022e8d  mov     eax, r14d
0x140022e90  lea     r15, [rax+rax*2]
0x140022e94  call    cs:__imp_CoTaskMemAlloc
0x140022e9a  mov     [r12+r15*8+10h], rax
0x140022e9f  mov     rdx, rax; pDestinationSid
0x140022ea2  test    rax, rax
0x140022ea5  jnz     short loc_140022EB6
0x140022ea7  mov     esi, 8007000Eh
0x140022eac  jmp     short loc_140022EF4
0x140022eae  mov     ebx, r15d
0x140022eb1  mov     r14d, r15d
0x140022eb4  jmp     short loc_140022EFC
0x140022eb6  test    esi, esi
0x140022eb8  js      short loc_140022EF4
0x140022eba  mov     rax, [rbp+57h+var_B8]
0x140022ebe  mov     ecx, [rax+rdi*8]; nDestinationSidLength
0x140022ec1  mov     [r12+r15*8+8], ecx
0x140022ec6  mov     r8, [rbp+57h+var_B8]
0x140022eca  mov     r8, [r8+rdi*8+8]; pSourceSid
0x140022ecf  call    cs:__imp_CopySid
0x140022ed5  test    eax, eax
0x140022ed7  jnz     short loc_140022EF4
0x140022ed9  mov     rcx, [r12+r15*8+10h]; pv
0x140022ede  call    cs:__imp_CoTaskMemFree
0x140022ee4  mov     dword ptr [r12+r15*8+8], 0
0x140022eed  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140022ef2  mov     esi, eax
0x140022ef4  inc     r14d
0x140022ef7  xor     r15d, r15d
0x140022efa  inc     ebx
0x140022efc  test    esi, esi
0x140022efe  jns     loc_140022E70
0x140022f04  jmp     short loc_140022F26
0x140022f06  lea     rdx, [rbp+57h+var_80]; struct tagSTAT_CHUNK *
0x140022f0a  mov     rcx, r13; this
0x140022f0d  call    ?AddChunk@CFilterSink@@QEAAJPEAUtagSTAT_CHUNK@@@Z; CFilterSink::AddChunk(tagSTAT_CHUNK *)
0x140022f12  mov     esi, eax
0x140022f14  test    eax, eax
0x140022f16  js      short loc_140022F26
0x140022f18  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x140022f1c  mov     rcx, r13; this
0x140022f1f  call    ?AddValue@CFilterSink@@QEAAJPEAUtagPROPVARIANT@@@Z; CFilterSink::AddValue(tagPROPVARIANT *)
0x140022f24  mov     esi, eax
0x140022f26  mov     edi, [rbp+57h+var_C0]
0x140022f29  lea     rcx, [rbp+57h+var_98]; this
0x140022f2d  mov     rbx, [rbp+57h+var_B8]
0x140022f31  mov     [rbp+57h+var_98], r15
0x140022f35  mov     [rbp+57h+var_90], r15d
0x140022f39  call    ?FreeBlobs@CSidContainer@@QEAAXXZ; CSidContainer::FreeBlobs(void)
0x140022f3e  lea     rcx, [rbp+57h+pvar]; pvar
0x140022f42  mov     [rbp+57h+var_98], rbx
0x140022f46  mov     [rbp+57h+var_90], edi
0x140022f49  call    cs:__imp_PropVariantClear
0x140022f4f  lea     rcx, [rbp+57h+var_98]; this
0x140022f53  call    ?FreeBlobs@CSidContainer@@QEAAXXZ; CSidContainer::FreeBlobs(void)
0x140022f58  mov     eax, esi
0x140022f5a  mov     rcx, [rbp+57h+var_40]
0x140022f5e  xor     rcx, rsp; StackCookie
0x140022f61  call    __security_check_cookie
0x140022f66  mov     rbx, [rsp+0F0h+arg_10]
0x140022f6e  add     rsp, 0C0h
0x140022f75  pop     r15
0x140022f77  pop     r14
0x140022f79  pop     r13
0x140022f7b  pop     r12
0x140022f7d  pop     rdi
0x140022f7e  pop     rsi
0x140022f7f  pop     rbp
0x140022f80  retn
```
