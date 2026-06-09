# IMSAdminBaseW_GetData_Proxy

- ea: `0x180002c40`
- end: `0x180002e6e`
- name: `IMSAdminBaseW_GetData_Proxy`
- size: `558`
- prototype: `HRESULT __stdcall(IMSAdminBaseW *This, METADATA_HANDLE hMDHandle, LPCWSTR pszMDPath, PMETADATA_RECORD pmdrMDData, DWORD *pdwMDRequiredDataLen)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task`

## callees

- `0x180001124`
- `0x180002c40`
- `0x1800031f4`
- `0x180003f60`
- `0x18000413c`
- `0x1800083d2`
- `0x180009010`

## import_xrefs

- `RPCRT4!NdrClientCall2` at `0x180002d7d`
- `RPCRT4!NdrClientCall2` at `0x180002d7d`
- `ole32!CoTaskMemFree` at `0x180002e53`
- `ole32!CoTaskMemFree` at `0x180002e53`

## pseudocode

```c
HRESULT __stdcall IMSAdminBaseW_GetData_Proxy(
        IMSAdminBaseW *This,
        METADATA_HANDLE hMDHandle,
        LPCWSTR pszMDPath,
        PMETADATA_RECORD pmdrMDData,
        DWORD *pdwMDRequiredDataLen)
{
  volatile signed __int32 *v9; // rdi
  HRESULT ClientReceiveCryptoStorage; // ebx
  struct ADM_SECURE_DATA *v11; // rax
  void *v12; // rcx
  size_t Size; // [rsp+40h] [rbp-98h] BYREF
  int v15; // [rsp+48h] [rbp-90h]
  LPVOID pv; // [rsp+50h] [rbp-88h] BYREF
  struct IIS_CRYPTO_STORAGE *v17; // [rsp+58h] [rbp-80h] BYREF
  void *Src[2]; // [rsp+60h] [rbp-78h] BYREF
  __int128 v19; // [rsp+70h] [rbp-68h] BYREF
  __int128 v20; // [rsp+80h] [rbp-58h]
  __int64 v21; // [rsp+90h] [rbp-48h]

  v19 = 0;
  v20 = 0;
  v21 = 0;
  Src[0] = 0;
  Size = 0;
  v17 = 0;
  pv = 0;
  if ( pmdrMDData )
  {
    v11 = ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData((struct IUnknown *)This);
    v9 = (volatile signed __int32 *)v11;
    Src[1] = v11;
    if ( v11 )
    {
      ClientReceiveCryptoStorage = ADM_SECURE_DATA::GetClientReceiveCryptoStorage(v11, &v17, (struct IUnknown *)This);
      if ( ClientReceiveCryptoStorage >= 0 )
      {
        v19 = *(_OWORD *)&pmdrMDData->dwMDIdentifier;
        v20 = *(_OWORD *)&pmdrMDData->dwMDDataLen;
        v21 = *(_QWORD *)&pmdrMDData->dwMDDataTag;
        *((_QWORD *)&v20 + 1) = 0;
        ClientReceiveCryptoStorage = (unsigned int)NdrClientCall2(
                                                     &pStubDescriptor,
                                                     &byte_18000B3B6,
                                                     This,
                                                     hMDHandle,
                                                     pszMDPath,
                                                     &v19,
                                                     pdwMDRequiredDataLen,
                                                     &pv).Pointer;
        if ( ClientReceiveCryptoStorage >= 0 )
        {
          ClientReceiveCryptoStorage = (*(__int64 (__fastcall **)(struct IIS_CRYPTO_STORAGE *, void **, size_t *, char *, LPVOID))(*(_QWORD *)v17 + 8LL))(
                                         v17,
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
              v15 = -2147024774;
            }
            else
            {
              memcpy_0(pmdrMDData->pbMDData, Src[0], (unsigned int)Size);
              pmdrMDData->dwMDDataLen = Size;
              *(_OWORD *)&pmdrMDData->dwMDIdentifier = v19;
              pmdrMDData->dwMDDataTag = v21;
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
    v9 = 0;
    ClientReceiveCryptoStorage = -2147024809;
  }
  if ( v9 && _InterlockedExchangeAdd(v9 + 6, 0xFFFFFFFF) == 1 )
  {
    ADM_SECURE_DATA::~ADM_SECURE_DATA((ADM_SECURE_DATA *)v9);
    operator delete((void *)v9);
  }
  v12 = pv;
  if ( pv )
  {
    *(_BYTE *)pv = 88;
    CoTaskMemFree(v12);
  }
  return ClientReceiveCryptoStorage;
}

```

