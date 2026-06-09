# CEcsRegKey::Get(CEcsRegKey const &,ushort const *,ulong,bool,_SECURITY_ATTRIBUTES *,bool *,bool)

- ea: `0x1800b1e44`
- end: `0x1800b2087`
- name: `?Get@CEcsRegKey@@SA?AV1@AEBV1@PEBGK_NPEAU_SECURITY_ATTRIBUTES@@PEA_N2@Z`
- size: `579`
- prototype: `HKEY *__fastcall(HKEY *, HKEY *, const WCHAR *, int, char, struct _SECURITY_ATTRIBUTES *lpSecurityAttributes, bool *pExceptionObject, unsigned __int8)`
- caller_count: `31`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ce40`
- `0x18000ded0`
- `0x18000f750`
- `0x180018660`
- `0x180028e1c`
- `0x1800297c0`
- `0x18002a140`
- `0x18002c5e0`
- `0x18002d6e0`
- `0x180039bf8`
- `0x18003cc04`
- `0x18003d088`
- `0x18003d344`
- `0x18003d6c0`
- `0x18003d944`
- `0x1800640b4`
- `0x180064e54`
- `0x1800653c4`
- `0x180065bfc`
- `0x180066a94`
- `0x180066bec`
- `0x180066d3c`
- `0x180067004`
- `0x180067240`
- `0x180069258`
- `0x18006e090`
- `0x180076fb4`
- `0x18007812c`
- `0x1800b7c28`
- `0x1800cc7cc`
- `0x1800d04c0`

## callees

- `0x180003604`
- `0x180007e10`
- `0x180011314`
- `0x18002dad0`
- `0x1800b1e44`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800b1f71`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b1f71`
- `ADVAPI32!RegCreateKeyExW` at `0x1800b201f`
- `ADVAPI32!RegCreateKeyExW` at `0x1800b201f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY *__fastcall CEcsRegKey::Get(
        HKEY *a1,
        HKEY *a2,
        const WCHAR *a3,
        int a4,
        char a5,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        bool *pExceptionObject,
        unsigned __int8 a8)
{
  _BYTE *v12; // rax
  char v13; // cl
  bool *v14; // rdi
  int v15; // ebx
  int v16; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-29h] BYREF
  int v19; // [rsp+54h] [rbp-25h]
  int v20; // [rsp+58h] [rbp-21h] BYREF
  int v21; // [rsp+5Ch] [rbp-1Dh]
  char v22; // [rsp+60h] [rbp-19h]
  const char *v23; // [rsp+68h] [rbp-11h]
  __int64 v24; // [rsp+70h] [rbp-9h]

  v19 = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_63d0a48fd594302e11410a9a9f7a963e_Traceguids);
      v12 = WPP_GLOBAL_Control;
    }
  }
  if ( (v12[68] & 2) != 0 && v12[65] >= 6u )
  {
    v13 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v13 = 0;
LABEL_9:
  v20 = 0;
  v21 = 54;
  v22 = v13;
  v23 = "CEcsRegKey::Get";
  v24 = 0;
  v14 = pExceptionObject;
  if ( pExceptionObject )
    *pExceptionObject = 0;
  if ( lpSecurityAttributes && !a5 )
  {
    v20 = -2147024809;
    HIWORD(v21) = 58;
    LODWORD(pExceptionObject) = -2147024809;
    throw (long *)&pExceptionObject;
  }
  v20 = 0;
  LOWORD(v21) = 58;
  *a1 = 0;
  v19 = 1;
  dwDisposition = 2;
  if ( a5 )
  {
    v16 = RegCreateKeyExW(*a2, a3, 0, 0, 0, a4 | ((a8 + 1) << 8), lpSecurityAttributes, a1, &dwDisposition);
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    v20 = v16;
    if ( v16 < 0 )
    {
      HIWORD(v21) = 94;
      LODWORD(pExceptionObject) = v16;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v21) = 94;
  }
  else
  {
    v15 = RegOpenKeyExW(*a2, a3, 0, a4 | ((a8 + 1) << 8), a1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        12,
        (unsigned int)WPP_63d0a48fd594302e11410a9a9f7a963e_Traceguids,
        (_DWORD)a3,
        v15);
    }
    if ( v15 != 2 )
    {
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      v20 = v15;
      if ( v15 < 0 )
      {
        HIWORD(v21) = 81;
        LODWORD(pExceptionObject) = v15;
        throw (long *)&pExceptionObject;
      }
      LOWORD(v21) = 81;
    }
  }
  if ( v14 )
    *v14 = dwDisposition == 1;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v20);
  return a1;
}

