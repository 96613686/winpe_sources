# Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetElementData(uchar *,ulong,_SDP_ELEMENT_DATA *)

- ea: `0x180028ddc`
- end: `0x18002907b`
- name: `?BluetoothSdpGetElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAU_SDP_ELEMENT_DATA@@@Z`
- size: `671`
- prototype: `unsigned int __fastcall(Microsoft::Bluetooth::Services::BthServ *__hidden this, unsigned __int8 *, unsigned int, struct _SDP_ELEMENT_DATA *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028c44`
- `0x180028d24`

## callees

- `0x180028ddc`
- `0x180034008`
- `0x180034024`
- `0x180034034`
- `0x180034040`
- `0x180034050`
- `0x1800341f8`
- `0x18003427c`
- `0x18003428c`
- `0x180034298`
- `0x1800342dc`
- `0x180035f6c`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetElementData(
        Microsoft::Bluetooth::Services::BthServ *this,
        unsigned __int8 *a2,
        __int64 *a3,
        struct _SDP_ELEMENT_DATA *a4)
{
  __int64 *v4; // rdi
  unsigned int v6; // r10d
  unsigned __int8 v7; // cl
  unsigned __int8 v8; // dl
  unsigned __int8 v9; // cl
  int v10; // r15d
  _QWORD *v11; // rbx
  _BYTE *v12; // rsi
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  __int64 result; // rax
  int v20; // ecx
  __int128 v21; // [rsp+30h] [rbp-10h] BYREF
  int v22; // [rsp+70h] [rbp+30h] BYREF
  int v23; // [rsp+88h] [rbp+48h] BYREF

