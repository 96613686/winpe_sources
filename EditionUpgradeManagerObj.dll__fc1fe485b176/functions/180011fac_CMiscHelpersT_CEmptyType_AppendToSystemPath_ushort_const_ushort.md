# CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)

- ea: `0x180011fac`
- end: `0x18001222f`
- name: `?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z`
- size: `643`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800170b0`

## callees

- `0x180001ac0`
- `0x1800090dc`
- `0x180009480`
- `0x18000b448`
- `0x18000b68c`
- `0x18000b984`
- `0x180011fac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800121ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800121cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800121ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800121ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800121cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800121ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012021`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180012017`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180012017`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::AppendToSystemPath(__int64 a1, unsigned __int16 **a2)
{
  __int64 v3; // rbx
  unsigned __int16 *v4; // r15
  __int64 v5; // rsi
  signed int LastError; // eax
  unsigned int v7; // edi
  __int64 v8; // rdx
  WCHAR *v9; // rax
  __int64 v10; // rcx
  int Internal; // eax
  int StringCch; // eax
  int v13; // eax
  int v14; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v21 = 1;
  v20 = 0;
  v18 = 0;
  v3 = 0;
  v22 = *(_DWORD *)L"\\";
  v19 = 0;
  v4 = 0;
  v5 = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
LABEL_6:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_32;
  }
  v8 = 260;
  v9 = Buffer;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v7 = v8 == 0 ? 0x80070057 : 0;
  v10 = (260 - v8) & -(__int64)(v8 != 0);
  if ( !v8 )
    goto LABEL_6;
  if ( Buffer[v10 - 1] == 92 || Buffer[v10 - 1] == 47 )
    --v10;
  if ( v10 == (unsigned int)v10 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v7 = 0;
  }
  else
  {
    v7 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) == 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer);
    v7 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v5 = v18;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_6;
  LODWORD(v18) = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"ChangePk.exe", &v18);
  v7 = StringCch;
  if ( StringCch >= 0 )
  {
    v13 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(L"ChangePk.exe");
    v7 = v13;
    if ( v13 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
    v3 = v19;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_6;
  v14 = STRAPI_MultiCat(&v20, 3u, v5, &v22, v3);
  v7 = v14;
  if ( v14 >= 0 )
  {
    *a2 = v20;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
    v4 = v20;
  }
LABEL_32:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v3 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v4 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v7;
}

```

## disassembly

