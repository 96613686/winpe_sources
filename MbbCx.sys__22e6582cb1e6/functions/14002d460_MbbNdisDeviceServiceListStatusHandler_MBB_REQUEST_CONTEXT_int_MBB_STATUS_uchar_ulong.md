# MbbNdisDeviceServiceListStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x14002d460`
- end: `0x14002da9a`
- name: `?MbbNdisDeviceServiceListStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `1594`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callees

- `0x140001db8`
- `0x140001f90`
- `0x1400051ac`
- `0x140005644`
- `0x1400187d8`
- `0x14002d460`
- `0x14003df70`
- `0x14003f7e4`
- `0x140048040`
- `0x140048340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002d61c`
- `ntoskrnl!ExAllocatePool2` at `0x14002d7ca`
- `ntoskrnl!ExAllocatePool2` at `0x14002d61c`
- `ntoskrnl!ExAllocatePool2` at `0x14002d7ca`

## pseudocode

```c
__int64 __fastcall MbbNdisDeviceServiceListStatusHandler(
        __int64 a1,
        unsigned int a2,
        char a3,
        unsigned int *a4,
        unsigned int a5)
{
  unsigned int IsVariableFieldValid; // ebx
  int v9; // edx
  __int64 v10; // r15
  __int64 v11; // rbp
  unsigned int v12; // eax
  unsigned int v13; // ecx
  char v14; // si
  _DWORD *Pool2; // rax
  int v16; // edx
  void *v17; // r13
  unsigned int v18; // eax
  int v19; // r9d
  __int64 v20; // rdx
  __int64 v21; // r13
  unsigned int v22; // r8d
  __int64 v23; // rax
  unsigned __int64 v24; // rcx
  unsigned int v25; // r8d
  __int64 v26; // rsi
  unsigned int v27; // eax
  unsigned int v28; // eax
  void *v29; // rax
  int v30; // r9d
  int v31; // r9d
  char v33; // [rsp+30h] [rbp-58h]
  char v34; // [rsp+30h] [rbp-58h]
  int v35; // [rsp+38h] [rbp-50h]
  int v36; // [rsp+38h] [rbp-50h]
  _DWORD *v37; // [rsp+90h] [rbp+8h]
  char v38; // [rsp+98h] [rbp+10h]
  __int64 v39; // [rsp+A8h] [rbp+20h]

  IsVariableFieldValid = a2;
  if ( *(_QWORD *)(a1 + 424) || *(_BYTE *)(a1 + 576) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        172,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16));
    }
    return 65539;
  }
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v33 = a2;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        173,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v33);
    }
    return IsVariableFieldValid;
  }
  if ( (unsigned int)MbbUtilMbbToWwanStatus(a3) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        174,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a3);
    }
    return (unsigned int)-1073676267;
  }
  if ( !a4 || a5 < 8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        175,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a5,
        8);
    }
    return (unsigned int)-1073676267;
  }
  v10 = *a4;
  v11 = **(_QWORD **)(a1 + 48);
  if ( !(_DWORD)v10 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        176,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16));
    }
    *(_QWORD *)(v11 + 1112) = 0;
    IsVariableFieldValid = -1073741637;
    *(_DWORD *)(v11 + 1104) = 0;
    *(_DWORD *)(v11 + 1120) = 0;
    goto LABEL_57;
  }
  v12 = 32 * v10;
  if ( (unsigned __int64)(32 * v10) > 0xFFFFFFFF )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_56;
    v36 = 32;
    v31 = 177;
    v34 = *a4;
    goto LABEL_55;
  }
  v13 = v12 + 8;
  if ( v12 + 8 < v12 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_56;
    v36 = 8;
    v31 = 178;
    v34 = -1;
LABEL_55:
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_Ddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      3,
      v31,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v34,
      v36);
    goto LABEL_56;
  }
  if ( a5 < v13 || (v14 = 40 * v10, (unsigned __int64)(40 * v10) > 0xFFFFFFFF) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Dddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        3,
        179,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a5,
        v13,
        v10);
    goto LABEL_56;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(64, 40 * v10, 1683505741);
  v37 = Pool2;
  v17 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_24:
      IsVariableFieldValid = -1073741670;
      goto LABEL_57;
    }
    v35 = v10;
    LOBYTE(v18) = 40 * v10;
    v19 = 180;
