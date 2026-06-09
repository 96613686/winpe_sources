# HostNotifyDeclare

- ea: `0x18002cde8`
- end: `0x18002cfaf`
- name: `HostNotifyDeclare`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002cde8`
- `0x18002e264`
- `0x18005b3d0`
- `0x180379380`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002ce86`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ceea`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ce86`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ceea`
- `OLEAUT32!__imp_VariantInit` at `0x18002cf51`
- `OLEAUT32!__imp_VariantInit` at `0x18002cf51`
- `OLEAUT32!__imp_VariantClear` at `0x18002ce4f`
- `OLEAUT32!__imp_VariantClear` at `0x18002ceb4`
- `OLEAUT32!__imp_VariantClear` at `0x18002cf18`
- `OLEAUT32!__imp_VariantClear` at `0x18002cf75`
- `OLEAUT32!__imp_VariantClear` at `0x18002ce4f`
- `OLEAUT32!__imp_VariantClear` at `0x18002ceb4`
- `OLEAUT32!__imp_VariantClear` at `0x18002cf18`
- `OLEAUT32!__imp_VariantClear` at `0x18002cf75`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002cf92`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002cf92`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002ce3b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002ce3b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002cf3c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002cf85`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002cf3c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002cf85`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002ce1d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002ce1d`

## pseudocode

