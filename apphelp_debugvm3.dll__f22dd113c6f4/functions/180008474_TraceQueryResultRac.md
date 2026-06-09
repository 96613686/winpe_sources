# TraceQueryResultRac

- ea: `0x180008474`
- end: `0x1800089fd`
- name: `TraceQueryResultRac`
- size: `1417`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ea6c`

## callees

- `0x18000708c`
- `0x180007df8`
- `0x180008474`
- `0x180008a04`
- `0x180008a80`
- `0x180009720`
- `0x180009f8c`
- `0x18000ecc0`
- `0x18000f114`
- `0x18000f150`
- `0x180011240`
- `0x18002b7a4`
- `0x18002f65c`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18000873b`
- `ntdll!EtwEventUnregister` at `0x18000873b`
- `ntdll!EtwEventRegister` at `0x18000860c`
- `ntdll!EtwEventRegister` at `0x18000860c`
- `ntdll!RtlAllocateHeap` at `0x18000856a`
- `ntdll!RtlAllocateHeap` at `0x18000856a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008752`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008752`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000851e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000851e`
- `KERNEL32!GetPackageFullName` at `0x18000853f`
- `KERNEL32!GetPackageFullName` at `0x180008827`
- `KERNEL32!GetPackageFullName` at `0x18000853f`
- `KERNEL32!GetPackageFullName` at `0x180008827`

## pseudocode

