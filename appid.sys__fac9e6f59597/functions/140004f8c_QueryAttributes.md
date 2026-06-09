# QueryAttributes

- ea: `0x140004f8c`
- end: `0x1400051bb`
- name: `QueryAttributes`
- size: `559`
- prototype: `__int64 __fastcall(_QWORD *, char, _QWORD *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400051c4`
- `0x14000525c`
- `0x140005370`
- `0x14002dda8`

## callees

- `0x1400048b8`
- `0x140004f8c`
- `0x140006a20`
- `0x140006f40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400050c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000515a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000517d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400050c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000515a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000517d`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x140005119`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x140005119`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140005102`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140005102`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14000512b`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14000512b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004fef`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005025`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005053`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000507e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400050ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004fef`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005025`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005053`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000507e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400050ac`

## pseudocode

```c
__int64 __fastcall QueryAttributes(_QWORD *a1, char a2, _QWORD *a3)
{
  void *v6; // r14
  unsigned int v7; // ebx
  unsigned int v8; // esi
  int SecurityAttributesToken; // eax
  __int64 v10; // rcx
  unsigned int v11; // edi
  unsigned int v13[4]; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString[4]; // [rsp+40h] [rbp-19h] BYREF

  memset(DestinationString, 0, sizeof(DestinationString));
  v6 = 0;
  v13[0] = 0;
  *a3 = 0;
  if ( (a2 & 1) != 0 )
  {
    v7 = 100;
    RtlInitUnicodeString(DestinationString, L"EDP://PolicyFlags");
    v8 = 1;
  }
  else
  {
    v8 = 0;
    v7 = 16;
  }
  if ( (a2 & 2) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://EnterpriseIds");
  }
  if ( (a2 & 4) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"PEDP://IntentEnterpriseId");
  }
  if ( (a2 & 8) != 0 )
  {
    v7 += 84;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://EvaluationFlags");
  }
  if ( (a2 & 0x10) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://ExemptEnterpriseIds");
  }
  while ( 1 )
  {
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    v6 = (void *)EnterpriseContextLibMemAlloc(v7);
    if ( !v6 )
      return (unsigned int)-1073741801;
    if ( *a1 )
    {
      SecurityAttributesToken = SeQuerySecurityAttributesToken(*a1, DestinationString, v8, v6, v7);
    }
    else
    {
      v10 = a1[3];
      if ( v10 )
        SecurityAttributesToken = ZwQuerySecurityAttributesToken(v10, DestinationString, v8, v6, v7, v13);
      else
        SecurityAttributesToken = SeQuerySecurityAttributesTokenAccessInformation(a1[2], DestinationString, v8, v6);
    }
    v11 = SecurityAttributesToken;
    if ( SecurityAttributesToken != -1073741789 )
    {
      if ( SecurityAttributesToken == -1073741275 )
      {
        ExFreePoolWithTag(v6, 0);
        v11 = 0;
        *a3 = 0;
        return v11;
      }
      if ( SecurityAttributesToken >= 0 )
      {
        *a3 = v6;
        return v11;
      }
LABEL_27:
      ExFreePoolWithTag(v6, 0);
      return v11;
    }
    if ( v7 >= v13[0] )
      goto LABEL_27;
    v7 = v13[0];
  }
}

```

## disassembly

