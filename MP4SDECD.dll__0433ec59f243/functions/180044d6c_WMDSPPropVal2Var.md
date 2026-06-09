# WMDSPPropVal2Var

- ea: `0x180044d6c`
- end: `0x180044e5e`
- name: `WMDSPPropVal2Var`
- size: `242`
- prototype: `void __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045280`

## callees

- `0x180044d6c`
- `0x180045805`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ddf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ddf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044df4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044df4`
- `OLEAUT32!__imp_SysAllocString` at `0x180044e32`
- `OLEAUT32!__imp_SysAllocString` at `0x180044e32`
- `OLEAUT32!__imp_SysFreeString` at `0x180044e29`
- `OLEAUT32!__imp_SysFreeString` at `0x180044e3d`
- `OLEAUT32!__imp_SysFreeString` at `0x180044e29`
- `OLEAUT32!__imp_SysFreeString` at `0x180044e3d`

## pseudocode

```c
void __fastcall WMDSPPropVal2Var(__int64 a1, int *a2)
{
  void *v4; // rcx
  unsigned int v5; // eax
  void *v6; // rax
  OLECHAR *v7; // rcx
  BSTR v8; // rsi

  switch ( *(_WORD *)a1 )
  {
    case 3:
    case 4:
      goto LABEL_21;
    case 5:
LABEL_10:
      *(_QWORD *)(a1 + 8) = *(_QWORD *)a2;
      return;
    case 8:
      v7 = *(OLECHAR **)(a1 + 8);
      v8 = 0;
      if ( *(_QWORD *)a2 )
      {
        SysFreeString(v7);
        v8 = SysAllocString(*(const OLECHAR **)a2);
      }
      else
      {
        SysFreeString(v7);
      }
      *(_QWORD *)(a1 + 8) = v8;
      return;
    case 0xB:
      *(_WORD *)(a1 + 8) = *(_WORD *)a2;
      return;
    case 0x13:
LABEL_21:
      *(_DWORD *)(a1 + 8) = *a2;
      return;
    case 0x14:
      goto LABEL_10;
  }
  if ( *(_WORD *)a1 != 65 )
  {
    if ( *(_WORD *)a1 != 72 )
      return;
    goto LABEL_10;
  }
  v4 = *(void **)(a1 + 16);
  if ( v4 )
    CoTaskMemFree(v4);
  v5 = *a2;
  *(_DWORD *)(a1 + 8) = *a2;
  *(_QWORD *)(a1 + 16) = 0;
  if ( v5 )
  {
    v6 = CoTaskMemAlloc(v5);
    *(_QWORD *)(a1 + 16) = v6;
    if ( v6 )
      memcpy_0(v6, *((const void **)a2 + 1), *(unsigned int *)(a1 + 8));
  }
}

```

## disassembly

```asm
0x180044d6c  mov     [rsp+arg_0], rbx
0x180044d71  mov     [rsp+arg_8], rsi
0x180044d76  push    rdi
0x180044d77  sub     rsp, 20h
0x180044d7b  movzx   r8d, word ptr [rcx]
0x180044d7f  mov     rdi, rdx
0x180044d82  mov     rbx, rcx
0x180044d85  sub     r8d, 3
0x180044d89  jz      loc_180044E49
0x180044d8f  sub     r8d, 1
0x180044d93  jz      loc_180044E49
0x180044d99  sub     r8d, 1
0x180044d9d  jz      short loc_180044DCB
0x180044d9f  sub     r8d, 3
0x180044da3  jz      short loc_180044E1E
0x180044da5  sub     r8d, 3
0x180044da9  jz      short loc_180044E15
0x180044dab  sub     r8d, 8
0x180044daf  jz      loc_180044E49
0x180044db5  sub     r8d, 1
0x180044db9  jz      short loc_180044DCB
0x180044dbb  sub     r8d, 2Dh ; '-'
0x180044dbf  jz      short loc_180044DD4
0x180044dc1  cmp     r8d, 7
0x180044dc5  jnz     loc_180044E4E
0x180044dcb  mov     rax, [rdx]
0x180044dce  mov     [rcx+8], rax
0x180044dd2  jmp     short loc_180044E4E
0x180044dd4  mov     rcx, [rcx+10h]; pv
0x180044dd8  xor     esi, esi
0x180044dda  test    rcx, rcx
0x180044ddd  jz      short loc_180044DE5
0x180044ddf  call    cs:__imp_CoTaskMemFree
0x180044de5  mov     eax, [rdi]
0x180044de7  mov     [rbx+8], eax
0x180044dea  mov     [rbx+10h], rsi
0x180044dee  test    eax, eax
0x180044df0  jz      short loc_180044E4E
0x180044df2  mov     ecx, eax; cb
0x180044df4  call    cs:__imp_CoTaskMemAlloc
0x180044dfa  mov     [rbx+10h], rax
0x180044dfe  test    rax, rax
0x180044e01  jz      short loc_180044E4E
0x180044e03  mov     r8d, [rbx+8]; Size
0x180044e07  mov     rcx, rax; void *
0x180044e0a  mov     rdx, [rdi+8]; Src
0x180044e0e  call    memcpy_0
0x180044e13  jmp     short loc_180044E4E
0x180044e15  movzx   eax, word ptr [rdx]
0x180044e18  mov     [rcx+8], ax
0x180044e1c  jmp     short loc_180044E4E
0x180044e1e  mov     rcx, [rcx+8]; bstrString
0x180044e22  xor     esi, esi
0x180044e24  cmp     [rdx], rsi
0x180044e27  jz      short loc_180044E3D
0x180044e29  call    cs:__imp_SysFreeString
0x180044e2f  mov     rcx, [rdi]; psz
0x180044e32  call    cs:__imp_SysAllocString
0x180044e38  mov     rsi, rax
0x180044e3b  jmp     short loc_180044E43
0x180044e3d  call    cs:__imp_SysFreeString
0x180044e43  mov     [rbx+8], rsi
0x180044e47  jmp     short loc_180044E4E
0x180044e49  mov     eax, [rdx]
0x180044e4b  mov     [rcx+8], eax
0x180044e4e  mov     rbx, [rsp+28h+arg_0]
0x180044e53  mov     rsi, [rsp+28h+arg_8]
0x180044e58  add     rsp, 20h
0x180044e5c  pop     rdi
0x180044e5d  retn
```
