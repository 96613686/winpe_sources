# MSCryptGetAlgProperty

- ea: `0x180044eb0`
- end: `0x180045175`
- name: `MSCryptGetAlgProperty`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c040`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180044eb0`
- `0x18007f765`

## string_xrefs

- `0x180045087`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800450c4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800826b4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetAlgProperty(_DWORD *a1, const wchar_t *a2, int *a3, unsigned int a4, _DWORD *a5, char a6)
{
  unsigned int v10; // ebx
  __int64 result; // rax
  int v12; // ecx
  __int64 v13; // rax
  int v14; // edx
  int v15; // r8d
  int v16; // ecx
  int v17; // edx
  int v18; // eax
  int v19; // eax
  int v20; // ecx
  __int64 v21; // r9

  if ( !wcscmp_0(a2, L"ObjectLength") )
  {
    *a5 = 4;
    if ( !a3 )
      return 0;
    if ( a4 >= 4 )
    {
      *a3 = a1[7];
      return 0;
    }
    return (unsigned int)-1073741789;
  }
  if ( wcscmp_0(a2, L"KeyLengths") )
  {
    if ( !wcscmp_0(a2, L"BlockSizeList") )
    {
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( a4 >= 4 )
      {
        v10 = 0;
        *a3 = a1[4];
        return v10;
      }
      return (unsigned int)-1073741789;
    }
    if ( !wcscmp_0(a2, L"EffectiveKeyLength") )
    {
      if ( a1[2] == 65543 )
      {
        *a5 = 4;
        if ( !a3 )
          return 0;
        if ( a4 >= 4 )
        {
          v10 = 0;
          *a3 = a1[9];
          return v10;
        }
        return (unsigned int)-1073741789;
      }
      v21 = 2026;
    }
    else
    {
      if ( wcscmp_0(a2, L"AuthTagLength") )
      {
        v10 = -1073741637;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            v15,
            (unsigned int)"Status",
            187,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            69);
        return v10;
      }
      v16 = a1[2];
      if ( v16 == 65538 || v16 == 65545 )
      {
        if ( (unsigned int)(a1[3] - 4) <= 1 || v16 != 65538 )
        {
          v17 = 12;
          *a5 = 12;
          if ( !a3 )
            return 0;
          if ( a4 < 0xC )
            return (unsigned int)-1073741789;
          v18 = a1[3];
          if ( v18 == 4 )
          {
            v17 = 4;
            v19 = 16;
            v20 = 2;
          }
          else if ( v18 == 5 )
          {
            v19 = 16;
            v20 = 1;
          }
          else
          {
            v20 = 0;
            if ( a1[2] == 65545 )
            {
              v19 = 16;
              v17 = 16;
            }
            else
            {
              v17 = 0;
              v19 = 0;
            }
          }
          a3[1] = v19;
          result = 0;
          a3[2] = v20;
          *a3 = v17;
          return result;
        }
        v21 = 2070;
      }
      else
      {
        v21 = 2061;
      }
    }
    v10 = -1073741637;
    DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v21);
    return v10;
  }
  v12 = a1[2];
  *a5 = 12;
  if ( !a3 )
    return 0;
  if ( a4 < 0xC )
    return (unsigned int)-1073741789;
  v13 = (unsigned int)(unsigned __int16)v12 - 1;
  if ( (unsigned int)v13 >= 9 )
  {
    v10 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 1976);
    return v10;
  }
  *(_QWORD *)a3 = rgSymmAlgorithmDefaults[14 * v13 + 5];
  a3[2] = rgSymmAlgorithmDefaults[14 * v13 + 6];
  if ( a6 < 0 )
    a3[1] = HIDWORD(rgSymmAlgorithmDefaults[14 * v13 + 6]);
  a3[2] *= 8;
  a3[1] *= 8;
  *a3 *= 8;
  return 0;
}

