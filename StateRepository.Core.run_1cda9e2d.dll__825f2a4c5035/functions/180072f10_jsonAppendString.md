# jsonAppendString

- ea: `0x180072f10`
- end: `0x1800730d1`
- name: `jsonAppendString`
- size: `449`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180072da4`
- `0x180076000`
- `0x180076180`
- `0x18007750c`

## callees

- `0x180072b6c`
- `0x180072f10`
- `0x1800771e0`
- `0x180099814`

## pseudocode

```c
void __fastcall jsonAppendString(_QWORD *a1, char *a2, unsigned int a3)
{
  char *v3; // r14
  unsigned int v4; // ebp
  __int64 i; // rsi
  __int64 v7; // rdx
  __int64 v8; // r8
  char v9; // bl

  if ( !a2 )
    return;
  v3 = a2;
  v4 = a3;
  if ( a1[3] + (unsigned __int64)a3 + 2 >= a1[2] )
  {
    if ( (unsigned int)jsonStringGrow((__int64)a1, a3 + 2) )
      return;
  }
  *(_BYTE *)(a1[3] + a1[1]) = 34;
  ++a1[3];
  while ( 2 )
  {
    for ( i = 0; ; i = (unsigned int)(i + 4) )
    {
      v7 = (unsigned int)(i + 3);
      if ( (unsigned int)v7 >= v4 )
      {
        while ( (unsigned int)i < v4 )
        {
          if ( !byte_1800AA810[(unsigned __int8)v3[i]] )
            goto LABEL_13;
          i = (unsigned int)(i + 1);
        }
        goto LABEL_21;
      }
      if ( !byte_1800AA810[(unsigned __int8)v3[i]] )
        goto LABEL_20;
      v8 = (unsigned int)(i + 1);
      if ( !byte_1800AA810[(unsigned __int8)v3[v8]] )
        break;
      v8 = (unsigned int)(i + 2);
      if ( !byte_1800AA810[(unsigned __int8)v3[v8]] )
        break;
      if ( !byte_1800AA810[(unsigned __int8)v3[v7]] )
      {
        LODWORD(i) = i + 3;
        goto LABEL_13;
      }
    }
    LODWORD(i) = v8;
LABEL_20:
    if ( (unsigned int)i < v4 )
    {
LABEL_13:
      if ( (_DWORD)i )
      {
        memcpy_0((void *)(a1[1] + a1[3]), v3, (unsigned int)i);
        a1[3] += (unsigned int)i;
        v3 += (unsigned int)i;
        v4 -= i;
      }
      v9 = *v3;
      if ( *v3 == 34 || v9 == 92 )
      {
        if ( a1[3] + 3LL + (unsigned __int64)v4 > a1[2] && (unsigned int)jsonStringGrow((__int64)a1, v4 + 3) )
          return;
        *(_BYTE *)(a1[3] + a1[1]) = 92;
        *(_BYTE *)(++a1[3] + a1[1]) = v9;
      }
      else
      {
        if ( v9 != 39 )
        {
          if ( a1[3] + 7LL + (unsigned __int64)v4 > a1[2] && (unsigned int)jsonStringGrow((__int64)a1, v4 + 7) )
            return;
          LOBYTE(v7) = v9;
          jsonAppendControlChar(a1, v7);
LABEL_36:
          ++v3;
          --v4;
          continue;
        }
        *(_BYTE *)(a1[3] + a1[1]) = 39;
      }
      ++a1[3];
      goto LABEL_36;
    }
    break;
  }
LABEL_21:
  if ( (_DWORD)i )
  {
    memcpy_0((void *)(a1[1] + a1[3]), v3, (unsigned int)i);
    a1[3] += (unsigned int)i;
  }
  *(_BYTE *)(a1[3] + a1[1]) = 34;
  ++a1[3];
}

