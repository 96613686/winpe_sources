# CGetSupportedDeviceServicesJob::OnDeviceCommandCompletion(int,ulong,uchar *,void *,uint,uint *,uint *)

- ea: `0x14007aba0`
- end: `0x14007ae71`
- name: `?OnDeviceCommandCompletion@CGetSupportedDeviceServicesJob@@UEAAHHKPEAEPEAXIPEAI2@Z`
- size: `721`
- prototype: `__int64 __fastcall(CGetSupportedDeviceServicesJob *__hidden this, int, unsigned int, unsigned __int8 *, void *, size_t Size, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400069dc`
- `0x14000c778`
- `0x14000d054`
- `0x140019c78`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140040f0c`
- `0x14007aba0`
- `0x1400dfe00`
- `0x1400e0100`

## pseudocode

```c
__int64 __fastcall CGetSupportedDeviceServicesJob::OnDeviceCommandCompletion(
        CGetSupportedDeviceServicesJob *this,
        unsigned int a2,
        int a3,
        unsigned __int8 *a4,
        char *a5,
        size_t Size,
        unsigned int *a7,
        unsigned int *a8)
{
  unsigned int v10; // edi
  unsigned int SupportedDeviceServicesFromIhv; // eax
  unsigned int v13; // r15d
  unsigned int v14; // ebp
  unsigned int v15; // r13d
  __int16 v16; // ax
  __int64 v18; // [rsp+28h] [rbp-80h]
  __int64 v19; // [rsp+38h] [rbp-70h]
  unsigned int v20; // [rsp+40h] [rbp-68h] BYREF
  void *Src; // [rsp+48h] [rbp-60h]
  char v22; // [rsp+50h] [rbp-58h]

  v20 = 0;
  Src = 0;
  v10 = a2;
  v22 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      254,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  if ( !v10 )
  {
    memset(a5, 0, (unsigned int)Size);
    if ( (unsigned int)Size >= 0xC )
    {
      *(_QWORD *)(a5 + 4) = 0;
      SupportedDeviceServicesFromIhv = ParseWdiGetSupportedDeviceServicesFromIhv(
                                         (unsigned int)(a3 - 48),
                                         a4 + 48,
                                         *((_QWORD *)this + 67) + 5384LL,
                                         &v20);
      v10 = SupportedDeviceServicesFromIhv;
      if ( SupportedDeviceServicesFromIhv )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_25;
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          a3,
          256,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          SupportedDeviceServicesFromIhv);
      }
      else
      {
        v13 = v20;
        *a7 = 12;
        if ( v13 )
        {
          v14 = v13;
          v15 = 16 * v13 + 12;
          if ( (unsigned int)Size < v15 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(a2) = 2;
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                a2,
                1,
                257,
                (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids);
              v13 = v20;
            }
            v10 = -2147483643;
            v14 = (unsigned int)(Size - 12) >> 4;
            *a8 = v15;
          }
          memmove(a5 + 12, Src, 16LL * v14);
          *((_DWORD *)a5 + 1) = v14;
          *((_DWORD *)a5 + 2) = v13;
          *a7 += 16 * v14;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(a2) = 4;
            WPP_RECORDER_SF_DD(
              WPP_GLOBAL_Control->DeviceExtension,
              a2,
              1,
              258,
              (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
              *((_DWORD *)a5 + 1),
              *((_DWORD *)a5 + 2));
          }
        }
        v16 = 16 * *((_WORD *)a5 + 2);
        *(_WORD *)a5 = 384;
        *((_WORD *)a5 + 1) = v16 + 12;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v18) = Size;
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          1,
          255,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          v18);
      }
      v10 = -1073676268;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    LODWORD(v19) = v10;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      259,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v19);
  }
LABEL_25:
  ArrayOfElements<_WDI_PHY_STATISTICS_PARAMETERS>::Cleanup(&v20);
  return v10;
}

