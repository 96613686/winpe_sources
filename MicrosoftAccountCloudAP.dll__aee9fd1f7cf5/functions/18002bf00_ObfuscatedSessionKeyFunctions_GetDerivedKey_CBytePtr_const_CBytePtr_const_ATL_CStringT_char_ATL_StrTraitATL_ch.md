# ObfuscatedSessionKeyFunctions::GetDerivedKey(CBytePtr const &,CBytePtr const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ulong,CBytePtr &)

- ea: `0x18002bf00`
- end: `0x18002e2bc`
- name: `?GetDerivedKey@ObfuscatedSessionKeyFunctions@@UEAAJAEBVCBytePtr@@0AEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@KAEAV2@@Z`
- size: `9148`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const void **, unsigned int, void **)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005bbc`
- `0x180006e84`
- `0x180008440`
- `0x18000baac`
- `0x1800168f0`
- `0x180016924`
- `0x18001696c`
- `0x1800176a4`
- `0x18002bf00`
- `0x18002e2c4`
- `0x18002fbd4`
- `0x18002fddc`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002d1b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002d1b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d1ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d1ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c019`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c0b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c1a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c644`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ca9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cbe4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cc3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cce2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ce6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d051`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d35f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d3c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d434`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d4ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002de7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c019`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c0b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c1a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c644`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ca9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cbe4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cc3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cce2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ce6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d051`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d35f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d3c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d434`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d4ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002de7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c322`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c33f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cadb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cbae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cdae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d094`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d52b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d55c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d58d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d5b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d65c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d68d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d6be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d6e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002df25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002df57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002df83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dfaf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dfcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dfe9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e02c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e051`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e076`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e092`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e0af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e226`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e23f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c322`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c33f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cadb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cbae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cdae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d094`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d52b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d55c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d58d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d5b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d65c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d68d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d6be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d6e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002df25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002df57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002df83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dfaf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dfcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dfe9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e02c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e051`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e076`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e092`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e0af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e226`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e23f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c003`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c0a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c191`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c314`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c331`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c633`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cacb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cafc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cba0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cbd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cc26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cccf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ce59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d040`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d084`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d34d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d3b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d4a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d51b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d54c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d57d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d5a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d64c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d67d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d6ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d6d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002de65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002df17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002df47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002df73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002df9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dfbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dfdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e01e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e043`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e068`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e084`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e0a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e218`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e231`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c003`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c0a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c191`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c314`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c331`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c633`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cacb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cafc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cba0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cbd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cc26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cccf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ce59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d040`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d084`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d34d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d3b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d4a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d51b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d54c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d57d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d5a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d64c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d67d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d6ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d6d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002de65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002df17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002df47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002df73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002df9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dfbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dfdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dff4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e01e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e043`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e068`

## string_xrefs

