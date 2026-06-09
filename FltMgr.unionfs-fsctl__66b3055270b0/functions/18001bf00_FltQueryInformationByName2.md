# FltQueryInformationByName2

- ea: `0x18001bf00`
- end: `0x18001c12a`
- name: `FltQueryInformationByName2`
- size: `554`
- prototype: `__int64 __usercall@<rax>(PVOID FltObject@<rcx>, __int64@<rdx>, __int64, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18001beb0`

## callees

- `0x180009f20`
- `0x18001bf00`
- `0x180053944`
- `0x18005c1d0`
- `0x18005c3b0`
- `0x18005c450`
- `0x18005d850`
- `0x18005df50`
- `0x180066990`
- `0x1800718a0`

## import_xrefs

- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18001c11c`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18001c11c`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180026557`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180026557`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x180026629`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x180026629`
- `ntoskrnl!IoQueryInformationByName` at `0x18001c044`
- `ntoskrnl!IoQueryInformationByName` at `0x1800265e9`
- `ntoskrnl!IoQueryInformationByName` at `0x18002674f`
- `ntoskrnl!IoQueryInformationByName` at `0x18001c044`
- `ntoskrnl!IoQueryInformationByName` at `0x1800265e9`
- `ntoskrnl!IoQueryInformationByName` at `0x18002674f`

## pseudocode

