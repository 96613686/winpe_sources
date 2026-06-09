# CPort::OnCipherKeyUpdatedReceived(ulong,uchar *)

- ea: `0x14008563c`
- end: `0x1400858c9`
- name: `?OnCipherKeyUpdatedReceived@CPort@@QEAAXKPEAE@Z`
- size: `653`
- prototype: `void __fastcall(CPort *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140026010`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x14003895c`
- `0x14004120c`
- `0x14006556c`
- `0x14007436c`
- `0x14008563c`
- `0x14008d950`

## pseudocode

```c
void __fastcall CPort::OnCipherKeyUpdatedReceived(CPort *this, int a2, unsigned __int8 *a3)
{
  int v4; // esi
  int v6; // eax
  int v7; // edx
  int v8; // r8d
  int v9; // ebx
  int v10; // edx
  unsigned int v11; // ebx
  _QWORD *v12; // rsi
  int v13; // r8d
  int v14; // r9d
  int v15; // edx
  int v16; // r8d
  int v17; // [rsp+20h] [rbp-59h]
  unsigned int v18[2]; // [rsp+28h] [rbp-51h]
  __int64 v19; // [rsp+40h] [rbp-39h]
  int v20; // [rsp+50h] [rbp-29h] BYREF
  int v21; // [rsp+58h] [rbp-21h]
  __int64 v22; // [rsp+60h] [rbp-19h]
  int v23; // [rsp+68h] [rbp-11h]
  __int64 v24; // [rsp+70h] [rbp-9h]
  char v25; // [rsp+78h] [rbp-1h]
  int v26; // [rsp+80h] [rbp+7h]
  __int64 v27; // [rsp+88h] [rbp+Fh]
  char v28; // [rsp+90h] [rbp+17h]
  int v29; // [rsp+98h] [rbp+1Fh]
  __int64 v30; // [rsp+A0h] [rbp+27h]
  char v31; // [rsp+A8h] [rbp+2Fh]
  unsigned int v32; // [rsp+E8h] [rbp+6Fh] BYREF

  v20 &= ~1u;
  v4 = a2;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      344,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  v6 = ParseWdiIndicationCipherKeyUpdatedFromIhv(
         (unsigned int)(v4 - 48),
         a3 + 48,
         *((_QWORD *)this + 17) + 5384LL,
         &v20);
  v9 = v6;
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_23;
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      345,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      (char)this,
      *((_WORD *)this + 74),
      v6);
  }
  else
  {
    v11 = 52 * (v29 + 2);
    v32 = v11;
    v12 = operator new(v11);
    if ( v12 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_ddidd(WPP_GLOBAL_Control->DeviceExtension, v10, v13, v14, v17, v29, v21, v22, v23, v26);
      v9 = CWabiToDot11Converter::MapCipherKeyParams((struct _WDI_RSN_OFFLOAD_KEYS_CONTAINER *)&v20, v11, &v32, v12);
      if ( v9 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 2;
          LODWORD(v19) = v32;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            v16,
            348,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            (char)this,
            *((_WORD *)this + 74),
            v9,
            v19);
        }
      }
      else
      {
        CAdapter::IndicateStatus(*((CAdapter **)this + 17), *((_DWORD *)this + 36), 1073938478, 0, v12, v32);
      }
      operator delete(v12);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          v13,
          346,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
          (char)this,
          *((_WORD *)this + 74));
      }
      v9 = -1073741670;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v18[0] = v9;
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      349,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      *(_QWORD *)v18);
  }
LABEL_23:
  _WDI_RSN_OFFLOAD_KEYS_CONTAINER::~_WDI_RSN_OFFLOAD_KEYS_CONTAINER((_WDI_RSN_OFFLOAD_KEYS_CONTAINER *)&v20);
}

