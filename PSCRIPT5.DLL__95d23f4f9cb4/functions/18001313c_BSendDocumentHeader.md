# BSendDocumentHeader

- ea: `0x18001313c`
- end: `0x1800134f9`
- name: `BSendDocumentHeader`
- size: `957`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180014988`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x180012c34`
- `0x180012de0`
- `0x18001313c`
- `0x1800148ec`
- `0x18001493c`
- `0x180016940`
- `0x180016c90`
- `0x18001aa48`

## import_xrefs

- `WINSPOOL!GetJobW` at `0x180013232`
- `WINSPOOL!GetJobW` at `0x180013285`
- `WINSPOOL!GetJobW` at `0x180013232`
- `WINSPOOL!GetJobW` at `0x180013285`
- `KERNEL32!WideCharToMultiByte` at `0x1800132dc`
- `KERNEL32!WideCharToMultiByte` at `0x1800132dc`
- `KERNEL32!LocalFree` at `0x180013303`
- `KERNEL32!LocalFree` at `0x180013303`
- `KERNEL32!LocalAlloc` at `0x180013250`
- `KERNEL32!LocalAlloc` at `0x180013250`
- `GDI32!EngQueryLocalTime` at `0x1800131cc`
- `GDI32!EngQueryLocalTime` at `0x1800131cc`

## string_xrefs

- `0x1800131b8`: `%%%%Creator: PScript5.dll Version 5.2.2\n`

## pseudocode

