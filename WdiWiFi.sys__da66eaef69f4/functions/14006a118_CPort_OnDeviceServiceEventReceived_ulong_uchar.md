# CPort::OnDeviceServiceEventReceived(ulong,uchar *)

- ea: `0x14006a118`
- end: `0x14006a4d3`
- name: `?OnDeviceServiceEventReceived@CPort@@QEAAXKPEAE@Z`
- size: `955`
- prototype: `void __fastcall(CPort *this, int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000e2c0`

## callees

- `0x14000da4c`
- `0x1400122e0`
- `0x14002357c`
- `0x140023ae0`
- `0x14002aa28`
- `0x140034e04`
- `0x140034ec4`
- `0x14003b1d8`
- `0x14004fd6c`
- `0x14006a118`
- `0x14008da00`
- `0x1400da4f0`
- `0x1400da680`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006a34a`
- `ntoskrnl!ExAllocatePool2` at `0x14006a34a`

## pseudocode

```c
void __fastcall CPort::OnDeviceServiceEventReceived(CPort *this, int a2, unsigned __int8 *a3)
{
  unsigned int v4; // r14d
  int v5; // ebx
  int v7; // edx
  int v8; // r8d
  char v9; // di
  int v10; // edx
  int v11; // eax
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // r15d
  void *v15; // rbx
  int v16; // eax
  __int64 Pool2; // rax
  void *v18; // rdx
  int v19; // r8d
  _BYTE v20[4]; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-25h] BYREF
  void *Src; // [rsp+48h] [rbp-21h] BYREF
  int v23; // [rsp+50h] [rbp-19h] BYREF
  __int128 v24; // [rsp+54h] [rbp-15h]
  _DWORD v25[5]; // [rsp+64h] [rbp-5h] BYREF
  char v26; // [rsp+78h] [rbp+Fh]

  v23 &= ~1u;
  *(_QWORD *)v25 = 0;
  v4 = 0;
  *(_QWORD *)&v25[3] = 0;
  v5 = a2;
  v26 = 0;
  Src = 0;
  v21 = 0;
  v20[0] = 0;
  v24 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      424,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
  }
  if ( this->m_pAdapter->IsOperationalPowerState(this->m_pAdapter) )
  {
    v11 = ParseWdiIndicationDeviceServiceEventFromIhv(
            (unsigned int)(v5 - 48),
            a3 + 48,
            &this->m_pAdapter->m_TlvContext,
            &v23);
    v9 = v11;
    if ( v11 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_36;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        v13,
        426,
        (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
        (char)this,
        this->m_WfcPortId,
        v11);
      goto LABEL_32;
    }
    v14 = 32;
    if ( (v23 & 1) != 0 )
    {
      v15 = 0;
      v16 = CWabiToDot11Converter::CombineArrayOfByteArrays(&v25[1], &Src, &v21, v20);
      v9 = v16;
      if ( v16 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            1,
            427,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            v16);
        }
LABEL_28:
        if ( v20[0] )
          operator delete(Src);
        if ( v15 )
          operator delete(v15);
        goto LABEL_32;
      }
      v4 = v21;
      v14 = v21 + 32;
      if ( v21 >= 0xFFFFFFE0 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_DDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            1,
            428,
            (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
            v21,
            -1,
            1);
        }
        v9 = 1;
        goto LABEL_28;
      }
    }
    Pool2 = ExAllocatePool2(64, v14, 1198089303);
    v15 = (void *)Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)Pool2 = 2097536;
      *(_DWORD *)(Pool2 + 20) = v25[0];
      *(_OWORD *)(Pool2 + 4) = v24;
      if ( v4 )
      {
        v18 = Src;
        *(_DWORD *)(Pool2 + 28) = 32;
        *(_DWORD *)(Pool2 + 24) = v4;
        memmove((void *)(Pool2 + 32), v18, v4);
      }
      CAdapter::IndicateStatus(this->m_pAdapter, this->m_NdisPortNumber, 1073938479, 0, v15, v14);
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v10) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          v19,
          430,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
          (char)this,
          this->m_WfcPortId);
      }
    }
    else
    {
      v9 = -102;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          1,
          429,
          (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids);
      }
    }
    goto LABEL_28;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    goto LABEL_36;
  LOBYTE(v7) = 2;
  v9 = 0;
  WPP_RECORDER_SF_qD(
    WPP_GLOBAL_Control->DeviceExtension,
    v7,
    v8,
    425,
    (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
    (char)this,
    this->m_WfcPortId);
LABEL_32:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      431,
      (__int64)WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids,
      v9);
  }
