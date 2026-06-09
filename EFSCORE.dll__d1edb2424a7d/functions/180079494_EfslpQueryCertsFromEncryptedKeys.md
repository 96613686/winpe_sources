# EfslpQueryCertsFromEncryptedKeys

- ea: `0x180079494`
- end: `0x1800798bd`
- name: `EfslpQueryCertsFromEncryptedKeys`
- size: `1065`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180073ce0`

## callees

- `0x180004f86`
- `0x180005045`
- `0x18000b884`
- `0x180010bf0`
- `0x180063698`
- `0x180068b28`
- `0x180079494`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007989e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007989e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007979c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800797ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800797ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800797c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079845`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007984f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007985e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007986d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079876`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007988e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007979c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800797ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800797ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800797c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079845`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007984f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007985e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007986d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079876`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007988e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800794c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180079570`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800795b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007962b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180079654`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800796b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800794c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180079570`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800795b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007962b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180079654`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800796b7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800795a7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800795ce`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800795e9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800795a7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800795ce`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800795e9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800795e1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800795e1`

## pseudocode

```c
_BOOL8 __fastcall EfslpQueryCertsFromEncryptedKeys(unsigned int *a1, unsigned int *a2, _QWORD *a3)
{
  unsigned int v3; // r12d
  HLOCAL v6; // rax
  DWORD v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rsi
  __int64 v10; // rbp
  __int64 v11; // rbx
  void *v12; // rcx
  void *v13; // rcx

  v3 = *a1;
  *a2 = *a1;
  v6 = LocalAlloc(0x40u, 8LL * v3);
  *a3 = v6;
  if ( v6 )
  {
    v7 = 0;
    memset_0(v6, 0, 8LL * v3);
    if ( v3 )
    {
      EfsAlignBlock(a1 + 1);
      v7 = 8;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 8, 23, 53);
      v8 = (_QWORD *)*a3;
      if ( *(_QWORD *)*a3 )
      {
        LODWORD(v9) = 0;
        do
        {
          v10 = (unsigned int)v9;
          v11 = v8[(unsigned int)v9];
          if ( !*(_QWORD *)(v11 + 16) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v8);
          if ( !*(_QWORD *)(*(_QWORD *)(v11 + 16) + 8LL) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v8);
          LocalFree(*(HLOCAL *)(*(_QWORD *)(v11 + 16) + 8LL));
          LocalFree(*(HLOCAL *)(v11 + 16));
          v12 = *(void **)(v11 + 24);
          if ( v12 )
            LocalFree(v12);
          v13 = *(void **)(v11 + 8);
          if ( v13 )
            LocalFree(v13);
          LocalFree((HLOCAL)v11);
          v9 = (unsigned int)(v9 + 1);
          *(_QWORD *)(*a3 + 8 * v10) = 0;
          v8 = (_QWORD *)*a3;
        }
        while ( *(_QWORD *)(*a3 + 8 * v9) );
      }
      LocalFree(v8);
      *a3 = 0;
    }
  }
  else
  {
    v7 = 8;
  }
  SetLastError(v7);
  return v7 == 0;
}

```

## disassembly

