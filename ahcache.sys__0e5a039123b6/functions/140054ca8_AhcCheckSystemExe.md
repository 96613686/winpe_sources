# AhcCheckSystemExe

- ea: `0x140054ca8`
- end: `0x140054e4c`
- name: `AhcCheckSystemExe`
- size: `420`
- prototype: `__int64 __fastcall(BOOL *, void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140050e94`

## callees

- `0x140004553`
- `0x14003e364`
- `0x140045d44`
- `0x14005498c`
- `0x140054ca8`

## import_xrefs

- `ntoskrnl!ZwQuerySecurityObject` at `0x140054d3e`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140054da1`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140054d3e`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140054da1`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140054ddf`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140054ddf`
- `ntoskrnl!RtlEqualSid` at `0x140054e12`
- `ntoskrnl!RtlEqualSid` at `0x140054e12`

## string_xrefs

- `0x140054df5`: `Failed to get owner security descriptor [%x]`
- `0x140054db7`: `Failed to query security object [%x]`

## pseudocode

```c
__int64 __fastcall AhcCheckSystemExe(BOOL *a1, void *a2, void *a3)
{
  void *Pool2_0; // rsi
  __int64 v7; // r8
  NTSTATUS v8; // ebx
  NTSTATUS v9; // eax
  PSID v10; // rcx
  __int64 v11; // rcx
  NTSTATUS OwnerSecurityDescriptor; // eax
  BOOL v13; // ebx
  PULONG LengthNeeded; // [rsp+20h] [rbp-20h]
  PSID Owner; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+70h] [rbp+30h] BYREF
  ULONG Length; // [rsp+88h] [rbp+48h] BYREF

  *a1 = 0;
  OwnerDefaulted = 0;
  Owner = 0;
  Length = 64;
  Pool2_0 = (void *)ExAllocatePool2_0(256, 64, 1953517633);
  if ( Pool2_0 )
  {
    v9 = ZwQuerySecurityObject(a3, 1u, Pool2_0, Length, &Length);
    v8 = v9;
    if ( v9 != -1073741772 )
    {
      if ( v9 == -1073741789 || Length > 0x40 )
      {
        AslFree(v10, Pool2_0);
        Pool2_0 = (void *)AslAlloc(v11, Length, 1);
        if ( !Pool2_0 )
        {
          v7 = 335;
          goto LABEL_3;
        }
        v8 = ZwQuerySecurityObject(a3, 1u, Pool2_0, Length, &Length);
      }
      if ( v8 < 0 )
      {
        LODWORD(LengthNeeded) = v8;
        AslLogCallPrintf(1, "AhcCheckSystemExe", 347, "Failed to query security object [%x]", LengthNeeded);
LABEL_18:
        AslFree(v10, Pool2_0);
        return (unsigned int)v8;
      }
      OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(Pool2_0, &Owner, &OwnerDefaulted);
      v8 = OwnerSecurityDescriptor;
      if ( OwnerSecurityDescriptor < 0 )
      {
        LODWORD(LengthNeeded) = OwnerSecurityDescriptor;
        AslLogCallPrintf(1, "AhcCheckSystemExe", 356, "Failed to get owner security descriptor [%x]", LengthNeeded);
        goto LABEL_18;
      }
      v10 = Owner;
      v13 = 0;
      if ( Owner )
        v13 = RtlEqualSid(Owner, a2) != 0;
      *a1 = v13;
    }
    v8 = 0;
    goto LABEL_18;
  }
  v7 = 311;
