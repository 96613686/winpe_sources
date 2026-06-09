# ATL::CreateNormalizedObject

- ea: `0x18000cb14`
- end: `0x18000cd56`
- name: `ATL::CreateNormalizedObject`
- size: `578`
- prototype: `__int64 __usercall@<rax>(LPCOLESTR lpszProgID@<rcx>, BSTR pbstr)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18000c000`

## callees

- `0x180001800`
- `0x18000cb14`
- `0x180035010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x18000cc61`
- `ole32!CLSIDFromString` at `0x18000cc61`
- `ole32!CLSIDFromProgID` at `0x18000cc83`
- `ole32!CLSIDFromProgID` at `0x18000cc83`
- `ole32!CoGetClassObject` at `0x18000ccc2`
- `ole32!CoGetClassObject` at `0x18000ccc2`
- `ole32!CoCreateInstance` at `0x18000cbea`
- `ole32!CoCreateInstance` at `0x18000cd27`
- `ole32!CoCreateInstance` at `0x18000cbea`
- `ole32!CoCreateInstance` at `0x18000cd27`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cc96`
- `OLEAUT32!__imp_SysStringLen` at `0x18000cc96`
- `USER32!CharNextW` at `0x18000cc19`
- `USER32!CharNextW` at `0x18000cc27`
- `USER32!CharNextW` at `0x18000cc6c`
- `USER32!CharNextW` at `0x18000cc19`
- `USER32!CharNextW` at `0x18000cc27`
- `USER32!CharNextW` at `0x18000cc6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CreateNormalizedObject(WCHAR *lpszProgID, __int64 a2, LPVOID *a3, _BYTE *a4, BSTR pbstr)
{
  GUID *v9; // rcx
  unsigned int Instance; // eax
  LPWSTR v11; // rdi
  LPWSTR v12; // rax
  unsigned int ClassObject; // edi
  __int64 v14; // rax
  HRESULT v15; // eax
  LPVOID v16; // [rsp+40h] [rbp-48h] BYREF
  CLSID pclsid; // [rsp+48h] [rbp-40h] BYREF

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  pclsid = 0;
  *a4 = 0;
  if ( lpszProgID && *lpszProgID )
  {
    if ( ((*lpszProgID - 77) & 0xFFDF) != 0
      || ((lpszProgID[1] - 83) & 0xFFDF) != 0
      || ((lpszProgID[2] - 72) & 0xFFDF) != 0
      || ((lpszProgID[3] - 84) & 0xFFDF) != 0
      || ((lpszProgID[4] - 77) & 0xFFDF) != 0
      || ((lpszProgID[5] - 76) & 0xFFDF) != 0
      || lpszProgID[6] != 58 )
    {
      v11 = lpszProgID;
LABEL_15:
      if ( !*v11 )
      {
LABEL_21:
        ClassObject = -2147467259;
        v14 = -1;
        do
          ++v14;
        while ( lpszProgID[v14] );
        if ( (int)v14 >= 255 )
          return ClassObject;
        v15 = *lpszProgID == 123 ? CLSIDFromString(lpszProgID, &pclsid) : CLSIDFromProgID(lpszProgID, &pclsid);
        ClassObject = v15;
        if ( v15 < 0 )
          return ClassObject;
        if ( SysStringLen(pbstr) )
        {
          v16 = 0;
          ClassObject = CoGetClassObject(&pclsid, 1u, 0, &GUID_b196b28f_bab4_101a_b69c_00aa00341d07, &v16);
          if ( (ClassObject & 0x80000000) == 0 )
            ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, GUID *, BSTR, LPVOID *))(*(_QWORD *)v16 + 56LL))(
                            v16,
                            0,
                            0,
                            &GUID_00000000_0000_0000_c000_000000000046,
                            pbstr,
                            a3);
          if ( v16 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
          return ClassObject;
        }
        return (unsigned int)CoCreateInstance(&pclsid, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, a3);
      }
      v12 = (LPWSTR)L":";
      while ( 1 )
      {
        if ( !*v12 )
        {
LABEL_20:
          v11 = CharNextW(v11);
          if ( v11 )
            goto LABEL_15;
          goto LABEL_21;
        }
        if ( *v11 == *v12 )
          break;
        v12 = CharNextW(v12);
        if ( !v12 )
          goto LABEL_20;
      }
      if ( !CharNextW(v11) )
        goto LABEL_21;
      v9 = &GUID_8856f961_340a_11d0_a96b_00c04fd705a2;
    }
    else
    {
      v9 = &GUID_25336920_03f9_11cf_8fd0_00aa00686f13;
    }
    Instance = CoCreateInstance(v9, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, a3);
    *a4 = 1;
    return Instance;
  }
  return 0;
}

