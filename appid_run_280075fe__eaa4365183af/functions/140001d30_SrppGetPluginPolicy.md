# SrppGetPluginPolicy

- ea: `0x140001d30`
- end: `0x140001e43`
- name: `SrppGetPluginPolicy`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140001cb0`
- `0x1400237dc`

## callees

- `0x140001d30`
- `0x140032a50`

## pseudocode

```c
__int64 __fastcall SrppGetPluginPolicy(__int64 a1, _QWORD *a2, __int64 a3, __int64 *a4, _DWORD *a5)
{
  __int64 v8; // rdi
  __int64 v9; // rbx
  unsigned int i; // edx
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rbp
  __int64 v14; // r9
  unsigned int j; // r11d
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int128 v20; // xmm0

  if ( *(int *)(a1 + 208) >= 0 )
  {
    v8 = *(_QWORD *)(a1 + 216);
    if ( v8 )
    {
      v9 = v8 + 28LL * *(unsigned int *)(a3 + 28) + *(unsigned int *)(v8 + 16);
      for ( i = 0; i < *(_DWORD *)(a3 + 32); ++i )
      {
        v11 = *(_QWORD *)v9 - *a2;
        if ( *(_QWORD *)v9 == *a2 )
          v11 = *(_QWORD *)(v9 + 8) - a2[1];
        if ( !v11 )
        {
          v12 = *(_DWORD *)(v9 + 24);
          if ( v12 )
          {
            v13 = *(unsigned int *)(v8 + 24);
            v14 = AiAlloc(32LL * v12);
            if ( !v14 )
              return 3221225495LL;
            for ( j = 0; j < *(_DWORD *)(v9 + 24); *(_OWORD *)(v18 + v14) = v20 )
            {
              v17 = j + *(_DWORD *)(v9 + 20);
              v18 = 32LL * j;
              v19 = j++;
              *(_QWORD *)(v18 + v14 + 24) = *(_QWORD *)(*(_QWORD *)(a1 + 224) + 48 * v17 + 40);
              v20 = *(_OWORD *)(v8 + v13 + 16 * (v19 + *(unsigned int *)(v9 + 20)));
              *(_QWORD *)(v18 + v14 + 16) = 0;
            }
            *a4 = v14;
            *a5 = *(_DWORD *)(v9 + 24);
          }
          return 0;
        }
        v9 += 28;
      }
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x140001d30  push    rbx
0x140001d32  push    rbp
0x140001d33  push    rsi
0x140001d34  push    rdi
0x140001d35  push    r14
0x140001d37  sub     rsp, 20h
0x140001d3b  cmp     dword ptr [rcx+0D0h], 0
0x140001d42  mov     r14, r9
0x140001d45  mov     r11, rdx
0x140001d48  mov     rsi, rcx
0x140001d4b  jl      loc_140001E32
0x140001d51  mov     rdi, [rcx+0D8h]
0x140001d58  test    rdi, rdi
0x140001d5b  jz      loc_140001E32
0x140001d61  mov     eax, [r8+1Ch]
0x140001d65  mov     ebx, [rdi+10h]
0x140001d68  mov     r9d, [r8+20h]
0x140001d6c  imul    rax, 1Ch
0x140001d70  add     rax, rdi
0x140001d73  add     rbx, rax
0x140001d76  xor     edx, edx
0x140001d78  cmp     edx, r9d
0x140001d7b  jnb     loc_140001E32
0x140001d81  mov     rcx, [rbx]
0x140001d84  sub     rcx, [r11]
0x140001d87  jnz     short loc_140001D91
0x140001d89  mov     rcx, [rbx+8]
0x140001d8d  sub     rcx, [r11+8]
0x140001d91  test    rcx, rcx
0x140001d94  jz      short loc_140001D9E
0x140001d96  inc     edx
0x140001d98  add     rbx, 1Ch
0x140001d9c  jmp     short loc_140001D78
0x140001d9e  mov     eax, [rbx+18h]
0x140001da1  test    eax, eax
0x140001da3  jz      loc_140001E2E
0x140001da9  mov     ebp, [rdi+18h]
0x140001dac  mov     ecx, eax
0x140001dae  shl     rcx, 5
0x140001db2  call    AiAlloc
0x140001db7  mov     r9, rax
0x140001dba  test    rax, rax
0x140001dbd  jnz     short loc_140001DC6
0x140001dbf  mov     eax, 0C0000017h
0x140001dc4  jmp     short loc_140001E37
0x140001dc6  xor     r11d, r11d
0x140001dc9  lea     r10, [rdi+rbp]
0x140001dcd  cmp     [rbx+18h], r11d
0x140001dd1  jbe     short loc_140001E21
0x140001dd3  mov     ecx, [rbx+14h]
0x140001dd6  mov     rax, [rsi+0E0h]
0x140001ddd  add     ecx, r11d
0x140001de0  mov     r8d, r11d
0x140001de3  shl     r8, 5
0x140001de7  mov     edx, r11d
0x140001dea  inc     r11d
0x140001ded  lea     rcx, [rcx+rcx*2]
0x140001df1  add     rcx, rcx
0x140001df4  mov     rcx, [rax+rcx*8+28h]
0x140001df9  mov     [r8+r9+18h], rcx
0x140001dfe  mov     eax, [rbx+14h]
0x140001e01  add     rax, rdx
0x140001e04  add     rax, rax
0x140001e07  movups  xmm0, xmmword ptr [r10+rax*8]
0x140001e0c  mov     qword ptr [r8+r9+10h], 0
0x140001e15  movdqu  xmmword ptr [r8+r9], xmm0
0x140001e1b  cmp     r11d, [rbx+18h]
0x140001e1f  jb      short loc_140001DD3
0x140001e21  mov     rax, [rsp+48h+arg_20]
0x140001e26  mov     [r14], r9
0x140001e29  mov     ecx, [rbx+18h]
0x140001e2c  mov     [rax], ecx
0x140001e2e  xor     eax, eax
0x140001e30  jmp     short loc_140001E37
0x140001e32  mov     eax, 0C0000225h
0x140001e37  add     rsp, 20h
0x140001e3b  pop     r14
0x140001e3d  pop     rdi
0x140001e3e  pop     rsi
0x140001e3f  pop     rbp
0x140001e40  pop     rbx
0x140001e41  retn
```
