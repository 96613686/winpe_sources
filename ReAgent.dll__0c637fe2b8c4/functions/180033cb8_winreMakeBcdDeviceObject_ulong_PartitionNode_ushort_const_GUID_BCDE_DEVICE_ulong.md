# winreMakeBcdDeviceObject(ulong,PartitionNode *,ushort const *,_GUID *,_BCDE_DEVICE * *,ulong *)

- ea: `0x180033cb8`
- end: `0x180033f4c`
- name: `?winreMakeBcdDeviceObject@@YAKKPEAUPartitionNode@@PEBGPEAU_GUID@@PEAPEAU_BCDE_DEVICE@@PEAK@Z`
- size: `660`
- prototype: `unsigned int(unsigned int, struct PartitionNode *, const unsigned __int16 *, struct _GUID *, struct _BCDE_DEVICE **, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800333b4`
- `0x180034c8c`
- `0x18003648c`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x180033cb8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180033f41`
- `KERNEL32!HeapFree` at `0x180033f41`
- `KERNEL32!HeapAlloc` at `0x180033dd2`
- `KERNEL32!HeapAlloc` at `0x180033ea9`
- `KERNEL32!HeapAlloc` at `0x180033dd2`
- `KERNEL32!HeapAlloc` at `0x180033ea9`
- `KERNEL32!GetProcessHeap` at `0x180033dbf`
- `KERNEL32!GetProcessHeap` at `0x180033e96`
- `KERNEL32!GetProcessHeap` at `0x180033f33`
- `KERNEL32!GetProcessHeap` at `0x180033dbf`
- `KERNEL32!GetProcessHeap` at `0x180033e96`
- `KERNEL32!GetProcessHeap` at `0x180033f33`

## string_xrefs

- `0x180033d05`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180033d78`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180033ebf`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180033f0e`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180033f07`: `failed to copy partition path`
- `0x180033d8c`: `failed to get relative path length`
- `0x180033e37`: `failed to copy device file path`

## pseudocode

```c
__int64 __fastcall winreMakeBcdDeviceObject(
        __int64 a1,
        struct PartitionNode *a2,
        unsigned __int16 *a3,
        struct _GUID *a4,
        struct _BCDE_DEVICE **a5,
        unsigned int *a6)
{
  const unsigned __int16 *v6; // r13
  int v9; // edi
  int v10; // r11d
  unsigned int v11; // esi
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // r15
  SIZE_T v14; // r14
  HANDLE v15; // rax
  char *v16; // rax
  unsigned __int16 *v17; // rdi
  int v18; // eax
  int v19; // r9d
  unsigned __int16 *v20; // r8
  unsigned __int64 v21; // rdx
  const wchar_t *v22; // r8
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v25; // rax
  HANDLE v26; // rax
  int v27; // [rsp+28h] [rbp-40h]
  unsigned __int64 v28; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int16 *v29; // [rsp+80h] [rbp+18h]

  v29 = a3;
  v6 = (const unsigned __int16 *)((char *)a2 + 684);
  v28 = 0;
  v9 = StringCchLengthW((const unsigned __int16 *)a2 + 342, 0x12Eu, &v28);
  if ( v9 >= 0 )
  {
    v12 = v28;
    if ( v10 == 2 )
    {
      LODWORD(v14) = 2 * v28 + 62;
      ProcessHeap = GetProcessHeap();
      v25 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v12 + 62);
      v17 = v25;
      if ( !v25 )
      {
        v27 = 861;
        goto LABEL_21;
      }
      *(_DWORD *)v25 = 2;
      v18 = StringCchCopyW(v25 + 10, v12 + 1, v6);
      if ( v18 < 0 )
      {
        v19 = 867;
        goto LABEL_24;
      }
    }
    else if ( v10 == 4 )
    {
      v28 = 0;
      v9 = StringCchLengthW(a3, 0x12Eu, &v28);
      if ( v9 < 0 )
      {
        UnattendLogW(
          2,
          L"winreMakeBcdDeviceObject %s (0x%x) in file %S line %d",
          L"failed to get relative path length",
          (unsigned int)v9,
          "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
          889);
        return (unsigned __int16)v9;
      }
      ++v28;
      v13 = (2 * v28 + 61) & 0xFFFFFFFFFFFFFFFEuLL;
      v14 = v13 + ((2 * v12 + 63) & 0xFFFFFFFFFFFFFFFEuLL);
      v15 = GetProcessHeap();
      v16 = (char *)HeapAlloc(v15, 8u, v14);
      v17 = (unsigned __int16 *)v16;
      if ( !v16 )
      {
        v27 = 898;
LABEL_21:
        v11 = 8;
        UnattendLogW(
          2,
          L"winreMakeBcdDeviceObject %s (0x%x) in file %S line %d",
          L"failed to allocate memory",
          8,
          "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
          v27);
        return v11;
      }
      *(_DWORD *)&v16[v13] = 2;
      v18 = StringCchCopyW((unsigned __int16 *)&v16[v13 + 20], v12 + 1, v6);
      if ( v18 < 0 )
      {
        v19 = 910;
LABEL_24:
        v22 = L"failed to copy partition path";
        goto LABEL_25;
      }
      v20 = v29;
      v21 = v28;
      *(_DWORD *)v17 = 4;
      *((_DWORD *)v17 + 5) = v13;
      v18 = StringCchCopyW(v17 + 12, v21, v20);
      if ( v18 < 0 )
      {
        v22 = L"failed to copy device file path";
        v19 = 917;
LABEL_25:
        v11 = (unsigned __int16)v18;
        UnattendLogW(
          2,
          L"winreMakeBcdDeviceObject %s (0x%x) in file %S line %d",
          v22,
          (unsigned int)v18,
          "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
          v19);
        v26 = GetProcessHeap();
        HeapFree(v26, 0, v17);
        return v11;
      }
      if ( a4 )
        *(struct _GUID *)(v17 + 2) = *a4;
    }
    else
    {
      v17 = 0;
      LODWORD(v14) = 0;
    }
    v11 = 0;
    *a5 = (struct _BCDE_DEVICE *)v17;
    *a6 = v14;
    return v11;
  }
  UnattendLogW(
    2,
    L"winreMakeBcdDeviceObject %s (0x%x) in file %S line %d",
    L"failed to get string length",
    (unsigned int)v9,
    "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
    849);
  return (unsigned __int16)v9;
}

