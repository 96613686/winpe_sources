# _dynamic_initializer_for__Com::Module::FakeModule__

- ea: `0x180002620`
- end: `0x1800026ae`
- name: `_dynamic_initializer_for__Com::Module::FakeModule__`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x1800032c4`
- `0x1800036b8`
- `0x180003d20`
- `0x1800195c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int dynamic_initializer_for__Com::Module::FakeModule__()
{
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  _DWORD *v2; // [rsp+70h] [rbp+8h]

  v2 = operator new(0x20u);
  *(_OWORD *)v2 = 0;
  v2[2] = 1;
  v2[3] = 1;
  *(_QWORD *)v2 = &std::_Ref_count_obj2<Com::Module>::`vftable';
  *((_QWORD *)v2 + 3) = 0;
  *((_QWORD *)v2 + 2) = &Com::Module::`vftable';
  Com::Module::FakeModule = (__int64)(v2 + 4);
  qword_18004A6F0 = (__int64)v2;
  if ( v2 == (_DWORD *)-16LL )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Com::Module::FakeModule__);
}

```

## disassembly

```asm
0x180002620  sub     rsp, 68h
0x180002624  mov     ecx, 20h ; ' '; Size
0x180002629  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000262e  mov     [rsp+68h+arg_0], rax
0x180002633  xorps   xmm0, xmm0
0x180002636  movups  xmmword ptr [rax], xmm0
0x180002639  mov     ecx, 1
0x18000263e  mov     [rax+8], ecx
0x180002641  mov     [rax+0Ch], ecx
0x180002644  lea     rcx, ??_7?$_Ref_count_obj2@VModule@Com@@@std@@6B@; const std::_Ref_count_obj2<Com::Module>::`vftable'
0x18000264b  mov     [rax], rcx
0x18000264e  lea     rcx, [rax+10h]
0x180002652  mov     qword ptr [rcx+8], 0
0x18000265a  lea     rdx, ??_7Module@Com@@6B@; const Com::Module::`vftable'
0x180002661  mov     [rcx], rdx
0x180002664  mov     cs:?FakeModule@Module@Com@@2V?$shared_ref@VModule@Com@@@stdext@@B, rcx; stdext::shared_ref<Com::Module> const Com::Module::FakeModule
0x18000266b  mov     cs:qword_18004A6F0, rax
0x180002672  movdqu  [rsp+68h+var_48], xmm0
0x180002678  test    rcx, rcx
0x18000267b  jz      short loc_18000268D
0x18000267d  lea     rcx, _dynamic_atexit_destructor_for__Com__Module__FakeModule__
0x180002684  add     rsp, 68h
0x180002688  jmp     atexit
0x18000268d  mov     edx, 8000FFFFh; int
0x180002692  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180002697  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18000269c  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800026a3  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800026a8  call    _CxxThrowException_0
```
