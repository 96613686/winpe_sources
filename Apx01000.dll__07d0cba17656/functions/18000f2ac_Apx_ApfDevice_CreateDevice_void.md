# Apx::ApfDevice::CreateDevice(void)

- ea: `0x18000f2ac`
- end: `0x18000f65e`
- name: `?CreateDevice@ApfDevice@Apx@@AEAAJXZ`
- size: `946`
- prototype: `__int64 __fastcall(unsigned __int64 this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000fb6c`

## callees

- `0x18000163c`
- `0x180001d30`
- `0x180009d28`
- `0x18000a12c`
- `0x18000ef00`
- `0x18000f2ac`
- `0x18000f664`
- `0x18000f8fc`

## pseudocode

```c
__int64 __fastcall Apx::ApfDevice::CreateDevice(unsigned __int64 this)
{
  __int64 v2; // rax
  signed int ApxRootContainer; // edi
  __int64 v4; // rax
  const WCHAR *v5; // rcx
  __int64 v6; // rdx
  _WORD *v7; // r8
  _WORD *v8; // rcx
  __int64 v9; // r10
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // r8
  char *v12; // r9
  int v13; // eax
  char *v14; // r11
  __int64 v15; // rcx
  char *v16; // rbx
  __int64 v17; // rax
  int v18; // eax
  int v19; // ecx
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  char *v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  char *v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  char *v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  char *v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  char *v37; // [rsp+D0h] [rbp-30h]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  char *v39; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h]
  __int64 *v41; // [rsp+F0h] [rbp-10h]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  __int64 *v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v45; // [rsp+110h] [rbp+10h]
  int v46; // [rsp+118h] [rbp+18h]
  int v47; // [rsp+11Ch] [rbp+1Ch]
  const unsigned __int16 *v48; // [rsp+120h] [rbp+20h]
  int v49; // [rsp+128h] [rbp+28h]
  int v50; // [rsp+12Ch] [rbp+2Ch]
  char *v51; // [rsp+130h] [rbp+30h]
  __int64 v52; // [rsp+138h] [rbp+38h]
  unsigned __int64 *v53; // [rsp+140h] [rbp+40h]
  __int64 v54; // [rsp+148h] [rbp+48h]
  __int64 *v55; // [rsp+150h] [rbp+50h]
  __int64 v56; // [rsp+158h] [rbp+58h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  v2 = *(unsigned int *)(this + 72);
  *(_DWORD *)(this + 36) = 2;
  *(_DWORD *)(this + 4 * v2 + 40) = 2;
  if ( ++*(_DWORD *)(this + 72) >= 8u )
    *(_DWORD *)(this + 72) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  if ( (*(_BYTE *)(this + 32) & 0x20) != 0 )
    goto LABEL_21;
  ApxRootContainer = Apx::ApfDevice::FindOrCreateApxRootContainer((Apx::ApfDevice *)this);
  if ( ApxRootContainer >= 0 )
  {
    v4 = 2147483646;
    v5 = L"SWD\\APXENUM\\0";
    v6 = 261;
    v7 = (_WORD *)(this + 1372);
    do
    {
      if ( !v4 )
        break;
      if ( !*v5 )
        break;
      *v7++ = *v5++;
      --v4;
      --v6;
    }
    while ( v6 );
    v8 = v7 - 1;
    ApxRootContainer = v6 == 0 ? 0x8007007A : 0;
    if ( v6 )
      v8 = v7;
    *v8 = 0;
    if ( v6 )
    {
      *(_DWORD *)(this + 32) |= 0x20u;
LABEL_21:
      ApxRootContainer = Apx::ApfDevice::CreateApxDevice(this);
      if ( ApxRootContainer >= 0 )
        ApxRootContainer = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  if ( ApxRootContainer == -2147024891 )
  {
    if ( (*(_DWORD *)(this + 32) & 0x100) == 0 )
    {
      ApxRootContainer = Apx::ApfDevice::CreateDevice_Remote((Apx::ApfDevice *)this);
      if ( ApxRootContainer >= 0 )
      {
        *(_BYTE *)(this + 16) = 1;
LABEL_32:
        ApxRootContainer = 0;
      }
    }
  }
  else if ( ApxRootContainer >= 0 )
  {
    goto LABEL_32;
  }
  v9 = *((_QWORD *)ApxTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v9 > 4u
    && (*(_QWORD *)(v9 + 16) & 0x400000000001LL) != 0
    && (*(_QWORD *)(v9 + 24) & 0x400000000001LL) == *(_QWORD *)(v9 + 24) )
  {
    LODWORD(v22) = ApxRootContainer;
    v25 = 2048;
    v24 = ~this;
    v10 = (const unsigned __int16 *)(this + 1372);
    v11 = (const unsigned __int16 *)(this + 328);
    v12 = (char *)(this + 152);
    v13 = (*(_DWORD *)(this + 32) >> 8) & 1;
    v56 = 4;
    HIDWORD(v22) = v13;
    v14 = (char *)(this + 136);
    v15 = -1;
    LODWORD(v23) = *(_DWORD *)(this + 184);
    LOWORD(v21) = *(_WORD *)(this + 176);
    HIDWORD(v23) = *(_DWORD *)(this + 172);
    WORD1(v21) = *(_WORD *)(this + 170);
    LOWORD(v13) = *(_WORD *)(this + 168);
    v16 = (char *)(this + 120);
    WORD2(v21) = v13;
    v55 = &v22;
    v53 = &v24;
    v51 = (char *)&v22 + 4;
    v54 = 8;
    v52 = 4;
    if ( v10 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v10[v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v10 = &qword_18002C8D0;
      v18 = 2;
    }
    v48 = v10;
    v49 = v18;
    v50 = 0;
    if ( v11 )
    {
      do
        ++v15;
      while ( v11[v15] );
      v19 = 2 * v15 + 2;
    }
    else
    {
      v11 = &qword_18002C8D0;
      v19 = 2;
    }
    v46 = v19;
    v43 = &v23;
    v45 = v11;
    v33 = v12;
    v41 = &v21;
    v34 = 16;
    v39 = (char *)&v23 + 4;
    v32 = 16;
    v37 = (char *)&v21 + 2;
    v35 = (char *)&v21 + 4;
    v27 = &v25;
    v30 = 16;
    v47 = 0;
    v44 = 4;
    v42 = 2;
    v40 = 4;
    v38 = 2;
    v36 = 2;
    v31 = v14;
    v29 = v16;
    v28 = 8;
    tlgWriteTransfer_EventWriteTransfer(v9, byte_18002E3C3, 0, 0, 16, v26, v21, v22, v23, v24, v25);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  return (unsigned int)ApxRootContainer;
}

```

