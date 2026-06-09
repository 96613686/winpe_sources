# IkeProcessClearTextResponse

- ea: `0x1800217a0`
- end: `0x1800220b0`
- name: `IkeProcessClearTextResponse`
- size: `2320`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021770`
- `0x180021790`

## callees

- `0x1800061ec`
- `0x1800073d0`
- `0x180008388`
- `0x180011680`
- `0x180013500`
- `0x1800138f0`
- `0x1800217a0`
- `0x180026cb0`
- `0x180050850`
- `0x1800510ee`
- `0x18005bc40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800219cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180021a4e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800219cd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180021a4e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021863`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800218ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021aaa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021ae3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021b3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021b88`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021f15`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021f60`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021863`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800218ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021aaa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021ae3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021b3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021b88`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021f15`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180021f60`
- `ntdll!RtlIpv6AddressToStringW` at `0x180021a32`
- `ntdll!RtlIpv6AddressToStringW` at `0x180021a32`
- `ntdll!RtlIpv4AddressToStringW` at `0x180021a18`
- `ntdll!RtlIpv4AddressToStringW` at `0x180021a18`
- `ntdll!EtwEventWriteTransfer` at `0x1800219b1`
- `ntdll!EtwEventWriteTransfer` at `0x180021c83`
- `ntdll!EtwEventWriteTransfer` at `0x1800219b1`
- `ntdll!EtwEventWriteTransfer` at `0x180021c83`
- `WS2_32!__imp_htonl` at `0x180021cbf`
- `WS2_32!__imp_htonl` at `0x180021ccb`
- `WS2_32!__imp_htonl` at `0x180021cbf`
- `WS2_32!__imp_htonl` at `0x180021ccb`

## pseudocode

