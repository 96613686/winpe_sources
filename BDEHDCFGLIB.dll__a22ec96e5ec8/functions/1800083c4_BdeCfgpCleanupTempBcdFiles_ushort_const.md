# BdeCfgpCleanupTempBcdFiles(ushort const *)

- ea: `0x1800083c4`
- end: `0x18000849e`
- name: `?BdeCfgpCleanupTempBcdFiles@@YAJPEBG@Z`
- size: `218`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007bd0`

## callees

- `0x1800080f0`
- `0x1800083c4`
- `0x180008aac`
- `0x180008e1c`

## pseudocode

```c
__int64 __fastcall BdeCfgpCleanupTempBcdFiles(const unsigned __int16 *a1)
{
  WCHAR *v1; // rsi
  WCHAR *v2; // r14
  WCHAR *v3; // rdi
  int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  LPCWSTR v10; // [rsp+50h] [rbp+30h] BYREF
  LPCWSTR v11; // [rsp+58h] [rbp+38h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp+40h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = 0;
  lpFileName = 0;
  v11 = 0;
  v10 = 0;
  if ( a1 )
  {
    v6 = BdeCfgpBuildVolumePath(a1, L"\\Boot\\BCD.tmp", (unsigned __int16 **)&lpFileName);
    v1 = (WCHAR *)lpFileName;
    v5 = v6;
    if ( v6 >= 0 )
    {
      v5 = BdeCfgpDeleteFile(lpFileName);
      if ( v5 >= 0 )
      {
        v7 = BdeCfgpBuildVolumePath(a1, L"\\Boot\\BCD.tmp.LOG1", (unsigned __int16 **)&v11);
        v2 = (WCHAR *)v11;
        v5 = v7;
        if ( v7 >= 0 )
        {
          v5 = BdeCfgpDeleteFile(v11);
          if ( v5 >= 0 )
          {
            v8 = BdeCfgpBuildVolumePath(a1, L"\\Boot\\BCD.tmp.LOG2", (unsigned __int16 **)&v10);
            v3 = (WCHAR *)v10;
            v5 = v8;
            if ( v8 >= 0 )
              v5 = BdeCfgpDeleteFile(v10);
          }
        }
      }
    }
  }
  else
  {
    v5 = -2147467261;
  }
  BdeCfgpFree(v1);
  BdeCfgpFree(v2);
  BdeCfgpFree(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800083c4  mov     [rsp-28h+arg_18], rbx
0x1800083c9  push    rbp
0x1800083ca  push    rsi
0x1800083cb  push    rdi
0x1800083cc  push    r14
0x1800083ce  push    r15
0x1800083d0  mov     rbp, rsp
0x1800083d3  sub     rsp, 20h
0x1800083d7  xor     esi, esi
0x1800083d9  xor     r14d, r14d
0x1800083dc  xor     edi, edi
0x1800083de  mov     [rbp+lpFileName], rsi
0x1800083e2  mov     [rbp+arg_8], r14
0x1800083e6  mov     r15, rcx
0x1800083e9  mov     [rbp+arg_0], rdi
0x1800083ed  test    rcx, rcx
0x1800083f0  jnz     short loc_1800083F9
0x1800083f2  mov     ebx, 80004003h
0x1800083f7  jmp     short loc_180008473
0x1800083f9  lea     r8, [rbp+lpFileName]; unsigned __int16 **
0x1800083fd  lea     rdx, aBootBcdTmp; "\\Boot\\BCD.tmp"
0x180008404  call    ?BdeCfgpBuildVolumePath@@YAJPEBG0PEAPEAG@Z; BdeCfgpBuildVolumePath(ushort const *,ushort const *,ushort * *)
0x180008409  mov     rsi, [rbp+lpFileName]
0x18000840d  mov     ebx, eax
0x18000840f  test    eax, eax
0x180008411  js      short loc_180008473
0x180008413  mov     rcx, rsi; lpFileName
0x180008416  call    ?BdeCfgpDeleteFile@@YAJPEAG@Z; BdeCfgpDeleteFile(ushort *)
0x18000841b  mov     ebx, eax
0x18000841d  test    eax, eax
0x18000841f  js      short loc_180008473
0x180008421  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x180008425  mov     rcx, r15; unsigned __int16 *
0x180008428  lea     rdx, aBootBcdTmpLog1; "\\Boot\\BCD.tmp.LOG1"
0x18000842f  call    ?BdeCfgpBuildVolumePath@@YAJPEBG0PEAPEAG@Z; BdeCfgpBuildVolumePath(ushort const *,ushort const *,ushort * *)
0x180008434  mov     r14, [rbp+arg_8]
0x180008438  mov     ebx, eax
0x18000843a  test    eax, eax
0x18000843c  js      short loc_180008473
0x18000843e  mov     rcx, r14; lpFileName
0x180008441  call    ?BdeCfgpDeleteFile@@YAJPEAG@Z; BdeCfgpDeleteFile(ushort *)
0x180008446  mov     ebx, eax
0x180008448  test    eax, eax
0x18000844a  js      short loc_180008473
0x18000844c  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x180008450  mov     rcx, r15; unsigned __int16 *
0x180008453  lea     rdx, aBootBcdTmpLog2; "\\Boot\\BCD.tmp.LOG2"
0x18000845a  call    ?BdeCfgpBuildVolumePath@@YAJPEBG0PEAPEAG@Z; BdeCfgpBuildVolumePath(ushort const *,ushort const *,ushort * *)
0x18000845f  mov     rdi, [rbp+arg_0]
0x180008463  mov     ebx, eax
0x180008465  test    eax, eax
0x180008467  js      short loc_180008473
0x180008469  mov     rcx, rdi; lpFileName
0x18000846c  call    ?BdeCfgpDeleteFile@@YAJPEAG@Z; BdeCfgpDeleteFile(ushort *)
0x180008471  mov     ebx, eax
0x180008473  mov     rcx, rsi; lpMem
0x180008476  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x18000847b  mov     rcx, r14; lpMem
0x18000847e  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x180008483  mov     rcx, rdi; lpMem
0x180008486  call    ?BdeCfgpFree@@YAXPEAX@Z; BdeCfgpFree(void *)
0x18000848b  mov     eax, ebx
0x18000848d  mov     rbx, [rsp+20h+arg_18]
0x180008492  add     rsp, 20h
0x180008496  pop     r15
0x180008498  pop     r14
0x18000849a  pop     rdi
0x18000849b  pop     rsi
0x18000849c  pop     rbp
0x18000849d  retn
```