## disassembly

```asm
0x180002c40  mov     r11, rsp
0x180002c43  mov     [r11+20h], r9
0x180002c47  mov     [r11+18h], r8
0x180002c4b  mov     [rsp+arg_8], edx
0x180002c4f  mov     [r11+8], rcx
0x180002c53  push    rbx
0x180002c54  push    rsi
0x180002c55  push    rdi
0x180002c56  push    r12
0x180002c58  push    r13
0x180002c5a  push    r14
0x180002c5c  push    r15
0x180002c5e  sub     rsp, 0A0h
0x180002c65  mov     rsi, r9
0x180002c68  mov     r15, r8
0x180002c6b  mov     r12d, edx
0x180002c6e  mov     r14, rcx
0x180002c71  xorps   xmm0, xmm0
0x180002c74  xor     eax, eax
0x180002c76  movups  [rsp+0D8h+var_68], xmm0
0x180002c7b  movups  xmmword ptr [r11-58h], xmm0
0x180002c80  mov     [r11-48h], rax
0x180002c84  mov     [r11-78h], rax
0x180002c88  mov     dword ptr [rsp+0D8h+Size], eax
0x180002c8c  mov     dword ptr [rsp+0D8h+Size+4], eax
0x180002c90  mov     [r11-80h], rax
0x180002c94  mov     [rsp+0D8h+pv], rax
0x180002c99  test    r9, r9
0x180002c9c  jnz     short loc_180002CAA
0x180002c9e  xor     edi, edi
0x180002ca0  mov     ebx, 80070057h
0x180002ca5  jmp     loc_180002E24
0x180002caa  call    ?FindOrAddAndReferenceClientSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@@Z; ADM_SECURE_DATA::FindOrAddAndReferenceClientSecureData(IUnknown *)
0x180002caf  mov     rdi, rax
0x180002cb2  mov     [rsp+0D8h+var_70], rax
0x180002cb7  test    rax, rax
0x180002cba  jnz     short loc_180002CC6
0x180002cbc  mov     ebx, 800CC806h
0x180002cc1  jmp     loc_180002E24
0x180002cc6  mov     r8, r14; struct IUnknown *
0x180002cc9  lea     rdx, [rsp+0D8h+var_80]; struct IIS_CRYPTO_STORAGE **
0x180002cce  mov     rcx, rax; this
0x180002cd1  call    ?GetClientReceiveCryptoStorage@ADM_SECURE_DATA@@QEAAJPEAPEAVIIS_CRYPTO_STORAGE@@PEAUIUnknown@@@Z; ADM_SECURE_DATA::GetClientReceiveCryptoStorage(IIS_CRYPTO_STORAGE * *,IUnknown *)
0x180002cd6  mov     ebx, eax
0x180002cd8  test    eax, eax
0x180002cda  js      loc_180002E24
0x180002ce0  movups  xmm0, xmmword ptr [rsi]
0x180002ce3  movups  [rsp+0D8h+var_68], xmm0
0x180002ce8  movups  xmm1, xmmword ptr [rsi+10h]
0x180002cec  movups  [rsp+0D8h+var_58], xmm1
0x180002cf4  movsd   xmm0, qword ptr [rsi+20h]
0x180002cf9  movsd   [rsp+0D8h+var_48], xmm0
0x180002d02  jmp     short loc_180002D2F
0x180002d04  mov     ebx, eax
0x180002d06  bts     ebx, 1Ch
0x180002d0a  mov     rsi, [rsp+0D8h+arg_18]
0x180002d12  mov     r15, [rsp+0D8h+arg_10]
0x180002d1a  mov     r12d, [rsp+0D8h+arg_8]
0x180002d22  mov     r14, [rsp+0D8h+arg_0]
0x180002d2a  mov     rdi, [rsp+0D8h+var_70]
0x180002d2f  test    ebx, ebx
0x180002d31  js      loc_180002E24
0x180002d37  mov     qword ptr [rsp+0D8h+var_58+8], 0
0x180002d43  lea     rax, [rsp+0D8h+pv]
0x180002d48  mov     [rsp+0D8h+var_A0], rax
0x180002d4d  mov     r13, [rsp+0D8h+pdwMDRequiredDataLen]
0x180002d55  mov     [rsp+0D8h+var_A8], r13
0x180002d5a  lea     rax, [rsp+0D8h+var_68]
0x180002d5f  mov     [rsp+0D8h+var_B0], rax
0x180002d64  mov     [rsp+0D8h+var_B8], r15
0x180002d69  mov     r9d, r12d
0x180002d6c  mov     r8, r14
0x180002d6f  lea     rdx, byte_18000B3B6; pFormat
0x180002d76  lea     rcx, pStubDescriptor; pStubDescriptor
0x180002d7d  call    cs:__imp_NdrClientCall2
0x180002d83  mov     rbx, rax
0x180002d86  test    eax, eax
0x180002d88  js      loc_180002E24
0x180002d8e  mov     rcx, [rsp+0D8h+var_80]
0x180002d93  mov     rax, [rcx]
0x180002d96  mov     rdx, [rsp+0D8h+pv]
0x180002d9b  mov     [rsp+0D8h+var_B8], rdx
0x180002da0  lea     r9, [rsp+0D8h+Size+4]
0x180002da5  lea     r8, [rsp+0D8h+Size]
0x180002daa  lea     rdx, [rsp+0D8h+Src]
0x180002daf  mov     rax, [rax+8]
0x180002db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002db8  mov     ebx, eax
0x180002dba  test    eax, eax
0x180002dbc  js      short loc_180002E24
0x180002dbe  mov     eax, dword ptr [rsp+0D8h+Size]
0x180002dc2  cmp     [rsi+10h], eax
0x180002dc5  jb      short loc_180002E06
0x180002dc7  mov     r8d, eax; Size
0x180002dca  mov     rdx, [rsp+0D8h+Src]; Src
0x180002dcf  mov     rcx, [rsi+18h]; void *
0x180002dd3  call    memcpy_0
0x180002dd8  mov     eax, dword ptr [rsp+0D8h+Size]
0x180002ddc  mov     [rsi+10h], eax
0x180002ddf  mov     eax, dword ptr [rsp+0D8h+var_68]
0x180002de3  mov     [rsi], eax
0x180002de5  mov     eax, dword ptr [rsp+0D8h+var_68+4]
0x180002de9  mov     [rsi+4], eax
0x180002dec  mov     eax, dword ptr [rsp+0D8h+var_68+8]
0x180002df0  mov     [rsi+8], eax
0x180002df3  mov     eax, dword ptr [rsp+0D8h+var_68+0Ch]
0x180002df7  mov     [rsi+0Ch], eax
0x180002dfa  mov     eax, dword ptr [rsp+0D8h+var_48]
0x180002e01  mov     [rsi+20h], eax
0x180002e04  jmp     short loc_180002E13
0x180002e06  mov     [r13+0], eax
0x180002e0a  mov     ebx, 8007007Ah
0x180002e0f  mov     [rsp+0D8h+var_90], ebx
0x180002e13  jmp     short loc_180002E24
0x180002e15  bts     eax, 1Ch
0x180002e19  mov     ebx, eax
0x180002e1b  mov     [rsp+0D8h+var_90], eax
0x180002e1f  mov     rdi, [rsp+0D8h+var_70]
0x180002e24  test    rdi, rdi
0x180002e27  jz      short loc_180002E46
0x180002e29  or      eax, 0FFFFFFFFh
0x180002e2c  lock xadd [rdi+18h], eax
0x180002e31  cmp     eax, 1
0x180002e34  jnz     short loc_180002E46
0x180002e36  mov     rcx, rdi; this
0x180002e39  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x180002e3e  mov     rcx, rdi; Block
0x180002e41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002e46  mov     rcx, [rsp+0D8h+pv]; pv
0x180002e4b  test    rcx, rcx
0x180002e4e  jz      short loc_180002E59
0x180002e50  mov     byte ptr [rcx], 58h ; 'X'
0x180002e53  call    cs:__imp_CoTaskMemFree
0x180002e59  mov     eax, ebx
0x180002e5b  add     rsp, 0A0h
0x180002e62  pop     r15
0x180002e64  pop     r14
0x180002e66  pop     r13
0x180002e68  pop     r12
0x180002e6a  pop     rdi
0x180002e6b  pop     rsi
0x180002e6c  pop     rbx
0x180002e6d  retn
```
