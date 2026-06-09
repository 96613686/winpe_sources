# BSendDocumentHeader

- ea: `0x180013780`
- end: `0x180013b62`
- name: `BSendDocumentHeader`
- size: `994`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18001502c`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180013220`
- `0x1800133f8`
- `0x180013780`
- `0x180014f90`
- `0x180014fe0`
- `0x1800170a0`
- `0x1800173f8`
- `0x18001b388`

## import_xrefs

- `WINSPOOL!GetJobW` at `0x18001387c`
- `WINSPOOL!GetJobW` at `0x1800138db`
- `WINSPOOL!GetJobW` at `0x18001387c`
- `WINSPOOL!GetJobW` at `0x1800138db`
- `KERNEL32!WideCharToMultiByte` at `0x180013938`
- `KERNEL32!WideCharToMultiByte` at `0x180013938`
- `KERNEL32!LocalFree` at `0x180013965`
- `KERNEL32!LocalFree` at `0x180013965`
- `KERNEL32!LocalAlloc` at `0x1800138a0`
- `KERNEL32!LocalAlloc` at `0x1800138a0`
- `GDI32!EngQueryLocalTime` at `0x180013810`
- `GDI32!EngQueryLocalTime` at `0x180013810`

## string_xrefs

- `0x1800137fc`: `%%%%Creator: PScript5.dll Version 5.2.2\n`

## pseudocode

