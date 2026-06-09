# AslPathWildcardFindNext

- ea: `0x14004fee8`
- end: `0x14005071b`
- name: `AslPathWildcardFindNext`
- size: `2099`
- prototype: `__int64 __fastcall(wchar_t *, ULONGLONG, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x14002f430`
- `0x14005ac18`

## callees

- `0x140001f58`
- `0x140002034`
- `0x1400020ec`
- `0x14000436d`
- `0x14000437f`
- `0x14000440f`
- `0x140004553`
- `0x140007b40`
- `0x140007e40`
- `0x14003e364`
- `0x14004fee8`
- `0x140050724`
- `0x140050a14`

## import_xrefs

- `ntoskrnl!ZwQueryDirectoryFile` at `0x140050068`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140050068`

## string_xrefs

- `0x14004ffd1`: `AslPathWildcardFindNext`
- `0x1400502c6`: `AslPathWildcardFindNext`
- `0x14005032c`: `AslPathWildcardFindNext`
- `0x14005034b`: `AslPathWildcardFindNext`
- `0x1400506eb`: `AslPathWildcardFindNext`
- `0x14004ffb8`: `AslpPathWildcardPeekNode failed [%x]`
- `0x140050227`: `AslpPathWildcardPeekNode failed [%x]`
- `0x14004ffa9`: `AslpPathWildcardPeekNode`
- `0x14005020f`: `AslpPathWildcardPeekNode`
- `0x140050234`: `AslpPathWildcardPopNode`
- `0x14005029e`: `AslpPathWildcardPushNode failed [%x]`
- `0x1400506f7`: `RtlStringCbCopyNW failed [%x]`
- `0x14005031b`: `NtQueryDirectoryFile failed to query next file [%x]`
- `0x14005033f`: `FilePath: '%ws'  Pattern: '%ws'`
- `0x1400506de`: `AslpPathWildcardAllocMatchNode failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathWildcardFindNext(wchar_t *a1, ULONGLONG a2, unsigned __int64 *a3)
{
  __int16 *FileInformation; // r12
  unsigned __int64 v5; // rcx
  __int64 v6; // rax
  unsigned __int64 v7; // kr00_8
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rsi
  const char *v10; // r9
  __int64 v11; // r8
  unsigned int v12; // ebx
  NTSTATUS v14; // eax
  int v15; // eax
  const wchar_t *v16; // r14
  int matched; // eax
  NTSTATUS v18; // eax
  size_t v19; // rdx
  wchar_t *v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  const wchar_t *v23; // rcx
  __int64 v24; // rax
  wchar_t *v25; // r8
  wchar_t *v26; // rcx
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rdx
  __int64 v29; // rax
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rcx
  int v32; // ebx
  unsigned __int64 v33; // r13
  unsigned __int64 v34; // r9
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // rdx
  __int64 v39; // rax
  unsigned __int64 v40; // r10
  ULONGLONG v41; // rcx
  __int64 v42; // r9
  unsigned __int64 v43; // rcx
  char *v44; // rsi
  unsigned __int64 v45; // rbx
  __int64 v46; // r9
  ULONGLONG v47; // rbx
  ULONGLONG v48; // r10
  ULONGLONG v49; // rcx
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rcx
  ULONGLONG v52; // rsi
  ULONGLONG v53; // rdx
  ULONGLONG v54; // rsi
  size_t v55; // r14
  void *v56; // r15
  PVOID PoolWithTag_0; // rax
  void *v58; // rbx
  __int64 v59; // r14
  ULONGLONG v60; // rdx
  ULONGLONG v61; // rcx
  __int64 v62; // r10
  ULONGLONG v63; // r14
  size_t v64; // rsi
  void *v65; // r15
  PVOID v66; // rax
  void *v67; // rbx
  bool v68; // zf
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+28h] [rbp-59h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK v71; // [rsp+78h] [rbp-9h] BYREF
  struct _UNICODE_STRING v72; // [rsp+88h] [rbp+7h] BYREF
  __int128 v73; // [rsp+98h] [rbp+17h]
  ULONGLONG pullResult; // [rsp+F0h] [rbp+6Fh] BYREF
  ULONGLONG Size; // [rsp+F8h] [rbp+77h] BYREF

  pullResult = a2;
  if ( a3 == (unsigned __int64 *)-1LL )
    return 2147483654LL;
  if ( !a1 )
    return 3221225711LL;
  if ( !a3 )
    return 3221225713LL;
  v71 = 0;
  DestinationString = 0;
  v72 = 0;
  v73 = 0;
  FileInformation = (__int16 *)ExAllocatePool2_0(256, 616, 1953517633);
  if ( !FileInformation )
    return (unsigned int)-1073741801;
  while ( 1 )
  {
    do
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v5 = a3[4];
          if ( !v5 )
          {
            v12 = -2147483642;
            goto LABEL_11;
          }
          v7 = a3[3];
          v6 = v7 * (v5 - 1);
          pullResult = 0;
          if ( !is_mul_ok(v7, v5 - 1) || (v8 = a3[7], v9 = (unsigned __int16 *)(v8 + v6), v8 + v6 < v8) || !v9 )
          {
            AslLogCallPrintf(1, "AslpPathWildcardPeekNode", 2079, "RtlArrayGet failed to get the next node");
            v10 = "AslpPathWildcardPeekNode failed [%x]";
            v11 = 2498;
            v12 = -1073741595;
            goto LABEL_9;
          }
          if ( *((_QWORD *)v9 + 3) )
            break;
          AslLogCallPrintf(1, "AslPathWildcardFindNext", 2503, "Node on the stack with invalid handle.");
          v37 = a3[4];
          if ( v37 )
          {
            v38 = v37 - 1;
            pullResult = 0;
            v39 = a3[3] * (v37 - 1);
            if ( !is_mul_ok(a3[3], v38) )
              goto LABEL_39;
            v30 = a3[7];
            v31 = v30 + v39;
            goto LABEL_38;
          }
LABEL_98:
          v32 = -2147483622;
LABEL_40:
          LODWORD(IoStatusBlock) = v32;
          AslLogCallPrintf(1, "AslpPathWildcardPopNode", 2106, "AslpPathWildcardPeekNode failed [%x]", IoStatusBlock);
        }
        RtlInitUnicodeString_0(&DestinationString, *((PCWSTR *)v9 + 2));
        v14 = ZwQueryDirectoryFile(
                *((HANDLE *)v9 + 3),
                0,
                0,
                0,
                &v71,
                FileInformation,
                0x268u,
                FileBothDirectoryInformation,
                1u,
                &DestinationString,
                0);
        if ( v14 >= 0 )
          break;
        if ( v14 != -2147483642 && v14 != -1073741809 )
        {
          AslLogCallPrintf(
            1,
            "AslPathWildcardFindNext",
            2527,
            "NtQueryDirectoryFile failed to query next file [%x]",
            v14);
          AslLogCallPrintf(
            2,
            "AslPathWildcardFindNext",
            2528,
            "FilePath: '%ws'  Pattern: '%ws'",
            *((_QWORD *)v9 + 1),
            DestinationString.Buffer);
        }
        v27 = a3[4];
        if ( !v27 )
          goto LABEL_98;
        v28 = v27 - 1;
        pullResult = 0;
        v29 = a3[3] * (v27 - 1);
        if ( !is_mul_ok(a3[3], v28) )
          goto LABEL_39;
        v30 = a3[7];
        v31 = v29 + v30;
LABEL_38:
        if ( v31 < v30 || !v31 )
        {
LABEL_39:
          v32 = -1073741595;
          AslLogCallPrintf(1, "AslpPathWildcardPeekNode", 2079, "RtlArrayGet failed to get the next node");
          goto LABEL_40;
        }
        AslpPathWildcardFreeMatchNode(v31);
        v40 = a3[4];
        if ( v40 )
        {
          v41 = a3[3];
          pullResult = 0;
          if ( ULongLongMult(v41, v40 - 1, &pullResult) >= 0 )
          {
            v43 = a3[7];
            v44 = (char *)(v43 + pullResult);
            if ( v43 + pullResult >= v43 )
            {
              v45 = a3[4];
              v46 = ~v42;
              v68 = v46 + v45 == 0;
              v47 = v46 + v45;
              Size = v47;
              if ( v68 )
                goto LABEL_66;
              if ( ULongLongMult(v47, a3[3], &Size) >= 0 )
              {
                v49 = a3[3];
                pullResult = 0;
                if ( ULongLongMult(v49, v48, &pullResult) >= 0 )
                {
                  v50 = a3[7];
                  if ( v50 + pullResult >= v50 )
                  {
                    v47 = Size;
                    memmove(v44, (const void *)(v50 + pullResult), Size);
LABEL_66:
                    memset(&v44[v47], 0, a3[3]);
                    v51 = --a3[4];
                    if ( v51 > 0x10 )
                    {
                      v52 = a3[5];
                      v53 = a3[3];
                      if ( v53 * v52 >= 0x400 && v51 < v52 >> 2 )
                      {
                        pullResult = 0;
                        Size = 0;
                        if ( ULongLongMult(v52, v53, &pullResult) >= 0 )
                        {
                          v54 = v52 >> 1;
                          if ( ULongLongMult(v54, a3[3], &Size) >= 0 )
                          {
                            v55 = Size;
                            v56 = (void *)a3[7];
                            PoolWithTag_0 = ExAllocatePoolWithTag_0(PagedPool, Size, 0x72615452u);
                            v58 = PoolWithTag_0;
                            if ( v56 )
                            {
                              if ( PoolWithTag_0 )
                              {
                                memset(PoolWithTag_0, 0, v55);
                                if ( pullResult < v55 )
                                  v55 = pullResult;
                                memmove(v58, v56, v55);
                                ExFreePoolWithTag_0(v56, 0x72615452u);
LABEL_74:
                                a3[7] = (unsigned __int64)v58;
                                a3[5] = v54;
                              }
                            }
                            else if ( PoolWithTag_0 )
                            {
                              memset(PoolWithTag_0, 0, v55);
                              goto LABEL_74;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      v15 = *((_DWORD *)FileInformation + 15);
      v16 = (const wchar_t *)(FileInformation + 47);
      if ( v15 == 4 )
      {
        if ( *v16 != 46 )
          break;
        v68 = FileInformation[48] == 46;
      }
      else
      {
        if ( v15 != 2 )
          break;
        v16 = (const wchar_t *)(FileInformation + 47);
        v68 = FileInformation[47] == 46;
      }
    }
    while ( v68 );
    matched = AslpPathWildcardAllocMatchNode(&v72, (PCUNICODE_STRING)v9, v16, FileInformation[30]);
    if ( matched == -1073741197 )
      break;
    if ( matched != -1073741565 && matched != -1073741638 )
    {
      if ( matched < 0 )
      {
        LODWORD(IoStatusBlock) = matched;
        AslLogCallPrintf(
          1,
          "AslPathWildcardFindNext",
          2585,
          "AslpPathWildcardAllocMatchNode failed [%x]",
          IoStatusBlock);
      }
      else
      {
        v33 = a3[4];
        v34 = a3[5];
        if ( v33 >= v34 )
        {
          if ( v33 + 1 <= v34 )
          {
            v12 = -1073741811;
LABEL_76:
            v18 = v12;
LABEL_48:
            v10 = "AslpPathWildcardPushNode failed [%x]";
            v11 = 2577;
LABEL_49:
            LODWORD(IoStatusBlock) = v18;
LABEL_10:
            AslLogCallPrintf(1, "AslPathWildcardFindNext", v11, v10, IoStatusBlock);
            goto LABEL_11;
          }
          v59 = a3[6] - 1;
          if ( a3[6] + v33 < v33 + 1
            || (v60 = a3[3], v61 = a3[5], pullResult = 0, Size = 0, ULongLongMult(v61, v60, &pullResult) < 0)
            || (v63 = v62 & ~v59, ULongLongMult(v63, a3[3], &Size) < 0) )
          {
            v12 = -1073741675;
            goto LABEL_76;
          }
          v64 = Size;
          v65 = (void *)a3[7];
          v66 = ExAllocatePoolWithTag_0(PagedPool, Size, 0x72615452u);
          v67 = v66;
          if ( v65 )
          {
            if ( !v66 )
            {
LABEL_105:
              v12 = -1073741801;
              goto LABEL_76;
            }
            memset(v66, 0, v64);
            if ( pullResult < v64 )
              v64 = pullResult;
            memmove(v67, v65, v64);
            ExFreePoolWithTag_0(v65, 0x72615452u);
          }
          else
          {
            if ( !v66 )
              goto LABEL_105;
            memset(v66, 0, v64);
          }
          a3[7] = (unsigned __int64)v67;
          a3[5] = v63;
        }
        pullResult = 0;
        if ( !is_mul_ok(a3[3], v33) || (v35 = a3[7], v36 = v35 + a3[3] * v33, v36 < v35) )
        {
          v12 = -1073741675;
          v18 = -1073741675;
          goto LABEL_48;
        }
        *(struct _UNICODE_STRING *)v36 = v72;
        *(_OWORD *)(v36 + 16) = v73;
        ++a3[4];
      }
    }
  }
  v18 = RtlStringCbCopyNW(a1, 0x208u, *((STRSAFE_PCNZWCH *)v9 + 1), *v9);
  v12 = v18;
  if ( v18 < 0 )
  {
    v10 = "RtlStringCbCopyNW failed [%x]";
    v11 = 2601;
    goto LABEL_49;
  }
  if ( *(_WORD *)(*((_QWORD *)v9 + 1) + 2 * ((unsigned __int64)*v9 >> 1) - 2) != 92 )
  {
    v20 = a1;
    v21 = 260;
    do
    {
      if ( !*v20 )
        break;
      ++v20;
      --v21;
    }
    while ( v21 );
    v12 = v21 == 0 ? 0xC000000D : 0;
    v22 = (260 - v21) & -(__int64)(v21 != 0);
    if ( !v21 )
      goto LABEL_33;
    v23 = L"\\";
    v24 = 1;
    v25 = &a1[v22];
    v19 = 260 - v22;
    if ( 260 != v22 )
    {
      do
      {
        if ( !v24 )
          break;
        if ( !*v23 )
          break;
        *v25++ = *v23++;
        --v24;
        --v19;
      }
      while ( v19 );
    }
    v26 = v25 - 1;
    v12 = v19 == 0 ? 0x80000005 : 0;
    if ( v19 )
      v26 = v25;
    *v26 = 0;
    if ( !v19 )
    {
LABEL_33:
      v10 = "RtlStringCbCatNW failed [%x]";
      v11 = 2608;
LABEL_9:
      LODWORD(IoStatusBlock) = v12;
      goto LABEL_10;
    }
  }
  v18 = RtlStringCbCatNW(a1, v19, v16, *((unsigned int *)FileInformation + 15));
  v12 = v18;
  if ( v18 < 0 )
  {
    v10 = "RtlStringCbCatNW failed [%x]";
    v11 = 2615;
    goto LABEL_49;
  }
  v12 = 0;
LABEL_11:
  ExFreePoolWithTag_0(FileInformation, 0x74705041u);
  return v12;
}

```

## disassembly

```asm
0x14004fee8  mov     rax, rsp
0x14004feeb  mov     [rax+20h], rbx
0x14004feef  mov     [rax+10h], rdx
0x14004fef3  mov     [rax+8], rcx
0x14004fef7  push    rbp
0x14004fef8  push    rsi
0x14004fef9  push    rdi
0x14004fefa  push    r12
0x14004fefc  push    r13
0x14004fefe  push    r14
0x14004ff00  push    r15
0x14004ff02  lea     rbp, [rax-5Fh]
0x14004ff06  sub     rsp, 0A0h
0x14004ff0d  mov     rdi, r8
0x14004ff10  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14004ff14  jz      loc_140050642
0x14004ff1a  xor     r15d, r15d
0x14004ff1d  test    rcx, rcx
0x14004ff20  jz      loc_14005064C
0x14004ff26  test    r8, r8
0x14004ff29  jz      loc_140050656
0x14004ff2f  xorps   xmm0, xmm0
0x14004ff32  xorps   xmm1, xmm1
0x14004ff35  mov     edx, 268h
0x14004ff3a  mov     ecx, 100h
0x14004ff3f  mov     r8d, 74705041h
0x14004ff45  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14004ff49  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14004ff4d  movups  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x14004ff51  movups  [rbp+57h+var_40], xmm0
0x14004ff55  call    ExAllocatePool2_0
0x14004ff5a  mov     r12, rax
0x14004ff5d  test    rax, rax
0x14004ff60  jz      loc_140050660
0x14004ff66  mov     r13d, 1
0x14004ff6c  mov     rcx, [rdi+20h]
0x14004ff70  cmp     rcx, r13
0x14004ff73  jb      loc_140050008
0x14004ff79  lea     rax, [rcx-1]
0x14004ff7d  cmp     rax, rcx
0x14004ff80  jnb     short loc_14004FF9C
0x14004ff82  mul     qword ptr [rdi+18h]
0x14004ff86  mov     [rbp+57h+pullResult], r15
0x14004ff8a  test    rdx, rdx
0x14004ff8d  jnz     short loc_14004FF9C
0x14004ff8f  mov     rcx, [rdi+38h]
0x14004ff93  lea     rsi, [rcx+rax]
0x14004ff97  cmp     rsi, rcx
0x14004ff9a  jnb     short loc_14005000F
0x14004ff9c  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x14004ffa3  mov     r8d, 81Fh
0x14004ffa9  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x14004ffb0  mov     ecx, r13d
0x14004ffb3  call    AslLogCallPrintf
0x14004ffb8  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x14004ffbf  mov     r8d, 9C2h
0x14004ffc5  mov     ecx, r13d
0x14004ffc8  mov     ebx, 0C00000E5h
0x14004ffcd  mov     dword ptr [rsp+0D0h+IoStatusBlock], ebx
0x14004ffd1  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x14004ffd8  call    AslLogCallPrintf
0x14004ffdd  mov     edx, 74705041h; Tag
0x14004ffe2  mov     rcx, r12; P
0x14004ffe5  call    ExFreePoolWithTag_0
0x14004ffea  mov     eax, ebx
0x14004ffec  mov     rbx, [rsp+0D0h+arg_18]
0x14004fff4  add     rsp, 0A0h
0x14004fffb  pop     r15
0x14004fffd  pop     r14
0x14004ffff  pop     r13
0x140050001  pop     r12
0x140050003  pop     rdi
0x140050004  pop     rsi
0x140050005  pop     rbp
0x140050006  retn
0x140050008  mov     ebx, 80000006h
0x14005000d  jmp     short loc_14004FFDD
0x14005000f  test    rsi, rsi
0x140050012  jz      short loc_14004FF9C
0x140050014  cmp     [rsi+18h], r15
0x140050018  jz      loc_1400502B9
0x14005001e  mov     rdx, [rsi+10h]; SourceString
0x140050022  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140050026  call    RtlInitUnicodeString_0
0x14005002b  mov     rcx, [rsi+18h]; FileHandle
0x14005002f  lea     rax, [rbp+57h+DestinationString]
0x140050033  mov     [rsp+50h], r15b; RestartScan
0x140050038  xor     r9d, r9d; ApcContext
0x14005003b  mov     [rsp+0D0h+FileName], rax; FileName
0x140050040  xor     r8d, r8d; ApcRoutine
0x140050043  mov     [rsp+0D0h+ReturnSingleEntry], r13b; ReturnSingleEntry
0x140050048  lea     rax, [rbp+57h+var_60]
0x14005004c  mov     [rsp+0D0h+FileInformationClass], 3; FileInformationClass
0x140050054  xor     edx, edx; Event
0x140050056  mov     [rsp+0D0h+Length], 268h; Length
0x14005005e  mov     [rsp+0D0h+FileInformation], r12; FileInformation
0x140050063  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x140050068  call    cs:__imp_ZwQueryDirectoryFile
0x14005006f  nop     dword ptr [rax+rax+00h]
0x140050074  test    eax, eax
0x140050076  js      loc_1400501C0
0x14005007c  mov     eax, [r12+3Ch]
0x140050081  lea     r14, [r12+5Eh]
0x140050086  cmp     eax, 4
0x140050089  jz      loc_14005067C
0x14005008f  cmp     eax, 2
0x140050092  jz      loc_140050690
0x140050098  mov     r9d, [r12+38h]
0x14005009d  lea     rcx, [rbp+57h+var_50]; DestinationString
0x1400500a1  movzx   eax, word ptr [r12+3Ch]
0x1400500a7  mov     rdx, rsi; SourceString
0x1400500aa  mov     r8, [rsi+10h]
0x1400500ae  shr     r9d, 4
0x1400500b2  mov     word ptr [rsp+0D0h+FileInformation], ax; __int16
0x1400500b7  and     r9d, r13d
0x1400500ba  mov     [rsp+0D0h+IoStatusBlock], r14; pszSrc
0x1400500bf  call    AslpPathWildcardAllocMatchNode
0x1400500c4  cmp     eax, 0C0000273h
0x1400500c9  jnz     loc_140050248
0x1400500cf  mov     r13, [rbp+57h+pszDest]
0x1400500d3  mov     edx, 208h; cbDest
0x1400500d8  movzx   r9d, word ptr [rsi]; cbToCopy
0x1400500dc  mov     rcx, r13; pszDest
0x1400500df  mov     r8, [rsi+8]; pszSrc
0x1400500e3  call    RtlStringCbCopyNW
0x1400500e8  mov     ebx, eax
0x1400500ea  test    eax, eax
0x1400500ec  js      loc_1400506F7
0x1400500f2  movzx   ecx, word ptr [rsi]
0x1400500f5  mov     rax, [rsi+8]
0x1400500f9  shr     rcx, 1
0x1400500fc  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140050102  jz      loc_140050370
0x140050108  mov     edx, 104h
0x14005010d  mov     rax, r13
0x140050110  mov     r8d, edx
0x140050113  cmp     [rax], r15w
0x140050117  jz      short loc_140050123
0x140050119  add     rax, 2
0x14005011d  sub     r8, 1
0x140050121  jnz     short loc_140050113
0x140050123  mov     rax, r8
0x140050126  mov     rcx, rdx
0x140050129  neg     rax
0x14005012c  mov     rax, r8
0x14005012f  sbb     ebx, ebx
0x140050131  sub     rcx, r8
0x140050134  not     ebx
0x140050136  and     ebx, 0C000000Dh
0x14005013c  neg     rax
0x14005013f  sbb     r9, r9
0x140050142  and     r9, rcx
0x140050145  test    r8, r8
0x140050148  jz      short loc_1400501A9
0x14005014a  lea     rcx, asc_14000AF88; "\\"
0x140050151  mov     eax, 1
0x140050156  lea     r8, [r13+r9*2+0]
0x14005015b  sub     rdx, r9
0x14005015e  jz      short loc_140050184
0x140050160  test    rax, rax
0x140050163  jz      short loc_140050184
0x140050165  movzx   r9d, word ptr [rcx]
0x140050169  test    r9w, r9w
0x14005016d  jz      short loc_140050184
0x14005016f  mov     [r8], r9w
0x140050173  add     rcx, 2
0x140050177  add     r8, 2
0x14005017b  dec     rax
0x14005017e  sub     rdx, 1
0x140050182  jnz     short loc_140050160
0x140050184  mov     rax, rdx
0x140050187  lea     rcx, [r8-2]
0x14005018b  neg     rax
0x14005018e  sbb     ebx, ebx
0x140050190  not     ebx
0x140050192  and     ebx, 80000005h
0x140050198  test    rdx, rdx
0x14005019b  cmovnz  rcx, r8
0x14005019f  mov     [rcx], r15w
0x1400501a3  jnz     loc_140050370
0x1400501a9  lea     r9, aRtlstringcbcat; "RtlStringCbCatNW failed [%x]"
0x1400501b0  mov     r8d, 0A30h
0x1400501b6  mov     ecx, 1
0x1400501bb  jmp     loc_14004FFCD
0x1400501c0  cmp     eax, 80000006h
0x1400501c5  jnz     loc_140050310
0x1400501cb  mov     rax, [rdi+20h]
0x1400501cf  cmp     rax, r13
0x1400501d2  jb      loc_140050672
0x1400501d8  lea     rdx, [rax-1]
0x1400501dc  cmp     rdx, rax
0x1400501df  jnb     short loc_140050202
0x1400501e1  mov     rax, rdx
0x1400501e4  mov     [rbp+57h+pullResult], r15
0x1400501e8  mul     qword ptr [rdi+18h]
0x1400501ec  test    rdx, rdx
0x1400501ef  jnz     short loc_140050202
0x1400501f1  mov     rdx, [rdi+38h]
0x1400501f5  lea     rcx, [rax+rdx]
0x1400501f9  cmp     rcx, rdx
0x1400501fc  jnb     loc_140050392
0x140050202  lea     r9, aRtlarraygetFai; "RtlArrayGet failed to get the next node"
0x140050209  mov     r8d, 81Fh
0x14005020f  lea     rdx, aAslppathwildca_1; "AslpPathWildcardPeekNode"
0x140050216  mov     ecx, r13d
0x140050219  mov     ebx, 0C00000E5h
0x14005021e  call    AslLogCallPrintf
0x140050223  mov     dword ptr [rsp+0D0h+IoStatusBlock], ebx
0x140050227  lea     r9, aAslppathwildca; "AslpPathWildcardPeekNode failed [%x]"
0x14005022e  mov     r8d, 83Ah
0x140050234  lea     rdx, aAslppathwildca_8; "AslpPathWildcardPopNode"
0x14005023b  mov     ecx, r13d
0x14005023e  call    AslLogCallPrintf
0x140050243  jmp     loc_14004FF6C
0x140050248  cmp     eax, 0C0000103h
0x14005024d  jz      loc_14004FF6C
0x140050253  cmp     eax, 0C00000BAh
0x140050258  jz      loc_14004FF6C
0x14005025e  test    eax, eax
0x140050260  js      loc_1400506DA
0x140050266  mov     r13, [rdi+20h]
0x14005026a  mov     r9, [rdi+28h]
0x14005026e  cmp     r13, r9
0x140050271  jnb     loc_140050562
0x140050277  mov     rax, r13
0x14005027a  mov     [rbp+57h+pullResult], r15
0x14005027e  mul     qword ptr [rdi+18h]
0x140050282  test    rdx, rdx
0x140050285  jnz     short loc_140050297
0x140050287  mov     rcx, [rdi+38h]
0x14005028b  add     rax, rcx
0x14005028e  cmp     rax, rcx
0x140050291  jnb     loc_1400506BC
0x140050297  mov     ebx, 0C0000095h
0x14005029c  mov     eax, ebx
0x14005029e  lea     r9, aAslppathwildca_4; "AslpPathWildcardPushNode failed [%x]"
0x1400502a5  mov     r8d, 0A11h
0x1400502ab  mov     dword ptr [rsp+0D0h+IoStatusBlock], eax
0x1400502af  mov     ecx, 1
0x1400502b4  jmp     loc_14004FFD1
0x1400502b9  lea     r9, aNodeOnTheStack; "Node on the stack with invalid handle."
0x1400502c0  mov     r8d, 9C7h
0x1400502c6  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x1400502cd  mov     ecx, r13d
0x1400502d0  call    AslLogCallPrintf
0x1400502d5  mov     rax, [rdi+20h]
0x1400502d9  cmp     rax, r13
0x1400502dc  jb      loc_140050672
0x1400502e2  lea     rdx, [rax-1]
0x1400502e6  cmp     rdx, rax
0x1400502e9  jnb     loc_140050202
0x1400502ef  mov     rax, rdx
0x1400502f2  mov     [rbp+57h+pullResult], r15
0x1400502f6  mul     qword ptr [rdi+18h]
0x1400502fa  test    rdx, rdx
0x1400502fd  jnz     loc_140050202
0x140050303  mov     rdx, [rdi+38h]
0x140050307  lea     rcx, [rdx+rax]
0x14005030b  jmp     loc_1400501F9
0x140050310  cmp     eax, 0C000000Fh
0x140050315  jz      loc_1400501CB
0x14005031b  lea     r9, aNtquerydirecto; "NtQueryDirectoryFile failed to query ne"...
0x140050322  mov     dword ptr [rsp+0D0h+IoStatusBlock], eax
0x140050326  mov     r8d, 9DFh
0x14005032c  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x140050333  mov     ecx, r13d
0x140050336  call    AslLogCallPrintf
0x14005033b  mov     rax, [rbp+57h+DestinationString.Buffer]
0x14005033f  lea     r9, aFilepathWsPatt; "FilePath: '%ws'  Pattern: '%ws'"
0x140050346  mov     [rsp+0D0h+FileInformation], rax
0x14005034b  lea     rdx, aAslpathwildcar; "AslPathWildcardFindNext"
0x140050352  mov     rax, [rsi+8]
0x140050356  mov     r8d, 9E0h
0x14005035c  mov     ecx, 2
0x140050361  mov     [rsp+0D0h+IoStatusBlock], rax
0x140050366  call    AslLogCallPrintf
0x14005036b  jmp     loc_1400501CB
0x140050370  mov     r9d, [r12+3Ch]; cbToAppend
0x140050375  mov     r8, r14; pszSrc
0x140050378  mov     rcx, r13; pszDest
0x14005037b  call    RtlStringCbCatNW
0x140050380  mov     ebx, eax
0x140050382  test    eax, eax
0x140050384  js      loc_140050709
0x14005038a  mov     ebx, r15d
0x14005038d  jmp     loc_14004FFDD
0x140050392  test    rcx, rcx
0x140050395  jz      loc_140050202
0x14005039b  call    AslpPathWildcardFreeMatchNode
0x1400503a0  mov     r10, [rdi+20h]
0x1400503a4  lea     r9, [r10-1]
0x1400503a8  cmp     r9, r10
0x1400503ab  jnb     loc_14004FF6C
0x1400503b1  mov     rcx, [rdi+18h]; ullMultiplicand
0x1400503b5  lea     r8, [rbp+57h+pullResult]; pullResult
0x1400503b9  mov     rdx, r9; ullMultiplier
0x1400503bc  mov     [rbp+57h+pullResult], r15
0x1400503c0  call    ULongLongMult
0x1400503c5  test    eax, eax
0x1400503c7  js      loc_14004FF6C
  ... truncated ...
```
