# CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Clone(IEnumCATEGORYINFO * *)

- ea: `0x1800af800`
- end: `0x1800af90c`
- name: `?Clone@?$CSCMergedEnum@UIEnumCATEGORYINFO@@UtagCATEGORYINFO@@@@UEAAJPEAPEAUIEnumCATEGORYINFO@@@Z`
- size: `268`
- prototype: `HRESULT __fastcall(CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO> *this, IEnumCATEGORYINFO **ppenum)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800af5d8`
- `0x1800af800`
- `0x1800afe3c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800af84f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800af84f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800af8de`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800af8de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800af8f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800af8f0`
- `RPCRT4!RpcImpersonateClient` at `0x1800af87f`
- `RPCRT4!RpcImpersonateClient` at `0x1800af87f`

## pseudocode

```c
__int64 __fastcall CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Clone(
        CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO> *this,
        CSCMergedEnum<IEnumGUID,_GUID> **ppenum)
{
  unsigned __int64 v3; // rax
  IEnumGUID **v5; // rsi
  CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO> *v7; // rax
  CSCMergedEnum<IEnumGUID,_GUID> *v8; // rax
  CSCMergedEnum<IEnumGUID,_GUID> *v9; // rbx
  RPC_STATUS v10; // eax
  unsigned int m_cTotalEnum; // r8d
  __int64 v12; // rbp
  RPC_STATUS i; // r15d
  IEnumCATEGORYINFO *v14; // rcx
  unsigned int v15; // ebx
  _GUID m_myiid; // [rsp+20h] [rbp-48h] BYREF

  v3 = 8LL * this->m_cTotalEnum;
  if ( v3 > 0xFFFFFFFF )
    return 2147942934LL;
  v5 = (IEnumGUID **)CoTaskMemAlloc((unsigned int)v3);
  if ( !v5 )
    return 2147942414LL;
  v7 = (CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO> *)HeapAlloc(g_hHeap, 0, 0x30u);
  if ( v7
    && (m_myiid = this->m_myiid,
        CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>(v7, &m_myiid),
        (v9 = v8) != 0) )
  {
    v10 = RpcImpersonateClient(0);
    m_cTotalEnum = this->m_cTotalEnum;
    v12 = 0;
    for ( i = v10; (unsigned int)v12 < m_cTotalEnum; v12 = (unsigned int)(v12 + 1) )
    {
      v14 = this->m_pcsEnum[v12];
      ((void (__fastcall *)(IEnumCATEGORYINFO *, IEnumGUID **))v14->lpVtbl[2].QueryInterface)(v14, &v5[v12]);
      m_cTotalEnum = this->m_cTotalEnum;
    }
    CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Initialize(v9, v5, m_cTotalEnum);
    v9->m_CurrentEnum = this->m_CurrentEnum;
    *ppenum = v9;
    ((void (__fastcall *)(CSCMergedEnum<IEnumGUID,_GUID> *))v9->lpVtbl->AddRef)(v9);
    if ( !i )
      RevertToSelf();
    v15 = 0;
  }
  else
  {
    v15 = -2147024882;
  }
  CoTaskMemFree(v5);
  return v15;
}

```

## disassembly

```asm
0x1800af800  push    rbx
0x1800af802  push    rbp
0x1800af803  push    rsi
0x1800af804  push    rdi
0x1800af805  push    r14
0x1800af807  push    r15
0x1800af809  sub     rsp, 38h
0x1800af80d  mov     eax, [this+10h]
0x1800af810  mov     rdi, this
0x1800af813  shl     rax, 3
0x1800af817  mov     ecx, 0FFFFFFFFh
0x1800af81c  mov     r14, ppenum
0x1800af81f  cmp     rax, this
0x1800af822  ja      loc_1800AF8FA
0x1800af828  mov     ecx, eax; cb
0x1800af82a  call    cs:__imp_CoTaskMemAlloc
0x1800af830  mov     rsi, rax
0x1800af833  test    rax, rax
0x1800af836  jnz     short loc_1800AF842
0x1800af838  mov     eax, 8007000Eh
0x1800af83d  jmp     loc_1800AF8FF
0x1800af842  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800af849  xor     edx, edx; dwFlags
0x1800af84b  lea     r8d, [ppenum+30h]; dwBytes
0x1800af84f  call    cs:__imp_HeapAlloc
0x1800af855  test    rax, rax
0x1800af858  jz      loc_1800AF8E8
0x1800af85e  movups  xmm0, xmmword ptr [rdi+1Ch]
0x1800af862  lea     ppenum, [rsp+68h+var_48]
0x1800af867  mov     this, rax
0x1800af86a  movdqu  [rsp+68h+var_48], xmm0
0x1800af870  call    ??0?$CSCMergedEnum@UIEnumCATEGORYINFO@@UtagCATEGORYINFO@@@@QEAA@U_GUID@@@Z; CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>(_GUID)
0x1800af875  mov     rbx, rax
0x1800af878  test    rax, rax
0x1800af87b  jz      short loc_1800AF8E8
0x1800af87d  xor     ecx, ecx; BindingHandle
0x1800af87f  call    cs:__imp_RpcImpersonateClient
0x1800af885  mov     r8d, [rdi+10h]
0x1800af889  xor     ebp, ebp
0x1800af88b  mov     r15d, eax
0x1800af88e  test    r8d, r8d
0x1800af891  jz      short loc_1800AF8B6
0x1800af893  mov     this, [rdi+8]
0x1800af897  lea     ppenum, [rsi+rbp*8]
0x1800af89b  mov     this, [this+rbp*8]
0x1800af89f  mov     rax, [this]
0x1800af8a2  mov     rax, [rax+30h]
0x1800af8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af8ab  mov     r8d, [rdi+10h]; cEnum
0x1800af8af  inc     ebp
0x1800af8b1  cmp     ebp, r8d
0x1800af8b4  jb      short loc_1800AF893
0x1800af8b6  mov     ppenum, rsi; pcsEnum
0x1800af8b9  mov     this, rbx; this
0x1800af8bc  call    ?Initialize@?$CSCMergedEnum@UIEnumCATEGORYINFO@@UtagCATEGORYINFO@@@@QEAAJPEAPEAUIEnumCATEGORYINFO@@K@Z; CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Initialize(IEnumCATEGORYINFO * *,ulong)
0x1800af8c1  mov     eax, [rdi+18h]
0x1800af8c4  mov     this, rbx
0x1800af8c7  mov     [rbx+18h], eax
0x1800af8ca  mov     [r14], rbx
0x1800af8cd  mov     rax, [rbx]
0x1800af8d0  mov     rax, [rax+8]
0x1800af8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af8d9  test    r15d, r15d
0x1800af8dc  jnz     short loc_1800AF8E4
0x1800af8de  call    cs:__imp_RevertToSelf
0x1800af8e4  xor     ebx, ebx
0x1800af8e6  jmp     short loc_1800AF8ED
0x1800af8e8  mov     ebx, 8007000Eh
0x1800af8ed  mov     this, rsi; pv
0x1800af8f0  call    cs:__imp_CoTaskMemFree
0x1800af8f6  mov     eax, ebx
0x1800af8f8  jmp     short loc_1800AF8FF
0x1800af8fa  mov     eax, 80070216h
0x1800af8ff  add     rsp, 38h
0x1800af903  pop     r15
0x1800af905  pop     r14
0x1800af907  pop     rdi
0x1800af908  pop     rsi
0x1800af909  pop     rbp
0x1800af90a  pop     rbx
0x1800af90b  retn
```
