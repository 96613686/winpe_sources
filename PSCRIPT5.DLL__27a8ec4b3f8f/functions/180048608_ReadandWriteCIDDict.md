# ReadandWriteCIDDict

- ea: `0x180048608`
- end: `0x180048895`
- name: `ReadandWriteCIDDict`
- size: `653`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800477ac`

## callees

- `0x180001f20`
- `0x180047390`
- `0x180048544`
- `0x180048608`
- `0x18004a3cc`
- `0x18004a440`
- `0x18004e4fc`
- `0x18004fa68`
- `0x18004fb1c`
- `0x18004fbc4`
- `0x18005f010`

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
  v4 = (unsigned __int8)XCF_Read1((_JBTYPE *)a1);
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
      v19 = XCF_Read((_JBTYPE *)a1, v4);
      v5 += v4;
      XCF_ReadBlock(a1, v6 + v7 - 1, (unsigned int)(v19 - v6));
      XCF_ReadDictionary(a1);
      XCF_ReadBlock(a1, *(unsigned int *)(a1 + 7944), *(unsigned int *)(a1 + 7948));
      XCF_ReadDictionary(a1);
      if ( *(_DWORD *)(a1 + 656) )
      {
        ReadTableInfo(
          a1,
          (unsigned int)(*(_DWORD *)(a1 + 7944) + *(_DWORD *)(a1 + 660)),
          (_DWORD *)(a1 + 16 * (v3 + 1082LL)));
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
  result = XCF_PutData(a1, (__int64)v20, v16);
  *(_DWORD *)(a1 + 14972) = v1;
  *(_DWORD *)(a1 + 14964) = 0;
  return result;
}

```

## disassembly

