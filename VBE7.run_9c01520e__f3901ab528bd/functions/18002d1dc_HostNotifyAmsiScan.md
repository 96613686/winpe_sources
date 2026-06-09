# HostNotifyAmsiScan

- ea: `0x18002d1dc`
- end: `0x18002d341`
- name: `HostNotifyAmsiScan`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002d1dc`
- `0x18002e264`
- `0x18005b3d0`
- `0x180379380`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002d278`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d278`
- `OLEAUT32!__imp_VariantInit` at `0x18002d2de`
- `OLEAUT32!__imp_VariantInit` at `0x18002d2de`
- `OLEAUT32!__imp_VariantClear` at `0x18002d241`
- `OLEAUT32!__imp_VariantClear` at `0x18002d2a6`
- `OLEAUT32!__imp_VariantClear` at `0x18002d305`
- `OLEAUT32!__imp_VariantClear` at `0x18002d241`
- `OLEAUT32!__imp_VariantClear` at `0x18002d2a6`
- `OLEAUT32!__imp_VariantClear` at `0x18002d305`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002d322`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002d322`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002d22d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002d22d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002d2c9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002d315`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002d2c9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002d315`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002d20f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002d20f`

## pseudocode

```c
int __fastcall HostNotifyAmsiScan(char *a1, int a2)
{
  int v2; // eax
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v6; // rdi
  int v7; // ebx
  BSTR v8; // r14
  const OLECHAR *v9; // rax
  const OLECHAR *v10; // rbx
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  void *ppvData; // [rsp+70h] [rbp+30h] BYREF

  Vector = SafeArrayCreateVector((unsigned __int16)v2 - 52, 0, v2 - 62);
  v6 = Vector;
  if ( Vector )
  {
    ppvData = 0;
    LODWORD(Vector) = SafeArrayAccessData(Vector, &ppvData);
    v7 = (int)Vector;
    if ( (int)Vector >= 0 )
    {
      LODWORD(Vector) = VariantClear((VARIANTARG *)ppvData);
      v7 = (int)Vector;
      if ( (int)Vector >= 0 )
      {
        v8 = 0;
        *(_WORD *)ppvData = 8;
        if ( a1 )
        {
          v9 = OleAllocStrA(a1);
          v10 = v9;
          if ( v9 )
          {
            v8 = SysAllocString(v9);
            ((void (__fastcall *)(LPMALLOC, const OLECHAR *))Rby_lpMalloc->lpVtbl->Free)(Rby_lpMalloc, v10);
          }
        }
        *((_QWORD *)ppvData + 1) = v8;
        ppvData = (char *)ppvData + 24;
        LODWORD(Vector) = VariantClear((VARIANTARG *)ppvData);
        v7 = (int)Vector;
        if ( (int)Vector >= 0 )
        {
          *(_WORD *)ppvData = 22;
          *((_DWORD *)ppvData + 2) = a2;
          LODWORD(Vector) = SafeArrayUnaccessData(v6);
          v7 = (int)Vector;
          if ( (int)Vector >= 0 )
          {
            ppvData = 0;
            VariantInit(&pvarg);
            pvarg.vt = 8204;
            pvarg.llVal = (LONGLONG)v6;
            HostNotifyTelemetry(10, &pvarg);
            LODWORD(Vector) = VariantClear(&pvarg);
          }
        }
      }
    }
    if ( ppvData )
      LODWORD(Vector) = SafeArrayUnaccessData(v6);
    if ( v7 < 0 )
      LODWORD(Vector) = SafeArrayDestroy(v6);
  }
  return (int)Vector;
}

```

## disassembly

