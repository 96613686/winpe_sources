# SdbCreateHelpCenterURL

- ea: `0x180043730`
- end: `0x180043c56`
- name: `SdbCreateHelpCenterURL`
- size: `1318`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180043c5c`

## callees

- `0x1800055e0`
- `0x18000f114`
- `0x1800159e0`
- `0x180018f20`
- `0x180043354`
- `0x180043730`
- `0x180043de0`
- `0x180045bb8`
- `0x180059270`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180043870`
- `ntdll!RtlAllocateHeap` at `0x180043929`
- `ntdll!RtlAllocateHeap` at `0x1800439e7`
- `ntdll!RtlAllocateHeap` at `0x180043a93`
- `ntdll!RtlAllocateHeap` at `0x180043870`
- `ntdll!RtlAllocateHeap` at `0x180043929`
- `ntdll!RtlAllocateHeap` at `0x1800439e7`
- `ntdll!RtlAllocateHeap` at `0x180043a93`

## string_xrefs

- `0x18004378a`: `hcp://services/layout/fullwindow?topic=`
- `0x18004388b`: `SdbCreateHelpCenterURL`
- `0x1800438c0`: `SdbCreateHelpCenterURL`
- `0x180043af7`: `SdbCreateHelpCenterURL`
- `0x180043b91`: `SdbCreateHelpCenterURL`
- `0x180043bbf`: `SdbCreateHelpCenterURL`
- `0x180043b3a`: `Failed to get size required for CHM file path`
- `0x180043937`: `Failed to allocate CHM file path`
- `0x180043974`: `Failed to retrieve path to CHM file`

## pseudocode

