# IkeConstructNonce

- ea: `0x1800460c0`
- end: `0x180046504`
- name: `IkeConstructNonce`
- size: `1092`
- prototype: ``
- caller_count: `33`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800428c0`
- `0x180043270`
- `0x1800c2280`
- `0x1800c2618`
- `0x1800c2d68`
- `0x1800c30dc`
- `0x1800c3420`
- `0x1800c3834`
- `0x1800c3b20`
- `0x1800c459c`
- `0x1800e2f28`
- `0x1800e36f4`
- `0x1800e3d54`
- `0x1800e4224`
- `0x1800e4650`
- `0x1800e4a00`
- `0x1800e4d9c`
- `0x1800e5090`
- `0x1800e5478`
- `0x1800e58b0`
- `0x1800e59d0`
- `0x1800e5d1c`
- `0x1800e6040`
- `0x1800e638c`
- `0x1800e66d8`
- `0x1800e6a58`
- `0x1800e6c28`
- `0x1800e6e2c`
- `0x1800e7294`
- `0x1800e77b4`
- `0x1800e7b04`
- `0x18010935c`
- `0x180109764`

## callees

- `0x180003cf0`
- `0x180008388`
- `0x1800096c0`
- `0x180016534`
- `0x1800460c0`
- `0x18004882c`
- `0x180050850`
- `0x18005bc40`
- `0x180110d3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004613e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046177`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800461d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004621d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004613e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046177`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800461d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004621d`
- `ntdll!EtwEventWriteTransfer` at `0x1800462fd`
- `ntdll!EtwEventWriteTransfer` at `0x1800462fd`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800464ad`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800464ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004646f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800464c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004646f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800464c8`
- `WS2_32!__imp_htons` at `0x1800463af`
- `WS2_32!__imp_htons` at `0x1800463af`
- `ncrypt!BCryptGenRandom` at `0x18004633c`
- `ncrypt!BCryptGenRandom` at `0x18004633c`

## pseudocode

```c
__int64 __fastcall IkeConstructNonce(_DWORD *a1, __int64 *a2, __int64 a3, __int64 a4)
{
  _QWORD *v7; // rcx
  LPCRITICAL_SECTION v8; // rdx
  DWORD LockSemaphore; // eax
  LPVOID Value; // rax
  LPVOID v11; // r8
  __int64 v12; // rbx
  DWORD v13; // eax
  __int64 *v14; // rax
  __int64 v15; // r9
  LPCRITICAL_SECTION v16; // rax
  DWORD v17; // ecx
  __int64 *v18; // rax
  __int64 v19; // rcx
  DWORD v20; // ecx
  char *v21; // rax
  const WCHAR *v22; // rdx
  __int64 v23; // rax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdi
  char v28; // cl
  __int64 v29; // rcx
  __int64 v30; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  BOOL v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  int v37; // [rsp+30h] [rbp-69h]
  __int64 v38; // [rsp+40h] [rbp-59h] BYREF
  _DWORD v39[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v40; // [rsp+50h] [rbp-49h]
  char *v41; // [rsp+60h] [rbp-39h] BYREF
  int v42; // [rsp+68h] [rbp-31h]
  int v43; // [rsp+6Ch] [rbp-2Dh]
  __int16 *v44; // [rsp+70h] [rbp-29h]
  int v45; // [rsp+78h] [rbp-21h]
  int v46; // [rsp+7Ch] [rbp-1Dh]
  __int64 *v47; // [rsp+80h] [rbp-19h]
  __int64 v48; // [rsp+88h] [rbp-11h]
  const WCHAR *v49; // [rsp+90h] [rbp-9h]
  int v50; // [rsp+98h] [rbp-1h]
  int v51; // [rsp+9Ch] [rbp+3h]
  const char *v52; // [rsp+A0h] [rbp+7h]
  __int64 v53; // [rsp+A8h] [rbp+Fh]

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v8 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore, LockSemaphore == -1) )
    {
      v11 = 0;
    }
    else
    {
      Value = TlsGetValue(LockSemaphore);
      v7 = WPP_GLOBAL_Control;
      v11 = Value;
      v8 = gIkeExtGlobals;
    }
    v12 = (__int64)v11 + 8;
    if ( !v11 )
      v12 = 0;
    if ( v8
      && (v13 = (DWORD)v8[86].LockSemaphore, v13 != -1)
      && (v14 = (__int64 *)TlsGetValue(v13), v7 = WPP_GLOBAL_Control, v14) )
    {
      v15 = *v14;
    }
    else
    {
      LODWORD(v15) = 0;
    }
    WPP_SF_iS(v7[2], 10, (unsigned int)WPP_862de3e8a64a3df216a95f657c5e3376_Traceguids, v15, v12);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v16 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v17 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v17 != -1 )
      {
        v18 = (__int64 *)TlsGetValue(v17);
        if ( v18 )
        {
          v19 = *v18;
          v16 = gIkeExtGlobals;
LABEL_23:
          v38 = v19;
          v47 = &v38;
          v48 = 8;
          if ( !v16 )
            goto LABEL_31;
          v20 = (DWORD)v16[86].LockSemaphore;
          if ( v20 == -1 )
            goto LABEL_31;
          v21 = (char *)TlsGetValue(v20);
          v22 = (const WCHAR *)(v21 + 8);
          if ( !v21 )
            v22 = 0;
          if ( v22 )
          {
            v23 = -1;
            while ( v22[++v23] != 0 )
              ;
            v25 = 2 * v23 + 2;
          }
          else
          {
LABEL_31:
            v22 = &LocaleName;
            v25 = 2;
          }
          v50 = v25;
          v49 = v22;
          v52 = "Construct NONCE";
          v39[1] = 4;
          v41 = off_180173280;
          v51 = 0;
          v53 = 16;
          v39[0] = 184549376;
          v40 = 0;
          v42 = *(unsigned __int16 *)off_180173280;
          v44 = word_180164362;
          v43 = 2;
          v45 = 52;
          v46 = 1;
          EtwEventWriteTransfer(qword_180173298, v39, 0, 0, 5, &v41);
          goto LABEL_33;
        }
        v16 = gIkeExtGlobals;
      }
    }
    v19 = 0;
    goto LABEL_23;
  }
