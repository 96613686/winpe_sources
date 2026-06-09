# XPathQueryStringCompiler::ProcessSlashToken(Token *)

- ea: `0x180009ec0`
- end: `0x180009f1c`
- name: `?ProcessSlashToken@XPathQueryStringCompiler@@AEAAJPEAVToken@@@Z`
- size: `92`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct Token *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001078`
- `0x18000637c`
- `0x180007f5c`
- `0x180009ec0`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessSlashToken(XPathQueryStringCompiler *this, struct Token *a2)
{
  __int64 *v2; // rbx
  SingletonIterator *v3; // rax
  SingletonIterator *v4; // rcx

  v2 = (__int64 *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  v3 = (SingletonIterator *)operator new(0x38u);
  if ( v3 )
    v4 = SingletonIterator::SingletonIterator(v3, 1);
  else
    v4 = 0;
  ATL::CComPtrBase<StepCompositionIterator>::Attach(v2, ((unsigned __int64)v4 + 8) & -(__int64)(v4 != 0));
  return *v2 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180009ec0  push    rbx
0x180009ec2  sub     rsp, 20h
0x180009ec6  mov     rbx, [rcx+28h]
0x180009eca  mov     qword ptr [rcx+28h], 0
0x180009ed2  mov     ecx, 38h ; '8'; Size
0x180009ed7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009edc  test    rax, rax
0x180009edf  jz      short loc_180009EF0
0x180009ee1  mov     dl, 1; bool
0x180009ee3  mov     rcx, rax; this
0x180009ee6  call    ??0SingletonIterator@@QEAA@_N@Z; SingletonIterator::SingletonIterator(bool)
0x180009eeb  mov     rcx, rax
0x180009eee  jmp     short loc_180009EF2
0x180009ef0  xor     ecx, ecx
0x180009ef2  lea     rax, [rcx+8]
0x180009ef6  neg     rcx
0x180009ef9  mov     rcx, rbx
0x180009efc  sbb     rdx, rdx
0x180009eff  and     rdx, rax
0x180009f02  call    ?Attach@?$CComPtrBase@VStepCompositionIterator@@@ATL@@QEAAXPEAVStepCompositionIterator@@@Z; ATL::CComPtrBase<StepCompositionIterator>::Attach(StepCompositionIterator *)
0x180009f07  mov     rax, [rbx]
0x180009f0a  neg     rax
0x180009f0d  sbb     eax, eax
0x180009f0f  not     eax
0x180009f11  and     eax, 8007000Eh
0x180009f16  add     rsp, 20h
0x180009f1a  pop     rbx
0x180009f1b  retn
```
