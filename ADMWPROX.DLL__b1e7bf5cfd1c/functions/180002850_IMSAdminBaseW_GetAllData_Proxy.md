# IMSAdminBaseW_GetAllData_Proxy

- ea: `0x180002850`
- end: `0x180002a34`
- name: `IMSAdminBaseW_GetAllData_Proxy`
- size: `484`
- prototype: `HRESULT __stdcall(IMSAdminBaseW *This, METADATA_HANDLE hMDHandle, LPCWSTR pszMDPath, DWORD dwMDAttributes, DWORD dwMDUserType, DWORD dwMDDataType, DWORD *pdwMDNumDataEntries, DWORD *pdwMDDataSetNumber, DWORD dwMDBufferSize, unsigned __int8 *pbMDBuffer, DWORD *pdwMDRequiredBufferSize)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task`

## callees

- `0x180001124`
- `0x180002850`
- `0x1800031f4`
- `0x180003f60`
- `0x18000413c`
- `0x1800083d2`
- `0x180009010`

## import_xrefs

- `RPCRT4!NdrClientCall2` at `0x180002958`
- `RPCRT4!NdrClientCall2` at `0x180002958`
- `ole32!CoTaskMemFree` at `0x180002a13`
- `ole32!CoTaskMemFree` at `0x180002a13`

## pseudocode

```c
HRESULT __stdcall IMSAdminBaseW_GetAllData_Proxy(
        IMSAdminBaseW *This,
        METADATA_HANDLE hMDHandle,
        LPCWSTR pszMDPath,
        DWORD dwMDAttributes,
        DWORD dwMDUserType,
        DWORD dwMDDataType,
        DWORD *pdwMDNumDataEntries,
        DWORD *pdwMDDataSetNumber,
        DWORD dwMDBufferSize,
        unsigned __int8 *pbMDBuffer,
        DWORD *pdwMDRequiredBufferSize)
{
  struct ADM_SECURE_DATA *v13; // rax
  volatile signed __int32 *v14; // rsi
  HRESULT ClientReceiveCryptoStorage; // ebx
  void *v16; // rcx
  size_t Size; // [rsp+70h] [rbp-58h] BYREF
  int v19; // [rsp+78h] [rbp-50h]
  struct IIS_CRYPTO_STORAGE *v20; // [rsp+80h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-40h] BYREF
  void *Src[7]; // [rsp+90h] [rbp-38h] BYREF

  Src[0] = 0;
  Size = 0;
  v20 = 0;
  pv = 0;
  v13 = ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData((struct IUnknown *)This);
  v14 = (volatile signed __int32 *)v13;
  Src[1] = v13;
  if ( v13 )
  {
    ClientReceiveCryptoStorage = ADM_SECURE_DATA::GetClientReceiveCryptoStorage(v13, &v20, (struct IUnknown *)This);
    if ( ClientReceiveCryptoStorage >= 0 )
    {
      ClientReceiveCryptoStorage = (unsigned int)NdrClientCall2(
                                                   &pStubDescriptor,
                                                   &byte_18000B470,
                                                   This,
                                                   hMDHandle,
                                                   pszMDPath,
                                                   dwMDAttributes,
                                                   dwMDUserType,
                                                   dwMDDataType,
                                                   pdwMDNumDataEntries,
                                                   pdwMDDataSetNumber,
                                                   dwMDBufferSize,
                                                   pdwMDRequiredBufferSize,
                                                   &pv).Pointer;
      if ( ClientReceiveCryptoStorage >= 0 )
      {
        ClientReceiveCryptoStorage = (*(__int64 (__fastcall **)(struct IIS_CRYPTO_STORAGE *, void **, size_t *, char *, LPVOID))(*(_QWORD *)v20 + 8LL))(
                                       v20,
                                       Src,
                                       &Size,
                                       (char *)&Size + 4,
                                       pv);
        if ( ClientReceiveCryptoStorage >= 0 )
        {
          if ( dwMDBufferSize < (unsigned int)Size )
          {
            *pdwMDRequiredBufferSize = Size;
            ClientReceiveCryptoStorage = -2147024774;
            v19 = -2147024774;
          }
          else
          {
            memcpy_0(pbMDBuffer, Src[0], (unsigned int)Size);
          }
        }
      }
    }
  }
  else
  {
    ClientReceiveCryptoStorage = -2146646010;
  }
  if ( v14 && _InterlockedExchangeAdd(v14 + 6, 0xFFFFFFFF) == 1 )
  {
    ADM_SECURE_DATA::~ADM_SECURE_DATA((ADM_SECURE_DATA *)v14);
    operator delete((void *)v14);
  }
  v16 = pv;
  if ( pv )
  {
    *(_BYTE *)pv = 88;
    CoTaskMemFree(v16);
  }
  return ClientReceiveCryptoStorage;
}

```

## disassembly

