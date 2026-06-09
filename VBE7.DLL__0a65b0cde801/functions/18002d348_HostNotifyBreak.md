# HostNotifyBreak

- ea: `0x18002d348`
- end: `0x18002d4c7`
- name: `HostNotifyBreak`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002d348`
- `0x18002e264`
- `0x180379380`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002d442`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d442`
- `OLEAUT32!__imp_VariantInit` at `0x18002d467`
- `OLEAUT32!__imp_VariantInit` at `0x18002d467`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3af`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3f7`
- `OLEAUT32!__imp_VariantClear` at `0x18002d427`
- `OLEAUT32!__imp_VariantClear` at `0x18002d48e`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3af`
- `OLEAUT32!__imp_VariantClear` at `0x18002d3f7`
- `OLEAUT32!__imp_VariantClear` at `0x18002d427`
- `OLEAUT32!__imp_VariantClear` at `0x18002d48e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002d4aa`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002d4aa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002d39b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002d39b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002d453`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002d49d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002d453`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002d49d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002d37b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002d37b`

## pseudocode

```c
int __fastcall HostNotifyBreak(int a1, int a2, const OLECHAR *a3)
{
  int v3; // eax
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v8; // rdi
  int v9; // ebx
  int v10; // ecx
  BSTR v11; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  void *ppvData; // [rsp+88h] [rbp+48h] BYREF

  Vector = SafeArrayCreateVector((unsigned __int16)v3 - 52, 0, v3 - 61);
  v8 = Vector;
  if ( Vector )
  {
    ppvData = 0;
    LODWORD(Vector) = SafeArrayAccessData(Vector, &ppvData);
    v9 = (int)Vector;
    if ( (int)Vector >= 0 )
    {
      LODWORD(Vector) = VariantClear((VARIANTARG *)ppvData);
      v9 = (int)Vector;
      if ( (int)Vector >= 0 )
      {
        *(_WORD *)ppvData = 22;
        if ( a1 )
        {
          v10 = 2;
          if ( a1 != 5 )
            v10 = 0;
          *((_DWORD *)ppvData + 2) = v10;
        }
        else
        {
          *((_DWORD *)ppvData + 2) = 1;
        }
        ppvData = (char *)ppvData + 24;
        LODWORD(Vector) = VariantClear((VARIANTARG *)ppvData);
        v9 = (int)Vector;
        if ( (int)Vector >= 0 )
        {
          *(_WORD *)ppvData = 23;
          *((_DWORD *)ppvData + 2) = a2;
          ppvData = (char *)ppvData + 24;
          LODWORD(Vector) = VariantClear((VARIANTARG *)ppvData);
          v9 = (int)Vector;
          if ( (int)Vector >= 0 )
          {
            *(_WORD *)ppvData = 8;
            v11 = SysAllocString(a3);
            *((_QWORD *)ppvData + 1) = v11;
            LODWORD(Vector) = SafeArrayUnaccessData(v8);
            v9 = (int)Vector;
            if ( (int)Vector >= 0 )
            {
              ppvData = 0;
              VariantInit(&pvarg);
              pvarg.vt = 8204;
              pvarg.llVal = (LONGLONG)v8;
              HostNotifyTelemetry(11, &pvarg);
              LODWORD(Vector) = VariantClear(&pvarg);
            }
          }
        }
      }
    }
    if ( ppvData )
      LODWORD(Vector) = SafeArrayUnaccessData(v8);
    if ( v9 < 0 )
      LODWORD(Vector) = SafeArrayDestroy(v8);
  }
  return (int)Vector;
}

