# IkeProcessSspiInitiator

- ea: `0x180082cd0`
- end: `0x180083292`
- name: `IkeProcessSspiInitiator`
- size: `1474`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800825a4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180008388`
- `0x180025cfc`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x18005bce4`
- `0x18006dec8`
- `0x18007c950`
- `0x18007d46c`
- `0x18007f120`
- `0x180080058`
- `0x180082480`
- `0x180082cd0`
- `0x1800849cc`
- `0x180084c50`
- `0x180117fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083048`
- `SspiCli!InitializeSecurityContextW` at `0x180082f20`
- `SspiCli!InitializeSecurityContextW` at `0x180082f20`

## string_xrefs

- `0x1800831b1`: `ISC outtoken:`
- `0x180082ec4`: `ISC intoken:`
- `0x180082e5b`: `Received NULL SSPI token`

## pseudocode

```c
__int64 __fastcall IkeProcessSspiInitiator(__int64 a1, struct _SecBuffer *a2, unsigned int *a3, _DWORD *a4)
{
  SIZE_T cbBuffer; // rcx
  __int64 SecBuffer; // rbx
  struct _SecBuffer *v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // r15d
  __int64 v27; // rax
  unsigned int *v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  unsigned int v33; // edi
  __int64 v34; // rsi
  __int64 TlsPeerAddr; // rbx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  int TlsMmLuid; // eax
  __int64 v41; // rcx
  __int64 v42; // rax
  int v43; // r8d
  int v44; // r9d
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  _QWORD *v49; // rdi
  __int64 v50; // rdi
  __int64 v51; // rbx
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // r9
  int v56; // eax
  __int64 v57; // rdi
  __int64 v58; // rbx
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  int v63; // eax
  __int64 v64; // rcx
  __int64 v65; // rax
  int v66; // r8d
  int v67; // r9d
  _DWORD *v68; // rax
  __int64 v69; // rcx
  unsigned int v70; // eax
  unsigned int TargetDataRep[2]; // [rsp+28h] [rbp-D8h]
  __int64 v73; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v74; // [rsp+68h] [rbp-98h]
  __int64 v75; // [rsp+70h] [rbp-90h]
  struct _SecBufferDesc pOutput; // [rsp+78h] [rbp-88h] BYREF
  size_t Size[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _SecBufferDesc pInput; // [rsp+98h] [rbp-68h] BYREF
  unsigned int fContextReq; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v80; // [rsp+ACh] [rbp-54h] BYREF
  __int64 v81; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v82; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v83; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v84[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v85; // [rsp+F0h] [rbp-10h]
  __int64 v86; // [rsp+F8h] [rbp-8h]
  _BYTE v87[16]; // [rsp+100h] [rbp+0h] BYREF
  const char *p_fContextReq; // [rsp+110h] [rbp+10h]
  __int64 v89; // [rsp+118h] [rbp+18h]
  unsigned int *v90; // [rsp+120h] [rbp+20h]
  __int64 v91; // [rsp+128h] [rbp+28h]
  __int64 *v92; // [rsp+130h] [rbp+30h]
  __int64 v93; // [rsp+138h] [rbp+38h]

  v75 = a1;
  v74 = a4;
  fContextReq = 0;
  v73 = 0;
  pInput = 0;
  pOutput = 0;
  v82 = 0;
  *(_OWORD *)Size = 0;
  TraceLogHelper("IkeProcessSspiInitiator", 1);
  pInput.ulVersion = 0;
  pInput.cBuffers = 1;
  pOutput.ulVersion = 0;
  pOutput.cBuffers = 1;
  if ( *((_QWORD *)a3 + 12) )
  {
    cbBuffer = a2->cbBuffer;
    pInput.pBuffers = (PSecBuffer)Size;
    pOutput.pBuffers = (PSecBuffer)&v82;
    SecBuffer = IkeAllocateSecBuffer(cbBuffer);
    if ( SecBuffer )
      goto LABEL_53;
    memcpy_0((void *)Size[1], a2->pvBuffer, LODWORD(Size[0]));
    SecBuffer = IkeAllocateSecBuffer(*a3);
    if ( SecBuffer )
      goto LABEL_53;
  }
  else
  {
    v9 = (struct _SecBuffer *)*((_QWORD *)a3 + 13);
    v10 = *a3;
    pInput.pBuffers = a2;
    pOutput.pBuffers = v9;
    v9->cbBuffer = v10;
  }
  SetIscFlags(a1, a3, &fContextReq);
  if ( a2->cbBuffer )
  {
    SecBuffer = IkeImpersonate(a1, (__int64)a3);
    if ( SecBuffer )
      goto LABEL_53;
    v27 = *((_QWORD *)a3 + 13);
    if ( v27 )
      ++*(_DWORD *)(v27 + 80);
    IkeDumpSspiToken(a2->pvBuffer, "ISC intoken:", a2->cbBuffer);
    v28 = a3 + 10;
    v26 = InitializeSecurityContextW(
            (PCredHandle)(a3 + 2),
            (PCtxtHandle)(a3 + 6),
            *((SEC_WCHAR **)a3 + 8),
            fContextReq,
            0,
            0x10u,
            &pInput,
            0,
            (PCtxtHandle)(a3 + 6),
            &pOutput,
            a3 + 10,
            (PTimeStamp)a3 + 6);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v33 = *v28;
      v34 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v30);
      TlsMmLuid = IkeGetTlsMmLuid(v37, v36, v38, v39);
      WPP_SF_iSDD(
        v34,
        22,
        (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids,
        TlsMmLuid,
        TlsPeerAddr,
        v26,
        v33);
      v28 = a3 + 10;
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v81 = IkeGetTlsMmLuid(v30, v29, v31, v32);
      v85 = &v81;
      v86 = 8;
      v42 = IkeGetTlsPeerAddr(v41);
      tlgCreate1Sz_wchar_t(v87, v42);
      fContextReq = v26;
      p_fContextReq = (const char *)&fContextReq;
      v80 = *v28;
      v90 = &v80;
      v89 = 4;
      v91 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)byte_180155B61,
        v43,
        v44,
        6,
        (__int64)v84);
    }
    SecBuffer = IkeRevertImpersonation(a3);
    if ( SecBuffer )
      goto LABEL_53;
    if ( v26 == 590624 )
    {
      a3[18] |= 0x20u;
      v26 = 590610;
    }
    else if ( v26 && v26 != 590610 )
    {
      goto LABEL_28;
    }
LABEL_41:
    IkeDumpSspiToken(pOutput.pBuffers->pvBuffer, "ISC outtoken:", pOutput.pBuffers->cbBuffer);
    if ( !v26 )
    {
      v69 = *((_QWORD *)a3 + 13);
      if ( !v69 || (v70 = a3[18], (v70 & 8) != 0) )
      {
        if ( (a3[10] & 2) != 0
          || v69
          && ((SecBuffer = IkeGetPolicyFromSspi(v75, a3, &v73), (a3[18] & 0x800000) != 0)
           || (*(_BYTE *)(v73 + 48) & 8) != 0) )
        {
          *v74 = 1;
        }
      }
      else
      {
        a3[18] = v70 | 4;
      }
    }
    if ( *((_QWORD *)a3 + 12) )
      IkeProcessOakISCResponse(v26, Size, &v82);
    a3[18] |= 1u;
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = IkeGetTlsPeerAddr(v12);
    v21 = IkeGetTlsMmLuid(v18, v17, v19, v20);
    WPP_SF_iS(v15, 21, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v21, v16);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v81 = IkeGetTlsMmLuid(v12, v11, v13, v14);
    v85 = &v81;
    v86 = 8;
    v23 = IkeGetTlsPeerAddr(v22);
    tlgCreate1Sz_wchar_t(v87, v23);
    v89 = 25;
    p_fContextReq = "Received NULL SSPI token";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_180155BAD,
      v24,
      v25,
      5,
      (__int64)v84);
  }
  v26 = -2146893048;
LABEL_28:
  fContextReq = GetLastError();
  v49 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v50 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v51 = IkeGetTlsPeerAddr(v46);
      v56 = IkeGetTlsMmLuid(v53, v52, v54, v55);
      TargetDataRep[0] = fContextReq;
      WPP_SF_iSL(
        v50,
        23,
        (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids,
        v56,
        v51,
        *(_QWORD *)TargetDataRep);
      v49 = WPP_GLOBAL_Control;
    }
    if ( v49 != &WPP_GLOBAL_Control && *((_BYTE *)v49 + 25) >= 2u && (*((_BYTE *)v49 + 28) & 0x10) != 0 )
    {
      v57 = v49[2];
      v58 = IkeGetTlsPeerAddr(v46);
      v63 = IkeGetTlsMmLuid(v60, v59, v61, v62);
      TargetDataRep[0] = v26;
      WPP_SF_iSL(
        v57,
        24,
        (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids,
        v63,
        v58,
        *(_QWORD *)TargetDataRep);
    }
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v83 = IkeGetTlsMmLuid(v46, v45, v47, v48);
    v85 = &v83;
    v86 = 8;
    v65 = IkeGetTlsPeerAddr(v64);
    tlgCreate1Sz_wchar_t(v87, v65);
    v80 = fContextReq;
    p_fContextReq = "ISC failed";
    v90 = &v80;
    v89 = 11;
    v92 = &v81;
    v91 = 4;
    LODWORD(v81) = v26;
    v93 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_180155B05,
      v66,
      v67,
      7,
      (__int64)v84);
  }
  SecBuffer = SetSspiError(a3, v26, 1);
  if ( !SecBuffer )
  {
    v68 = (_DWORD *)*((_QWORD *)a3 + 13);
    if ( v68 )
      *v68 = 0;
    goto LABEL_41;
  }
LABEL_53:
  WfpMemFree(&Size[1]);
  WfpMemFree((char *)&v82 + 8);
  TraceLogHelper("IkeProcessSspiInitiator", 0);
  return IkeReturnError(SecBuffer, "IkeProcessSspiInitiator");
}

```

