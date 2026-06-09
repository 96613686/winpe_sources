# ClientAccessCheck

- ea: `0x1800036f0`
- end: `0x18000394a`
- name: `ClientAccessCheck`
- size: `602`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009740`
- `0x18000f680`

## callees

- `0x1800030e0`
- `0x1800036f0`
- `0x180003950`
- `0x180005a50`
- `0x18001cf50`
- `0x18001d9ac`
- `0x1800223e0`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x180003771`
- `ntdll!NtQueryWnfStateData` at `0x180003771`

## pseudocode

```c
void __fastcall ClientAccessCheck(__int64 a1)
{
  unsigned int v1; // eax
  int v2; // [rsp+30h] [rbp-1048h] BYREF
  int v3; // [rsp+34h] [rbp-1044h] BYREF
  void **pExceptionObject; // [rsp+38h] [rbp-1040h] BYREF
  __int128 v5; // [rsp+40h] [rbp-1038h]
  int v6; // [rsp+50h] [rbp-1028h]
  __int64 v7; // [rsp+58h] [rbp-1020h] BYREF
  _BYTE v8[4096]; // [rsp+60h] [rbp-1018h] BYREF

  v7 = a1;
  v3 = 0;
  v2 = 4096;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids,
      (unsigned int)a1,
      HIDWORD(a1));
    LODWORD(a1) = v7;
  }
  if ( (_DWORD)a1 || HIDWORD(v7) )
  {
    if ( !NtCurrentTeb()->IsImpersonating )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
      v6 = 5;
      pExceptionObject = &Broker::AccessDenied::`vftable';
      v5 = 0;
      throw (Broker::AccessDenied *)&pExceptionObject;
    }
    v1 = NtQueryWnfStateData(&v7, 0, 0, &v3, v8, &v2);
    if ( v1 == -1073741790 || v1 == -1073741772 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids, v1);
      v6 = 5;
      pExceptionObject = &Broker::AccessDenied::`vftable';
      v5 = 0;
      throw (Broker::AccessDenied *)&pExceptionObject;
    }
    if ( v1 == -1073741811 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids);
      v6 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v5 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids,
        (unsigned int)v7,
        HIDWORD(v7));
  }
}

```

## disassembly

