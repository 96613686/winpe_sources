# CBroker::CSystemEventsBrokerSystemNotificationCallback(void *,ulong,void *)

- ea: `0x180003bc0`
- end: `0x180004035`
- name: `?CSystemEventsBrokerSystemNotificationCallback@CBroker@@YAKPEAXK0@Z`
- size: `1141`
- prototype: `__int64 __fastcall(CBroker *this, void *, unsigned __int8 *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x180003bc0`
- `0x180005a50`
- `0x18001cf50`
- `0x1800223e0`
- `0x180022434`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180003df4`
- `ntdll!RtlPublishWnfStateData` at `0x180003df4`

## pseudocode

```c
__int64 __fastcall CBroker::CSystemEventsBrokerSystemNotificationCallback(
        CBroker *this,
        void *a2,
        unsigned __int8 *a3,
        void *a4)
{
  _QWORD *v5; // rbx
  unsigned __int8 v7; // si
  char v8; // bp
  int v9; // ecx
  __int64 v10; // [rsp+30h] [rbp-1038h]
  _DWORD v11[1024]; // [rsp+40h] [rbp-1028h] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v10 = 0;
  if ( a3 )
  {
    v7 = 0;
    v8 = 0;
    if ( !memcmp_0(a3, &GUID_GLOBAL_USER_PRESENCE, 0x10u) )
    {
      v10 = 0x41840B3EA3BC6875LL;
      if ( *((_DWORD *)a3 + 5) )
      {
        if ( (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 4u )
        {
          WPP_SF_(v5[2], 45, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
          v5 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        if ( (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 4u )
        {
          WPP_SF_(v5[2], 44, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
          v5 = WPP_GLOBAL_Control;
        }
        v7 = 1;
      }
      v8 = 1;
    }
    if ( !memcmp_0(a3, &GUID_MONITOR_POWER_ON, 0x10u) )
    {
      v10 = 0x41840B3EA3BC7875LL;
      if ( *((_DWORD *)a3 + 5) )
      {
        if ( (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 4u )
        {
          WPP_SF_(v5[2], 47, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
          v5 = WPP_GLOBAL_Control;
        }
        v7 = 1;
      }
      else
      {
        if ( (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 4u )
        {
          WPP_SF_(v5[2], 46, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
          v5 = WPP_GLOBAL_Control;
        }
        v7 = 0;
      }
      v8 = 1;
    }
    if ( !memcmp_0(a3, &GUID_BATTERY_PERCENTAGE_REMAINING, 0x10u) )
    {
      v10 = 0x41840B3EA3BC5075LL;
      if ( (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 4u )
      {
        WPP_SF_d(v5[2], 48, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids, a3[20]);
        v5 = WPP_GLOBAL_Control;
      }
      v7 = a3[20];
      v8 = 1;
    }
    if ( !memcmp_0(a3, &GUID_ACDC_POWER_SOURCE, 0x10u) )
    {
      v10 = 0x41840B3EA3BC7075LL;
      if ( *((_DWORD *)a3 + 5) )
      {
        if ( (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 4u )
        {
          WPP_SF_(v5[2], 50, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
          v5 = WPP_GLOBAL_Control;
        }
        v7 = 0;
      }
      else
      {
        if ( (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 4u )
        {
          WPP_SF_(v5[2], 49, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
          v5 = WPP_GLOBAL_Control;
        }
        v7 = 1;
      }
      v8 = 1;
    }
    if ( !memcmp_0(a3, &GUID_LOW_POWER_EPOCH, 0x10u) )
    {
      v10 = 0x41840B3EA3BC9875LL;
      if ( *((_DWORD *)a3 + 5) == 1 )
      {
        if ( (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 4u )
          WPP_SF_(v5[2], 51, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
        v7 = 1;
      }
      else
      {
        if ( (*((_BYTE *)v5 + 28) & 0x10) != 0 && *((_BYTE *)v5 + 25) >= 4u )
          WPP_SF_(v5[2], 52, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
        v7 = 0;
      }
    }
    else if ( !v8 )
    {
      goto LABEL_6;
    }
    v11[1] = -1;
    v9 = 1;
    if ( v7 )
      v9 = 3;
    if ( v7 <= 1u )
      v11[0] = v9;
    else
      v11[0] = v9 | (v7 << 14);
    RtlPublishWnfStateData(v10, 0, v11, 8, 0);
    v5 = WPP_GLOBAL_Control;
  }
  else if ( (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 2u )
  {
    WPP_SF_(v5[2], 43, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
LABEL_6:
  if ( (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
    WPP_SF_(v5[2], 53, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180003bc0  push    rbx
0x180003bc2  mov     eax, 1060h
0x180003bc7  call    _alloca_probe
0x180003bcc  sub     rsp, rax
0x180003bcf  mov     rax, cs:__security_cookie
0x180003bd6  xor     rax, rsp
0x180003bd9  mov     [rsp+1068h+var_28], rax
0x180003be1  mov     [rsp+1068h+var_10], rdi
0x180003be9  mov     rdi, r8
0x180003bec  mov     [rsp+1068h+var_18], r14
0x180003bf4  mov     rbx, cs:WPP_GLOBAL_Control
0x180003bfb  test    byte ptr [rbx+1Ch], 1
0x180003bff  jz      short loc_180003C0B
0x180003c01  cmp     byte ptr [rbx+19h], 4
0x180003c05  jnb     loc_180003E35
0x180003c0b  xor     r14d, r14d
0x180003c0e  mov     [rsp+1068h+var_1038], r14
0x180003c13  test    rdi, rdi
0x180003c16  jnz     short loc_180003C57
0x180003c18  test    byte ptr [rbx+1Ch], 1
0x180003c1c  jnz     loc_180003EF0
0x180003c22  mov     r14, [rsp+1068h+var_18]
0x180003c2a  mov     rdi, [rsp+1068h+var_10]
0x180003c32  test    byte ptr [rbx+1Ch], 1
0x180003c36  jnz     loc_180003D5D
0x180003c3c  xor     eax, eax
0x180003c3e  mov     rcx, [rsp+1068h+var_28]
0x180003c46  xor     rcx, rsp; StackCookie
0x180003c49  call    __security_check_cookie
0x180003c4e  add     rsp, 1060h
0x180003c55  pop     rbx
0x180003c56  retn
0x180003c57  mov     [rsp+1068h+arg_0], rbp
0x180003c5f  lea     rdx, GUID_GLOBAL_USER_PRESENCE; Buf2
0x180003c66  mov     [rsp+1068h+arg_8], rsi
0x180003c6e  mov     r8d, 10h; Size
0x180003c74  mov     rcx, rdi; Buf1
0x180003c77  xor     sil, sil
0x180003c7a  xor     bpl, bpl
0x180003c7d  call    memcmp_0
0x180003c82  test    eax, eax
0x180003c84  jnz     short loc_180003CB6
0x180003c86  mov     dword ptr [rsp+1068h+var_1038], 0A3BC6875h
0x180003c8e  mov     dword ptr [rsp+1068h+var_1038+4], 41840B3Eh
0x180003c96  cmp     [rdi+14h], r14d
0x180003c9a  jnz     loc_180003E5C
0x180003ca0  test    byte ptr [rbx+1Ch], 10h
0x180003ca4  jz      short loc_180003CB0
0x180003ca6  cmp     byte ptr [rbx+19h], 4
0x180003caa  jnb     loc_180003F1B
0x180003cb0  mov     sil, 1
0x180003cb3  mov     bpl, 1
0x180003cb6  mov     r8d, 10h; Size
0x180003cbc  lea     rdx, GUID_MONITOR_POWER_ON; Buf2
0x180003cc3  mov     rcx, rdi; Buf1
0x180003cc6  call    memcmp_0
0x180003ccb  test    eax, eax
0x180003ccd  jz      loc_180003E06
0x180003cd3  mov     r8d, 10h; Size
0x180003cd9  lea     rdx, GUID_BATTERY_PERCENTAGE_REMAINING; Buf2
0x180003ce0  mov     rcx, rdi; Buf1
0x180003ce3  call    memcmp_0
0x180003ce8  test    eax, eax
0x180003cea  jnz     short loc_180003D0D
0x180003cec  mov     dword ptr [rsp+1068h+var_1038], 0A3BC5075h
0x180003cf4  mov     dword ptr [rsp+1068h+var_1038+4], 41840B3Eh
0x180003cfc  test    byte ptr [rbx+1Ch], 10h
0x180003d00  jnz     loc_180003EC0
0x180003d06  movzx   esi, byte ptr [rdi+14h]
0x180003d0a  mov     bpl, 1
0x180003d0d  mov     r8d, 10h; Size
0x180003d13  lea     rdx, GUID_ACDC_POWER_SOURCE; Buf2
0x180003d1a  mov     rcx, rdi; Buf1
0x180003d1d  call    memcmp_0
0x180003d22  test    eax, eax
0x180003d24  jz      loc_180003E91
0x180003d2a  mov     r8d, 10h; Size
0x180003d30  lea     rdx, GUID_LOW_POWER_EPOCH; Buf2
0x180003d37  mov     rcx, rdi; Buf1
0x180003d3a  call    memcmp_0
0x180003d3f  test    eax, eax
0x180003d41  jz      short loc_180003D81
0x180003d43  test    bpl, bpl
0x180003d46  jnz     short loc_180003DAE
0x180003d48  mov     rbp, [rsp+1068h+arg_0]
0x180003d50  mov     rsi, [rsp+1068h+arg_8]
0x180003d58  jmp     loc_180003C22
0x180003d5d  cmp     byte ptr [rbx+19h], 4
0x180003d61  jb      loc_180003C3C
0x180003d67  mov     rcx, [rbx+10h]
0x180003d6b  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003d72  mov     edx, 35h ; '5'
0x180003d77  call    WPP_SF_
0x180003d7c  jmp     loc_180003C3C
0x180003d81  cmp     dword ptr [rdi+14h], 1
0x180003d85  mov     dword ptr [rsp+1068h+var_1038], 0A3BC9875h
0x180003d8d  mov     dword ptr [rsp+1068h+var_1038+4], 41840B3Eh
0x180003d95  jnz     loc_18000400C
0x180003d9b  test    byte ptr [rbx+1Ch], 10h
0x180003d9f  jz      short loc_180003DAB
0x180003da1  cmp     byte ptr [rbx+19h], 4
0x180003da5  jnb     loc_180003FF2
0x180003dab  mov     sil, 1
0x180003dae  test    sil, sil
0x180003db1  mov     [rsp+1068h+var_1024], 0FFFFFFFFh
0x180003db9  mov     ecx, 1
0x180003dbe  mov     eax, 3
0x180003dc3  cmovnz  ecx, eax
0x180003dc6  cmp     sil, 1
0x180003dca  jbe     loc_180003E56
0x180003dd0  movzx   eax, sil
0x180003dd4  shl     eax, 0Eh
0x180003dd7  or      eax, ecx
0x180003dd9  mov     [rsp+1068h+var_1028], eax
0x180003ddd  mov     rcx, [rsp+1068h+var_1038]
0x180003de2  lea     r8, [rsp+1068h+var_1028]
0x180003de7  mov     r9d, 8
0x180003ded  mov     [rsp+1068h+var_1048], r14
0x180003df2  xor     edx, edx
0x180003df4  call    cs:__imp_RtlPublishWnfStateData
0x180003dfa  mov     rbx, cs:WPP_GLOBAL_Control
0x180003e01  jmp     loc_180003D48
0x180003e06  mov     dword ptr [rsp+1068h+var_1038], 0A3BC7875h
0x180003e0e  mov     dword ptr [rsp+1068h+var_1038+4], 41840B3Eh
0x180003e16  cmp     [rdi+14h], r14d
0x180003e1a  jz      loc_180003F3C
0x180003e20  test    byte ptr [rbx+1Ch], 10h
0x180003e24  jnz     loc_180003F6C
0x180003e2a  mov     sil, 1
0x180003e2d  mov     bpl, 1
0x180003e30  jmp     loc_180003CD3
0x180003e35  mov     rcx, [rbx+10h]
0x180003e39  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003e40  mov     edx, 2Ah ; '*'
0x180003e45  call    WPP_SF_
0x180003e4a  mov     rbx, cs:WPP_GLOBAL_Control
0x180003e51  jmp     loc_180003C0B
0x180003e56  mov     [rsp+1068h+var_1028], ecx
0x180003e5a  jmp     short loc_180003DDD
0x180003e5c  test    byte ptr [rbx+1Ch], 10h
0x180003e60  jz      loc_180003CB3
0x180003e66  cmp     byte ptr [rbx+19h], 4
0x180003e6a  jb      loc_180003CB3
0x180003e70  mov     rcx, [rbx+10h]
0x180003e74  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003e7b  mov     edx, 2Dh ; '-'
0x180003e80  call    WPP_SF_
0x180003e85  mov     rbx, cs:WPP_GLOBAL_Control
0x180003e8c  jmp     loc_180003CB3
0x180003e91  mov     dword ptr [rsp+1068h+var_1038], 0A3BC7075h
0x180003e99  mov     dword ptr [rsp+1068h+var_1038+4], 41840B3Eh
0x180003ea1  cmp     [rdi+14h], r14d
0x180003ea5  jnz     loc_180003FC2
0x180003eab  test    byte ptr [rbx+1Ch], 10h
0x180003eaf  jnz     loc_180003F97
0x180003eb5  mov     sil, 1
0x180003eb8  mov     bpl, 1
0x180003ebb  jmp     loc_180003D2A
0x180003ec0  cmp     byte ptr [rbx+19h], 4
0x180003ec4  jb      loc_180003D06
0x180003eca  movzx   r9d, byte ptr [rdi+14h]
0x180003ecf  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003ed6  mov     rcx, [rbx+10h]
0x180003eda  mov     edx, 30h ; '0'
0x180003edf  call    WPP_SF_d
0x180003ee4  mov     rbx, cs:WPP_GLOBAL_Control
0x180003eeb  jmp     loc_180003D06
0x180003ef0  cmp     byte ptr [rbx+19h], 2
0x180003ef4  jb      loc_180003C22
0x180003efa  mov     rcx, [rbx+10h]
0x180003efe  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003f05  mov     edx, 2Bh ; '+'
0x180003f0a  call    WPP_SF_
0x180003f0f  mov     rbx, cs:WPP_GLOBAL_Control
0x180003f16  jmp     loc_180003C22
0x180003f1b  mov     rcx, [rbx+10h]
0x180003f1f  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003f26  mov     edx, 2Ch ; ','
0x180003f2b  call    WPP_SF_
0x180003f30  mov     rbx, cs:WPP_GLOBAL_Control
0x180003f37  jmp     loc_180003CB0
0x180003f3c  test    byte ptr [rbx+1Ch], 10h
0x180003f40  jz      short loc_180003F64
0x180003f42  cmp     byte ptr [rbx+19h], 4
0x180003f46  jb      short loc_180003F64
0x180003f48  mov     rcx, [rbx+10h]
0x180003f4c  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003f53  mov     edx, 2Eh ; '.'
0x180003f58  call    WPP_SF_
0x180003f5d  mov     rbx, cs:WPP_GLOBAL_Control
0x180003f64  xor     sil, sil
0x180003f67  jmp     loc_180003E2D
0x180003f6c  cmp     byte ptr [rbx+19h], 4
0x180003f70  jb      loc_180003E2A
0x180003f76  mov     rcx, [rbx+10h]
0x180003f7a  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003f81  mov     edx, 2Fh ; '/'
0x180003f86  call    WPP_SF_
0x180003f8b  mov     rbx, cs:WPP_GLOBAL_Control
0x180003f92  jmp     loc_180003E2A
0x180003f97  cmp     byte ptr [rbx+19h], 4
0x180003f9b  jb      loc_180003EB5
0x180003fa1  mov     rcx, [rbx+10h]
0x180003fa5  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003fac  mov     edx, 31h ; '1'
0x180003fb1  call    WPP_SF_
0x180003fb6  mov     rbx, cs:WPP_GLOBAL_Control
0x180003fbd  jmp     loc_180003EB5
0x180003fc2  test    byte ptr [rbx+1Ch], 10h
0x180003fc6  jz      short loc_180003FEA
0x180003fc8  cmp     byte ptr [rbx+19h], 4
0x180003fcc  jb      short loc_180003FEA
0x180003fce  mov     rcx, [rbx+10h]
0x180003fd2  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003fd9  mov     edx, 32h ; '2'
0x180003fde  call    WPP_SF_
0x180003fe3  mov     rbx, cs:WPP_GLOBAL_Control
0x180003fea  xor     sil, sil
0x180003fed  jmp     loc_180003EB8
0x180003ff2  mov     rcx, [rbx+10h]
0x180003ff6  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180003ffd  mov     edx, 33h ; '3'
0x180004002  call    WPP_SF_
0x180004007  jmp     loc_180003DAB
0x18000400c  test    byte ptr [rbx+1Ch], 10h
0x180004010  jz      short loc_18000402D
0x180004012  cmp     byte ptr [rbx+19h], 4
0x180004016  jb      short loc_18000402D
0x180004018  mov     rcx, [rbx+10h]
0x18000401c  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x180004023  mov     edx, 34h ; '4'
0x180004028  call    WPP_SF_
0x18000402d  xor     sil, sil
0x180004030  jmp     loc_180003DAE
```