```c
__int64 __fastcall TraceQueryResultRac(const wchar_t *a1, __int64 a2, __int64 a3, DWORD a4, unsigned int a5)
{
  int v8; // r14d
  unsigned int v10; // edi
  unsigned int v11; // r15d
  __int64 i; // rdx
  HANDLE v13; // rax
  void *v14; // r13
  int v15; // edx
  int v16; // r9d
  WCHAR *Heap; // rax
  WCHAR *v18; // rbx
  int v19; // ecx
  int v20; // eax
  unsigned int v21; // r14d
  __int64 v22; // rbx
  __int64 v23; // r15
  const wchar_t *v24; // r13
  unsigned int v25; // r12d
  __int64 v26; // rsi
  unsigned int v27; // edi
  int FirstTag; // eax
  int v29; // edx
  int v30; // r8d
  int v31; // ecx
  int v32; // edx
  int v33; // edi
  unsigned int v35; // ebx
  unsigned int v36; // r12d
  __int64 StringTagPtr; // rbx
  unsigned int *BinaryTagData; // rax
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 ProcessSwitchContext; // rax
  __int64 v44; // r8
  int v45; // r13d
  __int64 v46; // rbx
  int v47; // ecx
  int v48; // r9d
  unsigned int v49; // [rsp+40h] [rbp-C0h] BYREF
  int v50; // [rsp+44h] [rbp-BCh] BYREF
  UINT32 packageFullNameLength; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v52[12]; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v53; // [rsp+58h] [rbp-A8h]
  DWORD v54; // [rsp+60h] [rbp-A0h]
  __int64 v55; // [rsp+68h] [rbp-98h]
  __int64 v56; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v57; // [rsp+80h] [rbp-80h]
  _QWORD v58[24]; // [rsp+90h] [rbp-70h] BYREF

  v53 = a3;
  v55 = a2;
  v54 = a4;
  v50 = 0;
  *(_DWORD *)&v52[8] = 0;
  packageFullNameLength = 0;
  v49 = 0;
  v8 = 1;
  v56 = 0;
  v10 = 0;
  memset_0(v58, 0, sizeof(v58));
  *(_QWORD *)v52 = (unsigned int)IsEventFilteringEnabled();
  v11 = AhpBuildLayerInfo(a1, a2, a3, v58);
  for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
  {
    v39 = HIDWORD(v58[3 * i + 2]);
    if ( (v39 & 0x80000) == 0 && (v39 & 0x10100) != 0x10100 )
    {
      v8 = 0;
      break;
    }
  }
  v13 = OpenProcess(0x1000u, 0, a4);
  v57 = v13;
  v14 = v13;
  if ( !v13 )
  {
    AslLogCallPrintf(1, "TraceQueryResultRac", 856, "Failed to get process handle.");
    goto LABEL_37;
  }
  if ( GetPackageFullName(v13, &packageFullNameLength, 0) == 122 && packageFullNameLength )
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * packageFullNameLength);
    v18 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "TraceQueryResultRac", 867, "Not enough memory.");
      goto LABEL_37;
    }
    if ( GetPackageFullName(v14, &packageFullNameLength, Heap) )
    {
      AslLogCallPrintf(1, "TraceQueryResultRac", 876, "Failed to get package full name.");
      goto LABEL_37;
    }
    if ( NtCurrentPeb()->pShimData )
      v42 = *((unsigned __int16 *)NtCurrentPeb()->pShimData + 266);
    else
      v42 = 0;
    ProcessSwitchContext = SbGetProcessSwitchContext(NtCurrentPeb()->pShimData, v40, v41, v42);
    if ( ProcessSwitchContext )
      v44 = *(_QWORD *)(ProcessSwitchContext + 24);
    else
      v44 = 0;
    v19 = CompatCacheGetAndSetRacEventSentPackage(&v50, v18, v44);
    v20 = v50;
  }
  else
  {
    v50 = 0;
    v19 = CompatCachepGetAndSetFlags((unsigned int)&v50, v15, (_DWORD)a1, v16, 1);
    if ( v19 < 0 )
      v20 = 0;
    else
      v20 = v50 & 1;
  }
  if ( v19 >= 0 && v20 && (!v11 || v8) )
    v21 = a5 | 0x80000000;
  else
    v21 = a5;
  if ( (v21 & 0xFFFFFF) != 0 )
  {
    AslLogCallPrintf(1, "TraceQueryResultRac", 906, "Invalid hint flags.");
  }
  else if ( (unsigned int)EtwEventRegister(AE_LOG, 0, 0, &v52[4]) )
  {
    AslLogCallPrintf(1, "TraceQueryResultRac", 915, "Failed to register event provider.");
  }
  else
  {
    if ( v11 )
    {
      v45 = *(_DWORD *)v52;
      v46 = 0;
      do
      {
        v47 = HIDWORD(v58[3 * v46 + 2]);
        if ( (v47 & 0x80000) == 0 && (v47 & 0x10100) != 0x10100 )
        {
          v48 = v21 | v47;
          if ( (v47 & 0x200) != 0 )
            AhpTraceFixGroup(*(_DWORD *)&v52[4], (_DWORD)a1, v55, v58[3 * v46 + 2], a4, v48, v45);
          else
            AhpTraceFix(*(__int64 *)&v52[4], a1, a4, v48, (unsigned int *)v58[3 * v46 + 1], v58[3 * v46], v45);
        }
        ++v10;
        ++v46;
      }
      while ( v10 < v11 );
    }
    v22 = v53;
    v23 = 0;
    v24 = a1;
    do
    {
      v25 = *(_DWORD *)(v22 + 4 * v23);
      if ( !v25 )
        break;
      if ( (unsigned int)SdbTagRefToTagID(v55, v25, &v56, &v49) && (v26 = v56) != 0 )
      {
        v27 = v21 | 0x80010001;
        if ( !(unsigned int)SdbFindFirstTag(v56, v49, 4105) )
          v27 = v21 | 0x10001;
        FirstTag = SdbFindFirstTag(v26, v49, 4102);
        v29 = v27 | 0x4000000;
        if ( !FirstTag )
          v29 = v27;
        v30 = *(_DWORD *)(v53 + 4 * v23 + 64);
        v31 = v29 | 0x1000000;
        if ( (v30 & 1) == 0 )
          v31 = v29;
        v32 = v31 | 0x20;
        if ( (v30 & 0x1000) == 0 )
          v32 = v31;
        v33 = v32 | 0x40;
        if ( (v30 & 0x2000) == 0 )
          v33 = v32;
        if ( (v25 & 0xF0000000) != 0 )
        {
          AhpTraceFixGroup(*(_DWORD *)&v52[4], (_DWORD)v24, v55, v25, v54, v33 | 0x200, *(_DWORD *)v52);
        }
        else
        {
          v35 = SdbFindFirstTag(v26, v49, 24582);
          if ( v35 )
          {
            v36 = SdbFindFirstTag(v26, v49, 36868);
            if ( v36 )
            {
              StringTagPtr = SdbGetStringTagPtr(v26, v35);
              BinaryTagData = (unsigned int *)SdbGetBinaryTagData(v26, v36);
              AhpTraceFix(*(__int64 *)&v52[4], v24, v54, v33 | 0x100, BinaryTagData, StringTagPtr, *(int *)v52);
            }
            else
            {
              AslLogCallPrintf(1, "TraceQueryResultRac", 1058, "Failed to get TAG_EXE_ID.");
            }
          }
          else
          {
            AslLogCallPrintf(1, "TraceQueryResultRac", 1049, "Failed to get TAG_APP_NAME.");
          }
        }
        v22 = v53;
      }
      else
      {
        AslLogCallPrintf(1, "TraceQueryResultRac", 989, "Failed to get EXE tag.");
      }
      v23 = (unsigned int)(v23 + 1);
    }
    while ( (unsigned int)v23 < 0x10 );
    v14 = v57;
    v10 = 1;
  }
LABEL_37:
  if ( *(_QWORD *)&v52[4] )
  {
    EtwEventUnregister();
    *(_QWORD *)&v52[4] = 0;
  }
  if ( v14 )
    CloseHandle(v14);
  return v10;
}

```