LABEL_3:
  v8 = -1073741801;
  AslLogCallPrintf(1, "AhcCheckSystemExe", v7, "Out of memory");
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140054ca8  mov     [rsp-28h+arg_8], rbx
0x140054cad  mov     [rsp-28h+arg_10], rsi
0x140054cb2  push    rbp
0x140054cb3  push    rdi
0x140054cb4  push    r12
0x140054cb6  push    r14
0x140054cb8  push    r15
0x140054cba  mov     rbp, rsp
0x140054cbd  sub     rsp, 40h
0x140054cc1  mov     eax, 40h ; '@'
0x140054cc6  mov     dword ptr [rcx], 0
0x140054ccc  mov     r15, r8
0x140054ccf  mov     [rbp+OwnerDefaulted], 0
0x140054cd3  mov     r12, rdx
0x140054cd6  mov     [rbp+Owner], 0
0x140054cde  mov     r14, rcx
0x140054ce1  mov     [rbp+Length], eax
0x140054ce4  mov     edx, eax
0x140054ce6  mov     r8d, 74705041h
0x140054cec  mov     ecx, 100h
0x140054cf1  call    ExAllocatePool2_0
0x140054cf6  mov     rsi, rax
0x140054cf9  test    rax, rax
0x140054cfc  jnz     short loc_140054D24
0x140054cfe  mov     r8d, 137h
0x140054d04  lea     ecx, [rax+1]
0x140054d07  lea     rdx, aAhcchecksystem; "AhcCheckSystemExe"
0x140054d0e  mov     ebx, 0C0000017h
0x140054d13  lea     r9, aOutOfMemory; "Out of memory"
0x140054d1a  call    AslLogCallPrintf
0x140054d1f  jmp     loc_140054E30
0x140054d24  mov     r9d, [rbp+Length]; Length
0x140054d28  lea     rax, [rbp+Length]
0x140054d2c  mov     edi, 1
0x140054d31  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x140054d36  mov     edx, edi; SecurityInformation
0x140054d38  mov     r8, rsi; SecurityDescriptor
0x140054d3b  mov     rcx, r15; Handle
0x140054d3e  call    cs:__imp_ZwQuerySecurityObject
0x140054d45  nop     dword ptr [rax+rax+00h]
0x140054d4a  mov     ebx, eax
0x140054d4c  cmp     eax, 0C0000034h
0x140054d51  jz      loc_140054E26
0x140054d57  cmp     eax, 0C0000023h
0x140054d5c  jz      short loc_140054D64
0x140054d5e  cmp     [rbp+Length], 40h ; '@'
0x140054d62  jbe     short loc_140054DAF
0x140054d64  mov     rdx, rsi
0x140054d67  call    AslFree
0x140054d6c  mov     edx, [rbp+Length]
0x140054d6f  mov     r8d, edi
0x140054d72  call    AslAlloc
0x140054d77  mov     rsi, rax
0x140054d7a  test    rax, rax
0x140054d7d  jnz     short loc_140054D8C
0x140054d7f  mov     r8d, 14Fh
0x140054d85  mov     ecx, edi
0x140054d87  jmp     loc_140054D07
0x140054d8c  mov     r9d, [rbp+Length]; Length
0x140054d90  lea     rax, [rbp+Length]
0x140054d94  mov     r8, rsi; SecurityDescriptor
0x140054d97  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x140054d9c  mov     edx, edi; SecurityInformation
0x140054d9e  mov     rcx, r15; Handle
0x140054da1  call    cs:__imp_ZwQuerySecurityObject
0x140054da8  nop     dword ptr [rax+rax+00h]
0x140054dad  mov     ebx, eax
0x140054daf  test    ebx, ebx
0x140054db1  jns     short loc_140054DD4
0x140054db3  mov     dword ptr [rsp+40h+LengthNeeded], ebx
0x140054db7  lea     r9, aFailedToQueryS; "Failed to query security object [%x]"
0x140054dbe  mov     r8d, 15Bh
0x140054dc4  lea     rdx, aAhcchecksystem; "AhcCheckSystemExe"
0x140054dcb  mov     ecx, edi
0x140054dcd  call    AslLogCallPrintf
0x140054dd2  jmp     short loc_140054E28
0x140054dd4  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140054dd8  mov     rcx, rsi; SecurityDescriptor
0x140054ddb  lea     rdx, [rbp+Owner]; Owner
0x140054ddf  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140054de6  nop     dword ptr [rax+rax+00h]
0x140054deb  mov     ebx, eax
0x140054ded  test    eax, eax
0x140054def  jns     short loc_140054E04
0x140054df1  mov     dword ptr [rsp+40h+LengthNeeded], eax
0x140054df5  lea     r9, aFailedToGetOwn; "Failed to get owner security descriptor"...
0x140054dfc  mov     r8d, 164h
0x140054e02  jmp     short loc_140054DC4
0x140054e04  mov     rcx, [rbp+Owner]; Sid1
0x140054e08  xor     ebx, ebx
0x140054e0a  test    rcx, rcx
0x140054e0d  jz      short loc_140054E23
0x140054e0f  mov     rdx, r12; Sid2
0x140054e12  call    cs:__imp_RtlEqualSid
0x140054e19  nop     dword ptr [rax+rax+00h]
0x140054e1e  test    al, al
0x140054e20  cmovnz  ebx, edi
0x140054e23  mov     [r14], ebx
0x140054e26  xor     ebx, ebx
0x140054e28  mov     rdx, rsi
0x140054e2b  call    AslFree
0x140054e30  lea     r11, [rsp+40h+var_s0]
0x140054e35  mov     eax, ebx
0x140054e37  mov     rbx, [r11+38h]
0x140054e3b  mov     rsi, [r11+40h]
0x140054e3f  mov     rsp, r11
0x140054e42  pop     r15
0x140054e44  pop     r14
0x140054e46  pop     r12
0x140054e48  pop     rdi
0x140054e49  pop     rbp
0x140054e4a  retn
```
