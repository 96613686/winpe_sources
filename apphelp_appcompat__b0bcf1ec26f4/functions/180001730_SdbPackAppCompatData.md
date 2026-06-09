# SdbPackAppCompatData

- ea: `0x180001730`
- end: `0x180001cdc`
- name: `SdbPackAppCompatData`
- size: `1452`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180001ea0`

## callees

- `0x180001730`
- `0x18000f114`
- `0x180018f20`
- `0x180019df8`
- `0x18002bed4`
- `0x180032290`
- `0x180037b2c`
- `0x180038240`
- `0x18003f6f0`
- `0x180052d08`
- `0x18005921d`
- `0x180059270`

## import_xrefs

- `ntdll!RtlQueryEnvironmentVariable_U` at `0x180001916`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x180001916`
- `ntdll!RtlInitUnicodeString` at `0x1800018f4`
- `ntdll!RtlInitUnicodeString` at `0x1800018f4`
- `ntdll!RtlFreeHeap` at `0x180001a6f`
- `ntdll!RtlFreeHeap` at `0x180001a92`
- `ntdll!RtlFreeHeap` at `0x180001bf2`
- `ntdll!RtlFreeHeap` at `0x180001c17`
- `ntdll!RtlFreeHeap` at `0x180001c3e`
- `ntdll!RtlFreeHeap` at `0x180001c99`
- `ntdll!RtlFreeHeap` at `0x180001a6f`
- `ntdll!RtlFreeHeap` at `0x180001a92`
- `ntdll!RtlFreeHeap` at `0x180001bf2`
- `ntdll!RtlFreeHeap` at `0x180001c17`
- `ntdll!RtlFreeHeap` at `0x180001c3e`
- `ntdll!RtlFreeHeap` at `0x180001c99`
- `ntdll!RtlAllocateHeap` at `0x18000181c`
- `ntdll!RtlAllocateHeap` at `0x180001a0c`
- `ntdll!RtlAllocateHeap` at `0x180001b68`
- `ntdll!RtlAllocateHeap` at `0x18000181c`
- `ntdll!RtlAllocateHeap` at `0x180001a0c`
- `ntdll!RtlAllocateHeap` at `0x180001b68`

## string_xrefs

- `0x1800017ec`: `SdbPackAppCompatData`
- `0x18000183a`: `SdbPackAppCompatData`
- `0x180001921`: `SdbPackAppCompatData`
- `0x1800019e5`: `RtlDWordAdd failed to compute required buffer size [%x]`
- `0x180001b44`: `RtlDWordAdd failed to compute required buffer size [%x]`
- `0x180001ae3`: `Failed to create mini pdb [%x]`
- `0x180001bb3`: `SdbCopyPdbToBuffer failed to copy pdb [%x]`
- `0x1800018c6`: `__COMPAT_LAYER`

## pseudocode