```asm
0x1800036f0  mov     eax, 1078h
0x1800036f5  call    _alloca_probe
0x1800036fa  sub     rsp, rax
0x1800036fd  mov     rax, cs:__security_cookie
0x180003704  xor     rax, rsp
0x180003707  mov     [rsp+1078h+var_18], rax
0x18000370f  mov     [rsp+1078h+var_1020], rcx
0x180003714  mov     [rsp+1078h+var_1044], 0
0x18000371c  mov     [rsp+1078h+var_1048], 1000h
0x180003724  mov     r10, cs:WPP_GLOBAL_Control
0x18000372b  test    byte ptr [r10+1Ch], 8
0x180003730  jnz     loc_1800037C3
0x180003736  test    ecx, ecx
0x180003738  jz      loc_180003835
0x18000373e  mov     eax, gs:179Ch
0x180003746  test    eax, eax
0x180003748  jz      loc_180003845
0x18000374e  lea     rax, [rsp+1078h+var_1048]
0x180003753  xor     r8d, r8d
0x180003756  mov     [rsp+1078h+var_1050], rax
0x18000375b  lea     r9, [rsp+1078h+var_1044]
0x180003760  lea     rax, [rsp+1078h+var_1018]
0x180003765  xor     edx, edx
0x180003767  lea     rcx, [rsp+1078h+var_1020]
0x18000376c  mov     [rsp+1078h+var_1058], rax
0x180003771  call    cs:__imp_NtQueryWnfStateData
0x180003777  cmp     eax, 0C0000022h
0x18000377c  jz      loc_1800038F1
0x180003782  cmp     eax, 0C0000034h
0x180003787  jz      loc_1800038F1
0x18000378d  cmp     eax, 0C000000Dh
0x180003792  jz      loc_18000389B
0x180003798  mov     rcx, cs:WPP_GLOBAL_Control
0x18000379f  test    byte ptr [rcx+1Ch], 8
0x1800037a3  jz      short loc_1800037AB
0x1800037a5  cmp     byte ptr [rcx+19h], 4
0x1800037a9  jnb     short loc_1800037FB
0x1800037ab  mov     rcx, [rsp+1078h+var_18]
0x1800037b3  xor     rcx, rsp; StackCookie
0x1800037b6  call    __security_check_cookie
0x1800037bb  add     rsp, 1078h
0x1800037c2  retn
0x1800037c3  cmp     byte ptr [r10+19h], 4
0x1800037c8  jb      loc_180003736
0x1800037ce  mov     rax, rcx
0x1800037d1  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x1800037d8  shr     rax, 20h
0x1800037dc  mov     r9d, ecx
0x1800037df  mov     rcx, [r10+10h]
0x1800037e3  mov     edx, 0Ah
0x1800037e8  mov     dword ptr [rsp+1078h+var_1058], eax
0x1800037ec  call    WPP_SF_DD
0x1800037f1  mov     rcx, [rsp+1078h+var_1020]
0x1800037f6  jmp     loc_180003736
0x1800037fb  mov     eax, dword ptr [rsp+1078h+var_1020+4]
0x1800037ff  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x180003806  mov     r9d, dword ptr [rsp+1078h+var_1020]
0x18000380b  mov     edx, 0Eh
0x180003810  mov     rcx, [rcx+10h]
0x180003814  mov     dword ptr [rsp+1078h+var_1058], eax
0x180003818  call    WPP_SF_DD
0x18000381d  mov     rcx, [rsp+1078h+var_18]
0x180003825  xor     rcx, rsp; StackCookie
0x180003828  call    __security_check_cookie
0x18000382d  add     rsp, 1078h
0x180003834  retn
0x180003835  cmp     dword ptr [rsp+1078h+var_1020+4], 0
0x18000383a  jz      loc_1800037AB
0x180003840  jmp     loc_18000373E
0x180003845  mov     rcx, cs:WPP_GLOBAL_Control
0x18000384c  test    byte ptr [rcx+1Ch], 8
0x180003850  jz      short loc_18000386D
0x180003852  cmp     byte ptr [rcx+19h], 2
0x180003856  jb      short loc_18000386D
0x180003858  mov     rcx, [rcx+10h]
0x18000385c  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x180003863  mov     edx, 0Bh
0x180003868  call    WPP_SF_
0x18000386d  xorps   xmm0, xmm0
0x180003870  mov     [rsp+1078h+var_1028], 5
0x180003878  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x18000387f  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x180003886  mov     [rsp+1078h+pExceptionObject], rax
0x18000388b  lea     rcx, [rsp+1078h+pExceptionObject]; pExceptionObject
0x180003890  movups  [rsp+1078h+var_1038], xmm0
0x180003895  call    _CxxThrowException_0
0x18000389b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038a2  test    byte ptr [rcx+1Ch], 8
0x1800038a6  jz      short loc_1800038C3
0x1800038a8  cmp     byte ptr [rcx+19h], 2
0x1800038ac  jb      short loc_1800038C3
0x1800038ae  mov     rcx, [rcx+10h]
0x1800038b2  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x1800038b9  mov     edx, 0Dh
0x1800038be  call    WPP_SF_
0x1800038c3  xorps   xmm0, xmm0
0x1800038c6  mov     [rsp+1078h+var_1028], 4
0x1800038ce  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x1800038d5  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800038dc  mov     [rsp+1078h+pExceptionObject], rax
0x1800038e1  lea     rcx, [rsp+1078h+pExceptionObject]; pExceptionObject
0x1800038e6  movups  [rsp+1078h+var_1038], xmm0
0x1800038eb  call    _CxxThrowException_0
0x1800038f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038f8  test    byte ptr [rcx+1Ch], 8
0x1800038fc  jz      short loc_18000391C
0x1800038fe  cmp     byte ptr [rcx+19h], 2
0x180003902  jb      short loc_18000391C
0x180003904  mov     rcx, [rcx+10h]
0x180003908  lea     r8, WPP_bd1538f8470038ec001d4a44b16548c6_Traceguids
0x18000390f  mov     edx, 0Ch
0x180003914  mov     r9d, eax
0x180003917  call    WPP_SF_d
0x18000391c  xorps   xmm0, xmm0
0x18000391f  mov     [rsp+1078h+var_1028], 5
0x180003927  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x18000392e  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x180003935  mov     [rsp+1078h+pExceptionObject], rax
0x18000393a  lea     rcx, [rsp+1078h+pExceptionObject]; pExceptionObject
0x18000393f  movups  [rsp+1078h+var_1038], xmm0
0x180003944  call    _CxxThrowException_0
```
