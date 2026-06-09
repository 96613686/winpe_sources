# CryptoHelper::HmacWithSessionKey(AadContextFunctions *,_AadApPluginKeyInfo *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,bool,_AP_BLOB *,_AP_BLOB *)

- ea: `0x18007f32c`
- end: `0x18007f659`
- name: `?HmacWithSessionKey@CryptoHelper@@SAJPEAVAadContextFunctions@@PEAU_AadApPluginKeyInfo@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@_N33@Z`
- size: `813`
- prototype: `__int64 __usercall@<rax>(AadContextFunctions *this@<rcx>, int, BCRYPT_ALG_HANDLE phAlgorithm)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180063980`

## callees

- `0x180007a90`
- `0x1800256d0`
- `0x180071e14`
- `0x180076f14`
- `0x180078b18`
- `0x18007f32c`
- `0x1800a8010`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18007f608`
- `bcrypt!BCryptDestroyHash` at `0x18007f608`
- `bcrypt!BCryptFinishHash` at `0x18007f56d`
- `bcrypt!BCryptFinishHash` at `0x18007f56d`
- `bcrypt!BCryptHashData` at `0x18007f4d3`
- `bcrypt!BCryptHashData` at `0x18007f4d3`
- `bcrypt!BCryptCreateHash` at `0x18007f493`
- `bcrypt!BCryptCreateHash` at `0x18007f493`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007f619`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007f619`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007f43b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007f43b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CryptoHelper::HmacWithSessionKey(
        AadContextFunctions *this,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        int a5,
        BCRYPT_ALG_HANDLE phAlgorithm)
{
  _QWORD *v9; // r9
  __int64 v10; // r10
  int v11; // ebx
  int v12; // ebx
  UCHAR *v13; // r14
  PUCHAR pbSecret; // [rsp+20h] [rbp-61h]
  __int64 dwFlags; // [rsp+30h] [rbp-51h]
  PUCHAR pbInput[2]; // [rsp+50h] [rbp-31h] BYREF
  __int128 v18; // [rsp+60h] [rbp-21h] BYREF
  UCHAR *v19; // [rsp+70h] [rbp-11h] BYREF
  __int64 v20; // [rsp+78h] [rbp-9h]
  AadContextFunctions *v21; // [rsp+80h] [rbp-1h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+D0h] [rbp+4Fh] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_OWORD *)pbInput = 0;
  v18 = 0;
  v19 = 0;
  v21 = this;
  v20 = 0;
  if ( this && a4 && a2 && IsApBlobDefined((struct _AP_BLOB *)(a2 + 24)) )
  {
    *v9 = 0;
    v9[1] = 0;
    v11 = StringUtility::EncodeString(this, v10, pbInput, 65001, 1);
    if ( v11 < 0 )
    {
      LODWORD(pbSecret) = v11;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, pbSecret, "crypto.cpp", 478, "HRESULT", &base);
      v12 = v11 & 0xAFFFFFFF | 0x40000000;
      goto LABEL_20;
    }
    v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 8u);
    if ( v12 >= 0 )
    {
      v12 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, *(PUCHAR *)(a2 + 32), *(_DWORD *)(a2 + 24), 0);
      if ( v12 >= 0 )
      {
        v12 = BCryptHashData(phHash, pbInput[1], (ULONG)pbInput[0], 0);
        if ( v12 >= 0 )
        {
          v13 = (UCHAR *)(*(__int64 (__fastcall **)(AadContextFunctions *, __int64, __int64))(*(_QWORD *)this + 8LL))(
                           this,
                           64,
                           32);
          Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v19);
          v19 = v13;
          v20 = 32;
          if ( v13 )
          {
            v12 = BCryptFinishHash(phHash, v13, 0x20u, 0);
            if ( v12 >= 0 )
            {
              *a4 = 32;
              a4[1] = v13;
              v19 = 0;
              v20 = 0;
              goto LABEL_20;
            }
            LODWORD(dwFlags) = 504;
          }
          else
          {
            v12 = -1073741801;
            LODWORD(dwFlags) = 501;
          }
        }
        else
        {
          LODWORD(dwFlags) = 496;
        }
      }
      else
      {
        LODWORD(dwFlags) = 493;
      }
    }
    else
    {
      LODWORD(dwFlags) = 480;
    }
  }
  else
  {
    v12 = -1073741811;
    LODWORD(dwFlags) = 473;
  }
  LODWORD(pbSecret) = v12;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, pbSecret, "crypto.cpp", dwFlags, "NTSTATUS", &base);
LABEL_20:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( this )
  {
    AadContextFunctions::LocalFreeApBlob(this, (struct _AP_BLOB *)pbInput);
    AadContextFunctions::LocalFreeApBlob(this, (struct _AP_BLOB *)&v18);
  }
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v19);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18007f32c  push    rbp
0x18007f32e  push    rbx
0x18007f32f  push    rsi
0x18007f330  push    rdi
0x18007f331  push    r14
0x18007f333  push    r15
0x18007f335  lea     rbp, [rsp-17h]
0x18007f33a  sub     rsp, 98h
0x18007f341  mov     rsi, r9
0x18007f344  mov     r10, r8
0x18007f347  mov     r14, rdx
0x18007f34a  mov     rdi, rcx
0x18007f34d  mov     [rbp+3Fh+phAlgorithm], 0
0x18007f355  mov     [rbp+3Fh+phHash], 0
0x18007f35d  xorps   xmm0, xmm0
0x18007f360  movups  xmmword ptr [rbp+3Fh+pbInput], xmm0
0x18007f364  xorps   xmm1, xmm1
0x18007f367  movups  [rbp+3Fh+var_60], xmm1
0x18007f36b  mov     [rbp+3Fh+var_50], 0
0x18007f373  mov     [rbp+3Fh+var_40], rcx
0x18007f377  mov     [rbp+3Fh+var_48], 0
0x18007f37f  test    rcx, rcx
0x18007f382  jz      loc_18007F5B4
0x18007f388  test    r9, r9
0x18007f38b  jz      loc_18007F5B4
0x18007f391  test    rdx, rdx
0x18007f394  jz      loc_18007F5B4
0x18007f39a  lea     rcx, [rdx+18h]; struct _AP_BLOB *
0x18007f39e  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x18007f3a3  test    al, al
0x18007f3a5  jz      loc_18007F5B4
0x18007f3ab  xor     eax, eax
0x18007f3ad  mov     [r9], rax
0x18007f3b0  mov     [r9+8], rax
0x18007f3b4  mov     byte ptr [rsp+0C0h+pbSecret], 1
0x18007f3b9  mov     r9d, 0FDE9h
0x18007f3bf  lea     r8, [rbp+3Fh+pbInput]
0x18007f3c3  mov     rdx, r10
0x18007f3c6  mov     rcx, rdi
0x18007f3c9  call    ?EncodeString@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@I_N@Z; StringUtility::EncodeString(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,uint,bool)
0x18007f3ce  mov     ebx, eax
0x18007f3d0  test    eax, eax
0x18007f3d2  jns     short loc_18007F427
0x18007f3d4  lea     rax, base
0x18007f3db  mov     [rsp+0C0h+var_80], rax
0x18007f3e0  lea     rax, aHresult; "HRESULT"
0x18007f3e7  mov     [rsp+0C0h+var_88], rax
0x18007f3ec  mov     dword ptr [rsp+0C0h+dwFlags], 1DEh
0x18007f3f4  lea     rax, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007f3fb  mov     qword ptr [rsp+0C0h+cbSecret], rax
0x18007f400  mov     dword ptr [rsp+0C0h+pbSecret], ebx
0x18007f404  mov     ecx, 2
0x18007f409  mov     r9d, ecx
0x18007f40c  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007f413  xor     edx, edx
0x18007f415  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007f41a  btr     ebx, 1Ch
0x18007f41e  bts     ebx, 1Eh
0x18007f422  jmp     loc_18007F5FF
0x18007f427  mov     r9d, 8; dwFlags
0x18007f42d  xor     r8d, r8d; pszImplementation
0x18007f430  lea     rdx, aSha256; "SHA256"
0x18007f437  lea     rcx, [rbp+3Fh+phAlgorithm]; phAlgorithm
0x18007f43b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18007f441  mov     ebx, eax
0x18007f443  test    eax, eax
0x18007f445  jns     short loc_18007F46C
0x18007f447  lea     rax, base
0x18007f44e  mov     [rsp+0C0h+var_80], rax
0x18007f453  lea     rax, aNtstatus; "NTSTATUS"
0x18007f45a  mov     [rsp+0C0h+var_88], rax
0x18007f45f  mov     dword ptr [rsp+0C0h+dwFlags], 1E0h
0x18007f467  jmp     loc_18007F5D9
0x18007f46c  mov     dword ptr [rsp+0C0h+dwFlags], 0; dwFlags
0x18007f474  mov     eax, [r14+18h]
0x18007f478  mov     [rsp+0C0h+cbSecret], eax; cbSecret
0x18007f47c  mov     rax, [r14+20h]
0x18007f480  mov     [rsp+0C0h+pbSecret], rax; pbSecret
0x18007f485  xor     r9d, r9d; cbHashObject
0x18007f488  xor     r8d, r8d; pbHashObject
0x18007f48b  lea     rdx, [rbp+3Fh+phHash]; phHash
0x18007f48f  mov     rcx, [rbp+3Fh+phAlgorithm]; hAlgorithm
0x18007f493  call    cs:__imp_BCryptCreateHash
0x18007f499  mov     ebx, eax
0x18007f49b  test    eax, eax
0x18007f49d  jns     short loc_18007F4C4
0x18007f49f  lea     rax, base
0x18007f4a6  mov     [rsp+0C0h+var_80], rax
0x18007f4ab  lea     rax, aNtstatus; "NTSTATUS"
0x18007f4b2  mov     [rsp+0C0h+var_88], rax
0x18007f4b7  mov     dword ptr [rsp+0C0h+dwFlags], 1EDh
0x18007f4bf  jmp     loc_18007F5D9
0x18007f4c4  xor     r9d, r9d; dwFlags
0x18007f4c7  mov     r8d, dword ptr [rbp+3Fh+pbInput]; cbInput
0x18007f4cb  mov     rdx, [rbp+3Fh+pbInput+8]; pbInput
0x18007f4cf  mov     rcx, [rbp+3Fh+phHash]; hHash
0x18007f4d3  call    cs:__imp_BCryptHashData
0x18007f4d9  mov     ebx, eax
0x18007f4db  test    eax, eax
0x18007f4dd  jns     short loc_18007F504
0x18007f4df  lea     rax, base
0x18007f4e6  mov     [rsp+0C0h+var_80], rax
0x18007f4eb  lea     rax, aNtstatus; "NTSTATUS"
0x18007f4f2  mov     [rsp+0C0h+var_88], rax
0x18007f4f7  mov     dword ptr [rsp+0C0h+dwFlags], 1F0h
0x18007f4ff  jmp     loc_18007F5D9
0x18007f504  mov     rax, [rdi]
0x18007f507  mov     r15d, 20h ; ' '
0x18007f50d  mov     r8d, r15d
0x18007f510  lea     edx, [r15+20h]
0x18007f514  mov     rcx, rdi
0x18007f517  mov     rax, [rax+8]
0x18007f51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f520  mov     r14, rax
0x18007f523  lea     rcx, [rbp+3Fh+var_50]
0x18007f527  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007f52c  mov     [rbp+3Fh+var_50], r14
0x18007f530  mov     [rbp+3Fh+var_48], r15
0x18007f534  test    r14, r14
0x18007f537  jnz     short loc_18007F560
0x18007f539  mov     ebx, 0C0000017h
0x18007f53e  lea     rax, base
0x18007f545  mov     [rsp+0C0h+var_80], rax
0x18007f54a  lea     rax, aNtstatus; "NTSTATUS"
0x18007f551  mov     [rsp+0C0h+var_88], rax
0x18007f556  mov     dword ptr [rsp+0C0h+dwFlags], 1F5h
0x18007f55e  jmp     short loc_18007F5D9
0x18007f560  xor     r9d, r9d; dwFlags
0x18007f563  mov     r8d, r15d; cbOutput
0x18007f566  mov     rdx, r14; pbOutput
0x18007f569  mov     rcx, [rbp+3Fh+phHash]; hHash
0x18007f56d  call    cs:__imp_BCryptFinishHash
0x18007f573  mov     ebx, eax
0x18007f575  test    eax, eax
0x18007f577  jns     short loc_18007F59B
0x18007f579  lea     rax, base
0x18007f580  mov     [rsp+0C0h+var_80], rax
0x18007f585  lea     rax, aNtstatus; "NTSTATUS"
0x18007f58c  mov     [rsp+0C0h+var_88], rax
0x18007f591  mov     dword ptr [rsp+0C0h+dwFlags], 1F8h
0x18007f599  jmp     short loc_18007F5D9
0x18007f59b  mov     [rsi], r15
0x18007f59e  mov     [rsi+8], r14
0x18007f5a2  mov     [rbp+3Fh+var_50], 0
0x18007f5aa  mov     [rbp+3Fh+var_48], 0
0x18007f5b2  jmp     short loc_18007F5FF
0x18007f5b4  mov     ebx, 0C000000Dh
0x18007f5b9  lea     rax, base
0x18007f5c0  mov     [rsp+0C0h+var_80], rax
0x18007f5c5  lea     rax, aNtstatus; "NTSTATUS"
0x18007f5cc  mov     [rsp+0C0h+var_88], rax
0x18007f5d1  mov     dword ptr [rsp+0C0h+dwFlags], 1D9h
0x18007f5d9  lea     rax, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007f5e0  mov     qword ptr [rsp+0C0h+cbSecret], rax
0x18007f5e5  mov     ecx, 2
0x18007f5ea  mov     dword ptr [rsp+0C0h+pbSecret], ebx
0x18007f5ee  mov     r9d, ecx
0x18007f5f1  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007f5f8  xor     edx, edx
0x18007f5fa  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007f5ff  mov     rcx, [rbp+3Fh+phHash]; hHash
0x18007f603  test    rcx, rcx
0x18007f606  jz      short loc_18007F60E
0x18007f608  call    cs:__imp_BCryptDestroyHash
0x18007f60e  mov     rcx, [rbp+3Fh+phAlgorithm]; hAlgorithm
0x18007f612  test    rcx, rcx
0x18007f615  jz      short loc_18007F61F
0x18007f617  xor     edx, edx; dwFlags
0x18007f619  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18007f61f  test    rdi, rdi
0x18007f622  jz      short loc_18007F63D
0x18007f624  lea     rdx, [rbp+3Fh+pbInput]; struct _AP_BLOB *
0x18007f628  mov     rcx, rdi; this
0x18007f62b  call    ?LocalFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LocalFreeApBlob(_AP_BLOB *)
0x18007f630  lea     rdx, [rbp+3Fh+var_60]; struct _AP_BLOB *
0x18007f634  mov     rcx, rdi; this
0x18007f637  call    ?LocalFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LocalFreeApBlob(_AP_BLOB *)
0x18007f63c  nop
0x18007f63d  lea     rcx, [rbp+3Fh+var_50]
0x18007f641  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007f646  nop
0x18007f647  mov     eax, ebx
0x18007f649  add     rsp, 98h
0x18007f650  pop     r15
0x18007f652  pop     r14
0x18007f654  pop     rdi
0x18007f655  pop     rsi
0x18007f656  pop     rbx
0x18007f657  pop     rbp
0x18007f658  retn
```
