# CWabiToDot11Converter::CombineArrayOfByteArrays(ArrayOfElements<ArrayOfElements<uchar>> *,uchar * *,uint *,bool *)

- ea: `0x14004fd6c`
- end: `0x14004ff80`
- name: `?CombineArrayOfByteArrays@CWabiToDot11Converter@@SAHPEAU?$ArrayOfElements@U?$ArrayOfElements@E@@@@PEAPEAEPEAIPEA_N@Z`
- size: `532`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004f630`
- `0x14004f8cc`
- `0x14004fad0`
- `0x14006a118`

## callees

- `0x140012214`
- `0x140017a90`
- `0x140034e04`
- `0x14004fd6c`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004fee6`
- `ntoskrnl!ExAllocatePool2` at `0x14004fee6`

## pseudocode

```c
__int64 __fastcall CWabiToDot11Converter::CombineArrayOfByteArrays(
        unsigned int *a1,
        __int64 *a2,
        unsigned int *a3,
        _BYTE *a4)
{
  unsigned int v4; // r10d
  unsigned int v6; // edx
  unsigned int v9; // r13d
  int *v10; // rcx
  int v11; // eax
  unsigned int v13; // esi
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // edx
  __int64 Pool2; // rax
  int v18; // edx
  int v19; // r8d
  __int64 v20; // rbp
  __int64 v21; // rdi
  char *v22; // r13
  __int64 v23; // rbx

  v4 = *a1;
  v6 = 0;
  *a4 = 0;
  v9 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( v4 )
  {
    if ( v4 == 1 )
    {
      v10 = (int *)*((_QWORD *)a1 + 1);
      *a2 = *((_QWORD *)v10 + 1);
      v11 = *v10;
      *a3 = *v10;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v6) = 5;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          (_DWORD)a3,
          55,
          (__int64)WPP_3271bc59e51a3fc518aedf1771aa60aa_Traceguids,
          v11);
      }
    }
    else
    {
      v13 = 0;
      v14 = *((_QWORD *)a1 + 1);
      do
      {
        v15 = v6++;
        v13 += *(_DWORD *)(v14 + 24 * v15);
      }
      while ( v6 < v4 );
      v16 = 0;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v16) = 5;
        WPP_RECORDER_SF_Ld(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          v14,
          56,
          (__int64)WPP_3271bc59e51a3fc518aedf1771aa60aa_Traceguids,
          v4,
          v13);
      }
      Pool2 = ExAllocatePool2(64, v13, 1198089303);
      v20 = Pool2;
      if ( Pool2 )
      {
        v21 = 0;
        if ( *a1 )
        {
          v22 = (char *)Pool2;
          do
          {
            v23 = 3 * v21;
            memmove(
              v22,
              *(const void **)(*((_QWORD *)a1 + 1) + 24 * v21 + 8),
              *(unsigned int *)(*((_QWORD *)a1 + 1) + 24 * v21));
            v21 = (unsigned int)(v21 + 1);
            v22 += *(unsigned int *)(*((_QWORD *)a1 + 1) + 8 * v23);
          }
          while ( (unsigned int)v21 < *a1 );
          v9 = 0;
        }
        *a2 = v20;
        *a3 = v13;
        *a4 = 1;
      }
      else
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            v19,
            57,
            (__int64)WPP_3271bc59e51a3fc518aedf1771aa60aa_Traceguids,
            v13);
        }
        return (unsigned int)-1073741670;
      }
    }
  }
  else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
         && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      54,
      (__int64)WPP_3271bc59e51a3fc518aedf1771aa60aa_Traceguids);
  }
  return v9;
}

```

## disassembly

