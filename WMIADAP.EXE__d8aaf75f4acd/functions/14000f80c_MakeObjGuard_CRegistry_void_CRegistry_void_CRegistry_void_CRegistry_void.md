# MakeObjGuard<CRegistry,void (CRegistry::*)(void)>(CRegistry &,void (CRegistry::*)(void))

- ea: `0x14000f80c`
- end: `0x14000f84b`
- name: `??$MakeObjGuard@VCRegistry@@P81@EAAXXZ@@YA?AV?$ObjScopeGuardImpl0@VCRegistry@@P81@EAAXXZ@@AEAVCRegistry@@P81@EAAXXZ@Z`
- size: `63`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x14000f91c`

## pseudocode

```c
__int64 __fastcall MakeObjGuard<CRegistry,void (CRegistry::*)(void)>(__int64 a1, __int64 a2)
{
  *(_BYTE *)a1 = 0;
  *(_QWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 16) = CRegistry::Close;
  return a1;
}

```

## disassembly

```asm
0x14000f80c  mov     [rsp+arg_0], rcx
0x14000f811  sub     rsp, 18h
0x14000f815  mov     [rsp+18h+var_18], 0
0x14000f81c  mov     byte ptr [rcx], 0
0x14000f81f  mov     [rcx+8], rdx
0x14000f823  lea     rax, ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x14000f82a  mov     [rcx+10h], rax
0x14000f82e  mov     eax, 2
0x14000f833  mov     [rsp+18h+var_18], eax
0x14000f836  and     eax, 0FFFFFFFDh
0x14000f839  mov     [rsp+18h+var_18], eax
0x14000f83c  or      eax, 1
0x14000f83f  mov     [rsp+18h+var_18], eax
0x14000f842  mov     rax, rcx
0x14000f845  add     rsp, 18h
0x14000f849  retn
```
