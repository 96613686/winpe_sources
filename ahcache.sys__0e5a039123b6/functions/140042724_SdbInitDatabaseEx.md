# SdbInitDatabaseEx

- ea: `0x140042724`
- end: `0x140042ace`
- name: `SdbInitDatabaseEx`
- size: `938`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x14002ae24`
- `0x14002e77c`
- `0x14005974c`

## callees

- `0x1400044f9`
- `0x140004553`
- `0x1400079f0`
- `0x140007e40`
- `0x14003e364`
- `0x140041d6c`
- `0x140042724`
- `0x140042ad4`
- `0x140042e28`
- `0x14004310c`
- `0x140043360`
- `0x140044fc8`
- `0x140045d44`

## import_xrefs

- `ntoskrnl!RtlGetVersion` at `0x140042a88`
- `ntoskrnl!RtlGetVersion` at `0x140042a88`

## string_xrefs

- `0x140042801`: `SdbpResolveInitSdbPath failed to resolve the sdb path [%x]`
- `0x14004288e`: `Unable to open main database %S`
- `0x1400429b2`: `Unable to open merge stub database %S`

## pseudocode

```c
__int64 __fastcall SdbInitDatabaseEx(unsigned int a1, const wchar_t *a2, unsigned __int16 a3)
{
  int v6; // ebx
  wchar_t *v7; // rsi
  __int64 Pool2_0; // rax
  int v9; // edx
  __int64 v10; // rdi
  int inited; // eax
  __int64 v13; // rdx
  const wchar_t ****v14; // r14
  unsigned int v15; // r8d
  __int64 v16; // rax
  int MergeStubPath; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  const wchar_t ***v20; // rax
  const wchar_t *v21; // rcx
  unsigned int v22; // r8d
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  wchar_t *v26; // [rsp+70h] [rbp-3B8h] BYREF
  __int64 v27; // [rsp+90h] [rbp-398h]
  __int64 v28; // [rsp+A0h] [rbp-388h]
  __int64 v29; // [rsp+A8h] [rbp-380h]
  _DWORD VersionInformation[72]; // [rsp+B0h] [rbp-378h] BYREF
  wchar_t Str2[264]; // [rsp+1D0h] [rbp-258h] BYREF

  LODWORD(v27) = a1;
  v6 = 0;
  memset(Str2, 0, 520);
  v7 = 0;
  v26 = 0;
  Pool2_0 = ExAllocatePool2_0(256, 1784, 1953517633);
  v10 = Pool2_0;
  v28 = Pool2_0;
  if ( !Pool2_0 )
  {
    AslLogCallPrintf(1, "SdbInitDatabaseEx", 554, "Failed to allocate sdb context");
    return 0;
  }
  *(_WORD *)(Pool2_0 + 584) = a3;
  if ( (a1 & 4) == 0 )
  {
    inited = SdbpResolveInitSdbPath(Str2, v9, a1, a2, a3);
    if ( inited < 0 )
    {
      AslLogCallPrintf(
        1,
        "SdbInitDatabaseEx",
        569,
        "SdbpResolveInitSdbPath failed to resolve the sdb path [%x]",
        inited);
      v14 = (const wchar_t ****)(v10 + 8);
LABEL_24:
      if ( *v14 )
        SdbCloseDatabaseRead(*v14);
      v24 = *(_QWORD *)(v10 + 16);
      if ( v24 )
        SdbCloseDatabaseRead(v24);
      AslFree(v24, (void *)v10);
      if ( v7 )
        AslFree(v25, v7);
      return 0;
    }
    v15 = 0;
    if ( (a1 & 8) != 0 )
      v15 = 32;
    *(_QWORD *)(v10 + 8) = SdbOpenDatabaseEx(Str2, v13, v15);
    v14 = (const wchar_t ****)(v10 + 8);
    v27 = v10 + 8;
    v16 = *(_QWORD *)(v10 + 8);
    if ( !v16 )
    {
      AslLogCallPrintf(1, "SdbInitDatabaseEx", 597, "Unable to open main database %S", Str2);
      goto LABEL_24;
    }
    *(_QWORD *)(v10 + 56) = v16;
    *(_DWORD *)(v10 + 64) = 3;
    *(_OWORD *)(v10 + 40) = *(_OWORD *)(v16 + 28);
    v29 = v10 + 36;
    *(_DWORD *)(v10 + 36) |= 1u;
    MergeStubPath = SdbGetMergeStubPath(&v26, Str2);
    if ( MergeStubPath == -1073741772 )
      goto LABEL_31;
    if ( MergeStubPath < 0 )
    {
      AslLogCallPrintf(1, "SdbInitDatabaseEx", 630, "Unable to find merge stub database for %S", Str2);
      v7 = v26;
      goto LABEL_24;
    }
    v20 = *v14;
    v19 = *v14 && *v20 && (v21 = **v20) != 0 && wcsicmp_0(v21, Str2) != 0;
    if ( (_DWORD)v19 )
    {
LABEL_31:
      *(_QWORD *)(v10 + 16) = 0;
      v7 = v26;
    }
    else
    {
      v22 = 0;
      if ( (a1 & 0x10) != 0 )
        v22 = 32;
      v7 = v26;
      *(_QWORD *)(v10 + 16) = SdbOpenDatabaseEx(v26, v18, v22);
      v23 = *(_QWORD *)(v10 + 16);
      if ( !v23 )
      {
        AslLogCallPrintf(1, "SdbInitDatabaseEx", 666, "Unable to open merge stub database %S", Str2);
        goto LABEL_24;
      }
      *(_QWORD *)(v10 + 120) = v23;
      *(_DWORD *)(v10 + 128) = 3;
      *(_OWORD *)(v10 + 104) = *(_OWORD *)(v23 + 28);
      *(_DWORD *)(v10 + 36) |= 4u;
    }
    if ( v7 )
      AslFree(v19, v7);
  }
  SdbpInitializeMatchers(v10);
  *(_DWORD *)(v10 + 552) = SdbpGetBinaryRuntimePlatform(a3);
  memset(&VersionInformation[1], 0, 0x118u);
  VersionInformation[0] = 284;
  RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation);
  LOBYTE(v6) = BYTE2(VersionInformation[70]) != 1;
  *(_DWORD *)(v10 + 568) = v6 + 1;
  return v10;
}

