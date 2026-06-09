# IMSAdminBaseW_EnumData_Proxy

- ea: `0x1800025f0`
- end: `0x18000283b`
- name: `IMSAdminBaseW_EnumData_Proxy`
- size: `587`
- prototype: `HRESULT __stdcall(IMSAdminBaseW *This, METADATA_HANDLE hMDHandle, LPCWSTR pszMDPath, PMETADATA_RECORD pmdrMDData, DWORD dwMDEnumDataIndex, DWORD *pdwMDRequiredDataLen)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task`

## callees

- `0x180001124`
- `0x1800025f0`
- `0x1800031f4`
- `0x180003f60`
- `0x18000413c`
- `0x1800083d2`
- `0x180009010`

## import_xrefs

- `RPCRT4!NdrClientCall2` at `0x18000273e`
- `RPCRT4!NdrClientCall2` at `0x18000273e`
- `ole32!CoTaskMemFree` at `0x180002820`
- `ole32!CoTaskMemFree` at `0x180002820`

## pseudocode

```c
HRESULT __stdcall IMSAdminBaseW_EnumData_Proxy(
        IMSAdminBaseW *This,
        METADATA_HANDLE hMDHandle,
        LPCWSTR pszMDPath,
        PMETADATA_RECORD pmdrMDData,
        DWORD dwMDEnumDataIndex,
        DWORD *pdwMDRequiredDataLen)
{
  volatile signed __int32 *v10; // rdi
  HRESULT ClientReceiveCryptoStorage; // ebx
  struct ADM_SECURE_DATA *v12; // rax
  void *v13; // rcx
  size_t Size; // [rsp+50h] [rbp-98h] BYREF
  int v16; // [rsp+58h] [rbp-90h]
  LPVOID pv; // [rsp+60h] [rbp-88h] BYREF
  struct IIS_CRYPTO_STORAGE *v18; // [rsp+68h] [rbp-80h] BYREF
  void *Src[2]; // [rsp+70h] [rbp-78h] BYREF
  __int128 v20; // [rsp+80h] [rbp-68h] BYREF
  __int128 v21; // [rsp+90h] [rbp-58h]
  __int64 v22; // [rsp+A0h] [rbp-48h]

  v20 = 0;
  v21 = 0;
  v22 = 0;
  Src[0] = 0;
  Size = 0;
  v18 = 0;
  pv = 0;
  if ( pmdrMDData )
  {
    v12 = ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData((struct IUnknown *)This);
    v10 = (volatile signed __int32 *)v12;
    Src[1] = v12;
    if ( v12 )
    {
      ClientReceiveCryptoStorage = ADM_SECURE_DATA::GetClientReceiveCryptoStorage(v12, &v18, (struct IUnknown *)This);
      if ( ClientReceiveCryptoStorage >= 0 )
      {
        v20 = *(_OWORD *)&pmdrMDData->dwMDIdentifier;
        v21 = *(_OWORD *)&pmdrMDData->dwMDDataLen;
        v22 = *(_QWORD *)&pmdrMDData->dwMDDataTag;
        *((_QWORD *)&v21 + 1) = 0;
        ClientReceiveCryptoStorage = (unsigned int)NdrClientCall2(
                                                     &pStubDescriptor,
                                                     &pFormat,
                                                     This,
                                                     hMDHandle,
                                                     pszMDPath,
                                                     &v20,
                                                     dwMDEnumDataIndex,
                                                     pdwMDRequiredDataLen,
                                                     &pv).Pointer;
        if ( ClientReceiveCryptoStorage >= 0 )
        {
          ClientReceiveCryptoStorage = (*(__int64 (__fastcall **)(struct IIS_CRYPTO_STORAGE *, void **, size_t *, char *, LPVOID))(*(_QWORD *)v18 + 8LL))(
                                         v18,
                                         Src,
                                         &Size,
                                         (char *)&Size + 4,
                                         pv);
          if ( ClientReceiveCryptoStorage >= 0 )
          {
            if ( pmdrMDData->dwMDDataLen < (unsigned int)Size )
            {
              *pdwMDRequiredDataLen = Size;
              ClientReceiveCryptoStorage = -2147024774;
              v16 = -2147024774;
            }
            else
            {
              memcpy_0(pmdrMDData->pbMDData, Src[0], (unsigned int)Size);
              pmdrMDData->dwMDDataLen = Size;
              *(_OWORD *)&pmdrMDData->dwMDIdentifier = v20;
              pmdrMDData->dwMDDataTag = v22;
            }
          }
        }
      }
    }
    else
    {
      ClientReceiveCryptoStorage = -2146646010;
    }
  }
  else
  {
    v10 = 0;
    ClientReceiveCryptoStorage = -2147024809;
  }
  if ( v10 && _InterlockedExchangeAdd(v10 + 6, 0xFFFFFFFF) == 1 )
  {
    ADM_SECURE_DATA::~ADM_SECURE_DATA((ADM_SECURE_DATA *)v10);
    operator delete((void *)v10);
  }
  v13 = pv;
  if ( pv )
  {
    *(_BYTE *)pv = 88;
    CoTaskMemFree(v13);
  }
  return ClientReceiveCryptoStorage;
}

```

