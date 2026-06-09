# BfeCreatePfnCondition

- ea: `0x1800235a0`
- end: `0x18002389c`
- name: `BfeCreatePfnCondition`
- size: `764`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013f60`

## callees

- `0x18000e7e0`
- `0x1800197d0`
- `0x1800235a0`
- `0x1800238a4`
- `0x180024e40`
- `0x180025fe4`
- `0x18005aa60`
- `0x18005b4fc`
- `0x18008ad6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002382c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002382c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800237e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800237e5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180023743`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180023743`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002372a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002372a`

## string_xrefs

- `0x180023851`: `BfeCreatePfnCondition`
- `0x18008bd0c`: `BfeCreatePfnCondition`

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
0x1800235a0  mov     [rsp-8+arg_10], rbx
0x1800235a5  mov     [rsp-8+arg_18], rdi
0x1800235aa  push    rbp
0x1800235ab  push    r12
0x1800235ad  push    r13
0x1800235af  push    r14
0x1800235b1  push    r15
0x1800235b3  lea     rbp, [rsp-40h]
0x1800235b8  sub     rsp, 140h
0x1800235bf  mov     rax, cs:__security_cookie
0x1800235c6  xor     rax, rsp
0x1800235c9  mov     [rbp+60h+var_30], rax
0x1800235cd  movaps  xmm0, xmmword ptr cs:aOSygSydXaCcWdW; "O:SYG:SYD:(XA;;CC;;;WD;(WIN://SYSAPPID "...
0x1800235d4  xor     r13d, r13d
0x1800235d7  movaps  xmm1, xmmword ptr cs:aOSygSydXaCcWdW+10h; "D:(XA;;CC;;;WD;(WIN://SYSAPPID Contains"...
0x1800235de  mov     r15, rdx
0x1800235e1  mov     eax, dword ptr cs:aOSygSydXaCcWdW+60h; "\""
0x1800235e7  mov     r14, rcx
0x1800235ea  movaps  xmmword ptr [rsp+160h+pszSrc], xmm0
0x1800235ef  mov     r12d, r13d
0x1800235f2  movaps  xmm0, xmmword ptr cs:aOSygSydXaCcWdW+20h; "C;;;WD;(WIN://SYSAPPID Contains \""
0x1800235f9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800235fd  movaps  [rsp+160h+var_110], xmm1
0x180023602  movaps  xmm1, xmmword ptr cs:aOSygSydXaCcWdW+30h; "WIN://SYSAPPID Contains \""
0x180023609  movaps  [rsp+160h+var_100], xmm0
0x18002360e  movaps  xmm0, xmmword ptr cs:aOSygSydXaCcWdW+40h; "SAPPID Contains \""
0x180023615  movaps  [rsp+160h+var_F0], xmm1
0x18002361a  movaps  xmm1, xmmword ptr cs:aOSygSydXaCcWdW+50h; "ontains \""
0x180023621  movaps  [rbp+60h+var_E0], xmm0
0x180023625  movaps  xmm0, xmmword ptr cs:aACcS11531ACcS1; "\"))(A;;CC;;;S-1-15-3-1)(A;;CC;;;S-1-15"...
0x18002362c  movaps  [rbp+60h+var_D0], xmm1
0x180023630  movaps  xmm1, xmmword ptr cs:aACcS11531ACcS1+10h; "C;;;S-1-15-3-1)(A;;CC;;;S-1-15-3-2)(A;;"...
0x180023637  movaps  xmmword ptr [rbp+60h+var_B0], xmm0
0x18002363b  movaps  xmm0, xmmword ptr cs:aACcS11531ACcS1+20h; "15-3-1)(A;;CC;;;S-1-15-3-2)(A;;CC;;;S-1"...
0x180023642  movaps  xmmword ptr [rbp+60h+var_B0+10h], xmm1
0x180023646  movaps  xmm1, xmmword ptr cs:aACcS11531ACcS1+30h; "A;;CC;;;S-1-15-3-2)(A;;CC;;;S-1-15-3-3)"
0x18002364d  movaps  xmmword ptr [rbp+60h+var_B0+20h], xmm0
0x180023651  movaps  xmm0, xmmword ptr cs:aACcS11531ACcS1+40h; "S-1-15-3-2)(A;;CC;;;S-1-15-3-3)"
0x180023658  movaps  xmmword ptr [rbp+60h+var_B0+30h], xmm1
0x18002365c  movaps  xmm1, xmmword ptr cs:aACcS11531ACcS1+50h; "-2)(A;;CC;;;S-1-15-3-3)"
0x180023663  movaps  [rbp+60h+var_70], xmm0
0x180023667  movaps  xmm0, xmmword ptr cs:aACcS11531ACcS1+60h; "C;;;S-1-15-3-3)"
0x18002366e  movaps  [rbp+60h+var_60], xmm1
0x180023672  movaps  xmm1, xmmword ptr cs:aACcS11531ACcS1+70h; "15-3-3)"
0x180023679  movaps  [rbp+60h+var_50], xmm0
0x18002367d  movaps  [rbp+60h+var_40], xmm1
0x180023681  mov     [rsp+160h+pszDest], r13
0x180023686  mov     [rbp+60h+var_C0], eax
0x180023689  mov     [rsp+160h+SecurityDescriptor], r13
0x18002368e  mov     [rsp+160h+var_138], r13
0x180023693  inc     rbx
0x180023696  cmp     [rcx+rbx*2], r13w
0x18002369b  jnz     short loc_180023693
0x18002369d  lea     rbx, ds:0E2h[rbx*2]
0x1800236a5  xor     edx, edx; dwFlags
0x1800236a7  mov     rcx, rbx; dwBytes
0x1800236aa  lea     r8, [rsp+160h+pszDest]
0x1800236af  call    WfpMemAlloc
0x1800236b4  mov     rdi, rax
0x1800236b7  test    rax, rax
0x1800236ba  jnz     loc_1800237CF
0x1800236c0  mov     rcx, [rsp+160h+pszDest]; void *
0x1800236c5  mov     r8, rbx; Size
0x1800236c8  xor     edx, edx; Val
0x1800236ca  call    memset_0
0x1800236cf  mov     rcx, [rsp+160h+pszDest]; pszDest
0x1800236d4  lea     r8, [rsp+160h+pszSrc]; pszSrc
0x1800236d9  mov     rdx, rbx; cbDest
0x1800236dc  call    StringCbCatW
0x1800236e1  test    eax, eax
0x1800236e3  js      loc_18002384B
0x1800236e9  mov     rcx, [rsp+160h+pszDest]; pszDest
0x1800236ee  mov     r8, r14; pszSrc
0x1800236f1  mov     rdx, rbx; cbDest
0x1800236f4  call    StringCbCatW
0x1800236f9  test    eax, eax
0x1800236fb  js      loc_18002384B
0x180023701  mov     rcx, [rsp+160h+pszDest]; pszDest
0x180023706  lea     r8, [rbp+60h+var_B0]; pszSrc
0x18002370a  mov     rdx, rbx; cbDest
0x18002370d  call    StringCbCatW
0x180023712  test    eax, eax
0x180023714  js      loc_18002384B
0x18002371a  mov     rcx, [rsp+160h+pszDest]; StringSecurityDescriptor
0x18002371f  lea     r8, [rsp+160h+SecurityDescriptor]; SecurityDescriptor
0x180023724  xor     r9d, r9d; SecurityDescriptorSize
0x180023727  lea     edx, [rdi+1]; StringSDRevision
0x18002372a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180023731  nop     dword ptr [rax+rax+00h]
0x180023736  test    eax, eax
0x180023738  jz      loc_18002382C
0x18002373e  mov     rcx, [rsp+160h+SecurityDescriptor]; pSecurityDescriptor
0x180023743  call    cs:__imp_GetSecurityDescriptorLength
0x18002374a  nop     dword ptr [rax+rax+00h]
0x18002374f  lea     r14, [r15+20h]
0x180023753  xor     edx, edx; dwFlags
0x180023755  lea     ecx, [rdi+10h]; dwBytes
0x180023758  mov     r13d, eax
0x18002375b  mov     r8, r14
0x18002375e  mov     [r14], r12
0x180023761  call    WfpMemAlloc
0x180023766  mov     rdi, rax
0x180023769  test    rax, rax
0x18002376c  jnz     loc_18002386D
0x180023772  lea     r8, [rsp+160h+var_138]
0x180023777  xor     edx, edx; dwFlags
0x180023779  mov     ecx, r13d; dwBytes
0x18002377c  call    WfpMemAlloc
0x180023781  mov     rdi, rax
0x180023784  test    rax, rax
0x180023787  jnz     loc_180023868
0x18002378d  mov     rbx, [rsp+160h+var_138]
0x180023792  mov     r8d, r13d; Size
0x180023795  mov     rdx, [rsp+160h+SecurityDescriptor]; Src
0x18002379a  mov     rcx, rbx; void *
0x18002379d  call    memcpy_0
0x1800237a2  movups  xmm0, cs:FWPM_CONDITION_ALE_PACKAGE_FAMILY_NAME
0x1800237a9  mov     rax, [r14]
0x1800237ac  mov     [r15+10h], r12d
0x1800237b0  movdqu  xmmword ptr [r15], xmm0
0x1800237b5  mov     dword ptr [r15+18h], 0Eh
0x1800237bd  mov     [rax], r13d
0x1800237c0  xor     r13d, r13d
0x1800237c3  mov     rax, [r14]
0x1800237c6  mov     [rsp+160h+var_138], r13
0x1800237cb  mov     [rax+8], rbx
0x1800237cf  cmp     [rsp+160h+pszDest], r13
0x1800237d4  jz      short loc_1800237E0
0x1800237d6  lea     rcx, [rsp+160h+pszDest]
0x1800237db  call    WfpMemFree
0x1800237e0  mov     rcx, [rsp+160h+SecurityDescriptor]; hMem
0x1800237e5  call    cs:__imp_LocalFree
0x1800237ec  nop     dword ptr [rax+rax+00h]
0x1800237f1  test    r12, r12
0x1800237f4  jnz     short loc_180023875
0x1800237f6  test    rdi, rdi
0x1800237f9  jnz     loc_180023884
0x1800237ff  mov     rax, rdi
0x180023802  mov     rcx, [rbp+60h+var_30]
0x180023806  xor     rcx, rsp; StackCookie
0x180023809  call    __security_check_cookie
0x18002380e  lea     r11, [rsp+160h+var_20]
0x180023816  mov     rbx, [r11+40h]
0x18002381a  mov     rdi, [r11+48h]
0x18002381e  mov     rsp, r11
0x180023821  pop     r15
0x180023823  pop     r14
0x180023825  pop     r13
0x180023827  pop     r12
0x180023829  pop     rbp
0x18002382a  retn
0x18002382c  call    cs:__imp_GetLastError
0x180023833  nop     dword ptr [rax+rax+00h]
0x180023838  test    eax, eax
0x18002383a  jg      short loc_180023841
0x18002383c  movsxd  rdi, eax
0x18002383f  jmp     short loc_1800237CF
0x180023841  movzx   eax, ax
0x180023844  or      eax, 80070000h
0x180023849  jmp     short loc_18002383C
0x18002384b  mov     r9d, 1
0x180023851  lea     rdx, aBfecreatepfnco; "BfeCreatePfnCondition"
0x180023858  mov     r8d, eax
0x18002385b  call    WfpReportSysErrorAsHResult
0x180023860  mov     rdi, rax
0x180023863  jmp     loc_1800237CF
0x180023868  mov     r12, [rsp+160h+var_138]
0x18002386d  xor     r13d, r13d
0x180023870  jmp     loc_1800237CF
0x180023875  lea     rcx, [rsp+160h+var_138]
0x18002387a  call    WfpMemFree
0x18002387f  jmp     loc_1800237F6
0x180023884  lea     rcx, [r15+20h]
0x180023888  cmp     [rcx], r13
0x18002388b  jz      loc_18008BD0C
0x180023891  call    WfpMemFree
0x180023896  nop
0x180023897  jmp     loc_18008BD0C
0x18008bd0c  lea     rdx, aBfecreatepfnco; "BfeCreatePfnCondition"
0x18008bd13  mov     rcx, rdi
0x18008bd16  call    WfpReportError
0x18008bd1b  nop
0x18008bd1c  jmp     loc_1800237FF
```
