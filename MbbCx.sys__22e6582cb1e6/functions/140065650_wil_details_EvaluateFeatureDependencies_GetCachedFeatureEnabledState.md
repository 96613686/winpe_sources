# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140065650`
- end: `0x140065721`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140065564`
- `0x140065650`

## callees

- `0x140065650`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2)
{
  unsigned __int32 v2; // esi
  int v4; // ebx
  __int64 *v5; // rdi
  __int64 v6; // rax
  unsigned __int32 v7; // eax
  unsigned int v8; // r8d
  __int64 v10; // [rsp+50h] [rbp+8h]

  v2 = *a1;
  v10 = *(unsigned int *)a1;
  if ( (*a1 & 0x200) != 0 )
  {
    HIDWORD(v10) = 0;
    v4 = (v2 >> 6) & 1;
    if ( v4 )
    {
      v5 = *(__int64 **)(a2 + 32);
      if ( v5 )
      {
        while ( 1 )
        {
          v6 = *v5;
          if ( !*v5 )
            break;
          if ( *(_BYTE *)(v6 + 30) || *(_BYTE *)(v6 + 29) )
          {
            if ( !*(_BYTE *)(v6 + 31) )
            {
              v4 = 0;
              goto LABEL_12;
            }
            v4 = 1;
            ++v5;
          }
          else
          {
            v4 = (wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_QWORD *)v6, *v5++) & 1) != 0;
            if ( !v4 )
              goto LABEL_12;
          }
        }
      }
    }
    do
    {
LABEL_12:
      v7 = v2;
      v8 = v4 & 0xFFFFFFCF | v2 & 0xFFFFFFCE;
      if ( (v2 & 1) == v4 )
        v8 = v4 | v2 & 0xFFFFFFFE;
      LODWORD(v10) = v8 & 0xFFFFFDFF;
      v2 = _InterlockedCompareExchange(a1, v8 & 0xFFFFFDFF, v2);
    }
    while ( v7 != v2 );
  }
  return v10;
}

```

## disassembly

```asm
0x140065650  push    rbx
0x140065652  push    rsi
0x140065653  push    rdi
0x140065654  push    r14
0x140065656  sub     rsp, 28h
0x14006565a  mov     esi, [rcx]
0x14006565c  mov     r14, rcx
0x14006565f  mov     [rsp+48h+arg_0], 0
0x140065668  mov     dword ptr [rsp+48h+arg_0], esi
0x14006566c  bt      esi, 9
0x140065670  jnb     loc_140065711
0x140065676  mov     ebx, esi
0x140065678  mov     [rsp+48h+arg_0], 0
0x140065681  shr     ebx, 6
0x140065684  and     ebx, 1
0x140065687  jz      short loc_1400656E3
0x140065689  mov     rdi, [rdx+20h]
0x14006568d  test    rdi, rdi
0x140065690  jz      short loc_1400656E3
0x140065692  mov     rax, [rdi]
0x140065695  test    rax, rax
0x140065698  jz      short loc_1400656E3
0x14006569a  cmp     byte ptr [rax+1Eh], 0
0x14006569e  jnz     short loc_1400656CC
0x1400656a0  cmp     byte ptr [rax+1Dh], 0
0x1400656a4  jnz     short loc_1400656CC
0x1400656a6  mov     rcx, [rax]
0x1400656a9  mov     rdx, rax
0x1400656ac  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400656b1  test    ebx, ebx
0x1400656b3  jz      short loc_1400656C0
0x1400656b5  test    al, 1
0x1400656b7  jz      short loc_1400656C0
0x1400656b9  mov     ebx, 1
0x1400656be  jmp     short loc_1400656C2
0x1400656c0  xor     ebx, ebx
0x1400656c2  add     rdi, 8
0x1400656c6  test    ebx, ebx
0x1400656c8  jnz     short loc_140065692
0x1400656ca  jmp     short loc_1400656E3
0x1400656cc  test    ebx, ebx
0x1400656ce  jz      short loc_1400656E1
0x1400656d0  cmp     byte ptr [rax+1Fh], 0
0x1400656d4  jz      short loc_1400656E1
0x1400656d6  mov     ebx, 1
0x1400656db  add     rdi, 8
0x1400656df  jmp     short loc_140065692
0x1400656e1  xor     ebx, ebx
0x1400656e3  mov     edx, esi
0x1400656e5  mov     ecx, esi
0x1400656e7  and     edx, 0FFFFFFFEh
0x1400656ea  and     ecx, 1
0x1400656ed  or      edx, ebx
0x1400656ef  mov     eax, esi
0x1400656f1  mov     r8d, edx
0x1400656f4  and     r8d, 0FFFFFFCFh
0x1400656f8  cmp     ecx, ebx
0x1400656fa  cmovz   r8d, edx
0x1400656fe  btr     r8d, 9
0x140065703  mov     dword ptr [rsp+48h+arg_0], r8d
0x140065708  lock cmpxchg [r14], r8d
0x14006570d  mov     esi, eax
0x14006570f  jnz     short loc_1400656E3
0x140065711  mov     rax, [rsp+48h+arg_0]
0x140065716  add     rsp, 28h
0x14006571a  pop     r14
0x14006571c  pop     rdi
0x14006571d  pop     rsi
0x14006571e  pop     rbx
0x14006571f  retn
```