LABEL_36:
  ArrayOfElements<ArrayOfElements<unsigned char>>::Cleanup(&v25[1]);
}

```

## disassembly

```asm
0x14006a118  mov     [rsp-8+arg_18], rbx
0x14006a11d  push    rbp
0x14006a11e  push    rsi
0x14006a11f  push    rdi
0x14006a120  push    r12
0x14006a122  push    r13
0x14006a124  push    r14
0x14006a126  push    r15
0x14006a128  lea     rbp, [rsp-27h]
0x14006a12d  sub     rsp, 90h
0x14006a134  mov     rax, cs:__security_cookie
0x14006a13b  xor     rax, rsp
0x14006a13e  mov     [rbp+57h+var_40], rax
0x14006a142  and     [rbp+57h+var_70], 0FFFFFFFEh
0x14006a146  xorps   xmm0, xmm0
0x14006a149  xor     r12d, r12d
0x14006a14c  mov     rdi, r8
0x14006a14f  mov     [rbp+57h+var_5C], r12
0x14006a153  mov     r14d, r12d
0x14006a156  mov     [rbp+57h+var_50], r12
0x14006a15a  mov     ebx, edx
0x14006a15c  mov     [rbp+57h+var_48], r12b
0x14006a160  mov     rsi, rcx
0x14006a163  mov     [rbp+57h+Src], r12
0x14006a167  mov     [rbp+57h+var_7C], r12d
0x14006a16b  mov     [rbp+57h+var_80], r12b
0x14006a16f  movups  [rbp+57h+var_6C], xmm0
0x14006a173  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14006a17a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14006a181  lea     r15, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14006a188  jz      short loc_14006A1BA
0x14006a18a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a191  cmp     byte ptr [rcx+29h], 5
0x14006a195  jnb     short loc_14006A19E
0x14006a197  cmp     [rcx+48h], r12w
0x14006a19c  jz      short loc_14006A1BA
0x14006a19e  mov     rcx, [rcx+40h]
0x14006a1a2  mov     r9d, 1A8h
0x14006a1a8  mov     r8d, 1
0x14006a1ae  mov     [rsp+0C0h+var_A0], r15
0x14006a1b3  mov     dl, 5
0x14006a1b5  call    WPP_RECORDER_SF_
0x14006a1ba  mov     rcx, [rsi+58h]
0x14006a1be  mov     rax, [rcx]
0x14006a1c1  mov     rax, [rax+10h]
0x14006a1c5  call    _guard_dispatch_icall
0x14006a1ca  test    al, al
0x14006a1cc  jnz     short loc_14006A20D
0x14006a1ce  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14006a1d5  jz      loc_14006A4A2
0x14006a1db  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a1e2  mov     r9d, 1A9h
0x14006a1e8  movzx   eax, word ptr [rsi+64h]
0x14006a1ec  mov     dl, 2
0x14006a1ee  mov     [rsp+0C0h+var_90], eax
0x14006a1f2  mov     edi, r12d
0x14006a1f5  mov     qword ptr [rsp+0C0h+var_98], rsi
0x14006a1fa  mov     rcx, [rcx+40h]
0x14006a1fe  mov     [rsp+0C0h+var_A0], r15
0x14006a203  call    WPP_RECORDER_SF_qD
0x14006a208  jmp     loc_14006A465
0x14006a20d  mov     r8, [rsi+58h]
0x14006a211  lea     rdx, [rdi+30h]
0x14006a215  add     r8, 3FF8h
0x14006a21c  lea     ecx, [rbx-30h]
0x14006a21f  lea     r9, [rbp+57h+var_70]
0x14006a223  call    ParseWdiIndicationDeviceServiceEventFromIhv
0x14006a228  mov     edi, eax
0x14006a22a  test    eax, eax
0x14006a22c  jz      short loc_14006A26E
0x14006a22e  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14006a235  jz      loc_14006A4A2
0x14006a23b  movzx   ecx, word ptr [rsi+64h]
0x14006a23f  mov     r9d, 1AAh
0x14006a245  mov     [rsp+0C0h+var_88], eax
0x14006a249  mov     dl, 2
0x14006a24b  mov     [rsp+0C0h+var_90], ecx
0x14006a24f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a256  mov     qword ptr [rsp+0C0h+var_98], rsi
0x14006a25b  mov     [rsp+0C0h+var_A0], r15
0x14006a260  mov     rcx, [rcx+40h]
0x14006a264  call    WPP_RECORDER_SF_qDD
0x14006a269  jmp     loc_14006A465
0x14006a26e  test    byte ptr [rbp+57h+var_70], 1
0x14006a272  mov     r15d, 20h ; ' '
0x14006a278  jz      loc_14006A33C
0x14006a27e  lea     r9, [rbp+57h+var_80]
0x14006a282  mov     rbx, r12
0x14006a285  lea     r8, [rbp+57h+var_7C]
0x14006a289  lea     rdx, [rbp+57h+Src]
0x14006a28d  lea     rcx, [rbp+57h+var_5C+4]
0x14006a291  call    ?CombineArrayOfByteArrays@CWabiToDot11Converter@@SAHPEAU?$ArrayOfElements@U?$ArrayOfElements@E@@@@PEAPEAEPEAIPEA_N@Z; CWabiToDot11Converter::CombineArrayOfByteArrays(ArrayOfElements<ArrayOfElements<uchar>> *,uchar * *,uint *,bool *)
0x14006a296  mov     edi, eax
0x14006a298  test    eax, eax
0x14006a29a  jz      short loc_14006A2DC
0x14006a29c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14006a2a3  lea     r15, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14006a2aa  jz      loc_14006A449
0x14006a2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a2b7  mov     r9d, 1ABh
0x14006a2bd  mov     [rsp+0C0h+var_98], eax
0x14006a2c1  mov     r8d, 1
0x14006a2c7  mov     dl, 2
0x14006a2c9  mov     [rsp+0C0h+var_A0], r15
0x14006a2ce  mov     rcx, [rcx+40h]
0x14006a2d2  call    WPP_RECORDER_SF_D
0x14006a2d7  jmp     loc_14006A449
0x14006a2dc  mov     r14d, [rbp+57h+var_7C]
0x14006a2e0  lea     r15d, [r14+20h]
0x14006a2e4  cmp     r15d, 20h ; ' '
0x14006a2e8  jnb     short loc_14006A33C
0x14006a2ea  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14006a2f1  lea     r15, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14006a2f8  jz      short loc_14006A332
0x14006a2fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a301  mov     r9d, 1ACh
0x14006a307  mov     [rsp+0C0h+var_88], 0C0000001h
0x14006a30f  mov     r8d, 1
0x14006a315  mov     [rsp+0C0h+var_90], 0FFFFFFFFh
0x14006a31d  mov     dl, 2
0x14006a31f  mov     [rsp+0C0h+var_98], r14d
0x14006a324  mov     rcx, [rcx+40h]
0x14006a328  mov     [rsp+0C0h+var_A0], r15
0x14006a32d  call    WPP_RECORDER_SF_DDD
0x14006a332  mov     edi, 0C0000001h
0x14006a337  jmp     loc_14006A449
0x14006a33c  mov     edx, r15d
0x14006a33f  mov     ecx, 40h ; '@'
0x14006a344  mov     r8d, 47696457h
0x14006a34a  call    cs:__imp_ExAllocatePool2
0x14006a351  nop     dword ptr [rax+rax+00h]
0x14006a356  mov     rbx, rax
0x14006a359  test    rax, rax
0x14006a35c  jnz     short loc_14006A39D
0x14006a35e  mov     edi, 0C000009Ah
0x14006a363  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14006a36a  lea     r15, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14006a371  jz      loc_14006A449
0x14006a377  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a37e  lea     r8d, [rax+1]
0x14006a382  mov     r9d, 1ADh
0x14006a388  mov     [rsp+0C0h+var_A0], r15
0x14006a38d  mov     dl, 2
0x14006a38f  mov     rcx, [rcx+40h]
0x14006a393  call    WPP_RECORDER_SF_
0x14006a398  jmp     loc_14006A449
0x14006a39d  mov     dword ptr [rax], 200180h
0x14006a3a3  mov     ecx, 20h ; ' '
0x14006a3a8  mov     eax, dword ptr [rbp+57h+var_5C]
0x14006a3ab  mov     [rbx+14h], eax
0x14006a3ae  mov     rax, qword ptr [rbp+57h+var_6C]
0x14006a3b2  mov     [rbx+4], rax
0x14006a3b6  mov     rax, qword ptr [rbp+57h+var_6C+8]
0x14006a3ba  mov     [rbx+0Ch], rax
0x14006a3be  test    r14d, r14d
0x14006a3c1  jz      short loc_14006A3DA
0x14006a3c3  mov     rdx, [rbp+57h+Src]; Src
0x14006a3c7  mov     [rbx+1Ch], ecx
0x14006a3ca  lea     rcx, [rbx+20h]; void *
0x14006a3ce  mov     r8d, r14d; Size
0x14006a3d1  mov     [rbx+18h], r14d
0x14006a3d5  call    memmove
0x14006a3da  mov     edx, [rsi+60h]; unsigned int
0x14006a3dd  xor     r9d, r9d; void *
0x14006a3e0  mov     rcx, [rsi+58h]; this
0x14006a3e4  mov     r8d, 4003002Fh; int
0x14006a3ea  mov     [rsp+0C0h+var_98], r15d; unsigned int
0x14006a3ef  mov     [rsp+0C0h+var_A0], rbx; void *
0x14006a3f4  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x14006a3f9  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14006a400  jz      short loc_14006A442
0x14006a402  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a409  cmp     byte ptr [rcx+29h], 5
0x14006a40d  jnb     short loc_14006A416
0x14006a40f  cmp     [rcx+48h], r12w
0x14006a414  jz      short loc_14006A442
0x14006a416  movzx   eax, word ptr [rsi+64h]
0x14006a41a  lea     r15, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14006a421  mov     rcx, [rcx+40h]
0x14006a425  mov     r9d, 1AEh
0x14006a42b  mov     [rsp+0C0h+var_90], eax
0x14006a42f  mov     dl, 5
0x14006a431  mov     qword ptr [rsp+0C0h+var_98], rsi
0x14006a436  mov     [rsp+0C0h+var_A0], r15
0x14006a43b  call    WPP_RECORDER_SF_qD
0x14006a440  jmp     short loc_14006A449
0x14006a442  lea     r15, WPP_9020e55d7b6a3fbfdf22f087f0ff8974_Traceguids
0x14006a449  cmp     [rbp+57h+var_80], r12b
0x14006a44d  jz      short loc_14006A458
0x14006a44f  mov     rcx, [rbp+57h+Src]; void *
0x14006a453  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006a458  test    rbx, rbx
0x14006a45b  jz      short loc_14006A465
0x14006a45d  mov     rcx, rbx; void *
0x14006a460  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006a465  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14006a46c  jz      short loc_14006A4A2
0x14006a46e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a475  cmp     byte ptr [rcx+29h], 5
0x14006a479  jnb     short loc_14006A482
0x14006a47b  cmp     [rcx+48h], r12w
0x14006a480  jz      short loc_14006A4A2
0x14006a482  mov     rcx, [rcx+40h]
0x14006a486  mov     r9d, 1AFh
0x14006a48c  mov     [rsp+0C0h+var_98], edi
0x14006a490  mov     r8d, 1
0x14006a496  mov     dl, 5
0x14006a498  mov     [rsp+0C0h+var_A0], r15
0x14006a49d  call    WPP_RECORDER_SF_D
0x14006a4a2  lea     rcx, [rbp+57h+var_5C+4]
0x14006a4a6  call    ?Cleanup@?$ArrayOfElements@U?$ArrayOfElements@E@@@@QEAAXXZ; ArrayOfElements<ArrayOfElements<uchar>>::Cleanup(void)
0x14006a4ab  mov     rcx, [rbp+57h+var_40]
0x14006a4af  xor     rcx, rsp; StackCookie
0x14006a4b2  call    __security_check_cookie
0x14006a4b7  mov     rbx, [rsp+0C0h+arg_18]
0x14006a4bf  add     rsp, 90h
0x14006a4c6  pop     r15
0x14006a4c8  pop     r14
0x14006a4ca  pop     r13
0x14006a4cc  pop     r12
0x14006a4ce  pop     rdi
0x14006a4cf  pop     rsi
0x14006a4d0  pop     rbp
0x14006a4d1  retn
```