## disassembly

```asm
0x1800025f0  mov     r11, rsp
0x1800025f3  mov     [r11+20h], r9
0x1800025f7  mov     [r11+18h], r8
0x1800025fb  mov     [rsp+arg_8], edx
0x1800025ff  mov     [r11+8], rcx
0x180002603  push    rbx
0x180002604  push    rsi
0x180002605  push    rdi
0x180002606  push    r12
0x180002608  push    r13
0x18000260a  push    r14
0x18000260c  push    r15
0x18000260e  sub     rsp, 0B0h
0x180002615  mov     rsi, r9
0x180002618  mov     r15, r8
0x18000261b  mov     r12d, edx
0x18000261e  mov     r14, rcx
0x180002621  xorps   xmm0, xmm0
0x180002624  xor     eax, eax
0x180002626  movups  xmmword ptr [r11-68h], xmm0
0x18000262b  movups  xmmword ptr [r11-58h], xmm0
0x180002630  mov     [r11-48h], rax
0x180002634  mov     [r11-78h], rax
0x180002638  mov     dword ptr [rsp+0E8h+Size], eax
0x18000263c  mov     dword ptr [rsp+0E8h+Size+4], eax
0x180002640  mov     [r11-80h], rax
0x180002644  mov     [rsp+0E8h+pv], rax
0x180002649  test    r9, r9
0x18000264c  jnz     short loc_18000265A
0x18000264e  xor     edi, edi
0x180002650  mov     ebx, 80070057h
0x180002655  jmp     loc_1800027F1
0x18000265a  call    ?FindOrAddAndReferenceClientSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@@Z; ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData(IUnknown *)
0x18000265f  mov     rdi, rax
0x180002662  mov     [rsp+0E8h+var_70], rax
0x180002667  test    rax, rax
0x18000266a  jnz     short loc_180002676
0x18000266c  mov     ebx, 800CC806h
0x180002671  jmp     loc_1800027F1
0x180002676  mov     r8, r14; struct IUnknown *
0x180002679  lea     rdx, [rsp+0E8h+var_80]; struct IIS_CRYPTO_STORAGE **
0x18000267e  mov     rcx, rax; this
0x180002681  call    ?GetClientReceiveCryptoStorage@ADM_SECURE_DATA@@QEAAJPEAPEAVIIS_CRYPTO_STORAGE@@PEAUIUnknown@@@Z; ADM_SECURE_DATA::GetClientReceiveCryptoStorage(IIS_CRYPTO_STORAGE * *,IUnknown *)
0x180002686  mov     ebx, eax
0x180002688  test    eax, eax
0x18000268a  js      loc_1800027F1
0x180002690  movups  xmm0, xmmword ptr [rsi]
0x180002693  movups  [rsp+0E8h+var_68], xmm0
0x18000269b  movups  xmm1, xmmword ptr [rsi+10h]
0x18000269f  movups  [rsp+0E8h+var_58], xmm1
0x1800026a7  movsd   xmm0, qword ptr [rsi+20h]
0x1800026ac  movsd   [rsp+0E8h+var_48], xmm0
0x1800026b5  jmp     short loc_1800026E2
0x1800026b7  mov     ebx, eax
0x1800026b9  bts     ebx, 1Ch
0x1800026bd  mov     rsi, [rsp+0E8h+arg_18]
0x1800026c5  mov     r15, [rsp+0E8h+arg_10]
0x1800026cd  mov     r12d, [rsp+0E8h+arg_8]
0x1800026d5  mov     r14, [rsp+0E8h+arg_0]
0x1800026dd  mov     rdi, [rsp+0E8h+var_70]
0x1800026e2  test    ebx, ebx
0x1800026e4  js      loc_1800027F1
0x1800026ea  mov     qword ptr [rsp+0E8h+var_58+8], 0
0x1800026f6  lea     rax, [rsp+0E8h+pv]
0x1800026fb  mov     [rsp+0E8h+var_A8], rax
0x180002700  mov     r13, [rsp+0E8h+pdwMDRequiredDataLen]
0x180002708  mov     [rsp+0E8h+var_B0], r13
0x18000270d  mov     eax, [rsp+0E8h+dwMDEnumDataIndex]
0x180002714  mov     [rsp+0E8h+var_B8], eax
0x180002718  lea     rax, [rsp+0E8h+var_68]
0x180002720  mov     [rsp+0E8h+var_C0], rax
0x180002725  mov     [rsp+0E8h+var_C8], r15
0x18000272a  mov     r9d, r12d
0x18000272d  mov     r8, r14
0x180002730  lea     rdx, pFormat; pFormat
0x180002737  lea     rcx, pStubDescriptor; pStubDescriptor
0x18000273e  call    cs:__imp_NdrClientCall2
0x180002744  mov     rbx, rax
0x180002747  test    eax, eax
0x180002749  js      loc_1800027F1
0x18000274f  mov     rcx, [rsp+0E8h+var_80]
0x180002754  mov     rax, [rcx]
0x180002757  mov     rdx, [rsp+0E8h+pv]
0x18000275c  mov     [rsp+0E8h+var_C8], rdx
0x180002761  lea     r9, [rsp+0E8h+Size+4]
0x180002766  lea     r8, [rsp+0E8h+Size]
0x18000276b  lea     rdx, [rsp+0E8h+Src]
0x180002770  mov     rax, [rax+8]
0x180002774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002779  mov     ebx, eax
0x18000277b  test    eax, eax
0x18000277d  js      short loc_1800027F1
0x18000277f  mov     eax, dword ptr [rsp+0E8h+Size]
0x180002783  cmp     [rsi+10h], eax
0x180002786  jb      short loc_1800027D3
0x180002788  mov     r8d, eax; Size
0x18000278b  mov     rdx, [rsp+0E8h+Src]; Src
0x180002790  mov     rcx, [rsi+18h]; void *
0x180002794  call    memcpy_0
0x180002799  mov     eax, dword ptr [rsp+0E8h+Size]
0x18000279d  mov     [rsi+10h], eax
0x1800027a0  mov     eax, dword ptr [rsp+0E8h+var_68]
0x1800027a7  mov     [rsi], eax
0x1800027a9  mov     eax, dword ptr [rsp+0E8h+var_68+4]
0x1800027b0  mov     [rsi+4], eax
0x1800027b3  mov     eax, dword ptr [rsp+0E8h+var_68+8]
0x1800027ba  mov     [rsi+8], eax
0x1800027bd  mov     eax, dword ptr [rsp+0E8h+var_68+0Ch]
0x1800027c4  mov     [rsi+0Ch], eax
0x1800027c7  mov     eax, dword ptr [rsp+0E8h+var_48]
0x1800027ce  mov     [rsi+20h], eax
0x1800027d1  jmp     short loc_1800027E0
0x1800027d3  mov     [r13+0], eax
0x1800027d7  mov     ebx, 8007007Ah
0x1800027dc  mov     [rsp+0E8h+var_90], ebx
0x1800027e0  jmp     short loc_1800027F1
0x1800027e2  bts     eax, 1Ch
0x1800027e6  mov     ebx, eax
0x1800027e8  mov     [rsp+0E8h+var_90], eax
0x1800027ec  mov     rdi, [rsp+0E8h+var_70]
0x1800027f1  test    rdi, rdi
0x1800027f4  jz      short loc_180002813
0x1800027f6  or      eax, 0FFFFFFFFh
0x1800027f9  lock xadd [rdi+18h], eax
0x1800027fe  cmp     eax, 1
0x180002801  jnz     short loc_180002813
0x180002803  mov     rcx, rdi; this
0x180002806  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x18000280b  mov     rcx, rdi; Block
0x18000280e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002813  mov     rcx, [rsp+0E8h+pv]; pv
0x180002818  test    rcx, rcx
0x18000281b  jz      short loc_180002826
0x18000281d  mov     byte ptr [rcx], 58h ; 'X'
0x180002820  call    cs:__imp_CoTaskMemFree
0x180002826  mov     eax, ebx
0x180002828  add     rsp, 0B0h
0x18000282f  pop     r15
0x180002831  pop     r14
0x180002833  pop     r13
0x180002835  pop     r12
0x180002837  pop     rdi
0x180002838  pop     rsi
0x180002839  pop     rbx
0x18000283a  retn
```