```

## disassembly

```asm
0x1800b1e44  mov     [rsp-8+arg_0], rcx
0x1800b1e49  push    rbp
0x1800b1e4a  push    rbx
0x1800b1e4b  push    rsi
0x1800b1e4c  push    rdi
0x1800b1e4d  push    r14
0x1800b1e4f  push    r15
0x1800b1e51  lea     rbp, [rsp-0Fh]
0x1800b1e56  sub     rsp, 88h
0x1800b1e5d  mov     ebx, r9d
0x1800b1e60  mov     r14, r8
0x1800b1e63  mov     r15, rdx
0x1800b1e66  mov     rsi, rcx
0x1800b1e69  mov     [rbp+37h+var_5C], 0
0x1800b1e70  lea     rcx, WPP_GLOBAL_Control
0x1800b1e77  mov     rax, cs:WPP_GLOBAL_Control
0x1800b1e7e  cmp     rax, rcx
0x1800b1e81  jz      short loc_1800B1EAB
0x1800b1e83  test    byte ptr [rax+44h], 2
0x1800b1e87  jz      short loc_1800B1EBB
0x1800b1e89  cmp     byte ptr [rax+41h], 6
0x1800b1e8d  jb      short loc_1800B1EAB
0x1800b1e8f  mov     edx, 0Bh
0x1800b1e94  lea     r8, WPP_63d0a48fd594302e11410a9a9f7a963e_Traceguids
0x1800b1e9b  mov     rcx, [rax+38h]
0x1800b1e9f  call    WPP_SF_
0x1800b1ea4  mov     rax, cs:WPP_GLOBAL_Control
0x1800b1eab  test    byte ptr [rax+44h], 2
0x1800b1eaf  jz      short loc_1800B1EBB
0x1800b1eb1  cmp     byte ptr [rax+41h], 6
0x1800b1eb5  jb      short loc_1800B1EBB
0x1800b1eb7  mov     cl, 1
0x1800b1eb9  jmp     short loc_1800B1EBD
0x1800b1ebb  xor     cl, cl
0x1800b1ebd  mov     [rbp+37h+var_58], 0
0x1800b1ec4  mov     [rbp+37h+var_54], 36h ; '6'
0x1800b1ecb  mov     [rbp+37h+var_50], cl
0x1800b1ece  lea     rax, aCecsregkeyGet; "CEcsRegKey::Get"
0x1800b1ed5  mov     [rbp+37h+var_48], rax
0x1800b1ed9  mov     [rbp+37h+var_40], 0
0x1800b1ee1  mov     rdi, [rbp+37h+pExceptionObject]
0x1800b1ee5  test    rdi, rdi
0x1800b1ee8  jz      short loc_1800B1EED
0x1800b1eea  mov     byte ptr [rdi], 0
0x1800b1eed  mov     eax, [rbp+37h+var_58]
0x1800b1ef0  mov     [rbp+37h+var_58], eax
0x1800b1ef3  mov     cl, [rbp+37h+arg_20]
0x1800b1ef6  mov     rdx, [rbp+37h+arg_28]
0x1800b1efa  test    rdx, rdx
0x1800b1efd  jz      short loc_1800B1F28
0x1800b1eff  test    cl, cl
0x1800b1f01  jnz     short loc_1800B1F28
0x1800b1f03  mov     ecx, 80070057h
0x1800b1f08  mov     [rbp+37h+var_58], ecx
0x1800b1f0b  mov     eax, 3Ah ; ':'
0x1800b1f10  mov     word ptr [rbp+37h+var_54+2], ax
0x1800b1f14  mov     dword ptr [rbp+37h+pExceptionObject], ecx
0x1800b1f17  lea     rdx, _TI1J; pThrowInfo
0x1800b1f1e  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1800b1f22  call    _CxxThrowException_0
0x1800b1f28  mov     [rbp+37h+var_58], 0
0x1800b1f2f  mov     eax, 3Ah ; ':'
0x1800b1f34  mov     word ptr [rbp+37h+var_54], ax
0x1800b1f38  mov     qword ptr [rsi], 0
0x1800b1f3f  mov     [rbp+37h+var_5C], 1
0x1800b1f46  mov     [rbp+37h+dwDisposition], 2
0x1800b1f4d  movzx   eax, [rbp+37h+arg_38]
0x1800b1f51  inc     eax
0x1800b1f53  shl     eax, 8
0x1800b1f56  or      eax, ebx
0x1800b1f58  xor     r8d, r8d; Reserved
0x1800b1f5b  test    cl, cl
0x1800b1f5d  jnz     loc_1800B1FF7
0x1800b1f63  mov     [rsp+0B0h+phkResult], rsi; phkResult
0x1800b1f68  mov     r9d, eax; samDesired
0x1800b1f6b  mov     rdx, r14; lpSubKey
0x1800b1f6e  mov     rcx, [r15]; hKey
0x1800b1f71  call    cs:__imp_RegOpenKeyExW
0x1800b1f77  mov     ebx, eax
0x1800b1f79  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1f80  lea     rax, WPP_GLOBAL_Control
0x1800b1f87  cmp     rcx, rax
0x1800b1f8a  jz      short loc_1800B1FB4
0x1800b1f8c  test    byte ptr [rcx+44h], 2
0x1800b1f90  jz      short loc_1800B1FB4
0x1800b1f92  cmp     byte ptr [rcx+41h], 4
0x1800b1f96  jb      short loc_1800B1FB4
0x1800b1f98  mov     edx, 0Ch
0x1800b1f9d  mov     dword ptr [rsp+0B0h+phkResult], ebx
0x1800b1fa1  mov     r9, r14
0x1800b1fa4  lea     r8, WPP_63d0a48fd594302e11410a9a9f7a963e_Traceguids
0x1800b1fab  mov     rcx, [rcx+38h]
0x1800b1faf  call    WPP_SF_Sd
0x1800b1fb4  cmp     ebx, 2
0x1800b1fb7  jz      loc_1800B205C
0x1800b1fbd  test    ebx, ebx
0x1800b1fbf  jle     short loc_1800B1FCA
0x1800b1fc1  movzx   ebx, bx
0x1800b1fc4  or      ebx, 80070000h
0x1800b1fca  mov     [rbp+37h+var_58], ebx
0x1800b1fcd  mov     [rbp+37h+var_58], ebx
0x1800b1fd0  mov     eax, 51h ; 'Q'
0x1800b1fd5  test    ebx, ebx
0x1800b1fd7  jns     short loc_1800B1FF1
0x1800b1fd9  mov     word ptr [rbp+37h+var_54+2], ax
0x1800b1fdd  mov     dword ptr [rbp+37h+pExceptionObject], ebx
0x1800b1fe0  lea     rdx, _TI1J; pThrowInfo
0x1800b1fe7  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1800b1feb  call    _CxxThrowException_0
0x1800b1ff1  mov     word ptr [rbp+37h+var_54], ax
0x1800b1ff5  jmp     short loc_1800B205C
0x1800b1ff7  lea     rcx, [rbp+37h+dwDisposition]
0x1800b1ffb  mov     [rsp+0B0h+lpdwDisposition], rcx; lpdwDisposition
0x1800b2000  mov     [rsp+0B0h+var_78], rsi; phkResult
0x1800b2005  mov     [rsp+0B0h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x1800b200a  mov     [rsp+0B0h+samDesired], eax; samDesired
0x1800b200e  mov     dword ptr [rsp+0B0h+phkResult], 0; dwOptions
0x1800b2016  xor     r9d, r9d; lpClass
0x1800b2019  mov     rdx, r14; lpSubKey
0x1800b201c  mov     rcx, [r15]; hKey
0x1800b201f  call    cs:__imp_RegCreateKeyExW
0x1800b2025  test    eax, eax
0x1800b2027  jle     short loc_1800B2031
0x1800b2029  movzx   eax, ax
0x1800b202c  or      eax, 80070000h
0x1800b2031  mov     [rbp+37h+var_58], eax
0x1800b2034  mov     [rbp+37h+var_58], eax
0x1800b2037  mov     ecx, 5Eh ; '^'
0x1800b203c  test    eax, eax
0x1800b203e  jns     short loc_1800B2058
0x1800b2040  mov     word ptr [rbp+37h+var_54+2], cx
0x1800b2044  mov     dword ptr [rbp+37h+pExceptionObject], eax
0x1800b2047  lea     rdx, _TI1J; pThrowInfo
0x1800b204e  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1800b2052  call    _CxxThrowException_0
0x1800b2058  mov     word ptr [rbp+37h+var_54], cx
0x1800b205c  test    rdi, rdi
0x1800b205f  jz      short loc_1800B206A
0x1800b2061  cmp     [rbp+37h+dwDisposition], 1
0x1800b2065  setz    al
0x1800b2068  mov     [rdi], al
0x1800b206a  lea     rcx, [rbp+37h+var_58]; this
0x1800b206e  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800b2073  mov     rax, rsi
0x1800b2076  add     rsp, 88h
0x1800b207d  pop     r15
0x1800b207f  pop     r14
0x1800b2081  pop     rdi
0x1800b2082  pop     rsi
0x1800b2083  pop     rbx
0x1800b2084  pop     rbp
0x1800b2085  retn
```
