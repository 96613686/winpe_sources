# CD3D12Strings::ToString(D3D12_FILTER)

- ea: `0x18002efd4`
- end: `0x18002f36e`
- name: `?ToString@CD3D12Strings@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4D3D12_FILTER@@@Z`
- size: `922`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002e790`

## callees

- `0x18002efd4`
- `0x180058468`
- `0x18009fa70`
- `0x18009fd4c`
- `0x18009fd8c`
- `0x1800bb480`
- `0x1800cc2e0`
- `0x1800e7358`

## string_xrefs

- `0x18002f0f4`: `D3D12_FILTER_COMPARISON_MIN_MAG_MIP_POINT`
- `0x18002f18e`: `D3D12_FILTER_COMPARISON_MIN_POINT_MAG_LINEAR_MIP_POINT`
- `0x18002f19a`: `D3D12_FILTER_COMPARISON_MIN_MAG_POINT_MIP_LINEAR`
- `0x18002f176`: `D3D12_FILTER_COMPARISON_MIN_LINEAR_MAG_MIP_POINT`
- `0x18002f182`: `D3D12_FILTER_COMPARISON_MIN_POINT_MAG_MIP_LINEAR`
- `0x18002f15e`: `D3D12_FILTER_COMPARISON_MIN_MAG_LINEAR_MIP_POINT`
- `0x18002f16a`: `D3D12_FILTER_COMPARISON_MIN_LINEAR_MAG_POINT_MIP_LINEAR`
- `0x18002f146`: `D3D12_FILTER_COMPARISON_MIN_MAG_ANISOTROPIC_MIP_POINT`
- `0x18002f152`: `D3D12_FILTER_COMPARISON_MIN_MAG_MIP_LINEAR`
- `0x18002f13a`: `D3D12_FILTER_COMPARISON_ANISOTROPIC`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CD3D12Strings::ToString(__int64 a1, __int64 a2)
{
  const char *v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rax
  _BYTE v7[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v8[32]; // [rsp+50h] [rbp-38h] BYREF

  if ( (int)a2 > 256 )
  {
    if ( (int)a2 > 384 )
    {
      switch ( (_DWORD)a2 )
      {
        case 0x181:
          v3 = "D3D12_FILTER_MAXIMUM_MIN_MAG_POINT_MIP_LINEAR";
          goto LABEL_86;
        case 0x184:
          v3 = "D3D12_FILTER_MAXIMUM_MIN_POINT_MAG_LINEAR_MIP_POINT";
          goto LABEL_86;
        case 0x185:
          v3 = "D3D12_FILTER_MAXIMUM_MIN_POINT_MAG_MIP_LINEAR";
          goto LABEL_86;
        case 0x190:
          v3 = "D3D12_FILTER_MAXIMUM_MIN_LINEAR_MAG_MIP_POINT";
          goto LABEL_86;
        case 0x191:
          v3 = "D3D12_FILTER_MAXIMUM_MIN_LINEAR_MAG_POINT_MIP_LINEAR";
          goto LABEL_86;
        case 0x194:
          v3 = "D3D12_FILTER_MAXIMUM_MIN_MAG_LINEAR_MIP_POINT";
          goto LABEL_86;
        case 0x195:
          v3 = "D3D12_FILTER_MAXIMUM_MIN_MAG_MIP_LINEAR";
          goto LABEL_86;
        case 0x1D4:
          v3 = "D3D12_FILTER_MAXIMUM_MIN_MAG_ANISOTROPIC_MIP_POINT";
          goto LABEL_86;
        case 0x1D5:
          v3 = "D3D12_FILTER_MAXIMUM_ANISOTROPIC";
          goto LABEL_86;
      }
    }
    else
    {
      switch ( (_DWORD)a2 )
      {
        case 0x180:
          v3 = "D3D12_FILTER_MAXIMUM_MIN_MAG_MIP_POINT";
          goto LABEL_86;
        case 0x101:
          v3 = "D3D12_FILTER_MINIMUM_MIN_MAG_POINT_MIP_LINEAR";
          goto LABEL_86;
        case 0x104:
          v3 = "D3D12_FILTER_MINIMUM_MIN_POINT_MAG_LINEAR_MIP_POINT";
          goto LABEL_86;
        case 0x105:
          v3 = "D3D12_FILTER_MINIMUM_MIN_POINT_MAG_MIP_LINEAR";
          goto LABEL_86;
        case 0x110:
          v3 = "D3D12_FILTER_MINIMUM_MIN_LINEAR_MAG_MIP_POINT";
          goto LABEL_86;
        case 0x111:
          v3 = "D3D12_FILTER_MINIMUM_MIN_LINEAR_MAG_POINT_MIP_LINEAR";
          goto LABEL_86;
        case 0x114:
          v3 = "D3D12_FILTER_MINIMUM_MIN_MAG_LINEAR_MIP_POINT";
          goto LABEL_86;
        case 0x115:
          v3 = "D3D12_FILTER_MINIMUM_MIN_MAG_MIP_LINEAR";
          goto LABEL_86;
        case 0x154:
          v3 = "D3D12_FILTER_MINIMUM_MIN_MAG_ANISOTROPIC_MIP_POINT";
          goto LABEL_86;
        case 0x155:
          v3 = "D3D12_FILTER_MINIMUM_ANISOTROPIC";
          goto LABEL_86;
      }
    }
LABEL_76:
    std::_Integral_to_string<char,int>(v7, a2, 0);
    v5 = std::operator+<char>(v8, v4, v7);
    std::operator+<char>(a1, v5, ")");
    std::string::_Tidy_deallocate(v8);
    std::string::_Tidy_deallocate(v7);
    return a1;
  }
  if ( (_DWORD)a2 == 256 )
  {
    v3 = "D3D12_FILTER_MINIMUM_MIN_MAG_MIP_POINT";
    goto LABEL_86;
  }
  if ( (int)a2 > 128 )
  {
    switch ( (_DWORD)a2 )
    {
      case 0x81:
        v3 = "D3D12_FILTER_COMPARISON_MIN_MAG_POINT_MIP_LINEAR";
        goto LABEL_86;
      case 0x84:
        v3 = "D3D12_FILTER_COMPARISON_MIN_POINT_MAG_LINEAR_MIP_POINT";
        goto LABEL_86;
      case 0x85:
        v3 = "D3D12_FILTER_COMPARISON_MIN_POINT_MAG_MIP_LINEAR";
        goto LABEL_86;
      case 0x90:
        v3 = "D3D12_FILTER_COMPARISON_MIN_LINEAR_MAG_MIP_POINT";
        goto LABEL_86;
      case 0x91:
        v3 = "D3D12_FILTER_COMPARISON_MIN_LINEAR_MAG_POINT_MIP_LINEAR";
        goto LABEL_86;
      case 0x94:
        v3 = "D3D12_FILTER_COMPARISON_MIN_MAG_LINEAR_MIP_POINT";
        goto LABEL_86;
      case 0x95:
        v3 = "D3D12_FILTER_COMPARISON_MIN_MAG_MIP_LINEAR";
        goto LABEL_86;
      case 0xD4:
        v3 = "D3D12_FILTER_COMPARISON_MIN_MAG_ANISOTROPIC_MIP_POINT";
        goto LABEL_86;
      case 0xD5:
        v3 = "D3D12_FILTER_COMPARISON_ANISOTROPIC";
        goto LABEL_86;
    }
    goto LABEL_76;
  }
  if ( (_DWORD)a2 == 128 )
  {
    v3 = "D3D12_FILTER_COMPARISON_MIN_MAG_MIP_POINT";
    goto LABEL_86;
  }
  if ( (int)a2 > 17 )
  {
    switch ( (_DWORD)a2 )
    {
      case 0x14:
        v3 = "D3D12_FILTER_MIN_MAG_LINEAR_MIP_POINT";
        goto LABEL_86;
      case 0x15:
        v3 = "D3D12_FILTER_MIN_MAG_MIP_LINEAR";
        goto LABEL_86;
      case 0x54:
        v3 = "D3D12_FILTER_MIN_MAG_ANISOTROPIC_MIP_POINT";
        goto LABEL_86;
      case 0x55:
        v3 = "D3D12_FILTER_ANISOTROPIC";
        goto LABEL_86;
    }
    goto LABEL_76;
  }
  if ( (_DWORD)a2 == 17 )
  {
    v3 = "D3D12_FILTER_MIN_LINEAR_MAG_POINT_MIP_LINEAR";
    goto LABEL_86;
  }
  if ( (_DWORD)a2 )
  {
    switch ( (_DWORD)a2 )
    {
      case 1:
        v3 = "D3D12_FILTER_MIN_MAG_POINT_MIP_LINEAR";
        goto LABEL_86;
      case 4:
        v3 = "D3D12_FILTER_MIN_POINT_MAG_LINEAR_MIP_POINT";
        goto LABEL_86;
      case 5:
        v3 = "D3D12_FILTER_MIN_POINT_MAG_MIP_LINEAR";
        goto LABEL_86;
      case 0x10:
        v3 = "D3D12_FILTER_MIN_LINEAR_MAG_MIP_POINT";
LABEL_86:
        std::string::string(a1, v3);
        return a1;
    }
    goto LABEL_76;
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::string::_Construct<1,char const *>(a1, "D3D12_FILTER_MIN_MAG_MIP_POINT", 30);
  return a1;
}

```

