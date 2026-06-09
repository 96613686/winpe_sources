# CWUEtwConsumer::TrimOrDeleteLogFilesOnReboot(CSusMap<unsigned __int64,wchar_t *,CSusSortedArrayListItemOpsBasic<unsigned __int64>,CSusArrayListItemOpSusFree<wchar_t *>> *,unsigned __int64,unsigned __int64)

- ea: `0x1400165cc`
- end: `0x1400166c1`
- name: `?TrimOrDeleteLogFilesOnReboot@CWUEtwConsumer@@IEAAJPEAV?$CSusMap@_KPEA_WV?$CSusSortedArrayListItemOpsBasic@_K@@V?$CSusArrayListItemOpSusFree@PEA_W@@@@_K_K@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400167cc`

## callees

- `0x1400165cc`
- `0x140045a8c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001667b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001667b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14001666e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14001666e`

## pseudocode

```c
__int64 __fastcall CWUEtwConsumer::TrimOrDeleteLogFilesOnReboot(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4)
{
  unsigned int v4; // ebx
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // r15
  unsigned int i; // esi
  const WCHAR *v12; // rcx

  v4 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  if ( *(_DWORD *)(a2 + 20) > 1u )
    qsort(
      *(void **)(a2 + 8),
      *(unsigned int *)(a2 + 20),
      0x10u,
      (_CoreCrtNonSecureSearchSortCompareFunction)CSusSortedArrayList<CSusMap<unsigned __int64,wchar_t *,CSusSortedArrayListItemOpsBasic<unsigned __int64>,CSusArrayListItemOpSusFree<wchar_t *>>::_tagMapEntry,CSusMap<unsigned __int64,wchar_t *,CSusSortedArrayListItemOpsBasic<unsigned __int64>,CSusArrayListItemOpSusFree<wchar_t *>>::CMapEntryOps>::CompareWeights);
  v9 = *(unsigned int *)(a2 + 20);
  v10 = 0;
  if ( (_DWORD)v9 )
    v10 = a4 / v9;
  for ( i = 0; i < (unsigned int)v9; ++i )
  {
    if ( i < *(_DWORD *)(a2 + 20) )
    {
      v4 = 0;
      v12 = *(const WCHAR **)(*(_QWORD *)(a2 + 8) + 16LL * i);
      if ( (*(_BYTE *)(a1 + 1776) & 0x20) != 0 )
      {
        MoveFileExW(v12, 0, 4u);
      }
      else if ( a4 > a3 && DeleteFileW(v12) )
      {
        if ( a4 < v10 )
          return (unsigned int)-2147024362;
        a4 -= v10;
      }
    }
    else
    {
      v4 = -2145124345;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400165cc  mov     [rsp+arg_0], rbx
0x1400165d1  mov     [rsp+arg_10], rbp
0x1400165d6  mov     [rsp+arg_18], rsi
0x1400165db  push    rdi
0x1400165dc  push    r12
0x1400165de  push    r13
0x1400165e0  push    r14
0x1400165e2  push    r15
0x1400165e4  sub     rsp, 20h
0x1400165e8  xor     ebx, ebx
0x1400165ea  mov     rbp, r9
0x1400165ed  mov     r12, r8
0x1400165f0  mov     rdi, rdx
0x1400165f3  mov     r13, rcx
0x1400165f6  test    rdx, rdx
0x1400165f9  jz      loc_14001669F
0x1400165ff  test    r8, r8
0x140016602  jz      loc_14001669F
0x140016608  cmp     dword ptr [rdx+14h], 1
0x14001660c  jbe     short loc_140016625
0x14001660e  mov     edx, [rdx+14h]; NumOfElements
0x140016611  lea     r9, ?CompareWeights@?$CSusSortedArrayList@U_tagMapEntry@?$CSusMap@_KPEA_WV?$CSusSortedArrayListItemOpsBasic@_K@@V?$CSusArrayListItemOpSusFree@PEA_W@@@@VCMapEntryOps@2@@@CAHPEBX0@Z; CompareFunction
0x140016618  mov     rcx, [rdi+8]; Base
0x14001661c  lea     r8d, [rbx+10h]; SizeOfElements
0x140016620  call    qsort
0x140016625  mov     r14d, [rdi+14h]
0x140016629  xor     r15d, r15d
0x14001662c  test    r14d, r14d
0x14001662f  jz      short loc_14001663C
0x140016631  xor     edx, edx
0x140016633  mov     rax, rbp
0x140016636  div     r14
0x140016639  mov     r15, rax
0x14001663c  xor     esi, esi
0x14001663e  test    r14d, r14d
0x140016641  jz      short loc_14001669B
0x140016643  cmp     esi, [rdi+14h]
0x140016646  jb      short loc_14001664F
0x140016648  mov     ebx, 80240007h
0x14001664d  jmp     short loc_14001668D
0x14001664f  mov     rax, [rdi+8]
0x140016653  xor     ebx, ebx
0x140016655  mov     ecx, esi
0x140016657  add     rcx, rcx
0x14001665a  test    byte ptr [r13+6F0h], 20h
0x140016662  mov     rcx, [rax+rcx*8]; lpFileName
0x140016666  jz      short loc_140016676
0x140016668  xor     edx, edx; lpNewFileName
0x14001666a  lea     r8d, [rbx+4]; dwFlags
0x14001666e  call    cs:__imp_MoveFileExW
0x140016674  jmp     short loc_14001668D
0x140016676  cmp     rbp, r12
0x140016679  jbe     short loc_14001668D
0x14001667b  call    cs:__imp_DeleteFileW
0x140016681  test    eax, eax
0x140016683  jz      short loc_14001668D
0x140016685  cmp     rbp, r15
0x140016688  jb      short loc_140016696
0x14001668a  sub     rbp, r15
0x14001668d  inc     esi
0x14001668f  cmp     esi, r14d
0x140016692  jb      short loc_140016643
0x140016694  jmp     short loc_14001669B
0x140016696  mov     ebx, 80070216h
0x14001669b  mov     eax, ebx
0x14001669d  jmp     short loc_1400166A4
0x14001669f  mov     eax, 80070057h
0x1400166a4  mov     rbx, [rsp+48h+arg_0]
0x1400166a9  mov     rbp, [rsp+48h+arg_10]
0x1400166ae  mov     rsi, [rsp+48h+arg_18]
0x1400166b3  add     rsp, 20h
0x1400166b7  pop     r15
0x1400166b9  pop     r14
0x1400166bb  pop     r13
0x1400166bd  pop     r12
0x1400166bf  pop     rdi
0x1400166c0  retn
```
