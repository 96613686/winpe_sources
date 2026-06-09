# CPropertyCache::createpropertycache(CCoreADsObject *,CPropertyCache * *)

- ea: `0x180010a74`
- end: `0x180010abb`
- name: `?createpropertycache@CPropertyCache@@SAJPEAVCCoreADsObject@@PEAPEAV1@@Z`
- size: `71`
- prototype: `__int64 __fastcall(struct CCoreADsObject *, struct CPropertyCache **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002b00`
- `0x180004360`

## callees

- `0x1800010b0`
- `0x18000fe60`
- `0x180010a74`

## pseudocode

```c
__int64 __fastcall CPropertyCache::createpropertycache(struct CCoreADsObject *a1, struct CPropertyCache **a2)
{
  CPropertyCache *v4; // rax
  CPropertyCache *v5; // rax

  v4 = (CPropertyCache *)operator new(0x68u);
  if ( !v4 )
    return 2147942414LL;
  v5 = CPropertyCache::CPropertyCache(v4);
  if ( !v5 )
    return 2147942414LL;
  *((_QWORD *)v5 + 2) = a1;
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x180010a74  mov     [rsp+arg_0], rbx
0x180010a79  push    rdi
0x180010a7a  sub     rsp, 20h
0x180010a7e  mov     rdi, rcx
0x180010a81  mov     rbx, rdx
0x180010a84  mov     ecx, 68h ; 'h'; Size
0x180010a89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010a8e  test    rax, rax
0x180010a91  jz      short loc_180010AAB
0x180010a93  mov     rcx, rax; this
0x180010a96  call    ??0CPropertyCache@@QEAA@XZ; CPropertyCache::CPropertyCache(void)
0x180010a9b  test    rax, rax
0x180010a9e  jz      short loc_180010AAB
0x180010aa0  mov     [rax+10h], rdi
0x180010aa4  mov     [rbx], rax
0x180010aa7  xor     eax, eax
0x180010aa9  jmp     short loc_180010AB0
0x180010aab  mov     eax, 8007000Eh
0x180010ab0  mov     rbx, [rsp+28h+arg_0]
0x180010ab5  add     rsp, 20h
0x180010ab9  pop     rdi
0x180010aba  retn
```
