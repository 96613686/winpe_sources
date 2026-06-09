# SDK::NullDNS::ComputeCurvedVersion(SDK::NullDNS &,IWICBitmap &,Setting::ActiveCategory &)

- ea: `0x18003cfe0`
- end: `0x18003d443`
- name: `?ComputeCurvedVersion@NullDNS@SDK@@SAJAEAV12@AEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z`
- size: `1123`
- prototype: `static int(struct SDK::NullDNS *, struct IWICBitmap *, struct Setting::ActiveCategory *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e4b0`
- `0x18003cfe0`
- `0x18003f600`
- `0x1800bf3b0`

## pseudocode

```c
__int64 __fastcall SDK::NullDNS::ComputeCurvedVersion(
        struct SDK::NullDNS *a1,
        struct IWICBitmap *a2,
        struct Setting::ActiveCategory *a3)
{
  unsigned int v3; // r11d
  int v4; // r14d
  char v5; // bl
  int v8; // eax
  int v9; // ebp
  int v10; // edi
  char v11; // si
  __int64 (__fastcall *v12)(struct IWICBitmap *, struct Setting::ActiveCategory *); // r9
  char *v13; // r10
  __int64 v14; // r8
  bool v15; // sf
  unsigned int v16; // eax
  _BYTE *v17; // r9
  void (__fastcall *MixedProvider)(int (*)(struct SDK::NullDNS *, struct IWICBitmap *, struct Setting::ActiveCategory *), unsigned __int64, __int64); // rax
  _BYTE *retaddr; // [rsp+58h] [rbp+0h]

  v3 = IntegralRelation::OddMap;
  v4 = 0;
  v5 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 2;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  do
  {
    if ( v8 > 15893826 )
    {
      if ( v14 <= 0 )
      {
        if ( v14 < 0 && (__int64)v13 < (__int64)(0x8000000000000000uLL - v14) )
          goto LABEL_35;
        v8 = 5297942;
      }
      else
      {
        if ( (__int64)v13 > 0x7FFFFFFFFFFFFFFFLL - v14 )
          goto LABEL_35;
        v8 = 5297942;
      }
    }
    else
    {
      if ( v8 == 15893826 )
      {
        --v10;
        if ( *(_BYTE *)v12 == (unsigned __int8)((IntegralRelation::OddMap ^ 0x8F508F2B) / 0x924DAA) )
        {
          v11 = 1;
          v5 = 1;
        }
        v15 = v10 < 0;
        goto LABEL_18;
      }
      if ( v8 <= 7946913 )
      {
        if ( v8 == 7946913 )
        {
          if ( *(_BYTE *)v12 == (unsigned __int8)((IntegralRelation::OddMap ^ 0xE42C222B) / 0x230FB8) )
          {
            v14 = *(int *)((char *)v12 + 1);
            v9 = 5;
            v8 = 2648971;
          }
          else
          {
            v8 = 10595884;
          }
        }
        else if ( v8 )
        {
          if ( v8 == 2648971 )
          {
            v8 = 18542797;
            v13 = (char *)SDK::NullDNS::TargetSlowImprovement + v9;
          }
          else
          {
            v12 = (__int64 (__fastcall *)(struct IWICBitmap *, struct Setting::ActiveCategory *))&v13[v14];
            v8 = 13244855;
          }
        }
        else
        {
          v12 = SDK::NullDNS::TargetSlowImprovement;
          v8 = 15893826;
        }
        continue;
      }
      if ( v8 != 10595884 )
      {
        if ( *(_BYTE *)v12 == (unsigned __int8)((IntegralRelation::OddMap ^ 0xF4FB4073) / 0x1320D8) )
          v11 = 1;
        v15 = --v10 < 0;
LABEL_18:
        if ( v15 )
          v5 = 1;
        v8 = 7946913;
        continue;
      }
      if ( *(_BYTE *)v12 != (unsigned __int8)((IntegralRelation::OddMap ^ 0x7D88275D) / 0x924DAA) )
        break;
      v14 = *((char *)v12 + 1);
      v9 = 2;
      v8 = 2648971;
    }
  }
  while ( !v5 );
  if ( v11 )
    v3 = ++IntegralRelation::OddMap;
LABEL_35:
  v16 = 4774617;
  v17 = 0;
LABEL_36:
  LOBYTE(v14) = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( v16 > 0x48DAEA )
        {
          if ( v16 == 4774688 )
          {
            if ( *v17 == (unsigned __int8)((v3 ^ v4) / 0x884A92) )
            {
              v16 = 3080546;
              goto LABEL_36;
            }
            v16 = 3080600;
          }
          else if ( v16 == 7855146 )
          {
            v17 = retaddr;
            v16 = 4774634;
          }
          else
          {
            v16 = 4774688;
            v4 = -1755447285;
          }
        }
        if ( v16 != 4774634 )
          break;
        v14 = (unsigned __int8)v14;
        v16 = 3080546;
        if ( (v3 ^ 0xFB58B3FE) == 0x9DDFAD )
          v16 = 10346413;
        else
          v14 = 1;
      }
      if ( v16 != 3080546 )
        break;
      v16 = 3080600;
      if ( (_BYTE)v14 != 1 )
        v16 = 7855146;
    }
    if ( v16 == 3080600 )
      break;
    LOBYTE(v14) = 0;
    v16 = 3080546;
  }
  if ( (_BYTE)v14 )
    IntegralRelation::OddMap = v3 + 1;
  MixedProvider = (void (__fastcall *)(int (*)(struct SDK::NullDNS *, struct IWICBitmap *, struct Setting::ActiveCategory *), unsigned __int64, __int64))GenerateMixedProvider(0xBF7F5F9FC0E07050uLL, 1371840586, v14);
  MixedProvider(
    SDK::NullDNS::ComputeCurvedVersion,
    (unsigned __int64)SDK::NullDNS::ComputeCurvedVersion ^ 0x16A3F3,
    435171);
  return SDK::NullDNS::TargetSlowImprovement(a2, a3);
}

```

