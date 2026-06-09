# ProcessMultiHashOperations

- ea: `0x180065a50`
- end: `0x180065f84`
- name: `ProcessMultiHashOperations`
- size: `1332`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180065720`

## callees

- `0x18000ecb0`
- `0x180065a50`
- `0x180083010`

## string_xrefs

- `0x180065edc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall ProcessMultiHashOperations(_DWORD *a1, unsigned int *a2, int a3)
{
  __int64 (__fastcall *v6)(); // r13
  __int64 (__fastcall *v7)(); // r12
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(int, int, int, int, __int64, __int64); // r13
  __int64 v10; // rbx
  unsigned int v11; // ebp
  __int64 v12; // r15
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdx
  _DWORD *v17; // r15
  __int64 (__fastcall *v18)(); // rax
  __int64 (__fastcall *v19)(); // rax
  __int64 v20; // r9
  __int64 (__fastcall *v22)(); // [rsp+80h] [rbp+8h]
  _DWORD *v23; // [rsp+88h] [rbp+10h]

  v22 = 0;
  v23 = 0;
  switch ( a1[2] )
  {
    case 0x20001:
      v6 = (__int64 (__fastcall *)())&SymCryptHmacMd5Append;
      v7 = (__int64 (__fastcall *)())SymCryptMd5Result;
      goto LABEL_3;
    case 0x20002:
      v6 = (__int64 (__fastcall *)())SymCryptSha1Append;
      v8 = 128;
      v7 = (__int64 (__fastcall *)())SymCryptSha1Result;
      goto LABEL_47;
    case 0x20003:
      v6 = SymCryptMd2Append;
      v7 = (__int64 (__fastcall *)())SymCryptMd2Result;
      goto LABEL_3;
    case 0x20004:
      v6 = SymCryptMd4Append;
      v7 = (__int64 (__fastcall *)())SymCryptMd4Result;
LABEL_3:
      v8 = 112;
      goto LABEL_47;
    case 0x20005:
      v9 = SymCryptParallelSha256Process;
      v10 = 128;
      goto LABEL_11;
    case 0x20006:
      v9 = SymCryptParallelSha384Process;
      goto LABEL_10;
    case 0x20007:
      v9 = SymCryptParallelSha512Process;
LABEL_10:
      v10 = 224;
LABEL_11:
      v11 = 0;
      v12 = (__int64)a1 + v10 * (unsigned int)a1[11] + 128;
      v13 = 0;
      while ( 2 )
      {
        if ( !a3 )
          return v11;
LABEL_13:
        v14 = 5 * v13;
        *(_QWORD *)(v12 + 40 * v13) = *a2;
        if ( a2[1] == 1 )
        {
          *(_DWORD *)(v12 + 40 * v13 + 8) = 1;
          goto LABEL_18;
        }
        if ( a2[1] == 2 )
        {
          *(_DWORD *)(v12 + 40 * v13 + 8) = 2;
          if ( a2[4] == a1[3] )
          {
LABEL_18:
            ++v13;
            *(_QWORD *)(v12 + 8 * v14 + 16) = *((_QWORD *)a2 + 1);
            --a3;
            v15 = a2[4];
            a2 += 6;
            *(_QWORD *)(v12 + 8 * v14 + 24) = v15;
            v16 = (unsigned int)a1[11];
            if ( v13 == 2 * (_DWORD)v16 || !a3 )
            {
              ((void (__fastcall *)(_DWORD *, __int64, __int64))v9)(a1 + 32, v16, v12);
              v13 = 0;
              continue;
            }
            goto LABEL_13;
          }
        }
        return (unsigned int)-1073741811;
      }
    case 0x20009:
      v6 = SymCryptHmacSha1Append;
      v7 = (__int64 (__fastcall *)())SymCryptHmacSha1Result;
      v18 = (__int64 (__fastcall *)())SymCryptHmacSha1Init;
      goto LABEL_23;
    case 0x2000A:
      v8 = 128;
      v22 = (__int64 (__fastcall *)())SymCryptHmacMd5Init;
      v6 = (__int64 (__fastcall *)())&SymCryptHmacMd5Append;
      v23 = a1 + 32;
      v7 = (__int64 (__fastcall *)())SymCryptHmacMd5Result;
      v17 = a1 + 44;
      goto LABEL_48;
    case 0x2000B:
      v6 = SymCryptHmacSha256Append;
      v7 = (__int64 (__fastcall *)())SymCryptHmacSha256Result;
      v18 = (__int64 (__fastcall *)())SymCryptHmacSha256Init;
LABEL_23:
      v22 = v18;
      v17 = a1 + 52;
      v8 = 144;
      v23 = a1 + 32;
      goto LABEL_48;
    case 0x2000C:
      v6 = SymCryptHmacSha384Append;
      v7 = (__int64 (__fastcall *)())SymCryptHmacSha384Result;
      v19 = (__int64 (__fastcall *)())SymCryptHmacSha512Init;
      goto LABEL_26;
    case 0x2000D:
      v6 = (__int64 (__fastcall *)())SymCryptSha512_256Append;
      v7 = (__int64 (__fastcall *)())SymCryptHmacSha512Result;
      v19 = (__int64 (__fastcall *)())SymCryptHmacSha512Init;
LABEL_26:
      v17 = a1 + 68;
      goto LABEL_27;
    case 0x2000E:
      v8 = 64;
      v22 = SymCryptAesCmacInit;
      v6 = (__int64 (__fastcall *)())SymCryptAesCmacAppend;
      v23 = a1 + 32;
      v7 = (__int64 (__fastcall *)())SymCryptAesCmacResult;
      v17 = a1 + 168;
      goto LABEL_48;
    case 0x2000F:
      v6 = (__int64 (__fastcall *)())SymCryptSha3_256Append;
      v7 = (__int64 (__fastcall *)())SymCryptShake128Result;
      goto LABEL_46;
    case 0x20010:
      v6 = (__int64 (__fastcall *)())SymCryptSha3_256Append;
      v7 = (__int64 (__fastcall *)())SymCryptSha3_384Result;
      goto LABEL_46;
    case 0x20011:
      v6 = (__int64 (__fastcall *)())SymCryptSha3_256Append;
      v7 = (__int64 (__fastcall *)())SymCryptSha3_512Result;
      goto LABEL_46;
    case 0x20012:
      v6 = SymCryptHmacSha3_512Append;
      v7 = SymCryptHmacSha3_384Result;
      goto LABEL_35;
    case 0x20013:
      v6 = SymCryptHmacSha3_512Append;
      v7 = SymCryptHmacSha3_384Result;
      goto LABEL_35;
    case 0x20014:
      v6 = SymCryptHmacSha3_512Append;
      v7 = SymCryptHmacSha3_384Result;
LABEL_35:
      v22 = SymCryptHmacSha3_512Init;
      v17 = a1 + 160;
      v8 = 272;
      v23 = a1 + 32;
      goto LABEL_48;
    case 0x20015:
      v6 = (__int64 (__fastcall *)())SymCryptCShake256Append;
      v7 = SymCryptCShake128Result;
      goto LABEL_39;
    case 0x20016:
      v6 = (__int64 (__fastcall *)())SymCryptCShake256Append;
      v7 = SymCryptCShake256Result;
LABEL_39:
      v17 = a1 + 132;
      goto LABEL_28;
    case 0x20017:
      v6 = SymCryptKmac256Append;
      v7 = SymCryptKmac128Result;
      v19 = SymCryptKmac128Init;
      goto LABEL_42;
    case 0x20018:
      v6 = SymCryptKmac256Append;
      v7 = SymCryptKmac256Result;
      v19 = SymCryptKmac128Init;
LABEL_42:
      v17 = a1 + 136;
LABEL_27:
      v22 = v19;
      v23 = a1 + 32;
LABEL_28:
      v8 = 240;
      goto LABEL_48;
    case 0x20019:
      v6 = (__int64 (__fastcall *)())SymCryptSha3_256Append;
      v7 = (__int64 (__fastcall *)())SymCryptShake128Result;
      goto LABEL_46;
    case 0x2001A:
      v6 = (__int64 (__fastcall *)())SymCryptSha3_256Append;
      v7 = (__int64 (__fastcall *)())SymCryptSha3_512Result;
LABEL_46:
      v8 = 240;
LABEL_47:
      v17 = a1 + 32;
LABEL_48:
      v11 = 0;
      while ( 2 )
      {
        if ( !a3 )
          return v11;
        if ( *a2 >= a1[11] )
        {
          v20 = 1786;
        }
        else
        {
          if ( a2[1] == 1 )
          {
            ((void (__fastcall *)(char *, _QWORD, _QWORD))v6)((char *)v17 + v8 * *a2, *((_QWORD *)a2 + 1), a2[4]);
LABEL_57:
            a2 += 6;
            --a3;
            continue;
          }
          if ( a2[1] == 2 )
          {
            if ( a2[4] == a1[3] )
            {
              ((void (__fastcall *)(char *, _QWORD))v7)((char *)v17 + v8 * *a2, *((_QWORD *)a2 + 1));
              if ( v22 )
                ((void (__fastcall *)(char *, _DWORD *))v22)((char *)v17 + v8 * *a2, v23);
              goto LABEL_57;
            }
            v20 = 1800;
          }
          else
          {
            v20 = 1814;
          }
        }
        break;
      }
      v11 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v20);
      return v11;
    default:
      return (unsigned int)-1073741637;
  }
}

