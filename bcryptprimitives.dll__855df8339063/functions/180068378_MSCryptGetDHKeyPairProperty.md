# MSCryptGetDHKeyPairProperty

- ea: `0x180068378`
- end: `0x180068597`
- name: `MSCryptGetDHKeyPairProperty`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800685a0`

## callees

- `0x18000ecb0`
- `0x1800525dc`
- `0x180056cf0`
- `0x180058204`
- `0x180067f48`
- `0x180068378`
- `0x18007f765`

## string_xrefs

- `0x18006856c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptGetDHKeyPairProperty(
        __int64 a1,
        const wchar_t *a2,
        _DWORD *a3,
        unsigned int a4,
        _DWORD *a5,
        int a6)
{
  _DWORD *v9; // r14
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int Value; // eax
  int v18; // [rsp+40h] [rbp-38h]
  __int64 v19; // [rsp+80h] [rbp+8h] BYREF

  v19 = 0;
  if ( !a1 || !a2 || (v9 = a5) == 0 || a6 )
  {
    v11 = -1073741811;
    v12 = 473;
    v13 = 3221225485LL;
    goto LABEL_25;
  }
  v10 = ValidateDHKey(a1, 0, &v19);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 480;
LABEL_7:
    v13 = (unsigned int)v10;
LABEL_25:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v12);
    return v11;
  }
  if ( !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"KeyStrength") || !wcscmp_0(a2, L"PublicKeyLength") )
  {
    *v9 = 4;
    if ( !a3 )
      return v11;
    if ( a4 >= 4 )
    {
      *a3 = 8 * *(_DWORD *)(v19 + 12);
      return v11;
    }
    return (unsigned int)-1073741789;
  }
  if ( !wcscmp_0(a2, L"DHParameters") || !wcscmp_0(a2, L"SecretAgreementParam") )
    return (unsigned int)GetDHGroupParam(v19, a3, a4, v9);
  if ( wcscmp_0(a2, L"DhQParameter") )
  {
    v11 = -1073741637;
    v12 = 572;
    v13 = 3221225659LL;
    goto LABEL_25;
  }
  v14 = v19;
  v15 = *(unsigned int *)(*(_QWORD *)(v19 + 24) + 28LL);
  *v9 = 8 * v15;
  if ( a3 )
  {
    if ( a4 >= 8 * (int)v15 )
    {
      Value = SymCryptDlgroupGetValue(*(_QWORD *)(v14 + 24), 0, 0, (int)a3, v15, 0, 0, 1, v18, 0, 0, 0);
      if ( Value )
      {
        v10 = SymcryptErrorCodeToNtStatus(Value);
        v11 = v10;
        v12 = 565;
        goto LABEL_7;
      }
      return v11;
    }
    return (unsigned int)-1073741789;
  }
  return v11;
}