## disassembly

```asm
0x18000f2ac  push    rbp
0x18000f2ae  push    rbx
0x18000f2af  push    rsi
0x18000f2b0  push    rdi
0x18000f2b1  push    r12
0x18000f2b3  push    r14
0x18000f2b5  lea     rbp, [rsp-78h]
0x18000f2ba  sub     rsp, 178h
0x18000f2c1  mov     rax, cs:__security_cookie
0x18000f2c8  xor     rax, rsp
0x18000f2cb  mov     [rbp+0A0h+var_40], rax
0x18000f2cf  mov     rbx, rcx
0x18000f2d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2d9  lea     r12, WPP_GLOBAL_Control
0x18000f2e0  cmp     rcx, r12
0x18000f2e3  jz      short loc_18000F306
0x18000f2e5  test    byte ptr [rcx+1Ch], 1
0x18000f2e9  jz      short loc_18000F306
0x18000f2eb  cmp     byte ptr [rcx+19h], 5
0x18000f2ef  jb      short loc_18000F306
0x18000f2f1  mov     rcx, [rcx+10h]
0x18000f2f5  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000f2fc  mov     edx, 16h
0x18000f301  call    WPP_SF_
0x18000f306  mov     eax, [rbx+48h]
0x18000f309  mov     r14d, 2
0x18000f30f  mov     [rbx+24h], r14d
0x18000f313  xor     esi, esi
0x18000f315  mov     [rbx+rax*4+28h], r14d
0x18000f31a  inc     dword ptr [rbx+48h]
0x18000f31d  cmp     dword ptr [rbx+48h], 8
0x18000f321  jb      short loc_18000F326
0x18000f323  mov     [rbx+48h], esi
0x18000f326  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f32d  cmp     rcx, r12
0x18000f330  jz      short loc_18000F353
0x18000f332  test    byte ptr [rcx+1Ch], 1
0x18000f336  jz      short loc_18000F353
0x18000f338  cmp     byte ptr [rcx+19h], 5
0x18000f33c  jb      short loc_18000F353
0x18000f33e  mov     rcx, [rcx+10h]
0x18000f342  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000f349  mov     edx, 18h
0x18000f34e  call    WPP_SF_
0x18000f353  test    byte ptr [rbx+20h], 20h
0x18000f357  jnz     short loc_18000F3C5
0x18000f359  mov     rcx, rbx; this
0x18000f35c  call    ?FindOrCreateApxRootContainer@ApfDevice@Apx@@AEAAJXZ; Apx::ApfDevice::FindOrCreateApxRootContainer(void)
0x18000f361  mov     edi, eax
0x18000f363  test    eax, eax
0x18000f365  js      short loc_18000F3D4
0x18000f367  mov     eax, 7FFFFFFEh
0x18000f36c  lea     rcx, pDeviceID; "SWD\\APXENUM\\0"
0x18000f373  mov     edx, 105h
0x18000f378  lea     r8, [rbx+55Ch]
0x18000f37f  test    rax, rax
0x18000f382  jz      short loc_18000F3A1
0x18000f384  movzx   r9d, word ptr [rcx]
0x18000f388  test    r9w, r9w
0x18000f38c  jz      short loc_18000F3A1
0x18000f38e  mov     [r8], r9w
0x18000f392  add     rcx, r14
0x18000f395  add     r8, r14
0x18000f398  dec     rax
0x18000f39b  sub     rdx, 1
0x18000f39f  jnz     short loc_18000F37F
0x18000f3a1  mov     rax, rdx
0x18000f3a4  lea     rcx, [r8-2]
0x18000f3a8  neg     rax
0x18000f3ab  sbb     edi, edi
0x18000f3ad  not     edi
0x18000f3af  and     edi, 8007007Ah
0x18000f3b5  test    rdx, rdx
0x18000f3b8  cmovnz  rcx, r8
0x18000f3bc  mov     [rcx], si
0x18000f3bf  jz      short loc_18000F3D4
0x18000f3c1  or      dword ptr [rbx+20h], 20h
0x18000f3c5  mov     rcx, rbx; this
0x18000f3c8  call    ?CreateApxDevice@ApfDevice@Apx@@AEAAJXZ; Apx::ApfDevice::CreateApxDevice(void)
0x18000f3cd  test    eax, eax
0x18000f3cf  mov     edi, eax
0x18000f3d1  cmovns  edi, esi
0x18000f3d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3db  cmp     rcx, r12
0x18000f3de  jz      short loc_18000F401
0x18000f3e0  test    byte ptr [rcx+1Ch], 1
0x18000f3e4  jz      short loc_18000F401
0x18000f3e6  cmp     byte ptr [rcx+19h], 5
0x18000f3ea  jb      short loc_18000F401
0x18000f3ec  mov     rcx, [rcx+10h]
0x18000f3f0  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000f3f7  mov     edx, 19h
0x18000f3fc  call    WPP_SF_
0x18000f401  cmp     edi, 80070005h
0x18000f407  jnz     short loc_18000F426
0x18000f409  test    dword ptr [rbx+20h], 100h
0x18000f410  jnz     short loc_18000F42C
0x18000f412  mov     rcx, rbx; this
0x18000f415  call    ?CreateDevice_Remote@ApfDevice@Apx@@AEAAJXZ; Apx::ApfDevice::CreateDevice_Remote(void)
0x18000f41a  mov     edi, eax
0x18000f41c  test    eax, eax
0x18000f41e  js      short loc_18000F42C
0x18000f420  mov     byte ptr [rbx+10h], 1
0x18000f424  jmp     short loc_18000F42A
0x18000f426  test    edi, edi
0x18000f428  js      short loc_18000F42C
0x18000f42a  mov     edi, esi
0x18000f42c  call    ?Instance@ApxTelemetryProvider@@KAPEAV1@XZ; ApxTelemetryProvider::Instance(void)
0x18000f431  mov     r10, [rax+8]
0x18000f435  mov     eax, [r10]
0x18000f438  cmp     eax, 4
0x18000f43b  jbe     loc_18000F613
0x18000f441  mov     rcx, [r10+18h]
0x18000f445  mov     rdx, 400000000001h
0x18000f44f  mov     rax, [r10+10h]
0x18000f453  test    rdx, rax
0x18000f456  jz      loc_18000F613
0x18000f45c  mov     rax, rcx
0x18000f45f  and     rax, rdx
0x18000f462  cmp     rax, rcx
0x18000f465  jnz     loc_18000F613
0x18000f46b  mov     rax, rbx
0x18000f46e  mov     [rsp+1A0h+var_168], edi
0x18000f472  not     rax
0x18000f475  mov     [rsp+1A0h+var_150], 800h
0x18000f47e  mov     [rsp+1A0h+var_158], rax
0x18000f483  lea     rdx, [rbx+55Ch]
0x18000f48a  mov     eax, [rbx+20h]
0x18000f48d  lea     r8, [rbx+148h]
0x18000f494  shr     eax, 8
0x18000f497  lea     r9, [rbx+98h]
0x18000f49e  and     eax, 1
0x18000f4a1  mov     [rbp+0A0h+var_48], 4
0x18000f4a9  mov     [rsp+1A0h+var_164], eax
0x18000f4ad  lea     r11, [rbx+88h]
0x18000f4b4  mov     eax, [rbx+0B8h]
0x18000f4ba  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000f4be  mov     [rsp+1A0h+var_160], eax
0x18000f4c2  movzx   eax, word ptr [rbx+0B0h]
0x18000f4c9  mov     [rsp+1A0h+var_170], ax
0x18000f4ce  mov     eax, [rbx+0ACh]
0x18000f4d4  mov     [rsp+1A0h+var_15C], eax
0x18000f4d8  movzx   eax, word ptr [rbx+0AAh]
0x18000f4df  mov     [rsp+1A0h+var_16E], ax
0x18000f4e4  movzx   eax, word ptr [rbx+0A8h]
0x18000f4eb  add     rbx, 78h ; 'x'
0x18000f4ef  mov     [rsp+1A0h+var_16C], ax
0x18000f4f4  lea     rax, [rsp+1A0h+var_168]
0x18000f4f9  mov     [rbp+0A0h+var_50], rax
0x18000f4fd  lea     rax, [rsp+1A0h+var_158]
0x18000f502  mov     [rbp+0A0h+var_60], rax
0x18000f506  lea     rax, [rsp+1A0h+var_164]
0x18000f50b  mov     [rbp+0A0h+var_70], rax
0x18000f50f  mov     [rbp+0A0h+var_58], 8
0x18000f517  mov     [rbp+0A0h+var_68], 4
0x18000f51f  test    rdx, rdx
0x18000f522  jz      short loc_18000F539
0x18000f524  mov     rax, rcx
0x18000f527  inc     rax
0x18000f52a  cmp     [rdx+rax*2], si
0x18000f52e  jnz     short loc_18000F527
0x18000f530  lea     eax, ds:2[rax*2]
0x18000f537  jmp     short loc_18000F543
0x18000f539  lea     rdx, qword_18002C8D0
0x18000f540  mov     eax, r14d
0x18000f543  mov     [rbp+0A0h+var_80], rdx
0x18000f547  mov     [rbp+0A0h+var_78], eax
0x18000f54a  mov     [rbp+0A0h+var_74], esi
0x18000f54d  test    r8, r8
0x18000f550  jz      short loc_18000F565
0x18000f552  inc     rcx
0x18000f555  cmp     [r8+rcx*2], si
0x18000f55a  jnz     short loc_18000F552
0x18000f55c  lea     ecx, ds:2[rcx*2]
0x18000f563  jmp     short loc_18000F56F
0x18000f565  lea     r8, qword_18002C8D0
0x18000f56c  mov     ecx, r14d
0x18000f56f  mov     [rbp+0A0h+var_88], ecx
0x18000f572  lea     rax, [rsp+1A0h+var_160]
0x18000f577  mov     [rbp+0A0h+var_A0], rax
0x18000f57b  lea     rdx, byte_18002E3C3
0x18000f582  mov     ecx, 10h
0x18000f587  mov     [rbp+0A0h+var_90], r8
0x18000f58b  lea     rax, [rsp+1A0h+var_170]
0x18000f590  mov     [rbp+0A0h+var_F0], r9
0x18000f594  mov     [rbp+0A0h+var_B0], rax
0x18000f598  xor     r9d, r9d
0x18000f59b  lea     rax, [rsp+1A0h+var_15C]
0x18000f5a0  mov     [rbp+0A0h+var_E8], rcx
0x18000f5a4  mov     [rbp+0A0h+var_C0], rax
0x18000f5a8  xor     r8d, r8d
0x18000f5ab  lea     rax, [rsp+1A0h+var_16E]
0x18000f5b0  mov     [rbp+0A0h+var_F8], rcx
0x18000f5b4  mov     [rbp+0A0h+var_D0], rax
0x18000f5b8  lea     rax, [rsp+1A0h+var_16C]
0x18000f5bd  mov     [rbp+0A0h+var_E0], rax
0x18000f5c1  lea     rax, [rsp+1A0h+var_150]
0x18000f5c6  mov     [rbp+0A0h+var_120], rax
0x18000f5ca  lea     rax, [rsp+1A0h+var_140]
0x18000f5cf  mov     [rsp+1A0h+var_178], rax
0x18000f5d4  mov     [rsp+1A0h+var_180], ecx
0x18000f5d8  mov     [rbp+0A0h+var_108], rcx
0x18000f5dc  mov     rcx, r10
0x18000f5df  mov     [rbp+0A0h+var_84], esi
0x18000f5e2  mov     [rbp+0A0h+var_98], 4
0x18000f5ea  mov     [rbp+0A0h+var_A8], r14
0x18000f5ee  mov     [rbp+0A0h+var_B8], 4
0x18000f5f6  mov     [rbp+0A0h+var_C8], r14
0x18000f5fa  mov     [rbp+0A0h+var_D8], r14
0x18000f5fe  mov     [rbp+0A0h+var_100], r11
0x18000f602  mov     [rbp+0A0h+var_110], rbx
0x18000f606  mov     [rbp+0A0h+var_118], 8
0x18000f60e  call    _tlgWriteTransfer_EventWriteTransfer
0x18000f613  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f61a  cmp     rcx, r12
0x18000f61d  jz      short loc_18000F640
0x18000f61f  test    byte ptr [rcx+1Ch], 1
0x18000f623  jz      short loc_18000F640
0x18000f625  cmp     byte ptr [rcx+19h], 5
0x18000f629  jb      short loc_18000F640
0x18000f62b  mov     rcx, [rcx+10h]
0x18000f62f  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000f636  mov     edx, 17h
0x18000f63b  call    WPP_SF_
0x18000f640  mov     eax, edi
0x18000f642  mov     rcx, [rbp+0A0h+var_40]
0x18000f646  xor     rcx, rsp; StackCookie
0x18000f649  call    __security_check_cookie
0x18000f64e  add     rsp, 178h
0x18000f655  pop     r14
0x18000f657  pop     r12
0x18000f659  pop     rdi
0x18000f65a  pop     rsi
0x18000f65b  pop     rbx
0x18000f65c  pop     rbp
0x18000f65d  retn
```
