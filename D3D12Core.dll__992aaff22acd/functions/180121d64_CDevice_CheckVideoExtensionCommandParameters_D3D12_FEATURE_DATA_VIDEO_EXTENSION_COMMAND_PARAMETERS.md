# CDevice::CheckVideoExtensionCommandParameters(D3D12_FEATURE_DATA_VIDEO_EXTENSION_COMMAND_PARAMETERS *)

- ea: `0x180121d64`
- end: `0x1801220a0`
- name: `?CheckVideoExtensionCommandParameters@CDevice@@QEAAJPEAUD3D12_FEATURE_DATA_VIDEO_EXTENSION_COMMAND_PARAMETERS@@@Z`
- size: `828`
- prototype: `__int64 __fastcall(CDevice *__hidden this, struct _GUID *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a7e94`
- `0x18011e560`

## callees

- `0x18000b010`
- `0x180053630`
- `0x180060b00`
- `0x18007efa0`
- `0x1800bb480`
- `0x1800bc094`
- `0x18011da78`
- `0x180121d64`
- `0x180122f78`
- `0x1801240f4`

## string_xrefs

- `0x180121f30`: `GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS returned an invalid D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAG.\n`
- `0x180121f51`: `GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS must set Read or Write Flags for D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_RESOURCE.\n`
- `0x180121ef7`: `GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS returned a nullptr for a parameter name.\n`
- `0x180121f12`: `GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS returned an invalid D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE.\n`
- `0x180121ec6`: `GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS returned a failure for a parameter set it claimed to support.\n`
- `0x180121f78`: `GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS reported a Resource parameter type for the CAPS_INPUT, CAPS_OUTPUT, or DEVICE_EXECUTE_OUTPUT stage.\n`
- `0x180121f95`: `GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS must set None Flags for parameters whose type is not D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_RESOURCE.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDevice::CheckVideoExtensionCommandParameters(CDevice *this, struct _GUID *a2)
{
  __int64 v5; // r8
  int Caps; // ecx
  __int64 v7; // r8
  CJournal *v8; // rcx
  unsigned int v9; // r14d
  __int64 i; // rsi
  __int64 v11; // r15
  CJournal *Data1; // rcx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // r9d
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // r8d
  __int64 v21; // rdx
  __int128 v22; // [rsp+40h] [rbp-78h] BYREF
  struct _GUID v23; // [rsp+50h] [rbp-68h] BYREF
  int v24; // [rsp+60h] [rbp-58h]
  int v25; // [rsp+64h] [rbp-54h]
  __int64 v26; // [rsp+68h] [rbp-50h]
  struct _GUID v27; // [rsp+70h] [rbp-48h] BYREF
  _QWORD v28[2]; // [rsp+80h] [rbp-38h]

  memset_0(*(void **)a2[1].Data4, 0, 16LL * *(unsigned int *)&a2[1].Data2);
  if ( !CDevice::IsVideoExtensionCommandDriverSupported(this, a2) )
    ThrowFailure(-2147024809);
  if ( (int)a2[1].Data1 >= 7 )
    ThrowFailure(-2147024809);
  if ( !*(_DWORD *)&a2[1].Data2 )
    return 0;
  if ( *((_DWORD *)this + 719) < 0x11u && a2[1].Data1 - 5 <= 1 )
    return 0;
  v27 = *a2;
  LODWORD(v28[0]) = ConvertToDDI(a2[1].Data1);
  *(_QWORD *)((char *)v28 + 4) = 0;
  Caps = CDevice::GetCaps(this, 24, v5, &v27, 28);
  ThrowFailure(Caps);
  if ( *(_DWORD *)&a2[1].Data2 != HIDWORD(v28[0]) )
    ThrowFailure(-2147024809);
  v22 = 0;
  v27 = 0;
  v28[0] = 0;
  std::vector<D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063>::_Construct_n<D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063 const &>(
    &v27,
    *(unsigned int *)&a2[1].Data2,
    &v22);
  v23 = *a2;
  v24 = ConvertToDDI(a2[1].Data1);
  v25 = *(_DWORD *)&a2[1].Data2;
  v26 = *(_QWORD *)&v27.Data1;
  if ( (int)CDevice::GetCaps(this, 25, v7, &v23, 32) < 0 )
  {
    CJournal::ReportDriverError(
      v8,
      -2005270496,
      "GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS returned a failure for a parameter set it cl"
      "aimed to support.\n");
    ThrowFailure(-2005270496);
  }
  v9 = 0;
  v11 = *(_QWORD *)v27.Data4;
  for ( i = *(_QWORD *)&v27.Data1; i != v11; i += 16 )
  {
    if ( !*(_QWORD *)i )
    {
      CJournal::ReportDriverError(
        v8,
        -2005270496,
        "GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS returned a nullptr for a parameter name.\n");
      ThrowFailure(-2005270496);
    }
    if ( *(int *)(i + 8) >= 11 )
    {
      CJournal::ReportDriverError(
        v8,
        -2005270496,
        "GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS returned an invalid D3D12DDI_VIDEO_EXTENSI"
        "ON_COMMAND_PARAMETER_TYPE.\n");
      ThrowFailure(-2005270496);
    }
    if ( (*(_DWORD *)(i + 12) & 0xFFFFFFFC) != 0 )
    {
      CJournal::ReportDriverError(
        v8,
        -2005270496,
        "GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS returned an invalid D3D12DDI_VIDEO_EXTENSI"
        "ON_COMMAND_PARAMETER_FLAG.\n");
      ThrowFailure(-2005270496);
    }
    if ( *(_DWORD *)(i + 8) == 10 )
    {
      if ( !*(_DWORD *)(i + 12) )
      {
        CJournal::ReportDriverError(
          v8,
          -2005270496,
          "GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS must set Read or Write Flags for D3D12DD"
          "I_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_RESOURCE.\n");
        ThrowFailure(-2005270496);
      }
      Data1 = (CJournal *)a2[1].Data1;
      if ( (((_DWORD)Data1 - 3) & 0xFFFFFFFC) == 0 && (_DWORD)Data1 != 5 )
      {
        CJournal::ReportDriverError(
          Data1,
          -2005270496,
          "GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS reported a Resource parameter type for t"
          "he CAPS_INPUT, CAPS_OUTPUT, or DEVICE_EXECUTE_OUTPUT stage.\n");
        ThrowFailure(-2005270496);
      }
    }
    else if ( *(_DWORD *)(i + 12) )
    {
      CJournal::ReportDriverError(
        v8,
        -2005270496,
        "GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_PARAMETERS must set None Flags for parameters whose t"
        "ype is not D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE_0063_RESOURCE.\n");
      ThrowFailure(-2005270496);
    }
    v13 = *(_DWORD *)(i + 8);
    if ( v13 > 5 )
    {
      v17 = v13 - 6;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            if ( v19 == 1 )
              v16 = 9;
            else
              v16 = 10;
          }
          else
          {
            v16 = 8;
          }
        }
        else
        {
          v16 = 7;
        }
      }
      else
      {
        v16 = 6;
      }
    }
    else if ( v13 == 5 )
    {
      v16 = 5;
    }
    else if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          if ( v15 == 1 )
            v16 = 3;
          else
            v16 = 4;
        }
        else
        {
          v16 = 2;
        }
      }
      else
      {
        v16 = 1;
      }
    }
    else
    {
      v16 = 0;
    }
    v20 = *(_DWORD *)(i + 12);
    v21 = 2LL * v9;
    v8 = *(CJournal **)a2[1].Data4;
    *((_QWORD *)v8 + v21) = *(_QWORD *)i;
    *((_DWORD *)v8 + 2 * v21 + 2) = v16;
    *((_DWORD *)v8 + 2 * v21 + 3) = v20 & 3;
    ++v9;
  }
  std::vector<D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063>::_Tidy(&v27);
  return 0;
}

```