```

## disassembly

```asm
0x180033cb8  mov     rax, rsp
0x180033cbb  mov     [rax+8], rbx
0x180033cbf  mov     [rax+18h], r8
0x180033cc3  push    rbp
0x180033cc4  push    rsi
0x180033cc5  push    rdi
0x180033cc6  push    r12
0x180033cc8  push    r13
0x180033cca  push    r14
0x180033ccc  push    r15
0x180033cce  sub     rsp, 30h
0x180033cd2  lea     r13, [rdx+2ACh]
0x180033cd9  mov     qword ptr [rax+10h], 0
0x180033ce1  mov     r11d, ecx
0x180033ce4  mov     r14d, 12Eh
0x180033cea  mov     rbp, r8
0x180033ced  mov     edx, r14d; unsigned __int64
0x180033cf0  mov     rcx, r13; unsigned __int16 *
0x180033cf3  lea     r8, [rax+10h]; unsigned __int64 *
0x180033cf7  mov     r12, r9
0x180033cfa  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180033cff  mov     edi, eax
0x180033d01  test    eax, eax
0x180033d03  jns     short loc_180033D3C
0x180033d05  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180033d0c  mov     [rsp+68h+var_40], 351h
0x180033d14  mov     [rsp+68h+var_48], rcx
0x180033d19  lea     r8, aFailedToGetStr; "failed to get string length"
0x180033d20  mov     ecx, 2
0x180033d25  lea     rdx, aWinremakebcdde; "winreMakeBcdDeviceObject %s (0x%x) in f"...
0x180033d2c  mov     r9d, edi
0x180033d2f  call    UnattendLogW
0x180033d34  movzx   esi, di
0x180033d37  jmp     loc_180033E70
0x180033d3c  mov     rsi, [rsp+68h+arg_8]
0x180033d41  mov     ebx, 2
0x180033d46  cmp     r11d, ebx
0x180033d49  jz      loc_180033E8E
0x180033d4f  cmp     r11d, 4
0x180033d53  jnz     loc_180033E87
0x180033d59  lea     r8, [rsp+68h+arg_8]; unsigned __int64 *
0x180033d5e  mov     [rsp+68h+arg_8], 0
0x180033d67  mov     rdx, r14; unsigned __int64
0x180033d6a  mov     rcx, rbp; unsigned __int16 *
0x180033d6d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180033d72  mov     edi, eax
0x180033d74  test    eax, eax
0x180033d76  jns     short loc_180033D97
0x180033d78  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180033d7f  mov     [rsp+68h+var_40], 379h
0x180033d87  mov     [rsp+68h+var_48], rcx
0x180033d8c  lea     r8, aFailedToGetRel; "failed to get relative path length"
0x180033d93  mov     ecx, ebx
0x180033d95  jmp     short loc_180033D25
0x180033d97  mov     rax, [rsp+68h+arg_8]
0x180033d9c  lea     r14, ds:3Fh[rsi*2]
0x180033da4  inc     rax
0x180033da7  and     r14, 0FFFFFFFFFFFFFFFEh
0x180033dab  mov     [rsp+68h+arg_8], rax
0x180033db0  lea     r15, ds:3Dh[rax*2]
0x180033db8  and     r15, 0FFFFFFFFFFFFFFFEh
0x180033dbc  add     r14, r15
0x180033dbf  call    cs:__imp_GetProcessHeap
0x180033dc5  mov     ebp, 8
0x180033dca  mov     r8, r14; dwBytes
0x180033dcd  mov     rcx, rax; hHeap
0x180033dd0  mov     edx, ebp; dwFlags
0x180033dd2  call    cs:__imp_HeapAlloc
0x180033dd8  mov     rdi, rax
0x180033ddb  test    rax, rax
0x180033dde  jnz     short loc_180033DED
0x180033de0  mov     [rsp+68h+var_40], 382h
0x180033de8  jmp     loc_180033EBF
0x180033ded  lea     rcx, [r15+14h]
0x180033df1  mov     [r15+rax], ebx
0x180033df5  add     rcx, rdi; unsigned __int16 *
0x180033df8  lea     rdx, [rsi+1]; unsigned __int64
0x180033dfc  mov     r8, r13; unsigned __int16 *
0x180033dff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033e04  test    eax, eax
0x180033e06  jns     short loc_180033E13
0x180033e08  mov     r9d, 38Eh
0x180033e0e  jmp     loc_180033F07
0x180033e13  mov     r8, [rsp+68h+arg_10]; unsigned __int16 *
0x180033e1b  lea     rcx, [rdi+18h]; unsigned __int16 *
0x180033e1f  mov     rdx, [rsp+68h+arg_8]; unsigned __int64
0x180033e24  mov     dword ptr [rdi], 4
0x180033e2a  mov     [rdi+14h], r15d
0x180033e2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033e33  test    eax, eax
0x180033e35  jns     short loc_180033E49
0x180033e37  lea     r8, aFailedToCopyDe; "failed to copy device file path"
0x180033e3e  mov     r9d, 395h
0x180033e44  jmp     loc_180033F0E
0x180033e49  test    r12, r12
0x180033e4c  jz      short loc_180033E58
0x180033e4e  movups  xmm0, xmmword ptr [r12]
0x180033e53  movdqu  xmmword ptr [rdi+4], xmm0
0x180033e58  mov     rcx, [rsp+68h+arg_20]
0x180033e60  xor     esi, esi
0x180033e62  mov     [rcx], rdi
0x180033e65  mov     rcx, [rsp+68h+arg_28]
0x180033e6d  mov     [rcx], r14d
0x180033e70  mov     rbx, [rsp+68h+arg_0]
0x180033e75  mov     eax, esi
0x180033e77  add     rsp, 30h
0x180033e7b  pop     r15
0x180033e7d  pop     r14
0x180033e7f  pop     r13
0x180033e81  pop     r12
0x180033e83  pop     rdi
0x180033e84  pop     rsi
0x180033e85  pop     rbp
0x180033e86  retn
0x180033e87  xor     edi, edi
0x180033e89  xor     r14d, r14d
0x180033e8c  jmp     short loc_180033E58
0x180033e8e  lea     r14, ds:3Eh[rsi*2]
0x180033e96  call    cs:__imp_GetProcessHeap
0x180033e9c  mov     ebp, 8
0x180033ea1  mov     r8, r14; dwBytes
0x180033ea4  mov     rcx, rax; hHeap
0x180033ea7  mov     edx, ebp; dwFlags
0x180033ea9  call    cs:__imp_HeapAlloc
0x180033eaf  mov     rdi, rax
0x180033eb2  test    rax, rax
0x180033eb5  jnz     short loc_180033EE7
0x180033eb7  mov     [rsp+68h+var_40], 35Dh
0x180033ebf  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180033ec6  mov     r9d, ebp
0x180033ec9  mov     [rsp+68h+var_48], rcx
0x180033ece  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x180033ed5  mov     ecx, ebx
0x180033ed7  lea     rdx, aWinremakebcdde; "winreMakeBcdDeviceObject %s (0x%x) in f"...
0x180033ede  mov     esi, ebp
0x180033ee0  call    UnattendLogW
0x180033ee5  jmp     short loc_180033E70
0x180033ee7  lea     rcx, [rax+14h]; unsigned __int16 *
0x180033eeb  mov     [rax], ebx
0x180033eed  mov     r8, r13; unsigned __int16 *
0x180033ef0  lea     rdx, [rsi+1]; unsigned __int64
0x180033ef4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033ef9  test    eax, eax
0x180033efb  jns     loc_180033E58
0x180033f01  mov     r9d, 363h
0x180033f07  lea     r8, aFailedToCopyPa; "failed to copy partition path"
0x180033f0e  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180033f15  mov     [rsp+68h+var_40], r9d
0x180033f1a  mov     [rsp+68h+var_48], rcx
0x180033f1f  lea     rdx, aWinremakebcdde; "winreMakeBcdDeviceObject %s (0x%x) in f"...
0x180033f26  mov     ecx, ebx
0x180033f28  movzx   esi, ax
0x180033f2b  mov     r9d, eax
0x180033f2e  call    UnattendLogW
0x180033f33  call    cs:__imp_GetProcessHeap
0x180033f39  mov     r8, rdi; lpMem
0x180033f3c  xor     edx, edx; dwFlags
0x180033f3e  mov     rcx, rax; hHeap
0x180033f41  call    cs:__imp_HeapFree
0x180033f47  jmp     loc_180033E70
```
