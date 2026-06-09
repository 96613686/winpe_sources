# AslRegistryGetStringExpand

- ea: `0x140031de4`
- end: `0x140031fc3`
- name: `AslRegistryGetStringExpand`
- size: `479`
- prototype: `__int64 __fastcall(wchar_t **, void *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400479a8`

## callees

- `0x140031de4`
- `0x1400327e0`
- `0x14003e364`
- `0x140040564`
- `0x140043274`
- `0x140045d44`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!wcschr` at `0x140031e2a`
- `ntoskrnl!wcschr` at `0x140031e2a`

## string_xrefs

- `0x140031e6d`: `AslRegistryGetStringExpand`
- `0x140031eb6`: `AslRegistryGetStringExpand`
- `0x140031f70`: `AslRegistryGetStringExpand`

## pseudocode

```c
__int64 __fastcall AslRegistryGetStringExpand(wchar_t **a1, void *a2, const WCHAR *a3, __int64 a4)
{
  void *v5; // rdi
  __int64 v7; // rcx
  int String; // ebx
  int ProcessWowInfo; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int16 v12; // r15
  __int16 v13; // r12
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v17; // [rsp+28h] [rbp-38h]
  int v18; // [rsp+30h] [rbp-30h]
  __int16 v19[2]; // [rsp+40h] [rbp-20h] BYREF
  __int16 v20; // [rsp+44h] [rbp-1Ch] BYREF
  wchar_t *Str; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-10h] BYREF

  v5 = 0;
  v19[0] = -1;
  Str = 0;
  v20 = -1;
  String = AslRegistryGetString(&Str, a2, a3);
  if ( String < 0 )
    goto LABEL_16;
  if ( !wcschr(Str, 0x25u) )
  {
    String = 0;
    *a1 = Str;
    return (unsigned int)String;
  }
  ProcessWowInfo = AslEnvGetProcessWowInfo(&v20, v19);
  String = ProcessWowInfo;
  if ( ProcessWowInfo >= 0 )
  {
    v22[0] = 260;
    v5 = (void *)AslAlloc(v10, 520, 1);
    if ( !v5 )
    {
      v11 = 1476;
LABEL_8:
      AslLogCallPrintf(1, "AslRegistryGetStringExpand", v11, "Out of memory");
      String = -1073741801;
      goto LABEL_16;
    }
    v12 = v19[0];
    v13 = v20;
    String = AslEnvExpandStrings2(a4, Str, v5, 260, v22, v20, v19[0]);
    if ( String == -1073741789 )
    {
      AslFree(v7, v5);
      v14 = v22[0];
      v5 = (void *)AslAlloc(v15, 2LL * v22[0], 1);
      if ( !v5 )
      {
        v11 = 1494;
        goto LABEL_8;
      }
      LOWORD(v18) = v12;
      LOWORD(v17) = v13;
      String = AslEnvExpandStrings2(a4, Str, v5, v14, v22, v17, v18);
    }
    if ( String >= 0 )
    {
      *a1 = (wchar_t *)v5;
      v5 = 0;
      String = 0;
    }
    else
    {
      LODWORD(v17) = String;
      AslLogCallPrintf(
        1,
        "AslRegistryGetStringExpand",
        1509,
        "AslEnvExpandStrings2 failed to expand strings for %ws [%x]",
        Str,
        v17);
    }
    goto LABEL_16;
  }
  AslLogCallPrintf(1, "AslRegistryGetStringExpand", 1464, "AslEnvGetProcessWowInfo failed [%x]", ProcessWowInfo);
LABEL_16:
  if ( Str )
    AslFree(v7, Str);
  if ( v5 )
    AslFree(v7, v5);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x140031de4  push    rbp
