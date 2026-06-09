# Appx::Packaging::AppxDigitalSignatureEditor::InitializeZipEditor(IStream *)

- ea: `0x18000539c`
- end: `0x18000569b`
- name: `?InitializeZipEditor@AppxDigitalSignatureEditor@Packaging@Appx@@IEAAJPEAUIStream@@@Z`
- size: `767`
- prototype: `__int64 __fastcall(Appx::Packaging::AppxDigitalSignatureEditor *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003800`

## callees

- `0x1800049e8`
- `0x180004bd4`
- `0x180004f9c`
- `0x18000539c`
- `0x1800056a4`
- `0x180005704`
- `0x180005794`
- `0x1800057a8`
- `0x180005830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005644`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000565f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005681`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005644`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000565f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005681`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18000546a`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800054f3`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800055ef`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18000546a`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800054f3`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800055ef`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800054ac`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800054ac`

## string_xrefs

- `0x18000544e`: `[Content_Types].xml`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::AppxDigitalSignatureEditor::InitializeZipEditor(
        Appx::Packaging::AppxDigitalSignatureEditor *this,
        struct IStream *a2)
{
  char *v2; // r13
  int v4; // ebx
  Appx::Packaging::ZipEditor *v5; // rcx
  int LastFileItem; // eax
  bool HasCurrent; // al
  Appx::Packaging::ZipFileItem **v8; // r15
  Appx::Packaging::ZipFileItem **v9; // r14
  int Current; // eax
  Appx::Packaging::ZipFileItem *v11; // rbx
  const CHAR *v12; // r12
  int CentralFileHeader; // eax
  struct Appx::Packaging::ZipCentralFileHeader *v14; // rbx
  __int64 v15; // rax
  Appx::Packaging::ZipFileItem **v16; // r8
  DWORD v18; // ecx
  DWORD v19; // ecx
  DWORD v20; // ecx
  struct Appx::Packaging::ZipFileItem *v21; // [rsp+30h] [rbp-10h] BYREF
  Appx::Packaging::ZipFileItem **v22; // [rsp+38h] [rbp-8h]
  bool v23; // [rsp+80h] [rbp+40h] BYREF
  Appx::Packaging::ZipFileItemEnumerator *v24; // [rsp+90h] [rbp+50h] BYREF
  struct Appx::Packaging::ZipCentralFileHeader *v25; // [rsp+98h] [rbp+58h] BYREF

  v2 = (char *)this + 8;
  v4 = Appx::Packaging::ZipEditor::Create(a2, 0, (char *)this + 8);
  if ( v4 < 0 )
  {
    v19 = (unsigned __int16)v4;
    if ( (v4 & 0x1FFF0000) != 0x70000 )
      v19 = v4;
    SetLastError(v19);
  }
  else
  {
    v5 = *(Appx::Packaging::ZipEditor **)v2;
    v24 = 0;
    LastFileItem = Appx::Packaging::ZipEditor::GetLastFileItem(v5, &v24);
    v4 = LastFileItem;
    if ( LastFileItem >= 0 )
    {
      v21 = 0;
      HasCurrent = Appx::Packaging::ZipFileItemEnumerator::HasCurrent(v24);
      v23 = HasCurrent;
      v22 = (Appx::Packaging::ZipFileItem **)((char *)this + 24);
      v8 = (Appx::Packaging::ZipFileItem **)((char *)this + 40);
      v9 = (Appx::Packaging::ZipFileItem **)((char *)this + 24);
      while ( HasCurrent )
      {
        v9 = (Appx::Packaging::ZipFileItem **)((char *)this + 24);
        v8 = (Appx::Packaging::ZipFileItem **)((char *)this + 40);
        if ( *((_QWORD *)this + 3) && *v8 )
          goto LABEL_18;
        Current = Appx::Packaging::ZipFileItemEnumerator::GetCurrent(v24, &v21);
        v4 = Current;
        if ( Current < 0 )
        {
          v18 = (unsigned __int16)Current;
          if ( (Current & 0x1FFF0000) != 0x70000 )
            v18 = Current;
          goto LABEL_27;
        }
        v11 = v21;
        v12 = (const CHAR *)*((_QWORD *)v21 + 8);
        if ( *v9 || CompareStringA(0x7Fu, 1u, v12, -1, "[Content_Types].xml", -1) != 2 )
        {
          if ( *v8 || CompareStringA(0x7Fu, 1u, v12, -1, "AppxSignature.p7x", -1) != 2 )
          {
            if ( !*((_QWORD *)this + 4) && CompareStringA(0x7Fu, 1u, v12, -1, "AppxMetadata/CodeIntegrity.cat", -1) == 2 )
              *((_QWORD *)this + 4) = v11;
          }
          else
          {
            *v8 = v11;
          }
        }
        else
        {
          *v9 = v11;
          v25 = 0;
          CentralFileHeader = Appx::Packaging::ZipFileItem::GetCentralFileHeader(v11, &v25);
          v4 = CentralFileHeader;
          if ( CentralFileHeader < 0 )
          {
            v20 = (unsigned __int16)CentralFileHeader;
            if ( (CentralFileHeader & 0x1FFF0000) != 0x70000 )
              v20 = CentralFileHeader;
            SetLastError(v20);
            Common::AutoPtrDeallocate<Appx::Packaging::ZipCentralFileHeader>(v25);
            goto LABEL_23;
          }
          v14 = v25;
          if ( !DosDateTimeToFileTime(*((_WORD *)v25 + 4), *((_WORD *)v25 + 3), (LPFILETIME)this + 6) )
          {
            *((_QWORD *)this + 6) = 0;
            SetLastError(0);
          }
          Common::AutoPtrDeallocate<Appx::Packaging::ZipCentralFileHeader>(v14);
        }
        Appx::Packaging::ZipFileItemEnumerator::MovePrevious(v24, &v23);
        HasCurrent = v23;
      }
      if ( *v8 )
      {
LABEL_18:
        v15 = *(_QWORD *)(*(_QWORD *)v2 + 24LL);
        if ( !v15 || *v8 != *(Appx::Packaging::ZipFileItem **)(*(_QWORD *)(*(_QWORD *)v2 + 8LL) + 8 * (v15 - 1)) )
        {
LABEL_30:
          SetLastError(0xBu);
          v4 = -2147024885;
          goto LABEL_23;
        }
        v16 = v22;
      }
      else
      {
        v16 = v9;
      }
      if ( *v16 )
      {
        v4 = 0;
        goto LABEL_23;
      }
      goto LABEL_30;
    }
    v18 = (unsigned __int16)LastFileItem;
    if ( (LastFileItem & 0x1FFF0000) != 0x70000 )
      v18 = LastFileItem;
LABEL_27:
    SetLastError(v18);
LABEL_23:
    Common::AutoPtrDeallocate<Appx::Packaging::ZipFileItemEnumerator>(v24);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000539c  push    rbp
0x18000539e  push    rbx
0x18000539f  push    rsi
0x1800053a0  push    r12
0x1800053a2  push    r13
0x1800053a4  push    r14
0x1800053a6  push    r15
0x1800053a8  mov     rbp, rsp
0x1800053ab  sub     rsp, 40h
0x1800053af  mov     rax, rdx
0x1800053b2  lea     r13, [rcx+8]
0x1800053b6  mov     rsi, rcx
0x1800053b9  mov     r8, r13
0x1800053bc  mov     rcx, rax
0x1800053bf  xor     edx, edx
0x1800053c1  call    ?Create@ZipEditor@Packaging@Appx@@SAJPEAUIStream@@PEBGAEAV?$AutoPtr@VZipEditor@Packaging@Appx@@$1??$AutoPtrDeallocate@VZipEditor@Packaging@Appx@@@Common@@YAXPEAV123@@Z@Common@@@Z; Appx::Packaging::ZipEditor::Create(IStream *,ushort const *,Common::AutoPtr<Appx::Packaging::ZipEditor,&Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(Appx::Packaging::ZipEditor *)> &)
0x1800053c6  xor     r12d, r12d
0x1800053c9  mov     ebx, eax
0x1800053cb  test    eax, eax
0x1800053cd  js      loc_18000562F
0x1800053d3  mov     rcx, [r13+0]; this
0x1800053d7  lea     rdx, [rbp+arg_10]; struct Appx::Packaging::ZipFileItemEnumerator **
0x1800053db  mov     [rbp+arg_10], r12
0x1800053df  call    ?GetLastFileItem@ZipEditor@Packaging@Appx@@QEAAJPEAPEAVZipFileItemEnumerator@23@@Z; Appx::Packaging::ZipEditor::GetLastFileItem(Appx::Packaging::ZipFileItemEnumerator * *)
0x1800053e4  mov     ebx, eax
0x1800053e6  test    eax, eax
0x1800053e8  js      loc_18000557B
0x1800053ee  mov     rcx, [rbp+arg_10]; this
0x1800053f2  mov     [rbp+var_10], r12
0x1800053f6  call    ?HasCurrent@ZipFileItemEnumerator@Packaging@Appx@@QEAA_NXZ; Appx::Packaging::ZipFileItemEnumerator::HasCurrent(void)
0x1800053fb  lea     r8, [rsi+18h]
0x1800053ff  mov     [rbp+arg_0], al
0x180005402  mov     [rbp+var_8], r8
0x180005406  lea     r15, [rsi+28h]
0x18000540a  mov     r14, r8
0x18000540d  test    al, al
0x18000540f  jz      loc_180005523
0x180005415  lea     r14, [rsi+18h]
0x180005419  lea     r15, [rsi+28h]
0x18000541d  cmp     [r14], r12
0x180005420  jnz     loc_18000559E
0x180005426  mov     rcx, [rbp+arg_10]; this
0x18000542a  lea     rdx, [rbp+var_10]; struct Appx::Packaging::ZipFileItem **
0x18000542e  call    ?GetCurrent@ZipFileItemEnumerator@Packaging@Appx@@QEAAJPEAPEAVZipFileItem@23@@Z; Appx::Packaging::ZipFileItemEnumerator::GetCurrent(Appx::Packaging::ZipFileItem * *)
0x180005433  mov     ebx, eax
0x180005435  test    eax, eax
0x180005437  js      loc_18000560D
0x18000543d  cmp     qword ptr [r14], 0
0x180005441  mov     rbx, [rbp+var_10]
0x180005445  mov     r12, [rbx+40h]
0x180005449  jnz     short loc_1800054CA
0x18000544b  or      ecx, 0FFFFFFFFh
0x18000544e  lea     rax, ?FileNameA@ContentTypes@Packaging@Appx@@3QBDB; "[Content_Types].xml"
0x180005455  mov     [rsp+40h+cchCount2], ecx; cchCount2
0x180005459  mov     r9d, ecx; cchCount1
0x18000545c  mov     r8, r12; lpString1
0x18000545f  mov     [rsp+40h+lpString2], rax; lpString2
0x180005464  lea     edx, [rcx+2]; dwCmpFlags
0x180005467  lea     ecx, [rdx+7Eh]; Locale
0x18000546a  call    cs:__imp_CompareStringA
0x180005471  nop     dword ptr [rax+rax+00h]
0x180005476  cmp     eax, 2
0x180005479  jnz     short loc_1800054CA
0x18000547b  lea     rdx, [rbp+arg_18]; struct Appx::Packaging::ZipCentralFileHeader **
0x18000547f  mov     [r14], rbx
0x180005482  mov     rcx, rbx; this
0x180005485  mov     [rbp+arg_18], 0
0x18000548d  call    ?GetCentralFileHeader@ZipFileItem@Packaging@Appx@@QEBAJPEAPEAUZipCentralFileHeader@23@@Z; Appx::Packaging::ZipFileItem::GetCentralFileHeader(Appx::Packaging::ZipCentralFileHeader * *)
0x180005492  mov     ebx, eax
0x180005494  test    eax, eax
0x180005496  js      loc_180005670
0x18000549c  mov     rbx, [rbp+arg_18]
0x1800054a0  lea     r8, [rsi+30h]; lpFileTime
0x1800054a4  movzx   edx, word ptr [rbx+6]; wFatTime
0x1800054a8  movzx   ecx, word ptr [rbx+8]; wFatDate
0x1800054ac  call    cs:__imp_DosDateTimeToFileTime
0x1800054b3  nop     dword ptr [rax+rax+00h]
0x1800054b8  test    eax, eax
0x1800054ba  jz      loc_180005655
0x1800054c0  mov     rcx, rbx; void *
0x1800054c3  call    ??$AutoPtrDeallocate@UZipCentralFileHeader@Packaging@Appx@@@Common@@YAXPEAUZipCentralFileHeader@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipCentralFileHeader>(Appx::Packaging::ZipCentralFileHeader *)
0x1800054c8  jmp     short loc_18000550B
0x1800054ca  cmp     qword ptr [r15], 0
0x1800054ce  jnz     loc_1800055C5
0x1800054d4  or      ecx, 0FFFFFFFFh
0x1800054d7  lea     rax, ?FileNameA@Signature@Packaging@Appx@@3QBDB; "AppxSignature.p7x"
0x1800054de  mov     [rsp+40h+cchCount2], ecx; cchCount2
0x1800054e2  mov     r9d, ecx; cchCount1
0x1800054e5  mov     r8, r12; lpString1
0x1800054e8  mov     [rsp+40h+lpString2], rax; lpString2
0x1800054ed  lea     edx, [rcx+2]; dwCmpFlags
0x1800054f0  lea     ecx, [rdx+7Eh]; Locale
0x1800054f3  call    cs:__imp_CompareStringA
0x1800054fa  nop     dword ptr [rax+rax+00h]
0x1800054ff  cmp     eax, 2
0x180005502  jnz     loc_1800055C5
0x180005508  mov     [r15], rbx
0x18000550b  mov     rcx, [rbp+arg_10]; this
0x18000550f  lea     rdx, [rbp+arg_0]; bool *
0x180005513  call    ?MovePrevious@ZipFileItemEnumerator@Packaging@Appx@@QEAAJPEA_N@Z; Appx::Packaging::ZipFileItemEnumerator::MovePrevious(bool *)
0x180005518  mov     al, [rbp+arg_0]
0x18000551b  xor     r12d, r12d
0x18000551e  jmp     loc_18000540D
0x180005523  cmp     [r15], r12
0x180005526  jz      loc_1800055C0
0x18000552c  mov     rdx, [r13+0]
0x180005530  mov     rax, [rdx+18h]
0x180005534  test    rax, rax
0x180005537  jz      short loc_1800055A8
0x180005539  lea     rcx, [rax-1]
0x18000553d  cmp     rcx, rax
0x180005540  jnb     loc_180005627
0x180005546  mov     rax, [rdx+8]
0x18000554a  mov     rax, [rax+rcx*8]
0x18000554e  cmp     [r15], rax
0x180005551  jnz     short loc_1800055A8
0x180005553  mov     r8, [rbp+var_8]
0x180005557  cmp     [r8], r12
0x18000555a  jz      short loc_1800055A8
0x18000555c  mov     ebx, r12d
0x18000555f  mov     rcx, [rbp+arg_10]
0x180005563  call    ??$AutoPtrDeallocate@VZipFileItemEnumerator@Packaging@Appx@@@Common@@YAXPEAVZipFileItemEnumerator@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipFileItemEnumerator>(Appx::Packaging::ZipFileItemEnumerator *)
0x180005568  mov     eax, ebx
0x18000556a  add     rsp, 40h
0x18000556e  pop     r15
0x180005570  pop     r14
0x180005572  pop     r13
0x180005574  pop     r12
0x180005576  pop     rsi
0x180005577  pop     rbx
0x180005578  pop     rbp
0x180005579  retn
0x18000557b  mov     ecx, eax
0x18000557d  and     ecx, 1FFF0000h
0x180005583  cmp     ecx, 70000h
0x180005589  movzx   ecx, ax
0x18000558c  jz      short loc_180005590
0x18000558e  mov     ecx, eax; dwErrCode
0x180005590  call    cs:__imp_SetLastError
0x180005597  nop     dword ptr [rax+rax+00h]
0x18000559c  jmp     short loc_18000555F
0x18000559e  cmp     [r15], r12
0x1800055a1  jnz     short loc_18000552C
0x1800055a3  jmp     loc_180005426
0x1800055a8  mov     ecx, 0Bh; dwErrCode
0x1800055ad  call    cs:__imp_SetLastError
0x1800055b4  nop     dword ptr [rax+rax+00h]
0x1800055b9  mov     ebx, 8007000Bh
0x1800055be  jmp     short loc_18000555F
0x1800055c0  mov     r8, r14
0x1800055c3  jmp     short loc_180005557
0x1800055c5  cmp     qword ptr [rsi+20h], 0
0x1800055ca  jnz     loc_18000550B
0x1800055d0  or      ecx, 0FFFFFFFFh
0x1800055d3  lea     rax, ?FileNameA@CodeIntegrity@Packaging@Appx@@3QBDB; "AppxMetadata/CodeIntegrity.cat"
0x1800055da  mov     [rsp+40h+cchCount2], ecx; cchCount2
0x1800055de  mov     r9d, ecx; cchCount1
0x1800055e1  mov     r8, r12; lpString1
0x1800055e4  mov     [rsp+40h+lpString2], rax; lpString2
0x1800055e9  lea     edx, [rcx+2]; dwCmpFlags
0x1800055ec  lea     ecx, [rdx+7Eh]; Locale
0x1800055ef  call    cs:__imp_CompareStringA
0x1800055f6  nop     dword ptr [rax+rax+00h]
0x1800055fb  cmp     eax, 2
0x1800055fe  jnz     loc_18000550B
0x180005604  mov     [rsi+20h], rbx
0x180005608  jmp     loc_18000550B
0x18000560d  and     eax, 1FFF0000h
0x180005612  movzx   ecx, bx
0x180005615  cmp     eax, 70000h
0x18000561a  jz      loc_180005590
0x180005620  mov     ecx, ebx
0x180005622  jmp     loc_180005590
0x180005627  mov     rax, r12
0x18000562a  jmp     loc_18000554E
0x18000562f  mov     ecx, ebx
0x180005631  and     ecx, 1FFF0000h
0x180005637  cmp     ecx, 70000h
0x18000563d  movzx   ecx, bx
0x180005640  jz      short loc_180005644
0x180005642  mov     ecx, ebx; dwErrCode
0x180005644  call    cs:__imp_SetLastError
0x18000564b  nop     dword ptr [rax+rax+00h]
0x180005650  jmp     loc_180005568
0x180005655  xor     ecx, ecx; dwErrCode
0x180005657  mov     qword ptr [rsi+30h], 0
0x18000565f  call    cs:__imp_SetLastError
0x180005666  nop     dword ptr [rax+rax+00h]
0x18000566b  jmp     loc_1800054C0
0x180005670  and     eax, 1FFF0000h
0x180005675  movzx   ecx, bx
0x180005678  cmp     eax, 70000h
0x18000567d  jz      short loc_180005681
0x18000567f  mov     ecx, ebx; dwErrCode
0x180005681  call    cs:__imp_SetLastError
0x180005688  nop     dword ptr [rax+rax+00h]
0x18000568d  mov     rcx, [rbp+arg_18]; void *
0x180005691  call    ??$AutoPtrDeallocate@UZipCentralFileHeader@Packaging@Appx@@@Common@@YAXPEAUZipCentralFileHeader@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipCentralFileHeader>(Appx::Packaging::ZipCentralFileHeader *)
0x180005696  jmp     loc_18000555F
```
