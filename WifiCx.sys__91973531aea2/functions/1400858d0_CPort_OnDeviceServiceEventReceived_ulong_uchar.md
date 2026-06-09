# CPort::OnDeviceServiceEventReceived(ulong,uchar *)

- ea: `0x1400858d0`
- end: `0x140085c2e`
- name: `?OnDeviceServiceEventReceived@CPort@@QEAAXKPEAE@Z`
- size: `862`
- prototype: `void __fastcall(CPort *this, int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x140026010`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140020c84`
- `0x14003895c`
- `0x14004126c`
- `0x140050574`
- `0x14007378c`
- `0x1400858d0`
- `0x1400dfd00`
- `0x1400dfe00`

## pseudocode

```c
void __fastcall CPort::OnDeviceServiceEventReceived(CPort *this, int a2, unsigned __int8 *a3)
{
  unsigned int v4; // esi
  int v5; // ebx
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  char v10; // di
  int v11; // edx
  unsigned int v12; // r14d
  void *v13; // rbx
  int v14; // eax
  int v15; // r8d
  char *v16; // rax
  void *v17; // rdx
  int v18; // r8d
  _BYTE v19[4]; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v20; // [rsp+44h] [rbp-25h] BYREF
  void *Src; // [rsp+48h] [rbp-21h] BYREF
  int v22; // [rsp+50h] [rbp-19h] BYREF
  __int128 v23; // [rsp+54h] [rbp-15h]
  _DWORD v24[5]; // [rsp+64h] [rbp-5h] BYREF
  char v25; // [rsp+78h] [rbp+Fh]

  v22 &= ~1u;
  *(_QWORD *)v24 = 0;
  v4 = 0;
  *(_QWORD *)&v24[3] = 0;
  v5 = a2;
  v25 = 0;
  Src = 0;
  v20 = 0;
  v19[0] = 0;
  v23 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      353,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  v7 = ParseWdiIndicationDeviceServiceEventFromIhv(
         (unsigned int)(v5 - 48),
         a3 + 48,
         *((_QWORD *)this + 17) + 5384LL,
         &v22);
  v10 = v7;
  if ( !v7 )
  {
    v12 = 32;
    if ( (v22 & 1) != 0 )
    {
      v13 = 0;
      v14 = CWabiToDot11Converter::CombineArrayOfByteArrays(&v24[1], &Src, &v20, v19);
      v10 = v14;
      if ( v14 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            1,
            355,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            v14);
        }
LABEL_25:
        if ( v19[0] )
          operator delete(Src);
        if ( v13 )
          operator delete(v13);
        goto LABEL_29;
      }
      v4 = v20;
      v12 = v20 + 32;
      if ( v20 >= 0xFFFFFFE0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = 2;
          WPP_RECORDER_SF_dDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            v15,
            356,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            v20,
            -1,
            1);
        }
        v10 = 1;
        goto LABEL_25;
      }
    }
    v16 = (char *)operator new(v12);
    v13 = v16;
    if ( v16 )
    {
      *(_DWORD *)v16 = 2097536;
      *((_DWORD *)v16 + 5) = v24[0];
      *(_OWORD *)(v16 + 4) = v23;
      if ( v4 )
      {
        v17 = Src;
        *((_DWORD *)v16 + 7) = 32;
        *((_DWORD *)v16 + 6) = v4;
        memmove(v16 + 32, v17, v4);
      }
      CAdapter::IndicateStatus(*((CAdapter **)this + 17), *((_DWORD *)this + 36), 1073938479, 0, v13, v12);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v11) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v18,
          358,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
          (char)this,
          *((_WORD *)this + 74));
      }
    }
    else
    {
      v10 = -102;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          1,
          357,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
      }
    }
    goto LABEL_25;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_33;
  LOBYTE(v8) = 2;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    v8,
    v9,
    354,
    (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
    (char)this,
    *((_WORD *)this + 74),
    v7);
LABEL_29:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      1,
      359,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v10);
  }
LABEL_33:
  ArrayOfElements<ArrayOfElements<unsigned char>>::Cleanup(&v24[1]);
}

