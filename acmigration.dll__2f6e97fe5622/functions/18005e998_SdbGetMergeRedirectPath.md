# SdbGetMergeRedirectPath

- ea: `0x18005e998`
- end: `0x18005eb4d`
- name: `SdbGetMergeRedirectPath`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005ec7c`

## callees

- `0x1800543c0`
- `0x18005a3d4`
- `0x18005e998`
- `0x18005f728`
- `0x18006002c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18005eae1`
- `ntdll!RtlFreeHeap` at `0x18005eb10`
- `ntdll!RtlFreeHeap` at `0x18005eae1`
- `ntdll!RtlFreeHeap` at `0x18005eb10`

## string_xrefs

- `0x18005ea3d`: `SdbpGetMergeRedirectPathInternal failed[%x]`
- `0x18005ea36`: `SdbGetMergeRedirectPath`
- `0x18005ea89`: `SdbGetMergeRedirectPath`

## pseudocode

```c
__int64 __fastcall SdbGetMergeRedirectPath(_QWORD *a1, BOOL *a2, int a3, WCHAR *a4)
{
  int MergeRedirectPathInternal; // ebx
  BOOL v10; // esi
  const wchar_t *FileNamePart; // rax
  int v12; // eax
  PVOID P[9]; // [rsp+30h] [rbp-48h] BYREF
  int v14; // [rsp+80h] [rbp+8h] BYREF

  v14 = 0;
  P[0] = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !(unsigned int)SdbpGetMergeSdbsSupported() )
  {
    MergeRedirectPathInternal = -1073741772;
    goto LABEL_20;
  }
  MergeRedirectPathInternal = SdbpGetMergeRedirectPathInternal(P, &v14, 1, a4);
  if ( (int)(MergeRedirectPathInternal + 0x80000000) >= 0 && MergeRedirectPathInternal != -1073741772 )
  {
    AslLogCallPrintf(
      1,
      "SdbGetMergeRedirectPath",
      2134,
      "SdbpGetMergeRedirectPathInternal failed[%x]",
      MergeRedirectPathInternal);
    goto LABEL_20;
  }
  v10 = 0;
  if ( MergeRedirectPathInternal >= 0 )
    v10 = v14 != 0;
  if ( !a3 || !v10 )
  {
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    v12 = SdbpGetMergeRedirectPathInternal(P, 0, 0, a4);
    MergeRedirectPathInternal = v12;
    if ( v12 < 0 )
    {
      if ( v12 != -1073741772 )
        AslLogCallPrintf(1, "SdbGetMergeRedirectPath", 2149, "SdbpGetMergeRedirectPathInternal failed[%x]", v12);
      goto LABEL_20;
    }
    goto LABEL_17;
  }
  FileNamePart = (const wchar_t *)AslPathGetFileNamePart(a4);
  AslLogCallPrintf(
    1,
    "SdbGetMergeRedirectPath",
    2158,
    "Handled Error: MergeSdb staged deletion feature was used, probably to prevent sdb mismatch error. SdbName: [%ls].",
    FileNamePart);
  if ( P[0] )
  {
    if ( MergeRedirectPathInternal < 0 )
    {
LABEL_20:
      if ( P[0] )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
      return (unsigned int)MergeRedirectPathInternal;
    }
LABEL_17:
    *a1 = P[0];
    P[0] = 0;
    if ( a2 )
      *a2 = v10;
    MergeRedirectPathInternal = 0;
    goto LABEL_20;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x18005e998  mov     rax, rsp
0x18005e99b  push    rbx
0x18005e99c  push    rbp
0x18005e99d  push    rsi
0x18005e99e  push    r12
0x18005e9a0  push    r14
0x18005e9a2  push    r15
0x18005e9a4  sub     rsp, 48h
0x18005e9a8  mov     dword ptr [rax+8], 0
0x18005e9af  mov     rbp, r9
0x18005e9b2  mov     qword ptr [rax-48h], 0
0x18005e9ba  mov     r12d, r8d
0x18005e9bd  mov     r14, rdx
0x18005e9c0  mov     r15, rcx
0x18005e9c3  test    rcx, rcx
0x18005e9c6  jnz     short loc_18005E9D2
0x18005e9c8  mov     eax, 0C00000EFh
0x18005e9cd  jmp     loc_18005EAE9
0x18005e9d2  mov     qword ptr [rcx], 0
0x18005e9d9  test    r14, r14
0x18005e9dc  jz      short loc_18005E9E4
0x18005e9de  mov     dword ptr [rdx], 0
0x18005e9e4  call    SdbpGetMergeSdbsSupported
0x18005e9e9  test    eax, eax
0x18005e9eb  jnz     short loc_18005E9F7
0x18005e9ed  mov     ebx, 0C0000034h
0x18005e9f2  jmp     loc_18005EAC8
0x18005e9f7  mov     esi, 1
0x18005e9fc  lea     rdx, [rsp+78h+arg_0]
0x18005ea04  mov     r8d, esi
0x18005ea07  lea     rcx, [rsp+78h+P]
0x18005ea0c  mov     r9, rbp
0x18005ea0f  call    SdbpGetMergeRedirectPathInternal
0x18005ea14  mov     ebx, eax
0x18005ea16  mov     eax, 80000000h
0x18005ea1b  lea     edx, [rbx+rax]
0x18005ea1e  test    eax, edx
0x18005ea20  jnz     short loc_18005EA4B
0x18005ea22  cmp     ebx, 0C0000034h
0x18005ea28  jz      short loc_18005EA4B
0x18005ea2a  mov     dword ptr [rsp+78h+var_58], ebx
0x18005ea2e  mov     r8d, 856h
0x18005ea34  mov     ecx, esi
0x18005ea36  lea     rdx, aSdbgetmergered_0; "SdbGetMergeRedirectPath"
0x18005ea3d  lea     r9, aSdbpgetmergere_0; "SdbpGetMergeRedirectPathInternal failed"...
0x18005ea44  call    AslLogCallPrintf
0x18005ea49  jmp     short loc_18005EAC8
0x18005ea4b  xor     esi, esi
0x18005ea4d  test    ebx, ebx
0x18005ea4f  js      short loc_18005EA5E
0x18005ea51  cmp     [rsp+78h+arg_0], esi
0x18005ea58  lea     eax, [rsi+1]
0x18005ea5b  cmovnz  esi, eax
0x18005ea5e  test    r12d, r12d
0x18005ea61  jz      loc_18005EAF7
0x18005ea67  test    esi, esi
0x18005ea69  jz      loc_18005EAF7
0x18005ea6f  mov     rcx, rbp
0x18005ea72  call    AslPathGetFileNamePart
0x18005ea77  lea     r9, aHandledErrorMe_0; "Handled Error: MergeSdb staged deletion"...
0x18005ea7e  mov     [rsp+78h+var_58], rax
0x18005ea83  mov     r8d, 86Eh
0x18005ea89  lea     rdx, aSdbgetmergered_0; "SdbGetMergeRedirectPath"
0x18005ea90  mov     ecx, 1
0x18005ea95  call    AslLogCallPrintf
0x18005ea9a  cmp     [rsp+78h+P], 0
0x18005eaa0  jnz     short loc_18005EAA9
0x18005eaa2  mov     ebx, 0C0000034h
0x18005eaa7  jmp     short loc_18005EAE7
0x18005eaa9  test    ebx, ebx
0x18005eaab  js      short loc_18005EAC8
0x18005eaad  mov     rax, [rsp+78h+P]
0x18005eab2  mov     [r15], rax
0x18005eab5  mov     [rsp+78h+P], 0
0x18005eabe  test    r14, r14
0x18005eac1  jz      short loc_18005EAC6
0x18005eac3  mov     [r14], esi
0x18005eac6  xor     ebx, ebx
0x18005eac8  mov     r8, [rsp+78h+P]; P
0x18005eacd  test    r8, r8
0x18005ead0  jz      short loc_18005EAE7
0x18005ead2  mov     rcx, gs:60h
0x18005eadb  xor     edx, edx; Flags
0x18005eadd  mov     rcx, [rcx+30h]; HeapHandle
0x18005eae1  call    cs:__imp_RtlFreeHeap
0x18005eae7  mov     eax, ebx
0x18005eae9  add     rsp, 48h
0x18005eaed  pop     r15
0x18005eaef  pop     r14
0x18005eaf1  pop     r12
0x18005eaf3  pop     rsi
0x18005eaf4  pop     rbp
0x18005eaf5  pop     rbx
0x18005eaf6  retn
0x18005eaf7  mov     r8, [rsp+78h+P]; P
0x18005eafc  test    r8, r8
0x18005eaff  jz      short loc_18005EB16
0x18005eb01  mov     rcx, gs:60h
0x18005eb0a  xor     edx, edx; Flags
0x18005eb0c  mov     rcx, [rcx+30h]; HeapHandle
0x18005eb10  call    cs:__imp_RtlFreeHeap
0x18005eb16  mov     r9, rbp
0x18005eb19  lea     rcx, [rsp+78h+P]
0x18005eb1e  xor     r8d, r8d
0x18005eb21  xor     edx, edx
0x18005eb23  call    SdbpGetMergeRedirectPathInternal
0x18005eb28  mov     ebx, eax
0x18005eb2a  test    eax, eax
0x18005eb2c  jns     loc_18005EAAD
0x18005eb32  cmp     eax, 0C0000034h
0x18005eb37  jz      short loc_18005EAC8
0x18005eb39  mov     dword ptr [rsp+78h+var_58], eax
0x18005eb3d  mov     r8d, 865h
0x18005eb43  mov     ecx, 1
0x18005eb48  jmp     loc_18005EA36
```
