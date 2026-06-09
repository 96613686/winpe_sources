# SdbOpenDatabaseEx

- ea: `0x180119160`
- end: `0x1801194c7`
- name: `SdbOpenDatabaseEx`
- size: `871`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18011da30`
- `0x18011e0b8`

## callees

- `0x1800197d4`
- `0x18001b5bc`
- `0x18001b830`
- `0x18001ccd0`
- `0x18001cce4`
- `0x18004f484`
- `0x180059920`
- `0x18005a8bc`
- `0x18006bc4c`
- `0x180118d38`
- `0x180119160`
- `0x18011aa24`
- `0x18011aaac`
- `0x1801234f4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1801191eb`
- `ntdll!RtlAllocateHeap` at `0x1801191eb`

## string_xrefs

- `0x1801191a5`: `SdbOpenDatabaseEx`
- `0x18011920a`: `SdbOpenDatabaseEx`
- `0x18011929f`: `SdbOpenDatabaseEx`
- `0x1801192dc`: `SdbOpenDatabaseEx`
- `0x180119308`: `SdbOpenDatabaseEx`
- `0x18011935f`: `SdbOpenDatabaseEx`
- `0x180119431`: `SdbOpenDatabaseEx`
- `0x180119470`: `SdbOpenDatabaseEx`
- `0x18011918a`: `Flags:%d; DatabasePath:%ws`
- `0x1801192cb`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x180119352`: `Failed to create file mapping [%x]`
- `0x1801192f6`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`
- `0x1801193d3`: `Failed to read database header`
- `0x180119463`: `Failed to open SDB - File size too large or small.`
- `0x180119424`: `SdbpOpenCompressedDatabase failed to open compressed database.`

## pseudocode

```c
_QWORD *__fastcall SdbOpenDatabaseEx(const WCHAR *a1, __int64 a2, unsigned int a3)
{
  _QWORD *Heap; // rax
  _QWORD *v6; // rbx
  int MergeRedirectPath; // r14d
  int v8; // esi
  const char *v9; // r9
  int v10; // r8d
  __int64 v11; // rsi
  __int64 v12; // rdx
  BOOL v14; // [rsp+30h] [rbp-30h] BYREF
  const WCHAR *v15; // [rsp+38h] [rbp-28h] BYREF
  _QWORD *v16; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h] BYREF
  int v18; // [rsp+50h] [rbp-10h]

  v17 = 0;
  v18 = 0;
  v14 = 0;
  AslLogCallPrintf(3, (unsigned int)"SdbOpenDatabaseEx", 2501, (unsigned int)"Flags:%d; DatabasePath:%ws");
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v16 = Heap;
  v6 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0xA80u);
    v15 = 0;
    if ( (a3 & 0x10) != 0 )
      goto LABEL_21;
    MergeRedirectPath = SdbGetMergeRedirectPath(&v15, &v14, (a3 & 0x20) == 0, (unsigned __int64)a1);
    if ( MergeRedirectPath < 0 )
    {
      if ( MergeRedirectPath != -1073741772 )
        AslLogCallPrintf(
          3,
          (unsigned int)"SdbOpenDatabaseEx",
          2527,
          (unsigned int)"SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]");
      v8 = MergeRedirectPath;
    }
    else if ( v15 )
    {
      if ( (a3 & 0x20) != 0 )
      {
        if ( !v14 )
          *((_DWORD *)v6 + 6) |= 0x20u;
      }
      else if ( v14 )
      {
        AslPathGetFileNamePart(a1);
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbOpenDatabaseEx",
          2539,
          (unsigned int)"Handled Error: MergeSdb staged deletion feature was used to prevent sdb mismatch error. SdbName: [%ls].");
      }
      v8 = AslFileMappingCreate((HANDLE **)v6, v15);
      if ( v8 < 0 )
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbOpenDatabaseEx",
          2558,
          (unsigned int)"Failed to create file mapping for redirected SDB file [%x]");
    }
    else
    {
      v8 = -1073741772;
    }
    if ( v15 )
      AslFree(NtCurrentPeb()->ProcessHeap, v15);
    if ( v8 < 0 || !*v6 )
    {
LABEL_21:
      if ( (int)AslFileMappingCreate((HANDLE **)v6, a1) < 0 )
      {
        v9 = "Failed to create file mapping [%x]";
        v10 = 2580;
LABEL_39:
        AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", v10, (_DWORD)v9);
LABEL_40:
        if ( v6 )
        {
          AslFileMappingDelete(*v6);
          AslFree(NtCurrentPeb()->ProcessHeap, v6);
        }
        return 0;
      }
    }
    v11 = *(_QWORD *)(*v6 + 24LL);
    if ( (unsigned __int64)(v11 - 42) > 0xFFFFFD5 )
    {
      v9 = "Failed to open SDB - File size too large or small.";
      v10 = 2589;
      goto LABEL_39;
    }
    if ( (int)AslFileMappingEnsureMappedAsEx(*v6) < 0 )
    {
      v9 = "Failed to map SDB [%x]";
      v10 = 2595;
      goto LABEL_39;
    }
    *((_DWORD *)v6 + 4) = 0;
    *((_DWORD *)v6 + 5) = v11;
    v6[1] = AslFileMappingGetViewBase(*v6);
    if ( !(unsigned int)SdbpReadMappedData((__int64)v6, 0, &v17, 0xCu) )
    {
      v9 = "Failed to read database header";
      v10 = 2608;
      goto LABEL_39;
    }
    if ( v18 != 1717724275 )
    {
      if ( v18 == 1717724282 )
      {
        if ( !(unsigned int)SdbpOpenCompressedDatabase(&v16, v12, a3) )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbOpenDatabaseEx",
            2627,
            (unsigned int)"SdbpOpenCompressedDatabase failed to open compressed database.");
          v6 = v16;
          goto LABEL_40;
        }
        return v16;
      }
      if ( (a3 & 2) == 0 )
      {
        v9 = "Magic does not match a valid value: 0x%lx";
        v10 = 2621;
        goto LABEL_39;
      }
    }
    if ( !(unsigned int)SdbpValidateAndApplyCompatFlags(v6, &v17, a3) )
      goto LABEL_40;
    return v6;
  }
  AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", 2509, (unsigned int)"Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x180119160  mov     r11, rsp
