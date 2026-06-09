# sub_1409EBFD4

- ea: `0x1409ebfd4`
- end: `0x1409ec28c`
- name: `sub_1409EBFD4`
- size: `696`
- prototype: `__int64 __fastcall(int, int, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140a12910`

## callees

- `0x140117c34`
- `0x1408bb2c4`
- `0x1408fe130`
- `0x1409e5d6c`
- `0x1409ebfd4`
- `0x1409ec290`
- `0x1409ec2b4`

## import_xrefs

- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1409ec078`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x1409ec078`
- `OLEAUT32!SysFreeString` at `0x1409ec10a`
- `OLEAUT32!SysFreeString` at `0x1409ec1c1`
- `OLEAUT32!SysFreeString` at `0x1409ec21c`
- `OLEAUT32!SysFreeString` at `0x1409ec233`
- `OLEAUT32!SysFreeString` at `0x1409ec10a`
- `OLEAUT32!SysFreeString` at `0x1409ec1c1`
- `OLEAUT32!SysFreeString` at `0x1409ec21c`
- `OLEAUT32!SysFreeString` at `0x1409ec233`
- `OLEAUT32!SafeArrayCreate` at `0x1409ec012`
- `OLEAUT32!SafeArrayCreate` at `0x1409ec012`
- `OLEAUT32!SafeArrayDestroy` at `0x1409ec144`
- `OLEAUT32!SafeArrayDestroy` at `0x1409ec266`
- `OLEAUT32!SafeArrayDestroy` at `0x1409ec144`
- `OLEAUT32!SafeArrayDestroy` at `0x1409ec266`
- `OLEAUT32!SafeArrayAccessData` at `0x1409ec069`
- `OLEAUT32!SafeArrayAccessData` at `0x1409ec069`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1409ec087`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1409ec119`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1409ec242`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1409ec087`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1409ec119`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1409ec242`

## pseudocode

```c
__int64 __fastcall sub_1409EBFD4(int a1, int a2, __int64 a3, int a4, __int64 a5, __int64 a6)
{
  SAFEARRAY *v10; // rax
  int v11; // edx
  int v12; // r9d
  SAFEARRAY *v13; // rbx
  int v15; // edx
  int v16; // r9d
  __int64 v17; // rax
  int v18; // edx
  int v19; // r9d
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // [rsp+30h] [rbp-40h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-38h] BYREF
  BSTR v24; // [rsp+40h] [rbp-30h] BYREF
  SAFEARRAY *psa; // [rsp+48h] [rbp-28h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-20h] BYREF
  void *ppvData[2]; // [rsp+58h] [rbp-18h] BYREF

  rgsabound = (SAFEARRAYBOUND)5LL;
  v10 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  psa = v10;
  v13 = v10;
  if ( !v10 )
  {
    v22 = -2147024882;
    sub_1409E5D6C(37524357, v11, 15, v12, (__int64)L"SetHrRet 0x%x", &v22);
    return (unsigned int)v22;
  }
  ppvData[0] = v10;
  ppvData[1] = 0;
  if ( SafeArrayAccessData(v10, &ppvData[1]) < 0 )
  {
    Mso20Win32Client_7228(528089233);
    if ( ppvData[0] )
      SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
    *(_OWORD *)ppvData = 0;
  }
  bstrString = 0;
  *(_WORD *)ppvData[1] = 3;
  *((_DWORD *)ppvData[1] + 2) = a1;
  *((_WORD *)ppvData[1] + 12) = 3;
  *((_DWORD *)ppvData[1] + 8) = a2;
  v22 = sub_1408FE130(&bstrString, a3);
  if ( v22 < 0 )
  {
    sub_1409E5D6C(37524361, v15, 15, v16, (__int64)L"IfFailRet 0x%x", &v22);
LABEL_10:
    if ( !(unsigned __int8)unknown_libname_9(&bstrString) )
      SysFreeString(bstrString);
    if ( ppvData[0] )
      SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
    *(_OWORD *)ppvData = 0;
    if ( !(unsigned __int8)unknown_libname_9(&psa) )
    {
      if ( v13 )
        SafeArrayDestroy(v13);
    }
    return (unsigned int)v22;
  }
  *((_WORD *)ppvData[1] + 24) = 8;
  v17 = sub_1408BB2C4(&bstrString);
  v24 = 0;
  *((_QWORD *)ppvData[1] + 7) = v17;
  v22 = sub_1409EC290(a5, &v24);
  if ( v22 < 0 )
  {
    sub_1409E5D6C(37524363, v18, 15, v19, (__int64)L"IfFailRet 0x%x", &v22);
    if ( !(unsigned __int8)unknown_libname_9(&v24) )
      SysFreeString(v24);
    goto LABEL_10;
  }
  *((_WORD *)ppvData[1] + 36) = 8;
  v20 = sub_1408BB2C4(&v24);
  *((_QWORD *)ppvData[1] + 10) = v20;
  *((_WORD *)ppvData[1] + 48) = 3;
  *((_DWORD *)ppvData[1] + 26) = a4;
  v21 = sub_1408BB2C4(&psa);
  sub_1409EC2B4(a6, v21);
  if ( !(unsigned __int8)unknown_libname_9(&v24) )
    SysFreeString(v24);
  if ( !(unsigned __int8)unknown_libname_9(&bstrString) )
    SysFreeString(bstrString);
  if ( ppvData[0] )
    SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
  *(_OWORD *)ppvData = 0;
  if ( !(unsigned __int8)unknown_libname_9(&psa) && psa )
    SafeArrayDestroy(psa);
  return 0;
}

```

