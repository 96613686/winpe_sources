# ChartPlayer::Detail::ProduceJsonInteractivityImpl(ChartPlayer::IInteractivity &,ChartPlayer::ResultInfo *)

- ea: `0x180004eb0`
- end: `0x1800053e4`
- name: `?ProduceJsonInteractivityImpl@Detail@ChartPlayer@@YAPEAUIString@2@AEAUIInteractivity@2@PEAUResultInfo@2@@Z`
- size: `1332`
- prototype: `struct ChartPlayer::IString *__fastcall(ChartPlayer::Detail *__hidden this, struct ChartPlayer::IInteractivity *, struct ChartPlayer::ResultInfo *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18012f23c`

## callees

- `0x180001224`
- `0x18000149c`
- `0x180002910`
- `0x180004eb0`
- `0x180005c90`
- `0x1800066d4`
- `0x18000675c`
- `0x1800067c4`
- `0x180008354`
- `0x180009070`
- `0x180009174`
- `0x180009200`
- `0x1801292bc`
- `0x18016c7b0`
- `0x18016cccc`
- `0x18016ea3e`
- `0x18016eaf0`

## import_xrefs

- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180004f81`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180004f81`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180004f76`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180004f76`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000521f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000521f`

## string_xrefs

- `0x18000535c`: `ChartPlayer client didn't return a Deleter.`
- `0x180005387`: `ChartPlayer client didn't return a Deleter.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
struct ChartPlayer::IString *__fastcall ChartPlayer::Detail::ProduceJsonInteractivityImpl(
        ChartPlayer::Detail *this,
        struct ChartPlayer::IInteractivity *a2,
        struct ChartPlayer::ResultInfo *a3)
{
  _QWORD *v5; // rax
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v12; // rax
  _QWORD **v13; // rax
  _QWORD *v14; // r14
  void *v15; // rbx
  unsigned int v16; // ebx
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  __int128 v18; // [rsp+20h] [rbp-158h] BYREF
  int v19; // [rsp+30h] [rbp-148h]
  struct ChartPlayer::IInteractivity *v20; // [rsp+38h] [rbp-140h]
  void *Block[2]; // [rsp+40h] [rbp-138h] BYREF
  void **v22; // [rsp+50h] [rbp-128h] BYREF
  void (*v23)(void); // [rsp+58h] [rbp-120h]
  __int64 v24; // [rsp+60h] [rbp-118h]
  ChartPlayer::Detail **v25; // [rsp+68h] [rbp-110h]
  _BYTE v26[8]; // [rsp+70h] [rbp-108h] BYREF
  __int64 v27; // [rsp+78h] [rbp-100h]
  _BYTE v28[32]; // [rsp+80h] [rbp-F8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+A0h] [rbp-D8h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-B8h] BYREF
  _BYTE v31[32]; // [rsp+E0h] [rbp-98h] BYREF
  ChartPlayer::Detail *v32; // [rsp+100h] [rbp-78h] BYREF
  __int64 v33; // [rsp+108h] [rbp-70h]
  int v34; // [rsp+110h] [rbp-68h]
  __int16 v35; // [rsp+114h] [rbp-64h]
  char v36; // [rsp+116h] [rbp-62h]
  ChartPlayer::Detail *v37; // [rsp+118h] [rbp-60h]
  __int64 v38; // [rsp+120h] [rbp-58h]
  __int128 v39; // [rsp+128h] [rbp-50h] BYREF
  __m128i si128; // [rsp+138h] [rbp-40h]
  _BYTE v41[16]; // [rsp+148h] [rbp-30h] BYREF
  __int64 v42; // [rsp+158h] [rbp-20h] BYREF

  v20 = a2;
  v19 = 0;
  v32 = this;
  v33 = (**(__int64 (__fastcall ***)(ChartPlayer::Detail *, struct ChartPlayer::IInteractivity *, struct ChartPlayer::ResultInfo *))this)(
          this,
          a2,
          a3);
  v34 = 0;
  v35 = 0;
  v36 = 0;
  if ( !v33 )
  {
    sub_180001224((__int64)pExceptionObject, 2, (__int64)"ChartPlayer client didn't return a Deleter.");
    throw (ChartPlayer::ChartPlayerError *)pExceptionObject;
  }
  v37 = this;
  v38 = 0;
  v38 = *(_QWORD *)sub_180009200(Block);
  sub_18000149C(&v32);
  if ( !v33 )
  {
    sub_180001224((__int64)v30, 2, (__int64)"ChartPlayer client didn't return a Deleter.");
    throw (ChartPlayer::ChartPlayerError *)v30;
  }
  v18 = 0;
  v5 = malloc(0x50u);
  if ( !v5 )
    std::_Xbad_alloc();
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *(_QWORD *)&v18 = v5;
  v6 = (*(__int64 (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v37 + 64LL))(v37);
  sub_18000149C(&v32);
  v22 = &ChartPlayer::InteractiveElement::`vftable';
  v23 = (void (*)(void))v33;
  v24 = v6;
  v25 = &v32;
  sub_18000149C(&v32);
  if ( !v24 )
  {
    sub_180001224((__int64)v31, 2, (__int64)"ChartPlayer client didn't return an IInteractiveElement.");
    throw (ChartPlayer::ChartPlayerError *)v31;
  }
  sub_180002910(v26, &v22, &v32);
  if ( !(*(unsigned int (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v37 + 8LL))(v37) && v27 )
  {
    Block[0] = &v39;
    v39 = 0;
    si128 = 0u;
    v7 = -1;
    do
      ++v7;
    while ( off_18021D0E0[0][v7] );
    sub_180009070(&v39, off_18021D0E0[0]);
    sub_1801292BC(v41, v26);
    Block[0] = &v39;
    Block[1] = &v42;
    v8 = sub_1800067C4(v28, Block);
    if ( &v18 != (__int128 *)v8 )
    {
      sub_180008354(&v18);
      v9 = v18;
      *(_QWORD *)&v18 = *(_QWORD *)v8;
      *(_QWORD *)v8 = v9;
      v10 = *((_QWORD *)&v18 + 1);
      *((_QWORD *)&v18 + 1) = *(_QWORD *)(v8 + 8);
      *(_QWORD *)(v8 + 8) = v10;
    }
    sub_1800066D4(v28);
    sub_18016CCCC(&v39, 48, 1, sub_1800028F0);
  }
  if ( (*(unsigned int (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)v37 + 8LL))(v37) )
  {
    if ( a2 )
      *(_DWORD *)a2 = 4;
    sub_1800066D4(v26);
    if ( v24 )
      v23();
LABEL_18:
    v24 = 19937;
    sub_1800066D4(&v18);
    return 0;
  }
  v12 = (_QWORD *)sub_1801292BC(v28, &v18);
  v39 = 0;
  si128 = _mm_load_si128((const __m128i *)&xmmword_1801BB7D0);
  LOBYTE(v39) = 0;
  v19 = 3;
  (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v12 + 24LL))(*v12, &v39);
  v13 = (_QWORD **)sub_180005C90(Block, &v39);
  v14 = *v13;
  *v13 = 0;
  v15 = Block[0];
  if ( Block[0] )
  {
    sub_180009174((char *)Block[0] + 16);
    free(v15);
  }
  Block[0] = (void *)19937;
  sub_180009174(&v39);
  sub_18000675C(v28);
  if ( (*(unsigned int (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)this + 24LL))(this) )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD *))(*v14 + 8LL))(v14);
    if ( v16 >= (*(unsigned int (__fastcall **)(ChartPlayer::Detail *))(*(_QWORD *)this + 24LL))(this) )
    {
      if ( a2 )
        *(_DWORD *)a2 = 6;
      if ( v14 )
      {
        v17 = (void (__fastcall ***)(_QWORD, __int64))((char *)v14 + *(int *)(v14[1] + 4LL) + 8);
        (**v17)(v17, 1);
      }
      sub_1800066D4(v26);
      if ( v24 )
        v23();
      goto LABEL_18;
    }
  }
  if ( a2 )
    *(_DWORD *)a2 = 1;
  sub_1800066D4(v26);
  if ( v24 )
    v23();
  v24 = 19937;
  sub_1800066D4(&v18);
  return (struct ChartPlayer::IString *)v14;
}

