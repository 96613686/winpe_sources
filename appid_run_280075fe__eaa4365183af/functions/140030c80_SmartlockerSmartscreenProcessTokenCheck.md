# SmartlockerSmartscreenProcessTokenCheck

- ea: `0x140030c80`
- end: `0x140030f21`
- name: `SmartlockerSmartscreenProcessTokenCheck`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002f560`

## callees

- `0x140022f7c`
- `0x140023110`
- `0x140030c80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140030d7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030dc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030de2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030f10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030d7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030dc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030de2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030f10`
- `ntoskrnl!ExAllocatePool2` at `0x140030d23`
- `ntoskrnl!ExAllocatePool2` at `0x140030d23`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x140030d58`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x140030d58`
- `ntoskrnl!ZwQuerySecurityPolicy` at `0x140030e73`
- `ntoskrnl!ZwQuerySecurityPolicy` at `0x140030e73`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030e3e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030e3e`

## pseudocode

```c
__int64 __fastcall SmartlockerSmartscreenProcessTokenCheck(__int64 a1, __int64 a2, unsigned int *a3, _QWORD *a4)
{
  PVOID v5; // rsi
  __int64 v7; // rbx
  unsigned int v8; // r14d
  unsigned int v9; // r15d
  __int64 Pool2; // rdi
  int v11; // eax
  int v12; // ebx
  __int64 result; // rax
  __int64 v14; // rax
  __int64 *v15; // r15
  __int64 v16; // r15
  int v17; // r8d
  int v18; // eax
  unsigned int v19; // [rsp+40h] [rbp-49h] BYREF
  int v20; // [rsp+44h] [rbp-45h] BYREF
  int v21; // [rsp+48h] [rbp-41h] BYREF
  PVOID P; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v23[2]; // [rsp+58h] [rbp-31h] BYREF
  _QWORD v24[2]; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v25[2]; // [rsp+78h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-1h] BYREF
  char v29; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v30; // [rsp+108h] [rbp+7Fh] BYREF

  v25[0] = 1310738;
  v25[1] = L"Microsoft";
  v24[0] = 3932218;
  v19 = 0;
  v24[1] = L"WindowsLockdownPolicySettings";
  v5 = 0;
  P = 0;
  v23[1] = L"ISGSmartscreenTrustSuppressed";
  v30 = 0;
  v7 = a2;
  v23[0] = 3932218;
  v8 = 0;
  v21 = 0;
  v9 = 654;
  v29 = 0;
  DestinationString = 0;
  v20 = 1;
  while ( 1 )
  {
    Pool2 = ExAllocatePool2(258, v9, 1098149235, a4);
    if ( !Pool2 )
      goto LABEL_6;
    v11 = ZwQuerySecurityAttributesToken(v7, L"HJ", 1, Pool2, v9, &v30);
    v12 = v11;
    if ( v11 != -1073741789 )
      break;
    if ( v9 >= v30 )
      goto LABEL_5;
    v9 = v30;
    ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
    v7 = a2;
  }
  if ( v11 < 0 )
  {
LABEL_5:
    ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
    Pool2 = 0;
LABEL_6:
    v12 = -1073741823;
    goto LABEL_7;
  }
  if ( !*(_DWORD *)(Pool2 + 4) )
    goto LABEL_6;
  v14 = *(_QWORD *)(Pool2 + 8);
  if ( *(_WORD *)(v14 + 16) != 16 )
    goto LABEL_6;
  v15 = *(__int64 **)(v14 + 32);
  if ( *((_DWORD *)v15 + 2) != 524 )
    goto LABEL_6;
  v16 = *v15;
  if ( (*(_DWORD *)v16 & 0x22) != 2 && (*(_DWORD *)v16 & 0x58) == 0 )
    goto LABEL_9;
  *(_WORD *)(v16 + 522) = 0;
  RtlInitUnicodeString(&DestinationString, (PCWSTR)(v16 + 4));
  if ( (*(_DWORD *)v16 & 0x40) == 0 && (int)ZwQuerySecurityPolicy(v25, v24, v23, &v21, &v29, &v20) >= 0 && v29 )
    goto LABEL_6;
  v18 = SmartlockerConstructOriginClaim(
          1,
          0,
          v17,
          *(_DWORD *)v16,
          (__int64)&DestinationString,
          (__int64)&v19,
          (__int64)&P);
  v5 = P;
  v12 = v18;
  if ( v18 >= 0 )
  {
    v8 = v19;
    v12 = SmartlockerTagProcessToken(a1, v19, P);
    if ( v12 >= 0 )
    {
      if ( a1 == a2 )
        goto LABEL_9;
      v12 = SmartlockerTagProcessToken(a2, v8, v5);
      if ( v12 >= 0 )
        goto LABEL_9;
    }
  }
  if ( v5 )
    ExFreePoolWithTag(v5, 0x41746D73u);
LABEL_7:
  v5 = 0;
  v8 = 0;
  if ( !Pool2 )
    goto LABEL_8;
LABEL_9:
  ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
LABEL_8:
  *a3 = v8;
  result = (unsigned int)v12;
  *a4 = v5;
  return result;
}

```

