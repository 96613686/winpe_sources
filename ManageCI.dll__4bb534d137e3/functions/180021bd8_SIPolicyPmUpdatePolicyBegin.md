# SIPolicyPmUpdatePolicyBegin

- ea: `0x180021bd8`
- end: `0x180021e2d`
- name: `SIPolicyPmUpdatePolicyBegin`
- size: `597`
- prototype: `__int64 __fastcall(__int64, void *, ULONG, _QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180012280`
- `0x1800123e0`

## callees

- `0x180020b44`
- `0x1800218d0`
- `0x180021bd8`
- `0x1800220e0`
- `0x18002234c`
- `0x180022a30`
- `0x180022bb8`
- `0x180025f64`
- `0x180027038`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e0a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021d9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021d9a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180021c98`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180021c98`
- `ntdll!RtlFreeUnicodeString` at `0x180021ddf`
- `ntdll!RtlFreeUnicodeString` at `0x180021de9`
- `ntdll!RtlFreeUnicodeString` at `0x180021ddf`
- `ntdll!RtlFreeUnicodeString` at `0x180021de9`

## pseudocode

```c
__int64 __fastcall SIPolicyPmUpdatePolicyBegin(__int64 a1, void *a2, ULONG a3, _QWORD *a4)
{
  char v4; // r14
  void *v6; // r15
  void *v7; // rsi
  __int64 v8; // rdi
  int TestsigningPolicy; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  struct _UNICODE_STRING *v14; // rbx
  char IsStateSeparationEnabled; // al
  struct _UNICODE_STRING *v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  _OWORD *v23; // rax
  _OWORD *v24; // rcx
  __int128 v25; // xmm0
  _QWORD *v26; // rax
  char v28[4]; // [rsp+38h] [rbp-39h] BYREF
  ULONG v29; // [rsp+3Ch] [rbp-35h] BYREF
  __int64 v30; // [rsp+40h] [rbp-31h] BYREF
  void *v31; // [rsp+48h] [rbp-29h] BYREF
  __int64 v32; // [rsp+50h] [rbp-21h] BYREF
  struct _UNICODE_STRING v33; // [rsp+58h] [rbp-19h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+68h] [rbp-9h] BYREF
  struct _UNICODE_STRING v35; // [rsp+78h] [rbp+7h] BYREF
  _BOOL8 v36; // [rsp+88h] [rbp+17h]
  char v37; // [rsp+D8h] [rbp+67h] BYREF
  _QWORD *v38; // [rsp+F0h] [rbp+7Fh]

  v38 = a4;
  v4 = 0;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  v6 = 0;
  v32 = 0;
  v7 = 0;
  v28[0] = 0;
  v33 = 0;
  v8 = 0;
  v37 = 0;
  UnicodeString = 0;
  TestsigningPolicy = SIPolicyGetTestsigningPolicy(v28, &v37);
  if ( TestsigningPolicy >= 0 )
  {
    SIPolicyPmCreateDefaultFolders();
    LOBYTE(v11) = v37;
    LOBYTE(v12) = v28[0];
    v13 = SIPolicyParsePolicyFormat(v12, v11, a2, a3, &v32);
    v8 = v32;
    TestsigningPolicy = v13;
    if ( v13 >= 0 )
    {
      if ( !v32 )
      {
        TestsigningPolicy = -1058471933;
        goto LABEL_24;
      }
      if ( *(_DWORD *)(v32 + 768) )
      {
        v4 = 1;
        v14 = &v33;
      }
      else
      {
        v14 = 0;
      }
      IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
      v16 = &v33;
      if ( v4 )
        v16 = 0;
      TestsigningPolicy = SIPolicyPmBuildPathFromPolicyID(
                            (_QWORD *)(v8 + (-(__int64)(*(_DWORD *)(v8 + 40) < 6u) & 0xFFFFFFFFFFFFFD50uLL) + 704),
                            0,
                            IsStateSeparationEnabled,
                            v16,
                            v14,
                            &UnicodeString);
      if ( TestsigningPolicy >= 0 )
      {
        v35 = v33;
        v36 = v4 == 0;
        if ( SIPolicyPmDoesPolicyExist(v17, &v35) )
        {
          v19 = SIPolicyPmReadPolicy(v18, &v33, &v31, &v29);
          v6 = v31;
          TestsigningPolicy = v19;
          if ( v19 < 0 )
            goto LABEL_24;
          LOBYTE(v20) = v37;
          LOBYTE(v21) = v28[0];
          v22 = SIPolicyParsePolicyFormat(v21, v20, v31, v29, &v30);
          v7 = (void *)v30;
          TestsigningPolicy = v22;
          if ( v22 < 0 )
            goto LABEL_24;
          if ( v30
            && (*(_QWORD *)(v8 + 32) < *(_QWORD *)(v30 + 32)
             || *(_DWORD *)(v8 + 768) && !v4 && (*(_DWORD *)(v30 + 44) & 0x80000) == 0) )
          {
            TestsigningPolicy = -1058471934;
            goto LABEL_24;
          }
        }
        TestsigningPolicy = SIPolicyPmWritePolicy(v18, &UnicodeString, a2, a3);
        if ( TestsigningPolicy >= 0 )
        {
          v23 = LocalAlloc(0x40u, 0x28u);
          v24 = v23;
          if ( v23 )
          {
            v25 = *(_OWORD *)((-(__int64)(*(_DWORD *)(v8 + 40) < 6u) & 0xFFFFFFFFFFFFFD50uLL) + v8 + 704);
            *((_BYTE *)v23 + 33) = v4;
            *((_BYTE *)v23 + 32) = v4 ^ 1;
            v26 = v38;
            *v24 = v25;
            *v26 = v24;
          }
          else
          {
            TestsigningPolicy = -1073741801;
          }
        }
      }
    }
  }
LABEL_24:
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v33);
  SIPolicyUninitialize((HLOCAL)v8);
  SIPolicyUninitialize(v7);
  LocalFree(0);
  LocalFree(v6);
  return (unsigned int)TestsigningPolicy;
}

```

