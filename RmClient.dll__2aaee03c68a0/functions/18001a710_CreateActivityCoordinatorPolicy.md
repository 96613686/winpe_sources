# CreateActivityCoordinatorPolicy

- ea: `0x18001a710`
- end: `0x18001a77c`
- name: `CreateActivityCoordinatorPolicy`
- size: `108`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180001f10`
- `0x18001a710`

## pseudocode

```c
__int64 __fastcall CreateActivityCoordinatorPolicy(unsigned int a1, _QWORD *a2)
{
  __int64 v2; // rdi
  _OWORD *v4; // rax
  _OWORD *v5; // r8
  __int64 result; // rax

  v2 = (int)a1;
  *a2 = 0;
  if ( a1 > 3 )
    return 2147942487LL;
  v4 = MIDL_user_allocate(0x20u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  *v4 = *((_OWORD *)&ActivityCoordinatorPolicyTemplatesTable + 2 * v2);
  result = 0;
  v5[1] = *((_OWORD *)&ActivityCoordinatorPolicyTemplatesTable + 2 * v2 + 1);
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x18001a710  mov     [rsp+arg_0], rbx
0x18001a715  push    rdi
0x18001a716  sub     rsp, 20h
0x18001a71a  movsxd  rdi, ecx
0x18001a71d  mov     rbx, rdx
0x18001a720  mov     qword ptr [rdx], 0
0x18001a727  cmp     edi, 3
0x18001a72a  ja      short loc_18001A76C
0x18001a72c  mov     ecx, 20h ; ' '; size
0x18001a731  call    MIDL_user_allocate
0x18001a736  mov     r8, rax
0x18001a739  test    rax, rax
0x18001a73c  jnz     short loc_18001A745
0x18001a73e  mov     eax, 8007000Eh
0x18001a743  jmp     short loc_18001A771
0x18001a745  lea     rcx, ?ActivityCoordinatorPolicyTemplatesTable@@3PAU_ACTIVITY_COORDINATOR_RESOURCE_CONDITIONS@@A; _ACTIVITY_COORDINATOR_RESOURCE_CONDITIONS near * ActivityCoordinatorPolicyTemplatesTable
0x18001a74c  mov     rax, rdi
0x18001a74f  shl     rax, 5
0x18001a753  movups  xmm0, xmmword ptr [rax+rcx]
0x18001a757  movups  xmmword ptr [r8], xmm0
0x18001a75b  movups  xmm1, xmmword ptr [rax+rcx+10h]
0x18001a760  xor     eax, eax
0x18001a762  movups  xmmword ptr [r8+10h], xmm1
0x18001a767  mov     [rbx], r8
0x18001a76a  jmp     short loc_18001A771
0x18001a76c  mov     eax, 80070057h
0x18001a771  mov     rbx, [rsp+28h+arg_0]
0x18001a776  add     rsp, 20h
0x18001a77a  pop     rdi
0x18001a77b  retn
```
