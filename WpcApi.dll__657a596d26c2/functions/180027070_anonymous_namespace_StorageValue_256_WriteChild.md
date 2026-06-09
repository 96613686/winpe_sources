# _anonymous_namespace_::StorageValue_256_::WriteChild

- ea: `0x180027070`
- end: `0x180027111`
- name: `_anonymous_namespace_::StorageValue_256_::WriteChild`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800032c4`
- `0x180003d20`
- `0x1800195c4`
- `0x180024edc`
- `0x180027070`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall anonymous_namespace_::StorageValue_256_::WriteChild(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // r8
  _QWORD *v6; // rax
  _BYTE pExceptionObject[56]; // [rsp+40h] [rbp-38h] BYREF

  v4 = operator new(0x38u);
  v5 = a1 + 2;
  if ( a1[5] > 7u )
    v5 = (_QWORD *)*v5;
  v6 = RegistryT<256>::RegistryT<256>(v4, a1[6], (int)v5);
  *a2 = v6;
  if ( !v6 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return a2;
}

```

## disassembly

```asm
0x180027070  mov     [rsp+arg_0], rbx
0x180027075  mov     [rsp+arg_8], rdx
0x18002707a  push    rdi
0x18002707b  sub     rsp, 70h
0x18002707f  mov     rbx, rdx
0x180027082  mov     rdi, rcx
0x180027085  mov     ecx, 38h ; '8'; Size
0x18002708a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002708f  mov     [rsp+78h+arg_18], rax
0x180027097  lea     r8, [rdi+10h]
0x18002709b  cmp     qword ptr [r8+18h], 7
0x1800270a0  jbe     short loc_1800270A5
0x1800270a2  mov     r8, [r8]
0x1800270a5  mov     rdx, [rdi+30h]
0x1800270a9  mov     rcx, rax
0x1800270ac  call    ??0?$RegistryT@$0BAA@@@QEAA@PEAUHKEY__@@PEBG_NPEAU_SECURITY_ATTRIBUTES@@@Z; RegistryT<256>::RegistryT<256>(HKEY__ *,ushort const *,bool,_SECURITY_ATTRIBUTES *)
0x1800270b1  nop
0x1800270b2  mov     [rsp+78h+arg_18], 0
0x1800270be  lea     rcx, [rsp+78h+arg_10]
0x1800270c6  mov     [rsp+78h+var_40], rcx
0x1800270cb  mov     [rsp+78h+arg_10], 0
0x1800270d7  mov     [rbx], rax
0x1800270da  test    rax, rax
0x1800270dd  jz      short loc_1800270F0
0x1800270df  mov     rax, rbx
0x1800270e2  mov     rbx, [rsp+78h+arg_0]
0x1800270ea  add     rsp, 70h
0x1800270ee  pop     rdi
0x1800270ef  retn
0x1800270f0  mov     edx, 8000FFFFh; int
0x1800270f5  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800270fa  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800270ff  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180027106  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18002710b  call    _CxxThrowException_0
```