  v23 = 0;
  v22 = 0;
  v4 = a3;
  v21 = 0;
  if ( !this )
    return 87;
  if ( !(_DWORD)a2 )
    return 87;
  if ( !a3 )
    return 87;
  v6 = (_DWORD)a2 - 1;
  v7 = *(_BYTE *)this;
  v8 = v7 & 7;
  v9 = v7 >> 3;
  if ( v8 < 5u )
  {
    if ( v9 )
    {
      a3 = qword_18003CCF8;
      if ( v6 < *((_DWORD *)qword_18003CCF8 + v8) )
        return 87;
    }
  }
  v10 = v9;
  v11 = v4 + 1;
  *((_DWORD *)v4 + 1) = 0;
  v12 = (char *)this + 1;
  *(_OWORD *)(v4 + 1) = 0;
  if ( !v9 )
  {
    if ( !v8 )
      goto LABEL_55;
    return 87;
  }
  v13 = v9 - 1;
  if ( !v13 )
  {
    switch ( v8 )
    {
      case 0u:
        *((_DWORD *)v4 + 1) = 16;
        goto LABEL_17;
      case 1u:
        *((_DWORD *)v4 + 1) = 272;
        goto LABEL_32;
      case 2u:
        *((_DWORD *)v4 + 1) = 528;
        goto LABEL_30;
    }
    if ( v8 != 3 )
    {
      if ( v8 != 4 )
        return 87;
      *((_DWORD *)v4 + 1) = 1040;
      goto LABEL_39;
    }
    *((_DWORD *)v4 + 1) = 784;
LABEL_41:
    SdpRetrieveUint64((char *)this + 1, v4 + 1, a3, a4);
    *v11 = SdpByteSwapUint64(*v11);
    goto LABEL_55;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    switch ( v8 )
    {
      case 0u:
        *((_DWORD *)v4 + 1) = 32;
        goto LABEL_17;
      case 1u:
        *((_DWORD *)v4 + 1) = 288;
        goto LABEL_32;
      case 2u:
LABEL_29:
        *((_DWORD *)v4 + 1) = 544;
LABEL_30:
        SdpRetrieveUint32((char *)this + 1, v4 + 1);
        *(_DWORD *)v11 = SdpByteSwapUint32(*(unsigned int *)v11);
        goto LABEL_55;
    }
    if ( v8 != 3 )
    {
      if ( v8 != 4 )
        return 87;
      *((_DWORD *)v4 + 1) = 1056;
LABEL_39:
      SdpRetrieveUint128((char *)this + 1, v4 + 1, a3, a4);
      SdpByteSwapUint128(v4 + 1);
      goto LABEL_55;
    }
    *((_DWORD *)v4 + 1) = 800;
    goto LABEL_41;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    if ( v8 != 1 )
    {
      if ( v8 != 2 )
      {
        if ( v8 == 4 )
        {
          *((_DWORD *)v4 + 1) = 1072;
          SdpRetrieveUuid128((char *)this + 1, &v21, a3, a4);
          SdpByteSwapUuid128(&v21, v4 + 1);
          goto LABEL_55;
        }
        return 87;
      }
      goto LABEL_29;
    }
    *((_DWORD *)v4 + 1) = 304;
LABEL_32:
    SdpRetrieveUint16((char *)this + 1, v4 + 1, a3, a4);
    *(_WORD *)v11 = SdpByteSwapUint16(*(unsigned __int16 *)v11);
    goto LABEL_55;
  }
  v16 = v15 - 1;
  if ( !v16 )
    goto LABEL_18;
  v17 = v16 - 1;
  if ( !v17 )
  {
    if ( !v8 )
    {
LABEL_17:
      *(_BYTE *)v11 = *v12;
      goto LABEL_55;
    }
    return 87;
  }
  v18 = v17 - 1;
  if ( v18 && (unsigned int)(v18 - 1) >= 2 )
    return 87;
LABEL_18:
  LOBYTE(a3) = v8;
  if ( (int)SdpValidateVariableSize((int)this + 1, v6, (_DWORD)a3, (unsigned int)&v23, (__int64)&v22) < 0 )
    return 87;
  switch ( v10 )
  {
    case 4:
      goto LABEL_23;
    case 6:
    case 7:
      v20 = v23 + 1;
      *v11 = this;
      *((_DWORD *)v4 + 4) = v22 + v20;
      break;
    case 8:
LABEL_23:
      *v11 = &v12[v22];
      *((_DWORD *)v4 + 4) = v23;
      break;
  }
LABEL_55:
  result = 0;
  *(_DWORD *)v4 = v10;
  return result;
}

