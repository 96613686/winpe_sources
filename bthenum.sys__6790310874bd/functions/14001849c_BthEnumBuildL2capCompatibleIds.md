# BthEnumBuildL2capCompatibleIds

- ea: `0x14001849c`
- end: `0x140018747`
- name: `BthEnumBuildL2capCompatibleIds`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140019058`

## callees

- `0x140001294`
- `0x140007d00`
- `0x140008140`
- `0x14001849c`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x14001863a`
- `ntoskrnl!ExFreePool` at `0x14001863a`
- `ntoskrnl!ExAllocatePool2` at `0x140018608`
- `ntoskrnl!ExAllocatePool2` at `0x140018608`

## pseudocode

```c
__int64 __fastcall BthEnumBuildL2capCompatibleIds(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rax
  NTSTATUS v5; // eax
  __int64 v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rdi
  unsigned int v9; // esi
  unsigned int v10; // ebx
  _WORD *Pool2; // rax
  _WORD *v12; // rdx
  __int64 v13; // r11
  wchar_t *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r8
  _WORD *v17; // r9
  _WORD *v18; // rcx
  _WORD *v19; // r10
  wchar_t *v20; // rax
  __int64 v21; // r8
  _WORD *v22; // r9
  _WORD *v23; // rcx
  __int64 v25; // [rsp+20h] [rbp-E0h]
  _BYTE v26[22]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[104]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v28[104]; // [rsp+120h] [rbp+20h] BYREF

  memset(pszDest, 0, 0xCAu);
  v4 = *(_QWORD *)(a1 + 56);
  *(_OWORD *)v26 = *(_OWORD *)L"_HCIBYPASS";
  *(_QWORD *)&v26[14] = *(_QWORD *)L"ASS";
  if ( *(_DWORD *)(a1 + 2880) )
    v5 = RtlStringCchPrintfW(pszDest, 0x65u, L"%s%s%s", busId, v4, v26);
  else
    v5 = RtlStringCchPrintfW(pszDest, 0x65u, L"%s%s", busId, v4);
  v6 = -1;
  if ( v5 >= 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( pszDest[v8] );
    v7 = v8 + 1;
  }
  else
  {
    v7 = 0;
  }
  memset(v28, 0, 0xCAu);
  *(_WORD *)&v26[16] = aGeneric[8];
  v9 = 0;
  v25 = *(_QWORD *)(a1 + 56);
  *(_OWORD *)v26 = *(_OWORD *)L"_GENERIC";
  if ( RtlStringCchPrintfW(v28, 0x65u, L"%s%s%s", busId, v25, v26) >= 0 )
  {
    do
      ++v6;
    while ( v28[v6] );
    v9 = v6 + 1;
  }
  if ( !v7 || !v9 )
    return (unsigned int)-1073741811;
  v10 = 0;
  Pool2 = (_WORD *)ExAllocatePool2(256, 2LL * (v9 + v7 + 1), 1330467906);
  v12 = Pool2;
  if ( Pool2 )
  {
    if ( v7 <= 0x7FFFFFFFuLL )
    {
      v13 = 2147483646;
      v14 = pszDest;
      v15 = 2147483646;
      v16 = v7;
      v17 = v12;
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v17++ = *v14++;
        --v15;
        --v16;
      }
      while ( v16 );
      v18 = v17 - 1;
      v10 = v16 == 0 ? 0x80000005 : 0;
      if ( v16 )
        v18 = v17;
      *v18 = 0;
      if ( v16 )
      {
        v19 = &v12[v7];
        if ( v9 <= 0x7FFFFFFFuLL )
        {
          v20 = v28;
          v21 = v9;
          v22 = &v12[v7];
          do
          {
            if ( !v13 )
              break;
            if ( !*v20 )
              break;
            *v22++ = *v20++;
            --v13;
            --v21;
          }
          while ( v21 );
          v23 = v22 - 1;
          v10 = v21 == 0 ? 0x80000005 : 0;
          if ( v21 )
            v23 = v22;
          *v23 = 0;
          if ( v21 )
          {
            v19[v9] = 0;
            *a2 = v12;
            return v10;
          }
        }
        else
        {
          *v19 = 0;
        }
        v10 = -1073741811;
      }
    }
    else
    {
      v10 = -1073741811;
      *Pool2 = 0;
    }
    ExFreePool(v12);
  }
  return v10;
}

```

## disassembly

