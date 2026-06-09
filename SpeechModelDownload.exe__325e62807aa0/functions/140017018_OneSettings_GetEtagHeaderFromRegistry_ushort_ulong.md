# OneSettings::GetEtagHeaderFromRegistry(ushort *,ulong)

- ea: `0x140017018`
- end: `0x1400171c3`
- name: `?GetEtagHeaderFromRegistry@OneSettings@@AEAAJPEAGK@Z`
- size: `427`
- prototype: `__int64 __fastcall(OneSettings *this, unsigned __int16 *, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400168b4`

## callees

- `0x1400030dc`
- `0x140017018`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001707d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140017197`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001707d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140017197`

## pseudocode

```c
__int64 __fastcall OneSettings::GetEtagHeaderFromRegistry(OneSettings *this, unsigned __int16 *a2, DWORD a3)
{
  char *v3; // rdi
  bool v4; // cf
  bool v5; // zf
  const WCHAR *v8; // rdx
  LSTATUS ValueW; // eax
  signed int v10; // ebx
  const wchar_t *v11; // rcx
  __int64 v12; // rbp
  __int64 v13; // rax
  unsigned __int16 *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r14
  unsigned __int16 *v17; // rcx
  unsigned __int64 v18; // r8
  LSTATUS v19; // eax
  DWORD pcbData; // [rsp+A0h] [rbp+18h] BYREF

  pcbData = a3;
  v3 = (char *)this + 128;
  v4 = *((_QWORD *)this + 19) < 7u;
  v5 = *((_QWORD *)this + 19) == 7;
  pcbData = 0;
  if ( v4 || v5 )
    v8 = (const WCHAR *)((char *)this + 128);
  else
    v8 = *(const WCHAR **)v3;
  ValueW = RegGetValueW(*((HKEY *)this + 20), v8, L"ETag", 2u, 0, 0, &pcbData);
  v10 = ValueW;
  if ( !ValueW )
    goto LABEL_8;
  if ( ValueW > 0 )
    v10 = (unsigned __int16)ValueW | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_8:
    if ( pcbData + 30 < 0x208 )
    {
      v11 = L"If-None-Match:";
      v12 = 130;
      v13 = 2147483646;
      v14 = a2;
      v15 = 0;
      do
      {
        if ( !v13 )
          break;
        if ( !*v11 )
          break;
        *v14++ = *v11++;
        --v13;
        ++v15;
        --v12;
      }
      while ( v12 );
      v16 = v15 - 1;
      v17 = v14 - 1;
      if ( v12 )
        v16 = v15;
      v10 = v12 == 0 ? 0x8007007A : 0;
      if ( v12 )
        v17 = v14;
      *v17 = 0;
      if ( v12 )
      {
        v18 = 2 * (130 - v16);
        if ( v18 > 2 )
          memset_0(&a2[v16 + 1], 0, v18 - 2);
        v4 = *((_QWORD *)v3 + 3) < 7u;
        v5 = *((_QWORD *)v3 + 3) == 7;
        pcbData = 2 * (130 - v16);
        if ( !v4 && !v5 )
          v3 = *(char **)v3;
        v19 = RegGetValueW(*((HKEY *)this + 20), (LPCWSTR)v3, L"ETag", 2u, 0, &a2[v16], &pcbData);
        if ( v19 )
        {
          if ( v19 > 0 )
            return (unsigned __int16)v19 | 0x80070000;
          else
            return (unsigned int)v19;
        }
      }
    }
    else
    {
      return (unsigned int)-2147024662;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140017018  mov     rax, rsp
0x14001701b  mov     [rax+18h], r8d
0x14001701f  push    rbx
0x140017020  push    rbp
0x140017021  push    rsi
0x140017022  push    rdi
0x140017023  push    r12
0x140017025  push    r13
0x140017027  push    r14
0x140017029  push    r15
0x14001702b  sub     rsp, 48h
0x14001702f  xor     r13d, r13d
0x140017032  lea     rdi, [rcx+80h]
0x140017039  cmp     qword ptr [rdi+18h], 7
0x14001703e  mov     r12, rdx
0x140017041  mov     r15, rcx
0x140017044  mov     [rax+18h], r13d
0x140017048  jbe     short loc_14001704F
0x14001704a  mov     rdx, [rdi]
0x14001704d  jmp     short loc_140017052
0x14001704f  mov     rdx, rdi; lpSubKey
0x140017052  mov     rcx, [rcx+0A0h]; hkey
0x140017059  lea     rax, [rsp+88h+arg_10]
0x140017061  mov     [rsp+88h+pcbData], rax; pcbData
0x140017066  lea     r8, aEtag; "ETag"
0x14001706d  mov     [rsp+88h+pvData], r13; pvData
0x140017072  mov     r9d, 2; dwFlags
0x140017078  mov     [rsp+88h+pdwType], r13; pdwType
0x14001707d  call    cs:__imp_RegGetValueW
0x140017083  mov     ebx, eax
0x140017085  test    eax, eax
0x140017087  jz      short loc_14001709C
0x140017089  jle     short loc_140017094
0x14001708b  movzx   ebx, ax
0x14001708e  or      ebx, 80070000h
0x140017094  test    ebx, ebx
0x140017096  js      loc_1400171B0
0x14001709c  mov     eax, [rsp+88h+arg_10]
0x1400170a3  add     eax, 1Eh
0x1400170a6  cmp     eax, 208h
0x1400170ab  jb      short loc_1400170B7
0x1400170ad  mov     ebx, 800700EAh
0x1400170b2  jmp     loc_1400171B0
0x1400170b7  mov     esi, 82h
0x1400170bc  lea     rcx, aIfNoneMatch; "If-None-Match:"
0x1400170c3  mov     ebp, esi
0x1400170c5  mov     eax, 7FFFFFFEh
0x1400170ca  mov     rdx, r12
0x1400170cd  mov     r8, r13
0x1400170d0  test    rax, rax
0x1400170d3  jz      short loc_1400170F7
0x1400170d5  movzx   r9d, word ptr [rcx]
0x1400170d9  test    r9w, r9w
0x1400170dd  jz      short loc_1400170F7
0x1400170df  mov     [rdx], r9w
0x1400170e3  add     rcx, 2
0x1400170e7  add     rdx, 2
0x1400170eb  dec     rax
0x1400170ee  inc     r8
0x1400170f1  sub     rbp, 1
0x1400170f5  jnz     short loc_1400170D0
0x1400170f7  test    rbp, rbp
0x1400170fa  lea     r14, [r8-1]
0x1400170fe  mov     rax, rbp
0x140017101  lea     rcx, [rdx-2]
0x140017105  cmovnz  r14, r8
0x140017109  neg     rax
0x14001710c  sbb     ebx, ebx
0x14001710e  not     ebx
0x140017110  and     ebx, 8007007Ah
0x140017116  test    rbp, rbp
0x140017119  cmovnz  rcx, rdx
0x14001711d  mov     [rcx], r13w
0x140017121  lea     r13, [r12+r14*2]
0x140017125  jz      loc_1400171B0
0x14001712b  mov     rax, rsi
0x14001712e  sub     rax, r14
0x140017131  lea     r8, [rax+rax]
0x140017135  cmp     r8, 2
0x140017139  jbe     short loc_14001714A
0x14001713b  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x14001713f  lea     rcx, [r13+2]; void *
0x140017143  xor     edx, edx; Val
0x140017145  call    memset_0
0x14001714a  test    rbp, rbp
0x14001714d  jz      short loc_1400171B0
0x14001714f  sub     esi, r14d
0x140017152  add     esi, esi
0x140017154  cmp     qword ptr [rdi+18h], 7
0x140017159  mov     [rsp+88h+arg_10], esi
0x140017160  jbe     short loc_140017165
0x140017162  mov     rdi, [rdi]
0x140017165  mov     rcx, [r15+0A0h]; hkey
0x14001716c  lea     rax, [rsp+88h+arg_10]
0x140017174  mov     [rsp+88h+pcbData], rax; pcbData
0x140017179  lea     r8, aEtag; "ETag"
0x140017180  mov     [rsp+88h+pvData], r13; pvData
0x140017185  mov     r9d, 2; dwFlags
0x14001718b  mov     rdx, rdi; lpSubKey
0x14001718e  mov     [rsp+88h+pdwType], 0; pdwType
0x140017197  call    cs:__imp_RegGetValueW
0x14001719d  test    eax, eax
0x14001719f  jz      short loc_1400171B0
0x1400171a1  jg      short loc_1400171A7
0x1400171a3  mov     ebx, eax
0x1400171a5  jmp     short loc_1400171B0
0x1400171a7  movzx   ebx, ax
0x1400171aa  or      ebx, 80070000h
0x1400171b0  mov     eax, ebx
0x1400171b2  add     rsp, 48h
0x1400171b6  pop     r15
0x1400171b8  pop     r14
0x1400171ba  pop     r13
0x1400171bc  pop     r12
0x1400171be  pop     rdi
0x1400171bf  pop     rsi
0x1400171c0  pop     rbp
0x1400171c1  pop     rbx
0x1400171c2  retn
```
