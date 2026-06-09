# SBC::SbcControl::ReadSbcFrameData(int const (* const)[8],ushort (* const)[2][8])

- ea: `0x1400187d0`
- end: `0x1400188a4`
- name: `?ReadSbcFrameData@SbcControl@SBC@@QEAAXQEAY07$$CBHQEAY117G@Z`
- size: `212`
- prototype: `void __fastcall(SBC::SbcControl *__hidden this, const int (*const)[8], unsigned __int16 (*const)[2][8])`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140018148`

## callees

- `0x1400187d0`
- `0x140019098`

## pseudocode

```c
void __fastcall SBC::SbcControl::ReadSbcFrameData(
        SBC::SbcControl *this,
        const int (*const a2)[8],
        unsigned __int16 (*const a3)[2][8])
{
  const int *v3; // rbx
  int v4; // eax
  unsigned __int64 v7; // rax
  int i; // esi
  int j; // ebp
  int v10; // r14d
  const int *v11; // r15
  __int64 v12; // rbx
  unsigned __int16 v13; // ax

  v3 = (const int *)a2;
  v4 = *((_DWORD *)this + 7) * *((_DWORD *)this + 5);
  *((_DWORD *)this + 14) = 0;
  *((_WORD *)this + 30) = 0;
  v7 = (unsigned int)(4 * v4 + 32);
  *((_QWORD *)this + 6) = *((_QWORD *)this + 5) + (v7 >> 3);
  SBC::SbcControl::getbits(this, v7 & 7);
  if ( *((_DWORD *)this + 2) == 3 )
    SBC::SbcControl::getbits(this, *((_DWORD *)this + 7));
  for ( i = 0; i < *((_DWORD *)this + 6); ++i )
  {
    for ( j = 0; j < *((_DWORD *)this + 5); ++j )
    {
      v10 = 0;
      if ( *((int *)this + 7) > 0 )
      {
        v11 = &v3[8 * j];
        do
        {
          v12 = v10;
          v13 = SBC::SbcControl::getbits(this, v11[v10++]);
          (*a3)[2 * i][8 * j + v12] = v13;
        }
        while ( v10 < *((_DWORD *)this + 7) );
        v3 = (const int *)a2;
      }
    }
  }
}

```

## disassembly

```asm
0x1400187d0  mov     [rsp+arg_8], rdx
0x1400187d5  push    rbx
0x1400187d6  push    rbp
0x1400187d7  push    rsi
0x1400187d8  push    rdi
0x1400187d9  push    r12
0x1400187db  push    r13
0x1400187dd  push    r14
0x1400187df  push    r15
0x1400187e1  sub     rsp, 28h
0x1400187e5  mov     eax, [rcx+14h]
0x1400187e8  mov     rbx, rdx
0x1400187eb  imul    eax, [rcx+1Ch]
0x1400187ef  mov     r13, r8
0x1400187f2  mov     rdi, rcx
0x1400187f5  mov     dword ptr [rcx+38h], 0
0x1400187fc  lea     edx, ds:20h[rax*4]
0x140018803  xor     eax, eax
0x140018805  mov     [rcx+3Ch], ax
0x140018809  mov     eax, edx
0x14001880b  and     edx, 7; unsigned int
0x14001880e  shr     rax, 3
0x140018812  add     rax, [rcx+28h]
0x140018816  mov     [rcx+30h], rax
0x14001881a  call    ?getbits@SbcControl@SBC@@AEAAII@Z; SBC::SbcControl::getbits(uint)
0x14001881f  cmp     dword ptr [rdi+8], 3
0x140018823  jnz     short loc_140018830
0x140018825  mov     edx, [rdi+1Ch]; unsigned int
0x140018828  mov     rcx, rdi; this
0x14001882b  call    ?getbits@SbcControl@SBC@@AEAAII@Z; SBC::SbcControl::getbits(uint)
0x140018830  xor     esi, esi
0x140018832  cmp     [rdi+18h], esi
0x140018835  jle     short loc_140018892
0x140018837  xor     ebp, ebp
0x140018839  cmp     [rdi+14h], ebp
0x14001883c  jle     short loc_14001888B
0x14001883e  xor     r14d, r14d
0x140018841  cmp     [rdi+1Ch], r14d
0x140018845  jle     short loc_140018884
0x140018847  movsxd  rcx, ebp
0x14001884a  movsxd  rax, esi
0x14001884d  mov     r15, rcx
0x140018850  shl     r15, 5
0x140018854  add     r15, rbx
0x140018857  lea     r12, [rcx+rax*2]
0x14001885b  shl     r12, 4
0x14001885f  add     r12, r13
0x140018862  movsxd  rbx, r14d
0x140018865  mov     rcx, rdi; this
0x140018868  mov     edx, [r15+rbx*4]; unsigned int
0x14001886c  call    ?getbits@SbcControl@SBC@@AEAAII@Z; SBC::SbcControl::getbits(uint)
0x140018871  inc     r14d
0x140018874  mov     [r12+rbx*2], ax
0x140018879  cmp     r14d, [rdi+1Ch]
0x14001887d  jl      short loc_140018862
0x14001887f  mov     rbx, [rsp+68h+arg_8]
0x140018884  inc     ebp
0x140018886  cmp     ebp, [rdi+14h]
0x140018889  jl      short loc_14001883E
0x14001888b  inc     esi
0x14001888d  cmp     esi, [rdi+18h]
0x140018890  jl      short loc_140018837
0x140018892  add     rsp, 28h
0x140018896  pop     r15
0x140018898  pop     r14
0x14001889a  pop     r13
0x14001889c  pop     r12
0x14001889e  pop     rdi
0x14001889f  pop     rsi
0x1400188a0  pop     rbp
0x1400188a1  pop     rbx
0x1400188a2  retn
```