## disassembly

```asm
0x18003cfe0  mov     [rsp+arg_0], rbx
0x18003cfe5  push    rbp
0x18003cfe6  push    rsi
0x18003cfe7  push    rdi
0x18003cfe8  push    r12
0x18003cfea  push    r13
0x18003cfec  push    r14
0x18003cfee  push    r15
0x18003cff0  sub     rsp, 20h
0x18003cff4  mov     r11d, cs:?OddMap@IntegralRelation@@2IA; uint IntegralRelation::OddMap
0x18003cffb  xor     r14d, r14d
0x18003cffe  xor     bl, bl
0x18003d000  mov     r12, r8
0x18003d003  mov     r15, rdx
0x18003d006  mov     eax, r14d
0x18003d009  mov     ebp, r14d
0x18003d00c  lea     rdx, ?TargetSlowImprovement@NullDNS@SDK@@CAJAEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::TargetSlowImprovement(IWICBitmap &,Setting::ActiveCategory &)
0x18003d013  lea     edi, [r14+2]
0x18003d017  xor     sil, sil
0x18003d01a  lea     r13d, [r14+1]
0x18003d01e  mov     r9d, r14d
0x18003d021  mov     r10d, r14d
0x18003d024  mov     r8d, r14d
0x18003d027  mov     ecx, 50D716h
0x18003d02c  nop     dword ptr [rax+00h]
0x18003d030  cmp     eax, 0F28542h
0x18003d035  jg      loc_18003D17E
0x18003d03b  jz      loc_18003D159
0x18003d041  cmp     eax, 7942A1h
0x18003d046  jg      loc_18003D0CD
0x18003d04c  jz      short loc_18003D08C
0x18003d04e  test    eax, eax
0x18003d050  jz      short loc_18003D07F
0x18003d052  cmp     eax, 286B8Bh
0x18003d057  jz      short loc_18003D06F
0x18003d059  cmp     eax, ecx
0x18003d05b  jnz     loc_18003D2FD
0x18003d061  lea     r9, [r8+r10]
0x18003d065  mov     eax, 0CA19B7h
0x18003d06a  jmp     loc_18003D2FD
0x18003d06f  movsxd  r10, ebp
0x18003d072  mov     eax, 11AF0CDh
0x18003d077  add     r10, rdx
0x18003d07a  jmp     loc_18003D2FD
0x18003d07f  mov     r9, rdx
0x18003d082  mov     eax, 0F28542h
0x18003d087  jmp     loc_18003D2FD
0x18003d08c  mov     ecx, r11d
0x18003d08f  mov     eax, 1D34B645h
0x18003d094  xor     ecx, 0E42C222Bh
0x18003d09a  mul     ecx
0x18003d09c  mov     ecx, 50D716h
0x18003d0a1  shr     edx, 12h
0x18003d0a4  cmp     [r9], dl
0x18003d0a7  lea     rdx, ?TargetSlowImprovement@NullDNS@SDK@@CAJAEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::TargetSlowImprovement(IWICBitmap &,Setting::ActiveCategory &)
0x18003d0ae  jnz     short loc_18003D0C3
0x18003d0b0  movsxd  r8, dword ptr [r9+1]
0x18003d0b4  mov     ebp, 5
0x18003d0b9  mov     eax, 286B8Bh
0x18003d0be  jmp     loc_18003D2FD
0x18003d0c3  mov     eax, 0A1AE2Ch
0x18003d0c8  jmp     loc_18003D2FD
0x18003d0cd  cmp     eax, 0A1AE2Ch
0x18003d0d2  jz      short loc_18003D11D
0x18003d0d4  cmp     eax, 0CA19B7h
0x18003d0d9  jnz     loc_18003D2FD
0x18003d0df  mov     ecx, r11d
0x18003d0e2  movzx   esi, sil
0x18003d0e6  xor     ecx, 0F4FB4073h
0x18003d0ec  mov     eax, 0D6220E65h
0x18003d0f1  mul     ecx
0x18003d0f3  shr     edx, 14h
0x18003d0f6  cmp     [r9], dl
0x18003d0f9  cmovz   esi, r13d
0x18003d0fd  sub     edi, 1
0x18003d100  movzx   ebx, bl
0x18003d103  lea     rdx, ?TargetSlowImprovement@NullDNS@SDK@@CAJAEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::TargetSlowImprovement(IWICBitmap &,Setting::ActiveCategory &)
0x18003d10a  cmovs   ebx, r13d
0x18003d10e  mov     eax, 7942A1h
0x18003d113  mov     ecx, 50D716h
0x18003d118  jmp     loc_18003D2FD
0x18003d11d  mov     ecx, r11d
0x18003d120  mov     eax, 0DFF913E7h
0x18003d125  xor     ecx, 7D88275Dh
0x18003d12b  mul     ecx
0x18003d12d  shr     edx, 17h
0x18003d130  cmp     [r9], dl
0x18003d133  jnz     loc_18003D305
0x18003d139  movsx   r8, byte ptr [r9+1]
0x18003d13e  lea     rdx, ?TargetSlowImprovement@NullDNS@SDK@@CAJAEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::TargetSlowImprovement(IWICBitmap &,Setting::ActiveCategory &)
0x18003d145  mov     ebp, 2
0x18003d14a  mov     eax, 286B8Bh
0x18003d14f  mov     ecx, 50D716h
0x18003d154  jmp     loc_18003D2FD
0x18003d159  mov     ecx, r11d
0x18003d15c  mov     eax, 0DFF913E7h
0x18003d161  xor     ecx, 8F508F2Bh
0x18003d167  dec     edi
0x18003d169  mul     ecx
0x18003d16b  shr     edx, 17h
0x18003d16e  cmp     [r9], dl
0x18003d171  jnz     short loc_18003D17A
0x18003d173  mov     sil, 1
0x18003d176  movzx   ebx, sil
0x18003d17a  test    edi, edi
0x18003d17c  jmp     short loc_18003D100
0x18003d17e  cmp     eax, 235E19Ah
0x18003d183  jg      loc_18003D29C
0x18003d189  jz      loc_18003D249
0x18003d18f  cmp     eax, 11AF0CDh
0x18003d194  jz      short loc_18003D1F9
0x18003d196  cmp     eax, 1BC9EF9h
0x18003d19b  jz      short loc_18003D1C1
0x18003d19d  cmp     eax, 20D760Fh
0x18003d1a2  jnz     loc_18003D2FD
0x18003d1a8  movzx   eax, byte ptr [r9+3]
0x18003d1ad  and     al, 0FCh
0x18003d1af  cmp     al, 14h
0x18003d1b1  jnz     loc_18003D305
0x18003d1b7  mov     eax, 235E19Ah
0x18003d1bc  jmp     loc_18003D2FD
0x18003d1c1  movzx   eax, byte ptr [r9]
0x18003d1c5  dec     edi
0x18003d1c7  or      al, 0E0h
0x18003d1c9  cmp     al, 0E0h
0x18003d1cb  jnz     short loc_18003D1E6
0x18003d1cd  movzx   eax, byte ptr [r9+2]
0x18003d1d2  or      al, 20h
0x18003d1d4  cmp     al, 40h ; '@'
0x18003d1d6  jnb     short loc_18003D1E6
0x18003d1d8  cmp     byte ptr [r9+3], 0D4h
0x18003d1dd  jnz     short loc_18003D1E6
0x18003d1df  mov     sil, 1
0x18003d1e2  movzx   ebx, sil
0x18003d1e6  test    edi, edi
0x18003d1e8  movzx   ebx, bl
0x18003d1eb  mov     eax, 20D760Fh
0x18003d1f0  cmovs   ebx, r13d
0x18003d1f4  jmp     loc_18003D2FD
0x18003d1f9  test    r8, r8
0x18003d1fc  jle     short loc_18003D21B
0x18003d1fe  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003d208  sub     rax, r8
0x18003d20b  cmp     r10, rax
0x18003d20e  jg      loc_18003D314
0x18003d214  mov     eax, ecx
0x18003d216  jmp     loc_18003D2FD
0x18003d21b  mov     rax, r8
0x18003d21e  neg     rax
0x18003d221  test    r8, r8
0x18003d224  jns     short loc_18003D242
0x18003d226  mov     r13, 8000000000000000h
0x18003d230  add     rax, r13
0x18003d233  mov     r13d, 1
0x18003d239  cmp     r10, rax
0x18003d23c  jl      loc_18003D314
0x18003d242  mov     eax, ecx
0x18003d244  jmp     loc_18003D2FD
0x18003d249  movzx   eax, byte ptr [r9+3]
0x18003d24e  and     al, 3
0x18003d250  movzx   r8d, al
0x18003d254  test    r8b, 2
0x18003d258  lea     eax, [r8-4]
0x18003d25c  movzx   ecx, al
0x18003d25f  movzx   eax, byte ptr [r9+2]
0x18003d264  cmovz   ecx, r8d
0x18003d268  movsx   edx, cl
0x18003d26b  mov     ecx, 50D716h
0x18003d270  shl     edx, 8
0x18003d273  add     edx, eax
0x18003d275  movzx   eax, byte ptr [r9+1]
0x18003d27a  shl     edx, 8
0x18003d27d  add     edx, eax
0x18003d27f  movzx   eax, byte ptr [r9]
0x18003d283  shl     edx, 8
0x18003d286  add     edx, eax
0x18003d288  mov     eax, 25E4D25h
0x18003d28d  movsxd  r8, edx
0x18003d290  lea     rdx, ?TargetSlowImprovement@NullDNS@SDK@@CAJAEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::TargetSlowImprovement(IWICBitmap &,Setting::ActiveCategory &)
0x18003d297  cmovz   eax, ecx
0x18003d29a  jmp     short loc_18003D2FD
0x18003d29c  cmp     eax, 25E4D25h
0x18003d2a1  jz      short loc_18003D2B5
0x18003d2a3  cmp     eax, 350D267h
0x18003d2a8  jnz     short loc_18003D2FD
0x18003d2aa  lea     r9, [r10+r8*4]
0x18003d2ae  mov     eax, 1BC9EF9h
0x18003d2b3  jmp     short loc_18003D2FD
0x18003d2b5  mov     rax, r8
0x18003d2b8  neg     rax
0x18003d2bb  shl     rax, 2
0x18003d2bf  test    r8, r8
0x18003d2c2  jle     short loc_18003D2DE
0x18003d2c4  mov     r13, 7FFFFFFFFFFFFFFFh
0x18003d2ce  add     rax, r13
0x18003d2d1  mov     r13d, 1
0x18003d2d7  cmp     r10, rax
0x18003d2da  jg      short loc_18003D314
0x18003d2dc  jmp     short loc_18003D2F8
0x18003d2de  jns     short loc_18003D2F8
0x18003d2e0  mov     r13, 8000000000000000h
0x18003d2ea  add     rax, r13
0x18003d2ed  mov     r13d, 1
0x18003d2f3  cmp     r10, rax
0x18003d2f6  jl      short loc_18003D314
0x18003d2f8  mov     eax, 350D267h
0x18003d2fd  test    bl, bl
0x18003d2ff  jz      loc_18003D030
0x18003d305  test    sil, sil
0x18003d308  jz      short loc_18003D314
0x18003d30a  inc     r11d
0x18003d30d  mov     cs:?OddMap@IntegralRelation@@2IA, r11d; uint IntegralRelation::OddMap
0x18003d314  mov     eax, 48DAD9h
0x18003d319  mov     r9, r14
0x18003d31c  mov     ebx, 77DC2Ah
0x18003d321  mov     r10d, 9DDFADh
0x18003d327  mov     r8b, 1
0x18003d32a  nop     word ptr [rax+rax+00h]
0x18003d330  cmp     eax, 48DAEAh
0x18003d335  ja      short loc_18003D38B
0x18003d337  jz      short loc_18003D36C
0x18003d339  mov     ecx, eax
0x18003d33b  sub     ecx, 2F0162h
0x18003d341  jz      short loc_18003D35E
0x18003d343  sub     ecx, 36h ; '6'
0x18003d346  jz      loc_18003D3E0
0x18003d34c  cmp     ecx, 19D941h
0x18003d352  jnz     short loc_18003D330
0x18003d354  xor     r8b, r8b
0x18003d357  mov     eax, 2F0162h
0x18003d35c  jmp     short loc_18003D330
0x18003d35e  cmp     r8b, 1
0x18003d362  mov     eax, 2F0198h
0x18003d367  cmovnz  eax, ebx
0x18003d36a  jmp     short loc_18003D330
0x18003d36c  mov     ecx, r11d
0x18003d36f  movzx   r8d, r8b
0x18003d373  xor     ecx, 0FB58B3FEh
0x18003d379  mov     eax, 2F0162h
0x18003d37e  cmp     ecx, r10d
0x18003d381  cmovnz  r8d, r13d
0x18003d385  cmovz   eax, r10d
0x18003d389  jmp     short loc_18003D330
0x18003d38b  cmp     eax, 48DB20h
0x18003d390  jz      short loc_18003D3B7
0x18003d392  cmp     eax, ebx
0x18003d394  jz      short loc_18003D3A8
0x18003d396  cmp     eax, r10d
0x18003d399  jnz     short loc_18003D330
0x18003d39b  mov     eax, 48DB20h
0x18003d3a0  mov     r14d, 975E000Bh
0x18003d3a6  jmp     short loc_18003D330
0x18003d3a8  mov     r9, [rsp+58h]
0x18003d3ad  mov     eax, 48DAEAh
0x18003d3b2  jmp     loc_18003D330
0x18003d3b7  mov     ecx, r14d
0x18003d3ba  mov     eax, 0F06D1CE1h
0x18003d3bf  xor     ecx, r11d
0x18003d3c2  mul     ecx
0x18003d3c4  shr     edx, 17h
0x18003d3c7  cmp     [r9], dl
0x18003d3ca  jnz     short loc_18003D3D6
0x18003d3cc  mov     eax, 2F0162h
0x18003d3d1  jmp     loc_18003D327
0x18003d3d6  mov     eax, 2F0198h
0x18003d3db  jmp     loc_18003D330
0x18003d3e0  test    r8b, r8b
0x18003d3e3  jz      short loc_18003D3EF
0x18003d3e5  inc     r11d
0x18003d3e8  mov     cs:?OddMap@IntegralRelation@@2IA, r11d; uint IntegralRelation::OddMap
0x18003d3ef  mov     edx, 51C4A04Ah
0x18003d3f4  mov     rcx, 0BF7F5F9FC0E07050h
0x18003d3fe  call    GenerateMixedProvider
0x18003d403  lea     rdx, ?ComputeCurvedVersion@NullDNS@SDK@@SAJAEAV12@AEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::ComputeCurvedVersion(SDK::NullDNS &,IWICBitmap &,Setting::ActiveCategory &)
0x18003d40a  mov     r8d, 6A3E3h
0x18003d410  xor     rdx, 16A3F3h
0x18003d417  lea     rcx, ?ComputeCurvedVersion@NullDNS@SDK@@SAJAEAV12@AEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::ComputeCurvedVersion(SDK::NullDNS &,IWICBitmap &,Setting::ActiveCategory &)
0x18003d41e  call    cs:__guard_dispatch_icall_fptr
0x18003d424  mov     rdx, r12; struct Setting::ActiveCategory *
0x18003d427  mov     rcx, r15; struct IWICBitmap *
0x18003d42a  mov     rbx, [rsp+58h+arg_0]
0x18003d42f  add     rsp, 20h
0x18003d433  pop     r15
0x18003d435  pop     r14
0x18003d437  pop     r13
0x18003d439  pop     r12
0x18003d43b  pop     rdi
0x18003d43c  pop     rsi
0x18003d43d  pop     rbp
0x18003d43e  jmp     ?TargetSlowImprovement@NullDNS@SDK@@CAJAEAUIWICBitmap@@AEAVActiveCategory@Setting@@@Z; SDK::NullDNS::TargetSlowImprovement(IWICBitmap &,Setting::ActiveCategory &)
```
