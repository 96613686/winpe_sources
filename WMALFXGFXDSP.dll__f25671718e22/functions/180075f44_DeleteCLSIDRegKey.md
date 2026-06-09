# DeleteCLSIDRegKey

- ea: `0x180075f44`
- end: `0x180076044`
- name: `DeleteCLSIDRegKey`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180075c00`

## callees

- `0x180015190`
- `0x180015e90`
- `0x180015ea8`
- `0x180015f08`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180076021`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180076021`

## string_xrefs

- `0x180075f63`: `CLSID\{`

## pseudocode

```c
LSTATUS __fastcall DeleteCLSIDRegKey(unsigned int *a1)
{
  int v3; // [rsp+20h] [rbp-128h]
  int v4; // [rsp+28h] [rbp-120h]
  int v5; // [rsp+30h] [rbp-118h]
  int v6; // [rsp+38h] [rbp-110h]
  int v7; // [rsp+40h] [rbp-108h]
  int v8; // [rsp+48h] [rbp-100h]
  int v9; // [rsp+50h] [rbp-F8h]
  int v10; // [rsp+58h] [rbp-F0h]
  int v11; // [rsp+60h] [rbp-E8h]
  int v12; // [rsp+68h] [rbp-E0h]
  wchar_t Buffer[8]; // [rsp+70h] [rbp-D8h] BYREF
  _BYTE v14[144]; // [rsp+80h] [rbp-C8h] BYREF

  wcscpy(Buffer, L"CLSID\\{");
  memset_0(v14, 0, sizeof(v14));
  v12 = *((unsigned __int8 *)a1 + 15);
  v11 = *((unsigned __int8 *)a1 + 14);
  v10 = *((unsigned __int8 *)a1 + 13);
  v9 = *((unsigned __int8 *)a1 + 12);
  v8 = *((unsigned __int8 *)a1 + 11);
  v7 = *((unsigned __int8 *)a1 + 10);
  v6 = *((unsigned __int8 *)a1 + 9);
  v5 = *((unsigned __int8 *)a1 + 8);
  v4 = *((unsigned __int16 *)a1 + 3);
  v3 = *((unsigned __int16 *)a1 + 2);
  swprintf_s(
    &Buffer[7],
    0x49u,
    L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x",
    *a1,
    v3,
    v4,
    v5,
    v6,
    v7,
    v8,
    v9,
    v10,
    v11,
    v12,
    *(_QWORD *)Buffer,
    *(_QWORD *)&Buffer[4]);
  wcscat_s(Buffer, 0x50u, L"}");
  return SHDeleteKeyW(HKEY_CLASSES_ROOT, Buffer);
}

```

## disassembly

```asm
0x180075f44  push    rbx
0x180075f46  push    rsi
0x180075f47  push    rdi
0x180075f48  push    r14
0x180075f4a  sub     rsp, 128h
0x180075f51  mov     rax, cs:__security_cookie
0x180075f58  xor     rax, rsp
0x180075f5b  mov     [rsp+148h+var_38], rax
0x180075f63  movups  xmm0, xmmword ptr cs:aClsid; "CLSID\\{"
0x180075f6a  mov     r14, rcx
0x180075f6d  xor     edx, edx; Val
0x180075f6f  mov     r8d, 90h; Size
0x180075f75  lea     rcx, [rsp+148h+var_C8]; void *
0x180075f7d  movdqu  xmmword ptr [rsp+148h+Buffer], xmm0
0x180075f83  call    memset_0
0x180075f88  movzx   edx, byte ptr [r14+0Eh]
0x180075f8d  movzx   ecx, byte ptr [r14+0Dh]
0x180075f92  movzx   r8d, byte ptr [r14+0Ch]
0x180075f97  movzx   r9d, byte ptr [r14+0Bh]
0x180075f9c  movzx   eax, byte ptr [r14+0Fh]
0x180075fa1  movzx   r10d, byte ptr [r14+0Ah]
0x180075fa6  movzx   r11d, byte ptr [r14+9]
0x180075fab  movzx   ebx, byte ptr [r14+8]
0x180075fb0  movzx   edi, word ptr [r14+6]
0x180075fb5  movzx   esi, word ptr [r14+4]
0x180075fba  mov     [rsp+148h+var_E0], eax
0x180075fbe  mov     [rsp+148h+var_E8], edx
0x180075fc2  mov     edx, 49h ; 'I'; BufferCount
0x180075fc7  mov     [rsp+148h+var_F0], ecx
0x180075fcb  lea     rcx, [rsp+148h+Buffer+0Eh]; Buffer
0x180075fd0  mov     [rsp+148h+var_F8], r8d
0x180075fd5  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x180075fdc  mov     [rsp+148h+var_100], r9d
0x180075fe1  mov     r9d, [r14]
0x180075fe4  mov     [rsp+148h+var_108], r10d
0x180075fe9  mov     [rsp+148h+var_110], r11d
0x180075fee  mov     [rsp+148h+var_118], ebx
0x180075ff2  mov     [rsp+148h+var_120], edi
0x180075ff6  mov     [rsp+148h+var_128], esi
0x180075ffa  call    swprintf_s
0x180075fff  lea     r8, Source; "}"
0x180076006  mov     edx, 50h ; 'P'; SizeInWords
0x18007600b  lea     rcx, [rsp+148h+Buffer]; Destination
0x180076010  call    wcscat_s
0x180076015  lea     rdx, [rsp+148h+Buffer]; pszSubKey
0x18007601a  mov     rcx, 0FFFFFFFF80000000h; hkey
0x180076021  call    cs:__imp_SHDeleteKeyW
0x180076027  mov     rcx, [rsp+148h+var_38]
0x18007602f  xor     rcx, rsp; StackCookie
0x180076032  call    __security_check_cookie
0x180076037  add     rsp, 128h
0x18007603e  pop     r14
0x180076040  pop     rdi
0x180076041  pop     rsi
0x180076042  pop     rbx
0x180076043  retn
```
