# SdbOpenDatabaseEx

- ea: `0x140042ad4`
- end: `0x140042e22`
- name: `SdbOpenDatabaseEx`
- size: `846`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140029954`
- `0x14002a898`
- `0x14002e934`
- `0x140042724`

## callees

- `0x1400079f0`
- `0x140007e40`
- `0x14002e270`
- `0x14002e3b8`
- `0x140031938`
- `0x1400344cc`
- `0x14003e248`
- `0x14003e364`
- `0x140041f48`
- `0x14004224c`
- `0x140042ad4`
- `0x140045d44`
- `0x140045df8`
- `0x140046074`
- `0x14005498c`
- `0x140055020`

## string_xrefs

- `0x140042af7`: `Flags:%d; DatabasePath:%ws`
- `0x140042b12`: `SdbOpenDatabaseEx`
- `0x140042b6b`: `SdbOpenDatabaseEx`
- `0x140042bfc`: `SdbOpenDatabaseEx`
- `0x140042c3d`: `SdbOpenDatabaseEx`
- `0x140042c6a`: `SdbOpenDatabaseEx`
- `0x140042cb6`: `SdbOpenDatabaseEx`
- `0x140042d99`: `SdbOpenDatabaseEx`
- `0x140042dd9`: `SdbOpenDatabaseEx`
- `0x140042c59`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`
- `0x140042c2c`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x140042ca9`: `Failed to create file mapping [%x]`
- `0x140042dcc`: `Failed to open SDB - File size too large or small.`
- `0x140042d3b`: `Failed to read database header`
- `0x140042d8c`: `SdbpOpenCompressedDatabase failed to open compressed database.`

## pseudocode

```c
_QWORD *__fastcall SdbOpenDatabaseEx(const wchar_t *a1, __int64 a2, unsigned int a3)
{
  const WCHAR *v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  int MergeRedirectPath; // eax
  __int64 v10; // rcx
  int v11; // esi
  int v12; // ebx
  const wchar_t *FileNamePart; // rax
  int v14; // eax
  int v15; // eax
  const char *v16; // r9
  __int64 v17; // r8
  __int64 v18; // rsi
  __int64 v19; // rbx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v24; // rcx
  __int64 v25; // [rsp+20h] [rbp-40h]
  int v26; // [rsp+30h] [rbp-30h] BYREF
  WCHAR *v27; // [rsp+38h] [rbp-28h] BYREF
  _QWORD *v28; // [rsp+40h] [rbp-20h] BYREF
  __int64 v29; // [rsp+48h] [rbp-18h] BYREF
  int v30; // [rsp+50h] [rbp-10h]

  v29 = 0;
  v30 = 0;
  v26 = 0;
  v5 = a1;
  if ( !a1 )
    v5 = &pszSrc;
  AslLogCallPrintf(3, "SdbOpenDatabaseEx", 2501, "Flags:%d; DatabasePath:%ws", a3, v5);
  v7 = (_QWORD *)AslAlloc(v6, 2688, 1);
  v28 = v7;
  v8 = v7;
  if ( v7 )
  {
    memset(v7, 0, 0xA80u);
    v27 = 0;
    if ( (a3 & 0x10) != 0 )
      goto LABEL_47;
    MergeRedirectPath = SdbGetMergeRedirectPath(&v27, &v26, (a3 & 0x20) == 0, a1);
    v11 = MergeRedirectPath;
    if ( MergeRedirectPath < 0 )
    {
      if ( MergeRedirectPath != -1073741772 )
        AslLogCallPrintf(
          3,
          "SdbOpenDatabaseEx",
          2527,
          "SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]",
          MergeRedirectPath);
      v12 = v11;
    }
    else if ( v27 )
    {
      if ( (a3 & 0x20) != 0 )
      {
        if ( !v26 )
          *((_DWORD *)v8 + 6) |= 0x20u;
      }
      else if ( v26 )
      {
        FileNamePart = AslPathGetFileNamePart(a1);
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2539,
          "Handled Error: MergeSdb staged deletion feature was used to prevent sdb mismatch error. SdbName: [%ls].",
          FileNamePart);
      }
      v14 = AslFileMappingCreate(v8, v27, 0);
      v12 = v14;
      if ( v14 < 0 )
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2558,
          "Failed to create file mapping for redirected SDB file [%x]",
          v14);
    }
    else
    {
      v12 = -1073741772;
    }
    if ( v27 )
      AslFree(v10, v27);
    if ( v12 < 0 || !*v8 )
    {
LABEL_47:
      v15 = AslFileMappingCreate(v8, a1, 0);
      if ( v15 < 0 )
      {
        v16 = "Failed to create file mapping [%x]";
        v17 = 2580;
LABEL_25:
        LODWORD(v25) = v15;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", v17, v16, v25);
        goto LABEL_42;
      }
    }
    v18 = *(_QWORD *)(*v8 + 24LL);
    if ( (unsigned __int64)(v18 - 42) > 0xFFFFFD5 )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2589, "Failed to open SDB - File size too large or small.");
      goto LABEL_42;
    }
    v19 = *v8;
    LOBYTE(v20) = SdbpShouldMapSdbToKernelMemory();
    v15 = AslFileMappingEnsureMappedAsEx(v19, v21, v20);
    if ( v15 < 0 )
    {
      v16 = "Failed to map SDB [%x]";
      v17 = 2595;
      goto LABEL_25;
    }
    *((_DWORD *)v8 + 4) = 0;
    *((_DWORD *)v8 + 5) = v18;
    v8[1] = AslFileMappingGetViewBase(*v8);
    if ( !(unsigned int)SdbpReadMappedData(v8, 0, &v29, 12) )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2608, "Failed to read database header");
      goto LABEL_42;
    }
    v15 = v30;
    if ( v30 != 1717724275 )
    {
      if ( v30 == 1717724282 )
      {
        if ( (unsigned int)SdbpOpenCompressedDatabase(&v28, v22, a3) )
          return v28;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2627, "SdbpOpenCompressedDatabase failed to open compressed database.");
        v8 = v28;
LABEL_42:
        if ( v8 )
        {
          AslFileMappingDelete((PVOID *)*v8);
          AslFree(v24, v8);
        }
        return 0;
      }
      if ( (a3 & 2) == 0 )
      {
        v16 = "Magic does not match a valid value: 0x%lx";
        v17 = 2621;
        goto LABEL_25;
      }
    }
    if ( (unsigned int)SdbpValidateAndApplyCompatFlags(v8, &v29, a3) )
      return v8;
    goto LABEL_42;
  }
  AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2509, "Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x140042ad4  mov     [rsp-28h+arg_8], rbx