## disassembly

```asm
0x140030c80  mov     [rsp-8+arg_8], rdx
0x140030c85  mov     [rsp-8+arg_0], rcx
0x140030c8a  push    rbp
0x140030c8b  push    rbx
0x140030c8c  push    rsi
0x140030c8d  push    rdi
0x140030c8e  push    r12
0x140030c90  push    r13
0x140030c92  push    r14
0x140030c94  push    r15
0x140030c96  lea     rbp, [rsp-1Fh]
0x140030c9b  sub     rsp, 0A8h
0x140030ca2  lea     rax, aMicrosoft; "Microsoft"
0x140030ca9  mov     [rbp+57h+var_68], 140012h
0x140030cb1  mov     [rbp+57h+var_60], rax
0x140030cb5  mov     r13, r8
0x140030cb8  xor     r8d, r8d
0x140030cbb  mov     [rbp+57h+var_78], 3C003Ah
0x140030cc3  lea     rax, aWindowslockdow; "WindowsLockdownPolicySettings"
0x140030cca  mov     [rbp+57h+var_A0], r8d
0x140030cce  mov     [rbp+57h+var_70], rax
0x140030cd2  mov     esi, r8d
0x140030cd5  lea     rax, aIsgsmartscreen; "ISGSmartscreenTrustSuppressed"
0x140030cdc  mov     [rbp+57h+P], r8
0x140030ce0  xorps   xmm0, xmm0
0x140030ce3  mov     [rbp+57h+var_80], rax
0x140030ce7  mov     r12, r9
0x140030cea  mov     [rbp+57h+arg_18], r8d
0x140030cee  mov     rbx, rdx
0x140030cf1  mov     [rbp+57h+var_88], 3C003Ah
0x140030cf9  mov     r14d, r8d
0x140030cfc  mov     [rbp+57h+var_98], r8d
0x140030d00  mov     r15d, 28Eh
0x140030d06  mov     [rbp+57h+arg_10], sil
0x140030d0a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140030d0e  mov     [rbp+57h+var_9C], 1
0x140030d15  mov     edx, r15d
0x140030d18  mov     ecx, 102h
0x140030d1d  mov     r8d, 41746D73h
0x140030d23  call    cs:__imp_ExAllocatePool2
0x140030d2a  nop     dword ptr [rax+rax+00h]
0x140030d2f  mov     rdi, rax
0x140030d32  test    rax, rax
0x140030d35  jz      short loc_140030D8B
0x140030d37  lea     rax, [rbp+57h+arg_18]
0x140030d3b  mov     r9, rdi
0x140030d3e  mov     [rsp+0E0h+var_B8], rax
0x140030d43  lea     rdx, aHj; "HJ"
0x140030d4a  mov     r8d, 1
0x140030d50  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x140030d55  mov     rcx, rbx
0x140030d58  call    cs:__imp_ZwQuerySecurityAttributesToken
0x140030d5f  nop     dword ptr [rax+rax+00h]
0x140030d64  mov     ebx, eax
0x140030d66  cmp     eax, 0C0000023h
0x140030d6b  jz      short loc_140030DCF
0x140030d6d  test    eax, eax
0x140030d6f  jns     loc_140030DF7
0x140030d75  mov     edx, 41746D73h; Tag
0x140030d7a  mov     rcx, rdi; P
0x140030d7d  call    cs:__imp_ExFreePoolWithTag
0x140030d84  nop     dword ptr [rax+rax+00h]
0x140030d89  xor     edi, edi
0x140030d8b  mov     ebx, 0C0000001h
0x140030d90  xor     esi, esi
0x140030d92  xor     r14d, r14d
0x140030d95  test    rdi, rdi
0x140030d98  jnz     short loc_140030DB9
0x140030d9a  mov     [r13+0], r14d
0x140030d9e  mov     eax, ebx
0x140030da0  mov     [r12], rsi
0x140030da4  add     rsp, 0A8h
0x140030dab  pop     r15
0x140030dad  pop     r14
0x140030daf  pop     r13
0x140030db1  pop     r12
0x140030db3  pop     rdi
0x140030db4  pop     rsi
0x140030db5  pop     rbx
0x140030db6  pop     rbp
0x140030db7  retn
0x140030db9  mov     edx, 41746D73h; Tag
0x140030dbe  mov     rcx, rdi; P
0x140030dc1  call    cs:__imp_ExFreePoolWithTag
0x140030dc8  nop     dword ptr [rax+rax+00h]
0x140030dcd  jmp     short loc_140030D9A
0x140030dcf  mov     eax, [rbp+57h+arg_18]
0x140030dd2  cmp     r15d, eax
0x140030dd5  jnb     short loc_140030D75
0x140030dd7  mov     edx, 41746D73h; Tag
0x140030ddc  mov     rcx, rdi; P
0x140030ddf  mov     r15d, eax
0x140030de2  call    cs:__imp_ExFreePoolWithTag
0x140030de9  nop     dword ptr [rax+rax+00h]
0x140030dee  mov     rbx, [rbp+57h+arg_8]
0x140030df2  jmp     loc_140030D15
0x140030df7  cmp     [rdi+4], esi
0x140030dfa  jbe     short loc_140030D8B
0x140030dfc  mov     rax, [rdi+8]
0x140030e00  cmp     word ptr [rax+10h], 10h
0x140030e05  jnz     short loc_140030D8B
0x140030e07  mov     r15, [rax+20h]
0x140030e0b  cmp     dword ptr [r15+8], 20Ch
0x140030e13  jnz     loc_140030D8B
0x140030e19  mov     r15, [r15]
0x140030e1c  mov     ecx, [r15]
0x140030e1f  mov     eax, ecx
0x140030e21  and     al, 22h
0x140030e23  cmp     al, 2
0x140030e25  jz      short loc_140030E2C
0x140030e27  test    cl, 58h
0x140030e2a  jz      short loc_140030DB9
0x140030e2c  xor     eax, eax
0x140030e2e  lea     rdx, [r15+4]; SourceString
0x140030e32  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140030e36  mov     [r15+20Ah], ax
0x140030e3e  call    cs:__imp_RtlInitUnicodeString
0x140030e45  nop     dword ptr [rax+rax+00h]
0x140030e4a  mov     eax, [r15]
0x140030e4d  test    al, 40h
0x140030e4f  jnz     short loc_140030E8D
0x140030e51  lea     rax, [rbp+57h+var_9C]
0x140030e55  mov     [rsp+0E0h+var_B8], rax
0x140030e5a  lea     r9, [rbp+57h+var_98]
0x140030e5e  lea     rax, [rbp+57h+arg_10]
0x140030e62  lea     r8, [rbp+57h+var_88]
0x140030e66  mov     [rsp+0E0h+var_C0], rax
0x140030e6b  lea     rdx, [rbp+57h+var_78]
0x140030e6f  lea     rcx, [rbp+57h+var_68]
0x140030e73  call    cs:__imp_ZwQuerySecurityPolicy
0x140030e7a  nop     dword ptr [rax+rax+00h]
0x140030e7f  test    eax, eax
0x140030e81  js      short loc_140030E8D
0x140030e83  cmp     [rbp+57h+arg_10], sil
0x140030e87  jnz     loc_140030D8B
0x140030e8d  mov     r9d, [r15]
0x140030e90  lea     rax, [rbp+57h+P]
0x140030e94  mov     [rsp+0E0h+var_B0], rax
0x140030e99  xor     edx, edx
0x140030e9b  lea     rax, [rbp+57h+var_A0]
0x140030e9f  mov     ecx, 1
0x140030ea4  mov     [rsp+0E0h+var_B8], rax
0x140030ea9  lea     rax, [rbp+57h+DestinationString]
0x140030ead  mov     [rsp+0E0h+var_C0], rax
0x140030eb2  call    SmartlockerConstructOriginClaim
0x140030eb7  mov     rsi, [rbp+57h+P]
0x140030ebb  mov     ebx, eax
0x140030ebd  test    eax, eax
0x140030ebf  js      short loc_140030EFF
0x140030ec1  mov     r15, [rbp+57h+arg_0]
0x140030ec5  mov     r8, rsi
0x140030ec8  mov     r14d, [rbp+57h+var_A0]
0x140030ecc  mov     rcx, r15
0x140030ecf  mov     edx, r14d
0x140030ed2  call    SmartlockerTagProcessToken
0x140030ed7  mov     ebx, eax
0x140030ed9  test    eax, eax
0x140030edb  js      short loc_140030EFF
0x140030edd  mov     rcx, [rbp+57h+arg_8]
0x140030ee1  cmp     r15, rcx
0x140030ee4  jz      loc_140030DB9
0x140030eea  mov     r8, rsi
0x140030eed  mov     edx, r14d
0x140030ef0  call    SmartlockerTagProcessToken
0x140030ef5  mov     ebx, eax
0x140030ef7  test    eax, eax
0x140030ef9  jns     loc_140030DB9
0x140030eff  test    rsi, rsi
0x140030f02  jz      loc_140030D90
0x140030f08  mov     edx, 41746D73h; Tag
0x140030f0d  mov     rcx, rsi; P
0x140030f10  call    cs:__imp_ExFreePoolWithTag
0x140030f17  nop     dword ptr [rax+rax+00h]
0x140030f1c  jmp     loc_140030D90
```