```

## disassembly

```asm
0x180065a50  mov     [rsp+arg_10], rbx
0x180065a55  push    rbp
0x180065a56  push    rsi
0x180065a57  push    rdi
0x180065a58  push    r12
0x180065a5a  push    r13
0x180065a5c  push    r14
0x180065a5e  push    r15
0x180065a60  sub     rsp, 40h
0x180065a64  mov     eax, [rcx+8]
0x180065a67  mov     esi, r8d
0x180065a6a  add     eax, 0FFFDFFFFh; switch 26 cases
0x180065a6f  mov     rdi, rdx
0x180065a72  mov     r14, rcx
0x180065a75  cmp     eax, 19h
0x180065a78  ja      def_180065AA2; jumptable 0000000180065AA2 default case, case 131080
0x180065a7e  xor     r8d, r8d
0x180065a81  lea     rcx, cs:180000000h
0x180065a88  mov     eax, ds:(jpt_180065AA2 - 180000000h)[rcx+rax*4]
0x180065a8f  add     rax, rcx
0x180065a92  mov     [rsp+78h+arg_0], r8
0x180065a9a  mov     [rsp+78h+arg_8], r8
0x180065aa2  jmp     rax; switch jump
0x180065aa8  lea     r13, SymCryptMd2Append; jumptable 0000000180065AA2 case 131075
0x180065aaf  lea     r12, SymCryptMd2Result
0x180065ab6  mov     ebx, 70h ; 'p'
0x180065abb  jmp     loc_180065E31
0x180065ac0  lea     r13, SymCryptMd4Append; jumptable 0000000180065AA2 case 131076
0x180065ac7  lea     r12, SymCryptMd4Result
0x180065ace  jmp     short loc_180065AB6
0x180065ad0  lea     r13, SymCryptHmacMd5Append; jumptable 0000000180065AA2 case 131073
0x180065ad7  lea     r12, SymCryptMd5Result
0x180065ade  jmp     short loc_180065AB6
0x180065ae0  lea     r13, SymCryptSha1Append; jumptable 0000000180065AA2 case 131074
0x180065ae7  mov     ebx, 80h
0x180065aec  lea     r12, SymCryptSha1Result
0x180065af3  jmp     loc_180065E31
0x180065af8  lea     r13, SymCryptParallelSha256Process; jumptable 0000000180065AA2 case 131077
0x180065aff  mov     ebx, 80h
0x180065b04  jmp     short loc_180065B1B
0x180065b06  lea     r13, SymCryptParallelSha384Process; jumptable 0000000180065AA2 case 131078
0x180065b0d  jmp     short loc_180065B16
0x180065b0f  lea     r13, SymCryptParallelSha512Process; jumptable 0000000180065AA2 case 131079
0x180065b16  mov     ebx, 0E0h
0x180065b1b  mov     eax, [r14+2Ch]
0x180065b1f  lea     r12, [r14+80h]
0x180065b26  mov     r15d, eax
0x180065b29  xor     ebp, ebp
0x180065b2b  imul    r15, rbx
0x180065b2f  mov     ebx, [r14]
0x180065b32  add     eax, eax
0x180065b34  add     r15, r12
0x180065b37  xor     r9d, r9d
0x180065b3a  lea     rax, [rax+rax*4]
0x180065b3e  lea     r8, [r15+rax*8]
0x180065b42  sub     rbx, r8
0x180065b45  mov     [rsp+78h+arg_0], r8
0x180065b4d  add     rbx, r14
0x180065b50  test    esi, esi
0x180065b52  jz      loc_180065F00
0x180065b58  mov     eax, [rdi]
0x180065b5a  lea     rdx, [r9+r9*4]
0x180065b5e  mov     [r15+rdx*8], rax
0x180065b62  mov     ecx, [rdi+4]
0x180065b65  sub     ecx, 1
0x180065b68  jz      short loc_180065B8B
0x180065b6a  cmp     ecx, 1
0x180065b6d  jnz     short loc_180065B81
0x180065b6f  mov     dword ptr [r15+rdx*8+8], 2
0x180065b78  mov     eax, [r14+0Ch]
0x180065b7c  cmp     [rdi+10h], eax
0x180065b7f  jz      short loc_180065B94
0x180065b81  mov     ebp, 0C000000Dh
0x180065b86  jmp     loc_180065F00
0x180065b8b  mov     dword ptr [r15+rdx*8+8], 1
0x180065b94  mov     rax, [rdi+8]
0x180065b98  inc     r9
0x180065b9b  mov     [r15+rdx*8+10h], rax
0x180065ba0  dec     esi
0x180065ba2  mov     eax, [rdi+10h]
0x180065ba5  add     rdi, 18h
0x180065ba9  mov     [r15+rdx*8+18h], rax
0x180065bae  mov     edx, [r14+2Ch]
0x180065bb2  lea     ecx, [rdx+rdx]
0x180065bb5  cmp     r9, rcx
0x180065bb8  jz      short loc_180065BBE
0x180065bba  test    esi, esi
0x180065bbc  jnz     short loc_180065B58
0x180065bbe  mov     [rsp+78h+var_50], rbx
0x180065bc3  mov     rcx, r12
0x180065bc6  mov     [rsp+78h+var_58], r8
0x180065bcb  mov     rax, r13
0x180065bce  mov     r8, r15
0x180065bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065bd6  mov     r8, [rsp+78h+arg_0]
0x180065bde  xor     r9d, r9d
0x180065be1  jmp     loc_180065B50
0x180065be6  lea     rax, SymCryptHmacMd5Init; jumptable 0000000180065AA2 case 131082
0x180065bed  mov     ebx, 80h
0x180065bf2  mov     [rsp+78h+arg_0], rax
0x180065bfa  lea     r13, SymCryptHmacMd5Append
0x180065c01  lea     rax, [r14+80h]
0x180065c08  mov     [rsp+78h+arg_8], rax
0x180065c10  lea     r12, SymCryptHmacMd5Result
0x180065c17  lea     r15, [r14+0B0h]
0x180065c1e  jmp     loc_180065E38
0x180065c23  lea     r13, SymCryptHmacSha1Append; jumptable 0000000180065AA2 case 131081
0x180065c2a  lea     r12, SymCryptHmacSha1Result
0x180065c31  lea     rax, SymCryptHmacSha1Init
0x180065c38  mov     [rsp+78h+arg_0], rax
0x180065c40  lea     r15, [r14+0D0h]
0x180065c47  lea     rax, [r14+80h]
0x180065c4e  mov     ebx, 90h
0x180065c53  mov     [rsp+78h+arg_8], rax
0x180065c5b  jmp     loc_180065E38
0x180065c60  lea     r13, SymCryptHmacSha256Append; jumptable 0000000180065AA2 case 131083
0x180065c67  lea     r12, SymCryptHmacSha256Result
0x180065c6e  lea     rax, SymCryptHmacSha256Init
0x180065c75  jmp     short loc_180065C38
0x180065c77  lea     r13, SymCryptHmacSha384Append; jumptable 0000000180065AA2 case 131084
0x180065c7e  lea     r12, SymCryptHmacSha384Result
0x180065c85  lea     rax, SymCryptHmacSha512Init
0x180065c8c  lea     r15, [r14+110h]
0x180065c93  mov     [rsp+78h+arg_0], rax
0x180065c9b  lea     rax, [r14+80h]
0x180065ca2  mov     [rsp+78h+arg_8], rax
0x180065caa  mov     ebx, 0F0h
0x180065caf  jmp     loc_180065E38
0x180065cb4  lea     r13, SymCryptSha512_256Append; jumptable 0000000180065AA2 case 131085
0x180065cbb  lea     r12, SymCryptHmacSha512Result
0x180065cc2  lea     rax, SymCryptHmacSha512Init
0x180065cc9  jmp     short loc_180065C8C
0x180065ccb  lea     rax, SymCryptAesCmacInit; jumptable 0000000180065AA2 case 131086
0x180065cd2  mov     ebx, 40h ; '@'
0x180065cd7  mov     [rsp+78h+arg_0], rax
0x180065cdf  lea     r13, SymCryptAesCmacAppend
0x180065ce6  lea     rax, [r14+80h]
0x180065ced  mov     [rsp+78h+arg_8], rax
0x180065cf5  lea     r12, SymCryptAesCmacResult
0x180065cfc  lea     r15, [r14+2A0h]
0x180065d03  jmp     loc_180065E38
0x180065d08  lea     r13, SymCryptSha3_256Append; jumptable 0000000180065AA2 case 131087
0x180065d0f  lea     r12, SymCryptShake128Result
0x180065d16  jmp     loc_180065E2C
0x180065d1b  lea     r13, SymCryptSha3_256Append; jumptable 0000000180065AA2 case 131088
0x180065d22  lea     r12, SymCryptSha3_384Result
0x180065d29  jmp     loc_180065E2C
0x180065d2e  lea     r13, SymCryptSha3_256Append; jumptable 0000000180065AA2 case 131089
0x180065d35  lea     r12, SymCryptSha3_512Result
0x180065d3c  jmp     loc_180065E2C
0x180065d41  lea     r13, SymCryptHmacSha3_512Append; jumptable 0000000180065AA2 case 131090
0x180065d48  lea     r12, SymCryptHmacSha3_384Result
0x180065d4f  lea     rax, SymCryptHmacSha3_512Init
0x180065d56  mov     [rsp+78h+arg_0], rax
0x180065d5e  lea     r15, [r14+280h]
0x180065d65  lea     rax, [r14+80h]
0x180065d6c  mov     ebx, 110h
0x180065d71  mov     [rsp+78h+arg_8], rax
0x180065d79  jmp     loc_180065E38
0x180065d7e  lea     r13, SymCryptHmacSha3_512Append; jumptable 0000000180065AA2 case 131091
0x180065d85  lea     r12, SymCryptHmacSha3_384Result
0x180065d8c  lea     rax, SymCryptHmacSha3_512Init
0x180065d93  jmp     short loc_180065D56
0x180065d95  lea     r13, SymCryptHmacSha3_512Append; jumptable 0000000180065AA2 case 131092
0x180065d9c  lea     r12, SymCryptHmacSha3_384Result
0x180065da3  lea     rax, SymCryptHmacSha3_512Init
0x180065daa  jmp     short loc_180065D56
0x180065dac  lea     r13, SymCryptCShake256Append; jumptable 0000000180065AA2 case 131093
0x180065db3  lea     r12, SymCryptCShake128Result
0x180065dba  lea     r15, [r14+210h]
0x180065dc1  jmp     loc_180065CAA
0x180065dc6  lea     r13, SymCryptCShake256Append; jumptable 0000000180065AA2 case 131094
0x180065dcd  lea     r12, SymCryptCShake256Result
0x180065dd4  jmp     short loc_180065DBA
0x180065dd6  lea     r13, SymCryptKmac256Append; jumptable 0000000180065AA2 case 131095
0x180065ddd  lea     r12, SymCryptKmac128Result
0x180065de4  lea     rax, SymCryptKmac128Init
0x180065deb  lea     r15, [r14+220h]
0x180065df2  jmp     loc_180065C93
0x180065df7  lea     r13, SymCryptKmac256Append; jumptable 0000000180065AA2 case 131096
0x180065dfe  lea     r12, SymCryptKmac256Result
0x180065e05  lea     rax, SymCryptKmac128Init
0x180065e0c  jmp     short loc_180065DEB
0x180065e0e  lea     r13, SymCryptSha3_256Append; jumptable 0000000180065AA2 case 131097
0x180065e15  lea     r12, SymCryptShake128Result
0x180065e1c  jmp     short loc_180065E2C
0x180065e1e  lea     r13, SymCryptSha3_256Append; jumptable 0000000180065AA2 case 131098
0x180065e25  lea     r12, SymCryptSha3_512Result
0x180065e2c  mov     ebx, 0F0h
0x180065e31  lea     r15, [r14+80h]
0x180065e38  xor     ebp, ebp
0x180065e3a  test    esi, esi
0x180065e3c  jz      loc_180065F00
0x180065e42  mov     edx, [rdi]
0x180065e44  cmp     edx, [r14+2Ch]
0x180065e48  jnb     loc_180065ED6
0x180065e4e  mov     ecx, [rdi+4]
0x180065e51  sub     ecx, 1
0x180065e54  jz      short loc_180065EA1
0x180065e56  cmp     ecx, 1
0x180065e59  jnz     short loc_180065ECE
0x180065e5b  mov     eax, [r14+0Ch]
0x180065e5f  cmp     [rdi+10h], eax
0x180065e62  jnz     short loc_180065EC6
0x180065e64  mov     ecx, edx
0x180065e66  mov     rax, r12
0x180065e69  mov     rdx, [rdi+8]
0x180065e6d  imul    rcx, rbx
0x180065e71  add     rcx, r15
0x180065e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e79  mov     r8, [rsp+78h+arg_0]
0x180065e81  test    r8, r8
0x180065e84  jz      short loc_180065EBB
0x180065e86  mov     ecx, [rdi]
0x180065e88  mov     rax, r8
0x180065e8b  mov     rdx, [rsp+78h+arg_8]
0x180065e93  imul    rcx, rbx
0x180065e97  add     rcx, r15
0x180065e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e9f  jmp     short loc_180065EBB
0x180065ea1  mov     r8d, [rdi+10h]
0x180065ea5  mov     rcx, rdx
0x180065ea8  mov     rdx, [rdi+8]
0x180065eac  mov     rax, r13
0x180065eaf  imul    rcx, rbx
0x180065eb3  add     rcx, r15
0x180065eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ebb  add     rdi, 18h
0x180065ebf  dec     esi
0x180065ec1  jmp     loc_180065E3A
0x180065ec6  mov     r9d, 708h
0x180065ecc  jmp     short loc_180065EDC
0x180065ece  mov     r9d, 716h
0x180065ed4  jmp     short loc_180065EDC
0x180065ed6  mov     r9d, 6FAh
0x180065edc  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180065ee3  mov     ecx, 0C000000Dh
0x180065ee8  lea     rdx, aStatus; "Status"
0x180065eef  mov     ebp, 0C000000Dh
0x180065ef4  call    DebugTraceError
0x180065ef9  jmp     short loc_180065F00
0x180065efb  mov     ebp, 0C00000BBh; jumptable 0000000180065AA2 default case, case 131080
0x180065f00  mov     rbx, [rsp+78h+arg_10]
0x180065f08  mov     eax, ebp
0x180065f0a  add     rsp, 40h
0x180065f0e  pop     r15
0x180065f10  pop     r14
0x180065f12  pop     r13
0x180065f14  pop     r12
0x180065f16  pop     rdi
0x180065f17  pop     rsi
0x180065f18  pop     rbp
0x180065f19  retn
```
