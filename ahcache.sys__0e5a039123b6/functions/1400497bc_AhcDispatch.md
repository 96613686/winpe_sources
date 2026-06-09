# AhcDispatch

- ea: `0x1400497bc`
- end: `0x140049b8e`
- name: `AhcDispatch`
- size: `978`
- prototype: `__int64 __fastcall(__int64, int, char *, char)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14005a240`

## callees

- `0x1400045b0`
- `0x140007e40`
- `0x140029954`
- `0x14002b128`
- `0x14002b268`
- `0x14002b850`
- `0x14002b950`
- `0x14002baa8`
- `0x14003e364`
- `0x1400436f8`
- `0x140045a00`
- `0x1400497bc`
- `0x140049ba0`
- `0x140049bfc`
- `0x14004af80`
- `0x14004be30`
- `0x14004c088`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x140049814`
- `ntoskrnl!MmIsUserAddress` at `0x140049814`
- `ntoskrnl!ProbeForRead` at `0x140049805`
- `ntoskrnl!ProbeForRead` at `0x140049805`

## string_xrefs

- `0x140049ad0`: `Incorrect service class`

## pseudocode

```c
__int64 __fastcall AhcDispatch(__int64 a1, int a2, char *a3, char a4)
{
  __int64 *v8; // r14
  char IsUserAddress; // al
  int *v10; // rcx
  _OWORD *v11; // rax
  __int64 v12; // rdx
  void *v13; // r15
  int v14; // edi
  unsigned int v15; // ebx
  unsigned int inited; // eax
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  int v22; // edi
  int v23; // edi
  int v24[114]; // [rsp+50h] [rbp-1C8h] BYREF

  memset(v24, 0, 0x188u);
  v8 = 0;
  if ( a4 )
    ProbeForRead(a3, 0x188u, 4u);
  IsUserAddress = MmIsUserAddress(a3);
  v10 = v24;
  if ( IsUserAddress )
  {
    RtlCopyFromUser(v24, a3, 0x188u);
  }
  else
  {
    v11 = a3;
    v12 = 3;
    do
    {
      *(_OWORD *)v10 = *v11;
      *((_OWORD *)v10 + 1) = v11[1];
      *((_OWORD *)v10 + 2) = v11[2];
      *((_OWORD *)v10 + 3) = v11[3];
      *((_OWORD *)v10 + 4) = v11[4];
      *((_OWORD *)v10 + 5) = v11[5];
      *((_OWORD *)v10 + 6) = v11[6];
      *((_OWORD *)v10 + 7) = v11[7];
      v10 += 32;
      v11 += 8;
      --v12;
    }
    while ( v12 );
    *(_QWORD *)v10 = *(_QWORD *)v11;
  }
  v13 = a3 + 384;
  if ( a2 <= 5 )
  {
    if ( a2 != 5 )
    {
      if ( !a2 )
      {
        PerfScenarioStart(&CompatCacheQueryStart);
        v8 = CompatCacheQueryStop;
        if ( !*(_DWORD *)(a1 + 96) )
          goto LABEL_11;
        ++*(_DWORD *)(a1 + 44);
        inited = AhcApiLookup(
                   a1,
                   *(_QWORD *)(a1 + 24),
                   (int)v24,
                   *(_QWORD *)(a1 + 32),
                   *(void **)&v24[94],
                   v24[96],
                   v13);
        goto LABEL_16;
      }
      v18 = a2 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( v20 )
          {
            if ( v20 != 1 )
            {
LABEL_41:
              AslLogCallPrintf(1, "AhcDispatch", 1631, "Incorrect service class");
              v15 = -1073741811;
              goto LABEL_12;
            }
            if ( !*(_DWORD *)(a1 + 96) )
              goto LABEL_25;
            ++*(_DWORD *)(a1 + 60);
            inited = AhcApiSnapStatistics((void *)(a1 + 40), *(void **)&v24[94]);
          }
          else
          {
            ++*(_DWORD *)(a1 + 56);
            inited = AhcApiClear(a1);
          }
LABEL_16:
          v15 = inited;
          goto LABEL_12;
        }
        PerfScenarioStart(&CompatCacheUpdateStart);
        v8 = CompatCacheUpdateStop;
        if ( *(_DWORD *)(a1 + 96) )
        {
          ++*(_DWORD *)(a1 + 52);
          inited = AhcApiUpdate(a1, &v24[24]);
          goto LABEL_16;
        }
      }
      else if ( *(_DWORD *)(a1 + 96) )
      {
        ++*(_DWORD *)(a1 + 48);
        inited = AhcApiRemove(*(_QWORD *)(a1 + 24));
        goto LABEL_16;
      }
LABEL_44:
      v15 = 0;
      goto LABEL_12;
    }
    if ( !*(_DWORD *)(a1 + 96) )
      goto LABEL_25;
    ++*(_DWORD *)(a1 + 64);
    inited = AhcApiSnapCache(*(_QWORD *)(a1 + 24), *(_QWORD *)&v24[94], (unsigned int)v24[96], v13);
    goto LABEL_16;
  }
  v14 = a2 - 6;
  if ( !v14 )
  {
    PerfScenarioStart(&CompatCdbQueryStart);
    v8 = (__int64 *)"\t";
    if ( !*(_DWORD *)(a1 + 96) )
    {
LABEL_11:
      v15 = -1073741275;
      goto LABEL_12;
    }
    inited = AhcApiLookupCdb(*(_QWORD *)(a1 + 32), &v24[62], *(_QWORD *)&v24[94], (unsigned int)v24[96]);
    goto LABEL_16;
  }
  v21 = v14 - 1;
  if ( !v21 )
  {
    if ( *(_DWORD *)(a1 + 96) )
    {
      inited = AhcCdbRefresh(*(_QWORD *)(a1 + 32));
      goto LABEL_16;
    }
    goto LABEL_44;
  }
  v22 = v21 - 1;
  if ( v22 )
  {
    v23 = v22 - 2;
    if ( v23 )
    {
      if ( v23 == 1 )
      {
        PerfScenarioStart(&CompatCacheQueryProcessStart);
        v8 = CompatCacheQueryProcessStop;
        if ( !*(_DWORD *)(a1 + 96) )
          goto LABEL_11;
        ++*(_DWORD *)(a1 + 68);
        inited = AhcApiLookupAndWriteToProcess(
                   a1,
                   *(_QWORD *)(a1 + 24),
                   (int)v24,
                   *(_QWORD *)(a1 + 32),
                   *(void **)&v24[94],
                   v24[96],
                   v13);
        goto LABEL_16;
      }
      goto LABEL_41;
    }
    if ( *(_DWORD *)(a1 + 96) )
    {
      inited = AhcApiInitProcessData(&v24[86]);
      goto LABEL_16;
    }
    goto LABEL_44;
  }
  if ( !*(_DWORD *)(a1 + 96) || !*(_DWORD *)(a1 + 92) )
  {
LABEL_25:
    v15 = -1073741823;
    goto LABEL_12;
  }
  if ( a4 == 1 )
  {
    PerfScenarioStart(&CompatMapQuirksStart);
    v8 = CompatMapQuirksStop;
    inited = AhcApiMapQuirks(a1, *(_QWORD *)&v24[94], (unsigned int)v24[96]);
    goto LABEL_16;
  }
  v15 = -1073741822;
