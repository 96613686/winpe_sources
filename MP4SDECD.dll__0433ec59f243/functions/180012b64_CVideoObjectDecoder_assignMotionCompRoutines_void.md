# CVideoObjectDecoder::assignMotionCompRoutines(void)

- ea: `0x180012b64`
- end: `0x180012cbf`
- name: `?assignMotionCompRoutines@CVideoObjectDecoder@@AEAAXXZ`
- size: `347`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800111bc`

## callees

- `0x180012b64`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::assignMotionCompRoutines(CVideoObjectDecoder *this)
{
  int v1; // edx
  __int64 (__fastcall *v2)(int, int, int, int, unsigned __int8 *, unsigned int, int, int, char); // rbp
  __int64 (__fastcall *v3)(int, int, int, int, int, int, char); // r14
  unsigned __int64 v4; // r8
  __int64 (__fastcall *v5)(int, int, int, int, int, int, int, char); // rdi
  __int64 (__fastcall *v6)(__int64, unsigned int, __int64, int, unsigned int, char, char); // rsi
  __int64 (__fastcall *v7)(int, int, int, int, int, int, int); // rbx
  unsigned __int64 v8; // r9
  unsigned __int64 v9; // r10
  unsigned __int64 v10; // r11
  __int64 (__fastcall *v11)(int, int, int, int, int, int, int, int); // rax

  v1 = *((_DWORD *)this + 24);
  if ( *((_DWORD *)this + 212) )
  {
    v2 = MocompInterlacedErrorRndCtrlUV_Daytona;
    v3 = MocompInterlacedRndCtrl_Daytona;
    v4 = (unsigned __int64)MocompQpel16x8ErrorRndCtrl_Daytona & -(__int64)(v1 != 0);
    v5 = g_MotionCompAndAddErrorRndCtrl_Daytona;
    v6 = g_MotionCompRndCtrl_Daytona;
    v7 = MocompQpel8x8RndCtrl_Daytona;
    v8 = (unsigned __int64)MocompQpel16x8RndCtrl_Daytona & -(__int64)(v1 != 0);
    v9 = (unsigned __int64)MocompQpel16x16ErrorRndCtrl_Daytona & -(__int64)(v1 != 0);
    v10 = (unsigned __int64)MocompQpel16x16RndCtrl_Daytona & -(__int64)(v1 != 0);
    v11 = MocompQpel8x8ErrorRndCtrl_Daytona;
  }
  else
  {
    v2 = MocompInterlacedErrorUV_Daytona;
    v3 = MocompInterlaced_Daytona;
    v4 = (unsigned __int64)MocompQpel16x8Error_Daytona & -(__int64)(v1 != 0);
    v5 = g_MotionCompAndAddError_Daytona;
    v6 = g_MotionComp_Daytona;
    v7 = MocompQpel8x8_Daytona;
    v8 = (unsigned __int64)MocompQpel16x8_Daytona & -(__int64)(v1 != 0);
    v9 = (unsigned __int64)MocompQpel16x16Error_Daytona & -(__int64)(v1 != 0);
    v10 = (unsigned __int64)MocompQpel16x16_Daytona & -(__int64)(v1 != 0);
    v11 = MocompQpel8x8Error_Daytona;
  }
  if ( !v1 )
  {
    v11 = (__int64 (__fastcall *)(int, int, int, int, int, int, int, int))v5;
    v7 = (__int64 (__fastcall *)(int, int, int, int, int, int, int))v6;
  }
  *((_QWORD *)this + 928) = v7;
  *((_QWORD *)this + 929) = v11;
  *((_QWORD *)this + 932) = v10;
  *((_QWORD *)this + 933) = v9;
  *((_QWORD *)this + 934) = v8;
  *((_QWORD *)this + 935) = v4;
  *((_QWORD *)this + 930) = v6;
  *((_QWORD *)this + 931) = v5;
  *((_QWORD *)this + 936) = v3;
  *((_QWORD *)this + 937) = v2;
  *((_QWORD *)this + 179) = g_MotionCompZeroMotion_Daytona;
}

```

## disassembly

