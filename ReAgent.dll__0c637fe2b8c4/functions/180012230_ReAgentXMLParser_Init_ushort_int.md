# ReAgentXMLParser::Init(ushort *,int)

- ea: `0x180012230`
- end: `0x180012427`
- name: `?Init@ReAgentXMLParser@@UEAAKPEAGH@Z`
- size: `503`
- prototype: `__int64 __fastcall(ReAgentXMLParser *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800121b0`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x180012230`
- `0x18005f010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800123f1`
- `ntdll!RtlNtStatusToDosError` at `0x1800123f1`
- `KERNEL32!HeapAlloc` at `0x1800122e5`
- `KERNEL32!HeapAlloc` at `0x180012388`
- `KERNEL32!HeapAlloc` at `0x1800122e5`
- `KERNEL32!HeapAlloc` at `0x180012388`
- `KERNEL32!GetProcessHeap` at `0x1800122d1`
- `KERNEL32!GetProcessHeap` at `0x180012376`
- `KERNEL32!GetProcessHeap` at `0x1800122d1`
- `KERNEL32!GetProcessHeap` at `0x180012376`
- `ServicingCommon!RtlCreateUtf8UCSStringBuilder` at `0x1800123b0`
- `ServicingCommon!RtlCreateUtf8UCSStringBuilder` at `0x1800123b0`
- `ServicingCommon!RtlCreateDefaultXmlWriter` at `0x1800123d2`
- `ServicingCommon!RtlCreateDefaultXmlWriter` at `0x1800123d2`
- `ole32!CoTaskMemFree` at `0x180012258`
- `ole32!CoTaskMemFree` at `0x18001226f`
- `ole32!CoTaskMemFree` at `0x180012286`
- `ole32!CoTaskMemFree` at `0x180012258`
- `ole32!CoTaskMemFree` at `0x18001226f`
- `ole32!CoTaskMemFree` at `0x180012286`

## string_xrefs

- `0x1800122fc`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x18001233f`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180012312`: `ReAgentXMLParser::Init %s (0x%x) in file %S line %d`
- `0x180012362`: `ReAgentXMLParser::Init %s (0x%x) in file %S line %d`
- `0x180012356`: `failed to copy file path`
- `0x1800123bc`: `RtlCreateUtf8UCSStringBuilder failed: 0x%x`
- `0x1800123de`: `RtlCreateDefaultXmlWriter failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReAgentXMLParser::Init(ReAgentXMLParser *this, unsigned __int16 *a2, int a3)
{
  void *v4; // rcx
  void *v7; // rcx
  void *v8; // rcx
  unsigned __int64 v10; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // rax
  unsigned int v13; // edi
  HANDLE v14; // rax
  LPVOID v15; // rax
  NTSTATUS Utf8UCSStringBuilder; // edi
  int v18; // [rsp+28h] [rbp-40h]
  unsigned __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  v19 = 0;
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 2) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 1) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 8);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *((_QWORD *)this + 8) = 0;
  }
  if ( !a2 )
    return 87;
  if ( (int)StringCchLengthW(a2, 0x7FFFFFFFu, &v19) < 0 || !v19 )
    return 87;
  v10 = v19 + 1;
  ProcessHeap = GetProcessHeap();
  v12 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v10);
  *((_QWORD *)this + 1) = v12;
  if ( v12 )
  {
    v13 = StringCchCopyW(v12, v10, a2);
    if ( (v13 & 0x80000000) != 0 )
    {
      UnattendLogW(
        2,
        L"ReAgentXMLParser::Init %s (0x%x) in file %S line %d",
        L"failed to copy file path",
        v13,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
        357);
      return (unsigned __int16)v13;
    }
    v14 = GetProcessHeap();
    v15 = HeapAlloc(v14, 8u, 0x1D38u);
    *((_QWORD *)this + 8) = v15;
    if ( !v15 )
    {
      v18 = 363;
      goto LABEL_13;
    }
    Utf8UCSStringBuilder = RtlCreateUtf8UCSStringBuilder(0, 0, (char *)this + 56, (char *)this + 48);
    if ( Utf8UCSStringBuilder >= 0 )
    {
      Utf8UCSStringBuilder = RtlCreateDefaultXmlWriter(3, *((_QWORD *)this + 6), (char *)this + 40);
      if ( Utf8UCSStringBuilder >= 0 )
      {
        v13 = 0;
        if ( !a3 )
          return v13;
        return (unsigned int)(*(__int64 (__fastcall **)(ReAgentXMLParser *))(*(_QWORD *)this + 16LL))(this);
      }
      UnattendLogW(1, L"RtlCreateDefaultXmlWriter failed: 0x%x", (unsigned int)Utf8UCSStringBuilder);
    }
    else
    {
      UnattendLogW(1, L"RtlCreateUtf8UCSStringBuilder failed: 0x%x", (unsigned int)Utf8UCSStringBuilder);
    }
    return RtlNtStatusToDosError(Utf8UCSStringBuilder);
  }
  v18 = 355;