```c
__int64 __fastcall IkeProcessClearTextResponse(unsigned int a1, __int64 a2)
{
  int v4; // r8d
  __int64 v5; // rbx
  LPCRITICAL_SECTION v6; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v9; // rcx
  DWORD v10; // ecx
  char *v11; // rax
  const WCHAR *v12; // rdx
  __int64 v13; // rax
  bool v14; // zf
  int v15; // eax
  DWORD v16; // ecx
  DWORD v17; // ecx
  LPCRITICAL_SECTION v18; // rdx
  _QWORD *v19; // rcx
  DWORD v20; // eax
  LPVOID v21; // rax
  LPVOID v22; // r8
  __int64 v23; // rdi
  DWORD v24; // eax
  __int64 *v25; // rax
  __int64 v26; // r9
  __int64 result; // rax
  LPCRITICAL_SECTION v28; // rax
  DWORD v29; // ecx
  __int64 *v30; // rax
  __int64 v31; // rcx
  DWORD v32; // ecx
  char *v33; // rax
  const WCHAR *v34; // rdx
  int v35; // ebx
  struct in_addr v36; // r13d
  u_long v37; // r14d
  u_long v38; // eax
  __int64 v39; // rdx
  u_long v40; // r15d
  int v41; // r9d
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // xmm0_8
  __int64 v49; // rdx
  __int64 v50; // xmm0_8
  LPCRITICAL_SECTION v51; // rax
  DWORD v52; // ecx
  __int64 *v53; // rax
  __int64 v54; // rcx
  DWORD v55; // ecx
  char *v56; // rax
  const WCHAR *v57; // rdx
  int v58; // ebx
  struct in_addr Addr; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v60; // [rsp+40h] [rbp-C0h] BYREF
  char v61[8]; // [rsp+48h] [rbp-B8h] BYREF
  u_long v62; // [rsp+50h] [rbp-B0h]
  int v63; // [rsp+54h] [rbp-ACh]
  __int64 v64; // [rsp+58h] [rbp-A8h]
  int v65; // [rsp+60h] [rbp-A0h]
  char v66[8]; // [rsp+84h] [rbp-7Ch] BYREF
  u_long v67; // [rsp+8Ch] [rbp-74h]
  int v68; // [rsp+90h] [rbp-70h]
  __int64 v69; // [rsp+94h] [rbp-6Ch]
  int v70; // [rsp+9Ch] [rbp-64h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  int v72; // [rsp+C8h] [rbp-38h]
  _QWORD v73[2]; // [rsp+F0h] [rbp-10h] BYREF
  char TlsValue[8]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR S[84]; // [rsp+108h] [rbp+8h] BYREF
  struct in6_addr v76; // [rsp+1B0h] [rbp+B0h] BYREF
  char *v77; // [rsp+1C0h] [rbp+C0h] BYREF
  int v78; // [rsp+1C8h] [rbp+C8h]
  int v79; // [rsp+1CCh] [rbp+CCh]
  char *v80; // [rsp+1D0h] [rbp+D0h]
  int v81; // [rsp+1D8h] [rbp+D8h]
  int v82; // [rsp+1DCh] [rbp+DCh]
  _QWORD *v83; // [rsp+1E0h] [rbp+E0h]
  __int64 v84; // [rsp+1E8h] [rbp+E8h]
  const WCHAR *v85; // [rsp+1F0h] [rbp+F0h]
  int v86; // [rsp+1F8h] [rbp+F8h]
  int v87; // [rsp+1FCh] [rbp+FCh]
  const char *v88; // [rsp+200h] [rbp+100h]
  __int64 v89; // [rsp+208h] [rbp+108h]

  memset_0(TlsValue, 0, 0xA8u);
  memset_0(&v60, 0, 0xB0u);
  v5 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v6 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v6 = gIkeExtGlobals;
LABEL_9:
    v9 = 0;
    goto LABEL_10;
  }
  v9 = *Value;
  v6 = gIkeExtGlobals;
LABEL_10:
  v73[0] = v9;
  v83 = v73;
  v84 = 8;
  if ( !v6 )
    goto LABEL_18;
  v10 = (DWORD)v6[86].LockSemaphore;
  if ( v10 == -1 )
    goto LABEL_18;
  v11 = (char *)TlsGetValue(v10);
  v12 = (const WCHAR *)(v11 + 8);
  if ( !v11 )
    v12 = 0;
  if ( v12 )
  {
    v13 = -1;
    do
      v14 = v12[++v13] == 0;
    while ( !v14 );
    v15 = 2 * v13 + 2;
  }
  else
  {
LABEL_18:
    v12 = &LocaleName;
    v15 = 2;
  }
  v86 = v15;
  v77 = off_180173280;
  v85 = v12;
  v87 = 0;
  v88 = "IkeProcessClearTextResponse";
  v89 = 28;
  *(_QWORD *)v76.u.Byte = 0x50B000000LL;
  *(_QWORD *)&v76.u.Word[4] = 1;
  v78 = *(unsigned __int16 *)off_180173280;
  v80 = (char *)&dword_180166EA4;
  v79 = 2;
  v81 = 45;
  v82 = 1;
  Addr = (struct in_addr)((unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata);
  EtwEventWriteTransfer(qword_180173298, &v76, 0, 0, 5, &v77);
LABEL_20:
  v16 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v16 != -1 )
    TlsSetValue(v16, TlsValue);
  if ( (Microsoft_Windows_NetworkSecurityEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)FwxTraceProvider_Context,
      (unsigned int)SaContextOperationBeginEvent,
      v4,
      1,
      (__int64)&v76);
  if ( *(_DWORD *)a2 )
  {
    v76 = *(struct in6_addr *)(a2 + 20);
    RtlIpv6AddressToStringW(&v76, S);
  }
  else
  {
    Addr = (struct in_addr)_byteswap_ulong(*(_DWORD *)(a2 + 20));
    RtlIpv4AddressToStringW(&Addr, S);
  }
  v17 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v17 != -1 )
    TlsSetValue(v17, TlsValue);
  IkeLogClearTextResp(a1, a2);
  v18 = gIkeExtGlobals;
  if ( ((__int64)gIkeExtGlobals[50].LockSemaphore & 0x800) == 0 )
  {
    if ( !*(_DWORD *)a2 )
    {
      v37 = htonl(*(_DWORD *)(a2 + 4));
      v38 = htonl(*(_DWORD *)(a2 + 20));
      LOBYTE(v39) = 1;
      v40 = v38;
      IkeAddrInitialize(v61, v39);
      v41 = (unsigned __int8)v61[0] - 1;
      if ( (unsigned int)v41 <= 7 )
      {
        v42 = 0;
        switch ( v61[0] )
        {
          case 1:
          case 4:
          case 7:
            v62 = v37;
            goto LABEL_67;
          case 5:
          case 6:
          case 8:
            v42 = WfpReportSysErrorAsWinError(v41, "IkeAddrSetAddrBytes", 87, 1);
LABEL_67:
            IkeReturnError(v42, "IkeAddrSetAddrBytes");
            LOBYTE(v43) = 1;
            IkeAddrInitialize(v66, v43);
            if ( (unsigned int)(unsigned __int8)v66[0] - 1 <= 7 )
            {
              v45 = 0;
              switch ( v66[0] )
              {
                case 1:
                case 4:
                case 7:
                  v67 = v40;
                  goto LABEL_76;
                case 5:
                case 6:
                case 8:
                  goto LABEL_74;
                default:
                  goto LABEL_94;
              }
            }
            break;
          default:
            break;
        }
      }
LABEL_94:
      __fastfail(5u);
    }
    LOBYTE(v18) = 5;
    IkeAddrInitialize(v61, v18);
    v47 = 0;
    switch ( v61[0] )
    {
      case 1:
      case 4:
      case 7:
        v47 = WfpReportSysErrorAsWinError(v46, "IkeAddrSetAddrBytes", 87, 1);
        goto LABEL_73;
      case 5:
      case 6:
      case 8:
        v48 = *(_QWORD *)(a2 + 8);
        v63 = *(_DWORD *)(a2 + 4);
        v65 = *(_DWORD *)(a2 + 16);
        v64 = v48;
LABEL_73:
        IkeReturnError(v47, "IkeAddrSetAddrBytes");
        LOBYTE(v49) = 5;
        IkeAddrInitialize(v66, v49);
        v45 = 0;
        switch ( v66[0] )
        {
          case 1:
          case 4:
          case 7:
LABEL_74:
            v45 = WfpReportSysErrorAsWinError(v44, "IkeAddrSetAddrBytes", 87, 1);
            goto LABEL_76;
          case 5:
          case 6:
          case 8:
            v50 = *(_QWORD *)(a2 + 24);
            v68 = *(_DWORD *)(a2 + 20);
            v70 = *(_DWORD *)(a2 + 32);
            v69 = v50;
LABEL_76:
            IkeReturnError(v45, "IkeAddrSetAddrBytes");
            v71 = *(_QWORD *)(a2 + 48);
            v72 = *(_DWORD *)(a2 + 56);
            v60 = a1;
            IkePostClrTxtResponse(&v60);
            IkeTlsActivityEnd();
            result = (unsigned int)dword_180173278;
            if ( (unsigned int)dword_180173278 <= 5 )
              return result;
            result = qword_180173288;
            if ( (qword_180173288 & 1) == 0 )
              return result;
            result = qword_180173290 & 1;
            if ( result != qword_180173290 )
              return result;
            v51 = gIkeExtGlobals;
            if ( !gIkeExtGlobals )
              goto LABEL_84;
            v52 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
            if ( v52 == -1 )
              goto LABEL_84;
            v53 = (__int64 *)TlsGetValue(v52);
            if ( v53 )
            {
              v54 = *v53;
              v51 = gIkeExtGlobals;
            }
            else
            {
              v51 = gIkeExtGlobals;
LABEL_84:
              v54 = 0;
            }
            v73[0] = v54;
            v83 = v73;
            v84 = 8;
            if ( !v51 )
              goto LABEL_92;
            v55 = (DWORD)v51[86].LockSemaphore;
            if ( v55 == -1 )
              goto LABEL_92;
            v56 = (char *)TlsGetValue(v55);
            v57 = (const WCHAR *)(v56 + 8);
            if ( !v56 )
              v57 = 0;
            if ( v57 )
            {
              do
                v14 = v57[++v5] == 0;
              while ( !v14 );
              v58 = 2 * v5 + 2;
            }
            else
            {
LABEL_92:
              v57 = &LocaleName;
              v58 = 2;
            }
            v77 = off_180173280;
            v85 = v57;
            v86 = v58;
            v87 = 0;
            v88 = "IkeProcessClearTextResponse";
            v89 = 28;
            *(_QWORD *)v76.u.Byte = 0x50B000000LL;
            *(_QWORD *)&v76.u.Word[4] = 1;
            v78 = *(unsigned __int16 *)off_180173280;
            v80 = byte_180166E6B;
            v36 = (struct in_addr)((unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata);
            v81 = 45;
            break;
          default:
            goto LABEL_94;
        }
        goto LABEL_60;
      default:
        goto LABEL_94;
    }
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v20 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
    if ( v20 == -1 )
    {
      v22 = 0;
    }
    else
    {
      v21 = TlsGetValue(v20);
      v18 = gIkeExtGlobals;
      v22 = v21;
      v19 = WPP_GLOBAL_Control;
    }
    v23 = (__int64)v22 + 8;
    if ( !v22 )
      v23 = 0;
    if ( v18
      && (v24 = (DWORD)v18[86].LockSemaphore, v24 != -1)
      && (v25 = (__int64 *)TlsGetValue(v24), v19 = WPP_GLOBAL_Control, v25) )
    {
      v26 = *v25;
    }
    else
    {
      LODWORD(v26) = 0;
    }
    WPP_SF_iS(v19[2], 16, (unsigned int)WPP_cc00778c82d836298410d94d06f43a3d_Traceguids, v26, v23);
  }
  result = (unsigned int)dword_180173278;
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v28 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v29 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v29 != -1 )
      {
        v30 = (__int64 *)TlsGetValue(v29);
        if ( v30 )
        {
          v31 = *v30;
          v28 = gIkeExtGlobals;
          goto LABEL_51;
        }
        v28 = gIkeExtGlobals;
      }
    }
    v31 = 0;
LABEL_51:
    v73[0] = v31;
    v83 = v73;
    v84 = 8;
    if ( !v28 )
      goto LABEL_58;
    v32 = (DWORD)v28[86].LockSemaphore;
    if ( v32 == -1 )
      goto LABEL_58;
    v33 = (char *)TlsGetValue(v32);
    v34 = (const WCHAR *)(v33 + 8);
    if ( !v33 )
      v34 = 0;
    if ( v34 )
    {
      do
        v14 = v34[++v5] == 0;
      while ( !v14 );
      v35 = 2 * v5 + 2;
    }
    else
    {
LABEL_58:
      v34 = &LocaleName;
      v35 = 2;
    }
    v85 = v34;
    v88 = "Ignoring clear-text response notify,             because disable-ND-retrans-shutoff regkey is set";
    v36 = (struct in_addr)((unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata);
    v77 = off_180173280;
    v86 = v35;
    v87 = 0;
    v89 = 98;
    v76 = (struct in6_addr)0x40B000000uLL;
    v78 = *(unsigned __int16 *)off_180173280;
    v80 = &byte_18014FE5F;
    v81 = 62;
LABEL_60:
    v82 = 1;
    v79 = 2;
    Addr = v36;
    return EtwEventWriteTransfer(qword_180173298, &v76, 0, 0, 5, &v77);
  }
  return result;
}

```

