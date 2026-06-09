# AhcCdbDetectServicing

- ea: `0x1400591c4`
- end: `0x140059743`
- name: `AhcCdbDetectServicing`
- size: `1407`
- prototype: `__int64 __fastcall(int *, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x140029954`
- `0x1400438c4`

## callees

- `0x1400079f0`
- `0x140007b40`
- `0x140008360`
- `0x140029e0c`
- `0x1400341b0`
- `0x14003e364`
- `0x140041d6c`
- `0x14004224c`
- `0x140045d44`
- `0x1400545a4`
- `0x1400591c4`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400595c8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400595c8`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140059607`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140059607`

## string_xrefs

- `0x1400592ae`: `Failed to get cache read time EA from %S [%x]. Assuming the file changed.`
- `0x14005936f`: `Failed to get cache read time EA from %S [%x]. Assuming the file changed.`
- `0x140059483`: `Failed to get cache read time EA from %S [%x]. Assuming the file changed.`
- `0x1400594da`: `\SystemRoot\System32\Drivers\ahcache.sys`
- `0x1400594f7`: `Failed to check timestamp for ahcache.sys [%x]`
- `0x140059547`: `Failed to check timestamp for ahcache.sys [%x]`
- `0x140059595`: `Failed to get cache read time EA from ahcache.sys [%x]. Assuming the file changed.`

## pseudocode

```c
__int64 __fastcall AhcCdbDetectServicing(int *a1, __int64 a2)
{
  const WCHAR *v2; // rdi
  int v3; // ecx
  const WCHAR *v4; // rsi
  char v5; // r13
  __int64 v6; // r15
  __int64 v8; // r13
  int FileTimestamp; // eax
  int v10; // ebx
  int EaByPath; // eax
  __int64 v12; // rdx
  _QWORD *v13; // rbx
  int MergeStubPath; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // r9
  _QWORD *v19; // r12
  int MergeRedirectPath; // eax
  int v21; // eax
  int FileNameTimestamp; // eax
  int v23; // eax
  int v24; // r15d
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rbx
  size_t v29; // rbx
  __int64 v30; // rcx
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const WCHAR *v35; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+28h] [rbp-D8h]
  char v37; // [rsp+30h] [rbp-D0h]
  _QWORD *v38; // [rsp+38h] [rbp-C8h]
  const WCHAR *v39; // [rsp+40h] [rbp-C0h] BYREF
  const WCHAR *v40; // [rsp+48h] [rbp-B8h] BYREF
  int *v41; // [rsp+50h] [rbp-B0h]
  __int128 v42; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD Buf1[30]; // [rsp+70h] [rbp-90h] BYREF

  v2 = 0;
  v41 = a1;
  v3 = *(_DWORD *)(a2 + 320);
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v40 = 0;
  v39 = 0;
  v37 = 0;
  v42 = 0;
  if ( 7 * v3 )
  {
    while ( 1 )
    {
      v8 = (unsigned int)v6 / 7;
      FileTimestamp = AhcpCdbGetFileTimestamp(&Buf1[v6], *(const WCHAR **)(a2 + 8 * v8 + 48), 0);
      v10 = FileTimestamp;
      if ( FileTimestamp < 0 )
        break;
      v10 = AhcpCdbGetFileTimestamp(&Buf1[(unsigned int)(v6 + 1)], *(const WCHAR **)(a2 + 8 * v8 + 48), 1);
      if ( v10 < 0 )
      {
        LODWORD(v36) = v10;
        v32 = 1493;
        v35 = *(const WCHAR **)(a2 + 8 * v8 + 48);
        goto LABEL_48;
      }
      EaByPath = AslFileSecGetEaByPath(&v42);
      if ( EaByPath < 0 )
      {
        AslLogCallPrintf(
          3,
          "AhcCdbDetectServicing",
          1503,
          "Failed to get cache read time EA from %S [%x]. Assuming the file changed.",
          *(const wchar_t **)(a2 + 8 * v8 + 48),
          EaByPath);
        v37 = 1;
      }
      v12 = *(_QWORD *)(a2 + 8 * v8 + 48);
      v13 = &Buf1[(unsigned int)(v6 + 2)];
      *(_OWORD *)v13 = 0;
      MergeStubPath = SdbGetMergeStubPath(&v39, v12);
      v4 = v39;
      if ( MergeStubPath >= 0 && v39 )
      {
        v15 = AhcpCdbGetFileTimestamp(v13, v39, 0);
        v10 = v15;
        if ( v15 < 0 )
        {
          LODWORD(v36) = v15;
          v32 = 1521;
          v35 = v4;
          goto LABEL_48;
        }
        v16 = AhcpCdbGetFileTimestamp(&Buf1[(unsigned int)(v6 + 3)], v4, 1);
        v10 = v16;
        if ( v16 < 0 )
        {
          LODWORD(v36) = v16;
          v32 = 1526;
          v35 = v4;
          goto LABEL_48;
        }
        v17 = AslFileSecGetEaByPath(&v42);
        if ( v17 < 0 )
        {
          AslLogCallPrintf(
            3,
            "AhcCdbDetectServicing",
            1536,
            "Failed to get cache read time EA from %S [%x]. Assuming the file changed.",
            v4,
            v17);
          v37 = 1;
        }
      }
      v18 = *(_QWORD *)(a2 + 8 * v8 + 48);
      Buf1[(unsigned int)(v6 + 4)] = 0;
      v38 = &Buf1[(unsigned int)(v6 + 5)];
      *v38 = 0;
      v19 = &Buf1[(unsigned int)(v6 + 6)];
      *v19 = 0;
      MergeRedirectPath = SdbGetMergeRedirectPath(&v40, 0, 0, v18);
      v2 = v40;
      if ( MergeRedirectPath < 0 || !v40 )
        goto LABEL_21;
      v21 = AhcpCdbGetFileTimestamp(&Buf1[(unsigned int)(v6 + 4)], v40, 0);
      v10 = v21;
      if ( v21 < 0 )
      {
        LODWORD(v36) = v21;
        v32 = 1557;
        v35 = v2;
        goto LABEL_48;
      }
      v5 = 1;
      FileNameTimestamp = AhcpCdbGetFileTimestamp(v38, v2, 1);
      v10 = FileNameTimestamp;
      if ( FileNameTimestamp < 0 )
      {
        v33 = "Failed to check timestamp for %S [%x]";
        v34 = 1562;
        goto LABEL_43;
      }
      FileNameTimestamp = AhcpCdbGetFileNameTimestamp(v19, v2);
      v10 = FileNameTimestamp;
      if ( FileNameTimestamp == -1073741275 )
      {
        *v19 = 0;
      }
      else if ( FileNameTimestamp < 0 )
      {
        v33 = "Failed to check timestamp in file name for %S [%x]";
        v34 = 1571;
LABEL_43:
        LODWORD(v36) = FileNameTimestamp;
        AslLogCallPrintf(1, "AhcCdbDetectServicing", v34, v33, v2, v36);
        goto LABEL_35;
      }
      v23 = AslFileSecGetEaByPath(&v42);
      if ( v23 < 0 )
      {
        AslLogCallPrintf(
          3,
          "AhcCdbDetectServicing",
          1581,
          "Failed to get cache read time EA from %S [%x]. Assuming the file changed.",
          v2,
          v23);
        v37 = 1;
      }
      else
      {
LABEL_21:
        v5 = v37;
      }
      v3 = *(_DWORD *)(a2 + 320);
      v6 = (unsigned int)(v6 + 7);
      if ( (unsigned int)v6 >= 7 * v3 )
        goto LABEL_23;
    }
    LODWORD(v36) = FileTimestamp;
    v32 = 1488;
    v35 = *(const WCHAR **)(a2 + 8 * v8 + 48);
LABEL_48:
    AslLogCallPrintf(1, "AhcCdbDetectServicing", v32, "Failed to check timestamp for %S [%x]", v35, v36);
  }
  else
  {
LABEL_23:
    v24 = 0;
    v25 = AhcpCdbGetFileTimestamp(&Buf1[7 * v3], L"\\SystemRoot\\System32\\Drivers\\ahcache.sys", 0);
    if ( v25 < 0 )
    {
      AslLogCallPrintf(1, "AhcCdbDetectServicing", 1595, "Failed to check timestamp for ahcache.sys [%x]", v25);
      Buf1[7 * *(_DWORD *)(a2 + 320)] = 0;
    }
    v26 = AhcpCdbGetFileTimestamp(
            &Buf1[7 * *(_DWORD *)(a2 + 320) + 1],
            L"\\SystemRoot\\System32\\Drivers\\ahcache.sys",
            1);
    if ( v26 < 0 )
    {
      AslLogCallPrintf(1, "AhcCdbDetectServicing", 1600, "Failed to check timestamp for ahcache.sys [%x]", v26);
      Buf1[7 * *(_DWORD *)(a2 + 320) + 1] = 0;
    }
    v27 = AslFileSecGetEaByPath(&v42);
    if ( v27 < 0 )
    {
      AslLogCallPrintf(
        3,
        "AhcCdbDetectServicing",
        1610,
        "Failed to get cache read time EA from ahcache.sys [%x]. Assuming the file changed.",
        v27);
      v5 = 1;
    }
    v28 = (unsigned int)(7 * *(_DWORD *)(a2 + 320) + 2);
    ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)a2);
    v29 = 8 * v28;
    if ( memcmp(Buf1, (const void *)(a2 + 80), v29) )
    {
      v24 = 1;
      memmove((void *)(a2 + 80), Buf1, v29);
    }
    ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)a2);
    if ( v5 )
    {
      AslLogCallPrintf(2, "AhcCdbDetectServicing", 1647, "SDB servicing detected by EA detection.");
      if ( !v24 )
        AslLogCallPrintf(
          1,
          "AhcCdbDetectServicing",
          1656,
          "Sdb servicing detected by EA detection, but not by timestamp detection. Ensure EA detection is not overly aggressive.");
    }
    v10 = 0;
    *v41 = v24;
  }
