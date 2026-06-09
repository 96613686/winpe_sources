# IoCopy_InterfaceReg(_CRYPT_INTERFACE_REG *,ulong,ulong *,uchar *)

- ea: `0x180019e84`
- end: `0x180019f39`
- name: `?IoCopy_InterfaceReg@@YAKPEAU_CRYPT_INTERFACE_REG@@KPEAKPEAE@Z`
- size: `181`
- prototype: `unsigned int __fastcall(struct _CRYPT_INTERFACE_REG *, unsigned int, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019f40`

## callees

- `0x180001d9c`
- `0x180019e84`
- `0x18001a008`

## pseudocode

```c
unsigned int __fastcall IoCopy_InterfaceReg(
        struct _CRYPT_INTERFACE_REG *a1,
        __int64 a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  __int64 v7; // r9
  ULONG cFunctions; // edx
  unsigned __int16 **rgpszFunctions; // rcx
  unsigned int result; // eax
  unsigned __int8 *v11; // rbp
  unsigned int v12; // ecx
  unsigned int v13; // [rsp+58h] [rbp+10h] BYREF

  v13 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !(unsigned int)ValidateInterfaceId(a1->dwInterface, 0) )
    return 87;
  cFunctions = a1->cFunctions;
  if ( !cFunctions )
    return 87;
  rgpszFunctions = a1->rgpszFunctions;
  if ( !rgpszFunctions )
    return 87;
  if ( (a1->dwFlags & 0xFFFFFFFE) != 0 )
    return 1004;
  v11 = (unsigned __int8 *)((v7 + 24) & -(__int64)(a4 != 0));
  result = IoCopy_SzStringArray(rgpszFunctions, cFunctions, &v13, v11);
  if ( !result )
  {
    v12 = v13;
    if ( v13 )
    {
      if ( a4 )
      {
        *(_DWORD *)a4 = a1->dwInterface;
        *((_DWORD *)a4 + 1) = a1->dwFlags;
        *((_QWORD *)a4 + 2) = v11;
        *((_DWORD *)a4 + 2) = a1->cFunctions;
      }
      if ( a3 )
        *a3 = v12 + 24;
      return 0;
    }
    return 87;
  }
  return result;
}

```

## disassembly

```asm
0x180019e84  mov     [rsp+arg_8], edx
0x180019e88  push    rbx
0x180019e89  push    rbp
0x180019e8a  push    rsi
0x180019e8b  push    rdi
0x180019e8c  sub     rsp, 28h
0x180019e90  mov     [rsp+48h+arg_8], 0
0x180019e98  mov     rsi, r9
0x180019e9b  mov     rdi, r8
0x180019e9e  mov     rbx, rcx
0x180019ea1  test    r8, r8
0x180019ea4  jz      short loc_180019EAD
0x180019ea6  mov     dword ptr [r8], 0
0x180019ead  mov     ecx, [rcx]; unsigned int
0x180019eaf  xor     edx, edx; unsigned int
0x180019eb1  call    ?ValidateInterfaceId@@YAHKK@Z; ValidateInterfaceId(ulong,ulong)
0x180019eb6  test    eax, eax
0x180019eb8  jz      short loc_180019F2A
0x180019eba  mov     edx, [rbx+8]; unsigned int
0x180019ebd  test    edx, edx
0x180019ebf  jz      short loc_180019F2A
0x180019ec1  mov     rcx, [rbx+10h]; unsigned __int16 **
0x180019ec5  test    rcx, rcx
0x180019ec8  jz      short loc_180019F2A
0x180019eca  test    dword ptr [rbx+4], 0FFFFFFFEh
0x180019ed1  jz      short loc_180019EDA
0x180019ed3  mov     eax, 3ECh
0x180019ed8  jmp     short loc_180019F2F
0x180019eda  lea     r8, [r9+18h]
0x180019ede  mov     rax, rsi
0x180019ee1  neg     rax
0x180019ee4  sbb     rbp, rbp
0x180019ee7  and     rbp, r8
0x180019eea  lea     r8, [rsp+48h+arg_8]; unsigned int *
0x180019eef  mov     r9, rbp; unsigned __int8 *
0x180019ef2  call    ?IoCopy_SzStringArray@@YAKPEAPEAGKPEAKPEAE@Z; IoCopy_SzStringArray(ushort * *,ulong,ulong *,uchar *)
0x180019ef7  test    eax, eax
0x180019ef9  jnz     short loc_180019F2F
0x180019efb  mov     ecx, [rsp+48h+arg_8]
0x180019eff  test    ecx, ecx
0x180019f01  jz      short loc_180019F2A
0x180019f03  test    rsi, rsi
0x180019f06  jz      short loc_180019F1C
0x180019f08  mov     eax, [rbx]
0x180019f0a  mov     [rsi], eax
0x180019f0c  mov     eax, [rbx+4]
0x180019f0f  mov     [rsi+4], eax
0x180019f12  mov     [rsi+10h], rbp
0x180019f16  mov     eax, [rbx+8]
0x180019f19  mov     [rsi+8], eax
0x180019f1c  test    rdi, rdi
0x180019f1f  jz      short loc_180019F26
0x180019f21  lea     eax, [rcx+18h]
0x180019f24  mov     [rdi], eax
0x180019f26  xor     eax, eax
0x180019f28  jmp     short loc_180019F2F
0x180019f2a  mov     eax, 57h ; 'W'
0x180019f2f  add     rsp, 28h
0x180019f33  pop     rdi
0x180019f34  pop     rsi
0x180019f35  pop     rbp
0x180019f36  pop     rbx
0x180019f37  retn
```