```

## disassembly

```asm
0x180044eb0  push    rbx
0x180044eb2  push    rbp
0x180044eb3  push    rsi
0x180044eb4  push    rdi
0x180044eb5  sub     rsp, 48h
0x180044eb9  mov     rbx, rdx
0x180044ebc  mov     rbp, rcx
0x180044ebf  mov     rcx, rbx; String1
0x180044ec2  lea     rdx, aObjectlength; "ObjectLength"
0x180044ec9  mov     esi, r9d
0x180044ecc  mov     rdi, r8
0x180044ecf  call    wcscmp_0
0x180044ed4  test    eax, eax
0x180044ed6  jnz     short loc_180044F07
0x180044ed8  mov     rax, [rsp+68h+arg_20]
0x180044ee0  mov     dword ptr [rax], 4
0x180044ee6  test    rdi, rdi
0x180044ee9  jz      short loc_180044EF9
0x180044eeb  cmp     esi, 4
0x180044eee  jb      loc_1800450B4
0x180044ef4  mov     eax, [rbp+1Ch]
0x180044ef7  mov     [rdi], eax
0x180044ef9  xor     ebx, ebx
0x180044efb  mov     eax, ebx
0x180044efd  add     rsp, 48h
0x180044f01  pop     rdi
0x180044f02  pop     rsi
0x180044f03  pop     rbp
0x180044f04  pop     rbx
0x180044f05  retn
0x180044f07  lea     rdx, aKeylengths; "KeyLengths"
0x180044f0e  mov     rcx, rbx; String1
0x180044f11  call    wcscmp_0
0x180044f16  test    eax, eax
0x180044f18  jnz     short loc_180044F98
0x180044f1a  mov     rax, [rsp+68h+arg_20]
0x180044f22  mov     ecx, [rbp+8]
0x180044f25  mov     dword ptr [rax], 0Ch
0x180044f2b  test    rdi, rdi
0x180044f2e  jz      short loc_180044EF9
0x180044f30  cmp     esi, 0Ch
0x180044f33  jb      loc_1800450B4
0x180044f39  movzx   eax, cx
0x180044f3c  dec     eax
0x180044f3e  cmp     eax, 9
0x180044f41  jnb     loc_1800450BE
0x180044f47  imul    rcx, rax, 70h ; 'p'
0x180044f4b  test    [rsp+68h+arg_28], 80h
0x180044f53  lea     rdx, rgSymmAlgorithmDefaults
0x180044f5a  movsd   xmm0, qword ptr [rcx+rdx+28h]
0x180044f60  movsd   qword ptr [rdi], xmm0
0x180044f64  mov     eax, [rcx+rdx+30h]
0x180044f68  mov     [rdi+8], eax
0x180044f6b  jnz     loc_1800450E6
0x180044f71  mov     eax, [rdi+8]
0x180044f74  shl     eax, 3
0x180044f77  mov     [rdi+8], eax
0x180044f7a  mov     eax, [rdi+4]
0x180044f7d  shl     eax, 3
0x180044f80  mov     [rdi+4], eax
0x180044f83  mov     eax, [rdi]
0x180044f85  shl     eax, 3
0x180044f88  xor     ebx, ebx
0x180044f8a  mov     [rdi], eax
0x180044f8c  mov     eax, ebx
0x180044f8e  add     rsp, 48h
0x180044f92  pop     rdi
0x180044f93  pop     rsi
0x180044f94  pop     rbp
0x180044f95  pop     rbx
0x180044f96  retn
0x180044f98  lea     rdx, aBlocksizelist; "BlockSizeList"
0x180044f9f  mov     rcx, rbx; String1
0x180044fa2  call    wcscmp_0
0x180044fa7  test    eax, eax
0x180044fa9  jz      loc_1800450F2
0x180044faf  lea     rdx, aEffectivekeyle; "EffectiveKeyLength"
0x180044fb6  mov     rcx, rbx; String1
0x180044fb9  call    wcscmp_0
0x180044fbe  test    eax, eax
0x180044fc0  jz      loc_18004511A
0x180044fc6  lea     rdx, aAuthtaglength; "AuthTagLength"
0x180044fcd  mov     rcx, rbx; String1
0x180044fd0  call    wcscmp_0
0x180044fd5  test    eax, eax
0x180044fd7  jnz     loc_18004505D
0x180044fdd  mov     ecx, [rbp+8]
0x180044fe0  cmp     ecx, 10002h
0x180044fe6  jnz     loc_180045132
0x180044fec  mov     eax, [rbp+0Ch]
0x180044fef  sub     eax, 4
0x180044ff2  cmp     eax, 1
0x180044ff5  ja      loc_180045149
0x180044ffb  mov     rax, [rsp+68h+arg_20]
0x180045003  mov     edx, 0Ch
0x180045008  mov     [rax], edx
0x18004500a  test    rdi, rdi
0x18004500d  jz      loc_180044EF9
0x180045013  cmp     esi, edx
0x180045015  jb      loc_1800450B4
0x18004501b  mov     eax, [rbp+0Ch]
0x18004501e  xor     ebx, ebx
0x180045020  cmp     eax, 4
0x180045023  jz      short loc_18004504C
0x180045025  cmp     eax, 5
0x180045028  jnz     loc_18004515A
0x18004502e  mov     eax, 10h
0x180045033  mov     ecx, 1
0x180045038  mov     [rdi+4], eax
0x18004503b  mov     eax, ebx
0x18004503d  mov     [rdi+8], ecx
0x180045040  mov     [rdi], edx
0x180045042  add     rsp, 48h
0x180045046  pop     rdi
0x180045047  pop     rsi
0x180045048  pop     rbp
0x180045049  pop     rbx
0x18004504a  retn
0x18004504c  mov     edx, 4
0x180045051  mov     eax, 10h
0x180045056  mov     ecx, 2
0x18004505b  jmp     short loc_180045038
0x18004505d  mov     ebx, 0C00000BBh
0x180045062  mov     rcx, cs:WPP_GLOBAL_Control
0x180045069  lea     rax, WPP_GLOBAL_Control
0x180045070  cmp     rcx, rax
0x180045073  jz      loc_180044EFB
0x180045079  test    byte ptr [rcx+1Ch], 1
0x18004507d  jz      loc_180044EFB
0x180045083  mov     rcx, [rcx+10h]
0x180045087  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004508e  mov     [rsp+68h+var_38], 845h
0x180045096  lea     r9, aStatus; "Status"
0x18004509d  mov     [rsp+68h+var_40], rax
0x1800450a2  mov     [rsp+68h+var_48], 0C00000BBh
0x1800450aa  call    WPP_SF_sDsd
0x1800450af  jmp     loc_180044EFB
0x1800450b4  mov     ebx, 0C0000023h
0x1800450b9  jmp     loc_180044EFB
0x1800450be  mov     r9d, 7B8h
0x1800450c4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800450cb  lea     rdx, aStatus; "Status"
0x1800450d2  mov     ecx, 0C0000008h
0x1800450d7  mov     ebx, 0C0000008h
0x1800450dc  call    DebugTraceError
0x1800450e1  jmp     loc_180044EFB
0x1800450e6  mov     eax, [rcx+rdx+34h]
0x1800450ea  mov     [rdi+4], eax
0x1800450ed  jmp     loc_180044F71
0x1800450f2  mov     rax, [rsp+68h+arg_20]
0x1800450fa  mov     dword ptr [rax], 4
0x180045100  test    rdi, rdi
0x180045103  jz      loc_180044EF9
0x180045109  cmp     esi, 4
0x18004510c  jb      short loc_1800450B4
0x18004510e  mov     eax, [rbp+10h]
0x180045111  xor     ebx, ebx
0x180045113  mov     [rdi], eax
0x180045115  jmp     loc_180044EFB
0x18004511a  cmp     dword ptr [rbp+8], 10007h
0x180045121  jz      loc_1800826D7
0x180045127  mov     r9d, 7EAh
0x18004512d  jmp     loc_1800826B4
0x180045132  cmp     ecx, 10009h
0x180045138  jz      loc_180044FEC
0x18004513e  mov     r9d, 80Dh
0x180045144  jmp     loc_1800826B4
0x180045149  cmp     ecx, 10002h
0x18004514f  jnz     loc_180044FFB
0x180045155  jmp     loc_1800826AE
0x18004515a  cmp     dword ptr [rbp+8], 10009h
0x180045161  mov     ecx, ebx
0x180045163  jnz     loc_180082703
0x180045169  mov     eax, 10h
0x18004516e  mov     edx, eax
0x180045170  jmp     loc_180045038
0x1800826ae  mov     r9d, 816h
0x1800826b4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800826bb  mov     ecx, 0C00000BBh
0x1800826c0  lea     rdx, aStatus; "Status"
0x1800826c7  mov     ebx, 0C00000BBh
0x1800826cc  call    DebugTraceError
0x1800826d1  nop
0x1800826d2  jmp     loc_180044EFB
0x1800826d7  mov     rax, [rsp+68h+arg_20]
0x1800826df  mov     dword ptr [rax], 4
0x1800826e5  test    rdi, rdi
0x1800826e8  jz      loc_180044EF9
0x1800826ee  cmp     esi, 4
0x1800826f1  jb      loc_1800450B4
0x1800826f7  mov     eax, [rbp+24h]
0x1800826fa  xor     ebx, ebx
0x1800826fc  mov     [rdi], eax
0x1800826fe  jmp     loc_180044EFB
0x180082703  mov     edx, ebx
0x180082705  mov     eax, ebx
0x180082707  jmp     loc_180045038
```
