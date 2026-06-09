# Binary::Policy::MarkQuickestList<Binary::Policy::SlowSource,3>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x1800886a0`
- end: `0x1800889b2`
- name: `??$MarkQuickestList@VSlowSource@Policy@Binary@@$02@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `786`
- prototype: `char __fastcall(_DWORD *, __int64, __int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008b130`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x1800886a0`
- `0x180089c70`

## pseudocode

```c
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::SlowSource,3>(
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
  int v31; // edx
  __int64 v32; // rcx
  int v33; // edx
  __int64 v34; // rcx
  int v35; // edx
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v38; // ecx
  int v39; // r8d
  int v40; // ecx
  bool v41; // sf
  int v43; // [rsp+30h] [rbp-71h] BYREF
  char v44; // [rsp+34h] [rbp-6Dh]
  int v45; // [rsp+38h] [rbp-69h] BYREF
  char v46; // [rsp+3Ch] [rbp-65h]
  _BYTE v47[8]; // [rsp+40h] [rbp-61h] BYREF
  __m256 v48; // [rsp+48h] [rbp-59h]
  _QWORD v49[8]; // [rsp+70h] [rbp-31h] BYREF

  _RBX = a2;
  Binary::Definition::GenerateAsyncServer((unsigned int)&v43, 5, 4, 4, a1[1] + 3);
  LODWORD(v10) = 0;
  v46 = 1;
  v11 = v44 == 0;
  v12 = 0;
  v44 = 1;
  if ( !v11 )
    v12 = v43;
  v45 = v12;
  v43 = 4;
  v13 = (int *)Data::FillClearSkill(v47, &v45, &v43);
  v14 = *((_BYTE *)v13 + 4);
  if ( v14 )
  {
    v15 = 4LL * *v13;
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
  Binary::Definition::GenerateAsyncServer((unsigned int)&v45, 5, 4, 4, *a1 + 3);
  v11 = v46 == 0;
  v46 = 1;
  if ( !v11 )
    v16 = v45;
  v43 = v16;
  v45 = 4;
  v44 = 1;
  v17 = (int *)Data::FillClearSkill(v47, &v43, &v45);
  if ( *((_BYTE *)v17 + 4)
    && (v18 = 4LL * *v17, LOBYTE(v17) = 4 * *v17, (unsigned __int64)(v18 + 0x80000000LL) <= 0xFFFFFFFF)
    && ((v19 = v16 - (__int64)(int)v18, (unsigned __int64)(v19 + 0x80000000LL) > 0xFFFFFFFF)
      ? (LOBYTE(v17) = 0, LODWORD(v19) = 0)
      : (LOBYTE(v17) = 1),
        (_BYTE)v17) )
  {
    if ( (unsigned int)v19 > 3 )
      LODWORD(v19) = (int)v19 % 4 + ((int)v19 % 4 < 0 ? 4 : 0);
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
    __asm { vmovups [rbp+4Fh+var_A8], ymm0 }
    __asm
    {
      vpextrq rcx, xmm0, 1
      vmovd   edx, xmm0
    }
    v25 = _EDX + 1;
    v49[0] = v22 + 2 * _RCX;
    if ( v25 < SLODWORD(v48.m256_f32[6]) )
    {
      v26 = *(_QWORD *)&v48.m256_f32[4] + _RCX;
    }
    else
    {
      v25 = 0;
      v26 = 0;
    }
    v27 = v25 + 1;
    v49[1] = v22 + 2 * v26;
    if ( v27 < SLODWORD(v48.m256_f32[6]) )
    {
      v28 = *(_QWORD *)&v48.m256_f32[4] + v26;
    }
    else
    {
      v27 = 0;
      v28 = 0;
    }
    v29 = v27 + 1;
    v49[2] = v22 + 2 * v28;
    if ( v29 < SLODWORD(v48.m256_f32[6]) )
    {
      v30 = *(_QWORD *)&v48.m256_f32[4] + v28;
    }
    else
    {
      v29 = 0;
      v30 = 0;
    }
    v31 = v29 + 1;
    v49[3] = v22 + 2 * v30;
    if ( v31 < SLODWORD(v48.m256_f32[6]) )
    {
      v32 = *(_QWORD *)&v48.m256_f32[4] + v30;
    }
    else
    {
      v31 = 0;
      v32 = 0;
    }
    v33 = v31 + 1;
    v49[4] = v22 + 2 * v32;
    if ( v33 < SLODWORD(v48.m256_f32[6]) )
    {
      v34 = *(_QWORD *)&v48.m256_f32[4] + v32;
    }
    else
    {
      v33 = 0;
      v34 = 0;
    }
    v35 = v33 + 1;
    v49[5] = v22 + 2 * v34;
    if ( v35 < SLODWORD(v48.m256_f32[6]) )
    {
      v36 = *(_QWORD *)&v48.m256_f32[4] + v34;
    }
    else
    {
      v35 = 0;
      v36 = 0;
    }
    v49[6] = v22 + 2 * v36;
    if ( v35 + 1 < SLODWORD(v48.m256_f32[6]) )
      v37 = *(_QWORD *)&v48.m256_f32[4] + v36;
    else
      v37 = 0;
    v49[7] = v22 + 2 * v37;
    __asm { vzeroupper }
    Binary::Policy::PutBooleanUnit<Binary::Policy::SlowSource,3>(v10, a4, a5, (unsigned int)v49, v19);
    LOBYTE(v17) = v19;
    v38 = 0;
    if ( Binary::Policy::SlowSource::GlobalCase[(int)v19] > 0 )
    {
      v39 = *(_DWORD *)(_RBX + 24);
      do
      {
        if ( ++*(_DWORD *)_RBX < v39 )
        {
          v17 = (int *)(*(_QWORD *)(_RBX + 16) + *(_QWORD *)(_RBX + 8));
          *(_QWORD *)(_RBX + 8) = v17;
        }
        else
        {
          *(_DWORD *)_RBX = 0;
          *(_QWORD *)(_RBX + 8) = 0;
        }
        ++v38;
      }
      while ( v38 < Binary::Policy::SlowSource::GlobalCase[(int)v19] );
    }
    v40 = v19 + 1;
    ++v20;
    v41 = (int)v19 - 3 < 0;
    LODWORD(v19) = 0;
    if ( v41 != __OFSUB__(v40, 4) )
      LODWORD(v19) = v40;
  }
  return (char)v17;
}

```

## disassembly

```asm
0x1800886a0  mov     [rsp-8+arg_0], rbx
0x1800886a5  push    rbp
0x1800886a6  push    rsi
0x1800886a7  push    rdi
0x1800886a8  push    r12
0x1800886aa  push    r13
0x1800886ac  push    r14
0x1800886ae  push    r15
0x1800886b0  lea     rbp, [rsp-1Fh]
0x1800886b5  sub     rsp, 0C0h
0x1800886bc  mov     rax, cs:__security_cookie
0x1800886c3  xor     rax, rsp
0x1800886c6  mov     [rbp+4Fh+var_40], rax
0x1800886ca  mov     eax, [rcx+4]
0x1800886cd  mov     r12, r9
0x1800886d0  mov     r15, [rbp+4Fh+arg_20]
0x1800886d4  mov     r9d, 4
0x1800886da  add     eax, 3
0x1800886dd  mov     r13, r8
0x1800886e0  mov     rbx, rdx
0x1800886e3  mov     [rsp+0F0h+var_D0], eax
0x1800886e7  mov     rsi, rcx
0x1800886ea  mov     r8d, r9d
0x1800886ed  mov     edx, 5
0x1800886f2  lea     rcx, [rbp+4Fh+var_C0]
0x1800886f6  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x1800886fb  xor     r14d, r14d
0x1800886fe  mov     [rbp+4Fh+var_B4], 1
0x180088702  cmp     [rbp+4Fh+var_BC], r14b
0x180088706  lea     r8, [rbp+4Fh+var_C0]
0x18008870a  mov     edi, r14d
0x18008870d  mov     [rbp+4Fh+var_BC], 1
0x180088711  cmovnz  edi, [rbp+4Fh+var_C0]
0x180088715  lea     rdx, [rbp+4Fh+var_B8]
0x180088719  lea     rcx, [rbp+4Fh+var_B0]
0x18008871d  mov     [rbp+4Fh+var_B8], edi
0x180088720  mov     [rbp+4Fh+var_C0], 4
0x180088727  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008872c  mov     edx, 80000000h
0x180088731  mov     r8d, 0FFFFFFFFh
0x180088737  movzx   ecx, byte ptr [rax+4]
0x18008873b  test    cl, cl
0x18008873d  jz      short loc_180088770
0x18008873f  movsxd  rcx, dword ptr [rax]
0x180088742  shl     rcx, 2
0x180088746  lea     rax, [rcx+rdx]
0x18008874a  cmp     rax, r8
0x18008874d  ja      short loc_18008876E
0x18008874f  movsxd  rax, ecx
0x180088752  movsxd  r14, edi
0x180088755  sub     r14, rax
0x180088758  lea     rax, [r14+rdx]
0x18008875c  cmp     rax, r8
0x18008875f  ja      short loc_180088765
0x180088761  mov     cl, 1
0x180088763  jmp     short loc_180088770
0x180088765  xor     cl, cl
0x180088767  xor     edi, edi
0x180088769  mov     r14d, edi
0x18008876c  jmp     short loc_180088772
0x18008876e  xor     cl, cl
0x180088770  xor     edi, edi
0x180088772  mov     eax, [rsi]
0x180088774  test    cl, cl
0x180088776  mov     r9d, 4
0x18008877c  lea     rcx, [rbp+4Fh+var_B8]
0x180088780  cmovz   r14d, edi
0x180088784  mov     edx, 5
0x180088789  add     eax, 3
0x18008878c  mov     r8d, r9d
0x18008878f  mov     [rsp+0F0h+var_D0], eax
0x180088793  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x180088798  cmp     [rbp+4Fh+var_B4], 0
0x18008879c  lea     r8, [rbp+4Fh+var_B8]
0x1800887a0  lea     rdx, [rbp+4Fh+var_C0]
0x1800887a4  mov     [rbp+4Fh+var_B4], 1
0x1800887a8  cmovnz  edi, [rbp+4Fh+var_B8]
0x1800887ac  lea     rcx, [rbp+4Fh+var_B0]
0x1800887b0  mov     [rbp+4Fh+var_C0], edi
0x1800887b3  mov     [rbp+4Fh+var_B8], 4
0x1800887ba  mov     [rbp+4Fh+var_BC], 1
0x1800887be  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x1800887c3  cmp     byte ptr [rax+4], 0
0x1800887c7  jz      short loc_180088826
0x1800887c9  movsxd  rcx, dword ptr [rax]
0x1800887cc  mov     edx, 80000000h
0x1800887d1  shl     rcx, 2
0x1800887d5  mov     r8d, 0FFFFFFFFh
0x1800887db  lea     rax, [rcx+rdx]
0x1800887df  cmp     rax, r8
0x1800887e2  ja      short loc_180088826
0x1800887e4  movsxd  rax, ecx
0x1800887e7  movsxd  rdi, edi
0x1800887ea  sub     rdi, rax
0x1800887ed  lea     rax, [rdi+rdx]
0x1800887f1  cmp     rax, r8
0x1800887f4  ja      short loc_1800887FD
0x1800887f6  mov     al, 1
0x1800887f8  xor     r11d, r11d
0x1800887fb  jmp     short loc_180088805
0x1800887fd  xor     al, al
0x1800887ff  xor     r11d, r11d
0x180088802  mov     edi, r11d
0x180088805  test    al, al
0x180088807  jz      short loc_180088829
0x180088809  cmp     edi, 3
0x18008880c  jbe     short loc_18008882C
0x18008880e  and     edi, 80000003h
0x180088814  jge     short loc_18008881D
0x180088816  dec     edi
0x180088818  or      edi, 0FFFFFFFCh
0x18008881b  inc     edi
0x18008881d  test    edi, edi
0x18008881f  jns     short loc_18008882C
0x180088821  add     edi, 4
0x180088824  jmp     short loc_18008882C
0x180088826  xor     r11d, r11d
0x180088829  mov     edi, r11d
0x18008882c  cmp     dword ptr [r15+8], 0
0x180088831  mov     esi, r11d
0x180088834  jle     loc_18008898B
0x18008883a  nop     word ptr [rax+rax+00h]
0x180088840  vmovups ymm0, ymmword ptr [rbx]
0x180088844  mov     r9, [r13+0]
0x180088848  vmovups [rbp+4Fh+var_A8], ymm0
0x18008884d  mov     r10d, dword ptr [rbp+4Fh+var_A8+18h]
0x180088851  mov     r8, qword ptr [rbp+4Fh+var_A8+10h]
0x180088855  vpextrq rcx, xmm0, 1
0x18008885b  vmovd   edx, xmm0
0x18008885f  inc     edx
0x180088861  lea     rax, [r9+rcx*2]
0x180088865  mov     [rbp+4Fh+var_80], rax
0x180088869  cmp     edx, r10d
0x18008886c  jl      short loc_180088876
0x18008886e  mov     edx, r11d
0x180088871  mov     rcx, r11
0x180088874  jmp     short loc_180088879
0x180088876  add     rcx, r8
0x180088879  inc     edx
0x18008887b  lea     rax, [r9+rcx*2]
0x18008887f  mov     [rbp+4Fh+var_78], rax
0x180088883  cmp     edx, r10d
0x180088886  jl      short loc_180088890
0x180088888  mov     edx, r11d
0x18008888b  mov     rcx, r11
0x18008888e  jmp     short loc_180088893
0x180088890  add     rcx, r8
0x180088893  inc     edx
0x180088895  lea     rax, [r9+rcx*2]
0x180088899  mov     [rbp+4Fh+var_70], rax
0x18008889d  cmp     edx, r10d
0x1800888a0  jl      short loc_1800888AA
0x1800888a2  mov     edx, r11d
0x1800888a5  mov     rcx, r11
0x1800888a8  jmp     short loc_1800888AD
0x1800888aa  add     rcx, r8
0x1800888ad  inc     edx
0x1800888af  lea     rax, [r9+rcx*2]
0x1800888b3  mov     [rbp+4Fh+var_68], rax
0x1800888b7  cmp     edx, r10d
0x1800888ba  jl      short loc_1800888C4
0x1800888bc  mov     edx, r11d
0x1800888bf  mov     rcx, r11
0x1800888c2  jmp     short loc_1800888C7
0x1800888c4  add     rcx, r8
0x1800888c7  inc     edx
0x1800888c9  lea     rax, [r9+rcx*2]
0x1800888cd  mov     [rbp+4Fh+var_60], rax
0x1800888d1  cmp     edx, r10d
0x1800888d4  jl      short loc_1800888DE
0x1800888d6  mov     edx, r11d
0x1800888d9  mov     rcx, r11
0x1800888dc  jmp     short loc_1800888E1
0x1800888de  add     rcx, r8
0x1800888e1  inc     edx
0x1800888e3  lea     rax, [r9+rcx*2]
0x1800888e7  mov     [rbp+4Fh+var_58], rax
0x1800888eb  cmp     edx, r10d
0x1800888ee  jl      short loc_1800888F8
0x1800888f0  mov     edx, r11d
0x1800888f3  mov     rcx, r11
0x1800888f6  jmp     short loc_1800888FB
0x1800888f8  add     rcx, r8
0x1800888fb  inc     edx
0x1800888fd  lea     rax, [r9+rcx*2]
0x180088901  mov     [rbp+4Fh+var_50], rax
0x180088905  cmp     edx, r10d
0x180088908  jl      short loc_18008890F
0x18008890a  mov     rcx, r11
0x18008890d  jmp     short loc_180088912
0x18008890f  add     rcx, r8
0x180088912  lea     rax, [r9+rcx*2]
0x180088916  mov     [rsp+0F0h+var_D0], edi
0x18008891a  mov     [rbp+4Fh+var_48], rax
0x18008891e  lea     r9, [rbp+4Fh+var_80]
0x180088922  mov     r8, r15
0x180088925  mov     rdx, r12
0x180088928  mov     ecx, r14d
0x18008892b  vzeroupper
0x18008892e  call    ??$PutBooleanUnit@VSlowSource@Policy@Binary@@$02@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY07$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::SlowSource,3>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[8],int)
0x180088933  xor     r11d, r11d
0x180088936  movsxd  rax, edi
0x180088939  lea     rdx, ?GlobalCase@SlowSource@Policy@Binary@@2V?$StripedCategory@H$03@Data@@B; Data::StripedCategory<int,4> const Binary::Policy::SlowSource::GlobalCase
0x180088940  mov     ecx, r11d
0x180088943  cmp     [rdx+rax*4], r11d
0x180088947  lea     rdx, [rdx+rax*4]
0x18008894b  jle     short loc_180088973
0x18008894d  mov     r8d, [rbx+18h]
0x180088951  inc     dword ptr [rbx]
0x180088953  cmp     [rbx], r8d
0x180088956  jl      short loc_180088961
0x180088958  mov     [rbx], r11d
0x18008895b  mov     [rbx+8], r11
0x18008895f  jmp     short loc_18008896D
0x180088961  mov     rax, [rbx+8]
0x180088965  add     rax, [rbx+10h]
0x180088969  mov     [rbx+8], rax
0x18008896d  inc     ecx
0x18008896f  cmp     ecx, [rdx]
0x180088971  jl      short loc_180088951
0x180088973  lea     ecx, [rdi+1]
0x180088976  inc     esi
0x180088978  cmp     ecx, 4
0x18008897b  mov     edi, r11d
0x18008897e  cmovl   edi, ecx
0x180088981  cmp     esi, [r15+8]
0x180088985  jl      loc_180088840
0x18008898b  mov     rcx, [rbp+4Fh+var_40]
0x18008898f  xor     rcx, rsp; StackCookie
0x180088992  call    __security_check_cookie
0x180088997  mov     rbx, [rsp+0F0h+arg_0]
0x18008899f  add     rsp, 0C0h
0x1800889a6  pop     r15
0x1800889a8  pop     r14
0x1800889aa  pop     r13
0x1800889ac  pop     r12
0x1800889ae  pop     rdi
0x1800889af  pop     rsi
0x1800889b0  pop     rbp
0x1800889b1  retn
```
