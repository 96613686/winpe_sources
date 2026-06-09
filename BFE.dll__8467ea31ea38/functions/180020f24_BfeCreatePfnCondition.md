# BfeCreatePfnCondition

- ea: `0x180020f24`
- end: `0x180021200`
- name: `BfeCreatePfnCondition`
- size: `732`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013480`

## callees

- `0x18000e000`
- `0x180018b74`
- `0x180020f24`
- `0x180021208`
- `0x180022730`
- `0x1800238b4`
- `0x180058b30`
- `0x1800595ac`
- `0x180087dcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021199`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002115d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002115d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800210c1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800210c1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800210ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800210ae`

## string_xrefs

- `0x1800211b8`: `BfeCreatePfnCondition`
- `0x180088d50`: `BfeCreatePfnCondition`

## pseudocode

```c
__int64 __fastcall BfeCreatePfnCondition(STRSAFE_LPCWSTR pszSrc, __int64 a2)
{
  void *v4; // r12
  __int64 v5; // rbx
  SIZE_T v6; // rbx
  __int64 v7; // rdi
  HRESULT v8; // eax
  __int64 v9; // rcx
  DWORD **v10; // r14
  DWORD SecurityDescriptorLength; // r13d
  void *v12; // rbx
  DWORD *v13; // rax
  DWORD *v14; // rax
  signed int LastError; // eax
  STRSAFE_LPWSTR pszDest; // [rsp+20h] [rbp-E0h] BYREF
  void *v18; // [rsp+28h] [rbp-D8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszSrca[56]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v21[8]; // [rsp+B0h] [rbp-50h] BYREF

  wcscpy(pszSrca, L"O:SYG:SYD:(XA;;CC;;;WD;(WIN://SYSAPPID Contains \"");
  v4 = 0;
  v5 = -1;
  wcscpy((wchar_t *)v21, L"\"))(A;;CC;;;S-1-15-3-1)(A;;CC;;;S-1-15-3-2)(A;;CC;;;S-1-15-3-3)");
  pszDest = 0;
  SecurityDescriptor = 0;
  v18 = 0;
  do
    ++v5;
  while ( pszSrc[v5] );
  v6 = 2 * v5 + 226;
  v7 = WfpMemAlloc(v6, 0);
  if ( !v7 )
  {
    memset_0(pszDest, 0, v6);
    v8 = StringCbCatW(pszDest, v6, pszSrca);
    if ( v8 < 0
      || (v8 = StringCbCatW(pszDest, v6, pszSrc), v8 < 0)
      || (v8 = StringCbCatW(pszDest, v6, (STRSAFE_LPCWSTR)v21), v8 < 0) )
    {
      v7 = WfpReportSysErrorAsHResult(v9, "BfeCreatePfnCondition", (unsigned int)v8, 1);
    }
    else if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(pszDest, 1u, &SecurityDescriptor, 0) )
    {
      v10 = (DWORD **)(a2 + 32);
      SecurityDescriptorLength = GetSecurityDescriptorLength(SecurityDescriptor);
      *(_QWORD *)(a2 + 32) = 0;
      v7 = WfpMemAlloc(0x10u, 0);
      if ( !v7 )
      {
        v7 = WfpMemAlloc(SecurityDescriptorLength, 0);
        if ( v7 )
        {
          v4 = v18;
        }
        else
        {
          v12 = v18;
          memcpy_0(v18, SecurityDescriptor, SecurityDescriptorLength);
          v13 = *v10;
          *(_DWORD *)(a2 + 16) = 0;
          *(_OWORD *)a2 = FWPM_CONDITION_ALE_PACKAGE_FAMILY_NAME;
          *(_DWORD *)(a2 + 24) = 14;
          *v13 = SecurityDescriptorLength;
          v14 = *v10;
          v18 = 0;
          *((_QWORD *)v14 + 1) = v12;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError;
    }
  }
  if ( pszDest )
    WfpMemFree(&pszDest);
  LocalFree(SecurityDescriptor);
  if ( v4 )
    WfpMemFree(&v18);
  if ( v7 )
  {
    if ( *(_QWORD *)(a2 + 32) )
      WfpMemFree(a2 + 32);
    WfpReportError(v7, "BfeCreatePfnCondition");
  }
  return v7;
}

```

