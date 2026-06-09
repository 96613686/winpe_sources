# Binary::Policy::MarkQuickestList<Binary::Policy::UniqueFact,2>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x18008fa80`
- end: `0x18008fd24`
- name: `??$MarkQuickestList@VUniqueFact@Policy@Binary@@$01@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `676`
- prototype: `char __fastcall(_DWORD *, __int64, __int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180095970`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x18008fa80`
- `0x180091820`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::UniqueFact,2>(
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
  int v14; // edi
  __int64 v15; // rax
  __int64 v16; // rdi
  int v17; // esi
  __int64 v18; // r9
  __int64 v19; // rcx
  int v20; // r10d
  int v21; // edx
  __int64 v22; // r8
  __int64 v23; // rcx
  int v24; // edx
  __int64 v25; // rcx
  int v26; // edx
  __int64 v27; // rcx
  int v28; // edx
  __int64 v29; // rcx
  int v30; // edx
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33; // ecx
  int v34; // r8d
  int v35; // ecx
  bool v36; // sf
  int v38; // [rsp+30h] [rbp-61h] BYREF
  char v39; // [rsp+34h] [rbp-5Dh]
  int v40; // [rsp+38h] [rbp-59h] BYREF
  char v41; // [rsp+3Ch] [rbp-55h]
  _BYTE v42[40]; // [rsp+40h] [rbp-51h] BYREF
  _QWORD v43[7]; // [rsp+68h] [rbp-29h] BYREF

  Binary::Definition::GenerateAsyncServer((unsigned int)&v38, 3, 1, 0, a1[1] + 3);
  LODWORD(v9) = 0;
  v41 = 1;
  v10 = v39 == 0;
  v11 = 0;
  v39 = 1;
  if ( !v10 )
    v11 = v38;
  v40 = v11;
  v38 = 1;
  v12 = (int *)Data::FillClearSkill(v42, &v40, &v38);
  v13 = *((_BYTE *)v12 + 4);
  if ( !v13 )
    goto LABEL_6;
  v9 = v11 - (__int64)*v12;
  if ( (unsigned __int64)(v9 + 0x80000000LL) <= 0xFFFFFFFF )
  {
    v13 = 1;
LABEL_6:
    v14 = 0;
    goto LABEL_7;
  }
  v13 = 0;
  v14 = 0;
  LODWORD(v9) = 0;
LABEL_7:
  if ( !v13 )
    LODWORD(v9) = 0;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v40, 3, 1, 0, *a1 + 3);
  v10 = v41 == 0;
  v41 = 1;
  if ( !v10 )
    v14 = v40;
  v38 = v14;
  v40 = 1;
  v39 = 1;
  v15 = Data::FillClearSkill(v42, &v38, &v40);
  if ( *(_BYTE *)(v15 + 4)
    && ((v16 = v14 - (__int64)*(int *)v15, (unsigned __int64)(v16 + 0x80000000LL) > 0xFFFFFFFF)
      ? (LOBYTE(v15) = 0, LODWORD(v16) = 0)
      : (LOBYTE(v15) = 1),
        (_BYTE)v15) )
  {
    if ( (_DWORD)v16 )
      LODWORD(v16) = 0;
  }
  else
  {
    LODWORD(v16) = 0;
  }
  v17 = 0;
  while ( v17 < *(_DWORD *)(a5 + 8) )
  {
    v18 = *a3;
    v19 = *(_QWORD *)(a2 + 8);
    v20 = *(_DWORD *)(a2 + 24);
    v21 = *(_DWORD *)a2 + 1;
    v22 = *(_QWORD *)(a2 + 16);
    v43[0] = *a3 + 2 * v19;
    if ( v21 < v20 )
    {
      v23 = v22 + v19;
    }
    else
    {
      v21 = 0;
      v23 = 0;
    }
    v24 = v21 + 1;
    v43[1] = v18 + 2 * v23;
    if ( v24 < v20 )
    {
      v25 = v22 + v23;
    }
    else
    {
      v24 = 0;
      v25 = 0;
    }
    v26 = v24 + 1;
    v43[2] = v18 + 2 * v25;
    if ( v26 < v20 )
    {
      v27 = v22 + v25;
    }
    else
    {
      v26 = 0;
      v27 = 0;
    }
    v28 = v26 + 1;
    v43[3] = v18 + 2 * v27;
    if ( v28 < v20 )
    {
      v29 = v22 + v27;
    }
    else
    {
      v28 = 0;
      v29 = 0;
    }
    v30 = v28 + 1;
    v43[4] = v18 + 2 * v29;
    if ( v30 < v20 )
    {
      v31 = v22 + v29;
    }
    else
    {
      v30 = 0;
      v31 = 0;
    }
    v43[5] = v18 + 2 * v31;
    if ( v30 + 1 < v20 )
      v32 = v22 + v31;
    else
      v32 = 0;
    v43[6] = v18 + 2 * v32;
    Binary::Policy::PutBooleanUnit<Binary::Policy::UniqueFact,2>(v9, a4, a5, (unsigned int)v43, v16);
    LOBYTE(v15) = v16;
    v33 = 0;
    if ( Binary::Policy::UniqueFact::GlobalCase[(int)v16] > 0 )
    {
      v34 = *(_DWORD *)(a2 + 24);
      do
      {
        if ( ++*(_DWORD *)a2 < v34 )
        {
          v15 = *(_QWORD *)(a2 + 16);
          *(_QWORD *)(a2 + 8) += v15;
        }
        else
        {
          *(_DWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
        }
        ++v33;
      }
      while ( v33 < Binary::Policy::UniqueFact::GlobalCase[(int)v16] );
    }
    v35 = v16 + 1;
    ++v17;
    v36 = (int)v16 < 0;
    LODWORD(v16) = 0;
    if ( v36 != __OFSUB__(v35, 1) )
      LODWORD(v16) = v35;
  }
  return v15;
}

```

## disassembly

```asm
0x18008fa80  mov     [rsp-8+arg_0], rbx
0x18008fa85  push    rbp
0x18008fa86  push    rsi
0x18008fa87  push    rdi
0x18008fa88  push    r12
0x18008fa8a  push    r13
0x18008fa8c  push    r14
0x18008fa8e  push    r15
0x18008fa90  lea     rbp, [rsp-1Fh]
0x18008fa95  sub     rsp, 0B0h
0x18008fa9c  mov     rax, cs:__security_cookie
0x18008faa3  xor     rax, rsp
0x18008faa6  mov     [rbp+4Fh+var_40], rax
0x18008faaa  mov     eax, [rcx+4]
0x18008faad  mov     r12, r9
0x18008fab0  mov     r15, [rbp+4Fh+arg_20]
0x18008fab4  xor     r9d, r9d
0x18008fab7  mov     r13, r8
0x18008faba  mov     rbx, rdx
0x18008fabd  mov     rsi, rcx
0x18008fac0  add     eax, 3
0x18008fac3  lea     rcx, [rbp+4Fh+var_B0]
0x18008fac7  mov     [rsp+0E0h+var_C0], eax
0x18008facb  lea     edx, [r9+3]
0x18008facf  lea     r8d, [r9+1]
0x18008fad3  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18008fad8  xor     r14d, r14d
0x18008fadb  mov     [rbp+4Fh+var_A4], 1
0x18008fadf  cmp     [rbp+4Fh+var_AC], r14b
0x18008fae3  lea     r8, [rbp+4Fh+var_B0]
0x18008fae7  mov     edi, r14d
0x18008faea  mov     [rbp+4Fh+var_AC], 1
0x18008faee  cmovnz  edi, [rbp+4Fh+var_B0]
0x18008faf2  lea     rdx, [rbp+4Fh+var_A8]
0x18008faf6  lea     rcx, [rbp+4Fh+var_A0]
0x18008fafa  mov     [rbp+4Fh+var_A8], edi
0x18008fafd  mov     [rbp+4Fh+var_B0], 1
0x18008fb04  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008fb09  mov     edx, 80000000h
0x18008fb0e  mov     r8d, 0FFFFFFFFh
0x18008fb14  movzx   ecx, byte ptr [rax+4]
0x18008fb18  test    cl, cl
0x18008fb1a  jz      short loc_18008FB30
0x18008fb1c  movsxd  rax, dword ptr [rax]
0x18008fb1f  movsxd  r14, edi
0x18008fb22  sub     r14, rax
0x18008fb25  lea     rax, [r14+rdx]
0x18008fb29  cmp     rax, r8
0x18008fb2c  ja      short loc_18008FBA8
0x18008fb2e  mov     cl, 1
0x18008fb30  xor     edi, edi
0x18008fb32  mov     eax, [rsi]
0x18008fb34  test    cl, cl
0x18008fb36  lea     rcx, [rbp+4Fh+var_A8]
0x18008fb3a  cmovz   r14d, edi
0x18008fb3e  xor     r9d, r9d
0x18008fb41  add     eax, 3
0x18008fb44  mov     [rsp+0E0h+var_C0], eax
0x18008fb48  lea     edx, [r9+3]
0x18008fb4c  lea     r8d, [r9+1]
0x18008fb50  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18008fb55  cmp     [rbp+4Fh+var_A4], 0
0x18008fb59  lea     r8, [rbp+4Fh+var_A8]
0x18008fb5d  lea     rdx, [rbp+4Fh+var_B0]
0x18008fb61  mov     [rbp+4Fh+var_A4], 1
0x18008fb65  cmovnz  edi, [rbp+4Fh+var_A8]
0x18008fb69  lea     rcx, [rbp+4Fh+var_A0]
0x18008fb6d  mov     [rbp+4Fh+var_B0], edi
0x18008fb70  mov     [rbp+4Fh+var_A8], 1
0x18008fb77  mov     [rbp+4Fh+var_AC], 1
0x18008fb7b  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008fb80  cmp     byte ptr [rax+4], 0
0x18008fb84  jz      short loc_18008FBC5
0x18008fb86  movsxd  rax, dword ptr [rax]
0x18008fb89  mov     ecx, 0FFFFFFFFh
0x18008fb8e  movsxd  rdi, edi
0x18008fb91  sub     rdi, rax
0x18008fb94  mov     eax, 80000000h
0x18008fb99  add     rax, rdi
0x18008fb9c  cmp     rax, rcx
0x18008fb9f  ja      short loc_18008FBB1
0x18008fba1  mov     al, 1
0x18008fba3  xor     r11d, r11d
0x18008fba6  jmp     short loc_18008FBB9
0x18008fba8  xor     cl, cl
0x18008fbaa  xor     edi, edi
0x18008fbac  mov     r14d, edi
0x18008fbaf  jmp     short loc_18008FB32
0x18008fbb1  xor     al, al
0x18008fbb3  xor     r11d, r11d
0x18008fbb6  mov     edi, r11d
0x18008fbb9  test    al, al
0x18008fbbb  jz      short loc_18008FBC8
0x18008fbbd  test    edi, edi
0x18008fbbf  cmovnz  edi, r11d
0x18008fbc3  jmp     short loc_18008FBCB
0x18008fbc5  xor     r11d, r11d
0x18008fbc8  mov     edi, r11d
0x18008fbcb  cmp     dword ptr [r15+8], 0
0x18008fbd0  mov     esi, r11d
0x18008fbd3  jle     loc_18008FCFD
0x18008fbd9  nop     dword ptr [rax+00000000h]
0x18008fbe0  mov     r9, [r13+0]
0x18008fbe4  mov     rcx, [rbx+8]
0x18008fbe8  mov     edx, [rbx]
0x18008fbea  mov     r10d, [rbx+18h]
0x18008fbee  inc     edx
0x18008fbf0  mov     r8, [rbx+10h]
0x18008fbf4  lea     rax, [r9+rcx*2]
0x18008fbf8  mov     [rbp+4Fh+var_78], rax
0x18008fbfc  cmp     edx, r10d
0x18008fbff  jl      short loc_18008FC09
0x18008fc01  mov     edx, r11d
0x18008fc04  mov     rcx, r11
0x18008fc07  jmp     short loc_18008FC0C
0x18008fc09  add     rcx, r8
0x18008fc0c  inc     edx
0x18008fc0e  lea     rax, [r9+rcx*2]
0x18008fc12  mov     [rbp+4Fh+var_70], rax
0x18008fc16  cmp     edx, r10d
0x18008fc19  jl      short loc_18008FC23
0x18008fc1b  mov     edx, r11d
0x18008fc1e  mov     rcx, r11
0x18008fc21  jmp     short loc_18008FC26
0x18008fc23  add     rcx, r8
0x18008fc26  inc     edx
0x18008fc28  lea     rax, [r9+rcx*2]
0x18008fc2c  mov     [rbp+4Fh+var_68], rax
0x18008fc30  cmp     edx, r10d
0x18008fc33  jl      short loc_18008FC3D
0x18008fc35  mov     edx, r11d
0x18008fc38  mov     rcx, r11
0x18008fc3b  jmp     short loc_18008FC40
0x18008fc3d  add     rcx, r8
0x18008fc40  inc     edx
0x18008fc42  lea     rax, [r9+rcx*2]
0x18008fc46  mov     [rbp+4Fh+var_60], rax
0x18008fc4a  cmp     edx, r10d
0x18008fc4d  jl      short loc_18008FC57
0x18008fc4f  mov     edx, r11d
0x18008fc52  mov     rcx, r11
0x18008fc55  jmp     short loc_18008FC5A
0x18008fc57  add     rcx, r8
0x18008fc5a  inc     edx
0x18008fc5c  lea     rax, [r9+rcx*2]
0x18008fc60  mov     [rbp+4Fh+var_58], rax
0x18008fc64  cmp     edx, r10d
0x18008fc67  jl      short loc_18008FC71
0x18008fc69  mov     edx, r11d
0x18008fc6c  mov     rcx, r11
0x18008fc6f  jmp     short loc_18008FC74
0x18008fc71  add     rcx, r8
0x18008fc74  inc     edx
0x18008fc76  lea     rax, [r9+rcx*2]
0x18008fc7a  mov     [rbp+4Fh+var_50], rax
0x18008fc7e  cmp     edx, r10d
0x18008fc81  jl      short loc_18008FC88
0x18008fc83  mov     rcx, r11
0x18008fc86  jmp     short loc_18008FC8B
0x18008fc88  add     rcx, r8
0x18008fc8b  lea     rax, [r9+rcx*2]
0x18008fc8f  mov     [rsp+0E0h+var_C0], edi
0x18008fc93  lea     r9, [rbp+4Fh+var_78]
0x18008fc97  mov     [rbp+4Fh+var_48], rax
0x18008fc9b  mov     ecx, r14d
0x18008fc9e  mov     r8, r15
0x18008fca1  mov     rdx, r12
0x18008fca4  call    ??$PutBooleanUnit@VUniqueFact@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY06$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::UniqueFact,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[7],int)
0x18008fca9  xor     r11d, r11d
0x18008fcac  movsxd  rax, edi
0x18008fcaf  lea     rdx, ?GlobalCase@UniqueFact@Policy@Binary@@2V?$StripedCategory@H$00@Data@@B; Data::StripedCategory<int,1> const Binary::Policy::UniqueFact::GlobalCase
0x18008fcb6  mov     ecx, r11d
0x18008fcb9  cmp     [rdx+rax*4], r11d
0x18008fcbd  lea     rdx, [rdx+rax*4]
0x18008fcc1  jle     short loc_18008FCE5
0x18008fcc3  mov     r8d, [rbx+18h]
0x18008fcc7  inc     dword ptr [rbx]
0x18008fcc9  cmp     [rbx], r8d
0x18008fccc  jl      short loc_18008FCD7
0x18008fcce  mov     [rbx], r11d
0x18008fcd1  mov     [rbx+8], r11
0x18008fcd5  jmp     short loc_18008FCDF
0x18008fcd7  mov     rax, [rbx+10h]
0x18008fcdb  add     [rbx+8], rax
0x18008fcdf  inc     ecx
0x18008fce1  cmp     ecx, [rdx]
0x18008fce3  jl      short loc_18008FCC7
0x18008fce5  lea     ecx, [rdi+1]
0x18008fce8  inc     esi
0x18008fcea  cmp     ecx, 1
0x18008fced  mov     edi, r11d
0x18008fcf0  cmovl   edi, ecx
0x18008fcf3  cmp     esi, [r15+8]
0x18008fcf7  jl      loc_18008FBE0
0x18008fcfd  mov     rcx, [rbp+4Fh+var_40]
0x18008fd01  xor     rcx, rsp; StackCookie
0x18008fd04  call    __security_check_cookie
0x18008fd09  mov     rbx, [rsp+0E0h+arg_0]
0x18008fd11  add     rsp, 0B0h
0x18008fd18  pop     r15
0x18008fd1a  pop     r14
0x18008fd1c  pop     r13
0x18008fd1e  pop     r12
0x18008fd20  pop     rdi
0x18008fd21  pop     rsi
0x18008fd22  pop     rbp
0x18008fd23  retn
```
