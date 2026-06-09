# BfpValidateBatchedMappingConfig

- ea: `0x140021d1c`
- end: `0x1400223a4`
- name: `BfpValidateBatchedMappingConfig`
- size: `1672`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x140010898`
- `0x14001d974`

## callees

- `0x140001348`
- `0x140002740`
- `0x140003140`
- `0x140003304`
- `0x140003e14`
- `0x140004060`
- `0x140021d1c`
- `0x1400223ac`

## pseudocode

```c
__int64 __fastcall BfpValidateBatchedMappingConfig(int *a1, unsigned __int64 a2)
{
  int v3; // edi
  int v4; // ecx
  __int64 v5; // rcx
  unsigned int v6; // edi
  char *v7; // r14
  char *v8; // r15
  unsigned int v9; // r9d
  __int64 i; // r8
  unsigned int v11; // r12d
  unsigned int v12; // ebx
  unsigned int j; // ebp
  __int64 v14; // rcx
  unsigned int v15; // r11d
  unsigned int v16; // r13d
  unsigned int v17; // r8d
  unsigned int v18; // r10d
  int v19; // r9d
  int v20; // edx
  unsigned int v21; // eax
  int v23; // r9d
  int v24; // r9d
  unsigned __int64 v25; // rax
  int v26; // r9d
  char v27; // [rsp+30h] [rbp-78h]
  char v28; // [rsp+30h] [rbp-78h]
  unsigned int v29; // [rsp+38h] [rbp-70h]
  char v30; // [rsp+40h] [rbp-68h]
  _WORD v31[2]; // [rsp+50h] [rbp-58h] BYREF
  int v32; // [rsp+54h] [rbp-54h]
  char *v33; // [rsp+58h] [rbp-50h]
  unsigned __int16 v34; // [rsp+B8h] [rbp+10h]

  if ( (unsigned int)a2 >= 0x28 )
  {
    v3 = *a1;
    if ( *a1 > (unsigned int)a2 )
    {
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v30 = a2;
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_sDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          6,
          122,
          (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
          181,
          v3,
          v30);
      }
      return v12;
    }
    v4 = a1[1];
    if ( (v4 & 0xCFFFFC00) != 0 )
    {
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_sDD(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          6,
          123,
          (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
          188,
          v4);
      }
      return v12;
    }
    v5 = (unsigned int)a1[6];
    v6 = v3 - 32;
    if ( (unsigned int)v5 >= v6 )
    {
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v12;
      v24 = 124;
    }
    else
    {
      a2 = (unsigned int)a1[7];
      if ( (unsigned int)a2 < v6 )
      {
        v7 = (char *)a1 + v5;
        if ( 32 * (unsigned __int64)*(unsigned int *)((char *)a1 + v5 + 32) >= v6 )
        {
          v12 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return v12;
          v23 = 126;
          v27 = -43;
          goto LABEL_28;
        }
        v8 = (char *)a1 + a2;
        v9 = *(int *)((char *)a1 + a2 + 32);
        if ( 8 * (unsigned __int64)v9 < v6 )
        {
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            if ( (unsigned int)i >= v9 )
            {
              v11 = *((_DWORD *)v7 + 8);
              v12 = 0;
              for ( j = 0; ; ++j )
              {
                if ( j >= v11 )
                  return v12;
                v14 = 32LL * j;
                v15 = *(_DWORD *)&v7[v14 + 40];
                v16 = *(unsigned __int16 *)&v7[v14 + 36];
                v17 = *(_DWORD *)&v7[v14 + 48];
                v18 = *(_DWORD *)&v7[v14 + 56];
                v19 = *(unsigned __int16 *)&v7[v14 + 60];
                a2 = *(unsigned int *)&v7[v14 + 64];
                v34 = *(_WORD *)&v7[v14 + 44];
                if ( v15 >= v6 )
                  break;
                if ( *(unsigned __int16 *)&v7[v14 + 38] + v15 > v6 )
                {
                  v12 = -1073741811;
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    return v12;
                  v24 = 131;
                  goto LABEL_70;
                }
                if ( v17 >= v6 )
                {
                  v12 = -1073741811;
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    return v12;
                  v24 = 132;
                  goto LABEL_70;
                }
                if ( v17 + *(unsigned __int16 *)&v7[v14 + 46] > v6 )
                {
                  v12 = -1073741811;
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    return v12;
                  v24 = 133;
                  goto LABEL_70;
                }
                if ( v18 >= v6 )
                {
                  v12 = -1073741811;
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    return v12;
                  v24 = 134;
                  goto LABEL_70;
                }
                if ( v18 + *(unsigned __int16 *)&v7[v14 + 52] > v6 )
                {
                  v12 = -1073741811;
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    return v12;
                  v24 = 135;
                  goto LABEL_70;
                }
                if ( (unsigned int)a2 >= v6 )
                {
                  v12 = -1073741811;
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    return v12;
                  v24 = 136;
                  goto LABEL_70;
                }
                if ( (int)a2 + v19 > v6 )
                {
                  v12 = -1073741811;
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    return v12;
                  v24 = 137;
                  goto LABEL_70;
                }
                v32 = 0;
                v31[0] = v19;
                v33 = (char *)a1 + a2 + 32;
                v31[1] = v19;
                if ( !(unsigned __int8)BfValidateShortName(v31) )
                {
                  v12 = -1073741811;
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    WPP_RECORDER_SF_sDZ(WPP_GLOBAL_Control->DeviceExtension, v20, 6, 138);
                  return v12;
                }
                v21 = *((_DWORD *)v8 + 8);
                if ( v16 >= v21 )
                {
                  v12 = -1073741811;
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    return v12;
                  v29 = v16;
                  v26 = 139;
                  v28 = 54;
LABEL_51:
                  LOBYTE(v20) = 2;
                  WPP_RECORDER_SF_sDd(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v20,
                    6,
                    v26,
                    (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                    (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                    v28,
                    v29);
                  return v12;
                }
                if ( v34 >= v21 )
                {
                  v12 = -1073741811;
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    return v12;
                  v29 = v34;
                  v26 = 140;
                  v28 = 60;
                  goto LABEL_51;
                }
              }
              v12 = -1073741811;
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                return v12;
              v24 = 130;
              goto LABEL_70;
            }
            v25 = *(_QWORD *)&v8[8 * i + 36];
            a2 = HIDWORD(v25);
            if ( HIDWORD(v25) >= v6 )
              break;
            if ( HIDWORD(v25) + (unsigned int)(unsigned __int16)v25 > v6 )
            {
              v12 = -1073741811;
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                return v12;
              v24 = 129;
              goto LABEL_70;
            }
          }
          v12 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return v12;
          v24 = 128;
          goto LABEL_70;
        }
        v12 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v23 = 127;
          v27 = -34;
          goto LABEL_28;
        }
        return v12;
      }
      v12 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v12;
      v24 = 125;
    }
LABEL_70:
    WPP_RECORDER_SF_sDDD(WPP_GLOBAL_Control->DeviceExtension, a2, 6, v24);
    return v12;
  }
  v12 = -1073741811;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v23 = 121;
    v27 = -82;
