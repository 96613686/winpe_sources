# AhcSdbQueryLookup

- ea: `0x14005974c`
- end: `0x140059bac`
- name: `AhcSdbQueryLookup`
- size: `1120`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _WORD *, unsigned __int16)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x140055898`

## callees

- `0x140003064`
- `0x14000479c`
- `0x1400079f0`
- `0x14002c708`
- `0x14002df04`
- `0x14003e364`
- `0x140042724`
- `0x140043590`
- `0x140044eb8`
- `0x140054e54`
- `0x14005974c`
- `0x140059d78`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140059860`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140059b37`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140059860`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140059b37`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005994c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140059b7a`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005994c`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140059b7a`

## string_xrefs

- `0x140059aec`: `Exception during lookup [%x]`

## pseudocode

```c
__int64 __fastcall AhcSdbQueryLookup(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        _WORD *a15,
        unsigned __int16 a16)
{
  __int64 inited; // r14
  char v18; // si
  _QWORD *v19; // rcx
  const char *v20; // r9
  __int64 v21; // r8
  unsigned int v22; // edi
  __int64 v23; // rax
  unsigned int LookupPackage; // eax
  __int64 v25; // rdi
  int LookupXap; // eax
  __int64 v27; // rcx
  _BYTE v29[3]; // [rsp+71h] [rbp-C7h] BYREF
  int IsTaskHostXapLaunch; // [rsp+74h] [rbp-C4h]
  __int64 v31; // [rsp+78h] [rbp-C0h]
  __int64 v32; // [rsp+80h] [rbp-B8h]
  __int64 v33; // [rsp+88h] [rbp-B0h]
  __int64 v34; // [rsp+90h] [rbp-A8h]
  __int64 v35; // [rsp+98h] [rbp-A0h]
  __int64 v36; // [rsp+A0h] [rbp-98h]
  __int64 v37; // [rsp+A8h] [rbp-90h]
  __int64 v38; // [rsp+B0h] [rbp-88h]
  __int64 v39; // [rsp+B8h] [rbp-80h]
  __int64 v40; // [rsp+C0h] [rbp-78h]
  __int64 v41; // [rsp+C8h] [rbp-70h]
  __int64 v42; // [rsp+D0h] [rbp-68h]
  __int64 v43; // [rsp+D8h] [rbp-60h]
  __int128 v44; // [rsp+E0h] [rbp-58h] BYREF

  v40 = a4;
  v41 = a3;
  v42 = a2;
  v39 = a5;
  v38 = a6;
  v33 = a7;
  v32 = a8;
  v43 = a9;
  v37 = a10;
  v36 = a11;
  v35 = a12;
  v34 = a13;
  v44 = 0;
  inited = 0;
  v31 = 0;
  v29[0] = 0;
  v18 = 0;
  if ( !(unsigned int)Feature_MapSdbFilesToKernelMemory__private_IsEnabledDeviceUsageNoInline() )
  {
    inited = SdbInitDatabaseEx(0, 0, a16);
    v31 = inited;
    if ( !inited )
    {
      v20 = "Failed to initialize SDB [%x]";
      v21 = 381;
      goto LABEL_5;
    }
LABEL_13:
    if ( a15 && *a15 )
      SdbOverrideMatcherEx(inited);
    if ( v34 )
    {
      LookupPackage = AhcpSdbQueryLookupPackage(a9, (_DWORD)a1, inited, v34, a14);
    }
    else
    {
      v25 = v35;
      IsTaskHostXapLaunch = AhcpIsTaskHostXapLaunch(v29, &v44, v35, a14);
      if ( IsTaskHostXapLaunch >= 0 && v29[0] )
      {
        LookupXap = AhcpSdbQueryLookupXap(a1, (unsigned int)&v44);
        v22 = LookupXap;
        IsTaskHostXapLaunch = LookupXap;
        if ( LookupXap < 0 )
          AslLogCallPrintf(1, "AhcSdbQueryLookup", 418, "AhcpSdbQueryLookupXap failed [%x]", LookupXap);
        goto LABEL_26;
      }
      LookupPackage = AhcpSdbQueryLookupExe(a1, v39, v38, v33, v32, inited, v37, v36, v25, a14);
    }
    IsTaskHostXapLaunch = LookupPackage;
    v22 = LookupPackage;
LABEL_26:
    v18 = 0;
    goto LABEL_27;
  }
  ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)(a9 + 720));
  v18 = 1;
  v19 = *(_QWORD **)(a9 + 712);
  if ( v19 || (v19 = (_QWORD *)SdbInitDatabaseEx(0, 0, a16), (*(_QWORD *)(a9 + 712) = v19) != 0) )
  {
    v23 = v19[1];
    if ( *(_QWORD *)(*(_QWORD *)v23 + 16LL) && *(_BYTE *)(*(_QWORD *)v23 + 60LL) )
    {
      inited = SdbDuplicateSdbHandleEx(v19);
      v31 = inited;
      if ( !inited )
      {
        v22 = -1073741823;
        IsTaskHostXapLaunch = -1073741823;
        AslLogCallPrintf(1, "AhcSdbQueryLookup", 368, "Failed to duplicate shared SDB handle [%x]", -1073741823);
        goto LABEL_27;
      }
    }
    else
    {
      AslLogCallPrintf(1, "AhcSdbQueryLookup", 359, "Shared SDB handle is in user address space [%p]", v19);
      inited = *(_QWORD *)(a9 + 712);
      v31 = inited;
      *(_QWORD *)(a9 + 712) = 0;
    }
    ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)(a9 + 720));
    goto LABEL_13;
  }
  v20 = "Failed to initialize shared SDB handle [%x]";
  v21 = 347;
LABEL_5:
  IsTaskHostXapLaunch = -1073741480;
  v22 = -1073741480;
  AslLogCallPrintf(1, "AhcSdbQueryLookup", v21, v20, -1073741480);
LABEL_27:
  if ( inited )
  {
    SdbReleaseDatabase(inited);
    if ( !v18 )
    {
      ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)(a9 + 720));
      v18 = 1;
    }
    v27 = *(_QWORD *)(a9 + 712);
    if ( v27 && (*(_DWORD *)(v27 + 1768) || *(int *)(v27 + 1776) <= 0) )
    {
      SdbReleaseDatabase(v27);
      *(_QWORD *)(a9 + 712) = 0;
    }
  }
  if ( v18 )
    ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)(a9 + 720));
  return v22;
}

```

