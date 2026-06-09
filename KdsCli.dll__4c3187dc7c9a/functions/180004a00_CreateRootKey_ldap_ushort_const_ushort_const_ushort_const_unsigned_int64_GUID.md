# CreateRootKey(ldap *,ushort const *,ushort const *,ushort const *,unsigned __int64,_GUID *)

- ea: `0x180004a00`
- end: `0x180004d56`
- name: `?CreateRootKey@@YAJPEAUldap@@PEBG11_KPEAU_GUID@@@Z`
- size: `854`
- prototype: `__int64 __usercall@<rax>(LDAP *ld@<rcx>, PWSTR base@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int64, struct _GUID *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x180002888`
- `0x180004a00`
- `0x180004f9c`
- `0x180005284`
- `0x180005934`
- `0x180006cb8`
- `0x180006d10`
- `0x180006d90`
- `0x180007060`
- `0x18000fd6c`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004d17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004d17`
- `bcrypt!BCryptGenRandom` at `0x180004b21`
- `bcrypt!BCryptGenRandom` at `0x180004b21`
- `RPCRT4!UuidFromStringW` at `0x180004c5e`
- `RPCRT4!UuidFromStringW` at `0x180004c5e`
- `RPCRT4!RpcStringFreeW` at `0x180004cf9`
- `RPCRT4!RpcStringFreeW` at `0x180004cf9`

## string_xrefs

- `0x180004b9b`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180004c3f`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`

## pseudocode

```c
__int64 __fastcall CreateRootKey(
        LDAP *ld,
        PWSTR base,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int64 a5,
        struct _GUID *Uuid)
{
  struct _SIDKEY_AD_ATTRIBUTE *v9; // r14
  int ServerConfig; // eax
  struct _KDS_CONFIGURATION *v12; // rdi
  signed int RootKeyDN; // ebx
  unsigned int v14; // r9d
  unsigned int v15; // esi
  struct _SIDKEY_AD_ATTRIBUTE *v16; // rax
  RPC_STATUS v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-B0h] BYREF
  struct _KDS_CONFIGURATION *v22; // [rsp+58h] [rbp-A8h] BYREF
  void *lpMem; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+78h] [rbp-88h] BYREF
  __int128 v26; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL hMem[2]; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+A8h] [rbp-58h] BYREF
  struct _KDS_CONFIGURATION **v29; // [rsp+B8h] [rbp-48h]
  __int64 v30; // [rsp+C0h] [rbp-40h]
  UCHAR pbBuffer[64]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[160]; // [rsp+110h] [rbp+10h] BYREF

  v9 = 0;
  memset_0(v32, 0, 0x96u);
  StringUuid = 0;
  lpMem = 0;
  v22 = 0;
  *(_OWORD *)hMem = 0;
  v25 = 0;
  v26 = 0;
  v24 = 0;
  memset_0(pbBuffer, 0, sizeof(pbBuffer));
  ServerConfig = GetServerConfig(ld, base, 1, &v22);
  v12 = v22;
  RootKeyDN = ServerConfig;
  if ( ServerConfig < 0 )
  {
    v14 = 363;
    goto LABEL_21;
  }
  RootKeyDN = GenerateObjGuid(&StringUuid);
  if ( RootKeyDN < 0 )
  {
    v14 = 371;
    goto LABEL_21;
  }
  RootKeyDN = GetRootKeyDN(a3, StringUuid, (unsigned __int16 **)&lpMem);
  if ( RootKeyDN < 0 )
  {
    v14 = 382;
    goto LABEL_21;
  }
  RootKeyDN = GenerateSecDescrBerVal((__int64)hMem);
  if ( RootKeyDN < 0 )
  {
    v14 = 390;
    goto LABEL_21;
  }
  RootKeyDN = BCryptGenRandom(0, pbBuffer, 0x40u, 2u);
  if ( RootKeyDN < 0 )
  {
    v14 = 403;
    goto LABEL_21;
  }
  LODWORD(v26) = 64;
  *((_QWORD *)&v26 + 1) = pbBuffer;
  v15 = 12;
  if ( *((_QWORD *)v12 + 5) )
  {
    v15 = 13;
    LODWORD(v25) = *((_DWORD *)v12 + 12);
    *((_QWORD *)&v25 + 1) = *((_QWORD *)v12 + 5);
  }
  if ( *((_QWORD *)v12 + 2) )
  {
    ++v15;
    LODWORD(v24) = *((_DWORD *)v12 + 6);
    *((_QWORD *)&v24 + 1) = *((_QWORD *)v12 + 2);
  }
  v16 = (struct _SIDKEY_AD_ATTRIBUTE *)SIDKeyProvAlloc(24LL * v15);
  v9 = v16;
  if ( !v16 )
  {
    RootKeyDN = -2147024882;
    SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", 0x1AEu);
    goto LABEL_27;
  }
  RootKeyDN = GenerateRootKeyAttributes(
                (__int64)a4,
                a5,
                (__int64)v16,
                (unsigned int *)v12,
                (__int64)StringUuid,
                (__int64)&v26,
                (__int64)hMem,
                (__int64)&v25,
                (__int64)&v24,
                (__int64)v32);
  if ( RootKeyDN < 0 )
  {
    v14 = 448;
    goto LABEL_21;
  }
  RootKeyDN = AddADObject(ld, (unsigned __int16 *)lpMem, v9, v15);
  if ( RootKeyDN < 0 )
  {
    v14 = 460;
LABEL_21:
    SidKeyDebugTraceError(RootKeyDN, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", v14);
    if ( RootKeyDN < 0 )
      goto LABEL_27;
  }
  if ( Uuid )
  {
    v17 = UuidFromStringW(StringUuid, Uuid);
    if ( v17 )
    {
      if ( v17 > 0 )
        RootKeyDN = (unsigned __int16)v17 | 0x80070000;
      else
        RootKeyDN = v17;
    }
  }
LABEL_27:
  memset_0(v32, 0, 0x55u);
  if ( RootKeyDN < 0 )
  {
    if ( (Microsoft_Windows_KdsSvcEnableBits & 1) != 0 )
    {
      LODWORD(v22) = RootKeyDN;
      v29 = &v22;
      v30 = 4;
      McGenEventWrite_EventWriteTransfer(v18, (const EVENT_DESCRIPTOR *)KdsSvcMRKCreationFailure, v19, 2u, &v28);
    }
  }
  else if ( (Microsoft_Windows_KdsSvcEnableBits & 2) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v18, KdsSvcCreateMRK, StringUuid);
  }
  if ( v9 )
    SIDKeyProvFree(v9);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( lpMem )
    SIDKeyProvFree(lpMem);
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( v12 )
    FreeServerConfig(v12);
  return (unsigned int)RootKeyDN;
}