## disassembly

```asm
0x180008474  push    rbp
0x180008476  push    rbx
0x180008477  push    rsi
0x180008478  push    rdi
0x180008479  push    r12
0x18000847b  push    r13
0x18000847d  push    r14
0x18000847f  push    r15
0x180008481  lea     rbp, [rsp-68h]
0x180008486  sub     rsp, 168h
0x18000848d  mov     rax, cs:__security_cookie
0x180008494  xor     rax, rsp
0x180008497  mov     [rbp+0A0h+var_50], rax
0x18000849b  xor     eax, eax
0x18000849d  mov     [rsp+1A0h+var_148], r8
0x1800084a2  mov     r15, r8
0x1800084a5  mov     [rsp+1A0h+var_138], rdx
0x1800084aa  mov     rbx, rdx
0x1800084ad  mov     [rsp+1A0h+var_140], r9d
0x1800084b2  mov     rsi, rcx
0x1800084b5  mov     [rsp+1A0h+var_15C], eax
0x1800084b9  xor     edx, edx; Val
0x1800084bb  mov     [rsp+1A0h+var_150], rax
0x1800084c0  mov     r8d, 0C0h; Size
0x1800084c6  mov     [rsp+1A0h+packageFullNameLength], eax
0x1800084ca  lea     rcx, [rbp+0A0h+var_110]; void *
0x1800084ce  mov     [rsp+1A0h+var_160], eax
0x1800084d2  lea     r14d, [rax+1]
0x1800084d6  mov     [rsp+1A0h+var_130], rax
0x1800084db  mov     r12d, r9d
0x1800084de  mov     edi, eax
0x1800084e0  call    memset_0
0x1800084e5  call    IsEventFilteringEnabled
0x1800084ea  lea     r9, [rbp+0A0h+var_110]
0x1800084ee  mov     [rsp+1A0h+var_154], eax
0x1800084f2  mov     r8, r15
0x1800084f5  mov     rdx, rbx
0x1800084f8  mov     rcx, rsi
0x1800084fb  call    AhpBuildLayerInfo
0x180008500  mov     r15d, eax
0x180008503  xor     edx, edx
0x180008505  mov     r8d, 10100h
0x18000850b  cmp     edx, r15d
0x18000850e  jb      loc_1800087FB
0x180008514  mov     r8d, r12d; dwProcessId
0x180008517  xor     edx, edx; bInheritHandle
0x180008519  mov     ecx, 1000h; dwDesiredAccess
0x18000851e  call    cs:__imp_OpenProcess
0x180008524  mov     [rbp+0A0h+var_120], rax
0x180008528  mov     r13, rax
0x18000852b  test    rax, rax
0x18000852e  jz      loc_18000897B
0x180008534  xor     r8d, r8d; packageFullName
0x180008537  lea     rdx, [rsp+1A0h+packageFullNameLength]; packageFullNameLength
0x18000853c  mov     rcx, rax; hProcess
0x18000853f  call    cs:__imp_GetPackageFullName
0x180008545  cmp     eax, 7Ah ; 'z'
0x180008548  jnz     short loc_18000859F
0x18000854a  mov     eax, [rsp+1A0h+packageFullNameLength]
0x18000854e  test    eax, eax
0x180008550  jz      short loc_18000859F
0x180008552  mov     rcx, gs:60h
0x18000855b  mov     r8d, eax
0x18000855e  add     r8, r8; Size
0x180008561  mov     edx, 8; Flags
0x180008566  mov     rcx, [rcx+30h]; HeapHandle
0x18000856a  call    cs:__imp_RtlAllocateHeap
0x180008570  mov     rbx, rax
0x180008573  test    rax, rax
0x180008576  jnz     loc_18000881C
0x18000857c  lea     r9, aNotEnoughMemor_0; "Not enough memory."
0x180008583  mov     r8d, 363h
0x180008589  lea     rdx, aTracequeryresu_1; "TraceQueryResultRac"
0x180008590  mov     ecx, 1
0x180008595  call    AslLogCallPrintf
0x18000859a  jmp     loc_180008731
0x18000859f  mov     r8, rsi
0x1800085a2  mov     [rsp+1A0h+var_15C], edi
0x1800085a6  lea     rcx, [rsp+1A0h+var_15C]
0x1800085ab  mov     dword ptr [rsp+1A0h+var_180], 1
0x1800085b3  call    CompatCachepGetAndSetFlags
0x1800085b8  mov     ecx, eax
0x1800085ba  test    eax, eax
0x1800085bc  js      loc_1800088A5
0x1800085c2  mov     eax, [rsp+1A0h+var_15C]
0x1800085c6  and     eax, 1
0x1800085c9  test    ecx, ecx
0x1800085cb  js      loc_1800088B5
0x1800085d1  test    eax, eax
0x1800085d3  jz      loc_1800088B5
0x1800085d9  test    r15d, r15d
0x1800085dc  jnz     loc_1800088AC
0x1800085e2  mov     r14d, [rbp+0A0h+arg_20]
0x1800085e9  bts     r14d, 1Fh
0x1800085ee  test    r14d, 0FFFFFFh
0x1800085f5  jnz     loc_1800088C1
0x1800085fb  lea     r9, [rsp+1A0h+var_150]
0x180008600  xor     r8d, r8d
0x180008603  xor     edx, edx
0x180008605  lea     rcx, AE_LOG
0x18000860c  call    cs:__imp_EtwEventRegister
0x180008612  test    eax, eax
0x180008614  jnz     loc_1800089B8
0x18000861a  test    r15d, r15d
0x18000861d  jnz     loc_1800088D8
0x180008623  mov     rbx, [rsp+1A0h+var_148]
0x180008628  xor     r15d, r15d
0x18000862b  mov     r13, rsi
0x18000862e  mov     r12d, [rbx+r15*4]
0x180008632  test    r12d, r12d
0x180008635  jz      loc_180008728
0x18000863b  mov     rcx, [rsp+1A0h+var_138]
0x180008640  lea     r9, [rsp+1A0h+var_160]
0x180008645  lea     r8, [rsp+1A0h+var_130]
0x18000864a  mov     edx, r12d
0x18000864d  call    SdbTagRefToTagID
0x180008652  test    eax, eax
0x180008654  jz      loc_18000898D
0x18000865a  mov     rsi, [rsp+1A0h+var_130]
0x18000865f  test    rsi, rsi
0x180008662  jz      loc_18000898D
0x180008668  mov     edx, [rsp+1A0h+var_160]
0x18000866c  mov     ebx, r14d
0x18000866f  mov     r8d, 1009h
0x180008675  mov     rcx, rsi
0x180008678  or      ebx, 10001h
0x18000867e  call    SdbFindFirstTag
0x180008683  mov     edx, [rsp+1A0h+var_160]
0x180008687  mov     edi, ebx
0x180008689  bts     edi, 1Fh
0x18000868d  mov     r8d, 1006h
0x180008693  test    eax, eax
0x180008695  mov     rcx, rsi
0x180008698  cmovz   edi, ebx
0x18000869b  call    SdbFindFirstTag
0x1800086a0  mov     edx, edi
0x1800086a2  bts     edx, 1Ah
0x1800086a6  test    eax, eax
0x1800086a8  mov     rax, [rsp+1A0h+var_148]
0x1800086ad  cmovz   edx, edi
0x1800086b0  mov     ecx, edx
0x1800086b2  mov     r8d, [rax+r15*4+40h]
0x1800086b7  bts     ecx, 18h
0x1800086bb  test    r8b, 1
0x1800086bf  cmovz   ecx, edx
0x1800086c2  mov     edx, ecx
0x1800086c4  or      edx, 20h
0x1800086c7  bt      r8d, 0Ch
0x1800086cc  cmovnb  edx, ecx
0x1800086cf  mov     edi, edx
0x1800086d1  or      edi, 40h
0x1800086d4  bt      r8d, 0Dh
0x1800086d9  cmovnb  edi, edx
0x1800086dc  test    r12d, 0F0000000h
0x1800086e3  jz      loc_18000877A
0x1800086e9  mov     eax, [rsp+1A0h+var_154]
0x1800086ed  bts     edi, 9
0x1800086f1  mov     r8, [rsp+1A0h+var_138]
0x1800086f6  mov     r9d, r12d
0x1800086f9  mov     rcx, [rsp+1A0h+var_150]
0x1800086fe  mov     rdx, r13
0x180008701  mov     [rsp+1A0h+var_170], eax
0x180008705  mov     eax, [rsp+1A0h+var_140]
0x180008709  mov     dword ptr [rsp+1A0h+var_178], edi
0x18000870d  mov     dword ptr [rsp+1A0h+var_180], eax
0x180008711  call    AhpTraceFixGroup
0x180008716  mov     rbx, [rsp+1A0h+var_148]
0x18000871b  inc     r15d
0x18000871e  cmp     r15d, 10h
0x180008722  jb      loc_18000862E
0x180008728  mov     r13, [rbp+0A0h+var_120]
0x18000872c  mov     edi, 1
0x180008731  mov     rcx, [rsp+1A0h+var_150]
0x180008736  test    rcx, rcx
0x180008739  jz      short loc_18000874A
0x18000873b  call    cs:__imp_EtwEventUnregister
0x180008741  mov     [rsp+1A0h+var_150], 0
0x18000874a  test    r13, r13
0x18000874d  jz      short loc_180008758
0x18000874f  mov     rcx, r13; hObject
0x180008752  call    cs:__imp_CloseHandle
0x180008758  mov     eax, edi
0x18000875a  mov     rcx, [rbp+0A0h+var_50]
0x18000875e  xor     rcx, rsp; StackCookie
0x180008761  call    __security_check_cookie
0x180008766  add     rsp, 168h
0x18000876d  pop     r15
0x18000876f  pop     r14
0x180008771  pop     r13
0x180008773  pop     r12
0x180008775  pop     rdi
0x180008776  pop     rsi
0x180008777  pop     rbx
0x180008778  pop     rbp
0x180008779  retn
0x18000877a  mov     edx, [rsp+1A0h+var_160]
0x18000877e  mov     r8d, 6006h
0x180008784  mov     rcx, rsi
0x180008787  call    SdbFindFirstTag
0x18000878c  mov     ebx, eax
0x18000878e  test    eax, eax
0x180008790  jz      loc_1800089EB
0x180008796  mov     edx, [rsp+1A0h+var_160]
0x18000879a  mov     r8d, 9004h
0x1800087a0  mov     rcx, rsi
0x1800087a3  call    SdbFindFirstTag
0x1800087a8  mov     r12d, eax
0x1800087ab  test    eax, eax
0x1800087ad  jz      loc_180008958
0x1800087b3  mov     edx, ebx
0x1800087b5  mov     rcx, rsi
0x1800087b8  call    SdbGetStringTagPtr
0x1800087bd  mov     edx, r12d
0x1800087c0  mov     rcx, rsi
0x1800087c3  mov     rbx, rax
0x1800087c6  call    SdbGetBinaryTagData
0x1800087cb  mov     ecx, [rsp+1A0h+var_154]
0x1800087cf  bts     edi, 8
0x1800087d3  mov     r8d, [rsp+1A0h+var_140]
0x1800087d8  mov     r9d, edi
0x1800087db  mov     [rsp+1A0h+var_170], ecx
0x1800087df  mov     rdx, r13
0x1800087e2  mov     rcx, [rsp+1A0h+var_150]
0x1800087e7  mov     [rsp+1A0h+var_178], rbx
0x1800087ec  mov     [rsp+1A0h+var_180], rax
0x1800087f1  call    AhpTraceFix
0x1800087f6  jmp     loc_180008716
0x1800087fb  lea     rcx, [rdx+rdx*2]
0x1800087ff  mov     eax, [rbp+rcx*8+0A0h+var_FC]
0x180008803  bt      eax, 13h
0x180008807  jb      short loc_180008815
0x180008809  and     eax, r8d
0x18000880c  cmp     eax, r8d
0x18000880f  jnz     loc_18000889D
0x180008815  inc     edx
0x180008817  jmp     loc_18000850B
0x18000881c  mov     r8, rbx; packageFullName
0x18000881f  lea     rdx, [rsp+1A0h+packageFullNameLength]; packageFullNameLength
0x180008824  mov     rcx, r13; hProcess
0x180008827  call    cs:__imp_GetPackageFullName
0x18000882d  test    eax, eax
0x18000882f  jnz     loc_180008946
0x180008835  mov     rax, gs:60h
0x18000883e  cmp     [rax+2D8h], rdi
0x180008845  jz      loc_1800088D3
0x18000884b  mov     rax, gs:60h
0x180008854  mov     rcx, [rax+2D8h]
0x18000885b  movzx   r9d, word ptr [rcx+214h]
0x180008863  mov     rcx, gs:60h
0x18000886c  mov     rcx, [rcx+2D8h]
0x180008873  call    SbGetProcessSwitchContext
0x180008878  test    rax, rax
0x18000887b  jz      loc_1800089B0
0x180008881  mov     r8, [rax+18h]
0x180008885  mov     rdx, rbx
0x180008888  lea     rcx, [rsp+1A0h+var_15C]
0x18000888d  call    CompatCacheGetAndSetRacEventSentPackage
0x180008892  mov     ecx, eax
0x180008894  mov     eax, [rsp+1A0h+var_15C]
0x180008898  jmp     loc_1800085C9
0x18000889d  xor     r14d, r14d
0x1800088a0  jmp     loc_180008514
0x1800088a5  xor     eax, eax
0x1800088a7  jmp     loc_1800085C9
0x1800088ac  test    r14d, r14d
0x1800088af  jnz     loc_1800085E2
0x1800088b5  mov     r14d, [rbp+0A0h+arg_20]
0x1800088bc  jmp     loc_1800085EE
0x1800088c1  lea     r9, aInvalidHintFla; "Invalid hint flags."
0x1800088c8  mov     r8d, 38Ah
0x1800088ce  jmp     loc_180008589
0x1800088d3  xor     r9d, r9d
0x1800088d6  jmp     short loc_180008863
0x1800088d8  mov     r13d, [rsp+1A0h+var_154]
0x1800088dd  xor     ebx, ebx
0x1800088df  lea     rdx, [rbx+rbx*2]
0x1800088e3  mov     ecx, [rbp+rdx*8+0A0h+var_FC]
0x1800088e7  bt      ecx, 13h
0x1800088eb  jb      short loc_180008936
0x1800088ed  mov     r8d, 10100h
0x1800088f3  mov     eax, ecx
0x1800088f5  and     eax, r8d
0x1800088f8  cmp     eax, r8d
0x1800088fb  jz      short loc_180008936
0x1800088fd  mov     r9d, ecx
0x180008900  mov     [rsp+1A0h+var_170], r13d
0x180008905  or      r9d, r14d
0x180008908  bt      ecx, 9
0x18000890c  mov     rcx, [rsp+1A0h+var_150]
0x180008911  jb      loc_1800089CA
0x180008917  mov     rax, [rbp+rdx*8+0A0h+var_110]
0x18000891c  mov     r8d, r12d
0x18000891f  mov     [rsp+1A0h+var_178], rax
0x180008924  mov     rax, [rbp+rdx*8+0A0h+var_108]
0x180008929  mov     rdx, rsi
0x18000892c  mov     [rsp+1A0h+var_180], rax
0x180008931  call    AhpTraceFix
0x180008936  inc     edi
0x180008938  inc     rbx
0x18000893b  cmp     edi, r15d
  ... truncated ...
```