```c
__int64 __fastcall FltQueryInformationByName2(
        _QWORD *FltObject,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        __int16 *a9)
{
  bool v9; // bl
  __int64 v10; // rsi
  _QWORD *v11; // r13
  __int64 v13; // r12
  unsigned int v14; // edi
  unsigned __int16 v16; // dx
  unsigned int ExtraCreateParameter; // eax
  int v18; // eax
  unsigned int v19; // r15d
  PVOID v20; // r15
  __int64 v21; // rdx
  PVOID v22; // r12
  __int64 TargetInfo; // r15
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  unsigned __int16 v26; // cx
  PVOID FltObjecta; // [rsp+28h] [rbp-E0h]
  PVOID FltObjectb; // [rsp+28h] [rbp-E0h]
  int v29[2]; // [rsp+58h] [rbp-B0h] BYREF
  PVOID v30; // [rsp+60h] [rbp-A8h] BYREF
  PVOID v31; // [rsp+68h] [rbp-A0h] BYREF
  PVOID v32; // [rsp+70h] [rbp-98h] BYREF
  __int64 v33; // [rsp+78h] [rbp-90h] BYREF
  __int128 v34; // [rsp+80h] [rbp-88h] BYREF
  __int128 v35; // [rsp+90h] [rbp-78h]
  __int64 v36; // [rsp+A0h] [rbp-68h]
  _QWORD *v37; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-58h]
  PVOID EcpContext; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v40[48]; // [rsp+C0h] [rbp-48h] BYREF
  unsigned int v43; // [rsp+178h] [rbp+70h]
  unsigned int v44; // [rsp+178h] [rbp+70h]
  char v45; // [rsp+178h] [rbp+70h]

  v9 = 0;
  v10 = 0;
  v11 = 0;
  EcpContext = 0;
  v13 = 0;
  *(_QWORD *)v29 = 0;
  v32 = 0;
  v30 = 0;
  v37 = 0;
  v31 = 0;
  v33 = 0;
  v34 = 0;
  LOWORD(v34) = 40;
  v38 = 1;
  v36 = 1;
  memset(v40, 0, 44);
  v35 = 0;
  if ( a9 )
  {
    v16 = *a9;
    if ( (unsigned __int16)*a9 < 0x20u || *((_QWORD *)a9 + 2) )
    {
      v14 = -1073741811;
      goto LABEL_7;
    }
    *((_QWORD *)&v34 + 1) = *((_QWORD *)a9 + 1);
    *((_QWORD *)&v35 + 1) = *((_QWORD *)a9 + 3);
    if ( v16 >= 0x28u )
      v36 = *((_QWORD *)a9 + 4);
  }
  v14 = TargetedIOCtrlGenerateECP(
          (PVOID *)v29,
          0,
          0,
          FltObject[7],
          FltObject,
          a2,
          0,
          (PECP_LIST *)&v34 + 1,
          &EcpContext);
  if ( (int)FltpDbgStatus(v14, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 9104, 3223060491LL) < 0 )
  {
    v10 = *(_QWORD *)v29;
  }
  else
  {
    v9 = (*(_BYTE *)(*(_QWORD *)v29 + 6LL) & 8) != 0;
    if ( a2 )
      *(_QWORD *)&v35 = *(_QWORD *)(*(_QWORD *)(a2 + 64) + 64LL);
    v14 = IoQueryInformationByName(a3, a4, a5, a6, a7, a8 | 0x100u, &v34);
    if ( v14 + 1073740952 > 1 )
    {
LABEL_6:
      FltpDbgStatus(v14, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 9372, 0);
      goto LABEL_7;
    }
    if ( a9 )
    {
      if ( *((_QWORD *)&v34 + 1) )
      {
        ExtraCreateParameter = FsRtlFindExtraCreateParameter(
                                 *((PECP_LIST *)&v34 + 1),
                                 &GUID_ECP_FLT_CREATEFILE_TARGET,
                                 &v32,
                                 0);
        if ( (int)FltpDbgStatus(ExtraCreateParameter, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 9189, 0) >= 0 )
        {
          v43 = FltpGenerateDeviceHintEcp(&v30, **(_WORD **)(a3 + 16), *((struct _ECP_LIST **)&v34 + 1));
          if ( (int)FltpDbgStatus(v43, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 9202, 0) >= 0 )
          {
            LODWORD(FltObjecta) = a7;
            v18 = IoQueryInformationByName(a3, a4, a5, a6, FltObjecta, 256, &v34);
            v19 = v18;
            v29[0] = v18;
            if ( (unsigned int)(v18 + 1073740952) <= 1 || v18 == -1073740650 )
            {
              v20 = v31;
              while ( FsRtlIsEcpAcknowledged(v30) )
              {
                if ( v29[0] == -1073740650 )
                {
                  LOBYTE(v21) = 1;
                  v44 = FltpResetDeviceHintEcp(v30, v21);
                  if ( (int)FltpDbgStatus(v44, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 9253, 0) < 0 )
                  {
                    v14 = v44;
                    break;
                  }
                  v45 = 0;
                }
                else
                {
                  v22 = v30;
                  TargetInfo = (unsigned int)FltpGetTargetInfo(v30, *(_QWORD **)(a2 + 72), (PVOID *)&v37, &v31, &v33);
                  if ( (int)FltpDbgStatus(TargetInfo, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 9277, 0) < 0 )
                  {
                    v14 = TargetInfo;
                    break;
                  }
                  v11 = v37;
                  if ( !v37 || (*((_BYTE *)v32 + 24) & 1) == 0 )
                  {
                    FltpAcknowledgeTargetInfo(v37, v31, v33, v32);
                    break;
                  }
                  FltpResetDeviceHintEcp(v22, 0);
                  v13 = v33;
                  v20 = v31;
                  v45 = 1;
                }
                v24 = *(_OWORD *)(a3 + 16);
                *(_OWORD *)v40 = *(_OWORD *)a3;
                v25 = *(_OWORD *)(a3 + 32);
                *(_QWORD *)&v40[24] = *((_QWORD *)&v24 + 1);
                *(_QWORD *)&v40[16] = v13 + 8;
                *(_OWORD *)&v40[32] = v25;
                *(_QWORD *)&v35 = *(_QWORD *)(v11[8] + 64LL);
                LODWORD(FltObjectb) = a7;
                v29[0] = IoQueryInformationByName(v40, a4, a5, a6, FltObjectb, 256, &v34);
                if ( (int)FltpDbgStatus((unsigned int)v29[0], "minkernel\\fs\\filtermgr\\filter\\iosup.c", 9330, 0) >= 0 )
                {
                  FltpAcknowledgeTargetInfo(v11, v20, v13, v32);
                  v14 = v29[0];
                  break;
                }
                if ( (unsigned int)(v29[0] + 1073740952) > 1 && v29[0] != -1073740650 )
                {
                  v14 = v29[0];
                  FltpCleanupTargetInfo(v11, v20, v13);
                  break;
                }
                FltpCleanupTargetInfo(v11, v20, v13);
                v26 = v38 + 1;
                if ( !v45 )
                  v26 = v38;
                if ( v26 >= 0x40u )
                  break;
                LOWORD(v38) = v26;
              }
              FltpCleanupDeviceHintEcp(*((_QWORD *)&v34 + 1));
              goto LABEL_6;
            }
            FltpCleanupDeviceHintEcp(*((_QWORD *)&v34 + 1));
            v14 = v19;
          }
          else
          {
            v14 = v43;
          }
        }
      }
    }
  }
LABEL_7:
  CleanupTargetedIo(v10, (char *)&v34 + 8, v9);
  if ( EcpContext )
    FsRtlInsertExtraCreateParameter(*((PECP_LIST *)&v34 + 1), EcpContext);
  return v14;
}

```

