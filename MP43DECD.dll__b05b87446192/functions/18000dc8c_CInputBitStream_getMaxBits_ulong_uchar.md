# CInputBitStream::getMaxBits(ulong,uchar *)

- ea: `0x18000dc8c`
- end: `0x18000ddff`
- name: `?getMaxBits@CInputBitStream@@QEAAEKPEAE@Z`
- size: `371`
- prototype: `unsigned __int8 __fastcall(CInputBitStream *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d9a0`
- `0x18000dacc`
- `0x18000de90`
- `0x18000e0c0`
- `0x18000e1b0`
- `0x18000e290`
- `0x18000e520`
- `0x18000e6a0`
- `0x18000e910`
- `0x1800127d8`
- `0x180012b44`

## callees

- `0x18000dc8c`

## pseudocode

```c
unsigned __int8 __fastcall CInputBitStream::getMaxBits(CInputBitStream *this, unsigned int a2, unsigned __int8 *a3)
{
  unsigned int v3; // r11d
  __int64 v5; // rbx
  __int64 v6; // rcx
  int v7; // r11d
  int v9; // r9d
  unsigned __int8 *v10; // rcx
  int v11; // eax
  unsigned int v12; // edx
  int v13; // edx
  unsigned __int8 *v14; // rdx
  int v15; // ecx
  int v16; // eax
  __int64 v17; // rax
  unsigned int v18; // ecx

  v3 = *((_DWORD *)this + 4);
  v5 = a2;
  if ( a2 <= v3 )
  {
    _mm_lfence();
    v6 = 2 * (*((_DWORD *)&getMask + a2) & (*((_DWORD *)this + 3) >> (v3 - a2)));
LABEL_3:
    v7 = v3 - a3[v6];
LABEL_4:
    *((_DWORD *)this + 4) = v7;
    if ( a3[v6 + 1] == 0xFF )
      *((_DWORD *)this + 5) = 3;
    return a3[v6 + 1];
  }
  v9 = *((_DWORD *)this + 2);
  if ( v9 >= 2 )
  {
    *((_DWORD *)this + 3) <<= 16;
    v10 = *(unsigned __int8 **)this;
    v11 = *((_DWORD *)this + 3) | v10[1];
    *((_DWORD *)this + 3) = v11;
    v12 = v11 | (*v10 << 8);
    *((_DWORD *)this + 3) = v12;
    *(_QWORD *)this = v10 + 2;
    v13 = 2 * (*((_DWORD *)&getMask + v5) & (v12 >> (v3 - v5 + 16)));
    *((_DWORD *)this + 2) = v9 - 2;
    v6 = v13;
    *((_DWORD *)this + 4) = v3 + 16;
    v7 = v3 - a3[v13] + 16;
    goto LABEL_4;
  }
  if ( v9 )
  {
    v14 = *(unsigned __int8 **)this;
    do
    {
      v3 += 8;
      v15 = *((_DWORD *)this + 3) << 8;
      *((_DWORD *)this + 3) = v15;
      v16 = *v14++;
      *(_QWORD *)this = v14;
      --v9;
      *((_DWORD *)this + 3) = v16 | v15;
      *((_DWORD *)this + 2) = v9;
      *((_DWORD *)this + 4) = v3;
    }
    while ( v9 );
  }
  if ( v3 >= (unsigned int)v5 )
  {
    _mm_lfence();
    v6 = 2 * (*((_DWORD *)&getMask + v5) & (*((_DWORD *)this + 3) >> (v3 - v5)));
    goto LABEL_3;
  }
  v17 = (*((_DWORD *)this + 3) & *((_DWORD *)&getMask + v3)) << (v5 - v3 + 1);
  v18 = a3[v17];
  if ( v3 < v18 )
  {
    *((_DWORD *)this + 5) = 1;
    return -1;
  }
  else
  {
    *((_DWORD *)this + 4) = v3 - v18;
    if ( a3[v17 + 1] == 0xFF )
      *((_DWORD *)this + 5) = 3;
    return a3[v17 + 1];
  }
}

```

## disassembly