LABEL_13:
  v13 = 8;
  UnattendLogW(
    2,
    L"ReAgentXMLParser::Init %s (0x%x) in file %S line %d",
    L"failed to allocate memory",
    8,
    "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
    v18);
  return v13;
}

```

## disassembly

```asm
0x180012230  push    rbx
0x180012232  push    rbp
0x180012233  push    rsi
0x180012234  push    rdi
0x180012235  push    r14
0x180012237  push    r15
0x180012239  sub     rsp, 38h
0x18001223d  mov     rbx, rcx
0x180012240  mov     [rsp+68h+arg_0], 0
0x180012249  mov     rcx, [rcx+10h]; pv
0x18001224d  mov     r15d, r8d
0x180012250  mov     rbp, rdx
0x180012253  test    rcx, rcx
0x180012256  jz      short loc_180012266
0x180012258  call    cs:__imp_CoTaskMemFree
0x18001225e  mov     qword ptr [rbx+10h], 0
0x180012266  mov     rcx, [rbx+8]; pv
0x18001226a  test    rcx, rcx
0x18001226d  jz      short loc_18001227D
0x18001226f  call    cs:__imp_CoTaskMemFree
0x180012275  mov     qword ptr [rbx+8], 0
0x18001227d  mov     rcx, [rbx+40h]; pv
0x180012281  test    rcx, rcx
0x180012284  jz      short loc_180012294
0x180012286  call    cs:__imp_CoTaskMemFree
0x18001228c  mov     qword ptr [rbx+40h], 0
0x180012294  test    rbp, rbp
0x180012297  jnz     short loc_1800122A1
0x180012299  lea     eax, [rbp+57h]
0x18001229c  jmp     loc_18001241A
0x1800122a1  lea     r8, [rsp+68h+arg_0]; unsigned __int64 *
0x1800122a6  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800122ab  mov     rcx, rbp; unsigned __int16 *
0x1800122ae  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800122b3  test    eax, eax
0x1800122b5  js      loc_180012413
0x1800122bb  mov     rdi, [rsp+68h+arg_0]
0x1800122c0  test    rdi, rdi
0x1800122c3  jz      loc_180012413
0x1800122c9  mov     esi, 1
0x1800122ce  add     rdi, rsi
0x1800122d1  call    cs:__imp_GetProcessHeap
0x1800122d7  lea     r14d, [rsi+7]
0x1800122db  mov     rcx, rax; hHeap
0x1800122de  mov     edx, r14d; dwFlags
0x1800122e1  lea     r8, [rdi+rdi]; dwBytes
0x1800122e5  call    cs:__imp_HeapAlloc
0x1800122eb  mov     [rbx+8], rax
0x1800122ef  test    rax, rax
0x1800122f2  jnz     short loc_18001232B
0x1800122f4  mov     [rsp+68h+var_40], 163h
0x1800122fc  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180012303  mov     r9d, r14d
0x180012306  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x18001230d  mov     [rsp+68h+var_48], rax
0x180012312  lea     rdx, aReagentxmlpars_3; "ReAgentXMLParser::Init %s (0x%x) in fil"...
0x180012319  mov     ecx, 2
0x18001231e  mov     edi, r14d
0x180012321  call    UnattendLogW
0x180012326  jmp     loc_180012418
0x18001232b  mov     r8, rbp; unsigned __int16 *
0x18001232e  mov     rdx, rdi; unsigned __int64
0x180012331  mov     rcx, rax; unsigned __int16 *
0x180012334  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012339  mov     edi, eax
0x18001233b  test    eax, eax
0x18001233d  jns     short loc_180012376
0x18001233f  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180012346  mov     [rsp+68h+var_40], 165h
0x18001234e  mov     r9d, edi
0x180012351  mov     [rsp+68h+var_48], rax
0x180012356  lea     r8, aFailedToCopyFi_0; "failed to copy file path"
0x18001235d  mov     ecx, 2
0x180012362  lea     rdx, aReagentxmlpars_3; "ReAgentXMLParser::Init %s (0x%x) in fil"...
0x180012369  call    UnattendLogW
0x18001236e  movzx   edi, di
0x180012371  jmp     loc_180012418
0x180012376  call    cs:__imp_GetProcessHeap
0x18001237c  mov     r8d, 1D38h; dwBytes
0x180012382  mov     edx, r14d; dwFlags
0x180012385  mov     rcx, rax; hHeap
0x180012388  call    cs:__imp_HeapAlloc
0x18001238e  mov     [rbx+40h], rax
0x180012392  test    rax, rax
0x180012395  jnz     short loc_1800123A4
0x180012397  mov     [rsp+68h+var_40], 16Bh
0x18001239f  jmp     loc_1800122FC
0x1800123a4  lea     r8, [rbx+38h]
0x1800123a8  xor     edx, edx
0x1800123aa  lea     r9, [rbx+30h]
0x1800123ae  xor     ecx, ecx
0x1800123b0  call    cs:__imp_RtlCreateUtf8UCSStringBuilder
0x1800123b6  mov     edi, eax
0x1800123b8  test    eax, eax
0x1800123ba  jns     short loc_1800123C5
0x1800123bc  lea     rdx, aRtlcreateutf8u_0; "RtlCreateUtf8UCSStringBuilder failed: 0"...
0x1800123c3  jmp     short loc_1800123E5
0x1800123c5  mov     rdx, [rbx+30h]
0x1800123c9  lea     r8, [rbx+28h]
0x1800123cd  mov     ecx, 3
0x1800123d2  call    cs:__imp_RtlCreateDefaultXmlWriter
0x1800123d8  mov     edi, eax
0x1800123da  test    eax, eax
0x1800123dc  jns     short loc_1800123F9
0x1800123de  lea     rdx, aRtlcreatedefau_0; "RtlCreateDefaultXmlWriter failed: 0x%x"
0x1800123e5  mov     r8d, edi
0x1800123e8  mov     ecx, esi
0x1800123ea  call    UnattendLogW
0x1800123ef  mov     ecx, edi; Status
0x1800123f1  call    cs:__imp_RtlNtStatusToDosError
0x1800123f7  jmp     short loc_18001240F
0x1800123f9  xor     edi, edi
0x1800123fb  test    r15d, r15d
0x1800123fe  jz      short loc_180012418
0x180012400  mov     rax, [rbx]
0x180012403  mov     rcx, rbx
0x180012406  mov     rax, [rax+10h]
0x18001240a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001240f  mov     edi, eax
0x180012411  jmp     short loc_180012418
0x180012413  mov     edi, 57h ; 'W'
0x180012418  mov     eax, edi
0x18001241a  add     rsp, 38h
0x18001241e  pop     r15
0x180012420  pop     r14
0x180012422  pop     rdi
0x180012423  pop     rsi
0x180012424  pop     rbp
0x180012425  pop     rbx
0x180012426  retn
```
