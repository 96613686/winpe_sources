# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x18000ebd8`
- end: `0x18000ec2a`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ec30`
- `0x18000f318`
- `0x18001e930`
- `0x18001fae4`
- `0x180030808`
- `0x1800308ec`
- `0x180036f28`
- `0x18003a5fc`
- `0x18004026c`
- `0x180052e6c`
- `0x18005670c`
- `0x18005678c`
- `0x180056884`
- `0x18006b820`
- `0x18006b8d8`
- `0x18006bc20`
- `0x18006c260`

## callees

- `0x18000ebd8`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000ec1f`
- `ntdll!EtwEventWriteTransfer` at `0x18000ec1f`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_1800B2078;
  if ( qword_1800B2078 )
  {
    *(_QWORD *)a5 = qword_1800B2078;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v6 = 0;
  }
  *(_DWORD *)(a5 + 8) = (_DWORD)v5;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWriteTransfer(S_Microsoft_Windows_Kerberos_Key_Distribution_Center_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x18000ebd8  sub     rsp, 38h
0x18000ebdc  mov     rcx, cs:qword_1800B2078
0x18000ebe3  mov     rax, [rsp+38h+arg_20]
0x18000ebe8  test    rcx, rcx
0x18000ebeb  jnz     short loc_18000EBF5
0x18000ebed  mov     [rax], rcx
0x18000ebf0  xor     r8d, r8d
0x18000ebf3  jmp     short loc_18000EC01
0x18000ebf5  mov     [rax], rcx
0x18000ebf8  mov     r8d, 2
0x18000ebfe  movzx   ecx, word ptr [rcx]
0x18000ec01  mov     [rax+8], ecx
0x18000ec04  mov     [rax+0Ch], r8d
0x18000ec08  xor     r8d, r8d
0x18000ec0b  mov     rcx, cs:S_Microsoft_Windows_Kerberos_Key_Distribution_Center_Context
0x18000ec12  mov     [rsp+38h+var_10], rax
0x18000ec17  mov     [rsp+38h+var_18], r9d
0x18000ec1c  xor     r9d, r9d
0x18000ec1f  call    cs:__imp_EtwEventWriteTransfer
0x18000ec25  add     rsp, 38h
0x18000ec29  retn
```
