# CFileObject::CompareTo(UnBCL::Object const *)

- ea: `0x180027314`
- end: `0x18002738c`
- name: `?CompareTo@CFileObject@@UEBAHPEBVObject@UnBCL@@@Z`
- size: `120`
- prototype: `int __fastcall(CFileObject *this, const struct UnBCL::Object *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180027300`

## callees

- `0x180027314`
- `0x1800502a7`

## import_xrefs

- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18002737b`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18002737b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18002735c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180027369`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18002735c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180027369`

## pseudocode

```c
int __fastcall CFileObject::CompareTo(CFileObject *this, const struct UnBCL::Object *a2)
{
  __int64 v4; // rax
  const struct UnBCL::String *P; // rbx
  const struct UnBCL::String *v6; // rax

  if ( !a2 )
    return 1;
  v4 = _RTDynamicCast_0(a2, 0, &UnBCL::Object `RTTI Type Descriptor', &CFileObject `RTTI Type Descriptor', 0);
  if ( !v4 )
    return -1;
  P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v4 + 24);
  v6 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this - 104);
  return UnBCL::String::Compare(v6, P, 1);
}

```

## disassembly

```asm
0x180027314  mov     [rsp+arg_0], rbx
0x180027319  push    rdi
0x18002731a  sub     rsp, 30h
0x18002731e  mov     rax, rdx
0x180027321  mov     rdi, rcx
0x180027324  test    rdx, rdx
0x180027327  jnz     short loc_18002732E
0x180027329  lea     eax, [rdx+1]
0x18002732c  jmp     short loc_180027381
0x18002732e  lea     r9, ??_R0?AVCFileObject@@@8; CFileObject `RTTI Type Descriptor'
0x180027335  mov     [rsp+38h+var_18], 0
0x18002733d  lea     r8, ??_R0?AVObject@UnBCL@@@8; UnBCL::Object `RTTI Type Descriptor'
0x180027344  xor     edx, edx
0x180027346  mov     rcx, rax
0x180027349  call    __RTDynamicCast_0
0x18002734e  test    rax, rax
0x180027351  jnz     short loc_180027358
0x180027353  or      eax, 0FFFFFFFFh
0x180027356  jmp     short loc_180027381
0x180027358  lea     rcx, [rax+18h]
0x18002735c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180027362  lea     rcx, [rdi-68h]
0x180027366  mov     rbx, rax
0x180027369  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18002736f  mov     r8d, 1
0x180027375  mov     rdx, rbx
0x180027378  mov     rcx, rax
0x18002737b  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBV12@0H@Z; UnBCL::String::Compare(UnBCL::String const *,UnBCL::String const *,int)
0x180027381  mov     rbx, [rsp+38h+arg_0]
0x180027386  add     rsp, 30h
0x18002738a  pop     rdi
0x18002738b  retn
```