- `0x18002d1aa`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ObfuscatedSessionKeyFunctions::GetDerivedKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const void **a4,
        unsigned int a5,
        void **a6)
{
  __int64 *v9; // rax
  __int64 v10; // rdx
  int v11; // r8d
  int v12; // r14d
  unsigned int v13; // edi
  unsigned int v14; // ebx
  HANDLE ProcessHeap; // rax
  _OWORD *v16; // rax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r8
  void *v19; // r15
  void *v20; // r13
  HANDLE v21; // rax
  _QWORD *v22; // rax
  unsigned __int64 v23; // rsi
  void *v24; // r12
  unsigned int v25; // eax
  unsigned int v26; // ecx
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rdi
  HANDLE v30; // rax
  _DWORD *v31; // rax
  int v32; // ecx
  unsigned int v33; // eax
  void *v34; // r10
  unsigned int v35; // r9d
  unsigned int v36; // edi
  int v37; // ecx
  unsigned int v38; // eax
  unsigned __int64 v39; // r10
  void *v40; // r10
  HANDLE v41; // rax
  HANDLE v42; // rax
  int v43; // ecx
  unsigned int v44; // eax
  unsigned int v45; // ecx
  int v46; // ecx
  unsigned int v47; // eax
  unsigned int v48; // eax
  int v49; // ecx
  unsigned int v50; // eax
  unsigned int v51; // eax
  int v52; // ecx
  unsigned int v53; // eax
  void *v54; // rax
  unsigned int v55; // eax
  unsigned int v56; // edi
  HANDLE v57; // rax
  _DWORD *v58; // rax
  void *v59; // rdi
  unsigned int *v60; // rbx
  __int64 v61; // r14
  char *v62; // rdx
  unsigned __int8 v63; // al
  unsigned __int64 i; // rcx
  unsigned __int8 *v65; // r15
  _BYTE *v66; // r13
  int v67; // r9d
  unsigned int v68; // r10d
  int v69; // edi
  int v70; // ebx
  int v71; // r11d
  unsigned int v72; // r9d
  int v73; // r11d
  int v74; // r10d
  int v75; // r9d
  unsigned int v76; // r8d
  int v77; // r10d
  int v78; // edx
  int v79; // r8d
  int v80; // r10d
  int v81; // r8d
  unsigned int v82; // r9d
  unsigned int v83; // r10d
  int v84; // r8d
  int v85; // r9d
  int v86; // r10d
  int v87; // r8d
  int v88; // r9d
  int v89; // r10d
  int v90; // r11d
  int v91; // r9d
  unsigned int v92; // r8d
  int v93; // r10d
  HANDLE v94; // rax
  _DWORD *v95; // rax
  int v96; // r14d
  unsigned int *v97; // rax
  HANDLE v98; // rax
  HANDLE v99; // rax
  HANDLE v100; // rax
  void *v101; // rcx
  _QWORD *v102; // rax
  HANDLE v103; // rax
  _OWORD *v104; // rcx
  HANDLE v105; // rax
  _QWORD *v106; // rax
  HANDLE v107; // rax
  HANDLE v108; // rax
  HANDLE v109; // rax
  HANDLE v110; // rax
  int v111; // ecx
  unsigned int v112; // ecx
  unsigned int v113; // ecx
  unsigned int v114; // ebx
  HANDLE v115; // rax
  char *v116; // rax
  char *v117; // rcx
  char *v118; // rcx
  unsigned int v119; // r10d
  unsigned int v120; // r9d
  unsigned int v121; // r11d
  unsigned int v122; // eax
  char *v123; // r11
  __int64 v124; // rax
  unsigned int v125; // ebx
  HANDLE v126; // rax
  HANDLE v127; // rax
  char *v128; // r8
  __int64 v129; // rax
  unsigned int v130; // r9d
  unsigned int v131; // r11d
  int LastError; // eax
  bool v133; // sf
  FARPROC ProcAddress; // rax
  __int64 v135; // rcx
  unsigned int *v136; // r11
  SIZE_T v137; // r9
  unsigned int v138; // r11d
  unsigned __int64 v139; // r10
  unsigned int v140; // r10d
  HANDLE v141; // rax
  _QWORD *v142; // rcx
  HANDLE v143; // rax
  void *v144; // rax
  HANDLE v145; // rax
  void *v146; // r9
  HANDLE v147; // rax
  void *v148; // rcx
  _QWORD *v149; // rax
  HANDLE v150; // rax
  HANDLE v151; // rax
  HANDLE v152; // rax
  HANDLE v153; // rax
  int v154; // ecx
  unsigned int *v155; // rax
  HANDLE v156; // rax
  HANDLE v157; // rax
  HANDLE v158; // rax
  HANDLE v159; // rax
  _DWORD *v160; // rax
  _DWORD *v161; // r10
  unsigned __int8 v162; // dl
  unsigned __int64 v163; // r11
  unsigned __int8 *v164; // r8
  unsigned int v165; // edx
  int v166; // r10d
  int v167; // r11d
  unsigned int v168; // r9d
  int v169; // ecx
  int v170; // r8d
  _BYTE *v171; // r10
  unsigned int v172; // r11d
  char v173; // bl
  int v174; // r10d
  unsigned __int8 *v175; // rdx
  _BYTE *v176; // r14
  int v177; // r12d
  int v178; // r15d
  int v179; // esi
  int v180; // edi
  int v181; // ecx
  unsigned int v182; // r9d
  int v183; // r10d
  unsigned int v184; // ecx
  int v185; // r9d
  int v186; // r10d
  unsigned int v187; // ecx
  int v188; // r9d
  int v189; // r11d
  int v190; // ebx
  unsigned int v191; // r10d
  int v192; // r9d
  unsigned int v193; // r10d
  int v194; // ecx
  int v195; // r9d
  int v196; // r10d
  int v197; // ecx
  unsigned int v198; // r9d
  int v199; // r10d
  int v200; // ecx
  int v201; // r9d
  unsigned int v202; // r10d
  int v203; // ecx
  unsigned __int64 j; // rax
  unsigned int *v205; // rcx
  _DWORD *v206; // r9
  char *v207; // r11
  unsigned __int64 v208; // rax
  char *v209; // r9
  int v210; // ebx
  char *v211; // rcx
  HANDLE v212; // rax
  size_t v213; // rbx
  int *v214; // rax
  HANDLE v215; // rax
  HANDLE v216; // rax
  HANDLE v217; // rax
  HANDLE v218; // rax
  HANDLE v219; // rax
  HANDLE v220; // rax
  HANDLE v221; // rax
  void *v222; // rdi
  HANDLE v223; // rax
  void *v224; // rdi
  HANDLE v225; // rax
  void *v226; // rdi
  HANDLE v227; // rax
  HANDLE v228; // rax
  HANDLE v229; // rax
  int *v230; // r14
  int *v231; // rax
  int *v232; // rcx
  _QWORD *v233; // rcx
  unsigned int *v234; // rax
  unsigned int *v235; // rcx
  HANDLE v236; // rax
  HANDLE v237; // rax
  const unsigned __int16 *v239; // [rsp+20h] [rbp-E0h]
  int v240; // [rsp+20h] [rbp-E0h]
  unsigned int v241; // [rsp+30h] [rbp-D0h]
  int v242; // [rsp+30h] [rbp-D0h]
  unsigned int v243; // [rsp+30h] [rbp-D0h]
  int v244; // [rsp+30h] [rbp-D0h]
  int v245; // [rsp+30h] [rbp-D0h]
  unsigned int *v246; // [rsp+38h] [rbp-C8h]
  void *v247; // [rsp+38h] [rbp-C8h]
  _QWORD *v248; // [rsp+40h] [rbp-C0h]
  char *v249; // [rsp+40h] [rbp-C0h]
  _QWORD *v250; // [rsp+40h] [rbp-C0h]
  LPVOID v251; // [rsp+48h] [rbp-B8h]
  void *v252; // [rsp+48h] [rbp-B8h]
  void *v253; // [rsp+48h] [rbp-B8h]
  void *v254; // [rsp+48h] [rbp-B8h]
  char *v255; // [rsp+48h] [rbp-B8h]
  char *v256; // [rsp+48h] [rbp-B8h]
  char *v257; // [rsp+48h] [rbp-B8h]
  unsigned int *v258; // [rsp+48h] [rbp-B8h]
  void *v259; // [rsp+48h] [rbp-B8h]
  void *v260; // [rsp+48h] [rbp-B8h]
  void *v261; // [rsp+48h] [rbp-B8h]
  void *v262; // [rsp+48h] [rbp-B8h]
  void *v263; // [rsp+48h] [rbp-B8h]
  void *v264; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v265; // [rsp+48h] [rbp-B8h]
  void *v266; // [rsp+48h] [rbp-B8h]
  void *v267; // [rsp+48h] [rbp-B8h]
  void *v268; // [rsp+48h] [rbp-B8h]
  unsigned int *v269; // [rsp+58h] [rbp-A8h]
  unsigned int v270; // [rsp+60h] [rbp-A0h]
  int v271; // [rsp+60h] [rbp-A0h]
  int v272; // [rsp+60h] [rbp-A0h]
  int v273; // [rsp+60h] [rbp-A0h]
  unsigned int v274; // [rsp+60h] [rbp-A0h]
  char v275; // [rsp+60h] [rbp-A0h]
  int v276; // [rsp+68h] [rbp-98h]
  char *v277; // [rsp+68h] [rbp-98h]
  unsigned int v278; // [rsp+68h] [rbp-98h]
  _QWORD *v279; // [rsp+68h] [rbp-98h]
  int v280; // [rsp+68h] [rbp-98h]
  void *v281; // [rsp+70h] [rbp-90h]
  void *Src; // [rsp+78h] [rbp-88h]
  char *Srca; // [rsp+78h] [rbp-88h]
  char *Srcb; // [rsp+78h] [rbp-88h]
  _DWORD *Srcc; // [rsp+78h] [rbp-88h]
  char *Srcd; // [rsp+78h] [rbp-88h]
  char *Srce; // [rsp+78h] [rbp-88h]
  SIZE_T Srcf; // [rsp+78h] [rbp-88h]
  _BYTE *Srcg; // [rsp+78h] [rbp-88h]
  char *Srch; // [rsp+78h] [rbp-88h]
  unsigned int v291; // [rsp+80h] [rbp-80h]
  unsigned int v292; // [rsp+80h] [rbp-80h]
  unsigned int v293; // [rsp+80h] [rbp-80h]
  unsigned int v294; // [rsp+80h] [rbp-80h]
  char *v295; // [rsp+80h] [rbp-80h]
  int v296; // [rsp+80h] [rbp-80h]
  unsigned int v297; // [rsp+88h] [rbp-78h]
  unsigned int v298; // [rsp+88h] [rbp-78h]
  int v299; // [rsp+8Ch] [rbp-74h]
  int v300; // [rsp+8Ch] [rbp-74h]
  __int64 v301; // [rsp+90h] [rbp-70h]
  unsigned __int64 v302; // [rsp+90h] [rbp-70h]
  _QWORD *v303; // [rsp+98h] [rbp-68h]
  unsigned int Size; // [rsp+A0h] [rbp-60h]
  int Sizea; // [rsp+A0h] [rbp-60h]
  SIZE_T v306; // [rsp+A8h] [rbp-58h]
  SIZE_T v307; // [rsp+A8h] [rbp-58h]
  void *v308; // [rsp+B0h] [rbp-50h]
  unsigned int v309; // [rsp+B0h] [rbp-50h]
  char *v310; // [rsp+B0h] [rbp-50h]
  _DWORD *v311; // [rsp+B0h] [rbp-50h]
  const void *dwBytes; // [rsp+B8h] [rbp-48h]
  unsigned int dwBytesa; // [rsp+B8h] [rbp-48h]
  SIZE_T dwBytesb; // [rsp+B8h] [rbp-48h]
  SIZE_T dwBytesc; // [rsp+B8h] [rbp-48h]
  SIZE_T dwBytesd; // [rsp+B8h] [rbp-48h]
  unsigned int v317; // [rsp+C0h] [rbp-40h]
  unsigned int v318; // [rsp+C0h] [rbp-40h]
  unsigned int v319; // [rsp+C0h] [rbp-40h]
  unsigned int v320; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v321; // [rsp+C0h] [rbp-40h]
  unsigned int v322; // [rsp+C8h] [rbp-38h]
  int v323; // [rsp+C8h] [rbp-38h]
  int *lpMem; // [rsp+D0h] [rbp-30h]
  int v325; // [rsp+D8h] [rbp-28h] BYREF
  void *v326; // [rsp+E0h] [rbp-20h]
  void *v327; // [rsp+E8h] [rbp-18h]
  void *v328; // [rsp+F0h] [rbp-10h]
  void *v329; // [rsp+F8h] [rbp-8h]
  unsigned int v330; // [rsp+100h] [rbp+0h]
  __int64 v331; // [rsp+108h] [rbp+8h] BYREF
  HMODULE phModule; // [rsp+110h] [rbp+10h] BYREF
  __int128 v333; // [rsp+118h] [rbp+18h] BYREF
  __int128 v334; // [rsp+128h] [rbp+28h]
  __int64 v335; // [rsp+138h] [rbp+38h] BYREF
  void *v336; // [rsp+140h] [rbp+40h]
  _QWORD v337[13]; // [rsp+148h] [rbp+48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v330 = a5;
  v331 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
  {
    v9 = std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,unsigned short const (&)[5],0>(
           &v335,
           L"o.gd");
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(
      &v331,
      v9);
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v335);
  }
  v325 = 0;
  v337[0] = "ObfuscatedSessionKeyFunctions::GetDerivedKey";
  v337[1] = &v325;
  v337[2] = 0;
  v337[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\sessionkeymanager\\obfuscatedsessionkeyfunctions.cpp",
    "ObfuscatedSessionKeyFunctions::GetDerivedKey",
    (const char *)0x17,
    0,
    v239);
  if ( *(_DWORD *)a2 )
  {
    CBytePtr::SetLength((CBytePtr *)a6, a5, 1);
    if ( a5 < 0x20 )
    {
      v12 = -2147024774;
      v325 = -2147024774;
LABEL_405:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\sessionkeymanager\\obfuscatedsessionkeyfunctions.cpp",
        (const char *)(unsigned int)v12,
        v240);
      goto LABEL_406;
    }
    v336 = a6[1];
    v297 = *(_DWORD *)a3;
    v308 = *(void **)(a3 + 8);
    dwBytes = *a4;
    v13 = *((_DWORD *)*a4 - 4);
    v270 = v13;
    v14 = *(_DWORD *)a2;
    Size = *(_DWORD *)a2;
    Src = *(void **)(a2 + 8);
    ProcessHeap = GetProcessHeap();
    v16 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
    v19 = v16;
    if ( !v16 )
    {
      v20 = 0;
      v12 = -1073741801;
      goto LABEL_54;
    }
    *v16 = xmmword_18004D3C0;
    v16[1] = xmmword_18004D3D0;
    v16[2] = xmmword_18004D3E0;
    v16[3] = xmmword_18004D3F0;
    v16[4] = xmmword_18004D400;
    v16[5] = xmmword_18004D410;
    v16[6] = xmmword_18004D420;
    v16[7] = xmmword_18004D430;
    v16[8] = xmmword_18004D440;
    v16[9] = xmmword_18004D450;
    v21 = GetProcessHeap();
    v22 = HeapAlloc(v21, 8u, 8u);
    v20 = v22;
    if ( !v22 )
    {
      v12 = -1073741801;
      goto LABEL_54;
    }
    *v22 = qword_18004D300;
    v23 = __rdtsc();
    v322 = v14 + 4;
    if ( v14 >= 0xFFFFFFFC )
    {
      v12 = -1073741675;
      goto LABEL_399;
    }
    v24 = 0;
    lpMem = 0;
    v276 = 0;
    v25 = v14 + 200;
    LODWORD(v18) = -1;
    v299 = -1;
    v26 = -1;
    v17 = 196;
    if ( v14 + 200 >= 0xC4 )
      v26 = v14 + 200;
    v12 = v25 < 0xC4 ? -805306219 : 0x10000000;
    if ( v25 < 0xC4 )
      goto LABEL_47;
    v317 = v13 + 4;
    if ( v13 < 0xFFFFFFFC )
    {
      v27 = v26 + v13 + 4;
      v17 = 0xFFFFFFFFLL;
      if ( v27 >= v26 )
        v17 = v27;
      v12 = v27 < v26 ? -805306219 : 0x10000000;
      if ( v27 < v26 )
        goto LABEL_47;
      v291 = v297 + 4;
      if ( v297 < 0xFFFFFFFC )
      {
        v28 = v17 + v297 + 4;
        v29 = 0xFFFFFFFFLL;
        if ( v28 >= (unsigned int)v17 )
          v29 = v28;
        v12 = v28 < (unsigned int)v17 ? -805306219 : 0x10000000;
        if ( v28 >= (unsigned int)v17 )
        {
          v30 = GetProcessHeap();
          v31 = HeapAlloc(v30, 8u, (unsigned int)v29);
          v24 = v31;
          if ( !v31 )
          {
            v12 = -1073741801;
LABEL_399:
            v236 = GetProcessHeap();
            HeapFree(v236, 0, v19);
LABEL_400:
            if ( v20 )
            {
              v237 = GetProcessHeap();
              HeapFree(v237, 0, v20);
            }
            v325 = v12;
            if ( v12 >= 0 )
            {
              CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v337, v17, v18);
              std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v331);
              return 0;
            }
            goto LABEL_405;
          }
          v17 = (unsigned __int64)(v31 + 1);
          if ( v31 + 1 < v31 )
            goto LABEL_46;
          if ( v31 + 2 <= (_DWORD *)((char *)v31 + v29) )
          {
            *v31 = 4;
            *(_DWORD *)v17 = 113;
            v17 = (unsigned __int64)v31;
            v32 = 0;
            do
            {
              v33 = *(_DWORD *)v17 + 4;
              if ( *(_DWORD *)v17 >= 0xFFFFFFFC )
                goto LABEL_46;
              v18 = v17 + v33;
              if ( v18 < v17 )
                goto LABEL_46;
              v17 += v33;
              ++v32;
            }
            while ( !v32 );
            v34 = (void *)(v18 + 4);
            if ( v18 + 4 < v18 )
              goto LABEL_46;
            v35 = v29;
            LODWORD(v18) = 160;
            if ( v17 + 164 <= (unsigned __int64)v24 + v29 )
            {
              *(_DWORD *)v17 = 160;
              if ( v19 )
              {
                memcpy_0(v34, v19, 0xA0u);
                v35 = v29;
              }
              LODWORD(v18) = 8;
              v36 = v35;
              if ( !v20 )
                goto LABEL_64;
              if ( v24 )
              {
                v37 = 0;
                v17 = (unsigned __int64)v24;
                while ( 1 )
                {
                  v38 = *(_DWORD *)v17 + 4;
                  if ( *(_DWORD *)v17 >= 0xFFFFFFFC )
                    goto LABEL_46;
                  v39 = v17 + v38;
                  if ( v39 < v17 )
                    goto LABEL_46;
                  v17 += v38;
                  if ( (unsigned int)++v37 >= 2 )
                  {
                    v40 = (void *)(v39 + 4);
                    if ( (unsigned __int64)v40 < v17 )
                      goto LABEL_46;
                    if ( v17 + 12 <= (unsigned __int64)v24 + v35 )
                    {
                      *(_DWORD *)v17 = 8;
                      memcpy_0(v40, v20, 8u);
                      v17 = (unsigned __int64)v24;
                      v43 = 0;
                      LODWORD(v18) = v36;
                      v241 = v36;
                      while ( 1 )
                      {
                        v44 = *(_DWORD *)v17 + 4;
                        if ( *(_DWORD *)v17 >= 0xFFFFFFFC || v17 + v44 < v17 )
                          goto LABEL_46;
                        v17 += v44;
                        if ( (unsigned int)++v43 >= 3 )
                        {
                          if ( v17 + 4 < v17 )
                            goto LABEL_46;
                          if ( v17 + 12 <= (unsigned __int64)v24 + v36 )
                          {
                            *(_DWORD *)v17 = 8;
                            *(_QWORD *)(v17 + 4) = v23;
                            goto LABEL_62;
                          }
                          goto LABEL_105;
                        }
                      }
                    }
                    goto LABEL_105;
                  }
                }
              }
              if ( v35 + 12 < v35 )
                goto LABEL_46;
              LODWORD(v18) = v35 + 24;
              v241 = v35 + 24;
              if ( v35 + 24 < v35 + 12 )
                goto LABEL_46;
LABEL_62:
              if ( Src )
              {
                if ( !Size )
                  goto LABEL_64;
              }
              else if ( Size )
              {
LABEL_64:
                v12 = -1073741811;
                goto LABEL_47;
              }
              if ( v24 )
              {
                v17 = (unsigned __int64)v24;
                v46 = 0;
                while ( 1 )
                {
                  v47 = *(_DWORD *)v17 + 4;
                  if ( *(_DWORD *)v17 >= 0xFFFFFFFC || v17 + v47 < v17 )
                    goto LABEL_46;
                  v17 += v47;
                  if ( (unsigned int)++v46 >= 4 )
                  {
                    if ( v17 + 4 < v17 )
                      goto LABEL_46;
                    if ( v17 + Size + 4LL <= (unsigned __int64)v24 + (unsigned int)v18 )
                    {
                      *(_DWORD *)v17 = Size;
                      if ( Src )
                      {
                        memcpy_0((void *)(v17 + 4), Src, Size);
                        LODWORD(v18) = v241;
                      }
                      goto LABEL_77;
                    }
                    goto LABEL_105;
                  }
                }
              }
              v45 = v18 + v322;
              if ( (unsigned int)v18 + v322 < (unsigned int)v18 )
                goto LABEL_46;
              LODWORD(v18) = v18 + v322;
              v241 = v45;
LABEL_77:
              if ( dwBytes )
              {
                if ( !v270 )
                  goto LABEL_64;
              }
              else if ( v270 )
              {
                goto LABEL_64;
              }
              if ( v24 )
              {
                v17 = (unsigned __int64)v24;
                v49 = 0;
                while ( 1 )
                {
                  v50 = *(_DWORD *)v17 + 4;
                  if ( *(_DWORD *)v17 >= 0xFFFFFFFC || v17 + v50 < v17 )
                    goto LABEL_46;
                  v17 += v50;
                  if ( (unsigned int)++v49 >= 5 )
                  {
                    if ( v17 + 4 < v17 )
                      goto LABEL_46;
                    if ( v17 + v270 + 4LL <= (unsigned __int64)v24 + (unsigned int)v18 )
                    {
                      *(_DWORD *)v17 = v270;
                      if ( dwBytes )
                      {
                        memcpy_0((void *)(v17 + 4), dwBytes, v270);
                        LODWORD(v18) = v241;
                      }
                      goto LABEL_92;
                    }
                    goto LABEL_105;
                  }
                }
              }
              v48 = v18 + v317;
              if ( (unsigned int)v18 + v317 < (unsigned int)v18 )
                goto LABEL_46;
              LODWORD(v18) = v18 + v317;
              v241 = v48;
LABEL_92:
              if ( v308 )
              {
                if ( !v297 )
                  goto LABEL_64;
              }
              else if ( v297 )
              {
                goto LABEL_64;
              }
              if ( v24 )
              {
                v17 = (unsigned __int64)v24;
                v52 = 0;
                while ( 1 )
                {
                  v53 = *(_DWORD *)v17 + 4;
                  if ( *(_DWORD *)v17 >= 0xFFFFFFFC || v17 + v53 < v17 )
                    goto LABEL_46;
                  v17 += v53;
                  if ( (unsigned int)++v52 >= 6 )
                  {
                    if ( v17 + 4 < v17 )
                      goto LABEL_46;
                    if ( v17 + v297 + 4LL <= (unsigned __int64)v24 + (unsigned int)v18 )
                    {
                      *(_DWORD *)v17 = v297;
                      if ( v308 )
                      {
                        memcpy_0((void *)(v17 + 4), v308, v297);
                        LODWORD(v18) = v241;
                      }
                      goto LABEL_108;
                    }
                    goto LABEL_105;
                  }
                }
              }
              v51 = v18 + v291;
              if ( (unsigned int)v18 + v291 < (unsigned int)v18 )
              {
LABEL_46:
                v12 = -1073741675;
                goto LABEL_47;
              }
              LODWORD(v18) = v18 + v291;
              v241 = v51;
LABEL_108:
              if ( v330 >= 0xFFFFFFFC )
                goto LABEL_396;
              v318 = v330 + 24;
              if ( v330 + 24 < 0x14 )
                goto LABEL_396;
              v54 = (void *)__rdtsc();
              v17 = (unsigned __int64)HIDWORD(v54) << 32;
              v251 = v54;
              LODWORD(v18) = v18 + 8;
              if ( (unsigned int)v18 < 8 || (v55 = (v18 + 7) & 0xFFFFFFF8, v309 = v55, v55 < (unsigned int)v18) )
              {
                v12 = -805306219;
                goto LABEL_50;
              }
              v323 = 0;
              v56 = (v18 + 7) & 0xFFFFFFF8;
              Srca = (char *)v55;
              v57 = GetProcessHeap();
              v58 = HeapAlloc(v57, 8u, v56);
              v59 = v58;
              if ( !v58 )
              {
                v12 = -805306345;
LABEL_361:
                if ( v12 < 0 )
                {
LABEL_50:
                  if ( v24 )
                  {
                    v41 = GetProcessHeap();
                    HeapFree(v41, 0, v24);
                  }
                  if ( lpMem )
                  {
                    v42 = GetProcessHeap();
                    HeapFree(v42, 0, lpMem);
                  }
LABEL_54:
                  if ( !v19 )
                    goto LABEL_400;
                  goto LABEL_399;
                }
                if ( v323 != 3 )
                {
LABEL_363:
                  v12 = -1073425151;
                  goto LABEL_50;
                }
                if ( !lpMem )
                {
                  v12 = -1073741811;
                  goto LABEL_50;
                }
                if ( lpMem + 1 >= lpMem )
                {
                  v230 = 0;
                  if ( *lpMem )
                    v230 = lpMem + 1;
                  if ( *lpMem != 4 )
                  {
LABEL_381:
                    v12 = -1073741789;
                    goto LABEL_50;
                  }
                  v12 = *v230;
                  if ( v12 == -805306333 )
                  {
                    v276 = -2147024774;
                  }
                  else
                  {
                    v276 = v12;
                    if ( v12 != -2147024774 && v12 < 0 )
                      goto LABEL_50;
                  }
                  v231 = lpMem;
                  v17 = 0;
                  while ( 1 )
                  {
                    v232 = v231 + 1;
                    if ( v231 + 1 < v231 )
                      break;
                    v231 = (int *)((char *)v232 + (unsigned int)*v231);
                    if ( v231 < v232 )
                      break;
                    v17 = (unsigned int)(v17 + 1);
                    if ( (_DWORD)v17 )
                    {
                      v17 = (unsigned __int64)(v231 + 1);
                      if ( v231 + 1 < v231 )
                        break;
                      v233 = 0;
                      if ( *v231 )
                        v233 = v231 + 1;
                      if ( *v231 != 8 )
                        goto LABEL_381;
                      if ( v23 != *v233 )
                        goto LABEL_363;
                      v234 = (unsigned int *)lpMem;
                      v17 = 0;
                      while ( 1 )
                      {
                        v235 = v234 + 1;
                        if ( v234 + 1 < v234 )
                          goto LABEL_396;
                        v234 = (unsigned int *)((char *)v235 + *v234);
                        if ( v234 < v235 )
                          goto LABEL_396;
                        v17 = (unsigned int)(v17 + 1);
                        if ( (unsigned int)v17 >= 2 )
                        {
                          if ( v234 + 1 < v234 )
                            goto LABEL_396;
                          v17 = 0;
                          if ( *v234 )
                            v17 = (unsigned __int64)(v234 + 1);
                          v12 = 0;
                          if ( *v234 )
                          {
                            if ( *v234 < v330 )
                            {
                              v12 = -2147024774;
                              goto LABEL_50;
                            }
                            memcpy_0(v336, (const void *)v17, *v234);
                          }
                          goto LABEL_48;
                        }
                      }
                    }
                  }
                }
LABEL_396:
                v12 = -1073741675;
                goto LABEL_50;
              }
              *v58 = 7;
              if ( v58 + 1 < v58 || (v58[1] = v241, v58 + 2 < v58 + 1) )
              {
                v99 = GetProcessHeap();
                HeapFree(v99, 0, v59);
                v12 = -805306219;
                goto LABEL_361;
              }
              *(_QWORD *)&Srca[(_QWORD)v58 - 8] = v251;
              memcpy_0(v58 + 2, v24, v241);
              v269 = 0;
              v281 = 0;
              v60 = 0;
              v246 = 0;
              v303 = 0;
              v301 = 0;
              v61 = v309;
              if ( !v309 || (dwBytesa = v309 + 8, v62 = (char *)MemoryAlloc(v309 + 8LL), (v277 = v62) == 0) )
              {
                v12 = -805306367;
                goto LABEL_338;
              }
              v63 = 0;
              for ( i = 0; i < v309; ++i )
                v63 ^= *((_BYTE *)v59 + i);
              v326 = v19;
              v328 = v20;
              v327 = v24;
              if ( (unsigned __int64)v309 >> 3 )
              {
                Srcb = 0;
                v271 = 0;
                Sizea = 0;
                v65 = (unsigned __int8 *)v59;
                v66 = v62;
                v67 = 0;
                v68 = -1;
                v329 = v59;
                do
                {
                  v69 = v65[3] | ((v65[2] | (((*v65 << 8) | v65[1]) << 8)) << 8);
                  v70 = v65[7] | ((v65[6] | ((v65[5] | (v65[4] << 8)) << 8)) << 8);
                  v65 += 8;
                  v71 = v67 ^ v69 ^ ((v68 ^ v70) - 19032);
                  v72 = v71 ^ 0xC81ECB17;
                  v73 = v68 ^ v70 ^ (__ROR4__(v71 ^ 0xC81ECB17, 7) + 45493 * __ROR4__(v71, 15));
                  v74 = v72 ^ (51991 * __ROR4__(v73 - 1313519016, 9) - __ROR4__(v73, 10));
                  v75 = v73 ^ (__ROR4__(v74, 27) + 51230 * __ROR4__(v74 ^ 0xCB17, 28));
                  v76 = v74 ^ (-937506025 - (v75 ^ 0xB1B54A58));
                  v77 = v75 ^ (45493 * (v76 - 19032) - (v76 >> 6));
                  v78 = v76 ^ (19032 * (__ROR4__(v77, 15) ^ 0xCB17));
                  v79 = v77 ^ (51991 * (__ROR4__(~v78, 3) + 51230));
                  v80 = v79 ^ (45493 * (v78 ^ (v79 + 937486993) ^ 0xC81E)) ^ __ROR4__(v78 ^ (v79 + 937486993), 10);
                  v81 = v78 ^ (v79 + 937486993) ^ __ROR4__(v80, 3) ^ (51991 * __ROR4__(v80 ^ 0x4A58, 26));
                  v82 = v80 ^ (19032 * (__ROR4__(v81, 15) - 51230));
                  v83 = v81
                      ^ ((v82 ^ (v82 >> 14)) >> 1)
                      ^ (19032 * (v82 ^ 0xC81E))
                      ^ (19032 * (((v82 - 51991) >> 29) | (8 * (v82 - 51991))));
                  v84 = v82 ^ (45493 * (v83 - 51991) - (v83 >> 13));
                  v85 = v83 ^ __ROR4__(v84, 11) ^ (51991 * __ROR4__(-1313519016 - v84, 9));
                  v86 = v84 ^ (v85 - 51230 + 1313519016);
                  v87 = v85 ^ (19032 * (v86 ^ 0xB1B5) - __ROR4__(v86, 7));
                  v88 = v86 ^ (45493 * __ROR4__(v87 ^ 0xC81E, 28) - __ROR4__(v87, 16));
                  v89 = v87 ^ (__ROR4__(v88, 4) + 51991 * __ROR4__(-1313519016 - v88, 10));
                  v90 = v88 ^ __ROR4__(v89, 9) ^ (51230 * __ROR4__(v89 + 1313519016, 4));
                  v91 = v89 ^ (19032 * __ROR4__(v90 ^ 0xC81ECB17, 24) - __ROR4__(v90, 30));
                  v92 = v90 ^ (45493 * __ROR4__(-937506025 - v91, 11) - __ROR4__(v91, 12));
                  v93 = v91 ^ (v92 >> 8) ^ (51991 * (v92 ^ 0xB1B5));
                  v67 = v271 ^ v93;
                  v68 = v92 ^ Sizea ^ v93 ^ 0xC81ECB17 ^ 0xB1B54A58;
                  v66[3] = v67;
                  v66[7] = v68;
                  v66[2] = __ROR4__(v67, 8);
                  v66[6] = __ROR4__(v68, 8);
                  v66[1] = __ROR4__(v67, 16);
                  v66[5] = __ROR4__(v68, 16);
                  *v66 = __ROR4__(v67, 24);
                  v66[4] = __ROR4__(v68, 24);
                  v271 = v69;
                  Sizea = v70;
                  v66 += 8;
                  ++Srcb;
                }
                while ( (unsigned __int64)Srcb < (unsigned __int64)v309 >> 3 );
                v19 = v326;
                v24 = v327;
                v20 = v328;
                v59 = v329;
                v60 = 0;
                v61 = v309;
                v62 = v277;
              }
              *(_QWORD *)&v62[v61] = v63;
              v94 = GetProcessHeap();
              v95 = HeapAlloc(v94, 8u, 0x30u);
              v248 = v95;
              if ( v95 )
              {
                *v95 = dwBytesa;
                v100 = GetProcessHeap();
                v101 = HeapAlloc(v100, 8u, dwBytesa);
                v96 = -1073741801;
                v102 = v248;
                if ( v101 )
                {
                  v248[1] = v101;
                  memcpy_0(v101, v277, dwBytesa);
                  *((_DWORD *)v248 + 4) = 160;
                  v103 = GetProcessHeap();
                  v104 = HeapAlloc(v103, 8u, 0xA0u);
                  v102 = v248;
                  if ( v104 )
                  {
                    v248[3] = v104;
                    *v104 = xmmword_18004D310;
                    v104[1] = xmmword_18004D320;
                    v104[2] = xmmword_18004D330;
                    v104[3] = xmmword_18004D340;
                    v104[4] = xmmword_18004D350;
                    v104[5] = xmmword_18004D360;
                    v104[6] = xmmword_18004D370;
                    v104[7] = xmmword_18004D380;
                    v104[8] = xmmword_18004D390;
                    v104[9] = xmmword_18004D3A0;
                    *((_DWORD *)v248 + 8) = 8;
                    v105 = GetProcessHeap();
                    v106 = HeapAlloc(v105, 8u, 8u);
                    if ( v106 )
                    {
                      v248[5] = v106;
                      *v106 = qword_18004D3B0;
                      v97 = (unsigned int *)v248;
                      v242 = 0;
                      goto LABEL_127;
                    }
                    v102 = v248;
                  }
                  v248 = v102;
                }
                v242 = -1073741801;
                v252 = (void *)v102[1];
                if ( v252 )
                {
                  v107 = GetProcessHeap();
                  HeapFree(v107, 0, v252);
                  v102 = v248;
                  v248[1] = 0;
                }
                v253 = (void *)v102[3];
                if ( v253 )
                {
                  v108 = GetProcessHeap();
                  HeapFree(v108, 0, v253);
                  v102 = v248;
                  v248[3] = 0;
                }
                v254 = (void *)v102[5];
                if ( v254 )
                {
                  v109 = GetProcessHeap();
                  HeapFree(v109, 0, v254);
                  v248[5] = 0;
                }
                v110 = GetProcessHeap();
                HeapFree(v110, 0, v248);
              }
              else
              {
                v96 = -1073741801;
                v242 = -1073741801;
              }
              v97 = 0;
LABEL_127:
              v269 = v97;
              v98 = GetProcessHeap();
              HeapFree(v98, 0, v277);
              v111 = v242 | 0x10000000;
              if ( v242 < 0 )
              {
LABEL_332:
                v12 = v111;
                goto LABEL_333;
              }
              if ( *v269 < 0xFFFFFFFC )
              {
                v112 = *v269 + 8;
                if ( v112 >= *v269 + 4 )
                {
                  Srcc = v269 + 4;
                  v17 = v112 + v269[4];
                  if ( (unsigned int)v17 >= v112 )
                  {
                    v113 = v17 + 4;
                    if ( (int)v17 + 4 >= (unsigned int)v17 )
                    {
                      v292 = v113 + v269[8];
                      if ( v292 >= v113 )
                      {
                        v114 = v113 + v269[8];
                        v115 = GetProcessHeap();
                        v116 = (char *)HeapAlloc(v115, 8u, v114);
                        v249 = v116;
                        if ( !v116 )
                        {
                          v12 = -805306345;
LABEL_330:
                          v60 = v246;
                          goto LABEL_333;
                        }
                        *(_DWORD *)v116 = *v269;
                        v255 = v116 + 4;
                        if ( v116 + 4 < v116 )
                        {
                          v249 = v116;
                        }
                        else
                        {
                          memcpy_0(v116 + 4, *((const void **)v269 + 1), *v269);
                          v117 = &v255[*v269];
                          if ( v117 >= v255 )
                          {
                            *(_DWORD *)v117 = *Srcc;
                            v256 = v117 + 4;
                            if ( v117 + 4 >= v117 )
                            {
                              memcpy_0(v117 + 4, *((const void **)v269 + 3), (unsigned int)*Srcc);
                              v118 = &v256[*Srcc];
                              if ( v118 >= v256 )
                              {
                                *(_DWORD *)v118 = v269[8];
                                v257 = v118 + 4;
                                if ( v118 + 4 >= v118 )
                                {
                                  memcpy_0(v118 + 4, *((const void **)v269 + 5), v269[8]);
                                  if ( &v257[v269[8]] >= v257 )
                                  {
                                    v17 = (unsigned __int64)v249;
                                    v281 = v249;
                                    v119 = v292;
                                    v243 = v292;
                                    v120 = 0;
                                    v278 = 0;
                                    v121 = -1;
                                    if ( v318 < 0xFFFFFFF8 )
                                      v121 = v318 + 8;
                                    LODWORD(v18) = v318 >= 0xFFFFFFF8 ? -805306219 : 0x10000000;
                                    if ( v318 + 8 >= 8 )
                                    {
                                      v122 = (v121 + 7) & 0xFFFFFFF8;
                                      if ( v122 < v121 || (v293 = v122 + 8, v122 + 8 < v122) )
                                      {
LABEL_190:
                                        LODWORD(v18) = -1073741675;
                                        goto LABEL_187;
                                      }
                                      v243 = v119;
                                      v281 = v249;
                                      if ( v24 )
                                      {
                                        v281 = v249;
                                        v243 = v119;
                                        v123 = (char *)v24;
                                        v272 = 0;
                                        while ( 1 )
                                        {
                                          Srcd = v123 + 4;
                                          if ( v123 + 4 < v123 )
                                            break;
                                          v124 = *(unsigned int *)v123;
                                          v123 = &Srcd[v124];
                                          if ( &Srcd[v124] < Srcd )
                                            break;
                                          if ( ++v272 )
                                          {
                                            if ( v123 + 4 >= v123 )
                                            {
                                              v128 = (char *)v24;
                                              v273 = 0;
                                              while ( 1 )
                                              {
                                                Srce = v128 + 4;
                                                if ( v128 + 4 < v128 )
                                                  break;
                                                v129 = *(unsigned int *)v128;
                                                v128 = &Srce[v129];
                                                if ( &Srce[v129] < Srce )
                                                  break;
                                                if ( (unsigned int)++v273 >= 2 )
                                                {
                                                  if ( v128 + 4 < v128 )
                                                    goto LABEL_189;
                                                  if ( v293 >= 0xFFFFFFFC )
                                                    goto LABEL_190;
                                                  if ( v293 + 8 < v293 + 4 )
                                                    goto LABEL_190;
                                                  v130 = *(_DWORD *)v123 + v293 + 8;
                                                  if ( v130 < v293 + 8 )
                                                    goto LABEL_190;
                                                  v131 = v130 + 4;
                                                  if ( v130 + 4 < v130 )
                                                    goto LABEL_190;
                                                  v120 = v131 + *(_DWORD *)v128;
                                                  v278 = v120;
                                                  if ( v120 < v131 )
                                                    goto LABEL_190;
                                                  v281 = v249;
                                                  if ( v120 > 0x400000 )
                                                  {
                                                    LODWORD(v18) = -2147418113;
                                                    goto LABEL_187;
                                                  }
                                                  v243 = v119;
                                                  goto LABEL_170;
                                                }
                                              }
                                            }
                                            break;
                                          }
                                        }
LABEL_189:
                                        LODWORD(v18) = -1073741675;
                                      }
                                      else
                                      {
                                        LODWORD(v18) = -1073741811;
                                      }
                                    }
                                    if ( (v18 & 0x80000000) == 0LL )
                                    {
LABEL_170:
                                      v125 = v120;
                                      v126 = GetProcessHeap();
                                      v60 = (unsigned int *)HeapAlloc(v126, 8u, v125);
                                      if ( !v60 )
                                      {
LABEL_171:
                                        v12 = -805306345;
                                        goto LABEL_333;
                                      }
                                      v333 = 0;
                                      v334 = 0;
                                      phModule = 0;
                                      if ( !v281 )
                                      {
                                        v12 = -2147024809;
                                        goto LABEL_333;
                                      }
                                      *(_QWORD *)&v333 = v281;
                                      LODWORD(v334) = v243;
                                      *((_QWORD *)&v333 + 1) = v60;
                                      *(_QWORD *)((char *)&v334 + 4) = v278;
                                      if ( GetModuleHandleExW(1u, L"ntdll.dll", &phModule)
                                        && (ProcAddress = GetProcAddress(phModule, "NtQuerySystemInformation")) != 0 )
                                      {
                                        LastError = ((__int64 (__fastcall *)(__int64, __int128 *))ProcAddress)(
                                                      134,
                                                      &v333)
                                                  | 0x10000000;
                                        if ( LastError >= 0 )
                                        {
                                          v17 = DWORD1(v334);
                                          goto LABEL_205;
                                        }
                                      }
                                      else
                                      {
                                        LastError = GetLastError();
                                        v133 = LastError < 0;
                                        if ( LastError > 0 )
                                        {
                                          LastError = (unsigned __int16)LastError | 0x80070000;
                                          v133 = LastError < 0;
                                        }
                                        if ( !v133 )
                                        {
                                          v12 = -2147467259;
                                          goto LABEL_333;
                                        }
                                      }
                                      if ( LastError == -805306333 )
                                      {
                                        v12 = -2147024774;
                                        goto LABEL_333;
                                      }
                                      if ( LastError < 0 )
                                      {
                                        v12 = LastError;
                                        goto LABEL_333;
                                      }
                                      v17 = v278;
LABEL_205:
                                      if ( (unsigned int)v17 < 4 )
                                      {
LABEL_206:
                                        v12 = -805306306;
                                        goto LABEL_333;
                                      }
                                      v135 = *v60;
                                      v294 = *v60;
                                      v18 = (unsigned __int64)(v60 + 1);
                                      if ( v60 + 1 >= v60 )
                                      {
                                        if ( (int)v17 - 4 < (unsigned int)v135 )
                                          goto LABEL_206;
                                        Srcf = *v60;
                                        v136 = (unsigned int *)(v135 + v18);
                                        v310 = (char *)(v135 + v18);
                                        if ( v135 + v18 >= v18 && (unsigned int)v135 < 0xFFFFFFFC )
                                        {
                                          if ( (unsigned int)(v17 - (v135 + 4)) < 4 )
                                            goto LABEL_206;
                                          v137 = *v136;
                                          v319 = *v136;
                                          v18 = (unsigned __int64)(v136 + 1);
                                          if ( v136 + 1 >= v136 )
                                          {
                                            v138 = v135 + 8;
                                            if ( (int)v135 + 8 >= (unsigned int)(v135 + 4) )
                                            {
                                              if ( (unsigned int)v17 - v138 < (unsigned int)v137 )
                                                goto LABEL_206;
                                              dwBytesb = v137;
                                              v139 = v137 + v18;
                                              v258 = (unsigned int *)(v137 + v18);
                                              if ( v137 + v18 >= v18 )
                                              {
                                                LODWORD(v18) = v138 + v137;
                                                if ( v138 + (unsigned int)v137 >= v138 )
                                                {
                                                  if ( (unsigned int)(v17 - v18) < 4 )
                                                    goto LABEL_206;
                                                  v247 = (void *)(v139 + 4);
                                                  if ( v139 + 4 >= v139 )
                                                  {
                                                    v140 = v18 + 4;
                                                    if ( (int)v18 + 4 >= (unsigned int)v18 )
                                                    {
                                                      LODWORD(v18) = *v258;
                                                      v274 = *v258;
                                                      if ( (unsigned int)v17 - v140 < *v258 )
                                                        goto LABEL_206;
                                                      if ( v140 + (unsigned int)v18 >= v140 )
                                                      {
                                                        if ( (_DWORD)v17 != v140 + (_DWORD)v18
                                                          || (unsigned int)(v18 + v137 + v135) + 12LL != (unsigned int)v17 )
                                                        {
                                                          goto LABEL_206;
                                                        }
                                                        v141 = GetProcessHeap();
                                                        v142 = HeapAlloc(v141, 8u, 0x30u);
                                                        v279 = v142;
                                                        if ( !v142 )
                                                          goto LABEL_171;
                                                        v326 = v19;
                                                        v328 = v20;
                                                        v306 = v23;
                                                        v327 = v24;
                                                        v329 = v59;
                                                        v250 = 0;
                                                        if ( v60 == (unsigned int *)-4LL )
                                                        {
                                                          *(_DWORD *)v142 = 0;
                                                          v142[1] = 0;
                                                          v244 = 0;
                                                        }
                                                        else
                                                        {
                                                          *(_DWORD *)v142 = v294;
                                                          v143 = GetProcessHeap();
                                                          v144 = HeapAlloc(v143, 8u, Srcf);
                                                          if ( !v144 )
                                                          {
LABEL_236:
                                                            v244 = -1073741801;
                                                            v246 = v60;
                                                            v149 = v279;
                                                            v259 = (void *)v279[1];
                                                            if ( v259 )
                                                            {
                                                              v150 = GetProcessHeap();
                                                              HeapFree(v150, 0, v259);
                                                              v149 = v279;
                                                              v279[1] = 0;
                                                            }
                                                            v260 = (void *)v149[3];
                                                            if ( v260 )
                                                            {
                                                              v151 = GetProcessHeap();
                                                              HeapFree(v151, 0, v260);
                                                              v149 = v279;
                                                              v279[3] = 0;
                                                            }
                                                            v261 = (void *)v149[5];
                                                            if ( v261 )
                                                            {
                                                              v152 = GetProcessHeap();
                                                              HeapFree(v152, 0, v261);
                                                              v279[5] = 0;
                                                            }
                                                            v153 = GetProcessHeap();
                                                            HeapFree(v153, 0, v279);
                                                            v17 = 0;
                                                            goto LABEL_246;
                                                          }
                                                          v279[1] = v144;
                                                          v244 = 0;
                                                          memcpy_0(v144, v60 + 1, Srcf);
                                                          v142 = v279;
                                                        }
                                                        if ( v310 == (char *)-4LL )
                                                        {
                                                          *((_DWORD *)v142 + 4) = 0;
                                                          v142[3] = 0;
                                                        }
                                                        else
                                                        {
                                                          *((_DWORD *)v142 + 4) = v319;
                                                          v145 = GetProcessHeap();
                                                          v146 = HeapAlloc(v145, 8u, dwBytesb);
                                                          if ( !v146 )
                                                          {
LABEL_235:
                                                            v326 = v19;
                                                            v328 = v20;
                                                            v306 = v23;
                                                            v327 = v24;
                                                            v329 = v59;
                                                            goto LABEL_236;
                                                          }
                                                          v279[3] = v146;
                                                          v244 = 0;
                                                          memcpy_0(v146, v310 + 4, dwBytesb);
                                                          v142 = v279;
                                                        }
                                                        if ( v247 )
                                                        {
                                                          *((_DWORD *)v142 + 8) = v274;
                                                          v147 = GetProcessHeap();
                                                          v148 = HeapAlloc(v147, 8u, v274);
                                                          if ( !v148 )
                                                            goto LABEL_235;
                                                          v279[5] = v148;
                                                          v244 = 0;
                                                          memcpy_0(v148, v247, v274);
                                                          v142 = v279;
                                                        }
                                                        else
                                                        {
                                                          *((_DWORD *)v142 + 8) = 0;
                                                          v142[5] = 0;
                                                        }
                                                        v17 = (unsigned __int64)v142;
                                                        v250 = v142;
                                                        v246 = v60;
                                                        v329 = v59;
                                                        v327 = v24;
                                                        v306 = v23;
                                                        v328 = v20;
                                                        v326 = v19;
LABEL_246:
                                                        v154 = v244;
                                                        if ( v244 < 0 )
                                                        {
                                                          if ( v17 )
                                                          {
                                                            v262 = *(void **)(v17 + 8);
                                                            if ( v262 )
                                                            {
                                                              v156 = GetProcessHeap();
                                                              HeapFree(v156, 0, v262);
                                                              v17 = (unsigned __int64)v250;
                                                              v250[1] = 0;
                                                            }
                                                            v263 = *(void **)(v17 + 24);
                                                            if ( v263 )
                                                            {
                                                              v157 = GetProcessHeap();
                                                              HeapFree(v157, 0, v263);
                                                              v17 = (unsigned __int64)v250;
                                                              v250[3] = 0;
                                                            }
                                                            v264 = *(void **)(v17 + 40);
                                                            if ( v264 )
                                                            {
                                                              v158 = GetProcessHeap();
                                                              HeapFree(v158, 0, v264);
                                                              v250[5] = 0;
                                                            }
                                                            v159 = GetProcessHeap();
                                                            HeapFree(v159, 0, v250);
                                                            v154 = v244;
                                                          }
                                                          v155 = 0;
                                                        }
                                                        else
                                                        {
                                                          v155 = (unsigned int *)v17;
                                                          v303 = (_QWORD *)v17;
                                                        }
                                                        v111 = v154 | 0x10000000;
                                                        if ( v111 >= 0 )
                                                        {
                                                          if ( !v155
                                                            || (v265 = (unsigned __int8 *)*((_QWORD *)v155 + 1)) == 0
                                                            || !*v155 )
                                                          {
                                                            v12 = -805306355;
                                                            goto LABEL_330;
                                                          }
                                                          v302 = *v155 - 8LL;
                                                          v160 = MemoryAlloc(v302);
                                                          v161 = v160;
                                                          v311 = v160;
                                                          if ( !v160 )
                                                          {
LABEL_289:
                                                            v301 = 0;
                                                            v12 = -805306367;
                                                            goto LABEL_330;
                                                          }
                                                          v162 = 0;
                                                          dwBytesc = (SIZE_T)v265;
                                                          Srcg = v160;
                                                          v163 = v302;
                                                          v320 = v302 & 7;
                                                          if ( (v302 & 7) != 0 )
                                                          {
                                                            v164 = v265;
                                                            v165 = 0;
                                                            v166 = 0;
                                                            v167 = 0;
                                                            do
                                                            {
                                                              v245 = *v164++;
                                                              v275 = 8 * v165;
                                                              if ( v165 >= 4 )
                                                                v167 |= v245 << (56 - v275);
                                                              else
                                                                v166 |= v245 << (24 - v275);
                                                              ++v165;
                                                            }
                                                            while ( (int)v165 < (int)v320 );
                                                            v299 = v167;
                                                            v280 = v166;
                                                            dwBytesc = (SIZE_T)v164;
                                                            v246 = v60;
                                                            v329 = v59;
                                                            v327 = v24;
                                                            v306 = v23;
                                                            v328 = v20;
                                                            v326 = v19;
                                                            v162 = 0;
                                                            v161 = v160;
                                                            v163 = v302;
                                                            v168 = v280 ^ 0x92F65A5;
                                                            v169 = v299 ^ 0x699A899C;
                                                            if ( (v302 & 7) != 0 )
                                                            {
                                                              v170 = v280 ^ 0x92F65A5;
                                                              v171 = v160;
                                                              v172 = 0;
                                                              do
                                                              {
                                                                Srcg = v171 + 1;
                                                                if ( v172 >= 4 )
                                                                {
                                                                  v169 = __ROR4__(v169, 24);
                                                                  v173 = v169;
                                                                }
                                                                else
                                                                {
                                                                  v170 = __ROR4__(v170, 24);
                                                                  v173 = v170;
                                                                }
                                                                *v171 = v173;
                                                                ++v172;
                                                                ++v171;
                                                              }
                                                              while ( (int)v172 < (int)v320 );
                                                              v60 = v246;
                                                              v161 = v160;
                                                              v163 = v302;
                                                            }
                                                            if ( v320 <= 4 )
                                                            {
                                                              v298 = 0;
                                                              if ( v320 < 4 )
                                                                v168 = v168 >> (8 * (4 - v320)) << (8 * (4 - v320));
                                                            }
                                                            else
                                                            {
                                                              v298 = (v299 ^ 0x699A899Cu) >> (8 * (8 - v320)) << (8 * (8 - v320));
                                                            }
                                                          }
                                                          else
                                                          {
                                                            v280 = 0;
                                                            v298 = 0;
                                                            v168 = 0;
                                                          }
                                                          v321 = v163 >> 3;
                                                          if ( v163 >> 3 )
                                                          {
                                                            v295 = 0;
                                                            v174 = v298;
                                                            v175 = (unsigned __int8 *)dwBytesc;
                                                            v176 = Srcg;
                                                            v177 = v280;
                                                            v178 = v299;
                                                            do
                                                            {
                                                              v179 = v175[3]
                                                                   | ((v175[2] | (((*v175 << 8) | v175[1]) << 8)) << 8);
                                                              v180 = v175[7]
                                                                   | ((v175[6] | ((v175[5] | (v175[4] << 8)) << 8)) << 8);
                                                              v175 += 8;
                                                              v181 = v168 ^ v179;
                                                              v182 = v174 ^ v180 ^ v168 ^ v179 ^ 0x7F1137F ^ 0xAB69605E;
                                                              v183 = v181
                                                                   ^ (__ROR4__(v182, 22)
                                                                    + 4991 * __ROR4__(v182 + 1419157410, 27));
                                                              v184 = v182
                                                                   ^ (43881 * __ROR4__(v183 + 133239679, 9)
                                                                    - __ROR4__(v183, 30));
                                                              v185 = v183 ^ (24670 * (v184 - 4991) - (v184 >> 13));
                                                              v186 = v184
                                                                   ^ (2033 * __ROR4__(v185 ^ 0xAB69, 26)
                                                                    - __ROR4__(v185, 30));
                                                              v187 = v185 ^ (133239679 - (v186 ^ 0xAB69605E));
                                                              v188 = v186
                                                                   ^ (43881 * (v187 ^ 0x137F))
                                                                   ^ __ROR4__(v187, 6);
                                                              v189 = v187
                                                                   ^ (__ROR4__(v188, 30)
                                                                    + 24670 * __ROR4__(v188 + 133239679, 15));
                                                              v190 = v188
                                                                   ^ (2033 * __ROR4__(v189 + 1419157410, 14)
                                                                    - __ROR4__(v189, 24));
                                                              v191 = v189
                                                                   ^ __ROR4__(v190, 10)
                                                                   ^ (4991 * __ROR4__(v190 ^ 0xAB69605E, 12));
                                                              v192 = v191
                                                                   ^ (2033
                                                                    * (__ROR4__(
                                                                         ~(v190 ^ (v191 >> 10)
                                                                                ^ (43881 * (v191 ^ 0x7F1))),
                                                                         5)
                                                                     + 24670));
                                                              v193 = v190
                                                                   ^ (v191 >> 10)
                                                                   ^ (43881 * (v191 ^ 0x7F1))
                                                                   ^ (v192 - 2033)
                                                                   ^ 0xAB69605E;
                                                              v194 = v192
                                                                   ^ ((v193 >> 2) + 4991 * __ROR4__(v193 ^ 0x7F1, 30));
                                                              v195 = v193
                                                                   ^ (__ROR4__(v194, 25)
                                                                    + 43881 * __ROR4__(v194 - 133239679, 6));
                                                              v196 = v194
                                                                   ^ (24670 * (v195 ^ 0x137F) + __ROR4__(v195, 9));
                                                              v197 = v195
                                                                   ^ (__ROR4__(v196, 25)
                                                                    + 2033 * __ROR4__(v196 ^ 0xAB69, 27));
                                                              v198 = v196 ^ v197 ^ 0xAC987321;
                                                              v199 = v197 ^ (4991 * (__ROR4__(v198, 3) - 43881));
                                                              v200 = v198
                                                                   ^ (24670 * __ROR4__(v199 - 133239679, 1)
                                                                    - __ROR4__(v199, 6));
                                                              v201 = v199
                                                                   ^ (__ROR4__(v200, 18)
                                                                    + 2033 * __ROR4__(v200 - 1419157410, 29));
                                                              v202 = v200
                                                                   ^ (4991 * __ROR4__(v201 - 1419157410, 17)
                                                                    - __ROR4__(v201, 14));
                                                              v203 = v201 ^ (v202 >> 3) ^ (43881 * (v202 ^ 0x605E));
                                                              v168 = v202
                                                                   ^ v177
                                                                   ^ __ROR4__(v203, 30)
                                                                   ^ (24670 * __ROR4__(v203 ^ 0x7F1137F, 28));
                                                              v174 = v203 ^ v178;
                                                              v176[3] = v168;
                                                              v176[7] = v203 ^ v178;
                                                              v176[2] = __ROR4__(v168, 8);
                                                              v176[6] = __ROR4__(v203 ^ v178, 8);
                                                              v176[1] = __ROR4__(v168, 16);
                                                              v176[5] = __ROR4__(v203 ^ v178, 16);
                                                              *v176 = __ROR4__(v168, 24);
                                                              v176[4] = __ROR4__(v203 ^ v178, 24);
                                                              v177 = v179;
                                                              v178 = v180;
                                                              v176 += 8;
                                                              ++v295;
                                                            }
                                                            while ( (unsigned __int64)v295 < v321 );
                                                            v162 = 0;
                                                            v96 = -1073741801;
                                                            v19 = v326;
                                                            v24 = v327;
                                                            v20 = v328;
                                                            v59 = v329;
                                                            v23 = v306;
                                                            v60 = v246;
                                                            v161 = v160;
                                                            v163 = v302;
                                                          }
                                                          for ( j = 0; j < v163; ++j )
                                                            v162 ^= *((_BYTE *)v161 + j);
                                                          if ( v162 != *(_QWORD *)&v265[v163] )
                                                          {
                                                            MemoryFree(v161);
                                                            goto LABEL_289;
                                                          }
                                                          v205 = v269;
                                                          v17 = (unsigned __int64)v281;
                                                          v246 = v60;
                                                          LODWORD(v18) = (_DWORD)v303;
                                                          if ( (unsigned int)v163 < 4 )
                                                          {
                                                            v96 = -1073741762;
                                                            v301 = (__int64)v161;
LABEL_329:
                                                            v12 = v96 | 0x10000000;
                                                            goto LABEL_330;
                                                          }
                                                          v206 = v161;
                                                          v301 = (__int64)v161;
                                                          if ( v161 + 1 < v161 )
                                                            goto LABEL_326;
                                                          if ( (unsigned int)(v163 - 4) < 4 )
                                                          {
LABEL_294:
                                                            v96 = -1073741762;
                                                            v301 = (__int64)v161;
LABEL_328:
                                                            v269 = v205;
                                                            v281 = (void *)v17;
                                                            v246 = v60;
                                                            goto LABEL_329;
                                                          }
                                                          Srch = (char *)(v161 + 2);
                                                          v205 = v269;
                                                          if ( v161 + 2 < v161 + 1 )
                                                            goto LABEL_326;
                                                          if ( (unsigned int)(v163 - 8) < v161[1] )
                                                            goto LABEL_294;
                                                          if ( v161[1] >= 0xFFFFFFF8 )
                                                          {
LABEL_326:
                                                            v96 = -1073741675;
                                                          }
                                                          else
                                                          {
                                                            v307 = (unsigned int)v161[1];
                                                            dwBytesd = (unsigned int)v163;
                                                            v205 = v269;
                                                            v17 = (unsigned __int64)v281;
                                                            if ( (char *)v161 + (unsigned int)v163 >= (char *)v161 + v307 + 8 )
                                                            {
                                                              v207 = (char *)(v161 + 2);
                                                              if ( dwBytesd - v307 - 8 < 8 )
                                                              {
                                                                v300 = 0;
                                                                if ( v161 == (_DWORD *)-8LL )
                                                                {
                                                                  v301 = -8;
                                                                  v246 = v60;
                                                                }
                                                                else
                                                                {
                                                                  v208 = (unsigned __int64)v161 + v307 + 8;
                                                                  v161 = v311;
                                                                  if ( v208 < (unsigned __int64)Srch )
                                                                  {
                                                                    v96 = -1073741675;
                                                                    v301 = (__int64)v206;
                                                                    goto LABEL_329;
                                                                  }
                                                                  v209 = Srch;
                                                                  if ( v208 > (unsigned __int64)Srch )
                                                                  {
                                                                    v17 = (unsigned __int64)(v311 + 1);
                                                                    LODWORD(v18) = v307;
                                                                    v210 = 0;
                                                                    while ( v209 + 4 >= v209 )
                                                                    {
                                                                      if ( (unsigned __int64)(v209 + 4) > v208 )
                                                                        goto LABEL_314;
                                                                      if ( *(_DWORD *)v209 >= 0xFFFFFFFC )
                                                                        break;
                                                                      v211 = &v209[*(_DWORD *)v209 + 4];
                                                                      if ( v211 < v209 )
                                                                        break;
                                                                      v208 = v17 + v307 + 4;
                                                                      if ( (unsigned __int64)v211 > v208 )
                                                                        goto LABEL_314;
                                                                      v209 += (unsigned int)(*(_DWORD *)v209 + 4);
                                                                      v300 = ++v210;
                                                                      if ( (unsigned __int64)v211 >= v208 )
                                                                        goto LABEL_313;
                                                                    }
                                                                    v96 = -1073741675;
                                                                    goto LABEL_329;
                                                                  }
                                                                  v301 = (__int64)v311;
LABEL_313:
                                                                  if ( v209 != (char *)v208 )
                                                                  {
LABEL_314:
                                                                    v96 = -1073741811;
                                                                    goto LABEL_329;
                                                                  }
                                                                }
                                                                v296 = *v161;
                                                                if ( v161[1] )
                                                                {
                                                                  v212 = GetProcessHeap();
                                                                  v213 = v307;
                                                                  v214 = (int *)HeapAlloc(v212, 8u, v307);
                                                                  if ( !v214 )
                                                                    goto LABEL_329;
                                                                  v207 = Srch;
                                                                }
                                                                else
                                                                {
                                                                  v214 = 0;
                                                                  v213 = v307;
                                                                }
                                                                v96 = 0;
                                                                lpMem = v214;
                                                                if ( v207 )
                                                                  memcpy_0(v214, v207, v213);
                                                                v323 = v300;
                                                                if ( v296 != v300 )
                                                                  v96 = -1073741762;
                                                                goto LABEL_329;
                                                              }
                                                            }
                                                            v96 = -1073741762;
                                                          }
                                                          v301 = (__int64)v161;
                                                          goto LABEL_328;
                                                        }
                                                        v60 = v246;
                                                        goto LABEL_332;
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                      v12 = -805306219;
LABEL_333:
                                      if ( !v59 )
                                      {
LABEL_339:
                                        if ( v269 )
                                        {
                                          v266 = (void *)*((_QWORD *)v269 + 1);
                                          if ( v266 )
                                          {
                                            v216 = GetProcessHeap();
                                            HeapFree(v216, 0, v266);
                                            *((_QWORD *)v269 + 1) = 0;
                                          }
                                          v267 = (void *)*((_QWORD *)v269 + 3);
                                          if ( v267 )
                                          {
                                            v217 = GetProcessHeap();
                                            HeapFree(v217, 0, v267);
                                            *((_QWORD *)v269 + 3) = 0;
                                          }
                                          v268 = (void *)*((_QWORD *)v269 + 5);
                                          if ( v268 )
                                          {
                                            v218 = GetProcessHeap();
                                            HeapFree(v218, 0, v268);
                                            *((_QWORD *)v269 + 5) = 0;
                                          }
                                          v219 = GetProcessHeap();
                                          HeapFree(v219, 0, v269);
                                        }
                                        if ( v281 )
                                        {
                                          v220 = GetProcessHeap();
                                          HeapFree(v220, 0, v281);
                                        }
                                        if ( v60 )
                                        {
                                          v221 = GetProcessHeap();
                                          HeapFree(v221, 0, v60);
                                        }
                                        if ( v303 )
                                        {
                                          v222 = (void *)v303[1];
                                          if ( v222 )
                                          {
                                            v223 = GetProcessHeap();
                                            HeapFree(v223, 0, v222);
                                            v303[1] = 0;
                                          }
                                          v224 = (void *)v303[3];
                                          if ( v224 )
                                          {
                                            v225 = GetProcessHeap();
                                            HeapFree(v225, 0, v224);
                                            v303[3] = 0;
                                          }
                                          v226 = (void *)v303[5];
                                          if ( v226 )
                                          {
                                            v227 = GetProcessHeap();
                                            HeapFree(v227, 0, v226);
                                            v303[5] = 0;
                                          }
                                          v228 = GetProcessHeap();
                                          HeapFree(v228, 0, v303);
                                        }
                                        if ( v301 )
                                        {
                                          v229 = GetProcessHeap();
                                          HeapFree(v229, 0, (LPVOID)v301);
                                        }
                                        goto LABEL_361;
                                      }
LABEL_338:
                                      v215 = GetProcessHeap();
                                      HeapFree(v215, 0, v59);
                                      goto LABEL_339;
                                    }
LABEL_187:
                                    v12 = v18;
                                    goto LABEL_330;
                                  }
                                }
                              }
                            }
                          }
                        }
                        v127 = GetProcessHeap();
                        HeapFree(v127, 0, v249);
                      }
                    }
                  }
                }
              }
              v12 = -805306219;
              goto LABEL_330;
            }
          }
LABEL_105:
          v12 = -1073741789;
        }
LABEL_47:
        if ( v12 >= 0 )
        {
LABEL_48:
          if ( v276 )
            v12 = v276;
        }
        goto LABEL_50;
      }
    }
    v12 = -1073741675;
    goto LABEL_399;
  }
  v12 = -2147024809;
  v325 = -2147024809;
LABEL_406:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v337, v10, v11);
  std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v331);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002bf00  mov     [rsp-8+arg_0], rbx
0x18002bf05  push    rbp
0x18002bf06  push    rsi
0x18002bf07  push    rdi
0x18002bf08  push    r12
0x18002bf0a  push    r13
0x18002bf0c  push    r14
0x18002bf0e  push    r15
0x18002bf10  lea     rbp, [rsp-80h]
0x18002bf15  sub     rsp, 180h
0x18002bf1c  mov     r14, r9
0x18002bf1f  mov     rdi, r8
0x18002bf22  mov     rsi, rdx
0x18002bf25  mov     r15d, [rbp+0B0h+arg_20]
0x18002bf2c  mov     [rbp+0B0h+var_B0], r15d
0x18002bf30  mov     rbx, [rbp+0B0h+arg_28]
0x18002bf37  xor     r12d, r12d
0x18002bf3a  mov     [rbp+0B0h+var_A8], r12
0x18002bf3e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x18002bf45  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x18002bf4a  test    al, al
0x18002bf4c  jz      short loc_18002BF73
0x18002bf4e  lea     rdx, aOGd; "o.gd"
0x18002bf55  lea     rcx, [rbp+0B0h+var_78]
0x18002bf59  call    ??$make_unique@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAY04$$CBG$0A@@std@@YA?AV?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@0@AEAY04$$CBG@Z; std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,ushort const (&)[5],0>(ushort const (&)[5])
0x18002bf5e  mov     rdx, rax
0x18002bf61  lea     rcx, [rbp+0B0h+var_A8]
0x18002bf65  call    ??$?4U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@$0A@@?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation> &&)
0x18002bf6a  lea     rcx, [rbp+0B0h+var_78]
0x18002bf6e  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x18002bf73  mov     [rbp+0B0h+var_D8], r12d
0x18002bf77  lea     rdx, aObfuscatedsess; "ObfuscatedSessionKeyFunctions::GetDeriv"...
0x18002bf7e  mov     [rbp+0B0h+var_68], rdx
0x18002bf82  lea     rax, [rbp+0B0h+var_D8]
0x18002bf86  mov     [rbp+0B0h+var_60], rax
0x18002bf8a  mov     [rbp+0B0h+var_58], r12
0x18002bf8e  mov     [rbp+0B0h+var_50], r12
0x18002bf92  xor     r9d, r9d; unsigned int
0x18002bf95  lea     r8d, [r9+17h]; char *
0x18002bf99  lea     rcx, aOnecoreuapDsEx_10; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002bfa0  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18002bfa5  nop
0x18002bfa6  cmp     [rsi], r12d
0x18002bfa9  ja      short loc_18002BFBA
0x18002bfab  mov     r14d, 80070057h
0x18002bfb1  mov     [rbp+0B0h+var_D8], r14d
0x18002bfb5  jmp     loc_18002E28B
0x18002bfba  mov     r8b, 1; bool
0x18002bfbd  mov     edx, r15d; unsigned int
0x18002bfc0  mov     rcx, rbx; this
0x18002bfc3  call    ?SetLength@CBytePtr@@QEAAXK_N@Z; CBytePtr::SetLength(ulong,bool)
0x18002bfc8  cmp     r15d, 20h ; ' '
0x18002bfcc  jb      loc_18002E265
0x18002bfd2  mov     rax, [rbx+8]
0x18002bfd6  mov     [rbp+0B0h+var_70], rax
0x18002bfda  mov     eax, [rdi]
0x18002bfdc  mov     dword ptr [rbp+0B0h+var_128], eax
0x18002bfdf  mov     rcx, [rdi+8]
0x18002bfe3  mov     [rbp+0B0h+var_100], rcx
0x18002bfe7  mov     rax, [r14]
0x18002bfea  mov     [rbp+0B0h+dwBytes], rax
0x18002bfee  mov     edi, [rax-10h]
0x18002bff1  mov     dword ptr [rsp+1B0h+var_150], edi
0x18002bff5  mov     ebx, [rsi]
0x18002bff7  mov     dword ptr [rbp+0B0h+Size], ebx
0x18002bffa  mov     rax, [rsi+8]
0x18002bffe  mov     [rsp+1B0h+Src], rax
0x18002c003  call    cs:__imp_GetProcessHeap
0x18002c009  mov     rcx, rax; hHeap
0x18002c00c  mov     esi, 8
0x18002c011  mov     r8d, 0A0h; dwBytes
0x18002c017  mov     edx, esi; dwFlags
0x18002c019  call    cs:__imp_HeapAlloc
0x18002c01f  mov     r15, rax
0x18002c022  test    rax, rax
0x18002c025  jnz     short loc_18002C035
0x18002c027  xor     r13d, r13d
0x18002c02a  mov     r14d, 0C0000017h
0x18002c030  jmp     loc_18002C345
0x18002c035  movups  xmm0, cs:xmmword_18004D3C0
0x18002c03c  movups  xmmword ptr [rax], xmm0
0x18002c03f  movups  xmm1, cs:xmmword_18004D3D0
0x18002c046  movups  xmmword ptr [rax+10h], xmm1
0x18002c04a  movups  xmm0, cs:xmmword_18004D3E0
0x18002c051  movups  xmmword ptr [rax+20h], xmm0
0x18002c055  movups  xmm1, cs:xmmword_18004D3F0
0x18002c05c  movups  xmmword ptr [rax+30h], xmm1
0x18002c060  movups  xmm0, cs:xmmword_18004D400
0x18002c067  movups  xmmword ptr [rax+40h], xmm0
0x18002c06b  movups  xmm1, cs:xmmword_18004D410
0x18002c072  movups  xmmword ptr [rax+50h], xmm1
0x18002c076  movups  xmm0, cs:xmmword_18004D420
0x18002c07d  movups  xmmword ptr [rax+60h], xmm0
0x18002c081  movups  xmm1, cs:xmmword_18004D430
0x18002c088  movups  xmmword ptr [rax+70h], xmm1
0x18002c08c  movups  xmm0, cs:xmmword_18004D440
0x18002c093  movups  xmmword ptr [rax+80h], xmm0
0x18002c09a  movups  xmm1, cs:xmmword_18004D450
0x18002c0a1  movups  xmmword ptr [rax+90h], xmm1
0x18002c0a8  call    cs:__imp_GetProcessHeap
0x18002c0ae  mov     rcx, rax; hHeap
0x18002c0b1  mov     r8, rsi; dwBytes
0x18002c0b4  mov     edx, esi; dwFlags
0x18002c0b6  call    cs:__imp_HeapAlloc
0x18002c0bc  mov     r13, rax
0x18002c0bf  test    rax, rax
0x18002c0c2  jnz     short loc_18002C0CF
0x18002c0c4  mov     r14d, 0C0000017h
0x18002c0ca  jmp     loc_18002C345
0x18002c0cf  mov     rax, cs:qword_18004D300
0x18002c0d6  mov     [r13+0], rax
0x18002c0da  rdtsc
0x18002c0dc  shl     rdx, 20h
0x18002c0e0  or      rax, rdx
0x18002c0e3  mov     rsi, rax
0x18002c0e6  lea     eax, [rbx+4]
0x18002c0e9  mov     [rbp+0B0h+var_E8], eax
0x18002c0ec  cmp     eax, 4
0x18002c0ef  jb      loc_18002E212
0x18002c0f5  xor     r12d, r12d
0x18002c0f8  mov     [rbp+0B0h+lpMem], r12
0x18002c0fc  xor     r14d, r14d
0x18002c0ff  mov     dword ptr [rsp+1B0h+var_148], r14d
0x18002c104  add     eax, 0C4h
0x18002c109  or      r8d, 0FFFFFFFFh
0x18002c10d  mov     dword ptr [rbp+0B0h+var_128+4], r8d
0x18002c111  mov     ecx, r8d
0x18002c114  mov     edx, 0C4h
0x18002c119  cmp     eax, edx
0x18002c11b  cmovnb  ecx, eax
0x18002c11e  sbb     r14d, r14d
0x18002c121  mov     ebx, 0C0000095h
0x18002c126  and     r14d, ebx
0x18002c129  mov     r9d, 10000000h
0x18002c12f  add     r14d, r9d
0x18002c132  cmp     eax, edx
0x18002c134  jb      loc_18002C300
0x18002c13a  lea     eax, [rdi+4]
0x18002c13d  mov     dword ptr [rbp+0B0h+var_F0], eax
0x18002c140  cmp     eax, 4
0x18002c143  jb      loc_18002E20D
0x18002c149  add     eax, ecx
0x18002c14b  mov     edx, r8d
0x18002c14e  cmp     eax, ecx
0x18002c150  cmovnb  edx, eax
0x18002c153  sbb     r14d, r14d
0x18002c156  and     r14d, ebx
0x18002c159  add     r14d, r9d
0x18002c15c  cmp     eax, ecx
0x18002c15e  jb      loc_18002C300
0x18002c164  mov     eax, dword ptr [rbp+0B0h+var_128]
0x18002c167  add     eax, 4
0x18002c16a  mov     dword ptr [rbp+0B0h+var_130], eax
0x18002c16d  cmp     eax, 4
0x18002c170  jb      loc_18002E20D
0x18002c176  add     eax, edx
0x18002c178  mov     edi, r8d
0x18002c17b  cmp     eax, edx
0x18002c17d  cmovnb  edi, eax
0x18002c180  sbb     r14d, r14d
0x18002c183  and     r14d, ebx
0x18002c186  add     r14d, r9d
0x18002c189  cmp     eax, edx
0x18002c18b  jb      loc_18002C300
0x18002c191  call    cs:__imp_GetProcessHeap
0x18002c197  mov     rcx, rax; hHeap
0x18002c19a  mov     r8d, edi; dwBytes
0x18002c19d  lea     edx, [r12+8]; dwFlags
0x18002c1a2  call    cs:__imp_HeapAlloc
0x18002c1a8  mov     r12, rax
0x18002c1ab  test    rax, rax
0x18002c1ae  jnz     short loc_18002C1B9
0x18002c1b0  lea     r14d, [rbx-7Eh]
0x18002c1b4  jmp     loc_18002E218
0x18002c1b9  lea     rdx, [rax+4]
0x18002c1bd  cmp     rdx, r12
0x18002c1c0  jb      loc_18002C2FD
0x18002c1c6  lea     rcx, [rdi+rax]
0x18002c1ca  add     rax, 8
0x18002c1ce  cmp     rax, rcx
0x18002c1d1  ja      loc_18002C5A7
0x18002c1d7  mov     dword ptr [r12], 4
0x18002c1df  mov     dword ptr [rdx], 71h ; 'q'
0x18002c1e5  mov     rdx, r12
0x18002c1e8  xor     ecx, ecx
0x18002c1ea  mov     eax, [rdx]
0x18002c1ec  add     eax, 4
0x18002c1ef  cmp     eax, 4
0x18002c1f2  jb      loc_18002C2FD
0x18002c1f8  mov     r8d, eax
0x18002c1fb  add     r8, rdx
0x18002c1fe  cmp     r8, rdx
0x18002c201  jb      loc_18002C2FD
0x18002c207  mov     rdx, r8
0x18002c20a  inc     ecx
0x18002c20c  cmp     ecx, 1
0x18002c20f  jb      short loc_18002C1EA
0x18002c211  lea     r10, [r8+4]
0x18002c215  cmp     r10, rdx
0x18002c218  jb      loc_18002C2FD
0x18002c21e  mov     r9d, edi
0x18002c221  mov     [rsp+1B0h+var_168], r9
0x18002c226  mov     r11d, 0A0h
0x18002c22c  mov     r8d, r11d; Size
0x18002c22f  lea     rcx, [r12+rdi]
0x18002c233  lea     rax, [r8+4]
0x18002c237  add     rax, rdx
0x18002c23a  cmp     rax, rcx
0x18002c23d  ja      loc_18002C5A7
0x18002c243  mov     [rdx], r11d
0x18002c246  test    r15, r15
0x18002c249  jz      short loc_18002C25B
0x18002c24b  mov     rdx, r15; Src
0x18002c24e  mov     rcx, r10; void *
0x18002c251  call    memcpy_0
0x18002c256  mov     r9, [rsp+1B0h+var_168]
0x18002c25b  mov     r14d, 2
0x18002c261  lea     r8d, [r14+6]
0x18002c265  mov     edi, r9d
0x18002c268  test    r13, r13
0x18002c26b  jz      loc_18002C3C2
0x18002c271  test    r12, r12
0x18002c274  jnz     short loc_18002C287
0x18002c276  lea     edi, [r8+4]
0x18002c27a  add     edi, r9d
0x18002c27d  cmp     edi, r9d
0x18002c280  jb      short loc_18002C2FD
0x18002c282  inc     r14d
0x18002c285  jmp     short loc_18002C2EB
0x18002c287  xor     ecx, ecx
0x18002c289  mov     rdx, r12
0x18002c28c  mov     eax, [rdx]
0x18002c28e  add     eax, 4
0x18002c291  cmp     eax, 4
0x18002c294  jb      short loc_18002C2FD
0x18002c296  mov     r10d, eax
0x18002c299  add     r10, rdx
0x18002c29c  cmp     r10, rdx
0x18002c29f  jb      short loc_18002C2FD
0x18002c2a1  mov     rdx, r10
0x18002c2a4  inc     ecx
0x18002c2a6  cmp     ecx, r14d
0x18002c2a9  jb      short loc_18002C28C
0x18002c2ab  add     r10, 4
0x18002c2af  cmp     r10, rdx
0x18002c2b2  jb      short loc_18002C2FD
0x18002c2b4  mov     r11d, r8d
0x18002c2b7  mov     ecx, r9d
0x18002c2ba  add     rcx, r12
0x18002c2bd  lea     rax, [r8+4]
0x18002c2c1  add     rax, rdx
0x18002c2c4  cmp     rax, rcx
0x18002c2c7  ja      loc_18002C5A7
0x18002c2cd  mov     [rdx], r8d
0x18002c2d0  test    r13, r13
0x18002c2d3  jz      short loc_18002C2E3
0x18002c2d5  mov     r8d, r11d; Size
0x18002c2d8  mov     rdx, r13; Src
0x18002c2db  mov     rcx, r10; void *
0x18002c2de  call    memcpy_0
0x18002c2e3  inc     r14d
0x18002c2e6  test    r12, r12
0x18002c2e9  jnz     short loc_18002C353
0x18002c2eb  lea     r8d, [rdi+0Ch]
0x18002c2ef  mov     dword ptr [rsp+1B0h+var_180], r8d
0x18002c2f4  cmp     r8d, edi
0x18002c2f7  jnb     loc_18002C3AC
0x18002c2fd  mov     r14d, ebx
0x18002c300  test    r14d, r14d
0x18002c303  js      short loc_18002C30F
0x18002c305  mov     eax, dword ptr [rsp+1B0h+var_148]
0x18002c309  test    eax, eax
0x18002c30b  cmovnz  r14d, eax
0x18002c30f  test    r12, r12
0x18002c312  jz      short loc_18002C328
0x18002c314  call    cs:__imp_GetProcessHeap
0x18002c31a  mov     rcx, rax; hHeap
0x18002c31d  mov     r8, r12; lpMem
0x18002c320  xor     edx, edx; dwFlags
0x18002c322  call    cs:__imp_HeapFree
0x18002c328  mov     rbx, [rbp+0B0h+lpMem]
0x18002c32c  test    rbx, rbx
0x18002c32f  jz      short loc_18002C345
0x18002c331  call    cs:__imp_GetProcessHeap
0x18002c337  mov     rcx, rax; hHeap
0x18002c33a  mov     r8, rbx; lpMem
0x18002c33d  xor     edx, edx; dwFlags
0x18002c33f  call    cs:__imp_HeapFree
0x18002c345  test    r15, r15
0x18002c348  jz      loc_18002E22C
0x18002c34e  jmp     loc_18002E218
0x18002c353  mov     rdx, r12
0x18002c356  xor     ecx, ecx
0x18002c358  mov     r8d, edi
0x18002c35b  mov     dword ptr [rsp+1B0h+var_180], edi
0x18002c35f  test    r14d, r14d
0x18002c362  jz      short loc_18002C383
0x18002c364  mov     eax, [rdx]
0x18002c366  add     eax, 4
0x18002c369  cmp     eax, 4
  ... truncated ...
```
