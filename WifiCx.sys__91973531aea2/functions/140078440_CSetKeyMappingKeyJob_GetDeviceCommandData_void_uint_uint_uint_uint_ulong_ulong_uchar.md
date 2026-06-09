# CSetKeyMappingKeyJob::GetDeviceCommandData(void *,uint,uint *,uint *,uint,ulong *,ulong *,uchar * *)

- ea: `0x140078440`
- end: `0x140078bad`
- name: `?GetDeviceCommandData@CSetKeyMappingKeyJob@@UEAAHPEAXIPEAI1IPEAK2PEAPEAE@Z`
- size: `1901`
- prototype: `__int64 __fastcall(CSetKeyMappingKeyJob *__hidden this, void *, unsigned int, unsigned int *, unsigned int *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x140009420`
- `0x14000c940`
- `0x140019c78`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140023ef4`
- `0x14002bd34`
- `0x14003ff68`
- `0x14004018c`
- `0x140073410`
- `0x1400742b4`
- `0x140074344`
- `0x140076c54`
- `0x140076e74`
- `0x140078440`

## pseudocode

```c
__int64 __fastcall CSetKeyMappingKeyJob::GetDeviceCommandData(
        CSetKeyMappingKeyJob *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int8 **a9)
{
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v9; // rdi
  unsigned __int8 *v12; // rbx
  int v14; // r8d
  int v15; // edx
  unsigned int v16; // eax
  unsigned int v17; // edi
  unsigned int v18; // r14d
  unsigned int v19; // r12d
  _QWORD *v20; // rax
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v21; // rcx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v24; // rcx
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v25; // rcx
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v26; // rcx
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v27; // rcx
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v28; // rcx
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v29; // rcx
  unsigned int WdiSetAddCipherKeysToIhv; // eax
  int v31; // r9d
  _DWORD *v32; // rax
  _DWORD *v33; // rdi
  _WORD *v34; // rcx
  unsigned int v35; // eax
  int v37; // [rsp+30h] [rbp-71h]
  __int64 v38; // [rsp+38h] [rbp-69h]
  unsigned int v39; // [rsp+38h] [rbp-69h]
  int v40; // [rsp+70h] [rbp-31h] BYREF
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v41; // [rsp+78h] [rbp-29h]
  char v42; // [rsp+80h] [rbp-21h]
  int v43; // [rsp+88h] [rbp-19h] BYREF
  void *v44; // [rsp+90h] [rbp-11h]
  char v45; // [rsp+98h] [rbp-9h]

  v9 = 0;
  v40 = 0;
  v41 = 0;
  v12 = a2;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      76,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  v14 = 1;
  *a4 = 0;
  *a5 = 0;
  v15 = *v12;
  if ( (_BYTE)v15 == 0x80 && v12[1] && *((_WORD *)v12 + 1) >= 0x10u )
  {
    v16 = *((_DWORD *)v12 + 1) + 12;
    *a5 = v16;
    if ( a3 < v16 )
    {
      v17 = -2147483643;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          1,
          78,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v16,
          a3);
      }
      goto LABEL_53;
    }
    v18 = *((_DWORD *)v12 + 1);
    if ( v18 < 0x14 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          1,
          82,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      goto LABEL_50;
    }
    v19 = *((unsigned __int16 *)v12 + 15) + 20;
    if ( v18 < v19 )
    {
      v17 = -1073676267;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          1,
          79,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      goto LABEL_53;
    }
    if ( v12[28] )
    {
      *a7 = 30;
      v43 = 1;
      v32 = operator new(0x24u);
      v33 = v32;
      if ( v32 )
        `vector constructor iterator'(
          v32,
          0x24u,
          1u,
          (void *(*)(void *))_WDI_SET_DELETE_CIPHER_KEYS_CONTAINER::_WDI_SET_DELETE_CIPHER_KEYS_CONTAINER);
      else
        v33 = 0;
      v44 = v33;
      v33[3] = 0;
      *((_DWORD *)v44 + 4) = CDot11ToWabiConverter::MapCipherAlgorithm(*((unsigned int *)v12 + 5));
      *((_DWORD *)v44 + 5) = CDot11ToWabiConverter::MapP2PScanType(*((unsigned int *)v12 + 6));
      *((_DWORD *)v44 + 7) = 1;
      *((_BYTE *)v44 + 24) = v12[29];
      v34 = v44;
      *((_DWORD *)v44 + 1) = *((_DWORD *)v12 + 3);
      v34[4] = *((_WORD *)v12 + 8);
      v35 = GenerateWdiSetDeleteCipherKeysToIhv(
              (unsigned int)&v43,
              a6,
              (unsigned int)*((_QWORD *)this + 67) + 5384,
              (_DWORD)a8,
              (__int64)a9);
      v17 = v35;
      if ( v35 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_53;
        v39 = v35;
        v31 = 81;
        v37 = *((_DWORD *)this + 4);
LABEL_39:
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          v14,
          v31,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          v37,
          v39);
        goto LABEL_53;
      }
      goto LABEL_46;
    }
    *((_BYTE *)this + 1112) = 1;
    *a7 = 29;
    v40 = 1;
    v20 = operator new(0x110u);
    if ( v20 )
    {
      v9 = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER *)(v20 + 1);
      *v20 = 1;
      `vector constructor iterator'(
        v20 + 1,
        0x108u,
        1u,
        (void *(*)(void *))_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER);
    }
    v41 = v9;
    *(_DWORD *)v9 |= 1u;
    v21 = v41;
    *((_DWORD *)v41 + 1) = *((_DWORD *)v12 + 3);
    *((_WORD *)v21 + 4) = *((_WORD *)v12 + 8);
    *((_DWORD *)v41 + 7) = 1;
    *((_DWORD *)v41 + 4) = CDot11ToWabiConverter::MapCipherAlgorithm(*((unsigned int *)v12 + 5));
    *((_DWORD *)v41 + 5) = CDot11ToWabiConverter::MapP2PScanType(*((unsigned int *)v12 + 6));
    *((_BYTE *)v41 + 24) = v12[29];
    *(_DWORD *)v41 &= ~2u;
    v22 = *(_DWORD *)v41 & 0xFFFFFFBF;
    *(_DWORD *)v41 = v22;
    v22 &= ~8u;
    *(_DWORD *)v41 = v22;
    v22 &= ~0x10u;
    *(_DWORD *)v41 = v22;
    v22 &= ~0x20u;
    *(_DWORD *)v41 = v22;
    v22 &= ~0x80u;
    *(_DWORD *)v41 = v22;
    v23 = v22 & 0xFFFFFEFF;
    *(_DWORD *)v41 = v23;
    v14 = *((_DWORD *)v12 + 5);
    if ( v14 != 1 )
    {
      if ( *((_DWORD *)v12 + 5) == 2 )
      {
        *(_DWORD *)v41 = v23 | 4;
        v29 = v41;
        *((_DWORD *)v41 + 8) = *((_DWORD *)v12 + 8);
        *((_WORD *)v29 + 18) = *((_WORD *)v12 + 18);
        *(_DWORD *)v41 |= 0x20u;
        *((_DWORD *)v41 + 22) = *((_DWORD *)v12 + 10);
        *((_QWORD *)v41 + 12) = v12 + 48;
        *((_DWORD *)v41 + 28) = *((_DWORD *)v12 + 11);
        *((_QWORD *)v41 + 15) = &v12[*((unsigned int *)v12 + 10) + 48];
        goto LABEL_36;
      }
      if ( *((_DWORD *)v12 + 5) == 4 )
      {
        *(_DWORD *)v41 = v23 | 4;
        v28 = v41;
        *((_DWORD *)v41 + 8) = *((_DWORD *)v12 + 8);
        *((_WORD *)v28 + 18) = *((_WORD *)v12 + 18);
        *(_DWORD *)v41 |= 8u;
        *((_DWORD *)v41 + 10) = *((unsigned __int16 *)v12 + 20);
        *((_QWORD *)v41 + 6) = v12 + 44;
        goto LABEL_36;
      }
      if ( *((_DWORD *)v12 + 5) != 5 )
      {
        switch ( *((_DWORD *)v12 + 5) )
        {
          case 6:
            *(_DWORD *)v41 = v23 | 4;
            v27 = v41;
            *((_DWORD *)v41 + 8) = *((_DWORD *)v12 + 8);
            *((_WORD *)v27 + 18) = *((_WORD *)v12 + 18);
            *(_DWORD *)v41 |= 0x40u;
            *((_DWORD *)v41 + 34) = *((unsigned __int16 *)v12 + 20);
            *((_QWORD *)v41 + 18) = v12 + 44;
            goto LABEL_36;
          case 8:
            *(_DWORD *)v41 = v23 | 4;
            v26 = v41;
            *((_DWORD *)v41 + 8) = *((_DWORD *)v12 + 8);
            *((_WORD *)v26 + 18) = *((_WORD *)v12 + 18);
            *(_DWORD *)v41 |= 0x10u;
            *((_DWORD *)v41 + 16) = *((unsigned __int16 *)v12 + 20);
            *((_QWORD *)v41 + 9) = v12 + 44;
            goto LABEL_36;
          case 9:
            *(_DWORD *)v41 = v23 | 4;
            v25 = v41;
            *((_DWORD *)v41 + 8) = *((_DWORD *)v12 + 8);
            *((_WORD *)v25 + 18) = *((_WORD *)v12 + 18);
            *(_DWORD *)v41 |= 0x200u;
            *((_DWORD *)v41 + 52) = *((unsigned __int16 *)v12 + 20);
            *((_QWORD *)v41 + 27) = v12 + 44;
            goto LABEL_36;
        }
        v15 = *((_DWORD *)v12 + 5) - 12;
        if ( *((_DWORD *)v12 + 5) == 12 )
        {
          *(_DWORD *)v41 = v23 | 4;
          v24 = v41;
          *((_DWORD *)v41 + 8) = *((_DWORD *)v12 + 8);
          *((_WORD *)v24 + 18) = *((_WORD *)v12 + 18);
          *(_DWORD *)v41 |= 0x400u;
          *((_DWORD *)v41 + 58) = *((unsigned __int16 *)v12 + 20);
          *((_QWORD *)v41 + 30) = v12 + 44;
          goto LABEL_36;
        }
        if ( *((_DWORD *)v12 + 5) != 257 )
        {
          if ( v14 <= -1 )
          {
            *(_DWORD *)v41 = v23 | 0x100;
            *((_DWORD *)v41 + 46) = *((unsigned __int16 *)v12 + 15);
            *((_QWORD *)v41 + 24) = v12 + 32;
            goto LABEL_36;
          }
LABEL_50:
          v17 = -1073676267;
          goto LABEL_53;
        }
      }
    }
    *(_DWORD *)v41 = v23 | 0x80;
    *((_DWORD *)v41 + 40) = *((unsigned __int16 *)v12 + 15);
    *((_QWORD *)v41 + 21) = v12 + 32;
