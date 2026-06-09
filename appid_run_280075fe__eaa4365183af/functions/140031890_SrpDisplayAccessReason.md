# SrpDisplayAccessReason

- ea: `0x140031890`
- end: `0x140031d83`
- name: `SrpDisplayAccessReason`
- size: `1267`
- prototype: `__int64 __usercall@<rax>(REGHANDLE RegHandle@<rcx>, PCUNICODE_STRING, HANDLE, char, char)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x140024280`
- `0x140031370`
- `0x1400315b0`

## callees

- `0x1400016a8`
- `0x1400016d8`
- `0x140001ee0`
- `0x140001f58`
- `0x140031890`
- `0x140031d90`
- `0x140032420`

## pseudocode

```c
void __fastcall SrpDisplayAccessReason(
        REGHANDLE RegHandle,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned int a4,
        UNICODE_STRING *a5,
        HANDLE a6,
        char a7,
        char a8)
{
  bool v8; // zf
  REGHANDLE v12; // r10
  __int64 *v13; // rax
  __int64 *v14; // rbx
  unsigned int v16; // eax
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 *v19; // r9
  unsigned __int16 *v20; // r8
  const EVENT_DESCRIPTOR *v21; // rdx
  REGHANDLE v22; // rcx
  unsigned int *p_Length; // rdx
  __int64 *v24; // [rsp+20h] [rbp-60h]
  __int64 *v25; // [rsp+28h] [rbp-58h]
  UNICODE_STRING *String2; // [rsp+30h] [rbp-50h]
  HANDLE TokenHandle; // [rsp+38h] [rbp-48h]
  char v28; // [rsp+40h] [rbp-40h]
  __int64 v29[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v30[2]; // [rsp+60h] [rbp-20h] BYREF
  __int128 v31; // [rsp+70h] [rbp-10h] BYREF
  PCUNICODE_STRING v33; // [rsp+D0h] [rbp+50h]

  v8 = (*(_BYTE *)(a2 + 24) & 1) == 0;
  *(_OWORD *)v30 = 0;
  v31 = 0;
  v12 = RegHandle;
  *(_OWORD *)v29 = 0;
  if ( v8 )
  {
    v14 = SrpProcessAudited;
    v13 = SrpAppxProcessAudited;
  }
  else
  {
    v13 = (__int64 *)&SrpAppxProcessDisabled;
    v14 = SrpProcessDisabled;
  }
  if ( a8 )
    v14 = v13;
  if ( a5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_ZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        (unsigned int)WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids,
        (_DWORD)a3,
        (__int64)a5);
LABEL_13:
      v12 = RegHandle;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids, a3);
    goto LABEL_13;
  }
  v16 = a4 & 0xFF0000;
  if ( (a4 & 0xFF0000) == 0x20000 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids);
      v12 = RegHandle;
    }
  }
  else
  {
    if ( v16 == 0x400000 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        v18 = 20;
        goto LABEL_62;
      }
      goto LABEL_64;
    }
    if ( v16 > 0x300000 )
    {
      switch ( v16 )
      {
        case 0x500000u:
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            v18 = 21;
            goto LABEL_62;
          }
          goto LABEL_64;
        case 0x600000u:
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            v18 = 22;
            goto LABEL_62;
          }
          goto LABEL_64;
        case 0x700000u:
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            v18 = 23;
            goto LABEL_62;
          }
          goto LABEL_64;
        case 0x800000u:
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            v18 = 24;
            goto LABEL_62;
          }
          goto LABEL_64;
      }
      goto LABEL_44;
    }
    if ( v16 == 3145728 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        v18 = 19;
        goto LABEL_62;
      }
      goto LABEL_64;
    }
    if ( !v16 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        v18 = 16;
        goto LABEL_62;
      }
      goto LABEL_64;
    }
    if ( v16 != 0x10000 )
    {
      if ( v16 == 0x100000 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          v18 = 17;
          goto LABEL_62;
        }
LABEL_64:
        v28 = a7;
        v19 = 0;
        v20 = a3;
        TokenHandle = a6;
        v21 = (const EVENT_DESCRIPTOR *)v14;
        String2 = a5;
        v22 = v12;
        v25 = 0;
        v24 = 0;
        if ( !a8 )
        {
          AiLogSrpRuleEvent(v12, (PCEVENT_DESCRIPTOR)v14, a3, 0, 0, 0, a5, a6, a7);
          return;
        }
        goto LABEL_86;
      }
      if ( v16 == 0x200000 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          v18 = 18;
LABEL_62:
          WPP_SF_(v17->AttachedDevice, v18, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids);
          goto LABEL_63;
        }
        goto LABEL_64;
      }
LABEL_44:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids, a4);
LABEL_63:
        v12 = RegHandle;
        goto LABEL_64;
      }
      goto LABEL_64;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids);
      v12 = RegHandle;
    }
    v14 = SrpProcessAllowed;
    if ( a8 )
      v14 = (__int64 *)&SrpAppxProcessAllowed;
  }
  p_Length = (unsigned int *)(a2 + 28LL * (unsigned __int16)a4 + *(unsigned int *)(a2 + 8));
  v33 = (PCUNICODE_STRING)p_Length;
  LOWORD(v30[0]) = *((_WORD *)p_Length + 6);
  WORD1(v30[0]) = v30[0];
  if ( LOWORD(v30[0]) )
  {
    v30[1] = a2 + p_Length[2];
    if ( v30[1]
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids, v30);
      v12 = RegHandle;
      p_Length = (unsigned int *)&v33->Length;
    }
  }
  else
  {
    v30[1] = 0;
  }
  LOWORD(v29[0]) = *((_WORD *)p_Length + 10);
  WORD1(v29[0]) = v29[0];
  if ( LOWORD(v29[0]) )
  {
    v29[1] = a2 + p_Length[4];
    if ( v29[1]
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids, v29);
      v12 = RegHandle;
      p_Length = (unsigned int *)&v33->Length;
    }
  }
  else
  {
    v29[1] = 0;
  }
  LOWORD(v31) = *((_WORD *)p_Length + 2);
  WORD1(v31) = v31;
  if ( (_WORD)v31 )
    *((_QWORD *)&v31 + 1) = a2 + *p_Length;
  else
    *((_QWORD *)&v31 + 1) = 0;
  _InterlockedIncrement((volatile signed __int32 *)p_Length + 6);
  v19 = (__int64 *)&v31;
  v28 = a7;
  v20 = a3;
  v21 = (const EVENT_DESCRIPTOR *)v14;
  TokenHandle = a6;
  String2 = a5;
  v22 = v12;
  v25 = v29;
  v24 = v30;
  if ( !a8 )
  {
    AiLogSrpRuleEvent(v12, (PCEVENT_DESCRIPTOR)v14, a3, (__int64 *)&v31, v30, v29, a5, a6, a7);
    return;
  }
LABEL_86:
  AiLogAppxSrpRuleEvent(v22, v21, v20, v19, v24, v25, &String2->Length, TokenHandle, v28);
}

```