## disassembly

```asm
0x180082cd0  push    rbp
0x180082cd2  push    rbx
0x180082cd3  push    rsi
0x180082cd4  push    rdi
0x180082cd5  push    r12
0x180082cd7  push    r13
0x180082cd9  push    r14
0x180082cdb  push    r15
0x180082cdd  lea     rbp, [rsp-58h]
0x180082ce2  sub     rsp, 158h
0x180082ce9  mov     rax, cs:__security_cookie
0x180082cf0  xor     rax, rsp
0x180082cf3  mov     [rbp+90h+var_50], rax
0x180082cf7  xor     r15d, r15d
0x180082cfa  mov     [rsp+190h+var_120], rcx
0x180082cff  xorps   xmm0, xmm0
0x180082d02  mov     [rsp+190h+var_128], r9
0x180082d07  xorps   xmm1, xmm1
0x180082d0a  mov     [rbp+90h+fContextReq], r15d
0x180082d0e  mov     rdi, rdx
0x180082d11  mov     [rsp+190h+var_130], r15
0x180082d16  mov     rsi, rcx
0x180082d19  lea     r12d, [r15+1]
0x180082d1d  mov     edx, r12d
0x180082d20  lea     rcx, aIkeprocesssspi; "IkeProcessSspiInitiator"
0x180082d27  mov     r14, r8
0x180082d2a  movups  xmmword ptr [rbp+90h+var_F8.ulVersion], xmm0
0x180082d2e  movups  xmmword ptr [rsp+190h+var_118.ulVersion], xmm1
0x180082d33  movups  [rbp+90h+var_D8], xmm0
0x180082d37  movups  xmmword ptr [rbp+90h+Size], xmm1
0x180082d3b  call    TraceLogHelper
0x180082d40  mov     [rbp+90h+var_F8.ulVersion], r15d
0x180082d44  mov     [rbp+90h+var_F8.cBuffers], r12d
0x180082d48  mov     [rsp+190h+var_118.ulVersion], r15d
0x180082d4d  mov     [rsp+190h+var_118.cBuffers], r12d
0x180082d52  cmp     [r14+60h], r15
0x180082d56  jz      short loc_180082DAA
0x180082d58  mov     ecx, [rdi]; dwBytes
0x180082d5a  lea     rax, [rbp+90h+Size]
0x180082d5e  mov     [rbp+90h+var_F8.pBuffers], rax
0x180082d62  lea     rdx, [rbp+90h+Size]
0x180082d66  lea     rax, [rbp+90h+var_D8]
0x180082d6a  mov     [rbp+90h+var_118.pBuffers], rax
0x180082d6e  call    IkeAllocateSecBuffer
0x180082d73  mov     rbx, rax
0x180082d76  test    rax, rax
0x180082d79  jnz     loc_180083243
0x180082d7f  mov     r8d, dword ptr [rbp+90h+Size]; Size
0x180082d83  mov     rdx, [rdi+8]; Src
0x180082d87  mov     rcx, [rbp+90h+Size+8]; void *
0x180082d8b  call    memcpy_0
0x180082d90  mov     ecx, [r14]; dwBytes
0x180082d93  lea     rdx, [rbp+90h+var_D8]
0x180082d97  call    IkeAllocateSecBuffer
0x180082d9c  mov     rbx, rax
0x180082d9f  test    rax, rax
0x180082da2  jnz     loc_180083243
0x180082da8  jmp     short loc_180082DBB
0x180082daa  mov     rcx, [r14+68h]
0x180082dae  mov     eax, [r14]
0x180082db1  mov     [rbp+90h+var_F8.pBuffers], rdi
0x180082db5  mov     [rbp+90h+var_118.pBuffers], rcx
0x180082db9  mov     [rcx], eax
0x180082dbb  lea     r8, [rbp+90h+fContextReq]
0x180082dbf  mov     rdx, r14
0x180082dc2  mov     rcx, rsi
0x180082dc5  call    SetIscFlags
0x180082dca  cmp     [rdi], r15d
0x180082dcd  jnz     loc_180082E9D
0x180082dd3  mov     rdi, cs:WPP_GLOBAL_Control
0x180082dda  lea     r13, WPP_GLOBAL_Control
0x180082de1  mov     r12d, 4
0x180082de7  cmp     rdi, r13
0x180082dea  jz      short loc_180082E25
0x180082dec  cmp     [rdi+19h], r12b
0x180082df0  jb      short loc_180082E25
0x180082df2  test    byte ptr [rdi+1Ch], 10h
0x180082df6  jz      short loc_180082E25
0x180082df8  mov     rdi, [rdi+10h]
0x180082dfc  call    IkeGetTlsPeerAddr
0x180082e01  mov     rbx, rax
0x180082e04  call    IkeGetTlsMmLuid
0x180082e09  mov     r9, rax
0x180082e0c  mov     qword ptr [rsp+190h+Reserved1], rbx
0x180082e11  lea     edx, [r12+11h]
0x180082e16  mov     rcx, rdi
0x180082e19  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180082e20  call    WPP_SF_iS
0x180082e25  mov     eax, cs:dword_180173278
0x180082e2b  mov     esi, 8
0x180082e30  cmp     eax, r12d
0x180082e33  jbe     short loc_180082E92
0x180082e35  call    IkeGetTlsMmLuid
0x180082e3a  mov     [rbp+90h+var_E0], rax
0x180082e3e  lea     rax, [rbp+90h+var_E0]
0x180082e42  mov     [rbp+90h+var_A0], rax
0x180082e46  mov     [rbp+90h+var_98], rsi
0x180082e4a  call    IkeGetTlsPeerAddr
0x180082e4f  mov     rdx, rax
0x180082e52  lea     rcx, [rbp+90h+var_90]
0x180082e56  call    _tlgCreate1Sz_wchar_t
0x180082e5b  lea     rcx, aReceivedNullSs; "Received NULL SSPI token"
0x180082e62  mov     [rbp+90h+var_78], 19h
0x180082e6a  lea     rax, [rbp+90h+var_C0]
0x180082e6e  mov     [rbp+90h+var_80], rcx
0x180082e72  mov     qword ptr [rsp+190h+TargetDataRep], rax
0x180082e77  lea     rcx, dword_180173278
0x180082e7e  lea     rdx, byte_180155BAD
0x180082e85  mov     [rsp+190h+Reserved1], 5
0x180082e8d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180082e92  mov     r15d, 80090308h
0x180082e98  jmp     loc_180083048
0x180082e9d  mov     rdx, r14
0x180082ea0  mov     rcx, rsi
0x180082ea3  call    IkeImpersonate
0x180082ea8  mov     rbx, rax
0x180082eab  test    rax, rax
0x180082eae  jnz     loc_180083243
0x180082eb4  mov     rax, [r14+68h]
0x180082eb8  test    rax, rax
0x180082ebb  jz      short loc_180082EC1
0x180082ebd  add     [rax+50h], r12d
0x180082ec1  mov     r8d, [rdi]
0x180082ec4  lea     rdx, aIscIntoken; "ISC intoken:"
0x180082ecb  mov     rcx, [rdi+8]
0x180082ecf  call    IkeDumpSspiToken
0x180082ed4  mov     r9d, [rbp+90h+fContextReq]; fContextReq
0x180082ed8  lea     rax, [r14+30h]
0x180082edc  mov     r8, [r14+40h]; pszTargetName
0x180082ee0  lea     rdx, [r14+18h]; phContext
0x180082ee4  mov     [rsp+190h+ptsExpiry], rax; ptsExpiry
0x180082ee9  lea     rbx, [r14+28h]
0x180082eed  mov     [rsp+190h+pfContextAttr], rbx; pfContextAttr
0x180082ef2  lea     rax, [rsp+190h+var_118]
0x180082ef7  mov     [rsp+190h+pOutput], rax; pOutput
0x180082efc  lea     rcx, [r14+8]; phCredential
0x180082f00  mov     [rsp+190h+phNewContext], rdx; phNewContext
0x180082f05  lea     rax, [rbp+90h+var_F8]
0x180082f09  mov     [rsp+190h+Reserved2], r15d; Reserved2
0x180082f0e  mov     [rsp+190h+pInput], rax; pInput
0x180082f13  mov     [rsp+190h+TargetDataRep], 10h; TargetDataRep
0x180082f1b  mov     [rsp+190h+Reserved1], r15d; Reserved1
0x180082f20  call    cs:__imp_InitializeSecurityContextW
0x180082f26  mov     r15d, eax
0x180082f29  mov     rsi, cs:WPP_GLOBAL_Control
0x180082f30  lea     r13, WPP_GLOBAL_Control
0x180082f37  mov     r12d, 4
0x180082f3d  cmp     rsi, r13
0x180082f40  jz      short loc_180082F8A
0x180082f42  cmp     [rsi+19h], r12b
0x180082f46  jb      short loc_180082F8A
0x180082f48  test    byte ptr [rsi+1Ch], 10h
0x180082f4c  jz      short loc_180082F8A
0x180082f4e  mov     edi, [rbx]
0x180082f50  mov     rsi, [rsi+10h]
0x180082f54  call    IkeGetTlsPeerAddr
0x180082f59  mov     rbx, rax
0x180082f5c  call    IkeGetTlsMmLuid
0x180082f61  mov     dword ptr [rsp+190h+pInput], edi
0x180082f65  lea     edx, [r12+12h]
0x180082f6a  mov     r9, rax
0x180082f6d  mov     [rsp+190h+TargetDataRep], r15d
0x180082f72  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180082f79  mov     qword ptr [rsp+190h+Reserved1], rbx
0x180082f7e  mov     rcx, rsi
0x180082f81  call    WPP_SF_iSDD
0x180082f86  lea     rbx, [r14+28h]
0x180082f8a  mov     eax, cs:dword_180173278
0x180082f90  mov     esi, 8
0x180082f95  cmp     eax, r12d
0x180082f98  jbe     short loc_180083005
0x180082f9a  call    IkeGetTlsMmLuid
0x180082f9f  mov     [rbp+90h+var_E0], rax
0x180082fa3  lea     rax, [rbp+90h+var_E0]
0x180082fa7  mov     [rbp+90h+var_A0], rax
0x180082fab  mov     [rbp+90h+var_98], rsi
0x180082faf  call    IkeGetTlsPeerAddr
0x180082fb4  mov     rdx, rax
0x180082fb7  lea     rcx, [rbp+90h+var_90]
0x180082fbb  call    _tlgCreate1Sz_wchar_t
0x180082fc0  lea     rax, [rbp+90h+fContextReq]
0x180082fc4  mov     [rbp+90h+fContextReq], r15d
0x180082fc8  mov     [rbp+90h+var_80], rax
0x180082fcc  lea     rdx, byte_180155B61
0x180082fd3  mov     eax, [rbx]
0x180082fd5  lea     rcx, dword_180173278
0x180082fdc  mov     [rbp+90h+var_E4], eax
0x180082fdf  lea     rax, [rbp+90h+var_E4]
0x180082fe3  mov     [rbp+90h+var_70], rax
0x180082fe7  lea     rax, [rbp+90h+var_C0]
0x180082feb  mov     qword ptr [rsp+190h+TargetDataRep], rax
0x180082ff0  mov     [rsp+190h+Reserved1], 6
0x180082ff8  mov     [rbp+90h+var_78], r12
0x180082ffc  mov     [rbp+90h+var_68], r12
0x180083000  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083005  mov     rcx, r14
0x180083008  call    IkeRevertImpersonation
0x18008300d  mov     rbx, rax
0x180083010  test    rax, rax
0x180083013  jnz     loc_180083243
0x180083019  cmp     r15d, 90320h
0x180083020  jnz     short loc_180083032
0x180083022  or      dword ptr [r14+48h], 20h
0x180083027  mov     r15d, 90312h
0x18008302d  jmp     loc_1800831AD
0x180083032  test    r15d, r15d
0x180083035  jz      loc_1800831AD
0x18008303b  cmp     r15d, 90312h
0x180083042  jz      loc_1800831AD
0x180083048  call    cs:__imp_GetLastError
0x18008304e  mov     [rbp+90h+fContextReq], eax
0x180083051  mov     rdi, cs:WPP_GLOBAL_Control
0x180083058  cmp     rdi, r13
0x18008305b  jz      loc_1800830EB
0x180083061  cmp     [rdi+19h], r12b
0x180083065  jb      short loc_1800830A8
0x180083067  test    byte ptr [rdi+1Ch], 10h
0x18008306b  jz      short loc_1800830A8
0x18008306d  mov     rdi, [rdi+10h]
0x180083071  call    IkeGetTlsPeerAddr
0x180083076  mov     rbx, rax
0x180083079  call    IkeGetTlsMmLuid
0x18008307e  mov     r9, rax
0x180083081  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180083088  mov     eax, [rbp+90h+fContextReq]
0x18008308b  mov     edx, 17h
0x180083090  mov     [rsp+190h+TargetDataRep], eax
0x180083094  mov     rcx, rdi
0x180083097  mov     qword ptr [rsp+190h+Reserved1], rbx
0x18008309c  call    WPP_SF_iSL
0x1800830a1  mov     rdi, cs:WPP_GLOBAL_Control
0x1800830a8  cmp     rdi, r13
0x1800830ab  jz      short loc_1800830EB
0x1800830ad  cmp     byte ptr [rdi+19h], 2
0x1800830b1  jb      short loc_1800830EB
0x1800830b3  test    byte ptr [rdi+1Ch], 10h
0x1800830b7  jz      short loc_1800830EB
0x1800830b9  mov     rdi, [rdi+10h]
0x1800830bd  call    IkeGetTlsPeerAddr
0x1800830c2  mov     rbx, rax
0x1800830c5  call    IkeGetTlsMmLuid
0x1800830ca  mov     r9, rax
0x1800830cd  mov     [rsp+190h+TargetDataRep], r15d
0x1800830d2  mov     edx, 18h
0x1800830d7  mov     qword ptr [rsp+190h+Reserved1], rbx
0x1800830dc  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x1800830e3  mov     rcx, rdi
0x1800830e6  call    WPP_SF_iSL
0x1800830eb  mov     eax, cs:dword_180173278
0x1800830f1  cmp     eax, r12d
0x1800830f4  jbe     loc_180083185
0x1800830fa  call    IkeGetTlsMmLuid
0x1800830ff  mov     [rbp+90h+var_C8], rax
0x180083103  lea     rax, [rbp+90h+var_C8]
0x180083107  mov     [rbp+90h+var_A0], rax
0x18008310b  mov     [rbp+90h+var_98], 8
0x180083113  call    IkeGetTlsPeerAddr
0x180083118  mov     rdx, rax
0x18008311b  lea     rcx, [rbp+90h+var_90]
0x18008311f  call    _tlgCreate1Sz_wchar_t
0x180083124  mov     eax, [rbp+90h+fContextReq]
0x180083127  lea     rcx, aIscFailed; "ISC failed"
0x18008312e  mov     [rbp+90h+var_E4], eax
0x180083131  lea     rdx, byte_180155B05
0x180083138  lea     rax, [rbp+90h+var_E4]
0x18008313c  mov     [rbp+90h+var_80], rcx
0x180083140  mov     [rbp+90h+var_70], rax
0x180083144  lea     rcx, dword_180173278
0x18008314b  lea     rax, [rbp+90h+var_E0]
0x18008314f  mov     [rbp+90h+var_78], 0Bh
0x180083157  mov     [rbp+90h+var_60], rax
0x18008315b  lea     rax, [rbp+90h+var_C0]
0x18008315f  mov     qword ptr [rsp+190h+TargetDataRep], rax
0x180083164  mov     [rsp+190h+Reserved1], 7
0x18008316c  mov     [rbp+90h+var_68], 4
0x180083174  mov     dword ptr [rbp+90h+var_E0], r15d
0x180083178  mov     [rbp+90h+var_58], 4
0x180083180  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180083185  mov     r8d, 1
0x18008318b  mov     edx, r15d
0x18008318e  mov     rcx, r14
0x180083191  call    SetSspiError
0x180083196  mov     rbx, rax
0x180083199  test    rax, rax
0x18008319c  jnz     loc_180083243
0x1800831a2  mov     rax, [r14+68h]
0x1800831a6  test    rax, rax
0x1800831a9  jz      short loc_1800831AD
0x1800831ab  mov     [rax], ebx
0x1800831ad  mov     rcx, [rbp+90h+var_118.pBuffers]
0x1800831b1  lea     rdx, aIscOuttoken; "ISC outtoken:"
0x1800831b8  mov     r8d, [rcx]
0x1800831bb  mov     rcx, [rcx+8]
0x1800831bf  call    IkeDumpSspiToken
0x1800831c4  test    r15d, r15d
0x1800831c7  jnz     short loc_180083225
0x1800831c9  mov     rcx, [r14+68h]
0x1800831cd  test    rcx, rcx
0x1800831d0  jz      short loc_1800831E4
0x1800831d2  mov     eax, [r14+48h]
  ... truncated ...
```
