# Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints(ushort const * *,RtlArray<void *> &,unsigned __int64 &,unsigned __int64,RtlArray<Windows::Compat::Appraiser::IProperty *> &)

- ea: `0x1800e57a8`
- end: `0x1800e5aac`
- name: `?AddMultiDatapoints@TelemetryOutputter@Appraiser@Compat@Windows@@CAJPEAPEBGAEAV?$RtlArray@PEAX@@AEA_K_KAEAV?$RtlArray@PEAVIProperty@Appraiser@Compat@Windows@@@@@Z`
- size: `772`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800e50a0`
- `0x1800ec190`

## callees

- `0x180013e88`
- `0x180013f90`
- `0x1800144c4`
- `0x1800287d4`
- `0x18002a778`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180083094`
- `0x18008f784`
- `0x1800e57a8`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800e57e0`
- `KERNEL32!GetProcessHeap` at `0x1800e5a63`
- `KERNEL32!GetProcessHeap` at `0x1800e57e0`
- `KERNEL32!GetProcessHeap` at `0x1800e5a63`
- `KERNEL32!HeapFree` at `0x1800e5a58`
- `KERNEL32!HeapFree` at `0x1800e5a71`
- `KERNEL32!HeapFree` at `0x1800e5a90`
- `KERNEL32!HeapFree` at `0x1800e5a58`
- `KERNEL32!HeapFree` at `0x1800e5a71`
- `KERNEL32!HeapFree` at `0x1800e5a90`

## string_xrefs

- `0x1800e5928`: `String copy error: [0x%x].`
- `0x1800e596c`: `String copy error: [0x%x].`
- `0x1800e5898`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800e58ef`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800e593f`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800e597a`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800e59ac`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800e59f9`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800e5a2d`: `onecore\base\appcompat\appraiser\outputters\telemetry.cpp`
- `0x1800e5891`: `Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints`
- `0x1800e58e8`: `Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints`
- `0x1800e5938`: `Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints`
- `0x1800e5973`: `Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints`
- `0x1800e59a5`: `Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints`
- `0x1800e59f2`: `Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints`
- `0x1800e5a26`: `Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints(
        __int64 a1,
        __int64 a2,
        unsigned __int64 *a3,
        unsigned __int64 a4,
        unsigned __int64 *a5)
{
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int64 *v11; // rsi
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdi
  _QWORD *v14; // rax
  const unsigned __int16 *v15; // rax
  int v16; // eax
  unsigned int v17; // ebx
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rsi
  int v20; // eax
  void *v21; // rdi
  int v22; // eax
  unsigned __int64 v23; // rax
  HANDLE ProcessHeap; // rax
  char *v26; // [rsp+20h] [rbp-61h]
  char *v27; // [rsp+30h] [rbp-51h]
  LPVOID lpMem[2]; // [rsp+40h] [rbp-41h] BYREF
  HANDLE hHeap[2]; // [rsp+50h] [rbp-31h] BYREF
  __int128 v30; // [rsp+60h] [rbp-21h]
  LPVOID v31[2]; // [rsp+70h] [rbp-11h]
  int v32; // [rsp+80h] [rbp-1h]

  lpMem[1] = (LPVOID)-2LL;
  hHeap[0] = GetProcessHeap();
  v31[0] = (LPVOID)16;
  v30 = 0;
  v31[1] = 0;
  hHeap[1] = (HANDLE)16;
  v32 = 0;
  RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(hHeap, v9, v10, 16);
  lpMem[0] = 0;
  v11 = a5;
  v12 = a5[2];
  if ( !v12 )
  {
LABEL_11:
    v18 = RtlStringArray::AllocMultiString((RtlStringArray *)hHeap);
    v19 = v18;
    if ( !v18 )
    {
      v17 = -2147024882;
      goto LABEL_28;
    }
    Windows::Compat::Appraiser::Utilities::MultiStringToSingleString(v18);
    v20 = Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc((unsigned __int16 **)lpMem, v19);
    v17 = v20;
    if ( v20 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x9ADu,
          "onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
          "Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints",
          "String copy error: [0x%x].",
          v20);
      if ( *a3 < a4 )
      {
        v21 = lpMem[0];
        a5 = (unsigned __int64 *)lpMem[0];
        v22 = RtlArray<JsonValue *>::Append(a2, &a5);
        v17 = v22;
        if ( v22 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x9B2u,
              "onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
              "Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints",
              "RtlArray append error: [0x%x].",
              v22);
          v23 = *a3;
          *(_QWORD *)(a1 + 8 * v23) = v21;
          *a3 = v23 + 1;
          v21 = 0;
          v17 = 0;
        }
        else
        {
          LODWORD(v27) = v22;
          LODWORD(v26) = v22;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            178,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
            "Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints",
            v26,
            (int)"RtlArray append error: [0x%x].",
            v27);
        }
        goto LABEL_26;
      }
      v17 = -2147024662;
      LODWORD(v26) = -2147024662;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        175,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
        "Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints",
        v26,
        (int)"Index exceeded Capacity.",
        v27);
    }
    else
    {
      LODWORD(v27) = v20;
      LODWORD(v26) = v20;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        173,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
        "Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints",
        v26,
        (int)"String copy error: [0x%x].",
        v27);
    }
    v21 = lpMem[0];
