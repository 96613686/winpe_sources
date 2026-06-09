# sub_18000DDFC

- ea: `0x18000ddfc`
- end: `0x18000deb9`
- name: `sub_18000DDFC`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d6b0`

## callees

- `0x18000cc68`
- `0x18000ddfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000de56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000de56`

## pseudocode

```c
__int64 sub_18000DDFC()
{
  __int64 v0; // rdi
  __int64 i; // rbx
  __int64 v2; // rcx
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v0 = qword_180084410;
  i = 0;
  if ( qword_180084410 )
  {
    if ( !*(_QWORD *)(qword_180084410 + 8) )
    {
      v2 = *(_QWORD *)qword_180084410;
      v6 = 0;
      if ( (int)sub_18000CC68(v2, &v6) >= 0 && !*(_QWORD *)(v0 + 8) )
        *(_QWORD *)(v0 + 8) = v6;
    }
    v3 = (*(_QWORD *)(v0 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v0 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v3 + 4;
          return i;
        }
      }
    }
  }
  return i;
}

```

## disassembly

```asm
0x18000ddfc  mov     [rsp+arg_0], rbx
0x18000de01  push    rdi
0x18000de02  sub     rsp, 20h
0x18000de06  mov     rdi, cs:qword_180084410
0x18000de0d  xor     ebx, ebx
0x18000de0f  test    rdi, rdi
0x18000de12  jz      loc_18000DEAB
0x18000de18  cmp     [rdi+8], rbx
0x18000de1c  jnz     short loc_18000DE43
0x18000de1e  mov     rcx, [rdi]
0x18000de21  lea     rdx, [rsp+28h+arg_8]
0x18000de26  mov     [rsp+28h+arg_8], rbx
0x18000de2b  call    sub_18000CC68
0x18000de30  test    eax, eax
0x18000de32  js      short loc_18000DE43
0x18000de34  cmp     [rdi+8], rbx
0x18000de38  jnz     short loc_18000DE43
0x18000de3a  mov     rax, [rsp+28h+arg_8]
0x18000de3f  mov     [rdi+8], rax
0x18000de43  mov     rax, [rdi+8]
0x18000de47  lea     rcx, [rax+20h]
0x18000de4b  neg     rax
0x18000de4e  sbb     rdi, rdi
0x18000de51  and     rdi, rcx
0x18000de54  jz      short loc_18000DEAB
0x18000de56  call    cs:GetCurrentThreadId
0x18000de5c  mov     r8d, eax
0x18000de5f  mov     r9d, eax
0x18000de62  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000de6c  shr     r8, 2
0x18000de70  mul     r8
0x18000de73  shr     rdx, 3
0x18000de77  lea     rcx, [rdx+rdx*4]
0x18000de7b  add     rcx, rcx
0x18000de7e  sub     r8, rcx
0x18000de81  mov     rbx, [rdi+r8*8+8]
0x18000de86  test    rbx, rbx
0x18000de89  jz      short loc_18000DEAB
0x18000de8b  cmp     [rbx], r9d
0x18000de8e  jz      short loc_18000DE96
0x18000de90  mov     rbx, [rbx+8]
0x18000de94  jmp     short loc_18000DE86
0x18000de96  add     rbx, 10h
0x18000de9a  jz      short loc_18000DEAB
0x18000de9c  cmp     qword ptr [rbx+8], 0
0x18000dea1  jnz     short loc_18000DEAB
0x18000dea3  lea     rax, [rdi+4]
0x18000dea7  mov     [rbx+8], rax
0x18000deab  mov     rax, rbx
0x18000deae  mov     rbx, [rsp+28h+arg_0]
0x18000deb3  add     rsp, 20h
0x18000deb7  pop     rdi
0x18000deb8  retn
```