LABEL_36:
    WdiSetAddCipherKeysToIhv = GenerateWdiSetAddCipherKeysToIhv(
                                 (unsigned int)&v40,
                                 a6,
                                 (unsigned int)*((_QWORD *)this + 67) + 5384,
                                 (_DWORD)a8,
                                 (__int64)a9);
    v17 = WdiSetAddCipherKeysToIhv;
    if ( WdiSetAddCipherKeysToIhv )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_53;
      v31 = 80;
      v39 = WdiSetAddCipherKeysToIhv;
      v37 = *((_DWORD *)this + 4);
      goto LABEL_39;
    }
LABEL_46:
    *a4 = *a5;
    if ( v18 != v19 )
      v17 = -1073676267;
    goto LABEL_53;
  }
  v17 = -1073676267;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_qDdddddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      1,
      77,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      128,
      1,
      16,
      *v12,
      v12[1],
      *((_WORD *)v12 + 1));
  }
LABEL_53:
  if ( v41 )
    _WDI_SET_ADD_CIPHER_KEYS_CONTAINER::`vector deleting destructor'(v41, 3u);
  if ( v44 )
    operator delete(v44);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v15) = 5;
    LODWORD(v38) = v17;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      v14,
      83,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v38);
  }
  ArrayOfElements<_WDI_PHY_STATISTICS_PARAMETERS>::Cleanup(&v43);
  ArrayOfElements<_WDI_SET_ADD_CIPHER_KEYS_CONTAINER>::Cleanup(&v40);
  return v17;
}

```

