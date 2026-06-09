# Spectre::Transcoder::get_binary_item(std::shared_ptr<Spectre::Transcoder::TranscoderTextStream>,unsigned __int64,unsigned __int64,Spectre::Transcoder::PLYDataType,bool,__int64 *,unsigned __int64 *,float *)

- ea: `0x18036d980`
- end: `0x18036e0bc`
- name: `?get_binary_item@Transcoder@Spectre@@YAEV?$shared_ptr@VTranscoderTextStream@Transcoder@Spectre@@@std@@_K1W4PLYDataType@12@_NPEA_JPEA_KPEAM@Z`
- size: `1852`
- prototype: `char __fastcall(_QWORD *, __int64, __int64, int, char, double *, unsigned __int64 *, float *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180368e80`

## callees

- `0x1801d5400`
- `0x18036d980`
- `0x18039e5b0`
- `0x1804f99e0`

## import_xrefs

- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036da3c`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036db02`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036dbd9`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036dc9b`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036dd5b`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036de47`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036dea5`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036df90`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036da3c`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036db02`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036dbd9`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036dc9b`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036dd5b`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036de47`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036dea5`
- `MSVCP140!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18036df90`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Spectre::Transcoder::get_binary_item(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        double *a6,
        unsigned __int64 *a7,
        float *a8)
{
  volatile signed __int32 *v9; // rax
  unsigned __int64 v10; // r14
  float v11; // xmm0_4
  char result; // al
  volatile signed __int32 *v13; // rax
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // rcx
  volatile signed __int32 *v16; // rax
  __int64 v17; // r14
  volatile signed __int32 *v18; // rax
  __int64 v19; // r14
  volatile signed __int32 *v20; // rax
  unsigned int v21; // ebx
  volatile signed __int32 *v22; // r14
  volatile signed __int32 *v23; // rax
  volatile signed __int32 *v24; // rax
  int v25; // xmm6_4
  volatile signed __int32 *v26; // rax
  double v27; // xmm6_8
  unsigned int v28; // [rsp+28h] [rbp-B9h]
  unsigned int v29; // [rsp+28h] [rbp-B9h]
  double v30; // [rsp+28h] [rbp-B9h]
  _QWORD *v31; // [rsp+38h] [rbp-A9h]
  volatile signed __int32 *v32; // [rsp+40h] [rbp-A1h]
  _QWORD *v33; // [rsp+48h] [rbp-99h]
  volatile signed __int32 *v34; // [rsp+50h] [rbp-91h]
  _QWORD *v35; // [rsp+58h] [rbp-89h]
  volatile signed __int32 *v36; // [rsp+60h] [rbp-81h]
  _QWORD *v37; // [rsp+68h] [rbp-79h]
  volatile signed __int32 *v38; // [rsp+70h] [rbp-71h]
  _QWORD *v39; // [rsp+78h] [rbp-69h]
  volatile signed __int32 *v40; // [rsp+80h] [rbp-61h]
  _QWORD *v41; // [rsp+88h] [rbp-59h]
  volatile signed __int32 *v42; // [rsp+90h] [rbp-51h]
  _QWORD *v43; // [rsp+98h] [rbp-49h]
  volatile signed __int32 *v44; // [rsp+A0h] [rbp-41h]
  _QWORD *v45; // [rsp+A8h] [rbp-39h]
  volatile signed __int32 *v46; // [rsp+B0h] [rbp-31h]
  char v47; // [rsp+B8h] [rbp-29h] BYREF
  char v48[3]; // [rsp+B9h] [rbp-28h] BYREF
  __int16 v49; // [rsp+BCh] [rbp-25h] BYREF
  __int16 v50[2]; // [rsp+C0h] [rbp-21h] BYREF
  unsigned int v51; // [rsp+C4h] [rbp-1Dh] BYREF
  unsigned int v52; // [rsp+C8h] [rbp-19h] BYREF
  int v53; // [rsp+CCh] [rbp-15h] BYREF
  double v54; // [rsp+D0h] [rbp-11h] BYREF

  switch ( a4 )
  {
    case 1:
      if ( a3 == a2 )
        goto LABEL_73;
      v9 = (volatile signed __int32 *)a1[1];
      if ( v9 )
      {
        _InterlockedIncrement(v9 + 2);
        v9 = (volatile signed __int32 *)a1[1];
      }
      v31 = (_QWORD *)*a1;
      v32 = v9;
      v47 = 0;
      std::istream::read(*v31, &v47, 1);
      v10 = v47;
      if ( v32 && _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
      *(_QWORD *)a6 = v10;
      *a7 = v10;
      v11 = (float)(int)*(_QWORD *)a6;
      goto LABEL_10;
    case 2:
      if ( (unsigned __int64)(a3 - a2) < 2 )
        goto LABEL_73;
      v16 = (volatile signed __int32 *)a1[1];
      if ( v16 )
      {
        _InterlockedIncrement(v16 + 2);
        v16 = (volatile signed __int32 *)a1[1];
      }
      v35 = (_QWORD *)*a1;
      v36 = v16;
      v49 = 0;
      std::istream::read(*v35, &v49, 2);
      v17 = v49;
      if ( v36 )
      {
        if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
          if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
        }
      }
      *a7 = (unsigned __int16)v17;
      *(_QWORD *)a6 = v17;
      *a8 = (float)(int)v17;
      std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(a1);
      return 2;
    case 3:
      if ( (unsigned __int64)(a3 - a2) < 4 )
        goto LABEL_73;
      v20 = (volatile signed __int32 *)a1[1];
      if ( v20 )
      {
        _InterlockedIncrement(v20 + 2);
        v20 = (volatile signed __int32 *)a1[1];
      }
      v39 = (_QWORD *)*a1;
      v40 = v20;
      v51 = 0;
      std::istream::read(*v39, &v51, 4);
      v21 = v51;
      v22 = v40;
      goto LABEL_41;
    case 4:
      if ( a3 == a2 )
        goto LABEL_73;
      v13 = (volatile signed __int32 *)a1[1];
      if ( v13 )
      {
        _InterlockedIncrement(v13 + 2);
        v13 = (volatile signed __int32 *)a1[1];
      }
      v33 = (_QWORD *)*a1;
      v34 = v13;
      v48[0] = 0;
      std::istream::read(*v33, v48, 1);
      v14 = (unsigned __int8)v48[0];
      if ( v34 )
      {
        if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
          if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
        }
      }
      *a7 = v14;
      *(_QWORD *)a6 = v14;
      v15 = *a7;
      if ( (*a7 & 0x8000000000000000uLL) != 0LL )
        v11 = (float)(int)(*(_DWORD *)a7 & 1 | (v15 >> 1)) + (float)(int)(*(_DWORD *)a7 & 1 | (v15 >> 1));
      else
        v11 = (float)(int)v15;
LABEL_10:
      *a8 = v11;
      std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(a1);
      return 1;
    case 5:
      if ( (unsigned __int64)(a3 - a2) < 2 )
        goto LABEL_73;
      v18 = (volatile signed __int32 *)a1[1];
      if ( v18 )
      {
        _InterlockedIncrement(v18 + 2);
        v18 = (volatile signed __int32 *)a1[1];
      }
      v37 = (_QWORD *)*a1;
      v38 = v18;
      v50[0] = 0;
      std::istream::read(*v37, v50, 2);
      v19 = v50[0];
      if ( v38 )
      {
        if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
          if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
        }
      }
      *a7 = (unsigned __int16)v19;
      *(_QWORD *)a6 = v19;
      *a8 = (float)(int)v19;
      std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(a1);
      return 2;
    case 6:
      if ( (unsigned __int64)(a3 - a2) < 4 )
        goto LABEL_73;
      v23 = (volatile signed __int32 *)a1[1];
      if ( v23 )
      {
        _InterlockedIncrement(v23 + 2);
        v23 = (volatile signed __int32 *)a1[1];
      }
      v41 = (_QWORD *)*a1;
      v42 = v23;
      v52 = 0;
      std::istream::read(*v41, &v52, 4);
      v21 = v52;
      v22 = v42;
LABEL_41:
      if ( v22 )
      {
        if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
      v28 = v21;
      if ( a5 )
      {
        LOBYTE(v28) = HIBYTE(v21);
        HIBYTE(v28) = v21;
        BYTE1(v28) = BYTE2(v21);
        BYTE2(v28) = BYTE1(v21);
        v21 = v28;
      }
      *a7 = v21;
      *(_QWORD *)a6 = (int)v21;
      *(_DWORD *)a8 = v28;
      goto LABEL_48;
    case 7:
      if ( (unsigned __int64)(a3 - a2) < 4 )
        goto LABEL_73;
      v24 = (volatile signed __int32 *)a1[1];
      if ( v24 )
      {
        _InterlockedIncrement(v24 + 2);
        v24 = (volatile signed __int32 *)a1[1];
      }
      v43 = (_QWORD *)*a1;
      v44 = v24;
      v53 = 0;
      std::istream::read(*v43, &v53, 4);
      v25 = v53;
      if ( v44 )
      {
        if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
          if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
        }
      }
      v29 = v25;
      if ( a5 )
      {
        LOBYTE(v29) = HIBYTE(v25);
        HIBYTE(v29) = v25;
        BYTE1(v29) = BYTE2(v25);
        BYTE2(v29) = BYTE1(v25);
        v25 = v29;
      }
      *(_DWORD *)a8 = v25;
      *(_QWORD *)a6 = (int)v29;
      *a7 = v29;
LABEL_48:
      std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(a1);
      result = 4;
      break;
    case 8:
      if ( (unsigned __int64)(a3 - a2) < 8 )
        goto LABEL_73;
      v26 = (volatile signed __int32 *)a1[1];
      if ( v26 )
      {
        _InterlockedIncrement(v26 + 2);
        v26 = (volatile signed __int32 *)a1[1];
      }
      v45 = (_QWORD *)*a1;
      v46 = v26;
      v54 = 0.0;
      std::istream::read(*v45, &v54, 8);
      v27 = v54;
      if ( v46 )
      {
        if ( _InterlockedExchangeAdd(v46 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
          if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
        }
      }
      v30 = v27;
      if ( a5 )
      {
        LOBYTE(v30) = BYTE3(v27);
        BYTE3(v30) = LOBYTE(v27);
        BYTE1(v30) = BYTE2(v27);
        BYTE2(v30) = BYTE1(v27);
        BYTE4(v30) = HIBYTE(v27);
        HIBYTE(v30) = BYTE4(v27);
        BYTE5(v30) = BYTE6(v27);
        BYTE6(v30) = BYTE5(v27);
        v27 = v30;
      }
      *a8 = v27;
      *a6 = v30;
      *(double *)a7 = v30;
      std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(a1);
      result = 8;
      break;
    default:
LABEL_73:
      std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(a1);
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18036d980  mov     rax, rsp
0x18036d983  mov     [rax+10h], rbx
0x18036d987  mov     [rax+18h], rsi
0x18036d98b  mov     [rax+20h], rdi
0x18036d98f  push    rbp
0x18036d990  push    r12
0x18036d992  push    r13
0x18036d994  push    r14
0x18036d996  push    r15
0x18036d998  lea     rbp, [rax-3Fh]
0x18036d99c  sub     rsp, 0F0h
0x18036d9a3  movaps  xmmword ptr [rax-38h], xmm6
0x18036d9a7  mov     rax, cs:__security_cookie
0x18036d9ae  xor     rax, rsp
0x18036d9b1  mov     [rbp+37h+var_40], rax
0x18036d9b5  mov     rsi, rcx
0x18036d9b8  mov     [rsp+110h+var_F0], rcx
0x18036d9bd  mov     r12, [rbp+37h+arg_28]
0x18036d9c1  mov     r15, [rbp+37h+arg_30]
0x18036d9c5  mov     r13, [rbp+37h+arg_38]
0x18036d9c9  dec     r9d; switch 8 cases
0x18036d9cc  cmp     r9d, 7
0x18036d9d0  ja      def_18036D9EB; jumptable 000000018036D9EB default case
0x18036d9d6  movsxd  rax, r9d
0x18036d9d9  lea     r9, __ImageBase
0x18036d9e0  mov     ecx, ds:(jpt_18036D9EB - 180000000h)[r9+rax*4]
0x18036d9e8  add     rcx, r9
0x18036d9eb  jmp     rcx; switch jump
0x18036d9ed  sub     r8, rdx; jumptable 000000018036D9EB case 1
0x18036d9f0  cmp     r8, 1
0x18036d9f4  jb      def_18036D9EB; jumptable 000000018036D9EB default case
0x18036d9fa  xorps   xmm0, xmm0
0x18036d9fd  movdqu  [rsp+110h+var_E8+8], xmm0
0x18036da03  mov     rax, [rsi+8]
0x18036da07  test    rax, rax
0x18036da0a  jz      short loc_18036DA14
0x18036da0c  lock inc dword ptr [rax+8]
0x18036da10  mov     rax, [rsi+8]
0x18036da14  mov     rcx, [rsi]
0x18036da17  mov     qword ptr [rsp+110h+var_E8+8], rcx
0x18036da1c  mov     qword ptr [rsp+110h+var_D8], rax
0x18036da21  lea     rax, [rsp+110h+var_E8+8]
0x18036da26  mov     qword ptr [rsp+110h+var_E8], rax
0x18036da2b  mov     [rbp+37h+var_60], 0
0x18036da2f  mov     r8d, 1
0x18036da35  lea     rdx, [rbp+37h+var_60]
0x18036da39  mov     rcx, [rcx]
0x18036da3c  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18036da42  movsx   r14, [rbp+37h+var_60]
0x18036da47  mov     rbx, qword ptr [rsp+110h+var_D8]
0x18036da4c  test    rbx, rbx
0x18036da4f  jz      short loc_18036DA8B
0x18036da51  mov     edi, 0FFFFFFFFh
0x18036da56  mov     eax, edi
0x18036da58  lock xadd [rbx+8], eax
0x18036da5d  cmp     eax, 1
0x18036da60  jnz     short loc_18036DA8B
0x18036da62  mov     rax, [rbx]
0x18036da65  mov     rcx, rbx
0x18036da68  mov     rax, [rax]
0x18036da6b  call    cs:__guard_dispatch_icall_fptr
0x18036da71  lock xadd [rbx+0Ch], edi
0x18036da76  cmp     edi, 1
0x18036da79  jnz     short loc_18036DA8B
0x18036da7b  mov     rax, [rbx]
0x18036da7e  mov     rcx, rbx
0x18036da81  mov     rax, [rax+8]
0x18036da85  call    cs:__guard_dispatch_icall_fptr
0x18036da8b  mov     rax, r14
0x18036da8e  mov     [r12], rax
0x18036da92  mov     [r15], rax
0x18036da95  xorps   xmm0, xmm0
0x18036da98  cvtsi2ss xmm0, qword ptr [r12]
0x18036da9e  movss   dword ptr [r13+0], xmm0
0x18036daa4  mov     rcx, rsi; void *
0x18036daa7  call    ??1?$shared_ptr@VDeviceVertexLayout@Engine@Spectre@@@std@@QEAA@XZ; std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(void)
0x18036daac  mov     al, 1
0x18036daae  jmp     loc_18036E068
0x18036dab3  sub     r8, rdx; jumptable 000000018036D9EB case 4
0x18036dab6  cmp     r8, 1
0x18036daba  jb      def_18036D9EB; jumptable 000000018036D9EB default case
0x18036dac0  xorps   xmm0, xmm0
0x18036dac3  movdqu  [rsp+110h+var_D8+8], xmm0
0x18036dac9  mov     rax, [rsi+8]
0x18036dacd  test    rax, rax
0x18036dad0  jz      short loc_18036DADA
0x18036dad2  lock inc dword ptr [rax+8]
0x18036dad6  mov     rax, [rsi+8]
0x18036dada  mov     rcx, [rsi]
0x18036dadd  mov     qword ptr [rsp+110h+var_D8+8], rcx
0x18036dae2  mov     qword ptr [rsp+110h+var_C8], rax
0x18036dae7  lea     rax, [rsp+110h+var_D8+8]
0x18036daec  mov     qword ptr [rsp+110h+var_E8], rax
0x18036daf1  mov     [rbp+37h+var_5F], 0
0x18036daf5  mov     r8d, 1
0x18036dafb  lea     rdx, [rbp+37h+var_5F]
0x18036daff  mov     rcx, [rcx]
0x18036db02  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18036db08  movzx   r14d, [rbp+37h+var_5F]
0x18036db0d  mov     rbx, qword ptr [rsp+110h+var_C8]
0x18036db12  test    rbx, rbx
0x18036db15  jz      short loc_18036DB51
0x18036db17  mov     edi, 0FFFFFFFFh
0x18036db1c  mov     eax, edi
0x18036db1e  lock xadd [rbx+8], eax
0x18036db23  cmp     eax, 1
0x18036db26  jnz     short loc_18036DB51
0x18036db28  mov     rax, [rbx]
0x18036db2b  mov     rcx, rbx
0x18036db2e  mov     rax, [rax]
0x18036db31  call    cs:__guard_dispatch_icall_fptr
0x18036db37  lock xadd [rbx+0Ch], edi
0x18036db3c  cmp     edi, 1
0x18036db3f  jnz     short loc_18036DB51
0x18036db41  mov     rax, [rbx]
0x18036db44  mov     rcx, rbx
0x18036db47  mov     rax, [rax+8]
0x18036db4b  call    cs:__guard_dispatch_icall_fptr
0x18036db51  mov     rax, r14
0x18036db54  mov     [r15], rax
0x18036db57  mov     [r12], rax
0x18036db5b  mov     rcx, [r15]
0x18036db5e  xorps   xmm0, xmm0
0x18036db61  test    rcx, rcx
0x18036db64  js      short loc_18036DB70
0x18036db66  cvtsi2ss xmm0, rcx
0x18036db6b  jmp     loc_18036DA9E
0x18036db70  mov     rax, rcx
0x18036db73  shr     rax, 1
0x18036db76  and     ecx, 1
0x18036db79  or      rax, rcx
0x18036db7c  cvtsi2ss xmm0, rax
0x18036db81  addss   xmm0, xmm0
0x18036db85  jmp     loc_18036DA9E
0x18036db8a  sub     r8, rdx; jumptable 000000018036D9EB case 2
0x18036db8d  cmp     r8, 2
0x18036db91  jb      def_18036D9EB; jumptable 000000018036D9EB default case
0x18036db97  xorps   xmm0, xmm0
0x18036db9a  movdqu  [rsp+110h+var_C8+8], xmm0
0x18036dba0  mov     rax, [rsi+8]
0x18036dba4  test    rax, rax
0x18036dba7  jz      short loc_18036DBB1
0x18036dba9  lock inc dword ptr [rax+8]
0x18036dbad  mov     rax, [rsi+8]
0x18036dbb1  mov     rcx, [rsi]
0x18036dbb4  mov     qword ptr [rsp+110h+var_C8+8], rcx
0x18036dbb9  mov     [rsp+110h+var_B8], rax
0x18036dbbe  lea     rax, [rsp+110h+var_C8+8]
0x18036dbc3  mov     qword ptr [rsp+110h+var_E8], rax
0x18036dbc8  xor     eax, eax
0x18036dbca  mov     [rbp+37h+var_5C], ax
0x18036dbce  lea     r8d, [rax+2]
0x18036dbd2  lea     rdx, [rbp+37h+var_5C]
0x18036dbd6  mov     rcx, [rcx]
0x18036dbd9  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18036dbdf  movsx   r14, [rbp+37h+var_5C]
0x18036dbe4  mov     rbx, [rsp+110h+var_B8]
0x18036dbe9  test    rbx, rbx
0x18036dbec  jz      short loc_18036DC28
0x18036dbee  mov     edi, 0FFFFFFFFh
0x18036dbf3  mov     eax, edi
0x18036dbf5  lock xadd [rbx+8], eax
0x18036dbfa  cmp     eax, 1
0x18036dbfd  jnz     short loc_18036DC28
0x18036dbff  mov     rax, [rbx]
0x18036dc02  mov     rcx, rbx
0x18036dc05  mov     rax, [rax]
0x18036dc08  call    cs:__guard_dispatch_icall_fptr
0x18036dc0e  lock xadd [rbx+0Ch], edi
0x18036dc13  cmp     edi, 1
0x18036dc16  jnz     short loc_18036DC28
0x18036dc18  mov     rax, [rbx]
0x18036dc1b  mov     rcx, rbx
0x18036dc1e  mov     rax, [rax+8]
0x18036dc22  call    cs:__guard_dispatch_icall_fptr
0x18036dc28  movzx   eax, r14w
0x18036dc2c  mov     [r15], rax
0x18036dc2f  mov     [r12], r14
0x18036dc33  movd    xmm0, r14d
0x18036dc38  cvtdq2ps xmm0, xmm0
0x18036dc3b  movss   dword ptr [r13+0], xmm0
0x18036dc41  mov     rcx, rsi; void *
0x18036dc44  call    ??1?$shared_ptr@VDeviceVertexLayout@Engine@Spectre@@@std@@QEAA@XZ; std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(void)
0x18036dc49  mov     al, 2
0x18036dc4b  jmp     loc_18036E068
0x18036dc50  sub     r8, rdx; jumptable 000000018036D9EB case 5
0x18036dc53  cmp     r8, 2
0x18036dc57  jb      def_18036D9EB; jumptable 000000018036D9EB default case
0x18036dc5d  xorps   xmm0, xmm0
0x18036dc60  movdqu  [rbp+37h+var_B0], xmm0
0x18036dc65  mov     rax, [rsi+8]
0x18036dc69  test    rax, rax
0x18036dc6c  jz      short loc_18036DC76
0x18036dc6e  lock inc dword ptr [rax+8]
0x18036dc72  mov     rax, [rsi+8]
0x18036dc76  mov     rcx, [rsi]
0x18036dc79  mov     qword ptr [rbp+37h+var_B0], rcx
0x18036dc7d  mov     qword ptr [rbp+37h+var_B0+8], rax
0x18036dc81  lea     rax, [rbp+37h+var_B0]
0x18036dc85  mov     qword ptr [rsp+110h+var_E8], rax
0x18036dc8a  xor     eax, eax
0x18036dc8c  mov     [rbp+37h+var_58], ax
0x18036dc90  lea     r8d, [rax+2]
0x18036dc94  lea     rdx, [rbp+37h+var_58]
0x18036dc98  mov     rcx, [rcx]
0x18036dc9b  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18036dca1  movsx   r14, [rbp+37h+var_58]
0x18036dca6  mov     rbx, qword ptr [rbp+37h+var_B0+8]
0x18036dcaa  test    rbx, rbx
0x18036dcad  jz      short loc_18036DCE9
0x18036dcaf  mov     edi, 0FFFFFFFFh
0x18036dcb4  mov     eax, edi
0x18036dcb6  lock xadd [rbx+8], eax
0x18036dcbb  cmp     eax, 1
0x18036dcbe  jnz     short loc_18036DCE9
0x18036dcc0  mov     rax, [rbx]
0x18036dcc3  mov     rcx, rbx
0x18036dcc6  mov     rax, [rax]
0x18036dcc9  call    cs:__guard_dispatch_icall_fptr
0x18036dccf  lock xadd [rbx+0Ch], edi
0x18036dcd4  cmp     edi, 1
0x18036dcd7  jnz     short loc_18036DCE9
0x18036dcd9  mov     rax, [rbx]
0x18036dcdc  mov     rcx, rbx
0x18036dcdf  mov     rax, [rax+8]
0x18036dce3  call    cs:__guard_dispatch_icall_fptr
0x18036dce9  movzx   eax, r14w
0x18036dced  mov     [r15], rax
0x18036dcf0  mov     [r12], r14
0x18036dcf4  movd    xmm0, r14d
0x18036dcf9  cvtdq2ps xmm0, xmm0
0x18036dcfc  movss   dword ptr [r13+0], xmm0
0x18036dd02  mov     rcx, rsi; void *
0x18036dd05  call    ??1?$shared_ptr@VDeviceVertexLayout@Engine@Spectre@@@std@@QEAA@XZ; std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(void)
0x18036dd0a  mov     al, 2
0x18036dd0c  jmp     loc_18036E068
0x18036dd11  sub     r8, rdx; jumptable 000000018036D9EB case 3
0x18036dd14  cmp     r8, 4
0x18036dd18  jb      def_18036D9EB; jumptable 000000018036D9EB default case
0x18036dd1e  xorps   xmm0, xmm0
0x18036dd21  movdqu  [rbp+37h+var_A0], xmm0
0x18036dd26  mov     rax, [rsi+8]
0x18036dd2a  test    rax, rax
0x18036dd2d  jz      short loc_18036DD37
0x18036dd2f  lock inc dword ptr [rax+8]
0x18036dd33  mov     rax, [rsi+8]
0x18036dd37  mov     rcx, [rsi]
0x18036dd3a  mov     qword ptr [rbp+37h+var_A0], rcx
0x18036dd3e  mov     qword ptr [rbp+37h+var_A0+8], rax
0x18036dd42  lea     rax, [rbp+37h+var_A0]
0x18036dd46  mov     qword ptr [rsp+110h+var_E8], rax
0x18036dd4b  xor     eax, eax
0x18036dd4d  mov     [rbp+37h+var_54], eax
0x18036dd50  lea     r8d, [rax+4]
0x18036dd54  lea     rdx, [rbp+37h+var_54]
0x18036dd58  mov     rcx, [rcx]
0x18036dd5b  call    cs:__imp_?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z; std::istream::read(char *,__int64)
0x18036dd61  mov     ebx, [rbp+37h+var_54]
0x18036dd64  mov     r14, qword ptr [rbp+37h+var_A0+8]
0x18036dd68  test    r14, r14
0x18036dd6b  jz      short loc_18036DDA9
0x18036dd6d  mov     edi, 0FFFFFFFFh
0x18036dd72  mov     eax, edi
0x18036dd74  lock xadd [r14+8], eax
0x18036dd7a  cmp     eax, 1
0x18036dd7d  jnz     short loc_18036DDA9
0x18036dd7f  mov     rax, [r14]
0x18036dd82  mov     rcx, r14
0x18036dd85  mov     rax, [rax]
0x18036dd88  call    cs:__guard_dispatch_icall_fptr
0x18036dd8e  lock xadd [r14+0Ch], edi
0x18036dd94  cmp     edi, 1
0x18036dd97  jnz     short loc_18036DDA9
0x18036dd99  mov     rax, [r14]
0x18036dd9c  mov     rcx, r14
0x18036dd9f  mov     rax, [rax+8]
0x18036dda3  call    cs:__guard_dispatch_icall_fptr
0x18036dda9  mov     eax, ebx
0x18036ddab  shr     eax, 18h
0x18036ddae  cmp     [rbp+37h+arg_20], 0
0x18036ddb2  mov     dword ptr [rsp+110h+var_F0], ebx
0x18036ddb6  jz      short loc_18036DDD6
0x18036ddb8  mov     byte ptr [rsp+110h+var_F0], al
0x18036ddbc  mov     byte ptr [rsp+110h+var_F0+3], bl
0x18036ddc0  movzx   ecx, byte ptr [rsp+110h+var_F0+1]
0x18036ddc5  movzx   eax, byte ptr [rsp+110h+var_F0+2]
0x18036ddca  mov     byte ptr [rsp+110h+var_F0+1], al
0x18036ddce  mov     byte ptr [rsp+110h+var_F0+2], cl
0x18036ddd2  mov     ebx, dword ptr [rsp+110h+var_F0]
0x18036ddd6  mov     eax, ebx
0x18036ddd8  mov     [r15], rax
0x18036dddb  movsxd  rax, ebx
0x18036ddde  mov     [r12], rax
0x18036dde2  movss   xmm0, dword ptr [rsp+110h+var_F0]
0x18036dde8  movss   dword ptr [r13+0], xmm0
0x18036ddee  mov     rcx, rsi; void *
0x18036ddf1  call    ??1?$shared_ptr@VDeviceVertexLayout@Engine@Spectre@@@std@@QEAA@XZ; std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(void)
0x18036ddf6  mov     al, 4
0x18036ddf8  jmp     loc_18036E068
0x18036ddfd  sub     r8, rdx; jumptable 000000018036D9EB case 6
  ... truncated ...
```