LABEL_26:
    HeapFree(hHeap[0], 0, v19);
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    goto LABEL_28;
  }
  v13 = 0;
  while ( 1 )
  {
    v14 = 0;
    if ( v13 < v12 )
    {
      a5 = 0;
      if ( !is_mul_ok(v11[1], v13) || (v14 = (_QWORD *)(v11[5] + v11[1] * v13), (unsigned __int64)v14 < v11[5]) )
        v14 = 0;
    }
    v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 16LL))(*v14);
    v16 = RtlStringArray::Append((RtlStringArray *)hHeap, v15, 0);
    v17 = v16;
    if ( v16 < 0 )
      break;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x9A4u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
        "Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints",
        "RtlArray append error: [0x%x].",
        v16);
    ++v13;
    v12 = v11[2];
    if ( v13 >= v12 )
      goto LABEL_11;
  }
  LODWORD(v27) = v16;
  LODWORD(v26) = v16;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    164,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\telemetry.cpp",
    "Windows::Compat::Appraiser::TelemetryOutputter::AddMultiDatapoints",
    v26,
    (int)"RtlArray append error: [0x%x].",
    v27);
LABEL_28:
  RtlStringArray::Clear((RtlStringArray *)hHeap);
  if ( v31[1] )
    HeapFree(hHeap[0], 0, v31[1]);
  return v17;
}