0x140031de6  push    rbx
0x140031de7  push    rdi
0x140031de8  push    r12
0x140031dea  push    r13
0x140031dec  push    r14
0x140031dee  push    r15
0x140031df0  mov     rbp, rsp
0x140031df3  sub     rsp, 60h
0x140031df7  mov     eax, 0FFFFh
0x140031dfc  mov     r14, rcx
0x140031dff  xor     edi, edi
0x140031e01  mov     [rbp+var_20], ax
0x140031e05  lea     rcx, [rbp+Str]
0x140031e09  mov     [rbp+Str], rdi
0x140031e0d  mov     [rbp+var_1C], ax
0x140031e11  mov     r13, r9
0x140031e14  call    AslRegistryGetString
0x140031e19  mov     ebx, eax
0x140031e1b  test    eax, eax
0x140031e1d  js      loc_140031F95
0x140031e23  mov     rcx, [rbp+Str]; Str
0x140031e27  lea     edx, [rdi+25h]; Ch
0x140031e2a  call    cs:__imp_wcschr
0x140031e31  nop     dword ptr [rax+rax+00h]
0x140031e36  test    rax, rax
0x140031e39  jnz     short loc_140031E49
0x140031e3b  mov     rax, [rbp+Str]
0x140031e3f  xor     ebx, ebx
0x140031e41  mov     [r14], rax
0x140031e44  jmp     loc_140031FB0
0x140031e49  lea     rdx, [rbp+var_20]
0x140031e4d  lea     rcx, [rbp+var_1C]
0x140031e51  call    AslEnvGetProcessWowInfo
0x140031e56  mov     ebx, eax
0x140031e58  test    eax, eax
0x140031e5a  jns     short loc_140031E83
0x140031e5c  lea     r9, aAslenvgetproce_1; "AslEnvGetProcessWowInfo failed [%x]"
0x140031e63  mov     dword ptr [rsp+60h+var_40], eax
0x140031e67  mov     r8d, 5B8h
0x140031e6d  lea     rdx, aAslregistryget_8; "AslRegistryGetStringExpand"
0x140031e74  mov     ecx, 1
0x140031e79  call    AslLogCallPrintf
0x140031e7e  jmp     loc_140031F95
0x140031e83  mov     ebx, 104h
0x140031e88  mov     edx, 208h
0x140031e8d  mov     r8d, 1
0x140031e93  mov     [rbp+var_10], rbx
0x140031e97  call    AslAlloc
0x140031e9c  mov     rdi, rax
0x140031e9f  test    rax, rax
0x140031ea2  jnz     short loc_140031ECC
0x140031ea4  mov     r8d, 5C4h
0x140031eaa  lea     r9, aOutOfMemory; "Out of memory"
0x140031eb1  mov     ecx, 1
0x140031eb6  lea     rdx, aAslregistryget_8; "AslRegistryGetStringExpand"
0x140031ebd  call    AslLogCallPrintf
0x140031ec2  mov     ebx, 0C0000017h
0x140031ec7  jmp     loc_140031F95
0x140031ecc  movzx   r15d, [rbp+var_20]
0x140031ed1  lea     rax, [rbp+var_10]
0x140031ed5  movzx   r12d, [rbp+var_1C]
0x140031eda  mov     r9, rbx
0x140031edd  mov     rdx, [rbp+Str]
0x140031ee1  mov     r8, rdi
0x140031ee4  mov     word ptr [rsp+60h+var_30], r15w
0x140031eea  mov     rcx, r13
0x140031eed  mov     word ptr [rsp+60h+var_38], r12w
0x140031ef3  mov     [rsp+60h+var_40], rax
0x140031ef8  call    AslEnvExpandStrings2
0x140031efd  mov     ebx, eax
0x140031eff  cmp     eax, 0C0000023h
0x140031f04  jnz     short loc_140031F5D
0x140031f06  mov     rdx, rdi
0x140031f09  call    AslFree
0x140031f0e  mov     rbx, [rbp+var_10]
0x140031f12  mov     r8d, 1
0x140031f18  lea     rdx, [rbx+rbx]
0x140031f1c  call    AslAlloc
0x140031f21  mov     rdi, rax
0x140031f24  test    rax, rax
0x140031f27  jnz     short loc_140031F34
0x140031f29  mov     r8d, 5D6h
0x140031f2f  jmp     loc_140031EAA
0x140031f34  mov     rdx, [rbp+Str]
0x140031f38  lea     rax, [rbp+var_10]
0x140031f3c  mov     word ptr [rsp+60h+var_30], r15w
0x140031f42  mov     r9, rbx
0x140031f45  mov     word ptr [rsp+60h+var_38], r12w
0x140031f4b  mov     r8, rdi
0x140031f4e  mov     rcx, r13
0x140031f51  mov     [rsp+60h+var_40], rax
0x140031f56  call    AslEnvExpandStrings2
0x140031f5b  mov     ebx, eax
0x140031f5d  test    ebx, ebx
0x140031f5f  jns     short loc_140031F8E
0x140031f61  mov     rax, [rbp+Str]
0x140031f65  lea     r9, aAslenvexpandst_1; "AslEnvExpandStrings2 failed to expand s"...
0x140031f6c  mov     dword ptr [rsp+60h+var_38], ebx
0x140031f70  lea     rdx, aAslregistryget_8; "AslRegistryGetStringExpand"
0x140031f77  mov     r8d, 5E5h
0x140031f7d  mov     [rsp+60h+var_40], rax
0x140031f82  mov     ecx, 1
0x140031f87  call    AslLogCallPrintf
0x140031f8c  jmp     short loc_140031F95
0x140031f8e  mov     [r14], rdi
0x140031f91  xor     edi, edi
0x140031f93  xor     ebx, ebx
0x140031f95  mov     rdx, [rbp+Str]
0x140031f99  test    rdx, rdx
0x140031f9c  jz      short loc_140031FA3
0x140031f9e  call    AslFree
0x140031fa3  test    rdi, rdi
0x140031fa6  jz      short loc_140031FB0
0x140031fa8  mov     rdx, rdi
0x140031fab  call    AslFree
0x140031fb0  mov     eax, ebx
0x140031fb2  add     rsp, 60h
0x140031fb6  pop     r15
0x140031fb8  pop     r14
0x140031fba  pop     r13
0x140031fbc  pop     r12
0x140031fbe  pop     rdi
0x140031fbf  pop     rbx
0x140031fc0  pop     rbp
0x140031fc1  retn
```
