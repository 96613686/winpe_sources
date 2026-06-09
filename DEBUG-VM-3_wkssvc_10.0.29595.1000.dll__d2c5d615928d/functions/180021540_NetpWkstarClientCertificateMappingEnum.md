# NetpWkstarClientCertificateMappingEnum

- ea: `0x180021540`
- end: `0x180021abf`
- name: `NetpWkstarClientCertificateMappingEnum`
- size: `1407`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180008950`
- `0x1800089d0`
- `0x180009a40`
- `0x180021540`
- `0x1800224e8`
- `0x180022b54`
- `0x180022b7c`
- `0x180022eb4`
- `0x180024200`
- `0x18002431c`
- `0x1800247d8`
- `0x180033159`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800215f6`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800215f6`
- `ntdll!RtlReleaseResource` at `0x1800216e0`
- `ntdll!RtlReleaseResource` at `0x1800216e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021698`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021749`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021789`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800217cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002180d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002184f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021891`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800218d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021915`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021957`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021698`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021749`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021789`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800217cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002180d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002184f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021891`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800218d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021915`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021957`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021a79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021a79`

## string_xrefs

- `0x1800215be`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetpWkstarClientCertificateMappingEnum(__int64 a1, void **a2, __int64 a3, _DWORD *a4)
{
  _QWORD *v6; // rcx
  __int64 v8; // rdi
  unsigned int CertificateMappings; // eax
  unsigned int v10; // ebx
  __int64 v11; // rax
  HLOCAL v12; // rax
  unsigned int v13; // ebp
  _QWORD *v14; // rcx
  __int64 v15; // rsi
  __int64 v16; // rax
  SIZE_T v17; // rbx
  HLOCAL v18; // rax
  __int64 v19; // rax
  SIZE_T v20; // rbx
  HLOCAL v21; // rax
  __int64 v22; // rax
  SIZE_T v23; // rbx
  HLOCAL v24; // rax
  __int64 v25; // rax
  SIZE_T v26; // rbx
  HLOCAL v27; // rax
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
  int v43; // eax
  int v44; // edx
  int v45; // r8d
  void *v46; // rcx

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a2 && a4 )
  {
    if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, (__int64)a2, L"WkstaConfigurationInfo") )
    {
      return 5;
    }
    else
    {
      *a2 = 0;
      *a4 = 0;
      v8 = 0;
      RtlAcquireResourceExclusive(&stru_18004EB90, 1u);
      WsFreeCertificateMappings();
      CertificateMappings = WsGetCertificateMappings();
      v10 = CertificateMappings;
      if ( CertificateMappings )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            101,
            &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids,
            CertificateMappings);
        }
      }
      else
      {
        v11 = *(unsigned int *)(*((_QWORD *)hMem + 1) + 4LL);
        if ( (_DWORD)v11 )
        {
          v12 = LocalAlloc(0x40u, 96 * v11);
          v8 = (__int64)v12;
          if ( v12 )
          {
            v13 = 0;
            *a4 = *(_DWORD *)(*((_QWORD *)hMem + 1) + 4LL);
            *a2 = v12;
            v14 = hMem;
            v15 = *(_QWORD *)(*((_QWORD *)hMem + 1) + 8LL);
            while ( v13 < *(_DWORD *)(v14[1] + 4LL) )
            {
              v16 = -1;
              do
                ++v16;
              while ( *(_WORD *)(*(_QWORD *)v15 + 2 * v16) );
              v17 = 2 * v16 + 2;
              v18 = LocalAlloc(0x40u, v17);
              *(_QWORD *)v8 = v18;
              if ( !v18 )
                goto LABEL_24;
              memcpy_0(v18, *(const void **)v15, v17);
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 8) + 2 * v19) );
              v20 = 2 * v19 + 2;
              v21 = LocalAlloc(0x40u, v20);
              *(_QWORD *)(v8 + 8) = v21;
              if ( !v21 )
                goto LABEL_24;
              memcpy_0(v21, *(const void **)(v15 + 8), v20);
              v22 = -1;
              do
                ++v22;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 16) + 2 * v22) );
              v23 = 2 * v22 + 2;
              v24 = LocalAlloc(0x40u, v23);
              *(_QWORD *)(v8 + 16) = v24;
              if ( !v24 )
                goto LABEL_24;
              memcpy_0(v24, *(const void **)(v15 + 16), v23);
              v25 = -1;
              do
                ++v25;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 24) + 2 * v25) );
              v26 = 2 * v25 + 2;
              v27 = LocalAlloc(0x40u, v26);
              *(_QWORD *)(v8 + 24) = v27;
              if ( !v27 )
                goto LABEL_24;
              memcpy_0(v27, *(const void **)(v15 + 24), v26);
              v28 = -1;
              do
                ++v28;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 32) + 2 * v28) );
              v29 = 2 * v28 + 2;
              v30 = LocalAlloc(0x40u, v29);
              *(_QWORD *)(v8 + 32) = v30;
              if ( !v30 )
                goto LABEL_24;
              memcpy_0(v30, *(const void **)(v15 + 32), v29);
              v31 = -1;
              do
                ++v31;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 40) + 2 * v31) );
              v32 = 2 * v31 + 2;
              v33 = LocalAlloc(0x40u, v32);
              *(_QWORD *)(v8 + 40) = v33;
              if ( !v33 )
                goto LABEL_24;
              memcpy_0(v33, *(const void **)(v15 + 40), v32);
              v34 = -1;
              do
                ++v34;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 48) + 2 * v34) );
              v35 = 2 * v34 + 2;
              v36 = LocalAlloc(0x40u, v35);
              *(_QWORD *)(v8 + 48) = v36;
              if ( !v36 )
                goto LABEL_24;
              memcpy_0(v36, *(const void **)(v15 + 48), v35);
              v37 = -1;
              do
                ++v37;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 56) + 2 * v37) );
              v38 = 2 * v37 + 2;
              v39 = LocalAlloc(0x40u, v38);
              *(_QWORD *)(v8 + 56) = v39;
              if ( !v39 )
                goto LABEL_24;
              memcpy_0(v39, *(const void **)(v15 + 56), v38);
              v40 = -1;
              do
                ++v40;
              while ( *(_WORD *)(*(_QWORD *)(v15 + 64) + 2 * v40) );
              v41 = 2 * v40 + 2;
              v42 = LocalAlloc(0x40u, v41);
              *(_QWORD *)(v8 + 64) = v42;
              if ( !v42 )
                goto LABEL_24;
              memcpy_0(v42, *(const void **)(v15 + 64), v41);
              v10 = WsImpersonateClient2("NetpWkstarClientCertificateMappingEnum", 92);
              if ( v10 )
                break;
              PopulateRenewalChain(v8);
              WsRevertToSelf2("NetpWkstarClientCertificateMappingEnum", 3683);
              v43 = *(_DWORD *)(v15 + 80);
              *(_DWORD *)(v8 + 80) = v43;
              v44 = *(_DWORD *)(v15 + 84);
              *(_DWORD *)(v8 + 84) = v44;
              v45 = *(_DWORD *)(v15 + 88);
              *(_DWORD *)(v8 + 88) = v45;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_SSSSSSSSSSddd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v44,
                  v45,
                  *(_QWORD *)v8,
                  *(_QWORD *)(v8 + 8),
                  *(_QWORD *)(v8 + 16),
                  *(_QWORD *)(v8 + 24),
                  *(_QWORD *)(v8 + 32),
                  *(_QWORD *)(v8 + 40),
                  *(_QWORD *)(v8 + 48),
                  *(_QWORD *)(v8 + 56),
                  *(_QWORD *)(v8 + 64),
                  *(_QWORD *)(v8 + 72),
                  v43,
                  v44,
                  v45);
              }
              v14 = hMem;
              v15 += 96;
              v8 += 96;
              ++v13;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
            }
LABEL_24:
            v10 = 8;
          }
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
        }
      }
      RtlReleaseResource(&stru_18004EB90);
      if ( v10 && v8 )
      {
        while ( 1 )
        {
          v46 = *a2;
          if ( (void *)v8 == *a2 )
            break;
          WsFreeCertificateMapping(v8);
          v8 -= 96;
        }
        if ( v46 )
          LocalFree(v46);
        *a2 = 0;
      }
      return v10;
    }
  }
  else
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) )
      WPP_SF_(v6[2], 100, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
    return 87;
  }
}

```