```asm
0x14004fd6c  mov     [rsp+arg_8], rbx
0x14004fd71  mov     [rsp+arg_18], r9
0x14004fd76  push    rbp
0x14004fd77  push    rsi
0x14004fd78  push    rdi
0x14004fd79  push    r12
0x14004fd7b  push    r13
0x14004fd7d  push    r14
0x14004fd7f  push    r15
0x14004fd81  sub     rsp, 40h
0x14004fd85  mov     r10d, [rcx]
0x14004fd88  mov     r12, rdx
0x14004fd8b  xor     edx, edx
0x14004fd8d  mov     r15, r8
0x14004fd90  mov     [rsp+78h+arg_0], edx
0x14004fd97  mov     r14, rcx
0x14004fd9a  mov     [r9], dl
0x14004fd9d  mov     r13d, edx
0x14004fda0  mov     [r12], rdx
0x14004fda4  mov     [r8], edx
0x14004fda7  test    r10d, r10d
0x14004fdaa  jz      short loc_14004FE06
0x14004fdac  cmp     r10d, 1
0x14004fdb0  jnz     loc_14004FE72
0x14004fdb6  mov     rcx, [rcx+8]
0x14004fdba  mov     rax, [rcx+8]
0x14004fdbe  mov     [r12], rax
0x14004fdc2  mov     eax, [rcx]
0x14004fdc4  mov     [r8], eax
0x14004fdc7  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004fdce  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14004fdd5  jz      short loc_14004FDEA
0x14004fdd7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fdde  cmp     byte ptr [rcx+29h], 5
0x14004fde2  jnb     short loc_14004FE4C
0x14004fde4  cmp     [rcx+48h], dx
0x14004fde8  jnz     short loc_14004FE4C
0x14004fdea  mov     rbx, [rsp+78h+arg_8]
0x14004fdf2  mov     eax, r13d
0x14004fdf5  add     rsp, 40h
0x14004fdf9  pop     r15
0x14004fdfb  pop     r14
0x14004fdfd  pop     r13
0x14004fdff  pop     r12
0x14004fe01  pop     rdi
0x14004fe02  pop     rsi
0x14004fe03  pop     rbp
0x14004fe04  retn
0x14004fe06  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004fe0d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14004fe14  jz      short loc_14004FDEA
0x14004fe16  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fe1d  cmp     byte ptr [rcx+29h], 5
0x14004fe21  jnb     short loc_14004FE29
0x14004fe23  cmp     [rcx+48h], dx
0x14004fe27  jz      short loc_14004FDEA
0x14004fe29  mov     rcx, [rcx+40h]
0x14004fe2d  lea     rdi, WPP_3271bc59e51a3fc518aedf1771aa60aa_Traceguids
0x14004fe34  mov     r9d, 36h ; '6'
0x14004fe3a  mov     [rsp+78h+var_58], rdi
0x14004fe3f  mov     dl, 5
0x14004fe41  lea     r8d, [r9-35h]
0x14004fe45  call    WPP_RECORDER_SF_
0x14004fe4a  jmp     short loc_14004FDEA
0x14004fe4c  mov     rcx, [rcx+40h]
0x14004fe50  lea     rdi, WPP_3271bc59e51a3fc518aedf1771aa60aa_Traceguids
0x14004fe57  mov     [rsp+78h+var_50], eax
0x14004fe5b  mov     r9d, 37h ; '7'
0x14004fe61  mov     dl, 5
0x14004fe63  mov     [rsp+78h+var_58], rdi
0x14004fe68  call    WPP_RECORDER_SF_d
0x14004fe6d  jmp     loc_14004FDEA
0x14004fe72  mov     esi, edx
0x14004fe74  test    r10d, r10d
0x14004fe77  jz      short loc_14004FE90
0x14004fe79  mov     r8, [rcx+8]
0x14004fe7d  mov     eax, edx
0x14004fe7f  inc     edx
0x14004fe81  lea     rcx, [rax+rax*2]
0x14004fe85  add     esi, [r8+rcx*8]
0x14004fe89  cmp     edx, r10d
0x14004fe8c  jb      short loc_14004FE7D
0x14004fe8e  xor     edx, edx
0x14004fe90  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004fe97  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14004fe9e  lea     rdi, WPP_3271bc59e51a3fc518aedf1771aa60aa_Traceguids
0x14004fea5  jz      short loc_14004FED9
0x14004fea7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004feae  cmp     byte ptr [rcx+29h], 5
0x14004feb2  jnb     short loc_14004FEBA
0x14004feb4  cmp     [rcx+48h], dx
0x14004feb8  jz      short loc_14004FED9
0x14004feba  mov     rcx, [rcx+40h]
0x14004febe  mov     r9d, 38h ; '8'
0x14004fec4  mov     [rsp+78h+var_48], esi
0x14004fec8  mov     dl, 5
0x14004feca  mov     [rsp+78h+var_50], r10d
0x14004fecf  mov     [rsp+78h+var_58], rdi
0x14004fed4  call    WPP_RECORDER_SF_Ld
0x14004fed9  mov     edx, esi
0x14004fedb  mov     ecx, 40h ; '@'
0x14004fee0  mov     r8d, 47696457h
0x14004fee6  call    cs:__imp_ExAllocatePool2
0x14004feed  nop     dword ptr [rax+rax+00h]
0x14004fef2  mov     rbp, rax
0x14004fef5  test    rax, rax
0x14004fef8  jnz     short loc_14004FF2D
0x14004fefa  cmp     cs:WPP_RECORDER_INITIALIZED, rbx; __annotation("TMF:",
0x14004ff01  jz      short loc_14004FF22
0x14004ff03  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ff0a  lea     r9d, [rax+39h]
0x14004ff0e  mov     [rsp+78h+var_50], esi
0x14004ff12  mov     dl, 2
0x14004ff14  mov     [rsp+78h+var_58], rdi
0x14004ff19  mov     rcx, [rcx+40h]
0x14004ff1d  call    WPP_RECORDER_SF_d
0x14004ff22  mov     r13d, 0C000009Ah
0x14004ff28  jmp     loc_14004FDEA
0x14004ff2d  xor     edi, edi
0x14004ff2f  cmp     [r14], edi
0x14004ff32  jbe     short loc_14004FF69
0x14004ff34  mov     r13, rbp
0x14004ff37  mov     rdx, [r14+8]
0x14004ff3b  lea     rbx, [rdi+rdi*2]
0x14004ff3f  mov     rcx, r13; void *
0x14004ff42  mov     r8d, [rdx+rbx*8]; Size
0x14004ff46  mov     rdx, [rdx+rbx*8+8]; Src
0x14004ff4b  call    memmove
0x14004ff50  mov     rcx, [r14+8]
0x14004ff54  inc     edi
0x14004ff56  mov     edx, [rcx+rbx*8]
0x14004ff59  add     r13, rdx
0x14004ff5c  cmp     edi, [r14]
0x14004ff5f  jb      short loc_14004FF37
0x14004ff61  mov     r13d, [rsp+78h+arg_0]
0x14004ff69  mov     rax, [rsp+78h+arg_18]
0x14004ff71  mov     [r12], rbp
0x14004ff75  mov     [r15], esi
0x14004ff78  mov     byte ptr [rax], 1
0x14004ff7b  jmp     loc_14004FDEA
```
