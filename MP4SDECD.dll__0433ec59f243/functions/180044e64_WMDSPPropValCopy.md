# WMDSPPropValCopy

- ea: `0x180044e64`
- end: `0x180044f4d`
- name: `WMDSPPropValCopy`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044bd0`
- `0x180045240`
- `0x1800454e0`

## callees

- `0x180044e64`
- `0x180045805`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044ee6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044ee6`
- `OLEAUT32!__imp_SysAllocString` at `0x180044f22`
- `OLEAUT32!__imp_SysAllocString` at `0x180044f22`
- `OLEAUT32!__imp_SysFreeString` at `0x180044f19`
- `OLEAUT32!__imp_SysFreeString` at `0x180044f2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180044f19`
- `OLEAUT32!__imp_SysFreeString` at `0x180044f2d`

## pseudocode

```c
void __fastcall WMDSPPropValCopy(__int16 a1, OLECHAR **a2, int *a3)
{
  OLECHAR *v5; // rcx
  unsigned int v6; // eax
  OLECHAR *v7; // rax
  OLECHAR *v8; // rcx
  BSTR v9; // rsi

  switch ( a1 )
  {
    case 3:
    case 4:
      goto LABEL_21;
    case 5:
LABEL_10:
      *a2 = *(OLECHAR **)a3;
      return;
    case 8:
      v8 = *a2;
      v9 = 0;
      if ( *(_QWORD *)a3 )
      {
        SysFreeString(v8);
        v9 = SysAllocString(*(const OLECHAR **)a3);
      }
      else
      {
        SysFreeString(v8);
      }
      *a2 = v9;
      return;
    case 11:
      *(_WORD *)a2 = *(_WORD *)a3;
      return;
    case 19:
LABEL_21:
      *(_DWORD *)a2 = *a3;
      return;
    case 20:
      goto LABEL_10;
  }
  if ( a1 != 65 )
  {
    if ( a1 != 72 )
      return;
    goto LABEL_10;
  }
  v5 = a2[1];
  if ( v5 )
    CoTaskMemFree(v5);
  v6 = *a3;
  *(_DWORD *)a2 = *a3;
  a2[1] = 0;
  if ( v6 )
  {
    v7 = (OLECHAR *)CoTaskMemAlloc(v6);
    a2[1] = v7;
    if ( v7 )
      memcpy_0(v7, *((const void **)a3 + 1), *(unsigned int *)a2);
  }
}

```

## disassembly

```asm
0x180044e64  mov     [rsp+arg_0], rbx
0x180044e69  mov     [rsp+arg_8], rsi
0x180044e6e  push    rdi
0x180044e6f  sub     rsp, 20h
0x180044e73  movzx   r9d, cx
0x180044e77  mov     rdi, r8
0x180044e7a  mov     rbx, rdx
0x180044e7d  sub     r9d, 3
0x180044e81  jz      loc_180044F38
0x180044e87  sub     r9d, 1
0x180044e8b  jz      loc_180044F38
0x180044e91  sub     r9d, 1
0x180044e95  jz      short loc_180044EBF
0x180044e97  sub     r9d, 3
0x180044e9b  jz      short loc_180044F0F
0x180044e9d  sub     r9d, 3
0x180044ea1  jz      short loc_180044F06
0x180044ea3  sub     r9d, 8
0x180044ea7  jz      loc_180044F38
0x180044ead  sub     r9d, 1
0x180044eb1  jz      short loc_180044EBF
0x180044eb3  sub     r9d, 2Dh ; '-'
0x180044eb7  jz      short loc_180044EC7
0x180044eb9  cmp     r9d, 7
0x180044ebd  jnz     short loc_180044F3D
0x180044ebf  mov     rax, [r8]
0x180044ec2  mov     [rdx], rax
0x180044ec5  jmp     short loc_180044F3D
0x180044ec7  mov     rcx, [rdx+8]; pv
0x180044ecb  xor     esi, esi
0x180044ecd  test    rcx, rcx
0x180044ed0  jz      short loc_180044ED8
0x180044ed2  call    cs:__imp_CoTaskMemFree
0x180044ed8  mov     eax, [rdi]
0x180044eda  mov     [rbx], eax
0x180044edc  mov     [rbx+8], rsi
0x180044ee0  test    eax, eax
0x180044ee2  jz      short loc_180044F3D
0x180044ee4  mov     ecx, eax; cb
0x180044ee6  call    cs:__imp_CoTaskMemAlloc
0x180044eec  mov     [rbx+8], rax
0x180044ef0  test    rax, rax
0x180044ef3  jz      short loc_180044F3D
0x180044ef5  mov     r8d, [rbx]; Size
0x180044ef8  mov     rcx, rax; void *
0x180044efb  mov     rdx, [rdi+8]; Src
0x180044eff  call    memcpy_0
0x180044f04  jmp     short loc_180044F3D
0x180044f06  movzx   eax, word ptr [r8]
0x180044f0a  mov     [rdx], ax
0x180044f0d  jmp     short loc_180044F3D
0x180044f0f  mov     rcx, [rdx]; bstrString
0x180044f12  xor     esi, esi
0x180044f14  cmp     [r8], rsi
0x180044f17  jz      short loc_180044F2D
0x180044f19  call    cs:__imp_SysFreeString
0x180044f1f  mov     rcx, [rdi]; psz
0x180044f22  call    cs:__imp_SysAllocString
0x180044f28  mov     rsi, rax
0x180044f2b  jmp     short loc_180044F33
0x180044f2d  call    cs:__imp_SysFreeString
0x180044f33  mov     [rbx], rsi
0x180044f36  jmp     short loc_180044F3D
0x180044f38  mov     eax, [r8]
0x180044f3b  mov     [rdx], eax
0x180044f3d  mov     rbx, [rsp+28h+arg_0]
0x180044f42  mov     rsi, [rsp+28h+arg_8]
0x180044f47  add     rsp, 20h
0x180044f4b  pop     rdi
0x180044f4c  retn
```
