# WriteSubrs

- ea: `0x18004de80`
- end: `0x18004e036`
- name: `WriteSubrs`
- size: `438`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004d3a8`

## callees

- `0x180001f20`
- `0x18004ac9c`
- `0x18004b690`
- `0x18004b714`
- `0x18004c1c4`
- `0x18004de80`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall WriteSubrs(__int64 a1, int a2)
{
  __int64 result; // rax
  unsigned int v5; // esi
  unsigned __int16 v6; // r15
  unsigned int i; // r12d
  unsigned int v8; // ebx
  __int64 v9; // [rsp+20h] [rbp-49h]
  unsigned __int16 v10; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int8 *v11; // [rsp+38h] [rbp-31h] BYREF
  _OWORD v12[3]; // [rsp+40h] [rbp-29h] BYREF
  __int16 v13; // [rsp+70h] [rbp+7h]

  result = 0;
  v13 = 0;
  v11 = 0;
  v10 = 0;
  memset(v12, 0, sizeof(v12));
  if ( a2 )
    v5 = *(_DWORD *)(a1 + 6820);
  else
    v5 = *(_DWORD *)(a1 + 14328) - 1;
  if ( !v5 )
  {
    if ( !*(_DWORD *)(a1 + 488) || !a2 )
      return result;
    goto LABEL_9;
  }
  if ( a2 )
  {
LABEL_9:
    if ( *(int *)(a1 + 488) > 0 )
      LODWORD(result) = 2;
  }
  (*(void (**)(_OWORD *, __int64, const char *, ...))(a1 + 360))(
    v12,
    50,
    "/Subrs %u  array\r\n",
    (unsigned int)result + v5);
  PutString(a1, (__int64)v12);
  v6 = *(_WORD *)(a1 + 7976);
  if ( v6 == 0xFFFF )
    v6 = 0;
  for ( i = 0; i < v5; ++i )
  {
    GetSubr(a1, i, a2, &v11, &v10);
    v8 = v10;
    LODWORD(v9) = v10 + v6;
    (*(void (**)(_OWORD *, __int64, const char *, ...))(a1 + 360))(v12, 50, "dup %ld %lu -| ", i, v9);
    PutString(a1, (__int64)v12);
    PutType1CharString(a1, v11, v8);
    PutString(a1, (__int64)" |\r\n");
  }
  if ( a2 )
  {
    if ( *(int *)(a1 + 488) > 0 )
    {
      WriteDVSubr(a1, v5, *(_WORD *)(a1 + 558), v6);
      WriteDVSubr(a1, v5 + 1, *(_WORD *)(a1 + 556), v6);
    }
  }
  return PutString(a1, (__int64)"|-\r\n");
}

```

## disassembly