```asm
0x180011fac  push    rbp
0x180011fae  push    rbx
0x180011faf  push    rsi
0x180011fb0  push    rdi
0x180011fb1  push    r12
0x180011fb3  push    r13
0x180011fb5  push    r14
0x180011fb7  push    r15
0x180011fb9  lea     rbp, [rsp-178h]
0x180011fc1  sub     rsp, 278h
0x180011fc8  mov     rax, cs:__security_cookie
0x180011fcf  xor     rax, rsp
0x180011fd2  mov     [rbp+1B0h+var_50], rax
0x180011fd9  mov     eax, dword ptr cs:asc_180026A54; "\\"
0x180011fdf  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x180011fe4  xor     r13d, r13d
0x180011fe7  mov     [rsp+2B0h+var_268], 1
0x180011fef  mov     r12, rdx
0x180011ff2  mov     [rsp+2B0h+var_270], r13
0x180011ff7  mov     r14d, 104h
0x180011ffd  mov     [rsp+2B0h+var_280], r13
0x180012002  mov     ebx, r13d
0x180012005  mov     [rsp+2B0h+var_264], eax
0x180012009  mov     edx, r14d; uSize
0x18001200c  mov     [rsp+2B0h+var_278], rbx
0x180012011  mov     r15d, r13d
0x180012014  mov     esi, r13d
0x180012017  call    cs:__imp_GetSystemDirectoryW
0x18001201d  test    eax, eax
0x18001201f  jnz     short loc_18001204B
0x180012021  call    cs:__imp_GetLastError
0x180012027  mov     edi, eax
0x180012029  test    eax, eax
0x18001202b  jnz     short loc_180012034
0x18001202d  mov     edi, 80004005h
0x180012032  jmp     short loc_18001203F
0x180012034  jle     short loc_18001203F
0x180012036  movzx   edi, ax
0x180012039  or      edi, 80070000h
0x18001203f  mov     ecx, edi
0x180012041  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012046  jmp     loc_1800121A0
0x18001204b  mov     rdx, r14
0x18001204e  lea     rax, [rsp+2B0h+Buffer]
0x180012053  cmp     [rax], r13w
0x180012057  jz      short loc_180012063
0x180012059  add     rax, 2
0x18001205d  sub     rdx, 1
0x180012061  jnz     short loc_180012053
0x180012063  mov     rax, rdx
0x180012066  neg     rax
0x180012069  mov     rax, rdx
0x18001206c  sbb     edi, edi
0x18001206e  sub     r14, rdx
0x180012071  not     edi
0x180012073  and     edi, 80070057h
0x180012079  neg     rax
0x18001207c  sbb     rcx, rcx
0x18001207f  and     rcx, r14
0x180012082  test    rdx, rdx
0x180012085  jz      short loc_18001203F
0x180012087  mov     eax, 5Ch ; '\'
0x18001208c  cmp     ax, word ptr [rsp+rcx*2+2B0h+var_264+2]
0x180012091  jz      short loc_18001209F
0x180012093  mov     eax, 2Fh ; '/'
0x180012098  cmp     ax, word ptr [rsp+rcx*2+2B0h+var_264+2]
0x18001209d  jnz     short loc_1800120A2
0x18001209f  dec     rcx
0x1800120a2  mov     r14d, ecx
0x1800120a5  cmp     rcx, r14
0x1800120a8  jz      short loc_1800120BB
0x1800120aa  mov     edi, 80070216h
0x1800120af  mov     r14d, r13d
0x1800120b2  mov     ecx, edi
0x1800120b4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800120b9  jmp     short loc_1800120C5
0x1800120bb  xor     ecx, ecx
0x1800120bd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800120c2  mov     edi, r13d
0x1800120c5  mov     ecx, edi
0x1800120c7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800120cc  test    edi, edi
0x1800120ce  jns     short loc_1800120D9
0x1800120d0  mov     ecx, edi
0x1800120d2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800120d7  jmp     short loc_1800120FD
0x1800120d9  lea     r8, [rsp+2B0h+var_280]
0x1800120de  mov     edx, r14d
0x1800120e1  lea     rcx, [rsp+2B0h+Buffer]; Src
0x1800120e6  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x1800120eb  mov     edi, eax
0x1800120ed  test    eax, eax
0x1800120ef  jns     short loc_1800120F8
0x1800120f1  mov     ecx, eax
0x1800120f3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800120f8  mov     rsi, [rsp+2B0h+var_280]
0x1800120fd  mov     ecx, edi
0x1800120ff  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012104  test    edi, edi
0x180012106  js      loc_18001203F
0x18001210c  lea     rdx, [rsp+2B0h+var_280]
0x180012111  mov     dword ptr [rsp+2B0h+var_280], r13d
0x180012116  lea     rcx, aChangepkExe; "ChangePk.exe"
0x18001211d  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180012122  mov     edi, eax
0x180012124  test    eax, eax
0x180012126  jns     short loc_180012131
0x180012128  mov     ecx, eax
0x18001212a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001212f  jmp     short loc_180012158
0x180012131  mov     edx, dword ptr [rsp+2B0h+var_280]
0x180012135  lea     r8, [rsp+2B0h+var_278]
0x18001213a  lea     rcx, aChangepkExe; "ChangePk.exe"
0x180012141  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180012146  mov     edi, eax
0x180012148  test    eax, eax
0x18001214a  jns     short loc_180012153
0x18001214c  mov     ecx, eax
0x18001214e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012153  mov     rbx, [rsp+2B0h+var_278]
0x180012158  mov     ecx, edi
0x18001215a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001215f  test    edi, edi
0x180012161  js      loc_18001203F
0x180012167  lea     r9, [rsp+2B0h+var_264]
0x18001216c  mov     [rsp+2B0h+var_290], rbx
0x180012171  mov     r8, rsi
0x180012174  lea     rcx, [rsp+2B0h+var_270]; unsigned __int16 **
0x180012179  mov     edx, 3; unsigned int
0x18001217e  call    ?STRAPI_MultiCat@@YAJPEAPEAGKZZ; STRAPI_MultiCat(ushort * *,ulong,...)
0x180012183  mov     edi, eax
0x180012185  test    eax, eax
0x180012187  jns     short loc_180012197
0x180012189  mov     ecx, eax
0x18001218b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012190  mov     r15, [rsp+2B0h+var_270]
0x180012195  jmp     short loc_1800121A0
0x180012197  mov     rax, [rsp+2B0h+var_270]
0x18001219c  mov     [r12], rax
0x1800121a0  mov     ecx, edi
0x1800121a2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800121a7  test    rbx, rbx
0x1800121aa  jz      short loc_1800121C8
0x1800121ac  call    cs:__imp_GetProcessHeap
0x1800121b2  lea     r8, [rbx-4]; lpMem
0x1800121b6  xor     edx, edx; dwFlags
0x1800121b8  mov     rcx, rax; hHeap
0x1800121bb  call    cs:__imp_HeapFree
0x1800121c1  xor     ecx, ecx
0x1800121c3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800121c8  test    rsi, rsi
0x1800121cb  jz      short loc_1800121E9
0x1800121cd  call    cs:__imp_GetProcessHeap
0x1800121d3  lea     r8, [rsi-4]; lpMem
0x1800121d7  xor     edx, edx; dwFlags
0x1800121d9  mov     rcx, rax; hHeap
0x1800121dc  call    cs:__imp_HeapFree
0x1800121e2  xor     ecx, ecx
0x1800121e4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800121e9  test    r15, r15
0x1800121ec  jz      short loc_18001220A
0x1800121ee  call    cs:__imp_GetProcessHeap
0x1800121f4  lea     r8, [r15-4]; lpMem
0x1800121f8  xor     edx, edx; dwFlags
0x1800121fa  mov     rcx, rax; hHeap
0x1800121fd  call    cs:__imp_HeapFree
0x180012203  xor     ecx, ecx
0x180012205  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001220a  mov     eax, edi
0x18001220c  mov     rcx, [rbp+1B0h+var_50]
0x180012213  xor     rcx, rsp; StackCookie
0x180012216  call    __security_check_cookie
0x18001221b  add     rsp, 278h
0x180012222  pop     r15
0x180012224  pop     r14
0x180012226  pop     r13
0x180012228  pop     r12
0x18001222a  pop     rdi
0x18001222b  pop     rsi
0x18001222c  pop     rbx
0x18001222d  pop     rbp
0x18001222e  retn
```
