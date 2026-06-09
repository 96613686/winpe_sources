# VinitMainKeywordTableIndexes

- ea: `0x180036de0`
- end: `0x180036fc0`
- name: `VinitMainKeywordTableIndexes`
- size: `480`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036c84`

## callees

- `0x180036de0`
- `0x180076624`

## string_xrefs

- `0x180036eea`: `Command`
- `0x180036f61`: `MemConfigKB`
- `0x180036f7c`: `MemConfigMB`
- `0x180036ea0`: `MemoryConfigMB`
- `0x180036e82`: `MemoryConfigKB`

## pseudocode

```c
void __fastcall VinitMainKeywordTableIndexes(__int64 a1)
{
  __int64 v1; // r15
  __int64 v3; // rbp
  unsigned int v4; // ebx
  __int64 v5; // rcx
  const char *v6; // rsi
  char *v7; // rsi
  int v8; // edx
  int v9; // edx

  v1 = *(_QWORD *)(a1 + 648);
  v3 = 0;
  do
  {
    v4 = *(_DWORD *)(v1 + 8 * v3);
    if ( v4 < *(_DWORD *)(v1 + 8 * v3 + 4) )
    {
      v5 = v1;
      do
      {
        if ( (_DWORD)v3 )
        {
          if ( (_DWORD)v3 == 3 )
          {
            v6 = (&mMainKeywordTable)[4 * v4];
            if ( !strcmp_0(v6, "Name") )
            {
              *(_DWORD *)(a1 + 2552) = v4;
            }
            else if ( !strcmp_0(v6, "MemoryConfigKB") )
            {
              *(_DWORD *)(a1 + 2540) = v4;
            }
            else if ( !strcmp_0(v6, "MemoryConfigMB") )
            {
              *(_DWORD *)(a1 + 2536) = v4;
            }
          }
          else if ( (_DWORD)v3 == 4 )
          {
            if ( !strcmp_0((&mMainKeywordTable)[4 * v4], "Cmd") )
              *(_DWORD *)(a1 + 2548) = v4;
          }
          else
          {
            v4 = *(_DWORD *)(v5 + 8 * v3 + 4);
          }
        }
        else
        {
          v7 = (&mMainKeywordTable)[4 * v4];
          if ( !strcmp_0(v7, "Option") )
          {
            *(_DWORD *)(a1 + 2524) = v4;
          }
          else if ( !strcmp_0(v7, "Command") )
          {
            *(_DWORD *)(a1 + 2544) = v4;
          }
          else
          {
            v8 = (unsigned __int8)*v7 - 123;
            if ( *v7 == 123 )
              v8 = (unsigned __int8)v7[1];
            if ( v8 )
            {
              v9 = (unsigned __int8)*v7 - 125;
              if ( *v7 == 125 )
                v9 = (unsigned __int8)v7[1];
              if ( v9 )
              {
                if ( !strcmp_0(v7, "IgnoreBlock") )
                {
                  *(_DWORD *)(a1 + 2232) = v4;
                }
                else if ( !strcmp_0(v7, "MemConfigKB") )
                {
                  *(_DWORD *)(a1 + 2516) = v4;
                }
                else if ( !strcmp_0(v7, "MemConfigMB") )
                {
                  *(_DWORD *)(a1 + 2520) = v4;
                }
              }
              else
              {
                *(_DWORD *)(a1 + 2532) = v4;
              }
            }
            else
            {
              *(_DWORD *)(a1 + 2528) = v4;
            }
          }
        }
        ++v4;
        v5 = v1;
      }
      while ( v4 < *(_DWORD *)(v1 + 8 * v3 + 4) );
    }
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (_DWORD)v3 != 8 );
}

