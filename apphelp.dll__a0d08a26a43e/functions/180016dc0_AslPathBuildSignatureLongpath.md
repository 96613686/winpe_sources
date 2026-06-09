# AslPathBuildSignatureLongpath

- ea: `0x180016dc0`
- end: `0x180016f99`
- name: `AslPathBuildSignatureLongpath`
- size: `473`
- prototype: `__int64 __fastcall(WCHAR **, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180016250`
- `0x18001a714`
- `0x18003d070`

## callees

- `0x18000f114`
- `0x180016dc0`
- `0x180016fa0`
- `0x180017134`
- `0x18001813c`
- `0x18001865c`
- `0x180018f20`
- `0x180033af0`

## string_xrefs

- `0x180016e6d`: `AslPathBuildSignatureLongpath`
- `0x180016edd`: `AslPathBuildSignatureLongpath`
- `0x180016f21`: `AslPathBuildSignatureLongpath`
- `0x180016f4d`: `AslPathBuildSignatureLongpath`
- `0x180016e5c`: `AslPathBuildSignatureForDirectoryFileLongpath for %ws [%x]`
- `0x180016eb8`: `AslPathBuildSignatureForInternetFileLongpath failed for %ws [%x]`
- `0x180016ecb`: `AslPathGetLongFileNameLongpath failed for %ws [%x]`
- `0x180016f0f`: `AslPathIsOnRemovableMedia failed for %ws [%x]`
- `0x180016f3b`: `AslPathIsTemporaryInternetFile failed for %ws [%x]`

## pseudocode

```c
__int64 __fastcall AslPathBuildSignatureLongpath(WCHAR **a1, __int64 a2)
{
  void *v3; // rsi
  int LongFileNameLongpath; // eax
  unsigned int v6; // ebx
  WCHAR *v7; // rdi
  int v8; // eax
  int IsTemporaryInternetFile; // eax
  int v10; // eax
  int v11; // eax
  const char *v12; // r9
  __int64 v13; // r8
  __int64 v15; // [rsp+28h] [rbp-18h]
  WCHAR *v16; // [rsp+30h] [rbp-10h] BYREF
  int v17; // [rsp+70h] [rbp+30h] BYREF
  int v18; // [rsp+80h] [rbp+40h] BYREF
  void *v19; // [rsp+88h] [rbp+48h] BYREF

  *a1 = 0;
  v3 = 0;
  v18 = 0;
  v19 = 0;
  v16 = 0;
  v17 = 0;
  LongFileNameLongpath = AslPathGetLongFileNameLongpath(&v16);
  v6 = LongFileNameLongpath;
  if ( LongFileNameLongpath < 0 )
  {
    AslLogCallPrintf(
      1,
      "AslPathBuildSignatureLongpath",
      1162,
      "AslPathGetLongFileNameLongpath failed for %ws [%x]",
      a2,
      LongFileNameLongpath);
    v7 = v16;
    goto LABEL_14;
  }
  v7 = v16;
  v8 = AslPathIsOnRemovableMedia(&v17, v16);
  v6 = v8;
  if ( v8 < 0 )
  {
    AslLogCallPrintf(1, "AslPathBuildSignatureLongpath", 1172, "AslPathIsOnRemovableMedia failed for %ws [%x]", v7, v8);
    goto LABEL_14;
  }
  if ( !v17 )
  {
    IsTemporaryInternetFile = AslPathIsTemporaryInternetFile(&v18, v7);
    if ( IsTemporaryInternetFile < 0 )
    {
      AslLogCallPrintf(
        2,
        "AslPathBuildSignatureLongpath",
        1186,
        "AslPathIsTemporaryInternetFile failed for %ws [%x]",
        v7,
        IsTemporaryInternetFile);
      v10 = 0;
    }
    else
    {
      v10 = v18;
    }
    if ( !v10 )
      goto LABEL_7;
    v11 = AslPathBuildSignatureForInternetFileLongpath(&v19, v7);
    v6 = v11;
    if ( v11 < 0 )
    {
      v12 = "AslPathBuildSignatureForInternetFileLongpath failed for %ws [%x]";
      v13 = 1198;
      goto LABEL_11;
    }
LABEL_20:
    v3 = v19;
    if ( v19 )
    {
      *a1 = (WCHAR *)v19;
      v3 = 0;
      goto LABEL_8;
    }
LABEL_7:
    *a1 = v7;
    v7 = 0;
LABEL_8:
    v6 = 0;
    goto LABEL_12;
  }
  v11 = AslPathBuildSignatureForDirectoryFileLongpath(&v19, (__int64)v7);
  v6 = v11;
  if ( v11 >= 0 )
    goto LABEL_20;
  v12 = "AslPathBuildSignatureForDirectoryFileLongpath for %ws [%x]";
  v13 = 1179;
LABEL_11:
  LODWORD(v15) = v11;
  AslLogCallPrintf(1, "AslPathBuildSignatureLongpath", v13, v12, v7, v15);
  v3 = v19;
LABEL_12:
  if ( v3 )
    AslFree(NtCurrentPeb()->ProcessHeap, v3);
LABEL_14:
  if ( v7 )
    AslFree(NtCurrentPeb()->ProcessHeap, v7);
  return v6;
}

```

