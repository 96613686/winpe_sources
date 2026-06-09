# CPort::SendResponseToServiceQueryInitialRequest(CServicesManager *,_WDI_MAC_ADDRESS *,_WDI_BSS_ENTRY_CHANNEL_INFO *,ulong,_DOT11_ANQP_ACTION_FRAME *)

- ea: `0x14002e080`
- end: `0x14002e5dd`
- name: `?SendResponseToServiceQueryInitialRequest@CPort@@QEAAXPEAVCServicesManager@@PEAU_WDI_MAC_ADDRESS@@PEAU_WDI_BSS_ENTRY_CHANNEL_INFO@@KPEAU_DOT11_ANQP_ACTION_FRAME@@@Z`
- size: `1373`
- prototype: `void __fastcall(CPort *__hidden this, struct CServicesManager *, struct _WDI_MAC_ADDRESS *, struct _WDI_BSS_ENTRY_CHANNEL_INFO *, unsigned int, struct _DOT11_ANQP_ACTION_FRAME *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400889f0`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14001a630`
- `0x140024a20`
- `0x14002b148`
- `0x14002e080`
- `0x14002ea0c`
- `0x14002ec58`
- `0x140050574`
- `0x140054ed8`
- `0x1400db5b4`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CPort::SendResponseToServiceQueryInitialRequest(
        CPort *this,
        struct CServicesManager *a2,
        struct _WDI_MAC_ADDRESS *a3,
        struct _WDI_BSS_ENTRY_CHANNEL_INFO *a4,
        unsigned int a5,
        struct _DOT11_ANQP_ACTION_FRAME *a6)
{
  struct _DOT11_ANQP_ACTION_FRAME *v6; // rsi
  char v8; // cl
  unsigned int v9; // edx
  unsigned int v10; // r14d
  bool v11; // zf
  int PortIdForPortType; // eax
  int v13; // edx
  char v14; // cl
  int v15; // r9d
  __int64 (__fastcall ***v16)(_QWORD); // rcx
  CPropertyCache *v17; // rax
  int PropertyBuffer; // eax
  int v19; // eax
  int v20; // edx
  int v21; // r14d
  void *v22; // rax
  unsigned __int8 *v23; // rdi
  int v24; // r9d
  int v25; // edx
  int v26; // r8d
  __int64 v27; // r9
  __int64 v28; // r8
  int v29; // edx
  char v30; // [rsp+28h] [rbp-58h]
  char v31; // [rsp+28h] [rbp-58h]
  unsigned int v32; // [rsp+60h] [rbp-20h]
  unsigned __int8 *v33; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int8 *v34; // [rsp+70h] [rbp-10h] BYREF
  CServicesManager *v35; // [rsp+C8h] [rbp+48h]
  struct _WDI_MAC_ADDRESS *v36; // [rsp+D0h] [rbp+50h]

  v36 = a3;
  v35 = a2;
  v6 = a6;
  v33 = 0;
  v34 = 0;
  v8 = *((_BYTE *)a6 + 6);
  if ( v8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        230,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        *((_BYTE *)a6 + 3),
        v8);
    }
    goto LABEL_4;
  }
  v9 = a5;
  v10 = *((unsigned __int8 *)a6 + 7) + (*((unsigned __int8 *)a6 + 8) << 8);
  v32 = v10;
  if ( a5 < v10 + 9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        (_DWORD)a3,
        231,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        a5,
        *((_BYTE *)a6 + 7) + 9);
    }
    return;
  }
  v11 = *((_DWORD *)this + 38) == 8;
  LOWORD(a6) = *((_WORD *)this + 74);
  if ( v11 )
  {
    PortIdForPortType = CAdapter::GetPortIdForPortType(*((_QWORD *)this + 17), 4, &a6);
    v14 = PortIdForPortType;
    if ( PortIdForPortType )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v15 = 232;
      goto LABEL_12;
    }
  }
  v16 = (__int64 (__fastcall ***)(_QWORD))(*((_QWORD *)this + 17) + 8LL);
  LODWORD(a6) = 0;
  v17 = (CPropertyCache *)(**v16)(v16);
  PropertyBuffer = CPropertyCache::GetPropertyBuffer(v17, 0x3Bu, (unsigned int *)&a6, &v33);
  v14 = PropertyBuffer;
  if ( PropertyBuffer )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return;
    v15 = 233;
LABEL_12:
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      1,
      v15,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v14);
    return;
  }
  if ( (unsigned int)a6 < 0x28
    || (v13 = (int)v33,
        (unsigned int)a6 < *((unsigned int *)v33 + 4)
                         + 40LL
                         + *((unsigned int *)v33 + 7)
                         + (unsigned __int64)*((unsigned int *)v33 + 9)) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return;
    v24 = 234;
    v30 = (char)a6;
    goto LABEL_42;
  }
  LODWORD(a6) = 0;
  v19 = WFDSvcEncodeANQPResponse(v10, (__int64)&a6, 0);
  v21 = (int)a6;
  if ( v19 == -1073741789 && (_DWORD)a6 )
  {
    if ( (unsigned int)a6 > 0xFFFF )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = 2;
        WPP_RECORDER_SF_Ld(
          WPP_GLOBAL_Control->DeviceExtension,
          v20,
          (_DWORD)a3,
          236,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
          (char)a6,
          255);
      }
      goto LABEL_4;
    }
    v22 = operator new((unsigned int)a6);
    wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(&v34, v22);
    v23 = v34;
    if ( !v34 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v24 = 237;
      v30 = v21;
LABEL_42:
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        1,
        v24,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        v30);
      return;
    }
    LODWORD(a6) = v21;
    v25 = WFDSvcEncodeANQPResponse(v32, (__int64)&a6, v34);
    if ( v25 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v31 = v25;
        LOBYTE(v25) = 2;
        WPP_RECORDER_SF_dDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v25,
          v26,
          238,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
          v31,
          v21,
          (char)a6);
      }
    }
    else
    {
      v28 = (unsigned int)a6;
      if ( (unsigned int)a6 >= *((unsigned __int16 *)v35 + 14) )
      {
        if ( CServicesManager::AddComebackResponseContext(
               v35,
               v36,
               *((_BYTE *)v6 + 2),
               (struct _DOT11_ANQP_ACTION_FRAME *)((char *)v6 + 3),
               (unsigned __int16)a6,
               v23) )
        {
LABEL_4:
          LOBYTE(a4) = *((_BYTE *)v6 + 6);
          LOBYTE(a3) = *((_BYTE *)v6 + 2);
          CPort::SendANQPQueryResponse(this, 11, a3, a4);
          return;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v29) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v29,
            1,
            239,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            154);
        }
      }
      else
      {
        LOBYTE(v27) = *((_BYTE *)v6 + 6);
        LOBYTE(v28) = *((_BYTE *)v6 + 2);
        CPort::SendANQPQueryResponse(this, 11, v28, v27);
      }
    }
    if ( v23 )
      operator delete(v23);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v20) = 2;
    WPP_RECORDER_SF_Ld(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      (_DWORD)a3,
      235,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v19,
      (char)a6);
  }
}

```