```

## disassembly

```asm
0x180036de0  push    rbx
0x180036de2  push    rbp
0x180036de3  push    rsi
0x180036de4  push    rdi
0x180036de5  push    r12
0x180036de7  push    r14
0x180036de9  push    r15
0x180036deb  sub     rsp, 20h
0x180036def  mov     r15, [rcx+288h]
0x180036df6  lea     r12, mMainKeywordTable
0x180036dfd  mov     rdi, rcx
0x180036e00  xor     ebp, ebp
0x180036e02  mov     ebx, [r15+rbp*8]
0x180036e06  cmp     ebx, [r15+rbp*8+4]
0x180036e0b  jnb     loc_180036FA5
0x180036e11  mov     rcx, r15
0x180036e14  mov     eax, ebp
0x180036e16  test    ebp, ebp
0x180036e18  jz      loc_180036EC2
0x180036e1e  sub     eax, 3
0x180036e21  jz      short loc_180036E5A
0x180036e23  cmp     eax, 1
0x180036e26  jz      short loc_180036E31
0x180036e28  mov     ebx, [rcx+rbp*8+4]
0x180036e2c  jmp     loc_180036F95
0x180036e31  mov     ecx, ebx
0x180036e33  lea     rdx, aCmd; "Cmd"
0x180036e3a  shl     rcx, 5
0x180036e3e  mov     rcx, [rcx+r12]; Str1
0x180036e42  call    strcmp_0
0x180036e47  test    eax, eax
0x180036e49  jnz     loc_180036F95
0x180036e4f  mov     [rdi+9F4h], ebx
0x180036e55  jmp     loc_180036F95
0x180036e5a  mov     eax, ebx
0x180036e5c  lea     rdx, aName_0; "Name"
0x180036e63  shl     rax, 5
0x180036e67  mov     rsi, [rax+r12]
0x180036e6b  mov     rcx, rsi; Str1
0x180036e6e  call    strcmp_0
0x180036e73  test    eax, eax
0x180036e75  jnz     short loc_180036E82
0x180036e77  mov     [rdi+9F8h], ebx
0x180036e7d  jmp     loc_180036F95
0x180036e82  lea     rdx, aMemoryconfigkb; "MemoryConfigKB"
0x180036e89  mov     rcx, rsi; Str1
0x180036e8c  call    strcmp_0
0x180036e91  test    eax, eax
0x180036e93  jnz     short loc_180036EA0
0x180036e95  mov     [rdi+9ECh], ebx
0x180036e9b  jmp     loc_180036F95
0x180036ea0  lea     rdx, aMemoryconfigmb; "MemoryConfigMB"
0x180036ea7  mov     rcx, rsi; Str1
0x180036eaa  call    strcmp_0
0x180036eaf  test    eax, eax
0x180036eb1  jnz     loc_180036F95
0x180036eb7  mov     [rdi+9E8h], ebx
0x180036ebd  jmp     loc_180036F95
0x180036ec2  mov     eax, ebx
0x180036ec4  lea     rdx, aOption; "Option"
0x180036ecb  shl     rax, 5
0x180036ecf  mov     rsi, [rax+r12]
0x180036ed3  mov     rcx, rsi; Str1
0x180036ed6  call    strcmp_0
0x180036edb  test    eax, eax
0x180036edd  jnz     short loc_180036EEA
0x180036edf  mov     [rdi+9DCh], ebx
0x180036ee5  jmp     loc_180036F95
0x180036eea  lea     rdx, aCommand; "Command"
0x180036ef1  mov     rcx, rsi; Str1
0x180036ef4  call    strcmp_0
0x180036ef9  test    eax, eax
0x180036efb  jnz     short loc_180036F08
0x180036efd  mov     [rdi+9F0h], ebx
0x180036f03  jmp     loc_180036F95
0x180036f08  movzx   edx, byte ptr [rsi]
0x180036f0b  sub     edx, 7Bh ; '{'
0x180036f0e  jnz     short loc_180036F1B
0x180036f10  movzx   edx, byte ptr [rsi+1]
0x180036f14  xor     eax, eax
0x180036f16  movzx   ecx, al
0x180036f19  sub     edx, ecx
0x180036f1b  test    edx, edx
0x180036f1d  jnz     short loc_180036F27
0x180036f1f  mov     [rdi+9E0h], ebx
0x180036f25  jmp     short loc_180036F95
0x180036f27  movzx   edx, byte ptr [rsi]
0x180036f2a  sub     edx, 7Dh ; '}'
0x180036f2d  jnz     short loc_180036F3A
0x180036f2f  movzx   edx, byte ptr [rsi+1]
0x180036f33  xor     eax, eax
0x180036f35  movzx   ecx, al
0x180036f38  sub     edx, ecx
0x180036f3a  test    edx, edx
0x180036f3c  jnz     short loc_180036F46
0x180036f3e  mov     [rdi+9E4h], ebx
0x180036f44  jmp     short loc_180036F95
0x180036f46  lea     rdx, aIgnoreblock; "IgnoreBlock"
0x180036f4d  mov     rcx, rsi; Str1
0x180036f50  call    strcmp_0
0x180036f55  test    eax, eax
0x180036f57  jnz     short loc_180036F61
0x180036f59  mov     [rdi+8B8h], ebx
0x180036f5f  jmp     short loc_180036F95
0x180036f61  lea     rdx, aMemconfigkb; "MemConfigKB"
0x180036f68  mov     rcx, rsi; Str1
0x180036f6b  call    strcmp_0
0x180036f70  test    eax, eax
0x180036f72  jnz     short loc_180036F7C
0x180036f74  mov     [rdi+9D4h], ebx
0x180036f7a  jmp     short loc_180036F95
0x180036f7c  lea     rdx, aMemconfigmb; "MemConfigMB"
0x180036f83  mov     rcx, rsi; Str1
0x180036f86  call    strcmp_0
0x180036f8b  test    eax, eax
0x180036f8d  jnz     short loc_180036F95
0x180036f8f  mov     [rdi+9D8h], ebx
0x180036f95  inc     ebx
0x180036f97  mov     rcx, r15
0x180036f9a  cmp     ebx, [r15+rbp*8+4]
0x180036f9f  jb      loc_180036E14
0x180036fa5  inc     ebp
0x180036fa7  cmp     ebp, 8
0x180036faa  jnz     loc_180036E02
0x180036fb0  add     rsp, 20h
0x180036fb4  pop     r15
0x180036fb6  pop     r14
0x180036fb8  pop     r12
0x180036fba  pop     rdi
0x180036fbb  pop     rsi
0x180036fbc  pop     rbp
0x180036fbd  pop     rbx
0x180036fbe  retn
```
