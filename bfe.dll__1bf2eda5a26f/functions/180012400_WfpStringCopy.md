# WfpStringCopy

- ea: `0x180012400`
- end: `0x1800126d9`
- name: `WfpStringCopy`
- size: `729`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `12`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000fad0`
- `0x1800215e4`
- `0x180021858`
- `0x18003498c`
- `0x18003a434`
- `0x18003dfc8`
- `0x180043da8`
- `0x1800485bc`
- `0x18004a7a4`
- `0x18004aeb8`
- `0x180066508`
- `0x1800707e0`

## callees

- `0x18000f1a8`
- `0x180010ad0`
- `0x180012400`
- `0x180012b54`
- `0x180018b74`
- `0x18004e230`
- `0x1800542bc`
- `0x180058b30`
- `0x180087dcc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012493`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012493`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800126c7`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800126c7`

## string_xrefs

- `0x180012587`: `WfpBufferCopy`
- `0x180012669`: `WfpStringCopy`

## pseudocode

```c
__int64 __fastcall WfpStringCopy(_WORD *Src, __int64 a2, void **a3)
{
  __int64 result; // rax
  __int64 v6; // rax
  SIZE_T v8; // rbp
  __int64 v9; // rsi
  void *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdi
  _QWORD *v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rax
  int v17; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v18[16]; // [rsp+38h] [rbp-60h] BYREF
  const char *v19; // [rsp+48h] [rbp-50h]
  __int64 v20; // [rsp+50h] [rbp-48h]
  int *v21; // [rsp+58h] [rbp-40h]
  __int64 v22; // [rsp+60h] [rbp-38h]

  *a3 = 0;
  result = 0;
  if ( Src )
  {
    v6 = -1;
    while ( Src[++v6] != 0 )
      ;
    v8 = 2 * v6 + 2;
    v9 = 0;
    if ( 2 * v6 == -2 )
      goto LABEL_24;
    if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(Src, a2, a3) )
    {
      v13 = WfpMemAlloc25B(v8);
    }
    else
    {
      v10 = HeapAlloc(gWfpHeap, 0, v8);
      *a3 = v10;
      if ( v10 )
      {
        v13 = 0;
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v10));
      }
      else
      {
        v16 = WfpReportSysErrorAsNtStatus(v11, "HeapAlloc", 3221225495LL);
        v13 = v16;
        if ( v16 )
          WfpReportError(v16, "WfpMemAlloc");
      }
    }
    if ( v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v12, 0, (__int64)"WfpPoolAllocNonPaged", v13);
        v14 = WPP_GLOBAL_Control;
      }
      if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
      {
        v17 = v13;
        v21 = &v17;
        v19 = "WfpPoolAllocNonPaged";
        v20 = 21;
        v22 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v12,
          3,
          (__int64)v18);
        v14 = WPP_GLOBAL_Control;
        goto LABEL_19;
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
    }
    if ( !v13 )
    {
      memcpy_0(*a3, Src, v8);
      return 0;
    }
LABEL_19:
    v9 = v13;
    v15 = v13;
    if ( v14 != &WPP_GLOBAL_Control && *((_BYTE *)v14 + 25) >= 2u && (*((_BYTE *)v14 + 28) & 1) != 0 )
      WPP_SF_Ssd(v14[2], 26, v12, 0, (__int64)"WfpBufferCopy", v13);
    if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
    {
      v17 = v13;
      v21 = &v17;
      v19 = "WfpBufferCopy";
      v20 = 14;
      v22 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        &MICROSOFT_WFP_PROVIDER_Context,
        (__int64)WFP_USERMODE_ERROR,
        v12,
        3,
        (__int64)v18);
      goto LABEL_30;
    }
LABEL_24:
    v15 = v9;
    if ( !v9 )
      return v15;
LABEL_30:
    WfpReportError(v9, "WfpStringCopy");
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x180012400  mov     r11, rsp
0x180012403  push    rbx
0x180012404  push    r14
0x180012406  push    r15
0x180012408  sub     rsp, 80h
0x18001240f  mov     rax, cs:__security_cookie
0x180012416  xor     rax, rsp
0x180012419  mov     [rsp+98h+var_30], rax
0x18001241e  xor     r15d, r15d
0x180012421  mov     r14, r8
0x180012424  mov     [r8], r15
0x180012427  mov     rbx, rcx
0x18001242a  mov     eax, r15d
0x18001242d  test    rcx, rcx
0x180012430  jz      loc_1800125EB
0x180012436  mov     [r11+10h], rbp
0x18001243a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180012441  mov     [r11+20h], rsi
0x180012445  nop     word ptr [rax+rax+00000000h]
0x180012450  cmp     [rcx+rax*2+2], r15w
0x180012456  lea     rax, [rax+1]
0x18001245a  jnz     short loc_180012450
0x18001245c  lea     rbp, ds:2[rax*2]
0x180012464  mov     [rsp+98h+var_20], rdi
0x180012469  mov     [rsp+98h+var_28], r12
0x18001246e  mov     rsi, r15
0x180012471  test    rbp, rbp
0x180012474  jz      loc_1800125C2
0x18001247a  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18001247f  xor     edx, edx; dwFlags
0x180012481  test    eax, eax
0x180012483  jnz     loc_180012605
0x180012489  mov     rcx, cs:gWfpHeap; hHeap
0x180012490  mov     r8, rbp; dwBytes
0x180012493  call    cs:__imp_HeapAlloc
0x180012499  mov     [r14], rax
0x18001249c  test    rax, rax
0x18001249f  jz      loc_180012689
0x1800124a5  cmp     cs:gWfpTrackHeapBytes, r15d
0x1800124ac  mov     rdi, r15
0x1800124af  jnz     loc_1800126BB
0x1800124b5  lea     r12, WPP_GLOBAL_Control
0x1800124bc  test    rdi, rdi
0x1800124bf  jz      loc_18001267D
0x1800124c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124cc  lea     rsi, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x1800124d3  cmp     rcx, r12
0x1800124d6  jz      short loc_180012505
0x1800124d8  cmp     byte ptr [rcx+19h], 2
0x1800124dc  jb      short loc_180012505
0x1800124de  test    byte ptr [rcx+1Ch], 1
0x1800124e2  jz      short loc_180012505
0x1800124e4  mov     rcx, [rcx+10h]
0x1800124e8  mov     edx, 1Ah
0x1800124ed  mov     [rsp+98h+var_70], edi
0x1800124f1  xor     r9d, r9d
0x1800124f4  mov     [rsp+98h+var_78], rsi
0x1800124f9  call    WPP_SF_Ssd
0x1800124fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180012505  cmp     cs:1800EF078h, r15d
0x18001250c  jnz     short loc_180012529
0x18001250e  test    rdi, rdi
0x180012511  jnz     short loc_180012581
0x180012513  mov     rcx, [r14]; void *
0x180012516  mov     r8, rbp; Size
0x180012519  mov     rdx, rbx; Src
0x18001251c  call    memcpy_0
0x180012521  mov     rax, rdi
0x180012524  jmp     loc_1800125D1
0x180012529  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x180012530  jz      short loc_18001250E
0x180012532  lea     rax, [rsp+98h+var_68]
0x180012537  mov     [rsp+98h+var_68], edi
0x18001253b  mov     [rsp+98h+var_40], rax
0x180012540  lea     rdx, WFP_USERMODE_ERROR
0x180012547  lea     rax, [rsp+98h+var_60]
0x18001254c  mov     [rsp+98h+var_50], rsi
0x180012551  mov     r9d, 3
0x180012557  mov     [rsp+98h+var_78], rax
0x18001255c  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180012563  mov     [rsp+98h+var_48], 15h
0x18001256c  mov     [rsp+98h+var_38], 4
0x180012575  call    McGenEventWrite_EtwEventWriteTransfer
0x18001257a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012581  mov     rsi, rdi
0x180012584  mov     rbx, rdi
0x180012587  lea     rbp, aWfpbuffercopy; "WfpBufferCopy"
0x18001258e  cmp     rcx, r12
0x180012591  jz      short loc_1800125B9
0x180012593  cmp     byte ptr [rcx+19h], 2
0x180012597  jb      short loc_1800125B9
0x180012599  test    byte ptr [rcx+1Ch], 1
0x18001259d  jz      short loc_1800125B9
0x18001259f  mov     rcx, [rcx+10h]
0x1800125a3  mov     edx, 1Ah
0x1800125a8  mov     [rsp+98h+var_70], edi
0x1800125ac  xor     r9d, r9d
0x1800125af  mov     [rsp+98h+var_78], rbp
0x1800125b4  call    WPP_SF_Ssd
0x1800125b9  cmp     cs:1800EF078h, r15d
0x1800125c0  jnz     short loc_180012618
0x1800125c2  mov     rbx, rsi
0x1800125c5  test    rsi, rsi
0x1800125c8  jnz     loc_180012669
0x1800125ce  mov     rax, rbx
0x1800125d1  mov     rdi, [rsp+98h+var_20]
0x1800125d6  mov     r12, [rsp+98h+var_28]
0x1800125db  mov     rbp, [rsp+98h+arg_8]
0x1800125e3  mov     rsi, [rsp+98h+arg_18]
0x1800125eb  mov     rcx, [rsp+98h+var_30]
0x1800125f0  xor     rcx, rsp; StackCookie
0x1800125f3  call    __security_check_cookie
0x1800125f8  add     rsp, 80h
0x1800125ff  pop     r15
0x180012601  pop     r14
0x180012603  pop     rbx
0x180012604  retn
0x180012605  mov     r8, r14
0x180012608  mov     rcx, rbp; dwBytes
0x18001260b  call    WfpMemAlloc25B
0x180012610  mov     rdi, rax
0x180012613  jmp     loc_1800124B5
0x180012618  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x18001261f  jz      short loc_1800125C2
0x180012621  lea     rax, [rsp+98h+var_68]
0x180012626  mov     [rsp+98h+var_68], edi
0x18001262a  mov     [rsp+98h+var_40], rax
0x18001262f  lea     rdx, WFP_USERMODE_ERROR
0x180012636  lea     rax, [rsp+98h+var_60]
0x18001263b  mov     [rsp+98h+var_50], rbp
0x180012640  mov     r9d, 3
0x180012646  mov     [rsp+98h+var_78], rax
0x18001264b  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180012652  mov     [rsp+98h+var_48], 0Eh
0x18001265b  mov     [rsp+98h+var_38], 4
0x180012664  call    McGenEventWrite_EtwEventWriteTransfer
0x180012669  lea     rdx, aWfpstringcopy; "WfpStringCopy"
0x180012670  mov     rcx, rsi
0x180012673  call    WfpReportError
0x180012678  jmp     loc_1800125CE
0x18001267d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012684  jmp     loc_18001250E
0x180012689  mov     r8d, 0C0000017h
0x18001268f  lea     rdx, aHeapalloc; "HeapAlloc"
0x180012696  call    WfpReportSysErrorAsNtStatus
0x18001269b  mov     rdi, rax
0x18001269e  test    rax, rax
0x1800126a1  jz      loc_1800124B5
0x1800126a7  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x1800126ae  mov     rcx, rax
0x1800126b1  call    WfpReportError
0x1800126b6  jmp     loc_1800124B5
0x1800126bb  mov     rcx, cs:gWfpHeap; hHeap
0x1800126c2  mov     r8, rax; lpMem
0x1800126c5  xor     edx, edx; dwFlags
0x1800126c7  call    cs:__imp_HeapSize
0x1800126cd  lock add cs:gWfpHeapBytesAllocated, eax
0x1800126d4  jmp     loc_1800124B5
```