## disassembly

```asm
0x180021bd8  mov     rax, rsp
0x180021bdb  mov     [rax+10h], rbx
0x180021bdf  mov     [rax+20h], r9
0x180021be3  mov     [rax+8], cl
0x180021be6  push    rbp
0x180021be7  push    rsi
0x180021be8  push    rdi
0x180021be9  push    r12
0x180021beb  push    r13
0x180021bed  push    r14
0x180021bef  push    r15
0x180021bf1  lea     rbp, [rax-5Fh]
0x180021bf5  sub     rsp, 90h
0x180021bfc  xor     r14d, r14d
0x180021bff  lea     rcx, [rbp+57h+var_90]
0x180021c03  xorps   xmm0, xmm0
0x180021c06  mov     [rbp+57h+var_80], r14
0x180021c0a  mov     r13, rdx
0x180021c0d  mov     [rbp+57h+var_8C], r14d
0x180021c11  lea     rdx, [rbp+57h+arg_0]
0x180021c15  mov     [rbp+57h+var_88], r14
0x180021c19  mov     r15d, r14d
0x180021c1c  mov     [rbp+57h+var_78], r14
0x180021c20  mov     esi, r14d
0x180021c23  mov     [rbp+57h+var_90], r14b
0x180021c27  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x180021c2b  mov     edi, r14d
0x180021c2e  mov     [rbp+57h+arg_0], r14b
0x180021c32  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x180021c36  mov     r12d, r8d
0x180021c39  call    SIPolicyGetTestsigningPolicy
0x180021c3e  mov     ebx, eax
0x180021c40  test    eax, eax
0x180021c42  js      loc_180021DDB
0x180021c48  call    SIPolicyPmCreateDefaultFolders
0x180021c4d  mov     dl, [rbp+57h+arg_0]
0x180021c50  lea     rax, [rbp+57h+var_78]
0x180021c54  mov     cl, [rbp+57h+var_90]
0x180021c57  mov     r9d, r12d
0x180021c5a  mov     r8, r13
0x180021c5d  mov     [rsp+0C0h+var_A0], rax
0x180021c62  call    SIPolicyParsePolicyFormat
0x180021c67  mov     rdi, [rbp+57h+var_78]
0x180021c6b  mov     ebx, eax
0x180021c6d  test    eax, eax
0x180021c6f  js      loc_180021DDB
0x180021c75  test    rdi, rdi
0x180021c78  jnz     short loc_180021C84
0x180021c7a  mov     ebx, 0C0E90003h
0x180021c7f  jmp     loc_180021DDB
0x180021c84  cmp     [rdi+300h], r14d
0x180021c8b  jz      short loc_180021C96
0x180021c8d  mov     r14b, 1
0x180021c90  lea     rbx, [rbp+57h+var_70]
0x180021c94  jmp     short loc_180021C98
0x180021c96  xor     ebx, ebx
0x180021c98  call    cs:__imp_RtlIsStateSeparationEnabled
0x180021c9e  xor     ecx, ecx
0x180021ca0  lea     rdx, [rbp+57h+UnicodeString]
0x180021ca4  mov     [rsp+28h], rdx
0x180021ca9  lea     r9, [rbp+57h+var_70]
0x180021cad  test    r14b, r14b
0x180021cb0  mov     [rsp+0C0h+var_A0], rbx
0x180021cb5  mov     r8b, al
0x180021cb8  cmovnz  r9, rcx
0x180021cbc  cmp     dword ptr [rdi+28h], 6
0x180021cc0  sbb     rcx, rcx
0x180021cc3  xor     edx, edx
0x180021cc5  and     rcx, 0FFFFFFFFFFFFFD50h
0x180021ccc  add     rcx, 2C0h
0x180021cd3  add     rcx, rdi
0x180021cd6  call    SIPolicyPmBuildPathFromPolicyID
0x180021cdb  mov     ebx, eax
0x180021cdd  test    eax, eax
0x180021cdf  js      loc_180021DDB
0x180021ce5  movups  xmm0, xmmword ptr [rbp+57h+var_70.Length]
0x180021ce9  xor     eax, eax
0x180021ceb  lea     rdx, [rbp+57h+var_50]
0x180021cef  mov     [rbp+57h+var_40], rax
0x180021cf3  test    r14b, r14b
0x180021cf6  movdqu  [rbp+57h+var_50], xmm0
0x180021cfb  setz    byte ptr [rbp+57h+var_40]
0x180021cff  call    SIPolicyPmDoesPolicyExist
0x180021d04  test    al, al
0x180021d06  jz      short loc_180021D7D
0x180021d08  lea     r9, [rbp+57h+var_8C]
0x180021d0c  lea     r8, [rbp+57h+var_80]
0x180021d10  lea     rdx, [rbp+57h+var_70]
0x180021d14  call    SIPolicyPmReadPolicy
0x180021d19  mov     r15, [rbp+57h+var_80]
0x180021d1d  mov     ebx, eax
0x180021d1f  test    eax, eax
0x180021d21  js      loc_180021DDB
0x180021d27  mov     r9d, [rbp+57h+var_8C]
0x180021d2b  lea     rax, [rbp+57h+var_88]
0x180021d2f  mov     dl, [rbp+57h+arg_0]
0x180021d32  mov     r8, r15
0x180021d35  mov     cl, [rbp+57h+var_90]
0x180021d38  mov     [rsp+0C0h+var_A0], rax
0x180021d3d  call    SIPolicyParsePolicyFormat
0x180021d42  mov     rsi, [rbp+57h+var_88]
0x180021d46  mov     ebx, eax
0x180021d48  test    eax, eax
0x180021d4a  js      loc_180021DDB
0x180021d50  test    rsi, rsi
0x180021d53  jz      short loc_180021D7D
0x180021d55  mov     rax, [rsi+20h]
0x180021d59  cmp     [rdi+20h], rax
0x180021d5d  jb      short loc_180021D76
0x180021d5f  cmp     dword ptr [rdi+300h], 0
0x180021d66  jz      short loc_180021D7D
0x180021d68  test    r14b, r14b
0x180021d6b  jnz     short loc_180021D7D
0x180021d6d  test    dword ptr [rsi+2Ch], 80000h
0x180021d74  jnz     short loc_180021D7D
0x180021d76  mov     ebx, 0C0E90002h
0x180021d7b  jmp     short loc_180021DDB
0x180021d7d  mov     r9d, r12d
0x180021d80  lea     rdx, [rbp+57h+UnicodeString]
0x180021d84  mov     r8, r13
0x180021d87  call    SIPolicyPmWritePolicy
0x180021d8c  mov     ebx, eax
0x180021d8e  test    eax, eax
0x180021d90  js      short loc_180021DDB
0x180021d92  mov     edx, 28h ; '('; uBytes
0x180021d97  lea     ecx, [rdx+18h]; uFlags
0x180021d9a  call    cs:__imp_LocalAlloc
0x180021da0  mov     rcx, rax
0x180021da3  test    rax, rax
0x180021da6  jnz     short loc_180021DAF
0x180021da8  mov     ebx, 0C0000017h
0x180021dad  jmp     short loc_180021DDB
0x180021daf  cmp     dword ptr [rdi+28h], 6
0x180021db3  sbb     rax, rax
0x180021db6  and     rax, 0FFFFFFFFFFFFFD50h
0x180021dbc  movups  xmm0, xmmword ptr [rax+rdi+2C0h]
0x180021dc4  mov     al, r14b
0x180021dc7  mov     [rcx+21h], r14b
0x180021dcb  xor     al, 1
0x180021dcd  mov     [rcx+20h], al
0x180021dd0  mov     rax, [rbp+57h+arg_18]
0x180021dd4  movdqu  xmmword ptr [rcx], xmm0
0x180021dd8  mov     [rax], rcx
0x180021ddb  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180021ddf  call    cs:__imp_RtlFreeUnicodeString
0x180021de5  lea     rcx, [rbp+57h+var_70]; UnicodeString
0x180021de9  call    cs:__imp_RtlFreeUnicodeString
0x180021def  mov     rcx, rdi; hMem
0x180021df2  call    SIPolicyUninitialize
0x180021df7  mov     rcx, rsi; hMem
0x180021dfa  call    SIPolicyUninitialize
0x180021dff  xor     ecx, ecx; hMem
0x180021e01  call    cs:__imp_LocalFree
0x180021e07  mov     rcx, r15; hMem
0x180021e0a  call    cs:__imp_LocalFree
0x180021e10  mov     eax, ebx
0x180021e12  mov     rbx, [rsp+0C0h+arg_8]
0x180021e1a  add     rsp, 90h
0x180021e21  pop     r15
0x180021e23  pop     r14
0x180021e25  pop     r13
0x180021e27  pop     r12
0x180021e29  pop     rdi
0x180021e2a  pop     rsi
0x180021e2b  pop     rbp
0x180021e2c  retn
```