## disassembly

```asm
0x140031890  mov     [rsp-28h+arg_10], rbx
0x140031895  mov     [rsp-28h+arg_18], rsi
0x14003189a  mov     [rsp-28h+arg_0], rcx
0x14003189f  push    rbp
0x1400318a0  push    rdi
0x1400318a1  push    r12
0x1400318a3  push    r13
0x1400318a5  push    r15
0x1400318a7  mov     rbp, rsp
0x1400318aa  sub     rsp, 80h
0x1400318b1  test    byte ptr [rdx+18h], 1
0x1400318b5  xorps   xmm0, xmm0
0x1400318b8  movzx   edi, [rbp+arg_38]
0x1400318bc  xorps   xmm1, xmm1
0x1400318bf  movups  xmmword ptr [rbp+var_20], xmm0
0x1400318c3  mov     r15d, r9d
0x1400318c6  mov     r13, r8
0x1400318c9  movups  [rbp+var_10], xmm1
0x1400318cd  mov     r12, rdx
0x1400318d0  mov     r10, rcx
0x1400318d3  movups  xmmword ptr [rbp+var_30], xmm0
0x1400318d7  jz      short loc_1400318E9
0x1400318d9  lea     rax, SrpAppxProcessDisabled
0x1400318e0  lea     rbx, SrpProcessDisabled
0x1400318e7  jmp     short loc_1400318F7
0x1400318e9  lea     rbx, SrpProcessAudited
0x1400318f0  lea     rax, SrpAppxProcessAudited
0x1400318f7  mov     rsi, [rbp+arg_20]
0x1400318fb  test    dil, dil
0x1400318fe  mov     [rsp+80h+arg_8], r14
0x140031906  cmovnz  rbx, rax
0x14003190a  test    rsi, rsi
0x14003190d  jz      short loc_14003194A
0x14003190f  mov     rcx, cs:WPP_GLOBAL_Control
0x140031916  lea     r14, WPP_GLOBAL_Control
0x14003191d  cmp     rcx, r14
0x140031920  jz      short loc_140031982
0x140031922  test    dword ptr [rcx+2Ch], 200h
0x140031929  jz      short loc_140031982
0x14003192b  mov     rcx, [rcx+18h]
0x14003192f  lea     r8, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids
0x140031936  mov     edx, 0Ch
0x14003193b  mov     [rsp+80h+var_60], rsi
0x140031940  mov     r9, r13
0x140031943  call    WPP_SF_ZZ
0x140031948  jmp     short loc_14003197E
0x14003194a  mov     rcx, cs:WPP_GLOBAL_Control
0x140031951  lea     r14, WPP_GLOBAL_Control
0x140031958  cmp     rcx, r14
0x14003195b  jz      short loc_140031982
0x14003195d  test    dword ptr [rcx+2Ch], 200h
0x140031964  jz      short loc_140031982
0x140031966  mov     rcx, [rcx+18h]
0x14003196a  lea     r8, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids
0x140031971  mov     edx, 0Dh
0x140031976  mov     r9, r13
0x140031979  call    WPP_SF_Z
0x14003197e  mov     r10, [rbp+arg_0]
0x140031982  mov     eax, r15d
0x140031985  and     eax, 0FF0000h
0x14003198a  cmp     eax, 20000h
0x14003198f  jz      loc_140031BFB
0x140031995  cmp     eax, 400000h
0x14003199a  jz      loc_140031B8C
0x1400319a0  cmp     eax, 300000h
0x1400319a5  ja      loc_140031AB6
0x1400319ab  jz      loc_140031A8F
0x1400319b1  test    eax, eax
0x1400319b3  jz      loc_140031A68
0x1400319b9  cmp     eax, 10000h
0x1400319be  jz      short loc_140031A20
0x1400319c0  cmp     eax, 100000h
0x1400319c5  jz      short loc_1400319F9
0x1400319c7  cmp     eax, 200000h
0x1400319cc  jnz     loc_140031ADA
0x1400319d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400319d9  cmp     rcx, r14
0x1400319dc  jz      loc_140031BBA
0x1400319e2  test    dword ptr [rcx+2Ch], 200h
0x1400319e9  jz      loc_140031BBA
0x1400319ef  mov     edx, 12h
0x1400319f4  jmp     loc_140031BA6
0x1400319f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a00  cmp     rcx, r14
0x140031a03  jz      loc_140031BBA
0x140031a09  test    dword ptr [rcx+2Ch], 200h
0x140031a10  jz      loc_140031BBA
0x140031a16  mov     edx, 11h
0x140031a1b  jmp     loc_140031BA6
0x140031a20  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a27  cmp     rcx, r14
0x140031a2a  jz      short loc_140031A4E
0x140031a2c  test    dword ptr [rcx+2Ch], 200h
0x140031a33  jz      short loc_140031A4E
0x140031a35  mov     rcx, [rcx+18h]
0x140031a39  lea     r8, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids
0x140031a40  mov     edx, 0Eh
0x140031a45  call    WPP_SF_
0x140031a4a  mov     r10, [rbp+arg_0]
0x140031a4e  test    dil, dil
0x140031a51  lea     rax, SrpAppxProcessAllowed
0x140031a58  lea     rbx, SrpProcessAllowed
0x140031a5f  cmovnz  rbx, rax
0x140031a63  jmp     loc_140031C29
0x140031a68  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a6f  cmp     rcx, r14
0x140031a72  jz      loc_140031BBA
0x140031a78  test    dword ptr [rcx+2Ch], 200h
0x140031a7f  jz      loc_140031BBA
0x140031a85  mov     edx, 10h
0x140031a8a  jmp     loc_140031BA6
0x140031a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a96  cmp     rcx, r14
0x140031a99  jz      loc_140031BBA
0x140031a9f  test    dword ptr [rcx+2Ch], 200h
0x140031aa6  jz      loc_140031BBA
0x140031aac  mov     edx, 13h
0x140031ab1  jmp     loc_140031BA6
0x140031ab6  cmp     eax, 500000h
0x140031abb  jz      loc_140031B70
0x140031ac1  cmp     eax, 600000h
0x140031ac6  jz      loc_140031B54
0x140031acc  cmp     eax, 700000h
0x140031ad1  jz      short loc_140031B38
0x140031ad3  cmp     eax, 800000h
0x140031ad8  jz      short loc_140031B14
0x140031ada  mov     rcx, cs:WPP_GLOBAL_Control
0x140031ae1  cmp     rcx, r14
0x140031ae4  jz      loc_140031BBA
0x140031aea  test    dword ptr [rcx+2Ch], 200h
0x140031af1  jz      loc_140031BBA
0x140031af7  mov     rcx, [rcx+18h]
0x140031afb  lea     r8, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids
0x140031b02  mov     edx, 19h
0x140031b07  mov     r9d, r15d
0x140031b0a  call    WPP_SF_D
0x140031b0f  jmp     loc_140031BB6
0x140031b14  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b1b  cmp     rcx, r14
0x140031b1e  jz      loc_140031BBA
0x140031b24  test    dword ptr [rcx+2Ch], 200h
0x140031b2b  jz      loc_140031BBA
0x140031b31  mov     edx, 18h
0x140031b36  jmp     short loc_140031BA6
0x140031b38  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b3f  cmp     rcx, r14
0x140031b42  jz      short loc_140031BBA
0x140031b44  test    dword ptr [rcx+2Ch], 200h
0x140031b4b  jz      short loc_140031BBA
0x140031b4d  mov     edx, 17h
0x140031b52  jmp     short loc_140031BA6
0x140031b54  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b5b  cmp     rcx, r14
0x140031b5e  jz      short loc_140031BBA
0x140031b60  test    dword ptr [rcx+2Ch], 200h
0x140031b67  jz      short loc_140031BBA
0x140031b69  mov     edx, 16h
0x140031b6e  jmp     short loc_140031BA6
0x140031b70  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b77  cmp     rcx, r14
0x140031b7a  jz      short loc_140031BBA
0x140031b7c  test    dword ptr [rcx+2Ch], 200h
0x140031b83  jz      short loc_140031BBA
0x140031b85  mov     edx, 15h
0x140031b8a  jmp     short loc_140031BA6
0x140031b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b93  cmp     rcx, r14
0x140031b96  jz      short loc_140031BBA
0x140031b98  test    dword ptr [rcx+2Ch], 200h
0x140031b9f  jz      short loc_140031BBA
0x140031ba1  mov     edx, 14h
0x140031ba6  mov     rcx, [rcx+18h]
0x140031baa  lea     r8, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids
0x140031bb1  call    WPP_SF_
0x140031bb6  mov     r10, [rbp+arg_0]
0x140031bba  mov     eax, dword ptr [rbp+arg_30]
0x140031bbd  xor     r15d, r15d
0x140031bc0  mov     dword ptr [rsp+80h+var_40], eax; char
0x140031bc4  xor     r9d, r9d
0x140031bc7  mov     rax, [rbp+arg_28]
0x140031bcb  mov     r8, r13
0x140031bce  mov     [rsp+80h+TokenHandle], rax; TokenHandle
0x140031bd3  mov     rdx, rbx; EventDescriptor
0x140031bd6  mov     [rsp+80h+String2], rsi; __int64
0x140031bdb  mov     rcx, r10; RegHandle
0x140031bde  mov     [rsp+80h+var_58], r15; __int64
0x140031be3  mov     [rsp+80h+var_60], r15; __int64
0x140031be8  test    dil, dil
0x140031beb  jnz     loc_140031D59
0x140031bf1  call    AiLogSrpRuleEvent
0x140031bf6  jmp     loc_140031D5E
0x140031bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140031c02  cmp     rcx, r14
0x140031c05  jz      short loc_140031C29
0x140031c07  test    dword ptr [rcx+2Ch], 200h
0x140031c0e  jz      short loc_140031C29
0x140031c10  mov     rcx, [rcx+18h]
0x140031c14  lea     r8, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids
0x140031c1b  mov     edx, 0Fh
0x140031c20  call    WPP_SF_
0x140031c25  mov     r10, [rbp+arg_0]
0x140031c29  mov     edx, [r12+8]
0x140031c2e  movzx   ecx, r15w
0x140031c32  xor     r15d, r15d
0x140031c35  imul    rax, rcx, 1Ch
0x140031c39  add     rax, r12
0x140031c3c  add     rdx, rax
0x140031c3f  mov     [rbp+arg_20], rdx
0x140031c43  movzx   eax, word ptr [rdx+0Ch]
0x140031c47  mov     word ptr [rbp+var_20], ax
0x140031c4b  mov     word ptr [rbp+var_20+2], ax
0x140031c4f  test    ax, ax
0x140031c52  jz      short loc_140031C98
0x140031c54  mov     ecx, [rdx+8]
0x140031c57  add     rcx, r12
0x140031c5a  mov     [rbp+var_20+8], rcx
0x140031c5e  jz      short loc_140031C9C
0x140031c60  mov     rcx, cs:WPP_GLOBAL_Control
0x140031c67  cmp     rcx, r14
0x140031c6a  jz      short loc_140031C9C
0x140031c6c  test    dword ptr [rcx+2Ch], 200h
0x140031c73  jz      short loc_140031C9C
0x140031c75  mov     rcx, [rcx+18h]
0x140031c79  lea     r9, [rbp+var_20]
0x140031c7d  mov     edx, 1Ah
0x140031c82  lea     r8, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids
0x140031c89  call    WPP_SF_Z
0x140031c8e  mov     r10, [rbp+arg_0]
0x140031c92  mov     rdx, [rbp+arg_20]
0x140031c96  jmp     short loc_140031C9C
0x140031c98  mov     [rbp+var_20+8], r15
0x140031c9c  movzx   eax, word ptr [rdx+14h]
0x140031ca0  mov     word ptr [rbp+var_30], ax
0x140031ca4  mov     word ptr [rbp+var_30+2], ax
0x140031ca8  test    ax, ax
0x140031cab  jz      short loc_140031CF1
0x140031cad  mov     ecx, [rdx+10h]
0x140031cb0  add     rcx, r12
0x140031cb3  mov     [rbp+var_30+8], rcx
0x140031cb7  jz      short loc_140031CF5
0x140031cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140031cc0  cmp     rcx, r14
0x140031cc3  jz      short loc_140031CF5
0x140031cc5  test    dword ptr [rcx+2Ch], 200h
0x140031ccc  jz      short loc_140031CF5
0x140031cce  mov     rcx, [rcx+18h]
0x140031cd2  lea     r9, [rbp+var_30]
0x140031cd6  mov     edx, 1Bh
0x140031cdb  lea     r8, WPP_33080b75deef3fb5316bbc69d46312e2_Traceguids
0x140031ce2  call    WPP_SF_Z
0x140031ce7  mov     r10, [rbp+arg_0]
0x140031ceb  mov     rdx, [rbp+arg_20]
0x140031cef  jmp     short loc_140031CF5
0x140031cf1  mov     [rbp+var_30+8], r15
0x140031cf5  movzx   eax, word ptr [rdx+4]
0x140031cf9  mov     word ptr [rbp+var_10], ax
0x140031cfd  mov     word ptr [rbp+var_10+2], ax
0x140031d01  test    ax, ax
0x140031d04  jz      short loc_140031D11
0x140031d06  mov     eax, [rdx]
0x140031d08  add     rax, r12
0x140031d0b  mov     qword ptr [rbp+var_10+8], rax
0x140031d0f  jmp     short loc_140031D15
0x140031d11  mov     qword ptr [rbp+var_10+8], r15
0x140031d15  lock inc dword ptr [rdx+18h]
0x140031d19  mov     eax, dword ptr [rbp+arg_30]
0x140031d1c  lea     r9, [rbp+var_10]
0x140031d20  mov     dword ptr [rsp+80h+var_40], eax; char
0x140031d24  mov     r8, r13
0x140031d27  mov     rax, [rbp+arg_28]
0x140031d2b  mov     rdx, rbx; EventDescriptor
0x140031d2e  mov     [rsp+80h+TokenHandle], rax; __int64
0x140031d33  lea     rax, [rbp+var_30]
0x140031d37  mov     [rsp+80h+String2], rsi; String2
0x140031d3c  mov     rcx, r10; RegHandle
0x140031d3f  mov     [rsp+80h+var_58], rax; __int64
0x140031d44  lea     rax, [rbp+var_20]
0x140031d48  mov     [rsp+80h+var_60], rax; __int64
0x140031d4d  test    dil, dil
0x140031d50  jnz     short loc_140031D59
0x140031d52  call    AiLogSrpRuleEvent
0x140031d57  jmp     short loc_140031D5E
0x140031d59  call    AiLogAppxSrpRuleEvent
0x140031d5e  mov     r14, [rsp+80h+arg_8]
0x140031d66  lea     r11, [rsp+80h+var_s0]
0x140031d6e  mov     rbx, [r11+40h]
0x140031d72  mov     rsi, [r11+48h]
0x140031d76  mov     rsp, r11
0x140031d79  pop     r15
0x140031d7b  pop     r13
0x140031d7d  pop     r12
0x140031d7f  pop     rdi
0x140031d80  pop     rbp
0x140031d81  retn
```