```

## disassembly

```asm
0x180068378  mov     rax, rsp
0x18006837b  mov     [rax+10h], rbx
0x18006837f  mov     [rax+18h], rbp
0x180068383  push    rsi
0x180068384  push    rdi
0x180068385  push    r14
0x180068387  sub     rsp, 60h
0x18006838b  mov     qword ptr [rax+8], 0
0x180068393  mov     ebp, r9d
0x180068396  mov     rsi, r8
0x180068399  mov     rdi, rdx
0x18006839c  test    rcx, rcx
0x18006839f  jz      loc_18006855C
0x1800683a5  test    rdx, rdx
0x1800683a8  jz      loc_18006855C
0x1800683ae  mov     r14, [rsp+78h+arg_20]
0x1800683b6  test    r14, r14
0x1800683b9  jz      loc_18006855C
0x1800683bf  cmp     [rsp+78h+arg_28], 0
0x1800683c7  jnz     loc_18006855C
0x1800683cd  lea     r8, [rax+8]
0x1800683d1  xor     edx, edx
0x1800683d3  call    ValidateDHKey
0x1800683d8  mov     ebx, eax
0x1800683da  test    eax, eax
0x1800683dc  jns     short loc_1800683EB
0x1800683de  mov     r9d, 1E0h
0x1800683e4  mov     ecx, eax
0x1800683e6  jmp     loc_18006856C
0x1800683eb  lea     rdx, aKeylength; "KeyLength"
0x1800683f2  mov     rcx, rdi; String1
0x1800683f5  call    wcscmp_0
0x1800683fa  test    eax, eax
0x1800683fc  jz      loc_180068532
0x180068402  lea     rdx, aKeystrength; "KeyStrength"
0x180068409  mov     rcx, rdi; String1
0x18006840c  call    wcscmp_0
0x180068411  test    eax, eax
0x180068413  jz      loc_180068532
0x180068419  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x180068420  mov     rcx, rdi; String1
0x180068423  call    wcscmp_0
0x180068428  test    eax, eax
0x18006842a  jz      loc_180068532
0x180068430  lea     rdx, aDhparameters; "DHParameters"
0x180068437  mov     rcx, rdi; String1
0x18006843a  call    wcscmp_0
0x18006843f  test    eax, eax
0x180068441  jz      loc_180068518
0x180068447  lea     rdx, aSecretagreemen; "SecretAgreementParam"
0x18006844e  mov     rcx, rdi; String1
0x180068451  call    wcscmp_0
0x180068456  test    eax, eax
0x180068458  jz      loc_180068518
0x18006845e  lea     rdx, aDhqparameter; "DhQParameter"
0x180068465  mov     rcx, rdi; String1
0x180068468  call    wcscmp_0
0x18006846d  test    eax, eax
0x18006846f  jnz     loc_180068506
0x180068475  mov     rcx, [rsp+78h+arg_0]
0x18006847d  mov     rax, [rcx+18h]
0x180068481  mov     edx, [rax+1Ch]
0x180068484  lea     eax, ds:0[rdx*8]
0x18006848b  mov     [r14], eax
0x18006848e  test    rsi, rsi
0x180068491  jz      loc_18006857F
0x180068497  cmp     ebp, eax
0x180068499  jb      loc_180068543
0x18006849f  mov     rcx, [rcx+18h]; int
0x1800684a3  mov     r9, rsi; int
0x1800684a6  mov     [rsp+78h+var_20], 0; __int64
0x1800684af  xor     r8d, r8d; int
0x1800684b2  mov     [rsp+78h+var_28], 0; __int64
0x1800684bb  mov     [rsp+78h+var_30], 0; void *
0x1800684c4  mov     [rsp+78h+var_40], 1; int
0x1800684cc  mov     [rsp+78h+var_48], 0; __int64
0x1800684d5  mov     [rsp+78h+var_50], 0; __int64
0x1800684de  mov     [rsp+78h+var_58], rdx; __int64
0x1800684e3  xor     edx, edx; int
0x1800684e5  call    SymCryptDlgroupGetValue
0x1800684ea  test    eax, eax
0x1800684ec  jz      loc_18006857F
0x1800684f2  mov     ecx, eax
0x1800684f4  call    SymcryptErrorCodeToNtStatus
0x1800684f9  mov     ebx, eax
0x1800684fb  mov     r9d, 235h
0x180068501  jmp     loc_1800683E4
0x180068506  mov     ebx, 0C00000BBh
0x18006850b  mov     r9d, 23Ch
0x180068511  mov     ecx, 0C00000BBh
0x180068516  jmp     short loc_18006856C
0x180068518  mov     rcx, [rsp+78h+arg_0]
0x180068520  mov     r9, r14
0x180068523  mov     r8d, ebp
0x180068526  mov     rdx, rsi
0x180068529  call    GetDHGroupParam
0x18006852e  mov     ebx, eax
0x180068530  jmp     short loc_18006857F
0x180068532  mov     dword ptr [r14], 4
0x180068539  test    rsi, rsi
0x18006853c  jz      short loc_18006857F
0x18006853e  cmp     ebp, 4
0x180068541  jnb     short loc_18006854A
0x180068543  mov     ebx, 0C0000023h
0x180068548  jmp     short loc_18006857F
0x18006854a  mov     rax, [rsp+78h+arg_0]
0x180068552  mov     ecx, [rax+0Ch]
0x180068555  shl     ecx, 3
0x180068558  mov     [rsi], ecx
0x18006855a  jmp     short loc_18006857F
0x18006855c  mov     ebx, 0C000000Dh
0x180068561  mov     r9d, 1D9h
0x180068567  mov     ecx, 0C000000Dh
0x18006856c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068573  lea     rdx, aStatus; "Status"
0x18006857a  call    DebugTraceError
0x18006857f  lea     r11, [rsp+78h+var_18]
0x180068584  mov     eax, ebx
0x180068586  mov     rbx, [r11+28h]
0x18006858a  mov     rbp, [r11+30h]
0x18006858e  mov     rsp, r11
0x180068591  pop     r14
0x180068593  pop     rdi
0x180068594  pop     rsi
0x180068595  retn
```