```asm
0x180079494  push    rbx
0x180079496  push    rbp
0x180079497  push    rsi
0x180079498  push    rdi
0x180079499  push    r12
0x18007949b  push    r13
0x18007949d  push    r14
0x18007949f  push    r15
0x1800794a1  sub     rsp, 48h
0x1800794a5  mov     r12d, [rcx]
0x1800794a8  mov     rsi, rcx
0x1800794ab  mov     [rdx], r12d
0x1800794ae  mov     ebx, r12d
0x1800794b1  shl     rbx, 3
0x1800794b5  mov     ecx, 40h ; '@'; uFlags
0x1800794ba  mov     rdx, rbx; uBytes
0x1800794bd  mov     [rsp+88h+arg_10], r12d
0x1800794c5  mov     r14, r8
0x1800794c8  call    cs:__imp_LocalAlloc
0x1800794ce  xor     r15d, r15d
0x1800794d1  mov     [r14], rax
0x1800794d4  test    rax, rax
0x1800794d7  jnz     short loc_1800794E1
0x1800794d9  lea     edi, [rax+8]
0x1800794dc  jmp     loc_18007989C
0x1800794e1  mov     edi, r15d
0x1800794e4  mov     r8, rbx; Size
0x1800794e7  lea     r15, [rsi+4]
0x1800794eb  xor     edx, edx; Val
0x1800794ed  mov     rcx, rax; void *
0x1800794f0  mov     [rsp+88h+var_58], r15
0x1800794f5  call    memset_0
0x1800794fa  xor     ecx, ecx
0x1800794fc  mov     r13d, ecx
0x1800794ff  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180079503  lea     esi, [rcx+8]
0x180079506  mov     [rsp+88h+arg_8], r13d
0x18007950e  cmp     r13d, r12d
0x180079511  jnb     loc_180079899
0x180079517  mov     [rsp+88h+pDestinationSid], rcx
0x18007951f  lea     r8, [rsp+88h+arg_0]
0x180079527  mov     [rsp+88h+arg_0], cl
0x18007952e  lea     rdx, [rsp+88h+pDestinationSid]
0x180079536  mov     rcx, r15; Src
0x180079539  call    EfsAlignBlock
0x18007953e  mov     r12, [rsp+88h+pDestinationSid]
0x180079546  xor     r15d, r15d
0x180079549  mov     edi, eax
0x18007954b  test    r12, r12
0x18007954e  jz      loc_1800797EC
0x180079554  mov     r15d, [r12+4]
0x180079559  add     r15, r12
0x18007955c  cmp     dword ptr [r15+8], 3
0x180079561  jz      short loc_180079568
0x180079563  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pPublicKeyInfo->KeySourceTag == EfsCertificateThumbprint")
0x180079568  mov     edx, 20h ; ' '; uBytes
0x18007956d  lea     ecx, [rdx+20h]; uFlags
0x180079570  call    cs:__imp_LocalAlloc
0x180079576  mov     rbx, rax
0x180079579  test    rax, rax
0x18007957c  jz      loc_1800797CB
0x180079582  xorps   xmm0, xmm0
0x180079585  movups  xmmword ptr [rax], xmm0
0x180079588  movups  xmmword ptr [rax+10h], xmm0
0x18007958c  mov     dword ptr [rax], 20h ; ' '
0x180079592  cmp     dword ptr [r15+4], 0
0x180079597  jz      loc_18007961D
0x18007959d  mov     r13d, [r15+4]
0x1800795a1  add     r13, r15
0x1800795a4  mov     rcx, r13; pSid
0x1800795a7  call    cs:__imp_GetLengthSid
0x1800795ad  mov     edx, eax; uBytes
0x1800795af  mov     ecx, 40h ; '@'; uFlags
0x1800795b4  call    cs:__imp_LocalAlloc
0x1800795ba  mov     [rsp+88h+pDestinationSid], rax
0x1800795c2  mov     rcx, r13; pSid
0x1800795c5  mov     [rbx+8], rax
0x1800795c9  test    rax, rax
0x1800795cc  jz      short loc_1800795E9
0x1800795ce  call    cs:__imp_GetLengthSid
0x1800795d4  mov     rdx, [rsp+88h+pDestinationSid]; pDestinationSid
0x1800795dc  mov     r8, r13; pSourceSid
0x1800795df  mov     ecx, eax; nDestinationSidLength
0x1800795e1  call    cs:__imp_CopySid
0x1800795e7  jmp     short loc_180079615
0x1800795e9  call    cs:__imp_GetLengthSid
0x1800795ef  mov     rcx, cs:g_hPublisher
0x1800795f6  lea     rdx, EFS_ERROR_MEMORY
0x1800795fd  mov     r8d, eax
0x180079600  mov     [rsp+88h+var_68], 0C57h
0x180079608  mov     r9d, 17h
0x18007960e  call    fnEfsLogTrace1
0x180079613  mov     edi, esi
0x180079615  mov     r13d, [rsp+88h+arg_8]
0x18007961d  test    edi, edi
0x18007961f  jnz     loc_18007977D
0x180079625  lea     edx, [rdi+10h]; uBytes
0x180079628  lea     ecx, [rdi+40h]; uFlags
0x18007962b  call    cs:__imp_LocalAlloc
0x180079631  mov     [rbx+10h], rax
0x180079635  test    rax, rax
0x180079638  jz      loc_180079754
0x18007963e  mov     ecx, [r15+10h]
0x180079642  add     r15, rcx
0x180079645  mov     ecx, [r15+4]
0x180079649  mov     [rax], ecx
0x18007964b  lea     ecx, [rdi+40h]; uFlags
0x18007964e  mov     rax, [rbx+10h]
0x180079652  mov     edx, [rax]; uBytes
0x180079654  call    cs:__imp_LocalAlloc
0x18007965a  mov     rcx, [rbx+10h]
0x18007965e  mov     [rcx+8], rax
0x180079662  mov     rax, [rbx+10h]
0x180079666  mov     rcx, [rax+8]; void *
0x18007966a  mov     r8d, [rax]; Size
0x18007966d  test    rcx, rcx
0x180079670  jz      loc_18007974A
0x180079676  mov     edx, [r15]
0x180079679  add     rdx, r15; Src
0x18007967c  call    memcpy_0
0x180079681  xor     ecx, ecx
0x180079683  cmp     [r15+10h], ecx
0x180079687  jz      short loc_1800796F1
0x180079689  mov     eax, [r15+10h]
0x18007968d  add     r15, rax
0x180079690  mov     rax, rbp
0x180079693  inc     rax
0x180079696  cmp     [r15+rax*2], cx
0x18007969b  jnz     short loc_180079693
0x18007969d  inc     eax
0x18007969f  mov     ecx, 40h ; '@'; uFlags
0x1800796a4  mov     [rsp+88h+arg_8], eax
0x1800796ab  mov     [rsp+88h+pDestinationSid], rax
0x1800796b3  lea     rdx, [rax+rax]; uBytes
0x1800796b7  call    cs:__imp_LocalAlloc
0x1800796bd  xor     ecx, ecx
0x1800796bf  mov     [rbx+18h], rax
0x1800796c3  test    rax, rax
0x1800796c6  jz      short loc_18007972E
0x1800796c8  mov     rdx, [rsp+88h+pDestinationSid]; unsigned __int64
0x1800796d0  mov     r8, r15; unsigned __int16 *
0x1800796d3  mov     rcx, rax; unsigned __int16 *
0x1800796d6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800796db  mov     r11d, [rsp+88h+arg_8]
0x1800796e3  mov     rdx, [rbx+18h]
0x1800796e7  dec     r11d
0x1800796ea  xor     ecx, ecx
0x1800796ec  mov     [rdx+r11*2], cx
0x1800796f1  mov     rax, [r14]
0x1800796f4  mov     edx, r13d
0x1800796f7  mov     [rax+rdx*8], rbx
0x1800796fb  cmp     [rsp+88h+arg_0], cl
0x180079702  jz      short loc_18007970E
0x180079704  mov     rcx, r12; lpMem
0x180079707  call    EfsFreeHeap
0x18007970c  xor     ecx, ecx
0x18007970e  mov     r15, [rsp+88h+var_58]
0x180079713  inc     r13d
0x180079716  mov     r12d, [rsp+88h+arg_10]
0x18007971e  mov     eax, [r15]
0x180079721  add     r15, rax
0x180079724  mov     [rsp+88h+var_58], r15
0x180079729  jmp     loc_180079506
0x18007972e  inc     rbp
0x180079731  cmp     [r15+rbp*2], cx
0x180079736  jnz     short loc_18007972E
0x180079738  lea     r8d, ds:2[rbp*2]
0x180079740  mov     [rsp+88h+var_68], 0CA2h
0x180079748  jmp     short loc_180079762
0x18007974a  mov     [rsp+88h+var_68], 0C7Dh
0x180079752  jmp     short loc_180079762
0x180079754  mov     [rsp+88h+var_68], 0CAAh
0x18007975c  mov     r8d, 10h
0x180079762  mov     rcx, cs:g_hPublisher
0x180079769  lea     rdx, EFS_ERROR_MEMORY
0x180079770  mov     r9d, 17h
0x180079776  call    fnEfsLogTrace1
0x18007977b  mov     edi, esi
0x18007977d  mov     rax, [rbx+10h]
0x180079781  xor     r15d, r15d
0x180079784  test    rax, rax
0x180079787  jz      short loc_1800797A2
0x180079789  mov     rcx, [rax+8]; hMem
0x18007978d  test    rcx, rcx
0x180079790  jz      short loc_180079798
0x180079792  call    cs:__imp_LocalFree
0x180079798  mov     rcx, [rbx+10h]; hMem
0x18007979c  call    cs:__imp_LocalFree
0x1800797a2  mov     rcx, [rbx+18h]; hMem
0x1800797a6  test    rcx, rcx
0x1800797a9  jz      short loc_1800797B1
0x1800797ab  call    cs:__imp_LocalFree
0x1800797b1  mov     rcx, [rbx+8]; hMem
0x1800797b5  test    rcx, rcx
0x1800797b8  jz      short loc_1800797C0
0x1800797ba  call    cs:__imp_LocalFree
0x1800797c0  mov     rcx, rbx; hMem
0x1800797c3  call    cs:__imp_LocalFree
0x1800797c9  jmp     short loc_1800797D0
0x1800797cb  mov     edi, esi
0x1800797cd  xor     r15d, r15d
0x1800797d0  cmp     [rsp+88h+arg_0], r15b
0x1800797d8  jz      short loc_1800797E2
0x1800797da  mov     rcx, r12; lpMem
0x1800797dd  call    EfsFreeHeap
0x1800797e2  test    edi, edi
0x1800797e4  jz      loc_18007989C
0x1800797ea  jmp     short loc_180079812
0x1800797ec  mov     rcx, cs:g_hPublisher
0x1800797f3  lea     rdx, EFS_API_ERROR
0x1800797fa  mov     r9d, 17h
0x180079800  mov     [rsp+88h+var_68], 0C35h
0x180079808  mov     r8d, esi
0x18007980b  mov     edi, esi
0x18007980d  call    fnEfsLogTrace1
0x180079812  mov     rcx, [r14]
0x180079815  cmp     [rcx], r15
0x180079818  jz      short loc_18007988E
0x18007981a  mov     esi, r15d
0x18007981d  mov     ebp, esi
0x18007981f  mov     rbx, [rcx+rbp*8]
0x180079823  cmp     [rbx+10h], r15
0x180079827  jnz     short loc_18007982E
0x180079829  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pTmp->pHash")
0x18007982e  mov     rax, [rbx+10h]
0x180079832  cmp     [rax+8], r15
0x180079836  jnz     short loc_18007983D
0x180079838  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pTmp->pHash->pbData")
0x18007983d  mov     rcx, [rbx+10h]
0x180079841  mov     rcx, [rcx+8]; hMem
0x180079845  call    cs:__imp_LocalFree
0x18007984b  mov     rcx, [rbx+10h]; hMem
0x18007984f  call    cs:__imp_LocalFree
0x180079855  mov     rcx, [rbx+18h]; hMem
0x180079859  test    rcx, rcx
0x18007985c  jz      short loc_180079864
0x18007985e  call    cs:__imp_LocalFree
0x180079864  mov     rcx, [rbx+8]; hMem
0x180079868  test    rcx, rcx
0x18007986b  jz      short loc_180079873
0x18007986d  call    cs:__imp_LocalFree
0x180079873  mov     rcx, rbx; hMem
0x180079876  call    cs:__imp_LocalFree
0x18007987c  mov     rax, [r14]
0x18007987f  inc     esi
0x180079881  mov     [rax+rbp*8], r15
0x180079885  mov     rcx, [r14]; hMem
0x180079888  cmp     [rcx+rsi*8], r15
0x18007988c  jnz     short loc_18007981D
0x18007988e  call    cs:__imp_LocalFree
0x180079894  mov     [r14], r15
0x180079897  jmp     short loc_18007989C
0x180079899  xor     r15d, r15d
0x18007989c  mov     ecx, edi; dwErrCode
0x18007989e  call    cs:__imp_SetLastError
0x1800798a4  test    edi, edi
0x1800798a6  mov     eax, r15d
0x1800798a9  setz    al
0x1800798ac  add     rsp, 48h
0x1800798b0  pop     r15
0x1800798b2  pop     r14
0x1800798b4  pop     r13
0x1800798b6  pop     r12
0x1800798b8  pop     rdi
0x1800798b9  pop     rsi
0x1800798ba  pop     rbp
0x1800798bb  pop     rbx
0x1800798bc  retn
```