```

## disassembly

```asm
0x180004a00  mov     [rsp-8+arg_18], rbx
0x180004a05  push    rbp
0x180004a06  push    rsi
0x180004a07  push    rdi
0x180004a08  push    r12
0x180004a0a  push    r13
0x180004a0c  push    r14
0x180004a0e  push    r15
0x180004a10  lea     rbp, [rsp-0C0h]
0x180004a18  sub     rsp, 1C0h
0x180004a1f  mov     rax, cs:__security_cookie
0x180004a26  xor     rax, rsp
0x180004a29  mov     [rbp+0F0h+var_40], rax
0x180004a30  mov     r15, [rbp+0F0h+Uuid]
0x180004a37  mov     rsi, r8
0x180004a3a  mov     rbx, rdx
0x180004a3d  mov     r12, rcx
0x180004a40  xor     edi, edi
0x180004a42  lea     rcx, [rbp+0F0h+var_E0]; void *
0x180004a46  xor     edx, edx; Val
0x180004a48  mov     r8d, 96h; Size
0x180004a4e  mov     r14d, edi
0x180004a51  mov     r13, r9
0x180004a54  call    memset_0
0x180004a59  xorps   xmm0, xmm0
0x180004a5c  mov     [rsp+1F0h+StringUuid], rdi
0x180004a61  xorps   xmm1, xmm1
0x180004a64  mov     [rsp+1F0h+lpMem], rdi
0x180004a69  xor     edx, edx; Val
0x180004a6b  mov     [rsp+1F0h+var_198], rdi
0x180004a70  lea     r8d, [rdi+40h]; Size
0x180004a74  lea     rcx, [rbp+0F0h+pbBuffer]; void *
0x180004a78  movups  xmmword ptr [rbp+0F0h+hMem], xmm0
0x180004a7c  movups  [rsp+1F0h+var_178], xmm1
0x180004a81  movups  [rbp+0F0h+var_168], xmm0
0x180004a85  movups  [rsp+1F0h+var_188], xmm1
0x180004a8a  call    memset_0
0x180004a8f  lea     r9, [rsp+1F0h+var_198]; struct _KDS_CONFIGURATION **
0x180004a94  mov     rdx, rbx; base
0x180004a97  lea     r8d, [rdi+1]; int
0x180004a9b  mov     rcx, r12; ld
0x180004a9e  call    ?GetServerConfig@@YAJPEAUldap@@PEBGHPEAPEAU_KDS_CONFIGURATION@@@Z; GetServerConfig(ldap *,ushort const *,int,_KDS_CONFIGURATION * *)
0x180004aa3  mov     rdi, [rsp+1F0h+var_198]
0x180004aa8  mov     ebx, eax
0x180004aaa  test    eax, eax
0x180004aac  jns     short loc_180004AB9
0x180004aae  mov     r9d, 16Bh
0x180004ab4  jmp     loc_180004C38
0x180004ab9  lea     rcx, [rsp+1F0h+StringUuid]; StringUuid
0x180004abe  call    ?GenerateObjGuid@@YAJPEAPEAG@Z; GenerateObjGuid(ushort * *)
0x180004ac3  mov     ebx, eax
0x180004ac5  test    eax, eax
0x180004ac7  jns     short loc_180004AD4
0x180004ac9  mov     r9d, 173h
0x180004acf  jmp     loc_180004C38
0x180004ad4  mov     rdx, [rsp+1F0h+StringUuid]; unsigned __int16 *
0x180004ad9  lea     r8, [rsp+1F0h+lpMem]; unsigned __int16 **
0x180004ade  mov     rcx, rsi; unsigned __int16 *
0x180004ae1  call    ?GetRootKeyDN@@YAJPEBG0PEAPEAG@Z; GetRootKeyDN(ushort const *,ushort const *,ushort * *)
0x180004ae6  mov     ebx, eax
0x180004ae8  test    eax, eax
0x180004aea  jns     short loc_180004AF7
0x180004aec  mov     r9d, 17Eh
0x180004af2  jmp     loc_180004C38
0x180004af7  lea     rcx, [rbp+0F0h+hMem]
0x180004afb  call    GenerateSecDescrBerVal
0x180004b00  mov     ebx, eax
0x180004b02  test    eax, eax
0x180004b04  jns     short loc_180004B11
0x180004b06  mov     r9d, 186h
0x180004b0c  jmp     loc_180004C38
0x180004b11  mov     r9d, 2; dwFlags
0x180004b17  lea     rdx, [rbp+0F0h+pbBuffer]; pbBuffer
0x180004b1b  xor     ecx, ecx; hAlgorithm
0x180004b1d  lea     r8d, [r9+3Eh]; cbBuffer
0x180004b21  call    cs:__imp_BCryptGenRandom
0x180004b27  mov     ebx, eax
0x180004b29  test    eax, eax
0x180004b2b  jns     short loc_180004B38
0x180004b2d  mov     r9d, 193h
0x180004b33  jmp     loc_180004C38
0x180004b38  lea     rax, [rbp+0F0h+pbBuffer]
0x180004b3c  mov     dword ptr [rbp+0F0h+var_168], 40h ; '@'
0x180004b43  mov     qword ptr [rbp+0F0h+var_168+8], rax
0x180004b47  mov     esi, 0Ch
0x180004b4c  cmp     [rdi+28h], r14
0x180004b50  jz      short loc_180004B66
0x180004b52  mov     eax, [rdi+30h]
0x180004b55  mov     esi, 0Dh
0x180004b5a  mov     dword ptr [rsp+1F0h+var_178], eax
0x180004b5e  mov     rax, [rdi+28h]
0x180004b62  mov     qword ptr [rbp+0F0h+var_178+8], rax
0x180004b66  cmp     [rdi+10h], r14
0x180004b6a  jz      short loc_180004B7E
0x180004b6c  mov     eax, [rdi+18h]
0x180004b6f  inc     esi
0x180004b71  mov     dword ptr [rsp+1F0h+var_188], eax
0x180004b75  mov     rax, [rdi+10h]
0x180004b79  mov     qword ptr [rsp+1F0h+var_188+8], rax
0x180004b7e  mov     eax, esi
0x180004b80  lea     rcx, [rax+rax*2]
0x180004b84  shl     rcx, 3; unsigned __int64
0x180004b88  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180004b8d  mov     r14, rax
0x180004b90  test    rax, rax
0x180004b93  jnz     short loc_180004BBD
0x180004b95  mov     r9d, 1AEh; unsigned int
0x180004b9b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180004ba2  lea     rdx, aHr; "hr"
0x180004ba9  mov     ecx, 8007000Eh; unsigned int
0x180004bae  mov     ebx, 8007000Eh
0x180004bb3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180004bb8  jmp     loc_180004C77
0x180004bbd  mov     rdx, [rbp+0F0h+arg_20]
0x180004bc4  lea     rax, [rbp+0F0h+var_E0]
0x180004bc8  mov     [rsp+1F0h+var_1A8], rax
0x180004bcd  mov     r9, rdi
0x180004bd0  lea     rax, [rsp+1F0h+var_188]
0x180004bd5  mov     r8, r14
0x180004bd8  mov     [rsp+1F0h+var_1B0], rax
0x180004bdd  mov     rcx, r13
0x180004be0  lea     rax, [rsp+1F0h+var_178]
0x180004be5  mov     [rsp+1F0h+var_1B8], rax
0x180004bea  lea     rax, [rbp+0F0h+hMem]
0x180004bee  mov     [rsp+1F0h+var_1C0], rax
0x180004bf3  lea     rax, [rbp+0F0h+var_168]
0x180004bf7  mov     [rsp+1F0h+var_1C8], rax
0x180004bfc  mov     rax, [rsp+1F0h+StringUuid]
0x180004c01  mov     [rsp+1F0h+var_1D0], rax
0x180004c06  call    GenerateRootKeyAttributes
0x180004c0b  mov     ebx, eax
0x180004c0d  test    eax, eax
0x180004c0f  jns     short loc_180004C19
0x180004c11  mov     r9d, 1C0h
0x180004c17  jmp     short loc_180004C38
0x180004c19  mov     rdx, [rsp+1F0h+lpMem]; unsigned __int16 *
0x180004c1e  mov     r9d, esi; unsigned int
0x180004c21  mov     r8, r14; struct _SIDKEY_AD_ATTRIBUTE *
0x180004c24  mov     rcx, r12; struct ldap *
0x180004c27  call    ?AddADObject@@YAJPEAUldap@@PEAGPEAU_SIDKEY_AD_ATTRIBUTE@@K@Z; AddADObject(ldap *,ushort *,_SIDKEY_AD_ATTRIBUTE *,ulong)
0x180004c2c  mov     ebx, eax
0x180004c2e  test    eax, eax
0x180004c30  jns     short loc_180004C51
0x180004c32  mov     r9d, 1CCh; unsigned int
0x180004c38  lea     rdx, aHr; "hr"
0x180004c3f  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180004c46  mov     ecx, ebx; unsigned int
0x180004c48  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180004c4d  test    ebx, ebx
0x180004c4f  js      short loc_180004C77
0x180004c51  test    r15, r15
0x180004c54  jz      short loc_180004C77
0x180004c56  mov     rcx, [rsp+1F0h+StringUuid]; StringUuid
0x180004c5b  mov     rdx, r15; Uuid
0x180004c5e  call    cs:__imp_UuidFromStringW
0x180004c64  test    eax, eax
0x180004c66  jz      short loc_180004C77
0x180004c68  jg      short loc_180004C6E
0x180004c6a  mov     ebx, eax
0x180004c6c  jmp     short loc_180004C77
0x180004c6e  movzx   ebx, ax
0x180004c71  or      ebx, 80070000h
0x180004c77  xor     edx, edx; Val
0x180004c79  lea     rcx, [rbp+0F0h+var_E0]; void *
0x180004c7d  lea     r8d, [rdx+55h]; Size
0x180004c81  call    memset_0
0x180004c86  test    ebx, ebx
0x180004c88  js      short loc_180004CA6
0x180004c8a  test    cs:Microsoft_Windows_KdsSvcEnableBits, 2
0x180004c91  jz      short loc_180004CDF
0x180004c93  mov     r8, [rsp+1F0h+StringUuid]
0x180004c98  lea     rdx, KdsSvcCreateMRK
0x180004c9f  call    McTemplateU0z_EventWriteTransfer
0x180004ca4  jmp     short loc_180004CDF
0x180004ca6  test    cs:Microsoft_Windows_KdsSvcEnableBits, 1
0x180004cad  jz      short loc_180004CDF
0x180004caf  lea     rax, [rsp+1F0h+var_198]
0x180004cb4  mov     dword ptr [rsp+1F0h+var_198], ebx
0x180004cb8  mov     [rbp+0F0h+var_138], rax
0x180004cbc  lea     rdx, KdsSvcMRKCreationFailure
0x180004cc3  lea     rax, [rbp+0F0h+var_148]
0x180004cc7  mov     [rbp+0F0h+var_130], 4
0x180004ccf  mov     r9d, 2
0x180004cd5  mov     [rsp+1F0h+var_1D0], rax
0x180004cda  call    McGenEventWrite_EventWriteTransfer
0x180004cdf  test    r14, r14
0x180004ce2  jz      short loc_180004CEC
0x180004ce4  mov     rcx, r14; lpMem
0x180004ce7  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180004cec  cmp     [rsp+1F0h+StringUuid], 0
0x180004cf2  jz      short loc_180004CFF
0x180004cf4  lea     rcx, [rsp+1F0h+StringUuid]; String
0x180004cf9  call    cs:__imp_RpcStringFreeW
0x180004cff  mov     rcx, [rsp+1F0h+lpMem]; lpMem
0x180004d04  test    rcx, rcx
0x180004d07  jz      short loc_180004D0E
0x180004d09  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180004d0e  mov     rcx, [rbp+0F0h+hMem+8]; hMem
0x180004d12  test    rcx, rcx
0x180004d15  jz      short loc_180004D1D
0x180004d17  call    cs:__imp_LocalFree
0x180004d1d  test    rdi, rdi
0x180004d20  jz      short loc_180004D2A
0x180004d22  mov     rcx, rdi; lpMem
0x180004d25  call    ?FreeServerConfig@@YAXPEAU_KDS_CONFIGURATION@@@Z; FreeServerConfig(_KDS_CONFIGURATION *)
0x180004d2a  mov     eax, ebx
0x180004d2c  mov     rcx, [rbp+0F0h+var_40]
0x180004d33  xor     rcx, rsp; StackCookie
0x180004d36  call    __security_check_cookie
0x180004d3b  mov     rbx, [rsp+1F0h+arg_18]
0x180004d43  add     rsp, 1C0h
0x180004d4a  pop     r15
0x180004d4c  pop     r14
0x180004d4e  pop     r13
0x180004d50  pop     r12
0x180004d52  pop     rdi
0x180004d53  pop     rsi
0x180004d54  pop     rbp
0x180004d55  retn
```