```c
__int64 __fastcall SdbPackAppCompatData(__int64 a1, __int64 a2, PVOID *a3, unsigned int *a4)
{
  char *v4; // rdi
  unsigned __int16 *v5; // r12
  unsigned int v6; // r13d
  char *v7; // rsi
  unsigned int v10; // r14d
  char *Heap; // rax
  __int64 v12; // rdx
  _OWORD *v13; // rcx
  _OWORD *v14; // rax
  __int128 v15; // xmm1
  NTSTATUS v16; // ecx
  int v17; // ecx
  unsigned int v18; // eax
  char *v19; // rax
  PVOID *v20; // rdi
  int v21; // eax
  __int128 v22; // xmm0
  int v23; // eax
  const char *v24; // r9
  __int64 v25; // r8
  unsigned int v26; // ebx
  char *v27; // rax
  int v28; // eax
  PVOID *v29; // rbx
  int v30; // eax
  unsigned int *v31; // rax
  __int64 v33; // [rsp+20h] [rbp-69h]
  int v34; // [rsp+30h] [rbp-59h]
  void *Src; // [rsp+38h] [rbp-51h] BYREF
  int v36[2]; // [rsp+40h] [rbp-49h]
  PVOID *v37; // [rsp+48h] [rbp-41h]
  __int64 v38; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING Value; // [rsp+58h] [rbp-31h] BYREF
  unsigned int *v40; // [rsp+68h] [rbp-21h]
  _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-19h] BYREF
  __int64 v42[2]; // [rsp+80h] [rbp-9h] BYREF

  v4 = (char *)*a3;
  v5 = 0;
  v40 = a4;
  v6 = 0;
  v37 = a3;
  v7 = 0;
  *(_QWORD *)v36 = a1;
  Src = 0;
  v38 = 0;
  DestinationString = 0;
  Value = 0;
  *(_OWORD *)v42 = 0;
  if ( !v4 )
  {
    v10 = 4568;
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x11D8u);
    v4 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "SdbPackAppCompatData", 101, "Failed to allocate %d bytes", 4568);
      return v6;
    }
    v34 = 1;
    *((_DWORD *)Heap + 130) = 4568;
    *((_DWORD *)Heap + 131) = -1408373333;
LABEL_13:
    v12 = 3;
    v13 = v4 + 536;
    v14 = (_OWORD *)a2;
    do
    {
      *v13 = *v14;
      v13[1] = v14[1];
      v13[2] = v14[2];
      v13[3] = v14[3];
      v13[4] = v14[4];
      v13[5] = v14[5];
      v13[6] = v14[6];
      v15 = v14[7];
      v14 += 8;
      v13[7] = v15;
      v13 += 8;
      --v12;
    }
    while ( v12 );
    *v13 = *v14;
    v13[1] = v14[1];
    v13[2] = v14[2];
    v13[3] = v14[3];
    *((_QWORD *)v13 + 8) = *((_QWORD *)v14 + 8);
    RtlInitUnicodeString(&DestinationString, L"__COMPAT_LAYER");
    *(_DWORD *)&Value.Length = 0x2000000;
    Value.Buffer = (PWSTR)(v4 + 3396);
    v16 = RtlQueryEnvironmentVariable_U(0, &DestinationString, &Value);
    if ( (int)(v16 + 0x80000000) >= 0 && v16 != -1073741568 )
      AslLogCallPrintf(1, "SdbPackAppCompatData", 134, "Failed to query environment variable [%x]", v16);
    SdbUnpackCustomSdbs(*(_QWORD *)v36, a2);
    ParseCobaltFlags(v4, *(_QWORD *)v36);
    v17 = v36[0];
    *((_WORD *)v4 + 266) = *(_WORD *)(*(_QWORD *)v36 + 584LL);
    *((_QWORD *)v4 + 567) = 0;
    if ( *(_DWORD *)a2 || *(_DWORD *)(a2 + 128) )
      *((_DWORD *)v4 + 132) = 1;
    if ( *((_DWORD *)v4 + 132) )
    {
      ParseCobaltProcFlagsFromQueryResult2Alloc((__int64)&Src, (__int64)v42, v17);
      v5 = (unsigned __int16 *)Src;
      if ( Src )
      {
        v18 = *(unsigned __int16 *)Src;
        LODWORD(Src) = v18 + 4568;
        if ( v18 + 4568 < v18 )
        {
          LODWORD(v33) = -1073741675;
          AslLogCallPrintf(
            1,
            "SdbPackAppCompatData",
            167,
            "RtlDWordAdd failed to compute required buffer size [%x]",
            v33);
LABEL_44:
          if ( v4 && v34 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
          goto LABEL_55;
        }
        v19 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v18 + 4568);
        v7 = v19;
        if ( !v19 )
        {
          LODWORD(v33) = (_DWORD)Src;
          AslLogCallPrintf(1, "SdbPackAppCompatData", 173, "Failed to allocate %d bytes", v33);
          goto LABEL_44;
        }
        memcpy_0(v19, v4, 0x11D8u);
        memcpy_0(v7 + 4568, v5, *v5);
        if ( v34 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
        }
        else
        {
          v20 = v37;
          if ( *v37 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v37);
            *v20 = 0;
          }
        }
        v21 = *v5;
        v4 = v7;
        v22 = *(_OWORD *)v42;
        *((_DWORD *)v7 + 1137) = 4568;
        v10 = (unsigned int)Src;
        *(_OWORD *)(v7 + 4552) = v22;
        *((_DWORD *)v7 + 1136) = v21;
        v34 = 1;
      }
      v23 = SdbQueryResultsToMiniDb(*(_QWORD *)v36, a2, &v38);
      if ( v23 < 0 )
      {
        v24 = "Failed to create mini pdb [%x]";
        v25 = 219;
LABEL_34:
        LODWORD(v33) = v23;
        AslLogCallPrintf(1, "SdbPackAppCompatData", v25, v24, v33);
LABEL_35:
        v7 = 0;
        goto LABEL_44;
      }
      LODWORD(Src) = 0;
      v23 = SdbCopyPdbToBuffer(v38, 0, &Src);
      if ( v23 != -1073741789 )
      {
        v24 = "SdbPackAppExeDataWithPdb failed to return size required [%x]";
        v25 = 226;
        goto LABEL_34;
      }
      v26 = (_DWORD)Src + v10;
      v36[0] = (_DWORD)Src + v10;
      if ( (unsigned int)Src + v10 < (unsigned int)Src )
      {
        LODWORD(v33) = -1073741675;
        AslLogCallPrintf(1, "SdbPackAppCompatData", 232, "RtlDWordAdd failed to compute required buffer size [%x]", v33);
        goto LABEL_35;
      }
      v27 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v26);
      v7 = v27;
      if ( !v27 )
      {
        LODWORD(v33) = v26;
        AslLogCallPrintf(1, "SdbPackAppCompatData", 238, "Failed to allocate %d bytes", v33);
        goto LABEL_44;
      }
      memcpy_0(v27, v4, v10);
      v28 = SdbCopyPdbToBuffer(v38, &v7[v10], &Src);
      if ( v28 < 0 )
      {
        LODWORD(v33) = v28;
        AslLogCallPrintf(1, "SdbPackAppCompatData", 249, "SdbCopyPdbToBuffer failed to copy pdb [%x]", v33);
        goto LABEL_44;
      }
      if ( v34 && v4 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
        v29 = v37;
      }
      else
      {
        v29 = v37;
        if ( *v37 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v37);
      }
      v30 = (int)Src;
      v4 = v7;
      *((_DWORD *)v7 + 1135) = v10;
      v10 = v36[0];
      *((_DWORD *)v7 + 1134) = v30;
    }
    else
    {
      v29 = v37;
    }
    v31 = v40;
    v7 = 0;
    *v29 = v4;
    *v31 = v10;
    v6 = 1;
    goto LABEL_55;
  }
  if ( (*(_BYTE *)(a2 + 192) & 0x40) != 0 && !*((_DWORD *)v4 + 1107) && !*((_DWORD *)v4 + 1108) )
    SdbAddLayerTagRefToQuery(a1, a2, L"ApplicationMonitor");
  v10 = 4568;
  if ( *a4 == 4568 && *((_DWORD *)v4 + 130) == 4568 )
  {
    v34 = 0;
    if ( *((_DWORD *)v4 + 131) == -1408373333 )
      goto LABEL_13;
  }
  AslLogCallPrintf(1, "SdbPackAppCompatData", 95, "Invalid arguments");
LABEL_55:
  if ( v38 )
    SdbCloseDatabase(v38);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v5 )
    AslFree(NtCurrentPeb()->ProcessHeap, v5);
  return v6;
}

```