0x180119163  mov     [r11+10h], rbx
0x180119167  mov     [r11+20h], rsi
0x18011916b  push    rbp
0x18011916c  push    rdi
0x18011916d  push    r12
0x18011916f  push    r13
0x180119171  push    r14
0x180119173  mov     rbp, rsp
0x180119176  sub     rsp, 60h
0x18011917a  mov     rax, cs:__security_cookie
0x180119181  xor     rax, rsp
0x180119184  mov     [rbp+var_8], rax
0x180119188  xor     eax, eax
0x18011918a  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x180119191  mov     r13, rcx
0x180119194  mov     [rbp+var_18], rax
0x180119198  mov     [rbp+var_10], eax
0x18011919b  lea     rcx, byte_1801389F0
0x1801191a2  mov     [rbp+var_30], eax
0x1801191a5  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1801191ac  mov     r12d, r8d
0x1801191af  test    r13, r13
0x1801191b2  mov     rax, r13
0x1801191b5  cmovz   rax, rcx
0x1801191b9  mov     ecx, 3
0x1801191be  mov     [r11-60h], rax
0x1801191c2  mov     [r11-68h], r8d
0x1801191c6  mov     r8d, 9C5h
0x1801191cc  call    AslLogCallPrintf
0x1801191d1  mov     rcx, gs:60h
0x1801191da  mov     edi, 0A80h
0x1801191df  mov     r8d, edi; Size
0x1801191e2  mov     edx, 8; Flags
0x1801191e7  mov     rcx, [rcx+30h]; HeapHandle
0x1801191eb  call    cs:__imp_RtlAllocateHeap
0x1801191f1  mov     [rbp+var_20], rax
0x1801191f5  mov     rbx, rax
0x1801191f8  test    rax, rax
0x1801191fb  jnz     short loc_18011921E
0x1801191fd  lea     r9, aFailedToAlloca_10; "Failed to allocate DB structure"
0x180119204  mov     r8d, 9CDh
0x18011920a  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180119211  lea     ecx, [rax+1]
0x180119214  call    AslLogCallPrintf
0x180119219  jmp     loc_1801194A0
0x18011921e  mov     r8, rdi; Size
0x180119221  xor     edx, edx; Val
0x180119223  mov     rcx, rbx; void *
0x180119226  call    memset_0
0x18011922b  mov     [rbp+var_28], 0
0x180119233  mov     edi, 1
0x180119238  test    r12b, 10h
0x18011923c  jnz     loc_180119343
0x180119242  lea     r8d, [rdi-1]
0x180119246  mov     esi, r12d
0x180119249  and     esi, 20h
0x18011924c  lea     rdx, [rbp+var_30]
0x180119250  mov     r9, r13
0x180119253  lea     rcx, [rbp+var_28]
0x180119257  setz    r8b
0x18011925b  call    SdbGetMergeRedirectPath
0x180119260  mov     r14d, eax
0x180119263  test    eax, eax
0x180119265  js      loc_1801192EC
0x18011926b  cmp     [rbp+var_28], 0
0x180119270  jnz     short loc_18011927C
0x180119272  mov     esi, 0C0000034h
0x180119277  jmp     loc_18011931C
0x18011927c  test    esi, esi
0x18011927e  jnz     short loc_1801192AF
0x180119280  cmp     [rbp+var_30], esi
0x180119283  jz      short loc_1801192B9
0x180119285  mov     rcx, r13
0x180119288  call    AslPathGetFileNamePart
0x18011928d  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x180119294  mov     [rsp+60h+var_40], rax
0x180119299  mov     r8d, 9EBh
0x18011929f  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1801192a6  mov     ecx, edi
0x1801192a8  call    AslLogCallPrintf
0x1801192ad  jmp     short loc_1801192B9
0x1801192af  cmp     [rbp+var_30], 0
0x1801192b3  jnz     short loc_1801192B9
0x1801192b5  or      dword ptr [rbx+18h], 20h
0x1801192b9  mov     rdx, [rbp+var_28]
0x1801192bd  mov     rcx, rbx
0x1801192c0  call    AslFileMappingCreate
0x1801192c5  mov     esi, eax
0x1801192c7  test    eax, eax
0x1801192c9  jns     short loc_18011931C
0x1801192cb  lea     r9, aFailedToCreate_2; "Failed to create file mapping for redir"...
0x1801192d2  mov     dword ptr [rsp+60h+var_40], eax
0x1801192d6  mov     r8d, 9FEh
0x1801192dc  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1801192e3  mov     ecx, edi
0x1801192e5  call    AslLogCallPrintf
0x1801192ea  jmp     short loc_18011931C
0x1801192ec  mov     esi, 0C0000034h
0x1801192f1  cmp     r14d, esi
0x1801192f4  jz      short loc_180119319
0x1801192f6  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x1801192fd  mov     dword ptr [rsp+60h+var_40], r14d
0x180119302  mov     r8d, 9DFh
0x180119308  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x18011930f  mov     ecx, 3
0x180119314  call    AslLogCallPrintf
0x180119319  mov     esi, r14d
0x18011931c  cmp     [rbp+var_28], 0
0x180119321  jz      short loc_180119339
0x180119323  mov     rcx, gs:60h
0x18011932c  mov     rdx, [rbp+var_28]
0x180119330  mov     rcx, [rcx+30h]
0x180119334  call    AslFree
0x180119339  test    esi, esi
0x18011933b  js      short loc_180119343
0x18011933d  cmp     qword ptr [rbx], 0
0x180119341  jnz     short loc_180119376
0x180119343  mov     rdx, r13
0x180119346  mov     rcx, rbx
0x180119349  call    AslFileMappingCreate
0x18011934e  test    eax, eax
0x180119350  jns     short loc_180119376
0x180119352  lea     r9, aFailedToCreate; "Failed to create file mapping [%x]"
0x180119359  mov     r8d, 0A14h
0x18011935f  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180119366  mov     dword ptr [rsp+60h+var_40], eax
0x18011936a  mov     ecx, edi
0x18011936c  call    AslLogCallPrintf
0x180119371  jmp     loc_18011947E
0x180119376  mov     rcx, [rbx]
0x180119379  mov     rsi, [rcx+18h]
0x18011937d  lea     rax, [rsi-2Ah]
0x180119381  cmp     rax, 0FFFFFD5h
0x180119387  ja      loc_180119463
0x18011938d  call    AslFileMappingEnsureMappedAsEx
0x180119392  test    eax, eax
0x180119394  jns     short loc_1801193A5
0x180119396  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x18011939d  mov     r8d, 0A23h
0x1801193a3  jmp     short loc_18011935F
0x1801193a5  mov     dword ptr [rbx+10h], 0
0x1801193ac  mov     [rbx+14h], esi
0x1801193af  mov     rcx, [rbx]
0x1801193b2  call    AslFileMappingGetViewBase
0x1801193b7  mov     r9d, 0Ch
0x1801193bd  mov     [rbx+8], rax
0x1801193c1  lea     r8, [rbp+var_18]
0x1801193c5  xor     edx, edx
0x1801193c7  mov     rcx, rbx
0x1801193ca  call    SdbpReadMappedData
0x1801193cf  test    eax, eax
0x1801193d1  jnz     short loc_1801193E5
0x1801193d3  lea     r9, aFailedToReadDa_0; "Failed to read database header"
0x1801193da  mov     r8d, 0A30h
0x1801193e0  jmp     loc_180119470
0x1801193e5  mov     eax, [rbp+var_10]
0x1801193e8  mov     ecx, 6662647Ah
0x1801193ed  cmp     eax, 66626473h
0x1801193f2  jz      short loc_180119410
0x1801193f4  cmp     eax, ecx
0x1801193f6  jz      short loc_180119414
0x1801193f8  test    r12b, 2
0x1801193fc  jnz     short loc_180119410
0x1801193fe  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x180119405  mov     r8d, 0A3Dh
0x18011940b  jmp     loc_18011935F
0x180119410  cmp     eax, ecx
0x180119412  jnz     short loc_18011944B
0x180119414  mov     r8d, r12d
0x180119417  lea     rcx, [rbp+var_20]
0x18011941b  call    SdbpOpenCompressedDatabase
0x180119420  test    eax, eax
0x180119422  jnz     short loc_180119445
0x180119424  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x18011942b  mov     r8d, 0A43h
0x180119431  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180119438  mov     ecx, edi
0x18011943a  call    AslLogCallPrintf
0x18011943f  mov     rbx, [rbp+var_20]
0x180119443  jmp     short loc_18011947E
0x180119445  mov     rbx, [rbp+var_20]
0x180119449  jmp     short loc_18011945E
0x18011944b  mov     r8d, r12d
0x18011944e  lea     rdx, [rbp+var_18]
0x180119452  mov     rcx, rbx
0x180119455  call    SdbpValidateAndApplyCompatFlags
0x18011945a  test    eax, eax
0x18011945c  jz      short loc_18011947E
0x18011945e  mov     rax, rbx
0x180119461  jmp     short loc_1801194A2
0x180119463  lea     r9, aFailedToOpenSd; "Failed to open SDB - File size too larg"...
0x18011946a  mov     r8d, 0A1Dh
0x180119470  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180119477  mov     ecx, edi
0x180119479  call    AslLogCallPrintf
0x18011947e  test    rbx, rbx
0x180119481  jz      short loc_1801194A0
0x180119483  mov     rcx, [rbx]
0x180119486  call    AslFileMappingDelete
0x18011948b  mov     rcx, gs:60h
0x180119494  mov     rdx, rbx
0x180119497  mov     rcx, [rcx+30h]
0x18011949b  call    AslFree
0x1801194a0  xor     eax, eax
0x1801194a2  mov     rcx, [rbp+var_8]
0x1801194a6  xor     rcx, rsp; StackCookie
0x1801194a9  call    __security_check_cookie
0x1801194ae  lea     r11, [rsp+60h+var_s0]
0x1801194b3  mov     rbx, [r11+38h]
0x1801194b7  mov     rsi, [r11+48h]
0x1801194bb  mov     rsp, r11
0x1801194be  pop     r14
0x1801194c0  pop     r13
0x1801194c2  pop     r12
0x1801194c4  pop     rdi
0x1801194c5  pop     rbp
0x1801194c6  retn
```