```c
_BOOL8 __fastcall BSendDocumentHeader(__int64 a1)
{
  HLOCAL v2; // rdi
  const WCHAR *v3; // r8
  __int64 v4; // r9
  const char *v5; // r8
  const char *v6; // r8
  __int64 v7; // rax
  const char *v8; // r8
  __int16 v9; // cx
  const char *v10; // rdx
  __int64 v11; // rcx
  DWORD pcbNeeded; // [rsp+40h] [rbp-C0h] BYREF
  _ENG_TIME_FIELDS v14; // [rsp+48h] [rbp-B8h] BYREF
  CHAR MultiByteStr[256]; // [rsp+60h] [rbp-A0h] BYREF

  pcbNeeded = 0;
  v14 = 0;
  DSCSend(a1, (const char *)2);
  BSendClean7BitDSC(a1, "%%%%Title: %s\r\n", (const char *)(a1 + 2904));
  DSCSend(a1, "%%%%Creator: PScript5.dll Version 5.2.2\r\n");
  EngQueryLocalTime(&v14);
  DSCSend(
    a1,
    "%%%%CreationDate: %d/%d/%d %d:%d:%d\r\n",
    v14.usMonth,
    v14.usDay,
    v14.usYear,
    v14.usHour,
    v14.usMinute,
    v14.usSecond);
  if ( !GetJobW(*(HANDLE *)(a1 + 24), *(_DWORD *)(a1 + 2232), 1u, 0, 0, &pcbNeeded) )
  {
    if ( pcbNeeded )
    {
      v2 = LocalAlloc(0, pcbNeeded);
      if ( v2 )
      {
        if ( GetJobW(*(HANDLE *)(a1 + 24), *(_DWORD *)(a1 + 2232), 1u, (LPBYTE)v2, pcbNeeded, &pcbNeeded)
          && *((_QWORD *)v2 + 3) )
        {
          memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
          v3 = (const WCHAR *)*((_QWORD *)v2 + 3);
          v4 = -1;
          do
            ++v4;
          while ( v3[v4] );
          WideCharToMultiByte(0, 0, v3, v4 + 1, MultiByteStr, 256, 0, 0);
          MultiByteStr[255] = 0;
          BSendClean7BitDSC(a1, "%%%%For: %s\r\n", MultiByteStr);
        }
        LocalFree(v2);
      }
    }
  }
  BSendBoundingBox(a1, 0);
  v5 = "(atend)";
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) == 2 )
    v5 = "1";
  DSCSend(a1, (const char *)3, v5);
  v6 = "Portrait";
  if ( *(_DWORD *)(a1 + 716) )
    v6 = "Landscape";
  DSCSend(a1, (const char *)8, v6);
  v7 = *(_QWORD *)(a1 + 96);
  if ( !*(_DWORD *)(v7 + 124) || (v8 = "Ascend", *(_DWORD *)(v7 + 136)) )
    v8 = "Special";
  DSCSend(a1, (const char *)7, v8);
  DSCSend(a1, "%%%%DocumentNeededResources: (atend)\r\n");
  DSCSend(a1, "%%%%DocumentSuppliedResources: (atend)\r\n");
  if ( *(_WORD *)(a1 + 166) )
    DSCSend(a1, "%%%%P8BIT\r\n");
  v9 = *(_WORD *)(a1 + 166);
  if ( ((v9 - 2) & 0xFFFD) != 0 )
  {
    v10 = "%%%%DocumentData: Clean7Bit\r\n";
    if ( v9 == 16 )
      v10 = "%%%%DocumentData: Binary\r\n";
  }
  else
  {
    v10 = "%%%%DocumentData: Clean8Bit\r\n";
  }
  DSCSend(a1, v10);
  DSCSend(a1, "%%%%TargetDevice: ");
  OPSendInvocation(a1, *(_QWORD *)(a1 + 2144) + 32LL);
  OPRawPortWrite(a1, " ", 1);
  OPSendInvocation(a1, *(_QWORD *)(a1 + 2144) + 24LL);
  OPRawPortWrite(a1, "\r\n", 2);
  DSCSend(a1, "%%%%LanguageLevel: %d\r\n", *(_DWORD *)(*(_QWORD *)(a1 + 96) + 140LL));
  DSCSend(a1, (const char *)0x15);
  DSCSend(a1, (const char *)0xB);
  DSCSend(a1, (const char *)0xC);
  BSendBoundingBox(a1, 106);
  BSendViewingOrientation(a1);
  *(_DWORD *)(a1 + 2184) = DwGetOrientIndex(a1);
  DSCSend(v11, (const char *)0xD);
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x18001313c  mov     [rsp-8+arg_8], rbx
0x180013141  mov     [rsp-8+arg_10], rsi
0x180013146  push    rbp
0x180013147  push    rdi
0x180013148  push    r15
0x18001314a  lea     rbp, [rsp-70h]
0x18001314f  sub     rsp, 170h
0x180013156  mov     rax, cs:__security_cookie
0x18001315d  xor     rax, rsp
0x180013160  mov     [rbp+80h+var_20], rax
0x180013164  mov     rax, [rcx+60h]
0x180013168  lea     r8, DSC_EPSF; " EPSF-3.0"
0x18001316f  xor     esi, esi
0x180013171  mov     rbx, rcx
0x180013174  xorps   xmm0, xmm0
0x180013177  mov     [rsp+180h+var_140], esi
0x18001317b  movups  xmmword ptr [rsp+180h+var_138.usYear], xmm0
0x180013180  lea     rcx, dword_1800624DC
0x180013187  lea     r15d, [rsi+2]
0x18001318b  cmp     [rax+7Ch], r15d
0x18001318f  mov     edx, r15d
0x180013192  cmovnz  r8, rcx
0x180013196  mov     rcx, rbx
0x180013199  call    DSCSend
0x18001319e  lea     r8, [rbx+0B58h]
0x1800131a5  mov     rcx, rbx
0x1800131a8  lea     r9d, [r15+7Eh]
0x1800131ac  lea     rdx, DSC_Title; "%%%%Title: %s\r\n"
0x1800131b3  call    BSendClean7BitDSC
0x1800131b8  lea     rdx, DSC_Creator; "%%%%Creator: PScript5.dll Version 5.2.2"...
0x1800131bf  mov     rcx, rbx
0x1800131c2  call    DSCSend
0x1800131c7  lea     rcx, [rsp+180h+var_138]; PENG_TIME_FIELDS
0x1800131cc  call    cs:__imp_EngQueryLocalTime
0x1800131d2  movzx   ecx, [rsp+180h+var_138.usMinute]
0x1800131d7  movzx   edx, [rsp+180h+var_138.usHour]
0x1800131dc  movzx   eax, [rsp+180h+var_138.usSecond]
0x1800131e1  movzx   r10d, [rsp+180h+var_138.usYear]
0x1800131e7  movzx   r9d, [rsp+180h+var_138.usDay]
0x1800131ed  movzx   r8d, [rsp+180h+var_138.usMonth]
0x1800131f3  mov     dword ptr [rsp+180h+lpUsedDefaultChar], eax
0x1800131f7  mov     dword ptr [rsp+180h+lpDefaultChar], ecx
0x1800131fb  mov     rcx, rbx
0x1800131fe  mov     dword ptr [rsp+180h+pcbNeeded], edx
0x180013202  lea     rdx, DSC_CreationDate; "%%%%CreationDate: %d/%d/%d %d:%d:%d\r\n"
0x180013209  mov     [rsp+180h+cbBuf], r10d
0x18001320e  call    DSCSend
0x180013213  mov     edx, [rbx+8B8h]; JobId
0x180013219  lea     rax, [rsp+180h+var_140]
0x18001321e  mov     rcx, [rbx+18h]; hPrinter
0x180013222  lea     r8d, [rsi+1]; Level
0x180013226  mov     [rsp+180h+pcbNeeded], rax; pcbNeeded
0x18001322b  xor     r9d, r9d; pJob
0x18001322e  mov     [rsp+180h+cbBuf], esi; cbBuf
0x180013232  call    cs:__imp_GetJobW
0x180013238  test    eax, eax
0x18001323a  jnz     loc_180013309
0x180013240  mov     eax, [rsp+180h+var_140]
0x180013244  test    eax, eax
0x180013246  jz      loc_180013309
0x18001324c  mov     edx, eax; uBytes
0x18001324e  xor     ecx, ecx; uFlags
0x180013250  call    cs:__imp_LocalAlloc
0x180013256  mov     rdi, rax
0x180013259  test    rax, rax
0x18001325c  jz      loc_180013309
0x180013262  mov     ecx, [rsp+180h+var_140]
0x180013266  lea     rax, [rsp+180h+var_140]
0x18001326b  mov     edx, [rbx+8B8h]; JobId
0x180013271  lea     r8d, [rsi+1]; Level
0x180013275  mov     [rsp+180h+pcbNeeded], rax; pcbNeeded
0x18001327a  mov     r9, rdi; pJob
0x18001327d  mov     [rsp+180h+cbBuf], ecx; cbBuf
0x180013281  mov     rcx, [rbx+18h]; hPrinter
0x180013285  call    cs:__imp_GetJobW
0x18001328b  test    eax, eax
0x18001328d  jz      short loc_180013300
0x18001328f  cmp     [rdi+18h], rsi
0x180013293  jz      short loc_180013300
0x180013295  xor     edx, edx; Val
0x180013297  lea     rcx, [rsp+180h+MultiByteStr]; void *
0x18001329c  mov     r8d, 100h; Size
0x1800132a2  call    memset_0
0x1800132a7  mov     r8, [rdi+18h]; lpWideCharStr
0x1800132ab  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800132af  inc     r9
0x1800132b2  cmp     [r8+r9*2], si
0x1800132b7  jnz     short loc_1800132AF
0x1800132b9  mov     [rsp+180h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x1800132be  lea     rax, [rsp+180h+MultiByteStr]
0x1800132c3  mov     [rsp+180h+lpDefaultChar], rsi; lpDefaultChar
0x1800132c8  inc     r9d; cchWideChar
0x1800132cb  mov     dword ptr [rsp+180h+pcbNeeded], 100h; cbMultiByte
0x1800132d3  xor     edx, edx; dwFlags
0x1800132d5  xor     ecx, ecx; CodePage
0x1800132d7  mov     qword ptr [rsp+180h+cbBuf], rax; lpMultiByteStr
0x1800132dc  call    cs:__imp_WideCharToMultiByte
0x1800132e2  mov     r9d, 100h
0x1800132e8  mov     [rbp+80h+var_21], sil
0x1800132ec  lea     r8, [rsp+180h+MultiByteStr]
0x1800132f1  mov     rcx, rbx
0x1800132f4  lea     rdx, DSC_User; "%%%%For: %s\r\n"
0x1800132fb  call    BSendClean7BitDSC
0x180013300  mov     rcx, rdi; hMem
0x180013303  call    cs:__imp_LocalFree
0x180013309  xor     edx, edx
0x18001330b  mov     rcx, rbx
0x18001330e  call    BSendBoundingBox
0x180013313  mov     rax, [rbx+60h]
0x180013317  lea     rcx, DSC_One; "1"
0x18001331e  lea     r8, DSC_Atend; "(atend)"
0x180013325  mov     edx, 3
0x18001332a  cmp     [rax+7Ch], r15d
0x18001332e  cmovz   r8, rcx
0x180013332  mov     rcx, rbx
0x180013335  call    DSCSend
0x18001333a  cmp     [rbx+2CCh], esi
0x180013340  lea     rax, DSC_OrientLandscape; "Landscape"
0x180013347  lea     r8, DSC_OrientPortrait; "Portrait"
0x18001334e  mov     edx, 8
0x180013353  cmovnz  r8, rax
0x180013357  mov     rcx, rbx
0x18001335a  call    DSCSend
0x18001335f  mov     rax, [rbx+60h]
0x180013363  cmp     [rax+7Ch], esi
0x180013366  jz      short loc_180013377
0x180013368  lea     r8, DSC_PageOrderAscend; "Ascend"
0x18001336f  cmp     [rax+88h], esi
0x180013375  jz      short loc_18001337E
0x180013377  lea     r8, DSC_PageOrderSpecial; "Special"
0x18001337e  mov     edx, 7
0x180013383  mov     rcx, rbx
0x180013386  call    DSCSend
0x18001338b  lea     rdx, DSC_DocNeededResAtend; "%%%%DocumentNeededResources: (atend)\r"...
0x180013392  mov     rcx, rbx
0x180013395  call    DSCSend
0x18001339a  lea     rdx, DSC_DocSuppliedResAtend; "%%%%DocumentSuppliedResources: (atend)"...
0x1800133a1  mov     rcx, rbx
0x1800133a4  call    DSCSend
0x1800133a9  cmp     [rbx+0A6h], si
0x1800133b0  jz      short loc_1800133C1
0x1800133b2  lea     rdx, DSC_Netware; "%%%%P8BIT\r\n"
0x1800133b9  mov     rcx, rbx
0x1800133bc  call    DSCSend
0x1800133c1  movzx   ecx, word ptr [rbx+0A6h]
0x1800133c8  mov     edx, 0FFFDh
0x1800133cd  movzx   eax, cx
0x1800133d0  sub     ax, r15w
0x1800133d4  test    dx, ax
0x1800133d7  jz      short loc_1800133F1
0x1800133d9  cmp     cx, 10h
0x1800133dd  lea     rdx, DSC_7Bit; "%%%%DocumentData: Clean7Bit\r\n"
0x1800133e4  lea     rax, DSC_Binary; "%%%%DocumentData: Binary\r\n"
0x1800133eb  cmovz   rdx, rax
0x1800133ef  jmp     short loc_1800133F8
0x1800133f1  lea     rdx, DSC_8Bit; "%%%%DocumentData: Clean8Bit\r\n"
0x1800133f8  mov     rcx, rbx
0x1800133fb  call    DSCSend
0x180013400  lea     rdx, DSC_TargetDevice; "%%%%TargetDevice: "
0x180013407  mov     rcx, rbx
0x18001340a  call    DSCSend
0x18001340f  mov     rdx, [rbx+860h]
0x180013416  mov     rcx, rbx
0x180013419  add     rdx, 20h ; ' '
0x18001341d  call    OPSendInvocation
0x180013422  mov     r8d, 1
0x180013428  lea     rdx, gstrSpace; " "
0x18001342f  mov     rcx, rbx
0x180013432  call    OPRawPortWrite
0x180013437  mov     rdx, [rbx+860h]
0x18001343e  mov     rcx, rbx
0x180013441  add     rdx, 18h
0x180013445  call    OPSendInvocation
0x18001344a  mov     r8d, r15d
0x18001344d  lea     rdx, gstrCRLF; "\r\n"
0x180013454  mov     rcx, rbx
0x180013457  call    OPRawPortWrite
0x18001345c  mov     r8, [rbx+60h]
0x180013460  lea     rdx, DSC_LanguageLevel; "%%%%LanguageLevel: %d\r\n"
0x180013467  mov     rcx, rbx
0x18001346a  mov     r8d, [r8+8Ch]
0x180013471  call    DSCSend
0x180013476  mov     edx, 15h
0x18001347b  mov     rcx, rbx
0x18001347e  call    DSCSend
0x180013483  mov     edx, 0Bh
0x180013488  mov     rcx, rbx
0x18001348b  call    DSCSend
0x180013490  mov     edx, 0Ch
0x180013495  mov     rcx, rbx
0x180013498  call    DSCSend
0x18001349d  mov     edx, 6Ah ; 'j'
0x1800134a2  mov     rcx, rbx
0x1800134a5  call    BSendBoundingBox
0x1800134aa  mov     rcx, rbx
0x1800134ad  call    BSendViewingOrientation
0x1800134b2  mov     rcx, rbx
0x1800134b5  call    DwGetOrientIndex
0x1800134ba  mov     edx, 0Dh
0x1800134bf  mov     [rbx+888h], eax
0x1800134c5  call    DSCSend
0x1800134ca  cmp     [rbx+0D70h], esi
0x1800134d0  mov     eax, esi
0x1800134d2  setz    al
0x1800134d5  mov     rcx, [rbp+80h+var_20]
0x1800134d9  xor     rcx, rsp; StackCookie
0x1800134dc  call    __security_check_cookie
0x1800134e1  lea     r11, [rsp+180h+var_10]
0x1800134e9  mov     rbx, [r11+28h]
0x1800134ed  mov     rsi, [r11+30h]
0x1800134f1  mov     rsp, r11
0x1800134f4  pop     r15
0x1800134f6  pop     rdi
0x1800134f7  pop     rbp
0x1800134f8  retn
```
