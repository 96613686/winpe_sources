# EarlyHeight

- ea: `0x18000c660`
- end: `0x18000cbcd`
- name: `EarlyHeight`
- size: `1389`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180003180`
- `0x180003cc4`
- `0x180007b70`
- `0x18000c660`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x18000cad8`
- `api-ms-win-crt-private-l1-1-0!_o__controlfp_s` at `0x18000cad8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c85e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c85e`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18000c80f`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18000c80f`

## pseudocode

```c
HANDLE __fastcall EarlyHeight(DWORD64 a1, __int64 a2, int a3)
{
  DWORD64 *v3; // r13
  __int64 v4; // rdi
  int v6; // ebx
  int v7; // esi
  unsigned int v8; // r12d
  DWORD64 v9; // r15
  HANDLE result; // rax
  int v11; // ecx
  const unsigned int near *const *v12; // r11
  int v13; // r10d
  unsigned int i; // r9d
  unsigned int v15; // ecx
  __int64 v16; // r8
  __int64 v17; // rcx
  int v18; // edi
  unsigned int v19; // ebx
  int v20; // eax
  HANDLE v22; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h]
  _DWORD v24[4]; // [rsp+38h] [rbp-C8h]
  _QWORD v25[4]; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  CONTEXT Context; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v30[16]; // [rsp+550h] [rbp+450h] BYREF
  _DWORD v31[16]; // [rsp+590h] [rbp+490h] BYREF
  _UNKNOWN *retaddr; // [rsp+618h] [rbp+518h] BYREF

  v3 = 0;
  v4 = a2;
  v23 = a2;
  v22 = 0;
  v6 = 7;
  memset_0(&Context, 0, sizeof(Context));
  v24[0] = 52;
  v25[0] = Area::IntegralRecord::IntegratedBinary;
  v7 = 8;
  v24[1] = 104;
  v25[1] = off_180125088;
  v8 = 79;
  v24[2] = 1040;
  v25[2] = qword_180129D50;
  v9 = 0;
  v24[3] = 312;
  v25[3] = qword_1800C4710;
  result = 0;
LABEL_2:
  v11 = a3;
  while ( 1 )
  {
    while ( v6 > 49 )
    {
      if ( v6 == 55 )
      {
        result = v22;
        v6 = 909;
        goto LABEL_2;
      }
      if ( v6 != 707 )
      {
        result = v22;
        if ( v6 == 807 )
        {
          v6 = 909;
          if ( v7 == 4 )
            v6 = 49;
        }
        else
        {
          v12 = &ScatteredInformation::PaintShortTermException;
          v13 = ScatteredInformation::StripedSeries ^ 0x157E9386;
          for ( i = 0; i < 0x1E; i += 2 )
          {
            v15 = *((_DWORD *)v12++ + 1);
            v16 = (unsigned __int8)((v13 ^ v15) / 0x9D28AF) - i - 1;
            v17 = (unsigned __int8)(((unsigned int)v13 ^ *((_DWORD *)v12 - 2)) / 0x9D28AF) - i;
            *((_QWORD *)&ScatteredInformation::StripedSeries + v17 + 1) = *((_QWORD *)&ScatteredInformation::StripedSeries
                                                                          + v16
                                                                          + 1);
          }
          v26 = 0;
          v27 = 0x2F5FFFFF008080D0LL;
          v30[0] = 923746055;
          v18 = ScatteredInformation::StripedSeries ^ 0x157E9386;
          v28 = 0xEF8F2FCFF09060B0uLL;
          IntegralRelation::OddMap = ScatteredInformation::StripedSeries ^ 0x157E9386;
          v30[1] = 656355095;
          v30[2] = 906903046;
          v30[3] = 639512086;
          v30[4] = 890060037;
          v30[5] = 622669077;
          v30[6] = 873217028;
          v30[7] = 605826068;
          v30[8] = 856374019;
          v30[9] = 588983059;
          v30[10] = 839531010;
          v30[11] = 572140050;
          v30[12] = 822688001;
          v30[13] = 555297041;
          v30[14] = 805844992;
          v30[15] = 538454032;
          v31[0] = 923746055;
          v31[1] = 656355095;
          v31[2] = 906903046;
          v31[3] = 639512086;
          v31[4] = 890060037;
          v31[5] = 622669077;
          v31[6] = 873217028;
          v31[7] = 605826068;
          v31[8] = 856374019;
          v31[9] = 588983059;
          v31[10] = 839531010;
          v31[11] = 572140050;
          v31[12] = 822688001;
          v31[13] = 555297041;
          v31[14] = 805844992;
          v31[15] = 538454032;
          v19 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
                  (__int64)&ScatteredInformation::StripedSeries,
                  &v27,
                  (__int64)v30)
              ^ 0xAAAAAAAA;
          v20 = ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(
                  (__int64)&ScatteredInformation::StripedSeries,
                  &v28,
                  (__int64)v31);
          _o__controlfp_s(&v26, (v20 ^ 0xAAAAAAAA) - v18, v19);
          v4 = v23;
          result = v22;
          v6 = 49;
        }
        goto LABEL_2;
      }
      if ( !v4 )
      {
        if ( v8 >= 4 )
        {
          result = v22;
          v6 = 807;
        }
        else
        {
          v6 = 37;
          v7 = 0;
          result = v22;
          a1 = v25[v8] - ((v8 + 1) << 6);
          v9 = a1 + v24[v8] - 48 * v8 - 48;
          ++v8;
        }
        goto LABEL_2;
      }
      result = v22;
      if ( !Context.ContextFlags )
      {
        v8 = 0;
        v6 = 17;
        goto LABEL_2;
      }
      v11 = a3;
      if ( v3 )
      {
        v9 = *v3;
        v6 = 21;
      }
      else
      {
        v6 = 19;
      }
    }
    if ( v6 == 49 )
      return result;
    if ( v6 == 7 )
    {
      if ( a1 )
      {
        result = GetCurrentThread();
        v22 = result;
        v6 = 707;
        goto LABEL_2;
      }
      v6 = 807;
    }
    else if ( v6 == 17 )
    {
      v6 = 707;
      Context.ContextFlags = v4 ^ a1;
      result = v22;
    }
    else
    {
      if ( v6 != 19 )
      {
        if ( v6 == 21 )
        {
          GetThreadContext(result, &Context);
          result = v22;
          v7 = 0;
          v6 = 37;
        }
        else if ( v7 )
        {
          switch ( v7 )
          {
            case 1:
              if ( Context.Dr1 >= a1 && Context.Dr1 <= v9 )
                v6 = 55;
              result = v22;
              v7 = 2;
              break;
            case 2:
              if ( Context.Dr2 >= a1 && Context.Dr2 <= v9 )
                v6 = 55;
              result = v22;
              v7 = 3;
              break;
            case 3:
              if ( Context.Dr3 >= a1 && Context.Dr3 <= v9 )
                v6 = 55;
              result = v22;
              v7 = 4;
              break;
            default:
              result = v22;
              v4 = 0;
              v23 = 0;
              v6 = 707;
              break;
          }
        }
        else
        {
          if ( Context.Dr0 >= a1 && Context.Dr0 <= v9 )
            v6 = 55;
          result = v22;
          v7 = 1;
        }
        goto LABEL_2;
      }
      Context.ContextFlags -= v11;
      v3 = (DWORD64 *)&retaddr;
      v6 = 707;
    }
  }
}

```