```

## disassembly

```asm
0x18002d348  mov     [rsp-28h+arg_0], rbx
0x18002d34d  mov     [rsp-28h+arg_8], rsi
0x18002d352  push    rbp
0x18002d353  push    rdi
0x18002d354  push    r12
0x18002d356  push    r14
0x18002d358  push    r15
0x18002d35a  mov     rbp, rsp
0x18002d35d  mov     eax, 40h
0x18002d362  call    _alloca_probe
0x18002d367  sub     rsp, rax
0x18002d36a  mov     r15, r8
0x18002d36d  mov     esi, ecx
0x18002d36f  mov     r14d, edx
0x18002d372  lea     ecx, [rax-34h]; vt
0x18002d375  lea     r8d, [rax-3Dh]; cElements
0x18002d379  xor     edx, edx; lLbound
0x18002d37b  call    cs:__imp_SafeArrayCreateVector
0x18002d381  xor     r12d, r12d
0x18002d384  mov     rdi, rax
0x18002d387  test    rax, rax
0x18002d38a  jz      loc_18002D4B0
0x18002d390  lea     rdx, [rbp+ppvData]; ppvData
0x18002d394  mov     rcx, rax; psa
0x18002d397  mov     [rbp+ppvData], r12
0x18002d39b  call    cs:__imp_SafeArrayAccessData
0x18002d3a1  mov     ebx, eax
0x18002d3a3  test    eax, eax
0x18002d3a5  js      loc_18002D494
0x18002d3ab  mov     rcx, [rbp+ppvData]; pvarg
0x18002d3af  call    cs:__imp_VariantClear
0x18002d3b5  mov     ebx, eax
0x18002d3b7  test    eax, eax
0x18002d3b9  js      loc_18002D494
0x18002d3bf  mov     rax, [rbp+ppvData]
0x18002d3c3  lea     ecx, [r12+16h]
0x18002d3c8  mov     [rax], cx
0x18002d3cb  mov     rax, [rbp+ppvData]
0x18002d3cf  test    esi, esi
0x18002d3d1  jz      short loc_18002D3E4
0x18002d3d3  lea     ecx, [r12+2]
0x18002d3d8  cmp     esi, 5
0x18002d3db  cmovnz  ecx, r12d
0x18002d3df  mov     [rax+8], ecx
0x18002d3e2  jmp     short loc_18002D3EB
0x18002d3e4  mov     dword ptr [rax+8], 1
0x18002d3eb  mov     rcx, [rbp+ppvData]
0x18002d3ef  add     rcx, 18h; pvarg
0x18002d3f3  mov     [rbp+ppvData], rcx
0x18002d3f7  call    cs:__imp_VariantClear
0x18002d3fd  mov     ebx, eax
0x18002d3ff  test    eax, eax
0x18002d401  js      loc_18002D494
0x18002d407  mov     rax, [rbp+ppvData]
0x18002d40b  mov     ecx, 17h
0x18002d410  mov     [rax], cx
0x18002d413  mov     rax, [rbp+ppvData]
0x18002d417  mov     [rax+8], r14d
0x18002d41b  mov     rcx, [rbp+ppvData]
0x18002d41f  add     rcx, 18h; pvarg
0x18002d423  mov     [rbp+ppvData], rcx
0x18002d427  call    cs:__imp_VariantClear
0x18002d42d  mov     ebx, eax
0x18002d42f  test    eax, eax
0x18002d431  js      short loc_18002D494
0x18002d433  mov     rax, [rbp+ppvData]
0x18002d437  mov     ecx, 8
0x18002d43c  mov     [rax], cx
0x18002d43f  mov     rcx, r15; psz
0x18002d442  call    cs:__imp_SysAllocString
0x18002d448  mov     rcx, [rbp+ppvData]
0x18002d44c  mov     [rcx+8], rax
0x18002d450  mov     rcx, rdi; psa
0x18002d453  call    cs:__imp_SafeArrayUnaccessData
0x18002d459  mov     ebx, eax
0x18002d45b  test    eax, eax
0x18002d45d  js      short loc_18002D494
0x18002d45f  lea     rcx, [rbp+pvarg]; pvarg
0x18002d463  mov     [rbp+ppvData], r12
0x18002d467  call    cs:__imp_VariantInit
0x18002d46d  mov     r11d, 200Ch
0x18002d473  lea     rdx, [rbp+pvarg]
0x18002d477  mov     ecx, 0Bh
0x18002d47c  mov     word ptr [rbp+pvarg], r11w
0x18002d481  mov     qword ptr [rbp+pvarg+8], rdi
0x18002d485  call    ?HostNotifyTelemetry@@YAXW4VBETELEMETRYDATAPOINT@@QEAUtagVARIANT@@@Z; HostNotifyTelemetry(VBETELEMETRYDATAPOINT,tagVARIANT * const)
0x18002d48a  lea     rcx, [rbp+pvarg]; pvarg
0x18002d48e  call    cs:__imp_VariantClear
0x18002d494  cmp     [rbp+ppvData], r12
0x18002d498  jz      short loc_18002D4A3
0x18002d49a  mov     rcx, rdi; psa
0x18002d49d  call    cs:__imp_SafeArrayUnaccessData
0x18002d4a3  test    ebx, ebx
0x18002d4a5  jns     short loc_18002D4B0
0x18002d4a7  mov     rcx, rdi; psa
0x18002d4aa  call    cs:__imp_SafeArrayDestroy
0x18002d4b0  mov     rbx, [rsp+40h+arg_0]
0x18002d4b5  mov     rsi, [rsp+40h+arg_8]
0x18002d4ba  add     rsp, 40h
0x18002d4be  pop     r15
0x18002d4c0  pop     r14
0x18002d4c2  pop     r12
0x18002d4c4  pop     rdi
0x18002d4c5  pop     rbp
0x18002d4c6  retn
```