```asm
0x14001849c  mov     [rsp-8+arg_10], rbx
0x1400184a1  push    rbp
0x1400184a2  push    rsi
0x1400184a3  push    rdi
0x1400184a4  push    r12
0x1400184a6  push    r13
0x1400184a8  push    r14
0x1400184aa  push    r15
0x1400184ac  lea     rbp, [rsp-100h]
0x1400184b4  sub     rsp, 200h
0x1400184bb  mov     rax, cs:__security_cookie
0x1400184c2  xor     rax, rsp
0x1400184c5  mov     [rbp+130h+var_40], rax
0x1400184cc  mov     r12, rdx
0x1400184cf  mov     r15, rcx
0x1400184d2  mov     esi, 0CAh
0x1400184d7  lea     rcx, [rsp+230h+pszDest]; void *
0x1400184dc  mov     r8d, esi; Size
0x1400184df  xor     edx, edx; Val
0x1400184e1  call    memset
0x1400184e6  movups  xmm0, xmmword ptr cs:aHcibypass; "_HCIBYPASS"
0x1400184ed  lea     r14d, [rsi-65h]
0x1400184f1  mov     rax, [r15+38h]
0x1400184f5  movsd   xmm1, qword ptr cs:aHcibypass+0Eh; "ASS"
0x1400184fd  lea     r9, busId; "BTHENUM\\"
0x140018504  xor     r13d, r13d
0x140018507  mov     edx, r14d; cchDest
0x14001850a  movups  [rsp+230h+var_200], xmm0
0x14001850f  movsd   qword ptr [rsp+230h+var_200+0Eh], xmm1
0x140018515  cmp     [r15+0B40h], r13d
0x14001851c  jz      short loc_140018540
0x14001851e  lea     rcx, [rsp+230h+var_200]
0x140018523  mov     [rsp+230h+var_208], rcx
0x140018528  lea     r8, aSSS; "%s%s%s"
0x14001852f  lea     rcx, [rsp+230h+pszDest]; pszDest
0x140018534  mov     [rsp+230h+var_210], rax
0x140018539  call    RtlStringCchPrintfW
0x14001853e  jmp     short loc_140018556
0x140018540  lea     r8, aSS_0; "%s%s"
0x140018547  mov     [rsp+230h+var_210], rax
0x14001854c  lea     rcx, [rsp+230h+pszDest]; pszDest
0x140018551  call    RtlStringCchPrintfW
0x140018556  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14001855a  test    eax, eax
0x14001855c  jns     short loc_140018563
0x14001855e  mov     edi, r13d
0x140018561  jmp     short loc_140018577
0x140018563  lea     rax, [rsp+230h+pszDest]
0x140018568  mov     rdi, rbx
0x14001856b  inc     rdi
0x14001856e  cmp     [rax+rdi*2], r13w
0x140018573  jnz     short loc_14001856B
0x140018575  inc     edi
0x140018577  mov     r8, rsi; Size
0x14001857a  lea     rcx, [rbp+130h+var_110]; void *
0x14001857e  xor     edx, edx; Val
0x140018580  call    memset
0x140018585  movzx   eax, word ptr cs:aGeneric+10h; ""
0x14001858c  lea     r9, busId; "BTHENUM\\"
0x140018593  movups  xmm0, xmmword ptr cs:aGeneric; "_GENERIC"
0x14001859a  mov     [rsp+230h+var_1F0], ax
0x14001859f  lea     r8, aSSS; "%s%s%s"
0x1400185a6  lea     rax, [rsp+230h+var_200]
0x1400185ab  mov     rdx, r14; cchDest
0x1400185ae  mov     [rsp+230h+var_208], rax
0x1400185b3  lea     rcx, [rbp+130h+var_110]; pszDest
0x1400185b7  mov     rax, [r15+38h]
0x1400185bb  mov     esi, r13d
0x1400185be  mov     [rsp+230h+var_210], rax
0x1400185c3  movups  [rsp+230h+var_200], xmm0
0x1400185c8  call    RtlStringCchPrintfW
0x1400185cd  test    eax, eax
0x1400185cf  js      short loc_1400185E2
0x1400185d1  lea     rax, [rbp+130h+var_110]
0x1400185d5  inc     rbx
0x1400185d8  cmp     [rax+rbx*2], r13w
0x1400185dd  jnz     short loc_1400185D5
0x1400185df  lea     esi, [rbx+1]
0x1400185e2  test    edi, edi
0x1400185e4  jz      loc_140018715
0x1400185ea  test    esi, esi
0x1400185ec  jz      loc_140018715
0x1400185f2  lea     edx, [rdi+1]
0x1400185f5  mov     ecx, 100h
0x1400185fa  add     edx, esi
0x1400185fc  mov     r8d, 4F4D5442h
0x140018602  add     rdx, rdx
0x140018605  mov     ebx, r13d
0x140018608  call    cs:__imp_ExAllocatePool2
0x14001860f  nop     dword ptr [rax+rax+00h]
0x140018614  mov     rdx, rax
0x140018617  test    rax, rax
0x14001861a  jz      loc_14001871A
0x140018620  mov     r10d, edi
0x140018623  mov     r14d, 7FFFFFFFh
0x140018629  cmp     r10, r14
0x14001862c  jbe     short loc_14001864B
0x14001862e  mov     ebx, 0C000000Dh
0x140018633  mov     [rax], r13w
0x140018637  mov     rcx, rdx; P
0x14001863a  call    cs:__imp_ExFreePool
0x140018641  nop     dword ptr [rax+rax+00h]
0x140018646  jmp     loc_14001871A
0x14001864b  mov     r11d, 7FFFFFFEh
0x140018651  lea     rcx, [rsp+230h+pszDest]
0x140018656  mov     eax, r11d
0x140018659  mov     r8, r10
0x14001865c  mov     r9, rdx
0x14001865f  test    rax, rax
0x140018662  jz      short loc_140018681
0x140018664  movzx   ebx, word ptr [rcx]
0x140018667  test    bx, bx
0x14001866a  jz      short loc_140018681
0x14001866c  mov     [r9], bx
0x140018670  add     rcx, 2
0x140018674  add     r9, 2
0x140018678  dec     rax
0x14001867b  sub     r8, 1
0x14001867f  jnz     short loc_14001865F
0x140018681  mov     rax, r8
0x140018684  lea     rcx, [r9-2]
0x140018688  neg     rax
0x14001868b  mov     r15d, 80000005h
0x140018691  sbb     ebx, ebx
0x140018693  not     ebx
0x140018695  and     ebx, r15d
0x140018698  test    r8, r8
0x14001869b  cmovnz  rcx, r9
0x14001869f  mov     [rcx], r13w
0x1400186a3  jz      short loc_140018637
0x1400186a5  mov     edi, esi
0x1400186a7  lea     r10, [rdx+r10*2]
0x1400186ab  cmp     rdi, r14
0x1400186ae  jbe     short loc_1400186B6
0x1400186b0  mov     [r10], r13w
0x1400186b4  jmp     short loc_140018700
0x1400186b6  lea     rax, [rbp+130h+var_110]
0x1400186ba  mov     r8, rdi
0x1400186bd  mov     r9, r10
0x1400186c0  test    r11, r11
0x1400186c3  jz      short loc_1400186E2
0x1400186c5  movzx   ecx, word ptr [rax]
0x1400186c8  test    cx, cx
0x1400186cb  jz      short loc_1400186E2
0x1400186cd  mov     [r9], cx
0x1400186d1  add     rax, 2
0x1400186d5  add     r9, 2
0x1400186d9  dec     r11
0x1400186dc  sub     r8, 1
0x1400186e0  jnz     short loc_1400186C0
0x1400186e2  mov     rax, r8
0x1400186e5  lea     rcx, [r9-2]
0x1400186e9  neg     rax
0x1400186ec  sbb     ebx, ebx
0x1400186ee  not     ebx
0x1400186f0  and     ebx, r15d
0x1400186f3  test    r8, r8
0x1400186f6  cmovnz  rcx, r9
0x1400186fa  mov     [rcx], r13w
0x1400186fe  jnz     short loc_14001870A
0x140018700  mov     ebx, 0C000000Dh
0x140018705  jmp     loc_140018637
0x14001870a  mov     [r10+rdi*2], r13w
0x14001870f  mov     [r12], rdx
0x140018713  jmp     short loc_14001871A
0x140018715  mov     ebx, 0C000000Dh
0x14001871a  mov     eax, ebx
0x14001871c  mov     rcx, [rbp+130h+var_40]
0x140018723  xor     rcx, rsp; StackCookie
0x140018726  call    __security_check_cookie
0x14001872b  mov     rbx, [rsp+230h+arg_10]
0x140018733  add     rsp, 200h
0x14001873a  pop     r15
0x14001873c  pop     r14
0x14001873e  pop     r13
0x140018740  pop     r12
0x140018742  pop     rdi
0x140018743  pop     rsi
0x140018744  pop     rbp
0x140018745  retn
```
