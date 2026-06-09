# Binary::Policy::MarkQuickestList<Binary::Policy::EasyQuantity,2>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)

- ea: `0x18008ec30`
- end: `0x18008eee4`
- name: `??$MarkQuickestList@VEasyQuantity@Policy@Binary@@$01@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180093ab0`

## callees

- `0x180003180`
- `0x1800541e0`
- `0x180054440`
- `0x18008ec30`
- `0x18008fe70`

## pseudocode

```c
char __fastcall Binary::Policy::MarkQuickestList<Binary::Policy::EasyQuantity,2>(
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
  __int64 v30; // rcx
  int v31; // ecx
  int v32; // r8d
  int v33; // ecx
  bool v34; // sf
  int v36; // [rsp+30h] [rbp-51h] BYREF
  char v37; // [rsp+34h] [rbp-4Dh]
  int v38; // [rsp+38h] [rbp-49h] BYREF
  char v39; // [rsp+3Ch] [rbp-45h]
  _BYTE v40[40]; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v41[5]; // [rsp+68h] [rbp-19h] BYREF

  Binary::Definition::GenerateAsyncServer((unsigned int)&v36, 3, 2, 0, a1[1] + 2);
  LODWORD(v9) = 0;
  v39 = 1;
  v10 = v37 == 0;
  v11 = 0;
  v37 = 1;
  if ( !v10 )
    v11 = v36;
  v38 = v11;
  v36 = 2;
  v12 = (int *)Data::FillClearSkill(v40, &v38, &v36);
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
  Binary::Definition::GenerateAsyncServer((unsigned int)&v38, 3, 2, 0, *a1 + 2);
  v10 = v39 == 0;
  v39 = 1;
  if ( !v10 )
    v15 = v38;
  v36 = v15;
  v38 = 2;
  v37 = 1;
  v16 = (int *)Data::FillClearSkill(v40, &v36, &v38);
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
  while ( v19 < a5[2] )
  {
    v20 = *a3;
    v21 = *(_QWORD *)(a2 + 8);
    v22 = *(_DWORD *)(a2 + 24);
    v23 = *(_DWORD *)a2 + 1;
    v24 = *(_QWORD *)(a2 + 16);
    v41[0] = *a3 + 2 * v21;
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
    v41[1] = v20 + 2 * v25;
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
    v41[2] = v20 + 2 * v27;
    if ( v28 < v22 )
    {
      v29 = v24 + v27;
    }
    else
    {
      v28 = 0;
      v29 = 0;
    }
    v41[3] = v20 + 2 * v29;
    if ( v28 + 1 < v22 )
      v30 = v24 + v29;
    else
      v30 = 0;
    v41[4] = v20 + 2 * v30;
    Binary::Policy::PutBooleanUnit<Binary::Policy::EasyQuantity,2>(v9, a4, a5, v41, v18);
    LOBYTE(v16) = v18;
    v31 = 0;
    if ( Binary::Policy::EasyQuantity::GlobalCase[(int)v18] > 0 )
    {
      v32 = *(_DWORD *)(a2 + 24);
      do
      {
        if ( ++*(_DWORD *)a2 < v32 )
        {
          v16 = (int *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 8));
          *(_QWORD *)(a2 + 8) = v16;
        }
        else
        {
          *(_DWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
        }
        ++v31;
      }
      while ( v31 < Binary::Policy::EasyQuantity::GlobalCase[(int)v18] );
    }
    v33 = v18 + 1;
    ++v19;
    v34 = (int)v18 - 1 < 0;
    LODWORD(v18) = 0;
    if ( v34 != __OFSUB__(v33, 2) )
      LODWORD(v18) = v33;
  }
  return (char)v16;
}

```

## disassembly