```

## disassembly

```asm
0x1400858d0  mov     [rsp-8+arg_18], rbx
0x1400858d5  push    rbp
0x1400858d6  push    rsi
0x1400858d7  push    rdi
0x1400858d8  push    r12
0x1400858da  push    r13
0x1400858dc  push    r14
0x1400858de  push    r15
0x1400858e0  lea     rbp, [rsp-27h]
0x1400858e5  sub     rsp, 90h
0x1400858ec  mov     rax, cs:__security_cookie
0x1400858f3  xor     rax, rsp
0x1400858f6  mov     [rbp+57h+var_40], rax
0x1400858fa  and     [rbp+57h+var_70], 0FFFFFFFEh
0x1400858fe  xorps   xmm0, xmm0
0x140085901  xor     r12d, r12d
0x140085904  mov     rdi, r8
0x140085907  mov     [rbp+57h+var_5C], r12
0x14008590b  mov     esi, r12d
0x14008590e  mov     [rbp+57h+var_50], r12
0x140085912  mov     ebx, edx
0x140085914  mov     [rbp+57h+var_48], r12b
0x140085918  mov     r15, rcx
0x14008591b  mov     [rbp+57h+Src], r12
0x14008591f  mov     [rbp+57h+var_7C], r12d
0x140085923  mov     [rbp+57h+var_80], r12b
0x140085927  movups  [rbp+57h+var_6C], xmm0
0x14008592b  lea     r13, WPP_RECORDER_INITIALIZED
0x140085932  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140085939  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140085940  jz      short loc_140085972
0x140085942  mov     rcx, cs:WPP_GLOBAL_Control
0x140085949  cmp     byte ptr [rcx+29h], 5
0x14008594d  jnb     short loc_140085956
0x14008594f  cmp     [rcx+48h], r12w
0x140085954  jz      short loc_140085972
0x140085956  mov     rcx, [rcx+40h]
0x14008595a  mov     r9d, 161h
0x140085960  mov     r8d, 1
0x140085966  mov     [rsp+0C0h+var_A0], r14
0x14008596b  mov     dl, 5
0x14008596d  call    WPP_RECORDER_SF_
0x140085972  mov     r8, [r15+88h]
0x140085979  lea     rdx, [rdi+30h]
0x14008597d  add     r8, 1508h
0x140085984  lea     ecx, [rbx-30h]
0x140085987  lea     r9, [rbp+57h+var_70]
0x14008598b  call    ParseWdiIndicationDeviceServiceEventFromIhv
0x140085990  mov     edi, eax
0x140085992  test    eax, eax
0x140085994  jz      short loc_1400859DA
0x140085996  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14008599d  jz      loc_140085BFD
0x1400859a3  movzx   ecx, word ptr [r15+94h]
0x1400859ab  mov     r9d, 162h
0x1400859b1  mov     [rsp+0C0h+var_88], eax
0x1400859b5  mov     dl, 2
0x1400859b7  mov     [rsp+0C0h+var_90], ecx
0x1400859bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400859c2  mov     qword ptr [rsp+0C0h+var_98], r15
0x1400859c7  mov     [rsp+0C0h+var_A0], r14
0x1400859cc  mov     rcx, [rcx+40h]
0x1400859d0  call    WPP_RECORDER_SF_qDD
0x1400859d5  jmp     loc_140085BC0
0x1400859da  test    byte ptr [rbp+57h+var_70], 1
0x1400859de  mov     r14d, 20h ; ' '
0x1400859e4  jz      loc_140085AA0
0x1400859ea  lea     r9, [rbp+57h+var_80]
0x1400859ee  mov     rbx, r12
0x1400859f1  lea     r8, [rbp+57h+var_7C]
0x1400859f5  lea     rdx, [rbp+57h+Src]
0x1400859f9  lea     rcx, [rbp+57h+var_5C+4]
0x1400859fd  call    ?CombineArrayOfByteArrays@CWabiToDot11Converter@@SAHPEAU?$ArrayOfElements@U?$ArrayOfElements@E@@@@PEAPEAEPEAIPEA_N@Z; CWabiToDot11Converter::CombineArrayOfByteArrays(ArrayOfElements<ArrayOfElements<uchar>> *,uchar * *,uint *,bool *)
0x140085a02  mov     edi, eax
0x140085a04  test    eax, eax
0x140085a06  jz      short loc_140085A48
0x140085a08  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140085a0f  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140085a16  jz      loc_140085BA4
0x140085a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140085a23  mov     r9d, 163h
0x140085a29  mov     [rsp+0C0h+var_98], eax
0x140085a2d  mov     r8d, 1
0x140085a33  mov     dl, 2
0x140085a35  mov     [rsp+0C0h+var_A0], r14
0x140085a3a  mov     rcx, [rcx+40h]
0x140085a3e  call    WPP_RECORDER_SF_d
0x140085a43  jmp     loc_140085BA4
0x140085a48  mov     esi, [rbp+57h+var_7C]
0x140085a4b  lea     r14d, [rsi+20h]
0x140085a4f  cmp     r14d, 20h ; ' '
0x140085a53  jnb     short loc_140085AA0
0x140085a55  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140085a5c  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140085a63  jz      short loc_140085A96
0x140085a65  mov     rcx, cs:WPP_GLOBAL_Control
0x140085a6c  mov     r9d, 164h
0x140085a72  mov     [rsp+0C0h+var_88], 0C0000001h
0x140085a7a  mov     dl, 2
0x140085a7c  mov     [rsp+0C0h+var_90], 0FFFFFFFFh
0x140085a84  mov     [rsp+0C0h+var_98], esi
0x140085a88  mov     rcx, [rcx+40h]
0x140085a8c  mov     [rsp+0C0h+var_A0], r14
0x140085a91  call    WPP_RECORDER_SF_dDd
0x140085a96  mov     edi, 0C0000001h
0x140085a9b  jmp     loc_140085BA4
0x140085aa0  mov     ecx, r14d; unsigned __int64
0x140085aa3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140085aa8  mov     rbx, rax
0x140085aab  test    rax, rax
0x140085aae  jnz     short loc_140085AEF
0x140085ab0  mov     edi, 0C000009Ah
0x140085ab5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140085abc  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140085ac3  jz      loc_140085BA4
0x140085ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x140085ad0  lea     r8d, [rax+1]
0x140085ad4  mov     r9d, 165h
0x140085ada  mov     [rsp+0C0h+var_A0], r14
0x140085adf  mov     dl, 2
0x140085ae1  mov     rcx, [rcx+40h]
0x140085ae5  call    WPP_RECORDER_SF_
0x140085aea  jmp     loc_140085BA4
0x140085aef  mov     dword ptr [rax], 200180h
0x140085af5  mov     ecx, 20h ; ' '
0x140085afa  mov     eax, dword ptr [rbp+57h+var_5C]
0x140085afd  mov     [rbx+14h], eax
0x140085b00  mov     rax, qword ptr [rbp+57h+var_6C]
0x140085b04  mov     [rbx+4], rax
0x140085b08  mov     rax, qword ptr [rbp+57h+var_6C+8]
0x140085b0c  mov     [rbx+0Ch], rax
0x140085b10  test    esi, esi
0x140085b12  jz      short loc_140085B2A
0x140085b14  mov     rdx, [rbp+57h+Src]; Src
0x140085b18  mov     [rbx+1Ch], ecx
0x140085b1b  lea     rcx, [rbx+20h]; void *
0x140085b1f  mov     r8d, esi; Size
0x140085b22  mov     [rbx+18h], esi
0x140085b25  call    memmove
0x140085b2a  mov     edx, [r15+90h]; unsigned int
0x140085b31  xor     r9d, r9d; void *
0x140085b34  mov     rcx, [r15+88h]; this
0x140085b3b  mov     r8d, 4003002Fh; int
0x140085b41  mov     [rsp+0C0h+var_98], r14d; unsigned int
0x140085b46  mov     [rsp+0C0h+var_A0], rbx; void *
0x140085b4b  call    ?IndicateStatus@CAdapter@@QEAAXKHPEAX0K@Z; CAdapter::IndicateStatus(ulong,int,void *,void *,ulong)
0x140085b50  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140085b57  jz      short loc_140085B9D
0x140085b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140085b60  cmp     byte ptr [rcx+29h], 5
0x140085b64  jnb     short loc_140085B6D
0x140085b66  cmp     [rcx+48h], r12w
0x140085b6b  jz      short loc_140085B9D
0x140085b6d  movzx   eax, word ptr [r15+94h]
0x140085b75  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140085b7c  mov     rcx, [rcx+40h]
0x140085b80  mov     r9d, 166h
0x140085b86  mov     [rsp+0C0h+var_90], eax
0x140085b8a  mov     dl, 5
0x140085b8c  mov     qword ptr [rsp+0C0h+var_98], r15
0x140085b91  mov     [rsp+0C0h+var_A0], r14
0x140085b96  call    WPP_RECORDER_SF_qD
0x140085b9b  jmp     short loc_140085BA4
0x140085b9d  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140085ba4  cmp     [rbp+57h+var_80], r12b
0x140085ba8  jz      short loc_140085BB3
0x140085baa  mov     rcx, [rbp+57h+Src]; void *
0x140085bae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140085bb3  test    rbx, rbx
0x140085bb6  jz      short loc_140085BC0
0x140085bb8  mov     rcx, rbx; void *
0x140085bbb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140085bc0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140085bc7  jz      short loc_140085BFD
0x140085bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140085bd0  cmp     byte ptr [rcx+29h], 5
0x140085bd4  jnb     short loc_140085BDD
0x140085bd6  cmp     [rcx+48h], r12w
0x140085bdb  jz      short loc_140085BFD
0x140085bdd  mov     rcx, [rcx+40h]
0x140085be1  mov     r9d, 167h
0x140085be7  mov     [rsp+0C0h+var_98], edi
0x140085beb  mov     r8d, 1
0x140085bf1  mov     dl, 5
0x140085bf3  mov     [rsp+0C0h+var_A0], r14
0x140085bf8  call    WPP_RECORDER_SF_d
0x140085bfd  lea     rcx, [rbp+57h+var_5C+4]
0x140085c01  call    ?Cleanup@?$ArrayOfElements@U?$ArrayOfElements@E@@@@QEAAXXZ; ArrayOfElements<ArrayOfElements<uchar>>::Cleanup(void)
0x140085c06  mov     rcx, [rbp+57h+var_40]
0x140085c0a  xor     rcx, rsp; StackCookie
0x140085c0d  call    __security_check_cookie
0x140085c12  mov     rbx, [rsp+0C0h+arg_18]
0x140085c1a  add     rsp, 90h
0x140085c21  pop     r15
0x140085c23  pop     r14
0x140085c25  pop     r13
0x140085c27  pop     r12
0x140085c29  pop     rdi
0x140085c2a  pop     rsi
0x140085c2b  pop     rbp
0x140085c2c  retn
```
