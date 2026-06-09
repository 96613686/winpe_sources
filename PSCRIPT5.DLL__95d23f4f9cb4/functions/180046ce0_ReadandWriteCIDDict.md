# ReadandWriteCIDDict

- ea: `0x180046ce0`
- end: `0x180046f6c`
- name: `ReadandWriteCIDDict`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180045e88`

## callees

- `0x180001ee0`
- `0x180045a70`
- `0x180046c1c`
- `0x180046ce0`
- `0x180048b5c`
- `0x180048bd0`
- `0x18004cc6c`
- `0x18004e1c8`
- `0x18004e27c`
- `0x18004e324`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall ReadandWriteCIDDict(__int64 a1)
{
  unsigned int v1; // ebp
  unsigned __int16 v3; // r15
  unsigned int v4; // r12d
  unsigned int v5; // r13d
  int v6; // esi
  unsigned int v7; // r14d
  __int64 v8; // rax
  unsigned int v9; // ecx
  __int16 v10; // ax
  unsigned __int16 v11; // si
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned __int16 v16; // ax
  __int64 result; // rax
  int v18; // [rsp+30h] [rbp-68h]
  int v19; // [rsp+34h] [rbp-64h]
  _BYTE v20[16]; // [rsp+38h] [rbp-60h] BYREF

  v1 = 0;
  v18 = *(_DWORD *)(a1 + 1500);
  XCF_ReadBlock(a1, (unsigned int)(*(_DWORD *)(a1 + 7820) + 2), 1);
  v3 = 0;
  v4 = (unsigned __int8)XCF_Read1(a1);
  v5 = v4 + *(_DWORD *)(a1 + 7820) + 3;
  v6 = 1;
  v7 = v5 + v4 * *(unsigned __int16 *)(a1 + 14952);
  if ( *(_WORD *)(a1 + 14952) )
  {
    v8 = a1 + 488;
    do
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(a1 + 352))(v8, 0, 7352);
      XCF_ReadBlock(a1, v5, v4);
      v19 = XCF_Read(a1, v4);
      v5 += v4;
      XCF_ReadBlock(a1, v6 + v7 - 1, (unsigned int)(v19 - v6));
      XCF_ReadDictionary(a1);
      XCF_ReadBlock(a1, *(unsigned int *)(a1 + 7944), *(unsigned int *)(a1 + 7948));
      XCF_ReadDictionary(a1);
      if ( *(_DWORD *)(a1 + 656) )
      {
        ReadTableInfo(a1, (unsigned int)(*(_DWORD *)(a1 + 7944) + *(_DWORD *)(a1 + 660)), a1 + 16 * (v3 + 1082LL));
        v9 = *(_DWORD *)(a1 + 16 * (v3 + 1082LL));
        if ( v9 >= 0x4D8 )
        {
          v10 = 1131;
          if ( v9 >= 0x846C )
            v10 = 0x8000;
        }
        else
        {
          v10 = 107;
        }
        *(_WORD *)(a1 + 2LL * v3 + 21408) = v10;
      }
      if ( *(_BYTE *)(a1 + 7988) == 1 )
        v11 = 5;
      else
        v11 = *(_WORD *)(a1 + 16 * (v3 + 1082LL));
      AssignDictionaryDefaults(a1);
      *(_DWORD *)(a1 + 1500) = v18;
      if ( *(_DWORD *)(a1 + 1132) == 1 )
        v12 = *(_DWORD *)(a1 + 1136);
      else
        LOBYTE(v12) = 0;
      *(_BYTE *)(a1 + v3 + 15008) = v12;
      if ( *(_DWORD *)(a1 + 812) == 1 )
        v13 = *(_DWORD *)(a1 + 816);
      else
        v13 = 0;
      *(_DWORD *)(a1 + 4LL * v3 + 15264) = v13;
      if ( *(_DWORD *)(a1 + 804) == 1 )
        v14 = *(_DWORD *)(a1 + 808);
      else
        v14 = 0;
      *(_DWORD *)(a1 + 4LL * v3 + 16288) = v14;
      XT1_WriteCIDDict(a1, v3, v1, v11);
      v15 = v11;
      ++v3;
      v6 = v19;
      v1 += 4 * v15 + 4;
      v8 = a1 + 488;
    }
    while ( v3 < *(_WORD *)(a1 + 14952) );
  }
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v20, 10, "def%s", "\r\n");
  v16 = (*(__int64 (__fastcall **)(_BYTE *))(a1 + 336))(v20);
  result = XCF_PutData(a1, v20, v16);
  *(_DWORD *)(a1 + 14972) = v1;
  *(_DWORD *)(a1 + 14964) = 0;
  return result;
}

```

