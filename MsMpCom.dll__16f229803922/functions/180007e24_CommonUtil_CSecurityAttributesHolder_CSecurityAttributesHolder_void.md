# CommonUtil::CSecurityAttributesHolder::CSecurityAttributesHolder(void *)

- ea: `0x180007e24`
- end: `0x180007ee8`
- name: `??0CSecurityAttributesHolder@CommonUtil@@IEAA@PEAX@Z`
- size: `196`
- prototype: `_QWORD(CommonUtil::CSecurityAttributesHolder *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007fdc`

## callees

- `0x180007c10`
- `0x180007e24`
- `0x1800090e4`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180007e87`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180007e87`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180007e9d`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180007e9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CommonUtil::CSecurityAttributesHolder *__fastcall CommonUtil::CSecurityAttributesHolder::CSecurityAttributesHolder(
        CommonUtil::CSecurityAttributesHolder *this,
        void *a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v8; // eax
  int v9; // edx
  unsigned int LastFailure; // eax
  int v11; // edx
  BOOL bOwnerDefaulted; // [rsp+50h] [rbp+18h] BYREF
  BOOL v13; // [rsp+58h] [rbp+20h] BYREF

  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &CommonUtil::CSecurityAttributesHolder::`vftable';
  v4 = (_QWORD *)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  v13 = 0;
  bOwnerDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(a2, &v13, (PACL *)this + 3, &bOwnerDefaulted) )
  {
    LastFailure = HrGetLastFailure(v5);
    CommonUtil::CommonThrowHr((CommonUtil *)LastFailure, v11);
  }
  if ( !GetSecurityDescriptorOwner(a2, (PSID *)this + 4, &bOwnerDefaulted) )
  {
    v8 = HrGetLastFailure(v6);
    CommonUtil::CommonThrowHr((CommonUtil *)v8, v9);
  }
  *v4 = a2;
  *((_DWORD *)this + 10) = 24;
  *((_QWORD *)this + 6) = v4;
  *((_DWORD *)this + 14) = 0;
  return this;
}

```

## disassembly

```asm
0x180007e24  mov     r11, rsp
0x180007e27  mov     [r11+10h], rbx
0x180007e2b  mov     [r11+8], rcx
0x180007e2f  push    rsi
0x180007e30  push    rdi
0x180007e31  push    r14
0x180007e33  sub     rsp, 20h
0x180007e37  mov     rsi, rdx
0x180007e3a  mov     rbx, rcx
0x180007e3d  mov     dword ptr [rcx+8], 0
0x180007e44  lea     rax, ??_7CSecurityAttributesHolder@CommonUtil@@6B@; const CommonUtil::CSecurityAttributesHolder::`vftable'
0x180007e4b  mov     [rcx], rax
0x180007e4e  lea     rdi, [rcx+10h]
0x180007e52  mov     qword ptr [rdi], 0
0x180007e59  lea     r8, [rcx+18h]; pDacl
0x180007e5d  mov     qword ptr [r8], 0
0x180007e64  mov     qword ptr [rcx+20h], 0
0x180007e6c  mov     [rsp+38h+arg_18], 0
0x180007e74  mov     [rsp+38h+bOwnerDefaulted], 0
0x180007e7c  lea     r9, [r11+18h]; lpbDaclDefaulted
0x180007e80  lea     rdx, [r11+20h]; lpbDaclPresent
0x180007e84  mov     rcx, rsi; pSecurityDescriptor
0x180007e87  call    cs:__imp_GetSecurityDescriptorDacl
0x180007e8d  test    eax, eax
0x180007e8f  jz      short loc_180007EDB
0x180007e91  lea     r8, [rsp+38h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180007e96  lea     rdx, [rbx+20h]; pOwner
0x180007e9a  mov     rcx, rsi; pSecurityDescriptor
0x180007e9d  call    cs:__imp_GetSecurityDescriptorOwner
0x180007ea3  test    eax, eax
0x180007ea5  jz      short loc_180007ECD
0x180007ea7  mov     [rdi], rsi
0x180007eaa  mov     dword ptr [rbx+28h], 18h
0x180007eb1  mov     [rbx+30h], rdi
0x180007eb5  mov     dword ptr [rbx+38h], 0
0x180007ebc  mov     rax, rbx
0x180007ebf  mov     rbx, [rsp+38h+arg_8]
0x180007ec4  add     rsp, 20h
0x180007ec8  pop     r14
0x180007eca  pop     rdi
0x180007ecb  pop     rsi
0x180007ecc  retn
0x180007ecd  call    HrGetLastFailure
0x180007ed2  nop
0x180007ed3  mov     ecx, eax; this
0x180007ed5  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x180007edb  call    HrGetLastFailure
0x180007ee0  mov     ecx, eax; this
0x180007ee2  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
```