```

## disassembly

```asm
0x140042724  push    rbx
0x140042726  push    rsi
0x140042727  push    rdi
0x140042728  push    r12
0x14004272a  push    r13
0x14004272c  push    r14
0x14004272e  push    r15
0x140042730  sub     rsp, 3F0h
0x140042737  mov     rax, cs:__security_cookie
0x14004273e  xor     rax, rsp
0x140042741  mov     [rsp+428h+var_48], rax
0x140042749  movzx   r13d, r8w
0x14004274d  mov     r14, rdx
0x140042750  mov     r12d, ecx
0x140042753  mov     dword ptr [rsp+428h+var_398], ecx
0x14004275a  mov     [rsp+428h+var_3C8], r8w
0x140042760  xor     ebx, ebx
0x140042762  mov     [rsp+428h+Str2], bx
0x14004276a  xor     edx, edx; Val
0x14004276c  mov     r8d, 206h; Size
0x140042772  lea     rcx, [rsp+428h+var_256]; void *
0x14004277a  call    memset
0x14004277f  mov     esi, ebx
0x140042781  mov     [rsp+428h+var_3B8], rbx
0x140042786  mov     edx, 6F8h
0x14004278b  mov     ecx, 100h
0x140042790  mov     r8d, 74705041h
0x140042796  call    ExAllocatePool2_0
0x14004279b  mov     rdi, rax
0x14004279e  mov     [rsp+428h+var_388], rax
0x1400427a6  test    rax, rax
0x1400427a9  jnz     short loc_1400427CE
0x1400427ab  lea     r9, aFailedToAlloca_6; "Failed to allocate sdb context"
0x1400427b2  mov     r8d, 22Ah
0x1400427b8  lea     rdx, aSdbinitdatabas_0; "SdbInitDatabaseEx"
0x1400427bf  lea     ecx, [rbx+1]
0x1400427c2  call    AslLogCallPrintf
0x1400427c7  xor     eax, eax
0x1400427c9  jmp     loc_140042AAA
0x1400427ce  mov     [rax+248h], r13w
0x1400427d6  test    r12b, 4
0x1400427da  jnz     loc_140042A49
0x1400427e0  mov     word ptr [rsp+428h+var_408], r13w; char
0x1400427e6  mov     r9, r14
0x1400427e9  mov     r8d, r12d
0x1400427ec  lea     rcx, [rsp+428h+Str2]; pszDest
0x1400427f4  call    SdbpResolveInitSdbPath
0x1400427f9  test    eax, eax
0x1400427fb  jns     short loc_140042828
0x1400427fd  mov     dword ptr [rsp+428h+var_408], eax
0x140042801  lea     r9, aSdbpresolveini_0; "SdbpResolveInitSdbPath failed to resolv"...
0x140042808  mov     r8d, 239h
0x14004280e  lea     rdx, aSdbinitdatabas_0; "SdbInitDatabaseEx"
0x140042815  mov     ecx, 1
0x14004281a  call    AslLogCallPrintf
0x14004281f  lea     r14, [rdi+8]
0x140042823  jmp     loc_1400429DD
0x140042828  mov     [rsp+428h+var_3C0], ebx
0x14004282c  test    r12b, 8
0x140042830  mov     r8d, ebx
0x140042833  mov     r15d, 20h ; ' '
0x140042839  cmovnz  r8d, r15d
0x14004283d  mov     [rsp+428h+var_3C0], r8d
0x140042842  lea     rcx, [rsp+428h+Str2]
0x14004284a  call    SdbOpenDatabaseEx
0x14004284f  mov     [rdi+8], rax
0x140042853  jmp     short loc_14004287A
0x140042855  mov     rdi, [rsp+428h+var_388]
0x14004285d  mov     qword ptr [rdi+8], 0
0x140042865  xor     ebx, ebx
0x140042867  mov     rsi, [rsp+428h+var_3B8]
0x14004286c  mov     r12d, dword ptr [rsp+428h+var_398]
0x140042874  movzx   r13d, [rsp+428h+var_3C8]
0x14004287a  lea     r14, [rdi+8]
0x14004287e  mov     [rsp+428h+var_398], r14
0x140042886  mov     rax, [r14]
0x140042889  test    rax, rax
0x14004288c  jnz     short loc_1400428A0
0x14004288e  lea     r9, aUnableToOpenMa; "Unable to open main database %S"
0x140042895  mov     r8d, 255h
0x14004289b  jmp     loc_1400429BF
0x1400428a0  mov     [rdi+38h], rax
0x1400428a4  mov     dword ptr [rdi+40h], 3
0x1400428ab  movups  xmm0, xmmword ptr [rax+1Ch]
0x1400428af  movdqu  xmmword ptr [rdi+28h], xmm0
0x1400428b4  lea     r15, [rdi+24h]
0x1400428b8  mov     [rsp+428h+var_380], r15
0x1400428c0  or      dword ptr [r15], 1
0x1400428c4  lea     rdx, [rsp+428h+Str2]
0x1400428cc  lea     rcx, [rsp+428h+var_3B8]
0x1400428d1  call    SdbGetMergeStubPath
0x1400428d6  cmp     eax, 0C0000034h
0x1400428db  jz      loc_140042A33
0x1400428e1  test    eax, eax
0x1400428e3  jns     short loc_14004291A
0x1400428e5  lea     rax, [rsp+428h+Str2]
0x1400428ed  mov     qword ptr [rsp+428h+var_408], rax
0x1400428f2  lea     r9, aUnableToFindMe; "Unable to find merge stub database for "...
0x1400428f9  mov     r8d, 276h
0x1400428ff  lea     rdx, aSdbinitdatabas_0; "SdbInitDatabaseEx"
0x140042906  mov     ecx, 1
0x14004290b  call    AslLogCallPrintf
0x140042910  mov     rsi, [rsp+428h+var_3B8]
0x140042915  jmp     loc_1400429DD
0x14004291a  mov     rax, [r14]
0x14004291d  test    rax, rax
0x140042920  jz      short loc_140042948
0x140042922  mov     rcx, [rax]
0x140042925  test    rcx, rcx
0x140042928  jz      short loc_140042948
0x14004292a  mov     rcx, [rcx]; Str1
0x14004292d  test    rcx, rcx
0x140042930  jz      short loc_140042948
0x140042932  lea     rdx, [rsp+428h+Str2]; Str2
0x14004293a  call    _wcsicmp_0
0x14004293f  mov     ecx, ebx
0x140042941  test    eax, eax
0x140042943  setnz   cl
0x140042946  jmp     short loc_14004294A
0x140042948  mov     ecx, ebx
0x14004294a  test    ecx, ecx
0x14004294c  jnz     loc_140042A33
0x140042952  mov     [rsp+428h+var_3C0], ebx
0x140042956  test    r12b, 10h
0x14004295a  mov     r8d, ebx
0x14004295d  lea     eax, [rcx+20h]
0x140042960  cmovnz  r8d, eax
0x140042964  mov     [rsp+428h+var_3C0], r8d
0x140042969  mov     rsi, [rsp+428h+var_3B8]
0x14004296e  mov     rcx, rsi
0x140042971  call    SdbOpenDatabaseEx
0x140042976  mov     [rdi+10h], rax
0x14004297a  jmp     short loc_1400429A9
0x14004297c  mov     rdi, [rsp+428h+var_388]
0x140042984  mov     qword ptr [rdi+10h], 0
0x14004298c  xor     ebx, ebx
0x14004298e  mov     rsi, [rsp+428h+var_3B8]
0x140042993  movzx   r13d, [rsp+428h+var_3C8]
0x140042999  mov     r14, [rsp+428h+var_398]
0x1400429a1  mov     r15, [rsp+428h+var_380]
0x1400429a9  mov     rax, [rdi+10h]
0x1400429ad  test    rax, rax
0x1400429b0  jnz     short loc_140042A16
0x1400429b2  lea     r9, aUnableToOpenMe; "Unable to open merge stub database %S"
0x1400429b9  mov     r8d, 29Ah
0x1400429bf  lea     rax, [rsp+428h+Str2]
0x1400429c7  mov     qword ptr [rsp+428h+var_408], rax
0x1400429cc  lea     rdx, aSdbinitdatabas_0; "SdbInitDatabaseEx"
0x1400429d3  mov     ecx, 1
0x1400429d8  call    AslLogCallPrintf
0x1400429dd  mov     rcx, [r14]
0x1400429e0  test    rcx, rcx
0x1400429e3  jz      short loc_1400429EA
0x1400429e5  call    SdbCloseDatabaseRead
0x1400429ea  mov     rcx, [rdi+10h]
0x1400429ee  test    rcx, rcx
0x1400429f1  jz      short loc_1400429F8
0x1400429f3  call    SdbCloseDatabaseRead
0x1400429f8  mov     rdx, rdi
0x1400429fb  call    AslFree
0x140042a00  test    rsi, rsi
0x140042a03  jz      loc_1400427C7
0x140042a09  mov     rdx, rsi
0x140042a0c  call    AslFree
0x140042a11  jmp     loc_1400427C7
0x140042a16  mov     [rdi+78h], rax
0x140042a1a  mov     dword ptr [rdi+80h], 3
0x140042a24  movups  xmm0, xmmword ptr [rax+1Ch]
0x140042a28  movdqu  xmmword ptr [rdi+68h], xmm0
0x140042a2d  or      dword ptr [r15], 4
0x140042a31  jmp     short loc_140042A3C
0x140042a33  mov     [rdi+10h], rbx
0x140042a37  mov     rsi, [rsp+428h+var_3B8]
0x140042a3c  test    rsi, rsi
0x140042a3f  jz      short loc_140042A49
0x140042a41  mov     rdx, rsi
0x140042a44  call    AslFree
0x140042a49  mov     rcx, rdi
0x140042a4c  call    SdbpInitializeMatchers
0x140042a51  movzx   ecx, r13w
0x140042a55  call    SdbpGetBinaryRuntimePlatform
0x140042a5a  mov     [rdi+228h], eax
0x140042a60  xor     edx, edx; Val
0x140042a62  mov     r8d, 118h; Size
0x140042a68  lea     rcx, [rsp+428h+VersionInformation.dwMajorVersion]; void *
0x140042a70  call    memset
0x140042a75  mov     [rsp+428h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140042a80  lea     rcx, [rsp+428h+VersionInformation]; lpVersionInformation
0x140042a88  call    cs:__imp_RtlGetVersion
0x140042a8f  nop     dword ptr [rax+rax+00h]
0x140042a94  cmp     [rsp+428h+var_25E], 1
0x140042a9c  setnz   bl
0x140042a9f  inc     ebx
0x140042aa1  mov     [rdi+238h], ebx
0x140042aa7  mov     rax, rdi
0x140042aaa  mov     rcx, [rsp+428h+var_48]
0x140042ab2  xor     rcx, rsp; StackCookie
0x140042ab5  call    __security_check_cookie
0x140042aba  add     rsp, 3F0h
0x140042ac1  pop     r15
0x140042ac3  pop     r14
0x140042ac5  pop     r13
0x140042ac7  pop     r12
0x140042ac9  pop     rdi
0x140042aca  pop     rsi
0x140042acb  pop     rbx
0x140042acc  retn
0x14005bcec  push    rbp
0x14005bcee  sub     rsp, 60h
0x14005bcf2  mov     rbp, rdx
0x14005bcf5  mov     [rbp+78h], rcx
0x14005bcf9  mov     rax, [rbp+78h]
0x14005bcfd  mov     r10, [rax+8]
0x14005bd01  mov     rax, [rbp+78h]
0x14005bd05  mov     r9, [rax]
0x14005bd08  mov     rax, [rbp+78h]
0x14005bd0c  mov     rcx, [rax]
0x14005bd0f  mov     r8d, [rcx+4]
0x14005bd13  mov     rax, [rbp+78h]
0x14005bd17  mov     rcx, [rax+8]
0x14005bd1b  mov     rdx, [rcx+0F8h]
0x14005bd22  mov     rax, [rbp+78h]
0x14005bd26  mov     rax, [rax]
0x14005bd29  mov     [rsp+68h+var_18], r10
0x14005bd2e  mov     [rsp+68h+var_20], r9
0x14005bd33  mov     [rsp+68h+var_28], r8d
0x14005bd38  mov     [rsp+68h+var_30], rdx
0x14005bd3d  mov     [rsp+68h+var_38], 0
0x14005bd45  lea     rcx, byte_14000DA20
0x14005bd4c  mov     [rsp+68h+var_40], rcx
0x14005bd51  mov     eax, [rax]
0x14005bd53  mov     dword ptr [rsp+68h+var_48], eax
0x14005bd57  lea     r9, aShimExceptionX; "Shim Exception %#x in module \"%hs\", l"...
0x14005bd5e  mov     r8d, 0F5h
0x14005bd64  lea     rdx, aShimexceptionh; "ShimExceptionHandler"
0x14005bd6b  mov     ecx, 1
0x14005bd70  call    AslLogCallPrintf
0x14005bd75  mov     dword ptr [rbp+88h], 1
0x14005bd7f  mov     eax, [rbp+88h]
0x14005bd85  add     rsp, 60h
0x14005bd89  pop     rbp
0x14005bd8a  retn
0x14005bd8c  push    rbp
0x14005bd8e  sub     rsp, 60h
0x14005bd92  mov     rbp, rdx
0x14005bd95  mov     [rbp+80h], rcx
0x14005bd9c  mov     rax, [rbp+80h]
0x14005bda3  mov     r10, [rax+8]
0x14005bda7  mov     rax, [rbp+80h]
0x14005bdae  mov     r9, [rax]
0x14005bdb1  mov     rax, [rbp+80h]
0x14005bdb8  mov     rcx, [rax]
0x14005bdbb  mov     r8d, [rcx+4]
0x14005bdbf  mov     rax, [rbp+80h]
0x14005bdc6  mov     rcx, [rax+8]
0x14005bdca  mov     rdx, [rcx+0F8h]
0x14005bdd1  mov     rax, [rbp+80h]
0x14005bdd8  mov     rax, [rax]
0x14005bddb  mov     [rsp+68h+var_18], r10
0x14005bde0  mov     [rsp+68h+var_20], r9
0x14005bde5  mov     [rsp+68h+var_28], r8d
0x14005bdea  mov     [rsp+68h+var_30], rdx
0x14005bdef  mov     [rsp+68h+var_38], 0
0x14005bdf7  lea     rcx, byte_14000DA20
0x14005bdfe  mov     [rsp+68h+var_40], rcx
0x14005be03  mov     eax, [rax]
0x14005be05  mov     dword ptr [rsp+68h+var_48], eax
0x14005be09  lea     r9, aShimExceptionX; "Shim Exception %#x in module \"%hs\", l"...
0x14005be10  mov     r8d, 0F5h
0x14005be16  lea     rdx, aShimexceptionh; "ShimExceptionHandler"
0x14005be1d  mov     ecx, 1
0x14005be22  call    AslLogCallPrintf
0x14005be27  mov     dword ptr [rbp+98h], 1
0x14005be31  mov     eax, [rbp+98h]
0x14005be37  add     rsp, 60h
0x14005be3b  pop     rbp
0x14005be3c  retn
```