## disassembly

```asm
0x180001730  push    rbp
0x180001732  push    rbx
0x180001733  push    rsi
0x180001734  push    rdi
0x180001735  push    r12
0x180001737  push    r13
0x180001739  push    r14
0x18000173b  push    r15
0x18000173d  lea     rbp, [rsp-1Fh]
0x180001742  sub     rsp, 0A8h
0x180001749  mov     rax, cs:__security_cookie
0x180001750  xor     rax, rsp
0x180001753  mov     [rbp+57h+var_50], rax
0x180001757  mov     rdi, [r8]
0x18000175a  xor     r12d, r12d
0x18000175d  xorps   xmm0, xmm0
0x180001760  mov     [rbp+57h+var_78], r9
0x180001764  xor     r13d, r13d
0x180001767  mov     [rbp+57h+var_98], r8
0x18000176b  xor     esi, esi
0x18000176d  mov     qword ptr [rbp+57h+var_A0], rcx
0x180001771  mov     [rbp+57h+Src], r12
0x180001775  xorps   xmm1, xmm1
0x180001778  mov     [rbp+57h+var_90], r12
0x18000177c  mov     r15, r9
0x18000177f  mov     rbx, rdx
0x180001782  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180001786  movups  xmmword ptr [rbp+57h+Value.Length], xmm1
0x18000178a  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18000178e  test    rdi, rdi
0x180001791  jz      short loc_180001801
0x180001793  test    byte ptr [rdx+0C0h], 40h
0x18000179a  jz      short loc_1800017B8
0x18000179c  cmp     [rdi+114Ch], esi
0x1800017a2  jnz     short loc_1800017B8
0x1800017a4  cmp     [rdi+1150h], esi
0x1800017aa  jnz     short loc_1800017B8
0x1800017ac  lea     r8, aApplicationmon; "ApplicationMonitor"
0x1800017b3  call    SdbAddLayerTagRefToQuery
0x1800017b8  mov     r14d, 11D8h
0x1800017be  cmp     [r15], r14d
0x1800017c1  jnz     short loc_1800017DF
0x1800017c3  cmp     [rdi+208h], r14d
0x1800017ca  jnz     short loc_1800017DF
0x1800017cc  cmp     dword ptr [rdi+20Ch], 0AC0DEDABh
0x1800017d6  mov     [rbp+57h+var_B0], esi
0x1800017d9  jz      loc_180001866
0x1800017df  mov     r8d, 5Fh ; '_'
0x1800017e5  lea     r9, aInvalidArgumen_0; "Invalid arguments"
0x1800017ec  lea     rdx, aSdbpackappcomp_0; "SdbPackAppCompatData"
0x1800017f3  lea     ecx, [r8-5Eh]
0x1800017f7  call    AslLogCallPrintf
0x1800017fc  jmp     loc_180001C71
0x180001801  mov     rcx, gs:60h
0x18000180a  mov     r14d, 11D8h
0x180001810  mov     r8d, r14d; Size
0x180001813  mov     edx, 8; Flags
0x180001818  mov     rcx, [rcx+30h]; HeapHandle
0x18000181c  call    cs:__imp_RtlAllocateHeap
0x180001822  mov     rdi, rax
0x180001825  test    rax, rax
0x180001828  jnz     short loc_18000184E
0x18000182a  lea     r9, aFailedToAlloca_34; "Failed to allocate %d bytes"
0x180001831  mov     [rsp+0E0h+var_C0], r14d
0x180001836  lea     r8d, [rax+65h]
0x18000183a  lea     rdx, aSdbpackappcomp_0; "SdbPackAppCompatData"
0x180001841  lea     ecx, [rax+1]
0x180001844  call    AslLogCallPrintf
0x180001849  jmp     loc_180001CB9
0x18000184e  mov     [rbp+57h+var_B0], 1
0x180001855  mov     [rax+208h], r14d
0x18000185c  mov     dword ptr [rax+20Ch], 0AC0DEDABh
0x180001866  mov     edx, 3
0x18000186b  lea     rcx, [rdi+218h]
0x180001872  mov     rax, rbx
0x180001875  lea     r8d, [rdx+7Dh]
0x180001879  movups  xmm0, xmmword ptr [rax]
0x18000187c  movups  xmmword ptr [rcx], xmm0
0x18000187f  movups  xmm1, xmmword ptr [rax+10h]
0x180001883  movups  xmmword ptr [rcx+10h], xmm1
0x180001887  movups  xmm0, xmmword ptr [rax+20h]
0x18000188b  movups  xmmword ptr [rcx+20h], xmm0
0x18000188f  movups  xmm1, xmmword ptr [rax+30h]
0x180001893  movups  xmmword ptr [rcx+30h], xmm1
0x180001897  movups  xmm0, xmmword ptr [rax+40h]
0x18000189b  movups  xmmword ptr [rcx+40h], xmm0
0x18000189f  movups  xmm1, xmmword ptr [rax+50h]
0x1800018a3  movups  xmmword ptr [rcx+50h], xmm1
0x1800018a7  movups  xmm0, xmmword ptr [rax+60h]
0x1800018ab  movups  xmmword ptr [rcx+60h], xmm0
0x1800018af  movups  xmm1, xmmword ptr [rax+70h]
0x1800018b3  add     rax, r8
0x1800018b6  movups  xmmword ptr [rcx+70h], xmm1
0x1800018ba  add     rcx, r8
0x1800018bd  sub     rdx, 1
0x1800018c1  jnz     short loc_180001879
0x1800018c3  movups  xmm0, xmmword ptr [rax]
0x1800018c6  lea     rdx, SourceString; "__COMPAT_LAYER"
0x1800018cd  movups  xmmword ptr [rcx], xmm0
0x1800018d0  movups  xmm1, xmmword ptr [rax+10h]
0x1800018d4  movups  xmmword ptr [rcx+10h], xmm1
0x1800018d8  movups  xmm0, xmmword ptr [rax+20h]
0x1800018dc  movups  xmmword ptr [rcx+20h], xmm0
0x1800018e0  movups  xmm1, xmmword ptr [rax+30h]
0x1800018e4  movups  xmmword ptr [rcx+30h], xmm1
0x1800018e8  mov     rax, [rax+40h]
0x1800018ec  mov     [rcx+40h], rax
0x1800018f0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800018f4  call    cs:__imp_RtlInitUnicodeString
0x1800018fa  lea     rax, [rdi+0D44h]
0x180001901  mov     dword ptr [rbp+57h+Value.Length], 2000000h
0x180001908  lea     r8, [rbp+57h+Value]; Value
0x18000190c  mov     [rbp+57h+Value.Buffer], rax
0x180001910  lea     rdx, [rbp+57h+DestinationString]; Name
0x180001914  xor     ecx, ecx; Environment
0x180001916  call    cs:__imp_RtlQueryEnvironmentVariable_U
0x18000191c  mov     edx, 80000000h
0x180001921  lea     r15, aSdbpackappcomp_0; "SdbPackAppCompatData"
0x180001928  mov     ecx, eax
0x18000192a  add     eax, edx
0x18000192c  test    edx, eax
0x18000192e  jnz     short loc_180001956
0x180001930  cmp     ecx, 0C0000100h
0x180001936  jz      short loc_180001956
0x180001938  mov     [rsp+0E0h+var_C0], ecx
0x18000193c  lea     r9, aFailedToQueryE; "Failed to query environment variable [%"...
0x180001943  mov     ecx, 1
0x180001948  mov     r8d, 86h
0x18000194e  mov     rdx, r15
0x180001951  call    AslLogCallPrintf
0x180001956  mov     rcx, qword ptr [rbp+57h+var_A0]
0x18000195a  mov     rdx, rbx
0x18000195d  call    SdbUnpackCustomSdbs
0x180001962  mov     rdx, qword ptr [rbp+57h+var_A0]
0x180001966  mov     rcx, rdi
0x180001969  call    ParseCobaltFlags
0x18000196e  mov     rcx, qword ptr [rbp+57h+var_A0]
0x180001972  movzx   eax, word ptr [rcx+248h]
0x180001979  mov     [rdi+214h], ax
0x180001980  xor     eax, eax
0x180001982  mov     [rdi+11B8h], rax
0x180001989  cmp     [rbx], eax
0x18000198b  jnz     short loc_180001995
0x18000198d  cmp     [rbx+80h], eax
0x180001993  jz      short loc_18000199F
0x180001995  mov     dword ptr [rdi+210h], 1
0x18000199f  cmp     [rdi+210h], eax
0x1800019a5  jz      loc_180001C5D
0x1800019ab  mov     r8, rcx; int
0x1800019ae  lea     rdx, [rbp+57h+var_60]; __int64
0x1800019b2  lea     rcx, [rbp+57h+Src]; __int64
0x1800019b6  mov     r9, rbx
0x1800019b9  call    ParseCobaltProcFlagsFromQueryResult2Alloc
0x1800019be  mov     r12, [rbp+57h+Src]
0x1800019c2  test    r12, r12
0x1800019c5  jz      loc_180001ACA
0x1800019cb  movzx   eax, word ptr [r12]
0x1800019d0  lea     ecx, [rax+11D8h]
0x1800019d6  mov     dword ptr [rbp+57h+Src], ecx
0x1800019d9  cmp     ecx, eax
0x1800019db  jnb     short loc_1800019F7
0x1800019dd  mov     [rsp+0E0h+var_C0], 0C0000095h
0x1800019e5  lea     r9, aRtldwordaddFai; "RtlDWordAdd failed to compute required "...
0x1800019ec  mov     r8d, 0A7h
0x1800019f2  jmp     loc_180001BC0
0x1800019f7  mov     r8d, ecx; Size
0x1800019fa  mov     edx, 8; Flags
0x1800019ff  mov     rcx, gs:60h
0x180001a08  mov     rcx, [rcx+30h]; HeapHandle
0x180001a0c  call    cs:__imp_RtlAllocateHeap
0x180001a12  mov     rsi, rax
0x180001a15  test    rax, rax
0x180001a18  jnz     short loc_180001A35
0x180001a1a  mov     r14d, dword ptr [rbp+57h+Src]
0x180001a1e  lea     r9, aFailedToAlloca_34; "Failed to allocate %d bytes"
0x180001a25  mov     [rsp+0E0h+var_C0], r14d
0x180001a2a  mov     r8d, 0ADh
0x180001a30  jmp     loc_180001BC0
0x180001a35  mov     r8, r14; Size
0x180001a38  mov     rdx, rdi; Src
0x180001a3b  mov     rcx, rsi; void *
0x180001a3e  call    memcpy_0
0x180001a43  movzx   r8d, word ptr [r12]; Size
0x180001a48  lea     rcx, [rsi+11D8h]; void *
0x180001a4f  mov     rdx, r12; Src
0x180001a52  call    memcpy_0
0x180001a57  cmp     [rbp+57h+var_B0], r13d
0x180001a5b  jz      short loc_180001A77
0x180001a5d  mov     rcx, gs:60h
0x180001a66  mov     r8, rdi; P
0x180001a69  xor     edx, edx; Flags
0x180001a6b  mov     rcx, [rcx+30h]; HeapHandle
0x180001a6f  call    cs:__imp_RtlFreeHeap
0x180001a75  jmp     short loc_180001A9B
0x180001a77  mov     rdi, [rbp+57h+var_98]
0x180001a7b  mov     r8, [rdi]; P
0x180001a7e  test    r8, r8
0x180001a81  jz      short loc_180001A9B
0x180001a83  mov     rcx, gs:60h
0x180001a8c  xor     edx, edx; Flags
0x180001a8e  mov     rcx, [rcx+30h]; HeapHandle
0x180001a92  call    cs:__imp_RtlFreeHeap
0x180001a98  mov     [rdi], r13
0x180001a9b  movzx   eax, word ptr [r12]
0x180001aa0  mov     rdi, rsi
0x180001aa3  movups  xmm0, xmmword ptr [rbp+57h+var_60]
0x180001aa7  mov     [rsi+11C4h], r14d
0x180001aae  mov     r14d, dword ptr [rbp+57h+Src]
0x180001ab2  movdqu  xmmword ptr [rsi+11C8h], xmm0
0x180001aba  mov     [rsi+11C0h], eax
0x180001ac0  mov     esi, 1
0x180001ac5  mov     [rbp+57h+var_B0], esi
0x180001ac8  jmp     short loc_180001ACF
0x180001aca  mov     esi, 1
0x180001acf  mov     rcx, qword ptr [rbp+57h+var_A0]
0x180001ad3  lea     r8, [rbp+57h+var_90]
0x180001ad7  mov     rdx, rbx
0x180001ada  call    SdbQueryResultsToMiniDb
0x180001adf  test    eax, eax
0x180001ae1  jns     short loc_180001B05
0x180001ae3  lea     r9, aFailedToCreate_27; "Failed to create mini pdb [%x]"
0x180001aea  mov     r8d, 0DBh
0x180001af0  mov     [rsp+0E0h+var_C0], eax
0x180001af4  mov     rdx, r15
0x180001af7  mov     ecx, esi
0x180001af9  call    AslLogCallPrintf
0x180001afe  xor     esi, esi
0x180001b00  jmp     loc_180001BCD
0x180001b05  mov     rcx, [rbp+57h+var_90]
0x180001b09  lea     r8, [rbp+57h+Src]
0x180001b0d  xor     edx, edx
0x180001b0f  mov     dword ptr [rbp+57h+Src], r13d
0x180001b13  call    SdbCopyPdbToBuffer
0x180001b18  cmp     eax, 0C0000023h
0x180001b1d  jz      short loc_180001B2E
0x180001b1f  lea     r9, aSdbpackappexed; "SdbPackAppExeDataWithPdb failed to retu"...
0x180001b26  mov     r8d, 0E2h
0x180001b2c  jmp     short loc_180001AF0
0x180001b2e  mov     eax, dword ptr [rbp+57h+Src]
0x180001b31  lea     ebx, [rax+r14]
0x180001b35  mov     [rbp+57h+var_A0], ebx
0x180001b38  cmp     ebx, eax
0x180001b3a  jnb     short loc_180001B53
0x180001b3c  mov     [rsp+0E0h+var_C0], 0C0000095h
0x180001b44  lea     r9, aRtldwordaddFai; "RtlDWordAdd failed to compute required "...
0x180001b4b  mov     r8d, 0E8h
0x180001b51  jmp     short loc_180001AF4
0x180001b53  mov     rcx, gs:60h
0x180001b5c  mov     edx, 8; Flags
0x180001b61  mov     r8d, ebx; Size
0x180001b64  mov     rcx, [rcx+30h]; HeapHandle
0x180001b68  call    cs:__imp_RtlAllocateHeap
0x180001b6e  mov     rsi, rax
0x180001b71  test    rax, rax
0x180001b74  jnz     short loc_180001B89
0x180001b76  mov     [rsp+0E0h+var_C0], ebx
0x180001b7a  lea     r9, aFailedToAlloca_34; "Failed to allocate %d bytes"
0x180001b81  mov     r8d, 0EEh
0x180001b87  jmp     short loc_180001BC0
0x180001b89  mov     r8d, r14d; Size
0x180001b8c  mov     rdx, rdi; Src
0x180001b8f  mov     rcx, rsi; void *
0x180001b92  mov     ebx, r14d
0x180001b95  call    memcpy_0
0x180001b9a  mov     rcx, [rbp+57h+var_90]
0x180001b9e  lea     rdx, [rbx+rsi]
0x180001ba2  lea     r8, [rbp+57h+Src]
0x180001ba6  call    SdbCopyPdbToBuffer
0x180001bab  test    eax, eax
0x180001bad  jns     short loc_180001BFA
0x180001baf  mov     [rsp+0E0h+var_C0], eax
0x180001bb3  lea     r9, aSdbcopypdbtobu; "SdbCopyPdbToBuffer failed to copy pdb ["...
0x180001bba  mov     r8d, 0F9h
0x180001bc0  mov     rdx, r15
0x180001bc3  mov     ecx, 1
0x180001bc8  call    AslLogCallPrintf
0x180001bcd  test    rdi, rdi
0x180001bd0  jz      loc_180001C71
0x180001bd6  cmp     [rbp+57h+var_B0], r13d
0x180001bda  jz      loc_180001C71
0x180001be0  mov     rcx, gs:60h
0x180001be9  mov     r8, rdi; P
0x180001bec  xor     edx, edx; Flags
0x180001bee  mov     rcx, [rcx+30h]; HeapHandle
0x180001bf2  call    cs:__imp_RtlFreeHeap
0x180001bf8  jmp     short loc_180001C71
0x180001bfa  cmp     [rbp+57h+var_B0], r13d
0x180001bfe  jz      short loc_180001C23
0x180001c00  test    rdi, rdi
0x180001c03  jz      short loc_180001C23
0x180001c05  mov     rcx, gs:60h
0x180001c0e  mov     r8, rdi; P
0x180001c11  xor     edx, edx; Flags
0x180001c13  mov     rcx, [rcx+30h]; HeapHandle
0x180001c17  call    cs:__imp_RtlFreeHeap
0x180001c1d  mov     rbx, [rbp+57h+var_98]
0x180001c21  jmp     short loc_180001C44
0x180001c23  mov     rbx, [rbp+57h+var_98]
0x180001c27  mov     r8, [rbx]; P
0x180001c2a  test    r8, r8
  ... truncated ...
```