## disassembly

```asm
0x18002efd4  push    rbx
0x18002efd6  sub     rsp, 80h
0x18002efdd  mov     rax, cs:__security_cookie
0x18002efe4  xor     rax, rsp
0x18002efe7  mov     [rsp+88h+var_18], rax
0x18002efec  mov     rbx, rcx
0x18002efef  mov     [rsp+88h+var_60], rcx
0x18002eff4  xor     r8d, r8d
0x18002eff7  mov     eax, 100h
0x18002effc  cmp     edx, eax
0x18002effe  jg      loc_18002F1B2
0x18002f004  jz      loc_18002F1A6
0x18002f00a  mov     eax, 80h
0x18002f00f  cmp     edx, eax
0x18002f011  jg      loc_18002F100
0x18002f017  jz      loc_18002F0F4
0x18002f01d  cmp     edx, 11h
0x18002f020  jg      loc_18002F0AA
0x18002f026  jz      short loc_18002F09E
0x18002f028  mov     ecx, edx
0x18002f02a  test    edx, edx
0x18002f02c  jz      short loc_18002F076
0x18002f02e  sub     ecx, 1
0x18002f031  jz      short loc_18002F06A
0x18002f033  sub     ecx, 3
0x18002f036  jz      short loc_18002F05E
0x18002f038  sub     ecx, 1
0x18002f03b  jz      short loc_18002F052
0x18002f03d  cmp     ecx, 0Bh
0x18002f040  jnz     loc_18002F2B9
0x18002f046  lea     rdx, aD3d12FilterMin_14; "D3D12_FILTER_MIN_LINEAR_MAG_MIP_POINT"
0x18002f04d  jmp     loc_18002F34D
0x18002f052  lea     rdx, aD3d12FilterMin_6; "D3D12_FILTER_MIN_POINT_MAG_MIP_LINEAR"
0x18002f059  jmp     loc_18002F34D
0x18002f05e  lea     rdx, aD3d12FilterMin_4; "D3D12_FILTER_MIN_POINT_MAG_LINEAR_MIP_P"...
0x18002f065  jmp     loc_18002F34D
0x18002f06a  lea     rdx, aD3d12FilterMin_17; "D3D12_FILTER_MIN_MAG_POINT_MIP_LINEAR"
0x18002f071  jmp     loc_18002F34D
0x18002f076  xorps   xmm0, xmm0
0x18002f079  movups  xmmword ptr [rbx], xmm0
0x18002f07c  mov     [rbx+10h], r8
0x18002f080  mov     [rbx+18h], r8
0x18002f084  mov     r8d, 1Eh
0x18002f08a  lea     rdx, aD3d12FilterMin_15; "D3D12_FILTER_MIN_MAG_MIP_POINT"
0x18002f091  mov     rcx, rbx
0x18002f094  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002f099  jmp     loc_18002F355
0x18002f09e  lea     rdx, aD3d12FilterMin_5; "D3D12_FILTER_MIN_LINEAR_MAG_POINT_MIP_L"...
0x18002f0a5  jmp     loc_18002F350
0x18002f0aa  mov     ecx, edx
0x18002f0ac  sub     ecx, 14h
0x18002f0af  jz      short loc_18002F0E8
0x18002f0b1  sub     ecx, 1
0x18002f0b4  jz      short loc_18002F0DC
0x18002f0b6  sub     ecx, 3Fh ; '?'
0x18002f0b9  jz      short loc_18002F0D0
0x18002f0bb  cmp     ecx, 1
0x18002f0be  jnz     loc_18002F2B9
0x18002f0c4  lea     rdx, aD3d12FilterAni; "D3D12_FILTER_ANISOTROPIC"
0x18002f0cb  jmp     loc_18002F34D
0x18002f0d0  lea     rdx, aD3d12FilterMin_9; "D3D12_FILTER_MIN_MAG_ANISOTROPIC_MIP_PO"...
0x18002f0d7  jmp     loc_18002F34D
0x18002f0dc  lea     rdx, aD3d12FilterMin_16; "D3D12_FILTER_MIN_MAG_MIP_LINEAR"
0x18002f0e3  jmp     loc_18002F34D
0x18002f0e8  lea     rdx, aD3d12FilterMin_7; "D3D12_FILTER_MIN_MAG_LINEAR_MIP_POINT"
0x18002f0ef  jmp     loc_18002F34D
0x18002f0f4  lea     rdx, aD3d12FilterCom_5; "D3D12_FILTER_COMPARISON_MIN_MAG_MIP_POI"...
0x18002f0fb  jmp     loc_18002F350
0x18002f100  mov     ecx, edx
0x18002f102  sub     ecx, 81h
0x18002f108  jz      loc_18002F19A
0x18002f10e  sub     ecx, 3
0x18002f111  jz      short loc_18002F18E
0x18002f113  sub     ecx, 1
0x18002f116  jz      short loc_18002F182
0x18002f118  sub     ecx, 0Bh
0x18002f11b  jz      short loc_18002F176
0x18002f11d  sub     ecx, 1
0x18002f120  jz      short loc_18002F16A
0x18002f122  sub     ecx, 3
0x18002f125  jz      short loc_18002F15E
0x18002f127  sub     ecx, 1
0x18002f12a  jz      short loc_18002F152
0x18002f12c  sub     ecx, 3Fh ; '?'
0x18002f12f  jz      short loc_18002F146
0x18002f131  cmp     ecx, 1
0x18002f134  jnz     loc_18002F2B9
0x18002f13a  lea     rdx, aD3d12FilterCom_0; "D3D12_FILTER_COMPARISON_ANISOTROPIC"
0x18002f141  jmp     loc_18002F34D
0x18002f146  lea     rdx, aD3d12FilterCom_7; "D3D12_FILTER_COMPARISON_MIN_MAG_ANISOTR"...
0x18002f14d  jmp     loc_18002F34D
0x18002f152  lea     rdx, aD3d12FilterCom_2; "D3D12_FILTER_COMPARISON_MIN_MAG_MIP_LIN"...
0x18002f159  jmp     loc_18002F34D
0x18002f15e  lea     rdx, aD3d12FilterCom_1; "D3D12_FILTER_COMPARISON_MIN_MAG_LINEAR_"...
0x18002f165  jmp     loc_18002F34D
0x18002f16a  lea     rdx, aD3d12FilterCom_4; "D3D12_FILTER_COMPARISON_MIN_LINEAR_MAG_"...
0x18002f171  jmp     loc_18002F34D
0x18002f176  lea     rdx, aD3d12FilterCom_6; "D3D12_FILTER_COMPARISON_MIN_LINEAR_MAG_"...
0x18002f17d  jmp     loc_18002F34D
0x18002f182  lea     rdx, aD3d12FilterCom; "D3D12_FILTER_COMPARISON_MIN_POINT_MAG_M"...
0x18002f189  jmp     loc_18002F34D
0x18002f18e  lea     rdx, aD3d12FilterCom_8; "D3D12_FILTER_COMPARISON_MIN_POINT_MAG_L"...
0x18002f195  jmp     loc_18002F34D
0x18002f19a  lea     rdx, aD3d12FilterCom_3; "D3D12_FILTER_COMPARISON_MIN_MAG_POINT_M"...
0x18002f1a1  jmp     loc_18002F34D
0x18002f1a6  lea     rdx, aD3d12FilterMin_0; "D3D12_FILTER_MINIMUM_MIN_MAG_MIP_POINT"
0x18002f1ad  jmp     loc_18002F350
0x18002f1b2  mov     eax, 180h
0x18002f1b7  cmp     edx, eax
0x18002f1b9  jg      loc_18002F277
0x18002f1bf  jz      loc_18002F26B
0x18002f1c5  mov     ecx, edx
0x18002f1c7  sub     ecx, 101h
0x18002f1cd  jz      loc_18002F25F
0x18002f1d3  sub     ecx, 3
0x18002f1d6  jz      short loc_18002F253
0x18002f1d8  sub     ecx, 1
0x18002f1db  jz      short loc_18002F247
0x18002f1dd  sub     ecx, 0Bh
0x18002f1e0  jz      short loc_18002F23B
0x18002f1e2  sub     ecx, 1
0x18002f1e5  jz      short loc_18002F22F
0x18002f1e7  sub     ecx, 3
0x18002f1ea  jz      short loc_18002F223
0x18002f1ec  sub     ecx, 1
0x18002f1ef  jz      short loc_18002F217
0x18002f1f1  sub     ecx, 3Fh ; '?'
0x18002f1f4  jz      short loc_18002F20B
0x18002f1f6  cmp     ecx, 1
0x18002f1f9  jnz     loc_18002F2B9
0x18002f1ff  lea     rdx, aD3d12FilterMin_2; "D3D12_FILTER_MINIMUM_ANISOTROPIC"
0x18002f206  jmp     loc_18002F34D
0x18002f20b  lea     rdx, aD3d12FilterMin; "D3D12_FILTER_MINIMUM_MIN_MAG_ANISOTROPI"...
0x18002f212  jmp     loc_18002F34D
0x18002f217  lea     rdx, aD3d12FilterMin_12; "D3D12_FILTER_MINIMUM_MIN_MAG_MIP_LINEAR"
0x18002f21e  jmp     loc_18002F34D
0x18002f223  lea     rdx, aD3d12FilterMin_11; "D3D12_FILTER_MINIMUM_MIN_MAG_LINEAR_MIP"...
0x18002f22a  jmp     loc_18002F34D
0x18002f22f  lea     rdx, aD3d12FilterMin_8; "D3D12_FILTER_MINIMUM_MIN_LINEAR_MAG_POI"...
0x18002f236  jmp     loc_18002F34D
0x18002f23b  lea     rdx, aD3d12FilterMin_1; "D3D12_FILTER_MINIMUM_MIN_LINEAR_MAG_MIP"...
0x18002f242  jmp     loc_18002F34D
0x18002f247  lea     rdx, aD3d12FilterMin_3; "D3D12_FILTER_MINIMUM_MIN_POINT_MAG_MIP_"...
0x18002f24e  jmp     loc_18002F34D
0x18002f253  lea     rdx, aD3d12FilterMin_13; "D3D12_FILTER_MINIMUM_MIN_POINT_MAG_LINE"...
0x18002f25a  jmp     loc_18002F34D
0x18002f25f  lea     rdx, aD3d12FilterMin_10; "D3D12_FILTER_MINIMUM_MIN_MAG_POINT_MIP_"...
0x18002f266  jmp     loc_18002F34D
0x18002f26b  lea     rdx, aD3d12FilterMax_4; "D3D12_FILTER_MAXIMUM_MIN_MAG_MIP_POINT"
0x18002f272  jmp     loc_18002F350
0x18002f277  mov     ecx, edx
0x18002f279  sub     ecx, 181h
0x18002f27f  jz      loc_18002F346
0x18002f285  sub     ecx, 3
0x18002f288  jz      loc_18002F33D
0x18002f28e  sub     ecx, 1
0x18002f291  jz      loc_18002F334
0x18002f297  sub     ecx, 0Bh
0x18002f29a  jz      loc_18002F32B
0x18002f2a0  sub     ecx, 1
0x18002f2a3  jz      short loc_18002F322
0x18002f2a5  sub     ecx, 3
0x18002f2a8  jz      short loc_18002F319
0x18002f2aa  sub     ecx, 1
0x18002f2ad  jz      short loc_18002F310
0x18002f2af  sub     ecx, 3Fh ; '?'
0x18002f2b2  jz      short loc_18002F307
0x18002f2b4  cmp     ecx, 1
0x18002f2b7  jz      short loc_18002F2FE
0x18002f2b9  lea     rcx, [rsp+88h+var_58]
0x18002f2be  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x18002f2c3  nop
0x18002f2c4  lea     r8, [rsp+88h+var_58]
0x18002f2c9  lea     rcx, [rsp+88h+var_38]
0x18002f2ce  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18002f2d3  nop
0x18002f2d4  lea     r8, asc_1802AFB58; ")"
0x18002f2db  mov     rdx, rax
0x18002f2de  mov     rcx, rbx
0x18002f2e1  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18002f2e6  nop
0x18002f2e7  lea     rcx, [rsp+88h+var_38]
0x18002f2ec  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002f2f1  nop
0x18002f2f2  lea     rcx, [rsp+88h+var_58]
0x18002f2f7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002f2fc  jmp     short loc_18002F355
0x18002f2fe  lea     rdx, aD3d12FilterMax_8; "D3D12_FILTER_MAXIMUM_ANISOTROPIC"
0x18002f305  jmp     short loc_18002F34D
0x18002f307  lea     rdx, aD3d12FilterMax_3; "D3D12_FILTER_MAXIMUM_MIN_MAG_ANISOTROPI"...
0x18002f30e  jmp     short loc_18002F34D
0x18002f310  lea     rdx, aD3d12FilterMax_2; "D3D12_FILTER_MAXIMUM_MIN_MAG_MIP_LINEAR"
0x18002f317  jmp     short loc_18002F34D
0x18002f319  lea     rdx, aD3d12FilterMax_6; "D3D12_FILTER_MAXIMUM_MIN_MAG_LINEAR_MIP"...
0x18002f320  jmp     short loc_18002F34D
0x18002f322  lea     rdx, aD3d12FilterMax_7; "D3D12_FILTER_MAXIMUM_MIN_LINEAR_MAG_POI"...
0x18002f329  jmp     short loc_18002F34D
0x18002f32b  lea     rdx, aD3d12FilterMax; "D3D12_FILTER_MAXIMUM_MIN_LINEAR_MAG_MIP"...
0x18002f332  jmp     short loc_18002F34D
0x18002f334  lea     rdx, aD3d12FilterMax_1; "D3D12_FILTER_MAXIMUM_MIN_POINT_MAG_MIP_"...
0x18002f33b  jmp     short loc_18002F34D
0x18002f33d  lea     rdx, aD3d12FilterMax_5; "D3D12_FILTER_MAXIMUM_MIN_POINT_MAG_LINE"...
0x18002f344  jmp     short loc_18002F34D
0x18002f346  lea     rdx, aD3d12FilterMax_0; "D3D12_FILTER_MAXIMUM_MIN_MAG_POINT_MIP_"...
0x18002f34d  mov     rcx, rbx
0x18002f350  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002f355  mov     rax, rbx
0x18002f358  mov     rcx, [rsp+88h+var_18]
0x18002f35d  xor     rcx, rsp; StackCookie
0x18002f360  call    __security_check_cookie
0x18002f365  add     rsp, 80h
0x18002f36c  pop     rbx
0x18002f36d  retn
```