LABEL_33:
  v27 = WfpMemAlloc(0x30u, 0);
  if ( v27 )
    goto LABEL_39;
  v27 = IkeReturnError(0, "IkeGenRandom");
  if ( v27 )
    goto LABEL_39;
  v28 = 40;
  LOWORD(v37) = 0;
  if ( *a1 != 2 )
    v28 = 10;
  *(_BYTE *)(*a2 + *((unsigned __int16 *)a2 + 7)) = v28;
  v27 = IkeExpandPacket(a2, 52);
  if ( v27 )
  {
LABEL_39:
    if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline(v26);
    if ( IsEnabledDeviceUsageNoInline )
    {
      v32 = HeapFree(gWfpHeap, 0, 0);
      if ( !gHeapFreeFailedFired && !v32 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v34, v33, v35);
        gHeapFreeFailedFired = 1;
      }
    }
    else
    {
      HeapFree(gWfpHeap, 0, 0);
    }
  }
  else
  {
    *((_WORD *)a2 + 7) = *((_WORD *)a2 + 6);
    HIWORD(v37) = htons(0x34u);
    *(_DWORD *)(*((unsigned __int16 *)a2 + 6) + *a2) = v37;
    *((_WORD *)a2 + 6) += 4;
    v29 = *((unsigned __int16 *)a2 + 6);
    v30 = *a2;
    *(_OWORD *)(v29 + v30) = MEMORY[0];
    *(_OWORD *)(v29 + v30 + 16) = MEMORY[0x10];
    *(_OWORD *)(v29 + v30 + 32) = MEMORY[0x20];
    *((_WORD *)a2 + 6) += 48;
    *(_QWORD *)(a4 + 8) = 0;
    *(_DWORD *)a4 = 48;
  }
  return IkeReturnError(v27, "IkeConstructNonce");
}

