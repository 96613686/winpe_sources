# COrientationChecker::COrientationScanner::ProcessTheJunction(void)

- ea: `0x100450940`
- end: `0x1004509a8`
- name: `?ProcessTheJunction@COrientationScanner@COrientationChecker@@UEAAJXZ`
- size: `104`
- prototype: `__int64 __fastcall(COrientationChecker::COrientationScanner *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x100441c90`
- `0x100450940`

## pseudocode

```c
__int64 __fastcall COrientationChecker::COrientationScanner::ProcessTheJunction(
        COrientationChecker::COrientationScanner *this)
{
  __int64 v2; // rax
  unsigned int v3; // edx

  CScanner::ClassifyFillOnly(this);
  v2 = *((_QWORD *)this + 40);
  if ( v2 )
  {
    v3 = *(unsigned __int16 *)(v2 + 72);
    if ( (v3 & 0x20) != 0 )
    {
      *((_DWORD *)this + 130) = 3;
      return 0;
    }
    *((_DWORD *)this + 130) = ((((unsigned __int8)(v3 >> 4)
                               ^ (unsigned __int8)((unsigned __int16)(v3 ^ ((unsigned __int16)v3 >> 4)) >> 8))
                              & 1) == 0)
                            + 1;
    *((_BYTE *)this + 513) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x100450940  push    rbx
0x100450942  sub     rsp, 20h
0x100450946  mov     rbx, rcx
0x100450949  call    ?ClassifyFillOnly@CScanner@@QEAAXXZ; CScanner::ClassifyFillOnly(void)
0x10045094e  mov     rax, [rbx+140h]
0x100450955  test    rax, rax
0x100450958  jz      short loc_1004509A0
0x10045095a  movzx   edx, word ptr [rax+48h]
0x10045095e  movzx   eax, dl
0x100450961  shr     al, 5
0x100450964  test    al, 1
0x100450966  jz      short loc_10045097A
0x100450968  mov     dword ptr [rbx+208h], 3
0x100450972  xor     eax, eax
0x100450974  add     rsp, 20h
0x100450978  pop     rbx
0x100450979  retn
0x10045097a  movzx   eax, dx
0x10045097d  shr     edx, 4
0x100450980  mov     ecx, eax
0x100450982  shr     ecx, 4
0x100450985  xor     ecx, eax
0x100450987  shr     ecx, 8
0x10045098a  xor     ecx, edx
0x10045098c  not     ecx
0x10045098e  and     ecx, 1
0x100450991  inc     ecx
0x100450993  mov     [rbx+208h], ecx
0x100450999  mov     byte ptr [rbx+201h], 1
0x1004509a0  xor     eax, eax
0x1004509a2  add     rsp, 20h
0x1004509a6  pop     rbx
0x1004509a7  retn
```
