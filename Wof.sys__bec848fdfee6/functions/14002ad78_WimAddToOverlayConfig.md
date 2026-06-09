# WimAddToOverlayConfig

- ea: `0x14002ad78`
- end: `0x14002b06f`
- name: `WimAddToOverlayConfig`
- size: `759`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, _OWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140026440`

## callees

- `0x14000d3b8`
- `0x14000fce4`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002ad78`
- `0x14002b48c`
- `0x14002b78c`
- `0x14002be3c`
- `0x14003c5c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002b018`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b02e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b048`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b018`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b02e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b048`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002ae7d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002ae7d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002afed`
- `ntoskrnl!ObfDereferenceObject` at `0x14002afed`
- `FLTMGR!FltClose` at `0x14002b002`
- `FLTMGR!FltClose` at `0x14002b002`

## pseudocode

```c
__int64 __fastcall WimAddToOverlayConfig(__int64 a1, int a2, int a3, int a4, int a5, _OWORD *a6, _QWORD *a7)
{
  char *PoolWithTag; // rsi
  int v8; // r13d
  int v9; // ebx
  int v10; // edx
  int v11; // edi
  int OverlayConfig; // eax
  _DWORD *v13; // r14
  size_t v14; // r15
  unsigned int v15; // r12d
  char *v16; // rdi
  __int64 v17; // rbx
  unsigned int v18; // edx
  int v19; // r8d
  _OWORD *v20; // rax
  int v21; // eax
  int v22; // eax
  int v24; // [rsp+30h] [rbp-30h] BYREF
  void *Src; // [rsp+38h] [rbp-28h] BYREF
  PVOID P; // [rsp+40h] [rbp-20h] BYREF
  PVOID Object; // [rsp+48h] [rbp-18h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-10h] BYREF
  size_t Size; // [rsp+A8h] [rbp+48h] BYREF
  int v31; // [rsp+B8h] [rbp+58h]

  v31 = a4;
  PoolWithTag = 0;
  v8 = a1 + 64;
  v9 = a1;
  v24 = 0;
  LODWORD(Size) = 0;
  FileHandle = 0;
  Object = 0;
  Src = 0;
  P = 0;
  v11 = WimPathToBootEnvironmentDevice((int)a1 + 64, a2 + 64, a3, (unsigned int)&P, (__int64)&Size);
  if ( v11 < 0 )
    goto LABEL_28;
  LOBYTE(v10) = 1;
  OverlayConfig = WimReadOverlayConfig(
                    v9,
                    v10,
                    (unsigned int)&FileHandle,
                    (unsigned int)&Object,
                    (__int64)&Src,
                    (__int64)&v24);
  v13 = Src;
  v11 = OverlayConfig;
  if ( OverlayConfig >= 0 )
  {
    v14 = *((unsigned int *)Src + 2);
    v15 = v24 + v14 + Size;
    if ( v15 > 0x200000 || *((_DWORD *)Src + 3) >= 0x100u )
    {
      v11 = -1073740761;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, 3221226535LL);
    }
    else
    {
      PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v15, 0x66637077u);
      if ( PoolWithTag )
      {
        LODWORD(Src) = v13[3] * v14 + 24;
        memmove(PoolWithTag, v13, (unsigned int)Src);
        v16 = &PoolWithTag[*((_DWORD *)PoolWithTag + 2) * *((_DWORD *)PoolWithTag + 3)];
        memset(v16 + 24, 0, v14);
        v17 = *((_QWORD *)PoolWithTag + 2);
        v18 = 0;
        v19 = v24;
        *((_DWORD *)v16 + 10) = v31;
        *((_DWORD *)v16 + 11) = a5;
        *((_DWORD *)v16 + 9) = Size;
        v20 = a6;
        *((_QWORD *)v16 + 3) = v17;
        *((_DWORD *)v16 + 8) = v19;
        *((_OWORD *)v16 + 3) = *v20;
        ++*((_DWORD *)PoolWithTag + 3);
        ++*((_QWORD *)PoolWithTag + 2);
        if ( *((_DWORD *)PoolWithTag + 3) )
        {
          do
          {
            v21 = v18++;
            *(_DWORD *)&PoolWithTag[*((_DWORD *)PoolWithTag + 2) * v21 + 32] += v14;
          }
          while ( v18 < *((_DWORD *)PoolWithTag + 3) );
        }
        memmove(
          &PoolWithTag[(unsigned int)(v14 + (_DWORD)Src)],
          (char *)v13 + (unsigned int)Src,
          (unsigned int)(v19 - (_DWORD)Src));
        memmove(&PoolWithTag[(unsigned int)(v14 + v24)], P, (unsigned int)Size);
        v22 = WimWriteOverlayConfig(a1, FileHandle, Object, PoolWithTag, v15);
        v11 = v22;
        if ( v22 >= 0 )
        {
          WimPublishConfigChangeNotification();
          *a7 = v17;
        }
        else if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Zd(
            WPP_GLOBAL_Control->AttachedDevice,
            48,
            (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
            v8,
            v22);
        }
        goto LABEL_24;
      }
      v11 = -1073741801;
    }
  }
  else if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Zd(
      WPP_GLOBAL_Control->AttachedDevice,
      46,
      (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
      v8,
      OverlayConfig);
  }
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
LABEL_24:
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
LABEL_28:
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002ad78  mov     r11, rsp
0x14002ad7b  mov     [r11+18h], rbx
0x14002ad7f  mov     [r11+20h], r9d
0x14002ad83  mov     [r11+8], rcx
0x14002ad87  push    rbp
0x14002ad88  push    rsi
0x14002ad89  push    rdi
0x14002ad8a  push    r12
0x14002ad8c  push    r13
0x14002ad8e  push    r14
0x14002ad90  push    r15
0x14002ad92  mov     rbp, rsp
0x14002ad95  sub     rsp, 60h
0x14002ad99  xor     esi, esi
0x14002ad9b  lea     r13, [rcx+40h]
0x14002ad9f  mov     rbx, rcx
0x14002ada2  mov     [rbp+var_30], esi
0x14002ada5  lea     rax, [rbp+Size]
0x14002ada9  mov     dword ptr [rbp+Size], esi
0x14002adac  mov     rcx, r13
0x14002adaf  mov     [rbp+FileHandle], rsi
0x14002adb3  add     rdx, 40h ; '@'
0x14002adb7  mov     [rbp+Object], rsi
0x14002adbb  lea     r9, [rbp+P]
0x14002adbf  mov     [rbp+Src], rsi
0x14002adc3  mov     [rbp+P], rsi
0x14002adc7  mov     [r11-78h], rax
0x14002adcb  call    WimPathToBootEnvironmentDevice
0x14002add0  mov     edi, eax
0x14002add2  test    eax, eax
0x14002add4  js      loc_14002B03C
0x14002adda  lea     rax, [rbp+var_30]
0x14002adde  mov     dl, 1
0x14002ade0  mov     [rsp+60h+var_38], rax
0x14002ade5  lea     r9, [rbp+Object]
0x14002ade9  lea     rax, [rbp+Src]
0x14002aded  mov     rcx, rbx
0x14002adf0  lea     r8, [rbp+FileHandle]
0x14002adf4  mov     [rsp+60h+var_40], rax
0x14002adf9  call    WimReadOverlayConfig
0x14002adfe  mov     r14, [rbp+Src]
0x14002ae02  mov     edi, eax
0x14002ae04  test    eax, eax
0x14002ae06  jns     short loc_14002AE45
0x14002ae08  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ae0f  test    dword ptr [rcx+2Ch], 400h
0x14002ae16  jz      loc_14002AFE4
0x14002ae1c  cmp     byte ptr [rcx+29h], 2
0x14002ae20  jb      loc_14002AFE4
0x14002ae26  mov     rcx, [rcx+18h]
0x14002ae2a  lea     edx, [rsi+2Eh]
0x14002ae2d  mov     r9, r13
0x14002ae30  mov     dword ptr [rsp+60h+var_40], eax
0x14002ae34  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002ae3b  call    WPP_SF_Zd
0x14002ae40  jmp     loc_14002AFE4
0x14002ae45  mov     r15d, [r14+8]
0x14002ae49  mov     r12d, dword ptr [rbp+Size]
0x14002ae4d  add     r12d, r15d
0x14002ae50  add     r12d, [rbp+var_30]
0x14002ae54  cmp     r12d, 200000h
0x14002ae5b  ja      loc_14002AFB1
0x14002ae61  cmp     dword ptr [r14+0Ch], 100h
0x14002ae69  jnb     loc_14002AFB1
0x14002ae6f  mov     edx, r12d; NumberOfBytes
0x14002ae72  mov     ecx, 1; PoolType
0x14002ae77  mov     r8d, 66637077h; Tag
0x14002ae7d  call    cs:__imp_ExAllocatePoolWithTag
0x14002ae84  nop     dword ptr [rax+rax+00h]
0x14002ae89  mov     rsi, rax
0x14002ae8c  test    rax, rax
0x14002ae8f  jnz     short loc_14002AE9B
0x14002ae91  mov     edi, 0C0000017h
0x14002ae96  jmp     loc_14002AFE4
0x14002ae9b  mov     eax, r15d
0x14002ae9e  mov     rdx, r14; Src
0x14002aea1  imul    eax, [r14+0Ch]
0x14002aea6  mov     rcx, rsi; void *
0x14002aea9  add     eax, 18h
0x14002aeac  mov     r8d, eax; Size
0x14002aeaf  mov     dword ptr [rbp+Src], eax
0x14002aeb2  call    memmove
0x14002aeb7  mov     edi, [rsi+0Ch]
0x14002aeba  mov     r8, r15; Size
0x14002aebd  imul    edi, [rsi+8]
0x14002aec1  xor     edx, edx; Val
0x14002aec3  add     rdi, rsi
0x14002aec6  lea     rcx, [rdi+18h]; void *
0x14002aeca  call    memset
0x14002aecf  mov     rbx, [rsi+10h]
0x14002aed3  xor     edx, edx
0x14002aed5  mov     eax, [rbp+arg_18]
0x14002aed8  mov     r8d, [rbp+var_30]
0x14002aedc  mov     [rdi+28h], eax
0x14002aedf  mov     eax, [rbp+arg_20]
0x14002aee2  mov     [rdi+2Ch], eax
0x14002aee5  mov     eax, dword ptr [rbp+Size]
0x14002aee8  mov     [rdi+24h], eax
0x14002aeeb  mov     rax, [rbp+arg_28]
0x14002aeef  mov     [rdi+18h], rbx
0x14002aef3  mov     [rdi+20h], r8d
0x14002aef7  movups  xmm0, xmmword ptr [rax]
0x14002aefa  movdqu  xmmword ptr [rdi+30h], xmm0
0x14002aeff  inc     dword ptr [rsi+0Ch]
0x14002af02  inc     qword ptr [rsi+10h]
0x14002af06  cmp     [rsi+0Ch], edx
0x14002af09  jz      short loc_14002AF1D
0x14002af0b  mov     eax, edx
0x14002af0d  inc     edx
0x14002af0f  imul    eax, [rsi+8]
0x14002af13  add     [rax+rsi+20h], r15d
0x14002af18  cmp     edx, [rsi+0Ch]
0x14002af1b  jb      short loc_14002AF0B
0x14002af1d  mov     ecx, dword ptr [rbp+Src]
0x14002af20  sub     r8d, ecx; Size
0x14002af23  lea     rdx, [r14+rcx]; Src
0x14002af27  add     ecx, r15d
0x14002af2a  add     rcx, rsi; void *
0x14002af2d  call    memmove
0x14002af32  mov     ecx, [rbp+var_30]
0x14002af35  mov     r8d, dword ptr [rbp+Size]; Size
0x14002af39  add     ecx, r15d
0x14002af3c  mov     rdx, [rbp+P]; Src
0x14002af40  add     rcx, rsi; void *
0x14002af43  call    memmove
0x14002af48  mov     r8, [rbp+Object]
0x14002af4c  mov     r9, rsi
0x14002af4f  mov     rdx, [rbp+FileHandle]
0x14002af53  mov     rcx, [rbp+arg_0]
0x14002af57  mov     dword ptr [rsp+60h+var_40], r12d
0x14002af5c  call    WimWriteOverlayConfig
0x14002af61  mov     edi, eax
0x14002af63  test    eax, eax
0x14002af65  jns     short loc_14002AFA3
0x14002af67  mov     rcx, cs:WPP_GLOBAL_Control
0x14002af6e  test    dword ptr [rcx+2Ch], 400h
0x14002af75  jz      loc_14002B00E
0x14002af7b  cmp     byte ptr [rcx+29h], 2
0x14002af7f  jb      loc_14002B00E
0x14002af85  mov     rcx, [rcx+18h]
0x14002af89  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002af90  mov     edx, 30h ; '0'
0x14002af95  mov     dword ptr [rsp+60h+var_40], eax
0x14002af99  mov     r9, r13
0x14002af9c  call    WPP_SF_Zd
0x14002afa1  jmp     short loc_14002B00E
0x14002afa3  call    WimPublishConfigChangeNotification
0x14002afa8  mov     rax, [rbp+arg_30]
0x14002afac  mov     [rax], rbx
0x14002afaf  jmp     short loc_14002B00E
0x14002afb1  mov     edi, 0C0000427h
0x14002afb6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002afbd  test    dword ptr [rcx+2Ch], 400h
0x14002afc4  jz      short loc_14002AFE4
0x14002afc6  cmp     byte ptr [rcx+29h], 2
0x14002afca  jb      short loc_14002AFE4
0x14002afcc  mov     rcx, [rcx+18h]
0x14002afd0  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002afd7  mov     edx, 2Fh ; '/'
0x14002afdc  mov     r9d, edi
0x14002afdf  call    WPP_SF_d
0x14002afe4  mov     rcx, [rbp+Object]; Object
0x14002afe8  test    rcx, rcx
0x14002afeb  jz      short loc_14002AFF9
0x14002afed  call    cs:__imp_ObfDereferenceObject
0x14002aff4  nop     dword ptr [rax+rax+00h]
0x14002aff9  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002affd  test    rcx, rcx
0x14002b000  jz      short loc_14002B00E
0x14002b002  call    cs:__imp_FltClose
0x14002b009  nop     dword ptr [rax+rax+00h]
0x14002b00e  test    r14, r14
0x14002b011  jz      short loc_14002B024
0x14002b013  xor     edx, edx; Tag
0x14002b015  mov     rcx, r14; P
0x14002b018  call    cs:__imp_ExFreePoolWithTag
0x14002b01f  nop     dword ptr [rax+rax+00h]
0x14002b024  test    rsi, rsi
0x14002b027  jz      short loc_14002B03A
0x14002b029  xor     edx, edx; Tag
0x14002b02b  mov     rcx, rsi; P
0x14002b02e  call    cs:__imp_ExFreePoolWithTag
0x14002b035  nop     dword ptr [rax+rax+00h]
0x14002b03a  xor     esi, esi
0x14002b03c  cmp     [rbp+P], rsi
0x14002b040  jz      short loc_14002B054
0x14002b042  mov     rcx, [rbp+P]; P
0x14002b046  xor     edx, edx; Tag
0x14002b048  call    cs:__imp_ExFreePoolWithTag
0x14002b04f  nop     dword ptr [rax+rax+00h]
0x14002b054  mov     rbx, [rsp+60h+arg_10]
0x14002b05c  mov     eax, edi
0x14002b05e  add     rsp, 60h
0x14002b062  pop     r15
0x14002b064  pop     r14
0x14002b066  pop     r13
0x14002b068  pop     r12
0x14002b06a  pop     rdi
0x14002b06b  pop     rsi
0x14002b06c  pop     rbp
0x14002b06d  retn
```