```asm
0x140004f8c  mov     [rsp-8+arg_8], rbx
0x140004f91  mov     [rsp-8+arg_18], rsi
0x140004f96  push    rbp
0x140004f97  push    rdi
0x140004f98  push    r12
0x140004f9a  push    r14
0x140004f9c  push    r15
0x140004f9e  lea     rbp, [rsp-37h]
0x140004fa3  sub     rsp, 90h
0x140004faa  mov     rax, cs:__security_cookie
0x140004fb1  xor     rax, rsp
0x140004fb4  mov     [rbp+57h+var_30], rax
0x140004fb8  mov     edi, edx
0x140004fba  mov     r12, r8
0x140004fbd  xor     edx, edx; Val
0x140004fbf  mov     r15, rcx
0x140004fc2  lea     rcx, [rbp+57h+DestinationString]; void *
0x140004fc6  lea     r8d, [rdx+40h]; Size
0x140004fca  call    memset
0x140004fcf  xor     r14d, r14d
0x140004fd2  mov     [rbp+57h+var_80], r14d
0x140004fd6  mov     [r12], r14
0x140004fda  test    dil, 1
0x140004fde  jz      short loc_140005000
0x140004fe0  lea     rdx, SourceString; "EDP://PolicyFlags"
0x140004fe7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140004feb  lea     ebx, [r14+64h]
0x140004fef  call    cs:__imp_RtlInitUnicodeString
0x140004ff6  nop     dword ptr [rax+rax+00h]
0x140004ffb  lea     esi, [rbx-63h]
0x140004ffe  jmp     short loc_140005005
0x140005000  xor     esi, esi
0x140005002  lea     ebx, [rsi+10h]
0x140005005  test    dil, 2
0x140005009  jz      short loc_140005033
0x14000500b  mov     eax, esi
0x14000500d  lea     rcx, [rbp+57h+DestinationString]
0x140005011  shl     rax, 4
0x140005015  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x14000501c  add     rcx, rax; DestinationString
0x14000501f  add     ebx, 98h
0x140005025  call    cs:__imp_RtlInitUnicodeString
0x14000502c  nop     dword ptr [rax+rax+00h]
0x140005031  inc     esi
0x140005033  test    dil, 4
0x140005037  jz      short loc_140005061
0x140005039  mov     eax, esi
0x14000503b  lea     rcx, [rbp+57h+DestinationString]
0x14000503f  shl     rax, 4
0x140005043  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x14000504a  add     rcx, rax; DestinationString
0x14000504d  add     ebx, 98h
0x140005053  call    cs:__imp_RtlInitUnicodeString
0x14000505a  nop     dword ptr [rax+rax+00h]
0x14000505f  inc     esi
0x140005061  test    dil, 8
0x140005065  jz      short loc_14000508C
0x140005067  mov     eax, esi
0x140005069  lea     rcx, [rbp+57h+DestinationString]
0x14000506d  shl     rax, 4
0x140005071  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x140005078  add     rcx, rax; DestinationString
0x14000507b  add     ebx, 54h ; 'T'
0x14000507e  call    cs:__imp_RtlInitUnicodeString
0x140005085  nop     dword ptr [rax+rax+00h]
0x14000508a  inc     esi
0x14000508c  test    dil, 10h
0x140005090  jz      short loc_1400050BA
0x140005092  mov     eax, esi
0x140005094  lea     rcx, [rbp+57h+DestinationString]
0x140005098  shl     rax, 4
0x14000509c  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x1400050a3  add     rcx, rax; DestinationString
0x1400050a6  add     ebx, 98h
0x1400050ac  call    cs:__imp_RtlInitUnicodeString
0x1400050b3  nop     dword ptr [rax+rax+00h]
0x1400050b8  inc     esi
0x1400050ba  test    r14, r14
0x1400050bd  jz      short loc_1400050D0
0x1400050bf  xor     edx, edx; Tag
0x1400050c1  mov     rcx, r14; P
0x1400050c4  call    cs:__imp_ExFreePoolWithTag
0x1400050cb  nop     dword ptr [rax+rax+00h]
0x1400050d0  mov     ecx, ebx
0x1400050d2  call    EnterpriseContextLibMemAlloc
0x1400050d7  mov     r14, rax
0x1400050da  test    rax, rax
0x1400050dd  jz      loc_14000518B
0x1400050e3  mov     rcx, [r15]
0x1400050e6  lea     rax, [rbp+57h+var_80]
0x1400050ea  mov     [rsp+0B0h+var_88], rax
0x1400050ef  mov     r9, r14
0x1400050f2  mov     [rsp+0B0h+var_90], ebx
0x1400050f6  mov     r8d, esi
0x1400050f9  lea     rdx, [rbp+57h+DestinationString]
0x1400050fd  test    rcx, rcx
0x140005100  jz      short loc_140005110
0x140005102  call    cs:__imp_SeQuerySecurityAttributesToken
0x140005109  nop     dword ptr [rax+rax+00h]
0x14000510e  jmp     short loc_140005137
0x140005110  mov     rcx, [r15+18h]
0x140005114  test    rcx, rcx
0x140005117  jz      short loc_140005127
0x140005119  call    cs:__imp_ZwQuerySecurityAttributesToken
0x140005120  nop     dword ptr [rax+rax+00h]
0x140005125  jmp     short loc_140005137
0x140005127  mov     rcx, [r15+10h]
0x14000512b  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x140005132  nop     dword ptr [rax+rax+00h]
0x140005137  mov     edi, eax
0x140005139  cmp     eax, 0C0000023h
0x14000513e  jnz     short loc_14000514D
0x140005140  cmp     ebx, [rbp+57h+var_80]
0x140005143  jnb     short loc_140005178
0x140005145  mov     ebx, [rbp+57h+var_80]
0x140005148  jmp     loc_1400050BA
0x14000514d  cmp     edi, 0C0000225h
0x140005153  jnz     short loc_14000516E
0x140005155  xor     edx, edx; Tag
0x140005157  mov     rcx, r14; P
0x14000515a  call    cs:__imp_ExFreePoolWithTag
0x140005161  nop     dword ptr [rax+rax+00h]
0x140005166  xor     edi, edi
0x140005168  mov     [r12], rdi
0x14000516c  jmp     short loc_140005190
0x14000516e  test    edi, edi
0x140005170  js      short loc_140005178
0x140005172  mov     [r12], r14
0x140005176  jmp     short loc_140005190
0x140005178  xor     edx, edx; Tag
0x14000517a  mov     rcx, r14; P
0x14000517d  call    cs:__imp_ExFreePoolWithTag
0x140005184  nop     dword ptr [rax+rax+00h]
0x140005189  jmp     short loc_140005190
0x14000518b  mov     edi, 0C0000017h
0x140005190  mov     eax, edi
0x140005192  mov     rcx, [rbp+57h+var_30]
0x140005196  xor     rcx, rsp; StackCookie
0x140005199  call    __security_check_cookie
0x14000519e  lea     r11, [rsp+0B0h+var_20]
0x1400051a6  mov     rbx, [r11+38h]
0x1400051aa  mov     rsi, [r11+48h]
0x1400051ae  mov     rsp, r11
0x1400051b1  pop     r15
0x1400051b3  pop     r14
0x1400051b5  pop     r12
0x1400051b7  pop     rdi
0x1400051b8  pop     rbp
0x1400051b9  retn
```