## disassembly

```asm
0x140078440  push    rbp
0x140078442  push    rbx
0x140078443  push    rsi
0x140078444  push    rdi
0x140078445  push    r12
0x140078447  push    r13
0x140078449  push    r14
0x14007844b  push    r15
0x14007844d  lea     rbp, [rsp-7]
0x140078452  sub     rsp, 0A8h
0x140078459  xor     edi, edi
0x14007845b  mov     r13, r9
0x14007845e  mov     [rbp+3Fh+var_70], edi
0x140078461  mov     r14d, r8d
0x140078464  mov     [rbp+3Fh+var_68], rdi
0x140078468  mov     rbx, rdx
0x14007846b  mov     [rbp+3Fh+var_60], dil
0x14007846f  mov     rsi, rcx
0x140078472  mov     [rbp+3Fh+var_58], edi
0x140078475  mov     [rbp+3Fh+var_50], rdi
0x140078479  mov     [rbp+3Fh+var_48], dil
0x14007847d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140078484  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14007848b  lea     r10, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140078492  jz      short loc_1400784D7
0x140078494  mov     rcx, cs:WPP_GLOBAL_Control
0x14007849b  cmp     byte ptr [rcx+29h], 5
0x14007849f  jnb     short loc_1400784A7
0x1400784a1  cmp     [rcx+48h], di
0x1400784a5  jz      short loc_1400784D0
0x1400784a7  mov     eax, [rsi+10h]
0x1400784aa  mov     r9d, 4Ch ; 'L'
0x1400784b0  mov     rcx, [rcx+40h]
0x1400784b4  mov     dl, 5
0x1400784b6  mov     [rsp+0E0h+var_B0], eax
0x1400784ba  mov     [rsp+0E0h+var_B8], rsi
0x1400784bf  mov     [rsp+0E0h+var_C0], r10
0x1400784c4  call    WPP_RECORDER_SF_qD
0x1400784c9  lea     r10, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x1400784d0  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400784d7  mov     r15, [rbp+3Fh+arg_20]
0x1400784db  mov     r8d, 1
0x1400784e1  mov     [r13+0], edi
0x1400784e5  mov     [r15], edi
0x1400784e8  lea     r11d, [r8+0Fh]
0x1400784ec  movzx   edx, byte ptr [rbx]
0x1400784ef  cmp     dl, 80h
0x1400784f2  jnz     loc_140078AB6
0x1400784f8  cmp     [rbx+1], r8b
0x1400784fc  jb      loc_140078AB6
0x140078502  cmp     [rbx+2], r11w
0x140078507  jb      loc_140078AB6
0x14007850d  mov     eax, [rbx+4]
0x140078510  add     eax, 0Ch
0x140078513  mov     [r15], eax
0x140078516  cmp     r14d, eax
0x140078519  jnb     short loc_140078562
0x14007851b  mov     edi, 80000005h
0x140078520  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140078527  jz      loc_140078B13
0x14007852d  mov     rcx, cs:WPP_GLOBAL_Control
0x140078534  lea     r9d, [r8+4Dh]
0x140078538  mov     [rsp+0E0h+var_A0], r14d
0x14007853d  mov     dl, 2
0x14007853f  mov     dword ptr [rsp+0E0h+var_A8], eax
0x140078543  mov     eax, [rsi+10h]
0x140078546  mov     rcx, [rcx+40h]
0x14007854a  mov     [rsp+0E0h+var_B0], eax
0x14007854e  mov     [rsp+0E0h+var_B8], rsi
0x140078553  mov     [rsp+0E0h+var_C0], r10
0x140078558  call    WPP_RECORDER_SF_qDdd
0x14007855d  jmp     loc_140078B13
0x140078562  mov     r14d, [rbx+4]
0x140078566  cmp     r14d, 14h
0x14007856a  jb      loc_140078A7D
0x140078570  movzx   r12d, word ptr [rbx+1Eh]
0x140078575  add     r12d, 14h
0x140078579  cmp     r14d, r12d
0x14007857c  jnb     short loc_1400785BE
0x14007857e  mov     edi, 0C0010015h
0x140078583  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14007858a  jz      loc_140078B13
0x140078590  mov     rcx, cs:WPP_GLOBAL_Control
0x140078597  mov     r9d, 4Fh ; 'O'
0x14007859d  mov     eax, [rsi+10h]
0x1400785a0  mov     dl, 2
0x1400785a2  mov     [rsp+0E0h+var_B0], eax
0x1400785a6  mov     [rsp+0E0h+var_B8], rsi
0x1400785ab  mov     rcx, [rcx+40h]
0x1400785af  mov     [rsp+0E0h+var_C0], r10
0x1400785b4  call    WPP_RECORDER_SF_qD
0x1400785b9  jmp     loc_140078B13
0x1400785be  mov     rax, [rbp+3Fh+arg_30]
0x1400785c2  cmp     [rbx+1Ch], dil
0x1400785c6  jnz     loc_140078977
0x1400785cc  mov     [rsi+458h], r8b
0x1400785d3  mov     ecx, 110h; unsigned __int64
0x1400785d8  mov     dword ptr [rax], 1Dh
0x1400785de  mov     [rbp+3Fh+var_70], r8d
0x1400785e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400785e7  test    rax, rax
0x1400785ea  jz      short loc_14007860F
0x1400785ec  mov     ecx, 1
0x1400785f1  lea     rdi, [rax+8]
0x1400785f5  mov     [rax], rcx
0x1400785f8  lea     r9, ??0_WDI_SET_ADD_CIPHER_KEYS_CONTAINER@@QEAA@XZ; void *(*)(void *)
0x1400785ff  mov     r8d, ecx; unsigned __int64
0x140078602  mov     edx, 108h; unsigned __int64
0x140078607  mov     rcx, rdi; void *
0x14007860a  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14007860f  mov     [rbp+3Fh+var_68], rdi
0x140078613  or      dword ptr [rdi], 1
0x140078616  mov     rcx, [rbp+3Fh+var_68]
0x14007861a  mov     eax, [rbx+0Ch]
0x14007861d  mov     [rcx+4], eax
0x140078620  movzx   eax, word ptr [rbx+10h]
0x140078624  mov     [rcx+8], ax
0x140078628  mov     rax, [rbp+3Fh+var_68]
0x14007862c  mov     dword ptr [rax+1Ch], 1
0x140078633  mov     ecx, [rbx+14h]
0x140078636  call    ?MapCipherAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_CIPHER_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@@Z; CDot11ToWabiConverter::MapCipherAlgorithm(_DOT11_CIPHER_ALGORITHM)
0x14007863b  mov     r9d, eax
0x14007863e  mov     rax, [rbp+3Fh+var_68]
0x140078642  mov     [rax+10h], r9d
0x140078646  mov     ecx, [rbx+18h]
0x140078649  call    ?MapP2PScanType@CDot11ToWabiConverter@@SA?AW4_WDI_P2P_SCAN_TYPE@@W4_DOT11_WFD_SCAN_TYPE@@@Z; CDot11ToWabiConverter::MapP2PScanType(_DOT11_WFD_SCAN_TYPE)
0x14007864e  mov     edx, eax
0x140078650  mov     rax, [rbp+3Fh+var_68]
0x140078654  mov     [rax+14h], edx
0x140078657  mov     rax, [rbp+3Fh+var_68]
0x14007865b  mov     cl, [rbx+1Dh]
0x14007865e  mov     [rax+18h], cl
0x140078661  mov     rax, [rbp+3Fh+var_68]
0x140078665  and     dword ptr [rax], 0FFFFFFFDh
0x140078668  mov     rax, [rbp+3Fh+var_68]
0x14007866c  mov     ecx, [rax]
0x14007866e  and     ecx, 0FFFFFFBFh
0x140078671  mov     [rax], ecx
0x140078673  and     ecx, 0FFFFFFF7h
0x140078676  mov     rax, [rbp+3Fh+var_68]
0x14007867a  mov     [rax], ecx
0x14007867c  and     ecx, 0FFFFFFEFh
0x14007867f  mov     rax, [rbp+3Fh+var_68]
0x140078683  mov     [rax], ecx
0x140078685  and     ecx, 0FFFFFFDFh
0x140078688  mov     rax, [rbp+3Fh+var_68]
0x14007868c  mov     [rax], ecx
0x14007868e  btr     ecx, 7
0x140078692  mov     rax, [rbp+3Fh+var_68]
0x140078696  mov     [rax], ecx
0x140078698  btr     ecx, 8
0x14007869c  mov     rax, [rbp+3Fh+var_68]
0x1400786a0  mov     [rax], ecx
0x1400786a2  mov     r8d, [rbx+14h]
0x1400786a6  mov     edx, r8d
0x1400786a9  sub     edx, 1
0x1400786ac  jz      loc_1400788CC
0x1400786b2  sub     edx, 1
0x1400786b5  jz      loc_140078876
0x1400786bb  sub     edx, 2
0x1400786be  jz      loc_14007883B
0x1400786c4  sub     edx, 1
0x1400786c7  jz      loc_1400788CC
0x1400786cd  sub     edx, 1
0x1400786d0  jz      loc_1400787F7
0x1400786d6  sub     edx, 2
0x1400786d9  jz      loc_1400787B9
0x1400786df  sub     edx, 1
0x1400786e2  jz      loc_140078774
0x1400786e8  sub     edx, 3
0x1400786eb  jz      short loc_14007872F
0x1400786ed  cmp     edx, 0F5h
0x1400786f3  jz      loc_1400788CC
0x1400786f9  cmp     r8d, 0FFFFFFFFh
0x1400786fd  jg      loc_140078AAF
0x140078703  mov     rax, [rbp+3Fh+var_68]
0x140078707  bts     ecx, 8
0x14007870b  mov     [rax], ecx
0x14007870d  mov     rax, [rbp+3Fh+var_68]
0x140078711  movzx   ecx, word ptr [rbx+1Eh]
0x140078715  mov     [rax+0B8h], ecx
0x14007871b  lea     rcx, [rbx+20h]
0x14007871f  mov     rax, [rbp+3Fh+var_68]
0x140078723  mov     [rax+0C0h], rcx
0x14007872a  jmp     loc_1400788F3
0x14007872f  mov     rax, [rbp+3Fh+var_68]
0x140078733  or      ecx, 4
0x140078736  mov     [rax], ecx
0x140078738  mov     rcx, [rbp+3Fh+var_68]
0x14007873c  mov     eax, [rbx+20h]
0x14007873f  mov     [rcx+20h], eax
0x140078742  movzx   eax, word ptr [rbx+24h]
0x140078746  mov     [rcx+24h], ax
0x14007874a  mov     rax, [rbp+3Fh+var_68]
0x14007874e  bts     dword ptr [rax], 0Ah
0x140078752  mov     rax, [rbp+3Fh+var_68]
0x140078756  movzx   ecx, word ptr [rbx+28h]
0x14007875a  mov     [rax+0E8h], ecx
0x140078760  lea     rcx, [rbx+2Ch]
0x140078764  mov     rax, [rbp+3Fh+var_68]
0x140078768  mov     [rax+0F0h], rcx
0x14007876f  jmp     loc_1400788F3
0x140078774  mov     rax, [rbp+3Fh+var_68]
0x140078778  or      ecx, 4
0x14007877b  mov     [rax], ecx
0x14007877d  mov     rcx, [rbp+3Fh+var_68]
0x140078781  mov     eax, [rbx+20h]
0x140078784  mov     [rcx+20h], eax
0x140078787  movzx   eax, word ptr [rbx+24h]
0x14007878b  mov     [rcx+24h], ax
0x14007878f  mov     rax, [rbp+3Fh+var_68]
0x140078793  bts     dword ptr [rax], 9
0x140078797  mov     rax, [rbp+3Fh+var_68]
0x14007879b  movzx   ecx, word ptr [rbx+28h]
0x14007879f  mov     [rax+0D0h], ecx
0x1400787a5  lea     rcx, [rbx+2Ch]
0x1400787a9  mov     rax, [rbp+3Fh+var_68]
0x1400787ad  mov     [rax+0D8h], rcx
0x1400787b4  jmp     loc_1400788F3
0x1400787b9  mov     rax, [rbp+3Fh+var_68]
0x1400787bd  or      ecx, 4
0x1400787c0  mov     [rax], ecx
0x1400787c2  mov     rcx, [rbp+3Fh+var_68]
0x1400787c6  mov     eax, [rbx+20h]
0x1400787c9  mov     [rcx+20h], eax
0x1400787cc  movzx   eax, word ptr [rbx+24h]
0x1400787d0  mov     [rcx+24h], ax
0x1400787d4  mov     rax, [rbp+3Fh+var_68]
0x1400787d8  or      dword ptr [rax], 10h
0x1400787db  mov     rax, [rbp+3Fh+var_68]
0x1400787df  movzx   ecx, word ptr [rbx+28h]
0x1400787e3  mov     [rax+40h], ecx
0x1400787e6  lea     rcx, [rbx+2Ch]
0x1400787ea  mov     rax, [rbp+3Fh+var_68]
0x1400787ee  mov     [rax+48h], rcx
0x1400787f2  jmp     loc_1400788F3
0x1400787f7  mov     rax, [rbp+3Fh+var_68]
0x1400787fb  or      ecx, 4
0x1400787fe  mov     [rax], ecx
0x140078800  mov     rcx, [rbp+3Fh+var_68]
0x140078804  mov     eax, [rbx+20h]
0x140078807  mov     [rcx+20h], eax
0x14007880a  movzx   eax, word ptr [rbx+24h]
0x14007880e  mov     [rcx+24h], ax
0x140078812  mov     rax, [rbp+3Fh+var_68]
0x140078816  or      dword ptr [rax], 40h
0x140078819  mov     rax, [rbp+3Fh+var_68]
0x14007881d  movzx   ecx, word ptr [rbx+28h]
0x140078821  mov     [rax+88h], ecx
0x140078827  lea     rcx, [rbx+2Ch]
0x14007882b  mov     rax, [rbp+3Fh+var_68]
0x14007882f  mov     [rax+90h], rcx
0x140078836  jmp     loc_1400788F3
0x14007883b  mov     rax, [rbp+3Fh+var_68]
0x14007883f  or      ecx, 4
0x140078842  mov     [rax], ecx
0x140078844  mov     rcx, [rbp+3Fh+var_68]
0x140078848  mov     eax, [rbx+20h]
0x14007884b  mov     [rcx+20h], eax
0x14007884e  movzx   eax, word ptr [rbx+24h]
0x140078852  mov     [rcx+24h], ax
0x140078856  mov     rax, [rbp+3Fh+var_68]
0x14007885a  or      dword ptr [rax], 8
0x14007885d  mov     rax, [rbp+3Fh+var_68]
0x140078861  movzx   ecx, word ptr [rbx+28h]
0x140078865  mov     [rax+28h], ecx
0x140078868  lea     rcx, [rbx+2Ch]
0x14007886c  mov     rax, [rbp+3Fh+var_68]
0x140078870  mov     [rax+30h], rcx
0x140078874  jmp     short loc_1400788F3
0x140078876  mov     rax, [rbp+3Fh+var_68]
0x14007887a  or      ecx, 4
0x14007887d  mov     [rax], ecx
0x14007887f  mov     rcx, [rbp+3Fh+var_68]
0x140078883  mov     eax, [rbx+20h]
0x140078886  mov     [rcx+20h], eax
0x140078889  movzx   eax, word ptr [rbx+24h]
0x14007888d  mov     [rcx+24h], ax
0x140078891  mov     rax, [rbp+3Fh+var_68]
0x140078895  or      dword ptr [rax], 20h
0x140078898  mov     rax, [rbp+3Fh+var_68]
0x14007889c  mov     ecx, [rbx+28h]
0x14007889f  mov     [rax+58h], ecx
0x1400788a2  lea     rcx, [rbx+30h]
0x1400788a6  mov     rax, [rbp+3Fh+var_68]
0x1400788aa  mov     [rax+60h], rcx
0x1400788ae  mov     rax, [rbp+3Fh+var_68]
0x1400788b2  mov     ecx, [rbx+2Ch]
0x1400788b5  mov     [rax+70h], ecx
0x1400788b8  mov     ecx, [rbx+28h]
0x1400788bb  mov     rax, [rbp+3Fh+var_68]
0x1400788bf  add     rcx, 30h ; '0'
0x1400788c3  add     rcx, rbx
0x1400788c6  mov     [rax+78h], rcx
0x1400788ca  jmp     short loc_1400788F3
0x1400788cc  mov     rax, [rbp+3Fh+var_68]
0x1400788d0  bts     ecx, 7
0x1400788d4  mov     [rax], ecx
0x1400788d6  mov     rax, [rbp+3Fh+var_68]
0x1400788da  movzx   ecx, word ptr [rbx+1Eh]
  ... truncated ...
```
