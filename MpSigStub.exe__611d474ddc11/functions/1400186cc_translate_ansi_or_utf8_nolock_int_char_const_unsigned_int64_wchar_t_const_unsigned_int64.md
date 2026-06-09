# translate_ansi_or_utf8_nolock(int,char * const,unsigned __int64,wchar_t * const,unsigned __int64)

- ea: `0x1400186cc`
- end: `0x14001899b`
- name: `?translate_ansi_or_utf8_nolock@@YAHHQEAD_KQEA_W1@Z`
- size: `719`
- prototype: `__int64 __fastcall(unsigned int, char *const, __int64, wchar_t *const, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140018abc`

## callees

- `0x14000f9fc`
- `0x14000fa6c`
- `0x1400149ac`
- `0x1400186cc`
- `0x14001a72c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001894a`
- `KERNEL32!GetLastError` at `0x14001894a`
- `KERNEL32!ReadFile` at `0x1400187a3`
- `KERNEL32!ReadFile` at `0x1400187a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall translate_ansi_or_utf8_nolock(
        unsigned int a1,
        char *const a2,
        __int64 a3,
        wchar_t *const a4,
        unsigned __int64 a5)
{
  __int64 v6; // rbp
  __int64 v9; // rdi
  __int64 v10; // rax
  void *v11; // r10
  char *v12; // r9
  char *v13; // rax
  char *v14; // rbx
  char v15; // cl
  char *v16; // rdx
  __int64 v17; // rcx
  char v18; // cl
  __int64 v19; // rdx
  char v20; // al
  unsigned int v21; // ebx
  __int64 result; // rax
  __int64 v23; // r8
  char *v24; // rcx
  char *v25; // rbx
  __int64 i; // rdx
  __int64 v27; // rcx
  char v28; // cl
  char v29; // cl
  unsigned int v30; // ebx
  int v31; // eax
  DWORD LastError; // eax
  __int64 v33; // rdx
  char v34; // cl
  char Buffer; // [rsp+60h] [rbp+8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp+10h] BYREF

  v6 = (__int64)(int)a1 >> 6;
  v9 = 9LL * (a1 & 0x3F);
  v10 = qword_1400D69C0[v6];
  v11 = *(void **)(v10 + 72LL * (a1 & 0x3F) + 40);
  if ( a3 && *a2 == 10 )
    *(_BYTE *)(v10 + 72LL * (a1 & 0x3F) + 56) |= 4u;
  else
    *(_BYTE *)(v10 + 72LL * (a1 & 0x3F) + 56) &= ~4u;
  v12 = &a2[a3];
  v13 = a2;
  v14 = a2;
  if ( a2 >= &a2[a3] )
    goto LABEL_31;
  while ( 1 )
  {
    v15 = *v13;
    if ( *v13 == 26 )
    {
      v19 = qword_1400D69C0[v6];
      v20 = *(_BYTE *)(v19 + 8 * v9 + 56);
      if ( (v20 & 0x40) == 0 )
      {
        *(_BYTE *)(v19 + 8 * v9 + 56) = v20 | 2;
        goto LABEL_31;
      }
      *v14 = 26;
      goto LABEL_30;
    }
    v16 = v13 + 1;
    if ( v15 == 13 )
      break;
    ++v13;
    *v14 = v15;
LABEL_14:
    ++v14;
    if ( v13 >= v12 )
      goto LABEL_31;
  }
  if ( v16 < v12 )
  {
    if ( *v16 == 10 )
    {
      *v14 = 10;
      v17 = 2;
    }
    else
    {
      *v14 = 13;
      v17 = 1;
    }
    v13 += v17;
    goto LABEL_14;
  }
  Buffer = 0;
  NumberOfBytesRead = 0;
  if ( ReadFile(v11, &Buffer, 1u, &NumberOfBytesRead, 0) && NumberOfBytesRead )
  {
    if ( (*(_BYTE *)(qword_1400D69C0[v6] + 8 * v9 + 56) & 0x48) != 0 )
    {
      v18 = Buffer;
      if ( Buffer == 10 )
      {
LABEL_20:
        *v14 = 10;
        goto LABEL_30;
      }
      *v14 = 13;
      *(_BYTE *)(qword_1400D69C0[v6] + 8 * v9 + 58) = v18;
    }
    else
    {
      if ( Buffer == 10 && v14 == a2 )
        goto LABEL_20;
      lseeki64_nolock(a1, -1, 1);
      if ( Buffer == 10 )
        goto LABEL_31;
      *v14 = 13;
    }
  }
  else
  {
    *v14 = 13;
  }
LABEL_30:
  LODWORD(v14) = (_DWORD)v14 + 1;
LABEL_31:
  v21 = (_DWORD)v14 - (_DWORD)a2;
  if ( !v21 )
    return 0;
  v23 = qword_1400D69C0[v6];
  if ( !*(_BYTE *)(v23 + 8 * v9 + 57) )
    return v21;
  v24 = &a2[v21];
  v25 = v24 - 1;
  if ( *(v24 - 1) >= 0 )
  {
    LODWORD(v25) = (_DWORD)v24;
    goto LABEL_54;
  }
  for ( i = 1;
        !*((_BYTE *)&qword_1400D67C8[1] + (unsigned __int8)*v25) && (unsigned int)i <= 4 && v25 >= a2;
        i = (unsigned int)(i + 1) )
  {
    --v25;
  }
  v27 = (unsigned __int8)*v25;
  if ( !*((_BYTE *)&qword_1400D67C8[1] + v27) )
  {
    *(_DWORD *)sub_14000FA6C(v27, i) = 42;
    return 0xFFFFFFFFLL;
  }
  if ( *((char *)&qword_1400D67C8[1] + v27) + 1 == (_DWORD)i )
  {
    LODWORD(v25) = i + (_DWORD)v25;
  }
  else if ( (*(_BYTE *)(v23 + 8 * v9 + 56) & 0x48) != 0 )
  {
    ++v25;
    *(_BYTE *)(v23 + 8 * v9 + 58) = v27;
    if ( (unsigned int)i >= 2 )
    {
      v28 = *v25++;
      *(_BYTE *)(qword_1400D69C0[v6] + 8 * v9 + 59) = v28;
    }
    if ( (_DWORD)i == 3 )
    {
      v29 = *v25;
      LODWORD(v25) = (_DWORD)v25 + 1;
      *(_BYTE *)(qword_1400D69C0[v6] + 8 * v9 + 60) = v29;
    }
    LODWORD(v25) = (_DWORD)v25 - i;
  }
  else
  {
    lseeki64_nolock(a1, -(int)i, 1);
  }
LABEL_54:
  v30 = (_DWORD)v25 - (_DWORD)a2;
  v31 = _acrt_MultiByteToWideChar(65001, 0, a2, v30, a4, a5);
  if ( v31 )
  {
    v33 = qword_1400D69C0[v6];
    v34 = *(_BYTE *)(v33 + 8 * v9 + 61) & 0xFD | (v30 != v31 ? 2 : 0);
    result = (unsigned int)(2 * v31);
    *(_BYTE *)(v33 + 8 * v9 + 61) = v34;
  }
  else
  {
    LastError = GetLastError();
    sub_14000F9FC(LastError);
    return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x1400186cc  mov     [rsp+arg_10], rbx
0x1400186d1  mov     [rsp+arg_18], rbp
0x1400186d6  push    rsi
0x1400186d7  push    rdi
0x1400186d8  push    r12
0x1400186da  push    r14
0x1400186dc  push    r15
0x1400186de  sub     rsp, 30h
0x1400186e2  movsxd  r14, ecx
0x1400186e5  lea     r11, cs:140000000h
0x1400186ec  mov     rax, r14
0x1400186ef  mov     rbp, r14
0x1400186f2  and     eax, 3Fh
0x1400186f5  sar     rbp, 6
0x1400186f9  mov     r15, r9
0x1400186fc  mov     rsi, rdx
0x1400186ff  lea     rdi, [rax+rax*8]
0x140018703  mov     rax, rva qword_1400D69C0[r11+rbp*8]
0x14001870b  mov     r10, [rax+rdi*8+28h]
0x140018710  test    r8, r8
0x140018713  jz      short loc_140018721
0x140018715  cmp     byte ptr [rdx], 0Ah
0x140018718  jnz     short loc_140018721
0x14001871a  or      byte ptr [rax+rdi*8+38h], 4
0x14001871f  jmp     short loc_140018726
0x140018721  and     byte ptr [rax+rdi*8+38h], 0FBh
0x140018726  lea     r9, [rdx+r8]
0x14001872a  mov     rax, rsi
0x14001872d  mov     rbx, rsi
0x140018730  mov     r12d, 1
0x140018736  cmp     rsi, r9
0x140018739  jnb     loc_140018840
0x14001873f  mov     cl, [rax]
0x140018741  cmp     cl, 1Ah
0x140018744  jz      loc_140018823
0x14001874a  lea     rdx, [rax+1]
0x14001874e  cmp     cl, 0Dh
0x140018751  jz      short loc_14001875A
0x140018753  mov     rax, rdx
0x140018756  mov     [rbx], cl
0x140018758  jmp     short loc_140018777
0x14001875a  cmp     rdx, r9
0x14001875d  jnb     short loc_140018784
0x14001875f  cmp     byte ptr [rdx], 0Ah
0x140018762  jnz     short loc_14001876E
0x140018764  mov     byte ptr [rbx], 0Ah
0x140018767  mov     ecx, 2
0x14001876c  jmp     short loc_140018774
0x14001876e  mov     byte ptr [rbx], 0Dh
0x140018771  mov     rcx, r12
0x140018774  add     rax, rcx
0x140018777  inc     rbx
0x14001877a  cmp     rax, r9
0x14001877d  jb      short loc_14001873F
0x14001877f  jmp     loc_140018840
0x140018784  xor     eax, eax
0x140018786  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14001878b  mov     r8d, r12d; nNumberOfBytesToRead
0x14001878e  mov     [rsp+58h+Buffer], al
0x140018792  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x140018797  mov     [rsp+58h+NumberOfBytesRead], eax
0x14001879b  mov     rcx, r10; hFile
0x14001879e  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x1400187a3  call    cs:ReadFile
0x1400187a9  test    eax, eax
0x1400187ab  jz      short loc_140018817
0x1400187ad  cmp     [rsp+58h+NumberOfBytesRead], 0
0x1400187b2  jz      short loc_140018817
0x1400187b4  lea     r11, cs:140000000h
0x1400187bb  mov     rax, rva qword_1400D69C0[r11+rbp*8]
0x1400187c3  test    byte ptr [rax+rdi*8+38h], 48h
0x1400187c8  jz      short loc_1400187E9
0x1400187ca  mov     cl, [rsp+58h+Buffer]
0x1400187ce  cmp     cl, 0Ah
0x1400187d1  jnz     short loc_1400187D8
0x1400187d3  mov     byte ptr [rbx], 0Ah
0x1400187d6  jmp     short loc_14001883D
0x1400187d8  mov     byte ptr [rbx], 0Dh
0x1400187db  mov     rax, rva qword_1400D69C0[r11+rbp*8]
0x1400187e3  mov     [rax+rdi*8+3Ah], cl
0x1400187e7  jmp     short loc_14001883D
0x1400187e9  cmp     [rsp+58h+Buffer], 0Ah
0x1400187ee  jnz     short loc_1400187F5
0x1400187f0  cmp     rbx, rsi
0x1400187f3  jz      short loc_1400187D3
0x1400187f5  mov     r8d, r12d
0x1400187f8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400187fc  mov     ecx, r14d
0x1400187ff  call    _lseeki64_nolock
0x140018804  cmp     [rsp+58h+Buffer], 0Ah
0x140018809  lea     r11, cs:140000000h
0x140018810  jz      short loc_140018840
0x140018812  mov     byte ptr [rbx], 0Dh
0x140018815  jmp     short loc_14001883D
0x140018817  mov     byte ptr [rbx], 0Dh
0x14001881a  lea     r11, cs:140000000h
0x140018821  jmp     short loc_14001883D
0x140018823  mov     rdx, rva qword_1400D69C0[r11+rbp*8]
0x14001882b  mov     al, [rdx+rdi*8+38h]
0x14001882f  test    al, 40h
0x140018831  jnz     short loc_14001883B
0x140018833  or      al, 2
0x140018835  mov     [rdx+rdi*8+38h], al
0x140018839  jmp     short loc_140018840
0x14001883b  mov     [rbx], cl
0x14001883d  add     rbx, r12
0x140018840  sub     ebx, esi
0x140018842  jnz     short loc_14001884B
0x140018844  xor     eax, eax
0x140018846  jmp     loc_140018984
0x14001884b  mov     r8, rva qword_1400D69C0[r11+rbp*8]
0x140018853  cmp     byte ptr [r8+rdi*8+39h], 0
0x140018859  jnz     short loc_140018862
0x14001885b  mov     eax, ebx
0x14001885d  jmp     loc_140018984
0x140018862  movsxd  rcx, ebx
0x140018865  add     rcx, rsi
0x140018868  lea     rbx, [rcx-1]
0x14001886c  cmp     byte ptr [rbx], 0
0x14001886f  jl      short loc_140018879
0x140018871  mov     rbx, rcx
0x140018874  jmp     loc_14001891F
0x140018879  mov     edx, r12d
0x14001887c  jmp     short loc_14001888E
0x14001887e  cmp     edx, 4
0x140018881  ja      short loc_14001889C
0x140018883  cmp     rbx, rsi
0x140018886  jb      short loc_14001889C
0x140018888  sub     rbx, r12
0x14001888b  add     edx, r12d
0x14001888e  movzx   eax, byte ptr [rbx]
0x140018891  cmp     byte ptr [rax+r11+0D67D0h], 0
0x14001889a  jz      short loc_14001887E
0x14001889c  movzx   ecx, byte ptr [rbx]
0x14001889f  movsx   eax, byte ptr [rcx+r11+0D67D0h]
0x1400188a8  test    eax, eax
0x1400188aa  jnz     short loc_1400188BF
0x1400188ac  call    sub_14000FA6C
0x1400188b1  mov     dword ptr [rax], 2Ah ; '*'
0x1400188b7  or      eax, 0FFFFFFFFh
0x1400188ba  jmp     loc_140018984
0x1400188bf  inc     eax
0x1400188c1  cmp     eax, edx
0x1400188c3  jnz     short loc_1400188CC
0x1400188c5  mov     eax, edx
0x1400188c7  add     rbx, rax
0x1400188ca  jmp     short loc_14001891F
0x1400188cc  test    byte ptr [r8+rdi*8+38h], 48h
0x1400188d2  jz      short loc_14001890F
0x1400188d4  add     rbx, r12
0x1400188d7  mov     [r8+rdi*8+3Ah], cl
0x1400188dc  cmp     edx, 2
0x1400188df  jb      short loc_1400188F2
0x1400188e1  mov     cl, [rbx]
0x1400188e3  add     rbx, r12
0x1400188e6  mov     rax, rva qword_1400D69C0[r11+rbp*8]
0x1400188ee  mov     [rax+rdi*8+3Bh], cl
0x1400188f2  cmp     edx, 3
0x1400188f5  jnz     short loc_140018908
0x1400188f7  mov     cl, [rbx]
0x1400188f9  add     rbx, r12
0x1400188fc  mov     rax, rva qword_1400D69C0[r11+rbp*8]
0x140018904  mov     [rax+rdi*8+3Ch], cl
0x140018908  mov     eax, edx
0x14001890a  sub     rbx, rax
0x14001890d  jmp     short loc_14001891F
0x14001890f  neg     edx
0x140018911  mov     r8d, r12d
0x140018914  movsxd  rdx, edx
0x140018917  mov     ecx, r14d
0x14001891a  call    _lseeki64_nolock
0x14001891f  mov     eax, dword ptr [rsp+58h+arg_20]
0x140018926  sub     ebx, esi
0x140018928  mov     [rsp+58h+var_30], eax
0x14001892c  mov     r9d, ebx
0x14001892f  mov     r8, rsi
0x140018932  mov     [rsp+58h+lpOverlapped], r15
0x140018937  xor     edx, edx
0x140018939  mov     ecx, 0FDE9h
0x14001893e  call    __acrt_MultiByteToWideChar
0x140018943  mov     r8d, eax
0x140018946  test    eax, eax
0x140018948  jnz     short loc_14001895C
0x14001894a  call    cs:GetLastError
0x140018950  mov     ecx, eax
0x140018952  call    sub_14000F9FC
0x140018957  jmp     loc_1400188B7
0x14001895c  sub     eax, ebx
0x14001895e  lea     rdx, cs:140000000h
0x140018965  mov     rdx, rva qword_1400D69C0[rdx+rbp*8]
0x14001896d  neg     eax
0x14001896f  sbb     cl, cl
0x140018971  and     cl, 2
0x140018974  mov     al, [rdx+rdi*8+3Dh]
0x140018978  and     al, 0FDh
0x14001897a  or      cl, al
0x14001897c  lea     eax, [r8+r8]
0x140018980  mov     [rdx+rdi*8+3Dh], cl
0x140018984  mov     rbx, [rsp+58h+arg_10]
0x140018989  mov     rbp, [rsp+58h+arg_18]
0x14001898e  add     rsp, 30h
0x140018992  pop     r15
0x140018994  pop     r14
0x140018996  pop     r12
0x140018998  pop     rdi
0x140018999  pop     rsi
0x14001899a  retn
```
