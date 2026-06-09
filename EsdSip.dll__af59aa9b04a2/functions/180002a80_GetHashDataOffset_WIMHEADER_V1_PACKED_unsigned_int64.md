# GetHashDataOffset(_WIMHEADER_V1_PACKED *,unsigned __int64 *)

- ea: `0x180002a80`
- end: `0x180002b07`
- name: `?GetHashDataOffset@@YA_NPEAU_WIMHEADER_V1_PACKED@@PEA_K@Z`
- size: `135`
- prototype: `char __fastcall(struct _WIMHEADER_V1_PACKED *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019e0`
- `0x180002210`
- `0x180002edc`

## callees

- `0x180002a80`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180002af3`
- `KERNEL32!SetLastError` at `0x180002af3`

## pseudocode

```c
char __fastcall GetHashDataOffset(struct _WIMHEADER_V1_PACKED *a1, unsigned __int64 *a2)
{
  char *v3; // r9
  char *v4; // r10
  char *v5; // rdx
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // r9
  _QWORD v10[4]; // [rsp+20h] [rbp-28h] BYREF
  char v11; // [rsp+40h] [rbp-8h] BYREF

  v10[1] = (char *)a1 + 72;
  v3 = (char *)a1 + 48;
  v10[0] = (char *)a1 + 48;
  v4 = (char *)a1 + 96;
  v10[3] = (char *)a1 + 124;
  v10[2] = (char *)a1 + 96;
  v5 = (char *)v10;
  v6 = 0;
  while ( 1 )
  {
    if ( v3 != v4 )
    {
      v7 = *((_QWORD *)v3 + 1);
      v8 = v7 + (*(_QWORD *)v3 & 0xFFFFFFFFFFFFFFLL);
      if ( v8 < v7 )
      {
        SetLastError(0x216u);
        return 0;
      }
      if ( v6 < v8 )
        v6 = v8;
    }
    v5 += 8;
    if ( v5 == &v11 )
      break;
    v3 = *(char **)v5;
  }
  *a2 = v6;
  return 1;
}

```

## disassembly

```asm
0x180002a80  sub     rsp, 48h
0x180002a84  lea     rax, [rcx+48h]
0x180002a88  mov     r11, rdx
0x180002a8b  mov     [rsp+48h+var_20], rax
0x180002a90  lea     r9, [rcx+30h]
0x180002a94  lea     rax, [rcx+7Ch]
0x180002a98  mov     [rsp+48h+var_28], r9
0x180002a9d  lea     r10, [rcx+60h]
0x180002aa1  mov     [rsp+48h+var_10], rax
0x180002aa6  mov     [rsp+48h+var_18], r10
0x180002aab  lea     rdx, [rsp+48h+var_28]
0x180002ab0  xor     r8d, r8d
0x180002ab3  cmp     r9, r10
0x180002ab6  jz      short loc_180002ADB
0x180002ab8  mov     rcx, [r9+8]
0x180002abc  mov     rax, [r9]
0x180002abf  mov     r9, 0FFFFFFFFFFFFFFh
0x180002ac9  and     r9, rax
0x180002acc  add     r9, rcx
0x180002acf  cmp     r9, rcx
0x180002ad2  jb      short loc_180002AEE
0x180002ad4  cmp     r8, r9
0x180002ad7  cmovb   r8, r9
0x180002adb  add     rdx, 8
0x180002adf  lea     rax, [rsp+48h+var_8]
0x180002ae4  cmp     rdx, rax
0x180002ae7  jz      short loc_180002AFD
0x180002ae9  mov     r9, [rdx]
0x180002aec  jmp     short loc_180002AB3
0x180002aee  mov     ecx, 216h; dwErrCode
0x180002af3  call    cs:__imp_SetLastError
0x180002af9  xor     al, al
0x180002afb  jmp     short loc_180002B02
0x180002afd  mov     [r11], r8
0x180002b00  mov     al, 1
0x180002b02  add     rsp, 48h
0x180002b06  retn
```