```

## disassembly

```asm
0x14007aba0  push    rbx
0x14007aba2  push    rbp
0x14007aba3  push    rsi
0x14007aba4  push    rdi
0x14007aba5  push    r12
0x14007aba7  push    r13
0x14007aba9  push    r14
0x14007abab  push    r15
0x14007abad  sub     rsp, 68h
0x14007abb1  xor     r13d, r13d
0x14007abb4  mov     rbp, r9
0x14007abb7  mov     [rsp+0A8h+var_68], r13d
0x14007abbc  mov     r15d, r8d
0x14007abbf  mov     [rsp+0A8h+Src], r13
0x14007abc4  mov     edi, edx
0x14007abc6  mov     [rsp+0A8h+var_58], r13b
0x14007abcb  mov     rsi, rcx
0x14007abce  lea     r12, WPP_RECORDER_INITIALIZED
0x14007abd5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007abdc  lea     rbx, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x14007abe3  jz      short loc_14007AC1B
0x14007abe5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007abec  cmp     byte ptr [rcx+29h], 5
0x14007abf0  jnb     short loc_14007ABF9
0x14007abf2  cmp     [rcx+48h], r13w
0x14007abf7  jz      short loc_14007AC1B
0x14007abf9  mov     eax, [rsi+10h]
0x14007abfc  mov     r9d, 0FEh
0x14007ac02  mov     rcx, [rcx+40h]
0x14007ac06  mov     dl, 5
0x14007ac08  mov     [rsp+0A8h+var_78], eax
0x14007ac0c  mov     [rsp+0A8h+var_80], rsi
0x14007ac11  mov     [rsp+0A8h+var_88], rbx
0x14007ac16  call    WPP_RECORDER_SF_qD
0x14007ac1b  test    edi, edi
0x14007ac1d  jnz     loc_14007AE10
0x14007ac23  mov     r14d, dword ptr [rsp+0A8h+Size]
0x14007ac2b  xor     edx, edx; Val
0x14007ac2d  mov     rbx, [rsp+0A8h+arg_20]
0x14007ac35  mov     r8d, r14d; Size
0x14007ac38  mov     rcx, rbx; void *
0x14007ac3b  call    memset
0x14007ac40  cmp     r14d, 0Ch
0x14007ac44  jnb     short loc_14007AC86
0x14007ac46  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007ac4d  lea     rbx, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x14007ac54  jz      short loc_14007AC7C
0x14007ac56  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ac5d  lea     r8d, [rdi+1]
0x14007ac61  mov     r9d, 0FFh
0x14007ac67  mov     dword ptr [rsp+0A8h+var_80], r14d
0x14007ac6c  mov     dl, 2
0x14007ac6e  mov     [rsp+0A8h+var_88], rbx
0x14007ac73  mov     rcx, [rcx+40h]
0x14007ac77  call    WPP_RECORDER_SF_d
0x14007ac7c  mov     edi, 0C0010014h
0x14007ac81  jmp     loc_14007AE10
0x14007ac86  mov     [rbx+4], r13
0x14007ac8a  lea     rdx, [rbp+30h]
0x14007ac8e  mov     r8, [rsi+218h]
0x14007ac95  lea     ecx, [r15-30h]
0x14007ac99  add     r8, 1508h
0x14007aca0  lea     r9, [rsp+0A8h+var_68]
0x14007aca5  call    ParseWdiGetSupportedDeviceServicesFromIhv
0x14007acaa  mov     edi, eax
0x14007acac  test    eax, eax
0x14007acae  jz      short loc_14007ACF6
0x14007acb0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007acb7  jz      loc_14007AE53
0x14007acbd  mov     rcx, cs:WPP_GLOBAL_Control
0x14007acc4  lea     rbx, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x14007accb  mov     dword ptr [rsp+0A8h+var_70], eax
0x14007accf  mov     r9d, 100h
0x14007acd5  mov     eax, [rsi+10h]
0x14007acd8  mov     dl, 2
0x14007acda  mov     [rsp+0A8h+var_78], eax
0x14007acde  mov     rcx, [rcx+40h]
0x14007ace2  mov     [rsp+0A8h+var_80], rsi
0x14007ace7  mov     [rsp+0A8h+var_88], rbx
0x14007acec  call    WPP_RECORDER_SF_qDD
0x14007acf1  jmp     loc_14007AE10
0x14007acf6  mov     r12, [rsp+0A8h+arg_30]
0x14007acfe  mov     r15d, [rsp+0A8h+var_68]
0x14007ad03  mov     dword ptr [r12], 0Ch
0x14007ad0b  test    r15d, r15d
0x14007ad0e  jz      loc_14007ADED
0x14007ad14  mov     r13d, r15d
0x14007ad17  mov     ebp, r15d
0x14007ad1a  shl     r13d, 4
0x14007ad1e  add     r13d, 0Ch
0x14007ad22  cmp     r14d, r13d
0x14007ad25  jnb     short loc_14007AD7D
0x14007ad27  lea     rax, WPP_RECORDER_INITIALIZED
0x14007ad2e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007ad35  jz      short loc_14007AD66
0x14007ad37  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ad3e  lea     rax, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x14007ad45  mov     r9d, 101h
0x14007ad4b  mov     [rsp+0A8h+var_88], rax
0x14007ad50  mov     r8d, 1
0x14007ad56  mov     dl, 2
0x14007ad58  mov     rcx, [rcx+40h]
0x14007ad5c  call    WPP_RECORDER_SF_
0x14007ad61  mov     r15d, [rsp+0A8h+var_68]
0x14007ad66  mov     rax, [rsp+0A8h+arg_38]
0x14007ad6e  lea     ebp, [r14-0Ch]
0x14007ad72  mov     edi, 80000005h
0x14007ad77  shr     ebp, 4
0x14007ad7a  mov     [rax], r13d
0x14007ad7d  mov     rdx, [rsp+0A8h+Src]; Src
0x14007ad82  lea     rcx, [rbx+0Ch]; void *
0x14007ad86  mov     r8d, ebp
0x14007ad89  shl     r8, 4; Size
0x14007ad8d  call    memmove
0x14007ad92  mov     [rbx+4], ebp
0x14007ad95  shl     ebp, 4
0x14007ad98  mov     [rbx+8], r15d
0x14007ad9c  add     [r12], ebp
0x14007ada0  lea     r12, WPP_RECORDER_INITIALIZED
0x14007ada7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007adae  jz      short loc_14007ADE8
0x14007adb0  mov     eax, [rbx+8]
0x14007adb3  mov     r9d, 102h
0x14007adb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007adc0  mov     r8d, 1
0x14007adc6  mov     [rsp+0A8h+var_78], eax
0x14007adca  mov     dl, 4
0x14007adcc  mov     eax, [rbx+4]
0x14007adcf  mov     dword ptr [rsp+0A8h+var_80], eax
0x14007add3  lea     rax, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x14007adda  mov     rcx, [rcx+40h]
0x14007adde  mov     [rsp+0A8h+var_88], rax
0x14007ade3  call    WPP_RECORDER_SF_DD
0x14007ade8  xor     r13d, r13d
0x14007adeb  jmp     short loc_14007ADF4
0x14007aded  lea     r12, WPP_RECORDER_INITIALIZED
0x14007adf4  movzx   eax, word ptr [rbx+4]
0x14007adf8  shl     ax, 4
0x14007adfc  add     ax, 0Ch
0x14007ae00  mov     word ptr [rbx], 180h
0x14007ae05  mov     [rbx+2], ax
0x14007ae09  lea     rbx, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x14007ae10  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007ae17  jz      short loc_14007AE53
0x14007ae19  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ae20  cmp     byte ptr [rcx+29h], 5
0x14007ae24  jnb     short loc_14007AE2D
0x14007ae26  cmp     [rcx+48h], r13w
0x14007ae2b  jz      short loc_14007AE53
0x14007ae2d  mov     eax, [rsi+10h]
0x14007ae30  mov     r9d, 103h
0x14007ae36  mov     rcx, [rcx+40h]
0x14007ae3a  mov     dl, 5
0x14007ae3c  mov     dword ptr [rsp+0A8h+var_70], edi
0x14007ae40  mov     [rsp+0A8h+var_78], eax
0x14007ae44  mov     [rsp+0A8h+var_80], rsi
0x14007ae49  mov     [rsp+0A8h+var_88], rbx
0x14007ae4e  call    WPP_RECORDER_SF_qDD
0x14007ae53  lea     rcx, [rsp+0A8h+var_68]
0x14007ae58  call    ?Cleanup@?$ArrayOfElements@U_WDI_PHY_STATISTICS_PARAMETERS@@@@QEAAXXZ; ArrayOfElements<_WDI_PHY_STATISTICS_PARAMETERS>::Cleanup(void)
0x14007ae5d  mov     eax, edi
0x14007ae5f  add     rsp, 68h
0x14007ae63  pop     r15
0x14007ae65  pop     r14
0x14007ae67  pop     r13
0x14007ae69  pop     r12
0x14007ae6b  pop     rdi
0x14007ae6c  pop     rsi
0x14007ae6d  pop     rbp
0x14007ae6e  pop     rbx
0x14007ae6f  retn
```