```asm
0x18004de80  push    rbp
0x18004de82  push    rbx
0x18004de83  push    rsi
0x18004de84  push    rdi
0x18004de85  push    r12
0x18004de87  push    r13
0x18004de89  push    r14
0x18004de8b  push    r15
0x18004de8d  lea     rbp, [rsp-1Fh]
0x18004de92  sub     rsp, 88h
0x18004de99  mov     rax, cs:__security_cookie
0x18004dea0  xor     rax, rsp
0x18004dea3  mov     [rbp+57h+var_48], rax
0x18004dea7  xor     eax, eax
0x18004dea9  xorps   xmm0, xmm0
0x18004deac  mov     [rbp+57h+var_50], ax
0x18004deb0  mov     r14d, edx
0x18004deb3  mov     [rbp+57h+var_88], rax
0x18004deb7  mov     rdi, rcx
0x18004deba  mov     [rbp+57h+var_90], ax
0x18004debe  movups  [rbp+57h+var_80], xmm0
0x18004dec2  movups  [rbp+57h+var_70], xmm0
0x18004dec6  movups  [rbp+57h+var_60], xmm0
0x18004deca  test    edx, edx
0x18004decc  jz      short loc_18004DED6
0x18004dece  mov     esi, [rcx+1AA4h]
0x18004ded4  jmp     short loc_18004DEDE
0x18004ded6  mov     esi, [rcx+37F8h]
0x18004dedc  dec     esi
0x18004dede  test    esi, esi
0x18004dee0  jnz     short loc_18004DEF8
0x18004dee2  cmp     [rcx+1E8h], eax
0x18004dee8  jz      loc_18004E015
0x18004deee  test    r14d, r14d
0x18004def1  jnz     short loc_18004DEFD
0x18004def3  jmp     loc_18004E015
0x18004def8  test    r14d, r14d
0x18004defb  jz      short loc_18004DF0A
0x18004defd  cmp     [rcx+1E8h], eax
0x18004df03  jle     short loc_18004DF0A
0x18004df05  mov     eax, 2
0x18004df0a  lea     r9d, [rax+rsi]
0x18004df0e  mov     edx, 32h ; '2'
0x18004df13  mov     rax, [rdi+168h]
0x18004df1a  lea     r8, aSubrsUArray; "/Subrs %u  array\r\n"
0x18004df21  lea     rcx, [rbp+57h+var_80]
0x18004df25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df2a  lea     rdx, [rbp+57h+var_80]
0x18004df2e  mov     rcx, rdi
0x18004df31  call    PutString
0x18004df36  movzx   r15d, word ptr [rdi+1F28h]
0x18004df3e  cmp     r15w, 0FFFFh
0x18004df43  jnz     short loc_18004DF48
0x18004df45  xor     r15d, r15d
0x18004df48  xor     r12d, r12d
0x18004df4b  test    esi, esi
0x18004df4d  jz      short loc_18004DFCB
0x18004df4f  movzx   r13d, r15w
0x18004df53  lea     rax, [rbp+57h+var_90]
0x18004df57  mov     r8d, r14d
0x18004df5a  lea     r9, [rbp+57h+var_88]
0x18004df5e  mov     [rsp+0C0h+var_A0], rax
0x18004df63  mov     edx, r12d
0x18004df66  mov     rcx, rdi
0x18004df69  call    GetSubr
0x18004df6e  movzx   ebx, [rbp+57h+var_90]
0x18004df72  lea     r8, aDupLdLu; "dup %ld %lu -| "
0x18004df79  mov     rax, [rdi+168h]
0x18004df80  mov     r9d, r12d
0x18004df83  mov     edx, 32h ; '2'
0x18004df88  lea     ecx, [rbx+r13]
0x18004df8c  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x18004df90  lea     rcx, [rbp+57h+var_80]
0x18004df94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df99  lea     rdx, [rbp+57h+var_80]
0x18004df9d  mov     rcx, rdi
0x18004dfa0  call    PutString
0x18004dfa5  mov     rdx, [rbp+57h+var_88]
0x18004dfa9  mov     r8d, ebx
0x18004dfac  mov     rcx, rdi
0x18004dfaf  call    PutType1CharString
0x18004dfb4  lea     rdx, asc_18006CA4C; " |\r\n"
0x18004dfbb  mov     rcx, rdi
0x18004dfbe  call    PutString
0x18004dfc3  inc     r12d
0x18004dfc6  cmp     r12d, esi
0x18004dfc9  jb      short loc_18004DF53
0x18004dfcb  test    r14d, r14d
0x18004dfce  jz      short loc_18004E006
0x18004dfd0  cmp     dword ptr [rdi+1E8h], 0
0x18004dfd7  jle     short loc_18004E006
0x18004dfd9  movzx   r8d, word ptr [rdi+22Eh]
0x18004dfe1  movzx   r9d, r15w
0x18004dfe5  mov     edx, esi
0x18004dfe7  mov     rcx, rdi
0x18004dfea  call    WriteDVSubr
0x18004dfef  movzx   r8d, word ptr [rdi+22Ch]
0x18004dff7  lea     edx, [rsi+1]
0x18004dffa  movzx   r9d, r15w
0x18004dffe  mov     rcx, rdi
0x18004e001  call    WriteDVSubr
0x18004e006  lea     rdx, asc_18006CA84; "|-\r\n"
0x18004e00d  mov     rcx, rdi
0x18004e010  call    PutString
0x18004e015  mov     rcx, [rbp+57h+var_48]
0x18004e019  xor     rcx, rsp; StackCookie
0x18004e01c  call    __security_check_cookie
0x18004e021  add     rsp, 88h
0x18004e028  pop     r15
0x18004e02a  pop     r14
0x18004e02c  pop     r13
0x18004e02e  pop     r12
0x18004e030  pop     rdi
0x18004e031  pop     rsi
0x18004e032  pop     rbx
0x18004e033  pop     rbp
0x18004e034  retn
```
