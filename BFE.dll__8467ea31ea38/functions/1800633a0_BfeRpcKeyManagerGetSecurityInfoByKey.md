# BfeRpcKeyManagerGetSecurityInfoByKey

- ea: `0x1800633a0`
- end: `0x1800634a5`
- name: `BfeRpcKeyManagerGetSecurityInfoByKey`
- size: `261`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, SECURITY_INFORMATION, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009aa0`
- `0x18000ad28`
- `0x18001236c`
- `0x180018b74`
- `0x180020c30`
- `0x180022360`
- `0x180045600`
- `0x18005766c`
- `0x180058b30`
- `0x1800633a0`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180063462`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180063462`

## string_xrefs

- `0x180063420`: `BfeKeyManagerGetSecurityInfoByKey`
- `0x18006344e`: `BfeKeyManagerGetSecurityInfoByKey`

## pseudocode

```c
__int64 __fastcall BfeRpcKeyManagerGetSecurityInfoByKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        SECURITY_INFORMATION a4,
        __int64 a5)
{
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 Info; // rax
  _OWORD v12[2]; // [rsp+38h] [rbp-40h] BYREF

  memset(v12, 0, sizeof(v12));
  v7 = BfeCallCreate(a1, a2, 0, 1, v12);
  if ( !v7 )
  {
    v8 = BfeSecurityInformationValidate(a4);
    LODWORD(v7) = v8;
    if ( !v8 )
    {
      if ( (unsigned int)BfeGuidIsNull(a3) )
        Info = BfeObjectSecurityGetInfo(gBfeKeyManagerComponent, a4);
      else
        Info = WfpReportSysErrorAsWinError(v9, "BfeKeyManagerGetSecurityInfoByKey", 2150760489LL);
      LODWORD(v7) = Info;
      if ( Info )
      {
        WfpReportError(Info, "BfeKeyManagerGetSecurityInfoByKey");
      }
      else
      {
        *(_DWORD *)a5 = RtlLengthSecurityDescriptor(0);
        *(_QWORD *)(a5 + 8) = 0;
      }
    }
  }
  BfeCallDestroy(v12);
  BfeRpcRaiseExceptionIfError(v7);
  return 0;
}

```

## disassembly

```asm
0x1800633a0  mov     r11, rsp
0x1800633a3  mov     [r11+8], rbx
0x1800633a7  mov     [r11+18h], rbp
0x1800633ab  push    rsi
0x1800633ac  push    rdi
0x1800633ad  push    r14
0x1800633af  sub     rsp, 60h
0x1800633b3  mov     rax, cs:__security_cookie
0x1800633ba  xor     rax, rsp
0x1800633bd  mov     [rsp+78h+var_20], rax
0x1800633c2  mov     r14, [rsp+78h+arg_20]
0x1800633ca  lea     rax, [r11-40h]
0x1800633ce  xorps   xmm0, xmm0
0x1800633d1  mov     [r11-58h], rax
0x1800633d5  xor     edi, edi
0x1800633d7  mov     esi, r9d
0x1800633da  mov     rbp, r8
0x1800633dd  mov     [r11-48h], rdi
0x1800633e1  xor     r8d, r8d; int
0x1800633e4  movups  [rsp+78h+var_40], xmm0
0x1800633e9  lea     r9d, [rdi+1]; int
0x1800633ed  movups  [rsp+78h+var_30], xmm0
0x1800633f2  call    BfeCallCreate
0x1800633f7  mov     rbx, rax
0x1800633fa  test    rax, rax
0x1800633fd  jnz     short loc_18006346F
0x1800633ff  mov     ecx, esi
0x180063401  call    BfeSecurityInformationValidate
0x180063406  mov     rbx, rax
0x180063409  test    rax, rax
0x18006340c  jnz     short loc_18006346F
0x18006340e  mov     rcx, rbp
0x180063411  call    BfeGuidIsNull
0x180063416  test    eax, eax
0x180063418  jnz     short loc_18006342E
0x18006341a  mov     r8d, 80320029h
0x180063420  lea     rdx, aBfekeymanagerg; "BfeKeyManagerGetSecurityInfoByKey"
0x180063427  call    WfpReportSysErrorAsWinError
0x18006342c  jmp     short loc_180063446
0x18006342e  mov     rcx, qword ptr cs:gBfeKeyManagerComponent; pSecurityDescriptor
0x180063435  lea     r8, [rsp+78h+var_48]
0x18006343a  mov     edx, esi; SecurityInformation
0x18006343c  call    BfeObjectSecurityGetInfo
0x180063441  mov     rdi, [rsp+78h+var_48]
0x180063446  mov     rbx, rax
0x180063449  test    rax, rax
0x18006344c  jz      short loc_18006345F
0x18006344e  lea     rdx, aBfekeymanagerg; "BfeKeyManagerGetSecurityInfoByKey"
0x180063455  mov     rcx, rax
0x180063458  call    WfpReportError
0x18006345d  jmp     short loc_18006346F
0x18006345f  mov     rcx, rdi; SecurityDescriptor
0x180063462  call    cs:__imp_RtlLengthSecurityDescriptor
0x180063468  mov     [r14], eax
0x18006346b  mov     [r14+8], rdi
0x18006346f  lea     rcx, [rsp+78h+var_40]
0x180063474  call    BfeCallDestroy
0x180063479  mov     rcx, rbx; exception
0x18006347c  call    BfeRpcRaiseExceptionIfError
0x180063481  xor     eax, eax
0x180063483  mov     rcx, [rsp+78h+var_20]
0x180063488  xor     rcx, rsp; StackCookie
0x18006348b  call    __security_check_cookie
0x180063490  lea     r11, [rsp+78h+var_18]
0x180063495  mov     rbx, [r11+20h]
0x180063499  mov     rbp, [r11+30h]
0x18006349d  mov     rsp, r11
0x1800634a0  pop     r14
0x1800634a2  pop     rdi
0x1800634a3  pop     rsi
0x1800634a4  retn
```