LABEL_23:
    LOBYTE(v16) = 2;
    WPP_RECORDER_SF_Ddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      3,
      v19,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      v18,
      v35);
    goto LABEL_24;
  }
  memset(Pool2, 0, 40 * v10);
  *(_QWORD *)(v11 + 1112) = v17;
  v21 = 0;
  *(_DWORD *)(v11 + 1104) = 0;
  *(_DWORD *)(v11 + 1120) = a4[1];
  while ( 1 )
  {
    v22 = a4[2 * v21 + 3];
    if ( v22 < 0x1C )
    {
      IsVariableFieldValid = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_57;
      v30 = 181;
      goto LABEL_48;
    }
    IsVariableFieldValid = MbbIsVariableFieldValid(a5, a4[2 * v21 + 2], v22, 0x200u, 4u, 1);
    if ( IsVariableFieldValid )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_57;
      v30 = 182;
LABEL_48:
      LOBYTE(v20) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v20,
        3,
        v30,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        v21);
      goto LABEL_57;
    }
    v23 = a4[2 * v21 + 2];
    v24 = 4LL * *(unsigned int *)((char *)a4 + v23 + 24);
    if ( v24 > 0xFFFFFFFF )
      goto LABEL_41;
    v25 = v24 + 28;
    if ( (int)v24 + 28 < (unsigned int)v24 )
      goto LABEL_41;
    v26 = (unsigned int)v23;
    v27 = v25 + v23;
    v38 = v27;
    if ( v27 < v25 )
    {
      v14 = -1;
      goto LABEL_41;
    }
    if ( a5 < v27 )
      break;
    v20 = 5 * v21;
    v39 = v20;
    v37[2 * v20] = _byteswap_ulong(*(unsigned int *)((char *)a4 + v26));
    LOWORD(v37[2 * v20 + 1]) = __ROR2__(*(_WORD *)((char *)a4 + v26 + 4), 8);
    HIWORD(v37[2 * v20 + 1]) = __ROR2__(*(_WORD *)((char *)a4 + v26 + 6), 8);
    *(_QWORD *)&v37[2 * v20 + 2] = *(_QWORD *)((char *)a4 + v26 + 8);
    v37[2 * v20 + 4] = *(unsigned int *)((char *)a4 + v26 + 16);
    v37[2 * v20 + 5] = *(unsigned int *)((char *)a4 + v26 + 20);
    v28 = *(unsigned int *)((char *)a4 + v26 + 24);
    if ( v28 )
    {
      v29 = (void *)ExAllocatePool2(IsVariableFieldValid + 64, 4LL * v28, 1683505741);
      v16 = v39;
      *(_QWORD *)&v37[2 * v39 + 8] = v29;
      if ( !v29 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_24;
        v19 = 184;
        v18 = 4 * *(unsigned int *)((char *)a4 + v26 + 24);
        v35 = v21;
        goto LABEL_23;
      }
      v37[2 * v39 + 6] = *(unsigned int *)((char *)a4 + v26 + 24);
      memmove(v29, (char *)a4 + v26 + 28, 4LL * *(unsigned int *)((char *)a4 + v26 + 24));
    }
    ++*(_DWORD *)(v11 + 1104);
    v21 = (unsigned int)(v21 + 1);
    v14 = v38;
    if ( (unsigned int)v21 >= (unsigned int)v10 )
      return IsVariableFieldValid;
  }
  v14 = v27;
LABEL_41:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Dddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      3,
      183,
      (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      *(_DWORD *)(a1 + 16),
      a5,
      v14,
      v21);
LABEL_56:
  IsVariableFieldValid = -1073676267;
