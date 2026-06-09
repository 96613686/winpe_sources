# Apx::ApfDevice::RemoveDevice(void)

- ea: `0x18000ff54`
- end: `0x1800101c3`
- name: `?RemoveDevice@ApfDevice@Apx@@AEAAXXZ`
- size: `623`
- prototype: `void __fastcall(unsigned __int64 this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f830`

## callees

- `0x18000163c`
- `0x180001d30`
- `0x180009d28`
- `0x18000a12c`
- `0x18000c19c`
- `0x18000ff54`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x180010142`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x180010142`

## pseudocode

```c
void __fastcall Apx::ApfDevice::RemoveDevice(unsigned __int64 this)
{
  __int64 v2; // r10
  const unsigned __int16 *v3; // rax
  __int64 v4; // rcx
  int v5; // ecx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned __int64 v8; // [rsp+30h] [rbp-39h] BYREF
  __int64 v9; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v10[32]; // [rsp+40h] [rbp-29h] BYREF
  __int64 *v11; // [rsp+60h] [rbp-9h]
  __int64 v12; // [rsp+68h] [rbp-1h]
  char *v13; // [rsp+70h] [rbp+7h]
  __int64 v14; // [rsp+78h] [rbp+Fh]
  const unsigned __int16 *v15; // [rsp+80h] [rbp+17h]
  int v16; // [rsp+88h] [rbp+1Fh]
  int v17; // [rsp+8Ch] [rbp+23h]
  unsigned __int64 *v18; // [rsp+90h] [rbp+27h]
  __int64 v19; // [rsp+98h] [rbp+2Fh]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  v2 = *((_QWORD *)ApxTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v2 > 4u
    && (*(_QWORD *)(v2 + 16) & 0x400000000001LL) != 0
    && (*(_QWORD *)(v2 + 24) & 0x400000000001LL) == *(_QWORD *)(v2 + 24) )
  {
    v9 = 2048;
    v19 = 8;
    v8 = ~this;
    v3 = (const unsigned __int16 *)(this + 328);
    v18 = &v8;
    if ( this == -328 )
    {
      v3 = &qword_18002C8D0;
      v5 = 2;
    }
    else
    {
      v4 = -1;
      do
        ++v4;
      while ( v3[v4] );
      v5 = 2 * v4 + 2;
    }
    v15 = v3;
    v16 = v5;
    v11 = &v9;
    v13 = (char *)(this + 120);
    v17 = 0;
    v14 = 16;
    v12 = 8;
    ((void (__fastcall *)(__int64, __int16 *, _QWORD, _QWORD, int, _BYTE *, unsigned __int64, __int64))tlgWriteTransfer_EventWriteTransfer)(
      v2,
      &word_18002E366,
      0,
      0,
      6,
      v10,
      v8,
      v9);
  }
  if ( *(_BYTE *)(this + 16) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( *(_QWORD *)(this + 24) )
    {
      Apx::ApfRpc::RemoveDevice_Rpc((void **)(this + 24));
      *(_QWORD *)(this + 24) = 0;
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
      {
        v7 = 33;
LABEL_35:
        WPP_SF_(v6[2], v7, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
        v6 = WPP_GLOBAL_Control;
        goto LABEL_36;
      }
      goto LABEL_36;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( *(_QWORD *)(this + 24) )
    {
      SwDeviceClose(*(_QWORD *)(this + 24));
      *(_QWORD *)(this + 24) = 0;
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
      {
        v7 = 31;
        goto LABEL_35;
      }
LABEL_36:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
        WPP_SF_(v6[2], 29, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x18000ff54  mov     [rsp-8+arg_8], rbx
0x18000ff59  mov     [rsp-8+arg_10], rdi
0x18000ff5e  push    rbp
0x18000ff5f  push    r12
0x18000ff61  push    r15
0x18000ff63  lea     rbp, [rsp-47h]
0x18000ff68  sub     rsp, 0B0h
0x18000ff6f  mov     rax, cs:__security_cookie
0x18000ff76  xor     rax, rsp
0x18000ff79  mov     [rbp+57h+var_20], rax
0x18000ff7d  mov     rbx, rcx
0x18000ff80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff87  lea     r15, WPP_GLOBAL_Control
0x18000ff8e  lea     r12, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000ff95  cmp     rcx, r15
0x18000ff98  jz      short loc_18000FFB7
0x18000ff9a  test    byte ptr [rcx+1Ch], 1
0x18000ff9e  jz      short loc_18000FFB7
0x18000ffa0  cmp     byte ptr [rcx+19h], 5
0x18000ffa4  jb      short loc_18000FFB7
0x18000ffa6  mov     rcx, [rcx+10h]
0x18000ffaa  mov     edx, 1Ch
0x18000ffaf  mov     r8, r12
0x18000ffb2  call    WPP_SF_
0x18000ffb7  call    ?Instance@ApxTelemetryProvider@@KAPEAV1@XZ; ApxTelemetryProvider::Instance(void)
0x18000ffbc  xor     edi, edi
0x18000ffbe  mov     r10, [rax+8]
0x18000ffc2  mov     eax, [r10]
0x18000ffc5  cmp     eax, 4
0x18000ffc8  jbe     loc_180010098
0x18000ffce  mov     rcx, [r10+18h]
0x18000ffd2  mov     rdx, 400000000001h
0x18000ffdc  mov     rax, [r10+10h]
0x18000ffe0  test    rdx, rax
0x18000ffe3  jz      loc_180010098
0x18000ffe9  mov     rax, rcx
0x18000ffec  and     rax, rdx
0x18000ffef  cmp     rax, rcx
0x18000fff2  jnz     loc_180010098
0x18000fff8  mov     rax, rbx
0x18000fffb  mov     [rbp+57h+var_88], 800h
0x180010003  not     rax
0x180010006  mov     [rbp+57h+var_28], 8
0x18001000e  mov     [rbp+57h+var_90], rax
0x180010012  lea     rcx, [rbp+57h+var_90]
0x180010016  lea     rax, [rbx+148h]
0x18001001d  mov     [rbp+57h+var_30], rcx
0x180010021  lea     rdx, [rbx+78h]
0x180010025  test    rax, rax
0x180010028  jz      short loc_180010040
0x18001002a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001002e  inc     rcx
0x180010031  cmp     [rax+rcx*2], di
0x180010035  jnz     short loc_18001002E
0x180010037  lea     ecx, ds:2[rcx*2]
0x18001003e  jmp     short loc_18001004C
0x180010040  lea     rax, qword_18002C8D0
0x180010047  mov     ecx, 2
0x18001004c  mov     [rbp+57h+var_40], rax
0x180010050  xor     r9d, r9d
0x180010053  lea     rax, [rbp+57h+var_88]
0x180010057  mov     [rbp+57h+var_38], ecx
0x18001005a  mov     [rbp+57h+var_60], rax
0x18001005e  xor     r8d, r8d
0x180010061  lea     rax, [rbp+57h+var_80]
0x180010065  mov     [rbp+57h+var_50], rdx
0x180010069  mov     [rsp+0C0h+var_98], rax
0x18001006e  lea     rdx, word_18002E366
0x180010075  mov     rcx, r10
0x180010078  mov     [rsp+0C0h+var_A0], 6
0x180010080  mov     [rbp+57h+var_34], edi
0x180010083  mov     [rbp+57h+var_48], 10h
0x18001008b  mov     [rbp+57h+var_58], 8
0x180010093  call    _tlgWriteTransfer_EventWriteTransfer
0x180010098  cmp     [rbx+10h], dil
0x18001009c  jz      short loc_180010108
0x18001009e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100a5  cmp     rcx, r15
0x1800100a8  jz      short loc_1800100CE
0x1800100aa  test    byte ptr [rcx+1Ch], 1
0x1800100ae  jz      short loc_1800100CE
0x1800100b0  cmp     byte ptr [rcx+19h], 5
0x1800100b4  jb      short loc_1800100CE
0x1800100b6  mov     rcx, [rcx+10h]
0x1800100ba  mov     edx, 20h ; ' '
0x1800100bf  mov     r8, r12
0x1800100c2  call    WPP_SF_
0x1800100c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100ce  cmp     [rbx+18h], rdi
0x1800100d2  jz      short loc_1800100E8
0x1800100d4  lea     rcx, [rbx+18h]; void **
0x1800100d8  call    ?RemoveDevice_Rpc@ApfRpc@Apx@@SAXPEAPEAX@Z; Apx::ApfRpc::RemoveDevice_Rpc(void * *)
0x1800100dd  mov     [rbx+18h], rdi
0x1800100e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100e8  cmp     rcx, r15
0x1800100eb  jz      loc_18001019E
0x1800100f1  test    byte ptr [rcx+1Ch], 1
0x1800100f5  jz      loc_18001017C
0x1800100fb  cmp     byte ptr [rcx+19h], 5
0x1800100ff  jb      short loc_18001017C
0x180010101  mov     edx, 21h ; '!'
0x180010106  jmp     short loc_180010169
0x180010108  mov     rcx, cs:WPP_GLOBAL_Control
0x18001010f  cmp     rcx, r15
0x180010112  jz      short loc_180010138
0x180010114  test    byte ptr [rcx+1Ch], 1
0x180010118  jz      short loc_180010138
0x18001011a  cmp     byte ptr [rcx+19h], 5
0x18001011e  jb      short loc_180010138
0x180010120  mov     rcx, [rcx+10h]
0x180010124  mov     edx, 1Eh
0x180010129  mov     r8, r12
0x18001012c  call    WPP_SF_
0x180010131  mov     rcx, cs:WPP_GLOBAL_Control
0x180010138  cmp     [rbx+18h], rdi
0x18001013c  jz      short loc_180010153
0x18001013e  mov     rcx, [rbx+18h]
0x180010142  call    cs:__imp_SwDeviceClose
0x180010148  mov     [rbx+18h], rdi
0x18001014c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010153  cmp     rcx, r15
0x180010156  jz      short loc_18001019E
0x180010158  test    byte ptr [rcx+1Ch], 1
0x18001015c  jz      short loc_18001017C
0x18001015e  cmp     byte ptr [rcx+19h], 5
0x180010162  jb      short loc_18001017C
0x180010164  mov     edx, 1Fh
0x180010169  mov     rcx, [rcx+10h]
0x18001016d  mov     r8, r12
0x180010170  call    WPP_SF_
0x180010175  mov     rcx, cs:WPP_GLOBAL_Control
0x18001017c  cmp     rcx, r15
0x18001017f  jz      short loc_18001019E
0x180010181  test    byte ptr [rcx+1Ch], 1
0x180010185  jz      short loc_18001019E
0x180010187  cmp     byte ptr [rcx+19h], 5
0x18001018b  jb      short loc_18001019E
0x18001018d  mov     rcx, [rcx+10h]
0x180010191  mov     edx, 1Dh
0x180010196  mov     r8, r12
0x180010199  call    WPP_SF_
0x18001019e  mov     rcx, [rbp+57h+var_20]
0x1800101a2  xor     rcx, rsp; StackCookie
0x1800101a5  call    __security_check_cookie
0x1800101aa  lea     r11, [rsp+0C0h+var_10]
0x1800101b2  mov     rbx, [r11+28h]
0x1800101b6  mov     rdi, [r11+30h]
0x1800101ba  mov     rsp, r11
0x1800101bd  pop     r15
0x1800101bf  pop     r12
0x1800101c1  pop     rbp
0x1800101c2  retn
```