## disassembly

```asm
0x18001bf00  mov     rax, rsp
0x18001bf03  mov     [rax+20h], r9
0x18001bf07  mov     [rax+18h], r8
0x18001bf0b  push    rbp
0x18001bf0c  push    rdi
0x18001bf0d  lea     rbp, [rax-28h]
0x18001bf11  sub     rsp, 118h
0x18001bf18  xor     r8d, r8d; int
0x18001bf1b  mov     [rax+8], rbx
0x18001bf1f  mov     [rax-18h], rsi
0x18001bf23  xorps   xmm0, xmm0
0x18001bf26  mov     [rax-20h], r12
0x18001bf2a  xor     bl, bl
0x18001bf2c  mov     [rax-28h], r13
0x18001bf30  mov     esi, r8d
0x18001bf33  mov     [rax-30h], r14
0x18001bf37  mov     r13d, r8d
0x18001bf3a  mov     [rax-38h], r15
0x18001bf3e  mov     r14, rdx
0x18001bf41  mov     r15, [rbp+20h+arg_40]
0x18001bf45  mov     eax, 28h ; '('
0x18001bf4a  mov     [rbp+20h+EcpContext], r8
0x18001bf4e  mov     r12d, r8d
0x18001bf51  mov     qword ptr [rsp+120h+var_D0], r8
0x18001bf56  mov     [rsp+120h+var_B8], r8
0x18001bf5b  mov     [rsp+120h+var_C8], r8
0x18001bf60  mov     [rbp+20h+var_80], r8
0x18001bf64  mov     [rsp+120h+var_C0], r8
0x18001bf69  mov     qword ptr [rsp+120h+var_B0], r8
0x18001bf6e  movups  [rsp+120h+var_B0+8], xmm0
0x18001bf73  mov     word ptr [rsp+120h+var_B0+8], ax
0x18001bf78  mov     eax, 1
0x18001bf7d  mov     [rbp+20h+var_78], rax
0x18001bf81  mov     [rbp+20h+var_88], rax
0x18001bf85  movups  [rbp+20h+var_58], xmm0
0x18001bf89  movups  [rbp+20h+var_68], xmm0
0x18001bf8d  movups  [rbp+20h+var_58+0Ch], xmm0
0x18001bf91  movups  [rbp+20h+var_98], xmm0
0x18001bf95  test    r15, r15
0x18001bf98  jnz     loc_18001C0CD
0x18001bf9e  mov     r9, [rcx+38h]; int
0x18001bfa2  lea     rax, [rbp+20h+EcpContext]
0x18001bfa6  mov     [rsp+40h], rax; __int64
0x18001bfab  xor     edx, edx; int
0x18001bfad  lea     rax, [rbp+20h+EcpList]
0x18001bfb1  mov     [rsp+120h+var_E8], rax; EcpList
0x18001bfb6  mov     [rsp+120h+var_F0], r8; PVOID
0x18001bfbb  mov     [rsp+120h+var_F8], r14; __int64
0x18001bfc0  mov     [rsp+120h+FltObject], rcx; FltObject
0x18001bfc5  lea     rcx, [rsp+120h+var_D0]; int
0x18001bfca  call    TargetedIOCtrlGenerateECP
0x18001bfcf  mov     r8d, 2390h
0x18001bfd5  mov     [rsp+120h+FltObject], rsi
0x18001bfda  mov     r9d, 0C01C000Bh
0x18001bfe0  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18001bfe7  mov     ecx, eax
0x18001bfe9  mov     edi, eax
0x18001bfeb  call    FltpDbgStatus
0x18001bff0  test    eax, eax
0x18001bff2  js      loc_18001C10E
0x18001bff8  mov     rbx, qword ptr [rsp+120h+var_D0]
0x18001bffd  movzx   ebx, byte ptr [rbx+6]
0x18001c001  shr     bl, 3
0x18001c004  and     bl, 1
0x18001c007  test    r14, r14
0x18001c00a  jz      short loc_18001C018
0x18001c00c  mov     rax, [r14+40h]
0x18001c010  mov     rcx, [rax+40h]
0x18001c014  mov     qword ptr [rbp+20h+var_98], rcx
0x18001c018  mov     eax, [rbp+20h+arg_38]
0x18001c01b  lea     rcx, [rsp+120h+var_B0+8]
0x18001c020  mov     r9d, [rbp+20h+arg_28]
0x18001c024  bts     eax, 8
0x18001c028  mov     r8, [rbp+20h+arg_20]
0x18001c02c  mov     rdx, [rbp+20h+arg_18]
0x18001c030  mov     [rsp+120h+var_F0], rcx
0x18001c035  mov     rcx, [rbp+20h+arg_10]
0x18001c039  mov     dword ptr [rsp+120h+var_F8], eax
0x18001c03d  mov     eax, [rbp+20h+arg_30]
0x18001c040  mov     dword ptr [rsp+120h+FltObject], eax
0x18001c044  call    cs:__imp_IoQueryInformationByName
0x18001c04b  nop     dword ptr [rax+rax+00h]
0x18001c050  mov     edi, eax
0x18001c052  add     eax, 3FFFFC98h
0x18001c057  cmp     eax, 1
0x18001c05a  jbe     loc_180026532
0x18001c060  mov     r8d, 249Ch
0x18001c066  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18001c06d  xor     r9d, r9d
0x18001c070  mov     ecx, edi
0x18001c072  call    FltpDbgStatus
0x18001c077  movzx   r8d, bl
0x18001c07b  lea     rdx, [rbp+20h+EcpList]
0x18001c07f  mov     rcx, rsi
0x18001c082  call    CleanupTargetedIo
0x18001c087  mov     rdx, [rbp+20h+EcpContext]; EcpContext
0x18001c08b  mov     r15, [rsp+120h+var_30]
0x18001c093  mov     r14, [rsp+120h+var_28]
0x18001c09b  mov     r13, [rsp+120h+var_20]
0x18001c0a3  mov     r12, [rsp+120h+var_18]
0x18001c0ab  mov     rsi, [rsp+110h]
0x18001c0b3  mov     rbx, [rsp+120h+arg_0]
0x18001c0bb  test    rdx, rdx
0x18001c0be  jnz     short loc_18001C118
0x18001c0c0  mov     eax, edi
0x18001c0c2  add     rsp, 118h
0x18001c0c9  pop     rdi
0x18001c0ca  pop     rbp
0x18001c0cb  retn
0x18001c0cd  movzx   edx, word ptr [r15]
0x18001c0d1  cmp     dx, 20h ; ' '
0x18001c0d5  jb      short loc_18001C104
0x18001c0d7  cmp     [r15+10h], rsi
0x18001c0db  jnz     short loc_18001C104
0x18001c0dd  mov     rax, [r15+8]
0x18001c0e1  mov     [rbp+20h+EcpList], rax
0x18001c0e5  mov     rax, [r15+18h]
0x18001c0e9  mov     qword ptr [rbp+20h+var_98+8], rax
0x18001c0ed  cmp     dx, 28h ; '('
0x18001c0f1  jb      loc_18001BF9E
0x18001c0f7  mov     rax, [r15+20h]
0x18001c0fb  mov     [rbp+20h+var_88], rax
0x18001c0ff  jmp     loc_18001BF9E
0x18001c104  mov     edi, 0C000000Dh
0x18001c109  jmp     loc_18001C077
0x18001c10e  mov     rsi, qword ptr [rsp+120h+var_D0]
0x18001c113  jmp     loc_18001C077
0x18001c118  mov     rcx, [rbp+20h+EcpList]; EcpList
0x18001c11c  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x18001c123  nop     dword ptr [rax+rax+00h]
0x18001c128  jmp     short loc_18001C0C0
0x180026532  test    r15, r15
0x180026535  jz      loc_18001C077
0x18002653b  mov     rcx, [rbp+20h+EcpList]; EcpList
0x18002653f  test    rcx, rcx
0x180026542  jz      loc_18001C077
0x180026548  xor     r9d, r9d; EcpContextSize
0x18002654b  lea     r8, [rsp+120h+var_B8]; EcpContext
0x180026550  lea     rdx, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x180026557  call    cs:__imp_FsRtlFindExtraCreateParameter
0x18002655e  nop     dword ptr [rax+rax+00h]
0x180026563  mov     r8d, 23E5h
0x180026569  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180026570  mov     ecx, eax
0x180026572  xor     r9d, r9d
0x180026575  call    FltpDbgStatus
0x18002657a  test    eax, eax
0x18002657c  js      loc_18001C077
0x180026582  mov     r15, [rbp+20h+arg_10]
0x180026586  lea     rcx, [rsp+120h+var_C8]
0x18002658b  mov     r8, [rbp+20h+EcpList]
0x18002658f  mov     rdx, [r15+10h]
0x180026593  movzx   edx, word ptr [rdx]
0x180026596  call    FltpGenerateDeviceHintEcp
0x18002659b  mov     r8d, 23F2h
0x1800265a1  mov     dword ptr [rbp+20h+arg_40], eax
0x1800265a4  xor     r9d, r9d
0x1800265a7  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x1800265ae  mov     ecx, eax
0x1800265b0  call    FltpDbgStatus
0x1800265b5  test    eax, eax
0x1800265b7  jns     short loc_1800265C1
0x1800265b9  mov     edi, dword ptr [rbp+20h+arg_40]
0x1800265bc  jmp     loc_18001C077
0x1800265c1  mov     r9d, [rbp+20h+arg_28]
0x1800265c5  lea     rax, [rsp+120h+var_B0+8]
0x1800265ca  mov     r8, [rbp+20h+arg_20]
0x1800265ce  mov     rcx, r15
0x1800265d1  mov     rdx, [rbp+20h+arg_18]
0x1800265d5  mov     [rsp+120h+var_F0], rax
0x1800265da  mov     eax, [rbp+20h+arg_30]
0x1800265dd  mov     dword ptr [rsp+120h+var_F8], 100h
0x1800265e5  mov     dword ptr [rsp+120h+FltObject], eax
0x1800265e9  call    cs:__imp_IoQueryInformationByName
0x1800265f0  nop     dword ptr [rax+rax+00h]
0x1800265f5  mov     r15d, eax
0x1800265f8  mov     [rsp+120h+var_D0], eax
0x1800265fc  lea     ecx, [rax+3FFFFC98h]
0x180026602  cmp     ecx, 1
0x180026605  jbe     short loc_18002661F
0x180026607  cmp     eax, 0C0000496h
0x18002660c  jz      short loc_18002661F
0x18002660e  mov     rcx, [rbp+20h+EcpList]
0x180026612  call    FltpCleanupDeviceHintEcp
0x180026617  mov     edi, r15d
0x18002661a  jmp     loc_18001C077
0x18002661f  mov     r15, [rsp+120h+var_C0]
0x180026624  mov     rcx, [rsp+120h+var_C8]; EcpContext
0x180026629  call    cs:__imp_FsRtlIsEcpAcknowledged
0x180026630  nop     dword ptr [rax+rax+00h]
0x180026635  test    al, al
0x180026637  jz      loc_180026804
0x18002663d  cmp     [rsp+120h+var_D0], 0C0000496h
0x180026645  jnz     short loc_18002667B
0x180026647  mov     rcx, [rsp+120h+var_C8]
0x18002664c  mov     dl, 1
0x18002664e  call    FltpResetDeviceHintEcp
0x180026653  xor     r9d, r9d
0x180026656  mov     dword ptr [rbp+20h+arg_40], eax
0x180026659  mov     r8d, 2425h
0x18002665f  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180026666  mov     ecx, eax
0x180026668  call    FltpDbgStatus
0x18002666d  test    eax, eax
0x18002666f  js      loc_1800267CF
0x180026675  mov     byte ptr [rbp+20h+arg_40], sil
0x180026679  jmp     short loc_1800266F6
0x18002667b  mov     r12, [rsp+120h+var_C8]
0x180026680  lea     rax, [rsp+120h+var_B0]
0x180026685  mov     rdx, [r14+48h]
0x180026689  lea     r9, [rsp+120h+var_C0]
0x18002668e  mov     rcx, r12
0x180026691  mov     [rsp+120h+FltObject], rax
0x180026696  lea     r8, [rbp+20h+var_80]
0x18002669a  call    FltpGetTargetInfo
0x18002669f  xor     r9d, r9d
0x1800266a2  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x1800266a9  mov     r8d, 243Dh
0x1800266af  mov     ecx, eax
0x1800266b1  mov     r15d, eax
0x1800266b4  call    FltpDbgStatus
0x1800266b9  test    eax, eax
0x1800266bb  js      loc_180026801
0x1800266c1  mov     r13, [rbp+20h+var_80]
0x1800266c5  mov     r9, [rsp+120h+var_B8]
0x1800266ca  test    r13, r13
0x1800266cd  jz      loc_1800267ED
0x1800266d3  test    byte ptr [r9+18h], 1
0x1800266d8  jz      loc_1800267ED
0x1800266de  xor     edx, edx
0x1800266e0  mov     rcx, r12
0x1800266e3  call    FltpResetDeviceHintEcp
0x1800266e8  mov     r12, qword ptr [rsp+120h+var_B0]
0x1800266ed  mov     r15, [rsp+120h+var_C0]
0x1800266f2  mov     byte ptr [rbp+20h+arg_40], 1
0x1800266f6  mov     rax, [rbp+20h+arg_10]
0x1800266fa  mov     r9d, [rbp+20h+arg_28]
0x1800266fe  mov     r8, [rbp+20h+arg_20]
0x180026702  mov     rdx, [rbp+20h+arg_18]
0x180026706  movups  xmm0, xmmword ptr [rax]
0x180026709  movups  xmm1, xmmword ptr [rax+10h]
0x18002670d  movups  [rbp+20h+var_68], xmm0
0x180026711  movups  xmm0, xmmword ptr [rax+20h]
0x180026715  lea     rax, [r12+8]
0x18002671a  movups  [rbp+20h+var_58], xmm1
0x18002671e  mov     qword ptr [rbp+20h+var_58], rax
0x180026722  movups  [rbp+20h+var_48], xmm0
0x180026726  mov     rax, [r13+40h]
0x18002672a  mov     rcx, [rax+40h]
0x18002672e  lea     rax, [rsp+120h+var_B0+8]
0x180026733  mov     [rsp+120h+var_F0], rax
0x180026738  mov     eax, [rbp+20h+arg_30]
0x18002673b  mov     qword ptr [rbp+20h+var_98], rcx
0x18002673f  lea     rcx, [rbp+20h+var_68]
0x180026743  mov     dword ptr [rsp+120h+var_F8], 100h
0x18002674b  mov     dword ptr [rsp+120h+FltObject], eax
0x18002674f  call    cs:__imp_IoQueryInformationByName
0x180026756  nop     dword ptr [rax+rax+00h]
0x18002675b  xor     r9d, r9d
0x18002675e  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180026765  mov     ecx, eax
0x180026767  mov     [rsp+120h+var_D0], eax
0x18002676b  mov     r8d, 2472h
0x180026771  call    FltpDbgStatus
0x180026776  test    eax, eax
0x180026778  jns     short loc_1800267D4
0x18002677a  mov     ecx, [rsp+120h+var_D0]
0x18002677e  lea     eax, [rcx+3FFFFC98h]
0x180026784  cmp     eax, 1
0x180026787  jbe     short loc_1800267A3
0x180026789  cmp     ecx, 0C0000496h
0x18002678f  jz      short loc_1800267A3
0x180026791  mov     edi, ecx
0x180026793  mov     r8, r12
0x180026796  mov     rcx, r13
0x180026799  mov     rdx, r15
0x18002679c  call    FltpCleanupTargetInfo
0x1800267a1  jmp     short loc_180026804
0x1800267a3  mov     r8, r12
0x1800267a6  mov     rdx, r15
0x1800267a9  mov     rcx, r13
0x1800267ac  call    FltpCleanupTargetInfo
0x1800267b1  mov     rax, [rbp+20h+var_78]
0x1800267b5  cmp     byte ptr [rbp+20h+arg_40], sil
0x1800267b9  lea     ecx, [rax+1]
0x1800267bc  cmovz   cx, ax
0x1800267c0  cmp     cx, 40h ; '@'
0x1800267c4  jnb     short loc_180026804
0x1800267c6  mov     word ptr [rbp+20h+var_78], cx
0x1800267ca  jmp     loc_180026624
0x1800267cf  mov     edi, dword ptr [rbp+20h+arg_40]
0x1800267d2  jmp     short loc_180026804
0x1800267d4  mov     r9, [rsp+120h+var_B8]
0x1800267d9  mov     r8, r12
0x1800267dc  mov     rdx, r15
0x1800267df  mov     rcx, r13
0x1800267e2  call    FltpAcknowledgeTargetInfo
0x1800267e7  mov     edi, [rsp+120h+var_D0]
0x1800267eb  jmp     short loc_180026804
0x1800267ed  mov     r8, qword ptr [rsp+120h+var_B0]
  ... truncated ...
```
