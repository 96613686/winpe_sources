# __FrameHandler4::FrameUnwindToState(unsigned __int64 *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int)

- ea: `0x14000d960`
- end: `0x14000dc6c`
- name: `?FrameUnwindToState@__FrameHandler4@@SAXPEA_KPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@H@Z`
- size: `780`
- prototype: `void __fastcall(unsigned __int64 *, struct _xDISPATCHER_CONTEXT *, struct FH4::FuncInfo4 *, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x14000b374`
- `0x14000cf60`

## callees

- `0x14000a353`
- `0x14000a390`
- `0x14000b910`
- `0x14000b940`
- `0x14000bb3c`
- `0x14000be88`
- `0x14000bff8`
- `0x14000d960`
- `0x14000ddf4`
- `0x14000dec0`
- `0x14000df94`
- `0x14000e170`
- `0x14000e220`

## pseudocode

```c
void __fastcall __FrameHandler4::FrameUnwindToState(
        unsigned __int64 *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        struct FH4::FuncInfo4 *a3,
        int a4)
{
  int StateFromIterators; // edi
  struct _xDISPATCHER_CONTEXT *v9; // r14
  __int64 v10; // rax
  __int64 *p_ImageBase; // rsi
  __int64 v12; // rcx
  FH4::UWMap4 *v13; // rdx
  _BYTE *v14; // rdx
  __int64 v15; // rcx
  FH4::UWMap4 *v16; // r15
  FH4::UWMap4 *v17; // rbx
  __m128i v18; // xmm6
  int v19; // r9d
  int v20; // eax
  int v21; // ecx
  unsigned __int64 v22; // rdx
  __m128i v23; // xmm6
  unsigned __int64 v24; // r8
  __int64 v25; // rax
  FH4::UWMap4 *v26[2]; // [rsp+30h] [rbp-108h] BYREF
  int v27; // [rsp+40h] [rbp-F8h]
  int v28; // [rsp+44h] [rbp-F4h]
  int v29; // [rsp+48h] [rbp-F0h]
  int *v30; // [rsp+50h] [rbp-E8h] BYREF
  FH4::UWMap4 *v31; // [rsp+58h] [rbp-E0h]
  unsigned __int64 *v32; // [rsp+60h] [rbp-D8h]
  __int64 ImageBase; // [rsp+68h] [rbp-D0h]
  struct _xDISPATCHER_CONTEXT *v34; // [rsp+70h] [rbp-C8h]
  unsigned __int64 *v35; // [rsp+78h] [rbp-C0h]
  __int64 *v36; // [rsp+80h] [rbp-B8h]
  int *v37; // [rsp+88h] [rbp-B0h]
  FH4::UWMap4 *v38; // [rsp+90h] [rbp-A8h]
  __int128 v39; // [rsp+A0h] [rbp-98h] BYREF
  __m128i v40; // [rsp+B0h] [rbp-88h]
  int v41; // [rsp+C0h] [rbp-78h] BYREF
  FH4::UWMap4 *v42; // [rsp+C8h] [rbp-70h]
  __int128 v43; // [rsp+D0h] [rbp-68h]

  v35 = a1;
  v32 = a1;
  v29 = a4;
  ImageBase = GetImageBase();
  StateFromIterators = __FrameHandler4::StateFromControlPc(a3, a2);
  v9 = a2 + 1;
  v34 = a2 + 1;
  if ( LODWORD(a2[1].ControlPc) )
  {
    if ( *(_DWORD *)(_vcrt_getptd() + 120) != -2 )
      abort();
    StateFromIterators = LODWORD(v9->ControlPc) - 2;
  }
  else if ( *(_DWORD *)(_vcrt_getptd() + 120) != -2 )
  {
    StateFromIterators = *(_DWORD *)(_vcrt_getptd() + 120);
    *(_DWORD *)(_vcrt_getptd() + 120) = -2;
  }
  v10 = _vcrt_getptd();
  ++*(_DWORD *)(v10 + 48);
  p_ImageBase = &a2->ImageBase;
  v36 = p_ImageBase;
  v12 = *p_ImageBase;
  v13 = 0;
  v42 = 0;
  v43 = 0;
  if ( *((_DWORD *)a3 + 2) )
  {
    v14 = (_BYTE *)(v12 + *((int *)a3 + 2));
    v15 = *v14 & 0xF;
    v13 = (FH4::UWMap4 *)&v14[-*((char *)&FH4::s_negLengthTab + v15)];
    v41 = *((_DWORD *)v13 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v15);
    v42 = v13;
  }
  else
  {
    v41 = 0;
  }
  v26[0] = (FH4::UWMap4 *)&v41;
  v26[1] = v13;
  v30 = &v41;
  v31 = v13;
  FH4::UWMap4::getStartStop(
    (FH4::UWMap4 *)&v41,
    StateFromIterators,
    a4,
    (struct FH4::UWMap4::iterator *)v26,
    (struct FH4::UWMap4::iterator *)&v30);
  while ( 1 )
  {
    v37 = &v41;
    v38 = v42;
    v16 = v26[1];
    if ( v26[1] < v42 || v26[1] <= v31 )
      break;
    FH4::UWMap4::ReadEntry(v26[0], (unsigned __int8 **)&v26[1]);
    v26[1] = v16;
    v17 = v26[0];
    v40 = *((__m128i *)v26[0] + 1);
    v18 = v40;
    v39 = *(_OWORD *)v26;
    FH4::UWMap4::ReadEntry(v26[0], (unsigned __int8 **)&v26[1]);
    v26[1] = (FH4::UWMap4 *)((char *)v16 - *((unsigned int *)v17 + 4));
    StateFromIterators = FH4::UWMap4::getStateFromIterators(
                           (const struct FH4::UWMap4::iterator *)&v30,
                           a4,
                           (const struct FH4::UWMap4::iterator *)&v39,
                           StateFromIterators,
                           (const struct FH4::UWMap4::iterator *)v26);
    v28 = StateFromIterators;
    v27 = 0;
    v19 = 0;
    v20 = _mm_cvtsi128_si32(_mm_srli_si128(v18, 8));
    v21 = _mm_cvtsi128_si32(_mm_srli_si128(v18, 4));
    if ( v21 )
      v19 = v20;
    v27 = v19;
    if ( v19 )
    {
      LODWORD(v9->ControlPc) = StateFromIterators + 2;
      if ( (unsigned int)(v21 - 1) <= 1 )
      {
        v22 = *v32;
        v23 = _mm_srli_si128(v18, 12);
        if ( v21 == 2 )
          v24 = *(_QWORD *)((unsigned int)_mm_cvtsi128_si32(v23) + v22);
        else
          v24 = v22 + (unsigned int)_mm_cvtsi128_si32(v23);
        CallSettingFrameEncoded(*p_ImageBase + v19, v22, v24, 259);
      }
      else
      {
        CallSettingFrame(*p_ImageBase + v19, a1, 259);
      }
      SetImageBase(ImageBase);
    }
  }
  if ( *(int *)(_vcrt_getptd() + 48) > 0 )
  {
    v25 = _vcrt_getptd();
    --*(_DWORD *)(v25 + 48);
  }
}

```