## disassembly

```asm
0x1800217a0  mov     [rsp-8+arg_10], rbx
0x1800217a5  push    rbp
0x1800217a6  push    rsi
0x1800217a7  push    rdi
0x1800217a8  push    r12
0x1800217aa  push    r13
0x1800217ac  push    r14
0x1800217ae  push    r15
0x1800217b0  lea     rbp, [rsp-120h]
0x1800217b8  sub     rsp, 220h
0x1800217bf  mov     rax, cs:__security_cookie
0x1800217c6  xor     rax, rsp
0x1800217c9  mov     [rbp+150h+var_40], rax
0x1800217d0  mov     rdi, rdx
0x1800217d3  mov     r12d, ecx
0x1800217d6  xor     edx, edx; Val
0x1800217d8  lea     rcx, [rbp+150h+TlsValue]; void *
0x1800217dc  mov     r8d, 0A8h; Size
0x1800217e2  call    memset_0
0x1800217e7  xor     edx, edx; Val
0x1800217e9  lea     rcx, [rsp+250h+var_210]; void *
0x1800217ee  mov     r8d, 0B0h; Size
0x1800217f4  call    memset_0
0x1800217f9  mov     eax, cs:dword_180173278
0x1800217ff  lea     r15, aIkeprocessclea; "IkeProcessClearTextResponse"
0x180021806  xor     r14d, r14d
0x180021809  lea     r13, _TraceLoggingMetadataEnd
0x180021810  lea     rsi, _TraceLoggingMetadata
0x180021817  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002181e  cmp     eax, 5
0x180021821  jbe     loc_1800219B7
0x180021827  mov     rcx, cs:qword_180173290
0x18002182e  mov     rax, cs:qword_180173288
0x180021835  test    al, 1
0x180021837  jz      loc_1800219B7
0x18002183d  mov     rax, rcx
0x180021840  and     eax, 1
0x180021843  cmp     rax, rcx
0x180021846  jnz     loc_1800219B7
0x18002184c  mov     rax, cs:gIkeExtGlobals
0x180021853  test    rax, rax
0x180021856  jz      short loc_180021881
0x180021858  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002185e  cmp     ecx, 0FFFFFFFFh
0x180021861  jz      short loc_180021881
0x180021863  call    cs:__imp_TlsGetValue
0x180021869  test    rax, rax
0x18002186c  jz      short loc_18002187A
0x18002186e  mov     rcx, [rax]
0x180021871  mov     rax, cs:gIkeExtGlobals
0x180021878  jmp     short loc_180021884
0x18002187a  mov     rax, cs:gIkeExtGlobals
0x180021881  mov     rcx, r14
0x180021884  mov     [rbp+150h+var_160], rcx
0x180021888  lea     rcx, [rbp+150h+var_160]
0x18002188c  mov     [rbp+150h+var_70], rcx
0x180021893  mov     [rbp+150h+var_68], 8
0x18002189e  test    rax, rax
0x1800218a1  jz      short loc_1800218E5
0x1800218a3  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800218a9  cmp     ecx, 0FFFFFFFFh
0x1800218ac  jz      short loc_1800218E5
0x1800218ae  call    cs:__imp_TlsGetValue
0x1800218b4  test    rax, rax
0x1800218b7  lea     rdx, [rax+8]
0x1800218bb  cmovz   rdx, r14
0x1800218bf  test    rdx, rdx
0x1800218c2  jz      short loc_1800218E5
0x1800218c4  mov     rax, rbx
0x1800218c7  nop     word ptr [rax+rax+00000000h]
0x1800218d0  cmp     [rdx+rax*2+2], r14w
0x1800218d6  lea     rax, [rax+1]
0x1800218da  jnz     short loc_1800218D0
0x1800218dc  lea     eax, ds:2[rax*2]
0x1800218e3  jmp     short loc_1800218F1
0x1800218e5  lea     rdx, LocaleName
0x1800218ec  mov     eax, 2
0x1800218f1  mov     [rbp+150h+var_58], eax
0x1800218f7  xor     r9d, r9d
0x1800218fa  movzx   eax, cs:word_180166E9A
0x180021901  xor     r8d, r8d
0x180021904  mov     dword ptr [rbp+150h+var_A0.u+4], eax
0x18002190a  mov     rax, cs:off_180173280
0x180021911  mov     [rbp+150h+var_90], rax
0x180021918  mov     [rbp+150h+var_60], rdx
0x18002191f  lea     rdx, [rbp+150h+var_A0]
0x180021926  mov     [rbp+150h+var_54], r14d
0x18002192d  mov     [rbp+150h+var_50], r15
0x180021934  mov     [rbp+150h+var_48], 1Ch
0x18002193f  mov     dword ptr [rbp+150h+var_A0.u], 0B000000h
0x180021949  mov     qword ptr [rbp+150h+var_A0.u+8], 1
0x180021954  movzx   eax, word ptr [rax]
0x180021957  mov     [rbp+150h+var_88], eax
0x18002195d  lea     rax, dword_180166EA4
0x180021964  mov     [rbp+150h+var_80], rax
0x18002196b  mov     rax, r13
0x18002196e  sub     eax, esi
0x180021970  mov     [rbp+150h+var_84], 2
0x18002197a  mov     [rbp+150h+var_78], 2Dh ; '-'
0x180021984  mov     [rbp+150h+var_74], 1
0x18002198e  mov     dword ptr [rsp+250h+Addr.S_un], eax
0x180021992  mov     eax, dword ptr [rsp+250h+Addr.S_un]
0x180021996  mov     rcx, cs:qword_180173298
0x18002199d  lea     rax, [rbp+150h+var_90]
0x1800219a4  mov     [rsp+250h+var_228], rax
0x1800219a9  mov     dword ptr [rsp+250h+var_230], 5
0x1800219b1  call    cs:__imp_EtwEventWriteTransfer
0x1800219b7  mov     rax, cs:gIkeExtGlobals
0x1800219be  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800219c4  cmp     ecx, 0FFFFFFFFh
0x1800219c7  jz      short loc_1800219D3
0x1800219c9  lea     rdx, [rbp+150h+TlsValue]; lpTlsValue
0x1800219cd  call    cs:__imp_TlsSetValue
0x1800219d3  test    byte ptr cs:Microsoft_Windows_NetworkSecurityEnableBits, 1
0x1800219da  jz      short loc_180021A01
0x1800219dc  lea     rax, [rbp+150h+var_A0]
0x1800219e3  mov     r9d, 1
0x1800219e9  lea     rdx, SaContextOperationBeginEvent
0x1800219f0  mov     [rsp+250h+var_230], rax
0x1800219f5  lea     rcx, FwxTraceProvider_Context
0x1800219fc  call    McGenEventWrite_EtwEventWriteTransfer
0x180021a01  lea     rdx, [rbp+150h+S]; S
0x180021a05  cmp     [rdi], r14d
0x180021a08  jnz     short loc_180021A20
0x180021a0a  mov     eax, [rdi+14h]
0x180021a0d  lea     rcx, [rsp+250h+Addr]; Addr
0x180021a12  bswap   eax
0x180021a14  mov     dword ptr [rsp+250h+Addr.S_un], eax
0x180021a18  call    cs:__imp_RtlIpv4AddressToStringW
0x180021a1e  jmp     short loc_180021A38
0x180021a20  movups  xmm0, xmmword ptr [rdi+14h]
0x180021a24  lea     rcx, [rbp+150h+var_A0]; Addr
0x180021a2b  movups  xmmword ptr [rbp+150h+var_A0.u], xmm0
0x180021a32  call    cs:__imp_RtlIpv6AddressToStringW
0x180021a38  mov     rax, cs:gIkeExtGlobals
0x180021a3f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180021a45  cmp     ecx, 0FFFFFFFFh
0x180021a48  jz      short loc_180021A54
0x180021a4a  lea     rdx, [rbp+150h+TlsValue]; lpTlsValue
0x180021a4e  call    cs:__imp_TlsSetValue
0x180021a54  mov     rdx, rdi
0x180021a57  mov     ecx, r12d
0x180021a5a  call    IkeLogClearTextResp
0x180021a5f  mov     rdx, cs:gIkeExtGlobals
0x180021a66  test    dword ptr [rdx+7E8h], 800h
0x180021a70  jz      loc_180021CB3
0x180021a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a7d  lea     rax, WPP_GLOBAL_Control
0x180021a84  cmp     rcx, rax
0x180021a87  jz      loc_180021B17
0x180021a8d  cmp     byte ptr [rcx+19h], 4
0x180021a91  jb      loc_180021B17
0x180021a97  test    byte ptr [rcx+1Ch], 10h
0x180021a9b  jz      short loc_180021B17
0x180021a9d  mov     eax, [rdx+0D88h]
0x180021aa3  cmp     eax, 0FFFFFFFFh
0x180021aa6  jz      short loc_180021AC3
0x180021aa8  mov     ecx, eax; dwTlsIndex
0x180021aaa  call    cs:__imp_TlsGetValue
0x180021ab0  mov     rdx, cs:gIkeExtGlobals
0x180021ab7  mov     r8, rax
0x180021aba  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ac1  jmp     short loc_180021AC6
0x180021ac3  mov     r8, r14
0x180021ac6  test    r8, r8
0x180021ac9  lea     rdi, [r8+8]
0x180021acd  cmovz   rdi, r14
0x180021ad1  test    rdx, rdx
0x180021ad4  jz      short loc_180021AFA
0x180021ad6  mov     eax, [rdx+0D88h]
0x180021adc  cmp     eax, 0FFFFFFFFh
0x180021adf  jz      short loc_180021AFA
0x180021ae1  mov     ecx, eax; dwTlsIndex
0x180021ae3  call    cs:__imp_TlsGetValue
0x180021ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x180021af0  test    rax, rax
0x180021af3  jz      short loc_180021AFA
0x180021af5  mov     r9, [rax]
0x180021af8  jmp     short loc_180021AFD
0x180021afa  mov     r9, r14
0x180021afd  mov     rcx, [rcx+10h]
0x180021b01  lea     r8, WPP_cc00778c82d836298410d94d06f43a3d_Traceguids
0x180021b08  mov     edx, 10h
0x180021b0d  mov     [rsp+250h+var_230], rdi
0x180021b12  call    WPP_SF_iS
0x180021b17  mov     eax, cs:dword_180173278
0x180021b1d  cmp     eax, 4
0x180021b20  jbe     loc_180021C89
0x180021b26  mov     rax, cs:gIkeExtGlobals
0x180021b2d  test    rax, rax
0x180021b30  jz      short loc_180021B5B
0x180021b32  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180021b38  cmp     ecx, 0FFFFFFFFh
0x180021b3b  jz      short loc_180021B5B
0x180021b3d  call    cs:__imp_TlsGetValue
0x180021b43  test    rax, rax
0x180021b46  jz      short loc_180021B54
0x180021b48  mov     rcx, [rax]
0x180021b4b  mov     rax, cs:gIkeExtGlobals
0x180021b52  jmp     short loc_180021B5E
0x180021b54  mov     rax, cs:gIkeExtGlobals
0x180021b5b  mov     rcx, r14
0x180021b5e  mov     [rbp+150h+var_160], rcx
0x180021b62  lea     rcx, [rbp+150h+var_160]
0x180021b66  mov     [rbp+150h+var_70], rcx
0x180021b6d  mov     [rbp+150h+var_68], 8
0x180021b78  test    rax, rax
0x180021b7b  jz      short loc_180021BB5
0x180021b7d  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180021b83  cmp     ecx, 0FFFFFFFFh
0x180021b86  jz      short loc_180021BB5
0x180021b88  call    cs:__imp_TlsGetValue
0x180021b8e  test    rax, rax
0x180021b91  lea     rdx, [rax+8]
0x180021b95  cmovz   rdx, r14
0x180021b99  test    rdx, rdx
0x180021b9c  jz      short loc_180021BB5
0x180021b9e  xchg    ax, ax
0x180021ba0  cmp     [rdx+rbx*2+2], r14w
0x180021ba6  lea     rbx, [rbx+1]
0x180021baa  jnz     short loc_180021BA0
0x180021bac  lea     ebx, ds:2[rbx*2]
0x180021bb3  jmp     short loc_180021BC1
0x180021bb5  lea     rdx, LocaleName
0x180021bbc  mov     ebx, 2
0x180021bc1  lea     rax, aIgnoringClearT; "Ignoring clear-text response notify,   "...
0x180021bc8  mov     [rbp+150h+var_60], rdx
0x180021bcf  mov     [rbp+150h+var_50], rax
0x180021bd6  sub     r13d, esi
0x180021bd9  movzx   eax, cs:word_18014FE55
0x180021be0  mov     dword ptr [rbp+150h+var_A0.u+4], eax
0x180021be6  mov     rax, cs:off_180173280
0x180021bed  mov     [rbp+150h+var_90], rax
0x180021bf4  mov     [rbp+150h+var_58], ebx
0x180021bfa  mov     [rbp+150h+var_54], r14d
0x180021c01  mov     [rbp+150h+var_48], 62h ; 'b'
0x180021c0c  mov     dword ptr [rbp+150h+var_A0.u], 0B000000h
0x180021c16  mov     qword ptr [rbp+150h+var_A0.u+8], r14
0x180021c1d  movzx   eax, word ptr [rax]
0x180021c20  mov     [rbp+150h+var_88], eax
0x180021c26  lea     rax, byte_18014FE5F
0x180021c2d  mov     [rbp+150h+var_80], rax
0x180021c34  mov     [rbp+150h+var_78], 3Eh ; '>'
0x180021c3e  mov     [rbp+150h+var_74], 1
0x180021c48  lea     rdx, [rbp+150h+var_A0]
0x180021c4f  mov     [rbp+150h+var_84], 2
0x180021c59  xor     r9d, r9d
0x180021c5c  mov     dword ptr [rsp+250h+Addr.S_un], r13d
0x180021c61  xor     r8d, r8d
0x180021c64  mov     eax, dword ptr [rsp+250h+Addr.S_un]
0x180021c68  mov     rcx, cs:qword_180173298
0x180021c6f  lea     rax, [rbp+150h+var_90]
0x180021c76  mov     [rsp+250h+var_228], rax
0x180021c7b  mov     dword ptr [rsp+250h+var_230], 5
0x180021c83  call    cs:__imp_EtwEventWriteTransfer
0x180021c89  mov     rcx, [rbp+150h+var_40]
0x180021c90  xor     rcx, rsp; StackCookie
0x180021c93  call    __security_check_cookie
0x180021c98  mov     rbx, [rsp+250h+arg_10]
0x180021ca0  add     rsp, 220h
0x180021ca7  pop     r15
0x180021ca9  pop     r14
0x180021cab  pop     r13
0x180021cad  pop     r12
0x180021caf  pop     rdi
0x180021cb0  pop     rsi
0x180021cb1  pop     rbp
0x180021cb2  retn
0x180021cb3  cmp     [rdi], r14d
0x180021cb6  jnz     loc_180021DBA
0x180021cbc  mov     ecx, [rdi+4]; hostlong
0x180021cbf  call    cs:__imp_htonl
0x180021cc5  mov     ecx, [rdi+14h]; hostlong
0x180021cc8  mov     r14d, eax
0x180021ccb  call    cs:__imp_htonl
0x180021cd1  mov     dl, 1
0x180021cd3  lea     rcx, [rsp+250h+var_208]
0x180021cd8  mov     r15d, eax
0x180021cdb  call    IkeAddrInitialize
0x180021ce0  movzx   r9d, [rsp+250h+var_208]
0x180021ce6  dec     r9d; switch 8 cases
0x180021ce9  cmp     r9d, 7
0x180021ced  ja      def_180021D14; jumptable 0000000180021D14 default case, cases 2,3
0x180021cf3  xor     r8d, r8d
0x180021cf6  cmp     r9d, 7
0x180021cfa  ja      def_180021D14; jumptable 0000000180021D14 default case, cases 2,3
0x180021d00  lea     rsi, __ImageBase
0x180021d07  movsxd  rcx, r9d
0x180021d0a  mov     eax, ds:(jpt_180021D14 - 180000000h)[rsi+rcx*4]
0x180021d11  add     rax, rsi
0x180021d14  jmp     rax; switch jump
0x180021d16  mov     [rsp+250h+var_200], r14d; jumptable 0000000180021D14 cases 1,4,7
0x180021d1b  jmp     short loc_180021D38
0x180021d1d  mov     r9d, 1; jumptable 0000000180021D14 cases 5,6,8
0x180021d23  lea     rdx, aIkeaddrsetaddr_0; "IkeAddrSetAddrBytes"
0x180021d2a  mov     r8d, 57h ; 'W'
0x180021d30  call    WfpReportSysErrorAsWinError
0x180021d35  mov     r8, rax
0x180021d38  lea     rdx, aIkeaddrsetaddr_0; "IkeAddrSetAddrBytes"
0x180021d3f  mov     rcx, r8
  ... truncated ...
```