```asm
0x180012b64  push    rbx
0x180012b66  push    rbp
0x180012b67  push    rsi
0x180012b68  push    rdi
0x180012b69  push    r14
0x180012b6b  cmp     dword ptr [rcx+350h], 0
0x180012b72  mov     edx, [rcx+60h]
0x180012b75  mov     eax, edx
0x180012b77  jnz     loc_180012C4E
0x180012b7d  neg     eax
0x180012b7f  lea     rbp, MocompInterlacedErrorUV_Daytona
0x180012b86  lea     rax, MocompQpel16x8Error_Daytona
0x180012b8d  sbb     r8, r8
0x180012b90  lea     r14, MocompInterlaced_Daytona
0x180012b97  and     r8, rax
0x180012b9a  lea     rdi, g_MotionCompAndAddError_Daytona
0x180012ba1  mov     eax, edx
0x180012ba3  lea     rsi, g_MotionComp_Daytona
0x180012baa  neg     eax
0x180012bac  lea     rbx, MocompQpel8x8_Daytona
0x180012bb3  lea     rax, MocompQpel16x8_Daytona
0x180012bba  sbb     r9, r9
0x180012bbd  and     r9, rax
0x180012bc0  mov     eax, edx
0x180012bc2  neg     eax
0x180012bc4  lea     rax, MocompQpel16x16Error_Daytona
0x180012bcb  sbb     r10, r10
0x180012bce  and     r10, rax
0x180012bd1  mov     eax, edx
0x180012bd3  neg     eax
0x180012bd5  lea     rax, MocompQpel16x16_Daytona
0x180012bdc  sbb     r11, r11
0x180012bdf  and     r11, rax
0x180012be2  lea     rax, MocompQpel8x8Error_Daytona
0x180012be9  test    edx, edx
0x180012beb  cmovz   rax, rdi
0x180012bef  cmovz   rbx, rsi
0x180012bf3  mov     [rcx+1D00h], rbx
0x180012bfa  mov     [rcx+1D08h], rax
0x180012c01  lea     rax, g_MotionCompZeroMotion_Daytona
0x180012c08  mov     [rcx+1D20h], r11
0x180012c0f  mov     [rcx+1D28h], r10
0x180012c16  mov     [rcx+1D30h], r9
0x180012c1d  mov     [rcx+1D38h], r8
0x180012c24  mov     [rcx+1D10h], rsi
0x180012c2b  mov     [rcx+1D18h], rdi
0x180012c32  mov     [rcx+1D40h], r14
0x180012c39  mov     [rcx+1D48h], rbp
0x180012c40  mov     [rcx+598h], rax
0x180012c47  pop     r14
0x180012c49  pop     rdi
0x180012c4a  pop     rsi
0x180012c4b  pop     rbp
0x180012c4c  pop     rbx
0x180012c4d  retn
0x180012c4e  neg     eax
0x180012c50  lea     rbp, MocompInterlacedErrorRndCtrlUV_Daytona
0x180012c57  lea     rax, MocompQpel16x8ErrorRndCtrl_Daytona
0x180012c5e  sbb     r8, r8
0x180012c61  lea     r14, MocompInterlacedRndCtrl_Daytona
0x180012c68  and     r8, rax
0x180012c6b  lea     rdi, g_MotionCompAndAddErrorRndCtrl_Daytona
0x180012c72  mov     eax, edx
0x180012c74  lea     rsi, g_MotionCompRndCtrl_Daytona
0x180012c7b  neg     eax
0x180012c7d  lea     rbx, MocompQpel8x8RndCtrl_Daytona
0x180012c84  lea     rax, MocompQpel16x8RndCtrl_Daytona
0x180012c8b  sbb     r9, r9
0x180012c8e  and     r9, rax
0x180012c91  mov     eax, edx
0x180012c93  neg     eax
0x180012c95  lea     rax, MocompQpel16x16ErrorRndCtrl_Daytona
0x180012c9c  sbb     r10, r10
0x180012c9f  and     r10, rax
0x180012ca2  mov     eax, edx
0x180012ca4  neg     eax
0x180012ca6  lea     rax, MocompQpel16x16RndCtrl_Daytona
0x180012cad  sbb     r11, r11
0x180012cb0  and     r11, rax
0x180012cb3  lea     rax, MocompQpel8x8ErrorRndCtrl_Daytona
0x180012cba  jmp     loc_180012BE9
```
