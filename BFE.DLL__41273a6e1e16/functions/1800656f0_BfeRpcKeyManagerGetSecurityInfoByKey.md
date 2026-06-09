# BfeRpcKeyManagerGetSecurityInfoByKey

- ea: `0x1800656f0`
- end: `0x1800657fc`
- name: `BfeRpcKeyManagerGetSecurityInfoByKey`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a070`
- `0x18000b3d4`
- `0x180012d8c`
- `0x1800197d0`
- `0x180023280`
- `0x180024a5c`
- `0x1800474b8`
- `0x1800593ac`
- `0x18005aa60`
- `0x1800656f0`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x1800657b2`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800657b2`

## string_xrefs

- `0x180065770`: `BfeKeyManagerGetSecurityInfoByKey`
- `0x18006579e`: `BfeKeyManagerGetSecurityInfoByKey`

## pseudocode

```c
__int64 __fastcall BfeRpcKeyManagerGetSecurityInfoByKey(
        int a1,
        int a2,
        __int64 a3,
        SECURITY_INFORMATION a4,
        __int64 a5)
{
  void *v5; // rdi
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 Info; // rax
  void *v12; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v13[2]; // [rsp+38h] [rbp-40h] BYREF

  v5 = 0;
  v12 = 0;
  memset(v13, 0, sizeof(v13));
  v8 = BfeCallCreate(a1, a2, 0, 1, v13);
  if ( !v8 )
  {
    v8 = BfeSecurityInformationValidate(a4);
    if ( !v8 )
    {
      if ( (unsigned int)BfeGuidIsNull(a3) )
      {
        Info = BfeObjectSecurityGetInfo(gBfeKeyManagerComponent, a4, &v12);
        v5 = v12;
      }
      else
      {
        Info = WfpReportSysErrorAsWinError(v9, "BfeKeyManagerGetSecurityInfoByKey", 2150760489LL);
      }
      LODWORD(v8) = Info;
      if ( Info )
      {
        WfpReportError(Info, "BfeKeyManagerGetSecurityInfoByKey");
      }
      else
      {
        *(_DWORD *)a5 = RtlLengthSecurityDescriptor(v5);
        *(_QWORD *)(a5 + 8) = v5;
      }
    }
  }
  BfeCallDestroy(v13);
  BfeRpcRaiseExceptionIfError(v8);
  return 0;
}

```

## disassembly

```asm
0x1800656f0  mov     r11, rsp
0x1800656f3  mov     [r11+8], rbx
0x1800656f7  mov     [r11+18h], rbp
0x1800656fb  push    rsi
0x1800656fc  push    rdi
0x1800656fd  push    r14
0x1800656ff  sub     rsp, 60h
0x180065703  mov     rax, cs:__security_cookie
0x18006570a  xor     rax, rsp
0x18006570d  mov     [rsp+78h+var_20], rax
0x180065712  mov     r14, [rsp+78h+arg_20]
0x18006571a  lea     rax, [r11-40h]
0x18006571e  xorps   xmm0, xmm0
0x180065721  mov     [r11-58h], rax
0x180065725  xor     edi, edi
0x180065727  mov     esi, r9d
0x18006572a  mov     rbp, r8
0x18006572d  mov     [r11-48h], rdi
0x180065731  xor     r8d, r8d; int
0x180065734  movups  [rsp+78h+var_40], xmm0
0x180065739  lea     r9d, [rdi+1]; int
0x18006573d  movups  [rsp+78h+var_30], xmm0
0x180065742  call    BfeCallCreate
0x180065747  mov     rbx, rax
0x18006574a  test    rax, rax
0x18006574d  jnz     short loc_1800657C5
0x18006574f  mov     ecx, esi
0x180065751  call    BfeSecurityInformationValidate
0x180065756  mov     rbx, rax
0x180065759  test    rax, rax
0x18006575c  jnz     short loc_1800657C5
0x18006575e  mov     rcx, rbp
0x180065761  call    BfeGuidIsNull
0x180065766  test    eax, eax
0x180065768  jnz     short loc_18006577E
0x18006576a  mov     r8d, 80320029h
0x180065770  lea     rdx, aBfekeymanagerg; "BfeKeyManagerGetSecurityInfoByKey"
0x180065777  call    WfpReportSysErrorAsWinError
0x18006577c  jmp     short loc_180065796
0x18006577e  mov     rcx, qword ptr cs:gBfeKeyManagerComponent; pSecurityDescriptor
0x180065785  lea     r8, [rsp+78h+var_48]
0x18006578a  mov     edx, esi; SecurityInformation
0x18006578c  call    BfeObjectSecurityGetInfo
0x180065791  mov     rdi, [rsp+78h+var_48]
0x180065796  mov     rbx, rax
0x180065799  test    rax, rax
0x18006579c  jz      short loc_1800657AF
0x18006579e  lea     rdx, aBfekeymanagerg; "BfeKeyManagerGetSecurityInfoByKey"
0x1800657a5  mov     rcx, rax
0x1800657a8  call    WfpReportError
0x1800657ad  jmp     short loc_1800657C5
0x1800657af  mov     rcx, rdi; SecurityDescriptor
0x1800657b2  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800657b9  nop     dword ptr [rax+rax+00h]
0x1800657be  mov     [r14], eax
0x1800657c1  mov     [r14+8], rdi
0x1800657c5  lea     rcx, [rsp+78h+var_40]
0x1800657ca  call    BfeCallDestroy
0x1800657cf  mov     rcx, rbx; exception
0x1800657d2  call    BfeRpcRaiseExceptionIfError
0x1800657d7  xor     eax, eax
0x1800657d9  mov     rcx, [rsp+78h+var_20]
0x1800657de  xor     rcx, rsp; StackCookie
0x1800657e1  call    __security_check_cookie
0x1800657e6  lea     r11, [rsp+78h+var_18]
0x1800657eb  mov     rbx, [r11+20h]
0x1800657ef  mov     rbp, [r11+30h]
0x1800657f3  mov     rsp, r11
0x1800657f6  pop     r14
0x1800657f8  pop     rdi
0x1800657f9  pop     rsi
0x1800657fa  retn
```
