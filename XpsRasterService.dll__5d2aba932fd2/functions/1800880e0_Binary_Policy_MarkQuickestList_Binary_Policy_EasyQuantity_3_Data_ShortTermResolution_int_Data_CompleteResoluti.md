# Binary::Policy::MarkQuickestList<Binary::Policy::EasyQuantity,3>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x1800880e0`
- end: `0x180088396`
- name: `??$MarkQuickestList@VEasyQuantity@Policy@Binary@@$02@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `694`
- prototype: `char __fastcall(_DWORD *, __int64, __int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008d660`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x1800880e0`
- `0x180089230`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::EasyQuantity,3>(
        _DWORD *a1,
        __int64 a2,
        __int64 *a3,
        int a4,
        __int64 a5)
{
  __int64 v10; // r14
  bool v11; // zf
  int v12; // edi
  int *v13; // rax
  char v14; // cl
  __int64 v15; // rcx
  int v16; // edi
  int *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdi
  int v20; // esi
  __int64 v22; // r9
  int v25; // edx
  __int64 v26; // rcx
  int v27; // edx
  __int64 v28; // rcx
  int v29; // edx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // ecx
  int v33; // r8d
  int v34; // ecx
  bool v35; // sf
  int v37; // [rsp+30h] [rbp-51h] BYREF
  char v38; // [rsp+34h] [rbp-4Dh]
  int v39; // [rsp+38h] [rbp-49h] BYREF
  char v40; // [rsp+3Ch] [rbp-45h]
  _BYTE v41[8]; // [rsp+40h] [rbp-41h] BYREF
  __m256 v42; // [rsp+48h] [rbp-39h]
  _QWORD v43[5]; // [rsp+68h] [rbp-19h] BYREF

  _RBX = a2;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v37, 3, 2, 0, a1[1] + 2);
  LODWORD(v10) = 0;
  v40 = 1;
  v11 = v38 == 0;
  v12 = 0;
  v38 = 1;
  if ( !v11 )
    v12 = v37;
  v39 = v12;
  v37 = 2;
  v13 = (int *)Data::FillClearSkill(v41, &v39, &v37);
  v14 = *((_BYTE *)v13 + 4);
  if ( v14 )
  {
    v15 = 2LL * *v13;
    if ( (unsigned __int64)(v15 + 0x80000000LL) > 0xFFFFFFFF )
    {
      v14 = 0;
    }
    else
    {
      v10 = v12 - (__int64)(int)v15;
      if ( (unsigned __int64)(v10 + 0x80000000LL) > 0xFFFFFFFF )
      {
        v14 = 0;
        v16 = 0;
        LODWORD(v10) = 0;
        goto LABEL_10;
      }
      v14 = 1;
    }
  }
  v16 = 0;
LABEL_10:
  if ( !v14 )
    LODWORD(v10) = 0;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v39, 3, 2, 0, *a1 + 2);
  v11 = v40 == 0;
  v40 = 1;
  if ( !v11 )
    v16 = v39;
  v37 = v16;
  v39 = 2;
  v38 = 1;
  v17 = (int *)Data::FillClearSkill(v41, &v37, &v39);
  if ( *((_BYTE *)v17 + 4)
    && (v18 = 2LL * *v17, LOBYTE(v17) = 2 * *v17, (unsigned __int64)(v18 + 0x80000000LL) <= 0xFFFFFFFF)
    && ((v19 = v16 - (__int64)(int)v18, (unsigned __int64)(v19 + 0x80000000LL) > 0xFFFFFFFF)
      ? (LOBYTE(v17) = 0, LODWORD(v19) = 0)
      : (LOBYTE(v17) = 1),
        (_BYTE)v17) )
  {
    if ( (unsigned int)v19 > 1 )
      LODWORD(v19) = (int)v19 % 2 + ((int)v19 % 2 < 0 ? 2 : 0);
  }
  else
  {
    LODWORD(v19) = 0;
  }
  v20 = 0;
  while ( v20 < *(_DWORD *)(a5 + 8) )
  {
    __asm { vmovups ymm0, ymmword ptr [rbx] }
    v22 = *a3;
    __asm { vmovups [rbp+4Fh+var_88], ymm0 }
    __asm
    {
      vpextrq rcx, xmm0, 1
      vmovd   edx, xmm0
    }
    v25 = _EDX + 1;
    v43[0] = v22 + 2 * _RCX;
    if ( v25 < SLODWORD(v42.m256_f32[6]) )
    {
      v26 = *(_QWORD *)&v42.m256_f32[4] + _RCX;
    }
    else
    {
      v25 = 0;
      v26 = 0;
    }
    v27 = v25 + 1;
    v43[1] = v22 + 2 * v26;
    if ( v27 < SLODWORD(v42.m256_f32[6]) )
    {
      v28 = *(_QWORD *)&v42.m256_f32[4] + v26;
    }
    else
    {
      v27 = 0;
      v28 = 0;
    }
    v29 = v27 + 1;
    v43[2] = v22 + 2 * v28;
    if ( v29 < SLODWORD(v42.m256_f32[6]) )
    {
      v30 = *(_QWORD *)&v42.m256_f32[4] + v28;
    }
    else
    {
      v29 = 0;
      v30 = 0;
    }
    v43[3] = v22 + 2 * v30;
    if ( v29 + 1 < SLODWORD(v42.m256_f32[6]) )
      v31 = *(_QWORD *)&v42.m256_f32[4] + v30;
    else
      v31 = 0;
    v43[4] = v22 + 2 * v31;
    __asm { vzeroupper }
    Binary::Policy::PutBooleanUnit<Binary::Policy::EasyQuantity,3>(v10, a4, a5, (unsigned int)v43, v19);
    LOBYTE(v17) = v19;
    v32 = 0;
    if ( Binary::Policy::EasyQuantity::GlobalCase[(int)v19] > 0 )
    {
      v33 = *(_DWORD *)(_RBX + 24);
      do
      {
        if ( ++*(_DWORD *)_RBX < v33 )
        {
          v17 = (int *)(*(_QWORD *)(_RBX + 16) + *(_QWORD *)(_RBX + 8));
          *(_QWORD *)(_RBX + 8) = v17;
        }
        else
        {
          *(_DWORD *)_RBX = 0;
          *(_QWORD *)(_RBX + 8) = 0;
        }
        ++v32;
      }
      while ( v32 < Binary::Policy::EasyQuantity::GlobalCase[(int)v19] );
    }
    v34 = v19 + 1;
    ++v20;
    v35 = (int)v19 - 1 < 0;
    LODWORD(v19) = 0;
    if ( v35 != __OFSUB__(v34, 2) )
      LODWORD(v19) = v34;
  }
  return (char)v17;
}