## disassembly

```asm
0x180016dc0  push    rbp
0x180016dc2  push    rbx
0x180016dc3  push    rsi
0x180016dc4  push    rdi
0x180016dc5  push    r14
0x180016dc7  mov     rbp, rsp
0x180016dca  sub     rsp, 40h
0x180016dce  mov     r14, rcx
0x180016dd1  mov     qword ptr [rcx], 0
0x180016dd8  xor     esi, esi
0x180016dda  mov     [rbp+arg_10], 0
0x180016de1  lea     rcx, [rbp+var_10]
0x180016de5  mov     [rbp+arg_18], rsi
0x180016de9  mov     [rbp+var_10], rsi
0x180016ded  mov     rdi, rdx
0x180016df0  mov     [rbp+arg_0], 0
0x180016df7  call    AslPathGetLongFileNameLongpath
0x180016dfc  mov     ebx, eax
0x180016dfe  test    eax, eax
0x180016e00  js      loc_180016EC7
0x180016e06  mov     rdi, [rbp+var_10]
0x180016e0a  lea     rcx, [rbp+arg_0]
0x180016e0e  mov     rdx, rdi
0x180016e11  call    AslPathIsOnRemovableMedia
0x180016e16  mov     ebx, eax
0x180016e18  test    eax, eax
0x180016e1a  js      loc_180016F0B
0x180016e20  mov     rdx, rdi
0x180016e23  cmp     [rbp+arg_0], esi
0x180016e26  jnz     short loc_180016E49
0x180016e28  lea     rcx, [rbp+arg_10]
0x180016e2c  call    AslPathIsTemporaryInternetFile
0x180016e31  test    eax, eax
0x180016e33  js      loc_180016F37
0x180016e39  mov     eax, [rbp+arg_10]
0x180016e3c  test    eax, eax
0x180016e3e  jnz     short loc_180016EA6
0x180016e40  mov     [r14], rdi
0x180016e43  xor     edi, edi
0x180016e45  xor     ebx, ebx
0x180016e47  jmp     short loc_180016E87
0x180016e49  lea     rcx, [rbp+arg_18]
0x180016e4d  call    AslPathBuildSignatureForDirectoryFileLongpath
0x180016e52  mov     ebx, eax
0x180016e54  test    eax, eax
0x180016e56  jns     loc_180016EF4
0x180016e5c  lea     r9, aAslpathbuildsi_1; "AslPathBuildSignatureForDirectoryFileLo"...
0x180016e63  mov     r8d, 49Bh
0x180016e69  mov     dword ptr [rsp+40h+var_18], eax
0x180016e6d  lea     rdx, aAslpathbuildsi_3; "AslPathBuildSignatureLongpath"
0x180016e74  mov     ecx, 1
0x180016e79  mov     [rsp+40h+var_20], rdi
0x180016e7e  call    AslLogCallPrintf
0x180016e83  mov     rsi, [rbp+arg_18]
0x180016e87  test    rsi, rsi
0x180016e8a  jnz     loc_180016F65
0x180016e90  test    rdi, rdi
0x180016e93  jnz     loc_180016F7F
0x180016e99  mov     eax, ebx
0x180016e9b  add     rsp, 40h
0x180016e9f  pop     r14
0x180016ea1  pop     rdi
0x180016ea2  pop     rsi
0x180016ea3  pop     rbx
0x180016ea4  pop     rbp
0x180016ea5  retn
0x180016ea6  mov     rdx, rdi
0x180016ea9  lea     rcx, [rbp+arg_18]
0x180016ead  call    AslPathBuildSignatureForInternetFileLongpath
0x180016eb2  mov     ebx, eax
0x180016eb4  test    eax, eax
0x180016eb6  jns     short loc_180016EF4
0x180016eb8  lea     r9, aAslpathbuildsi_5; "AslPathBuildSignatureForInternetFileLon"...
0x180016ebf  mov     r8d, 4AEh
0x180016ec5  jmp     short loc_180016E69
0x180016ec7  mov     dword ptr [rsp+40h+var_18], eax
0x180016ecb  lea     r9, aAslpathgetlong; "AslPathGetLongFileNameLongpath failed f"...
0x180016ed2  mov     r8d, 48Ah
0x180016ed8  mov     [rsp+40h+var_20], rdi
0x180016edd  lea     rdx, aAslpathbuildsi_3; "AslPathBuildSignatureLongpath"
0x180016ee4  mov     ecx, 1
0x180016ee9  call    AslLogCallPrintf
0x180016eee  mov     rdi, [rbp+var_10]
0x180016ef2  jmp     short loc_180016E90
0x180016ef4  mov     rsi, [rbp+arg_18]
0x180016ef8  test    rsi, rsi
0x180016efb  jz      loc_180016E40
0x180016f01  mov     [r14], rsi
0x180016f04  xor     esi, esi
0x180016f06  jmp     loc_180016E45
0x180016f0b  mov     dword ptr [rsp+40h+var_18], eax
0x180016f0f  lea     r9, aAslpathisonrem_0; "AslPathIsOnRemovableMedia failed for %w"...
0x180016f16  mov     r8d, 494h
0x180016f1c  mov     [rsp+40h+var_20], rdi
0x180016f21  lea     rdx, aAslpathbuildsi_3; "AslPathBuildSignatureLongpath"
0x180016f28  mov     ecx, 1
0x180016f2d  call    AslLogCallPrintf
0x180016f32  jmp     loc_180016E90
0x180016f37  mov     dword ptr [rsp+40h+var_18], eax
0x180016f3b  lea     r9, aAslpathistempo; "AslPathIsTemporaryInternetFile failed f"...
0x180016f42  mov     r8d, 4A2h
0x180016f48  mov     [rsp+40h+var_20], rdi
0x180016f4d  lea     rdx, aAslpathbuildsi_3; "AslPathBuildSignatureLongpath"
0x180016f54  mov     ecx, 2
0x180016f59  call    AslLogCallPrintf
0x180016f5e  xor     eax, eax
0x180016f60  jmp     loc_180016E3C
0x180016f65  mov     rcx, gs:60h
0x180016f6e  mov     rdx, rsi
0x180016f71  mov     rcx, [rcx+30h]
0x180016f75  call    AslFree
0x180016f7a  jmp     loc_180016E90
0x180016f7f  mov     rcx, gs:60h
0x180016f88  mov     rdx, rdi
0x180016f8b  mov     rcx, [rcx+30h]
0x180016f8f  call    AslFree
0x180016f94  jmp     loc_180016E99
```
