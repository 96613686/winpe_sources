# UlQueryServiceConfigIoctl

- ea: `0x140018210`
- end: `0x14001884c`
- name: `UlQueryServiceConfigIoctl`
- size: `1596`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140018210`
- `0x140018854`
- `0x140018934`
- `0x1400191f8`
- `0x1400a7518`
- `0x1400f1248`
- `0x14012eefc`
- `0x14013e214`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c45cc`
- `0x1401cde34`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400184ff`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400184ff`
- `ntoskrnl!IofCompleteRequest` at `0x14001847c`
- `ntoskrnl!IofCompleteRequest` at `0x14001847c`
- `ntoskrnl!IoIs32bitProcess` at `0x14001829a`
- `ntoskrnl!IoIs32bitProcess` at `0x1400182f4`
- `ntoskrnl!IoIs32bitProcess` at `0x140018343`
- `ntoskrnl!IoIs32bitProcess` at `0x1400184af`
- `ntoskrnl!IoIs32bitProcess` at `0x1400184cb`
- `ntoskrnl!IoIs32bitProcess` at `0x140018685`
- `ntoskrnl!IoIs32bitProcess` at `0x140172447`
- `ntoskrnl!IoIs32bitProcess` at `0x140172471`
- `ntoskrnl!IoIs32bitProcess` at `0x140172487`
- `ntoskrnl!IoIs32bitProcess` at `0x14001829a`
- `ntoskrnl!IoIs32bitProcess` at `0x1400182f4`
- `ntoskrnl!IoIs32bitProcess` at `0x140018343`
- `ntoskrnl!IoIs32bitProcess` at `0x1400184af`
- `ntoskrnl!IoIs32bitProcess` at `0x1400184cb`
- `ntoskrnl!IoIs32bitProcess` at `0x140018685`
- `ntoskrnl!IoIs32bitProcess` at `0x140172447`
- `ntoskrnl!IoIs32bitProcess` at `0x140172471`
- `ntoskrnl!IoIs32bitProcess` at `0x140172487`

## pseudocode