```asm
0x18000dc8c  mov     [rsp+arg_0], rbx
0x18000dc91  mov     r11d, [rcx+10h]
0x18000dc95  mov     r10, rcx
0x18000dc98  mov     ebx, edx
0x18000dc9a  cmp     edx, r11d
0x18000dc9d  ja      short loc_18000DCE5
0x18000dc9f  lfence
0x18000dca2  mov     r9d, [r10+0Ch]
0x18000dca6  mov     ecx, r11d
0x18000dca9  sub     ecx, ebx
0x18000dcab  shr     r9d, cl
0x18000dcae  lea     rcx, ?getMask@@3PAKA; ulong near * getMask
0x18000dcb5  and     r9d, [rcx+rbx*4]
0x18000dcb9  add     r9d, r9d
0x18000dcbc  movsxd  rcx, r9d
0x18000dcbf  movzx   eax, byte ptr [rcx+r8]
0x18000dcc4  sub     r11d, eax
0x18000dcc7  mov     [r10+10h], r11d
0x18000dccb  cmp     byte ptr [rcx+r8+1], 0FFh
0x18000dcd1  jnz     short loc_18000DCDB
0x18000dcd3  mov     dword ptr [r10+14h], 3
0x18000dcdb  mov     al, [rcx+r8+1]
0x18000dce0  jmp     loc_18000DDF9
0x18000dce5  mov     r9d, [rcx+8]
0x18000dce9  cmp     r9d, 2
0x18000dced  jl      short loc_18000DD4F
0x18000dcef  shl     dword ptr [rcx+0Ch], 10h
0x18000dcf3  mov     rcx, [rcx]
0x18000dcf6  movzx   eax, byte ptr [rcx+1]
0x18000dcfa  or      eax, [r10+0Ch]
0x18000dcfe  mov     [r10+0Ch], eax
0x18000dd02  movzx   edx, byte ptr [rcx]
0x18000dd05  shl     edx, 8
0x18000dd08  or      edx, eax
0x18000dd0a  lea     rax, [rcx+2]
0x18000dd0e  mov     ecx, r11d
0x18000dd11  mov     [r10+0Ch], edx
0x18000dd15  sub     ecx, ebx
0x18000dd17  mov     [r10], rax
0x18000dd1a  add     ecx, 10h
0x18000dd1d  lea     eax, [r9-2]
0x18000dd21  shr     edx, cl
0x18000dd23  lea     rcx, ?getMask@@3PAKA; ulong near * getMask
0x18000dd2a  and     edx, [rcx+rbx*4]
0x18000dd2d  add     edx, edx
0x18000dd2f  mov     [r10+8], eax
0x18000dd33  lea     eax, [r11+10h]
0x18000dd37  movsxd  rcx, edx
0x18000dd3a  mov     [r10+10h], eax
0x18000dd3e  movzx   eax, byte ptr [rcx+r8]
0x18000dd43  sub     r11d, eax
0x18000dd46  add     r11d, 10h
0x18000dd4a  jmp     loc_18000DCC7
0x18000dd4f  test    r9d, r9d
0x18000dd52  jz      short loc_18000DD85
0x18000dd54  mov     rdx, [rcx]
0x18000dd57  mov     ecx, [r10+0Ch]
0x18000dd5b  add     r11d, 8
0x18000dd5f  shl     ecx, 8
0x18000dd62  mov     [r10+0Ch], ecx
0x18000dd66  movzx   eax, byte ptr [rdx]
0x18000dd69  inc     rdx
0x18000dd6c  or      ecx, eax
0x18000dd6e  mov     [r10], rdx
0x18000dd71  dec     r9d
0x18000dd74  mov     [r10+0Ch], ecx
0x18000dd78  mov     [r10+8], r9d
0x18000dd7c  mov     [r10+10h], r11d
0x18000dd80  test    r9d, r9d
0x18000dd83  jnz     short loc_18000DD57
0x18000dd85  cmp     r11d, ebx
0x18000dd88  jb      short loc_18000DDAC
0x18000dd8a  lfence
0x18000dd8d  mov     edx, [r10+0Ch]
0x18000dd91  mov     ecx, r11d
0x18000dd94  sub     ecx, ebx
0x18000dd96  shr     edx, cl
0x18000dd98  lea     rcx, ?getMask@@3PAKA; ulong near * getMask
0x18000dd9f  and     edx, [rcx+rbx*4]
0x18000dda2  add     edx, edx
0x18000dda4  movsxd  rcx, edx
0x18000dda7  jmp     loc_18000DCBF
0x18000ddac  mov     eax, r11d
0x18000ddaf  lea     rcx, ?getMask@@3PAKA; ulong near * getMask
0x18000ddb6  sub     ebx, r11d
0x18000ddb9  mov     eax, [rcx+rax*4]
0x18000ddbc  and     eax, [r10+0Ch]
0x18000ddc0  lea     ecx, [rbx+1]
0x18000ddc3  shl     eax, cl
0x18000ddc5  cdqe
0x18000ddc7  movzx   ecx, byte ptr [rax+r8]
0x18000ddcc  cmp     r11d, ecx
0x18000ddcf  jb      short loc_18000DDEF
0x18000ddd1  sub     r11d, ecx
0x18000ddd4  mov     [r10+10h], r11d
0x18000ddd8  cmp     byte ptr [rax+r8+1], 0FFh
0x18000ddde  jnz     short loc_18000DDE8
0x18000dde0  mov     dword ptr [r10+14h], 3
0x18000dde8  mov     al, [rax+r8+1]
0x18000dded  jmp     short loc_18000DDF9
0x18000ddef  mov     dword ptr [r10+14h], 1
0x18000ddf7  mov     al, 0FFh
0x18000ddf9  mov     rbx, [rsp+arg_0]
0x18000ddfe  retn
```