## disassembly

```asm
0x18000c660  mov     [rsp-8+arg_18], rbx
0x18000c665  push    rbp
0x18000c666  push    rsi
0x18000c667  push    rdi
0x18000c668  push    r12
0x18000c66a  push    r13
0x18000c66c  push    r14
0x18000c66e  push    r15
0x18000c670  lea     rbp, [rsp-4E0h]
0x18000c678  sub     rsp, 5E0h
0x18000c67f  mov     rax, cs:__security_cookie
0x18000c686  xor     rax, rsp
0x18000c689  mov     [rbp+510h+var_40], rax
0x18000c690  xor     r13d, r13d
0x18000c693  mov     [rsp+610h+var_5F0], r8d
0x18000c698  mov     rdi, rdx
0x18000c69b  mov     [rsp+610h+var_5E0], rdx
0x18000c6a0  mov     r14, rcx
0x18000c6a3  mov     [rsp+610h+var_5E8], r13
0x18000c6a8  xor     edx, edx; Val
0x18000c6aa  lea     rcx, [rbp+510h+Context]; void *
0x18000c6ae  mov     r8d, 4D0h; Size
0x18000c6b4  lea     ebx, [r13+7]
0x18000c6b8  call    memset_0
0x18000c6bd  lea     rax, ?IntegratedBinary@IntegralRecord@Area@@3UMoveTemporaryRaster@12@A; Area::IntegralRecord::MoveTemporaryRaster Area::IntegralRecord::IntegratedBinary
0x18000c6c4  mov     [rsp+610h+var_5D8], 34h ; '4'
0x18000c6cc  mov     [rsp+610h+var_5C8], rax
0x18000c6d1  lea     esi, [rbx+1]
0x18000c6d4  lea     rax, off_180125088
0x18000c6db  mov     [rsp+610h+var_5D4], 68h ; 'h'
0x18000c6e3  mov     [rsp+610h+var_5C0], rax
0x18000c6e8  lea     r12d, [r13+4Fh]
0x18000c6ec  lea     rax, qword_180129D50
0x18000c6f3  mov     [rsp+610h+var_5D0], 410h
0x18000c6fb  mov     [rsp+610h+var_5B8], rax
0x18000c700  xor     r15d, r15d
0x18000c703  lea     rax, qword_1800C4710
0x18000c70a  mov     [rsp+610h+var_5CC], 138h
0x18000c712  mov     [rsp+610h+var_5B0], rax
0x18000c717  mov     eax, r13d
0x18000c71a  mov     r8d, 31h ; '1'
0x18000c720  mov     edx, 37h ; '7'
0x18000c725  mov     ecx, [rsp+610h+var_5F0]
0x18000c729  nop     dword ptr [rax+00000000h]
0x18000c730  cmp     ebx, 31h ; '1'
0x18000c733  jg      loc_18000C873
0x18000c739  jz      loc_18000CBA3
0x18000c73f  cmp     ebx, 7
0x18000c742  jz      loc_18000C84F
0x18000c748  cmp     ebx, 11h
0x18000c74b  jz      loc_18000C838
0x18000c751  cmp     ebx, 13h
0x18000c754  jz      loc_18000C824
0x18000c75a  cmp     ebx, 15h
0x18000c75d  jz      loc_18000C808
0x18000c763  cmp     ebx, 25h ; '%'
0x18000c766  jnz     short loc_18000C730
0x18000c768  mov     ecx, esi
0x18000c76a  test    esi, esi
0x18000c76c  jz      short loc_18000C7EA
0x18000c76e  sub     ecx, 1
0x18000c771  jz      short loc_18000C7CC
0x18000c773  sub     ecx, 1
0x18000c776  jz      short loc_18000C7AE
0x18000c778  cmp     ecx, 1
0x18000c77b  jz      short loc_18000C790
0x18000c77d  mov     rax, [rsp+610h+var_5E8]
0x18000c782  xor     edi, edi
0x18000c784  mov     [rsp+610h+var_5E0], rdi
0x18000c789  mov     ebx, 2C3h
0x18000c78e  jmp     short loc_18000C725
0x18000c790  mov     rax, [rbp+510h+Context.Dr3]
0x18000c794  cmp     rax, r14
0x18000c797  jb      short loc_18000C79F
0x18000c799  cmp     rax, r15
0x18000c79c  cmovbe  ebx, edx
0x18000c79f  mov     rax, [rsp+610h+var_5E8]
0x18000c7a4  mov     esi, 4
0x18000c7a9  jmp     loc_18000C725
0x18000c7ae  mov     rax, [rbp+510h+Context.Dr2]
0x18000c7b2  cmp     rax, r14
0x18000c7b5  jb      short loc_18000C7BD
0x18000c7b7  cmp     rax, r15
0x18000c7ba  cmovbe  ebx, edx
0x18000c7bd  mov     rax, [rsp+610h+var_5E8]
0x18000c7c2  mov     esi, 3
0x18000c7c7  jmp     loc_18000C725
0x18000c7cc  mov     rax, [rbp+510h+Context.Dr1]
0x18000c7d0  cmp     rax, r14
0x18000c7d3  jb      short loc_18000C7DB
0x18000c7d5  cmp     rax, r15
0x18000c7d8  cmovbe  ebx, edx
0x18000c7db  mov     rax, [rsp+610h+var_5E8]
0x18000c7e0  mov     esi, 2
0x18000c7e5  jmp     loc_18000C725
0x18000c7ea  mov     rax, [rbp+510h+Context.Dr0]
0x18000c7ee  cmp     rax, r14
0x18000c7f1  jb      short loc_18000C7F9
0x18000c7f3  cmp     rax, r15
0x18000c7f6  cmovbe  ebx, edx
0x18000c7f9  mov     rax, [rsp+610h+var_5E8]
0x18000c7fe  mov     esi, 1
0x18000c803  jmp     loc_18000C725
0x18000c808  lea     rdx, [rbp+510h+Context]; lpContext
0x18000c80c  mov     rcx, rax; hThread
0x18000c80f  call    cs:__imp_GetThreadContext
0x18000c815  mov     rax, [rsp+610h+var_5E8]
0x18000c81a  xor     esi, esi
0x18000c81c  lea     ebx, [rsi+25h]
0x18000c81f  jmp     loc_18000C71A
0x18000c824  sub     [rbp+510h+Context.ContextFlags], ecx
0x18000c827  lea     r13, [rbp+518h]
0x18000c82e  mov     ebx, 2C3h
0x18000c833  jmp     loc_18000C730
0x18000c838  mov     eax, r14d
0x18000c83b  mov     ebx, 2C3h
0x18000c840  xor     eax, edi
0x18000c842  mov     [rbp+510h+Context.ContextFlags], eax
0x18000c845  mov     rax, [rsp+610h+var_5E8]
0x18000c84a  jmp     loc_18000C730
0x18000c84f  test    r14, r14
0x18000c852  jnz     short loc_18000C85E
0x18000c854  mov     ebx, 327h
0x18000c859  jmp     loc_18000C730
0x18000c85e  call    cs:__imp_GetCurrentThread
0x18000c864  mov     [rsp+610h+var_5E8], rax
0x18000c869  mov     ebx, 2C3h
0x18000c86e  jmp     loc_18000C71A
0x18000c873  mov     ecx, ebx
0x18000c875  sub     ecx, 37h ; '7'
0x18000c878  jz      loc_18000CB94
0x18000c87e  sub     ecx, 28Ch
0x18000c884  jz      loc_18000CB07
0x18000c88a  mov     rax, [rsp+610h+var_5E8]
0x18000c88f  sub     ecx, 64h ; 'd'
0x18000c892  jz      loc_18000CAF6
0x18000c898  cmp     ecx, 66h ; 'f'
0x18000c89b  mov     ecx, [rsp+610h+var_5F0]
0x18000c89f  jnz     loc_18000C730
0x18000c8a5  mov     r10d, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x18000c8ac  lea     r11, ?PaintShortTermException@ScatteredInformation@@2QBIB; uint const near * const ScatteredInformation::PaintShortTermException
0x18000c8b3  xor     r10d, 157E9386h
0x18000c8ba  lea     rbx, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x18000c8c1  xor     r9d, r9d
0x18000c8c4  nop     dword ptr [rax+00h]
0x18000c8c8  nop     dword ptr [rax+rax+00000000h]
0x18000c8d0  mov     ecx, [r11+4]
0x18000c8d4  lea     r11, [r11+8]
0x18000c8d8  xor     ecx, r10d
0x18000c8db  mov     eax, 68404C21h
0x18000c8e0  mul     ecx
0x18000c8e2  mov     ecx, [r11-8]
0x18000c8e6  mov     eax, 68404C21h
0x18000c8eb  xor     ecx, r10d
0x18000c8ee  shr     edx, 16h
0x18000c8f1  movzx   r8d, dl
0x18000c8f5  mul     ecx
0x18000c8f7  sub     r8d, r9d
0x18000c8fa  shr     edx, 16h
0x18000c8fd  dec     r8d
0x18000c900  movzx   ecx, dl
0x18000c903  sub     ecx, r9d
0x18000c906  add     r9d, 2
0x18000c90a  mov     rax, [rbx+r8*8+8]
0x18000c90f  mov     [rbx+rcx*8+8], rax
0x18000c914  cmp     r9d, 1Eh
0x18000c918  jb      short loc_18000C8D0
0x18000c91a  mov     edi, cs:?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x18000c920  lea     r8, [rbp+510h+var_C0]
0x18000c927  mov     rax, 2F5FFFFF008080D0h
0x18000c931  mov     [rsp+610h+var_5A8], 0
0x18000c939  mov     [rsp+610h+var_5A0], rax
0x18000c93e  lea     rdx, [rsp+610h+var_5A0]
0x18000c943  mov     rax, 0EF8F2FCFF09060B0h
0x18000c94d  mov     [rbp+510h+var_C0], 370F3F07h
0x18000c957  xor     edi, 157E9386h
0x18000c95d  mov     [rsp+610h+var_598], rax
0x18000c962  mov     rcx, rbx
0x18000c965  mov     cs:?OddMap@IntegralRelation@@2IA, edi; uint IntegralRelation::OddMap
0x18000c96b  mov     [rbp+510h+var_BC], 271F2F17h
0x18000c975  mov     [rbp+510h+var_B8], 360E3E06h
0x18000c97f  mov     [rbp+510h+var_B4], 261E2E16h
0x18000c989  mov     [rbp+510h+var_B0], 350D3D05h
0x18000c993  mov     [rbp+510h+var_AC], 251D2D15h
0x18000c99d  mov     [rbp+510h+var_A8], 340C3C04h
0x18000c9a7  mov     [rbp+510h+var_A4], 241C2C14h
0x18000c9b1  mov     [rbp+510h+var_A0], 330B3B03h
0x18000c9bb  mov     [rbp+510h+var_9C], 231B2B13h
0x18000c9c5  mov     [rbp+510h+var_98], 320A3A02h
0x18000c9cf  mov     [rbp+510h+var_94], 221A2A12h
0x18000c9d9  mov     [rbp+510h+var_90], 31093901h
0x18000c9e3  mov     [rbp+510h+var_8C], 21192911h
0x18000c9ed  mov     [rbp+510h+var_88], 30083800h
0x18000c9f7  mov     [rbp+510h+var_84], 20182810h
0x18000ca01  mov     [rbp+510h+var_80], 370F3F07h
0x18000ca0b  mov     [rbp+510h+var_7C], 271F2F17h
0x18000ca15  mov     [rbp+510h+var_78], 360E3E06h
0x18000ca1f  mov     [rbp+510h+var_74], 261E2E16h
0x18000ca29  mov     [rbp+510h+var_70], 350D3D05h
0x18000ca33  mov     [rbp+510h+var_6C], 251D2D15h
0x18000ca3d  mov     [rbp+510h+var_68], 340C3C04h
0x18000ca47  mov     [rbp+510h+var_64], 241C2C14h
0x18000ca51  mov     [rbp+510h+var_60], 330B3B03h
0x18000ca5b  mov     [rbp+510h+var_5C], 231B2B13h
0x18000ca65  mov     [rbp+510h+var_58], 320A3A02h
0x18000ca6f  mov     [rbp+510h+var_54], 221A2A12h
0x18000ca79  mov     [rbp+510h+var_50], 31093901h
0x18000ca83  mov     [rbp+510h+var_4C], 21192911h
0x18000ca8d  mov     [rbp+510h+var_48], 30083800h
0x18000ca97  mov     [rbp+510h+var_44], 20182810h
0x18000caa1  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x18000caa6  mov     rbx, rax
0x18000caa9  lea     r8, [rbp+510h+var_80]
0x18000cab0  lea     rdx, [rsp+610h+var_598]
0x18000cab5  xor     ebx, 0AAAAAAAAh
0x18000cabb  lea     rcx, ?StripedSeries@ScatteredInformation@@2V1@A; ScatteredInformation ScatteredInformation::StripedSeries
0x18000cac2  call    ??$WriteConstructStrategy@_K$0EA@@ScatteredInformation@@AEBA_KAEB_KAEAY0EA@$$CBE@Z; ScatteredInformation::WriteConstructStrategy<unsigned __int64,64>(unsigned __int64 const &,uchar const (&)[64])
0x18000cac7  xor     eax, 0AAAAAAAAh
0x18000cacc  lea     rcx, [rsp+610h+var_5A8]
0x18000cad1  sub     eax, edi
0x18000cad3  mov     r8d, ebx
0x18000cad6  mov     edx, eax
0x18000cad8  call    cs:__imp__o__controlfp_s
0x18000cade  mov     rdi, [rsp+610h+var_5E0]
0x18000cae3  mov     r8d, 31h ; '1'
0x18000cae9  mov     rax, [rsp+610h+var_5E8]
0x18000caee  mov     ebx, r8d
0x18000caf1  jmp     loc_18000C720
0x18000caf6  cmp     esi, 4
0x18000caf9  mov     ebx, 38Dh
0x18000cafe  cmovz   ebx, r8d
0x18000cb02  jmp     loc_18000C725
0x18000cb07  test    rdi, rdi
0x18000cb0a  jnz     short loc_18000CB5C
0x18000cb0c  cmp     r12d, 4
0x18000cb10  jnb     short loc_18000CB4D
0x18000cb12  mov     edx, r12d
0x18000cb15  lea     eax, [r12+r12*2]
0x18000cb19  lea     ecx, [r12+1]
0x18000cb1e  shl     eax, 4
0x18000cb21  shl     ecx, 6
0x18000cb24  lea     ebx, [rdi+25h]
0x18000cb27  xor     esi, esi
0x18000cb29  mov     r15d, [rsp+rdx*4+610h+var_5D8]
0x18000cb2e  mov     r14, [rsp+rdx*8+610h+var_5C8]
0x18000cb33  sub     r15d, eax
0x18000cb36  mov     rax, [rsp+610h+var_5E8]
0x18000cb3b  sub     r15d, 30h ; '0'
0x18000cb3f  sub     r14, rcx
0x18000cb42  add     r15, r14
0x18000cb45  inc     r12d
0x18000cb48  jmp     loc_18000C720
0x18000cb4d  mov     rax, [rsp+610h+var_5E8]
0x18000cb52  mov     ebx, 327h
0x18000cb57  jmp     loc_18000C725
0x18000cb5c  cmp     [rbp+510h+Context.ContextFlags], 0
0x18000cb60  mov     rax, [rsp+610h+var_5E8]
0x18000cb65  jnz     short loc_18000CB74
0x18000cb67  xor     r12d, r12d
0x18000cb6a  lea     ebx, [r12+11h]
0x18000cb6f  jmp     loc_18000C725
0x18000cb74  mov     ecx, [rsp+610h+var_5F0]
0x18000cb78  test    r13, r13
0x18000cb7b  jnz     short loc_18000CB86
0x18000cb7d  lea     ebx, [r13+13h]
0x18000cb81  jmp     loc_18000C730
0x18000cb86  mov     r15, [r13+0]
0x18000cb8a  mov     ebx, 15h
0x18000cb8f  jmp     loc_18000C730
0x18000cb94  mov     rax, [rsp+610h+var_5E8]
0x18000cb99  mov     ebx, 38Dh
0x18000cb9e  jmp     loc_18000C725
0x18000cba3  mov     rcx, [rbp+510h+var_40]
0x18000cbaa  xor     rcx, rsp; StackCookie
0x18000cbad  call    __security_check_cookie
0x18000cbb2  mov     rbx, [rsp+610h+arg_18]
0x18000cbba  add     rsp, 5E0h
0x18000cbc1  pop     r15
0x18000cbc3  pop     r14
0x18000cbc5  pop     r13
0x18000cbc7  pop     r12
0x18000cbc9  pop     rdi
0x18000cbca  pop     rsi
0x18000cbcb  pop     rbp
0x18000cbcc  retn
```
