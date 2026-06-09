# Binary::Policy::MarkQuickestList<Binary::Policy::SlowSource,2>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x18008f1e0`
- end: `0x18008f4e2`
- name: `??$MarkQuickestList@VSlowSource@Policy@Binary@@$01@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `770`
- prototype: `char __fastcall(_DWORD *, __int64, __int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180092da0`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x18008f1e0`
- `0x1800908b0`

## pseudocode

```c
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::SlowSource,2>(
        _DWORD *a1,
        __int64 a2,
        __int64 *a3,
        int a4,
        __int64 a5)
{
  __int64 v9; // r14
  bool v10; // zf
  int v11; // edi
  int *v12; // rax
  char v13; // cl
  __int64 v14; // rcx
  int v15; // edi
  int *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdi
  int v19; // esi
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // r10d
  int v23; // edx
  __int64 v24; // r8
  __int64 v25; // rcx
  int v26; // edx
  __int64 v27; // rcx
  int v28; // edx
  __int64 v29; // rcx
  int v30; // edx
  __int64 v31; // rcx
  int v32; // edx
  __int64 v33; // rcx
  int v34; // edx
  __int64 v35; // rcx
  __int64 v36; // rcx
  int v37; // ecx
  int v38; // r8d
  int v39; // ecx
  bool v40; // sf
  int v42; // [rsp+30h] [rbp-71h] BYREF
  char v43; // [rsp+34h] [rbp-6Dh]
  int v44; // [rsp+38h] [rbp-69h] BYREF
  char v45; // [rsp+3Ch] [rbp-65h]
  _BYTE v46[48]; // [rsp+40h] [rbp-61h] BYREF
  _QWORD v47[8]; // [rsp+70h] [rbp-31h] BYREF

  Binary::Definition::GenerateAsyncServer((unsigned int)&v42, 5, 4, 4, a1[1] + 3);
  LODWORD(v9) = 0;
  v45 = 1;
  v10 = v43 == 0;
  v11 = 0;
  v43 = 1;
  if ( !v10 )
    v11 = v42;
  v44 = v11;
  v42 = 4;
  v12 = (int *)Data::FillClearSkill(v46, &v44, &v42);
  v13 = *((_BYTE *)v12 + 4);
  if ( v13 )
  {
    v14 = 4LL * *v12;
    if ( (unsigned __int64)(v14 + 0x80000000LL) > 0xFFFFFFFF )
    {
      v13 = 0;
    }
    else
    {
      v9 = v11 - (__int64)(int)v14;
      if ( (unsigned __int64)(v9 + 0x80000000LL) > 0xFFFFFFFF )
      {
        v13 = 0;
        v15 = 0;
        LODWORD(v9) = 0;
        goto LABEL_10;
      }
      v13 = 1;
    }
  }
  v15 = 0;
LABEL_10:
  if ( !v13 )
    LODWORD(v9) = 0;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v44, 5, 4, 4, *a1 + 3);
  v10 = v45 == 0;
  v45 = 1;
  if ( !v10 )
    v15 = v44;
  v42 = v15;
  v44 = 4;
  v43 = 1;
  v16 = (int *)Data::FillClearSkill(v46, &v42, &v44);
  if ( *((_BYTE *)v16 + 4)
    && (v17 = 4LL * *v16, LOBYTE(v16) = 4 * *v16, (unsigned __int64)(v17 + 0x80000000LL) <= 0xFFFFFFFF)
    && ((v18 = v15 - (__int64)(int)v17, (unsigned __int64)(v18 + 0x80000000LL) > 0xFFFFFFFF)
      ? (LOBYTE(v16) = 0, LODWORD(v18) = 0)
      : (LOBYTE(v16) = 1),
        (_BYTE)v16) )
  {
    if ( (unsigned int)v18 > 3 )
      LODWORD(v18) = (int)v18 % 4 + ((int)v18 % 4 < 0 ? 4 : 0);
  }
  else
  {
    LODWORD(v18) = 0;
  }
  v19 = 0;
  while ( v19 < *(_DWORD *)(a5 + 8) )
  {
    v20 = *a3;
    v21 = *(_QWORD *)(a2 + 8);
    v22 = *(_DWORD *)(a2 + 24);
    v23 = *(_DWORD *)a2 + 1;
    v24 = *(_QWORD *)(a2 + 16);
    v47[0] = *a3 + 2 * v21;
    if ( v23 < v22 )
    {
      v25 = v24 + v21;
    }
    else
    {
      v23 = 0;
      v25 = 0;
    }
    v26 = v23 + 1;
    v47[1] = v20 + 2 * v25;
    if ( v26 < v22 )
    {
      v27 = v24 + v25;
    }
    else
    {
      v26 = 0;
      v27 = 0;
    }
    v28 = v26 + 1;
    v47[2] = v20 + 2 * v27;
    if ( v28 < v22 )
    {
      v29 = v24 + v27;
    }
    else
    {
      v28 = 0;
      v29 = 0;
    }
    v30 = v28 + 1;
    v47[3] = v20 + 2 * v29;
    if ( v30 < v22 )
    {
      v31 = v24 + v29;
    }
    else
    {
      v30 = 0;
      v31 = 0;
    }
    v32 = v30 + 1;
    v47[4] = v20 + 2 * v31;
    if ( v32 < v22 )
    {
      v33 = v24 + v31;
    }
    else
    {
      v32 = 0;
      v33 = 0;
    }
    v34 = v32 + 1;
    v47[5] = v20 + 2 * v33;
    if ( v34 < v22 )
    {
      v35 = v24 + v33;
    }
    else
    {
      v34 = 0;
      v35 = 0;
    }
    v47[6] = v20 + 2 * v35;
    if ( v34 + 1 < v22 )
      v36 = v24 + v35;
    else
      v36 = 0;
    v47[7] = v20 + 2 * v36;
    Binary::Policy::PutBooleanUnit<Binary::Policy::SlowSource,2>(v9, a4, a5, (unsigned int)v47, v18);
    LOBYTE(v16) = v18;
    v37 = 0;
    if ( Binary::Policy::SlowSource::GlobalCase[(int)v18] > 0 )
    {
      v38 = *(_DWORD *)(a2 + 24);
      do
      {
        if ( ++*(_DWORD *)a2 < v38 )
        {
          v16 = (int *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 8));
          *(_QWORD *)(a2 + 8) = v16;
        }
        else
        {
          *(_DWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
        }
        ++v37;
      }
      while ( v37 < Binary::Policy::SlowSource::GlobalCase[(int)v18] );
    }
    v39 = v18 + 1;
    ++v19;
    v40 = (int)v18 - 3 < 0;
    LODWORD(v18) = 0;
    if ( v40 != __OFSUB__(v39, 4) )
      LODWORD(v18) = v39;
  }
  return (char)v16;
}

```

## disassembly

```asm
0x18008f1e0  mov     [rsp-8+arg_0], rbx
0x18008f1e5  push    rbp
0x18008f1e6  push    rsi
0x18008f1e7  push    rdi
0x18008f1e8  push    r12
0x18008f1ea  push    r13
0x18008f1ec  push    r14
0x18008f1ee  push    r15
0x18008f1f0  lea     rbp, [rsp-1Fh]
0x18008f1f5  sub     rsp, 0C0h
0x18008f1fc  mov     rax, cs:__security_cookie
0x18008f203  xor     rax, rsp
0x18008f206  mov     [rbp+4Fh+var_40], rax
0x18008f20a  mov     eax, [rcx+4]
0x18008f20d  mov     r12, r9
0x18008f210  mov     r15, [rbp+4Fh+arg_20]
0x18008f214  mov     r9d, 4
0x18008f21a  add     eax, 3
0x18008f21d  mov     r13, r8
0x18008f220  mov     rbx, rdx
0x18008f223  mov     [rsp+0F0h+var_D0], eax
0x18008f227  mov     rsi, rcx
0x18008f22a  mov     r8d, r9d
0x18008f22d  mov     edx, 5
0x18008f232  lea     rcx, [rbp+4Fh+var_C0]
0x18008f236  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18008f23b  xor     r14d, r14d
0x18008f23e  mov     [rbp+4Fh+var_B4], 1
0x18008f242  cmp     [rbp+4Fh+var_BC], r14b
0x18008f246  lea     r8, [rbp+4Fh+var_C0]
0x18008f24a  mov     edi, r14d
0x18008f24d  mov     [rbp+4Fh+var_BC], 1
0x18008f251  cmovnz  edi, [rbp+4Fh+var_C0]
0x18008f255  lea     rdx, [rbp+4Fh+var_B8]
0x18008f259  lea     rcx, [rbp+4Fh+var_B0]
0x18008f25d  mov     [rbp+4Fh+var_B8], edi
0x18008f260  mov     [rbp+4Fh+var_C0], 4
0x18008f267  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008f26c  mov     edx, 80000000h
0x18008f271  mov     r8d, 0FFFFFFFFh
0x18008f277  movzx   ecx, byte ptr [rax+4]
0x18008f27b  test    cl, cl
0x18008f27d  jz      short loc_18008F2B0
0x18008f27f  movsxd  rcx, dword ptr [rax]
0x18008f282  shl     rcx, 2
0x18008f286  lea     rax, [rcx+rdx]
0x18008f28a  cmp     rax, r8
0x18008f28d  ja      short loc_18008F2AE
0x18008f28f  movsxd  rax, ecx
0x18008f292  movsxd  r14, edi
0x18008f295  sub     r14, rax
0x18008f298  lea     rax, [r14+rdx]
0x18008f29c  cmp     rax, r8
0x18008f29f  ja      short loc_18008F2A5
0x18008f2a1  mov     cl, 1
0x18008f2a3  jmp     short loc_18008F2B0
0x18008f2a5  xor     cl, cl
0x18008f2a7  xor     edi, edi
0x18008f2a9  mov     r14d, edi
0x18008f2ac  jmp     short loc_18008F2B2
0x18008f2ae  xor     cl, cl
0x18008f2b0  xor     edi, edi
0x18008f2b2  mov     eax, [rsi]
0x18008f2b4  test    cl, cl
0x18008f2b6  mov     r9d, 4
0x18008f2bc  lea     rcx, [rbp+4Fh+var_B8]
0x18008f2c0  cmovz   r14d, edi
0x18008f2c4  mov     edx, 5
0x18008f2c9  add     eax, 3
0x18008f2cc  mov     r8d, r9d
0x18008f2cf  mov     [rsp+0F0h+var_D0], eax
0x18008f2d3  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18008f2d8  cmp     [rbp+4Fh+var_B4], 0
0x18008f2dc  lea     r8, [rbp+4Fh+var_B8]
0x18008f2e0  lea     rdx, [rbp+4Fh+var_C0]
0x18008f2e4  mov     [rbp+4Fh+var_B4], 1
0x18008f2e8  cmovnz  edi, [rbp+4Fh+var_B8]
0x18008f2ec  lea     rcx, [rbp+4Fh+var_B0]
0x18008f2f0  mov     [rbp+4Fh+var_C0], edi
0x18008f2f3  mov     [rbp+4Fh+var_B8], 4
0x18008f2fa  mov     [rbp+4Fh+var_BC], 1
0x18008f2fe  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008f303  cmp     byte ptr [rax+4], 0
0x18008f307  jz      short loc_18008F366
0x18008f309  movsxd  rcx, dword ptr [rax]
0x18008f30c  mov     edx, 80000000h
0x18008f311  shl     rcx, 2
0x18008f315  mov     r8d, 0FFFFFFFFh
0x18008f31b  lea     rax, [rcx+rdx]
0x18008f31f  cmp     rax, r8
0x18008f322  ja      short loc_18008F366
0x18008f324  movsxd  rax, ecx
0x18008f327  movsxd  rdi, edi
0x18008f32a  sub     rdi, rax
0x18008f32d  lea     rax, [rdi+rdx]
0x18008f331  cmp     rax, r8
0x18008f334  ja      short loc_18008F33D
0x18008f336  mov     al, 1
0x18008f338  xor     r11d, r11d
0x18008f33b  jmp     short loc_18008F345
0x18008f33d  xor     al, al
0x18008f33f  xor     r11d, r11d
0x18008f342  mov     edi, r11d
0x18008f345  test    al, al
0x18008f347  jz      short loc_18008F369
0x18008f349  cmp     edi, 3
0x18008f34c  jbe     short loc_18008F36C
0x18008f34e  and     edi, 80000003h
0x18008f354  jge     short loc_18008F35D
0x18008f356  dec     edi
0x18008f358  or      edi, 0FFFFFFFCh
0x18008f35b  inc     edi
0x18008f35d  test    edi, edi
0x18008f35f  jns     short loc_18008F36C
0x18008f361  add     edi, 4
0x18008f364  jmp     short loc_18008F36C
0x18008f366  xor     r11d, r11d
0x18008f369  mov     edi, r11d
0x18008f36c  cmp     dword ptr [r15+8], 0
0x18008f371  mov     esi, r11d
0x18008f374  jle     loc_18008F4BB
0x18008f37a  nop     word ptr [rax+rax+00h]
0x18008f380  mov     r9, [r13+0]
0x18008f384  mov     rcx, [rbx+8]
0x18008f388  mov     edx, [rbx]
0x18008f38a  mov     r10d, [rbx+18h]
0x18008f38e  inc     edx
0x18008f390  mov     r8, [rbx+10h]
0x18008f394  lea     rax, [r9+rcx*2]
0x18008f398  mov     [rbp+4Fh+var_80], rax
0x18008f39c  cmp     edx, r10d
0x18008f39f  jl      short loc_18008F3A9
0x18008f3a1  mov     edx, r11d
0x18008f3a4  mov     rcx, r11
0x18008f3a7  jmp     short loc_18008F3AC
0x18008f3a9  add     rcx, r8
0x18008f3ac  inc     edx
0x18008f3ae  lea     rax, [r9+rcx*2]
0x18008f3b2  mov     [rbp+4Fh+var_78], rax
0x18008f3b6  cmp     edx, r10d
0x18008f3b9  jl      short loc_18008F3C3
0x18008f3bb  mov     edx, r11d
0x18008f3be  mov     rcx, r11
0x18008f3c1  jmp     short loc_18008F3C6
0x18008f3c3  add     rcx, r8
0x18008f3c6  inc     edx
0x18008f3c8  lea     rax, [r9+rcx*2]
0x18008f3cc  mov     [rbp+4Fh+var_70], rax
0x18008f3d0  cmp     edx, r10d
0x18008f3d3  jl      short loc_18008F3DD
0x18008f3d5  mov     edx, r11d
0x18008f3d8  mov     rcx, r11
0x18008f3db  jmp     short loc_18008F3E0
0x18008f3dd  add     rcx, r8
0x18008f3e0  inc     edx
0x18008f3e2  lea     rax, [r9+rcx*2]
0x18008f3e6  mov     [rbp+4Fh+var_68], rax
0x18008f3ea  cmp     edx, r10d
0x18008f3ed  jl      short loc_18008F3F7
0x18008f3ef  mov     edx, r11d
0x18008f3f2  mov     rcx, r11
0x18008f3f5  jmp     short loc_18008F3FA
0x18008f3f7  add     rcx, r8
0x18008f3fa  inc     edx
0x18008f3fc  lea     rax, [r9+rcx*2]
0x18008f400  mov     [rbp+4Fh+var_60], rax
0x18008f404  cmp     edx, r10d
0x18008f407  jl      short loc_18008F411
0x18008f409  mov     edx, r11d
0x18008f40c  mov     rcx, r11
0x18008f40f  jmp     short loc_18008F414
0x18008f411  add     rcx, r8
0x18008f414  inc     edx
0x18008f416  lea     rax, [r9+rcx*2]
0x18008f41a  mov     [rbp+4Fh+var_58], rax
0x18008f41e  cmp     edx, r10d
0x18008f421  jl      short loc_18008F42B
0x18008f423  mov     edx, r11d
0x18008f426  mov     rcx, r11
0x18008f429  jmp     short loc_18008F42E
0x18008f42b  add     rcx, r8
0x18008f42e  inc     edx
0x18008f430  lea     rax, [r9+rcx*2]
0x18008f434  mov     [rbp+4Fh+var_50], rax
0x18008f438  cmp     edx, r10d
0x18008f43b  jl      short loc_18008F442
0x18008f43d  mov     rcx, r11
0x18008f440  jmp     short loc_18008F445
0x18008f442  add     rcx, r8
0x18008f445  lea     rax, [r9+rcx*2]
0x18008f449  mov     [rsp+0F0h+var_D0], edi
0x18008f44d  lea     r9, [rbp+4Fh+var_80]
0x18008f451  mov     [rbp+4Fh+var_48], rax
0x18008f455  mov     ecx, r14d
0x18008f458  mov     r8, r15
0x18008f45b  mov     rdx, r12
0x18008f45e  call    ??$PutBooleanUnit@VSlowSource@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY07$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::SlowSource,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[8],int)
0x18008f463  xor     r11d, r11d
0x18008f466  movsxd  rax, edi
0x18008f469  lea     rdx, ?GlobalCase@SlowSource@Policy@Binary@@2V?$StripedCategory@H$03@Data@@B; Data::StripedCategory<int,4> const Binary::Policy::SlowSource::GlobalCase
0x18008f470  mov     ecx, r11d
0x18008f473  cmp     [rdx+rax*4], r11d
0x18008f477  lea     rdx, [rdx+rax*4]
0x18008f47b  jle     short loc_18008F4A3
0x18008f47d  mov     r8d, [rbx+18h]
0x18008f481  inc     dword ptr [rbx]
0x18008f483  cmp     [rbx], r8d
0x18008f486  jl      short loc_18008F491
0x18008f488  mov     [rbx], r11d
0x18008f48b  mov     [rbx+8], r11
0x18008f48f  jmp     short loc_18008F49D
0x18008f491  mov     rax, [rbx+8]
0x18008f495  add     rax, [rbx+10h]
0x18008f499  mov     [rbx+8], rax
0x18008f49d  inc     ecx
0x18008f49f  cmp     ecx, [rdx]
0x18008f4a1  jl      short loc_18008F481
0x18008f4a3  lea     ecx, [rdi+1]
0x18008f4a6  inc     esi
0x18008f4a8  cmp     ecx, 4
0x18008f4ab  mov     edi, r11d
0x18008f4ae  cmovl   edi, ecx
0x18008f4b1  cmp     esi, [r15+8]
0x18008f4b5  jl      loc_18008F380
0x18008f4bb  mov     rcx, [rbp+4Fh+var_40]
0x18008f4bf  xor     rcx, rsp; StackCookie
0x18008f4c2  call    __security_check_cookie
0x18008f4c7  mov     rbx, [rsp+0F0h+arg_0]
0x18008f4cf  add     rsp, 0C0h
0x18008f4d6  pop     r15
0x18008f4d8  pop     r14
0x18008f4da  pop     r13
0x18008f4dc  pop     r12
0x18008f4de  pop     rdi
0x18008f4df  pop     rsi
0x18008f4e0  pop     rbp
0x18008f4e1  retn
```
