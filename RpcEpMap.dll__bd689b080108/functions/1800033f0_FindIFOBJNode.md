# FindIFOBJNode

- ea: `0x1800033f0`
- end: `0x180003595`
- name: `FindIFOBJNode`
- size: `421`
- prototype: `__int64 *__fastcall(__int64 *, __int64, __int64, unsigned int, void *, int, int, unsigned int (__fastcall *)(__int64 *, __int64, __int64, _QWORD, int, int), __int64, int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800018a0`
- `0x180002bc0`
- `0x180005b24`
- `0x180006cf0`

## callees

- `0x1800033f0`
- `0x18000a980`
- `0x18000b010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180003519`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180003519`

## pseudocode

```c
__int64 *__fastcall FindIFOBJNode(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        void *a5,
        int a6,
        int a7,
        unsigned int (__fastcall *a8)(__int64 *, __int64, __int64, _QWORD, int, int),
        __int64 a9,
        int *a10)
{
  int v14; // eax
  int v15; // ecx
  int v17; // [rsp+40h] [rbp-188h]
  DWORD PrivilegeSetLength; // [rsp+44h] [rbp-184h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp-180h] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp-17Ch] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+50h] [rbp-178h]
  int *v22; // [rsp+58h] [rbp-170h]
  _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp-168h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp-158h] BYREF

  pSecurityDescriptor = a5;
  v22 = a10;
  PrivilegeSetLength = 0;
  GrantedAccess = 0;
  AccessStatus = 0;
  v17 = 0;
  GenericMapping.GenericRead = 0x20000;
  GenericMapping.GenericWrite = 0x20000;
  GenericMapping.GenericExecute = 0x20000;
  GenericMapping.GenericAll = 2031616;
  while ( a1 )
  {
    if ( a9 && a9 != a1[5] )
    {
      a1 = 0;
      break;
    }
    if ( !a8(a1, a2, a3, a4, a6, a7) )
    {
      v14 = (int)pSecurityDescriptor;
      if ( !pSecurityDescriptor )
        goto LABEL_11;
      PrivilegeSetLength = 256;
      if ( AccessCheck(
             pSecurityDescriptor,
             (HANDLE)a1[3],
             0x20000u,
             &GenericMapping,
             &PrivilegeSet,
             &PrivilegeSetLength,
             &GrantedAccess,
             &AccessStatus) )
      {
        if ( AccessStatus )
        {
          v14 = 0;
          v15 = 0;
          goto LABEL_12;
        }
        v17 = 1;
      }
    }
    a1 = (__int64 *)*a1;
  }
  v14 = 1168;
LABEL_11:
  v15 = v17;
LABEL_12:
  if ( v22 )
  {
    if ( v15 )
      v14 = 5;
    *v22 = v14;
  }
  return a1;
}

