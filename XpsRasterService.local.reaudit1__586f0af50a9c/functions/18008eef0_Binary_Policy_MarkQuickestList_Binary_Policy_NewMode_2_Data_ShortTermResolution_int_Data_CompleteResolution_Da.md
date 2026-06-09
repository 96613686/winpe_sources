# Binary::Policy::MarkQuickestList<Binary::Policy::NewMode,2>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x18008eef0`
- end: `0x18008f1d4`
- name: `??$MarkQuickestList@VNewMode@Policy@Binary@@$01@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800920e0`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x18008eef0`
- `0x180090300`

## pseudocode

```c
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::NewMode,2>(
        _DWORD *a1,
        __int64 a2,
        __int64 *a3,
        _DWORD *a4,
        _DWORD *a5)
{
  __int64 v9; // r14
  bool v10; // zf
  int v11; // edi
  int *v12; // rax
  char v13; // cl
  __int64 v14; // rcx
  int v15; // edi
  __int64 v16; // rax
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
  __int64 v34; // rcx
  int v35; // ecx
  int v36; // r8d
  int v37; // ecx
  bool v38; // sf
  int v40; // [rsp+30h] [rbp-61h] BYREF
  char v41; // [rsp+34h] [rbp-5Dh]
  int v42; // [rsp+38h] [rbp-59h] BYREF
  char v43; // [rsp+3Ch] [rbp-55h]
  _BYTE v44[40]; // [rsp+40h] [rbp-51h] BYREF
  _QWORD v45[7]; // [rsp+68h] [rbp-29h] BYREF

  Binary::Definition::GenerateAsyncServer((unsigned int)&v40, 7, 2, 2, a1[1] + 3);
  LODWORD(v9) = 0;
  v43 = 1;
  v10 = v41 == 0;
  v11 = 0;
  v41 = 1;
  if ( !v10 )
    v11 = v40;
  v42 = v11;
  v40 = 2;
  v12 = (int *)Data::FillClearSkill(v44, &v42, &v40);
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
  Binary::Definition::GenerateAsyncServer((unsigned int)&v42, 7, 2, 2, *a1 + 3);
  v10 = v43 == 0;
  v43 = 1;
  if ( !v10 )
    v15 = v42;
  v40 = v15;
  v42 = 2;
  v41 = 1;
  v16 = Data::FillClearSkill(v44, &v40, &v42);
  if ( *(_BYTE *)(v16 + 4)
    && (v17 = 2LL * *(int *)v16, LOBYTE(v16) = 2 * *(_DWORD *)v16, (unsigned __int64)(v17 + 0x80000000LL) <= 0xFFFFFFFF)
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
  while ( v19 < a5[2] )
  {
    v20 = *a3;
    v21 = *(_QWORD *)(a2 + 8);
    v22 = *(_DWORD *)(a2 + 24);
    v23 = *(_DWORD *)a2 + 1;
    v24 = *(_QWORD *)(a2 + 16);
    v45[0] = *a3 + 2 * v21;
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
    v45[1] = v20 + 2 * v25;
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
    v45[2] = v20 + 2 * v27;
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
    v45[3] = v20 + 2 * v29;
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
    v45[4] = v20 + 2 * v31;
    if ( v32 < v22 )
    {
      v33 = v24 + v31;
    }
    else
    {
      v32 = 0;
      v33 = 0;
    }
    v45[5] = v20 + 2 * v33;
    if ( v32 + 1 < v22 )
      v34 = v24 + v33;
    else
      v34 = 0;
    v45[6] = v20 + 2 * v34;
    Binary::Policy::PutBooleanUnit<Binary::Policy::NewMode,2>(v9, a4, a5, v45, v18);
    LOBYTE(v16) = v18;
    v35 = 0;
    if ( Binary::Policy::NewMode::GlobalCase[(int)v18] > 0 )
    {
      v36 = *(_DWORD *)(a2 + 24);
      do
      {
        if ( ++*(_DWORD *)a2 < v36 )
        {
          v16 = *(_QWORD *)(a2 + 16);
          *(_QWORD *)(a2 + 8) += v16;
        }
        else
        {
          *(_DWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
        }
        ++v35;
      }
      while ( v35 < Binary::Policy::NewMode::GlobalCase[(int)v18] );
    }
    v37 = v18 + 1;
    ++v19;
    v38 = (int)v18 - 1 < 0;
    LODWORD(v18) = 0;
    if ( v38 != __OFSUB__(v37, 2) )
      LODWORD(v18) = v37;
  }
  return v16;
}

```

## disassembly

```asm
0x18008eef0  mov     [rsp-8+arg_0], rbx
0x18008eef5  push    rbp
0x18008eef6  push    rsi
0x18008eef7  push    rdi
0x18008eef8  push    r12
0x18008eefa  push    r13
0x18008eefc  push    r14
0x18008eefe  push    r15
0x18008ef00  lea     rbp, [rsp-1Fh]
0x18008ef05  sub     rsp, 0B0h
0x18008ef0c  mov     rax, cs:__security_cookie
0x18008ef13  xor     rax, rsp
0x18008ef16  mov     [rbp+4Fh+var_40], rax
0x18008ef1a  mov     eax, [rcx+4]
0x18008ef1d  mov     r12, r9
0x18008ef20  mov     r15, [rbp+4Fh+arg_20]
0x18008ef24  mov     r9d, 2
0x18008ef2a  add     eax, 3
0x18008ef2d  mov     r13, r8
0x18008ef30  mov     rbx, rdx
0x18008ef33  mov     [rsp+0E0h+var_C0], eax
0x18008ef37  mov     rsi, rcx
0x18008ef3a  mov     r8d, r9d
0x18008ef3d  mov     edx, 7
0x18008ef42  lea     rcx, [rbp+4Fh+var_B0]
0x18008ef46  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18008ef4b  xor     r14d, r14d
0x18008ef4e  mov     [rbp+4Fh+var_A4], 1
0x18008ef52  cmp     [rbp+4Fh+var_AC], r14b
0x18008ef56  lea     r8, [rbp+4Fh+var_B0]
0x18008ef5a  mov     edi, r14d
0x18008ef5d  mov     [rbp+4Fh+var_AC], 1
0x18008ef61  cmovnz  edi, [rbp+4Fh+var_B0]
0x18008ef65  lea     rdx, [rbp+4Fh+var_A8]
0x18008ef69  lea     rcx, [rbp+4Fh+var_A0]
0x18008ef6d  mov     [rbp+4Fh+var_A8], edi
0x18008ef70  mov     [rbp+4Fh+var_B0], 2
0x18008ef77  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008ef7c  mov     edx, 80000000h
0x18008ef81  mov     r8d, 0FFFFFFFFh
0x18008ef87  movzx   ecx, byte ptr [rax+4]
0x18008ef8b  test    cl, cl
0x18008ef8d  jz      short loc_18008EFBF
0x18008ef8f  movsxd  rcx, dword ptr [rax]
0x18008ef92  add     rcx, rcx
0x18008ef95  lea     rax, [rcx+rdx]
0x18008ef99  cmp     rax, r8
0x18008ef9c  ja      short loc_18008EFBD
0x18008ef9e  movsxd  rax, ecx
0x18008efa1  movsxd  r14, edi
0x18008efa4  sub     r14, rax
0x18008efa7  lea     rax, [r14+rdx]
0x18008efab  cmp     rax, r8
0x18008efae  ja      short loc_18008EFB4
0x18008efb0  mov     cl, 1
0x18008efb2  jmp     short loc_18008EFBF
0x18008efb4  xor     cl, cl
0x18008efb6  xor     edi, edi
0x18008efb8  mov     r14d, edi
0x18008efbb  jmp     short loc_18008EFC1
0x18008efbd  xor     cl, cl
0x18008efbf  xor     edi, edi
0x18008efc1  mov     eax, [rsi]
0x18008efc3  test    cl, cl
0x18008efc5  mov     r9d, 2
0x18008efcb  lea     rcx, [rbp+4Fh+var_A8]
0x18008efcf  cmovz   r14d, edi
0x18008efd3  mov     edx, 7
0x18008efd8  add     eax, 3
0x18008efdb  mov     r8d, r9d
0x18008efde  mov     [rsp+0E0h+var_C0], eax
0x18008efe2  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18008efe7  cmp     [rbp+4Fh+var_A4], 0
0x18008efeb  lea     r8, [rbp+4Fh+var_A8]
0x18008efef  lea     rdx, [rbp+4Fh+var_B0]
0x18008eff3  mov     [rbp+4Fh+var_A4], 1
0x18008eff7  cmovnz  edi, [rbp+4Fh+var_A8]
0x18008effb  lea     rcx, [rbp+4Fh+var_A0]
0x18008efff  mov     [rbp+4Fh+var_B0], edi
0x18008f002  mov     [rbp+4Fh+var_A8], 2
0x18008f009  mov     [rbp+4Fh+var_AC], 1
0x18008f00d  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008f012  cmp     byte ptr [rax+4], 0
0x18008f016  jz      short loc_18008F074
0x18008f018  movsxd  rcx, dword ptr [rax]
0x18008f01b  mov     edx, 80000000h
0x18008f020  add     rcx, rcx
0x18008f023  mov     r8d, 0FFFFFFFFh
0x18008f029  lea     rax, [rcx+rdx]
0x18008f02d  cmp     rax, r8
0x18008f030  ja      short loc_18008F074
0x18008f032  movsxd  rax, ecx
0x18008f035  movsxd  rdi, edi
0x18008f038  sub     rdi, rax
0x18008f03b  lea     rax, [rdi+rdx]
0x18008f03f  cmp     rax, r8
0x18008f042  ja      short loc_18008F04B
0x18008f044  mov     al, 1
0x18008f046  xor     r11d, r11d
0x18008f049  jmp     short loc_18008F053
0x18008f04b  xor     al, al
0x18008f04d  xor     r11d, r11d
0x18008f050  mov     edi, r11d
0x18008f053  test    al, al
0x18008f055  jz      short loc_18008F077
0x18008f057  cmp     edi, 1
0x18008f05a  jbe     short loc_18008F07A
0x18008f05c  and     edi, 80000001h
0x18008f062  jge     short loc_18008F06B
0x18008f064  dec     edi
0x18008f066  or      edi, 0FFFFFFFEh
0x18008f069  inc     edi
0x18008f06b  test    edi, edi
0x18008f06d  jns     short loc_18008F07A
0x18008f06f  add     edi, 2
0x18008f072  jmp     short loc_18008F07A
0x18008f074  xor     r11d, r11d
0x18008f077  mov     edi, r11d
0x18008f07a  cmp     dword ptr [r15+8], 0
0x18008f07f  mov     esi, r11d
0x18008f082  jle     loc_18008F1AD
0x18008f088  nop     dword ptr [rax+rax+00000000h]
0x18008f090  mov     r9, [r13+0]
0x18008f094  mov     rcx, [rbx+8]
0x18008f098  mov     edx, [rbx]
0x18008f09a  mov     r10d, [rbx+18h]
0x18008f09e  inc     edx
0x18008f0a0  mov     r8, [rbx+10h]
0x18008f0a4  lea     rax, [r9+rcx*2]
0x18008f0a8  mov     [rbp+4Fh+var_78], rax
0x18008f0ac  cmp     edx, r10d
0x18008f0af  jl      short loc_18008F0B9
0x18008f0b1  mov     edx, r11d
0x18008f0b4  mov     rcx, r11
0x18008f0b7  jmp     short loc_18008F0BC
0x18008f0b9  add     rcx, r8
0x18008f0bc  inc     edx
0x18008f0be  lea     rax, [r9+rcx*2]
0x18008f0c2  mov     [rbp+4Fh+var_70], rax
0x18008f0c6  cmp     edx, r10d
0x18008f0c9  jl      short loc_18008F0D3
0x18008f0cb  mov     edx, r11d
0x18008f0ce  mov     rcx, r11
0x18008f0d1  jmp     short loc_18008F0D6
0x18008f0d3  add     rcx, r8
0x18008f0d6  inc     edx
0x18008f0d8  lea     rax, [r9+rcx*2]
0x18008f0dc  mov     [rbp+4Fh+var_68], rax
0x18008f0e0  cmp     edx, r10d
0x18008f0e3  jl      short loc_18008F0ED
0x18008f0e5  mov     edx, r11d
0x18008f0e8  mov     rcx, r11
0x18008f0eb  jmp     short loc_18008F0F0
0x18008f0ed  add     rcx, r8
0x18008f0f0  inc     edx
0x18008f0f2  lea     rax, [r9+rcx*2]
0x18008f0f6  mov     [rbp+4Fh+var_60], rax
0x18008f0fa  cmp     edx, r10d
0x18008f0fd  jl      short loc_18008F107
0x18008f0ff  mov     edx, r11d
0x18008f102  mov     rcx, r11
0x18008f105  jmp     short loc_18008F10A
0x18008f107  add     rcx, r8
0x18008f10a  inc     edx
0x18008f10c  lea     rax, [r9+rcx*2]
0x18008f110  mov     [rbp+4Fh+var_58], rax
0x18008f114  cmp     edx, r10d
0x18008f117  jl      short loc_18008F121
0x18008f119  mov     edx, r11d
0x18008f11c  mov     rcx, r11
0x18008f11f  jmp     short loc_18008F124
0x18008f121  add     rcx, r8
0x18008f124  inc     edx
0x18008f126  lea     rax, [r9+rcx*2]
0x18008f12a  mov     [rbp+4Fh+var_50], rax
0x18008f12e  cmp     edx, r10d
0x18008f131  jl      short loc_18008F138
0x18008f133  mov     rcx, r11
0x18008f136  jmp     short loc_18008F13B
0x18008f138  add     rcx, r8
0x18008f13b  lea     rax, [r9+rcx*2]
0x18008f13f  mov     [rsp+0E0h+var_C0], edi
0x18008f143  lea     r9, [rbp+4Fh+var_78]
0x18008f147  mov     [rbp+4Fh+var_48], rax
0x18008f14b  mov     ecx, r14d
0x18008f14e  mov     r8, r15
0x18008f151  mov     rdx, r12
0x18008f154  call    ??$PutBooleanUnit@VNewMode@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY06$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::NewMode,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[7],int)
0x18008f159  xor     r11d, r11d
0x18008f15c  movsxd  rax, edi
0x18008f15f  lea     rdx, ?GlobalCase@NewMode@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B; Data::StripedCategory<int,2> const Binary::Policy::NewMode::GlobalCase
0x18008f166  mov     ecx, r11d
0x18008f169  cmp     [rdx+rax*4], r11d
0x18008f16d  lea     rdx, [rdx+rax*4]
0x18008f171  jle     short loc_18008F195
0x18008f173  mov     r8d, [rbx+18h]
0x18008f177  inc     dword ptr [rbx]
0x18008f179  cmp     [rbx], r8d
0x18008f17c  jl      short loc_18008F187
0x18008f17e  mov     [rbx], r11d
0x18008f181  mov     [rbx+8], r11
0x18008f185  jmp     short loc_18008F18F
0x18008f187  mov     rax, [rbx+10h]
0x18008f18b  add     [rbx+8], rax
0x18008f18f  inc     ecx
0x18008f191  cmp     ecx, [rdx]
0x18008f193  jl      short loc_18008F177
0x18008f195  lea     ecx, [rdi+1]
0x18008f198  inc     esi
0x18008f19a  cmp     ecx, 2
0x18008f19d  mov     edi, r11d
0x18008f1a0  cmovl   edi, ecx
0x18008f1a3  cmp     esi, [r15+8]
0x18008f1a7  jl      loc_18008F090
0x18008f1ad  mov     rcx, [rbp+4Fh+var_40]
0x18008f1b1  xor     rcx, rsp; StackCookie
0x18008f1b4  call    __security_check_cookie
0x18008f1b9  mov     rbx, [rsp+0E0h+arg_0]
0x18008f1c1  add     rsp, 0B0h
0x18008f1c8  pop     r15
0x18008f1ca  pop     r14
0x18008f1cc  pop     r13
0x18008f1ce  pop     r12
0x18008f1d0  pop     rdi
0x18008f1d1  pop     rsi
0x18008f1d2  pop     rbp
0x18008f1d3  retn
```