```

## disassembly

```asm
0x1800e57a8  push    rbp
0x1800e57aa  push    rbx
0x1800e57ab  push    rsi
0x1800e57ac  push    rdi
0x1800e57ad  push    r12
0x1800e57af  push    r13
0x1800e57b1  push    r14
0x1800e57b3  push    r15
0x1800e57b5  lea     rbp, [rsp-17h]
0x1800e57ba  sub     rsp, 98h
0x1800e57c1  mov     [rbp+4Fh+var_88], 0FFFFFFFFFFFFFFFEh
0x1800e57c9  mov     r15, r9
0x1800e57cc  mov     r14, r8
0x1800e57cf  mov     r13, rdx
0x1800e57d2  mov     r12, rcx
0x1800e57d5  xorps   xmm0, xmm0
0x1800e57d8  movups  xmmword ptr [rbp+4Fh+hHeap], xmm0
0x1800e57dc  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x1800e57e0  call    cs:__imp_GetProcessHeap
0x1800e57e6  mov     [rbp+4Fh+hHeap], rax
0x1800e57ea  mov     r9d, 10h
0x1800e57f0  mov     [rbp+4Fh+var_60], r9
0x1800e57f4  xorps   xmm0, xmm0
0x1800e57f7  movdqu  [rbp+4Fh+var_70], xmm0
0x1800e57fc  mov     [rbp+4Fh+var_60+8], 0
0x1800e5804  mov     [rbp+4Fh+hHeap+8], r9
0x1800e5808  mov     [rbp+4Fh+var_50], 0
0x1800e580f  lea     rcx, [rbp+4Fh+hHeap]
0x1800e5813  call    ?Initialize@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJPEAX_K1H@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x1800e5818  nop
0x1800e5819  mov     [rbp+4Fh+lpMem], 0
0x1800e5821  mov     rsi, [rbp+4Fh+arg_20]
0x1800e5825  mov     rcx, [rsi+10h]
0x1800e5829  test    rcx, rcx
0x1800e582c  jz      loc_1800E58B9
0x1800e5832  xor     edi, edi
0x1800e5834  xor     eax, eax
0x1800e5836  cmp     rdi, rcx
0x1800e5839  jnb     short loc_1800E5857
0x1800e583b  mov     [rbp+4Fh+arg_20], rax
0x1800e583f  mov     rax, rdi
0x1800e5842  mul     qword ptr [rsi+8]
0x1800e5846  test    rdx, rdx
0x1800e5849  jnz     short loc_1800E5855
0x1800e584b  add     rax, [rsi+28h]
0x1800e584f  cmp     rax, [rsi+28h]
0x1800e5853  jnb     short loc_1800E5857
0x1800e5855  xor     eax, eax
0x1800e5857  mov     rcx, [rax]
0x1800e585a  mov     rax, [rcx]
0x1800e585d  mov     rax, [rax+10h]
0x1800e5861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5866  mov     rdx, rax; unsigned __int16 *
0x1800e5869  xor     r8d, r8d; unsigned __int64
0x1800e586c  lea     rcx, [rbp+4Fh+hHeap]; this
0x1800e5870  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x1800e5875  mov     ebx, eax
0x1800e5877  test    eax, eax
0x1800e5879  js      short loc_1800E58D4
0x1800e587b  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800e5881  test    cl, 1
0x1800e5884  jz      short loc_1800E58A9
0x1800e5886  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800e588a  lea     r9, aRtlarrayAppend_1; "RtlArray append error: [0x%x]."
0x1800e5891  lea     r8, aWindowsCompatA_625; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800e5898  lea     rdx, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800e589f  mov     ecx, 9A4h; unsigned int
0x1800e58a4  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800e58a9  inc     rdi
0x1800e58ac  mov     rcx, [rsi+10h]
0x1800e58b0  cmp     rdi, rcx
0x1800e58b3  jb      loc_1800E5834
0x1800e58b9  lea     rcx, [rbp+4Fh+hHeap]; this
0x1800e58bd  call    ?AllocMultiString@RtlStringArray@@QEAAPEAGXZ; RtlStringArray::AllocMultiString(void)
0x1800e58c2  mov     rsi, rax
0x1800e58c5  test    rax, rax
0x1800e58c8  jnz     short loc_1800E590A
0x1800e58ca  mov     ebx, 8007000Eh
0x1800e58cf  jmp     loc_1800E5A78
0x1800e58d4  mov     dword ptr [rsp+0D0h+var_A0], ebx; char *
0x1800e58d8  lea     rax, aRtlarrayAppend_1; "RtlArray append error: [0x%x]."
0x1800e58df  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x1800e58e4  mov     dword ptr [rsp+0D0h+var_B0], ebx; char *
0x1800e58e8  lea     r9, aWindowsCompatA_625; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800e58ef  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800e58f6  mov     edx, 9A4h; bool
0x1800e58fb  mov     ecx, 1; this
0x1800e5900  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800e5905  jmp     loc_1800E5A78
0x1800e590a  mov     rcx, rsi; unsigned __int16 *
0x1800e590d  call    ?MultiStringToSingleString@Utilities@Appraiser@Compat@Windows@@SAXPEAG@Z; Windows::Compat::Appraiser::Utilities::MultiStringToSingleString(ushort *)
0x1800e5912  mov     rdx, rsi; unsigned __int16 *
0x1800e5915  lea     rcx, [rbp+4Fh+lpMem]; unsigned __int16 **
0x1800e5919  call    ?CopyStringNonConstAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAGPEBG@Z; Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(ushort * *,ushort const *)
0x1800e591e  mov     ebx, eax
0x1800e5920  test    eax, eax
0x1800e5922  jns     short loc_1800E595E
0x1800e5924  mov     dword ptr [rsp+0D0h+var_A0], eax; char *
0x1800e5928  lea     r9, aStringCopyErro; "String copy error: [0x%x]."
0x1800e592f  mov     qword ptr [rsp+0D0h+var_A8], r9; int
0x1800e5934  mov     dword ptr [rsp+0D0h+var_B0], eax; char *
0x1800e5938  lea     r9, aWindowsCompatA_625; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800e593f  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800e5946  mov     edx, 9ADh; bool
0x1800e594b  mov     ecx, 1; this
0x1800e5950  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800e5955  mov     rdi, [rbp+4Fh+lpMem]
0x1800e5959  jmp     loc_1800E5A4F
0x1800e595e  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800e5964  test    al, 1
0x1800e5966  jz      short loc_1800E598B
0x1800e5968  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1800e596c  lea     r9, aStringCopyErro; "String copy error: [0x%x]."
0x1800e5973  lea     r8, aWindowsCompatA_625; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800e597a  lea     rdx, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800e5981  mov     ecx, 9ADh; unsigned int
0x1800e5986  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800e598b  cmp     [r14], r15
0x1800e598e  jb      short loc_1800E59C4
0x1800e5990  lea     rax, aIndexExceededC; "Index exceeded Capacity."
0x1800e5997  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x1800e599c  mov     ebx, 800700EAh
0x1800e59a1  mov     dword ptr [rsp+0D0h+var_B0], ebx; char *
0x1800e59a5  lea     r9, aWindowsCompatA_625; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800e59ac  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800e59b3  mov     edx, 9AFh; bool
0x1800e59b8  mov     ecx, 1; this
0x1800e59bd  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800e59c2  jmp     short loc_1800E5955
0x1800e59c4  mov     rdi, [rbp+4Fh+lpMem]
0x1800e59c8  mov     [rbp+4Fh+arg_20], rdi
0x1800e59cc  lea     rdx, [rbp+4Fh+arg_20]
0x1800e59d0  mov     rcx, r13
0x1800e59d3  call    ?Append@?$RtlArray@PEAUJsonValue@@@@QEAAJAEBQEAUJsonValue@@@Z; RtlArray<JsonValue *>::Append(JsonValue * const &)
0x1800e59d8  mov     ebx, eax
0x1800e59da  test    eax, eax
0x1800e59dc  jns     short loc_1800E5A11
0x1800e59de  mov     dword ptr [rsp+0D0h+var_A0], eax; char *
0x1800e59e2  lea     rax, aRtlarrayAppend_1; "RtlArray append error: [0x%x]."
0x1800e59e9  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x1800e59ee  mov     dword ptr [rsp+0D0h+var_B0], ebx; char *
0x1800e59f2  lea     r9, aWindowsCompatA_625; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800e59f9  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800e5a00  mov     edx, 9B2h; bool
0x1800e5a05  mov     ecx, 1; this
0x1800e5a0a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800e5a0f  jmp     short loc_1800E5A4F
0x1800e5a11  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800e5a17  test    al, 1
0x1800e5a19  jz      short loc_1800E5A3E
0x1800e5a1b  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1800e5a1f  lea     r9, aRtlarrayAppend_1; "RtlArray append error: [0x%x]."
0x1800e5a26  lea     r8, aWindowsCompatA_625; "Windows::Compat::Appraiser::TelemetryOu"...
0x1800e5a2d  lea     rdx, aOnecoreBaseApp_22; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800e5a34  mov     ecx, 9B2h; unsigned int
0x1800e5a39  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800e5a3e  mov     rax, [r14]
0x1800e5a41  mov     [r12+rax*8], rdi
0x1800e5a45  inc     rax
0x1800e5a48  mov     [r14], rax
0x1800e5a4b  xor     edi, edi
0x1800e5a4d  xor     ebx, ebx
0x1800e5a4f  mov     r8, rsi; lpMem
0x1800e5a52  xor     edx, edx; dwFlags
0x1800e5a54  mov     rcx, [rbp+4Fh+hHeap]; hHeap
0x1800e5a58  call    cs:__imp_HeapFree
0x1800e5a5e  test    rdi, rdi
0x1800e5a61  jz      short loc_1800E5A78
0x1800e5a63  call    cs:__imp_GetProcessHeap
0x1800e5a69  mov     r8, rdi; lpMem
0x1800e5a6c  xor     edx, edx; dwFlags
0x1800e5a6e  mov     rcx, rax; hHeap
0x1800e5a71  call    cs:__imp_HeapFree
0x1800e5a77  nop
0x1800e5a78  lea     rcx, [rbp+4Fh+hHeap]; this
0x1800e5a7c  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x1800e5a81  mov     r8, [rbp+4Fh+var_60+8]; lpMem
0x1800e5a85  test    r8, r8
0x1800e5a88  jz      short loc_1800E5A96
0x1800e5a8a  xor     edx, edx; dwFlags
0x1800e5a8c  mov     rcx, [rbp+4Fh+hHeap]; hHeap
0x1800e5a90  call    cs:__imp_HeapFree
0x1800e5a96  mov     eax, ebx
0x1800e5a98  add     rsp, 98h
0x1800e5a9f  pop     r15
0x1800e5aa1  pop     r14
0x1800e5aa3  pop     r13
0x1800e5aa5  pop     r12
0x1800e5aa7  pop     rdi
0x1800e5aa8  pop     rsi
0x1800e5aa9  pop     rbx
0x1800e5aaa  pop     rbp
0x1800e5aab  retn
```