LABEL_28:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      6,
      v23,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      v27);
  }
  return v12;
}

```

## disassembly

```asm
0x140021d1c  push    rbx
0x140021d1e  push    rbp
0x140021d1f  push    rsi
0x140021d20  push    rdi
0x140021d21  push    r12
0x140021d23  push    r13
0x140021d25  push    r14
0x140021d27  push    r15
0x140021d29  sub     rsp, 68h
0x140021d2d  mov     rsi, rcx
0x140021d30  cmp     edx, 28h ; '('
0x140021d33  jb      loc_140021ECA
0x140021d39  mov     edi, [rcx]
0x140021d3b  cmp     edi, edx
0x140021d3d  ja      loc_140021F2F
0x140021d43  mov     ecx, [rcx+4]
0x140021d46  test    ecx, 0CFFFFC00h
0x140021d4c  jnz     loc_140021F91
0x140021d52  mov     ecx, [rsi+18h]
0x140021d55  add     edi, 0FFFFFFE0h
0x140021d58  cmp     ecx, edi
0x140021d5a  jnb     loc_140021FEF
0x140021d60  mov     edx, [rsi+1Ch]
0x140021d63  cmp     edx, edi
0x140021d65  jnb     loc_140022023
0x140021d6b  lea     r14, [rsi+rcx]
0x140021d6f  mov     ecx, edi
0x140021d71  mov     eax, [r14+20h]
0x140021d75  shl     rax, 5
0x140021d79  cmp     rax, rcx
0x140021d7c  jnb     loc_140022057
0x140021d82  lea     r15, [rsi+rdx]
0x140021d86  mov     r9d, [r15+20h]
0x140021d8a  mov     eax, r9d
0x140021d8d  shl     rax, 3
0x140021d91  cmp     rax, rcx
0x140021d94  jnb     loc_140022083
0x140021d9a  xor     r8d, r8d
0x140021d9d  cmp     r8d, r9d
0x140021da0  jb      loc_1400220A1
0x140021da6  mov     r12d, [r14+20h]
0x140021daa  xor     ebx, ebx
0x140021dac  xor     ebp, ebp
0x140021dae  cmp     ebp, r12d
0x140021db1  jnb     loc_140021EB6
0x140021db7  mov     ecx, ebp
0x140021db9  shl     rcx, 5
0x140021dbd  mov     r11d, [rcx+r14+28h]
0x140021dc2  movzx   eax, word ptr [rcx+r14+2Ch]
0x140021dc8  movzx   r13d, word ptr [rcx+r14+24h]
0x140021dce  mov     r8d, [rcx+r14+30h]
0x140021dd3  mov     r10d, [rcx+r14+38h]
0x140021dd8  movzx   r9d, word ptr [rcx+r14+3Ch]
0x140021dde  mov     edx, [rcx+r14+40h]
0x140021de3  mov     [rsp+0A8h+arg_8], ax
0x140021deb  cmp     r11d, edi
0x140021dee  jnb     loc_140022359
0x140021df4  movzx   eax, word ptr [rcx+r14+26h]
0x140021dfa  add     r11d, eax
0x140021dfd  cmp     r11d, edi
0x140021e00  ja      loc_140022327
0x140021e06  cmp     r8d, edi
0x140021e09  jnb     loc_1400222F5
0x140021e0f  movzx   r11d, word ptr [rcx+r14+2Eh]
0x140021e15  add     r11d, r8d
0x140021e18  cmp     r11d, edi
0x140021e1b  ja      loc_1400222C0
0x140021e21  cmp     r10d, edi
0x140021e24  jnb     loc_14002228B
0x140021e2a  movzx   ecx, word ptr [rcx+r14+34h]
0x140021e30  add     ecx, r10d
0x140021e33  cmp     ecx, edi
0x140021e35  ja      loc_140022257
0x140021e3b  cmp     edx, edi
0x140021e3d  jnb     loc_140022223
0x140021e43  lea     ecx, [rdx+r9]
0x140021e47  cmp     ecx, edi
0x140021e49  ja      loc_1400221EF
0x140021e4f  lea     rcx, [rsi+20h]
0x140021e53  mov     [rsp+0A8h+var_54], ebx
0x140021e57  add     rcx, rdx
0x140021e5a  mov     [rsp+0A8h+var_58], r9w
0x140021e60  mov     [rsp+0A8h+var_50], rcx
0x140021e65  lea     rcx, [rsp+0A8h+var_58]
0x140021e6a  mov     [rsp+0A8h+var_56], r9w
0x140021e70  call    BfValidateShortName
0x140021e75  test    al, al
0x140021e77  jz      loc_1400221A3
0x140021e7d  mov     eax, [r15+20h]
0x140021e81  cmp     r13d, eax
0x140021e84  jnb     short loc_140021E9D
0x140021e86  movzx   ecx, [rsp+0A8h+arg_8]
0x140021e8e  cmp     ecx, eax
0x140021e90  jnb     loc_14002212E
0x140021e96  inc     ebp
0x140021e98  jmp     loc_140021DAE
0x140021e9d  mov     ebx, 0C000000Dh
0x140021ea2  lea     rax, WPP_RECORDER_INITIALIZED
0x140021ea9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021eb0  jnz     loc_14002215B
0x140021eb6  mov     eax, ebx
0x140021eb8  add     rsp, 68h
0x140021ebc  pop     r15
0x140021ebe  pop     r14
0x140021ec0  pop     r13
0x140021ec2  pop     r12
0x140021ec4  pop     rdi
0x140021ec5  pop     rsi
0x140021ec6  pop     rbp
0x140021ec7  pop     rbx
0x140021ec8  retn
0x140021eca  mov     ebx, 0C000000Dh
0x140021ecf  lea     rax, WPP_RECORDER_INITIALIZED
0x140021ed6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021edd  jz      short loc_140021EB6
0x140021edf  mov     r9d, 79h ; 'y'
0x140021ee5  mov     dword ptr [rsp+0A8h+var_78], 13AEh
0x140021eed  jmp     short loc_140021EFD
0x140021eef  mov     r9d, 7Fh
0x140021ef5  mov     dword ptr [rsp+0A8h+var_78], 13DEh
0x140021efd  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f04  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140021f0b  mov     [rsp+0A8h+var_80], rax
0x140021f10  mov     r8d, 6
0x140021f16  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140021f1d  mov     dl, 2
0x140021f1f  mov     [rsp+0A8h+var_88], rax
0x140021f24  mov     rcx, [rcx+40h]
0x140021f28  call    WPP_RECORDER_SF_sD
0x140021f2d  jmp     short loc_140021EB6
0x140021f2f  mov     ebx, 0C000000Dh
0x140021f34  lea     rax, WPP_RECORDER_INITIALIZED
0x140021f3b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021f42  jz      loc_140021EB6
0x140021f48  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f4f  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140021f56  mov     dword ptr [rsp+0A8h+var_68], edx
0x140021f5a  mov     r9d, 7Ah ; 'z'
0x140021f60  mov     dword ptr [rsp+0A8h+var_70], edi
0x140021f64  mov     dl, 2
0x140021f66  mov     dword ptr [rsp+0A8h+var_78], 13B5h
0x140021f6e  mov     rcx, [rcx+40h]
0x140021f72  mov     [rsp+0A8h+var_80], rax
0x140021f77  lea     r8d, [r9-74h]
0x140021f7b  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140021f82  mov     [rsp+0A8h+var_88], rax
0x140021f87  call    WPP_RECORDER_SF_sDdd
0x140021f8c  jmp     loc_140021EB6
0x140021f91  mov     ebx, 0C000000Dh
0x140021f96  lea     rax, WPP_RECORDER_INITIALIZED
0x140021f9d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021fa4  jz      loc_140021EB6
0x140021faa  mov     dword ptr [rsp+0A8h+var_70], ecx
0x140021fae  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140021fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140021fbc  mov     r9d, 7Bh ; '{'
0x140021fc2  mov     dword ptr [rsp+0A8h+var_78], 13BCh
0x140021fca  mov     dl, 2
0x140021fcc  mov     [rsp+0A8h+var_80], rax
0x140021fd1  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140021fd8  mov     [rsp+0A8h+var_88], rax
0x140021fdd  mov     rcx, [rcx+40h]
0x140021fe1  lea     r8d, [r9-75h]
0x140021fe5  call    WPP_RECORDER_SF_sDD
0x140021fea  jmp     loc_140021EB6
0x140021fef  mov     ebx, 0C000000Dh
0x140021ff4  lea     rax, WPP_RECORDER_INITIALIZED
0x140021ffb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140022002  jz      loc_140021EB6
0x140022008  mov     dword ptr [rsp+0A8h+var_68], edi
0x14002200c  mov     r9d, 7Ch ; '|'
0x140022012  mov     dword ptr [rsp+0A8h+var_70], ecx
0x140022016  mov     dword ptr [rsp+0A8h+var_78], 13C5h
0x14002201e  jmp     loc_140022389
0x140022023  mov     ebx, 0C000000Dh
0x140022028  lea     rax, WPP_RECORDER_INITIALIZED
0x14002202f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140022036  jz      loc_140021EB6
0x14002203c  mov     dword ptr [rsp+0A8h+var_68], edi
0x140022040  mov     r9d, 7Dh ; '}'
0x140022046  mov     dword ptr [rsp+0A8h+var_70], edx
0x14002204a  mov     dword ptr [rsp+0A8h+var_78], 13CCh
0x140022052  jmp     loc_140022389
0x140022057  mov     ebx, 0C000000Dh
0x14002205c  lea     rax, WPP_RECORDER_INITIALIZED
0x140022063  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002206a  jz      loc_140021EB6
0x140022070  mov     r9d, 7Eh ; '~'
0x140022076  mov     dword ptr [rsp+0A8h+var_78], 13D5h
0x14002207e  jmp     loc_140021EFD
0x140022083  mov     ebx, 0C000000Dh
0x140022088  lea     rax, WPP_RECORDER_INITIALIZED
0x14002208f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140022096  jz      loc_140021EB6
0x14002209c  jmp     loc_140021EEF
0x1400220a1  mov     rax, [r15+r8*8+24h]
0x1400220a6  mov     rdx, rax
0x1400220a9  shr     rdx, 20h
0x1400220ad  cmp     edx, edi
0x1400220af  jnb     short loc_1400220FA
0x1400220b1  movzx   r10d, ax
0x1400220b5  add     r10d, edx
0x1400220b8  cmp     r10d, edi
0x1400220bb  ja      short loc_1400220C5
0x1400220bd  inc     r8d
0x1400220c0  jmp     loc_140021D9D
0x1400220c5  mov     ebx, 0C000000Dh
0x1400220ca  lea     rax, WPP_RECORDER_INITIALIZED
0x1400220d1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400220d8  jz      loc_140021EB6
0x1400220de  mov     dword ptr [rsp+0A8h+var_68], edi
0x1400220e2  mov     r9d, 81h
0x1400220e8  mov     dword ptr [rsp+0A8h+var_70], r10d
0x1400220ed  mov     dword ptr [rsp+0A8h+var_78], 13EEh
0x1400220f5  jmp     loc_140022389
0x1400220fa  mov     ebx, 0C000000Dh
0x1400220ff  lea     rax, WPP_RECORDER_INITIALIZED
0x140022106  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002210d  jz      loc_140021EB6
0x140022113  mov     dword ptr [rsp+0A8h+var_68], edi
0x140022117  mov     r9d, 80h
0x14002211d  mov     dword ptr [rsp+0A8h+var_70], edx
0x140022121  mov     dword ptr [rsp+0A8h+var_78], 13E8h
0x140022129  jmp     loc_140022389
0x14002212e  mov     ebx, 0C000000Dh
0x140022133  lea     rax, WPP_RECORDER_INITIALIZED
0x14002213a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140022141  jz      loc_140021EB6
0x140022147  mov     dword ptr [rsp+0A8h+var_70], ecx
0x14002214b  mov     r9d, 8Ch
0x140022151  mov     dword ptr [rsp+0A8h+var_78], 143Ch
0x140022159  jmp     short loc_14002216E
0x14002215b  mov     dword ptr [rsp+0A8h+var_70], r13d
0x140022160  mov     r9d, 8Bh
0x140022166  mov     dword ptr [rsp+0A8h+var_78], 1436h
0x14002216e  mov     rcx, cs:WPP_GLOBAL_Control
0x140022175  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14002217c  mov     [rsp+0A8h+var_80], rax
0x140022181  mov     r8d, 6
0x140022187  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14002218e  mov     dl, 2
0x140022190  mov     [rsp+0A8h+var_88], rax
0x140022195  mov     rcx, [rcx+40h]
0x140022199  call    WPP_RECORDER_SF_sDd
0x14002219e  jmp     loc_140021EB6
0x1400221a3  mov     ebx, 0C000000Dh
0x1400221a8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400221af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400221b6  jz      loc_140021EB6
0x1400221bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400221c3  lea     rax, [rsp+0A8h+var_58]
0x1400221c8  mov     [rsp+0A8h+var_70], rax
0x1400221cd  mov     r9d, 8Ah
0x1400221d3  mov     r8d, 6
0x1400221d9  mov     dword ptr [rsp+0A8h+var_78], 1430h
0x1400221e1  mov     rcx, [rcx+40h]
0x1400221e5  call    WPP_RECORDER_SF_sDZ
0x1400221ea  jmp     loc_140021EB6
0x1400221ef  mov     ebx, 0C000000Dh
0x1400221f4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400221fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140022202  jz      loc_140021EB6
0x140022208  mov     dword ptr [rsp+0A8h+var_68], edi
0x14002220c  mov     r9d, 89h
0x140022212  mov     dword ptr [rsp+0A8h+var_70], ecx
0x140022216  mov     dword ptr [rsp+0A8h+var_78], 1424h
0x14002221e  jmp     loc_140022389
0x140022223  mov     ebx, 0C000000Dh
0x140022228  lea     rax, WPP_RECORDER_INITIALIZED
0x14002222f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140022236  jz      loc_140021EB6
0x14002223c  mov     dword ptr [rsp+0A8h+var_68], edi
0x140022240  mov     r9d, 88h
0x140022246  mov     dword ptr [rsp+0A8h+var_70], edx
0x14002224a  mov     dword ptr [rsp+0A8h+var_78], 141Eh
0x140022252  jmp     loc_140022389
0x140022257  mov     ebx, 0C000000Dh
0x14002225c  lea     rax, WPP_RECORDER_INITIALIZED
0x140022263  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002226a  jz      loc_140021EB6
0x140022270  mov     dword ptr [rsp+0A8h+var_68], edi
0x140022274  mov     r9d, 87h
0x14002227a  mov     dword ptr [rsp+0A8h+var_70], ecx
0x14002227e  mov     dword ptr [rsp+0A8h+var_78], 1418h
0x140022286  jmp     loc_140022389
0x14002228b  mov     ebx, 0C000000Dh
0x140022290  lea     rax, WPP_RECORDER_INITIALIZED
0x140022297  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002229e  jz      loc_140021EB6
0x1400222a4  mov     dword ptr [rsp+0A8h+var_68], edi
0x1400222a8  mov     r9d, 86h
0x1400222ae  mov     dword ptr [rsp+0A8h+var_70], r10d
0x1400222b3  mov     dword ptr [rsp+0A8h+var_78], 1412h
0x1400222bb  jmp     loc_140022389
0x1400222c0  mov     ebx, 0C000000Dh
0x1400222c5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400222cc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400222d3  jz      loc_140021EB6
0x1400222d9  mov     dword ptr [rsp+0A8h+var_68], edi
0x1400222dd  mov     r9d, 85h
  ... truncated ...
```