```c
_BOOL8 __fastcall BSendDocumentHeader(__int64 a1)
{
  __int64 v1; // rax
  const char *v2; // r8
  HLOCAL v4; // rdi
  const WCHAR *v5; // r8
  __int64 v6; // r9
  const char *v7; // r8
  const char *v8; // r8
  __int64 v9; // rax
  const char *v10; // r8
  __int16 v11; // cx
  const char *v12; // rdx
  __int64 v13; // rcx
  DWORD pcbNeeded; // [rsp+40h] [rbp-C0h] BYREF
  _ENG_TIME_FIELDS v16; // [rsp+48h] [rbp-B8h] BYREF
  CHAR MultiByteStr[256]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = *(_QWORD *)(a1 + 96);
  v2 = " EPSF-3.0";
  pcbNeeded = 0;
  v16 = 0;
  if ( *(_DWORD *)(v1 + 124) != 2 )
    v2 = (const char *)&dword_1800644DC;
  DSCSend(a1, (const char *)2, v2);
  BSendClean7BitDSC(a1, "%%%%Title: %s\r\n", (char *)(a1 + 2904), 128);
  DSCSend(a1, "%%%%Creator: PScript5.dll Version 5.2.2\r\n");
  EngQueryLocalTime(&v16);
  DSCSend(
    a1,
    "%%%%CreationDate: %d/%d/%d %d:%d:%d\r\n",
    v16.usMonth,
    v16.usDay,
    v16.usYear,
    v16.usHour,
    v16.usMinute,
    v16.usSecond);
  if ( !GetJobW(*(HANDLE *)(a1 + 24), *(_DWORD *)(a1 + 2232), 1u, 0, 0, &pcbNeeded) )
  {
    if ( pcbNeeded )
    {
      v4 = LocalAlloc(0, pcbNeeded);
      if ( v4 )
      {
        if ( GetJobW(*(HANDLE *)(a1 + 24), *(_DWORD *)(a1 + 2232), 1u, (LPBYTE)v4, pcbNeeded, &pcbNeeded)
          && *((_QWORD *)v4 + 3) )
        {
          memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
          v5 = (const WCHAR *)*((_QWORD *)v4 + 3);
          v6 = -1;
          do
            ++v6;
          while ( v5[v6] );
          WideCharToMultiByte(0, 0, v5, v6 + 1, MultiByteStr, 256, 0, 0);
          MultiByteStr[255] = 0;
          BSendClean7BitDSC(a1, "%%%%For: %s\r\n", MultiByteStr, 256);
        }
        LocalFree(v4);
      }
    }
  }
  BSendBoundingBox(a1, 0);
  v7 = "(atend)";
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) == 2 )
    v7 = "1";
  DSCSend(a1, (const char *)3, v7);
  v8 = "Portrait";
  if ( *(_DWORD *)(a1 + 716) )
    v8 = "Landscape";
  DSCSend(a1, (const char *)8, v8);
  v9 = *(_QWORD *)(a1 + 96);
  if ( !*(_DWORD *)(v9 + 124) || (v10 = "Ascend", *(_DWORD *)(v9 + 136)) )
    v10 = "Special";
  DSCSend(a1, (const char *)7, v10);
  DSCSend(a1, "%%%%DocumentNeededResources: (atend)\r\n");
  DSCSend(a1, "%%%%DocumentSuppliedResources: (atend)\r\n");
  if ( *(_WORD *)(a1 + 166) )
    DSCSend(a1, "%%%%P8BIT\r\n");
  v11 = *(_WORD *)(a1 + 166);
  if ( ((v11 - 2) & 0xFFFD) != 0 )
  {
    v12 = "%%%%DocumentData: Clean7Bit\r\n";
    if ( v11 == 16 )
      v12 = "%%%%DocumentData: Binary\r\n";
  }
  else
  {
    v12 = "%%%%DocumentData: Clean8Bit\r\n";
  }
  DSCSend(a1, v12);
  DSCSend(a1, "%%%%TargetDevice: ");
  OPSendInvocation(a1, (unsigned int *)(*(_QWORD *)(a1 + 2144) + 32LL));
  OPRawPortWrite(a1, " ", 1u);
  OPSendInvocation(a1, (unsigned int *)(*(_QWORD *)(a1 + 2144) + 24LL));
  OPRawPortWrite(a1, "\r\n", 2u);
  DSCSend(a1, "%%%%LanguageLevel: %d\r\n", *(_DWORD *)(*(_QWORD *)(a1 + 96) + 140LL));
  DSCSend(a1, (const char *)0x15);
  DSCSend(a1, (const char *)0xB);
  DSCSend(a1, (const char *)0xC);
  BSendBoundingBox(a1, 106);
  BSendViewingOrientation(a1);
  *(_DWORD *)(a1 + 2184) = DwGetOrientIndex(a1);
  DSCSend(v13, (const char *)0xD);
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x180013780  mov     [rsp-8+arg_8], rbx
0x180013785  mov     [rsp-8+arg_10], rsi
0x18001378a  push    rbp
0x18001378b  push    rdi
0x18001378c  push    r15
0x18001378e  lea     rbp, [rsp-70h]
0x180013793  sub     rsp, 170h
0x18001379a  mov     rax, cs:__security_cookie
0x1800137a1  xor     rax, rsp
0x1800137a4  mov     [rbp+80h+var_20], rax
0x1800137a8  mov     rax, [rcx+60h]
0x1800137ac  lea     r8, DSC_EPSF; " EPSF-3.0"
0x1800137b3  xor     esi, esi
0x1800137b5  mov     rbx, rcx
0x1800137b8  xorps   xmm0, xmm0
0x1800137bb  mov     [rsp+180h+var_140], esi
0x1800137bf  movups  xmmword ptr [rsp+180h+var_138.usYear], xmm0
0x1800137c4  lea     rcx, dword_1800644DC
0x1800137cb  lea     r15d, [rsi+2]
0x1800137cf  cmp     [rax+7Ch], r15d
0x1800137d3  mov     edx, r15d
0x1800137d6  cmovnz  r8, rcx
0x1800137da  mov     rcx, rbx
0x1800137dd  call    DSCSend
0x1800137e2  lea     r8, [rbx+0B58h]
0x1800137e9  mov     rcx, rbx
0x1800137ec  lea     r9d, [r15+7Eh]
0x1800137f0  lea     rdx, DSC_Title; "%%%%Title: %s\r\n"
0x1800137f7  call    BSendClean7BitDSC
0x1800137fc  lea     rdx, DSC_Creator; "%%%%Creator: PScript5.dll Version 5.2.2"...
0x180013803  mov     rcx, rbx
0x180013806  call    DSCSend
0x18001380b  lea     rcx, [rsp+180h+var_138]; PENG_TIME_FIELDS
0x180013810  call    cs:__imp_EngQueryLocalTime
0x180013817  nop     dword ptr [rax+rax+00h]
0x18001381c  movzx   ecx, [rsp+180h+var_138.usMinute]
0x180013821  movzx   edx, [rsp+180h+var_138.usHour]
0x180013826  movzx   eax, [rsp+180h+var_138.usSecond]
0x18001382b  movzx   r10d, [rsp+180h+var_138.usYear]
0x180013831  movzx   r9d, [rsp+180h+var_138.usDay]
0x180013837  movzx   r8d, [rsp+180h+var_138.usMonth]
0x18001383d  mov     dword ptr [rsp+180h+lpUsedDefaultChar], eax
0x180013841  mov     dword ptr [rsp+180h+lpDefaultChar], ecx
0x180013845  mov     rcx, rbx
0x180013848  mov     dword ptr [rsp+180h+pcbNeeded], edx
0x18001384c  lea     rdx, DSC_CreationDate; "%%%%CreationDate: %d/%d/%d %d:%d:%d\r\n"
0x180013853  mov     [rsp+180h+cbBuf], r10d
0x180013858  call    DSCSend
0x18001385d  mov     edx, [rbx+8B8h]; JobId
0x180013863  lea     rax, [rsp+180h+var_140]
0x180013868  mov     rcx, [rbx+18h]; hPrinter
0x18001386c  lea     r8d, [rsi+1]; Level
0x180013870  mov     [rsp+180h+pcbNeeded], rax; pcbNeeded
0x180013875  xor     r9d, r9d; pJob
0x180013878  mov     [rsp+180h+cbBuf], esi; cbBuf
0x18001387c  call    cs:__imp_GetJobW
0x180013883  nop     dword ptr [rax+rax+00h]
0x180013888  test    eax, eax
0x18001388a  jnz     loc_180013971
0x180013890  mov     eax, [rsp+180h+var_140]
0x180013894  test    eax, eax
0x180013896  jz      loc_180013971
0x18001389c  mov     edx, eax; uBytes
0x18001389e  xor     ecx, ecx; uFlags
0x1800138a0  call    cs:__imp_LocalAlloc
0x1800138a7  nop     dword ptr [rax+rax+00h]
0x1800138ac  mov     rdi, rax
0x1800138af  test    rax, rax
0x1800138b2  jz      loc_180013971
0x1800138b8  mov     ecx, [rsp+180h+var_140]
0x1800138bc  lea     rax, [rsp+180h+var_140]
0x1800138c1  mov     edx, [rbx+8B8h]; JobId
0x1800138c7  lea     r8d, [rsi+1]; Level
0x1800138cb  mov     [rsp+180h+pcbNeeded], rax; pcbNeeded
0x1800138d0  mov     r9, rdi; pJob
0x1800138d3  mov     [rsp+180h+cbBuf], ecx; cbBuf
0x1800138d7  mov     rcx, [rbx+18h]; hPrinter
0x1800138db  call    cs:__imp_GetJobW
0x1800138e2  nop     dword ptr [rax+rax+00h]
0x1800138e7  test    eax, eax
0x1800138e9  jz      short loc_180013962
0x1800138eb  cmp     [rdi+18h], rsi
0x1800138ef  jz      short loc_180013962
0x1800138f1  xor     edx, edx; Val
0x1800138f3  lea     rcx, [rsp+180h+MultiByteStr]; void *
0x1800138f8  mov     r8d, 100h; Size
0x1800138fe  call    memset_0
0x180013903  mov     r8, [rdi+18h]; lpWideCharStr
0x180013907  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001390b  inc     r9
0x18001390e  cmp     [r8+r9*2], si
0x180013913  jnz     short loc_18001390B
0x180013915  mov     [rsp+180h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x18001391a  lea     rax, [rsp+180h+MultiByteStr]
0x18001391f  mov     [rsp+180h+lpDefaultChar], rsi; lpDefaultChar
0x180013924  inc     r9d; cchWideChar
0x180013927  mov     dword ptr [rsp+180h+pcbNeeded], 100h; cbMultiByte
0x18001392f  xor     edx, edx; dwFlags
0x180013931  xor     ecx, ecx; CodePage
0x180013933  mov     qword ptr [rsp+180h+cbBuf], rax; lpMultiByteStr
0x180013938  call    cs:__imp_WideCharToMultiByte
0x18001393f  nop     dword ptr [rax+rax+00h]
0x180013944  mov     r9d, 100h
0x18001394a  mov     [rbp+80h+var_21], sil
0x18001394e  lea     r8, [rsp+180h+MultiByteStr]
0x180013953  mov     rcx, rbx
0x180013956  lea     rdx, DSC_User; "%%%%For: %s\r\n"
0x18001395d  call    BSendClean7BitDSC
0x180013962  mov     rcx, rdi; hMem
0x180013965  call    cs:__imp_LocalFree
0x18001396c  nop     dword ptr [rax+rax+00h]
0x180013971  xor     edx, edx
0x180013973  mov     rcx, rbx
0x180013976  call    BSendBoundingBox
0x18001397b  mov     rax, [rbx+60h]
0x18001397f  lea     rcx, DSC_One; "1"
0x180013986  lea     r8, DSC_Atend; "(atend)"
0x18001398d  mov     edx, 3
0x180013992  cmp     [rax+7Ch], r15d
0x180013996  cmovz   r8, rcx
0x18001399a  mov     rcx, rbx
0x18001399d  call    DSCSend
0x1800139a2  cmp     [rbx+2CCh], esi
0x1800139a8  lea     rax, DSC_OrientLandscape; "Landscape"
0x1800139af  lea     r8, DSC_OrientPortrait; "Portrait"
0x1800139b6  mov     edx, 8
0x1800139bb  cmovnz  r8, rax
0x1800139bf  mov     rcx, rbx
0x1800139c2  call    DSCSend
0x1800139c7  mov     rax, [rbx+60h]
0x1800139cb  cmp     [rax+7Ch], esi
0x1800139ce  jz      short loc_1800139DF
0x1800139d0  lea     r8, DSC_PageOrderAscend; "Ascend"
0x1800139d7  cmp     [rax+88h], esi
0x1800139dd  jz      short loc_1800139E6
0x1800139df  lea     r8, DSC_PageOrderSpecial; "Special"
0x1800139e6  mov     edx, 7
0x1800139eb  mov     rcx, rbx
0x1800139ee  call    DSCSend
0x1800139f3  lea     rdx, DSC_DocNeededResAtend; "%%%%DocumentNeededResources: (atend)\r"...
0x1800139fa  mov     rcx, rbx
0x1800139fd  call    DSCSend
0x180013a02  lea     rdx, DSC_DocSuppliedResAtend; "%%%%DocumentSuppliedResources: (atend)"...
0x180013a09  mov     rcx, rbx
0x180013a0c  call    DSCSend
0x180013a11  cmp     [rbx+0A6h], si
0x180013a18  jz      short loc_180013A29
0x180013a1a  lea     rdx, DSC_Netware; "%%%%P8BIT\r\n"
0x180013a21  mov     rcx, rbx
0x180013a24  call    DSCSend
0x180013a29  movzx   ecx, word ptr [rbx+0A6h]
0x180013a30  mov     edx, 0FFFDh
0x180013a35  movzx   eax, cx
0x180013a38  sub     ax, r15w
0x180013a3c  test    dx, ax
0x180013a3f  jz      short loc_180013A59
0x180013a41  cmp     cx, 10h
0x180013a45  lea     rdx, DSC_7Bit; "%%%%DocumentData: Clean7Bit\r\n"
0x180013a4c  lea     rax, DSC_Binary; "%%%%DocumentData: Binary\r\n"
0x180013a53  cmovz   rdx, rax
0x180013a57  jmp     short loc_180013A60
0x180013a59  lea     rdx, DSC_8Bit; "%%%%DocumentData: Clean8Bit\r\n"
0x180013a60  mov     rcx, rbx
0x180013a63  call    DSCSend
0x180013a68  lea     rdx, DSC_TargetDevice; "%%%%TargetDevice: "
0x180013a6f  mov     rcx, rbx
0x180013a72  call    DSCSend
0x180013a77  mov     rdx, [rbx+860h]
0x180013a7e  mov     rcx, rbx
0x180013a81  add     rdx, 20h ; ' '
0x180013a85  call    OPSendInvocation
0x180013a8a  mov     r8d, 1
0x180013a90  lea     rdx, gstrSpace; " "
0x180013a97  mov     rcx, rbx
0x180013a9a  call    OPRawPortWrite
0x180013a9f  mov     rdx, [rbx+860h]
0x180013aa6  mov     rcx, rbx
0x180013aa9  add     rdx, 18h
0x180013aad  call    OPSendInvocation
0x180013ab2  mov     r8d, r15d
0x180013ab5  lea     rdx, gstrCRLF; "\r\n"
0x180013abc  mov     rcx, rbx
0x180013abf  call    OPRawPortWrite
0x180013ac4  mov     r8, [rbx+60h]
0x180013ac8  lea     rdx, DSC_LanguageLevel; "%%%%LanguageLevel: %d\r\n"
0x180013acf  mov     rcx, rbx
0x180013ad2  mov     r8d, [r8+8Ch]
0x180013ad9  call    DSCSend
0x180013ade  mov     edx, 15h
0x180013ae3  mov     rcx, rbx
0x180013ae6  call    DSCSend
0x180013aeb  mov     edx, 0Bh
0x180013af0  mov     rcx, rbx
0x180013af3  call    DSCSend
0x180013af8  mov     edx, 0Ch
0x180013afd  mov     rcx, rbx
0x180013b00  call    DSCSend
0x180013b05  mov     edx, 6Ah ; 'j'
0x180013b0a  mov     rcx, rbx
0x180013b0d  call    BSendBoundingBox
0x180013b12  mov     rcx, rbx
0x180013b15  call    BSendViewingOrientation
0x180013b1a  mov     rcx, rbx
0x180013b1d  call    DwGetOrientIndex
0x180013b22  mov     edx, 0Dh
0x180013b27  mov     [rbx+888h], eax
0x180013b2d  call    DSCSend
0x180013b32  cmp     [rbx+0D70h], esi
0x180013b38  mov     eax, esi
0x180013b3a  setz    al
0x180013b3d  mov     rcx, [rbp+80h+var_20]
0x180013b41  xor     rcx, rsp; StackCookie
0x180013b44  call    __security_check_cookie
0x180013b49  lea     r11, [rsp+180h+var_10]
0x180013b51  mov     rbx, [r11+28h]
0x180013b55  mov     rsi, [r11+30h]
0x180013b59  mov     rsp, r11
0x180013b5c  pop     r15
0x180013b5e  pop     rdi
0x180013b5f  pop     rbp
0x180013b60  retn
```
