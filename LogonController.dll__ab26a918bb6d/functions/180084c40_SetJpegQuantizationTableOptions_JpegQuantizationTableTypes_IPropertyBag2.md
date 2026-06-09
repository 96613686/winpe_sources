# SetJpegQuantizationTableOptions(JpegQuantizationTableTypes,IPropertyBag2 *)

- ea: `0x180084c40`
- end: `0x180084dcc`
- name: `?SetJpegQuantizationTableOptions@@YAJW4JpegQuantizationTableTypes@@PEAUIPropertyBag2@@@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800428bc`

## callees

- `0x18006c000`
- `0x18006cad0`
- `0x180084c40`
- `0x180084df0`
- `0x18009d010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180084cbd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180084cdd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180084cbd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180084cdd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180084d9c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180084dab`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180084d9c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180084dab`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180084d0e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180084d42`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180084d0e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180084d42`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180084d2e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180084d62`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180084d2e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180084d62`

## pseudocode

```c
__int64 __fastcall SetJpegQuantizationTableOptions(__int64 a1, __int64 a2)
{
  SAFEARRAY *v3; // rax
  SAFEARRAY *v4; // rax
  SAFEARRAY *v5; // rcx
  rsize_t v6; // rdx
  HRESULT v7; // ebx
  rsize_t v8; // r9
  rsize_t v9; // rdx
  rsize_t v10; // r9
  void *ppvData; // [rsp+30h] [rbp-79h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-71h] BYREF
  SAFEARRAYBOUND v14; // [rsp+40h] [rbp-69h] BYREF
  SAFEARRAY *psa[2]; // [rsp+48h] [rbp-61h] BYREF
  __int128 v16; // [rsp+58h] [rbp-51h]
  SAFEARRAY *v17[2]; // [rsp+68h] [rbp-41h]
  _BYTE v18[4]; // [rsp+80h] [rbp-29h] BYREF
  __int16 v19; // [rsp+84h] [rbp-25h]
  const wchar_t *v20; // [rsp+90h] [rbp-19h]
  __int16 v21; // [rsp+ACh] [rbp+3h]
  const wchar_t *v22; // [rsp+B8h] [rbp+Fh]

  memset_0(v18, 0, 0x50u);
  rgsabound = (SAFEARRAYBOUND)64LL;
  v20 = L"Luminance";
  v19 = 8195;
  v22 = L"Chrominance";
  v21 = 8195;
  *(_OWORD *)psa = 0;
  v16 = 0;
  *(_OWORD *)v17 = 0;
  v3 = SafeArrayCreate(3u, 1u, &rgsabound);
  LOWORD(psa[0]) = 8195;
  psa[1] = v3;
  v14 = (SAFEARRAYBOUND)64LL;
  v4 = SafeArrayCreate(3u, 1u, &v14);
  v5 = psa[1];
  v17[0] = v4;
  WORD4(v16) = 8195;
  if ( psa[1] && v4 )
  {
    ppvData = 0;
    v7 = SafeArrayAccessData(psa[1], &ppvData);
    if ( v7 >= 0 )
    {
      memcpy_s_1(ppvData, v6, &dword_1800AEE54, v8);
      v7 = SafeArrayUnaccessData(psa[1]);
      if ( v7 >= 0 )
      {
        v7 = SafeArrayAccessData(v17[0], &ppvData);
        if ( v7 >= 0 )
        {
          memcpy_s_1(ppvData, v9, &dword_1800AEF54, v10);
          v7 = SafeArrayUnaccessData(v17[0]);
          if ( v7 >= 0 )
            v7 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, SAFEARRAY **))(*(_QWORD *)a2 + 32LL))(
                   a2,
                   2,
                   v18,
                   psa);
        }
      }
    }
    v5 = psa[1];
  }
  else
  {
    v7 = -2147024882;
  }
  if ( v5 )
    SafeArrayDestroy(v5);
  if ( v17[0] )
    SafeArrayDestroy(v17[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180084c40  push    rbp
0x180084c42  push    rbx
0x180084c43  push    rdi
0x180084c44  push    r15
0x180084c46  lea     rbp, [rsp-3Fh]
0x180084c4b  sub     rsp, 0E8h
0x180084c52  mov     rax, cs:__security_cookie
0x180084c59  xor     rax, rsp
0x180084c5c  mov     [rbp+57h+var_30], rax
0x180084c60  mov     rdi, rdx
0x180084c63  lea     rcx, [rbp+57h+var_80]; void *
0x180084c67  xor     edx, edx; Val
0x180084c69  lea     r8d, [rdx+50h]; Size
0x180084c6d  call    memset_0
0x180084c72  xorps   xmm0, xmm0
0x180084c75  mov     qword ptr [rbp+57h+rgsabound.cElements], 40h ; '@'
0x180084c7d  mov     ecx, 3; vt
0x180084c82  lea     rax, aLuminance; "Luminance"
0x180084c89  mov     [rbp+57h+var_70], rax
0x180084c8d  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180084c91  mov     r15d, 2003h
0x180084c97  lea     rax, aChrominance; "Chrominance"
0x180084c9e  mov     [rbp+57h+var_7C], r15w
0x180084ca3  lea     ebx, [rcx-2]
0x180084ca6  mov     [rbp+57h+var_48], rax
0x180084caa  mov     edx, ebx; cDims
0x180084cac  mov     [rbp+57h+var_54], r15w
0x180084cb1  movups  xmmword ptr [rbp+57h+psa], xmm0
0x180084cb5  movups  [rbp+57h+var_A8], xmm0
0x180084cb9  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x180084cbd  call    cs:__imp_SafeArrayCreate
0x180084cc3  lea     ecx, [rbx+2]; vt
0x180084cc6  mov     word ptr [rbp+57h+psa], r15w
0x180084ccb  lea     r8, [rbp+57h+var_C0]; rgsabound
0x180084ccf  mov     [rbp+57h+psa+8], rax
0x180084cd3  mov     edx, ebx; cDims
0x180084cd5  mov     qword ptr [rbp+57h+var_C0.cElements], 40h ; '@'
0x180084cdd  call    cs:__imp_SafeArrayCreate
0x180084ce3  mov     rcx, [rbp+57h+psa+8]; psa
0x180084ce7  mov     [rbp+57h+var_98], rax
0x180084ceb  mov     word ptr [rbp+57h+var_A8+8], r15w
0x180084cf0  test    rcx, rcx
0x180084cf3  jz      loc_180084D92
0x180084cf9  test    rax, rax
0x180084cfc  jz      loc_180084D92
0x180084d02  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180084d06  mov     [rbp+57h+ppvData], 0
0x180084d0e  call    cs:__imp_SafeArrayAccessData
0x180084d14  mov     ebx, eax
0x180084d16  test    eax, eax
0x180084d18  js      short loc_180084D8C
0x180084d1a  mov     rcx, [rbp+57h+ppvData]; Destination
0x180084d1e  lea     r8, dword_1800AEE54; Source
0x180084d25  call    memcpy_s_1
0x180084d2a  mov     rcx, [rbp+57h+psa+8]; psa
0x180084d2e  call    cs:__imp_SafeArrayUnaccessData
0x180084d34  mov     ebx, eax
0x180084d36  test    eax, eax
0x180084d38  js      short loc_180084D8C
0x180084d3a  mov     rcx, [rbp+57h+var_98]; psa
0x180084d3e  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180084d42  call    cs:__imp_SafeArrayAccessData
0x180084d48  mov     ebx, eax
0x180084d4a  test    eax, eax
0x180084d4c  js      short loc_180084D8C
0x180084d4e  mov     rcx, [rbp+57h+ppvData]; Destination
0x180084d52  lea     r8, dword_1800AEF54; Source
0x180084d59  call    memcpy_s_1
0x180084d5e  mov     rcx, [rbp+57h+var_98]; psa
0x180084d62  call    cs:__imp_SafeArrayUnaccessData
0x180084d68  mov     ebx, eax
0x180084d6a  test    eax, eax
0x180084d6c  js      short loc_180084D8C
0x180084d6e  mov     rax, [rdi]
0x180084d71  lea     r9, [rbp+57h+psa]
0x180084d75  lea     r8, [rbp+57h+var_80]
0x180084d79  mov     edx, 2
0x180084d7e  mov     rcx, rdi
0x180084d81  mov     rax, [rax+20h]
0x180084d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d8a  mov     ebx, eax
0x180084d8c  mov     rcx, [rbp+57h+psa+8]
0x180084d90  jmp     short loc_180084D97
0x180084d92  mov     ebx, 8007000Eh
0x180084d97  test    rcx, rcx
0x180084d9a  jz      short loc_180084DA2
0x180084d9c  call    cs:__imp_SafeArrayDestroy
0x180084da2  mov     rcx, [rbp+57h+var_98]; psa
0x180084da6  test    rcx, rcx
0x180084da9  jz      short loc_180084DB1
0x180084dab  call    cs:__imp_SafeArrayDestroy
0x180084db1  mov     eax, ebx
0x180084db3  mov     rcx, [rbp+57h+var_30]
0x180084db7  xor     rcx, rsp; StackCookie
0x180084dba  call    __security_check_cookie
0x180084dbf  add     rsp, 0E8h
0x180084dc6  pop     r15
0x180084dc8  pop     rdi
0x180084dc9  pop     rbx
0x180084dca  pop     rbp
0x180084dcb  retn
```