```c
__int64 __fastcall SdbCreateHelpCenterURL(int a1, int a2, unsigned int a3, _OWORD *a4, __int64 a5, unsigned int *a6)
{
  _OWORD *v6; // r12
  __int64 v8; // rdi
  __int64 v9; // rbx
  PVOID v10; // r15
  _WORD *v11; // r14
  int v12; // r13d
  _WORD *Heap; // rax
  _WORD *v14; // rsi
  __int64 v15; // r8
  int v16; // r12d
  unsigned int v17; // r13d
  __int64 BufferCch; // r12
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r13
  char *v22; // rax
  char *v23; // r12
  unsigned int *v24; // r11
  unsigned int v25; // edi
  unsigned int v26; // r10d
  __int64 v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v29; // [rsp+34h] [rbp-CCh]
  int v30; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v31; // [rsp+3Ch] [rbp-C4h]
  __int64 v32; // [rsp+40h] [rbp-C0h]
  unsigned int *v33; // [rsp+48h] [rbp-B8h]
  __int64 v34; // [rsp+50h] [rbp-B0h]
  _WORD v35[16]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v36[3]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t v37; // [rsp+A8h] [rbp-58h]
  _OWORD v38[5]; // [rsp+B0h] [rbp-50h] BYREF
  char v39[24]; // [rsp+100h] [rbp+0h] BYREF

  v6 = a4;
  v34 = a5;
  v30 = a1;
  v38[1] = *(_OWORD *)L"rvices/layout/fullwindow?topic=";
  v38[0] = *(_OWORD *)L"hcp://services/layout/fullwindow?topic=";
  v38[3] = *(_OWORD *)L"llwindow?topic=";
  v38[2] = *(_OWORD *)L"ayout/fullwindow?topic=";
  v38[4] = *(_OWORD *)L"?topic=";
  v33 = a6;
  v31 = a3;
  v28 = 0;
  memset(v35, 0, sizeof(v35));
  v37 = aMsItsLsIdhW2DS[24];
  v36[0] = *(_OWORD *)L"ms-its:%ls::/idh_w2_%d%s";
  v36[1] = *(_OWORD *)L"ls::/idh_w2_%d%s";
  v36[2] = *(_OWORD *)L"_w2_%d%s";
  if ( a2 < 0 )
  {
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v38 + v9) );
    v6 = v38;
    v29 = 0;
    v12 = 0;
    v10 = 0;
    v11 = 0;
  }
  else
  {
    if ( !a4 )
      return 0;
    v8 = -1;
    v29 = 0;
    v9 = -1;
    v10 = 0;
    v11 = 0;
    do
      ++v9;
    while ( *((_WORD *)a4 + v9) );
    v12 = 1;
  }
  v32 = (unsigned int)(v9 + 1);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v32);
  v14 = Heap;
  if ( Heap )
  {
    if ( (int)RtlStringCchCopyW(Heap, v32, v6) < 0 )
    {
      v15 = 2994;
LABEL_14:
      AslLogCallPrintf(1, "SdbCreateHelpCenterURL", v15, "The help URL is too long");
      goto LABEL_49;
    }
    if ( !v12 )
    {
      v16 = v30;
      if ( !(unsigned int)SdbpGetChmFilePath(v30, 0, &v28, 0, 0) || !v28 )
      {
        AslLogCallPrintf(1, "SdbCreateHelpCenterURL", 3014, "Failed to get size required for CHM file path");
        goto LABEL_49;
      }
      v10 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v28);
      if ( !v10 )
      {
        AslLogCallPrintf(1, "SdbCreateHelpCenterURL", 3021, "Failed to allocate CHM file path");
        goto LABEL_49;
      }
      v30 = 16;
      if ( !(unsigned int)SdbpGetChmFilePath(v16, (__int64)v10, &v28, (__int64)v35, (unsigned int *)&v30) )
      {
        AslLogCallPrintf(1, "SdbCreateHelpCenterURL", 3032, "Failed to retrieve path to CHM file");
        goto LABEL_49;
      }
      v17 = v31;
      if ( (int)RtlStringCchPrintfW(v39, 11, L"%d", v31) < 0 )
      {
        AslLogCallPrintf(1, "SdbCreateHelpCenterURL", 3046, "HtmlHelpID is too large for buffer");
        goto LABEL_49;
      }
      BufferCch = (unsigned int)GetBufferCch(v36, v10, v17, v35);
      v11 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * BufferCch);
      if ( !v11 )
      {
        AslLogCallPrintf(1, "SdbCreateHelpCenterURL", 3061, "Failed to allocate help center URL");
        goto LABEL_49;
      }
      LODWORD(v27) = v17;
      if ( (int)RtlStringCchPrintfW(v11, BufferCch, v36, v10, v27, v35) < 0 )
      {
        AslLogCallPrintf(1, "SdbCreateHelpCenterURL", 3075, "Start of helpcenter URL is too long");
        goto LABEL_49;
      }
      v28 = 0;
      if ( !(unsigned int)SdbEscapeApphelpURL(0, &v28, v11) )
      {
        v19 = -1;
        do
          ++v19;
        while ( v11[v19] );
        v20 = v28 + 1 + (_DWORD)v9 + (_DWORD)v19;
        v21 = (unsigned int)v20;
        v22 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v20);
        v23 = v22;
        if ( !v22 )
        {
          AslLogCallPrintf(1, "SdbCreateHelpCenterURL", 3102, "Failed to allocate final URL");
          goto LABEL_49;
        }
        if ( (int)RtlStringCchCopyW(v22, v21, v14) < 0 )
        {
          v15 = 3108;
          goto LABEL_14;
        }
        if ( !(unsigned int)SdbEscapeApphelpURL(&v23[2 * (unsigned int)v9], &v28, v11) )
        {
          AslLogCallPrintf(1, "SdbCreateHelpCenterURL", 3120, "Failed to escape final URL");
          AslFree(NtCurrentPeb()->ProcessHeap, v23);
          goto LABEL_49;
        }
        AslFree(NtCurrentPeb()->ProcessHeap, v14);
        v14 = v23;
      }
    }
    do
      ++v8;
    while ( v14[v8] );
    v24 = v33;
    if ( v33 )
    {
      v25 = v8 + 1;
      v26 = 2 * v25;
      if ( v34 )
      {
        if ( v26 > *v33 )
        {
          AslLogCallPrintf(
            1,
            "SdbCreateHelpCenterURL",
            3147,
            "Buffer too small: need %ld - provided %ld",
            2 * v25,
            *v33);
          goto LABEL_48;
        }
        if ( (int)RtlStringCchCopyW(v34, v25, v14) < 0 )
        {
          AslLogCallPrintf(1, "SdbCreateHelpCenterURL", 3155, "The help URL is too long");
          goto LABEL_48;
        }
      }
      *v24 = v26;
    }
    v29 = 1;
LABEL_48:
    if ( !v14 )
    {
LABEL_50:
      if ( v11 )
        AslFree(NtCurrentPeb()->ProcessHeap, v11);
      if ( v10 )
        AslFree(NtCurrentPeb()->ProcessHeap, v10);
      return v29;
    }
LABEL_49:
    AslFree(NtCurrentPeb()->ProcessHeap, v14);
    goto LABEL_50;
  }
  AslLogCallPrintf(1, "SdbCreateHelpCenterURL", 2988, "Failed to allocate URL buffer");
  return v29;
}

```

