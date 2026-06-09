# IssueCommandHS

- ea: `0x140009c10`
- end: `0x140009fd8`
- name: `IssueCommandHS`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000a2b8`

## callees

- `0x140001020`
- `0x140004adc`
- `0x140007cc0`
- `0x140007ee4`
- `0x140009a88`
- `0x140009b78`
- `0x140009c10`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140009d1c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140009d1c`

## pseudocode

```c
__int64 __fastcall IssueCommandHS(_QWORD *a1, __int64 a2, _OWORD *a3, __int64 a4, __int64 a5, char a6)
{
  int NextFree; // ebx
  unsigned __int16 v11; // dx
  __int64 v12; // rdi
  __int16 v13; // r13
  char v14; // r15
  char v15; // al
  char v16; // si
  __int16 v17; // bx
  int Default; // eax
  int v19; // edx
  __int64 v20; // r10
  bool v21; // cf
  __int64 v22; // r8
  int v23; // eax
  __int64 *v24; // rax
  bool v25; // cf
  __int64 v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  unsigned __int16 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rdx
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rax
  __int64 v34; // rax
  int v35; // eax
  __int64 v37; // [rsp+50h] [rbp-58h]
  unsigned __int16 v38; // [rsp+B0h] [rbp+8h] BYREF

  v38 = 0;
  a5 = a1[13];
  NextFree = QueueFindNextFree(a1, &v38, a2, 0);
  if ( NextFree >= 0 )
  {
    v11 = v38;
    v12 = a1[147] + 224LL * v38;
    v13 = __ROR2__(v38 + 1, 8);
    *(_QWORD *)(v12 + 160) = a4;
    v14 = a6;
    *(_BYTE *)(v12 + 201) = a6;
    *(_DWORD *)(v12 + 8) = 1;
    *(_DWORD *)(v12 + 12) = 1;
    *(_DWORD *)(v12 + 20) = 1;
    *(_DWORD *)(v12 + 16) = 1;
    *(_QWORD *)(v12 + 32) = a2;
    if ( a3 )
    {
      v15 = 1;
      *(_OWORD *)(v12 + 168) = *a3;
    }
    else
    {
      v15 = 0;
    }
    *(_BYTE *)(v12 + 184) = v15;
    v16 = 4;
    *(_QWORD *)(v12 + 192) = 0;
    *(_BYTE *)(v12 + 200) = 0;
    v37 = a1[148];
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = *(_WORD *)(v12 + 40) - 1;
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v19) = 4;
      WPP_RECORDER_SF_iD(Default, v19, 3, 42, (__int64)WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids, a2, v17);
      v11 = v38;
    }
    if ( (*(_DWORD *)(a2 + 12) & 0xC0) != 0 )
    {
      v20 = **(_QWORD **)(v12 + 216);
      v21 = a5 != 0;
      *(_DWORD *)(v12 + 24) = 3;
      *(_DWORD *)(v12 + 20) = 2;
      if ( v14 )
        v22 = a1[182];
      else
        v22 = 0;
      v23 = IssueBulkRequest(
              (_DWORD)a1,
              v12,
              4,
              v11,
              v20,
              v22,
              1024,
              v14 != 0 ? 17 : 1,
              (unsigned __int64)ReadyIUCompletion & -(__int64)v21);
      NextFree = v23;
      if ( v23 < 0 )
      {
        if ( v23 == -1073741810 )
        {
          v16 = 14;
        }
        else if ( v23 == -1073741764 )
        {
          v16 = 18;
        }
        *(_BYTE *)(a2 + 3) = v16;
LABEL_18:
        QueueReleaseEntry(v12);
        return (unsigned int)NextFree;
      }
    }
    else
    {
      *(_DWORD *)(v12 + 24) = 2;
    }
    v24 = *(__int64 **)(v12 + 208);
    v25 = a5 != 0;
    a5 = -a5;
    v26 = *v24;
    *(_DWORD *)(v12 + 16) = 2;
    if ( v14 )
      v27 = a1[181];
    else
      v27 = 0;
    v28 = IssueBulkRequest(
            (_DWORD)a1,
            v12,
            3,
            v38,
            v26,
            v27,
            1024,
            v14 != 0 ? 17 : 1,
            (unsigned __int64)SenseIUCompletion & -(__int64)v25);
    NextFree = v28;
    if ( v28 < 0 )
    {
      if ( v28 == -1073741810 )
      {
        v16 = 14;
      }
      else if ( v28 == -1073741764 )
      {
        v16 = 18;
      }
      *(_BYTE *)(*(_QWORD *)(v12 + 32) + 3LL) = v16;
      *(_DWORD *)(v12 + 16) = 3;
      if ( (*(_DWORD *)(a2 + 12) & 0xC0) != 0 )
      {
        *(_DWORD *)(v12 + 8) = 3;
        *(_DWORD *)(v12 + 12) = 3;
        CancelReadyIrp(v12);
        return 0;
      }
      goto LABEL_18;
    }
    v29 = v38;
    v30 = 32LL * v38 + v37;
    *(_BYTE *)v30 = 1;
    *(_OWORD *)(v30 + 16) = *(_OWORD *)(a2 + 72);
    v31 = a1[141];
    v32 = *(unsigned __int8 *)(a2 + 7);
    if ( v31 )
      v33 = *(_QWORD *)(32 * v32 + v31);
    else
      v33 = _byteswap_uint64(v32);
    *(_BYTE *)(v30 + 4) &= 0x80u;
    *(_QWORD *)(v30 + 8) = v33;
    *(_WORD *)(v30 + 2) = v13;
    *(_BYTE *)(v30 + 6) &= 3u;
    *(_DWORD *)(v12 + 8) = 2;
    if ( v14 )
      v34 = a1[180];
    else
      v34 = 0;
    v35 = IssueBulkRequest((_DWORD)a1, v12, 1, v29, v30, v34, 32, v14 != 0 ? 0x10 : 0, (__int64)CommandIUCompletion);
    NextFree = v35;
    if ( v35 < 0 )
    {
      if ( v35 == -1073741810 )
      {
        v16 = 14;
      }
      else if ( v35 == -1073741764 )
      {
        v16 = 18;
      }
      *(_BYTE *)(a2 + 3) = v16;
      NextFree = 0;
      *(_DWORD *)(v12 + 8) = 3;
      *(_DWORD *)(v12 + 12) = 3;
      if ( (*(_DWORD *)(a2 + 12) & 0xC0) != 0 )
        CancelReadyIrp(v12);
      CancelStatusIrp(v12);
    }
  }
  return (unsigned int)NextFree;
}

```