## disassembly

```asm
0x14002e080  mov     [rsp-38h+arg_0], rbx
0x14002e085  mov     [rsp-38h+arg_10], r8
0x14002e08a  mov     [rsp-38h+arg_8], rdx
0x14002e08f  push    rbp
0x14002e090  push    rsi
0x14002e091  push    rdi
0x14002e092  push    r12
0x14002e094  push    r13
0x14002e096  push    r14
0x14002e098  push    r15
0x14002e09a  mov     rbp, rsp
0x14002e09d  sub     rsp, 80h
0x14002e0a4  mov     rsi, [rbp+arg_28]
0x14002e0a8  xor     r12d, r12d
0x14002e0ab  mov     r15, rcx
0x14002e0ae  mov     [rbp+var_18], r12
0x14002e0b2  mov     r13, r9
0x14002e0b5  mov     [rbp+var_10], r12
0x14002e0b9  mov     rdi, r8
0x14002e0bc  mov     bl, r12b
0x14002e0bf  movzx   ecx, byte ptr [rsi+6]
0x14002e0c3  test    cl, cl
0x14002e0c5  jz      loc_14002E158
0x14002e0cb  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e0d2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e0d9  jz      short loc_14002E10D
0x14002e0db  mov     eax, ecx
0x14002e0dd  mov     r9d, 0E6h
0x14002e0e3  movzx   ecx, byte ptr [rsi+3]
0x14002e0e7  mov     dl, 2
0x14002e0e9  mov     [rsp+80h+var_50], eax
0x14002e0ed  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14002e0f4  mov     dword ptr [rsp+80h+var_58], ecx
0x14002e0f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e0ff  mov     qword ptr [rsp+80h+var_60], rax
0x14002e104  mov     rcx, [rcx+40h]
0x14002e108  call    WPP_RECORDER_SF_Ld
0x14002e10d  mov     eax, [r13+0]
0x14002e111  mov     [rsp+80h+var_28], r12
0x14002e116  mov     [rsp+80h+var_30], r12w
0x14002e11c  mov     [rsp+80h+var_38], eax
0x14002e120  mov     eax, [r13+4]
0x14002e124  mov     [rsp+80h+var_40], eax
0x14002e128  mov     [rsp+80h+var_48], rdi
0x14002e12d  mov     word ptr [rsp+80h+var_50], r12w
0x14002e133  mov     byte ptr [rsp+80h+var_58], bl
0x14002e137  mov     [rsp+80h+var_60], 3Bh ; ';'
0x14002e13e  mov     r9b, [rsi+6]
0x14002e142  mov     edx, 0Bh
0x14002e147  mov     r8b, [rsi+2]
0x14002e14b  mov     rcx, r15
0x14002e14e  call    ?SendANQPQueryResponse@CPort@@QEAAHW4_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE@@EEGTDOT11_ANQP_FRAGMENT_ID@@GPEAU_WDI_MAC_ADDRESS@@W4_WDI_BAND_ID@@IGPEAE@Z; CPort::SendANQPQueryResponse(_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE,uchar,uchar,ushort,DOT11_ANQP_FRAGMENT_ID,ushort,_WDI_MAC_ADDRESS *,_WDI_BAND_ID,uint,ushort,uchar *)
0x14002e153  jmp     loc_14002E5C1
0x14002e158  movzx   r14d, byte ptr [rsi+8]
0x14002e15d  movzx   eax, byte ptr [rsi+7]
0x14002e161  mov     edx, [rbp+arg_20]
0x14002e164  shl     r14d, 8
0x14002e168  add     r14d, eax
0x14002e16b  mov     [rbp+var_20], r14d
0x14002e16f  lea     ecx, [r14+9]
0x14002e173  cmp     edx, ecx
0x14002e175  jnb     short loc_14002E1BC
0x14002e177  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e17e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e185  jz      loc_14002E5C1
0x14002e18b  mov     [rsp+80h+var_50], ecx
0x14002e18f  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14002e196  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e19d  mov     r9d, 0E7h
0x14002e1a3  mov     dword ptr [rsp+80h+var_58], edx
0x14002e1a7  mov     dl, 2
0x14002e1a9  mov     qword ptr [rsp+80h+var_60], rax
0x14002e1ae  mov     rcx, [rcx+40h]
0x14002e1b2  call    WPP_RECORDER_SF_Ld
0x14002e1b7  jmp     loc_14002E5C1
0x14002e1bc  cmp     dword ptr [r15+98h], 8
0x14002e1c4  movzx   edx, word ptr [r15+94h]
0x14002e1cc  mov     word ptr [rbp+arg_28], dx
0x14002e1d0  jnz     short loc_14002E238
0x14002e1d2  mov     rcx, [r15+88h]
0x14002e1d9  lea     r8, [rbp+arg_28]
0x14002e1dd  mov     edx, 4
0x14002e1e2  call    ?GetPortIdForPortType@CAdapter@@QEAAHW4_WFC_PORT_TYPE@@PEAG@Z; CAdapter::GetPortIdForPortType(_WFC_PORT_TYPE,ushort *)
0x14002e1e7  mov     ecx, eax
0x14002e1e9  test    eax, eax
0x14002e1eb  jz      short loc_14002E234
0x14002e1ed  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e1f4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e1fb  jz      loc_14002E5C1
0x14002e201  mov     r9d, 0E8h
0x14002e207  mov     dword ptr [rsp+80h+var_58], ecx
0x14002e20b  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14002e212  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e219  mov     r8d, 1
0x14002e21f  mov     dl, 2
0x14002e221  mov     qword ptr [rsp+80h+var_60], rax
0x14002e226  mov     rcx, [rcx+40h]
0x14002e22a  call    WPP_RECORDER_SF_d
0x14002e22f  jmp     loc_14002E5C1
0x14002e234  movzx   edx, word ptr [rbp+arg_28]
0x14002e238  mov     rcx, [r15+88h]
0x14002e23f  add     rcx, 8
0x14002e243  mov     dword ptr [rbp+arg_28], r12d
0x14002e247  mov     rax, [rcx]
0x14002e24a  mov     rax, [rax]
0x14002e24d  call    _guard_dispatch_icall
0x14002e252  lea     r9, [rbp+var_18]; unsigned __int8 **
0x14002e256  mov     edx, 3Bh ; ';'; unsigned int
0x14002e25b  lea     r8, [rbp+arg_28]; unsigned int *
0x14002e25f  mov     rcx, rax; this
0x14002e262  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x14002e267  mov     ecx, eax
0x14002e269  test    eax, eax
0x14002e26b  jz      short loc_14002E28C
0x14002e26d  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e274  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e27b  jz      loc_14002E5C1
0x14002e281  mov     r9d, 0E9h
0x14002e287  jmp     loc_14002E207
0x14002e28c  mov     r12d, dword ptr [rbp+arg_28]
0x14002e290  cmp     r12d, 28h ; '('
0x14002e294  jb      loc_14002E582
0x14002e29a  mov     rdx, [rbp+var_18]
0x14002e29e  mov     eax, [rdx+1Ch]
0x14002e2a1  mov     ecx, [rdx+24h]
0x14002e2a4  add     rcx, rax
0x14002e2a7  mov     eax, [rdx+10h]
0x14002e2aa  add     rax, 28h ; '('
0x14002e2ae  add     rcx, rax
0x14002e2b1  cmp     r12, rcx
0x14002e2b4  jb      loc_14002E582
0x14002e2ba  lea     rcx, [rbp+arg_28]
0x14002e2be  mov     [rsp+80h+var_58], 0; unsigned __int8 *
0x14002e2c7  mov     qword ptr [rsp+80h+var_60], rcx; __int64
0x14002e2cc  mov     r9, rdx
0x14002e2cf  mov     ecx, r14d; unsigned int
0x14002e2d2  mov     dword ptr [rbp+arg_28], 0
0x14002e2d9  mov     r8d, r12d
0x14002e2dc  lea     rdx, [rsi+9]
0x14002e2e0  call    WFDSvcEncodeANQPResponse
0x14002e2e5  mov     r14d, dword ptr [rbp+arg_28]
0x14002e2e9  mov     ecx, eax
0x14002e2eb  cmp     eax, 0C0000023h
0x14002e2f0  jnz     loc_14002E543
0x14002e2f6  test    r14d, r14d
0x14002e2f9  jz      loc_14002E543
0x14002e2ff  mov     ecx, 0FFFFh
0x14002e304  cmp     r14d, ecx
0x14002e307  jbe     short loc_14002E37E
0x14002e309  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e310  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e317  jz      short loc_14002E346
0x14002e319  mov     [rsp+80h+var_50], ecx
0x14002e31d  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14002e324  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e32b  mov     r9d, 0ECh
0x14002e331  mov     dword ptr [rsp+80h+var_58], r14d
0x14002e336  mov     dl, 2
0x14002e338  mov     qword ptr [rsp+80h+var_60], rax
0x14002e33d  mov     rcx, [rcx+40h]
0x14002e341  call    WPP_RECORDER_SF_Ld
0x14002e346  xor     eax, eax
0x14002e348  mov     [rsp+80h+var_28], rax
0x14002e34d  xor     ecx, ecx
0x14002e34f  mov     [rsp+80h+var_30], ax
0x14002e354  mov     eax, [r13+0]
0x14002e358  mov     [rsp+80h+var_38], eax
0x14002e35c  mov     eax, [r13+4]
0x14002e360  mov     [rsp+80h+var_40], eax
0x14002e364  mov     [rsp+80h+var_48], rdi
0x14002e369  mov     word ptr [rsp+80h+var_50], cx
0x14002e36e  mov     byte ptr [rsp+80h+var_58], bl
0x14002e372  mov     [rsp+80h+var_60], 3Fh ; '?'
0x14002e379  jmp     loc_14002E13E
0x14002e37e  mov     rcx, r14; unsigned __int64
0x14002e381  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002e386  mov     rdx, rax
0x14002e389  lea     rcx, [rbp+var_10]
0x14002e38d  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x14002e392  mov     rdi, [rbp+var_10]
0x14002e396  test    rdi, rdi
0x14002e399  jnz     short loc_14002E3BF
0x14002e39b  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e3a2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e3a9  jz      loc_14002E5C1
0x14002e3af  mov     r9d, 0EDh
0x14002e3b5  mov     dword ptr [rsp+80h+var_58], r14d
0x14002e3ba  jmp     loc_14002E59D
0x14002e3bf  mov     r9, [rbp+var_18]
0x14002e3c3  lea     rax, [rbp+arg_28]
0x14002e3c7  mov     ecx, [rbp+var_20]; unsigned int
0x14002e3ca  lea     rdx, [rsi+9]
0x14002e3ce  mov     [rsp+80h+var_58], rdi; unsigned __int8 *
0x14002e3d3  mov     r8d, r12d
0x14002e3d6  mov     qword ptr [rsp+80h+var_60], rax; __int64
0x14002e3db  mov     dword ptr [rbp+arg_28], r14d
0x14002e3df  call    WFDSvcEncodeANQPResponse
0x14002e3e4  mov     edx, eax
0x14002e3e6  test    eax, eax
0x14002e3e8  jz      short loc_14002E444
0x14002e3ea  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e3f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e3f8  jz      short loc_14002E42E
0x14002e3fa  mov     ecx, dword ptr [rbp+arg_28]
0x14002e3fd  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14002e404  mov     dword ptr [rsp+80h+var_48], ecx
0x14002e408  mov     r9d, 0EEh
0x14002e40e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e415  mov     [rsp+80h+var_50], r14d
0x14002e41a  mov     dword ptr [rsp+80h+var_58], edx
0x14002e41e  mov     dl, 2
0x14002e420  mov     qword ptr [rsp+80h+var_60], rax
0x14002e425  mov     rcx, [rcx+40h]
0x14002e429  call    WPP_RECORDER_SF_dDd
0x14002e42e  test    rdi, rdi
0x14002e431  jz      loc_14002E5C1
0x14002e437  mov     rcx, rdi; void *
0x14002e43a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002e43f  jmp     loc_14002E5C1
0x14002e444  mov     rcx, [rbp+arg_8]; this
0x14002e448  mov     r8d, dword ptr [rbp+arg_28]
0x14002e44c  mov     r14, [rbp+arg_10]
0x14002e450  movzx   eax, word ptr [rcx+1Ch]
0x14002e454  cmp     r8d, eax
0x14002e457  jnb     short loc_14002E4A0
0x14002e459  mov     eax, [r13+0]
0x14002e45d  xor     ecx, ecx
0x14002e45f  mov     r9b, [rsi+6]
0x14002e463  xor     edx, edx
0x14002e465  mov     [rsp+80h+var_28], rdi
0x14002e46a  mov     [rsp+80h+var_30], r8w
0x14002e470  mov     r8b, [rsi+2]
0x14002e474  mov     [rsp+80h+var_38], eax
0x14002e478  mov     eax, [r13+4]
0x14002e47c  mov     [rsp+80h+var_40], eax
0x14002e480  mov     [rsp+80h+var_48], r14
0x14002e485  mov     word ptr [rsp+80h+var_50], cx
0x14002e48a  mov     byte ptr [rsp+80h+var_58], bl
0x14002e48e  mov     [rsp+80h+var_60], dx
0x14002e493  lea     edx, [rcx+0Bh]
0x14002e496  mov     rcx, r15
0x14002e499  call    ?SendANQPQueryResponse@CPort@@QEAAHW4_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE@@EEGTDOT11_ANQP_FRAGMENT_ID@@GPEAU_WDI_MAC_ADDRESS@@W4_WDI_BAND_ID@@IGPEAE@Z; CPort::SendANQPQueryResponse(_DOT11_ACTION_FRAME_PUBLIC_ACTION_TYPE,uchar,uchar,ushort,DOT11_ANQP_FRAGMENT_ID,ushort,_WDI_MAC_ADDRESS *,_WDI_BAND_ID,uint,ushort,uchar *)
0x14002e49e  jmp     short loc_14002E42E
0x14002e4a0  mov     [rsp+80h+var_58], rdi; unsigned __int8 *
0x14002e4a5  lea     r9, [rsi+3]; struct _DOT11_AVERTISEMENT_PROTOCOL_ELEMENT *
0x14002e4a9  mov     [rsp+80h+var_60], r8w; unsigned __int16
0x14002e4af  mov     rdx, r14; struct _WDI_MAC_ADDRESS *
0x14002e4b2  mov     r8b, [rsi+2]; unsigned __int8
0x14002e4b6  call    ?AddComebackResponseContext@CServicesManager@@QEAAPEAVCServiceComebackResponseContext@@PEAU_WDI_MAC_ADDRESS@@EPEAU_DOT11_AVERTISEMENT_PROTOCOL_ELEMENT@@GPEAE@Z; CServicesManager::AddComebackResponseContext(_WDI_MAC_ADDRESS *,uchar,_DOT11_AVERTISEMENT_PROTOCOL_ELEMENT *,ushort,uchar *)
0x14002e4bb  test    rax, rax
0x14002e4be  jnz     short loc_14002E50B
0x14002e4c0  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e4c7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e4ce  jz      loc_14002E42E
0x14002e4d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e4db  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14002e4e2  mov     r9d, 0EFh
0x14002e4e8  mov     dword ptr [rsp+80h+var_58], 0C000009Ah
0x14002e4f0  mov     r8d, 1
0x14002e4f6  mov     qword ptr [rsp+80h+var_60], rax
0x14002e4fb  mov     dl, 2
0x14002e4fd  mov     rcx, [rcx+40h]
0x14002e501  call    WPP_RECORDER_SF_d
0x14002e506  jmp     loc_14002E42E
0x14002e50b  xor     eax, eax
0x14002e50d  mov     [rsp+80h+var_28], rax
0x14002e512  xor     ecx, ecx
0x14002e514  mov     [rsp+80h+var_30], ax
0x14002e519  mov     eax, [r13+0]
0x14002e51d  mov     [rsp+80h+var_38], eax
0x14002e521  mov     eax, [r13+4]
0x14002e525  mov     [rsp+80h+var_40], eax
0x14002e529  mov     [rsp+80h+var_48], r14
0x14002e52e  mov     word ptr [rsp+80h+var_50], 1
0x14002e535  mov     byte ptr [rsp+80h+var_58], bl
0x14002e539  mov     [rsp+80h+var_60], cx
0x14002e53e  jmp     loc_14002E13E
0x14002e543  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e54a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e551  jz      short loc_14002E5C1
0x14002e553  mov     [rsp+80h+var_50], r14d
0x14002e558  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14002e55f  mov     dword ptr [rsp+80h+var_58], ecx
0x14002e563  mov     r9d, 0EBh
0x14002e569  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e570  mov     dl, 2
0x14002e572  mov     qword ptr [rsp+80h+var_60], rax
0x14002e577  mov     rcx, [rcx+40h]
0x14002e57b  call    WPP_RECORDER_SF_Ld
0x14002e580  jmp     short loc_14002E5C1
0x14002e582  lea     rax, WPP_RECORDER_INITIALIZED
0x14002e589  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e590  jz      short loc_14002E5C1
0x14002e592  mov     r9d, 0EAh
0x14002e598  mov     dword ptr [rsp+80h+var_58], r12d
0x14002e59d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e5a4  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14002e5ab  mov     r8d, 1
0x14002e5b1  mov     qword ptr [rsp+80h+var_60], rax
0x14002e5b6  mov     dl, 2
  ... truncated ...
```