LABEL_35:
  if ( v2 )
    AslFree(v30, v2);
  if ( v4 )
    AslFree(v30, v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400591c4  mov     [rsp-8+arg_10], rbx
0x1400591c9  push    rbp
0x1400591ca  push    rsi
0x1400591cb  push    rdi
0x1400591cc  push    r12
0x1400591ce  push    r13
0x1400591d0  push    r14
0x1400591d2  push    r15
0x1400591d4  lea     rbp, [rsp-70h]
0x1400591d9  sub     rsp, 170h
0x1400591e0  mov     rax, cs:__security_cookie
0x1400591e7  xor     rax, rsp
0x1400591ea  mov     [rbp+0A0h+var_40], rax
0x1400591ee  xor     edi, edi
0x1400591f0  mov     [rsp+1A0h+var_150], rcx
0x1400591f5  mov     ecx, [rdx+140h]
0x1400591fb  xor     esi, esi
0x1400591fd  xor     r13b, r13b
0x140059200  imul    eax, ecx, 7
0x140059203  xor     r15d, r15d
0x140059206  mov     [rsp+1A0h+var_158], rdi
0x14005920b  xorps   xmm0, xmm0
0x14005920e  mov     [rsp+1A0h+var_160], rsi
0x140059213  mov     r14, rdx
0x140059216  mov     [rsp+1A0h+var_170], r13b
0x14005921b  movups  [rsp+1A0h+var_148], xmm0
0x140059220  lea     r12d, [rdi+1]
0x140059224  test    eax, eax
0x140059226  jz      loc_1400594D2
0x14005922c  mov     eax, 24924925h
0x140059231  lea     rcx, [rsp+1A0h+Buf1]
0x140059236  mul     r15d
0x140059239  mov     eax, r15d
0x14005923c  lea     rcx, [rcx+r15*8]
0x140059240  sub     eax, edx
0x140059242  xor     r8d, r8d
0x140059245  shr     eax, 1
0x140059247  add     eax, edx
0x140059249  shr     eax, 2
0x14005924c  mov     r13d, eax
0x14005924f  mov     rdx, [r14+rax*8+30h]
0x140059254  call    AhcpCdbGetFileTimestamp
0x140059259  mov     rdx, [r14+r13*8+30h]
0x14005925e  mov     ebx, eax
0x140059260  test    eax, eax
0x140059262  js      loc_140059719
0x140059268  lea     rax, [rsp+1A0h+Buf1]
0x14005926d  mov     r8d, r12d
0x140059270  lea     ecx, [r15+1]
0x140059274  lea     rcx, [rax+rcx*8]
0x140059278  call    AhcpCdbGetFileTimestamp
0x14005927d  mov     ebx, eax
0x14005927f  mov     rax, [r14+r13*8+30h]
0x140059284  test    ebx, ebx
0x140059286  js      loc_140059708
0x14005928c  mov     r9, rax
0x14005928f  mov     dword ptr [rsp+1A0h+var_168], 10h
0x140059297  lea     rdx, [rsp+1A0h+var_168]
0x14005929c  lea     rcx, [rsp+1A0h+var_148]; void *
0x1400592a1  call    AslFileSecGetEaByPath
0x1400592a6  test    eax, eax
0x1400592a8  jns     short loc_1400592DB
0x1400592aa  mov     dword ptr [rsp+1A0h+var_178], eax
0x1400592ae  lea     r9, aFailedToGetCac; "Failed to get cache read time EA from %"...
0x1400592b5  mov     rax, [r14+r13*8+30h]
0x1400592ba  lea     rdx, aAhccdbdetectse; "AhcCdbDetectServicing"
0x1400592c1  mov     r8d, 5DFh
0x1400592c7  mov     [rsp+1A0h+var_180], rax
0x1400592cc  mov     ecx, 3
0x1400592d1  call    AslLogCallPrintf
0x1400592d6  mov     [rsp+1A0h+var_170], r12b
0x1400592db  mov     rdx, [r14+r13*8+30h]
0x1400592e0  lea     eax, [r15+2]
0x1400592e4  xorps   xmm0, xmm0
0x1400592e7  lea     rbx, [rsp+1A0h+Buf1]
0x1400592ec  lea     rbx, [rbx+rax*8]
0x1400592f0  lea     rcx, [rsp+1A0h+var_160]
0x1400592f5  movups  xmmword ptr [rbx], xmm0
0x1400592f8  call    SdbGetMergeStubPath
0x1400592fd  mov     rsi, [rsp+1A0h+var_160]
0x140059302  test    eax, eax
0x140059304  js      loc_140059397
0x14005930a  test    rsi, rsi
0x14005930d  jz      loc_140059397
0x140059313  xor     r8d, r8d
0x140059316  mov     rdx, rsi
0x140059319  mov     rcx, rbx
0x14005931c  call    AhcpCdbGetFileTimestamp
0x140059321  mov     ebx, eax
0x140059323  test    eax, eax
0x140059325  js      loc_1400596B7
0x14005932b  lea     rax, [rsp+1A0h+Buf1]
0x140059330  mov     r8d, r12d
0x140059333  lea     ecx, [r15+3]
0x140059337  mov     rdx, rsi
0x14005933a  lea     rcx, [rax+rcx*8]
0x14005933e  call    AhcpCdbGetFileTimestamp
0x140059343  mov     ebx, eax
0x140059345  test    eax, eax
0x140059347  js      loc_1400596A6
0x14005934d  mov     r9, rsi
0x140059350  mov     dword ptr [rsp+1A0h+var_168], 10h
0x140059358  lea     rdx, [rsp+1A0h+var_168]
0x14005935d  lea     rcx, [rsp+1A0h+var_148]; void *
0x140059362  call    AslFileSecGetEaByPath
0x140059367  test    eax, eax
0x140059369  jns     short loc_140059397
0x14005936b  mov     dword ptr [rsp+1A0h+var_178], eax
0x14005936f  lea     r9, aFailedToGetCac; "Failed to get cache read time EA from %"...
0x140059376  mov     r8d, 600h
0x14005937c  mov     [rsp+1A0h+var_180], rsi
0x140059381  lea     rdx, aAhccdbdetectse; "AhcCdbDetectServicing"
0x140059388  mov     ecx, 3
0x14005938d  call    AslLogCallPrintf
0x140059392  mov     [rsp+1A0h+var_170], r12b
0x140059397  mov     r9, [r14+r13*8+30h]
0x14005939c  lea     eax, [r15+4]
0x1400593a0  lea     ecx, [r15+5]
0x1400593a4  xor     r8d, r8d
0x1400593a7  lea     rbx, [rsp+1A0h+Buf1]
0x1400593ac  xor     edx, edx
0x1400593ae  lea     rbx, [rbx+rax*8]
0x1400593b2  lea     rax, [rsp+1A0h+Buf1]
0x1400593b7  mov     qword ptr [rbx], 0
0x1400593be  lea     rax, [rax+rcx*8]
0x1400593c2  mov     [rsp+1A0h+var_168], rax
0x1400593c7  lea     r12, [rsp+1A0h+Buf1]
0x1400593cc  mov     qword ptr [rax], 0
0x1400593d3  lea     rcx, [rsp+1A0h+var_158]
0x1400593d8  lea     eax, [r15+6]
0x1400593dc  lea     r12, [r12+rax*8]
0x1400593e0  mov     qword ptr [r12], 0
0x1400593e8  call    SdbGetMergeRedirectPath
0x1400593ed  mov     rdi, [rsp+1A0h+var_158]
0x1400593f2  test    eax, eax
0x1400593f4  js      loc_1400594B0
0x1400593fa  test    rdi, rdi
0x1400593fd  jz      loc_1400594B0
0x140059403  xor     r8d, r8d
0x140059406  mov     rdx, rdi
0x140059409  mov     rcx, rbx
0x14005940c  call    AhcpCdbGetFileTimestamp
0x140059411  mov     ebx, eax
0x140059413  test    eax, eax
0x140059415  js      loc_1400596F2
0x14005941b  mov     rcx, [rsp+1A0h+var_168]
0x140059420  mov     r13d, 1
0x140059426  mov     r8d, r13d
0x140059429  mov     rdx, rdi
0x14005942c  call    AhcpCdbGetFileTimestamp
0x140059431  mov     ebx, eax
0x140059433  test    eax, eax
0x140059435  js      loc_1400596E3
0x14005943b  mov     rdx, rdi
0x14005943e  mov     rcx, r12
0x140059441  call    AhcpCdbGetFileNameTimestamp
0x140059446  mov     ebx, eax
0x140059448  cmp     eax, 0C0000225h
0x14005944d  jnz     short loc_140059459
0x14005944f  mov     qword ptr [r12], 0
0x140059457  jmp     short loc_140059461
0x140059459  test    eax, eax
0x14005945b  js      loc_1400596C8
0x140059461  mov     r9, rdi
0x140059464  mov     dword ptr [rsp+1A0h+var_168], 10h
0x14005946c  lea     rdx, [rsp+1A0h+var_168]
0x140059471  lea     rcx, [rsp+1A0h+var_148]; void *
0x140059476  call    AslFileSecGetEaByPath
0x14005947b  test    eax, eax
0x14005947d  jns     short loc_1400594B0
0x14005947f  mov     dword ptr [rsp+1A0h+var_178], eax
0x140059483  lea     r9, aFailedToGetCac; "Failed to get cache read time EA from %"...
0x14005948a  mov     r8d, 62Dh
0x140059490  mov     [rsp+1A0h+var_180], rdi
0x140059495  lea     rdx, aAhccdbdetectse; "AhcCdbDetectServicing"
0x14005949c  mov     ecx, 3
0x1400594a1  call    AslLogCallPrintf
0x1400594a6  mov     r12d, r13d
0x1400594a9  mov     [rsp+1A0h+var_170], r12b
0x1400594ae  jmp     short loc_1400594BB
0x1400594b0  mov     r13b, [rsp+1A0h+var_170]
0x1400594b5  mov     r12d, 1
0x1400594bb  mov     ecx, [r14+140h]
0x1400594c2  add     r15d, 7
0x1400594c6  imul    eax, ecx, 7
0x1400594c9  cmp     r15d, eax
0x1400594cc  jb      loc_14005922C
0x1400594d2  imul    ecx, 7
0x1400594d5  lea     rax, [rsp+1A0h+Buf1]
0x1400594da  lea     rbx, aSystemrootSyst; "\\SystemRoot\\System32\\Drivers\\ahcach"...
0x1400594e1  xor     r8d, r8d
0x1400594e4  mov     rdx, rbx
0x1400594e7  xor     r15d, r15d
0x1400594ea  lea     rcx, [rax+rcx*8]
0x1400594ee  call    AhcpCdbGetFileTimestamp
0x1400594f3  test    eax, eax
0x1400594f5  jns     short loc_140059524
0x1400594f7  lea     r9, aFailedToCheckT_0; "Failed to check timestamp for ahcache.s"...
0x1400594fe  mov     dword ptr [rsp+1A0h+var_180], eax
0x140059502  mov     r8d, 63Bh
0x140059508  lea     rdx, aAhccdbdetectse; "AhcCdbDetectServicing"
0x14005950f  mov     ecx, r12d
0x140059512  call    AslLogCallPrintf
0x140059517  imul    eax, [r14+140h], 7
0x14005951f  mov     [rsp+rax*8+1A0h+Buf1], r15
0x140059524  imul    eax, [r14+140h], 7
0x14005952c  lea     rcx, [rsp+1A0h+Buf1]
0x140059531  mov     r8d, r12d
0x140059534  mov     rdx, rbx
0x140059537  add     eax, r12d
0x14005953a  lea     rcx, [rcx+rax*8]
0x14005953e  call    AhcpCdbGetFileTimestamp
0x140059543  test    eax, eax
0x140059545  jns     short loc_140059577
0x140059547  lea     r9, aFailedToCheckT_0; "Failed to check timestamp for ahcache.s"...
0x14005954e  mov     dword ptr [rsp+1A0h+var_180], eax
0x140059552  mov     r8d, 640h
0x140059558  lea     rdx, aAhccdbdetectse; "AhcCdbDetectServicing"
0x14005955f  mov     ecx, r12d
0x140059562  call    AslLogCallPrintf
0x140059567  imul    eax, [r14+140h], 7
0x14005956f  add     eax, r12d
0x140059572  mov     [rsp+rax*8+1A0h+Buf1], r15
0x140059577  mov     r9, rbx
0x14005957a  mov     dword ptr [rsp+1A0h+var_168], 10h
0x140059582  lea     rdx, [rsp+1A0h+var_168]
0x140059587  lea     rcx, [rsp+1A0h+var_148]; void *
0x14005958c  call    AslFileSecGetEaByPath
0x140059591  test    eax, eax
0x140059593  jns     short loc_1400595BA
0x140059595  lea     r9, aFailedToGetCac_0; "Failed to get cache read time EA from a"...
0x14005959c  mov     dword ptr [rsp+1A0h+var_180], eax
0x1400595a0  mov     r8d, 64Ah
0x1400595a6  lea     rdx, aAhccdbdetectse; "AhcCdbDetectServicing"
0x1400595ad  mov     ecx, 3
0x1400595b2  call    AslLogCallPrintf
0x1400595b7  mov     r13b, r12b
0x1400595ba  imul    ebx, [r14+140h], 7
0x1400595c2  mov     rcx, [r14]; Resource
0x1400595c5  add     ebx, 2
0x1400595c8  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400595cf  nop     dword ptr [rax+rax+00h]
0x1400595d4  shl     rbx, 3
0x1400595d8  lea     rdx, [r14+50h]; Buf2
0x1400595dc  mov     r8, rbx; Size
0x1400595df  lea     rcx, [rsp+1A0h+Buf1]; Buf1
0x1400595e4  call    memcmp
0x1400595e9  test    eax, eax
0x1400595eb  jz      short loc_140059604
0x1400595ed  mov     r8, rbx; Size
0x1400595f0  lea     rdx, [rsp+1A0h+Buf1]; Src
0x1400595f5  lea     rcx, [r14+50h]; void *
0x1400595f9  mov     r15d, 1
0x1400595ff  call    memmove
0x140059604  mov     rcx, [r14]; Resource
0x140059607  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14005960e  nop     dword ptr [rax+rax+00h]
0x140059613  test    r13b, r13b
0x140059616  jz      short loc_140059658
0x140059618  lea     r9, aSdbServicingDe_0; "SDB servicing detected by EA detection."
0x14005961f  mov     r8d, 66Fh
0x140059625  lea     rdx, aAhccdbdetectse; "AhcCdbDetectServicing"
0x14005962c  mov     ecx, 2
0x140059631  call    AslLogCallPrintf
0x140059636  test    r15d, r15d
0x140059639  jnz     short loc_140059658
0x14005963b  lea     r9, aSdbServicingDe; "Sdb servicing detected by EA detection,"...
0x140059642  mov     r8d, 678h
0x140059648  lea     rdx, aAhccdbdetectse; "AhcCdbDetectServicing"
0x14005964f  lea     ecx, [r15+1]
0x140059653  call    AslLogCallPrintf
0x140059658  mov     rax, [rsp+1A0h+var_150]
0x14005965d  xor     ebx, ebx
0x14005965f  mov     [rax], r15d
0x140059662  test    rdi, rdi
0x140059665  jz      short loc_14005966F
0x140059667  mov     rdx, rdi
0x14005966a  call    AslFree
0x14005966f  test    rsi, rsi
0x140059672  jz      short loc_14005967C
0x140059674  mov     rdx, rsi
0x140059677  call    AslFree
0x14005967c  mov     eax, ebx
0x14005967e  mov     rcx, [rbp+0A0h+var_40]
0x140059682  xor     rcx, rsp; StackCookie
0x140059685  call    __security_check_cookie
0x14005968a  mov     rbx, [rsp+1A0h+arg_10]
0x140059692  add     rsp, 170h
0x140059699  pop     r15
0x14005969b  pop     r14
0x14005969d  pop     r13
0x14005969f  pop     r12
0x1400596a1  pop     rdi
0x1400596a2  pop     rsi
0x1400596a3  pop     rbp
0x1400596a4  retn
0x1400596a6  mov     dword ptr [rsp+1A0h+var_178], eax
0x1400596aa  mov     r8d, 5F6h
0x1400596b0  mov     [rsp+1A0h+var_180], rsi
0x1400596b5  jmp     short loc_140059728
  ... truncated ...
```