```c
__int64 __fastcall UlQueryServiceConfigIoctl(PIRP Irp, __int64 a2)
{
  unsigned int v4; // esi
  NTSTATUS CommChannel; // ebx
  struct _IRP *v6; // r9
  struct _IRP *MasterIrp; // rax
  int *p_Type; // r14
  int v9; // ecx
  unsigned __int64 v10; // rbx
  int v11; // ecx
  int v12; // ecx
  IRP *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  PMDL MdlAddress; // r11
  _DWORD *v18; // r8
  __int64 v19; // r10
  unsigned int v20; // edx
  _DWORD *MappedSystemVa; // rax
  PMDL v22; // rax
  int v23; // ecx
  int v24; // ecx
  NTSTATUS SslBindingExtendedProperties; // eax
  BOOLEAN v27; // al
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  BOOLEAN v37; // al
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  unsigned int v42; // ecx
  BOOLEAN v43; // al
  __int64 v44; // r9
  __int64 v45; // rax
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  struct _IRP *v47; // [rsp+68h] [rbp-98h] BYREF
  _DWORD *v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v50[192]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v51; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v52; // [rsp+168h] [rbp+68h] BYREF

  v46 = 0;
  v51 = 0;
  v4 = 160;
  v48 = 0;
  v49 = 0;
  v52 = 0;
  v47 = 0;
  memset(v50, 0, 0xA0u);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qq(1033, 112, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, Irp, a2);
  CommChannel = UlGetCommChannel(a2, &v46);
  if ( CommChannel < 0 )
    goto LABEL_41;
  IoIs32bitProcess(Irp);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qilq(1033, 18, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, Irp, a2, 160, &v47);
  v6 = 0;
  v47 = 0;
  if ( *(_DWORD *)(a2 + 16) < 0xA0u )
  {
    CommChannel = -1073741789;
  }
  else
  {
    MasterIrp = Irp->AssociatedIrp.MasterIrp;
    if ( MasterIrp )
    {
      CommChannel = 0;
      v47 = Irp->AssociatedIrp.MasterIrp;
      v6 = MasterIrp;
    }
    else
    {
      CommChannel = -1073741811;
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qD(1033, 19, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, v6, CommChannel);
  if ( CommChannel < 0 )
    goto LABEL_41;
  if ( IoIs32bitProcess(Irp) )
  {
    UlpCaptureServiceConfigInfo32(v47, v50);
    p_Type = (int *)v50;
  }
  else
  {
    p_Type = (int *)&v47->Type;
  }
  v9 = *p_Type;
  v10 = 4;
  if ( *p_Type > 7 )
  {
    v38 = v9 - 8;
    if ( v38 )
    {
      v39 = v38 - 1;
      if ( !v39 )
      {
LABEL_98:
        IoIs32bitProcess(Irp);
        v4 = 168;
        goto LABEL_100;
      }
      v40 = v39 - 1;
      if ( v40 )
      {
        v41 = v40 - 1;
        if ( !v41 )
          goto LABEL_95;
        if ( v41 != 1 )
          goto LABEL_94;
        goto LABEL_98;
      }
    }
    IoIs32bitProcess(Irp);
    goto LABEL_100;
  }
  if ( v9 == 7 )
  {
LABEL_19:
    v4 = v10;
    v13 = Irp;
LABEL_20:
    IoIs32bitProcess(v13);
    goto LABEL_21;
  }
  if ( !v9 )
  {
    v4 = 136;
LABEL_100:
    v13 = Irp;
    goto LABEL_50;
  }
  v11 = v9 - 1;
  if ( v11 )
  {
    v10 = 2;
    v12 = v11 - 2;
    if ( !v12 )
      goto LABEL_19;
    v35 = v12 - 1;
    if ( !v35 )
    {
      v10 = 4;
      goto LABEL_19;
    }
    v36 = v35 - 1;
    if ( v36 )
    {
      if ( v36 == 1 )
      {
        v37 = IoIs32bitProcess(Irp);
        v13 = Irp;
        if ( v37 )
          v4 = 184;
        else
          v4 = 208;
        goto LABEL_50;
      }
LABEL_94:
      CommChannel = -1073741811;
      goto LABEL_41;
    }
LABEL_95:
    v43 = IoIs32bitProcess(Irp);
    v13 = Irp;
    if ( v43 )
      v4 = 192;
    else
      v4 = 216;
    goto LABEL_50;
  }
  v27 = IoIs32bitProcess(Irp);
  v13 = Irp;
  if ( v27 )
  {
    v4 = 56;
    goto LABEL_20;
  }
  v4 = 88;
LABEL_50:
  v10 = (-(__int64)(IoIs32bitProcess(v13) != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 8;
LABEL_21:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqLPqqq(v15, v14, v16, Irp, a2, v4, v10, &v48, &v49, &v52);
  MdlAddress = Irp->MdlAddress;
  v18 = 0;
  v19 = 0;
  v48 = 0;
  v20 = 0;
  v49 = 0;
  v52 = 0;
  if ( MdlAddress && *(_DWORD *)(a2 + 8) >= v4 )
  {
    if ( (((unsigned __int64)MdlAddress->StartVa + MdlAddress->ByteOffset) & (v10 - 1)) != 0 )
    {
      CommChannel = -1073741115;
    }
    else
    {
      if ( (MdlAddress->MdlFlags & 5) != 0 )
      {
        MappedSystemVa = MdlAddress->MappedSystemVa;
      }
      else
      {
        MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000000u);
        v18 = v48;
        v19 = v49;
        v20 = v52;
      }
      if ( MappedSystemVa )
      {
        v20 = *(_DWORD *)(a2 + 8);
        v18 = MappedSystemVa;
        v48 = MappedSystemVa;
        v22 = Irp->MdlAddress;
        v52 = v20;
        v19 = (__int64)v22->StartVa + v22->ByteOffset;
        v49 = v19;
        CommChannel = 0;
      }
      else
      {
        CommChannel = -1073741670;
      }
    }
  }
  else
  {
    CommChannel = -2147483643;
    Irp->IoStatus.Information = v4;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
  {
    WPP_SF_d(1033, 25, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)CommChannel);
    v18 = v48;
    v19 = v49;
    v20 = v52;
  }
  if ( CommChannel >= 0 )
  {
    v23 = *p_Type;
    if ( *p_Type > 7 )
    {
      v31 = v23 - 8;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( v32 )
        {
          v33 = v32 - 1;
          if ( v33 )
          {
            v34 = v33 - 1;
            if ( v34 )
            {
              if ( v34 != 1 )
                goto LABEL_40;
              SslBindingExtendedProperties = UlQuerySslBindingExtendedProperties(
                                               *(_QWORD *)(v46 + 56),
                                               4,
                                               p_Type[2],
                                               (int)p_Type + 16,
                                               p_Type[38],
                                               p_Type[39],
                                               (__int64)Irp,
                                               (__int64)v18,
                                               v19,
                                               v20,
                                               (__int64)&v51);
            }
            else
            {
              SslBindingExtendedProperties = UlQuerySslBinding(
                                               *(_QWORD *)(v46 + 56),
                                               4,
                                               p_Type[2],
                                               (int)p_Type + 16,
                                               p_Type[38],
                                               (__int64)Irp,
                                               (__int64)v18,
                                               v19,
                                               v20,
                                               (__int64)&v51);
            }
          }
          else
          {
            SslBindingExtendedProperties = UlQuerySslBindingExtendedProperties(
                                             *(_QWORD *)(v46 + 56),
                                             2,
                                             p_Type[2],
                                             (int)p_Type + 16,
                                             p_Type[38],
                                             p_Type[39],
                                             (__int64)Irp,
                                             (__int64)v18,
                                             v19,
                                             v20,
                                             (__int64)&v51);
          }
        }
        else
        {
          SslBindingExtendedProperties = UlQuerySslBindingExtendedProperties(
                                           *(_QWORD *)(v46 + 56),
                                           1,
                                           p_Type[2],
                                           (int)p_Type + 16,
                                           p_Type[38],
                                           p_Type[39],
                                           (__int64)Irp,
                                           (__int64)v18,
                                           v19,
                                           v20,
                                           (__int64)&v51);
        }
      }
      else
      {
        SslBindingExtendedProperties = UlQuerySslBindingExtendedProperties(
                                         *(_QWORD *)(v46 + 56),
                                         0,
                                         p_Type[2],
                                         (int)p_Type + 16,
                                         p_Type[38],
                                         p_Type[39],
                                         (__int64)Irp,
                                         (__int64)v18,
                                         v19,
                                         v20,
                                         (__int64)&v51);
      }
    }
    else if ( v23 == 7 )
    {
      SslBindingExtendedProperties = UlQuerySettingConfiguration(
                                       *(_QWORD *)(v46 + 56),
                                       p_Type[2],
                                       (_DWORD)v18,
                                       v20,
                                       (__int64)&v51);
    }
    else if ( v23 )
    {
      v24 = v23 - 1;
      if ( v24 )
      {
        v28 = v24 - 2;
        if ( v28 )
        {
          v29 = v28 - 1;
          if ( !v29 )
          {
            v42 = p_Type[2];
            if ( v42 <= 1 )
            {
              v44 = *(_QWORD *)(v46 + 56);
              v51 = 4;
              if ( v20 >= 4 )
              {
                v45 = 1120;
                if ( v42 != 1 )
                  v45 = 1116;
                CommChannel = 0;
                *v18 = *(_DWORD *)(v45 + v44);
              }
              else
              {
                CommChannel = -1073741675;
              }
            }
            else
            {
              CommChannel = -1073741811;
            }
LABEL_39:
            if ( (int)(CommChannel + 0x80000000) >= 0 && CommChannel != -2147483643 )
              goto LABEL_41;
LABEL_40:
            Irp->IoStatus.Information = v51;
            goto LABEL_41;
          }
          v30 = v29 - 1;
          if ( v30 )
          {
            if ( v30 != 1 )
              goto LABEL_40;
            SslBindingExtendedProperties = UlQuerySslBinding(
                                             *(_QWORD *)(v46 + 56),
                                             2,
                                             p_Type[2],
                                             (int)p_Type + 16,
                                             p_Type[38],
                                             (__int64)Irp,
                                             (__int64)v18,
                                             v19,
                                             v20,
                                             (__int64)&v51);
          }
          else
          {
            SslBindingExtendedProperties = UlQuerySslBinding(
                                             *(_QWORD *)(v46 + 56),
                                             1,
                                             p_Type[2],
                                             (int)p_Type + 16,
                                             p_Type[38],
                                             (__int64)Irp,
                                             (__int64)v18,
                                             v19,
                                             v20,
                                             (__int64)&v51);
          }
        }
        else
        {
          SslBindingExtendedProperties = UlQueryTimerConfiguration(
                                           *(_QWORD *)(v46 + 56),
                                           p_Type[2],
                                           (_DWORD)v18,
                                           v20,
                                           (__int64)&v51);
        }
      }
      else
      {
        SslBindingExtendedProperties = UlQuerySslBinding(
                                         *(_QWORD *)(v46 + 56),
                                         0,
                                         p_Type[2],
                                         (int)p_Type + 16,
                                         p_Type[38],
                                         (__int64)Irp,
                                         (__int64)v18,
                                         v19,
                                         v20,
                                         (__int64)&v51);
      }
    }
    else
    {
      SslBindingExtendedProperties = UlQueryIpListenList(*(_QWORD *)(v46 + 56), v20, (_DWORD)v18, v20, (__int64)&v51);
    }
    CommChannel = SslBindingExtendedProperties;
    goto LABEL_39;
  }
LABEL_41:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1033, 113, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, (unsigned int)CommChannel);
  if ( CommChannel != 259 )
  {
    Irp->IoStatus.Status = CommChannel;
    IofCompleteRequest(Irp, 0);
  }
  return (unsigned int)CommChannel;
}

```