## disassembly

```asm
0x180121d64  mov     [rsp+arg_10], rbx
0x180121d69  mov     [rsp+arg_18], rsi
0x180121d6e  push    rdi
0x180121d6f  push    r14
0x180121d71  push    r15
0x180121d73  sub     rsp, 0A0h
0x180121d7a  mov     rax, cs:__security_cookie
0x180121d81  xor     rax, rsp
0x180121d84  mov     [rsp+0B8h+var_28], rax
0x180121d8c  mov     rdi, rdx
0x180121d8f  mov     rbx, rcx
0x180121d92  mov     r8d, [rdx+14h]
0x180121d96  shl     r8, 4; Size
0x180121d9a  xor     edx, edx; Val
0x180121d9c  mov     rcx, [rdi+18h]; void *
0x180121da0  call    memset_0
0x180121da5  mov     rdx, rdi; struct _GUID *
0x180121da8  mov     rcx, rbx; this
0x180121dab  call    ?IsVideoExtensionCommandDriverSupported@CDevice@@QEAA_NAEBU_GUID@@@Z; CDevice::IsVideoExtensionCommandDriverSupported(_GUID const &)
0x180121db0  test    al, al
0x180121db2  jnz     short loc_180121DBE
0x180121db4  mov     ecx, 80070057h; int
0x180121db9  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121dbe  cmp     dword ptr [rdi+10h], 7
0x180121dc2  jl      short loc_180121DCE
0x180121dc4  mov     ecx, 80070057h; int
0x180121dc9  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121dce  cmp     dword ptr [rdi+14h], 0
0x180121dd2  jnz     short loc_180121DDB
0x180121dd4  xor     eax, eax
0x180121dd6  jmp     loc_180122077
0x180121ddb  cmp     dword ptr [rbx+0B3Ch], 11h
0x180121de2  jnb     short loc_180121DF6
0x180121de4  mov     eax, [rdi+10h]
0x180121de7  sub     eax, 5
0x180121dea  cmp     eax, 1
0x180121ded  ja      short loc_180121DF6
0x180121def  xor     eax, eax
0x180121df1  jmp     loc_180122077
0x180121df6  movups  xmm0, xmmword ptr [rdi]
0x180121df9  movdqu  [rsp+0B8h+var_48], xmm0
0x180121dff  mov     ecx, [rdi+10h]
0x180121e02  call    ?ConvertToDDI@@YA?AW4D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063@@W4D3D12_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE@@@Z; ConvertToDDI(D3D12_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE)
0x180121e07  mov     dword ptr [rsp+0B8h+var_38], eax
0x180121e0e  xor     eax, eax
0x180121e10  mov     qword ptr [rsp+0B8h+var_38+4], rax
0x180121e18  mov     [rsp+0B8h+var_98], 1Ch
0x180121e20  lea     r9, [rsp+0B8h+var_48]
0x180121e25  lea     edx, [rax+18h]
0x180121e28  mov     rcx, rbx
0x180121e2b  call    ?GetCaps@CDevice@@QEAAJW4D3D12DDICAPS_TYPE_VIDEO_0020@@PEAX1I@Z; CDevice::GetCaps(D3D12DDICAPS_TYPE_VIDEO_0020,void *,void *,uint)
0x180121e30  mov     ecx, eax; int
0x180121e32  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121e37  mov     eax, dword ptr [rsp+0B8h+var_38+4]
0x180121e3e  cmp     [rdi+14h], eax
0x180121e41  jz      short loc_180121E4D
0x180121e43  mov     ecx, 80070057h; int
0x180121e48  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121e4d  xorps   xmm0, xmm0
0x180121e50  movups  [rsp+0B8h+var_78], xmm0
0x180121e55  xorps   xmm1, xmm1
0x180121e58  movdqu  [rsp+0B8h+var_48], xmm1
0x180121e5e  mov     qword ptr [rsp+0B8h+var_38], 0
0x180121e6a  mov     edx, [rdi+14h]
0x180121e6d  lea     r8, [rsp+0B8h+var_78]
0x180121e72  lea     rcx, [rsp+0B8h+var_48]
0x180121e77  call    ??$_Construct_n@AEBUD3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063@@@?$vector@UD3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063@@V?$allocator@UD3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063@@@std@@@std@@AEAAX_KAEBUD3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063@@@Z; std::vector<D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063>::_Construct_n<D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063 const &>(unsigned __int64,D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063 const &)
0x180121e7c  nop
0x180121e7d  movups  xmm0, xmmword ptr [rdi]
0x180121e80  movdqu  [rsp+0B8h+var_68], xmm0
0x180121e86  mov     ecx, [rdi+10h]
0x180121e89  call    ?ConvertToDDI@@YA?AW4D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063@@W4D3D12_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE@@@Z; ConvertToDDI(D3D12_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE)
0x180121e8e  mov     [rsp+0B8h+var_58], eax
0x180121e92  mov     eax, [rdi+14h]
0x180121e95  mov     [rsp+0B8h+var_54], eax
0x180121e99  mov     rax, qword ptr [rsp+0B8h+var_48]
0x180121e9e  mov     [rsp+0B8h+var_50], rax
0x180121ea3  mov     [rsp+0B8h+var_98], 20h ; ' '
0x180121eab  lea     r9, [rsp+0B8h+var_68]
0x180121eb0  mov     edx, 19h
0x180121eb5  mov     rcx, rbx
0x180121eb8  call    ?GetCaps@CDevice@@QEAAJW4D3D12DDICAPS_TYPE_VIDEO_0020@@PEAX1I@Z; CDevice::GetCaps(D3D12DDICAPS_TYPE_VIDEO_0020,void *,void *,uint)
0x180121ebd  mov     ebx, 887A0020h
0x180121ec2  test    eax, eax
0x180121ec4  jns     short loc_180121EDB
0x180121ec6  lea     r8, aGetcapsForD3d1_17; "GetCaps for D3D12DDICAPS_TYPE_VIDEO_006"...
0x180121ecd  mov     edx, ebx; int
0x180121ecf  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180121ed4  mov     ecx, ebx; int
0x180121ed6  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121edb  xor     r14d, r14d
0x180121ede  mov     rsi, qword ptr [rsp+0B8h+var_48]
0x180121ee3  mov     r15, qword ptr [rsp+0B8h+var_48+8]
0x180121ee8  cmp     rsi, r15
0x180121eeb  jz      loc_18012205D
0x180121ef1  cmp     qword ptr [rsi], 0
0x180121ef5  jnz     short loc_180121F0C
0x180121ef7  lea     r8, aGetcapsForD3d1_0; "GetCaps for D3D12DDICAPS_TYPE_VIDEO_006"...
0x180121efe  mov     edx, ebx; int
0x180121f00  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180121f05  mov     ecx, ebx; int
0x180121f07  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121f0c  cmp     dword ptr [rsi+8], 0Bh
0x180121f10  jl      short loc_180121F27
0x180121f12  lea     r8, aGetcapsForD3d1_3; "GetCaps for D3D12DDICAPS_TYPE_VIDEO_006"...
0x180121f19  mov     edx, ebx; int
0x180121f1b  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180121f20  mov     ecx, ebx; int
0x180121f22  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121f27  test    dword ptr [rsi+0Ch], 0FFFFFFFCh
0x180121f2e  jz      short loc_180121F45
0x180121f30  lea     r8, aGetcapsForD3d1_12; "GetCaps for D3D12DDICAPS_TYPE_VIDEO_006"...
0x180121f37  mov     edx, ebx; int
0x180121f39  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180121f3e  mov     ecx, ebx; int
0x180121f40  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121f45  cmp     dword ptr [rsi+8], 0Ah
0x180121f49  jnz     short loc_180121F8F
0x180121f4b  cmp     dword ptr [rsi+0Ch], 0
0x180121f4f  jnz     short loc_180121F66
0x180121f51  lea     r8, aGetcapsForD3d1_20; "GetCaps for D3D12DDICAPS_TYPE_VIDEO_006"...
0x180121f58  mov     edx, ebx; int
0x180121f5a  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180121f5f  mov     ecx, ebx; int
0x180121f61  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121f66  mov     ecx, [rdi+10h]; this
0x180121f69  lea     eax, [rcx-3]
0x180121f6c  test    eax, 0FFFFFFFCh
0x180121f71  jnz     short loc_180121FAA
0x180121f73  cmp     ecx, 5
0x180121f76  jz      short loc_180121FAA
0x180121f78  lea     r8, aGetcapsForD3d1_22; "GetCaps for D3D12DDICAPS_TYPE_VIDEO_006"...
0x180121f7f  mov     edx, ebx; int
0x180121f81  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180121f86  mov     ecx, ebx; int
0x180121f88  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121f8d  jmp     short loc_180121FAA
0x180121f8f  cmp     dword ptr [rsi+0Ch], 0
0x180121f93  jz      short loc_180121FAA
0x180121f95  lea     r8, aGetcapsForD3d1_21; "GetCaps for D3D12DDICAPS_TYPE_VIDEO_006"...
0x180121f9c  mov     edx, ebx; int
0x180121f9e  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180121fa3  mov     ecx, ebx; int
0x180121fa5  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180121faa  mov     ecx, [rsi+8]
0x180121fad  cmp     ecx, 5
0x180121fb0  jg      short loc_180121FF4
0x180121fb2  jz      short loc_180121FEC
0x180121fb4  test    ecx, ecx
0x180121fb6  jz      short loc_180121FE7
0x180121fb8  sub     ecx, 1
0x180121fbb  jz      short loc_180121FDF
0x180121fbd  sub     ecx, 1
0x180121fc0  jz      short loc_180121FD7
0x180121fc2  cmp     ecx, 1
0x180121fc5  jz      short loc_180121FCF
0x180121fc7  mov     r9d, 4
0x180121fcd  jmp     short loc_18012202E
0x180121fcf  mov     r9d, 3
0x180121fd5  jmp     short loc_18012202E
0x180121fd7  mov     r9d, 2
0x180121fdd  jmp     short loc_18012202E
0x180121fdf  mov     r9d, 1
0x180121fe5  jmp     short loc_18012202E
0x180121fe7  xor     r9d, r9d
0x180121fea  jmp     short loc_18012202E
0x180121fec  mov     r9d, 5
0x180121ff2  jmp     short loc_18012202E
0x180121ff4  sub     ecx, 6
0x180121ff7  jz      short loc_180122028
0x180121ff9  sub     ecx, 1
0x180121ffc  jz      short loc_180122020
0x180121ffe  sub     ecx, 1
0x180122001  jz      short loc_180122018
0x180122003  cmp     ecx, 1
0x180122006  jz      short loc_180122010
0x180122008  mov     r9d, 0Ah
0x18012200e  jmp     short loc_18012202E
0x180122010  mov     r9d, 9
0x180122016  jmp     short loc_18012202E
0x180122018  mov     r9d, 8
0x18012201e  jmp     short loc_18012202E
0x180122020  mov     r9d, 7
0x180122026  jmp     short loc_18012202E
0x180122028  mov     r9d, 6
0x18012202e  mov     r8d, [rsi+0Ch]
0x180122032  mov     edx, r14d
0x180122035  add     rdx, rdx
0x180122038  mov     rcx, [rdi+18h]
0x18012203c  mov     rax, [rsi]
0x18012203f  mov     [rcx+rdx*8], rax
0x180122043  mov     [rcx+rdx*8+8], r9d
0x180122048  and     r8d, 3
0x18012204c  mov     [rcx+rdx*8+0Ch], r8d
0x180122051  inc     r14d
0x180122054  add     rsi, 10h
0x180122058  jmp     loc_180121EE8
0x18012205d  lea     rcx, [rsp+0B8h+var_48]
0x180122062  call    ?_Tidy@?$vector@UD3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063@@V?$allocator@UD3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063@@@std@@@std@@AEAAXXZ; std::vector<D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063>::_Tidy(void)
0x180122067  nop
0x180122068  xor     eax, eax
0x18012206a  jmp     short loc_180122077
0x18012206c  mov     eax, 80070057h
0x180122071  jmp     short loc_180122077
0x180122073  mov     eax, [rsp+0B8h+var_88]
0x180122077  mov     rcx, [rsp+0B8h+var_28]
0x18012207f  xor     rcx, rsp; StackCookie
0x180122082  call    __security_check_cookie
0x180122087  lea     r11, [rsp+0B8h+var_18]
0x18012208f  mov     rbx, [r11+30h]
0x180122093  mov     rsi, [r11+38h]
0x180122097  mov     rsp, r11
0x18012209a  pop     r15
0x18012209c  pop     r14
0x18012209e  pop     rdi
0x18012209f  retn
```
