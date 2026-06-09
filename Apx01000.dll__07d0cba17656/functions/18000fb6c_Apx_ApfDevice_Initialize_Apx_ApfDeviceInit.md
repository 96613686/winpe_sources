# Apx::ApfDevice::Initialize(Apx::ApfDeviceInit *)

- ea: `0x18000fb6c`
- end: `0x18000fed6`
- name: `?Initialize@ApfDevice@Apx@@AEAAJPEAVApfDeviceInit@2@@Z`
- size: `874`
- prototype: `__int64 __fastcall(Apx::ApfDevice *__hidden this, struct Apx::ApfDeviceInit *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010430`

## callees

- `0x18000a12c`
- `0x18000a1b4`
- `0x18000af34`
- `0x18000caac`
- `0x18000eae4`
- `0x18000eca0`
- `0x18000f2ac`
- `0x18000fb6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fc59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fc6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fc59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fc6b`

## pseudocode

```c
__int64 __fastcall Apx::ApfDevice::Initialize(Apx::ApfDevice *this, struct Apx::ApfDeviceInit *a2)
{
  signed int Device; // ebx
  __int64 v5; // rax
  int v7; // eax
  int v8; // ebx
  __int128 v9; // xmm0
  __int128 v10; // xmm0
  __int128 v11; // xmm0
  __int16 v12; // ax
  __int64 v13; // r11
  __int64 v14; // r8
  __int64 v15; // rax
  _WORD *v16; // rcx
  __int64 v17; // rdx
  _WORD *v18; // r9
  _WORD *v19; // rcx
  __int64 v20; // rax
  _WORD *v21; // rcx
  _WORD *v22; // rdx
  _WORD *v23; // rcx
  int v24; // eax
  _WORD *v25; // r8
  _WORD *v26; // rax
  __int64 v27; // rdx
  _WORD *v28; // rcx
  __int64 v29; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  Device = Apx::ApfWorkItemQueue::Initialize((Apx::ApfDevice *)((char *)this + 208));
  if ( Device < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
    }
    goto LABEL_10;
  }
  v7 = *((_DWORD *)a2 + 19);
  *((_DWORD *)this + 45) = v7;
  if ( !v7 )
    *((_DWORD *)this + 45) = GetCurrentProcessId();
  v8 = *((_DWORD *)this + 45);
  if ( v8 != GetCurrentProcessId() )
    *((_DWORD *)this + 8) |= 0x100u;
  *((_DWORD *)this + 46) = *((_DWORD *)a2 + 20);
  if ( (*((_BYTE *)a2 + 24) & 2) != 0 )
  {
    v9 = *(_OWORD *)((char *)a2 + 28);
    *((_DWORD *)this + 8) |= 1u;
    *(_OWORD *)((char *)this + 120) = v9;
  }
  if ( (*((_BYTE *)a2 + 24) & 4) != 0 )
  {
    v10 = *(_OWORD *)((char *)a2 + 44);
    *((_DWORD *)this + 8) |= 2u;
    *(_OWORD *)((char *)this + 152) = v10;
  }
  if ( (*((_BYTE *)a2 + 24) & 8) != 0 )
  {
    v11 = *(_OWORD *)((char *)a2 + 60);
    *((_DWORD *)this + 8) |= 4u;
    *(_OWORD *)((char *)this + 136) = v11;
  }
  if ( (*((_BYTE *)a2 + 24) & 0x40) != 0 )
  {
    *((_WORD *)this + 84) = *((_WORD *)a2 + 48);
    *((_WORD *)this + 85) = *((_WORD *)a2 + 49);
    *((_DWORD *)this + 43) = *((_DWORD *)a2 + 25);
    v12 = *((_WORD *)a2 + 52);
    *((_DWORD *)this + 8) |= 0x40u;
    *((_WORD *)this + 88) = v12;
  }
  v13 = 2147483646;
  v14 = 261;
  if ( (*((_BYTE *)a2 + 24) & 0x10) != 0 )
  {
    v15 = 2147483646;
    v16 = (_WORD *)((char *)a2 + 106);
    v17 = 261;
    v18 = (_WORD *)((char *)this + 328);
    do
    {
      if ( !v15 )
        break;
      if ( !*v16 )
        break;
      *v18++ = *v16++;
      --v15;
      --v17;
    }
    while ( v17 );
    v19 = v18 - 1;
    Device = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v19 = v18;
    *v19 = 0;
    if ( !v17 )
      goto LABEL_10;
    *((_DWORD *)this + 8) |= 8u;
  }
  if ( (*((_BYTE *)a2 + 24) & 0x20) != 0 )
  {
    v20 = 2147483646;
    v21 = (_WORD *)((char *)a2 + 628);
    v22 = (_WORD *)((char *)this + 1372);
    do
    {
      if ( !v20 )
        break;
      if ( !*v21 )
        break;
      *v22++ = *v21++;
      --v20;
      --v14;
    }
    while ( v14 );
    v23 = v22 - 1;
    Device = v14 == 0 ? 0x8007007A : 0;
    if ( v14 )
      v23 = v22;
    *v23 = 0;
    if ( !v14 )
      goto LABEL_10;
    *((_DWORD *)this + 8) |= 0x20u;
  }
  if ( *((char *)a2 + 24) < 0 )
    *((_DWORD *)this + 8) |= 0x80u;
  v24 = *((_DWORD *)a2 + 288);
  if ( v24 )
  {
    *((_DWORD *)this + 474) = v24;
    v25 = (_WORD *)((char *)this + 1900);
    v26 = (_WORD *)((char *)a2 + 1156);
    v27 = 80;
    do
    {
      if ( !v13 )
        break;
      if ( !*v26 )
        break;
      *v25++ = *v26++;
      --v13;
      --v27;
    }
    while ( v27 );
    v28 = v25 - 1;
    if ( v27 )
      v28 = v25;
    *v28 = 0;
    if ( !v27 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids,
          (_DWORD)a2 + 1156,
          v27 == 0 ? 0x7A : 0);
      }
      *((_DWORD *)this + 474) = 0;
    }
  }
  Device = Apx::ApfDevice::BuildHardwareIDs(this);
  if ( Device < 0
    || (Device = Apx::ApfDevice::BuildCompatibleIDs(this), Device < 0)
    || (Device = Apx::ApfDevice::CreateDevice((unsigned __int64)this), Device < 0) )
  {
LABEL_10:
    v5 = *((unsigned int *)this + 18);
    *((_DWORD *)this + 9) = 6;
    *((_DWORD *)this + v5 + 10) = 6;
    if ( ++*((_DWORD *)this + 18) >= 8u )
      *((_DWORD *)this + 18) = 0;
    goto LABEL_12;
  }
  v29 = *((unsigned int *)this + 18);
  *((_DWORD *)this + 9) = 3;
  *((_DWORD *)this + v29 + 10) = 3;
  if ( ++*((_DWORD *)this + 18) >= 8u )
    *((_DWORD *)this + 18) = 0;
  Device = 0;
LABEL_12:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  return (unsigned int)Device;
}

```