```asm
0x180002850  mov     rax, rsp
0x180002853  mov     [rax+8], rbx
0x180002857  mov     [rax+18h], r8
0x18000285b  mov     [rax+10h], edx
0x18000285e  push    rsi
0x18000285f  push    r12
0x180002861  push    r13
0x180002863  push    r14
0x180002865  push    r15
0x180002867  sub     rsp, 0A0h
0x18000286e  mov     r13d, r9d
0x180002871  mov     r14, rcx
0x180002874  mov     qword ptr [rax-38h], 0
0x18000287c  mov     dword ptr [rax-58h], 0
0x180002883  mov     dword ptr [rax-54h], 0
0x18000288a  mov     qword ptr [rax-48h], 0
0x180002892  mov     qword ptr [rax-40h], 0
0x18000289a  call    ?FindOrAddAndReferenceClientSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@@Z; ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData(IUnknown *)
0x18000289f  mov     rsi, rax
0x1800028a2  mov     [rsp+0C8h+var_30], rax
0x1800028aa  test    rax, rax
0x1800028ad  jnz     short loc_1800028B9
0x1800028af  mov     ebx, 800CC806h
0x1800028b4  jmp     loc_1800029E1
0x1800028b9  mov     r8, r14; struct IUnknown *
0x1800028bc  lea     rdx, [rsp+0C8h+var_48]; struct IIS_CRYPTO_STORAGE **
0x1800028c4  mov     rcx, rax; this
0x1800028c7  call    ?GetClientReceiveCryptoStorage@ADM_SECURE_DATA@@QEAAJPEAPEAVIIS_CRYPTO_STORAGE@@PEAUIUnknown@@@Z; ADM_SECURE_DATA::GetClientReceiveCryptoStorage(IIS_CRYPTO_STORAGE * *,IUnknown *)
0x1800028cc  mov     ebx, eax
0x1800028ce  test    eax, eax
0x1800028d0  js      loc_1800029E1
0x1800028d6  lea     rax, [rsp+0C8h+pv]
0x1800028de  mov     [rsp+0C8h+var_68], rax
0x1800028e3  mov     r15, [rsp+0C8h+pdwMDRequiredBufferSize]
0x1800028eb  mov     [rsp+0C8h+var_70], r15
0x1800028f0  mov     r12d, [rsp+0C8h+dwMDBufferSize]
0x1800028f8  mov     [rsp+0C8h+var_78], r12d
0x1800028fd  mov     rax, [rsp+0C8h+pdwMDDataSetNumber]
0x180002905  mov     [rsp+0C8h+var_80], rax
0x18000290a  mov     rax, [rsp+0C8h+pdwMDNumDataEntries]
0x180002912  mov     [rsp+0C8h+var_88], rax
0x180002917  mov     eax, [rsp+0C8h+dwMDDataType]
0x18000291e  mov     [rsp+0C8h+var_90], eax
0x180002922  mov     eax, [rsp+0C8h+dwMDUserType]
0x180002929  mov     [rsp+0C8h+var_98], eax
0x18000292d  mov     [rsp+0C8h+var_A0], r13d
0x180002932  mov     rax, [rsp+0C8h+arg_10]
0x18000293a  mov     [rsp+0C8h+var_A8], rax
0x18000293f  mov     r9d, [rsp+0C8h+arg_8]
0x180002947  mov     r8, r14
0x18000294a  lea     rdx, byte_18000B470; pFormat
0x180002951  lea     rcx, pStubDescriptor; pStubDescriptor
0x180002958  call    cs:__imp_NdrClientCall2
0x18000295e  mov     rbx, rax
0x180002961  test    eax, eax
0x180002963  js      short loc_1800029E1
0x180002965  mov     rcx, [rsp+0C8h+var_48]
0x18000296d  mov     rax, [rcx]
0x180002970  mov     rdx, [rsp+0C8h+pv]
0x180002978  mov     [rsp+0C8h+var_A8], rdx
0x18000297d  lea     r9, [rsp+0C8h+Size+4]
0x180002982  lea     r8, [rsp+0C8h+Size]
0x180002987  lea     rdx, [rsp+0C8h+Src]
0x18000298f  mov     rax, [rax+8]
0x180002993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002998  mov     ebx, eax
0x18000299a  test    eax, eax
0x18000299c  js      short loc_1800029E1
0x18000299e  mov     eax, dword ptr [rsp+0C8h+Size]
0x1800029a2  cmp     r12d, eax
0x1800029a5  jb      short loc_1800029C1
0x1800029a7  mov     r8d, eax; Size
0x1800029aa  mov     rdx, [rsp+0C8h+Src]; Src
0x1800029b2  mov     rcx, [rsp+0C8h+pbMDBuffer]; void *
0x1800029ba  call    memcpy_0
0x1800029bf  jmp     short loc_1800029CD
0x1800029c1  mov     [r15], eax
0x1800029c4  mov     ebx, 8007007Ah
0x1800029c9  mov     [rsp+0C8h+var_50], ebx
0x1800029cd  jmp     short loc_1800029E1
0x1800029cf  bts     eax, 1Ch
0x1800029d3  mov     ebx, eax
0x1800029d5  mov     [rsp+0C8h+var_50], eax
0x1800029d9  mov     rsi, [rsp+0C8h+var_30]
0x1800029e1  test    rsi, rsi
0x1800029e4  jz      short loc_180002A03
0x1800029e6  or      eax, 0FFFFFFFFh
0x1800029e9  lock xadd [rsi+18h], eax
0x1800029ee  cmp     eax, 1
0x1800029f1  jnz     short loc_180002A03
0x1800029f3  mov     rcx, rsi; this
0x1800029f6  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x1800029fb  mov     rcx, rsi; Block
0x1800029fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002a03  mov     rcx, [rsp+0C8h+pv]; pv
0x180002a0b  test    rcx, rcx
0x180002a0e  jz      short loc_180002A19
0x180002a10  mov     byte ptr [rcx], 58h ; 'X'
0x180002a13  call    cs:__imp_CoTaskMemFree
0x180002a19  mov     eax, ebx
0x180002a1b  mov     rbx, [rsp+0C8h+arg_0]
0x180002a23  add     rsp, 0A0h
0x180002a2a  pop     r15
0x180002a2c  pop     r14
0x180002a2e  pop     r13
0x180002a30  pop     r12
0x180002a32  pop     rsi
0x180002a33  retn
```