```c
int __fastcall HostNotifyDeclare(char *a1, char *a2, __int16 a3)
{
  int v3; // eax
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v8; // rdi
  int v9; // ebx
  BSTR v10; // r14
  const OLECHAR *v11; // rax
  const OLECHAR *v12; // rbx
  BSTR v13; // rsi
  const OLECHAR *v14; // rax
  const OLECHAR *v15; // rbx
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
        v10 = 0;
        *(_WORD *)ppvData = 8;
        if ( a1 )
        {
          v11 = OleAllocStrA(a1);
          v12 = v11;
          if ( v11 )
          {
            v10 = SysAllocString(v11);
            ((void (__fastcall *)(LPMALLOC, const OLECHAR *))Rby_lpMalloc->lpVtbl->Free)(Rby_lpMalloc, v12);
          }
        }
        *((_QWORD *)ppvData + 1) = v10;
        ppvData = (char *)ppvData + 24;
        LODWORD(Vector) = VariantClear((VARIANTARG *)ppvData);
        v9 = (int)Vector;
        if ( (int)Vector >= 0 )
        {
          v13 = 0;
          *(_WORD *)ppvData = 8;
          if ( a2 )
          {
            v14 = OleAllocStrA(a2);
            v15 = v14;
            if ( v14 )
            {
              v13 = SysAllocString(v14);
              ((void (__fastcall *)(LPMALLOC, const OLECHAR *))Rby_lpMalloc->lpVtbl->Free)(Rby_lpMalloc, v15);
            }
          }
          *((_QWORD *)ppvData + 1) = v13;
          ppvData = (char *)ppvData + 24;
          LODWORD(Vector) = VariantClear((VARIANTARG *)ppvData);
          v9 = (int)Vector;
          if ( (int)Vector >= 0 )
          {
            *(_WORD *)ppvData = 11;
            *((_WORD *)ppvData + 4) = a3;
            LODWORD(Vector) = SafeArrayUnaccessData(v8);
            v9 = (int)Vector;
            if ( (int)Vector >= 0 )
            {
              ppvData = 0;
              VariantInit(&pvarg);
              pvarg.vt = 8204;
              pvarg.llVal = (LONGLONG)v8;
              HostNotifyTelemetry(0, &pvarg);
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
0x18002cde8  mov     [rsp-28h+arg_0], rbx
0x18002cded  mov     [rsp-28h+arg_8], rsi
0x18002cdf2  push    rbp
0x18002cdf3  push    rdi
0x18002cdf4  push    r12
0x18002cdf6  push    r14
0x18002cdf8  push    r15
0x18002cdfa  mov     rbp, rsp
0x18002cdfd  mov     eax, 40h
0x18002ce02  call    _alloca_probe
0x18002ce07  sub     rsp, rax
0x18002ce0a  movzx   r12d, r8w
0x18002ce0e  mov     rsi, rcx
0x18002ce11  mov     r15, rdx
0x18002ce14  lea     ecx, [rax-34h]; vt
0x18002ce17  lea     r8d, [rax-3Dh]; cElements
0x18002ce1b  xor     edx, edx; lLbound
0x18002ce1d  call    cs:__imp_SafeArrayCreateVector
0x18002ce23  mov     rdi, rax
0x18002ce26  test    rax, rax
0x18002ce29  jz      loc_18002CF98
0x18002ce2f  and     [rbp+ppvData], 0
0x18002ce34  lea     rdx, [rbp+ppvData]; ppvData
0x18002ce38  mov     rcx, rax; psa
0x18002ce3b  call    cs:__imp_SafeArrayAccessData
0x18002ce41  mov     ebx, eax
0x18002ce43  test    eax, eax
0x18002ce45  js      loc_18002CF7B
0x18002ce4b  mov     rcx, [rbp+ppvData]; pvarg
0x18002ce4f  call    cs:__imp_VariantClear
0x18002ce55  mov     ebx, eax
0x18002ce57  test    eax, eax
0x18002ce59  js      loc_18002CF7B
0x18002ce5f  mov     rax, [rbp+ppvData]
0x18002ce63  mov     ecx, 8
0x18002ce68  xor     r14d, r14d
0x18002ce6b  mov     [rax], cx
0x18002ce6e  test    rsi, rsi
0x18002ce71  jz      short loc_18002CEA0
0x18002ce73  mov     rcx, rsi; char *
0x18002ce76  call    ?OleAllocStrA@@YAPEA_WPEAD@Z; OleAllocStrA(char *)
0x18002ce7b  mov     rbx, rax
0x18002ce7e  test    rax, rax
0x18002ce81  jz      short loc_18002CEA0
0x18002ce83  mov     rcx, rax; psz
0x18002ce86  call    cs:__imp_SysAllocString
0x18002ce8c  mov     rcx, cs:?Rby_lpMalloc@@3PEAUIMalloc@@EA; IMalloc * Rby_lpMalloc
0x18002ce93  mov     rdx, rbx
0x18002ce96  mov     r8, [rcx]
0x18002ce99  mov     r14, rax
0x18002ce9c  call    qword ptr [r8+28h]
0x18002cea0  mov     rcx, [rbp+ppvData]
0x18002cea4  mov     [rcx+8], r14
0x18002cea8  mov     rcx, [rbp+ppvData]
0x18002ceac  add     rcx, 18h; pvarg
0x18002ceb0  mov     [rbp+ppvData], rcx
0x18002ceb4  call    cs:__imp_VariantClear
0x18002ceba  mov     ebx, eax
0x18002cebc  test    eax, eax
0x18002cebe  js      loc_18002CF7B
0x18002cec4  mov     rax, [rbp+ppvData]
0x18002cec8  mov     ecx, 8
0x18002cecd  xor     esi, esi
0x18002cecf  mov     [rax], cx
0x18002ced2  test    r15, r15
0x18002ced5  jz      short loc_18002CF04
0x18002ced7  mov     rcx, r15; char *
0x18002ceda  call    ?OleAllocStrA@@YAPEA_WPEAD@Z; OleAllocStrA(char *)
0x18002cedf  mov     rbx, rax
0x18002cee2  test    rax, rax
0x18002cee5  jz      short loc_18002CF04
0x18002cee7  mov     rcx, rax; psz
0x18002ceea  call    cs:__imp_SysAllocString
0x18002cef0  mov     rcx, cs:?Rby_lpMalloc@@3PEAUIMalloc@@EA; IMalloc * Rby_lpMalloc
0x18002cef7  mov     rdx, rbx
0x18002cefa  mov     r8, [rcx]
0x18002cefd  mov     rsi, rax
0x18002cf00  call    qword ptr [r8+28h]
0x18002cf04  mov     rcx, [rbp+ppvData]
0x18002cf08  mov     [rcx+8], rsi
0x18002cf0c  mov     rcx, [rbp+ppvData]
0x18002cf10  add     rcx, 18h; pvarg
0x18002cf14  mov     [rbp+ppvData], rcx
0x18002cf18  call    cs:__imp_VariantClear
0x18002cf1e  mov     ebx, eax
0x18002cf20  test    eax, eax
0x18002cf22  js      short loc_18002CF7B
0x18002cf24  mov     rax, [rbp+ppvData]
0x18002cf28  mov     ecx, 0Bh
0x18002cf2d  mov     [rax], cx
0x18002cf30  mov     rax, [rbp+ppvData]
0x18002cf34  mov     rcx, rdi; psa
0x18002cf37  mov     [rax+8], r12w
0x18002cf3c  call    cs:__imp_SafeArrayUnaccessData
0x18002cf42  mov     ebx, eax
0x18002cf44  test    eax, eax
0x18002cf46  js      short loc_18002CF7B
0x18002cf48  and     [rbp+ppvData], 0
0x18002cf4d  lea     rcx, [rbp+pvarg]; pvarg
0x18002cf51  call    cs:__imp_VariantInit
0x18002cf57  mov     r11d, 200Ch
0x18002cf5d  lea     rdx, [rbp+pvarg]
0x18002cf61  xor     ecx, ecx
0x18002cf63  mov     word ptr [rbp+pvarg], r11w
0x18002cf68  mov     qword ptr [rbp+pvarg+8], rdi
0x18002cf6c  call    ?HostNotifyTelemetry@@YAXW4VBETELEMETRYDATAPOINT@@QEAUtagVARIANT@@@Z; HostNotifyTelemetry(VBETELEMETRYDATAPOINT,tagVARIANT * const)
0x18002cf71  lea     rcx, [rbp+pvarg]; pvarg
0x18002cf75  call    cs:__imp_VariantClear
0x18002cf7b  cmp     [rbp+ppvData], 0
0x18002cf80  jz      short loc_18002CF8B
0x18002cf82  mov     rcx, rdi; psa
0x18002cf85  call    cs:__imp_SafeArrayUnaccessData
0x18002cf8b  test    ebx, ebx
0x18002cf8d  jns     short loc_18002CF98
0x18002cf8f  mov     rcx, rdi; psa
0x18002cf92  call    cs:__imp_SafeArrayDestroy
0x18002cf98  mov     rbx, [rsp+40h+arg_0]
0x18002cf9d  mov     rsi, [rsp+40h+arg_8]
0x18002cfa2  add     rsp, 40h
0x18002cfa6  pop     r15
0x18002cfa8  pop     r14
0x18002cfaa  pop     r12
0x18002cfac  pop     rdi
0x18002cfad  pop     rbp
0x18002cfae  retn
```