0x140042ad9  push    rbp
0x140042ada  push    rsi
0x140042adb  push    rdi
0x140042adc  push    r12
0x140042ade  push    r15
0x140042ae0  mov     rbp, rsp
0x140042ae3  sub     rsp, 60h
0x140042ae7  mov     rax, cs:__security_cookie
0x140042aee  xor     rax, rsp
0x140042af1  mov     [rbp+var_8], rax
0x140042af5  xor     eax, eax
0x140042af7  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x140042afe  mov     r12, rcx
0x140042b01  mov     [rbp+var_18], rax
0x140042b05  mov     [rbp+var_10], eax
0x140042b08  lea     rcx, pszSrc
0x140042b0f  mov     [rbp+var_30], eax
0x140042b12  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140042b19  mov     r15d, r8d
0x140042b1c  test    r12, r12
0x140042b1f  mov     rax, r12
0x140042b22  cmovz   rax, rcx
0x140042b26  mov     ecx, 3
0x140042b2b  mov     [rsp+60h+var_38], rax
0x140042b30  mov     dword ptr [rsp+60h+var_40], r8d
0x140042b35  mov     r8d, 9C5h
0x140042b3b  call    AslLogCallPrintf
0x140042b40  mov     ebx, 0A80h
0x140042b45  mov     r8d, 1
0x140042b4b  mov     edx, ebx
0x140042b4d  call    AslAlloc
0x140042b52  mov     [rbp+var_20], rax
0x140042b56  mov     rdi, rax
0x140042b59  test    rax, rax
0x140042b5c  jnz     short loc_140042B7F
0x140042b5e  lea     r9, aFailedToAlloca_19; "Failed to allocate DB structure"
0x140042b65  mov     r8d, 9CDh
0x140042b6b  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140042b72  lea     ecx, [rax+1]
0x140042b75  call    AslLogCallPrintf
0x140042b7a  jmp     loc_140042DFF
0x140042b7f  mov     r8, rbx; Size
0x140042b82  xor     edx, edx; Val
0x140042b84  mov     rcx, rdi; void *
0x140042b87  call    memset
0x140042b8c  mov     [rbp+var_28], 0
0x140042b94  test    r15b, 10h
0x140042b98  jnz     loc_140042C97
0x140042b9e  mov     r8d, 0
0x140042ba4  lea     rdx, [rbp+var_30]
0x140042ba8  mov     ebx, r15d
0x140042bab  lea     rcx, [rbp+var_28]
0x140042baf  and     ebx, 20h
0x140042bb2  mov     r9, r12
0x140042bb5  setz    r8b
0x140042bb9  call    SdbGetMergeRedirectPath
0x140042bbe  mov     esi, eax
0x140042bc0  test    eax, eax
0x140042bc2  js      loc_140042C50
0x140042bc8  cmp     [rbp+var_28], 0
0x140042bcd  jnz     short loc_140042BD9
0x140042bcf  mov     ebx, 0C0000034h
0x140042bd4  jmp     loc_140042C7D
0x140042bd9  test    ebx, ebx
0x140042bdb  jnz     short loc_140042C0D
0x140042bdd  cmp     [rbp+var_30], ebx
0x140042be0  jz      short loc_140042C17
0x140042be2  mov     rcx, r12
0x140042be5  call    AslPathGetFileNamePart
0x140042bea  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x140042bf1  mov     [rsp+60h+var_40], rax
0x140042bf6  mov     r8d, 9EBh
0x140042bfc  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140042c03  lea     ecx, [rbx+1]
0x140042c06  call    AslLogCallPrintf
0x140042c0b  jmp     short loc_140042C17
0x140042c0d  cmp     [rbp+var_30], 0
0x140042c11  jnz     short loc_140042C17
0x140042c13  or      dword ptr [rdi+18h], 20h
0x140042c17  mov     rdx, [rbp+var_28]
0x140042c1b  xor     r8d, r8d
0x140042c1e  mov     rcx, rdi
0x140042c21  call    AslFileMappingCreate
0x140042c26  mov     ebx, eax
0x140042c28  test    eax, eax
0x140042c2a  jns     short loc_140042C7D
0x140042c2c  lea     r9, aFailedToCreate_5; "Failed to create file mapping for redir"...
0x140042c33  mov     dword ptr [rsp+60h+var_40], eax
0x140042c37  mov     r8d, 9FEh
0x140042c3d  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140042c44  mov     ecx, 1
0x140042c49  call    AslLogCallPrintf
0x140042c4e  jmp     short loc_140042C7D
0x140042c50  mov     ebx, 0C0000034h
0x140042c55  cmp     esi, ebx
0x140042c57  jz      short loc_140042C7B
0x140042c59  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x140042c60  mov     dword ptr [rsp+60h+var_40], esi
0x140042c64  mov     r8d, 9DFh
0x140042c6a  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140042c71  mov     ecx, 3
0x140042c76  call    AslLogCallPrintf
0x140042c7b  mov     ebx, esi
0x140042c7d  cmp     [rbp+var_28], 0
0x140042c82  jz      short loc_140042C8D
0x140042c84  mov     rdx, [rbp+var_28]
0x140042c88  call    AslFree
0x140042c8d  test    ebx, ebx
0x140042c8f  js      short loc_140042C97
0x140042c91  cmp     qword ptr [rdi], 0
0x140042c95  jnz     short loc_140042CD0
0x140042c97  xor     r8d, r8d
0x140042c9a  mov     rdx, r12
0x140042c9d  mov     rcx, rdi
0x140042ca0  call    AslFileMappingCreate
0x140042ca5  test    eax, eax
0x140042ca7  jns     short loc_140042CD0
0x140042ca9  lea     r9, aFailedToCreate_3; "Failed to create file mapping [%x]"
0x140042cb0  mov     r8d, 0A14h
0x140042cb6  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140042cbd  mov     dword ptr [rsp+60h+var_40], eax
0x140042cc1  mov     ecx, 1
0x140042cc6  call    AslLogCallPrintf
0x140042ccb  jmp     loc_140042DEA
0x140042cd0  mov     rax, [rdi]
0x140042cd3  mov     rsi, [rax+18h]
0x140042cd7  lea     rax, [rsi-2Ah]
0x140042cdb  cmp     rax, 0FFFFFD5h
0x140042ce1  ja      loc_140042DCC
0x140042ce7  mov     rbx, [rdi]
0x140042cea  call    SdbpShouldMapSdbToKernelMemory
0x140042cef  mov     r8b, al
0x140042cf2  mov     rcx, rbx
0x140042cf5  call    AslFileMappingEnsureMappedAsEx
0x140042cfa  test    eax, eax
0x140042cfc  jns     short loc_140042D0D
0x140042cfe  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x140042d05  mov     r8d, 0A23h
0x140042d0b  jmp     short loc_140042CB6
0x140042d0d  mov     dword ptr [rdi+10h], 0
0x140042d14  mov     [rdi+14h], esi
0x140042d17  mov     rcx, [rdi]
0x140042d1a  call    AslFileMappingGetViewBase
0x140042d1f  mov     r9d, 0Ch
0x140042d25  mov     [rdi+8], rax
0x140042d29  lea     r8, [rbp+var_18]
0x140042d2d  xor     edx, edx
0x140042d2f  mov     rcx, rdi
0x140042d32  call    SdbpReadMappedData
0x140042d37  test    eax, eax
0x140042d39  jnz     short loc_140042D4D
0x140042d3b  lea     r9, aFailedToReadDa_0; "Failed to read database header"
0x140042d42  mov     r8d, 0A30h
0x140042d48  jmp     loc_140042DD9
0x140042d4d  mov     eax, [rbp+var_10]
0x140042d50  mov     ecx, 6662647Ah
0x140042d55  cmp     eax, 66626473h
0x140042d5a  jz      short loc_140042D78
0x140042d5c  cmp     eax, ecx
0x140042d5e  jz      short loc_140042D7C
0x140042d60  test    r15b, 2
0x140042d64  jnz     short loc_140042D78
0x140042d66  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x140042d6d  mov     r8d, 0A3Dh
0x140042d73  jmp     loc_140042CB6
0x140042d78  cmp     eax, ecx
0x140042d7a  jnz     short loc_140042DB4
0x140042d7c  mov     r8d, r15d
0x140042d7f  lea     rcx, [rbp+var_20]
0x140042d83  call    SdbpOpenCompressedDatabase
0x140042d88  test    eax, eax
0x140042d8a  jnz     short loc_140042DAE
0x140042d8c  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x140042d93  mov     r8d, 0A43h
0x140042d99  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140042da0  lea     ecx, [rax+1]
0x140042da3  call    AslLogCallPrintf
0x140042da8  mov     rdi, [rbp+var_20]
0x140042dac  jmp     short loc_140042DEA
0x140042dae  mov     rdi, [rbp+var_20]
0x140042db2  jmp     short loc_140042DC7
0x140042db4  mov     r8d, r15d
0x140042db7  lea     rdx, [rbp+var_18]
0x140042dbb  mov     rcx, rdi
0x140042dbe  call    SdbpValidateAndApplyCompatFlags
0x140042dc3  test    eax, eax
0x140042dc5  jz      short loc_140042DEA
0x140042dc7  mov     rax, rdi
0x140042dca  jmp     short loc_140042E01
0x140042dcc  lea     r9, aFailedToOpenSd; "Failed to open SDB - File size too larg"...
0x140042dd3  mov     r8d, 0A1Dh
0x140042dd9  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140042de0  mov     ecx, 1
0x140042de5  call    AslLogCallPrintf
0x140042dea  test    rdi, rdi
0x140042ded  jz      short loc_140042DFF
0x140042def  mov     rcx, [rdi]; P
0x140042df2  call    AslFileMappingDelete
0x140042df7  mov     rdx, rdi
0x140042dfa  call    AslFree
0x140042dff  xor     eax, eax
0x140042e01  mov     rcx, [rbp+var_8]
0x140042e05  xor     rcx, rsp; StackCookie
0x140042e08  call    __security_check_cookie
0x140042e0d  mov     rbx, [rsp+60h+arg_8]
0x140042e15  add     rsp, 60h
0x140042e19  pop     r15
0x140042e1b  pop     r12
0x140042e1d  pop     rdi
0x140042e1e  pop     rsi
0x140042e1f  pop     rbp
0x140042e20  retn
```