## disassembly

```asm
0x140018210  mov     [rsp-8+arg_0], rbx
0x140018215  push    rbp
0x140018216  push    rsi
0x140018217  push    rdi
0x140018218  push    r14
0x14001821a  push    r15
0x14001821c  lea     rbp, [rsp-20h]
0x140018221  sub     rsp, 120h
0x140018228  mov     r15, rdx
0x14001822b  mov     [rsp+140h+var_E0], 0
0x140018234  mov     rdi, rcx
0x140018237  mov     [rbp+40h+arg_10], 0
0x14001823e  mov     esi, 0A0h
0x140018243  mov     [rsp+140h+var_D0], 0
0x14001824c  mov     r8d, esi; Size
0x14001824f  mov     [rsp+140h+var_C8], 0
0x140018258  xor     edx, edx; Val
0x14001825a  mov     [rbp+40h+arg_18], 0
0x140018261  lea     rcx, [rbp+40h+var_C0]; void *
0x140018265  mov     [rsp+140h+var_D8], 0
0x14001826e  call    memset
0x140018273  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14001827a  jnz     loc_140018644
0x140018280  lea     rdx, [rsp+140h+var_E0]
0x140018285  mov     rcx, r15
0x140018288  call    UlGetCommChannel
0x14001828d  mov     ebx, eax
0x14001828f  test    eax, eax
0x140018291  js      loc_14001845F
0x140018297  mov     rcx, rdi; Irp
0x14001829a  call    cs:__imp_IoIs32bitProcess
0x1400182a1  nop     dword ptr [rax+rax+00h]
0x1400182a6  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400182ad  jnz     loc_1400185E0
0x1400182b3  xor     r9d, r9d
0x1400182b6  mov     [rsp+140h+var_D8], r9
0x1400182bb  cmp     [r15+10h], esi
0x1400182bf  jb      loc_140018630
0x1400182c5  mov     rax, [rdi+18h]
0x1400182c9  test    rax, rax
0x1400182cc  jz      loc_14001863A
0x1400182d2  xor     ebx, ebx
0x1400182d4  mov     [rsp+140h+var_D8], rax
0x1400182d9  mov     r9, rax
0x1400182dc  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400182e3  jnz     loc_140018611
0x1400182e9  test    ebx, ebx
0x1400182eb  js      loc_14001845F
0x1400182f1  mov     rcx, rdi; Irp
0x1400182f4  call    cs:__imp_IoIs32bitProcess
0x1400182fb  nop     dword ptr [rax+rax+00h]
0x140018300  test    al, al
0x140018302  jnz     loc_140018598
0x140018308  mov     r14, [rsp+140h+var_D8]
0x14001830d  mov     ecx, [r14]
0x140018310  mov     ebx, 4
0x140018315  cmp     ecx, 7
0x140018318  jg      loc_1400186BA
0x14001831e  jz      short loc_14001833E
0x140018320  test    ecx, ecx
0x140018322  jz      loc_1400186B0
0x140018328  sub     ecx, 1
0x14001832b  jz      loc_1400184AC
0x140018331  mov     ebx, 2
0x140018336  sub     ecx, ebx
0x140018338  jnz     loc_140018667
0x14001833e  mov     esi, ebx
0x140018340  mov     rcx, rdi; Irp
0x140018343  call    cs:__imp_IoIs32bitProcess
0x14001834a  nop     dword ptr [rax+rax+00h]
0x14001834f  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140018356  jnz     loc_1400186EC
0x14001835c  mov     r11, [rdi+8]
0x140018360  xor     r8d, r8d
0x140018363  xor     r10d, r10d
0x140018366  mov     [rsp+140h+var_D0], r8
0x14001836b  xor     edx, edx; AccessMode
0x14001836d  mov     [rsp+140h+var_C8], r10
0x140018372  mov     [rbp+40h+arg_18], edx
0x140018375  test    r11, r11
0x140018378  jz      loc_1400185AF
0x14001837e  cmp     [r15+8], esi
0x140018382  jb      loc_1400185AF
0x140018388  mov     ecx, [r11+2Ch]
0x14001838c  lea     rax, [rbx-1]
0x140018390  add     rcx, [r11+20h]
0x140018394  test    rax, rcx
0x140018397  jnz     loc_140018724
0x14001839d  test    byte ptr [r11+0Ah], 5
0x1400183a2  jz      loc_1400184E9
0x1400183a8  mov     rax, [r11+18h]
0x1400183ac  test    rax, rax
0x1400183af  jz      loc_1400185BF
0x1400183b5  mov     edx, [r15+8]
0x1400183b9  mov     r8, rax
0x1400183bc  mov     [rsp+140h+var_D0], rax
0x1400183c1  mov     rax, [rdi+8]
0x1400183c5  mov     [rbp+40h+arg_18], edx
0x1400183c8  mov     r10d, [rax+2Ch]
0x1400183cc  add     r10, [rax+20h]
0x1400183d0  mov     [rsp+140h+var_C8], r10
0x1400183d5  xor     ebx, ebx
0x1400183d7  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400183de  jnz     loc_14001872E
0x1400183e4  test    ebx, ebx
0x1400183e6  js      short loc_14001845F
0x1400183e8  mov     ecx, [r14]
0x1400183eb  cmp     ecx, 7
0x1400183ee  jg      loc_140018556
0x1400183f4  jz      loc_1400187B2
0x1400183fa  test    ecx, ecx
0x1400183fc  jz      loc_140018793
0x140018402  sub     ecx, 1
0x140018405  jnz     loc_14001851D
0x14001840b  lea     rax, [rbp+40h+arg_10]
0x14001840f  mov     [rsp+140h+var_F8], rax
0x140018414  mov     dword ptr [rsp+140h+var_100], edx
0x140018418  xor     edx, edx
0x14001841a  mov     rcx, [rsp+140h+var_E0]
0x14001841f  lea     r9, [r14+10h]
0x140018423  mov     eax, [r14+98h]
0x14001842a  mov     [rsp+140h+var_108], r10
0x14001842f  mov     [rsp+140h+var_110], r8
0x140018434  mov     rcx, [rcx+38h]
0x140018438  mov     r8d, [r14+8]
0x14001843c  mov     qword ptr [rsp+140h+Priority], rdi
0x140018441  mov     [rsp+140h+BugCheckOnFailure], eax
0x140018445  call    UlQuerySslBinding
0x14001844a  mov     ebx, eax
0x14001844c  mov     ecx, 80000000h
0x140018451  lea     eax, [rbx+rcx]
0x140018454  test    ecx, eax
0x140018456  jz      short loc_1400184A2
0x140018458  mov     eax, [rbp+40h+arg_10]
0x14001845b  mov     [rdi+38h], rax
0x14001845f  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140018466  jnz     loc_14001882E
0x14001846c  cmp     ebx, 103h
0x140018472  jz      short loc_140018488
0x140018474  xor     edx, edx; PriorityBoost
0x140018476  mov     [rdi+30h], ebx
0x140018479  mov     rcx, rdi; Irp
0x14001847c  call    cs:__imp_IofCompleteRequest
0x140018483  nop     dword ptr [rax+rax+00h]
0x140018488  mov     eax, ebx
0x14001848a  mov     rbx, [rsp+140h+arg_0]
0x140018492  add     rsp, 120h
0x140018499  pop     r15
0x14001849b  pop     r14
0x14001849d  pop     rdi
0x14001849e  pop     rsi
0x14001849f  pop     rbp
0x1400184a0  retn
0x1400184a2  cmp     ebx, 80000005h
0x1400184a8  jz      short loc_140018458
0x1400184aa  jmp     short loc_14001845F
0x1400184ac  mov     rcx, rdi; Irp
0x1400184af  call    cs:__imp_IoIs32bitProcess
0x1400184b6  nop     dword ptr [rax+rax+00h]
0x1400184bb  mov     rcx, rdi; Irp
0x1400184be  test    al, al
0x1400184c0  jnz     loc_1400186A6
0x1400184c6  mov     esi, 58h ; 'X'
0x1400184cb  call    cs:__imp_IoIs32bitProcess
0x1400184d2  nop     dword ptr [rax+rax+00h]
0x1400184d7  neg     al
0x1400184d9  sbb     rbx, rbx
0x1400184dc  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1400184e0  add     rbx, 8
0x1400184e4  jmp     loc_14001834F
0x1400184e9  xor     r9d, r9d; RequestedAddress
0x1400184ec  mov     [rsp+140h+Priority], 40000000h; Priority
0x1400184f4  mov     rcx, r11; MemoryDescriptorList
0x1400184f7  mov     [rsp+140h+BugCheckOnFailure], edx; BugCheckOnFailure
0x1400184fb  lea     r8d, [r9+1]; CacheType
0x1400184ff  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140018506  nop     dword ptr [rax+rax+00h]
0x14001850b  mov     r8, [rsp+140h+var_D0]
0x140018510  mov     r10, [rsp+140h+var_C8]
0x140018515  mov     edx, [rbp+40h+arg_18]
0x140018518  jmp     loc_1400183AC
0x14001851d  sub     ecx, 2
0x140018520  jz      loc_140018770
0x140018526  sub     ecx, 1
0x140018529  jz      loc_140018759
0x14001852f  sub     ecx, 1
0x140018532  jz      loc_1400185C9
0x140018538  cmp     ecx, 1
0x14001853b  jnz     loc_140018458
0x140018541  lea     rax, [rbp+40h+arg_10]
0x140018545  mov     [rsp+140h+var_F8], rax
0x14001854a  mov     dword ptr [rsp+140h+var_100], edx
0x14001854e  lea     edx, [rcx+1]
0x140018551  jmp     loc_14001841A
0x140018556  sub     ecx, 8
0x140018559  jz      loc_14001881A
0x14001855f  sub     ecx, 1
0x140018562  jz      loc_140018803
0x140018568  sub     ecx, 1
0x14001856b  jz      loc_1400187EC
0x140018571  sub     ecx, 1
0x140018574  jz      loc_1400187D5
0x14001857a  cmp     ecx, 1
0x14001857d  jnz     loc_140018458
0x140018583  lea     rax, [rbp+40h+arg_10]
0x140018587  mov     [rsp+140h+var_F0], rax
0x14001858c  mov     dword ptr [rsp+140h+var_F8], edx
0x140018590  lea     edx, [rcx+3]
0x140018593  jmp     loc_1401724D6
0x140018598  mov     rcx, [rsp+140h+var_D8]
0x14001859d  lea     rdx, [rbp+40h+var_C0]
0x1400185a1  call    UlpCaptureServiceConfigInfo32
0x1400185a6  lea     r14, [rbp+40h+var_C0]
0x1400185aa  jmp     loc_14001830D
0x1400185af  mov     eax, esi
0x1400185b1  mov     ebx, 80000005h
0x1400185b6  mov     [rdi+38h], rax
0x1400185ba  jmp     loc_1400183D7
0x1400185bf  mov     ebx, 0C000009Ah
0x1400185c4  jmp     loc_1400183D7
0x1400185c9  lea     rax, [rbp+40h+arg_10]
0x1400185cd  mov     [rsp+140h+var_F8], rax
0x1400185d2  mov     dword ptr [rsp+140h+var_100], edx
0x1400185d6  mov     edx, 1
0x1400185db  jmp     loc_14001841A
0x1400185e0  lea     rax, [rsp+140h+var_D8]
0x1400185e5  mov     edx, 12h
0x1400185ea  mov     [rsp+140h+var_110], rax
0x1400185ef  lea     r8, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids
0x1400185f6  mov     [rsp+140h+Priority], esi
0x1400185fa  mov     ecx, 409h
0x1400185ff  mov     r9, rdi
0x140018602  mov     qword ptr [rsp+140h+BugCheckOnFailure], r15
0x140018607  call    WPP_SF_qilq
0x14001860c  jmp     loc_1400182B3
0x140018611  mov     edx, 13h
0x140018616  mov     [rsp+140h+BugCheckOnFailure], ebx
0x14001861a  mov     ecx, 409h
0x14001861f  lea     r8, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids
0x140018626  call    WPP_SF_qD
0x14001862b  jmp     loc_1400182E9
0x140018630  mov     ebx, 0C0000023h
0x140018635  jmp     loc_1400182DC
0x14001863a  mov     ebx, 0C000000Dh
0x14001863f  jmp     loc_1400182DC
0x140018644  mov     edx, 70h ; 'p'
0x140018649  mov     qword ptr [rsp+140h+BugCheckOnFailure], r15
0x14001864e  mov     ecx, 409h
0x140018653  lea     r8, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids
0x14001865a  mov     r9, rdi
0x14001865d  call    WPP_SF_qq
0x140018662  jmp     loc_140018280
0x140018667  sub     ecx, 1
0x14001866a  jz      loc_140172430
0x140018670  sub     ecx, 1
0x140018673  jz      loc_140172444
0x140018679  cmp     ecx, 1
0x14001867c  jnz     loc_14017243A
0x140018682  mov     rcx, rdi; Irp
0x140018685  call    cs:__imp_IoIs32bitProcess
0x14001868c  nop     dword ptr [rax+rax+00h]
0x140018691  mov     rcx, rdi
0x140018694  test    al, al
0x140018696  jz      loc_140172426
0x14001869c  mov     esi, 0B8h
0x1400186a1  jmp     loc_1400184CB
0x1400186a6  mov     esi, 38h ; '8'
0x1400186ab  jmp     loc_140018343
0x1400186b0  mov     esi, 88h
0x1400186b5  jmp     loc_140172493
0x1400186ba  sub     ecx, 8
0x1400186bd  jz      loc_140172484
0x1400186c3  sub     ecx, 1
0x1400186c6  jz      loc_14017246E
0x1400186cc  sub     ecx, 1
0x1400186cf  jz      loc_140172484
0x1400186d5  sub     ecx, 1
0x1400186d8  jz      loc_140172444
0x1400186de  cmp     ecx, 1
0x1400186e1  jnz     loc_14017243A
0x1400186e7  jmp     loc_14017246E
0x1400186ec  lea     rax, [rbp+40h+arg_18]
0x1400186f0  mov     r9, rdi
0x1400186f3  mov     [rsp+140h+var_F8], rax
0x1400186f8  lea     rax, [rsp+140h+var_C8]
0x1400186fd  mov     [rsp+140h+var_100], rax
0x140018702  lea     rax, [rsp+140h+var_D0]
0x140018707  mov     [rsp+140h+var_108], rax
0x14001870c  mov     [rsp+140h+var_110], rbx
0x140018711  mov     [rsp+140h+Priority], esi
0x140018715  mov     qword ptr [rsp+140h+BugCheckOnFailure], r15
0x14001871a  call    WPP_SF_qqLPqqq
0x14001871f  jmp     loc_14001835C
0x140018724  mov     ebx, 0C00002C5h
0x140018729  jmp     loc_1400183D7
0x14001872e  mov     edx, 19h
0x140018733  lea     r8, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids
0x14001873a  mov     ecx, 409h
0x14001873f  mov     r9d, ebx
0x140018742  call    WPP_SF_d
  ... truncated ...
```