```

## disassembly

```asm
0x14008563c  mov     [rsp-8+arg_0], rbx
0x140085641  mov     [rsp-8+arg_10], rsi
0x140085646  push    rbp
0x140085647  push    rdi
0x140085648  push    r12
0x14008564a  push    r14
0x14008564c  push    r15
0x14008564e  lea     rbp, [rsp-37h]
0x140085653  sub     rsp, 0B0h
0x14008565a  and     [rbp+57h+var_80], 0FFFFFFFEh
0x14008565e  mov     rbx, r8
0x140085661  xor     r14d, r14d
0x140085664  mov     esi, edx
0x140085666  mov     [rbp+57h+var_78], r14d
0x14008566a  mov     rdi, rcx
0x14008566d  mov     [rbp+57h+var_70], r14
0x140085671  mov     [rbp+57h+var_68], r14d
0x140085675  mov     [rbp+57h+var_60], r14
0x140085679  mov     [rbp+57h+var_58], r14b
0x14008567d  mov     [rbp+57h+var_50], r14d
0x140085681  mov     [rbp+57h+var_48], r14
0x140085685  mov     [rbp+57h+var_40], r14b
0x140085689  mov     [rbp+57h+var_38], r14d
0x14008568d  mov     [rbp+57h+var_30], r14
0x140085691  mov     [rbp+57h+var_28], r14b
0x140085695  lea     r15, WPP_RECORDER_INITIALIZED
0x14008569c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400856a3  lea     r12, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400856aa  jz      short loc_1400856DC
0x1400856ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400856b3  cmp     byte ptr [rcx+29h], 5
0x1400856b7  jnb     short loc_1400856C0
0x1400856b9  cmp     [rcx+48h], r14w
0x1400856be  jz      short loc_1400856DC
0x1400856c0  mov     rcx, [rcx+40h]
0x1400856c4  mov     r9d, 158h
0x1400856ca  mov     r8d, 1
0x1400856d0  mov     [rsp+0D0h+var_B0], r12
0x1400856d5  mov     dl, 5
0x1400856d7  call    WPP_RECORDER_SF_
0x1400856dc  mov     r8, [rdi+88h]
0x1400856e3  lea     rdx, [rbx+30h]
0x1400856e7  add     r8, 1508h
0x1400856ee  lea     ecx, [rsi-30h]
0x1400856f1  lea     r9, [rbp+57h+var_80]
0x1400856f5  call    ParseWdiIndicationCipherKeyUpdatedFromIhv
0x1400856fa  mov     ebx, eax
0x1400856fc  test    eax, eax
0x1400856fe  jz      short loc_140085743
0x140085700  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140085707  jz      loc_1400858A3
0x14008570d  movzx   ecx, word ptr [rdi+94h]
0x140085714  mov     r9d, 159h
0x14008571a  mov     dword ptr [rsp+0D0h+var_98], eax
0x14008571e  mov     dl, 2
0x140085720  mov     [rsp+0D0h+var_A0], ecx
0x140085724  mov     rcx, cs:WPP_GLOBAL_Control
0x14008572b  mov     qword ptr [rsp+0D0h+var_A8], rdi
0x140085730  mov     [rsp+0D0h+var_B0], r12
0x140085735  mov     rcx, [rcx+40h]
0x140085739  call    WPP_RECORDER_SF_qDD
0x14008573e  jmp     loc_140085866
0x140085743  mov     eax, [rbp+57h+var_38]
0x140085746  add     eax, 2
0x140085749  imul    ebx, eax, 34h ; '4'
0x14008574c  mov     ecx, ebx; unsigned __int64
0x14008574e  mov     [rbp+57h+arg_8], ebx
0x140085751  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140085756  mov     rsi, rax
0x140085759  test    rax, rax
0x14008575c  jnz     short loc_14008579E
0x14008575e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140085765  jz      short loc_140085794
0x140085767  mov     rcx, cs:WPP_GLOBAL_Control
0x14008576e  mov     r9d, 15Ah
0x140085774  movzx   eax, word ptr [rdi+94h]
0x14008577b  mov     dl, 2
0x14008577d  mov     [rsp+0D0h+var_A0], eax
0x140085781  mov     qword ptr [rsp+0D0h+var_A8], rdi
0x140085786  mov     rcx, [rcx+40h]
0x14008578a  mov     [rsp+0D0h+var_B0], r12
0x14008578f  call    WPP_RECORDER_SF_qD
0x140085794  mov     ebx, 0C000009Ah
0x140085799  jmp     loc_140085866
0x14008579e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400857a5  jz      short loc_1400857DC
0x1400857a7  mov     eax, [rbp+57h+var_50]
0x1400857aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400857b1  mov     [rsp+0D0h+var_88], eax
0x1400857b5  mov     eax, [rbp+57h+var_68]
0x1400857b8  mov     dword ptr [rsp+0D0h+var_90], eax
0x1400857bc  mov     rax, [rbp+57h+var_70]
0x1400857c0  mov     rcx, [rcx+40h]
0x1400857c4  mov     [rsp+0D0h+var_98], rax
0x1400857c9  mov     eax, [rbp+57h+var_78]
0x1400857cc  mov     [rsp+0D0h+var_A0], eax
0x1400857d0  mov     eax, [rbp+57h+var_38]
0x1400857d3  mov     [rsp+0D0h+var_A8], eax
0x1400857d7  call    WPP_RECORDER_SF_ddidd
0x1400857dc  mov     r9, rsi; void *
0x1400857df  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x1400857e3  mov     edx, ebx; unsigned int
0x1400857e5  lea     rcx, [rbp+57h+var_80]; struct _WDI_RSN_OFFLOAD_KEYS_CONTAINER *
0x1400857e9  call    ?MapCipherKeyParams@CWabiToDot11Converter@@SAHPEAU_WDI_RSN_OFFLOAD_KEYS_CONTAINER@@IPEAIPEAX@Z; CWabiToDot11Converter::MapCipherKeyParams(_WDI_RSN_OFFLOAD_KEYS_CONTAINER *,uint,uint *,void *)
0x1400857ee  mov     ebx, eax
0x1400857f0  test    eax, eax
0x1400857f2  jz      short loc_140085837
0x1400857f4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400857fb  jz      short loc_14008585E
0x1400857fd  movzx   ecx, word ptr [rdi+94h]
0x140085804  mov     r9d, 15Ch
0x14008580a  mov     eax, [rbp+57h+arg_8]
0x14008580d  mov     dl, 2
0x14008580f  mov     dword ptr [rsp+0D0h+var_90], eax
0x140085813  mov     dword ptr [rsp+0D0h+var_98], ebx
0x140085817  mov     [rsp+0D0h+var_A0], ecx
0x14008581b  mov     rcx, cs:WPP_GLOBAL_Control
0x140085822  mov     qword ptr [rsp+0D0h+var_A8], rdi
0x140085827  mov     [rsp+0D0h+var_B0], r12
0x14008582c  mov     rcx, [rcx+40h]
0x140085830  call    WPP_RECORDER_SF_qDdd
0x140085835  jmp     short loc_14008585E
0x140085837  mov     eax, [rbp+57h+arg_8]
0x14008583a  xor     r9d, r9d; void *
0x14008583d  mov     edx, [rdi+90h]; unsigned int
0x140085843  mov     r8d, 4003002Eh; int
0x140085849  mov     rcx, [rdi+88h]; this
0x140085850  mov     [rsp+0D0h+var_A8], eax; unsigned int
0x140085854  mov     [rsp+0D0h+var_B0], rsi; void *
0x140085859  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x14008585e  mov     rcx, rsi; void *
0x140085861  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140085866  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008586d  jz      short loc_1400858A3
0x14008586f  mov     rcx, cs:WPP_GLOBAL_Control
0x140085876  cmp     byte ptr [rcx+29h], 5
0x14008587a  jnb     short loc_140085883
0x14008587c  cmp     [rcx+48h], r14w
0x140085881  jz      short loc_1400858A3
0x140085883  mov     rcx, [rcx+40h]
0x140085887  mov     r9d, 15Dh
0x14008588d  mov     [rsp+0D0h+var_A8], ebx
0x140085891  mov     r8d, 1
0x140085897  mov     dl, 5
0x140085899  mov     [rsp+0D0h+var_B0], r12
0x14008589e  call    WPP_RECORDER_SF_d
0x1400858a3  lea     rcx, [rbp+57h+var_80]; this
0x1400858a7  call    ??1_WDI_RSN_OFFLOAD_KEYS_CONTAINER@@QEAA@XZ; _WDI_RSN_OFFLOAD_KEYS_CONTAINER::~_WDI_RSN_OFFLOAD_KEYS_CONTAINER(void)
0x1400858ac  lea     r11, [rsp+0D0h+var_20]
0x1400858b4  mov     rbx, [r11+30h]
0x1400858b8  mov     rsi, [r11+40h]
0x1400858bc  mov     rsp, r11
0x1400858bf  pop     r15
0x1400858c1  pop     r14
0x1400858c3  pop     r12
0x1400858c5  pop     rdi
0x1400858c6  pop     rbp
0x1400858c7  retn
```
