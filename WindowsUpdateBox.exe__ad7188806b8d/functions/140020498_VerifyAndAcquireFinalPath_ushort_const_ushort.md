# VerifyAndAcquireFinalPath(ushort const *,ushort * *)

- ea: `0x140020498`
- end: `0x140020664`
- name: `?VerifyAndAcquireFinalPath@@YAJPEBGPEAPEAG@Z`
- size: `460`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140005ec0`
- `0x140006110`
- `0x1400076e8`
- `0x14000a7d0`

## callees

- `0x1400076c8`
- `0x140008434`
- `0x1400135b8`
- `0x140016bb4`
- `0x14001f288`
- `0x140020498`
- `0x1400221fc`
- `0x140028224`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14002061d`
- `KERNEL32!HeapFree` at `0x14002064a`
- `KERNEL32!HeapFree` at `0x14002061d`
- `KERNEL32!HeapFree` at `0x14002064a`
- `KERNEL32!GetProcessHeap` at `0x140020608`
- `KERNEL32!GetProcessHeap` at `0x140020636`
- `KERNEL32!GetProcessHeap` at `0x140020608`
- `KERNEL32!GetProcessHeap` at `0x140020636`
- `KERNEL32!GetLastError` at `0x1400204f9`
- `KERNEL32!GetLastError` at `0x1400204f9`
- `KERNEL32!CompareStringW` at `0x140020570`
- `KERNEL32!CompareStringW` at `0x140020570`

## pseudocode

```c
__int64 __fastcall VerifyAndAcquireFinalPath(wchar_t *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // rdi
  unsigned int v6; // esi
  __int64 v7; // rcx
  unsigned int FinalPathFlags; // eax
  signed int LastError; // eax
  int v10; // eax
  PCNZWCH v11; // rbp
  HANDLE v12; // rcx
  int v13; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  PCNZWCH lpString1; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 *v18; // [rsp+80h] [rbp+18h]
  PCNZWCH lpString2; // [rsp+88h] [rbp+20h] BYREF

  v4 = 0;
  v5 = 0;
  v18 = 0;
  lpString1 = 0;
  lpString2 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
LABEL_3:
    v7 = v6;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_21;
  }
  FinalPathFlags = GetFinalPathFlags(a1);
  v4 = (unsigned __int16 *)FormFinalPathNameEx(a1, FinalPathFlags);
  if ( !v4 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    goto LABEL_3;
  }
  v10 = SkipLongPathPrefix(a1, &lpString1);
  v6 = v10;
  if ( v10 < 0 || (v10 = SkipLongPathPrefix(v4, &lpString2), v6 = v10, v10 < 0) )
  {
    v7 = (unsigned int)v10;
    goto LABEL_4;
  }
  v11 = lpString2;
  if ( CompareStringW(0x409u, 1u, lpString1, -1, lpString2, -1) != 2 )
  {
    v12 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v12 = g_shLogFile;
    OutputMsg(v12, g_shLogEvent, L"Spoofing detected: deleting [%s] -> [%s]", lpString1, v11);
    v6 = -2147024215;
    goto LABEL_3;
  }
  if ( a2 )
  {
    v13 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(v4);
    v6 = v13;
    if ( v13 >= 0 )
    {
      v5 = 0;
      *a2 = v18;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
      v5 = v18;
    }
  }
LABEL_21:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v4);
  }
  return v6;
}

```

## disassembly

