# LookupCertInAD

- ea: `0x180047b84`
- end: `0x180047f15`
- name: `LookupCertInAD`
- size: `913`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180046a34`

## callees

- `0x18000f35c`
- `0x18000f430`
- `0x18000faec`
- `0x180010b88`
- `0x18002c61c`
- `0x18002c6c8`
- `0x180047b84`
- `0x1800950b0`
- `0x18009bd1c`
- `0x1800d6ea0`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x180047de3`
- `msvcrt!free` at `0x180047e7d`
- `msvcrt!free` at `0x180047de3`
- `msvcrt!free` at `0x180047e7d`
- `ADVAPI32!CopySid` at `0x180047dd7`
- `ADVAPI32!CopySid` at `0x180047dd7`
- `ADVAPI32!CryptAcquireContextW` at `0x180047c4d`
- `ADVAPI32!CryptAcquireContextW` at `0x180047c4d`
- `KERNEL32!GetLastError` at `0x180047c57`
- `KERNEL32!GetLastError` at `0x180047dee`
- `KERNEL32!GetLastError` at `0x180047c57`
- `KERNEL32!GetLastError` at `0x180047dee`
- `mqsec!MQSigCreateCertificate` at `0x180047e71`
- `mqsec!MQSigCreateCertificate` at `0x180047e71`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LookupCertInAD(_QWORD *a1, const WCHAR *a2, DWORD a3, CReference **a4)
{
  int v8; // eax
  signed int v9; // ebx
  HCRYPTPROV *v10; // rax
  HCRYPTPROV *v11; // rdi
  DWORD LastError; // eax
  int v13; // ebx
  unsigned __int16 v14; // r8
  int v15; // eax
  __int64 v16; // r8
  int v17; // ebx
  int v18; // eax
  DWORD v19; // ebx
  void *v20; // rax
  BOOL v21; // ebx
  DWORD v22; // eax
  bool v23; // sf
  unsigned __int16 v24; // r8
  CReference *v26; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v27[2]; // [rsp+48h] [rbp-31h] BYREF
  HCRYPTPROV *v28; // [rsp+50h] [rbp-29h] BYREF
  __int16 v29; // [rsp+58h] [rbp-21h] BYREF
  DWORD nDestinationSidLength; // [rsp+60h] [rbp-19h]
  PSID pSourceSid; // [rsp+68h] [rbp-11h]
  __int16 v32; // [rsp+70h] [rbp-9h]
  unsigned int v33; // [rsp+78h] [rbp-1h]
  void *Block; // [rsp+80h] [rbp+7h]
  __int128 v35; // [rsp+88h] [rbp+Fh] BYREF

  v35 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a1 + 16LL))(*a1, &v35);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = (HCRYPTPROV *)MmAllocate(0x30u);
    v11 = v10;
    v28 = v10;
    if ( v10 )
    {
      *((_DWORD *)v10 + 2) = 1;
      *v10 = (HCRYPTPROV)&CERTINFO::`vftable';
      v10[2] = 0;
      v10[3] = 0;
      v10[4] = 0;
      *((_BYTE *)v10 + 40) = 0;
    }
    else
    {
      v11 = 0;
    }
    v28 = v11;
    if ( !CryptAcquireContextW(v11 + 2, 0, a2, a3, 0xF0000000) )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 22, WPP_c687450366573ca356992ecf9dac13b8_Traceguids, LastError);
      if ( v13 )
        LogMsgNTStatus(v13, (wchar_t *)L"qmsecutl", 0x78u);
      v14 = 1135;
      v9 = -1072824276;
LABEL_30:
      LogMsgHR(v9, (wchar_t *)L"qmsecutl", v14);
LABEL_40:
      SafeRelease<CSockTransport>((CReference *)v11);
      return (unsigned int)v9;
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, HCRYPTPROV, HCRYPTPROV *))(*(_QWORD *)*a1 + 136LL))(*a1, v11[2], v11 + 3);
    v17 = v15;
    if ( v15 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          23,
          WPP_c687450366573ca356992ecf9dac13b8_Traceguids,
          (unsigned int)v15);
      LogMsgHR(v17, (wchar_t *)L"qmsecutl", 0x82u);
      v9 = -1072824276;
      goto LABEL_40;
    }
    v27[0] = 701;
    v27[1] = 702;
    v29 = 1;
    v32 = 1;
    v18 = ADGetObjectPropertiesGuid(4, 0, v16, &v35, 2, v27, &v29);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          24,
          WPP_c687450366573ca356992ecf9dac13b8_Traceguids,
          (unsigned int)v18);
LABEL_39:
      R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(a4, (__int64 *)&v28);
      v9 = 0;
      goto LABEL_40;
    }
    v19 = nDestinationSidLength;
    v20 = MmAllocate(nDestinationSidLength);
    v11[4] = (HCRYPTPROV)v20;
    v21 = CopySid(v19, v20, pSourceSid);
    free(pSourceSid);
    if ( !v21 )
    {
      v22 = GetLastError();
      v9 = v22;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 25, WPP_c687450366573ca356992ecf9dac13b8_Traceguids, v22);
      v23 = v9 < 0;
      if ( v9 > 0 )
      {
        v9 = (unsigned __int16)v9 | 0x80070000;
        v23 = v9 < 0;
      }
      if ( !v23 )
        goto LABEL_40;
      v14 = 1136;
      goto LABEL_30;
    }
    v26 = 0;
    v9 = MQSigCreateCertificate(&v26, 0, Block, v33);
    free(Block);
    if ( v9 >= 0 )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD, CReference **))(*(_QWORD *)*a1 + 24LL))(*a1, &v26) )
      {
        if ( v26 )
          CReference::Release(v26);
        goto LABEL_39;
      }
      v24 = 1138;
      v9 = -1072824276;
    }
    else
    {
      v24 = 1137;
    }
    LogMsgHR(v9, (wchar_t *)L"qmsecutl", v24);
    if ( v26 )
      CReference::Release(v26);
    goto LABEL_40;
  }
  LogMsgHR(v8, (wchar_t *)L"qmsecutl", 0x6Eu);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180047b84  push    rbp
0x180047b86  push    rbx
0x180047b87  push    rsi
0x180047b88  push    rdi
0x180047b89  push    r12
0x180047b8b  push    r14
0x180047b8d  push    r15
0x180047b8f  lea     rbp, [rsp-27h]
0x180047b94  sub     rsp, 0A0h
0x180047b9b  mov     rax, cs:__security_cookie
0x180047ba2  xor     rax, rsp
0x180047ba5  mov     [rbp+57h+var_38], rax
0x180047ba9  mov     r12, r9
0x180047bac  mov     r15d, r8d
0x180047baf  mov     r14, rdx
0x180047bb2  mov     rsi, rcx
0x180047bb5  xorps   xmm0, xmm0
0x180047bb8  movups  [rbp+57h+var_48], xmm0
0x180047bbc  mov     rcx, [rcx]
0x180047bbf  mov     rax, [rcx]
0x180047bc2  lea     rdx, [rbp+57h+var_48]
0x180047bc6  mov     rax, [rax+10h]
0x180047bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047bcf  mov     ebx, eax
0x180047bd1  test    eax, eax
0x180047bd3  jns     short loc_180047BEE
0x180047bd5  mov     r8d, 6Eh ; 'n'; unsigned __int16
0x180047bdb  lea     rdx, aQmsecutl; "qmsecutl"
0x180047be2  mov     ecx, eax; int
0x180047be4  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180047be9  jmp     loc_180047EF5
0x180047bee  mov     ecx, 30h ; '0'; unsigned __int64
0x180047bf3  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180047bf8  mov     rdi, rax
0x180047bfb  mov     [rbp+57h+var_80], rax
0x180047bff  test    rax, rax
0x180047c02  jz      short loc_180047C33
0x180047c04  mov     dword ptr [rax+8], 1
0x180047c0b  lea     rax, ??_7CERTINFO@@6B@; const CERTINFO::`vftable'
0x180047c12  mov     [rdi], rax
0x180047c15  mov     qword ptr [rdi+10h], 0
0x180047c1d  mov     qword ptr [rdi+18h], 0
0x180047c25  mov     qword ptr [rdi+20h], 0
0x180047c2d  mov     byte ptr [rdi+28h], 0
0x180047c31  jmp     short loc_180047C35
0x180047c33  xor     edi, edi
0x180047c35  mov     [rbp+57h+var_80], rdi
0x180047c39  mov     [rsp+0D0h+dwFlags], 0F0000000h; dwFlags
0x180047c41  mov     r9d, r15d; dwProvType
0x180047c44  mov     r8, r14; szProvider
0x180047c47  xor     edx, edx; szContainer
0x180047c49  lea     rcx, [rdi+10h]; phProv
0x180047c4d  call    cs:__imp_CryptAcquireContextW
0x180047c53  test    eax, eax
0x180047c55  jnz     short loc_180047CBE
0x180047c57  call    cs:__imp_GetLastError
0x180047c5d  mov     ebx, eax
0x180047c5f  lea     rdx, WPP_GLOBAL_Control
0x180047c66  mov     rcx, cs:WPP_GLOBAL_Control
0x180047c6d  cmp     rcx, rdx
0x180047c70  jz      short loc_180047C96
0x180047c72  test    byte ptr [rcx+10Ch], 1
0x180047c79  jz      short loc_180047C96
0x180047c7b  mov     edx, 16h
0x180047c80  mov     r9d, eax
0x180047c83  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x180047c8a  mov     rcx, [rcx+100h]
0x180047c91  call    WPP_SF_d
0x180047c96  test    ebx, ebx
0x180047c98  jz      short loc_180047CAE
0x180047c9a  mov     r8d, 78h ; 'x'; unsigned __int16
0x180047ca0  lea     rdx, aQmsecutl; "qmsecutl"
0x180047ca7  mov     ecx, ebx; int
0x180047ca9  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180047cae  mov     r8d, 46Fh
0x180047cb4  mov     ebx, 0C00E002Ch
0x180047cb9  jmp     loc_180047E48
0x180047cbe  mov     rcx, [rsi]
0x180047cc1  mov     rax, [rcx]
0x180047cc4  lea     r8, [rdi+18h]
0x180047cc8  mov     rdx, [rdi+10h]
0x180047ccc  mov     rax, [rax+88h]
0x180047cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cd8  mov     ebx, eax
0x180047cda  test    eax, eax
0x180047cdc  jns     short loc_180047D33
0x180047cde  lea     rdx, WPP_GLOBAL_Control
0x180047ce5  mov     rcx, cs:WPP_GLOBAL_Control
0x180047cec  cmp     rcx, rdx
0x180047cef  jz      short loc_180047D15
0x180047cf1  test    byte ptr [rcx+10Ch], 1
0x180047cf8  jz      short loc_180047D15
0x180047cfa  mov     edx, 17h
0x180047cff  mov     r9d, eax
0x180047d02  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x180047d09  mov     rcx, [rcx+100h]
0x180047d10  call    WPP_SF_d
0x180047d15  mov     r8d, 82h; unsigned __int16
0x180047d1b  lea     rdx, aQmsecutl; "qmsecutl"
0x180047d22  mov     ecx, ebx; int
0x180047d24  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180047d29  mov     ebx, 0C00E002Ch
0x180047d2e  jmp     loc_180047EED
0x180047d33  mov     [rbp+57h+var_88], 2BDh
0x180047d3a  mov     [rbp+57h+var_84], 2BEh
0x180047d41  mov     r14d, 1
0x180047d47  mov     [rbp+57h+var_78], r14w
0x180047d4c  mov     [rbp+57h+var_60], r14w
0x180047d51  lea     rax, [rbp+57h+var_78]
0x180047d55  mov     [rsp+0D0h+var_A0], rax
0x180047d5a  lea     rax, [rbp+57h+var_88]
0x180047d5e  mov     [rsp+0D0h+var_A8], rax
0x180047d63  mov     [rsp+0D0h+dwFlags], 2
0x180047d6b  lea     r9, [rbp+57h+var_48]
0x180047d6f  xor     edx, edx
0x180047d71  lea     ecx, [rdx+4]
0x180047d74  call    ?ADGetObjectPropertiesGuid@@YAJW4AD_OBJECT@@PEB_W_NPEBU_GUID@@KQEBKQEAUtagPROPVARIANT@@@Z; ADGetObjectPropertiesGuid(AD_OBJECT,wchar_t const *,bool,_GUID const *,ulong,ulong const * const,tagPROPVARIANT * const)
0x180047d79  test    eax, eax
0x180047d7b  jns     short loc_180047DC0
0x180047d7d  lea     rdx, WPP_GLOBAL_Control
0x180047d84  mov     rcx, cs:WPP_GLOBAL_Control
0x180047d8b  cmp     rcx, rdx
0x180047d8e  jz      loc_180047EDF
0x180047d94  test    [rcx+10Ch], r14b
0x180047d9b  jz      loc_180047EDF
0x180047da1  lea     edx, [r14+17h]
0x180047da5  mov     r9d, eax
0x180047da8  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x180047daf  mov     rcx, [rcx+100h]
0x180047db6  call    WPP_SF_d
0x180047dbb  jmp     loc_180047EDF
0x180047dc0  mov     ebx, [rbp+57h+nDestinationSidLength]
0x180047dc3  mov     ecx, ebx; unsigned __int64
0x180047dc5  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180047dca  mov     [rdi+20h], rax
0x180047dce  mov     r8, [rbp+57h+pSourceSid]; pSourceSid
0x180047dd2  mov     rdx, rax; pDestinationSid
0x180047dd5  mov     ecx, ebx; nDestinationSidLength
0x180047dd7  call    cs:__imp_CopySid
0x180047ddd  mov     ebx, eax
0x180047ddf  mov     rcx, [rbp+57h+pSourceSid]; Block
0x180047de3  call    cs:__imp_free
0x180047de9  nop
0x180047dea  test    ebx, ebx
0x180047dec  jnz     short loc_180047E5B
0x180047dee  call    cs:__imp_GetLastError
0x180047df4  mov     ebx, eax
0x180047df6  lea     rdx, WPP_GLOBAL_Control
0x180047dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e04  cmp     rcx, rdx
0x180047e07  jz      short loc_180047E2D
0x180047e09  test    [rcx+10Ch], r14b
0x180047e10  jz      short loc_180047E2D
0x180047e12  mov     edx, 19h
0x180047e17  mov     r9d, eax
0x180047e1a  lea     r8, WPP_c687450366573ca356992ecf9dac13b8_Traceguids
0x180047e21  mov     rcx, [rcx+100h]
0x180047e28  call    WPP_SF_d
0x180047e2d  test    ebx, ebx
0x180047e2f  jle     short loc_180047E3C
0x180047e31  movzx   ebx, bx
0x180047e34  or      ebx, 80070000h
0x180047e3a  test    ebx, ebx
0x180047e3c  jns     loc_180047EED
0x180047e42  mov     r8d, 470h; unsigned __int16
0x180047e48  lea     rdx, aQmsecutl; "qmsecutl"
0x180047e4f  mov     ecx, ebx; int
0x180047e51  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180047e56  jmp     loc_180047EED
0x180047e5b  mov     [rbp+57h+var_90], 0
0x180047e63  mov     r9d, [rbp+57h+var_58]
0x180047e67  mov     r8, [rbp+57h+Block]
0x180047e6b  xor     edx, edx
0x180047e6d  lea     rcx, [rbp+57h+var_90]
0x180047e71  call    cs:__imp_MQSigCreateCertificate
0x180047e77  mov     ebx, eax
0x180047e79  mov     rcx, [rbp+57h+Block]; Block
0x180047e7d  call    cs:__imp_free
0x180047e83  nop
0x180047e84  test    ebx, ebx
0x180047e86  jns     short loc_180047EAD
0x180047e88  mov     r8d, 471h; unsigned __int16
0x180047e8e  lea     rdx, aQmsecutl; "qmsecutl"
0x180047e95  mov     ecx, ebx; int
0x180047e97  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180047e9c  nop
0x180047e9d  mov     rcx, [rbp+57h+var_90]; this
0x180047ea1  test    rcx, rcx
0x180047ea4  jz      short loc_180047EED
0x180047ea6  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x180047eab  jmp     short loc_180047EED
0x180047ead  mov     rcx, [rsi]
0x180047eb0  mov     rax, [rcx]
0x180047eb3  lea     rdx, [rbp+57h+var_90]
0x180047eb7  mov     rax, [rax+18h]
0x180047ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ec0  test    eax, eax
0x180047ec2  jnz     short loc_180047ED1
0x180047ec4  mov     r8d, 472h
0x180047eca  mov     ebx, 0C00E002Ch
0x180047ecf  jmp     short loc_180047E8E
0x180047ed1  mov     rcx, [rbp+57h+var_90]; this
0x180047ed5  test    rcx, rcx
0x180047ed8  jz      short loc_180047EDF
0x180047eda  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x180047edf  lea     rdx, [rbp+57h+var_80]
0x180047ee3  mov     rcx, r12
0x180047ee6  call    ??4?$R@UCTX_OPENREMOTE_HANDLE_TYPE@@@@QEAAAEAV0@AEBV0@@Z; R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(R<CTX_OPENREMOTE_HANDLE_TYPE> const &)
0x180047eeb  xor     ebx, ebx
0x180047eed  mov     rcx, rdi
0x180047ef0  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180047ef5  mov     eax, ebx
0x180047ef7  mov     rcx, [rbp+57h+var_38]
0x180047efb  xor     rcx, rsp; StackCookie
0x180047efe  call    __security_check_cookie
0x180047f03  add     rsp, 0A0h
0x180047f0a  pop     r15
0x180047f0c  pop     r14
0x180047f0e  pop     r12
0x180047f10  pop     rdi
0x180047f11  pop     rsi
0x180047f12  pop     rbx
0x180047f13  pop     rbp
0x180047f14  retn
```