```

## disassembly

```asm
0x180028ddc  mov     [rsp-28h+arg_8], rbx
0x180028de1  push    rbp
0x180028de2  push    rsi
0x180028de3  push    rdi
0x180028de4  push    r14
0x180028de6  push    r15
0x180028de8  mov     rbp, rsp
0x180028deb  sub     rsp, 40h
0x180028def  mov     [rbp+arg_18], 0
0x180028df6  xorps   xmm0, xmm0
0x180028df9  mov     [rbp+arg_0], 0
0x180028e00  mov     rdi, r8
0x180028e03  mov     eax, edx
0x180028e05  mov     r14, rcx
0x180028e08  movups  [rbp+var_10], xmm0
0x180028e0c  test    rcx, rcx
0x180028e0f  jz      loc_180028E9F
0x180028e15  test    eax, eax
0x180028e17  jz      loc_180028E9F
0x180028e1d  test    r8, r8
0x180028e20  jz      short loc_180028E9F
0x180028e22  mov     dl, [rcx]
0x180028e24  lea     r10d, [rax-1]
0x180028e28  mov     cl, dl
0x180028e2a  and     dl, 7
0x180028e2d  shr     cl, 3
0x180028e30  cmp     dl, 5
0x180028e33  jnb     short loc_180028E49
0x180028e35  test    cl, cl
0x180028e37  jz      short loc_180028E49
0x180028e39  movzx   eax, dl
0x180028e3c  lea     r8, qword_18003CCF8
0x180028e43  cmp     r10d, [r8+rax*4]
0x180028e47  jb      short loc_180028E9F
0x180028e49  movzx   r15d, cl
0x180028e4d  lea     rbx, [rdi+8]
0x180028e51  mov     dword ptr [rdi+4], 0
0x180028e58  lea     rsi, [r14+1]
0x180028e5c  mov     ecx, r15d
0x180028e5f  movups  xmmword ptr [rbx], xmm0
0x180028e62  test    r15d, r15d
0x180028e65  jz      loc_180029069
0x180028e6b  sub     ecx, 1
0x180028e6e  jz      loc_180029014
0x180028e74  sub     ecx, 1
0x180028e77  jz      loc_180028F9F
0x180028e7d  sub     ecx, 1
0x180028e80  jz      loc_180028F23
0x180028e86  sub     ecx, 1
0x180028e89  jz      short loc_180028EC2
0x180028e8b  sub     ecx, 1
0x180028e8e  jz      short loc_180028EB5
0x180028e90  sub     ecx, 1
0x180028e93  jz      short loc_180028EC2
0x180028e95  sub     ecx, 1
0x180028e98  jz      short loc_180028EC2
0x180028e9a  cmp     ecx, 1
0x180028e9d  jz      short loc_180028EC2
0x180028e9f  mov     eax, 57h ; 'W'
0x180028ea4  mov     rbx, [rsp+40h+arg_8]
0x180028ea9  add     rsp, 40h
0x180028ead  pop     r15
0x180028eaf  pop     r14
0x180028eb1  pop     rdi
0x180028eb2  pop     rsi
0x180028eb3  pop     rbp
0x180028eb4  retn
0x180028eb5  test    dl, dl
0x180028eb7  jnz     short loc_180028E9F
0x180028eb9  mov     al, [rsi]
0x180028ebb  mov     [rbx], al
0x180028ebd  jmp     loc_180029071
0x180028ec2  lea     rax, [rbp+arg_0]
0x180028ec6  mov     r8b, dl
0x180028ec9  mov     edx, r10d
0x180028ecc  mov     [rsp+40h+var_20], rax
0x180028ed1  lea     r9, [rbp+arg_18]
0x180028ed5  mov     rcx, rsi
0x180028ed8  call    SdpValidateVariableSize
0x180028edd  test    eax, eax
0x180028edf  js      short loc_180028E9F
0x180028ee1  mov     ecx, r15d
0x180028ee4  sub     ecx, 4
0x180028ee7  jz      short loc_180028EFC
0x180028ee9  sub     ecx, 2
0x180028eec  jz      short loc_180028F10
0x180028eee  sub     ecx, 1
0x180028ef1  jz      short loc_180028F10
0x180028ef3  cmp     ecx, 1
0x180028ef6  jnz     loc_180029071
0x180028efc  mov     eax, [rbp+arg_0]
0x180028eff  add     rax, rsi
0x180028f02  mov     [rbx], rax
0x180028f05  mov     eax, [rbp+arg_18]
0x180028f08  mov     [rdi+10h], eax
0x180028f0b  jmp     loc_180029071
0x180028f10  mov     ecx, [rbp+arg_18]
0x180028f13  inc     ecx
0x180028f15  mov     [rbx], r14
0x180028f18  add     ecx, [rbp+arg_0]
0x180028f1b  mov     [rdi+10h], ecx
0x180028f1e  jmp     loc_180029071
0x180028f23  movzx   ecx, dl
0x180028f26  sub     ecx, 1
0x180028f29  jz      short loc_180028F7D
0x180028f2b  sub     ecx, 1
0x180028f2e  jz      short loc_180028F5D
0x180028f30  cmp     ecx, 2
0x180028f33  jnz     loc_180028E9F
0x180028f39  lea     rdx, [rbp+var_10]
0x180028f3d  mov     dword ptr [rdi+4], 430h
0x180028f44  mov     rcx, rsi
0x180028f47  call    SdpRetrieveUuid128
0x180028f4c  mov     rdx, rbx
0x180028f4f  lea     rcx, [rbp+var_10]
0x180028f53  call    SdpByteSwapUuid128
0x180028f58  jmp     loc_180029071
0x180028f5d  mov     dword ptr [rdi+4], 220h
0x180028f64  mov     rdx, rbx
0x180028f67  mov     rcx, rsi
0x180028f6a  call    SdpRetrieveUint32
0x180028f6f  mov     ecx, [rbx]
0x180028f71  call    SdpByteSwapUint32
0x180028f76  mov     [rbx], eax
0x180028f78  jmp     loc_180029071
0x180028f7d  mov     dword ptr [rdi+4], 130h
0x180028f84  mov     rdx, rbx
0x180028f87  mov     rcx, rsi
0x180028f8a  call    SdpRetrieveUint16
0x180028f8f  movzx   ecx, word ptr [rbx]
0x180028f92  call    SdpByteSwapUint16
0x180028f97  mov     [rbx], ax
0x180028f9a  jmp     loc_180029071
0x180028f9f  movzx   ecx, dl
0x180028fa2  test    dl, dl
0x180028fa4  jz      short loc_180029008
0x180028fa6  sub     ecx, 1
0x180028fa9  jz      short loc_180028FFC
0x180028fab  sub     ecx, 1
0x180028fae  jz      short loc_180028F5D
0x180028fb0  sub     ecx, 1
0x180028fb3  jz      short loc_180028FDD
0x180028fb5  cmp     ecx, 1
0x180028fb8  jnz     loc_180028E9F
0x180028fbe  mov     dword ptr [rdi+4], 420h
0x180028fc5  mov     rdx, rbx
0x180028fc8  mov     rcx, rsi
0x180028fcb  call    SdpRetrieveUint128
0x180028fd0  mov     rcx, rbx
0x180028fd3  call    SdpByteSwapUint128
0x180028fd8  jmp     loc_180029071
0x180028fdd  mov     dword ptr [rdi+4], 320h
0x180028fe4  mov     rdx, rbx
0x180028fe7  mov     rcx, rsi
0x180028fea  call    SdpRetrieveUint64
0x180028fef  mov     rcx, [rbx]
0x180028ff2  call    SdpByteSwapUint64
0x180028ff7  mov     [rbx], rax
0x180028ffa  jmp     short loc_180029071
0x180028ffc  mov     dword ptr [rdi+4], 120h
0x180029003  jmp     loc_180028F84
0x180029008  mov     dword ptr [rdi+4], 20h ; ' '
0x18002900f  jmp     loc_180028EB9
0x180029014  movzx   ecx, dl
0x180029017  test    dl, dl
0x180029019  jz      short loc_18002905D
0x18002901b  sub     ecx, 1
0x18002901e  jz      short loc_180029051
0x180029020  sub     ecx, 1
0x180029023  jz      short loc_180029045
0x180029025  sub     ecx, 1
0x180029028  jz      short loc_18002903C
0x18002902a  cmp     ecx, 1
0x18002902d  jnz     loc_180028E9F
0x180029033  mov     dword ptr [rdi+4], 410h
0x18002903a  jmp     short loc_180028FC5
0x18002903c  mov     dword ptr [rdi+4], 310h
0x180029043  jmp     short loc_180028FE4
0x180029045  mov     dword ptr [rdi+4], 210h
0x18002904c  jmp     loc_180028F64
0x180029051  mov     dword ptr [rdi+4], 110h
0x180029058  jmp     loc_180028F84
0x18002905d  mov     dword ptr [rdi+4], 10h
0x180029064  jmp     loc_180028EB9
0x180029069  test    dl, dl
0x18002906b  jnz     loc_180028E9F
0x180029071  xor     eax, eax
0x180029073  mov     [rdi], r15d
0x180029076  jmp     loc_180028EA4
```