```

## disassembly

```asm
0x18000cb14  mov     [rsp+arg_8], rbx
0x18000cb19  push    rbp
0x18000cb1a  push    rsi
0x18000cb1b  push    rdi
0x18000cb1c  push    r14
0x18000cb1e  push    r15
0x18000cb20  sub     rsp, 60h
0x18000cb24  mov     rax, cs:__security_cookie
0x18000cb2b  xor     rax, rsp
0x18000cb2e  mov     [rsp+88h+var_30], rax
0x18000cb33  mov     r14, r9
0x18000cb36  mov     rsi, r8
0x18000cb39  mov     rbx, rcx
0x18000cb3c  mov     rbp, [rsp+88h+pbstr]
0x18000cb44  xor     r15d, r15d
0x18000cb47  test    r8, r8
0x18000cb4a  jnz     short loc_18000CB56
0x18000cb4c  mov     eax, 80004003h
0x18000cb51  jmp     loc_18000CD35
0x18000cb56  mov     [r8], r15
0x18000cb59  xorps   xmm0, xmm0
0x18000cb5c  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x18000cb61  mov     [r9], r15b
0x18000cb64  test    rbx, rbx
0x18000cb67  jz      loc_18000CD33
0x18000cb6d  movzx   eax, word ptr [rcx]
0x18000cb70  test    ax, ax
0x18000cb73  jz      loc_18000CD33
0x18000cb79  sub     ax, 4Dh ; 'M'
0x18000cb7d  mov     ecx, 0FFDFh
0x18000cb82  test    cx, ax
0x18000cb85  jnz     short loc_18000CBF9
0x18000cb87  movzx   eax, word ptr [rbx+2]
0x18000cb8b  sub     ax, 53h ; 'S'
0x18000cb8f  test    cx, ax
0x18000cb92  jnz     short loc_18000CBF9
0x18000cb94  movzx   eax, word ptr [rbx+4]
0x18000cb98  sub     ax, 48h ; 'H'
0x18000cb9c  test    cx, ax
0x18000cb9f  jnz     short loc_18000CBF9
0x18000cba1  movzx   eax, word ptr [rbx+6]
0x18000cba5  sub     ax, 54h ; 'T'
0x18000cba9  test    cx, ax
0x18000cbac  jnz     short loc_18000CBF9
0x18000cbae  movzx   eax, word ptr [rbx+8]
0x18000cbb2  sub     ax, 4Dh ; 'M'
0x18000cbb6  test    cx, ax
0x18000cbb9  jnz     short loc_18000CBF9
0x18000cbbb  movzx   eax, word ptr [rbx+0Ah]
0x18000cbbf  sub     ax, 4Ch ; 'L'
0x18000cbc3  test    cx, ax
0x18000cbc6  jnz     short loc_18000CBF9
0x18000cbc8  cmp     word ptr [rbx+0Ch], 3Ah ; ':'
0x18000cbcd  jnz     short loc_18000CBF9
0x18000cbcf  lea     rcx, _GUID_25336920_03f9_11cf_8fd0_00aa00686f13; rclsid
0x18000cbd6  mov     r8d, 1; dwClsContext
0x18000cbdc  xor     edx, edx; pUnkOuter
0x18000cbde  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000cbe5  mov     [rsp+88h+ppv], rsi; ppv
0x18000cbea  call    cs:__imp_CoCreateInstance
0x18000cbf0  mov     byte ptr [r14], 1
0x18000cbf4  jmp     loc_18000CD2D
0x18000cbf9  mov     rdi, rbx
0x18000cbfc  cmp     [rdi], r15w
0x18000cc00  jz      short loc_18000CC35
0x18000cc02  lea     rax, sz; ":"
0x18000cc09  movzx   ecx, word ptr [rax]
0x18000cc0c  test    cx, cx
0x18000cc0f  jz      short loc_18000CC24
0x18000cc11  cmp     [rdi], cx
0x18000cc14  jz      short loc_18000CC69
0x18000cc16  mov     rcx, rax; lpsz
0x18000cc19  call    cs:__imp_CharNextW
0x18000cc1f  test    rax, rax
0x18000cc22  jnz     short loc_18000CC09
0x18000cc24  mov     rcx, rdi; lpsz
0x18000cc27  call    cs:__imp_CharNextW
0x18000cc2d  mov     rdi, rax
0x18000cc30  test    rax, rax
0x18000cc33  jnz     short loc_18000CBFC
0x18000cc35  mov     edi, 80004005h
0x18000cc3a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cc3e  inc     rax
0x18000cc41  cmp     [rbx+rax*2], r15w
0x18000cc46  jnz     short loc_18000CC3E
0x18000cc48  cmp     eax, 0FFh
0x18000cc4d  jge     loc_18000CD2F
0x18000cc53  lea     rdx, [rsp+88h+pclsid]; lpclsid
0x18000cc58  mov     rcx, rbx; lpszProgID
0x18000cc5b  cmp     word ptr [rbx], 7Bh ; '{'
0x18000cc5f  jnz     short loc_18000CC83
0x18000cc61  call    cs:__imp_CLSIDFromString
0x18000cc67  jmp     short loc_18000CC89
0x18000cc69  mov     rcx, rdi; lpsz
0x18000cc6c  call    cs:__imp_CharNextW
0x18000cc72  test    rax, rax
0x18000cc75  jz      short loc_18000CC35
0x18000cc77  lea     rcx, _GUID_8856f961_340a_11d0_a96b_00c04fd705a2
0x18000cc7e  jmp     loc_18000CBD6
0x18000cc83  call    cs:__imp_CLSIDFromProgID
0x18000cc89  mov     edi, eax
0x18000cc8b  test    eax, eax
0x18000cc8d  js      loc_18000CD2F
0x18000cc93  mov     rcx, rbp; pbstr
0x18000cc96  call    cs:__imp_SysStringLen
0x18000cc9c  test    eax, eax
0x18000cc9e  jz      short loc_18000CD10
0x18000cca0  mov     [rsp+88h+var_48], r15
0x18000cca5  lea     rax, [rsp+88h+var_48]
0x18000ccaa  mov     [rsp+88h+ppv], rax; ppv
0x18000ccaf  lea     r9, _GUID_b196b28f_bab4_101a_b69c_00aa00341d07; riid
0x18000ccb6  xor     r8d, r8d; pvReserved
0x18000ccb9  lea     edx, [r8+1]; dwClsContext
0x18000ccbd  lea     rcx, [rsp+88h+pclsid]; rclsid
0x18000ccc2  call    cs:__imp_CoGetClassObject
0x18000ccc8  mov     edi, eax
0x18000ccca  test    eax, eax
0x18000cccc  js      short loc_18000CCF7
0x18000ccce  mov     rcx, [rsp+88h+var_48]
0x18000ccd3  mov     rax, [rcx]
0x18000ccd6  mov     [rsp+88h+var_60], rsi
0x18000ccdb  mov     [rsp+88h+ppv], rbp
0x18000cce0  lea     r9, _GUID_00000000_0000_0000_c000_000000000046
0x18000cce7  xor     r8d, r8d
0x18000ccea  xor     edx, edx
0x18000ccec  mov     rax, [rax+38h]
0x18000ccf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccf5  mov     edi, eax
0x18000ccf7  mov     rcx, [rsp+88h+var_48]
0x18000ccfc  test    rcx, rcx
0x18000ccff  jz      short loc_18000CD0E
0x18000cd01  mov     rax, [rcx]
0x18000cd04  mov     rax, [rax+10h]
0x18000cd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd0d  nop
0x18000cd0e  jmp     short loc_18000CD2F
0x18000cd10  mov     [rsp+88h+ppv], rsi; ppv
0x18000cd15  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000cd1c  xor     edx, edx; pUnkOuter
0x18000cd1e  lea     r8d, [rdx+1]; dwClsContext
0x18000cd22  lea     rcx, [rsp+88h+pclsid]; rclsid
0x18000cd27  call    cs:__imp_CoCreateInstance
0x18000cd2d  mov     edi, eax
0x18000cd2f  mov     eax, edi
0x18000cd31  jmp     short loc_18000CD35
0x18000cd33  xor     eax, eax
0x18000cd35  mov     rcx, [rsp+88h+var_30]
0x18000cd3a  xor     rcx, rsp; StackCookie
0x18000cd3d  call    __security_check_cookie
0x18000cd42  mov     rbx, [rsp+88h+arg_8]
0x18000cd4a  add     rsp, 60h
0x18000cd4e  pop     r15
0x18000cd50  pop     r14
0x18000cd52  pop     rdi
0x18000cd53  pop     rsi
0x18000cd54  pop     rbp
0x18000cd55  retn
```