## disassembly

```asm
0x180021540  push    rbx
0x180021542  push    rbp
0x180021543  push    rsi
0x180021544  push    rdi
0x180021545  push    r13
0x180021547  push    r14
0x180021549  push    r15
0x18002154b  sub     rsp, 80h
0x180021552  mov     rsi, r9
0x180021555  mov     r14, rdx
0x180021558  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002155f  lea     r13, WPP_GLOBAL_Control
0x180021566  lea     rbp, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x18002156d  cmp     rcx, r13
0x180021570  jz      short loc_180021596
0x180021572  test    byte ptr [rcx+1Ch], 2
0x180021576  jz      short loc_180021596
0x180021578  cmp     byte ptr [rcx+19h], 2
0x18002157c  jb      short loc_180021596
0x18002157e  mov     rcx, [rcx+10h]
0x180021582  mov     edx, 63h ; 'c'
0x180021587  mov     r8, rbp
0x18002158a  call    WPP_SF_
0x18002158f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021596  xor     r15d, r15d
0x180021599  test    r14, r14
0x18002159c  jz      loc_180021A86
0x1800215a2  test    rsi, rsi
0x1800215a5  jz      loc_180021A86
0x1800215ab  mov     rax, cs:ConfigurationInfoSd
0x1800215b2  lea     rcx, WsConfigInfoMapping
0x1800215b9  mov     [rsp+0B8h+var_88], rcx
0x1800215be  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x1800215c5  mov     dword ptr [rsp+0B8h+var_90], 2
0x1800215cd  mov     [rsp+0B8h+var_98], rax
0x1800215d2  call    NetpAccessCheckAndAuditEx
0x1800215d7  test    eax, eax
0x1800215d9  jz      short loc_1800215E4
0x1800215db  lea     eax, [r15+5]
0x1800215df  jmp     loc_180021AAD
0x1800215e4  mov     [r14], r15
0x1800215e7  lea     rcx, stru_18004EB90; Resource
0x1800215ee  mov     dl, 1; Wait
0x1800215f0  mov     [rsi], r15d
0x1800215f3  mov     rdi, r15
0x1800215f6  call    cs:__imp_RtlAcquireResourceExclusive
0x1800215fc  call    WsFreeCertificateMappings
0x180021601  call    WsGetCertificateMappings
0x180021606  mov     ebx, eax
0x180021608  test    eax, eax
0x18002160a  jz      short loc_180021649
0x18002160c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180021613  cmp     rcx, r13
0x180021616  jz      loc_1800216D9
0x18002161c  test    byte ptr [rcx+1Ch], 2
0x180021620  jz      loc_1800216D9
0x180021626  cmp     byte ptr [rcx+19h], 1
0x18002162a  jb      loc_1800216D9
0x180021630  mov     rcx, [rcx+10h]
0x180021634  mov     edx, 65h ; 'e'
0x180021639  mov     r9d, eax
0x18002163c  mov     r8, rbp
0x18002163f  call    WPP_SF_d
0x180021644  jmp     loc_1800216D9
0x180021649  mov     rax, cs:hMem
0x180021650  mov     rcx, [rax+8]
0x180021654  mov     eax, [rcx+4]
0x180021657  cmp     eax, 1
0x18002165a  jnb     short loc_180021687
0x18002165c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180021663  cmp     rcx, r13
0x180021666  jz      short loc_1800216D9
0x180021668  test    byte ptr [rcx+1Ch], 2
0x18002166c  jz      short loc_1800216D9
0x18002166e  cmp     byte ptr [rcx+19h], 2
0x180021672  jb      short loc_1800216D9
0x180021674  mov     rcx, [rcx+10h]
0x180021678  mov     edx, 66h ; 'f'
0x18002167d  mov     r8, rbp
0x180021680  call    WPP_SF_
0x180021685  jmp     short loc_1800216D9
0x180021687  lea     rdx, [rax+rax*2]
0x18002168b  mov     r13d, 40h ; '@'
0x180021691  shl     rdx, 5; uBytes
0x180021695  mov     ecx, r13d; uFlags
0x180021698  call    cs:__imp_LocalAlloc
0x18002169e  mov     rdi, rax
0x1800216a1  test    rax, rax
0x1800216a4  jnz     short loc_1800216FC
0x1800216a6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800216ad  lea     rax, WPP_GLOBAL_Control
0x1800216b4  cmp     rcx, rax
0x1800216b7  jz      short loc_1800216D4
0x1800216b9  test    byte ptr [rcx+1Ch], 2
0x1800216bd  jz      short loc_1800216D4
0x1800216bf  cmp     byte ptr [rcx+19h], 1
0x1800216c3  jb      short loc_1800216D4
0x1800216c5  mov     rcx, [rcx+10h]
0x1800216c9  lea     edx, [rdi+67h]
0x1800216cc  mov     r8, rbp
0x1800216cf  call    WPP_SF_
0x1800216d4  mov     ebx, 8
0x1800216d9  lea     rcx, stru_18004EB90; Resource
0x1800216e0  call    cs:__imp_RtlReleaseResource
0x1800216e6  test    ebx, ebx
0x1800216e8  jz      loc_180021A82
0x1800216ee  test    rdi, rdi
0x1800216f1  jz      loc_180021A82
0x1800216f7  jmp     loc_180021A6C
0x1800216fc  mov     rax, cs:hMem
0x180021703  mov     ebp, r15d
0x180021706  mov     rcx, [rax+8]
0x18002170a  mov     eax, [rcx+4]
0x18002170d  mov     [rsi], eax
0x18002170f  mov     [r14], rdi
0x180021712  mov     rcx, cs:hMem
0x180021719  mov     rax, [rcx+8]
0x18002171d  mov     rsi, [rax+8]
0x180021721  mov     rax, [rcx+8]
0x180021725  cmp     ebp, [rax+4]
0x180021728  jnb     short loc_1800216D9
0x18002172a  mov     rcx, [rsi]
0x18002172d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021731  inc     rax
0x180021734  cmp     [rcx+rax*2], r15w
0x180021739  jnz     short loc_180021731
0x18002173b  lea     rbx, ds:2[rax*2]
0x180021743  mov     ecx, r13d; uFlags
0x180021746  mov     rdx, rbx; uBytes
0x180021749  call    cs:__imp_LocalAlloc
0x18002174f  mov     [rdi], rax
0x180021752  test    rax, rax
0x180021755  jz      loc_1800216D4
0x18002175b  mov     rdx, [rsi]; Src
0x18002175e  mov     r8, rbx; Size
0x180021761  mov     rcx, rax; void *
0x180021764  call    memcpy_0
0x180021769  mov     rcx, [rsi+8]
0x18002176d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021771  inc     rax
0x180021774  cmp     [rcx+rax*2], r15w
0x180021779  jnz     short loc_180021771
0x18002177b  lea     rbx, ds:2[rax*2]
0x180021783  mov     ecx, r13d; uFlags
0x180021786  mov     rdx, rbx; uBytes
0x180021789  call    cs:__imp_LocalAlloc
0x18002178f  mov     [rdi+8], rax
0x180021793  test    rax, rax
0x180021796  jz      loc_1800216D4
0x18002179c  mov     rdx, [rsi+8]; Src
0x1800217a0  mov     r8, rbx; Size
0x1800217a3  mov     rcx, rax; void *
0x1800217a6  call    memcpy_0
0x1800217ab  mov     rcx, [rsi+10h]
0x1800217af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800217b3  inc     rax
0x1800217b6  cmp     [rcx+rax*2], r15w
0x1800217bb  jnz     short loc_1800217B3
0x1800217bd  lea     rbx, ds:2[rax*2]
0x1800217c5  mov     ecx, r13d; uFlags
0x1800217c8  mov     rdx, rbx; uBytes
0x1800217cb  call    cs:__imp_LocalAlloc
0x1800217d1  mov     [rdi+10h], rax
0x1800217d5  test    rax, rax
0x1800217d8  jz      loc_1800216D4
0x1800217de  mov     rdx, [rsi+10h]; Src
0x1800217e2  mov     r8, rbx; Size
0x1800217e5  mov     rcx, rax; void *
0x1800217e8  call    memcpy_0
0x1800217ed  mov     rcx, [rsi+18h]
0x1800217f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800217f5  inc     rax
0x1800217f8  cmp     [rcx+rax*2], r15w
0x1800217fd  jnz     short loc_1800217F5
0x1800217ff  lea     rbx, ds:2[rax*2]
0x180021807  mov     ecx, r13d; uFlags
0x18002180a  mov     rdx, rbx; uBytes
0x18002180d  call    cs:__imp_LocalAlloc
0x180021813  mov     [rdi+18h], rax
0x180021817  test    rax, rax
0x18002181a  jz      loc_1800216D4
0x180021820  mov     rdx, [rsi+18h]; Src
0x180021824  mov     r8, rbx; Size
0x180021827  mov     rcx, rax; void *
0x18002182a  call    memcpy_0
0x18002182f  mov     rcx, [rsi+20h]
0x180021833  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021837  inc     rax
0x18002183a  cmp     [rcx+rax*2], r15w
0x18002183f  jnz     short loc_180021837
0x180021841  lea     rbx, ds:2[rax*2]
0x180021849  mov     ecx, r13d; uFlags
0x18002184c  mov     rdx, rbx; uBytes
0x18002184f  call    cs:__imp_LocalAlloc
0x180021855  mov     [rdi+20h], rax
0x180021859  test    rax, rax
0x18002185c  jz      loc_1800216D4
0x180021862  mov     rdx, [rsi+20h]; Src
0x180021866  mov     r8, rbx; Size
0x180021869  mov     rcx, rax; void *
0x18002186c  call    memcpy_0
0x180021871  mov     rcx, [rsi+28h]
0x180021875  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021879  inc     rax
0x18002187c  cmp     [rcx+rax*2], r15w
0x180021881  jnz     short loc_180021879
0x180021883  lea     rbx, ds:2[rax*2]
0x18002188b  mov     ecx, r13d; uFlags
0x18002188e  mov     rdx, rbx; uBytes
0x180021891  call    cs:__imp_LocalAlloc
0x180021897  mov     [rdi+28h], rax
0x18002189b  test    rax, rax
0x18002189e  jz      loc_1800216D4
0x1800218a4  mov     rdx, [rsi+28h]; Src
0x1800218a8  mov     r8, rbx; Size
0x1800218ab  mov     rcx, rax; void *
0x1800218ae  call    memcpy_0
0x1800218b3  mov     rcx, [rsi+30h]
0x1800218b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800218bb  inc     rax
0x1800218be  cmp     [rcx+rax*2], r15w
0x1800218c3  jnz     short loc_1800218BB
0x1800218c5  lea     rbx, ds:2[rax*2]
0x1800218cd  mov     ecx, r13d; uFlags
0x1800218d0  mov     rdx, rbx; uBytes
0x1800218d3  call    cs:__imp_LocalAlloc
0x1800218d9  mov     [rdi+30h], rax
0x1800218dd  test    rax, rax
0x1800218e0  jz      loc_1800216D4
0x1800218e6  mov     rdx, [rsi+30h]; Src
0x1800218ea  mov     r8, rbx; Size
0x1800218ed  mov     rcx, rax; void *
0x1800218f0  call    memcpy_0
0x1800218f5  mov     rcx, [rsi+38h]
0x1800218f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800218fd  inc     rax
0x180021900  cmp     [rcx+rax*2], r15w
0x180021905  jnz     short loc_1800218FD
0x180021907  lea     rbx, ds:2[rax*2]
0x18002190f  mov     ecx, r13d; uFlags
0x180021912  mov     rdx, rbx; uBytes
0x180021915  call    cs:__imp_LocalAlloc
0x18002191b  mov     [rdi+38h], rax
0x18002191f  test    rax, rax
0x180021922  jz      loc_1800216D4
0x180021928  mov     rdx, [rsi+38h]; Src
0x18002192c  mov     r8, rbx; Size
0x18002192f  mov     rcx, rax; void *
0x180021932  call    memcpy_0
0x180021937  mov     rcx, [rsi+40h]
0x18002193b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002193f  inc     rax
0x180021942  cmp     [rcx+rax*2], r15w
0x180021947  jnz     short loc_18002193F
0x180021949  lea     rbx, ds:2[rax*2]
0x180021951  mov     ecx, r13d; uFlags
0x180021954  mov     rdx, rbx; uBytes
0x180021957  call    cs:__imp_LocalAlloc
0x18002195d  mov     [rdi+40h], rax
0x180021961  test    rax, rax
0x180021964  jz      loc_1800216D4
0x18002196a  mov     rdx, [rsi+40h]; Src
0x18002196e  mov     r8, rbx; Size
0x180021971  mov     rcx, rax; void *
0x180021974  call    memcpy_0
0x180021979  mov     edx, 0E5Ch
0x18002197e  lea     rcx, aNetpwkstarclie_0; "NetpWkstarClientCertificateMappingEnum"
0x180021985  call    WsImpersonateClient2
0x18002198a  mov     ebx, eax
0x18002198c  test    eax, eax
0x18002198e  jnz     loc_1800216D9
0x180021994  mov     rcx, rdi
0x180021997  call    PopulateRenewalChain
0x18002199c  mov     edx, 0E63h
0x1800219a1  lea     rcx, aNetpwkstarclie_0; "NetpWkstarClientCertificateMappingEnum"
0x1800219a8  call    WsRevertToSelf2
0x1800219ad  mov     eax, [rsi+50h]
0x1800219b0  mov     [rdi+50h], eax
0x1800219b3  mov     edx, [rsi+54h]
0x1800219b6  mov     [rdi+54h], edx
0x1800219b9  mov     r8d, [rsi+58h]
0x1800219bd  mov     [rdi+58h], r8d
0x1800219c1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800219c8  lea     r9, WPP_GLOBAL_Control
0x1800219cf  cmp     rcx, r9
0x1800219d2  jz      short loc_180021A4A
0x1800219d4  test    byte ptr [rcx+1Ch], 2
0x1800219d8  jz      short loc_180021A4A
0x1800219da  cmp     byte ptr [rcx+19h], 2
0x1800219de  jb      short loc_180021A4A
0x1800219e0  mov     r9, [rdi]
0x1800219e3  mov     rcx, [rcx+10h]
0x1800219e7  mov     [rsp+0B8h+var_40], r8d
0x1800219ec  mov     [rsp+0B8h+var_48], edx
0x1800219f0  mov     [rsp+0B8h+var_50], eax
0x1800219f4  mov     rax, [rdi+48h]
0x1800219f8  mov     [rsp+0B8h+var_58], rax
0x1800219fd  mov     rax, [rdi+40h]
0x180021a01  mov     [rsp+0B8h+var_60], rax
0x180021a06  mov     rax, [rdi+38h]
  ... truncated ...
```