```

## disassembly

```asm
0x1800460c0  mov     [rsp-8+arg_0], rbx
0x1800460c5  push    rbp
0x1800460c6  push    rsi
0x1800460c7  push    rdi
0x1800460c8  push    r12
0x1800460ca  push    r13
0x1800460cc  push    r14
0x1800460ce  push    r15
0x1800460d0  lea     rbp, [rsp-27h]
0x1800460d5  sub     rsp, 0C0h
0x1800460dc  mov     rax, cs:__security_cookie
0x1800460e3  xor     rax, rsp
0x1800460e6  mov     [rbp+57h+var_40], rax
0x1800460ea  xor     r13d, r13d
0x1800460ed  mov     r12, r9
0x1800460f0  mov     [rbp+57h+pbBuffer], r13
0x1800460f4  mov     r14, rdx
0x1800460f7  mov     r15, rcx
0x1800460fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180046101  lea     rax, WPP_GLOBAL_Control
0x180046108  cmp     rcx, rax
0x18004610b  jz      loc_1800461AB
0x180046111  cmp     byte ptr [rcx+19h], 4
0x180046115  jb      loc_1800461AB
0x18004611b  test    byte ptr [rcx+1Ch], 10h
0x18004611f  jz      loc_1800461AB
0x180046125  mov     rdx, cs:gIkeExtGlobals
0x18004612c  test    rdx, rdx
0x18004612f  jz      short loc_180046157
0x180046131  mov     eax, [rdx+0D88h]
0x180046137  cmp     eax, 0FFFFFFFFh
0x18004613a  jz      short loc_180046157
0x18004613c  mov     ecx, eax; dwTlsIndex
0x18004613e  call    cs:__imp_TlsGetValue
0x180046144  mov     rcx, cs:WPP_GLOBAL_Control
0x18004614b  mov     r8, rax
0x18004614e  mov     rdx, cs:gIkeExtGlobals
0x180046155  jmp     short loc_18004615A
0x180046157  mov     r8, r13
0x18004615a  test    r8, r8
0x18004615d  lea     rbx, [r8+8]
0x180046161  cmovz   rbx, r13
0x180046165  test    rdx, rdx
0x180046168  jz      short loc_18004618E
0x18004616a  mov     eax, [rdx+0D88h]
0x180046170  cmp     eax, 0FFFFFFFFh
0x180046173  jz      short loc_18004618E
0x180046175  mov     ecx, eax; dwTlsIndex
0x180046177  call    cs:__imp_TlsGetValue
0x18004617d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046184  test    rax, rax
0x180046187  jz      short loc_18004618E
0x180046189  mov     r9, [rax]
0x18004618c  jmp     short loc_180046191
0x18004618e  mov     r9, r13
0x180046191  mov     rcx, [rcx+10h]
0x180046195  lea     r8, WPP_862de3e8a64a3df216a95f657c5e3376_Traceguids
0x18004619c  mov     edx, 0Ah
0x1800461a1  mov     [rsp+0F0h+var_D0], rbx
0x1800461a6  call    WPP_SF_iS
0x1800461ab  mov     eax, cs:dword_180173278
0x1800461b1  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800461b8  cmp     eax, 4
0x1800461bb  jbe     loc_180046303
0x1800461c1  mov     rax, cs:gIkeExtGlobals
0x1800461c8  test    rax, rax
0x1800461cb  jz      short loc_1800461F6
0x1800461cd  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800461d3  cmp     ecx, 0FFFFFFFFh
0x1800461d6  jz      short loc_1800461F6
0x1800461d8  call    cs:__imp_TlsGetValue
0x1800461de  test    rax, rax
0x1800461e1  jz      short loc_1800461EF
0x1800461e3  mov     rcx, [rax]
0x1800461e6  mov     rax, cs:gIkeExtGlobals
0x1800461ed  jmp     short loc_1800461F9
0x1800461ef  mov     rax, cs:gIkeExtGlobals
0x1800461f6  mov     rcx, r13
0x1800461f9  mov     [rbp+57h+var_B0], rcx
0x1800461fd  lea     rcx, [rbp+57h+var_B0]
0x180046201  mov     [rbp+57h+var_70], rcx
0x180046205  mov     [rbp+57h+var_68], 8
0x18004620d  test    rax, rax
0x180046210  jz      short loc_180046255
0x180046212  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180046218  cmp     ecx, 0FFFFFFFFh
0x18004621b  jz      short loc_180046255
0x18004621d  call    cs:__imp_TlsGetValue
0x180046223  test    rax, rax
0x180046226  lea     rdx, [rax+8]
0x18004622a  cmovz   rdx, r13
0x18004622e  test    rdx, rdx
0x180046231  jz      short loc_180046255
0x180046233  mov     rax, rsi
0x180046236  nop     word ptr [rax+rax+00000000h]
0x180046240  cmp     [rdx+rax*2+2], r13w
0x180046246  lea     rax, [rax+1]
0x18004624a  jnz     short loc_180046240
0x18004624c  lea     eax, ds:2[rax*2]
0x180046253  jmp     short loc_180046261
0x180046255  lea     rdx, LocaleName
0x18004625c  mov     eax, 2
0x180046261  mov     [rbp+57h+var_58], eax
0x180046264  lea     rcx, _TraceLoggingMetadata
0x18004626b  mov     [rbp+57h+var_60], rdx
0x18004626f  lea     rax, aConstructNonce; "Construct NONCE"
0x180046276  mov     [rbp+57h+var_50], rax
0x18004627a  lea     rdx, [rbp+57h+var_A8]
0x18004627e  movzx   eax, cs:word_180164358
0x180046285  xor     r9d, r9d
0x180046288  mov     [rbp+57h+var_A4], eax
0x18004628b  xor     r8d, r8d
0x18004628e  mov     rax, cs:off_180173280
0x180046295  mov     [rbp+57h+var_90], rax
0x180046299  mov     [rbp+57h+var_54], r13d
0x18004629d  mov     [rbp+57h+var_48], 10h
0x1800462a5  mov     [rbp+57h+var_A8], 0B000000h
0x1800462ac  mov     [rbp+57h+var_A0], r13
0x1800462b0  movzx   eax, word ptr [rax]
0x1800462b3  mov     [rbp+57h+var_88], eax
0x1800462b6  lea     rax, word_180164362
0x1800462bd  mov     [rbp+57h+var_80], rax
0x1800462c1  lea     rax, _TraceLoggingMetadataEnd
0x1800462c8  sub     eax, ecx
0x1800462ca  mov     [rbp+57h+var_84], 2
0x1800462d1  mov     [rbp+57h+var_78], 34h ; '4'
0x1800462d8  mov     [rbp+57h+var_74], 1
0x1800462df  mov     [rbp+57h+var_C0], eax
0x1800462e2  mov     eax, [rbp+57h+var_C0]
0x1800462e5  mov     rcx, cs:qword_180173298
0x1800462ec  lea     rax, [rbp+57h+var_90]
0x1800462f0  mov     [rsp+0F0h+var_C8], rax
0x1800462f5  mov     dword ptr [rsp+0F0h+var_D0], 5
0x1800462fd  call    cs:__imp_EtwEventWriteTransfer
0x180046303  lea     r8, [rbp+57h+pbBuffer]
0x180046307  xor     edx, edx; dwFlags
0x180046309  mov     ecx, 30h ; '0'; dwBytes
0x18004630e  call    WfpMemAlloc
0x180046313  mov     rbx, [rbp+57h+pbBuffer]
0x180046317  mov     rdi, rax
0x18004631a  test    rax, rax
0x18004631d  jnz     loc_180046406
0x180046323  mov     rdi, r13
0x180046326  test    rbx, rbx
0x180046329  jz      short loc_180046358
0x18004632b  mov     r9d, 2; dwFlags
0x180046331  mov     r8d, 30h ; '0'; cbBuffer
0x180046337  mov     rdx, rbx; pbBuffer
0x18004633a  xor     ecx, ecx; hAlgorithm
0x18004633c  call    cs:__imp_BCryptGenRandom
0x180046342  test    eax, eax
0x180046344  jz      short loc_180046358
0x180046346  mov     r8d, eax
0x180046349  lea     rdx, aBcryptgenrando_0; "BCryptGenRandom"
0x180046350  call    WfpReportSysErrorAsNtStatus
0x180046355  mov     rdi, rax
0x180046358  lea     rdx, aIkegenrandom; "IkeGenRandom"
0x18004635f  mov     rcx, rdi
0x180046362  call    IkeReturnError
0x180046367  mov     rdi, rax
0x18004636a  test    rax, rax
0x18004636d  jnz     loc_180046406
0x180046373  movzx   eax, word ptr [r14+0Eh]
0x180046378  mov     cl, 28h ; '('
0x18004637a  add     rax, [r14]
0x18004637d  cmp     dword ptr [r15], 2
0x180046381  mov     [rbp+57h+var_C0], r13d
0x180046385  jz      short loc_180046389
0x180046387  mov     cl, 0Ah
0x180046389  mov     [rax], cl
0x18004638b  mov     edx, 34h ; '4'
0x180046390  mov     rcx, r14
0x180046393  call    IkeExpandPacket
0x180046398  mov     rdi, rax
0x18004639b  test    rax, rax
0x18004639e  jnz     short loc_180046406
0x1800463a0  movzx   eax, word ptr [r14+0Ch]
0x1800463a5  mov     ecx, 34h ; '4'; hostshort
0x1800463aa  mov     [r14+0Eh], ax
0x1800463af  call    cs:__imp_htons
0x1800463b5  movzx   edx, word ptr [r14+0Ch]
0x1800463ba  mov     rcx, [r14]
0x1800463bd  mov     word ptr [rbp+57h+var_C0+2], ax
0x1800463c1  mov     eax, [rbp+57h+var_C0]
0x1800463c4  mov     [rdx+rcx], eax
0x1800463c7  add     word ptr [r14+0Ch], 4
0x1800463cd  movups  xmm0, xmmword ptr [rbx]
0x1800463d0  movzx   ecx, word ptr [r14+0Ch]
0x1800463d5  mov     rax, [r14]
0x1800463d8  movups  xmmword ptr [rcx+rax], xmm0
0x1800463dc  movups  xmm1, xmmword ptr [rbx+10h]
0x1800463e0  movups  xmmword ptr [rcx+rax+10h], xmm1
0x1800463e5  movups  xmm0, xmmword ptr [rbx+20h]
0x1800463e9  movups  xmmword ptr [rcx+rax+20h], xmm0
0x1800463ee  add     word ptr [r14+0Ch], 30h ; '0'
0x1800463f4  mov     [r12+8], rbx
0x1800463f9  mov     dword ptr [r12], 30h ; '0'
0x180046401  jmp     loc_1800464CE
0x180046406  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x18004640c  test    al, 10h
0x18004640e  jz      short loc_180046415
0x180046410  and     eax, 1
0x180046413  jmp     short loc_18004641A
0x180046415  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18004641a  test    eax, eax
0x18004641c  jz      short loc_180046493
0x18004641e  cmp     cs:gWfpTrackHeapAllocs, r13d
0x180046425  jz      short loc_180046463
0x180046427  test    rbx, rbx
0x18004642a  jz      short loc_180046463
0x18004642c  lock xadd cs:gWfpNumHeapAllocs, esi
0x180046434  cmp     esi, 1
0x180046437  jns     short loc_180046463
0x180046439  cmp     cs:gMisalignedHeapTelemFired, r13d
0x180046440  jnz     short loc_18004645A
0x180046442  cmp     cs:gWfpNumHeapAllocs, r13d
0x180046449  jg      short loc_180046450
0x18004644b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "gWfpNumHeapAllocs > 0", "allocs and frees are out of sync")
0x180046450  mov     cs:gMisalignedHeapTelemFired, 1
0x18004645a  lock inc cs:gWfpNumHeapAllocs
0x180046461  jmp     short loc_1800464CE
0x180046463  mov     rcx, cs:gWfpHeap; hHeap
0x18004646a  mov     r8, rbx; lpMem
0x18004646d  xor     edx, edx; dwFlags
0x18004646f  call    cs:__imp_HeapFree
0x180046475  cmp     cs:gHeapFreeFailedFired, r13d
0x18004647c  jnz     short loc_1800464CE
0x18004647e  test    eax, eax
0x180046480  jnz     short loc_1800464CE
0x180046482  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "success", "HeapFree failed")
0x180046487  mov     cs:gHeapFreeFailedFired, 1
0x180046491  jmp     short loc_1800464CE
0x180046493  cmp     cs:gWfpTrackHeapBytes, r13d
0x18004649a  jz      short loc_1800464BC
0x18004649c  test    rbx, rbx
0x18004649f  jz      short loc_1800464BC
0x1800464a1  mov     rcx, cs:gWfpHeap; hHeap
0x1800464a8  mov     r8, rbx; lpMem
0x1800464ab  xor     edx, edx; dwFlags
0x1800464ad  call    cs:__imp_HeapSize
0x1800464b3  neg     eax
0x1800464b5  lock add cs:gWfpHeapBytesAllocated, eax
0x1800464bc  mov     rcx, cs:gWfpHeap; hHeap
0x1800464c3  mov     r8, rbx; lpMem
0x1800464c6  xor     edx, edx; dwFlags
0x1800464c8  call    cs:__imp_HeapFree
0x1800464ce  lea     rdx, aIkeconstructno; "IkeConstructNonce"
0x1800464d5  mov     rcx, rdi
0x1800464d8  call    IkeReturnError
0x1800464dd  mov     rcx, [rbp+57h+var_40]
0x1800464e1  xor     rcx, rsp; StackCookie
0x1800464e4  call    __security_check_cookie
0x1800464e9  mov     rbx, [rsp+0F0h+arg_0]
0x1800464f1  add     rsp, 0C0h
0x1800464f8  pop     r15
0x1800464fa  pop     r14
0x1800464fc  pop     r13
0x1800464fe  pop     r12
0x180046500  pop     rdi
0x180046501  pop     rsi
0x180046502  pop     rbp
0x180046503  retn
```