## disassembly

```asm
0x1409ebfd4  mov     rax, rsp
0x1409ebfd7  mov     [rax+8], rbx
0x1409ebfdb  mov     [rax+10h], rsi
0x1409ebfdf  mov     [rax+18h], rdi
0x1409ebfe3  mov     [rax+20h], r13
0x1409ebfe7  push    rbp
0x1409ebfe8  push    r14
0x1409ebfea  push    r15
0x1409ebfec  mov     rbp, rsp
0x1409ebfef  sub     rsp, 70h
0x1409ebff3  mov     r14d, ecx
0x1409ebff6  mov     qword ptr [rbp+rgsabound.cElements], 5
0x1409ebffe  mov     ecx, 0Ch; vt
0x1409ec003  mov     rdi, r8
0x1409ec006  mov     esi, edx
0x1409ec008  lea     r8, [rbp+rgsabound]; rgsabound
0x1409ec00c  mov     r15d, r9d
0x1409ec00f  lea     edx, [rcx-0Bh]; cDims
0x1409ec012  call    cs:SafeArrayCreate
0x1409ec018  mov     [rbp+psa], rax
0x1409ec01c  mov     rbx, rax
0x1409ec01f  test    rax, rax
0x1409ec022  jnz     short loc_1409EC056
0x1409ec024  lea     rax, [rbp+var_40]
0x1409ec028  mov     [rbp+var_40], 8007000Eh
0x1409ec02f  mov     [rsp+70h+var_48], rax
0x1409ec034  lea     r8d, [rbx+0Fh]
0x1409ec038  lea     rax, aSethrret0xX; "SetHrRet 0x%x"
0x1409ec03f  mov     ecx, 23C9385h
0x1409ec044  mov     [rsp+70h+var_50], rax
0x1409ec049  call    sub_1409E5D6C
0x1409ec04e  mov     eax, [rbp+var_40]
0x1409ec051  jmp     loc_1409EC26E
0x1409ec056  lea     rdx, [rbp+ppvData+8]; ppvData
0x1409ec05a  mov     [rbp+ppvData], rbx
0x1409ec05e  mov     rcx, rbx; psa
0x1409ec061  mov     [rbp+ppvData+8], 0
0x1409ec069  call    cs:SafeArrayAccessData
0x1409ec06f  test    eax, eax
0x1409ec071  jns     short loc_1409EC095
0x1409ec073  mov     ecx, 1F7A0091h
0x1409ec078  call    cs:Mso20Win32Client_7228
0x1409ec07e  mov     rcx, [rbp+ppvData]; psa
0x1409ec082  test    rcx, rcx
0x1409ec085  jz      short loc_1409EC08D
0x1409ec087  call    cs:SafeArrayUnaccessData
0x1409ec08d  xorps   xmm0, xmm0
0x1409ec090  movdqu  xmmword ptr [rbp+ppvData], xmm0
0x1409ec095  mov     rax, [rbp+ppvData+8]
0x1409ec099  lea     rcx, [rbp+bstrString]
0x1409ec09d  mov     r13d, 3
0x1409ec0a3  mov     [rbp+bstrString], 0
0x1409ec0ab  mov     rdx, rdi
0x1409ec0ae  mov     [rax], r13w
0x1409ec0b2  mov     rax, [rbp+ppvData+8]
0x1409ec0b6  mov     [rax+8], r14d
0x1409ec0ba  mov     rax, [rbp+ppvData+8]
0x1409ec0be  mov     [rax+18h], r13w
0x1409ec0c3  mov     rax, [rbp+ppvData+8]
0x1409ec0c7  mov     [rax+20h], esi
0x1409ec0ca  call    sub_1408FE130
0x1409ec0cf  mov     [rbp+var_40], eax
0x1409ec0d2  test    eax, eax
0x1409ec0d4  jns     short loc_1409EC14F
0x1409ec0d6  lea     rax, [rbp+var_40]
0x1409ec0da  mov     ecx, 23C9389h
0x1409ec0df  mov     [rsp+70h+var_48], rax
0x1409ec0e4  lea     r8d, [r13+0Ch]
0x1409ec0e8  lea     rax, aIffailret0xX; "IfFailRet 0x%x"
0x1409ec0ef  mov     [rsp+70h+var_50], rax
0x1409ec0f4  call    sub_1409E5D6C
0x1409ec0f9  lea     rcx, [rbp+bstrString]
0x1409ec0fd  call    unknown_libname_9; Microsoft VisualC v14 64bit runtime
0x1409ec102  test    al, al
0x1409ec104  jnz     short loc_1409EC110
0x1409ec106  mov     rcx, [rbp+bstrString]; bstrString
0x1409ec10a  call    cs:SysFreeString
0x1409ec110  mov     rcx, [rbp+ppvData]; psa
0x1409ec114  test    rcx, rcx
0x1409ec117  jz      short loc_1409EC11F
0x1409ec119  call    cs:SafeArrayUnaccessData
0x1409ec11f  xorps   xmm0, xmm0
0x1409ec122  lea     rcx, [rbp+psa]
0x1409ec126  movdqu  xmmword ptr [rbp+ppvData], xmm0
0x1409ec12b  call    unknown_libname_9; Microsoft VisualC v14 64bit runtime
0x1409ec130  test    al, al
0x1409ec132  jnz     loc_1409EC04E
0x1409ec138  test    rbx, rbx
0x1409ec13b  jz      loc_1409EC04E
0x1409ec141  mov     rcx, rbx; psa
0x1409ec144  call    cs:SafeArrayDestroy
0x1409ec14a  jmp     loc_1409EC04E
0x1409ec14f  mov     rax, [rbp+ppvData+8]
0x1409ec153  lea     rcx, [rbp+bstrString]
0x1409ec157  mov     edi, 8
0x1409ec15c  mov     [rax+30h], di
0x1409ec160  call    sub_1408BB2C4
0x1409ec165  mov     rcx, [rbp+ppvData+8]
0x1409ec169  lea     rdx, [rbp+var_30]
0x1409ec16d  mov     [rbp+var_30], 0
0x1409ec175  mov     [rcx+38h], rax
0x1409ec179  mov     rcx, [rbp+arg_20]
0x1409ec17d  call    sub_1409EC290
0x1409ec182  mov     [rbp+var_40], eax
0x1409ec185  test    eax, eax
0x1409ec187  jns     short loc_1409EC1CC
0x1409ec189  lea     rax, [rbp+var_40]
0x1409ec18d  mov     ecx, 23C938Bh
0x1409ec192  mov     [rsp+70h+var_48], rax
0x1409ec197  lea     r8d, [rdi+7]
0x1409ec19b  lea     rax, aIffailret0xX; "IfFailRet 0x%x"
0x1409ec1a2  mov     [rsp+70h+var_50], rax
0x1409ec1a7  call    sub_1409E5D6C
0x1409ec1ac  lea     rcx, [rbp+var_30]
0x1409ec1b0  call    unknown_libname_9; Microsoft VisualC v14 64bit runtime
0x1409ec1b5  test    al, al
0x1409ec1b7  jnz     loc_1409EC0F9
0x1409ec1bd  mov     rcx, [rbp+var_30]; bstrString
0x1409ec1c1  call    cs:SysFreeString
0x1409ec1c7  jmp     loc_1409EC0F9
0x1409ec1cc  mov     rax, [rbp+ppvData+8]
0x1409ec1d0  lea     rcx, [rbp+var_30]
0x1409ec1d4  mov     [rax+48h], di
0x1409ec1d8  call    sub_1408BB2C4
0x1409ec1dd  mov     rcx, [rbp+ppvData+8]
0x1409ec1e1  mov     [rcx+50h], rax
0x1409ec1e5  lea     rcx, [rbp+psa]
0x1409ec1e9  mov     rax, [rbp+ppvData+8]
0x1409ec1ed  mov     [rax+60h], r13w
0x1409ec1f2  mov     rax, [rbp+ppvData+8]
0x1409ec1f6  mov     [rax+68h], r15d
0x1409ec1fa  call    sub_1408BB2C4
0x1409ec1ff  mov     rcx, [rbp+arg_28]
0x1409ec203  mov     rdx, rax
0x1409ec206  call    sub_1409EC2B4
0x1409ec20b  lea     rcx, [rbp+var_30]
0x1409ec20f  call    unknown_libname_9; Microsoft VisualC v14 64bit runtime
0x1409ec214  test    al, al
0x1409ec216  jnz     short loc_1409EC222
0x1409ec218  mov     rcx, [rbp+var_30]; bstrString
0x1409ec21c  call    cs:SysFreeString
0x1409ec222  lea     rcx, [rbp+bstrString]
0x1409ec226  call    unknown_libname_9; Microsoft VisualC v14 64bit runtime
0x1409ec22b  test    al, al
0x1409ec22d  jnz     short loc_1409EC239
0x1409ec22f  mov     rcx, [rbp+bstrString]; bstrString
0x1409ec233  call    cs:SysFreeString
0x1409ec239  mov     rcx, [rbp+ppvData]; psa
0x1409ec23d  test    rcx, rcx
0x1409ec240  jz      short loc_1409EC248
0x1409ec242  call    cs:SafeArrayUnaccessData
0x1409ec248  xorps   xmm0, xmm0
0x1409ec24b  lea     rcx, [rbp+psa]
0x1409ec24f  movdqu  xmmword ptr [rbp+ppvData], xmm0
0x1409ec254  call    unknown_libname_9; Microsoft VisualC v14 64bit runtime
0x1409ec259  test    al, al
0x1409ec25b  jnz     short loc_1409EC26C
0x1409ec25d  mov     rcx, [rbp+psa]; psa
0x1409ec261  test    rcx, rcx
0x1409ec264  jz      short loc_1409EC26C
0x1409ec266  call    cs:SafeArrayDestroy
0x1409ec26c  xor     eax, eax
0x1409ec26e  lea     r11, [rsp+70h+var_s0]
0x1409ec273  mov     rbx, [r11+20h]
0x1409ec277  mov     rsi, [r11+28h]
0x1409ec27b  mov     rdi, [r11+30h]
0x1409ec27f  mov     r13, [r11+38h]
0x1409ec283  mov     rsp, r11
0x1409ec286  pop     r15
0x1409ec288  pop     r14
0x1409ec28a  pop     rbp
0x1409ec28b  retn
```