## disassembly

```asm
0x18000fb6c  push    rbx
0x18000fb6e  push    rbp
0x18000fb6f  push    rsi
0x18000fb70  push    rdi
0x18000fb71  push    r12
0x18000fb73  sub     rsp, 30h
0x18000fb77  mov     rsi, rdx
0x18000fb7a  mov     rdi, rcx
0x18000fb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb84  lea     r12, WPP_GLOBAL_Control
0x18000fb8b  cmp     rcx, r12
0x18000fb8e  jz      short loc_18000FBB1
0x18000fb90  test    byte ptr [rcx+1Ch], 1
0x18000fb94  jz      short loc_18000FBB1
0x18000fb96  cmp     byte ptr [rcx+19h], 5
0x18000fb9a  jb      short loc_18000FBB1
0x18000fb9c  mov     rcx, [rcx+10h]
0x18000fba0  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000fba7  mov     edx, 10h
0x18000fbac  call    WPP_SF_
0x18000fbb1  lea     rcx, [rdi+0D0h]; this
0x18000fbb8  call    ?Initialize@ApfWorkItemQueue@Apx@@QEAAJXZ; Apx::ApfWorkItemQueue::Initialize(void)
0x18000fbbd  xor     ebp, ebp
0x18000fbbf  mov     ebx, eax
0x18000fbc1  test    eax, eax
0x18000fbc3  jns     loc_18000FC4C
0x18000fbc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbd0  cmp     rcx, r12
0x18000fbd3  jz      short loc_18000FBF7
0x18000fbd5  test    byte ptr [rcx+1Ch], 20h
0x18000fbd9  jz      short loc_18000FBF7
0x18000fbdb  cmp     byte ptr [rcx+19h], 2
0x18000fbdf  jb      short loc_18000FBF7
0x18000fbe1  mov     rcx, [rcx+10h]
0x18000fbe5  lea     edx, [rbp+11h]
0x18000fbe8  mov     r9d, eax
0x18000fbeb  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000fbf2  call    WPP_SF_d
0x18000fbf7  mov     eax, [rdi+48h]
0x18000fbfa  mov     ecx, 6
0x18000fbff  mov     [rdi+24h], ecx
0x18000fc02  mov     [rdi+rax*4+28h], ecx
0x18000fc06  inc     dword ptr [rdi+48h]
0x18000fc09  cmp     dword ptr [rdi+48h], 8
0x18000fc0d  jb      short loc_18000FC12
0x18000fc0f  mov     [rdi+48h], ebp
0x18000fc12  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc19  cmp     rcx, r12
0x18000fc1c  jz      short loc_18000FC3F
0x18000fc1e  test    byte ptr [rcx+1Ch], 1
0x18000fc22  jz      short loc_18000FC3F
0x18000fc24  cmp     byte ptr [rcx+19h], 5
0x18000fc28  jb      short loc_18000FC3F
0x18000fc2a  mov     rcx, [rcx+10h]
0x18000fc2e  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000fc35  mov     edx, 13h
0x18000fc3a  call    WPP_SF_
0x18000fc3f  mov     eax, ebx
0x18000fc41  add     rsp, 30h
0x18000fc45  pop     r12
0x18000fc47  pop     rdi
0x18000fc48  pop     rsi
0x18000fc49  pop     rbp
0x18000fc4a  pop     rbx
0x18000fc4b  retn
0x18000fc4c  mov     eax, [rsi+4Ch]
0x18000fc4f  mov     [rdi+0B4h], eax
0x18000fc55  test    eax, eax
0x18000fc57  jnz     short loc_18000FC65
0x18000fc59  call    cs:__imp_GetCurrentProcessId
0x18000fc5f  mov     [rdi+0B4h], eax
0x18000fc65  mov     ebx, [rdi+0B4h]
0x18000fc6b  call    cs:__imp_GetCurrentProcessId
0x18000fc71  cmp     ebx, eax
0x18000fc73  jz      short loc_18000FC7A
0x18000fc75  bts     dword ptr [rdi+20h], 8
0x18000fc7a  mov     eax, [rsi+50h]
0x18000fc7d  mov     [rdi+0B8h], eax
0x18000fc83  test    byte ptr [rsi+18h], 2
0x18000fc87  jz      short loc_18000FC96
0x18000fc89  movups  xmm0, xmmword ptr [rsi+1Ch]
0x18000fc8d  or      dword ptr [rdi+20h], 1
0x18000fc91  movdqu  xmmword ptr [rdi+78h], xmm0
0x18000fc96  test    byte ptr [rsi+18h], 4
0x18000fc9a  jz      short loc_18000FCAC
0x18000fc9c  movups  xmm0, xmmword ptr [rsi+2Ch]
0x18000fca0  or      dword ptr [rdi+20h], 2
0x18000fca4  movdqu  xmmword ptr [rdi+98h], xmm0
0x18000fcac  test    byte ptr [rsi+18h], 8
0x18000fcb0  jz      short loc_18000FCC2
0x18000fcb2  movups  xmm0, xmmword ptr [rsi+3Ch]
0x18000fcb6  or      dword ptr [rdi+20h], 4
0x18000fcba  movdqu  xmmword ptr [rdi+88h], xmm0
0x18000fcc2  test    byte ptr [rsi+18h], 40h
0x18000fcc6  jz      short loc_18000FCF6
0x18000fcc8  movzx   eax, word ptr [rsi+60h]
0x18000fccc  mov     [rdi+0A8h], ax
0x18000fcd3  movzx   eax, word ptr [rsi+62h]
0x18000fcd7  mov     [rdi+0AAh], ax
0x18000fcde  mov     eax, [rsi+64h]
0x18000fce1  mov     [rdi+0ACh], eax
0x18000fce7  movzx   eax, word ptr [rsi+68h]
0x18000fceb  or      dword ptr [rdi+20h], 40h
0x18000fcef  mov     [rdi+0B0h], ax
0x18000fcf6  test    byte ptr [rsi+18h], 10h
0x18000fcfa  mov     r11d, 7FFFFFFEh
0x18000fd00  mov     r8d, 105h
0x18000fd06  jz      short loc_18000FD65
0x18000fd08  mov     eax, r11d
0x18000fd0b  lea     rcx, [rsi+6Ah]
0x18000fd0f  mov     edx, r8d
0x18000fd12  lea     r9, [rdi+148h]
0x18000fd19  test    rax, rax
0x18000fd1c  jz      short loc_18000FD3D
0x18000fd1e  movzx   r10d, word ptr [rcx]
0x18000fd22  test    r10w, r10w
0x18000fd26  jz      short loc_18000FD3D
0x18000fd28  mov     [r9], r10w
0x18000fd2c  add     rcx, 2
0x18000fd30  add     r9, 2
0x18000fd34  dec     rax
0x18000fd37  sub     rdx, 1
0x18000fd3b  jnz     short loc_18000FD19
0x18000fd3d  mov     rax, rdx
0x18000fd40  lea     rcx, [r9-2]
0x18000fd44  neg     rax
0x18000fd47  sbb     ebx, ebx
0x18000fd49  not     ebx
0x18000fd4b  and     ebx, 8007007Ah
0x18000fd51  test    rdx, rdx
0x18000fd54  cmovnz  rcx, r9
0x18000fd58  mov     [rcx], bp
0x18000fd5b  jz      loc_18000FBF7
0x18000fd61  or      dword ptr [rdi+20h], 8
0x18000fd65  test    byte ptr [rsi+18h], 20h
0x18000fd69  jz      short loc_18000FDC8
0x18000fd6b  mov     rax, r11
0x18000fd6e  lea     rcx, [rsi+274h]
0x18000fd75  lea     rdx, [rdi+55Ch]
0x18000fd7c  test    rax, rax
0x18000fd7f  jz      short loc_18000FDA0
0x18000fd81  movzx   r9d, word ptr [rcx]
0x18000fd85  test    r9w, r9w
0x18000fd89  jz      short loc_18000FDA0
0x18000fd8b  mov     [rdx], r9w
0x18000fd8f  add     rcx, 2
0x18000fd93  add     rdx, 2
0x18000fd97  dec     rax
0x18000fd9a  sub     r8, 1
0x18000fd9e  jnz     short loc_18000FD7C
0x18000fda0  mov     rax, r8
0x18000fda3  lea     rcx, [rdx-2]
0x18000fda7  neg     rax
0x18000fdaa  sbb     ebx, ebx
0x18000fdac  not     ebx
0x18000fdae  and     ebx, 8007007Ah
0x18000fdb4  test    r8, r8
0x18000fdb7  cmovnz  rcx, rdx
0x18000fdbb  mov     [rcx], bp
0x18000fdbe  jz      loc_18000FBF7
0x18000fdc4  or      dword ptr [rdi+20h], 20h
0x18000fdc8  test    byte ptr [rsi+18h], 80h
0x18000fdcc  jz      short loc_18000FDD3
0x18000fdce  bts     dword ptr [rdi+20h], 7
0x18000fdd3  mov     eax, [rsi+480h]
0x18000fdd9  test    eax, eax
0x18000fddb  jz      loc_18000FE7E
0x18000fde1  mov     [rdi+768h], eax
0x18000fde7  lea     r8, [rdi+76Ch]
0x18000fdee  lea     rax, [rsi+484h]
0x18000fdf5  mov     edx, 50h ; 'P'
0x18000fdfa  test    r11, r11
0x18000fdfd  jz      short loc_18000FE1C
0x18000fdff  movzx   ecx, word ptr [rax]
0x18000fe02  test    cx, cx
0x18000fe05  jz      short loc_18000FE1C
0x18000fe07  mov     [r8], cx
0x18000fe0b  add     rax, 2
0x18000fe0f  add     r8, 2
0x18000fe13  dec     r11
0x18000fe16  sub     rdx, 1
0x18000fe1a  jnz     short loc_18000FDFA
0x18000fe1c  mov     rax, rdx
0x18000fe1f  lea     rcx, [r8-2]
0x18000fe23  neg     rax
0x18000fe26  sbb     r10d, r10d
0x18000fe29  not     r10d
0x18000fe2c  and     r10d, 8007007Ah
0x18000fe33  test    rdx, rdx
0x18000fe36  cmovnz  rcx, r8
0x18000fe3a  mov     [rcx], bp
0x18000fe3d  jnz     short loc_18000FE7E
0x18000fe3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe46  cmp     rcx, r12
0x18000fe49  jz      short loc_18000FE78
0x18000fe4b  test    byte ptr [rcx+1Ch], 20h
0x18000fe4f  jz      short loc_18000FE78
0x18000fe51  cmp     byte ptr [rcx+19h], 2
0x18000fe55  jb      short loc_18000FE78
0x18000fe57  mov     rcx, [rcx+10h]
0x18000fe5b  lea     r9, [rsi+484h]
0x18000fe62  mov     edx, 12h
0x18000fe67  mov     [rsp+58h+var_38], r10d
0x18000fe6c  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000fe73  call    WPP_SF_Sd
0x18000fe78  mov     [rdi+768h], ebp
0x18000fe7e  mov     rcx, rdi; this
0x18000fe81  call    ?BuildHardwareIDs@ApfDevice@Apx@@AEAAJXZ; Apx::ApfDevice::BuildHardwareIDs(void)
0x18000fe86  mov     ebx, eax
0x18000fe88  test    eax, eax
0x18000fe8a  js      loc_18000FBF7
0x18000fe90  mov     rcx, rdi; this
0x18000fe93  call    ?BuildCompatibleIDs@ApfDevice@Apx@@AEAAJXZ; Apx::ApfDevice::BuildCompatibleIDs(void)
0x18000fe98  mov     ebx, eax
0x18000fe9a  test    eax, eax
0x18000fe9c  js      loc_18000FBF7
0x18000fea2  mov     rcx, rdi; this
0x18000fea5  call    ?CreateDevice@ApfDevice@Apx@@AEAAJXZ; Apx::ApfDevice::CreateDevice(void)
0x18000feaa  mov     ebx, eax
0x18000feac  test    eax, eax
0x18000feae  js      loc_18000FBF7
0x18000feb4  mov     eax, [rdi+48h]
0x18000feb7  mov     ecx, 3
0x18000febc  mov     [rdi+24h], ecx
0x18000febf  mov     [rdi+rax*4+28h], ecx
0x18000fec3  inc     dword ptr [rdi+48h]
0x18000fec6  cmp     dword ptr [rdi+48h], 8
0x18000feca  jb      short loc_18000FECF
0x18000fecc  mov     [rdi+48h], ebp
0x18000fecf  mov     ebx, ebp
0x18000fed1  jmp     loc_18000FC12
```
