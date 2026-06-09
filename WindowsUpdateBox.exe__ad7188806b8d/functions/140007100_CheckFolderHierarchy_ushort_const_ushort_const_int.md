# CheckFolderHierarchy(ushort const *,ushort const *,int *)

- ea: `0x140007100`
- end: `0x1400072b6`
- name: `?CheckFolderHierarchy@@YAJPEBG0PEAH@Z`
- size: `438`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400072bc`

## callees

- `0x140007100`
- `0x1400076c8`
- `0x1400135b8`
- `0x140016bb4`
- `0x14001dd28`
- `0x14001fd8c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007255`
- `KERNEL32!HeapFree` at `0x140007289`
- `KERNEL32!HeapFree` at `0x140007255`
- `KERNEL32!HeapFree` at `0x140007289`
- `KERNEL32!GetProcessHeap` at `0x140007241`
- `KERNEL32!GetProcessHeap` at `0x140007275`
- `KERNEL32!GetProcessHeap` at `0x140007241`
- `KERNEL32!GetProcessHeap` at `0x140007275`
- `KERNEL32!CompareStringW` at `0x140007207`
- `KERNEL32!CompareStringW` at `0x140007207`

## pseudocode

```c
__int64 __fastcall CheckFolderHierarchy(unsigned __int16 *a1, unsigned __int16 *a2, int *a3)
{
  __int64 v5; // rcx
  int v6; // ebx
  HANDLE v7; // rcx
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  void *v10; // rdi
  HANDLE v11; // rax
  __int64 v13; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-18h]
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  LPVOID v16; // [rsp+48h] [rbp-8h]

  v15 = 0;
  v16 = 0;
  v13 = 0;
  lpMem = 0;
  if ( a1 && a2 && a3 )
  {
    v6 = CMiscHelpersT<CEmptyType>::TokenizeString(a1);
    v5 = (unsigned int)v6;
    if ( v6 >= 0 )
    {
      v6 = CMiscHelpersT<CEmptyType>::TokenizeString(a2);
      v5 = (unsigned int)v6;
      if ( v6 >= 0 )
      {
        *a3 = 1;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v5 = 2147942487LL;
    v6 = -2147024809;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  v7 = 0;
  if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v7 = g_shLogFile;
  OutputMsg(v7, g_shLogEvent, L"%s: Error = 0x%X", L"CheckFolderHierarchy", v6);
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(&v13, 0);
  v8 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(&v15, 0);
  v10 = v16;
  if ( v16 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140007100  mov     [rsp-28h+arg_0], rbx
0x140007105  mov     [rsp-28h+arg_8], rsi
0x14000710a  mov     [rsp-28h+arg_10], rdi
0x14000710f  push    rbp
0x140007110  push    r12
0x140007112  push    r13
0x140007114  push    r14
0x140007116  push    r15
0x140007118  mov     rbp, rsp
0x14000711b  sub     rsp, 50h
0x14000711f  xor     r13d, r13d
0x140007122  mov     rdi, r8
0x140007125  mov     [rbp+var_10], r13
0x140007129  mov     rsi, rdx
0x14000712c  mov     [rbp+var_8], r13
0x140007130  mov     [rbp+var_20], r13
0x140007134  mov     [rbp+lpMem], r13
0x140007138  test    rcx, rcx
0x14000713b  jnz     short loc_140007146
0x14000713d  mov     ecx, 80070057h; Src
0x140007142  mov     ebx, ecx
0x140007144  jmp     short loc_140007175
0x140007146  test    rsi, rsi
0x140007149  jz      short loc_14000713D
0x14000714b  test    rdi, rdi
0x14000714e  jz      short loc_14000713D
0x140007150  lea     r8, [rbp+var_10]
0x140007154  call    ?TokenizeString@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGGPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@H@Z; CMiscHelpersT<CEmptyType>::TokenizeString(ushort const *,ushort,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,int)
0x140007159  mov     ebx, eax
0x14000715b  mov     ecx, eax
0x14000715d  test    eax, eax
0x14000715f  js      short loc_140007175
0x140007161  lea     r8, [rbp+var_20]
0x140007165  mov     rcx, rsi; Src
0x140007168  call    ?TokenizeString@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGGPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@H@Z; CMiscHelpersT<CEmptyType>::TokenizeString(ushort const *,ushort,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,int)
0x14000716d  mov     ebx, eax
0x14000716f  mov     ecx, eax
0x140007171  test    eax, eax
0x140007173  jns     short loc_1400071B5
0x140007175  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000717a  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140007181  lea     r9, aCheckfolderhie; "CheckFolderHierarchy"
0x140007188  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14000718f  mov     rcx, r13
0x140007192  mov     dword ptr [rsp+50h+lpString2], ebx
0x140007196  lea     rax, [r8-1]
0x14000719a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000719e  setnbe  al
0x1400071a1  test    al, al
0x1400071a3  cmovz   rcx, r8; hFile
0x1400071a7  lea     r8, aSError0xX; "%s: Error = 0x%X"
0x1400071ae  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x1400071b3  jmp     short loc_140007226
0x1400071b5  mov     esi, dword ptr [rbp+var_10+4]
0x1400071b8  cmp     dword ptr [rbp+var_20+4], esi
0x1400071bb  jge     short loc_1400071C5
0x1400071bd  mov     [rdi], r13d
0x1400071c0  mov     ebx, r13d
0x1400071c3  jmp     short loc_140007226
0x1400071c5  mov     r14d, r13d
0x1400071c8  test    esi, esi
0x1400071ca  jz      short loc_140007220
0x1400071cc  mov     r12, [rbp+var_8]
0x1400071d0  mov     r15, [rbp+lpMem]
0x1400071d4  movsxd  r8, r14d
0x1400071d7  mov     ecx, 409h; Locale
0x1400071dc  mov     [rsp+50h+cchCount2], 0FFFFFFFFh; cchCount2
0x1400071e4  mov     rax, [r15+r8*8]
0x1400071e8  mov     r8, [r12+r8*8]
0x1400071ec  test    rax, rax
0x1400071ef  cmovz   rax, r13
0x1400071f3  test    r8, r8
0x1400071f6  mov     [rsp+50h+lpString2], rax; lpString2
0x1400071fb  cmovz   r8, r13; lpString1
0x1400071ff  or      r9d, 0FFFFFFFFh; cchCount1
0x140007203  lea     edx, [r9+2]; dwCmpFlags
0x140007207  call    cs:__imp_CompareStringW
0x14000720e  nop     dword ptr [rax+rax+00h]
0x140007213  cmp     eax, 2
0x140007216  jnz     short loc_1400071BD
0x140007218  inc     r14d
0x14000721b  cmp     r14d, esi
0x14000721e  jb      short loc_1400071D4
0x140007220  mov     dword ptr [rdi], 1
0x140007226  mov     ecx, ebx
0x140007228  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000722d  xor     edx, edx
0x14000722f  lea     rcx, [rbp+var_20]
0x140007233  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x140007238  mov     rdi, [rbp+lpMem]
0x14000723c  test    rdi, rdi
0x14000723f  jz      short loc_140007261
0x140007241  call    cs:__imp_GetProcessHeap
0x140007248  nop     dword ptr [rax+rax+00h]
0x14000724d  mov     r8, rdi; lpMem
0x140007250  xor     edx, edx; dwFlags
0x140007252  mov     rcx, rax; hHeap
0x140007255  call    cs:__imp_HeapFree
0x14000725c  nop     dword ptr [rax+rax+00h]
0x140007261  xor     edx, edx
0x140007263  lea     rcx, [rbp+var_10]
0x140007267  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x14000726c  mov     rdi, [rbp+var_8]
0x140007270  test    rdi, rdi
0x140007273  jz      short loc_140007295
0x140007275  call    cs:__imp_GetProcessHeap
0x14000727c  nop     dword ptr [rax+rax+00h]
0x140007281  mov     r8, rdi; lpMem
0x140007284  xor     edx, edx; dwFlags
0x140007286  mov     rcx, rax; hHeap
0x140007289  call    cs:__imp_HeapFree
0x140007290  nop     dword ptr [rax+rax+00h]
0x140007295  lea     r11, [rsp+50h+var_s0]
0x14000729a  mov     eax, ebx
0x14000729c  mov     rbx, [r11+30h]
0x1400072a0  mov     rsi, [r11+38h]
0x1400072a4  mov     rdi, [r11+40h]
0x1400072a8  mov     rsp, r11
0x1400072ab  pop     r15
0x1400072ad  pop     r14
0x1400072af  pop     r13
0x1400072b1  pop     r12
0x1400072b3  pop     rbp
0x1400072b4  retn
```
