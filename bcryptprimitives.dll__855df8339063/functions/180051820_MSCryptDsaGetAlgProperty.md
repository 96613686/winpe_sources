# MSCryptDsaGetAlgProperty

- ea: `0x180051820`
- end: `0x180051966`
- name: `MSCryptDsaGetAlgProperty`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180069b40`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180051820`
- `0x180052794`
- `0x18007f765`

## string_xrefs

- `0x1800518a0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x180051926`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaGetAlgProperty(
        __int64 a1,
        const wchar_t *a2,
        _DWORD *a3,
        unsigned int a4,
        _DWORD *a5,
        int a6)
{
  _DWORD *v9; // rsi
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v15; // [rsp+40h] [rbp-28h] BYREF
  int v16; // [rsp+70h] [rbp+8h] BYREF

  v15 = 0;
  v16 = 0;
  if ( a1 && a2 && (v9 = a5) != 0 && !a6 )
  {
    v10 = ValidateDSAAlgorithm(a1, 0, &v16, &v15);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = 343;
      v13 = (unsigned int)v10;
LABEL_7:
      DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v12);
      return v11;
    }
    if ( wcscmp_0(a2, L"KeyLengths") )
    {
      v11 = -1073741637;
      v12 = 379;
      v13 = 3221225659LL;
      goto LABEL_7;
    }
    *v9 = 12;
    if ( a3 )
    {
      if ( a4 >= 0xC )
      {
        *a3 = 512;
        a3[1] = 3072;
        a3[2] = 64;
      }
      else
      {
        return (unsigned int)-1073741789;
      }
    }
  }
  else
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c",
        77);
  }
  return v11;
}

```

## disassembly

```asm
0x180051820  mov     rax, rsp
0x180051823  mov     [rax+10h], rbx
0x180051827  mov     [rax+18h], rbp
0x18005182b  push    rsi
0x18005182c  push    rdi
0x18005182d  push    r14
0x18005182f  sub     rsp, 50h
0x180051833  mov     qword ptr [rax-28h], 0
0x18005183b  mov     r14d, r9d
0x18005183e  mov     dword ptr [rax+8], 0
0x180051845  mov     rdi, r8
0x180051848  mov     rbp, rdx
0x18005184b  test    rcx, rcx
0x18005184e  jz      loc_180051904
0x180051854  test    rdx, rdx
0x180051857  jz      loc_180051904
0x18005185d  mov     rsi, [rsp+68h+arg_20]
0x180051865  test    rsi, rsi
0x180051868  jz      loc_180051904
0x18005186e  cmp     [rsp+68h+arg_28], 0
0x180051876  jnz     loc_180051904
0x18005187c  lea     r9, [rax-28h]
0x180051880  xor     edx, edx
0x180051882  lea     r8, [rax+8]
0x180051886  call    ValidateDSAAlgorithm
0x18005188b  mov     ebx, eax
0x18005188d  test    eax, eax
0x18005188f  jns     short loc_1800518B1
0x180051891  mov     r9d, 157h
0x180051897  mov     ecx, eax
0x180051899  lea     rdx, aStatus; "Status"
0x1800518a0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800518a7  call    DebugTraceError
0x1800518ac  jmp     loc_18005194E
0x1800518b1  lea     rdx, aKeylengths; "KeyLengths"
0x1800518b8  mov     rcx, rbp; String1
0x1800518bb  call    wcscmp_0
0x1800518c0  test    eax, eax
0x1800518c2  jnz     short loc_1800518F2
0x1800518c4  mov     dword ptr [rsi], 0Ch
0x1800518ca  test    rdi, rdi
0x1800518cd  jz      short loc_18005194E
0x1800518cf  cmp     r14d, 0Ch
0x1800518d3  jnb     short loc_1800518DC
0x1800518d5  mov     ebx, 0C0000023h
0x1800518da  jmp     short loc_18005194E
0x1800518dc  mov     dword ptr [rdi], 200h
0x1800518e2  mov     dword ptr [rdi+4], 0C00h
0x1800518e9  mov     dword ptr [rdi+8], 40h ; '@'
0x1800518f0  jmp     short loc_18005194E
0x1800518f2  mov     ebx, 0C00000BBh
0x1800518f7  mov     r9d, 17Bh
0x1800518fd  mov     ecx, 0C00000BBh
0x180051902  jmp     short loc_180051899
0x180051904  mov     ebx, 0C000000Dh
0x180051909  mov     rcx, cs:WPP_GLOBAL_Control
0x180051910  lea     rax, WPP_GLOBAL_Control
0x180051917  cmp     rcx, rax
0x18005191a  jz      short loc_18005194E
0x18005191c  test    byte ptr [rcx+1Ch], 1
0x180051920  jz      short loc_18005194E
0x180051922  mov     rcx, [rcx+10h]
0x180051926  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005192d  mov     [rsp+68h+var_38], 14Dh
0x180051935  lea     r9, aStatus; "Status"
0x18005193c  mov     [rsp+68h+var_40], rax
0x180051941  mov     [rsp+68h+var_48], 0C000000Dh
0x180051949  call    WPP_SF_sDsd
0x18005194e  lea     r11, [rsp+68h+var_18]
0x180051953  mov     eax, ebx
0x180051955  mov     rbx, [r11+28h]
0x180051959  mov     rbp, [r11+30h]
0x18005195d  mov     rsp, r11
0x180051960  pop     r14
0x180051962  pop     rdi
0x180051963  pop     rsi
0x180051964  retn
```