## disassembly

```asm
0x140009c10  mov     r11, rsp
0x140009c13  push    rbx
0x140009c14  push    rbp
0x140009c15  push    rsi
0x140009c16  push    rdi
0x140009c17  push    r12
0x140009c19  push    r13
0x140009c1b  push    r14
0x140009c1d  push    r15
0x140009c1f  sub     rsp, 68h
0x140009c23  xor     eax, eax
0x140009c25  mov     rsi, r8
0x140009c28  mov     [r11+8], ax
0x140009c2d  mov     r15, r9
0x140009c30  mov     rax, [rcx+68h]
0x140009c34  mov     rbp, rdx
0x140009c37  mov     r8, rdx
0x140009c3a  mov     [rsp+0A8h+arg_20], rax
0x140009c42  xor     r9d, r9d
0x140009c45  lea     rdx, [r11+8]
0x140009c49  mov     r14, rcx
0x140009c4c  call    QueueFindNextFree
0x140009c51  mov     ebx, eax
0x140009c53  test    eax, eax
0x140009c55  js      loc_140009FC4
0x140009c5b  movzx   edx, [rsp+0A8h+arg_0]
0x140009c63  mov     r11d, 1
0x140009c69  imul    rdi, rdx, 0E0h
0x140009c70  lea     r13d, [r11+rdx]
0x140009c74  mov     [rsp+0A8h+arg_0], dx
0x140009c7c  add     rdi, [r14+498h]
0x140009c83  ror     r13w, 8
0x140009c88  mov     [rdi+0A0h], r15
0x140009c8f  mov     r15b, [rsp+0A8h+arg_28]
0x140009c97  mov     [rdi+0C9h], r15b
0x140009c9e  mov     [rdi+8], r11d
0x140009ca2  mov     [rdi+0Ch], r11d
0x140009ca6  mov     [rdi+14h], r11d
0x140009caa  mov     [rdi+10h], r11d
0x140009cae  mov     [rdi+20h], rbp
0x140009cb2  test    rsi, rsi
0x140009cb5  jz      short loc_140009CC7
0x140009cb7  movups  xmm0, xmmword ptr [rsi]
0x140009cba  mov     al, r11b
0x140009cbd  movdqu  xmmword ptr [rdi+0A8h], xmm0
0x140009cc5  jmp     short loc_140009CC9
0x140009cc7  xor     al, al
0x140009cc9  mov     [rdi+0B8h], al
0x140009ccf  mov     esi, 4
0x140009cd4  mov     qword ptr [rdi+0C0h], 0
0x140009cdf  mov     byte ptr [rdi+0C8h], 0
0x140009ce6  cmp     cs:gTracingEnabled, 0
0x140009ced  mov     rax, [r14+4A0h]
0x140009cf4  mov     [rsp+0A8h+var_58], rax
0x140009cf9  jz      short loc_140009D5C
0x140009cfb  lea     rax, WPP_RECORDER_INITIALIZED
0x140009d02  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009d09  jz      short loc_140009D5C
0x140009d0b  movzx   ebx, word ptr [rdi+28h]
0x140009d0f  lea     r12d, [rsi+26h]
0x140009d13  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d1a  dec     ebx
0x140009d1c  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140009d23  nop     dword ptr [rax+rax+00h]
0x140009d28  mov     [rsp+0A8h+var_78], ebx
0x140009d2c  lea     r8d, [rsi-1]
0x140009d30  mov     rcx, rax
0x140009d33  mov     [rsp+0A8h+var_80], rbp
0x140009d38  lea     rax, WPP_32736fb5ed073acc00a38acab6f2acca_Traceguids
0x140009d3f  movzx   r9d, r12w
0x140009d43  mov     dl, sil
0x140009d46  mov     [rsp+0A8h+var_88], rax
0x140009d4b  call    WPP_RECORDER_SF_iD
0x140009d50  movzx   edx, [rsp+0A8h+arg_0]
0x140009d58  lea     r11d, [rsi-3]
0x140009d5c  mov     eax, [rbp+0Ch]
0x140009d5f  mov     r12d, 2
0x140009d65  test    al, 0C0h
0x140009d67  jz      loc_140009E12
0x140009d6d  mov     rax, [rdi+0D8h]
0x140009d74  mov     r10, [rax]
0x140009d77  mov     rax, [rsp+0A8h+arg_20]
0x140009d7f  neg     rax
0x140009d82  mov     dword ptr [rdi+18h], 3
0x140009d89  lea     rax, ReadyIUCompletion
0x140009d90  mov     [rdi+14h], r12d
0x140009d94  sbb     r9, r9
0x140009d97  and     r9, rax
0x140009d9a  test    r15b, r15b
0x140009d9d  jz      short loc_140009DA8
0x140009d9f  mov     r8, [r14+5B0h]
0x140009da6  jmp     short loc_140009DAB
0x140009da8  xor     r8d, r8d
0x140009dab  mov     [rsp+0A8h+var_68], r9
0x140009db0  mov     al, r15b
0x140009db3  neg     al
0x140009db5  movzx   r9d, dx
0x140009db9  mov     rdx, rdi
0x140009dbc  sbb     ecx, ecx
0x140009dbe  and     ecx, 10h
0x140009dc1  add     ecx, r11d
0x140009dc4  mov     [rsp+0A8h+var_70], ecx
0x140009dc8  mov     rcx, r14
0x140009dcb  mov     [rsp+0A8h+var_78], 400h
0x140009dd3  mov     [rsp+0A8h+var_80], r8
0x140009dd8  mov     r8d, esi
0x140009ddb  mov     [rsp+0A8h+var_88], r10
0x140009de0  call    IssueBulkRequest
0x140009de5  mov     ebx, eax
0x140009de7  test    eax, eax
0x140009de9  jns     short loc_140009E16
0x140009deb  cmp     eax, 0C000000Eh
0x140009df0  jz      short loc_140009DFE
0x140009df2  cmp     eax, 0C000003Ch
0x140009df7  jnz     short loc_140009E01
0x140009df9  mov     sil, 12h
0x140009dfc  jmp     short loc_140009E01
0x140009dfe  mov     sil, 0Eh
0x140009e01  mov     [rbp+3], sil
0x140009e05  mov     rcx, rdi
0x140009e08  call    QueueReleaseEntry
0x140009e0d  jmp     loc_140009FC4
0x140009e12  mov     [rdi+18h], r12d
0x140009e16  mov     rax, [rdi+0D0h]
0x140009e1d  neg     [rsp+0A8h+arg_20]
0x140009e25  sbb     r8, r8
0x140009e28  mov     r9, [rax]
0x140009e2b  lea     rax, SenseIUCompletion
0x140009e32  and     r8, rax
0x140009e35  mov     [rdi+10h], r12d
0x140009e39  test    r15b, r15b
0x140009e3c  jz      short loc_140009E47
0x140009e3e  mov     rdx, [r14+5A8h]
0x140009e45  jmp     short loc_140009E49
0x140009e47  xor     edx, edx
0x140009e49  mov     [rsp+0A8h+var_68], r8
0x140009e4e  mov     al, r15b
0x140009e51  neg     al
0x140009e53  mov     r8d, 3
0x140009e59  sbb     ecx, ecx
0x140009e5b  and     ecx, 10h
0x140009e5e  inc     ecx
0x140009e60  mov     [rsp+0A8h+var_70], ecx
0x140009e64  mov     rcx, r14
0x140009e67  mov     [rsp+0A8h+var_78], 400h
0x140009e6f  mov     [rsp+0A8h+var_80], rdx
0x140009e74  mov     rdx, rdi
0x140009e77  mov     [rsp+0A8h+var_88], r9
0x140009e7c  movzx   r9d, [rsp+0A8h+arg_0]
0x140009e85  call    IssueBulkRequest
0x140009e8a  mov     ebx, eax
0x140009e8c  test    eax, eax
0x140009e8e  jns     short loc_140009ED6
0x140009e90  cmp     eax, 0C000000Eh
0x140009e95  jz      short loc_140009EA3
0x140009e97  cmp     eax, 0C000003Ch
0x140009e9c  jnz     short loc_140009EA6
0x140009e9e  mov     sil, 12h
0x140009ea1  jmp     short loc_140009EA6
0x140009ea3  mov     sil, 0Eh
0x140009ea6  mov     rax, [rdi+20h]
0x140009eaa  mov     ecx, 3
0x140009eaf  mov     [rax+3], sil
0x140009eb3  mov     [rdi+10h], ecx
0x140009eb6  mov     eax, [rbp+0Ch]
0x140009eb9  test    al, 0C0h
0x140009ebb  jz      loc_140009E05
0x140009ec1  mov     [rdi+8], ecx
0x140009ec4  mov     [rdi+0Ch], ecx
0x140009ec7  mov     rcx, rdi
0x140009eca  call    CancelReadyIrp
0x140009ecf  xor     ebx, ebx
0x140009ed1  jmp     loc_140009FC4
0x140009ed6  movzx   r8d, [rsp+0A8h+arg_0]
0x140009edf  mov     rcx, [rsp+0A8h+var_58]
0x140009ee4  mov     eax, r8d
0x140009ee7  shl     rax, 5
0x140009eeb  add     rcx, rax
0x140009eee  mov     byte ptr [rcx], 1
0x140009ef1  movups  xmm0, xmmword ptr [rbp+48h]
0x140009ef5  movdqu  xmmword ptr [rcx+10h], xmm0
0x140009efa  mov     rdx, [r14+468h]
0x140009f01  movzx   eax, byte ptr [rbp+7]
0x140009f05  test    rdx, rdx
0x140009f08  jz      short loc_140009F14
0x140009f0a  shl     rax, 5
0x140009f0e  mov     rax, [rax+rdx]
0x140009f12  jmp     short loc_140009F17
0x140009f14  bswap   rax
0x140009f17  and     byte ptr [rcx+4], 80h
0x140009f1b  mov     [rcx+8], rax
0x140009f1f  mov     al, r15b
0x140009f22  mov     [rcx+2], r13w
0x140009f27  mov     r13d, 3
0x140009f2d  and     [rcx+6], r13b
0x140009f31  neg     al
0x140009f33  mov     [rdi+8], r12d
0x140009f37  sbb     edx, edx
0x140009f39  and     edx, 10h
0x140009f3c  test    r15b, r15b
0x140009f3f  jz      short loc_140009F4A
0x140009f41  mov     rax, [r14+5A0h]
0x140009f48  jmp     short loc_140009F4C
0x140009f4a  xor     eax, eax
0x140009f4c  lea     r9, CommandIUCompletion
0x140009f53  mov     [rsp+0A8h+var_68], r9
0x140009f58  movzx   r9d, r8w
0x140009f5c  mov     [rsp+0A8h+var_70], edx
0x140009f60  mov     r8d, 1
0x140009f66  mov     [rsp+0A8h+var_78], 20h ; ' '
0x140009f6e  mov     rdx, rdi
0x140009f71  mov     [rsp+0A8h+var_80], rax
0x140009f76  mov     [rsp+0A8h+var_88], rcx
0x140009f7b  mov     rcx, r14
0x140009f7e  call    IssueBulkRequest
0x140009f83  mov     ebx, eax
0x140009f85  test    eax, eax
0x140009f87  jns     short loc_140009FC4
0x140009f89  cmp     eax, 0C000000Eh
0x140009f8e  jz      short loc_140009F9C
0x140009f90  cmp     eax, 0C000003Ch
0x140009f95  jnz     short loc_140009F9F
0x140009f97  mov     sil, 12h
0x140009f9a  jmp     short loc_140009F9F
0x140009f9c  mov     sil, 0Eh
0x140009f9f  mov     [rbp+3], sil
0x140009fa3  xor     ebx, ebx
0x140009fa5  mov     [rdi+8], r13d
0x140009fa9  mov     [rdi+0Ch], r13d
0x140009fad  mov     eax, [rbp+0Ch]
0x140009fb0  test    al, 0C0h
0x140009fb2  jz      short loc_140009FBC
0x140009fb4  mov     rcx, rdi
0x140009fb7  call    CancelReadyIrp
0x140009fbc  mov     rcx, rdi
0x140009fbf  call    CancelStatusIrp
0x140009fc4  mov     eax, ebx
0x140009fc6  add     rsp, 68h
0x140009fca  pop     r15
0x140009fcc  pop     r14
0x140009fce  pop     r13
0x140009fd0  pop     r12
0x140009fd2  pop     rdi
0x140009fd3  pop     rsi
0x140009fd4  pop     rbp
0x140009fd5  pop     rbx
0x140009fd6  retn
```