## disassembly

```asm
0x180046ce0  push    rbx
0x180046ce2  push    rbp
0x180046ce3  push    rsi
0x180046ce4  push    rdi
0x180046ce5  push    r12
0x180046ce7  push    r13
0x180046ce9  push    r14
0x180046ceb  push    r15
0x180046ced  sub     rsp, 58h
0x180046cf1  mov     rax, cs:__security_cookie
0x180046cf8  xor     rax, rsp
0x180046cfb  mov     [rsp+98h+var_50], rax
0x180046d00  mov     edx, [rcx+1E8Ch]
0x180046d06  xor     ebp, ebp
0x180046d08  mov     eax, [rcx+5DCh]
0x180046d0e  add     edx, 2
0x180046d11  mov     rdi, rcx
0x180046d14  mov     [rsp+98h+var_68], eax
0x180046d18  lea     ebx, [rbp+1]
0x180046d1b  mov     r8d, ebx
0x180046d1e  call    XCF_ReadBlock
0x180046d23  mov     rcx, rdi
0x180046d26  call    XCF_Read1
0x180046d2b  movzx   ecx, word ptr [rdi+3A68h]
0x180046d32  xor     r15d, r15d
0x180046d35  mov     r13d, [rdi+1E8Ch]
0x180046d3c  mov     r14d, ecx
0x180046d3f  movzx   r12d, al
0x180046d43  add     r13d, 3
0x180046d47  imul    r14d, r12d
0x180046d4b  add     r13d, r12d
0x180046d4e  xor     eax, eax
0x180046d50  mov     esi, ebx
0x180046d52  add     r14d, r13d
0x180046d55  cmp     ax, cx
0x180046d58  jnb     loc_180046EF8
0x180046d5e  lea     rax, [rdi+1E8h]
0x180046d65  mov     rcx, rax
0x180046d68  xor     edx, edx
0x180046d6a  mov     rax, [rdi+160h]
0x180046d71  mov     r8d, 1CB8h
0x180046d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d7c  mov     r8d, r12d
0x180046d7f  mov     edx, r13d
0x180046d82  mov     rcx, rdi
0x180046d85  call    XCF_ReadBlock
0x180046d8a  mov     edx, r12d
0x180046d8d  mov     rcx, rdi
0x180046d90  call    XCF_Read
0x180046d95  mov     r8d, eax
0x180046d98  mov     [rsp+98h+var_64], eax
0x180046d9c  lea     edx, [r14-1]
0x180046da0  sub     r8d, esi
0x180046da3  add     edx, esi
0x180046da5  mov     rcx, rdi
0x180046da8  add     r13d, r12d
0x180046dab  call    XCF_ReadBlock
0x180046db0  mov     rcx, rdi
0x180046db3  call    XCF_ReadDictionary
0x180046db8  mov     r8d, [rdi+1F0Ch]
0x180046dbf  mov     rcx, rdi
0x180046dc2  mov     edx, [rdi+1F08h]
0x180046dc8  call    XCF_ReadBlock
0x180046dcd  mov     rcx, rdi
0x180046dd0  call    XCF_ReadDictionary
0x180046dd5  cmp     dword ptr [rdi+290h], 0
0x180046ddc  movzx   ebx, r15w
0x180046de0  jz      short loc_180046E3A
0x180046de2  mov     edx, [rdi+294h]
0x180046de8  lea     r8, [rbx+43Ah]
0x180046def  add     edx, [rdi+1F08h]
0x180046df5  mov     rcx, rdi
0x180046df8  shl     r8, 4
0x180046dfc  add     r8, rdi
0x180046dff  call    ReadTableInfo
0x180046e04  lea     rax, [rbx+43Ah]
0x180046e0b  add     rax, rax
0x180046e0e  mov     ecx, [rdi+rax*8]
0x180046e11  cmp     ecx, 4D8h
0x180046e17  jnb     short loc_180046E20
0x180046e19  mov     eax, 6Bh ; 'k'
0x180046e1e  jmp     short loc_180046E32
0x180046e20  mov     eax, 46Bh
0x180046e25  cmp     ecx, 846Ch
0x180046e2b  jb      short loc_180046E32
0x180046e2d  mov     eax, 8000h
0x180046e32  mov     [rdi+rbx*2+53A0h], ax
0x180046e3a  cmp     byte ptr [rdi+1F34h], 1
0x180046e41  mov     ecx, 43Ah
0x180046e46  mov     rax, rbx
0x180046e49  jnz     short loc_180046E52
0x180046e4b  mov     esi, 5
0x180046e50  jmp     short loc_180046E5C
0x180046e52  add     rax, rcx
0x180046e55  add     rax, rax
0x180046e58  movzx   esi, word ptr [rdi+rax*8]
0x180046e5c  mov     rcx, rdi
0x180046e5f  call    AssignDictionaryDefaults
0x180046e64  mov     eax, [rsp+98h+var_68]
0x180046e68  mov     ecx, 1
0x180046e6d  mov     [rdi+5DCh], eax
0x180046e73  cmp     [rdi+46Ch], ecx
0x180046e79  jnz     short loc_180046E83
0x180046e7b  mov     eax, [rdi+470h]
0x180046e81  jmp     short loc_180046E85
0x180046e83  xor     eax, eax
0x180046e85  mov     [rdi+rbx+3AA0h], al
0x180046e8c  cmp     [rdi+32Ch], ecx
0x180046e92  jnz     short loc_180046E9C
0x180046e94  mov     eax, [rdi+330h]
0x180046e9a  jmp     short loc_180046E9E
0x180046e9c  xor     eax, eax
0x180046e9e  mov     [rdi+rbx*4+3BA0h], eax
0x180046ea5  cmp     [rdi+324h], ecx
0x180046eab  jnz     short loc_180046EB5
0x180046ead  mov     eax, [rdi+328h]
0x180046eb3  jmp     short loc_180046EB7
0x180046eb5  xor     eax, eax
0x180046eb7  movzx   r9d, si
0x180046ebb  mov     [rdi+rbx*4+3FA0h], eax
0x180046ec2  mov     r8d, ebp
0x180046ec5  movzx   edx, r15w
0x180046ec9  mov     rcx, rdi
0x180046ecc  call    XT1_WriteCIDDict
0x180046ed1  movzx   eax, si
0x180046ed4  inc     r15w
0x180046ed8  mov     esi, [rsp+98h+var_64]
0x180046edc  lea     ebp, [rbp+rax*4+0]
0x180046ee0  add     ebp, 4
0x180046ee3  lea     rax, [rdi+1E8h]
0x180046eea  cmp     r15w, [rdi+3A68h]
0x180046ef2  jb      loc_180046D65
0x180046ef8  mov     rax, [rdi+168h]
0x180046eff  lea     r9, asc_180062FDC; "\r\n"
0x180046f06  lea     r8, aDefS; "def%s"
0x180046f0d  mov     edx, 0Ah
0x180046f12  lea     rcx, [rsp+98h+var_60]
0x180046f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f1c  mov     rax, [rdi+150h]
0x180046f23  lea     rcx, [rsp+98h+var_60]
0x180046f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f2d  movzx   r8d, ax
0x180046f31  lea     rdx, [rsp+98h+var_60]
0x180046f36  mov     rcx, rdi
0x180046f39  call    XCF_PutData
0x180046f3e  mov     [rdi+3A7Ch], ebp
0x180046f44  mov     dword ptr [rdi+3A74h], 0
0x180046f4e  mov     rcx, [rsp+98h+var_50]
0x180046f53  xor     rcx, rsp; StackCookie
0x180046f56  call    __security_check_cookie
0x180046f5b  add     rsp, 58h
0x180046f5f  pop     r15
0x180046f61  pop     r14
0x180046f63  pop     r13
0x180046f65  pop     r12
0x180046f67  pop     rdi
0x180046f68  pop     rsi
0x180046f69  pop     rbp
0x180046f6a  pop     rbx
0x180046f6b  retn
```
