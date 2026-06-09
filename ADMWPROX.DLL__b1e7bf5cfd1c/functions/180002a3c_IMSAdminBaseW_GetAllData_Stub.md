# IMSAdminBaseW_GetAllData_Stub

- ea: `0x180002a3c`
- end: `0x180002c37`
- name: `IMSAdminBaseW_GetAllData_Stub`
- size: `507`
- prototype: `HRESULT __stdcall(IMSAdminBaseW *This, METADATA_HANDLE hMDHandle, LPCWSTR pszMDPath, DWORD dwMDAttributes, DWORD dwMDUserType, DWORD dwMDDataType, DWORD *pdwMDNumDataEntries, DWORD *pdwMDDataSetNumber, DWORD dwMDBufferSize, DWORD *pdwMDRequiredBufferSize, struct _IIS_CRYPTO_BLOB **ppDataBlob)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180001ec0`

## callees

- `0x180001124`
- `0x180002a3c`
- `0x1800031f4`
- `0x180003e3c`
- `0x180004808`
- `0x180009010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180002a87`
- `KERNEL32!LocalAlloc` at `0x180002a87`
- `KERNEL32!LocalFree` at `0x180002c07`
- `KERNEL32!LocalFree` at `0x180002c07`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180002b5f`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180002b5f`
- `ole32!CoTaskMemFree` at `0x180002c1e`
- `ole32!CoTaskMemFree` at `0x180002c1e`

## pseudocode

```c
HRESULT __stdcall IMSAdminBaseW_GetAllData_Stub(
        IMSAdminBaseW *This,
        METADATA_HANDLE hMDHandle,
        LPCWSTR pszMDPath,
        DWORD dwMDAttributes,
        DWORD dwMDUserType,
        DWORD dwMDDataType,
        DWORD *pdwMDNumDataEntries,
        DWORD *pdwMDDataSetNumber,
        DWORD dwMDBufferSize,
        DWORD *pdwMDRequiredBufferSize,
        struct _IIS_CRYPTO_BLOB **ppDataBlob)
{
  struct _IIS_CRYPTO_BLOB **v11; // r14
  HRESULT CleartextBlob; // ebx
  _DWORD *v17; // rax
  _DWORD *v18; // rsi
  __int64 v19; // rdx
  int v20; // ecx
  unsigned __int64 v21; // rbx
  _DWORD *v22; // r8
  unsigned __int64 v23; // rbp
  struct ADM_SECURE_DATA *v24; // rax
  volatile signed __int32 *v25; // rdi
  __int64 (__fastcall ***v26)(_QWORD, LPVOID *, void *, _QWORD, _DWORD); // rcx
  void *v27; // rcx
  LPVOID pv[11]; // [rsp+60h] [rbp-58h] BYREF

  v11 = ppDataBlob;
  pv[0] = 0;
  if ( !ppDataBlob )
    return -2147024809;
  v17 = LocalAlloc(0x40u, dwMDBufferSize);
  v18 = v17;
  if ( v17 )
  {
    CleartextBlob = ((__int64 (__fastcall *)(IMSAdminBaseW *, _QWORD, LPCWSTR, _QWORD, DWORD, DWORD, DWORD *, DWORD *, DWORD, _DWORD *, DWORD *))This->lpVtbl->GetAllData)(
                      This,
                      hMDHandle,
                      pszMDPath,
                      dwMDAttributes,
                      dwMDUserType,
                      dwMDDataType,
                      pdwMDNumDataEntries,
                      pdwMDDataSetNumber,
                      dwMDBufferSize,
                      v17,
                      pdwMDRequiredBufferSize);
    if ( CleartextBlob < 0 )
      goto LABEL_25;
    v19 = *pdwMDNumDataEntries;
    v20 = 0;
    v21 = 28 * v19;
    v22 = v18;
    if ( (_DWORD)v19 )
    {
      do
      {
        v23 = (unsigned int)(v22[4] + v22[5]);
        v22 += 7;
        if ( v23 <= v21 )
          v23 = v21;
        v21 = v23;
        if ( (*(_BYTE *)(v22 - 6) & 4) != 0 )
          v20 = 1;
        LODWORD(v19) = v19 - 1;
      }
      while ( (_DWORD)v19 );
      if ( v20 )
      {
        LODWORD(ppDataBlob) = 0;
        if ( I_RpcBindingIsClientLocal(0, (unsigned int *)&ppDataBlob) || !(_DWORD)ppDataBlob )
        {
          v24 = ADM_SECURE_DATA::FindAndReferenceServerSecureData((struct IUnknown *)This, 1);
          v25 = (volatile signed __int32 *)v24;
          if ( !v24 )
          {
            CleartextBlob = -2146646010;
            goto LABEL_25;
          }
          v26 = (__int64 (__fastcall ***)(_QWORD, LPVOID *, void *, _QWORD, _DWORD))*((_QWORD *)v24 + 6);
          if ( v26 )
          {
            CleartextBlob = (**v26)(v26, pv, v18, (unsigned int)v23, 0);
            if ( CleartextBlob >= 0 )
              goto LABEL_22;
          }
          else
          {
            CleartextBlob = -2146646010;
          }
LABEL_23:
          if ( _InterlockedExchangeAdd(v25 + 6, 0xFFFFFFFF) == 1 )
          {
            ADM_SECURE_DATA::~ADM_SECURE_DATA((ADM_SECURE_DATA *)v25);
            operator delete((void *)v25);
          }
LABEL_25:
          LocalFree(v18);
          if ( CleartextBlob >= 0 )
            return CleartextBlob;
          goto LABEL_26;
        }
      }
    }
    v25 = 0;
    CleartextBlob = IISCryptoCreateCleartextBlob(pv, v18, v21);
    if ( CleartextBlob < 0 )
      goto LABEL_25;
LABEL_22:
    *v11 = (struct _IIS_CRYPTO_BLOB *)pv[0];
    if ( !v25 )
      goto LABEL_25;
    goto LABEL_23;
  }
  CleartextBlob = -2147024888;
LABEL_26:
  v27 = pv[0];
  if ( pv[0] )
  {
    *(_BYTE *)pv[0] = 88;
    CoTaskMemFree(v27);
  }
  return CleartextBlob;
}

```