LABEL_57:
  if ( v11 )
    FreeDeviceServiceState((struct _MBB_DS_STATE *)(v11 + 1104));
  return IsVariableFieldValid;
}

```

## disassembly

```asm
0x14002d460  mov     [rsp+arg_10], rbx
0x14002d465  push    rbp
0x14002d466  push    rsi
0x14002d467  push    rdi
0x14002d468  push    r12
0x14002d46a  push    r13
0x14002d46c  push    r14
0x14002d46e  push    r15
0x14002d470  sub     rsp, 50h
0x14002d474  cmp     qword ptr [rcx+1A8h], 0
0x14002d47c  mov     r14, r9
0x14002d47f  mov     esi, r8d
0x14002d482  mov     ebx, edx
0x14002d484  mov     rdi, rcx
0x14002d487  jnz     loc_14002DA39
0x14002d48d  cmp     byte ptr [rcx+240h], 0
0x14002d494  jnz     loc_14002DA39
0x14002d49a  test    edx, edx
0x14002d49c  jz      short loc_14002D4EC
0x14002d49e  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d4a5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d4ac  jz      loc_14002DA7F
0x14002d4b2  mov     eax, [rcx+10h]
0x14002d4b5  mov     r9d, 0ADh
0x14002d4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d4c2  mov     r8d, 3
0x14002d4c8  mov     dword ptr [rsp+88h+var_58], edx
0x14002d4cc  mov     dl, 2
0x14002d4ce  mov     [rsp+88h+var_60], eax
0x14002d4d2  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002d4d9  mov     qword ptr [rsp+88h+var_68], rax
0x14002d4de  mov     rcx, [rcx+40h]
0x14002d4e2  call    WPP_RECORDER_SF_DD
0x14002d4e7  jmp     loc_14002DA7F
0x14002d4ec  mov     ecx, esi
0x14002d4ee  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x14002d4f3  test    eax, eax
0x14002d4f5  jz      short loc_14002D546
0x14002d4f7  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d4fe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d505  jz      short loc_14002D53C
0x14002d507  mov     eax, [rdi+10h]
0x14002d50a  mov     r9d, 0AEh
0x14002d510  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d517  mov     r8d, 3
0x14002d51d  mov     dword ptr [rsp+88h+var_58], esi
0x14002d521  mov     dl, 2
0x14002d523  mov     [rsp+88h+var_60], eax
0x14002d527  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002d52e  mov     qword ptr [rsp+88h+var_68], rax
0x14002d533  mov     rcx, [rcx+40h]
0x14002d537  call    WPP_RECORDER_SF_DD
0x14002d53c  mov     ebx, 0C0010015h
0x14002d541  jmp     loc_14002DA7F
0x14002d546  mov     r12d, [rsp+88h+arg_20]
0x14002d54e  mov     r8d, 8
0x14002d554  test    r14, r14
0x14002d557  jz      loc_14002D9E5
0x14002d55d  cmp     r12d, r8d
0x14002d560  jb      loc_14002D9E5
0x14002d566  mov     rax, [rdi+30h]
0x14002d56a  xor     esi, esi
0x14002d56c  mov     r15d, [r14]
0x14002d56f  mov     rbp, [rax]
0x14002d572  test    r15d, r15d
0x14002d575  jnz     short loc_14002D5D3
0x14002d577  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d57e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d585  jz      short loc_14002D5B6
0x14002d587  mov     eax, [rdi+10h]
0x14002d58a  lea     r8d, [rsi+3]
0x14002d58e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d595  mov     r9d, 0B0h
0x14002d59b  mov     [rsp+88h+var_60], eax
0x14002d59f  mov     dl, 2
0x14002d5a1  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002d5a8  mov     qword ptr [rsp+88h+var_68], rax
0x14002d5ad  mov     rcx, [rcx+40h]
0x14002d5b1  call    WPP_RECORDER_SF_d
0x14002d5b6  mov     [rbp+458h], rsi
0x14002d5bd  mov     ebx, 0C00000BBh
0x14002d5c2  mov     [rbp+450h], esi
0x14002d5c8  mov     [rbp+460h], esi
0x14002d5ce  jmp     loc_14002D9CB
0x14002d5d3  mov     rax, r15
0x14002d5d6  mov     r9d, 0FFFFFFFFh
0x14002d5dc  shl     rax, 5
0x14002d5e0  cmp     rax, r9
0x14002d5e3  ja      loc_14002D978
0x14002d5e9  lea     ecx, [rax+8]
0x14002d5ec  cmp     ecx, eax
0x14002d5ee  jb      loc_14002D953
0x14002d5f4  cmp     r12d, ecx
0x14002d5f7  jb      loc_14002D92B
0x14002d5fd  lea     rsi, [r15+r15*4]
0x14002d601  shl     rsi, 3
0x14002d605  cmp     rsi, r9
0x14002d608  ja      loc_14002D92B
0x14002d60e  mov     r8d, 6458424Dh
0x14002d614  mov     rdx, rsi
0x14002d617  mov     ecx, 40h ; '@'
0x14002d61c  call    cs:__imp_ExAllocatePool2
0x14002d623  nop     dword ptr [rax+rax+00h]
0x14002d628  mov     [rsp+88h+arg_0], rax
0x14002d630  mov     r13, rax
0x14002d633  test    rax, rax
0x14002d636  jnz     short loc_14002D693
0x14002d638  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d63f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d646  jz      short loc_14002D689
0x14002d648  lea     eax, [r15+r15*4]
0x14002d64c  mov     dword ptr [rsp+88h+var_50], r15d
0x14002d651  shl     eax, 3
0x14002d654  mov     r9d, 0B4h
0x14002d65a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d661  mov     r8d, 3
0x14002d667  mov     dword ptr [rsp+88h+var_58], eax
0x14002d66b  mov     dl, 2
0x14002d66d  mov     eax, [rdi+10h]
0x14002d670  mov     [rsp+88h+var_60], eax
0x14002d674  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002d67b  mov     rcx, [rcx+40h]
0x14002d67f  mov     qword ptr [rsp+88h+var_68], rax
0x14002d684  call    WPP_RECORDER_SF_Ddd
0x14002d689  mov     ebx, 0C000009Ah
0x14002d68e  jmp     loc_14002D9CB
0x14002d693  mov     r8, rsi; Size
0x14002d696  xor     edx, edx; Val
0x14002d698  mov     rcx, r13; void *
0x14002d69b  call    memset
0x14002d6a0  mov     [rbp+458h], r13
0x14002d6a7  xor     r13d, r13d
0x14002d6aa  mov     dword ptr [rbp+450h], 0
0x14002d6b4  mov     eax, [r14+4]
0x14002d6b8  mov     [rbp+460h], eax
0x14002d6be  test    r15d, r15d
0x14002d6c1  jz      loc_14002DA7F
0x14002d6c7  mov     r8d, [r14+r13*8+0Ch]; unsigned int
0x14002d6cc  cmp     r8d, 1Ch
0x14002d6d0  jb      loc_14002D8D7
0x14002d6d6  mov     edx, [r14+r13*8+8]; unsigned int
0x14002d6db  mov     r9d, 200h; unsigned int
0x14002d6e1  mov     [rsp+88h+var_60], 1; int
0x14002d6e9  mov     ecx, r12d; unsigned int
0x14002d6ec  mov     [rsp+88h+var_68], 4; unsigned int
0x14002d6f4  call    ?MbbIsVariableFieldValid@@YAJKKKKKH@Z; MbbIsVariableFieldValid(ulong,ulong,ulong,ulong,ulong,int)
0x14002d6f9  mov     ebx, eax
0x14002d6fb  test    eax, eax
0x14002d6fd  jnz     loc_14002D8BB
0x14002d703  mov     eax, [r14+r13*8+8]
0x14002d708  mov     r9d, 0FFFFFFFFh
0x14002d70e  mov     [rsp+88h+arg_18], rax
0x14002d716  mov     ecx, [rax+r14+18h]
0x14002d71b  shl     rcx, 2
0x14002d71f  cmp     rcx, r9
0x14002d722  ja      loc_14002D865
0x14002d728  lea     r8d, [rcx+1Ch]
0x14002d72c  cmp     r8d, ecx
0x14002d72f  jb      loc_14002D865
0x14002d735  mov     esi, eax
0x14002d737  lea     eax, [r8+rsi]
0x14002d73b  mov     [rsp+88h+arg_8], eax
0x14002d742  cmp     eax, r8d
0x14002d745  jb      loc_14002D862
0x14002d74b  cmp     r12d, eax
0x14002d74e  jb      loc_14002D85E
0x14002d754  mov     eax, [rsi+r14]
0x14002d758  lea     rdx, ds:0[r13*4]
0x14002d760  mov     rcx, [rsp+88h+arg_0]
0x14002d768  add     rdx, r13
0x14002d76b  bswap   eax
0x14002d76d  mov     [rsp+88h+arg_18], rdx
0x14002d775  mov     [rcx+rdx*8], eax
0x14002d778  movzx   eax, word ptr [rsi+r14+4]
0x14002d77e  ror     ax, 8
0x14002d782  mov     [rcx+rdx*8+4], ax
0x14002d787  movzx   eax, word ptr [rsi+r14+6]
0x14002d78d  ror     ax, 8
0x14002d791  mov     [rcx+rdx*8+6], ax
0x14002d796  mov     rax, [rsi+r14+8]
0x14002d79b  mov     [rcx+rdx*8+8], rax
0x14002d7a0  mov     eax, [rsi+r14+10h]
0x14002d7a5  mov     [rcx+rdx*8+10h], eax
0x14002d7a9  mov     eax, [rsi+r14+14h]
0x14002d7ae  mov     [rcx+rdx*8+14h], eax
0x14002d7b2  mov     eax, [rsi+r14+18h]
0x14002d7b7  test    eax, eax
0x14002d7b9  jz      short loc_14002D814
0x14002d7bb  mov     edx, eax
0x14002d7bd  lea     ecx, [rbx+40h]
0x14002d7c0  shl     rdx, 2
0x14002d7c4  mov     r8d, 6458424Dh
0x14002d7ca  call    cs:__imp_ExAllocatePool2
0x14002d7d1  nop     dword ptr [rax+rax+00h]
0x14002d7d6  mov     rdx, [rsp+88h+arg_18]
0x14002d7de  mov     r9, rax
0x14002d7e1  mov     rax, [rsp+88h+arg_0]
0x14002d7e9  mov     [rax+rdx*8+20h], r9
0x14002d7ee  test    r9, r9
0x14002d7f1  jz      short loc_14002D832
0x14002d7f3  mov     ecx, [rsi+r14+18h]
0x14002d7f8  mov     [rax+rdx*8+18h], ecx
0x14002d7fc  lea     rdx, [rsi+1Ch]
0x14002d800  mov     r8d, [rsi+r14+18h]
0x14002d805  add     rdx, r14; Src
0x14002d808  shl     r8, 2; Size
0x14002d80c  mov     rcx, r9; void *
0x14002d80f  call    memmove
0x14002d814  inc     dword ptr [rbp+450h]
0x14002d81a  inc     r13d
0x14002d81d  mov     esi, [rsp+88h+arg_8]
0x14002d824  cmp     r13d, r15d
0x14002d827  jb      loc_14002D6C7
0x14002d82d  jmp     loc_14002DA7F
0x14002d832  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d839  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d840  jz      loc_14002D689
0x14002d846  mov     eax, [rsi+r14+18h]
0x14002d84b  mov     r9d, 0B8h
0x14002d851  shl     eax, 2
0x14002d854  mov     dword ptr [rsp+88h+var_50], r13d
0x14002d859  jmp     loc_14002D65A
0x14002d85e  mov     esi, eax
0x14002d860  jmp     short loc_14002D865
0x14002d862  mov     esi, r9d
0x14002d865  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d86c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d873  jz      loc_14002D9C6
0x14002d879  mov     [rsp+88h+var_48], r13d
0x14002d87e  mov     r9d, 0B7h
0x14002d884  mov     dword ptr [rsp+88h+var_50], esi
0x14002d888  mov     eax, [rdi+10h]
0x14002d88b  mov     r8d, 3
0x14002d891  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d898  mov     dword ptr [rsp+88h+var_58], r12d
0x14002d89d  mov     [rsp+88h+var_60], eax
0x14002d8a1  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002d8a8  mov     qword ptr [rsp+88h+var_68], rax
0x14002d8ad  mov     rcx, [rcx+40h]
0x14002d8b1  call    WPP_RECORDER_SF_Dddd
0x14002d8b6  jmp     loc_14002D9C6
0x14002d8bb  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d8c2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d8c9  jz      loc_14002D9CB
0x14002d8cf  mov     r9d, 0B6h
0x14002d8d5  jmp     short loc_14002D8F6
0x14002d8d7  mov     ebx, 0C000000Dh
0x14002d8dc  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d8e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d8ea  jz      loc_14002D9CB
0x14002d8f0  mov     r9d, 0B5h
0x14002d8f6  mov     eax, [rdi+10h]
0x14002d8f9  mov     r8d, 3
0x14002d8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d906  mov     dl, 2
0x14002d908  mov     dword ptr [rsp+88h+var_58], r13d
0x14002d90d  mov     [rsp+88h+var_60], eax
0x14002d911  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002d918  mov     qword ptr [rsp+88h+var_68], rax
0x14002d91d  mov     rcx, [rcx+40h]
0x14002d921  call    WPP_RECORDER_SF_DD
0x14002d926  jmp     loc_14002D9CB
0x14002d92b  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d932  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d939  jz      loc_14002D9C6
0x14002d93f  mov     [rsp+88h+var_48], r15d
0x14002d944  mov     r9d, 0B3h
0x14002d94a  mov     dword ptr [rsp+88h+var_50], ecx
0x14002d94e  jmp     loc_14002D888
0x14002d953  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d95a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d961  jz      short loc_14002D9C6
0x14002d963  mov     dword ptr [rsp+88h+var_50], r8d
0x14002d968  mov     r9d, 0B2h
0x14002d96e  mov     dword ptr [rsp+88h+var_58], 0FFFFFFFFh
0x14002d976  jmp     short loc_14002D99B
0x14002d978  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d97f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d986  jz      short loc_14002D9C6
0x14002d988  mov     dword ptr [rsp+88h+var_50], 20h ; ' '
0x14002d990  mov     r9d, 0B1h
0x14002d996  mov     dword ptr [rsp+88h+var_58], r15d
0x14002d99b  mov     eax, [rdi+10h]
0x14002d99e  mov     r8d, 3
0x14002d9a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d9ab  mov     dl, 2
0x14002d9ad  mov     [rsp+88h+var_60], eax
0x14002d9b1  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14002d9b8  mov     qword ptr [rsp+88h+var_68], rax
0x14002d9bd  mov     rcx, [rcx+40h]
0x14002d9c1  call    WPP_RECORDER_SF_Ddd
0x14002d9c6  mov     ebx, 0C0010015h
0x14002d9cb  test    rbp, rbp
0x14002d9ce  jz      loc_14002DA7F
0x14002d9d4  lea     rcx, [rbp+450h]; struct _MBB_DS_STATE *
0x14002d9db  call    ?FreeDeviceServiceState@@YAXPEAU_MBB_DS_STATE@@@Z; FreeDeviceServiceState(_MBB_DS_STATE *)
0x14002d9e0  jmp     loc_14002DA7F
0x14002d9e5  lea     rax, WPP_RECORDER_INITIALIZED
0x14002d9ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002d9f3  jz      loc_14002D53C
  ... truncated ...
```
