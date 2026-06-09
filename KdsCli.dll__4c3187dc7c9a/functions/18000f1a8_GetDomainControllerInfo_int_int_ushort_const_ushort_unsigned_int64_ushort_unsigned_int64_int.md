# GetDomainControllerInfo(int,int,ushort const *,ushort * *,unsigned __int64 *,ushort * *,unsigned __int64 *,int *)

- ea: `0x18000f1a8`
- end: `0x18000f474`
- name: `?GetDomainControllerInfo@@YAJHHPEBGPEAPEAGPEA_K12PEAH@Z`
- size: `716`
- prototype: `int(int, int, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *, unsigned __int16 **, unsigned __int64 *, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002bf0`
- `0x180003670`
- `0x18000f640`

## callees

- `0x18000f1a8`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `logoncli!DsGetDcNameW` at `0x18000f1ff`
- `logoncli!DsGetDcNameW` at `0x18000f1ff`
- `netutils!NetApiBufferFree` at `0x18000f45b`
- `netutils!NetApiBufferFree` at `0x18000f45b`

## string_xrefs

- `0x18000f20b`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`
- `0x18000f294`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`
- `0x18000f426`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`

## pseudocode

```c
__int64 __fastcall GetDomainControllerInfo(
        int a1,
        int a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5,
        unsigned __int16 **a6,
        unsigned __int64 *a7,
        int *a8)
{
  int v8; // r10d
  ULONG Flags; // eax
  DWORD DcNameW; // eax
  signed int v12; // ebx
  unsigned int v13; // r9d
  unsigned int v14; // ecx
  LPWSTR i; // rbx
  __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // r13
  unsigned __int64 v19; // rdi
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // r14
  unsigned __int64 v22; // rdi
  __int64 v23; // rbp
  unsigned __int16 *v24; // rdx
  __int64 v25; // rax
  unsigned __int16 *v26; // rcx
  LPWSTR DomainName; // rbx
  __int64 v28; // r15
  unsigned __int64 v29; // rdi
  unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // rsi
  signed int v32; // ecx
  unsigned int v33; // r9d
  unsigned __int64 v34; // rdi
  unsigned __int16 *v35; // rcx
  PDOMAIN_CONTROLLER_INFOW v36; // rax
  BOOL v37; // ecx
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+30h] [rbp-58h] BYREF

  DomainControllerInfo = 0;
  v8 = 1075843072;
  if ( a1 != 1 )
    v8 = 1075838976;
  Flags = v8 | 1;
  if ( a2 != 1 )
    Flags = v8;
  DcNameW = DsGetDcNameW(0, a3, 0, 0, Flags, &DomainControllerInfo);
  v12 = DcNameW;
  if ( DcNameW )
  {
    SidKeyDebugTraceError(
      DcNameW,
      "dwReturn",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx",
      0xC3u);
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v13 = 197;
    v14 = v12;
    goto LABEL_9;
  }
  for ( i = DomainControllerInfo->DomainControllerName; *i == 92; ++i )
    ;
  v16 = -1;
  v17 = -1;
  do
    ++v17;
  while ( i[v17] );
  v18 = 2 * v17;
  v19 = 2 * v17 + 2;
  v20 = (unsigned __int16 *)SIDKeyProvAlloc(v19);
  v21 = v20;
  if ( !v20 )
  {
    v12 = -2147024882;
    v13 = 213;
    v14 = -2147024882;
LABEL_9:
    SidKeyDebugTraceError(v14, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx", v13);
    goto LABEL_48;
  }
  v22 = v19 >> 1;
  if ( !v22 )
  {
    v12 = -2147024809;
    goto LABEL_45;
  }
  if ( v22 <= 0x7FFFFFFF )
  {
    v23 = 2147483646;
    v24 = v20;
    v25 = 2147483646;
    do
    {
      if ( !v25 )
        break;
      if ( !*i )
        break;
      *v24++ = *i++;
      --v25;
      --v22;
    }
    while ( v22 );
    v26 = v24 - 1;
    v12 = v22 == 0 ? 0x8007007A : 0;
    if ( v22 )
      v26 = v24;
    *v26 = 0;
    if ( !v22 )
      goto LABEL_45;
    DomainName = DomainControllerInfo->DomainName;
    do
      ++v16;
    while ( DomainName[v16] );
    v28 = 2 * v16;
    v29 = 2 * v16 + 2;
    v30 = (unsigned __int16 *)SIDKeyProvAlloc(v29);
    v31 = v30;
    if ( !v30 )
    {
      v12 = -2147024882;
      v32 = -2147024882;
      v33 = 231;
      goto LABEL_46;
    }
    v34 = v29 >> 1;
    if ( v34 )
    {
      if ( v34 > 0x7FFFFFFF )
      {
        v12 = -2147024809;
        v32 = -2147024809;
        *v30 = 0;
LABEL_41:
        v33 = 238;
        goto LABEL_46;
      }
      do
      {
        if ( !v23 )
          break;
        if ( !*DomainName )
          break;
        *v30++ = *DomainName++;
        --v23;
        --v34;
      }
      while ( v34 );
      v35 = v30 - 1;
      if ( v34 )
        v35 = v30;
      *v35 = 0;
      v32 = v34 == 0 ? 0x8007007A : 0;
    }
    else
    {
      v32 = -2147024809;
    }
    v12 = v32;
    if ( v32 >= 0 )
    {
      v36 = DomainControllerInfo;
      *a4 = v21;
      v37 = (v36->Flags & 0x100) == 0;
      *a5 = v18;
      *a6 = v31;
      *a7 = v28;
      *a8 = v37;
      goto LABEL_48;
    }
    goto LABEL_41;
  }
  v12 = -2147024809;
  *v20 = 0;
LABEL_45:
  v31 = 0;
  v32 = v12;
  v33 = 220;
LABEL_46:
  SidKeyDebugTraceError(v32, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx", v33);
  SIDKeyProvFree(v21);
  if ( v31 )
    SIDKeyProvFree(v31);
LABEL_48:
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000f1a8  push    rbx
0x18000f1aa  push    rbp
0x18000f1ab  push    rsi
0x18000f1ac  push    rdi
0x18000f1ad  push    r12
0x18000f1af  push    r13
0x18000f1b1  push    r14
0x18000f1b3  push    r15
0x18000f1b5  sub     rsp, 48h
0x18000f1b9  xor     r15d, r15d
0x18000f1bc  mov     eax, 40200000h
0x18000f1c1  cmp     ecx, 1
0x18000f1c4  mov     [rsp+88h+var_58], r15
0x18000f1c9  mov     r11, r8
0x18000f1cc  lea     rcx, [rsp+88h+var_58]
0x18000f1d1  mov     [rsp+88h+DomainControllerInfo], rcx; DomainControllerInfo
0x18000f1d6  mov     r10d, 40201000h
0x18000f1dc  cmovnz  r10d, eax
0x18000f1e0  mov     r12, r9
0x18000f1e3  mov     eax, r10d
0x18000f1e6  or      eax, 1
0x18000f1e9  cmp     edx, 1
0x18000f1ec  mov     rdx, r11; DomainName
0x18000f1ef  cmovnz  eax, r10d
0x18000f1f3  xor     r9d, r9d; SiteName
0x18000f1f6  xor     r8d, r8d; DomainGuid
0x18000f1f9  mov     [rsp+88h+Flags], eax; Flags
0x18000f1fd  xor     ecx, ecx; ComputerName
0x18000f1ff  call    cs:__imp_DsGetDcNameW
0x18000f205  mov     ebx, eax
0x18000f207  test    eax, eax
0x18000f209  jz      short loc_18000F252
0x18000f20b  lea     rdi, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000f212  mov     r9d, 0C3h; unsigned int
0x18000f218  mov     r8, rdi; char *
0x18000f21b  lea     rdx, aDwreturn; "dwReturn"
0x18000f222  mov     ecx, eax; unsigned int
0x18000f224  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f229  test    ebx, ebx
0x18000f22b  jle     short loc_18000F236
0x18000f22d  movzx   ebx, bx
0x18000f230  or      ebx, 80070000h
0x18000f236  mov     r9d, 0C5h; unsigned int
0x18000f23c  mov     r8, rdi; char *
0x18000f23f  mov     ecx, ebx; unsigned int
0x18000f241  lea     rdx, aHr; "hr"
0x18000f248  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f24d  jmp     loc_18000F451
0x18000f252  mov     rax, [rsp+88h+var_58]
0x18000f257  mov     rbx, [rax]
0x18000f25a  jmp     short loc_18000F260
0x18000f25c  add     rbx, 2
0x18000f260  cmp     word ptr [rbx], 5Ch ; '\'
0x18000f264  jz      short loc_18000F25C
0x18000f266  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f26a  mov     rax, rsi
0x18000f26d  inc     rax
0x18000f270  cmp     [rbx+rax*2], r15w
0x18000f275  jnz     short loc_18000F26D
0x18000f277  lea     r13, [rax+rax]
0x18000f27b  lea     rdi, [r13+2]
0x18000f27f  mov     rcx, rdi; unsigned __int64
0x18000f282  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000f287  mov     r14, rax
0x18000f28a  test    rax, rax
0x18000f28d  jnz     short loc_18000F2A8
0x18000f28f  mov     ebx, 8007000Eh
0x18000f294  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000f29b  mov     r9d, 0D5h
0x18000f2a1  mov     ecx, 8007000Eh
0x18000f2a6  jmp     short loc_18000F241
0x18000f2a8  shr     rdi, 1
0x18000f2ab  jz      loc_18000F40D
0x18000f2b1  cmp     rdi, 7FFFFFFFh
0x18000f2b8  jbe     short loc_18000F2C4
0x18000f2ba  mov     ebx, 80070057h
0x18000f2bf  jmp     loc_18000F417
0x18000f2c4  mov     ebp, 7FFFFFFEh
0x18000f2c9  mov     rdx, r14
0x18000f2cc  mov     eax, ebp
0x18000f2ce  test    rax, rax
0x18000f2d1  jz      short loc_18000F2EF
0x18000f2d3  movzx   ecx, word ptr [rbx]
0x18000f2d6  test    cx, cx
0x18000f2d9  jz      short loc_18000F2EF
0x18000f2db  mov     [rdx], cx
0x18000f2de  add     rbx, 2
0x18000f2e2  add     rdx, 2
0x18000f2e6  dec     rax
0x18000f2e9  sub     rdi, 1
0x18000f2ed  jnz     short loc_18000F2CE
0x18000f2ef  mov     rax, rdi
0x18000f2f2  lea     rcx, [rdx-2]
0x18000f2f6  neg     rax
0x18000f2f9  sbb     ebx, ebx
0x18000f2fb  not     ebx
0x18000f2fd  and     ebx, 8007007Ah
0x18000f303  test    rdi, rdi
0x18000f306  cmovnz  rcx, rdx
0x18000f30a  mov     [rcx], r15w
0x18000f30e  jz      loc_18000F41B
0x18000f314  mov     rax, [rsp+88h+var_58]
0x18000f319  mov     rbx, [rax+28h]
0x18000f31d  inc     rsi
0x18000f320  cmp     [rbx+rsi*2], r15w
0x18000f325  jnz     short loc_18000F31D
0x18000f327  lea     r15, [rsi+rsi]
0x18000f32b  lea     rdi, [r15+2]
0x18000f32f  mov     rcx, rdi; unsigned __int64
0x18000f332  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000f337  xor     edx, edx
0x18000f339  mov     rsi, rax
0x18000f33c  test    rax, rax
0x18000f33f  jnz     short loc_18000F356
0x18000f341  mov     ebx, 8007000Eh
0x18000f346  mov     ecx, 8007000Eh
0x18000f34b  mov     r9d, 0E7h
0x18000f351  jmp     loc_18000F426
0x18000f356  shr     rdi, 1
0x18000f359  jz      short loc_18000F3B7
0x18000f35b  cmp     rdi, 7FFFFFFFh
0x18000f362  jbe     short loc_18000F36D
0x18000f364  mov     ebx, 80070057h
0x18000f369  mov     ecx, ebx
0x18000f36b  jmp     short loc_18000F3C3
0x18000f36d  test    rbp, rbp
0x18000f370  jz      short loc_18000F38E
0x18000f372  movzx   ecx, word ptr [rbx]
0x18000f375  test    cx, cx
0x18000f378  jz      short loc_18000F38E
0x18000f37a  mov     [rax], cx
0x18000f37d  add     rbx, 2
0x18000f381  add     rax, 2
0x18000f385  dec     rbp
0x18000f388  sub     rdi, 1
0x18000f38c  jnz     short loc_18000F36D
0x18000f38e  test    rdi, rdi
0x18000f391  lea     rcx, [rax-2]
0x18000f395  cmovnz  rcx, rax
0x18000f399  neg     rdi
0x18000f39c  mov     [rcx], dx
0x18000f39f  sbb     ecx, ecx
0x18000f3a1  not     ecx
0x18000f3a3  and     ecx, 8007007Ah
0x18000f3a9  mov     ebx, ecx
0x18000f3ab  test    ecx, ecx
0x18000f3ad  jns     short loc_18000F3CC
0x18000f3af  mov     r9d, 0EEh
0x18000f3b5  jmp     short loc_18000F426
0x18000f3b7  mov     ebx, 80070057h
0x18000f3bc  mov     ecx, ebx
0x18000f3be  test    rdi, rdi
0x18000f3c1  jz      short loc_18000F3A9
0x18000f3c3  xor     r15d, r15d
0x18000f3c6  mov     [rax], r15w
0x18000f3ca  jmp     short loc_18000F3AF
0x18000f3cc  mov     rax, [rsp+88h+var_58]
0x18000f3d1  mov     [r12], r14
0x18000f3d5  mov     ecx, [rax+38h]
0x18000f3d8  mov     rax, [rsp+88h+arg_20]
0x18000f3e0  shr     ecx, 8
0x18000f3e3  not     ecx
0x18000f3e5  and     ecx, 1
0x18000f3e8  mov     [rax], r13
0x18000f3eb  mov     rax, [rsp+88h+arg_28]
0x18000f3f3  mov     [rax], rsi
0x18000f3f6  mov     rax, [rsp+88h+arg_30]
0x18000f3fe  mov     [rax], r15
0x18000f401  mov     rax, [rsp+88h+arg_38]
0x18000f409  mov     [rax], ecx
0x18000f40b  jmp     short loc_18000F451
0x18000f40d  mov     ebx, 80070057h
0x18000f412  test    rdi, rdi
0x18000f415  jz      short loc_18000F41B
0x18000f417  mov     [rax], r15w
0x18000f41b  mov     rsi, r15
0x18000f41e  mov     ecx, ebx; unsigned int
0x18000f420  mov     r9d, 0DCh; unsigned int
0x18000f426  lea     rdi, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000f42d  mov     r8, rdi; char *
0x18000f430  lea     rdx, aHr; "hr"
0x18000f437  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000f43c  mov     rcx, r14; lpMem
0x18000f43f  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000f444  test    rsi, rsi
0x18000f447  jz      short loc_18000F451
0x18000f449  mov     rcx, rsi; lpMem
0x18000f44c  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000f451  mov     rcx, [rsp+88h+var_58]; Buffer
0x18000f456  test    rcx, rcx
0x18000f459  jz      short loc_18000F461
0x18000f45b  call    cs:__imp_NetApiBufferFree
0x18000f461  mov     eax, ebx
0x18000f463  add     rsp, 48h
0x18000f467  pop     r15
0x18000f469  pop     r14
0x18000f46b  pop     r13
0x18000f46d  pop     r12
0x18000f46f  pop     rdi
0x18000f470  pop     rsi
0x18000f471  pop     rbp
0x18000f472  pop     rbx
0x18000f473  retn
```