```

## disassembly

```asm
0x1800033f0  push    rbx
0x1800033f2  push    rbp
0x1800033f3  push    rsi
0x1800033f4  push    rdi
0x1800033f5  push    r12
0x1800033f7  push    r13
0x1800033f9  push    r14
0x1800033fb  push    r15
0x1800033fd  sub     rsp, 188h
0x180003404  mov     rax, cs:__security_cookie
0x18000340b  xor     rax, rsp
0x18000340e  mov     [rsp+1C8h+var_58], rax
0x180003416  mov     rax, [rsp+1C8h+arg_20]
0x18000341e  mov     rsi, rdx
0x180003421  mov     r15, [rsp+1C8h+arg_38]
0x180003429  xor     edx, edx
0x18000342b  mov     rdi, [rsp+1C8h+arg_40]
0x180003433  mov     r14d, r9d
0x180003436  mov     r12d, [rsp+1C8h+arg_30]
0x18000343e  mov     rbp, r8
0x180003441  mov     r13d, [rsp+1C8h+arg_28]
0x180003449  mov     rbx, rcx
0x18000344c  mov     [rsp+1C8h+pSecurityDescriptor], rax
0x180003451  mov     rax, [rsp+1C8h+arg_48]
0x180003459  mov     [rsp+1C8h+var_170], rax
0x18000345e  mov     [rsp+1C8h+var_184], edx
0x180003462  mov     [rsp+1C8h+var_17C], edx
0x180003466  mov     [rsp+1C8h+var_180], edx
0x18000346a  mov     [rsp+1C8h+var_188], edx
0x18000346e  mov     [rsp+1C8h+GenericMapping.GenericRead], 20000h
0x180003476  mov     [rsp+1C8h+GenericMapping.GenericWrite], 20000h
0x18000347e  mov     [rsp+1C8h+GenericMapping.GenericExecute], 20000h
0x180003486  mov     [rsp+1C8h+GenericMapping.GenericAll], 1F0000h
0x18000348e  xchg    ax, ax
0x180003490  test    rbx, rbx
0x180003493  jz      loc_180003532
0x180003499  test    rdi, rdi
0x18000349c  jnz     loc_180003589
0x1800034a2  mov     dword ptr [rsp+1C8h+PrivilegeSetLength], r12d
0x1800034a7  mov     r9d, r14d
0x1800034aa  mov     r8, rbp
0x1800034ad  mov     dword ptr [rsp+1C8h+PrivilegeSet], r13d
0x1800034b2  mov     rdx, rsi
0x1800034b5  mov     rcx, rbx
0x1800034b8  mov     rax, r15
0x1800034bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c0  test    eax, eax
0x1800034c2  jz      short loc_1800034C9
0x1800034c4  mov     rbx, [rbx]
0x1800034c7  jmp     short loc_180003490
0x1800034c9  mov     rax, [rsp+1C8h+pSecurityDescriptor]
0x1800034ce  test    rax, rax
0x1800034d1  jz      loc_18000357A
0x1800034d7  lea     rcx, [rsp+1C8h+var_180]
0x1800034dc  mov     [rsp+1C8h+var_184], 100h
0x1800034e4  mov     rdx, [rbx+18h]; ClientToken
0x1800034e8  lea     r9, [rsp+1C8h+GenericMapping]; GenericMapping
0x1800034ed  mov     [rsp+1C8h+AccessStatus], rcx; AccessStatus
0x1800034f2  mov     r8d, 20000h; DesiredAccess
0x1800034f8  lea     rcx, [rsp+1C8h+var_17C]
0x1800034fd  mov     [rsp+1C8h+GrantedAccess], rcx; GrantedAccess
0x180003502  lea     rcx, [rsp+1C8h+var_184]
0x180003507  mov     [rsp+1C8h+PrivilegeSetLength], rcx; PrivilegeSetLength
0x18000350c  lea     rcx, [rsp+1C8h+var_158]
0x180003511  mov     [rsp+1C8h+PrivilegeSet], rcx; PrivilegeSet
0x180003516  mov     rcx, rax; pSecurityDescriptor
0x180003519  call    cs:__imp_AccessCheck
0x18000351f  test    eax, eax
0x180003521  jz      short loc_1800034C4
0x180003523  cmp     [rsp+1C8h+var_180], 0
0x180003528  jz      short loc_18000357C
0x18000352a  xor     eax, eax
0x18000352c  xor     ecx, ecx
0x18000352e  jmp     short loc_18000353B
0x180003530  xor     ebx, ebx
0x180003532  mov     eax, 490h
0x180003537  mov     ecx, [rsp+1C8h+var_188]
0x18000353b  mov     rdx, [rsp+1C8h+var_170]
0x180003540  test    rdx, rdx
0x180003543  jz      short loc_180003553
0x180003545  test    ecx, ecx
0x180003547  mov     r8d, 5
0x18000354d  cmovnz  eax, r8d
0x180003551  mov     [rdx], eax
0x180003553  mov     rax, rbx
0x180003556  mov     rcx, [rsp+1C8h+var_58]
0x18000355e  xor     rcx, rsp; StackCookie
0x180003561  call    __security_check_cookie
0x180003566  add     rsp, 188h
0x18000356d  pop     r15
0x18000356f  pop     r14
0x180003571  pop     r13
0x180003573  pop     r12
0x180003575  pop     rdi
0x180003576  pop     rsi
0x180003577  pop     rbp
0x180003578  pop     rbx
0x180003579  retn
0x18000357a  jmp     short loc_180003537
0x18000357c  mov     [rsp+1C8h+var_188], 1
0x180003584  jmp     loc_1800034C4
0x180003589  cmp     rdi, [rbx+28h]
0x18000358d  jz      loc_1800034A2
0x180003593  jmp     short loc_180003530
```