## disassembly

```asm
0x14000d960  mov     rax, rsp
0x14000d963  push    rbx
0x14000d964  push    rsi
0x14000d965  push    rdi
0x14000d966  push    r12
0x14000d968  push    r13
0x14000d96a  push    r14
0x14000d96c  push    r15
0x14000d96e  sub     rsp, 100h
0x14000d975  movaps  xmmword ptr [rax-48h], xmm6
0x14000d979  mov     rax, cs:__security_cookie
0x14000d980  xor     rax, rsp
0x14000d983  mov     [rsp+138h+var_58], rax
0x14000d98b  mov     r13d, r9d
0x14000d98e  mov     rbx, r8
0x14000d991  mov     rsi, rdx
0x14000d994  mov     r12, rcx
0x14000d997  mov     [rsp+138h+var_C0], rcx
0x14000d99c  mov     [rsp+138h+var_D8], rcx
0x14000d9a1  mov     [rsp+138h+var_F0], r9d
0x14000d9a6  call    _GetImageBase
0x14000d9ab  mov     [rsp+138h+var_D0], rax
0x14000d9b0  mov     rdx, rsi; struct _xDISPATCHER_CONTEXT *
0x14000d9b3  mov     rcx, rbx; struct FH4::FuncInfo4 *
0x14000d9b6  call    ?StateFromControlPc@__FrameHandler4@@SAHPEAUFuncInfo4@FH4@@PEAU_xDISPATCHER_CONTEXT@@@Z; __FrameHandler4::StateFromControlPc(FH4::FuncInfo4 *,_xDISPATCHER_CONTEXT *)
0x14000d9bb  mov     edi, eax
0x14000d9bd  lea     r14, [rsi+48h]
0x14000d9c1  mov     [rsp+138h+var_C8], r14
0x14000d9c6  cmp     dword ptr [r14], 0
0x14000d9ca  jz      short loc_14000D9E3
0x14000d9cc  call    __vcrt_getptd
0x14000d9d1  cmp     dword ptr [rax+78h], 0FFFFFFFEh
0x14000d9d5  jnz     loc_14000DC66
0x14000d9db  mov     edi, [r14]
0x14000d9de  sub     edi, 2
0x14000d9e1  jmp     short loc_14000DA02
0x14000d9e3  call    __vcrt_getptd
0x14000d9e8  cmp     dword ptr [rax+78h], 0FFFFFFFEh
0x14000d9ec  jz      short loc_14000DA02
0x14000d9ee  call    __vcrt_getptd
0x14000d9f3  mov     edi, [rax+78h]
0x14000d9f6  call    __vcrt_getptd
0x14000d9fb  mov     dword ptr [rax+78h], 0FFFFFFFEh
0x14000da02  call    __vcrt_getptd
0x14000da07  inc     dword ptr [rax+30h]
0x14000da0a  add     rsi, 8
0x14000da0e  mov     [rsp+138h+var_B8], rsi
0x14000da16  mov     rcx, [rsi]
0x14000da19  xor     edx, edx
0x14000da1b  mov     [rsp+138h+var_70], rdx
0x14000da23  xorps   xmm0, xmm0
0x14000da26  movups  [rsp+138h+var_68], xmm0
0x14000da2e  cmp     [rbx+8], edx
0x14000da31  jz      short loc_14000DA71
0x14000da33  movsxd  rdx, dword ptr [rbx+8]
0x14000da37  add     rdx, rcx
0x14000da3a  movzx   ecx, byte ptr [rdx]
0x14000da3d  and     ecx, 0Fh
0x14000da40  lea     r8, cs:140000000h
0x14000da47  movsx   rax, byte ptr [rcx+r8+115A0h]
0x14000da50  sub     rdx, rax
0x14000da53  mov     cl, [rcx+r8+115B0h]
0x14000da5b  mov     eax, [rdx-4]
0x14000da5e  shr     eax, cl
0x14000da60  mov     [rsp+138h+var_78], eax
0x14000da67  mov     [rsp+138h+var_70], rdx
0x14000da6f  jmp     short loc_14000DA78
0x14000da71  mov     [rsp+138h+var_78], edx
0x14000da78  lea     rax, [rsp+138h+var_78]
0x14000da80  mov     [rsp+138h+var_108], rax
0x14000da85  mov     [rsp+138h+var_108+8], rdx
0x14000da8a  lea     rax, [rsp+138h+var_78]
0x14000da92  mov     [rsp+138h+var_E8], rax
0x14000da97  mov     [rsp+138h+var_E0], rdx
0x14000da9c  lea     rax, [rsp+138h+var_E8]
0x14000daa1  mov     [rsp+138h+var_118], rax; struct FH4::UWMap4::iterator *
0x14000daa6  lea     r9, [rsp+138h+var_108]; struct FH4::UWMap4::iterator *
0x14000daab  mov     r8d, r13d; int
0x14000daae  mov     edx, edi; int
0x14000dab0  lea     rcx, [rsp+138h+var_78]; this
0x14000dab8  call    ?getStartStop@UWMap4@FH4@@QEAAXHHAEAViterator@12@0@Z; FH4::UWMap4::getStartStop(int,int,FH4::UWMap4::iterator &,FH4::UWMap4::iterator &)
0x14000dabd  nop
0x14000dabe  lea     rax, [rsp+138h+var_78]
0x14000dac6  mov     [rsp+138h+var_B0], rax
0x14000dace  mov     rax, [rsp+138h+var_70]
0x14000dad6  mov     [rsp+138h+var_A8], rax
0x14000dade  mov     r15, [rsp+138h+var_108+8]
0x14000dae3  cmp     r15, rax
0x14000dae6  jb      loc_14000DC28
0x14000daec  cmp     r15, [rsp+138h+var_E0]
0x14000daf1  jbe     loc_14000DC28
0x14000daf7  lea     rdx, [rsp+138h+var_108+8]; unsigned __int8 **
0x14000dafc  mov     rcx, [rsp+138h+var_108]; this
0x14000db01  call    ?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z; FH4::UWMap4::ReadEntry(uchar * *)
0x14000db06  mov     [rsp+138h+var_108+8], r15
0x14000db0b  mov     rbx, [rsp+138h+var_108]
0x14000db10  movups  xmm6, xmmword ptr [rbx+10h]
0x14000db14  movups  [rsp+138h+var_88], xmm6
0x14000db1c  movaps  xmm0, xmmword ptr [rsp+138h+var_108]
0x14000db21  movdqa  [rsp+138h+var_98], xmm0
0x14000db2a  lea     rdx, [rsp+138h+var_108+8]; unsigned __int8 **
0x14000db2f  mov     rcx, rbx; this
0x14000db32  call    ?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z; FH4::UWMap4::ReadEntry(uchar * *)
0x14000db37  mov     eax, [rbx+10h]
0x14000db3a  sub     r15, rax
0x14000db3d  mov     [rsp+138h+var_108+8], r15
0x14000db42  lea     rax, [rsp+138h+var_108]
0x14000db47  mov     [rsp+138h+var_118], rax; struct FH4::UWMap4::iterator *
0x14000db4c  mov     r9d, edi; int
0x14000db4f  lea     r8, [rsp+138h+var_98]; struct FH4::UWMap4::iterator *
0x14000db57  mov     edx, r13d; int
0x14000db5a  lea     rcx, [rsp+138h+var_E8]; struct FH4::UWMap4::iterator *
0x14000db5f  call    ?getStateFromIterators@UWMap4@FH4@@SAHAEBViterator@12@H0H0@Z; FH4::UWMap4::getStateFromIterators(FH4::UWMap4::iterator const &,int,FH4::UWMap4::iterator const &,int,FH4::UWMap4::iterator const &)
0x14000db64  mov     edi, eax
0x14000db66  mov     [rsp+138h+var_F4], eax
0x14000db6a  mov     [rsp+138h+var_F8], 0
0x14000db72  xor     r9d, r9d
0x14000db75  movdqa  xmm0, xmm6
0x14000db79  psrldq  xmm0, 8
0x14000db7e  movd    eax, xmm0
0x14000db82  movdqa  xmm1, xmm6
0x14000db86  psrldq  xmm1, 4
0x14000db8b  movd    ecx, xmm1
0x14000db8f  test    ecx, ecx
0x14000db91  cmovnz  r9d, eax
0x14000db95  mov     [rsp+138h+var_F8], r9d
0x14000db9a  test    r9d, r9d
0x14000db9d  jz      loc_14000DC23
0x14000dba3  lea     eax, [rdi+2]
0x14000dba6  mov     [r14], eax
0x14000dba9  lea     eax, [rcx-1]
0x14000dbac  cmp     eax, 1
0x14000dbaf  jbe     short loc_14000DBC7
0x14000dbb1  movsxd  rcx, r9d
0x14000dbb4  add     rcx, [rsi]
0x14000dbb7  mov     r8d, 103h
0x14000dbbd  mov     rdx, r12
0x14000dbc0  call    _CallSettingFrame
0x14000dbc5  jmp     short loc_14000DBFC
0x14000dbc7  mov     rax, [rsp+138h+var_D8]
0x14000dbcc  mov     rdx, [rax]
0x14000dbcf  psrldq  xmm6, 0Ch
0x14000dbd4  cmp     ecx, 2
0x14000dbd7  jnz     short loc_14000DBE3
0x14000dbd9  movd    eax, xmm6
0x14000dbdd  mov     r8, [rax+rdx]
0x14000dbe1  jmp     short loc_14000DBEB
0x14000dbe3  movd    r8d, xmm6
0x14000dbe8  add     r8, rdx
0x14000dbeb  movsxd  rcx, r9d
0x14000dbee  add     rcx, [rsi]
0x14000dbf1  mov     r9d, 103h
0x14000dbf7  call    _CallSettingFrameEncoded
0x14000dbfc  mov     rcx, [rsp+138h+var_D0]
0x14000dc01  call    _SetImageBase
0x14000dc06  jmp     short loc_14000DC23
0x14000dc08  mov     edi, [rsp+138h+var_F4]
0x14000dc0c  mov     r14, [rsp+138h+var_C8]
0x14000dc11  mov     r12, [rsp+138h+var_C0]
0x14000dc16  mov     r13d, [rsp+138h+var_F0]
0x14000dc1b  mov     rsi, [rsp+138h+var_B8]
0x14000dc23  jmp     loc_14000DABE
0x14000dc28  call    __vcrt_getptd
0x14000dc2d  cmp     dword ptr [rax+30h], 0
0x14000dc31  jle     short loc_14000DC3B
0x14000dc33  call    __vcrt_getptd
0x14000dc38  dec     dword ptr [rax+30h]
0x14000dc3b  mov     rcx, [rsp+138h+var_58]
0x14000dc43  xor     rcx, rsp; StackCookie
0x14000dc46  call    __security_check_cookie
0x14000dc4b  movaps  xmm6, [rsp+138h+var_48]
0x14000dc53  add     rsp, 100h
0x14000dc5a  pop     r15
0x14000dc5c  pop     r14
0x14000dc5e  pop     r13
0x14000dc60  pop     r12
0x14000dc62  pop     rdi
0x14000dc63  pop     rsi
0x14000dc64  pop     rbx
0x14000dc65  retn
0x14000dc66  call    abort
0x1400101f9  push    rbp
0x1400101fb  sub     rsp, 30h
0x1400101ff  mov     rbp, rdx
0x140010202  call    __FrameUnwindFilter
0x140010207  nop
0x140010208  add     rsp, 30h
0x14001020c  pop     rbp
0x14001020d  retn
0x14001020f  push    rbp
0x140010211  sub     rsp, 30h
0x140010215  mov     rbp, rdx
0x140010218  call    __vcrt_getptd
0x14001021d  cmp     dword ptr [rax+30h], 0
0x140010221  jle     short loc_14001022B
0x140010223  call    __vcrt_getptd
0x140010228  dec     dword ptr [rax+30h]
0x14001022b  add     rsp, 30h
0x14001022f  pop     rbp
0x140010230  retn
```
