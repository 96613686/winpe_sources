# SetJpegQuantizationTableOptions(JpegQuantizationTableTypes,IPropertyBag2 *)

- ea: `0x18015fad8`
- end: `0x18015fc99`
- name: `?SetJpegQuantizationTableOptions@@YAJW4JpegQuantizationTableTypes@@PEAUIPropertyBag2@@@Z`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801383d0`

## callees

- `0x180142e10`
- `0x180143a7c`
- `0x18015fad8`
- `0x1801612ac`
- `0x1803bb010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18015fb55`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18015fb7b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18015fb55`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18015fb7b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18015fc5c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18015fc71`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18015fc5c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18015fc71`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18015fbb2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18015fbf6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18015fbb2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18015fbf6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18015fbdc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18015fc1c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18015fbdc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18015fc1c`

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
      memcpy_s_1(ppvData, v6, &dword_18041F0A4, v8);
      v7 = SafeArrayUnaccessData(psa[1]);
      if ( v7 >= 0 )
      {
        v7 = SafeArrayAccessData(v17[0], &ppvData);
        if ( v7 >= 0 )
        {
          memcpy_s_1(ppvData, v9, &dword_18041F1A4, v10);
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
0x18015fad8  push    rbp
0x18015fada  push    rbx
0x18015fadb  push    rdi
0x18015fadc  push    r15
0x18015fade  lea     rbp, [rsp-3Fh]
0x18015fae3  sub     rsp, 0E8h
0x18015faea  mov     rax, cs:__security_cookie
0x18015faf1  xor     rax, rsp
0x18015faf4  mov     [rbp+57h+var_30], rax
0x18015faf8  mov     rdi, rdx
0x18015fafb  lea     rcx, [rbp+57h+var_80]; void *
0x18015faff  xor     edx, edx; Val
0x18015fb01  lea     r8d, [rdx+50h]; Size
0x18015fb05  call    memset_0
0x18015fb0a  xorps   xmm0, xmm0
0x18015fb0d  mov     qword ptr [rbp+57h+rgsabound.cElements], 40h ; '@'
0x18015fb15  mov     ecx, 3; vt
0x18015fb1a  lea     rax, aLuminance; "Luminance"
0x18015fb21  mov     [rbp+57h+var_70], rax
0x18015fb25  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18015fb29  mov     r15d, 2003h
0x18015fb2f  lea     rax, aChrominance; "Chrominance"
0x18015fb36  mov     [rbp+57h+var_7C], r15w
0x18015fb3b  lea     ebx, [rcx-2]
0x18015fb3e  mov     [rbp+57h+var_48], rax
0x18015fb42  mov     edx, ebx; cDims
0x18015fb44  mov     [rbp+57h+var_54], r15w
0x18015fb49  movups  xmmword ptr [rbp+57h+psa], xmm0
0x18015fb4d  movups  [rbp+57h+var_A8], xmm0
0x18015fb51  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x18015fb55  call    cs:__imp_SafeArrayCreate
0x18015fb5c  nop     dword ptr [rax+rax+00h]
0x18015fb61  lea     ecx, [rbx+2]; vt
0x18015fb64  mov     word ptr [rbp+57h+psa], r15w
0x18015fb69  lea     r8, [rbp+57h+var_C0]; rgsabound
0x18015fb6d  mov     [rbp+57h+psa+8], rax
0x18015fb71  mov     edx, ebx; cDims
0x18015fb73  mov     qword ptr [rbp+57h+var_C0.cElements], 40h ; '@'
0x18015fb7b  call    cs:__imp_SafeArrayCreate
0x18015fb82  nop     dword ptr [rax+rax+00h]
0x18015fb87  mov     rcx, [rbp+57h+psa+8]; psa
0x18015fb8b  mov     [rbp+57h+var_98], rax
0x18015fb8f  mov     word ptr [rbp+57h+var_A8+8], r15w
0x18015fb94  test    rcx, rcx
0x18015fb97  jz      loc_18015FC52
0x18015fb9d  test    rax, rax
0x18015fba0  jz      loc_18015FC52
0x18015fba6  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18015fbaa  mov     [rbp+57h+ppvData], 0
0x18015fbb2  call    cs:__imp_SafeArrayAccessData
0x18015fbb9  nop     dword ptr [rax+rax+00h]
0x18015fbbe  mov     ebx, eax
0x18015fbc0  test    eax, eax
0x18015fbc2  js      loc_18015FC4C
0x18015fbc8  mov     rcx, [rbp+57h+ppvData]; Destination
0x18015fbcc  lea     r8, dword_18041F0A4; Source
0x18015fbd3  call    memcpy_s_1
0x18015fbd8  mov     rcx, [rbp+57h+psa+8]; psa
0x18015fbdc  call    cs:__imp_SafeArrayUnaccessData
0x18015fbe3  nop     dword ptr [rax+rax+00h]
0x18015fbe8  mov     ebx, eax
0x18015fbea  test    eax, eax
0x18015fbec  js      short loc_18015FC4C
0x18015fbee  mov     rcx, [rbp+57h+var_98]; psa
0x18015fbf2  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18015fbf6  call    cs:__imp_SafeArrayAccessData
0x18015fbfd  nop     dword ptr [rax+rax+00h]
0x18015fc02  mov     ebx, eax
0x18015fc04  test    eax, eax
0x18015fc06  js      short loc_18015FC4C
0x18015fc08  mov     rcx, [rbp+57h+ppvData]; Destination
0x18015fc0c  lea     r8, dword_18041F1A4; Source
0x18015fc13  call    memcpy_s_1
0x18015fc18  mov     rcx, [rbp+57h+var_98]; psa
0x18015fc1c  call    cs:__imp_SafeArrayUnaccessData
0x18015fc23  nop     dword ptr [rax+rax+00h]
0x18015fc28  mov     ebx, eax
0x18015fc2a  test    eax, eax
0x18015fc2c  js      short loc_18015FC4C
0x18015fc2e  mov     rax, [rdi]
0x18015fc31  lea     r9, [rbp+57h+psa]
0x18015fc35  lea     r8, [rbp+57h+var_80]
0x18015fc39  mov     edx, 2
0x18015fc3e  mov     rcx, rdi
0x18015fc41  mov     rax, [rax+20h]
0x18015fc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015fc4a  mov     ebx, eax
0x18015fc4c  mov     rcx, [rbp+57h+psa+8]
0x18015fc50  jmp     short loc_18015FC57
0x18015fc52  mov     ebx, 8007000Eh
0x18015fc57  test    rcx, rcx
0x18015fc5a  jz      short loc_18015FC68
0x18015fc5c  call    cs:__imp_SafeArrayDestroy
0x18015fc63  nop     dword ptr [rax+rax+00h]
0x18015fc68  mov     rcx, [rbp+57h+var_98]; psa
0x18015fc6c  test    rcx, rcx
0x18015fc6f  jz      short loc_18015FC7D
0x18015fc71  call    cs:__imp_SafeArrayDestroy
0x18015fc78  nop     dword ptr [rax+rax+00h]
0x18015fc7d  mov     eax, ebx
0x18015fc7f  mov     rcx, [rbp+57h+var_30]
0x18015fc83  xor     rcx, rsp; StackCookie
0x18015fc86  call    __security_check_cookie
0x18015fc8b  add     rsp, 0E8h
0x18015fc92  pop     r15
0x18015fc94  pop     rdi
0x18015fc95  pop     rbx
0x18015fc96  pop     rbp
0x18015fc97  retn
```
