# SuplNode::SetBinaryRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT)

- ea: `0x180118e68`
- end: `0x180118fa8`
- name: `?SetBinaryRegValue@SuplNode@@AEAAJPEAUHKEY__@@PEBG1UtagVARIANT@@@Z`
- size: `320`
- prototype: `int(SuplNode *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180118a88`

## callees

- `0x1800a98c0`
- `0x180118e68`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180118f44`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180118f44`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180118f2c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180118f2c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180118f56`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180118f56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180118edb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180118edb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180118ebb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180118ebb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180118f8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180118f8d`

## pseudocode

```c
__int64 __fastcall SuplNode::SetBinaryRegValue(
        SuplNode *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct tagVARIANT *a5)
{
  LSTATUS v6; // eax
  int UBound; // ebx
  SAFEARRAY *parray; // rdi
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  void *ppvData; // [rsp+38h] [rbp-18h] BYREF
  LONG plUbound; // [rsp+40h] [rbp-10h] BYREF

  hKey = 0;
  ppvData = 0;
  plUbound = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 2u, &hKey);
  UBound = v6;
  if ( v6 )
  {
    if ( v6 <= 0 )
      goto LABEL_4;
    goto LABEL_3;
  }
  UBound = 0;
  if ( !a5->vt )
    goto LABEL_14;
  if ( a5->vt != 8209 || (parray = a5->parray) == 0 )
  {
    UBound = -2147024809;
    goto LABEL_4;
  }
  UBound = SafeArrayAccessData(parray, &ppvData);
  if ( UBound >= 0 )
  {
    UBound = SafeArrayGetUBound(parray, 1u, &plUbound);
    if ( UBound >= 0 )
    {
      ++plUbound;
      SafeArrayUnaccessData(parray);
LABEL_14:
      if ( ppvData )
      {
        if ( plUbound )
        {
          v6 = RegSetValueExW(hKey, a4, 0, 3u, (const BYTE *)ppvData, plUbound);
          if ( v6 )
          {
            if ( v6 > 0 )
            {
LABEL_3:
              UBound = (unsigned __int16)v6 | 0x80070000;
              goto LABEL_4;
            }
            UBound = v6;
          }
        }
      }
    }
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x180118e68  mov     [rsp-18h+arg_0], rbx
0x180118e6d  mov     [rsp-18h+arg_8], rsi
0x180118e72  push    rbp
0x180118e73  push    rdi
0x180118e74  push    r14
0x180118e76  mov     rbp, rsp
0x180118e79  sub     rsp, 50h
0x180118e7d  mov     rax, cs:__security_cookie
0x180118e84  xor     rax, rsp
0x180118e87  mov     [rbp+var_8], rax
0x180118e8b  mov     rdi, [rbp+arg_20]
0x180118e8f  lea     rcx, [rbp+hKey]
0x180118e93  xor     r14d, r14d
0x180118e96  mov     [rsp+50h+phkResult], rcx; phkResult
0x180118e9b  mov     rsi, r9
0x180118e9e  mov     [rbp+hKey], r14
0x180118ea2  mov     rdx, r8; lpSubKey
0x180118ea5  mov     [rbp+ppvData], r14
0x180118ea9  xor     r8d, r8d; ulOptions
0x180118eac  mov     [rbp+plUbound], r14d
0x180118eb0  lea     r9d, [r14+2]; samDesired
0x180118eb4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180118ebb  call    cs:__imp_RegOpenKeyExW
0x180118ec1  mov     ebx, eax
0x180118ec3  test    eax, eax
0x180118ec5  jz      short loc_180118F02
0x180118ec7  jle     short loc_180118ED2
0x180118ec9  movzx   ebx, ax
0x180118ecc  or      ebx, 80070000h
0x180118ed2  mov     rcx, [rbp+hKey]; hKey
0x180118ed6  test    rcx, rcx
0x180118ed9  jz      short loc_180118EE1
0x180118edb  call    cs:__imp_RegCloseKey
0x180118ee1  mov     eax, ebx
0x180118ee3  mov     rcx, [rbp+var_8]
0x180118ee7  xor     rcx, rsp; StackCookie
0x180118eea  call    __security_check_cookie
0x180118eef  mov     rbx, [rsp+50h+arg_0]
0x180118ef4  mov     rsi, [rsp+50h+arg_8]
0x180118ef9  add     rsp, 50h
0x180118efd  pop     r14
0x180118eff  pop     rdi
0x180118f00  pop     rbp
0x180118f01  retn
0x180118f02  mov     ebx, r14d
0x180118f05  cmp     [rdi], r14w
0x180118f09  jz      short loc_180118F5C
0x180118f0b  mov     eax, 2011h
0x180118f10  cmp     ax, [rdi]
0x180118f13  jz      short loc_180118F1C
0x180118f15  mov     ebx, 80070057h
0x180118f1a  jmp     short loc_180118ED2
0x180118f1c  mov     rdi, [rdi+8]
0x180118f20  test    rdi, rdi
0x180118f23  jz      short loc_180118F15
0x180118f25  lea     rdx, [rbp+ppvData]; ppvData
0x180118f29  mov     rcx, rdi; psa
0x180118f2c  call    cs:__imp_SafeArrayAccessData
0x180118f32  mov     ebx, eax
0x180118f34  test    eax, eax
0x180118f36  js      short loc_180118ED2
0x180118f38  lea     r8, [rbp+plUbound]; plUbound
0x180118f3c  mov     edx, 1; nDim
0x180118f41  mov     rcx, rdi; psa
0x180118f44  call    cs:__imp_SafeArrayGetUBound
0x180118f4a  mov     ebx, eax
0x180118f4c  test    eax, eax
0x180118f4e  js      short loc_180118ED2
0x180118f50  inc     [rbp+plUbound]
0x180118f53  mov     rcx, rdi; psa
0x180118f56  call    cs:__imp_SafeArrayUnaccessData
0x180118f5c  mov     rax, [rbp+ppvData]
0x180118f60  test    rax, rax
0x180118f63  jz      loc_180118ED2
0x180118f69  mov     ecx, [rbp+plUbound]
0x180118f6c  test    ecx, ecx
0x180118f6e  jz      loc_180118ED2
0x180118f74  mov     [rsp+50h+cbData], ecx; cbData
0x180118f78  mov     r9d, 3; dwType
0x180118f7e  mov     rcx, [rbp+hKey]; hKey
0x180118f82  xor     r8d, r8d; Reserved
0x180118f85  mov     rdx, rsi; lpValueName
0x180118f88  mov     [rsp+50h+phkResult], rax; lpData
0x180118f8d  call    cs:__imp_RegSetValueExW
0x180118f93  test    eax, eax
0x180118f95  jz      loc_180118ED2
0x180118f9b  jg      loc_180118EC9
0x180118fa1  mov     ebx, eax
0x180118fa3  jmp     loc_180118ED2
```
