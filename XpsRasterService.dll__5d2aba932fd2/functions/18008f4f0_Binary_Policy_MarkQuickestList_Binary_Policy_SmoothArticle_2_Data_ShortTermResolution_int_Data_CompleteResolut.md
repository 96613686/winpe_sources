# Binary::Policy::MarkQuickestList<Binary::Policy::SmoothArticle,2>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x18008f4f0`
- end: `0x18008f7f2`
- name: `??$MarkQuickestList@VSmoothArticle@Policy@Binary@@$01@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `770`
- prototype: `char __fastcall(_DWORD *, __int64, __int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180094b90`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x18008f4f0`
- `0x180090e30`

## pseudocode

```c
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::SmoothArticle,2>(
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

  Binary::Definition::GenerateAsyncServer((unsigned int)&v42, 5, 2, 2, a1[1] + 3);
  LODWORD(v9) = 0;
  v45 = 1;
  v10 = v43 == 0;
  v11 = 0;
  v43 = 1;
  if ( !v10 )
    v11 = v42;
  v44 = v11;
  v42 = 2;
  v12 = (int *)Data::FillClearSkill(v46, &v44, &v42);
  v13 = *((_BYTE *)v12 + 4);
  if ( v13 )
  {
    v14 = 2LL * *v12;
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
  Binary::Definition::GenerateAsyncServer((unsigned int)&v44, 5, 2, 2, *a1 + 3);
  v10 = v45 == 0;
  v45 = 1;
  if ( !v10 )
    v15 = v44;
  v42 = v15;
  v44 = 2;
  v43 = 1;
  v16 = (int *)Data::FillClearSkill(v46, &v42, &v44);
  if ( *((_BYTE *)v16 + 4)
    && (v17 = 2LL * *v16, LOBYTE(v16) = 2 * *v16, (unsigned __int64)(v17 + 0x80000000LL) <= 0xFFFFFFFF)
    && ((v18 = v15 - (__int64)(int)v17, (unsigned __int64)(v18 + 0x80000000LL) > 0xFFFFFFFF)
      ? (LOBYTE(v16) = 0, LODWORD(v18) = 0)
      : (LOBYTE(v16) = 1),
        (_BYTE)v16) )
  {
    if ( (unsigned int)v18 > 1 )
      LODWORD(v18) = (int)v18 % 2 + ((int)v18 % 2 < 0 ? 2 : 0);
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
    Binary::Policy::PutBooleanUnit<Binary::Policy::SmoothArticle,2>(v9, a4, a5, (unsigned int)v47, v18);
    LOBYTE(v16) = v18;
    v37 = 0;
    if ( Binary::Policy::SmoothArticle::GlobalCase[(int)v18] > 0 )
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
      while ( v37 < Binary::Policy::SmoothArticle::GlobalCase[(int)v18] );
    }
    v39 = v18 + 1;
    ++v19;
    v40 = (int)v18 - 1 < 0;
    LODWORD(v18) = 0;
    if ( v40 != __OFSUB__(v39, 2) )
      LODWORD(v18) = v39;
  }
  return (char)v16;
}

```

## disassembly

```asm
0x18008f4f0  mov     [rsp-8+arg_0], rbx
0x18008f4f5  push    rbp
0x18008f4f6  push    rsi
0x18008f4f7  push    rdi
0x18008f4f8  push    r12
0x18008f4fa  push    r13
0x18008f4fc  push    r14
0x18008f4fe  push    r15
0x18008f500  lea     rbp, [rsp-1Fh]
0x18008f505  sub     rsp, 0C0h
0x18008f50c  mov     rax, cs:__security_cookie
0x18008f513  xor     rax, rsp
0x18008f516  mov     [rbp+4Fh+var_40], rax
0x18008f51a  mov     eax, [rcx+4]
0x18008f51d  mov     r12, r9
0x18008f520  mov     r15, [rbp+4Fh+arg_20]
0x18008f524  mov     r9d, 2
0x18008f52a  add     eax, 3
0x18008f52d  mov     r13, r8
0x18008f530  mov     rbx, rdx
0x18008f533  mov     [rsp+0F0h+var_D0], eax
0x18008f537  mov     rsi, rcx
0x18008f53a  mov     r8d, r9d
0x18008f53d  mov     edx, 5
0x18008f542  lea     rcx, [rbp+4Fh+var_C0]
0x18008f546  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18008f54b  xor     r14d, r14d
0x18008f54e  mov     [rbp+4Fh+var_B4], 1
0x18008f552  cmp     [rbp+4Fh+var_BC], r14b
0x18008f556  lea     r8, [rbp+4Fh+var_C0]
0x18008f55a  mov     edi, r14d
0x18008f55d  mov     [rbp+4Fh+var_BC], 1
0x18008f561  cmovnz  edi, [rbp+4Fh+var_C0]
0x18008f565  lea     rdx, [rbp+4Fh+var_B8]
0x18008f569  lea     rcx, [rbp+4Fh+var_B0]
0x18008f56d  mov     [rbp+4Fh+var_B8], edi
0x18008f570  mov     [rbp+4Fh+var_C0], 2
0x18008f577  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008f57c  mov     edx, 80000000h
0x18008f581  mov     r8d, 0FFFFFFFFh
0x18008f587  movzx   ecx, byte ptr [rax+4]
0x18008f58b  test    cl, cl
0x18008f58d  jz      short loc_18008F5BF
0x18008f58f  movsxd  rcx, dword ptr [rax]
0x18008f592  add     rcx, rcx
0x18008f595  lea     rax, [rcx+rdx]
0x18008f599  cmp     rax, r8
0x18008f59c  ja      short loc_18008F5BD
0x18008f59e  movsxd  rax, ecx
0x18008f5a1  movsxd  r14, edi
0x18008f5a4  sub     r14, rax
0x18008f5a7  lea     rax, [r14+rdx]
0x18008f5ab  cmp     rax, r8
0x18008f5ae  ja      short loc_18008F5B4
0x18008f5b0  mov     cl, 1
0x18008f5b2  jmp     short loc_18008F5BF
0x18008f5b4  xor     cl, cl
0x18008f5b6  xor     edi, edi
0x18008f5b8  mov     r14d, edi
0x18008f5bb  jmp     short loc_18008F5C1
0x18008f5bd  xor     cl, cl
0x18008f5bf  xor     edi, edi
0x18008f5c1  mov     eax, [rsi]
0x18008f5c3  test    cl, cl
0x18008f5c5  mov     r9d, 2
0x18008f5cb  lea     rcx, [rbp+4Fh+var_B8]
0x18008f5cf  cmovz   r14d, edi
0x18008f5d3  mov     edx, 5
0x18008f5d8  add     eax, 3
0x18008f5db  mov     r8d, r9d
0x18008f5de  mov     [rsp+0F0h+var_D0], eax
0x18008f5e2  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18008f5e7  cmp     [rbp+4Fh+var_B4], 0
0x18008f5eb  lea     r8, [rbp+4Fh+var_B8]
0x18008f5ef  lea     rdx, [rbp+4Fh+var_C0]
0x18008f5f3  mov     [rbp+4Fh+var_B4], 1
0x18008f5f7  cmovnz  edi, [rbp+4Fh+var_B8]
0x18008f5fb  lea     rcx, [rbp+4Fh+var_B0]
0x18008f5ff  mov     [rbp+4Fh+var_C0], edi
0x18008f602  mov     [rbp+4Fh+var_B8], 2
0x18008f609  mov     [rbp+4Fh+var_BC], 1
0x18008f60d  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008f612  cmp     byte ptr [rax+4], 0
0x18008f616  jz      short loc_18008F674
0x18008f618  movsxd  rcx, dword ptr [rax]
0x18008f61b  mov     edx, 80000000h
0x18008f620  add     rcx, rcx
0x18008f623  mov     r8d, 0FFFFFFFFh
0x18008f629  lea     rax, [rcx+rdx]
0x18008f62d  cmp     rax, r8
0x18008f630  ja      short loc_18008F674
0x18008f632  movsxd  rax, ecx
0x18008f635  movsxd  rdi, edi
0x18008f638  sub     rdi, rax
0x18008f63b  lea     rax, [rdi+rdx]
0x18008f63f  cmp     rax, r8
0x18008f642  ja      short loc_18008F64B
0x18008f644  mov     al, 1
0x18008f646  xor     r11d, r11d
0x18008f649  jmp     short loc_18008F653
0x18008f64b  xor     al, al
0x18008f64d  xor     r11d, r11d
0x18008f650  mov     edi, r11d
0x18008f653  test    al, al
0x18008f655  jz      short loc_18008F677
0x18008f657  cmp     edi, 1
0x18008f65a  jbe     short loc_18008F67A
0x18008f65c  and     edi, 80000001h
0x18008f662  jge     short loc_18008F66B
0x18008f664  dec     edi
0x18008f666  or      edi, 0FFFFFFFEh
0x18008f669  inc     edi
0x18008f66b  test    edi, edi
0x18008f66d  jns     short loc_18008F67A
0x18008f66f  add     edi, 2
0x18008f672  jmp     short loc_18008F67A
0x18008f674  xor     r11d, r11d
0x18008f677  mov     edi, r11d
0x18008f67a  cmp     dword ptr [r15+8], 0
0x18008f67f  mov     esi, r11d
0x18008f682  jle     loc_18008F7CB
0x18008f688  nop     dword ptr [rax+rax+00000000h]
0x18008f690  mov     r9, [r13+0]
0x18008f694  mov     rcx, [rbx+8]
0x18008f698  mov     edx, [rbx]
0x18008f69a  mov     r10d, [rbx+18h]
0x18008f69e  inc     edx
0x18008f6a0  mov     r8, [rbx+10h]
0x18008f6a4  lea     rax, [r9+rcx*2]
0x18008f6a8  mov     [rbp+4Fh+var_80], rax
0x18008f6ac  cmp     edx, r10d
0x18008f6af  jl      short loc_18008F6B9
0x18008f6b1  mov     edx, r11d
0x18008f6b4  mov     rcx, r11
0x18008f6b7  jmp     short loc_18008F6BC
0x18008f6b9  add     rcx, r8
0x18008f6bc  inc     edx
0x18008f6be  lea     rax, [r9+rcx*2]
0x18008f6c2  mov     [rbp+4Fh+var_78], rax
0x18008f6c6  cmp     edx, r10d
0x18008f6c9  jl      short loc_18008F6D3
0x18008f6cb  mov     edx, r11d
0x18008f6ce  mov     rcx, r11
0x18008f6d1  jmp     short loc_18008F6D6
0x18008f6d3  add     rcx, r8
0x18008f6d6  inc     edx
0x18008f6d8  lea     rax, [r9+rcx*2]
0x18008f6dc  mov     [rbp+4Fh+var_70], rax
0x18008f6e0  cmp     edx, r10d
0x18008f6e3  jl      short loc_18008F6ED
0x18008f6e5  mov     edx, r11d
0x18008f6e8  mov     rcx, r11
0x18008f6eb  jmp     short loc_18008F6F0
0x18008f6ed  add     rcx, r8
0x18008f6f0  inc     edx
0x18008f6f2  lea     rax, [r9+rcx*2]
0x18008f6f6  mov     [rbp+4Fh+var_68], rax
0x18008f6fa  cmp     edx, r10d
0x18008f6fd  jl      short loc_18008F707
0x18008f6ff  mov     edx, r11d
0x18008f702  mov     rcx, r11
0x18008f705  jmp     short loc_18008F70A
0x18008f707  add     rcx, r8
0x18008f70a  inc     edx
0x18008f70c  lea     rax, [r9+rcx*2]
0x18008f710  mov     [rbp+4Fh+var_60], rax
0x18008f714  cmp     edx, r10d
0x18008f717  jl      short loc_18008F721
0x18008f719  mov     edx, r11d
0x18008f71c  mov     rcx, r11
0x18008f71f  jmp     short loc_18008F724
0x18008f721  add     rcx, r8
0x18008f724  inc     edx
0x18008f726  lea     rax, [r9+rcx*2]
0x18008f72a  mov     [rbp+4Fh+var_58], rax
0x18008f72e  cmp     edx, r10d
0x18008f731  jl      short loc_18008F73B
0x18008f733  mov     edx, r11d
0x18008f736  mov     rcx, r11
0x18008f739  jmp     short loc_18008F73E
0x18008f73b  add     rcx, r8
0x18008f73e  inc     edx
0x18008f740  lea     rax, [r9+rcx*2]
0x18008f744  mov     [rbp+4Fh+var_50], rax
0x18008f748  cmp     edx, r10d
0x18008f74b  jl      short loc_18008F752
0x18008f74d  mov     rcx, r11
0x18008f750  jmp     short loc_18008F755
0x18008f752  add     rcx, r8
0x18008f755  lea     rax, [r9+rcx*2]
0x18008f759  mov     [rsp+0F0h+var_D0], edi
0x18008f75d  lea     r9, [rbp+4Fh+var_80]
0x18008f761  mov     [rbp+4Fh+var_48], rax
0x18008f765  mov     ecx, r14d
0x18008f768  mov     r8, r15
0x18008f76b  mov     rdx, r12
0x18008f76e  call    ??$PutBooleanUnit@VSmoothArticle@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY07$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::SmoothArticle,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[8],int)
0x18008f773  xor     r11d, r11d
0x18008f776  movsxd  rax, edi
0x18008f779  lea     rdx, ?GlobalCase@SmoothArticle@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B; Data::StripedCategory<int,2> const Binary::Policy::SmoothArticle::GlobalCase
0x18008f780  mov     ecx, r11d
0x18008f783  cmp     [rdx+rax*4], r11d
0x18008f787  lea     rdx, [rdx+rax*4]
0x18008f78b  jle     short loc_18008F7B3
0x18008f78d  mov     r8d, [rbx+18h]
0x18008f791  inc     dword ptr [rbx]
0x18008f793  cmp     [rbx], r8d
0x18008f796  jl      short loc_18008F7A1
0x18008f798  mov     [rbx], r11d
0x18008f79b  mov     [rbx+8], r11
0x18008f79f  jmp     short loc_18008F7AD
0x18008f7a1  mov     rax, [rbx+8]
0x18008f7a5  add     rax, [rbx+10h]
0x18008f7a9  mov     [rbx+8], rax
0x18008f7ad  inc     ecx
0x18008f7af  cmp     ecx, [rdx]
0x18008f7b1  jl      short loc_18008F791
0x18008f7b3  lea     ecx, [rdi+1]
0x18008f7b6  inc     esi
0x18008f7b8  cmp     ecx, 2
0x18008f7bb  mov     edi, r11d
0x18008f7be  cmovl   edi, ecx
0x18008f7c1  cmp     esi, [r15+8]
0x18008f7c5  jl      loc_18008F690
0x18008f7cb  mov     rcx, [rbp+4Fh+var_40]
0x18008f7cf  xor     rcx, rsp; StackCookie
0x18008f7d2  call    __security_check_cookie
0x18008f7d7  mov     rbx, [rsp+0F0h+arg_0]
0x18008f7df  add     rsp, 0C0h
0x18008f7e6  pop     r15
0x18008f7e8  pop     r14
0x18008f7ea  pop     r13
0x18008f7ec  pop     r12
0x18008f7ee  pop     rdi
0x18008f7ef  pop     rsi
0x18008f7f0  pop     rbp
0x18008f7f1  retn
```