```asm
0x18002d1dc  mov     [rsp-18h+arg_0], rbx
0x18002d1e1  mov     [rsp-18h+arg_8], rsi
0x18002d1e6  mov     [rsp-18h+arg_18], rdi
0x18002d1eb  push    rbp
0x18002d1ec  push    r14
0x18002d1ee  push    r15
0x18002d1f0  mov     rbp, rsp
0x18002d1f3  mov     eax, 40h
0x18002d1f8  call    _alloca_probe
0x18002d1fd  sub     rsp, rax
0x18002d200  mov     rsi, rcx
0x18002d203  mov     r15d, edx
0x18002d206  lea     r8d, [rax-3Eh]; cElements
0x18002d20a  lea     ecx, [rax-34h]; vt
0x18002d20d  xor     edx, edx; lLbound
0x18002d20f  call    cs:__imp_SafeArrayCreateVector
0x18002d215  mov     rdi, rax
0x18002d218  test    rax, rax
0x18002d21b  jz      loc_18002D328
0x18002d221  and     [rbp+ppvData], 0
0x18002d226  lea     rdx, [rbp+ppvData]; ppvData
0x18002d22a  mov     rcx, rax; psa
0x18002d22d  call    cs:__imp_SafeArrayAccessData
0x18002d233  mov     ebx, eax
0x18002d235  test    eax, eax
0x18002d237  js      loc_18002D30B
0x18002d23d  mov     rcx, [rbp+ppvData]; pvarg
0x18002d241  call    cs:__imp_VariantClear
0x18002d247  mov     ebx, eax
0x18002d249  test    eax, eax
0x18002d24b  js      loc_18002D30B
0x18002d251  mov     rax, [rbp+ppvData]
0x18002d255  mov     ecx, 8
0x18002d25a  xor     r14d, r14d
0x18002d25d  mov     [rax], cx
0x18002d260  test    rsi, rsi
0x18002d263  jz      short loc_18002D292
0x18002d265  mov     rcx, rsi; char *
0x18002d268  call    ?OleAllocStrA@@YAPEA_WPEAD@Z; OleAllocStrA(char *)
0x18002d26d  mov     rbx, rax
0x18002d270  test    rax, rax
0x18002d273  jz      short loc_18002D292
0x18002d275  mov     rcx, rax; psz
0x18002d278  call    cs:__imp_SysAllocString
0x18002d27e  mov     rcx, cs:?Rby_lpMalloc@@3PEAUIMalloc@@EA; IMalloc * Rby_lpMalloc
0x18002d285  mov     rdx, rbx
0x18002d288  mov     r8, [rcx]
0x18002d28b  mov     r14, rax
0x18002d28e  call    qword ptr [r8+28h]
0x18002d292  mov     rcx, [rbp+ppvData]
0x18002d296  mov     [rcx+8], r14
0x18002d29a  mov     rcx, [rbp+ppvData]
0x18002d29e  add     rcx, 18h; pvarg
0x18002d2a2  mov     [rbp+ppvData], rcx
0x18002d2a6  call    cs:__imp_VariantClear
0x18002d2ac  mov     ebx, eax
0x18002d2ae  test    eax, eax
0x18002d2b0  js      short loc_18002D30B
0x18002d2b2  mov     rax, [rbp+ppvData]
0x18002d2b6  mov     ecx, 16h
0x18002d2bb  mov     [rax], cx
0x18002d2be  mov     rax, [rbp+ppvData]
0x18002d2c2  mov     rcx, rdi; psa
0x18002d2c5  mov     [rax+8], r15d
0x18002d2c9  call    cs:__imp_SafeArrayUnaccessData
0x18002d2cf  mov     ebx, eax
0x18002d2d1  test    eax, eax
0x18002d2d3  js      short loc_18002D30B
0x18002d2d5  and     [rbp+ppvData], 0
0x18002d2da  lea     rcx, [rbp+pvarg]; pvarg
0x18002d2de  call    cs:__imp_VariantInit
0x18002d2e4  mov     r11d, 200Ch
0x18002d2ea  lea     rdx, [rbp+pvarg]
0x18002d2ee  mov     ecx, 0Ah
0x18002d2f3  mov     word ptr [rbp+pvarg], r11w
0x18002d2f8  mov     qword ptr [rbp+pvarg+8], rdi
0x18002d2fc  call    ?HostNotifyTelemetry@@YAXW4VBETELEMETRYDATAPOINT@@QEAUtagVARIANT@@@Z; HostNotifyTelemetry(VBETELEMETRYDATAPOINT,tagVARIANT * const)
0x18002d301  lea     rcx, [rbp+pvarg]; pvarg
0x18002d305  call    cs:__imp_VariantClear
0x18002d30b  cmp     [rbp+ppvData], 0
0x18002d310  jz      short loc_18002D31B
0x18002d312  mov     rcx, rdi; psa
0x18002d315  call    cs:__imp_SafeArrayUnaccessData
0x18002d31b  test    ebx, ebx
0x18002d31d  jns     short loc_18002D328
0x18002d31f  mov     rcx, rdi; psa
0x18002d322  call    cs:__imp_SafeArrayDestroy
0x18002d328  mov     rbx, [rsp+40h+arg_0]
0x18002d32d  mov     rsi, [rsp+40h+arg_8]
0x18002d332  mov     rdi, [rsp+40h+arg_18]
0x18002d337  add     rsp, 40h
0x18002d33b  pop     r15
0x18002d33d  pop     r14
0x18002d33f  pop     rbp
0x18002d340  retn
```