```asm
0x140020498  mov     rax, rsp
0x14002049b  push    rbx
0x14002049c  push    rbp
0x14002049d  push    rsi
0x14002049e  push    rdi
0x14002049f  push    r14
0x1400204a1  sub     rsp, 40h
0x1400204a5  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1400204ad  mov     r14, rdx
0x1400204b0  mov     rsi, rcx
0x1400204b3  xor     ebx, ebx
0x1400204b5  mov     [rax-30h], rbx
0x1400204b9  xor     edi, edi
0x1400204bb  mov     [rax+18h], rdi
0x1400204bf  mov     [rax+8], rdi
0x1400204c3  mov     [rax+20h], rdi
0x1400204c7  test    rcx, rcx
0x1400204ca  jnz     short loc_1400204DD
0x1400204cc  mov     esi, 80070057h
0x1400204d1  mov     ecx, esi
0x1400204d3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400204d8  jmp     loc_1400205FB
0x1400204dd  xor     r8d, r8d
0x1400204e0  xor     edx, edx
0x1400204e2  call    GetFinalPathFlags
0x1400204e7  mov     edx, eax
0x1400204e9  mov     rcx, rsi
0x1400204ec  call    FormFinalPathNameEx
0x1400204f1  mov     rbx, rax
0x1400204f4  test    rax, rax
0x1400204f7  jnz     short loc_14002051F
0x1400204f9  call    cs:__imp_GetLastError
0x140020500  nop     dword ptr [rax+rax+00h]
0x140020505  mov     esi, eax
0x140020507  test    eax, eax
0x140020509  jnz     short loc_140020512
0x14002050b  mov     esi, 80004005h
0x140020510  jmp     short loc_1400204D1
0x140020512  jle     short loc_1400204D1
0x140020514  movzx   esi, ax
0x140020517  or      esi, 80070000h
0x14002051d  jmp     short loc_1400204D1
0x14002051f  lea     rdx, [rsp+68h+lpString1]; unsigned __int16 **
0x140020524  mov     rcx, rsi; unsigned __int16 *
0x140020527  call    ?SkipLongPathPrefix@@YAJPEBGPEAPEBG@Z; SkipLongPathPrefix(ushort const *,ushort const * *)
0x14002052c  mov     esi, eax
0x14002052e  test    eax, eax
0x140020530  jns     short loc_140020536
0x140020532  mov     ecx, eax
0x140020534  jmp     short loc_1400204D3
0x140020536  lea     rdx, [rsp+68h+arg_18]; unsigned __int16 **
0x14002053e  mov     rcx, rbx; unsigned __int16 *
0x140020541  call    ?SkipLongPathPrefix@@YAJPEBGPEAPEBG@Z; SkipLongPathPrefix(ushort const *,ushort const * *)
0x140020546  mov     esi, eax
0x140020548  test    eax, eax
0x14002054a  js      short loc_140020532
0x14002054c  or      r9d, 0FFFFFFFFh; cchCount1
0x140020550  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x140020555  mov     rbp, [rsp+68h+arg_18]
0x14002055d  mov     [rsp+68h+lpString2], rbp; lpString2
0x140020562  mov     r8, [rsp+68h+lpString1]; lpString1
0x140020567  lea     edx, [r9+2]; dwCmpFlags
0x14002056b  mov     ecx, 409h; Locale
0x140020570  call    cs:__imp_CompareStringW
0x140020577  nop     dword ptr [rax+rax+00h]
0x14002057c  cmp     eax, 2
0x14002057f  jz      short loc_1400205C2
0x140020581  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x140020588  lea     rax, [r8-1]
0x14002058c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140020590  setnbe  al
0x140020593  xor     ecx, ecx
0x140020595  test    al, al
0x140020597  cmovz   rcx, r8; hFile
0x14002059b  mov     [rsp+68h+lpString2], rbp
0x1400205a0  mov     r9, [rsp+68h+lpString1]
0x1400205a5  lea     r8, aSpoofingDetect_0; "Spoofing detected: deleting [%s] -> [%s"...
0x1400205ac  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x1400205b3  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x1400205b8  mov     esi, 800702A9h
0x1400205bd  jmp     loc_1400204D1
0x1400205c2  test    r14, r14
0x1400205c5  jz      short loc_1400205FB
0x1400205c7  lea     rdx, [rsp+68h+arg_10]
0x1400205cf  mov     rcx, rbx; Src
0x1400205d2  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x1400205d7  mov     esi, eax
0x1400205d9  test    eax, eax
0x1400205db  jns     short loc_1400205EE
0x1400205dd  mov     ecx, eax
0x1400205df  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400205e4  mov     rdi, [rsp+68h+arg_10]
0x1400205ec  jmp     short loc_1400205FB
0x1400205ee  mov     rax, [rsp+68h+arg_10]
0x1400205f6  xor     edi, edi
0x1400205f8  mov     [r14], rax
0x1400205fb  mov     ecx, esi
0x1400205fd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140020602  nop
0x140020603  test    rdi, rdi
0x140020606  jz      short loc_140020631
0x140020608  call    cs:__imp_GetProcessHeap
0x14002060f  nop     dword ptr [rax+rax+00h]
0x140020614  mov     rcx, rax; hHeap
0x140020617  lea     r8, [rdi-4]; lpMem
0x14002061b  xor     edx, edx; dwFlags
0x14002061d  call    cs:__imp_HeapFree
0x140020624  nop     dword ptr [rax+rax+00h]
0x140020629  xor     ecx, ecx
0x14002062b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140020630  nop
0x140020631  test    rbx, rbx
0x140020634  jz      short loc_140020656
0x140020636  call    cs:__imp_GetProcessHeap
0x14002063d  nop     dword ptr [rax+rax+00h]
0x140020642  mov     rcx, rax; hHeap
0x140020645  mov     r8, rbx; lpMem
0x140020648  xor     edx, edx; dwFlags
0x14002064a  call    cs:__imp_HeapFree
0x140020651  nop     dword ptr [rax+rax+00h]
0x140020656  mov     eax, esi
0x140020658  add     rsp, 40h
0x14002065c  pop     r14
0x14002065e  pop     rdi
0x14002065f  pop     rsi
0x140020660  pop     rbp
0x140020661  pop     rbx
0x140020662  retn
```
