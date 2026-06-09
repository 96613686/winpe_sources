# WIMHashFile::Hash(uchar *,ulong,uchar *)

- ea: `0x180001c20`
- end: `0x180001cd6`
- name: `?Hash@WIMHashFile@@QEAAJPEAEK0@Z`
- size: `182`
- prototype: `__int64 __fastcall(WIMHashFile *this, unsigned __int8 *, __int64, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019d4`
- `0x180001e9c`
- `0x18000228c`
- `0x180002474`

## callees

- `0x180001c20`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180001ca1`
- `bcrypt!BCryptFinishHash` at `0x180001ca1`
- `bcrypt!BCryptDestroyHash` at `0x180001cbe`
- `bcrypt!BCryptDestroyHash` at `0x180001cbe`
- `bcrypt!BCryptHashData` at `0x180001c86`
- `bcrypt!BCryptHashData` at `0x180001c86`
- `bcrypt!BCryptCreateHash` at `0x180001c65`
- `bcrypt!BCryptCreateHash` at `0x180001c65`

## pseudocode

```c
__int64 __fastcall WIMHashFile::Hash(WIMHashFile *this, unsigned __int8 *a2, __int64 a3, unsigned __int8 *a4)
{
  void *v4; // rcx
  NTSTATUS v7; // ebx
  unsigned int v8; // ebx
  NTSTATUS v9; // eax
  BCRYPT_HASH_HANDLE hHash; // [rsp+50h] [rbp+8h] BYREF

  v4 = (void *)*((_QWORD *)this + 20);
  hHash = 0;
  v7 = BCryptCreateHash(v4, &hHash, 0, 0, 0, 0, 0);
  if ( v7 < 0 || (v7 = BCryptHashData(hHash, a2, 0x54u, 0), v7 < 0) )
  {
    v8 = v7 | 0x10000000;
  }
  else
  {
    v9 = BCryptFinishHash(hHash, a4, 0x20u, 0);
    v8 = v9 | 0x10000000;
    if ( v9 >= 0 )
      v8 = 0;
  }
  if ( hHash )
    BCryptDestroyHash(hHash);
  return v8;
}

```

## disassembly

```asm
0x180001c20  mov     rax, rsp
0x180001c23  mov     [rax+10h], rbx
0x180001c27  mov     [rax+18h], rsi
0x180001c2b  push    rdi
0x180001c2c  sub     rsp, 40h
0x180001c30  mov     rcx, [rcx+0A0h]; hAlgorithm
0x180001c37  mov     rsi, r9
0x180001c3a  mov     dword ptr [rax-18h], 0
0x180001c41  mov     rdi, rdx
0x180001c44  mov     dword ptr [rax-20h], 0
0x180001c4b  lea     rdx, [rax+8]; phHash
0x180001c4f  xor     r9d, r9d; cbHashObject
0x180001c52  mov     qword ptr [rax-28h], 0
0x180001c5a  xor     r8d, r8d; pbHashObject
0x180001c5d  mov     qword ptr [rax+8], 0
0x180001c65  call    cs:__imp_BCryptCreateHash
0x180001c6b  mov     ebx, eax
0x180001c6d  test    eax, eax
0x180001c6f  jns     short loc_180001C77
0x180001c71  bts     ebx, 1Ch
0x180001c75  jmp     short loc_180001CB4
0x180001c77  mov     rcx, [rsp+48h+hHash]; hHash
0x180001c7c  xor     r9d, r9d; dwFlags
0x180001c7f  mov     rdx, rdi; pbInput
0x180001c82  lea     r8d, [r9+54h]; cbInput
0x180001c86  call    cs:__imp_BCryptHashData
0x180001c8c  mov     ebx, eax
0x180001c8e  test    eax, eax
0x180001c90  js      short loc_180001C71
0x180001c92  mov     rcx, [rsp+48h+hHash]; hHash
0x180001c97  xor     r9d, r9d; dwFlags
0x180001c9a  mov     rdx, rsi; pbOutput
0x180001c9d  lea     r8d, [r9+20h]; cbOutput
0x180001ca1  call    cs:__imp_BCryptFinishHash
0x180001ca7  xor     ecx, ecx
0x180001ca9  mov     ebx, eax
0x180001cab  bts     ebx, 1Ch
0x180001caf  test    eax, eax
0x180001cb1  cmovns  ebx, ecx
0x180001cb4  mov     rcx, [rsp+48h+hHash]; hHash
0x180001cb9  test    rcx, rcx
0x180001cbc  jz      short loc_180001CC4
0x180001cbe  call    cs:__imp_BCryptDestroyHash
0x180001cc4  mov     rsi, [rsp+48h+arg_10]
0x180001cc9  mov     eax, ebx
0x180001ccb  mov     rbx, [rsp+48h+arg_8]
0x180001cd0  add     rsp, 40h
0x180001cd4  pop     rdi
0x180001cd5  retn
```
