# MakeCLSIDRegPath(_GUID const &,ushort * const)

- ea: `0x18006c110`
- end: `0x18006c19e`
- name: `?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z`
- size: `142`
- prototype: `int(const struct _GUID *, unsigned __int16 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006bdf0`
- `0x18006c224`

## callees

- `0x18006b99c`

## string_xrefs

- `0x18006c15b`: `CLSID\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}`

## pseudocode

```c
__int64 __fastcall MakeCLSIDRegPath(const struct _GUID *a1, unsigned __int16 *const a2)
{
  int Data2; // [rsp+20h] [rbp-88h]
  int Data3; // [rsp+28h] [rbp-80h]
  int v5; // [rsp+30h] [rbp-78h]
  int v6; // [rsp+38h] [rbp-70h]
  int v7; // [rsp+40h] [rbp-68h]
  int v8; // [rsp+48h] [rbp-60h]
  int v9; // [rsp+50h] [rbp-58h]
  int v10; // [rsp+58h] [rbp-50h]
  int v11; // [rsp+60h] [rbp-48h]
  int v12; // [rsp+68h] [rbp-40h]

  v12 = a1->Data4[7];
  v11 = a1->Data4[6];
  v10 = a1->Data4[5];
  v9 = a1->Data4[4];
  v8 = a1->Data4[3];
  v7 = a1->Data4[2];
  v6 = a1->Data4[1];
  v5 = a1->Data4[0];
  Data3 = a1->Data3;
  Data2 = a1->Data2;
  return StringCchPrintfW(
           a2,
           0x50u,
           L"CLSID\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
           a1->Data1,
           Data2,
           Data3,
           v5,
           v6,
           v7,
           v8,
           v9,
           v10,
           v11,
           v12);
}

```

## disassembly

```asm
0x18006c110  push    rbx
0x18006c112  push    rbp
0x18006c113  push    rsi
0x18006c114  push    rdi
0x18006c115  push    r14
0x18006c117  push    r15
0x18006c119  sub     rsp, 78h
0x18006c11d  movzx   r8d, byte ptr [rcx+0Eh]
0x18006c122  mov     r15, rdx
0x18006c125  movzx   r9d, byte ptr [rcx+0Dh]
0x18006c12a  mov     edx, 50h ; 'P'; unsigned __int64
0x18006c12f  movzx   eax, byte ptr [rcx+0Fh]
0x18006c133  movzx   r10d, byte ptr [rcx+0Ch]
0x18006c138  movzx   r11d, byte ptr [rcx+0Bh]
0x18006c13d  movzx   ebx, byte ptr [rcx+0Ah]
0x18006c141  movzx   edi, byte ptr [rcx+9]
0x18006c145  movzx   esi, byte ptr [rcx+8]
0x18006c149  movzx   ebp, word ptr [rcx+6]
0x18006c14d  movzx   r14d, word ptr [rcx+4]
0x18006c152  mov     [rsp+0A8h+var_40], eax
0x18006c156  mov     [rsp+0A8h+var_48], r8d
0x18006c15b  lea     r8, aClsid08x04x04x; "CLSID\\{%08x-%04x-%04x-%02x%02x-%02x%02"...
0x18006c162  mov     [rsp+0A8h+var_50], r9d
0x18006c167  mov     r9d, [rcx]
0x18006c16a  mov     rcx, r15; unsigned __int16 *
0x18006c16d  mov     [rsp+0A8h+var_58], r10d
0x18006c172  mov     [rsp+0A8h+var_60], r11d
0x18006c177  mov     [rsp+0A8h+var_68], ebx
0x18006c17b  mov     [rsp+0A8h+var_70], edi
0x18006c17f  mov     [rsp+0A8h+var_78], esi
0x18006c183  mov     [rsp+0A8h+var_80], ebp
0x18006c187  mov     [rsp+0A8h+var_88], r14d
0x18006c18c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006c191  add     rsp, 78h
0x18006c195  pop     r15
0x18006c197  pop     r14
0x18006c199  pop     rdi
0x18006c19a  pop     rsi
0x18006c19b  pop     rbp
0x18006c19c  pop     rbx
0x18006c19d  retn
```