```

## disassembly

```asm
0x1800880e0  mov     [rsp-8+arg_0], rbx
0x1800880e5  push    rbp
0x1800880e6  push    rsi
0x1800880e7  push    rdi
0x1800880e8  push    r12
0x1800880ea  push    r13
0x1800880ec  push    r14
0x1800880ee  push    r15
0x1800880f0  lea     rbp, [rsp-1Fh]
0x1800880f5  sub     rsp, 0A0h
0x1800880fc  mov     rax, cs:__security_cookie
0x180088103  xor     rax, rsp
0x180088106  mov     [rbp+4Fh+var_40], rax
0x18008810a  mov     eax, [rcx+4]
0x18008810d  mov     r12, r9
0x180088110  mov     r15, [rbp+4Fh+arg_20]
0x180088114  xor     r9d, r9d
0x180088117  mov     r13, r8
0x18008811a  mov     rbx, rdx
0x18008811d  mov     rsi, rcx
0x180088120  add     eax, 2
0x180088123  lea     rcx, [rbp+4Fh+var_A0]
0x180088127  mov     [rsp+0D0h+var_B0], eax
0x18008812b  lea     edx, [r9+3]
0x18008812f  lea     r8d, [r9+2]
0x180088133  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180088138  xor     r14d, r14d
0x18008813b  mov     [rbp+4Fh+var_94], 1
0x18008813f  cmp     [rbp+4Fh+var_9C], r14b
0x180088143  lea     r8, [rbp+4Fh+var_A0]
0x180088147  mov     edi, r14d
0x18008814a  mov     [rbp+4Fh+var_9C], 1
0x18008814e  cmovnz  edi, [rbp+4Fh+var_A0]
0x180088152  lea     rdx, [rbp+4Fh+var_98]
0x180088156  lea     rcx, [rbp+4Fh+var_90]
0x18008815a  mov     [rbp+4Fh+var_98], edi
0x18008815d  mov     [rbp+4Fh+var_A0], 2
0x180088164  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x180088169  mov     edx, 80000000h
0x18008816e  mov     r8d, 0FFFFFFFFh
0x180088174  movzx   ecx, byte ptr [rax+4]
0x180088178  test    cl, cl
0x18008817a  jz      short loc_1800881AC
0x18008817c  movsxd  rcx, dword ptr [rax]
0x18008817f  add     rcx, rcx
0x180088182  lea     rax, [rcx+rdx]
0x180088186  cmp     rax, r8
0x180088189  ja      short loc_1800881AA
0x18008818b  movsxd  rax, ecx
0x18008818e  movsxd  r14, edi
0x180088191  sub     r14, rax
0x180088194  lea     rax, [r14+rdx]
0x180088198  cmp     rax, r8
0x18008819b  ja      short loc_1800881A1
0x18008819d  mov     cl, 1
0x18008819f  jmp     short loc_1800881AC
0x1800881a1  xor     cl, cl
0x1800881a3  xor     edi, edi
0x1800881a5  mov     r14d, edi
0x1800881a8  jmp     short loc_1800881AE
0x1800881aa  xor     cl, cl
0x1800881ac  xor     edi, edi
0x1800881ae  mov     eax, [rsi]
0x1800881b0  test    cl, cl
0x1800881b2  lea     rcx, [rbp+4Fh+var_98]
0x1800881b6  cmovz   r14d, edi
0x1800881ba  xor     r9d, r9d
0x1800881bd  add     eax, 2
0x1800881c0  mov     [rsp+0D0h+var_B0], eax
0x1800881c4  lea     edx, [r9+3]
0x1800881c8  lea     r8d, [r9+2]
0x1800881cc  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x1800881d1  cmp     [rbp+4Fh+var_94], 0
0x1800881d5  lea     r8, [rbp+4Fh+var_98]
0x1800881d9  lea     rdx, [rbp+4Fh+var_A0]
0x1800881dd  mov     [rbp+4Fh+var_94], 1
0x1800881e1  cmovnz  edi, [rbp+4Fh+var_98]
0x1800881e5  lea     rcx, [rbp+4Fh+var_90]
0x1800881e9  mov     [rbp+4Fh+var_A0], edi
0x1800881ec  mov     [rbp+4Fh+var_98], 2
0x1800881f3  mov     [rbp+4Fh+var_9C], 1
0x1800881f7  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x1800881fc  cmp     byte ptr [rax+4], 0
0x180088200  jz      short loc_18008825E
0x180088202  movsxd  rcx, dword ptr [rax]
0x180088205  mov     edx, 80000000h
0x18008820a  add     rcx, rcx
0x18008820d  mov     r8d, 0FFFFFFFFh
0x180088213  lea     rax, [rcx+rdx]
0x180088217  cmp     rax, r8
0x18008821a  ja      short loc_18008825E
0x18008821c  movsxd  rax, ecx
0x18008821f  movsxd  rdi, edi
0x180088222  sub     rdi, rax
0x180088225  lea     rax, [rdi+rdx]
0x180088229  cmp     rax, r8
0x18008822c  ja      short loc_180088235
0x18008822e  mov     al, 1
0x180088230  xor     r11d, r11d
0x180088233  jmp     short loc_18008823D
0x180088235  xor     al, al
0x180088237  xor     r11d, r11d
0x18008823a  mov     edi, r11d
0x18008823d  test    al, al
0x18008823f  jz      short loc_180088261
0x180088241  cmp     edi, 1
0x180088244  jbe     short loc_180088264
0x180088246  and     edi, 80000001h
0x18008824c  jge     short loc_180088255
0x18008824e  dec     edi
0x180088250  or      edi, 0FFFFFFFEh
0x180088253  inc     edi
0x180088255  test    edi, edi
0x180088257  jns     short loc_180088264
0x180088259  add     edi, 2
0x18008825c  jmp     short loc_180088264
0x18008825e  xor     r11d, r11d
0x180088261  mov     edi, r11d
0x180088264  cmp     dword ptr [r15+8], 0
0x180088269  mov     esi, r11d
0x18008826c  jle     loc_18008836F
0x180088272  vmovups ymm0, ymmword ptr [rbx]
0x180088276  mov     r9, [r13+0]
0x18008827a  vmovups [rbp+4Fh+var_88], ymm0
0x18008827f  mov     r10d, dword ptr [rbp+4Fh+var_88+18h]
0x180088283  mov     r8, qword ptr [rbp+4Fh+var_88+10h]
0x180088287  vpextrq rcx, xmm0, 1
0x18008828d  vmovd   edx, xmm0
0x180088291  inc     edx
0x180088293  lea     rax, [r9+rcx*2]
0x180088297  mov     [rbp+4Fh+var_68], rax
0x18008829b  cmp     edx, r10d
0x18008829e  jl      short loc_1800882A8
0x1800882a0  mov     edx, r11d
0x1800882a3  mov     rcx, r11
0x1800882a6  jmp     short loc_1800882AB
0x1800882a8  add     rcx, r8
0x1800882ab  inc     edx
0x1800882ad  lea     rax, [r9+rcx*2]
0x1800882b1  mov     [rbp+4Fh+var_60], rax
0x1800882b5  cmp     edx, r10d
0x1800882b8  jl      short loc_1800882C2
0x1800882ba  mov     edx, r11d
0x1800882bd  mov     rcx, r11
0x1800882c0  jmp     short loc_1800882C5
0x1800882c2  add     rcx, r8
0x1800882c5  inc     edx
0x1800882c7  lea     rax, [r9+rcx*2]
0x1800882cb  mov     [rbp+4Fh+var_58], rax
0x1800882cf  cmp     edx, r10d
0x1800882d2  jl      short loc_1800882DC
0x1800882d4  mov     edx, r11d
0x1800882d7  mov     rcx, r11
0x1800882da  jmp     short loc_1800882DF
0x1800882dc  add     rcx, r8
0x1800882df  inc     edx
0x1800882e1  lea     rax, [r9+rcx*2]
0x1800882e5  mov     [rbp+4Fh+var_50], rax
0x1800882e9  cmp     edx, r10d
0x1800882ec  jl      short loc_1800882F3
0x1800882ee  mov     rcx, r11
0x1800882f1  jmp     short loc_1800882F6
0x1800882f3  add     rcx, r8
0x1800882f6  lea     rax, [r9+rcx*2]
0x1800882fa  mov     [rsp+0D0h+var_B0], edi
0x1800882fe  mov     [rbp+4Fh+var_48], rax
0x180088302  lea     r9, [rbp+4Fh+var_68]
0x180088306  mov     r8, r15
0x180088309  mov     rdx, r12
0x18008830c  mov     ecx, r14d
0x18008830f  vzeroupper
0x180088312  call    ??$PutBooleanUnit@VEasyQuantity@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY04$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::EasyQuantity,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[5],int)
0x180088317  xor     r11d, r11d
0x18008831a  movsxd  rax, edi
0x18008831d  lea     rdx, ?GlobalCase@EasyQuantity@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B; Data::StripedCategory<int,2> const Binary::Policy::EasyQuantity::GlobalCase
0x180088324  mov     ecx, r11d
0x180088327  cmp     [rdx+rax*4], r11d
0x18008832b  lea     rdx, [rdx+rax*4]
0x18008832f  jle     short loc_180088357
0x180088331  mov     r8d, [rbx+18h]
0x180088335  inc     dword ptr [rbx]
0x180088337  cmp     [rbx], r8d
0x18008833a  jl      short loc_180088345
0x18008833c  mov     [rbx], r11d
0x18008833f  mov     [rbx+8], r11
0x180088343  jmp     short loc_180088351
0x180088345  mov     rax, [rbx+8]
0x180088349  add     rax, [rbx+10h]
0x18008834d  mov     [rbx+8], rax
0x180088351  inc     ecx
0x180088353  cmp     ecx, [rdx]
0x180088355  jl      short loc_180088335
0x180088357  lea     ecx, [rdi+1]
0x18008835a  inc     esi
0x18008835c  cmp     ecx, 2
0x18008835f  mov     edi, r11d
0x180088362  cmovl   edi, ecx
0x180088365  cmp     esi, [r15+8]
0x180088369  jl      loc_180088272
0x18008836f  mov     rcx, [rbp+4Fh+var_40]
0x180088373  xor     rcx, rsp; StackCookie
0x180088376  call    __security_check_cookie
0x18008837b  mov     rbx, [rsp+0D0h+arg_0]
0x180088383  add     rsp, 0A0h
0x18008838a  pop     r15
0x18008838c  pop     r14
0x18008838e  pop     r13
0x180088390  pop     r12
0x180088392  pop     rdi
0x180088393  pop     rsi
0x180088394  pop     rbp
0x180088395  retn
```