## disassembly

```asm
0x180043730  mov     [rsp-8+arg_0], rbx
0x180043735  push    rbp
0x180043736  push    rsi
0x180043737  push    rdi
0x180043738  push    r12
0x18004373a  push    r13
0x18004373c  push    r14
0x18004373e  push    r15
0x180043740  lea     rbp, [rsp-20h]
0x180043745  sub     rsp, 120h
0x18004374c  mov     rax, cs:__security_cookie
0x180043753  xor     rax, rsp
0x180043756  mov     [rbp+50h+var_38], rax
0x18004375a  movaps  xmm1, xmmword ptr cs:aHcpServicesLay+10h; "rvices/layout/fullwindow?topic="
0x180043761  xorps   xmm0, xmm0
0x180043764  mov     rax, [rbp+50h+arg_20]
0x18004376b  mov     r12, r9
0x18004376e  movups  xmmword ptr [rsp+150h+var_F6], xmm0
0x180043773  mov     [rsp+150h+var_100], rax
0x180043778  mov     rax, [rbp+50h+arg_28]
0x18004377f  movups  xmmword ptr [rsp+150h+var_F6+0Eh], xmm0
0x180043784  mov     [rsp+150h+var_118], ecx
0x180043788  xor     ecx, ecx
0x18004378a  movaps  xmm0, xmmword ptr cs:aHcpServicesLay; "hcp://services/layout/fullwindow?topic="
0x180043791  movaps  [rbp+50h+var_90], xmm1
0x180043795  movaps  xmm1, xmmword ptr cs:aHcpServicesLay+30h; "llwindow?topic="
0x18004379c  movaps  [rbp+50h+var_A0], xmm0
0x1800437a0  movaps  xmm0, xmmword ptr cs:aHcpServicesLay+20h; "ayout/fullwindow?topic="
0x1800437a7  movaps  [rbp+50h+var_70], xmm1
0x1800437ab  movaps  [rbp+50h+var_80], xmm0
0x1800437af  movaps  xmm0, xmmword ptr cs:aHcpServicesLay+40h; "?topic="
0x1800437b6  movaps  [rbp+50h+var_60], xmm0
0x1800437ba  mov     [rsp+150h+var_108], rax
0x1800437bf  movzx   eax, word ptr cs:aMsItsLsIdhW2DS+30h; ""
0x1800437c6  mov     [rsp+150h+var_114], r8d
0x1800437cb  mov     [rsp+150h+var_120], ecx
0x1800437cf  mov     [rsp+150h+var_F8], cx
0x1800437d4  mov     [rbp+50h+var_A8], ax
0x1800437d8  movups  xmm1, xmmword ptr cs:aMsItsLsIdhW2DS; "ms-its:%ls::/idh_w2_%d%s"
0x1800437df  movups  xmm0, xmmword ptr cs:aMsItsLsIdhW2DS+10h; "ls::/idh_w2_%d%s"
0x1800437e6  movups  [rsp+150h+var_D8], xmm1
0x1800437eb  movups  xmm1, xmmword ptr cs:aMsItsLsIdhW2DS+20h; "_w2_%d%s"
0x1800437f2  movups  [rbp+50h+var_C8], xmm0
0x1800437f6  movups  [rbp+50h+var_B8], xmm1
0x1800437fa  test    edx, edx
0x1800437fc  js      short loc_18004382D
0x1800437fe  test    r9, r9
0x180043801  jnz     short loc_18004380A
0x180043803  xor     eax, eax
0x180043805  jmp     loc_180043C2F
0x18004380a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004380e  mov     [rsp+150h+var_11C], ecx
0x180043812  mov     rbx, rdi
0x180043815  mov     r15, rcx
0x180043818  mov     r14, rcx
0x18004381b  inc     rbx
0x18004381e  cmp     [r9+rbx*2], cx
0x180043823  jnz     short loc_18004381B
0x180043825  mov     r13d, 1
0x18004382b  jmp     short loc_180043852
0x18004382d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180043831  lea     rax, [rbp+50h+var_A0]
0x180043835  mov     rbx, rdi
0x180043838  inc     rbx
0x18004383b  cmp     [rax+rbx*2], cx
0x18004383f  jnz     short loc_180043838
0x180043841  lea     r12, [rbp+50h+var_A0]
0x180043845  mov     [rsp+150h+var_11C], ecx
0x180043849  mov     r13d, ecx
0x18004384c  mov     r15, rcx
0x18004384f  mov     r14, rcx
0x180043852  mov     rcx, gs:60h
0x18004385b  lea     eax, [rbx+1]
0x18004385e  lea     r8, [rax+rax]; Size
0x180043862  mov     [rsp+150h+var_110], rax
0x180043867  mov     edx, 8; Flags
0x18004386c  mov     rcx, [rcx+30h]; HeapHandle
0x180043870  call    cs:__imp_RtlAllocateHeap
0x180043876  mov     rsi, rax
0x180043879  test    rax, rax
0x18004387c  jnz     short loc_18004389F
0x18004387e  lea     r9, aFailedToAlloca_3; "Failed to allocate URL buffer"
0x180043885  mov     r8d, 0BACh
0x18004388b  lea     rdx, aSdbcreatehelpc_0; "SdbCreateHelpCenterURL"
0x180043892  lea     ecx, [rax+1]
0x180043895  call    AslLogCallPrintf
0x18004389a  jmp     loc_180043C2B
0x18004389f  mov     rdx, [rsp+150h+var_110]
0x1800438a4  mov     r8, r12
0x1800438a7  mov     rcx, rsi
0x1800438aa  call    RtlStringCchCopyW
0x1800438af  test    eax, eax
0x1800438b1  jns     short loc_1800438D6
0x1800438b3  mov     r8d, 0BB2h
0x1800438b9  lea     r9, aTheHelpUrlIsTo; "The help URL is too long"
0x1800438c0  lea     rdx, aSdbcreatehelpc_0; "SdbCreateHelpCenterURL"
0x1800438c7  mov     ecx, 1
0x1800438cc  call    AslLogCallPrintf
0x1800438d1  jmp     loc_180043BE2
0x1800438d6  test    r13d, r13d
0x1800438d9  jnz     loc_180043B4C
0x1800438df  mov     r12d, [rsp+150h+var_118]
0x1800438e4  lea     r8, [rsp+150h+var_120]
0x1800438e9  xor     r13d, r13d
0x1800438ec  mov     ecx, r12d
0x1800438ef  xor     r9d, r9d
0x1800438f2  mov     [rsp+150h+var_130], r13
0x1800438f7  xor     edx, edx
0x1800438f9  call    SdbpGetChmFilePath
0x1800438fe  test    eax, eax
0x180043900  jz      loc_180043B3A
0x180043906  mov     eax, [rsp+150h+var_120]
0x18004390a  test    eax, eax
0x18004390c  jz      loc_180043B3A
0x180043912  mov     rcx, gs:60h
0x18004391b  lea     edx, [r13+8]; Flags
0x18004391f  mov     r8d, eax
0x180043922  add     r8, r8; Size
0x180043925  mov     rcx, [rcx+30h]; HeapHandle
0x180043929  call    cs:__imp_RtlAllocateHeap
0x18004392f  mov     r15, rax
0x180043932  test    rax, rax
0x180043935  jnz     short loc_180043949
0x180043937  lea     r9, aFailedToAlloca_5; "Failed to allocate CHM file path"
0x18004393e  mov     r8d, 0BCDh
0x180043944  jmp     loc_1800438C0
0x180043949  lea     rax, [rsp+150h+var_118]
0x18004394e  mov     [rsp+150h+var_118], 10h
0x180043956  lea     r9, [rsp+150h+var_F8]
0x18004395b  mov     [rsp+150h+var_130], rax
0x180043960  lea     r8, [rsp+150h+var_120]
0x180043965  mov     rdx, r15
0x180043968  mov     ecx, r12d
0x18004396b  call    SdbpGetChmFilePath
0x180043970  test    eax, eax
0x180043972  jnz     short loc_180043986
0x180043974  lea     r9, aFailedToRetrie_0; "Failed to retrieve path to CHM file"
0x18004397b  mov     r8d, 0BD8h
0x180043981  jmp     loc_1800438C0
0x180043986  mov     r13d, [rsp+150h+var_114]
0x18004398b  lea     r8, aD; "%d"
0x180043992  mov     r9d, r13d
0x180043995  lea     rcx, [rbp+50h+var_50]
0x180043999  mov     edx, 0Bh
0x18004399e  call    RtlStringCchPrintfW
0x1800439a3  test    eax, eax
0x1800439a5  jns     short loc_1800439B9
0x1800439a7  lea     r9, aHtmlhelpidIsTo; "HtmlHelpID is too large for buffer"
0x1800439ae  mov     r8d, 0BE6h
0x1800439b4  jmp     loc_1800438C0
0x1800439b9  lea     r9, [rsp+150h+var_F8]
0x1800439be  mov     r8d, r13d
0x1800439c1  mov     rdx, r15
0x1800439c4  lea     rcx, [rsp+150h+var_D8]
0x1800439c9  call    GetBufferCch
0x1800439ce  mov     rcx, gs:60h
0x1800439d7  mov     edx, 8; Flags
0x1800439dc  mov     r12d, eax
0x1800439df  mov     rcx, [rcx+30h]; HeapHandle
0x1800439e3  lea     r8, [r12+r12]; Size
0x1800439e7  call    cs:__imp_RtlAllocateHeap
0x1800439ed  mov     r14, rax
0x1800439f0  test    rax, rax
0x1800439f3  jnz     short loc_180043A07
0x1800439f5  lea     r9, aFailedToAlloca_35; "Failed to allocate help center URL"
0x1800439fc  mov     r8d, 0BF5h
0x180043a02  jmp     loc_1800438C0
0x180043a07  lea     rax, [rsp+150h+var_F8]
0x180043a0c  mov     r9, r15
0x180043a0f  mov     [rsp+150h+var_128], rax
0x180043a14  lea     r8, [rsp+150h+var_D8]
0x180043a19  mov     rdx, r12
0x180043a1c  mov     dword ptr [rsp+150h+var_130], r13d
0x180043a21  mov     rcx, r14
0x180043a24  call    RtlStringCchPrintfW
0x180043a29  xor     r13d, r13d
0x180043a2c  test    eax, eax
0x180043a2e  jns     short loc_180043A42
0x180043a30  lea     r9, aStartOfHelpcen; "Start of helpcenter URL is too long"
0x180043a37  mov     r8d, 0C03h
0x180043a3d  jmp     loc_1800438C0
0x180043a42  mov     r8, r14
0x180043a45  mov     [rsp+150h+var_120], r13d
0x180043a4a  lea     rdx, [rsp+150h+var_120]
0x180043a4f  xor     ecx, ecx
0x180043a51  call    SdbEscapeApphelpURL
0x180043a56  test    eax, eax
0x180043a58  jnz     loc_180043B4F
0x180043a5e  mov     rax, rdi
0x180043a61  inc     rax
0x180043a64  cmp     [r14+rax*2], r13w
0x180043a69  jnz     short loc_180043A61
0x180043a6b  lea     ecx, [rbx+rax]
0x180043a6e  mov     edx, 8; Flags
0x180043a73  mov     eax, [rsp+150h+var_120]
0x180043a77  inc     eax
0x180043a79  add     ecx, eax
0x180043a7b  mov     r13d, ecx
0x180043a7e  lea     r8, ds:0[rcx*2]; Size
0x180043a86  mov     rcx, gs:60h
0x180043a8f  mov     rcx, [rcx+30h]; HeapHandle
0x180043a93  call    cs:__imp_RtlAllocateHeap
0x180043a99  mov     r12, rax
0x180043a9c  test    rax, rax
0x180043a9f  jnz     short loc_180043AB3
0x180043aa1  lea     r9, aFailedToAlloca_16; "Failed to allocate final URL"
0x180043aa8  mov     r8d, 0C1Eh
0x180043aae  jmp     loc_1800438C0
0x180043ab3  mov     r8, rsi
0x180043ab6  mov     rdx, r13
0x180043ab9  mov     rcx, r12
0x180043abc  call    RtlStringCchCopyW
0x180043ac1  xor     r13d, r13d
0x180043ac4  test    eax, eax
0x180043ac6  jns     short loc_180043AD3
0x180043ac8  mov     r8d, 0C24h
0x180043ace  jmp     loc_1800438B9
0x180043ad3  mov     eax, ebx
0x180043ad5  lea     rdx, [rsp+150h+var_120]
0x180043ada  mov     r8, r14
0x180043add  lea     rcx, [r12+rax*2]
0x180043ae1  call    SdbEscapeApphelpURL
0x180043ae6  test    eax, eax
0x180043ae8  jnz     short loc_180043B20
0x180043aea  lea     r9, aFailedToEscape; "Failed to escape final URL"
0x180043af1  mov     r8d, 0C30h
0x180043af7  lea     rdx, aSdbcreatehelpc_0; "SdbCreateHelpCenterURL"
0x180043afe  lea     ecx, [rax+1]
0x180043b01  call    AslLogCallPrintf
0x180043b06  mov     rcx, gs:60h
0x180043b0f  mov     rdx, r12
0x180043b12  mov     rcx, [rcx+30h]
0x180043b16  call    AslFree
0x180043b1b  jmp     loc_180043BE2
0x180043b20  mov     rcx, gs:60h
0x180043b29  mov     rdx, rsi
0x180043b2c  mov     rcx, [rcx+30h]
0x180043b30  call    AslFree
0x180043b35  mov     rsi, r12
0x180043b38  jmp     short loc_180043B4F
0x180043b3a  lea     r9, aFailedToGetSiz; "Failed to get size required for CHM fil"...
0x180043b41  mov     r8d, 0BC6h
0x180043b47  jmp     loc_1800438C0
0x180043b4c  xor     r13d, r13d
0x180043b4f  inc     rdi
0x180043b52  cmp     [rsi+rdi*2], r13w
0x180043b57  jnz     short loc_180043B4F
0x180043b59  mov     r11, [rsp+150h+var_108]
0x180043b5e  test    r11, r11
0x180043b61  jz      short loc_180043BD5
0x180043b63  mov     rcx, [rsp+150h+var_100]
0x180043b68  inc     edi
0x180043b6a  lea     r10d, [rdi+rdi]
0x180043b6e  test    rcx, rcx
0x180043b71  jz      short loc_180043BD2
0x180043b73  mov     eax, [r11]
0x180043b76  cmp     r10d, eax
0x180043b79  jbe     short loc_180043BA4
0x180043b7b  mov     dword ptr [rsp+150h+var_128], eax
0x180043b7f  lea     r9, aBufferTooSmall_3; "Buffer too small: need %ld - provided %"...
0x180043b86  mov     r8d, 0C4Bh
0x180043b8c  mov     dword ptr [rsp+150h+var_130], r10d
0x180043b91  lea     rdx, aSdbcreatehelpc_0; "SdbCreateHelpCenterURL"
0x180043b98  mov     ecx, 1
0x180043b9d  call    AslLogCallPrintf
0x180043ba2  jmp     short loc_180043BDD
0x180043ba4  mov     edx, edi
0x180043ba6  mov     r8, rsi
0x180043ba9  call    RtlStringCchCopyW
0x180043bae  test    eax, eax
0x180043bb0  jns     short loc_180043BD2
0x180043bb2  lea     r9, aTheHelpUrlIsTo; "The help URL is too long"
0x180043bb9  mov     r8d, 0C53h
0x180043bbf  lea     rdx, aSdbcreatehelpc_0; "SdbCreateHelpCenterURL"
0x180043bc6  mov     ecx, 1
0x180043bcb  call    AslLogCallPrintf
0x180043bd0  jmp     short loc_180043BDD
0x180043bd2  mov     [r11], r10d
0x180043bd5  mov     [rsp+150h+var_11C], 1
0x180043bdd  test    rsi, rsi
0x180043be0  jz      short loc_180043BF7
0x180043be2  mov     rcx, gs:60h
0x180043beb  mov     rdx, rsi
0x180043bee  mov     rcx, [rcx+30h]
0x180043bf2  call    AslFree
0x180043bf7  test    r14, r14
0x180043bfa  jz      short loc_180043C11
0x180043bfc  mov     rcx, gs:60h
0x180043c05  mov     rdx, r14
0x180043c08  mov     rcx, [rcx+30h]
0x180043c0c  call    AslFree
0x180043c11  test    r15, r15
0x180043c14  jz      short loc_180043C2B
0x180043c16  mov     rcx, gs:60h
0x180043c1f  mov     rdx, r15
0x180043c22  mov     rcx, [rcx+30h]
0x180043c26  call    AslFree
0x180043c2b  mov     eax, [rsp+150h+var_11C]
0x180043c2f  mov     rcx, [rbp+50h+var_38]
0x180043c33  xor     rcx, rsp; StackCookie
  ... truncated ...
```
