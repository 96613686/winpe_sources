# NetpWkstarClientCertificateMappingGet

- ea: `0x180021ad0`
- end: `0x180021fe5`
- name: `NetpWkstarClientCertificateMappingGet`
- size: `1301`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180008950`
- `0x1800089d0`
- `0x180009a40`
- `0x180021ad0`
- `0x1800224e8`
- `0x180022b54`
- `0x180022d8c`
- `0x180023284`
- `0x180033159`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180021b68`
- `ntdll!RtlAcquireResourceExclusive` at `0x180021b68`
- `ntdll!RtlReleaseResource` at `0x180021f58`
- `ntdll!RtlReleaseResource` at `0x180021f58`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021ba7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021d52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021d95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021dda`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021e1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021e64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021ba7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021d52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021d95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021dda`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021e1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021e64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021fad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021fbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021fad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021fbc`

## string_xrefs

- `0x180021b38`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetpWkstarClientCertificateMappingGet(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _DWORD *a7,
        HLOCAL *a8)
{
  unsigned int v9; // ebx
  HLOCAL *v11; // rdi
  int v12; // ebp
  unsigned int v13; // r15d
  __int64 v14; // rsi
  _UNKNOWN **v15; // r10
  unsigned __int16 *v16; // rax
  int v17; // ecx
  int v18; // edx
  unsigned __int16 *v19; // rax
  int v20; // ecx
  int v21; // edx
  unsigned __int16 *v22; // rax
  int v23; // ecx
  int v24; // edx
  unsigned __int16 *v25; // rax
  int v26; // ecx
  int v27; // edx
  __int64 v28; // rax
  SIZE_T v29; // rbx
  HLOCAL v30; // rax
  __int64 v31; // rax
  SIZE_T v32; // rbx
  HLOCAL v33; // rax
  __int64 v34; // rax
  SIZE_T v35; // rbx
  HLOCAL v36; // rax
  __int64 v37; // rax
  SIZE_T v38; // rbx
  HLOCAL v39; // rax
  __int64 v40; // rax
  SIZE_T v41; // rbx
  HLOCAL v42; // rax
  HLOCAL v43; // rcx
  HLOCAL v44; // rcx
  HLOCAL v45; // rcx
  HLOCAL v46; // rcx
  HLOCAL v47; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
  }
  v9 = 0;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  RtlAcquireResourceExclusive(&stru_18004EB90, 1u);
  if ( a6 )
  {
    v11 = 0;
    v9 = 775;
  }
  else
  {
    v11 = (HLOCAL *)LocalAlloc(0x40u, 96LL * *(unsigned int *)(*((_QWORD *)hMem + 1) + 4LL));
    if ( v11 )
    {
      v12 = 0;
      v13 = 0;
      v14 = *(_QWORD *)(*((_QWORD *)hMem + 1) + 8LL);
      *a8 = v11;
      v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
      while ( v13 < *(_DWORD *)(*((_QWORD *)hMem + 1) + 4LL) )
      {
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 2u )
        {
          WPP_SF_SSSS((TRACEHANDLE)v15[2], a3, a4, a5);
          v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
        }
        v16 = (unsigned __int16 *)a2;
        if ( !a2 )
          goto LABEL_34;
        do
        {
          v17 = *(unsigned __int16 *)((char *)v16 + *(_QWORD *)v14 - a2);
          v18 = *v16 - v17;
          if ( v18 )
            break;
          ++v16;
        }
        while ( v17 );
        if ( !v18 )
        {
LABEL_34:
          v19 = (unsigned __int16 *)a3;
          if ( !a3 )
            goto LABEL_82;
          do
          {
            v20 = *(unsigned __int16 *)((char *)v19 + *(_QWORD *)(v14 + 8) - a3);
            v21 = *v19 - v20;
            if ( v21 )
              break;
            ++v19;
          }
          while ( v20 );
          if ( !v21 )
          {
LABEL_82:
            if ( !a4 )
              goto LABEL_83;
            v22 = (unsigned __int16 *)a4;
            do
            {
              v23 = *(unsigned __int16 *)((char *)v22 + *(_QWORD *)(v14 + 24) - a4);
              v24 = *v22 - v23;
              if ( v24 )
                break;
              ++v22;
            }
            while ( v23 );
            if ( !v24 )
            {
LABEL_83:
              if ( !a5 )
                goto LABEL_37;
              v25 = (unsigned __int16 *)a5;
              do
              {
                v26 = *(unsigned __int16 *)((char *)v25 + *(_QWORD *)(v14 + 32) - a5);
                v27 = *v25 - v26;
                if ( v27 )
                  break;
                ++v25;
              }
              while ( v26 );
              if ( !v27 )
              {
LABEL_37:
                if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 2u )
                  WPP_SF_(v15[2], 75, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
                v28 = -1;
                do
                  ++v28;
                while ( *(_WORD *)(*(_QWORD *)v14 + 2 * v28) );
                v29 = 2 * v28 + 2;
                v30 = LocalAlloc(0x40u, v29);
                *v11 = v30;
                if ( !v30 )
                  goto LABEL_10;
                memcpy_0(v30, *(const void **)v14, v29);
                v31 = -1;
                do
                  ++v31;
                while ( *(_WORD *)(*(_QWORD *)(v14 + 8) + 2 * v31) );
                v32 = 2 * v31 + 2;
                v33 = LocalAlloc(0x40u, v32);
                v11[1] = v33;
                if ( !v33 )
                  goto LABEL_10;
                memcpy_0(v33, *(const void **)(v14 + 8), v32);
                v34 = -1;
                do
                  ++v34;
                while ( *(_WORD *)(*(_QWORD *)(v14 + 24) + 2 * v34) );
                v35 = 2 * v34 + 2;
                v36 = LocalAlloc(0x40u, v35);
                v11[3] = v36;
                if ( !v36 )
                  goto LABEL_10;
                memcpy_0(v36, *(const void **)(v14 + 24), v35);
                v37 = -1;
                do
                  ++v37;
                while ( *(_WORD *)(*(_QWORD *)(v14 + 64) + 2 * v37) );
                v38 = 2 * v37 + 2;
                v39 = LocalAlloc(0x40u, v38);
                v11[8] = v39;
                if ( !v39 )
                  goto LABEL_10;
                memcpy_0(v39, *(const void **)(v14 + 64), v38);
                v40 = -1;
                do
                  ++v40;
                while ( *(_WORD *)(*(_QWORD *)(v14 + 32) + 2 * v40) );
                v41 = 2 * v40 + 2;
                v42 = LocalAlloc(0x40u, v41);
                v11[4] = v42;
                if ( !v42 )
                  goto LABEL_10;
                memcpy_0(v42, *(const void **)(v14 + 32), v41);
                *((_DWORD *)v11 + 20) = *(_DWORD *)(v14 + 80);
                *((_DWORD *)v11 + 21) = *(_DWORD *)(v14 + 84);
                *((_DWORD *)v11 + 22) = *(_DWORD *)(v14 + 88);
                v9 = WsImpersonateClient2("NetpWkstarClientCertificateMappingGet", 240);
                if ( v9 )
                  goto LABEL_62;
                PopulateRenewalChain((__int64)v11);
                WsRevertToSelf2("NetpWkstarClientCertificateMappingGet", 2549);
                v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_SSSSSdd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    (__int64)v11[1],
                    (__int64)v11[3],
                    (__int64)v11[4],
                    (__int64)v11[8],
                    *((_DWORD *)v11 + 20),
                    *((_DWORD *)v11 + 21));
                  v15 = (_UNKNOWN **)WPP_GLOBAL_Control;
                }
                ++v12;
                v11 += 12;
              }
            }
          }
        }
        v14 += 96;
        ++v13;
      }
      *a7 = v12;
    }
    else
    {
LABEL_10:
      v9 = 8;
    }
  }
LABEL_62:
  RtlReleaseResource(&stru_18004EB90);
  if ( v9 && v11 )
  {
    while ( v11 != *a8 )
    {
      if ( *v11 )
        LocalFree(*v11);
      v43 = v11[1];
      if ( v43 )
        LocalFree(v43);
      v44 = v11[3];
      if ( v44 )
        LocalFree(v44);
      v45 = v11[8];
      if ( v45 )
        LocalFree(v45);
      v46 = v11[4];
      if ( v46 )
        LocalFree(v46);
      v47 = v11[9];
      if ( v47 )
        LocalFree(v47);
      v11 -= 12;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180021ad0  mov     [rsp+arg_0], rbx
0x180021ad5  mov     [rsp+arg_10], r8
0x180021ada  mov     [rsp+arg_8], rdx
0x180021adf  push    rbp
0x180021ae0  push    rsi
0x180021ae1  push    rdi
0x180021ae2  push    r12
0x180021ae4  push    r13
0x180021ae6  push    r14
0x180021ae8  push    r15
0x180021aea  sub     rsp, 50h
0x180021aee  mov     r13, r9
0x180021af1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180021af8  lea     rax, WPP_GLOBAL_Control
0x180021aff  cmp     rcx, rax
0x180021b02  jz      short loc_180021B25
0x180021b04  test    byte ptr [rcx+1Ch], 2
0x180021b08  jz      short loc_180021B25
0x180021b0a  cmp     byte ptr [rcx+19h], 2
0x180021b0e  jb      short loc_180021B25
0x180021b10  mov     rcx, [rcx+10h]
0x180021b14  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180021b1b  mov     edx, 49h ; 'I'
0x180021b20  call    WPP_SF_
0x180021b25  mov     rax, cs:ConfigurationInfoSd
0x180021b2c  lea     rcx, WsConfigInfoMapping
0x180021b33  mov     [rsp+88h+var_58], rcx
0x180021b38  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x180021b3f  mov     dword ptr [rsp+88h+var_60], 2
0x180021b47  mov     [rsp+88h+var_68], rax
0x180021b4c  call    NetpAccessCheckAndAuditEx
0x180021b51  xor     ebx, ebx
0x180021b53  test    eax, eax
0x180021b55  jz      short loc_180021B5F
0x180021b57  lea     eax, [rbx+5]
0x180021b5a  jmp     loc_180021FCD
0x180021b5f  mov     dl, 1; Wait
0x180021b61  lea     rcx, stru_18004EB90; Resource
0x180021b68  call    cs:__imp_RtlAcquireResourceExclusive
0x180021b6e  mov     r14, [rsp+88h+arg_38]
0x180021b76  cmp     [rsp+88h+arg_28], ebx
0x180021b7d  jz      short loc_180021B8C
0x180021b7f  mov     rdi, rbx
0x180021b82  mov     ebx, 307h
0x180021b87  jmp     loc_180021F51
0x180021b8c  mov     rax, cs:hMem
0x180021b93  mov     rcx, [rax+8]
0x180021b97  mov     eax, [rcx+4]
0x180021b9a  mov     ecx, 40h ; '@'; uFlags
0x180021b9f  lea     rdx, [rax+rax*2]
0x180021ba3  shl     rdx, 5; uBytes
0x180021ba7  call    cs:__imp_LocalAlloc
0x180021bad  xor     r9d, r9d
0x180021bb0  mov     rdi, rax
0x180021bb3  test    rax, rax
0x180021bb6  jnz     short loc_180021BC2
0x180021bb8  mov     ebx, 8
0x180021bbd  jmp     loc_180021F51
0x180021bc2  mov     rax, cs:hMem
0x180021bc9  mov     ebp, r9d
0x180021bcc  mov     r12, [rsp+88h+arg_20]
0x180021bd4  mov     r15d, r9d
0x180021bd7  mov     rcx, [rax+8]
0x180021bdb  mov     rsi, [rcx+8]
0x180021bdf  mov     [r14], rdi
0x180021be2  mov     r10, cs:WPP_GLOBAL_Control
0x180021be9  mov     rax, cs:hMem
0x180021bf0  mov     rcx, [rax+8]
0x180021bf4  cmp     r15d, [rcx+4]
0x180021bf8  jnb     loc_180021F47
0x180021bfe  lea     r11, WPP_GLOBAL_Control; __annotation("TMF:",
0x180021c05  cmp     r10, r11
0x180021c08  jz      short loc_180021C51
0x180021c0a  test    byte ptr [r10+1Ch], 2
0x180021c0f  jz      short loc_180021C51
0x180021c11  cmp     byte ptr [r10+19h], 2
0x180021c16  jb      short loc_180021C51
0x180021c18  mov     rax, [rsp+88h+arg_10]
0x180021c20  mov     r9, [rsp+88h+arg_8]
0x180021c28  mov     rcx, [r10+10h]; LoggerHandle
0x180021c2c  mov     [rsp+88h+var_58], r12; __int64
0x180021c31  mov     [rsp+88h+var_60], r13; __int64
0x180021c36  mov     [rsp+88h+var_68], rax; __int64
0x180021c3b  call    WPP_SF_SSSS
0x180021c40  mov     r10, cs:WPP_GLOBAL_Control
0x180021c47  lea     r11, WPP_GLOBAL_Control
0x180021c4e  xor     r9d, r9d
0x180021c51  mov     rax, [rsp+88h+arg_8]
0x180021c59  test    rax, rax
0x180021c5c  jz      short loc_180021C80
0x180021c5e  mov     r8, [rsi]
0x180021c61  sub     r8, rax
0x180021c64  movzx   edx, word ptr [rax]
0x180021c67  movzx   ecx, word ptr [rax+r8]
0x180021c6c  sub     edx, ecx
0x180021c6e  jnz     short loc_180021C78
0x180021c70  add     rax, 2
0x180021c74  test    ecx, ecx
0x180021c76  jnz     short loc_180021C64
0x180021c78  test    edx, edx
0x180021c7a  jnz     loc_180021F3B
0x180021c80  mov     rax, [rsp+88h+arg_10]
0x180021c88  test    rax, rax
0x180021c8b  jz      short loc_180021CB0
0x180021c8d  mov     r8, [rsi+8]
0x180021c91  sub     r8, rax
0x180021c94  movzx   edx, word ptr [rax]
0x180021c97  movzx   ecx, word ptr [rax+r8]
0x180021c9c  sub     edx, ecx
0x180021c9e  jnz     short loc_180021CA8
0x180021ca0  add     rax, 2
0x180021ca4  test    ecx, ecx
0x180021ca6  jnz     short loc_180021C94
0x180021ca8  test    edx, edx
0x180021caa  jnz     loc_180021F3B
0x180021cb0  test    r13, r13
0x180021cb3  jz      short loc_180021CDB
0x180021cb5  mov     r8, [rsi+18h]
0x180021cb9  mov     rax, r13
0x180021cbc  sub     r8, r13
0x180021cbf  movzx   edx, word ptr [rax]
0x180021cc2  movzx   ecx, word ptr [rax+r8]
0x180021cc7  sub     edx, ecx
0x180021cc9  jnz     short loc_180021CD3
0x180021ccb  add     rax, 2
0x180021ccf  test    ecx, ecx
0x180021cd1  jnz     short loc_180021CBF
0x180021cd3  test    edx, edx
0x180021cd5  jnz     loc_180021F3B
0x180021cdb  test    r12, r12
0x180021cde  jz      short loc_180021D06
0x180021ce0  mov     r8, [rsi+20h]
0x180021ce4  mov     rax, r12
0x180021ce7  sub     r8, r12
0x180021cea  movzx   edx, word ptr [rax]
0x180021ced  movzx   ecx, word ptr [rax+r8]
0x180021cf2  sub     edx, ecx
0x180021cf4  jnz     short loc_180021CFE
0x180021cf6  add     rax, 2
0x180021cfa  test    ecx, ecx
0x180021cfc  jnz     short loc_180021CEA
0x180021cfe  test    edx, edx
0x180021d00  jnz     loc_180021F3B
0x180021d06  cmp     r10, r11; __annotation("TMF:",
0x180021d09  jz      short loc_180021D31
0x180021d0b  test    byte ptr [r10+1Ch], 2
0x180021d10  jz      short loc_180021D31
0x180021d12  cmp     byte ptr [r10+19h], 2
0x180021d17  jb      short loc_180021D31
0x180021d19  mov     rcx, [r10+10h]
0x180021d1d  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180021d24  mov     edx, 4Bh ; 'K'
0x180021d29  call    WPP_SF_
0x180021d2e  xor     r9d, r9d
0x180021d31  mov     rcx, [rsi]
0x180021d34  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021d38  inc     rax
0x180021d3b  cmp     [rcx+rax*2], r9w
0x180021d40  jnz     short loc_180021D38
0x180021d42  lea     rbx, ds:2[rax*2]
0x180021d4a  mov     ecx, 40h ; '@'; uFlags
0x180021d4f  mov     rdx, rbx; uBytes
0x180021d52  call    cs:__imp_LocalAlloc
0x180021d58  mov     [rdi], rax
0x180021d5b  test    rax, rax
0x180021d5e  jz      loc_180021BB8
0x180021d64  mov     rdx, [rsi]; Src
0x180021d67  mov     r8, rbx; Size
0x180021d6a  mov     rcx, rax; void *
0x180021d6d  call    memcpy_0
0x180021d72  mov     rcx, [rsi+8]
0x180021d76  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021d7a  xor     edx, edx
0x180021d7c  inc     rax
0x180021d7f  cmp     [rcx+rax*2], dx
0x180021d83  jnz     short loc_180021D7C
0x180021d85  lea     rbx, ds:2[rax*2]
0x180021d8d  mov     ecx, 40h ; '@'; uFlags
0x180021d92  mov     rdx, rbx; uBytes
0x180021d95  call    cs:__imp_LocalAlloc
0x180021d9b  mov     [rdi+8], rax
0x180021d9f  test    rax, rax
0x180021da2  jz      loc_180021BB8
0x180021da8  mov     rdx, [rsi+8]; Src
0x180021dac  mov     r8, rbx; Size
0x180021daf  mov     rcx, rax; void *
0x180021db2  call    memcpy_0
0x180021db7  mov     rcx, [rsi+18h]
0x180021dbb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021dbf  xor     edx, edx
0x180021dc1  inc     rax
0x180021dc4  cmp     [rcx+rax*2], dx
0x180021dc8  jnz     short loc_180021DC1
0x180021dca  lea     rbx, ds:2[rax*2]
0x180021dd2  mov     ecx, 40h ; '@'; uFlags
0x180021dd7  mov     rdx, rbx; uBytes
0x180021dda  call    cs:__imp_LocalAlloc
0x180021de0  mov     [rdi+18h], rax
0x180021de4  test    rax, rax
0x180021de7  jz      loc_180021BB8
0x180021ded  mov     rdx, [rsi+18h]; Src
0x180021df1  mov     r8, rbx; Size
0x180021df4  mov     rcx, rax; void *
0x180021df7  call    memcpy_0
0x180021dfc  mov     rcx, [rsi+40h]
0x180021e00  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021e04  xor     edx, edx
0x180021e06  inc     rax
0x180021e09  cmp     [rcx+rax*2], dx
0x180021e0d  jnz     short loc_180021E06
0x180021e0f  lea     rbx, ds:2[rax*2]
0x180021e17  mov     ecx, 40h ; '@'; uFlags
0x180021e1c  mov     rdx, rbx; uBytes
0x180021e1f  call    cs:__imp_LocalAlloc
0x180021e25  mov     [rdi+40h], rax
0x180021e29  test    rax, rax
0x180021e2c  jz      loc_180021BB8
0x180021e32  mov     rdx, [rsi+40h]; Src
0x180021e36  mov     r8, rbx; Size
0x180021e39  mov     rcx, rax; void *
0x180021e3c  call    memcpy_0
0x180021e41  mov     rcx, [rsi+20h]
0x180021e45  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021e49  xor     edx, edx
0x180021e4b  inc     rax
0x180021e4e  cmp     [rcx+rax*2], dx
0x180021e52  jnz     short loc_180021E4B
0x180021e54  lea     rbx, ds:2[rax*2]
0x180021e5c  mov     ecx, 40h ; '@'; uFlags
0x180021e61  mov     rdx, rbx; uBytes
0x180021e64  call    cs:__imp_LocalAlloc
0x180021e6a  mov     [rdi+20h], rax
0x180021e6e  test    rax, rax
0x180021e71  jz      loc_180021BB8
0x180021e77  mov     rdx, [rsi+20h]; Src
0x180021e7b  mov     r8, rbx; Size
0x180021e7e  mov     rcx, rax; void *
0x180021e81  call    memcpy_0
0x180021e86  mov     eax, [rsi+50h]
0x180021e89  lea     rcx, aNetpwkstarclie_2; "NetpWkstarClientCertificateMappingGet"
0x180021e90  mov     [rdi+50h], eax
0x180021e93  mov     edx, 9F0h
0x180021e98  mov     eax, [rsi+54h]
0x180021e9b  mov     [rdi+54h], eax
0x180021e9e  mov     eax, [rsi+58h]
0x180021ea1  mov     [rdi+58h], eax
0x180021ea4  call    WsImpersonateClient2
0x180021ea9  mov     ebx, eax
0x180021eab  test    eax, eax
0x180021ead  jnz     loc_180021F51
0x180021eb3  mov     rcx, rdi
0x180021eb6  call    PopulateRenewalChain
0x180021ebb  mov     edx, 9F5h
0x180021ec0  lea     rcx, aNetpwkstarclie_2; "NetpWkstarClientCertificateMappingGet"
0x180021ec7  call    WsRevertToSelf2
0x180021ecc  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180021ed3  lea     rax, WPP_GLOBAL_Control
0x180021eda  cmp     r10, rax
0x180021edd  jz      short loc_180021F32
0x180021edf  test    byte ptr [r10+1Ch], 2
0x180021ee4  jz      short loc_180021F32
0x180021ee6  cmp     byte ptr [r10+19h], 2
0x180021eeb  jb      short loc_180021F32
0x180021eed  mov     eax, [rdi+54h]
0x180021ef0  mov     r9, [rdi]
0x180021ef3  mov     rcx, [r10+10h]; LoggerHandle
0x180021ef7  mov     dword ptr [rsp+88h+var_40], eax; char
0x180021efb  mov     eax, [rdi+50h]
0x180021efe  mov     dword ptr [rsp+88h+var_48], eax; char
0x180021f02  mov     rax, [rdi+40h]
0x180021f06  mov     [rsp+88h+var_50], rax; __int64
0x180021f0b  mov     rax, [rdi+20h]
0x180021f0f  mov     [rsp+88h+var_58], rax; __int64
0x180021f14  mov     rax, [rdi+18h]
0x180021f18  mov     [rsp+88h+var_60], rax; __int64
0x180021f1d  mov     rax, [rdi+8]
0x180021f21  mov     [rsp+88h+var_68], rax; __int64
0x180021f26  call    WPP_SF_SSSSSdd
0x180021f2b  mov     r10, cs:WPP_GLOBAL_Control
0x180021f32  inc     ebp
0x180021f34  add     rdi, 60h ; '`'
0x180021f38  xor     r9d, r9d
0x180021f3b  add     rsi, 60h ; '`'
0x180021f3f  inc     r15d
0x180021f42  jmp     loc_180021BE9
0x180021f47  mov     rax, [rsp+88h+arg_30]
0x180021f4f  mov     [rax], ebp
0x180021f51  lea     rcx, stru_18004EB90; Resource
0x180021f58  call    cs:__imp_RtlReleaseResource
0x180021f5e  test    ebx, ebx
0x180021f60  jz      short loc_180021FCB
0x180021f62  test    rdi, rdi
0x180021f65  jz      short loc_180021FCB
0x180021f67  jmp     short loc_180021FC6
0x180021f69  mov     rcx, [rdi]; hMem
0x180021f6c  test    rcx, rcx
0x180021f6f  jz      short loc_180021F77
0x180021f71  call    cs:__imp_LocalFree
0x180021f77  mov     rcx, [rdi+8]; hMem
0x180021f7b  test    rcx, rcx
  ... truncated ...
```