LABEL_12:
  if ( v8 )
    PerfScenarioStop((PCEVENT_DESCRIPTOR)v8);
  return v15;
}

```

## disassembly

```asm
0x1400497bc  push    rbx
0x1400497be  push    rdi
0x1400497bf  push    r12
0x1400497c1  push    r13
0x1400497c3  push    r14
0x1400497c5  push    r15
0x1400497c7  sub     rsp, 1E8h
0x1400497ce  mov     r12b, r9b
0x1400497d1  mov     r15, r8
0x1400497d4  mov     edi, edx
0x1400497d6  mov     rbx, rcx
0x1400497d9  mov     r13d, 188h
0x1400497df  mov     r8d, r13d; Size
0x1400497e2  xor     edx, edx; Val
0x1400497e4  lea     rcx, [rsp+218h+var_1C8]; void *
0x1400497e9  call    memset
0x1400497ee  xor     r14d, r14d
0x1400497f1  mov     [rsp+218h+EventDescriptor], r14
0x1400497f6  test    r12b, r12b
0x1400497f9  jz      short loc_140049811
0x1400497fb  lea     r8d, [r14+4]; Alignment
0x1400497ff  mov     edx, r13d; Length
0x140049802  mov     rcx, r15; Address
0x140049805  call    cs:__imp_ProbeForRead
0x14004980c  nop     dword ptr [rax+rax+00h]
0x140049811  mov     rcx, r15
0x140049814  call    cs:__imp_MmIsUserAddress
0x14004981b  nop     dword ptr [rax+rax+00h]
0x140049820  lea     rcx, [rsp+218h+var_1C8]; void *
0x140049825  test    al, al
0x140049827  jnz     short loc_140049887
0x140049829  mov     rax, r15
0x14004982c  mov     edx, 3
0x140049831  lea     r8d, [rdx+7Dh]
0x140049835  movups  xmm0, xmmword ptr [rax]
0x140049838  movups  xmmword ptr [rcx], xmm0
0x14004983b  movups  xmm1, xmmword ptr [rax+10h]
0x14004983f  movups  xmmword ptr [rcx+10h], xmm1
0x140049843  movups  xmm0, xmmword ptr [rax+20h]
0x140049847  movups  xmmword ptr [rcx+20h], xmm0
0x14004984b  movups  xmm1, xmmword ptr [rax+30h]
0x14004984f  movups  xmmword ptr [rcx+30h], xmm1
0x140049853  movups  xmm0, xmmword ptr [rax+40h]
0x140049857  movups  xmmword ptr [rcx+40h], xmm0
0x14004985b  movups  xmm1, xmmword ptr [rax+50h]
0x14004985f  movups  xmmword ptr [rcx+50h], xmm1
0x140049863  movups  xmm0, xmmword ptr [rax+60h]
0x140049867  movups  xmmword ptr [rcx+60h], xmm0
0x14004986b  movups  xmm1, xmmword ptr [rax+70h]
0x14004986f  movups  xmmword ptr [rcx+70h], xmm1
0x140049873  add     rcx, r8
0x140049876  add     rax, r8
0x140049879  sub     rdx, 1
0x14004987d  jnz     short loc_140049835
0x14004987f  mov     rax, [rax]
0x140049882  mov     [rcx], rax
0x140049885  jmp     short loc_140049892
0x140049887  mov     r8, r13; Size
0x14004988a  mov     rdx, r15; Src
0x14004988d  call    RtlCopyFromUser
0x140049892  jmp     short loc_14004989D
0x140049894  mov     ebx, eax
0x140049896  mov     r14, [rsp+218h+EventDescriptor]
0x14004989b  jmp     short loc_1400498CF
0x14004989d  add     r15, 180h
0x1400498a4  cmp     edi, 5
0x1400498a7  jle     short loc_140049912
0x1400498a9  sub     edi, 6
0x1400498ac  jnz     loc_140049A59
0x1400498b2  lea     rcx, CompatCdbQueryStart; EventDescriptor
0x1400498b9  call    PerfScenarioStart
0x1400498be  lea     r14, CompatCdbQueryStop; "\t"
0x1400498c5  cmp     [rbx+60h], edi
0x1400498c8  jnz     short loc_1400498ED
0x1400498ca  mov     ebx, 0C0000225h
0x1400498cf  test    r14, r14
0x1400498d2  jnz     loc_140049B7F
0x1400498d8  mov     eax, ebx
0x1400498da  add     rsp, 1E8h
0x1400498e1  pop     r15
0x1400498e3  pop     r14
0x1400498e5  pop     r13
0x1400498e7  pop     r12
0x1400498e9  pop     rdi
0x1400498ea  pop     rbx
0x1400498eb  retn
0x1400498ed  mov     r9d, [rsp+218h+var_48]
0x1400498f5  mov     r8, [rsp+218h+var_50]
0x1400498fd  lea     rdx, [rsp+218h+var_D0]
0x140049905  mov     rcx, [rbx+20h]
0x140049909  call    AhcApiLookupCdb
0x14004990e  mov     ebx, eax
0x140049910  jmp     short loc_1400498CF
0x140049912  jz      loc_140049A2B
0x140049918  test    edi, edi
0x14004991a  jz      loc_1400499D4
0x140049920  sub     edi, 1
0x140049923  jz      loc_1400499B1
0x140049929  sub     edi, 1
0x14004992c  jz      short loc_14004997C
0x14004992e  sub     edi, 1
0x140049931  jz      short loc_14004996F
0x140049933  cmp     edi, 1
0x140049936  jnz     loc_140049AD0
0x14004993c  cmp     dword ptr [rbx+60h], 0
0x140049940  jz      short loc_140049965
0x140049942  lea     rcx, [rbx+28h]; Src
0x140049946  mov     eax, [rcx+14h]
0x140049949  inc     eax
0x14004994b  mov     [rbx+3Ch], eax
0x14004994e  mov     r8d, [rsp+218h+var_48]
0x140049956  mov     rdx, [rsp+218h+var_50]; void *
0x14004995e  call    AhcApiSnapStatistics
0x140049963  jmp     short loc_14004990E
0x140049965  mov     ebx, 0C0000001h
0x14004996a  jmp     loc_1400498CF
0x14004996f  inc     dword ptr [rbx+38h]
0x140049972  mov     rcx, rbx
0x140049975  call    AhcApiClear
0x14004997a  jmp     short loc_14004990E
0x14004997c  lea     rcx, CompatCacheUpdateStart; EventDescriptor
0x140049983  call    PerfScenarioStart
0x140049988  lea     r14, CompatCacheUpdateStop
0x14004998f  cmp     dword ptr [rbx+60h], 0
0x140049993  jz      loc_140049B10
0x140049999  inc     dword ptr [rbx+34h]
0x14004999c  lea     rdx, [rsp+218h+var_168]
0x1400499a4  mov     rcx, rbx
0x1400499a7  call    AhcApiUpdate
0x1400499ac  jmp     loc_14004990E
0x1400499b1  cmp     dword ptr [rbx+60h], 0
0x1400499b5  jz      loc_140049B10
0x1400499bb  inc     dword ptr [rbx+30h]
0x1400499be  lea     rdx, [rsp+218h+var_B8]
0x1400499c6  mov     rcx, [rbx+18h]; int
0x1400499ca  call    AhcApiRemove
0x1400499cf  jmp     loc_14004990E
0x1400499d4  lea     rcx, CompatCacheQueryStart; EventDescriptor
0x1400499db  call    PerfScenarioStart
0x1400499e0  lea     r14, CompatCacheQueryStop
0x1400499e7  cmp     dword ptr [rbx+60h], 0
0x1400499eb  jz      loc_1400498CA
0x1400499f1  inc     dword ptr [rbx+2Ch]
0x1400499f4  mov     [rsp+218h+var_1E8], r15; void *
0x1400499f9  mov     eax, [rsp+218h+var_48]
0x140049a00  mov     [rsp+218h+var_1F0], eax; int
0x140049a04  mov     rax, [rsp+218h+var_50]
0x140049a0c  mov     [rsp+218h+var_1F8], rax; void *
0x140049a11  mov     r9, [rbx+20h]; int
0x140049a15  lea     r8, [rsp+218h+var_1C8]; int
0x140049a1a  mov     rdx, [rbx+18h]; int
0x140049a1e  mov     rcx, rbx; int
0x140049a21  call    AhcApiLookup
0x140049a26  jmp     loc_14004990E
0x140049a2b  cmp     dword ptr [rbx+60h], 0
0x140049a2f  jz      loc_140049965
0x140049a35  inc     dword ptr [rbx+40h]
0x140049a38  mov     r9, r15
0x140049a3b  mov     r8d, [rsp+218h+var_48]
0x140049a43  mov     rdx, [rsp+218h+var_50]
0x140049a4b  mov     rcx, [rbx+18h]
0x140049a4f  call    AhcApiSnapCache
0x140049a54  jmp     loc_14004990E
0x140049a59  sub     edi, 1
0x140049a5c  jz      loc_140049B6B
0x140049a62  sub     edi, 1
0x140049a65  jz      loc_140049B17
0x140049a6b  sub     edi, 2
0x140049a6e  jz      loc_140049AF8
0x140049a74  cmp     edi, 1
0x140049a77  jnz     short loc_140049AD0
0x140049a79  lea     rcx, CompatCacheQueryProcessStart; EventDescriptor
0x140049a80  call    PerfScenarioStart
0x140049a85  lea     r14, CompatCacheQueryProcessStop
0x140049a8c  cmp     dword ptr [rbx+60h], 0
0x140049a90  jz      loc_1400498CA
0x140049a96  inc     dword ptr [rbx+44h]
0x140049a99  mov     [rsp+218h+var_1E8], r15; void *
0x140049a9e  mov     eax, [rsp+218h+var_48]
0x140049aa5  mov     [rsp+218h+var_1F0], eax; int
0x140049aa9  mov     rax, [rsp+218h+var_50]
0x140049ab1  mov     [rsp+218h+var_1F8], rax; void *
0x140049ab6  mov     r9, [rbx+20h]; int
0x140049aba  lea     r8, [rsp+218h+var_1C8]; int
0x140049abf  mov     rdx, [rbx+18h]; int
0x140049ac3  mov     rcx, rbx; int
0x140049ac6  call    AhcApiLookupAndWriteToProcess
0x140049acb  jmp     loc_14004990E
0x140049ad0  lea     r9, aIncorrectServi; "Incorrect service class"
0x140049ad7  mov     r8d, 65Fh
0x140049add  lea     rdx, aAhcdispatch; "AhcDispatch"
0x140049ae4  mov     ecx, 1
0x140049ae9  call    AslLogCallPrintf
0x140049aee  mov     ebx, 0C000000Dh
0x140049af3  jmp     loc_1400498CF
0x140049af8  cmp     dword ptr [rbx+60h], 0
0x140049afc  jz      short loc_140049B10
0x140049afe  lea     rcx, [rsp+218h+var_70]
0x140049b06  call    AhcApiInitProcessData
0x140049b0b  jmp     loc_14004990E
0x140049b10  xor     ebx, ebx
0x140049b12  jmp     loc_1400498CF
0x140049b17  cmp     dword ptr [rbx+60h], 0
0x140049b1b  jz      loc_140049965
0x140049b21  cmp     dword ptr [rbx+5Ch], 0
0x140049b25  jz      loc_140049965
0x140049b2b  cmp     r12b, 1
0x140049b2f  jz      short loc_140049B3B
0x140049b31  mov     ebx, 0C0000002h
0x140049b36  jmp     loc_1400498CF
0x140049b3b  lea     rcx, CompatMapQuirksStart; EventDescriptor
0x140049b42  call    PerfScenarioStart
0x140049b47  lea     r14, CompatMapQuirksStop
0x140049b4e  mov     r8d, [rsp+218h+var_48]
0x140049b56  mov     rdx, [rsp+218h+var_50]
0x140049b5e  mov     rcx, rbx
0x140049b61  call    AhcApiMapQuirks
0x140049b66  jmp     loc_14004990E
0x140049b6b  cmp     dword ptr [rbx+60h], 0
0x140049b6f  jz      short loc_140049B10
0x140049b71  mov     rcx, [rbx+20h]
0x140049b75  call    AhcCdbRefresh
0x140049b7a  jmp     loc_14004990E
0x140049b7f  mov     edx, ebx
0x140049b81  mov     rcx, r14; EventDescriptor
0x140049b84  call    PerfScenarioStop
0x140049b89  jmp     loc_1400498D8
```