## disassembly

```asm
0x14005974c  push    rbx
0x14005974e  push    rsi
0x14005974f  push    rdi
0x140059750  push    r12
0x140059752  push    r13
0x140059754  push    r14
0x140059756  push    r15
0x140059758  sub     rsp, 100h
0x14005975f  mov     rax, cs:__security_cookie
0x140059766  xor     rax, rsp
0x140059769  mov     [rsp+138h+var_48], rax
0x140059771  mov     [rsp+138h+var_78], r9
0x140059779  mov     [rsp+138h+var_70], r8
0x140059781  mov     [rsp+138h+var_68], rdx
0x140059789  mov     r12, rcx
0x14005978c  mov     rax, [rsp+138h+arg_20]
0x140059794  mov     [rsp+138h+var_80], rax
0x14005979c  mov     rax, [rsp+138h+arg_28]
0x1400597a4  mov     [rsp+138h+var_88], rax
0x1400597ac  mov     rax, [rsp+138h+arg_30]
0x1400597b4  mov     [rsp+138h+var_B0], rax
0x1400597bc  mov     rax, [rsp+138h+arg_38]
0x1400597c4  mov     [rsp+138h+var_B8], rax
0x1400597cc  mov     r15, [rsp+138h+arg_40]
0x1400597d4  mov     [rsp+138h+var_60], r15
0x1400597dc  mov     rax, [rsp+138h+arg_48]
0x1400597e4  mov     [rsp+138h+var_90], rax
0x1400597ec  mov     rax, [rsp+138h+arg_50]
0x1400597f4  mov     [rsp+138h+var_98], rax
0x1400597fc  mov     rax, [rsp+138h+arg_58]
0x140059804  mov     [rsp+138h+var_A0], rax
0x14005980c  mov     rax, [rsp+138h+arg_60]
0x140059814  mov     [rsp+138h+var_A8], rax
0x14005981c  mov     r13, [rsp+138h+arg_68]
0x140059824  movzx   edi, [rsp+138h+arg_78]
0x14005982c  xorps   xmm0, xmm0
0x14005982f  movups  [rsp+138h+var_58], xmm0
0x140059837  xor     ebx, ebx
0x140059839  mov     r14d, ebx
0x14005983c  mov     [rsp+138h+var_C0], rbx
0x140059841  mov     [rsp+138h+var_C7], bl
0x140059845  mov     sil, bl
0x140059848  mov     [rsp+138h+var_C8], bl
0x14005984c  call    Feature_MapSdbFilesToKernelMemory__private_IsEnabledDeviceUsageNoInline
0x140059851  test    eax, eax
0x140059853  jz      loc_14005999F
0x140059859  mov     rcx, [r15+2D0h]; Resource
0x140059860  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140059867  nop     dword ptr [rax+rax+00h]
0x14005986c  mov     sil, 1
0x14005986f  mov     [rsp+138h+var_C8], sil
0x140059874  mov     rcx, [r15+2C8h]; Src
0x14005987b  test    rcx, rcx
0x14005987e  jnz     short loc_1400598CC
0x140059880  movzx   r8d, di
0x140059884  xor     edx, edx
0x140059886  call    SdbInitDatabaseEx
0x14005988b  mov     rcx, rax
0x14005988e  mov     [r15+2C8h], rax
0x140059895  test    rax, rax
0x140059898  jnz     short loc_1400598CC
0x14005989a  lea     r9, aFailedToInitia_15; "Failed to initialize shared SDB handle "...
0x1400598a1  mov     r8d, 15Bh
0x1400598a7  mov     eax, 0C0000158h
0x1400598ac  mov     dword ptr [rsp+138h+var_118], eax
0x1400598b0  mov     [rsp+138h+var_C4], eax
0x1400598b4  mov     edi, eax
0x1400598b6  lea     rdx, aAhcsdbqueryloo_0; "AhcSdbQueryLookup"
0x1400598bd  mov     ecx, 1
0x1400598c2  call    AslLogCallPrintf
0x1400598c7  jmp     loc_140059AE0
0x1400598cc  mov     rax, [rcx+8]
0x1400598d0  mov     rdx, [rax]
0x1400598d3  cmp     [rdx+10h], rbx
0x1400598d7  jz      short loc_14005990F
0x1400598d9  cmp     [rdx+3Ch], bl
0x1400598dc  jz      short loc_14005990F
0x1400598de  movzx   edx, di
0x1400598e1  call    SdbDuplicateSdbHandleEx
0x1400598e6  mov     r14, rax
0x1400598e9  mov     [rsp+138h+var_C0], rax
0x1400598ee  test    rax, rax
0x1400598f1  jnz     short loc_140059945
0x1400598f3  mov     edi, 0C0000001h
0x1400598f8  mov     [rsp+138h+var_C4], edi
0x1400598fc  mov     dword ptr [rsp+138h+var_118], edi
0x140059900  lea     r9, aFailedToDuplic_1; "Failed to duplicate shared SDB handle ["...
0x140059907  mov     r8d, 170h
0x14005990d  jmp     short loc_1400598B6
0x14005990f  mov     [rsp+138h+var_118], rcx
0x140059914  lea     r9, aSharedSdbHandl; "Shared SDB handle is in user address sp"...
0x14005991b  mov     r8d, 167h
0x140059921  lea     rdx, aAhcsdbqueryloo_0; "AhcSdbQueryLookup"
0x140059928  mov     ecx, 1
0x14005992d  call    AslLogCallPrintf
0x140059932  mov     r14, [r15+2C8h]
0x140059939  mov     [rsp+138h+var_C0], r14
0x14005993e  mov     [r15+2C8h], rbx
0x140059945  mov     rcx, [r15+2D0h]; Resource
0x14005994c  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140059953  nop     dword ptr [rax+rax+00h]
0x140059958  mov     [rsp+138h+var_C8], bl
0x14005995c  mov     r9, [rsp+138h+arg_70]
0x140059964  test    r9, r9
0x140059967  jz      short loc_140059977
0x140059969  cmp     [r9], bx
0x14005996d  jz      short loc_140059977
0x14005996f  mov     rcx, r14
0x140059972  call    SdbOverrideMatcherEx
0x140059977  mov     rax, [rsp+138h+var_A8]
0x14005997f  test    rax, rax
0x140059982  jz      short loc_1400599CB
0x140059984  mov     [rsp+138h+var_118], r13
0x140059989  mov     r9, rax
0x14005998c  mov     r8, r14
0x14005998f  mov     rdx, r12
0x140059992  mov     rcx, r15
0x140059995  call    AhcpSdbQueryLookupPackage
0x14005999a  jmp     loc_140059AD3
0x14005999f  movzx   r8d, di
0x1400599a3  xor     edx, edx
0x1400599a5  xor     ecx, ecx
0x1400599a7  call    SdbInitDatabaseEx
0x1400599ac  mov     r14, rax
0x1400599af  mov     [rsp+138h+var_C0], rax
0x1400599b4  test    rax, rax
0x1400599b7  jnz     short loc_14005995C
0x1400599b9  lea     r9, aFailedToInitia_2; "Failed to initialize SDB [%x]"
0x1400599c0  mov     r8d, 17Dh
0x1400599c6  jmp     loc_1400598A7
0x1400599cb  mov     r9, r13
0x1400599ce  mov     rdi, [rsp+138h+var_A0]
0x1400599d6  mov     r8, rdi
0x1400599d9  lea     rdx, [rsp+138h+var_58]
0x1400599e1  lea     rcx, [rsp+138h+var_C7]
0x1400599e6  call    AhcpIsTaskHostXapLaunch
0x1400599eb  mov     [rsp+138h+var_C4], eax
0x1400599ef  test    eax, eax
0x1400599f1  js      short loc_140059A56
0x1400599f3  cmp     [rsp+138h+var_C7], bl
0x1400599f7  jz      short loc_140059A56
0x1400599f9  lea     rax, [rsp+138h+var_58]
0x140059a01  mov     [rsp+138h+var_118], rax
0x140059a06  mov     r9, r14
0x140059a09  mov     r8, [rsp+138h+var_B8]
0x140059a11  mov     rdx, [rsp+138h+var_B0]
0x140059a19  mov     rcx, r12
0x140059a1c  call    AhcpSdbQueryLookupXap
0x140059a21  mov     edi, eax
0x140059a23  mov     [rsp+138h+var_C4], eax
0x140059a27  test    eax, eax
0x140059a29  jns     loc_140059AD9
0x140059a2f  mov     dword ptr [rsp+138h+var_118], eax
0x140059a33  lea     r9, aAhcpsdbquerylo_0; "AhcpSdbQueryLookupXap failed [%x]"
0x140059a3a  mov     r8d, 1A2h
0x140059a40  lea     rdx, aAhcsdbqueryloo_0; "AhcSdbQueryLookup"
0x140059a47  mov     ecx, 1
0x140059a4c  call    AslLogCallPrintf
0x140059a51  jmp     loc_140059AD9
0x140059a56  mov     [rsp+138h+var_D8], r13
0x140059a5b  mov     [rsp+138h+var_E0], rdi
0x140059a60  mov     rax, [rsp+138h+var_98]
0x140059a68  mov     [rsp+138h+var_E8], rax
0x140059a6d  mov     rax, [rsp+138h+var_90]
0x140059a75  mov     [rsp+138h+var_F0], rax
0x140059a7a  mov     [rsp+138h+var_F8], r14
0x140059a7f  mov     rax, [rsp+138h+var_B8]
0x140059a87  mov     [rsp+138h+var_100], rax
0x140059a8c  mov     rax, [rsp+138h+var_B0]
0x140059a94  mov     [rsp+138h+var_108], rax
0x140059a99  mov     rax, [rsp+138h+var_88]
0x140059aa1  mov     [rsp+138h+var_110], rax
0x140059aa6  mov     rax, [rsp+138h+var_80]
0x140059aae  mov     [rsp+138h+var_118], rax
0x140059ab3  mov     r9, [rsp+138h+var_78]
0x140059abb  mov     r8, [rsp+138h+var_70]
0x140059ac3  mov     rdx, [rsp+138h+var_68]
0x140059acb  mov     rcx, r12
0x140059ace  call    AhcpSdbQueryLookupExe
0x140059ad3  mov     [rsp+138h+var_C4], eax
0x140059ad7  mov     edi, eax
0x140059ad9  mov     sil, bl
0x140059adc  mov     [rsp+138h+var_C8], bl
0x140059ae0  jmp     short loc_140059B1E
0x140059ae2  mov     edi, eax
0x140059ae4  mov     [rsp+138h+var_C4], eax
0x140059ae8  mov     dword ptr [rsp+138h+var_118], eax
0x140059aec  lea     r9, aExceptionDurin; "Exception during lookup [%x]"
0x140059af3  mov     r8d, 1BEh
0x140059af9  lea     rdx, aAhcsdbqueryloo_0; "AhcSdbQueryLookup"
0x140059b00  mov     ecx, 1
0x140059b05  call    AslLogCallPrintf
0x140059b0a  xor     ebx, ebx
0x140059b0c  mov     r14, [rsp+138h+var_C0]
0x140059b11  mov     sil, [rsp+138h+var_C8]
0x140059b16  mov     r15, [rsp+138h+var_60]
0x140059b1e  test    r14, r14
0x140059b21  jz      short loc_140059B6E
0x140059b23  mov     rcx, r14
0x140059b26  call    SdbReleaseDatabase
0x140059b2b  test    sil, sil
0x140059b2e  jnz     short loc_140059B46
0x140059b30  mov     rcx, [r15+2D0h]; Resource
0x140059b37  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140059b3e  nop     dword ptr [rax+rax+00h]
0x140059b43  mov     sil, 1
0x140059b46  mov     rcx, [r15+2C8h]
0x140059b4d  test    rcx, rcx
0x140059b50  jz      short loc_140059B6E
0x140059b52  cmp     [rcx+6E8h], ebx
0x140059b58  jnz     short loc_140059B62
0x140059b5a  cmp     [rcx+6F0h], ebx
0x140059b60  jg      short loc_140059B6E
0x140059b62  call    SdbReleaseDatabase
0x140059b67  mov     [r15+2C8h], rbx
0x140059b6e  test    sil, sil
0x140059b71  jz      short loc_140059B86
0x140059b73  mov     rcx, [r15+2D0h]; Resource
0x140059b7a  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140059b81  nop     dword ptr [rax+rax+00h]
0x140059b86  mov     eax, edi
0x140059b88  mov     rcx, [rsp+138h+var_48]
0x140059b90  xor     rcx, rsp; StackCookie
0x140059b93  call    __security_check_cookie
0x140059b98  add     rsp, 100h
0x140059b9f  pop     r15
0x140059ba1  pop     r14
0x140059ba3  pop     r13
0x140059ba5  pop     r12
0x140059ba7  pop     rdi
0x140059ba8  pop     rsi
0x140059ba9  pop     rbx
0x140059baa  retn
```
