# AthCreateFileW(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x180010e1c`
- end: `0x180010ece`
- name: `?AthCreateFileW@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `178`
- prototype: `void *__fastcall(const unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, DWORD, DWORD, HANDLE)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000eaa0`

## callees

- `0x180010e1c`
- `0x180012fc0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180010e5a`
- `KERNEL32!CreateFileW` at `0x180010e5a`
- `KERNEL32!SetFileInformationByHandle` at `0x180010eb0`
- `KERNEL32!SetFileInformationByHandle` at `0x180010eb0`

## pseudocode

```c
HANDLE __fastcall AthCreateFileW(
        const unsigned __int16 *a1,
        DWORD a2,
        DWORD a3,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile)
{
  HANDLE FileW; // rbx
  _OWORD FileInformation[2]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v11; // [rsp+60h] [rbp-28h]

  FileW = CreateFileW(a1, a2, a3, a4, dwCreationDisposition, dwFlagsAndAttributes, hTemplateFile);
  if ( FileW && ((dwFlagsAndAttributes & 1) != 0 || (a2 & 0x40000000) == 0) )
  {
    v11 = 0;
    FileInformation[0] = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    FileInformation[1] = FileInformation[0];
    SetFileInformationByHandle(FileW, FileBasicInfo, FileInformation, 0x28u);
  }
  return FileW;
}

```

## disassembly

```asm
0x180010e1c  push    rbx
0x180010e1e  push    rsi
0x180010e1f  push    rdi
0x180010e20  sub     rsp, 70h
0x180010e24  mov     rax, cs:__security_cookie
0x180010e2b  xor     rax, rsp
0x180010e2e  mov     [rsp+88h+var_20], rax
0x180010e33  mov     rax, [rsp+88h+arg_30]
0x180010e3b  mov     edi, edx
0x180010e3d  mov     r10d, [rsp+88h+arg_20]
0x180010e45  mov     esi, [rsp+88h+arg_28]
0x180010e4c  mov     [rsp+88h+hTemplateFile], rax; hTemplateFile
0x180010e51  mov     [rsp+88h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180010e55  mov     [rsp+88h+dwCreationDisposition], r10d; dwCreationDisposition
0x180010e5a  call    cs:__imp_CreateFileW
0x180010e60  mov     rbx, rax
0x180010e63  test    rax, rax
0x180010e66  jz      short loc_180010EB6
0x180010e68  test    sil, 1
0x180010e6c  setz    dl
0x180010e6f  bt      edi, 1Eh
0x180010e73  setb    cl
0x180010e76  test    cl, dl
0x180010e78  jnz     short loc_180010EB6
0x180010e7a  movdqa  xmm1, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180010e82  lea     r8, [rsp+88h+FileInformation]; lpFileInformation
0x180010e87  xor     eax, eax
0x180010e89  xorps   xmm0, xmm0
0x180010e8c  movups  [rsp+88h+FileInformation+4], xmm0
0x180010e91  xor     edx, edx; FileInformationClass
0x180010e93  mov     rcx, rbx; hFile
0x180010e96  movups  xmmword ptr [rsp+88h+var_34], xmm0
0x180010e9b  lea     r9d, [rax+28h]; dwBufferSize
0x180010e9f  mov     qword ptr [rsp+88h+var_34+0Ch], rax
0x180010ea4  movdqu  [rsp+88h+FileInformation], xmm1
0x180010eaa  movdqu  xmmword ptr [rsp+50h], xmm1
0x180010eb0  call    cs:__imp_SetFileInformationByHandle
0x180010eb6  mov     rax, rbx
0x180010eb9  mov     rcx, [rsp+88h+var_20]
0x180010ebe  xor     rcx, rsp; StackCookie
0x180010ec1  call    __security_check_cookie
0x180010ec6  add     rsp, 70h
0x180010eca  pop     rdi
0x180010ecb  pop     rsi
0x180010ecc  pop     rbx
0x180010ecd  retn
```
