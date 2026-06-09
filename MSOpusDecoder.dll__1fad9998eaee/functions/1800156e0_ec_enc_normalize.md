# ec_enc_normalize

- ea: `0x1800156e0`
- end: `0x1800157cb`
- name: `ec_enc_normalize`
- size: `235`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180015600`
- `0x1800157e0`
- `0x180015990`

## callees

- `0x1800156e0`

## pseudocode

```c
void __fastcall ec_enc_normalize(__int64 a1)
{
  unsigned int v1; // r8d
  unsigned int v2; // ebx
  int v3; // r9d
  int v4; // r10d
  __int64 v5; // r11
  int v6; // eax
  __int64 v7; // r8
  int v8; // eax
  unsigned int v10; // edx

  if ( *(_DWORD *)(a1 + 32) <= 0x800000u )
  {
    do
    {
      v1 = *(_DWORD *)(a1 + 36);
      v2 = v1 >> 23;
      if ( v1 >> 23 == 255 )
      {
        ++*(_DWORD *)(a1 + 40);
      }
      else
      {
        v3 = *(_DWORD *)(a1 + 44);
        v4 = *(_DWORD *)(a1 + 36) >> 31;
        if ( v3 >= 0 )
        {
          v5 = *(unsigned int *)(a1 + 28);
          if ( (unsigned int)(v5 + *(_DWORD *)(a1 + 12)) < *(_DWORD *)(a1 + 8) )
          {
            *(_BYTE *)(v5 + *(_QWORD *)a1) = (*(int *)(a1 + 36) < 0) + v3;
            ++*(_DWORD *)(a1 + 28);
            v1 = *(_DWORD *)(a1 + 36);
            v6 = 0;
          }
          else
          {
            v6 = -1;
          }
          *(_DWORD *)(a1 + 48) |= v6;
        }
        if ( *(_DWORD *)(a1 + 40) )
        {
          do
          {
            v7 = *(unsigned int *)(a1 + 28);
            if ( (unsigned int)(v7 + *(_DWORD *)(a1 + 12)) < *(_DWORD *)(a1 + 8) )
            {
              *(_BYTE *)(v7 + *(_QWORD *)a1) = v4 - 1;
              ++*(_DWORD *)(a1 + 28);
              v8 = 0;
            }
            else
            {
              v8 = -1;
            }
            *(_DWORD *)(a1 + 48) |= v8;
          }
          while ( (*(_DWORD *)(a1 + 40))-- != 1 );
          v1 = *(_DWORD *)(a1 + 36);
        }
        *(_DWORD *)(a1 + 44) = (unsigned __int8)v2;
      }
      v10 = *(_DWORD *)(a1 + 32);
      *(_DWORD *)(a1 + 24) += 8;
      v10 <<= 8;
      *(_DWORD *)(a1 + 36) = (v1 & 0x7FFFFF) << 8;
      *(_DWORD *)(a1 + 32) = v10;
    }
    while ( v10 <= 0x800000 );
  }
}

```

## disassembly

```asm
0x1800156e0  sub     rsp, 8
0x1800156e4  cmp     dword ptr [rcx+20h], 800000h
0x1800156eb  ja      loc_1800157C6
0x1800156f1  mov     [rsp+8+var_8], rbx
0x1800156f5  nop     word ptr [rax+rax+00000000h]
0x180015700  mov     r8d, [rcx+24h]
0x180015704  mov     ebx, r8d
0x180015707  shr     ebx, 17h
0x18001570a  cmp     ebx, 0FFh
0x180015710  jz      loc_180015797
0x180015716  mov     r9d, [rcx+2Ch]
0x18001571a  mov     r10d, ebx
0x18001571d  sar     r10d, 8
0x180015721  test    r9d, r9d
0x180015724  js      short loc_180015752
0x180015726  mov     r11d, [rcx+1Ch]
0x18001572a  mov     edx, [rcx+0Ch]
0x18001572d  add     edx, r11d
0x180015730  cmp     edx, [rcx+8]
0x180015733  jb      short loc_18001573C
0x180015735  mov     eax, 0FFFFFFFFh
0x18001573a  jmp     short loc_18001574F
0x18001573c  mov     rax, [rcx]
0x18001573f  add     r9b, r10b
0x180015742  mov     [r11+rax], r9b
0x180015746  inc     dword ptr [rcx+1Ch]
0x180015749  mov     r8d, [rcx+24h]
0x18001574d  xor     eax, eax
0x18001574f  or      [rcx+30h], eax
0x180015752  cmp     dword ptr [rcx+28h], 0
0x180015756  jbe     short loc_18001578F
0x180015758  lea     eax, [r10-1]
0x18001575c  movzx   r9d, al
0x180015760  mov     r8d, [rcx+1Ch]
0x180015764  mov     edx, [rcx+0Ch]
0x180015767  add     edx, r8d
0x18001576a  cmp     edx, [rcx+8]
0x18001576d  jb      short loc_180015776
0x18001576f  mov     eax, 0FFFFFFFFh
0x180015774  jmp     short loc_180015782
0x180015776  mov     rax, [rcx]
0x180015779  mov     [r8+rax], r9b
0x18001577d  inc     dword ptr [rcx+1Ch]
0x180015780  xor     eax, eax
0x180015782  or      [rcx+30h], eax
0x180015785  sub     dword ptr [rcx+28h], 1
0x180015789  jnz     short loc_180015760
0x18001578b  mov     r8d, [rcx+24h]
0x18001578f  movzx   eax, bl
0x180015792  mov     [rcx+2Ch], eax
0x180015795  jmp     short loc_18001579A
0x180015797  inc     dword ptr [rcx+28h]
0x18001579a  mov     edx, [rcx+20h]
0x18001579d  and     r8d, 7FFFFFh
0x1800157a4  add     dword ptr [rcx+18h], 8
0x1800157a8  shl     r8d, 8
0x1800157ac  shl     edx, 8
0x1800157af  mov     [rcx+24h], r8d
0x1800157b3  mov     [rcx+20h], edx
0x1800157b6  cmp     edx, 800000h
0x1800157bc  jbe     loc_180015700
0x1800157c2  mov     rbx, [rsp+8+var_8]
0x1800157c6  add     rsp, 8
0x1800157ca  retn
```
