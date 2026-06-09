# EstimateReconstructWindowsDiskNeeds

- ea: `0x180046170`
- end: `0x1800463b2`
- name: `EstimateReconstructWindowsDiskNeeds`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800218c0`
- `0x180024c80`
- `0x180026c90`
- `0x18002d2b0`
- `0x18004420c`
- `0x18004473c`
- `0x180046170`
- `0x1800478b8`
- `0x18004e6f4`
- `0x18004f780`
- `0x1800504d0`
- `0x180050980`

## string_xrefs

- `0x180046218`: `No new Windows root path specified`
- `0x1800461f2`: `No old Windows root path specified`
- `0x180046286`: `Failed allocating old windows root path.`
- `0x1800462bd`: `Failed to backslash terminate path.`
- `0x1800462ca`: `System32\ssshim.dll`
- `0x1800462de`: `Failed to append ssshim.dll to offline windows directory path.`
- `0x1800462f8`: `Failed to get archecture from ssshim.dll.`

## pseudocode

```c
unsigned __int64 __fastcall EstimateReconstructWindowsDiskNeeds(unsigned int a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v8; // rbx
  const char *v9; // r9
  __int64 v10; // rdx
  int ProcessorArchitectureFromImageArchitecture; // eax
  __int64 v12; // rbx
  unsigned __int16 v14[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v16; // [rsp+38h] [rbp-48h] BYREF
  __int64 v17; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-38h] BYREF
  __int64 v19; // [rsp+50h] [rbp-30h] BYREF
  int v20; // [rsp+58h] [rbp-28h]
  int v21; // [rsp+5Ch] [rbp-24h]
  __int64 v22; // [rsp+60h] [rbp-20h] BYREF
  char v23; // [rsp+68h] [rbp-18h]

  lpFileName = 0;
  v14[0] = 0;
  v16 = 0;
  v17 = 0;
  v19 = 0;
  v22 = 0;
  v23 = 0;
  v15 = 0xFFFF;
  v20 = 1000;
  v8 = 0;
  v21 = 10;
  CBSWdsLog(0x4000000, 0, 0, "pbr: Estimating disk space requirements...");
  if ( !a2 )
  {
    v9 = "No old Windows root path specified";
LABEL_3:
    v10 = 2147942487LL;
LABEL_4:
    CBSWdsLog(0x4000000, v10, 1, v9);
    goto LABEL_26;
  }
  if ( !a3 )
  {
    v9 = "No new Windows root path specified";
    goto LABEL_3;
  }
  Windows::AutoComPtr<ICbsUIHandler>::operator=(&v22, a4);
  v20 = v21 * ((a1 & 1) != 0 ? 38400 : 81139);
  v8 = (-(__int64)((a1 & 1) != 0) & 0xFFFFFFFEC0000000uLL) + 0x240000000LL;
  ProcessorArchitectureFromImageArchitecture = SczAllocConcat2Sz(&v16, a2, L"\\Windows\\");
  if ( ProcessorArchitectureFromImageArchitecture < 0 )
  {
    v9 = "Failed allocating old windows root path.";
LABEL_9:
    v10 = (unsigned int)ProcessorArchitectureFromImageArchitecture;
    goto LABEL_4;
  }
  ProcessorArchitectureFromImageArchitecture = SczAllocFromSz(&v17, a3);
  if ( ProcessorArchitectureFromImageArchitecture < 0 )
  {
    v9 = "Failed allocating memory";
    goto LABEL_9;
  }
  ProcessorArchitectureFromImageArchitecture = SczEnsureBackslashTerminated(&v17);
  if ( ProcessorArchitectureFromImageArchitecture < 0 )
  {
    v9 = "Failed to backslash terminate path.";
    goto LABEL_9;
  }
  ProcessorArchitectureFromImageArchitecture = SczAllocConcat2Sz(&lpFileName, v16, L"System32\\ssshim.dll");
  if ( ProcessorArchitectureFromImageArchitecture < 0 )
  {
    v9 = "Failed to append ssshim.dll to offline windows directory path.";
    goto LABEL_9;
  }
  ProcessorArchitectureFromImageArchitecture = FileExecutableArchitecture(lpFileName, v14);
  if ( ProcessorArchitectureFromImageArchitecture < 0 )
  {
    v9 = "Failed to get archecture from ssshim.dll.";
    goto LABEL_9;
  }
  ProcessorArchitectureFromImageArchitecture = GetProcessorArchitectureFromImageArchitecture(v14[0], &v15);
  if ( ProcessorArchitectureFromImageArchitecture < 0 )
  {
    v9 = "Failed to get processor architecture.";
    goto LABEL_9;
  }
  v12 = EstimateDiskNeedsHelper(a1, v16, a3, &v19);
  if ( v23 )
  {
    v8 = 0;
  }
  else if ( !v15 || v15 == 5 )
  {
    v8 = v12 + 157286400;
  }
  else
  {
    v8 = v12 + 209715200;
  }
LABEL_26:
  CBSWdsLog(0x4000000, 0, 0, "pbr: Estimated reconstruction disk space needed: %I64u", v8);
  Windows::AutoComPtr<IClassFactory>::Close(&v22);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v17);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v16);
  return v8;
}

