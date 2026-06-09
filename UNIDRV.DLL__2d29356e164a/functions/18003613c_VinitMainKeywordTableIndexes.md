# VinitMainKeywordTableIndexes

- ea: `0x18003613c`
- end: `0x18003631b`
- name: `VinitMainKeywordTableIndexes`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035fe0`

## callees

- `0x18003613c`
- `0x180074544`

## string_xrefs

- `0x180036246`: `Command`
- `0x1800362bd`: `MemConfigKB`
- `0x1800362d8`: `MemConfigMB`
- `0x1800361fc`: `MemoryConfigMB`
- `0x1800361de`: `MemoryConfigKB`

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
0x18003613c  push    rbx
0x18003613e  push    rbp
0x18003613f  push    rsi
0x180036140  push    rdi
0x180036141  push    r12
0x180036143  push    r14
0x180036145  push    r15
0x180036147  sub     rsp, 20h
0x18003614b  mov     r15, [rcx+288h]
0x180036152  lea     r12, mMainKeywordTable
0x180036159  mov     rdi, rcx
0x18003615c  xor     ebp, ebp
0x18003615e  mov     ebx, [r15+rbp*8]
0x180036162  cmp     ebx, [r15+rbp*8+4]
0x180036167  jnb     loc_180036301
0x18003616d  mov     rcx, r15
0x180036170  mov     eax, ebp
0x180036172  test    ebp, ebp
0x180036174  jz      loc_18003621E
0x18003617a  sub     eax, 3
0x18003617d  jz      short loc_1800361B6
0x18003617f  cmp     eax, 1
0x180036182  jz      short loc_18003618D
0x180036184  mov     ebx, [rcx+rbp*8+4]
0x180036188  jmp     loc_1800362F1
0x18003618d  mov     ecx, ebx
0x18003618f  lea     rdx, aCmd; "Cmd"
0x180036196  shl     rcx, 5
0x18003619a  mov     rcx, [rcx+r12]; Str1
0x18003619e  call    strcmp_0
0x1800361a3  test    eax, eax
0x1800361a5  jnz     loc_1800362F1
0x1800361ab  mov     [rdi+9F4h], ebx
0x1800361b1  jmp     loc_1800362F1
0x1800361b6  mov     eax, ebx
0x1800361b8  lea     rdx, aName_0; "Name"
0x1800361bf  shl     rax, 5
0x1800361c3  mov     rsi, [rax+r12]
0x1800361c7  mov     rcx, rsi; Str1
0x1800361ca  call    strcmp_0
0x1800361cf  test    eax, eax
0x1800361d1  jnz     short loc_1800361DE
0x1800361d3  mov     [rdi+9F8h], ebx
0x1800361d9  jmp     loc_1800362F1
0x1800361de  lea     rdx, aMemoryconfigkb; "MemoryConfigKB"
0x1800361e5  mov     rcx, rsi; Str1
0x1800361e8  call    strcmp_0
0x1800361ed  test    eax, eax
0x1800361ef  jnz     short loc_1800361FC
0x1800361f1  mov     [rdi+9ECh], ebx
0x1800361f7  jmp     loc_1800362F1
0x1800361fc  lea     rdx, aMemoryconfigmb; "MemoryConfigMB"
0x180036203  mov     rcx, rsi; Str1
0x180036206  call    strcmp_0
0x18003620b  test    eax, eax
0x18003620d  jnz     loc_1800362F1
0x180036213  mov     [rdi+9E8h], ebx
0x180036219  jmp     loc_1800362F1
0x18003621e  mov     eax, ebx
0x180036220  lea     rdx, aOption; "Option"
0x180036227  shl     rax, 5
0x18003622b  mov     rsi, [rax+r12]
0x18003622f  mov     rcx, rsi; Str1
0x180036232  call    strcmp_0
0x180036237  test    eax, eax
0x180036239  jnz     short loc_180036246
0x18003623b  mov     [rdi+9DCh], ebx
0x180036241  jmp     loc_1800362F1
0x180036246  lea     rdx, aCommand; "Command"
0x18003624d  mov     rcx, rsi; Str1
0x180036250  call    strcmp_0
0x180036255  test    eax, eax
0x180036257  jnz     short loc_180036264
0x180036259  mov     [rdi+9F0h], ebx
0x18003625f  jmp     loc_1800362F1
0x180036264  movzx   edx, byte ptr [rsi]
0x180036267  sub     edx, 7Bh ; '{'
0x18003626a  jnz     short loc_180036277
0x18003626c  movzx   edx, byte ptr [rsi+1]
0x180036270  xor     eax, eax
0x180036272  movzx   ecx, al
0x180036275  sub     edx, ecx
0x180036277  test    edx, edx
0x180036279  jnz     short loc_180036283
0x18003627b  mov     [rdi+9E0h], ebx
0x180036281  jmp     short loc_1800362F1
0x180036283  movzx   edx, byte ptr [rsi]
0x180036286  sub     edx, 7Dh ; '}'
0x180036289  jnz     short loc_180036296
0x18003628b  movzx   edx, byte ptr [rsi+1]
0x18003628f  xor     eax, eax
0x180036291  movzx   ecx, al
0x180036294  sub     edx, ecx
0x180036296  test    edx, edx
0x180036298  jnz     short loc_1800362A2
0x18003629a  mov     [rdi+9E4h], ebx
0x1800362a0  jmp     short loc_1800362F1
0x1800362a2  lea     rdx, aIgnoreblock; "IgnoreBlock"
0x1800362a9  mov     rcx, rsi; Str1
0x1800362ac  call    strcmp_0
0x1800362b1  test    eax, eax
0x1800362b3  jnz     short loc_1800362BD
0x1800362b5  mov     [rdi+8B8h], ebx
0x1800362bb  jmp     short loc_1800362F1
0x1800362bd  lea     rdx, aMemconfigkb; "MemConfigKB"
0x1800362c4  mov     rcx, rsi; Str1
0x1800362c7  call    strcmp_0
0x1800362cc  test    eax, eax
0x1800362ce  jnz     short loc_1800362D8
0x1800362d0  mov     [rdi+9D4h], ebx
0x1800362d6  jmp     short loc_1800362F1
0x1800362d8  lea     rdx, aMemconfigmb; "MemConfigMB"
0x1800362df  mov     rcx, rsi; Str1
0x1800362e2  call    strcmp_0
0x1800362e7  test    eax, eax
0x1800362e9  jnz     short loc_1800362F1
0x1800362eb  mov     [rdi+9D8h], ebx
0x1800362f1  inc     ebx
0x1800362f3  mov     rcx, r15
0x1800362f6  cmp     ebx, [r15+rbp*8+4]
0x1800362fb  jb      loc_180036170
0x180036301  inc     ebp
0x180036303  cmp     ebp, 8
0x180036306  jnz     loc_18003615E
0x18003630c  add     rsp, 20h
0x180036310  pop     r15
0x180036312  pop     r14
0x180036314  pop     r12
0x180036316  pop     rdi
0x180036317  pop     rsi
0x180036318  pop     rbp
0x180036319  pop     rbx
0x18003631a  retn
```