## disassembly

```asm
0x180020f24  mov     [rsp-8+arg_10], rbx
0x180020f29  mov     [rsp-8+arg_18], rdi
0x180020f2e  push    rbp
0x180020f2f  push    r12
0x180020f31  push    r13
0x180020f33  push    r14
0x180020f35  push    r15
0x180020f37  lea     rbp, [rsp-40h]
0x180020f3c  sub     rsp, 140h
0x180020f43  mov     rax, cs:__security_cookie
0x180020f4a  xor     rax, rsp
0x180020f4d  mov     [rbp+60h+var_30], rax
0x180020f51  movaps  xmm0, xmmword ptr cs:aOSygSydXaCcWdW; "O:SYG:SYD:(XA;;CC;;;WD;(WIN://SYSAPPID "...
0x180020f58  xor     r13d, r13d
0x180020f5b  movaps  xmm1, xmmword ptr cs:aOSygSydXaCcWdW+10h; "D:(XA;;CC;;;WD;(WIN://SYSAPPID Contains"...
0x180020f62  mov     r15, rdx
0x180020f65  mov     eax, dword ptr cs:aOSygSydXaCcWdW+60h; "\""
0x180020f6b  mov     r14, rcx
0x180020f6e  movaps  xmmword ptr [rsp+160h+pszSrc], xmm0
0x180020f73  mov     r12d, r13d
0x180020f76  movaps  xmm0, xmmword ptr cs:aOSygSydXaCcWdW+20h; "C;;;WD;(WIN://SYSAPPID Contains \""
0x180020f7d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180020f81  movaps  [rsp+160h+var_110], xmm1
0x180020f86  movaps  xmm1, xmmword ptr cs:aOSygSydXaCcWdW+30h; "WIN://SYSAPPID Contains \""
0x180020f8d  movaps  [rsp+160h+var_100], xmm0
0x180020f92  movaps  xmm0, xmmword ptr cs:aOSygSydXaCcWdW+40h; "SAPPID Contains \""
0x180020f99  movaps  [rsp+160h+var_F0], xmm1
0x180020f9e  movaps  xmm1, xmmword ptr cs:aOSygSydXaCcWdW+50h; "ontains \""
0x180020fa5  movaps  [rbp+60h+var_E0], xmm0
0x180020fa9  movaps  xmm0, xmmword ptr cs:aACcS11531ACcS1; "\"))(A;;CC;;;S-1-15-3-1)(A;;CC;;;S-1-15"...
0x180020fb0  movaps  [rbp+60h+var_D0], xmm1
0x180020fb4  movaps  xmm1, xmmword ptr cs:aACcS11531ACcS1+10h; "C;;;S-1-15-3-1)(A;;CC;;;S-1-15-3-2)(A;;"...
0x180020fbb  movaps  xmmword ptr [rbp+60h+var_B0], xmm0
0x180020fbf  movaps  xmm0, xmmword ptr cs:aACcS11531ACcS1+20h; "15-3-1)(A;;CC;;;S-1-15-3-2)(A;;CC;;;S-1"...
0x180020fc6  movaps  xmmword ptr [rbp+60h+var_B0+10h], xmm1
0x180020fca  movaps  xmm1, xmmword ptr cs:aACcS11531ACcS1+30h; "A;;CC;;;S-1-15-3-2)(A;;CC;;;S-1-15-3-3)"
0x180020fd1  movaps  xmmword ptr [rbp+60h+var_B0+20h], xmm0
0x180020fd5  movaps  xmm0, xmmword ptr cs:aACcS11531ACcS1+40h; "S-1-15-3-2)(A;;CC;;;S-1-15-3-3)"
0x180020fdc  movaps  xmmword ptr [rbp+60h+var_B0+30h], xmm1
0x180020fe0  movaps  xmm1, xmmword ptr cs:aACcS11531ACcS1+50h; "-2)(A;;CC;;;S-1-15-3-3)"
0x180020fe7  movaps  [rbp+60h+var_70], xmm0
0x180020feb  movaps  xmm0, xmmword ptr cs:aACcS11531ACcS1+60h; "C;;;S-1-15-3-3)"
0x180020ff2  movaps  [rbp+60h+var_60], xmm1
0x180020ff6  movaps  xmm1, xmmword ptr cs:aACcS11531ACcS1+70h; "15-3-3)"
0x180020ffd  movaps  [rbp+60h+var_50], xmm0
0x180021001  movaps  [rbp+60h+var_40], xmm1
0x180021005  mov     [rsp+160h+pszDest], r13
0x18002100a  mov     [rbp+60h+var_C0], eax
0x18002100d  mov     [rsp+160h+SecurityDescriptor], r13
0x180021012  mov     [rsp+160h+var_138], r13
0x180021017  inc     rbx
0x18002101a  cmp     [rcx+rbx*2], r13w
0x18002101f  jnz     short loc_180021017
0x180021021  lea     rbx, ds:0E2h[rbx*2]
0x180021029  xor     edx, edx; dwFlags
0x18002102b  mov     rcx, rbx; dwBytes
0x18002102e  lea     r8, [rsp+160h+pszDest]
0x180021033  call    WfpMemAlloc
0x180021038  mov     rdi, rax
0x18002103b  test    rax, rax
0x18002103e  jnz     loc_180021147
0x180021044  mov     rcx, [rsp+160h+pszDest]; void *
0x180021049  mov     r8, rbx; Size
0x18002104c  xor     edx, edx; Val
0x18002104e  call    memset_0
0x180021053  mov     rcx, [rsp+160h+pszDest]; pszDest
0x180021058  lea     r8, [rsp+160h+pszSrc]; pszSrc
0x18002105d  mov     rdx, rbx; cbDest
0x180021060  call    StringCbCatW
0x180021065  test    eax, eax
0x180021067  js      loc_1800211B2
0x18002106d  mov     rcx, [rsp+160h+pszDest]; pszDest
0x180021072  mov     r8, r14; pszSrc
0x180021075  mov     rdx, rbx; cbDest
0x180021078  call    StringCbCatW
0x18002107d  test    eax, eax
0x18002107f  js      loc_1800211B2
0x180021085  mov     rcx, [rsp+160h+pszDest]; pszDest
0x18002108a  lea     r8, [rbp+60h+var_B0]; pszSrc
0x18002108e  mov     rdx, rbx; cbDest
0x180021091  call    StringCbCatW
0x180021096  test    eax, eax
0x180021098  js      loc_1800211B2
0x18002109e  mov     rcx, [rsp+160h+pszDest]; StringSecurityDescriptor
0x1800210a3  lea     r8, [rsp+160h+SecurityDescriptor]; SecurityDescriptor
0x1800210a8  xor     r9d, r9d; SecurityDescriptorSize
0x1800210ab  lea     edx, [rdi+1]; StringSDRevision
0x1800210ae  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800210b4  test    eax, eax
0x1800210b6  jz      loc_180021199
0x1800210bc  mov     rcx, [rsp+160h+SecurityDescriptor]; pSecurityDescriptor
0x1800210c1  call    cs:__imp_GetSecurityDescriptorLength
0x1800210c7  lea     r14, [r15+20h]
0x1800210cb  xor     edx, edx; dwFlags
0x1800210cd  lea     ecx, [rdi+10h]; dwBytes
0x1800210d0  mov     r13d, eax
0x1800210d3  mov     r8, r14
0x1800210d6  mov     [r14], r12
0x1800210d9  call    WfpMemAlloc
0x1800210de  mov     rdi, rax
0x1800210e1  test    rax, rax
0x1800210e4  jnz     loc_1800211D4
0x1800210ea  lea     r8, [rsp+160h+var_138]
0x1800210ef  xor     edx, edx; dwFlags
0x1800210f1  mov     ecx, r13d; dwBytes
0x1800210f4  call    WfpMemAlloc
0x1800210f9  mov     rdi, rax
0x1800210fc  test    rax, rax
0x1800210ff  jnz     loc_1800211CF
0x180021105  mov     rbx, [rsp+160h+var_138]
0x18002110a  mov     r8d, r13d; Size
0x18002110d  mov     rdx, [rsp+160h+SecurityDescriptor]; Src
0x180021112  mov     rcx, rbx; void *
0x180021115  call    memcpy_0
0x18002111a  movups  xmm0, cs:FWPM_CONDITION_ALE_PACKAGE_FAMILY_NAME
0x180021121  mov     rax, [r14]
0x180021124  mov     [r15+10h], r12d
0x180021128  movdqu  xmmword ptr [r15], xmm0
0x18002112d  mov     dword ptr [r15+18h], 0Eh
0x180021135  mov     [rax], r13d
0x180021138  xor     r13d, r13d
0x18002113b  mov     rax, [r14]
0x18002113e  mov     [rsp+160h+var_138], r13
0x180021143  mov     [rax+8], rbx
0x180021147  cmp     [rsp+160h+pszDest], r13
0x18002114c  jz      short loc_180021158
0x18002114e  lea     rcx, [rsp+160h+pszDest]
0x180021153  call    WfpMemFree
0x180021158  mov     rcx, [rsp+160h+SecurityDescriptor]; hMem
0x18002115d  call    cs:__imp_LocalFree
0x180021163  test    r12, r12
0x180021166  jnz     short loc_1800211DC
0x180021168  test    rdi, rdi
0x18002116b  jnz     short loc_1800211E8
0x18002116d  mov     rax, rdi
0x180021170  mov     rcx, [rbp+60h+var_30]
0x180021174  xor     rcx, rsp; StackCookie
0x180021177  call    __security_check_cookie
0x18002117c  lea     r11, [rsp+160h+var_20]
0x180021184  mov     rbx, [r11+40h]
0x180021188  mov     rdi, [r11+48h]
0x18002118c  mov     rsp, r11
0x18002118f  pop     r15
0x180021191  pop     r14
0x180021193  pop     r13
0x180021195  pop     r12
0x180021197  pop     rbp
0x180021198  retn
0x180021199  call    cs:__imp_GetLastError
0x18002119f  test    eax, eax
0x1800211a1  jg      short loc_1800211A8
0x1800211a3  movsxd  rdi, eax
0x1800211a6  jmp     short loc_180021147
0x1800211a8  movzx   eax, ax
0x1800211ab  or      eax, 80070000h
0x1800211b0  jmp     short loc_1800211A3
0x1800211b2  mov     r9d, 1
0x1800211b8  lea     rdx, aBfecreatepfnco; "BfeCreatePfnCondition"
0x1800211bf  mov     r8d, eax
0x1800211c2  call    WfpReportSysErrorAsHResult
0x1800211c7  mov     rdi, rax
0x1800211ca  jmp     loc_180021147
0x1800211cf  mov     r12, [rsp+160h+var_138]
0x1800211d4  xor     r13d, r13d
0x1800211d7  jmp     loc_180021147
0x1800211dc  lea     rcx, [rsp+160h+var_138]
0x1800211e1  call    WfpMemFree
0x1800211e6  jmp     short loc_180021168
0x1800211e8  lea     rcx, [r15+20h]
0x1800211ec  cmp     [rcx], r13
0x1800211ef  jz      loc_180088D50
0x1800211f5  call    WfpMemFree
0x1800211fa  nop
0x1800211fb  jmp     loc_180088D50
0x180088d50  lea     rdx, aBfecreatepfnco; "BfeCreatePfnCondition"
0x180088d57  mov     rcx, rdi
0x180088d5a  call    WfpReportError
0x180088d5f  nop
0x180088d60  jmp     loc_18002116D
```
