# CMpegHeader::FromInt(ulong)

- ea: `0x180006894`
- end: `0x1800069cd`
- name: `?FromInt@CMpegHeader@@QEAAHK@Z`
- size: `313`
- prototype: `__int64 __fastcall(CMpegHeader *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006628`
- `0x18000de5c`

## callees

- `0x180006894`
- `0x1800069d4`

## pseudocode

```c
__int64 __fastcall CMpegHeader::FromInt(CMpegHeader *this, unsigned int a2)
{
  int v3; // edi
  int v4; // r10d
  int v5; // esi
  int v6; // ecx
  int v7; // r9d

  *((_DWORD *)this + 6) = (a2 & 0x10000) == 0;
  *((_DWORD *)this + 9) = (a2 >> 9) & 1;
  v3 = (a2 >> 17) & 3;
  v4 = (a2 >> 20) & 1;
  *((_DWORD *)this + 2) = a2 >> 21;
  *((_DWORD *)this + 10) = (a2 >> 8) & 1;
  v5 = (a2 >> 19) & 1;
  *((_DWORD *)this + 3) = v4;
  *((_DWORD *)this + 4) = v5;
  *((_DWORD *)this + 11) = (unsigned __int8)a2 >> 6;
  *((_DWORD *)this + 5) = 4 - v3;
  *((_DWORD *)this + 12) = (a2 >> 4) & 3;
  v6 = (unsigned __int16)a2 >> 12;
  *((_DWORD *)this + 7) = v6;
  *((_DWORD *)this + 13) = (a2 >> 3) & 1;
  v7 = (a2 >> 10) & 3;
  *((_DWORD *)this + 8) = v7;
  *((_DWORD *)this + 15) = a2 & 3;
  *((_DWORD *)this + 14) = (a2 >> 2) & 1;
  if ( a2 >> 21 == 2047 && v3 == 1 && v6 != 15 && (unsigned __int16)a2 >> 12 && v7 != 3 && (v4 || v3 == 1 && !v5) )
  {
    *((_DWORD *)this + 16) = 1;
    CMpegHeader::SetMembers(this);
  }
  else
  {
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    *((_DWORD *)this + 22) = 0;
  }
  return *((unsigned int *)this + 16);
}

```

## disassembly

```asm
0x180006894  mov     [rsp+arg_0], rbx
0x180006899  mov     [rsp+arg_8], rsi
0x18000689e  push    rdi
0x18000689f  sub     rsp, 20h
0x1800068a3  mov     rbx, rcx
0x1800068a6  mov     eax, edx
0x1800068a8  shr     eax, 10h
0x1800068ab  mov     edi, edx
0x1800068ad  not     eax
0x1800068af  shr     edi, 11h
0x1800068b2  and     eax, 1
0x1800068b5  mov     r10d, edx
0x1800068b8  mov     [rcx+18h], eax
0x1800068bb  mov     esi, edx
0x1800068bd  mov     eax, edx
0x1800068bf  shr     r10d, 14h
0x1800068c3  shr     eax, 9
0x1800068c6  mov     r8d, edx
0x1800068c9  and     eax, 1
0x1800068cc  shr     esi, 13h
0x1800068cf  mov     [rbx+24h], eax
0x1800068d2  and     edi, 3
0x1800068d5  mov     eax, edx
0x1800068d7  shr     r8d, 15h
0x1800068db  shr     eax, 8
0x1800068de  and     r10d, 1
0x1800068e2  and     eax, 1
0x1800068e5  mov     [rcx+8], r8d
0x1800068e9  mov     [rbx+28h], eax
0x1800068ec  and     esi, 1
0x1800068ef  mov     [rcx+0Ch], r10d
0x1800068f3  mov     eax, edx
0x1800068f5  shr     eax, 6
0x1800068f8  mov     r9d, edx
0x1800068fb  and     eax, 3
0x1800068fe  mov     [rcx+10h], esi
0x180006901  mov     [rbx+2Ch], eax
0x180006904  mov     r11d, 4
0x18000690a  mov     eax, edx
0x18000690c  shr     r9d, 0Ah
0x180006910  shr     eax, 4
0x180006913  sub     r11d, edi
0x180006916  and     eax, 3
0x180006919  mov     [rcx+14h], r11d
0x18000691d  mov     [rbx+30h], eax
0x180006920  mov     ecx, edx
0x180006922  mov     eax, edx
0x180006924  shr     ecx, 0Ch
0x180006927  shr     eax, 3
0x18000692a  and     ecx, 0Fh
0x18000692d  and     eax, 1
0x180006930  mov     [rbx+1Ch], ecx
0x180006933  mov     [rbx+34h], eax
0x180006936  and     r9d, 3
0x18000693a  mov     eax, edx
0x18000693c  mov     [rbx+20h], r9d
0x180006940  shr     eax, 2
0x180006943  and     edx, 3
0x180006946  and     eax, 1
0x180006949  mov     [rbx+3Ch], edx
0x18000694c  mov     [rbx+38h], eax
0x18000694f  xor     eax, eax
0x180006951  cmp     r8d, 7FFh
0x180006958  jnz     short loc_180006995
0x18000695a  cmp     r11d, 3
0x18000695e  jnz     short loc_180006995
0x180006960  cmp     ecx, 0Fh
0x180006963  jz      short loc_180006995
0x180006965  test    ecx, ecx
0x180006967  jz      short loc_180006995
0x180006969  cmp     r9d, r11d
0x18000696c  jz      short loc_180006995
0x18000696e  test    r10d, r10d
0x180006971  jz      short loc_1800069C2
0x180006973  mov     rcx, rbx; this
0x180006976  mov     dword ptr [rbx+40h], 1
0x18000697d  call    ?SetMembers@CMpegHeader@@AEAAXXZ; CMpegHeader::SetMembers(void)
0x180006982  mov     eax, [rbx+40h]
0x180006985  mov     rbx, [rsp+28h+arg_0]
0x18000698a  mov     rsi, [rsp+28h+arg_8]
0x18000698f  add     rsp, 20h
0x180006993  pop     rdi
0x180006994  retn
0x180006995  mov     [rbx+8], rax
0x180006999  mov     [rbx+10h], rax
0x18000699d  mov     [rbx+18h], rax
0x1800069a1  mov     [rbx+20h], rax
0x1800069a5  mov     [rbx+28h], rax
0x1800069a9  mov     [rbx+30h], rax
0x1800069ad  mov     [rbx+38h], rax
0x1800069b1  mov     [rbx+40h], rax
0x1800069b5  mov     [rbx+48h], rax
0x1800069b9  mov     [rbx+50h], rax
0x1800069bd  mov     [rbx+58h], eax
0x1800069c0  jmp     short loc_180006982
0x1800069c2  cmp     edi, 1
0x1800069c5  jnz     short loc_180006995
0x1800069c7  test    esi, esi
0x1800069c9  jz      short loc_180006973
0x1800069cb  jmp     short loc_180006995
```