## disassembly

```asm
0x180002a3c  push    rbx
0x180002a3e  push    rbp
0x180002a3f  push    rsi
0x180002a40  push    rdi
0x180002a41  push    r12
0x180002a43  push    r13
0x180002a45  push    r14
0x180002a47  push    r15
0x180002a49  sub     rsp, 78h
0x180002a4d  mov     r14, [rsp+0B8h+ppDataBlob]
0x180002a55  mov     r15d, r9d
0x180002a58  mov     [rsp+0B8h+pv], 0
0x180002a61  mov     r12, r8
0x180002a64  mov     r13d, edx
0x180002a67  mov     rdi, rcx
0x180002a6a  test    r14, r14
0x180002a6d  jnz     short loc_180002A79
0x180002a6f  mov     ebx, 80070057h
0x180002a74  jmp     loc_180002C24
0x180002a79  mov     ebx, [rsp+0B8h+dwMDBufferSize]
0x180002a80  mov     ecx, 40h ; '@'; uFlags
0x180002a85  mov     edx, ebx; uBytes
0x180002a87  call    cs:__imp_LocalAlloc
0x180002a8d  mov     rsi, rax
0x180002a90  test    rax, rax
0x180002a93  jnz     short loc_180002A9F
0x180002a95  mov     ebx, 80070008h
0x180002a9a  jmp     loc_180002C11
0x180002a9f  mov     rax, [rdi]
0x180002aa2  mov     r9d, r15d
0x180002aa5  mov     rbp, [rsp+0B8h+pdwMDNumDataEntries]
0x180002aad  mov     r8, r12
0x180002ab0  mov     edx, r13d
0x180002ab3  mov     rcx, rdi
0x180002ab6  mov     r10, [rax+68h]
0x180002aba  mov     rax, [rsp+0B8h+pdwMDRequiredBufferSize]
0x180002ac2  mov     [rsp+0B8h+var_68], rax
0x180002ac7  mov     rax, [rsp+0B8h+pdwMDDataSetNumber]
0x180002acf  mov     [rsp+0B8h+var_70], rsi
0x180002ad4  mov     [rsp+0B8h+var_78], ebx
0x180002ad8  mov     [rsp+0B8h+var_80], rax
0x180002add  mov     eax, [rsp+0B8h+dwMDDataType]
0x180002ae4  mov     [rsp+0B8h+var_88], rbp
0x180002ae9  mov     [rsp+0B8h+var_90], eax
0x180002aed  mov     eax, [rsp+0B8h+dwMDUserType]
0x180002af4  mov     [rsp+0B8h+var_98], eax
0x180002af8  mov     rax, r10
0x180002afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b00  mov     ebx, eax
0x180002b02  test    eax, eax
0x180002b04  js      loc_180002C04
0x180002b0a  mov     edx, [rbp+0]
0x180002b0d  xor     ecx, ecx
0x180002b0f  imul    rbx, rdx, 1Ch
0x180002b13  mov     r8, rsi
0x180002b16  test    edx, edx
0x180002b18  jz      loc_180002BC2
0x180002b1e  lea     r15d, [rcx+1]
0x180002b22  mov     ebp, [r8+14h]
0x180002b26  add     ebp, [r8+10h]
0x180002b2a  lea     r8, [r8+1Ch]
0x180002b2e  cmp     rbp, rbx
0x180002b31  cmovbe  rbp, rbx
0x180002b35  test    byte ptr [r8-18h], 4
0x180002b3a  mov     rbx, rbp
0x180002b3d  cmovnz  ecx, r15d
0x180002b41  add     edx, 0FFFFFFFFh
0x180002b44  jnz     short loc_180002B22
0x180002b46  test    ecx, ecx
0x180002b48  jz      short loc_180002BC2
0x180002b4a  lea     rdx, [rsp+0B8h+ppDataBlob]; ClientLocalFlag
0x180002b52  mov     dword ptr [rsp+0B8h+ppDataBlob], 0
0x180002b5d  xor     ecx, ecx; BindingHandle
0x180002b5f  call    cs:__imp_I_RpcBindingIsClientLocal
0x180002b65  test    eax, eax
0x180002b67  jnz     short loc_180002B72
0x180002b69  cmp     dword ptr [rsp+0B8h+ppDataBlob], eax
0x180002b70  jnz     short loc_180002BC2
0x180002b72  mov     edx, r15d; int
0x180002b75  mov     rcx, rdi; struct IUnknown *
0x180002b78  call    ?FindAndReferenceServerSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@H@Z; ADM_SECURE_DATA::FindAndReferenceServerSecureData(IUnknown *,int)
0x180002b7d  mov     rdi, rax
0x180002b80  test    rax, rax
0x180002b83  jnz     short loc_180002B8C
0x180002b85  mov     ebx, 800CC806h
0x180002b8a  jmp     short loc_180002C04
0x180002b8c  mov     rcx, [rax+30h]
0x180002b90  test    rcx, rcx
0x180002b93  jz      short loc_180002BBB
0x180002b95  mov     rax, [rcx]
0x180002b98  lea     rdx, [rsp+0B8h+pv]
0x180002b9d  mov     r9d, ebp
0x180002ba0  mov     [rsp+0B8h+var_98], 0
0x180002ba8  mov     r8, rsi
0x180002bab  mov     rax, [rax]
0x180002bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb3  mov     ebx, eax
0x180002bb5  test    eax, eax
0x180002bb7  js      short loc_180002BE7
0x180002bb9  jmp     short loc_180002BDA
0x180002bbb  mov     ebx, 800CC806h
0x180002bc0  jmp     short loc_180002BE7
0x180002bc2  mov     r8d, ebx
0x180002bc5  lea     rcx, [rsp+0B8h+pv]
0x180002bca  mov     rdx, rsi
0x180002bcd  xor     edi, edi
0x180002bcf  call    IISCryptoCreateCleartextBlob
0x180002bd4  mov     ebx, eax
0x180002bd6  test    eax, eax
0x180002bd8  js      short loc_180002C04
0x180002bda  mov     rax, [rsp+0B8h+pv]
0x180002bdf  mov     [r14], rax
0x180002be2  test    rdi, rdi
0x180002be5  jz      short loc_180002C04
0x180002be7  or      eax, 0FFFFFFFFh
0x180002bea  lock xadd [rdi+18h], eax
0x180002bef  cmp     eax, 1
0x180002bf2  jnz     short loc_180002C04
0x180002bf4  mov     rcx, rdi; this
0x180002bf7  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x180002bfc  mov     rcx, rdi; Block
0x180002bff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002c04  mov     rcx, rsi; hMem
0x180002c07  call    cs:__imp_LocalFree
0x180002c0d  test    ebx, ebx
0x180002c0f  jns     short loc_180002C24
0x180002c11  mov     rcx, [rsp+0B8h+pv]; pv
0x180002c16  test    rcx, rcx
0x180002c19  jz      short loc_180002C24
0x180002c1b  mov     byte ptr [rcx], 58h ; 'X'
0x180002c1e  call    cs:__imp_CoTaskMemFree
0x180002c24  mov     eax, ebx
0x180002c26  add     rsp, 78h
0x180002c2a  pop     r15
0x180002c2c  pop     r14
0x180002c2e  pop     r13
0x180002c30  pop     r12
0x180002c32  pop     rdi
0x180002c33  pop     rsi
0x180002c34  pop     rbp
0x180002c35  pop     rbx
0x180002c36  retn
```