```

## disassembly

```asm
0x180072f10  test    rdx, rdx
0x180072f13  jz      locret_18007303F
0x180072f19  push    rbx
0x180072f1a  push    rbp
0x180072f1b  push    rsi
0x180072f1c  push    rdi
0x180072f1d  push    r12
0x180072f1f  push    r14
0x180072f21  sub     rsp, 28h
0x180072f25  mov     r14, rdx
0x180072f28  mov     ebp, r8d
0x180072f2b  mov     rdi, rcx
0x180072f2e  lea     rdx, [rbp+2]
0x180072f32  add     rdx, [rcx+18h]
0x180072f36  cmp     rdx, [rcx+10h]
0x180072f3a  jb      short loc_180072F4C
0x180072f3c  lea     edx, [rbp+2]
0x180072f3f  call    jsonStringGrow
0x180072f44  test    eax, eax
0x180072f46  jnz     loc_180073033
0x180072f4c  mov     rcx, [rdi+18h]
0x180072f50  lea     r12, byte_1800AA810
0x180072f57  mov     rax, [rdi+8]
0x180072f5b  mov     byte ptr [rcx+rax], 22h ; '"'
0x180072f5f  inc     qword ptr [rdi+18h]
0x180072f63  xor     esi, esi
0x180072f65  lea     edx, [rsi+3]
0x180072f68  cmp     edx, ebp
0x180072f6a  jnb     loc_180073052
0x180072f70  movzx   ecx, byte ptr [rsi+r14]
0x180072f75  cmp     byte ptr [rcx+r12], 0
0x180072f7a  jz      loc_180073002
0x180072f80  lea     r8d, [rsi+1]
0x180072f84  movzx   ecx, byte ptr [r8+r14]
0x180072f89  cmp     byte ptr [rcx+r12], 0
0x180072f8e  jz      short loc_180072FFF
0x180072f90  lea     r8d, [rsi+2]
0x180072f94  movzx   ecx, byte ptr [r8+r14]
0x180072f99  cmp     byte ptr [rcx+r12], 0
0x180072f9e  jz      short loc_180072FFF
0x180072fa0  movzx   ecx, byte ptr [rdx+r14]
0x180072fa5  cmp     byte ptr [rcx+r12], 0
0x180072faa  jz      short loc_180072FB1
0x180072fac  add     esi, 4
0x180072faf  jmp     short loc_180072F65
0x180072fb1  mov     esi, edx
0x180072fb3  test    esi, esi
0x180072fb5  jz      short loc_180072FD5
0x180072fb7  mov     rcx, [rdi+18h]
0x180072fbb  mov     rdx, r14; Src
0x180072fbe  add     rcx, [rdi+8]; void *
0x180072fc2  mov     r8d, esi; Size
0x180072fc5  mov     ebx, esi
0x180072fc7  call    memcpy_0
0x180072fcc  add     [rdi+18h], rbx
0x180072fd0  add     r14, rbx
0x180072fd3  sub     ebp, esi
0x180072fd5  mov     bl, [r14]
0x180072fd8  cmp     bl, 22h ; '"'
0x180072fdb  jz      loc_180073086
0x180072fe1  cmp     bl, 5Ch ; '\'
0x180072fe4  jz      loc_180073086
0x180072fea  cmp     bl, 27h ; '''
0x180072fed  jnz     short loc_180073058
0x180072fef  mov     rcx, [rdi+18h]
0x180072ff3  mov     rax, [rdi+8]
0x180072ff7  mov     [rcx+rax], bl
0x180072ffa  jmp     loc_1800730C3
0x180072fff  mov     esi, r8d
0x180073002  cmp     esi, ebp
0x180073004  jb      short loc_180072FB3
0x180073006  test    esi, esi
0x180073008  jz      short loc_180073023
0x18007300a  mov     rcx, [rdi+18h]
0x18007300e  mov     rdx, r14; Src
0x180073011  add     rcx, [rdi+8]; void *
0x180073015  mov     r8d, esi; Size
0x180073018  mov     ebx, esi
0x18007301a  call    memcpy_0
0x18007301f  add     [rdi+18h], rbx
0x180073023  mov     rcx, [rdi+18h]
0x180073027  mov     rax, [rdi+8]
0x18007302b  mov     byte ptr [rcx+rax], 22h ; '"'
0x18007302f  inc     qword ptr [rdi+18h]
0x180073033  add     rsp, 28h
0x180073037  pop     r14
0x180073039  pop     r12
0x18007303b  pop     rdi
0x18007303c  pop     rsi
0x18007303d  pop     rbp
0x18007303e  pop     rbx
0x18007303f  retn
0x180073040  movzx   ecx, byte ptr [rsi+r14]
0x180073045  cmp     byte ptr [rcx+r12], 0
0x18007304a  jz      loc_180072FB3
0x180073050  inc     esi
0x180073052  cmp     esi, ebp
0x180073054  jb      short loc_180073040
0x180073056  jmp     short loc_180073006
0x180073058  mov     rax, [rdi+18h]
0x18007305c  add     rax, 7
0x180073060  mov     ecx, ebp
0x180073062  add     rcx, rax
0x180073065  cmp     rcx, [rdi+10h]
0x180073069  jbe     short loc_18007307A
0x18007306b  lea     edx, [rbp+7]
0x18007306e  mov     rcx, rdi
0x180073071  call    jsonStringGrow
0x180073076  test    eax, eax
0x180073078  jnz     short loc_180073033
0x18007307a  mov     dl, bl
0x18007307c  mov     rcx, rdi
0x18007307f  call    jsonAppendControlChar
0x180073084  jmp     short loc_1800730C7
0x180073086  mov     rax, [rdi+18h]
0x18007308a  add     rax, 3
0x18007308e  mov     ecx, ebp
0x180073090  add     rcx, rax
0x180073093  cmp     rcx, [rdi+10h]
0x180073097  jbe     short loc_1800730A8
0x180073099  lea     edx, [rbp+3]
0x18007309c  mov     rcx, rdi
0x18007309f  call    jsonStringGrow
0x1800730a4  test    eax, eax
0x1800730a6  jnz     short loc_180073033
0x1800730a8  mov     rcx, [rdi+18h]
0x1800730ac  mov     rax, [rdi+8]
0x1800730b0  mov     byte ptr [rcx+rax], 5Ch ; '\'
0x1800730b4  inc     qword ptr [rdi+18h]
0x1800730b8  mov     rcx, [rdi+18h]
0x1800730bc  mov     rax, [rdi+8]
0x1800730c0  mov     [rcx+rax], bl
0x1800730c3  inc     qword ptr [rdi+18h]
0x1800730c7  inc     r14
0x1800730ca  dec     ebp
0x1800730cc  jmp     loc_180072F63
```