```asm
0x180048608  push    rbx
0x18004860a  push    rbp
0x18004860b  push    rsi
0x18004860c  push    rdi
0x18004860d  push    r12
0x18004860f  push    r13
0x180048611  push    r14
0x180048613  push    r15
0x180048615  sub     rsp, 58h
0x180048619  mov     rax, cs:__security_cookie
0x180048620  xor     rax, rsp
0x180048623  mov     [rsp+98h+var_50], rax
0x180048628  mov     edx, [rcx+1E8Ch]
0x18004862e  xor     ebp, ebp
0x180048630  mov     eax, [rcx+5DCh]
0x180048636  add     edx, 2
0x180048639  mov     rdi, rcx
0x18004863c  mov     [rsp+98h+var_68], eax
0x180048640  lea     ebx, [rbp+1]
0x180048643  mov     r8d, ebx
0x180048646  call    XCF_ReadBlock
0x18004864b  mov     rcx, rdi
0x18004864e  call    XCF_Read1
0x180048653  movzx   ecx, word ptr [rdi+3A68h]
0x18004865a  xor     r15d, r15d
0x18004865d  mov     r13d, [rdi+1E8Ch]
0x180048664  mov     r14d, ecx
0x180048667  movzx   r12d, al
0x18004866b  add     r13d, 3
0x18004866f  imul    r14d, r12d
0x180048673  add     r13d, r12d
0x180048676  xor     eax, eax
0x180048678  mov     esi, ebx
0x18004867a  add     r14d, r13d
0x18004867d  cmp     ax, cx
0x180048680  jnb     loc_180048820
0x180048686  lea     rax, [rdi+1E8h]
0x18004868d  mov     rcx, rax
0x180048690  xor     edx, edx
0x180048692  mov     rax, [rdi+160h]
0x180048699  mov     r8d, 1CB8h
0x18004869f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486a4  mov     r8d, r12d
0x1800486a7  mov     edx, r13d
0x1800486aa  mov     rcx, rdi
0x1800486ad  call    XCF_ReadBlock
0x1800486b2  mov     edx, r12d
0x1800486b5  mov     rcx, rdi
0x1800486b8  call    XCF_Read
0x1800486bd  mov     r8d, eax
0x1800486c0  mov     [rsp+98h+var_64], eax
0x1800486c4  lea     edx, [r14-1]
0x1800486c8  sub     r8d, esi
0x1800486cb  add     edx, esi
0x1800486cd  mov     rcx, rdi
0x1800486d0  add     r13d, r12d
0x1800486d3  call    XCF_ReadBlock
0x1800486d8  mov     rcx, rdi
0x1800486db  call    XCF_ReadDictionary
0x1800486e0  mov     r8d, [rdi+1F0Ch]
0x1800486e7  mov     rcx, rdi
0x1800486ea  mov     edx, [rdi+1F08h]
0x1800486f0  call    XCF_ReadBlock
0x1800486f5  mov     rcx, rdi
0x1800486f8  call    XCF_ReadDictionary
0x1800486fd  cmp     dword ptr [rdi+290h], 0
0x180048704  movzx   ebx, r15w
0x180048708  jz      short loc_180048762
0x18004870a  mov     edx, [rdi+294h]
0x180048710  lea     r8, [rbx+43Ah]
0x180048717  add     edx, [rdi+1F08h]
0x18004871d  mov     rcx, rdi
0x180048720  shl     r8, 4
0x180048724  add     r8, rdi
0x180048727  call    ReadTableInfo
0x18004872c  lea     rax, [rbx+43Ah]
0x180048733  add     rax, rax
0x180048736  mov     ecx, [rdi+rax*8]
0x180048739  cmp     ecx, 4D8h
0x18004873f  jnb     short loc_180048748
0x180048741  mov     eax, 6Bh ; 'k'
0x180048746  jmp     short loc_18004875A
0x180048748  mov     eax, 46Bh
0x18004874d  cmp     ecx, 846Ch
0x180048753  jb      short loc_18004875A
0x180048755  mov     eax, 8000h
0x18004875a  mov     [rdi+rbx*2+53A0h], ax
0x180048762  cmp     byte ptr [rdi+1F34h], 1
0x180048769  mov     ecx, 43Ah
0x18004876e  mov     rax, rbx
0x180048771  jnz     short loc_18004877A
0x180048773  mov     esi, 5
0x180048778  jmp     short loc_180048784
0x18004877a  add     rax, rcx
0x18004877d  add     rax, rax
0x180048780  movzx   esi, word ptr [rdi+rax*8]
0x180048784  mov     rcx, rdi
0x180048787  call    AssignDictionaryDefaults
0x18004878c  mov     eax, [rsp+98h+var_68]
0x180048790  mov     ecx, 1
0x180048795  mov     [rdi+5DCh], eax
0x18004879b  cmp     [rdi+46Ch], ecx
0x1800487a1  jnz     short loc_1800487AB
0x1800487a3  mov     eax, [rdi+470h]
0x1800487a9  jmp     short loc_1800487AD
0x1800487ab  xor     eax, eax
0x1800487ad  mov     [rdi+rbx+3AA0h], al
0x1800487b4  cmp     [rdi+32Ch], ecx
0x1800487ba  jnz     short loc_1800487C4
0x1800487bc  mov     eax, [rdi+330h]
0x1800487c2  jmp     short loc_1800487C6
0x1800487c4  xor     eax, eax
0x1800487c6  mov     [rdi+rbx*4+3BA0h], eax
0x1800487cd  cmp     [rdi+324h], ecx
0x1800487d3  jnz     short loc_1800487DD
0x1800487d5  mov     eax, [rdi+328h]
0x1800487db  jmp     short loc_1800487DF
0x1800487dd  xor     eax, eax
0x1800487df  movzx   r9d, si
0x1800487e3  mov     [rdi+rbx*4+3FA0h], eax
0x1800487ea  mov     r8d, ebp
0x1800487ed  movzx   edx, r15w
0x1800487f1  mov     rcx, rdi
0x1800487f4  call    XT1_WriteCIDDict
0x1800487f9  movzx   eax, si
0x1800487fc  inc     r15w
0x180048800  mov     esi, [rsp+98h+var_64]
0x180048804  lea     ebp, [rbp+rax*4+0]
0x180048808  add     ebp, 4
0x18004880b  lea     rax, [rdi+1E8h]
0x180048812  cmp     r15w, [rdi+3A68h]
0x18004881a  jb      loc_18004868D
0x180048820  mov     rax, [rdi+168h]
0x180048827  lea     r9, asc_180064FCC; "\r\n"
0x18004882e  lea     r8, aDefS; "def%s"
0x180048835  mov     edx, 0Ah
0x18004883a  lea     rcx, [rsp+98h+var_60]
0x18004883f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048844  mov     rax, [rdi+150h]
0x18004884b  lea     rcx, [rsp+98h+var_60]
0x180048850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048855  movzx   r8d, ax
0x180048859  lea     rdx, [rsp+98h+var_60]
0x18004885e  mov     rcx, rdi
0x180048861  call    XCF_PutData
0x180048866  mov     [rdi+3A7Ch], ebp
0x18004886c  mov     dword ptr [rdi+3A74h], 0
0x180048876  mov     rcx, [rsp+98h+var_50]
0x18004887b  xor     rcx, rsp; StackCookie
0x18004887e  call    __security_check_cookie
0x180048883  add     rsp, 58h
0x180048887  pop     r15
0x180048889  pop     r14
0x18004888b  pop     r13
0x18004888d  pop     r12
0x18004888f  pop     rdi
0x180048890  pop     rsi
0x180048891  pop     rbp
0x180048892  pop     rbx
0x180048893  retn
```