```asm
0x18008ec30  mov     [rsp-8+arg_0], rbx
0x18008ec35  push    rbp
0x18008ec36  push    rsi
0x18008ec37  push    rdi
0x18008ec38  push    r12
0x18008ec3a  push    r13
0x18008ec3c  push    r14
0x18008ec3e  push    r15
0x18008ec40  lea     rbp, [rsp-1Fh]
0x18008ec45  sub     rsp, 0A0h
0x18008ec4c  mov     rax, cs:__security_cookie
0x18008ec53  xor     rax, rsp
0x18008ec56  mov     [rbp+4Fh+var_40], rax
0x18008ec5a  mov     eax, [rcx+4]
0x18008ec5d  mov     r12, r9
0x18008ec60  mov     r15, [rbp+4Fh+arg_20]
0x18008ec64  xor     r9d, r9d
0x18008ec67  mov     r13, r8
0x18008ec6a  mov     rbx, rdx
0x18008ec6d  mov     rsi, rcx
0x18008ec70  add     eax, 2
0x18008ec73  lea     rcx, [rbp+4Fh+var_A0]
0x18008ec77  mov     [rsp+0D0h+var_B0], eax
0x18008ec7b  lea     edx, [r9+3]
0x18008ec7f  lea     r8d, [r9+2]
0x18008ec83  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18008ec88  xor     r14d, r14d
0x18008ec8b  mov     [rbp+4Fh+var_94], 1
0x18008ec8f  cmp     [rbp+4Fh+var_9C], r14b
0x18008ec93  lea     r8, [rbp+4Fh+var_A0]
0x18008ec97  mov     edi, r14d
0x18008ec9a  mov     [rbp+4Fh+var_9C], 1
0x18008ec9e  cmovnz  edi, [rbp+4Fh+var_A0]
0x18008eca2  lea     rdx, [rbp+4Fh+var_98]
0x18008eca6  lea     rcx, [rbp+4Fh+var_90]
0x18008ecaa  mov     [rbp+4Fh+var_98], edi
0x18008ecad  mov     [rbp+4Fh+var_A0], 2
0x18008ecb4  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008ecb9  mov     edx, 80000000h
0x18008ecbe  mov     r8d, 0FFFFFFFFh
0x18008ecc4  movzx   ecx, byte ptr [rax+4]
0x18008ecc8  test    cl, cl
0x18008ecca  jz      short loc_18008ECFC
0x18008eccc  movsxd  rcx, dword ptr [rax]
0x18008eccf  add     rcx, rcx
0x18008ecd2  lea     rax, [rcx+rdx]
0x18008ecd6  cmp     rax, r8
0x18008ecd9  ja      short loc_18008ECFA
0x18008ecdb  movsxd  rax, ecx
0x18008ecde  movsxd  r14, edi
0x18008ece1  sub     r14, rax
0x18008ece4  lea     rax, [r14+rdx]
0x18008ece8  cmp     rax, r8
0x18008eceb  ja      short loc_18008ECF1
0x18008eced  mov     cl, 1
0x18008ecef  jmp     short loc_18008ECFC
0x18008ecf1  xor     cl, cl
0x18008ecf3  xor     edi, edi
0x18008ecf5  mov     r14d, edi
0x18008ecf8  jmp     short loc_18008ECFE
0x18008ecfa  xor     cl, cl
0x18008ecfc  xor     edi, edi
0x18008ecfe  mov     eax, [rsi]
0x18008ed00  test    cl, cl
0x18008ed02  lea     rcx, [rbp+4Fh+var_98]
0x18008ed06  cmovz   r14d, edi
0x18008ed0a  xor     r9d, r9d
0x18008ed0d  add     eax, 2
0x18008ed10  mov     [rsp+0D0h+var_B0], eax
0x18008ed14  lea     edx, [r9+3]
0x18008ed18  lea     r8d, [r9+2]
0x18008ed1c  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18008ed21  cmp     [rbp+4Fh+var_94], 0
0x18008ed25  lea     r8, [rbp+4Fh+var_98]
0x18008ed29  lea     rdx, [rbp+4Fh+var_A0]
0x18008ed2d  mov     [rbp+4Fh+var_94], 1
0x18008ed31  cmovnz  edi, [rbp+4Fh+var_98]
0x18008ed35  lea     rcx, [rbp+4Fh+var_90]
0x18008ed39  mov     [rbp+4Fh+var_A0], edi
0x18008ed3c  mov     [rbp+4Fh+var_98], 2
0x18008ed43  mov     [rbp+4Fh+var_9C], 1
0x18008ed47  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x18008ed4c  cmp     byte ptr [rax+4], 0
0x18008ed50  jz      short loc_18008EDAE
0x18008ed52  movsxd  rcx, dword ptr [rax]
0x18008ed55  mov     edx, 80000000h
0x18008ed5a  add     rcx, rcx
0x18008ed5d  mov     r8d, 0FFFFFFFFh
0x18008ed63  lea     rax, [rcx+rdx]
0x18008ed67  cmp     rax, r8
0x18008ed6a  ja      short loc_18008EDAE
0x18008ed6c  movsxd  rax, ecx
0x18008ed6f  movsxd  rdi, edi
0x18008ed72  sub     rdi, rax
0x18008ed75  lea     rax, [rdi+rdx]
0x18008ed79  cmp     rax, r8
0x18008ed7c  ja      short loc_18008ED85
0x18008ed7e  mov     al, 1
0x18008ed80  xor     r11d, r11d
0x18008ed83  jmp     short loc_18008ED8D
0x18008ed85  xor     al, al
0x18008ed87  xor     r11d, r11d
0x18008ed8a  mov     edi, r11d
0x18008ed8d  test    al, al
0x18008ed8f  jz      short loc_18008EDB1
0x18008ed91  cmp     edi, 1
0x18008ed94  jbe     short loc_18008EDB4
0x18008ed96  and     edi, 80000001h
0x18008ed9c  jge     short loc_18008EDA5
0x18008ed9e  dec     edi
0x18008eda0  or      edi, 0FFFFFFFEh
0x18008eda3  inc     edi
0x18008eda5  test    edi, edi
0x18008eda7  jns     short loc_18008EDB4
0x18008eda9  add     edi, 2
0x18008edac  jmp     short loc_18008EDB4
0x18008edae  xor     r11d, r11d
0x18008edb1  mov     edi, r11d
0x18008edb4  cmp     dword ptr [r15+8], 0
0x18008edb9  mov     esi, r11d
0x18008edbc  jle     loc_18008EEBD
0x18008edc2  nop     dword ptr [rax+00h]
0x18008edc6  nop     word ptr [rax+rax+00000000h]
0x18008edd0  mov     r9, [r13+0]
0x18008edd4  mov     rcx, [rbx+8]
0x18008edd8  mov     edx, [rbx]
0x18008edda  mov     r10d, [rbx+18h]
0x18008edde  inc     edx
0x18008ede0  mov     r8, [rbx+10h]
0x18008ede4  lea     rax, [r9+rcx*2]
0x18008ede8  mov     [rbp+4Fh+var_68], rax
0x18008edec  cmp     edx, r10d
0x18008edef  jl      short loc_18008EDF9
0x18008edf1  mov     edx, r11d
0x18008edf4  mov     rcx, r11
0x18008edf7  jmp     short loc_18008EDFC
0x18008edf9  add     rcx, r8
0x18008edfc  inc     edx
0x18008edfe  lea     rax, [r9+rcx*2]
0x18008ee02  mov     [rbp+4Fh+var_60], rax
0x18008ee06  cmp     edx, r10d
0x18008ee09  jl      short loc_18008EE13
0x18008ee0b  mov     edx, r11d
0x18008ee0e  mov     rcx, r11
0x18008ee11  jmp     short loc_18008EE16
0x18008ee13  add     rcx, r8
0x18008ee16  inc     edx
0x18008ee18  lea     rax, [r9+rcx*2]
0x18008ee1c  mov     [rbp+4Fh+var_58], rax
0x18008ee20  cmp     edx, r10d
0x18008ee23  jl      short loc_18008EE2D
0x18008ee25  mov     edx, r11d
0x18008ee28  mov     rcx, r11
0x18008ee2b  jmp     short loc_18008EE30
0x18008ee2d  add     rcx, r8
0x18008ee30  inc     edx
0x18008ee32  lea     rax, [r9+rcx*2]
0x18008ee36  mov     [rbp+4Fh+var_50], rax
0x18008ee3a  cmp     edx, r10d
0x18008ee3d  jl      short loc_18008EE44
0x18008ee3f  mov     rcx, r11
0x18008ee42  jmp     short loc_18008EE47
0x18008ee44  add     rcx, r8
0x18008ee47  lea     rax, [r9+rcx*2]
0x18008ee4b  mov     [rsp+0D0h+var_B0], edi
0x18008ee4f  lea     r9, [rbp+4Fh+var_68]
0x18008ee53  mov     [rbp+4Fh+var_48], rax
0x18008ee57  mov     ecx, r14d
0x18008ee5a  mov     r8, r15
0x18008ee5d  mov     rdx, r12
0x18008ee60  call    ??$PutBooleanUnit@VEasyQuantity@Policy@Binary@@$01@Policy@Binary@@YAXHAEAVCompleteOperation@01@AEBV?$ShortTermResolution@H@Data@@AEAY04$$CBV?$HighDescription@PEAG@4@H@Z; Binary::Policy::PutBooleanUnit<Binary::Policy::EasyQuantity,2>(int,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &,Data::HighDescription<ushort *> const (&)[5],int)
0x18008ee65  xor     r11d, r11d
0x18008ee68  movsxd  rax, edi
0x18008ee6b  lea     rdx, ?GlobalCase@EasyQuantity@Policy@Binary@@2V?$StripedCategory@H$01@Data@@B; Data::StripedCategory<int,2> const Binary::Policy::EasyQuantity::GlobalCase
0x18008ee72  mov     ecx, r11d
0x18008ee75  cmp     [rdx+rax*4], r11d
0x18008ee79  lea     rdx, [rdx+rax*4]
0x18008ee7d  jle     short loc_18008EEA5
0x18008ee7f  mov     r8d, [rbx+18h]
0x18008ee83  inc     dword ptr [rbx]
0x18008ee85  cmp     [rbx], r8d
0x18008ee88  jl      short loc_18008EE93
0x18008ee8a  mov     [rbx], r11d
0x18008ee8d  mov     [rbx+8], r11
0x18008ee91  jmp     short loc_18008EE9F
0x18008ee93  mov     rax, [rbx+8]
0x18008ee97  add     rax, [rbx+10h]
0x18008ee9b  mov     [rbx+8], rax
0x18008ee9f  inc     ecx
0x18008eea1  cmp     ecx, [rdx]
0x18008eea3  jl      short loc_18008EE83
0x18008eea5  lea     ecx, [rdi+1]
0x18008eea8  inc     esi
0x18008eeaa  cmp     ecx, 2
0x18008eead  mov     edi, r11d
0x18008eeb0  cmovl   edi, ecx
0x18008eeb3  cmp     esi, [r15+8]
0x18008eeb7  jl      loc_18008EDD0
0x18008eebd  mov     rcx, [rbp+4Fh+var_40]
0x18008eec1  xor     rcx, rsp; StackCookie
0x18008eec4  call    __security_check_cookie
0x18008eec9  mov     rbx, [rsp+0D0h+arg_0]
0x18008eed1  add     rsp, 0A0h
0x18008eed8  pop     r15
0x18008eeda  pop     r14
0x18008eedc  pop     r13
0x18008eede  pop     r12
0x18008eee0  pop     rdi
0x18008eee1  pop     rsi
0x18008eee2  pop     rbp
0x18008eee3  retn
```