```

## disassembly

```asm
0x180046170  push    rbp
0x180046172  push    rbx
0x180046173  push    rsi
0x180046174  push    rdi
0x180046175  push    r12
0x180046177  push    r14
0x180046179  push    r15
0x18004617b  mov     rbp, rsp
0x18004617e  sub     rsp, 80h
0x180046185  mov     rax, cs:__security_cookie
0x18004618c  xor     rax, rsp
0x18004618f  mov     [rbp+var_10], rax
0x180046193  xor     eax, eax
0x180046195  mov     [rbp+lpFileName], 0
0x18004619d  mov     r12, r9
0x1800461a0  mov     [rbp+var_50], ax
0x1800461a4  mov     rsi, r8
0x1800461a7  mov     [rbp+var_48], rax
0x1800461ab  mov     r15, rdx
0x1800461ae  mov     [rbp+var_40], rax
0x1800461b2  mov     r14d, ecx
0x1800461b5  mov     [rbp+var_30], rax
0x1800461b9  lea     r9, aPbrEstimatingD; "pbr: Estimating disk space requirements"...
0x1800461c0  mov     [rbp+var_20], rax
0x1800461c4  xor     r8d, r8d
0x1800461c7  mov     [rbp+var_18], al
0x1800461ca  xor     edx, edx
0x1800461cc  mov     [rbp+var_4C], 0FFFFh
0x1800461d3  mov     ecx, 4000000h
0x1800461d8  mov     [rbp+var_28], 3E8h
0x1800461df  xor     ebx, ebx
0x1800461e1  mov     [rbp+var_24], 0Ah
0x1800461e8  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1800461ed  test    r15, r15
0x1800461f0  jnz     short loc_180046213
0x1800461f2  lea     r9, aNoOldWindowsRo; "No old Windows root path specified"
0x1800461f9  mov     edx, 80070057h
0x1800461fe  mov     r8d, 1
0x180046204  mov     ecx, 4000000h
0x180046209  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18004620e  jmp     loc_18004635A
0x180046213  test    rsi, rsi
0x180046216  jnz     short loc_180046221
0x180046218  lea     r9, aNoNewWindowsRo; "No new Windows root path specified"
0x18004621f  jmp     short loc_1800461F9
0x180046221  mov     ebx, r14d
0x180046224  lea     rcx, [rbp+var_20]
0x180046228  mov     edi, 1
0x18004622d  mov     rdx, r12
0x180046230  and     ebx, edi
0x180046232  call    ??4?$AutoComPtr@UICbsUIHandler@@@Windows@@QEAAAEAV01@PEAUICbsUIHandler@@@Z; Windows::AutoComPtr<ICbsUIHandler>::operator=(ICbsUIHandler *)
0x180046237  mov     eax, ebx
0x180046239  neg     eax
0x18004623b  sbb     ecx, ecx
0x18004623d  and     ecx, 0FFFF590Dh
0x180046243  add     ecx, 13CF3h
0x180046249  imul    ecx, [rbp+var_24]
0x18004624d  mov     [rbp+var_28], ecx
0x180046250  neg     ebx
0x180046252  lea     r8, aWindows_0; "\\Windows\\"
0x180046259  mov     rax, 0FFFFFFFEC0000000h
0x180046263  lea     rcx, [rbp+var_48]
0x180046267  sbb     rbx, rbx
0x18004626a  mov     rdx, r15
0x18004626d  and     rbx, rax
0x180046270  mov     rax, 240000000h
0x18004627a  add     rbx, rax
0x18004627d  call    SczAllocConcat2Sz
0x180046282  test    eax, eax
0x180046284  jns     short loc_180046297
0x180046286  lea     r9, aFailedAllocati_1; "Failed allocating old windows root path"...
0x18004628d  mov     r8d, edi
0x180046290  mov     edx, eax
0x180046292  jmp     loc_180046204
0x180046297  mov     rdx, rsi
0x18004629a  lea     rcx, [rbp+var_40]
0x18004629e  call    SczAllocFromSz
0x1800462a3  test    eax, eax
0x1800462a5  jns     short loc_1800462B0
0x1800462a7  lea     r9, aFailedAllocati; "Failed allocating memory"
0x1800462ae  jmp     short loc_18004628D
0x1800462b0  lea     rcx, [rbp+var_40]
0x1800462b4  call    SczEnsureBackslashTerminated
0x1800462b9  test    eax, eax
0x1800462bb  jns     short loc_1800462C6
0x1800462bd  lea     r9, aFailedToBacksl; "Failed to backslash terminate path."
0x1800462c4  jmp     short loc_18004628D
0x1800462c6  mov     rdx, [rbp+var_48]
0x1800462ca  lea     r8, aSystem32Ssshim; "System32\\ssshim.dll"
0x1800462d1  lea     rcx, [rbp+lpFileName]
0x1800462d5  call    SczAllocConcat2Sz
0x1800462da  test    eax, eax
0x1800462dc  jns     short loc_1800462E7
0x1800462de  lea     r9, aFailedToAppend; "Failed to append ssshim.dll to offline "...
0x1800462e5  jmp     short loc_18004628D
0x1800462e7  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800462eb  lea     rdx, [rbp+var_50]
0x1800462ef  call    FileExecutableArchitecture
0x1800462f4  test    eax, eax
0x1800462f6  jns     short loc_180046301
0x1800462f8  lea     r9, aFailedToGetArc; "Failed to get archecture from ssshim.dl"...
0x1800462ff  jmp     short loc_18004628D
0x180046301  movzx   ecx, [rbp+var_50]; unsigned __int16
0x180046305  lea     rdx, [rbp+var_4C]; unsigned int *
0x180046309  call    ?GetProcessorArchitectureFromImageArchitecture@@YAJGPEAK@Z; GetProcessorArchitectureFromImageArchitecture(ushort,ulong *)
0x18004630e  test    eax, eax
0x180046310  jns     short loc_18004631E
0x180046312  lea     r9, aFailedToGetPro_3; "Failed to get processor architecture."
0x180046319  jmp     loc_18004628D
0x18004631e  mov     rdx, [rbp+var_48]
0x180046322  lea     r9, [rbp+var_30]
0x180046326  mov     r8, rsi
0x180046329  mov     ecx, r14d
0x18004632c  call    EstimateDiskNeedsHelper
0x180046331  cmp     [rbp+var_18], 0
0x180046335  mov     rbx, rax
0x180046338  jz      short loc_18004633E
0x18004633a  xor     ebx, ebx
0x18004633c  jmp     short loc_18004635A
0x18004633e  mov     eax, [rbp+var_4C]
0x180046341  test    eax, eax
0x180046343  jz      short loc_180046353
0x180046345  cmp     eax, 5
0x180046348  jz      short loc_180046353
0x18004634a  add     rbx, 0C800000h
0x180046351  jmp     short loc_18004635A
0x180046353  add     rbx, 9600000h
0x18004635a  lea     r9, aPbrEstimatedRe_0; "pbr: Estimated reconstruction disk spac"...
0x180046361  mov     [rsp+80h+var_60], rbx
0x180046366  xor     r8d, r8d
0x180046369  xor     edx, edx
0x18004636b  mov     ecx, 4000000h
0x180046370  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x180046375  lea     rcx, [rbp+var_20]
0x180046379  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18004637e  lea     rcx, [rbp+var_40]
0x180046382  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180046387  lea     rcx, [rbp+var_48]
0x18004638b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180046390  mov     rax, rbx
0x180046393  mov     rcx, [rbp+var_10]
0x180046397  xor     rcx, rsp; StackCookie
0x18004639a  call    __security_check_cookie
0x18004639f  add     rsp, 80h
0x1800463a6  pop     r15
0x1800463a8  pop     r14
0x1800463aa  pop     r12
0x1800463ac  pop     rdi
0x1800463ad  pop     rsi
0x1800463ae  pop     rbx
0x1800463af  pop     rbp
0x1800463b0  retn
```