```

## disassembly

```asm
0x180004eb0  mov     r11, rsp
0x180004eb3  mov     [r11+18h], rbx
0x180004eb7  mov     [r11+20h], rsi
0x180004ebb  push    rdi
0x180004ebc  push    r14
0x180004ebe  push    r15
0x180004ec0  sub     rsp, 160h
0x180004ec7  mov     rax, cs:__security_cookie
0x180004ece  xor     rax, rsp
0x180004ed1  mov     [rsp+178h+var_20], rax
0x180004ed9  mov     rdi, rdx
0x180004edc  mov     r15, rcx
0x180004edf  mov     [rsp+178h+var_140], rdx
0x180004ee4  mov     [rsp+178h+var_148], 0
0x180004eec  mov     [r11-78h], rcx
0x180004ef0  mov     rax, [rcx]
0x180004ef3  mov     rax, [rax]
0x180004ef6  call    cs:__guard_dispatch_icall_fptr
0x180004efc  mov     [rsp+178h+var_70], rax
0x180004f04  xor     ecx, ecx
0x180004f06  mov     [rsp+178h+var_68], ecx
0x180004f0d  mov     [rsp+178h+var_64], cx
0x180004f15  mov     [rsp+178h+var_62], cl
0x180004f1c  test    rax, rax
0x180004f1f  jz      loc_18000535C
0x180004f25  mov     [rsp+178h+var_60], r15
0x180004f2d  xor     eax, eax
0x180004f2f  mov     [rsp+178h+var_58], rax
0x180004f37  lea     rcx, [rsp+178h+Block]
0x180004f3c  call    sub_180009200
0x180004f41  mov     rcx, [rax]
0x180004f44  mov     [rsp+178h+var_58], rcx
0x180004f4c  lea     rcx, [rsp+178h+var_78]
0x180004f54  call    sub_18000149C
0x180004f59  cmp     [rsp+178h+var_70], 0
0x180004f62  jz      loc_180005387
0x180004f68  xorps   xmm0, xmm0
0x180004f6b  movdqu  [rsp+178h+var_158], xmm0
0x180004f71  mov     ecx, 50h ; 'P'; Size
0x180004f76  call    cs:malloc
0x180004f7c  test    rax, rax
0x180004f7f  jnz     short loc_180004F87
0x180004f81  call    cs:?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180004f87  mov     [rax], rax
0x180004f8a  mov     [rax+8], rax
0x180004f8e  mov     [rax+10h], rax
0x180004f92  mov     word ptr [rax+18h], 101h
0x180004f98  mov     qword ptr [rsp+178h+var_158], rax
0x180004f9d  mov     rcx, [rsp+178h+var_60]
0x180004fa5  mov     rax, [rcx]
0x180004fa8  mov     rax, [rax+40h]
0x180004fac  call    cs:__guard_dispatch_icall_fptr
0x180004fb2  mov     rbx, rax
0x180004fb5  lea     rcx, [rsp+178h+var_78]
0x180004fbd  call    sub_18000149C
0x180004fc2  lea     rax, ??_7InteractiveElement@ChartPlayer@@6B@; const ChartPlayer::InteractiveElement::`vftable'
0x180004fc9  mov     [rsp+178h+var_128], rax
0x180004fce  mov     rcx, [rsp+178h+var_70]
0x180004fd6  mov     [rsp+178h+var_120], rcx
0x180004fdb  mov     [rsp+178h+var_118], rbx
0x180004fe0  lea     rax, [rsp+178h+var_78]
0x180004fe8  mov     [rsp+178h+var_110], rax
0x180004fed  lea     rcx, [rsp+178h+var_78]
0x180004ff5  call    sub_18000149C
0x180004ffa  cmp     [rsp+178h+var_118], 0
0x180005000  jz      loc_1800053B5
0x180005006  lea     r8, [rsp+178h+var_78]
0x18000500e  lea     rdx, [rsp+178h+var_128]
0x180005013  lea     rcx, [rsp+178h+var_108]
0x180005018  call    sub_180002910
0x18000501d  mov     rcx, [rsp+178h+var_60]
0x180005025  mov     rax, [rcx]
0x180005028  mov     rax, [rax+8]
0x18000502c  call    cs:__guard_dispatch_icall_fptr
0x180005032  test    eax, eax
0x180005034  jnz     loc_180005139
0x18000503a  cmp     [rsp+178h+var_100], 0
0x180005040  jz      loc_180005139
0x180005046  lea     rax, [rsp+178h+var_50]
0x18000504e  mov     [rsp+178h+Block], rax
0x180005053  mov     rdx, cs:off_18021D0E0; "root"
0x18000505a  xorps   xmm0, xmm0
0x18000505d  movups  [rsp+178h+var_50], xmm0
0x180005065  mov     qword ptr [rsp+178h+var_40], 0
0x180005071  mov     qword ptr [rsp+178h+var_40+8], 0
0x18000507d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005081  inc     r8
0x180005084  cmp     byte ptr [rdx+r8], 0
0x180005089  jnz     short loc_180005081
0x18000508b  lea     rcx, [rsp+178h+var_50]
0x180005093  call    sub_180009070
0x180005098  lea     rdx, [rsp+178h+var_108]
0x18000509d  lea     rcx, [rsp+178h+var_30]
0x1800050a5  call    sub_1801292BC
0x1800050aa  lea     rax, [rsp+178h+var_50]
0x1800050b2  mov     [rsp+178h+Block], rax
0x1800050b7  lea     rax, [rsp+178h+var_20]
0x1800050bf  mov     [rsp+178h+var_130], rax
0x1800050c4  lea     rdx, [rsp+178h+Block]
0x1800050c9  lea     rcx, [rsp+178h+var_F8]
0x1800050d1  call    sub_1800067C4
0x1800050d6  mov     rbx, rax
0x1800050d9  lea     rax, [rsp+178h+var_158]
0x1800050de  cmp     rax, rbx
0x1800050e1  jz      short loc_18000510F
0x1800050e3  lea     rcx, [rsp+178h+var_158]
0x1800050e8  call    sub_180008354
0x1800050ed  mov     rdx, qword ptr [rsp+178h+var_158]
0x1800050f2  mov     rcx, [rbx]
0x1800050f5  mov     qword ptr [rsp+178h+var_158], rcx
0x1800050fa  mov     [rbx], rdx
0x1800050fd  mov     rcx, qword ptr [rsp+178h+var_158+8]
0x180005102  mov     rax, [rbx+8]
0x180005106  mov     qword ptr [rsp+178h+var_158+8], rax
0x18000510b  mov     [rbx+8], rcx
0x18000510f  lea     rcx, [rsp+178h+var_F8]
0x180005117  call    sub_1800066D4
0x18000511c  lea     r9, sub_1800028F0
0x180005123  mov     edx, 30h ; '0'
0x180005128  lea     r8d, [rdx-2Fh]
0x18000512c  lea     rcx, [rsp+178h+var_50]
0x180005134  call    sub_18016CCCC
0x180005139  mov     rcx, [rsp+178h+var_60]
0x180005141  mov     rax, [rcx]
0x180005144  mov     rax, [rax+8]
0x180005148  call    cs:__guard_dispatch_icall_fptr
0x18000514e  test    eax, eax
0x180005150  jz      short loc_180005197
0x180005152  test    rdi, rdi
0x180005155  jz      short loc_18000515D
0x180005157  mov     dword ptr [rdi], 4
0x18000515d  lea     rcx, [rsp+178h+var_108]
0x180005162  call    sub_1800066D4
0x180005167  mov     rcx, [rsp+178h+var_118]
0x18000516c  test    rcx, rcx
0x18000516f  jz      short loc_18000517C
0x180005171  mov     rax, [rsp+178h+var_120]
0x180005176  call    cs:__guard_dispatch_icall_fptr
0x18000517c  mov     esi, 4DE1h
0x180005181  mov     [rsp+178h+var_118], rsi
0x180005186  lea     rcx, [rsp+178h+var_158]
0x18000518b  call    sub_1800066D4
0x180005190  xor     eax, eax
0x180005192  jmp     loc_180005331
0x180005197  lea     rdx, [rsp+178h+var_158]
0x18000519c  lea     rcx, [rsp+178h+var_F8]
0x1800051a4  call    sub_1801292BC
0x1800051a9  xorps   xmm0, xmm0
0x1800051ac  movups  [rsp+178h+var_50], xmm0
0x1800051b4  movdqa  xmm1, cs:xmmword_1801BB7D0
0x1800051bc  movdqu  [rsp+178h+var_40], xmm1
0x1800051c5  mov     byte ptr [rsp+178h+var_50], 0
0x1800051cd  mov     [rsp+178h+var_148], 3
0x1800051d5  mov     rcx, [rax]
0x1800051d8  mov     rax, [rcx]
0x1800051db  lea     rdx, [rsp+178h+var_50]
0x1800051e3  mov     rax, [rax+18h]
0x1800051e7  call    cs:__guard_dispatch_icall_fptr
0x1800051ed  lea     rdx, [rsp+178h+var_50]
0x1800051f5  lea     rcx, [rsp+178h+Block]
0x1800051fa  call    sub_180005C90
0x1800051ff  mov     r14, [rax]
0x180005202  mov     qword ptr [rax], 0
0x180005209  mov     rbx, [rsp+178h+Block]
0x18000520e  test    rbx, rbx
0x180005211  jz      short loc_180005225
0x180005213  lea     rcx, [rbx+10h]
0x180005217  call    sub_180009174
0x18000521c  mov     rcx, rbx; Block
0x18000521f  call    cs:free
0x180005225  mov     esi, 4DE1h
0x18000522a  mov     [rsp+178h+Block], rsi
0x18000522f  lea     rcx, [rsp+178h+var_50]
0x180005237  call    sub_180009174
0x18000523c  lea     rcx, [rsp+178h+var_F8]
0x180005244  call    sub_18000675C
0x180005249  nop     dword ptr [rax+00000000h]
0x180005250  mov     rax, [r15]
0x180005253  mov     rcx, r15
0x180005256  mov     rax, [rax+18h]
0x18000525a  call    cs:__guard_dispatch_icall_fptr
0x180005260  test    eax, eax
0x180005262  jz      loc_1800052F1
0x180005268  mov     rax, [r14]
0x18000526b  mov     rcx, r14
0x18000526e  mov     rax, [rax+8]
0x180005272  call    cs:__guard_dispatch_icall_fptr
0x180005278  mov     ebx, eax
0x18000527a  mov     rdx, [r15]
0x18000527d  mov     rcx, r15
0x180005280  mov     rax, [rdx+18h]
0x180005284  call    cs:__guard_dispatch_icall_fptr
0x18000528a  cmp     ebx, eax
0x18000528c  jb      short loc_1800052F1
0x18000528e  test    rdi, rdi
0x180005291  jz      short loc_180005299
0x180005293  mov     dword ptr [rdi], 6
0x180005299  test    r14, r14
0x18000529c  jz      short loc_1800052BF
0x18000529e  mov     rax, [r14+8]
0x1800052a2  movsxd  rcx, dword ptr [rax+4]
0x1800052a6  add     rcx, 8
0x1800052aa  add     rcx, r14
0x1800052ad  mov     rax, [rcx]
0x1800052b0  mov     edx, 1
0x1800052b5  mov     rax, [rax]
0x1800052b8  call    cs:__guard_dispatch_icall_fptr
0x1800052be  nop
0x1800052bf  lea     rcx, [rsp+178h+var_108]
0x1800052c4  call    sub_1800066D4
0x1800052c9  mov     rcx, [rsp+178h+var_118]
0x1800052ce  test    rcx, rcx
0x1800052d1  jz      short loc_1800052DE
0x1800052d3  mov     rax, [rsp+178h+var_120]
0x1800052d8  call    cs:__guard_dispatch_icall_fptr
0x1800052de  mov     [rsp+178h+var_118], rsi
0x1800052e3  lea     rcx, [rsp+178h+var_158]
0x1800052e8  call    sub_1800066D4
0x1800052ed  xor     eax, eax
0x1800052ef  jmp     short loc_180005331
0x1800052f1  test    rdi, rdi
0x1800052f4  jz      short loc_1800052FC
0x1800052f6  mov     dword ptr [rdi], 1
0x1800052fc  lea     rcx, [rsp+178h+var_108]
0x180005301  call    sub_1800066D4
0x180005306  mov     rcx, [rsp+178h+var_118]
0x18000530b  test    rcx, rcx
0x18000530e  jz      short loc_18000531B
0x180005310  mov     rax, [rsp+178h+var_120]
0x180005315  call    cs:__guard_dispatch_icall_fptr
0x18000531b  mov     [rsp+178h+var_118], rsi
0x180005320  lea     rcx, [rsp+178h+var_158]
0x180005325  call    sub_1800066D4
0x18000532a  mov     rax, r14
0x18000532d  jmp     short loc_180005331
0x18000532f  xor     eax, eax
0x180005331  mov     rcx, [rsp+178h+var_20]
0x180005339  xor     rcx, rsp; StackCookie
0x18000533c  call    __security_check_cookie
0x180005341  lea     r11, [rsp+178h+var_18]
0x180005349  mov     rbx, [r11+30h]
0x18000534d  mov     rsi, [r11+38h]
0x180005351  mov     rsp, r11
0x180005354  pop     r15
0x180005356  pop     r14
0x180005358  pop     rdi
0x180005359  retn
0x18000535a  jmp     short loc_18000532F
0x18000535c  lea     r8, aChartplayerCli_0; "ChartPlayer client didn't return a Dele"...
0x180005363  lea     edx, [rax+2]
0x180005366  lea     rcx, [rsp+178h+pExceptionObject]
0x18000536e  call    sub_180001224
0x180005373  lea     rdx, __TI3?AUChartPlayerError@ChartPlayer@@; pThrowInfo
0x18000537a  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x180005382  call    _CxxThrowException
0x180005387  lea     r8, aChartplayerCli_0; "ChartPlayer client didn't return a Dele"...
0x18000538e  mov     edx, 2
0x180005393  lea     rcx, [rsp+178h+var_B8]
0x18000539b  call    sub_180001224
0x1800053a0  lea     rdx, __TI3?AUChartPlayerError@ChartPlayer@@; pThrowInfo
0x1800053a7  lea     rcx, [rsp+178h+var_B8]; pExceptionObject
0x1800053af  call    _CxxThrowException
0x1800053b5  lea     r8, aChartplayerCli_2; "ChartPlayer client didn't return an IIn"...
0x1800053bc  mov     edx, 2
0x1800053c1  lea     rcx, [rsp+178h+var_98]
0x1800053c9  call    sub_180001224
0x1800053ce  lea     rdx, __TI3?AUChartPlayerError@ChartPlayer@@; pThrowInfo
0x1800053d5  lea     rcx, [rsp+178h+var_98]; pExceptionObject
0x1800053dd  call    _CxxThrowException
```
