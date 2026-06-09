# Common::RegistryKey::GetStringValue(ushort const *,ulong,ulong *,ushort *,ulong *)

- ea: `0x18000fafc`
- end: `0x18000fbe1`
- name: `?GetStringValue@RegistryKey@Common@@QEAAJPEBGKPEAKPEAG1@Z`
- size: `229`
- prototype: `__int64 __fastcall(Common::RegistryKey *__hidden this, const unsigned __int16 *, unsigned int, unsigned int *, LPBYTE, LPDWORD lpType)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c698`

## callees

- `0x18000fafc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fb3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fb3c`

## pseudocode

```c
__int64 __fastcall Common::RegistryKey::GetStringValue(
        HKEY *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4,
        LPBYTE lpData,
        LPDWORD lpType)
{
  LPDWORD v6; // rdi
  LPBYTE v7; // rbx
  HKEY v9; // rcx
  LSTATUS v11; // eax
  int v12; // edx
  DWORD v14; // r8d
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF

  v6 = lpType;
  v7 = lpData;
  v9 = *this;
  cbData = 2 * a3;
  v11 = RegQueryValueExW(v9, a2, 0, lpType, lpData, &cbData);
  v12 = v11;
  if ( !v11 || v11 == 234 )
  {
    if ( v6 && *v6 > 2 && *v6 != 7 )
      return 2147944204LL;
    if ( (cbData & 1) != 0 )
      return 2147942413LL;
    v14 = cbData >> 1;
    if ( cbData >> 1 )
    {
      if ( v11 || !v7 )
      {
        --v14;
      }
      else if ( *(_WORD *)&v7[2 * v14 - 2] )
      {
        if ( v14 + 1 > a3 )
        {
          ++v14;
          v12 = 234;
        }
        else
        {
          *(_WORD *)&v7[2 * v14] = 0;
        }
      }
      else
      {
        --v14;
      }
    }
    if ( a4 )
      *a4 = v14;
    if ( v12 > 0 )
    {
      v12 = (unsigned __int16)v12;
      goto LABEL_24;
    }
  }
  else if ( v11 > 0 )
  {
    v12 = (unsigned __int16)v11;
LABEL_24:
    v12 |= 0x80070000;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000fafc  push    rbx
0x18000fafe  push    rsi
0x18000faff  push    rdi
0x18000fb00  push    r14
0x18000fb02  sub     rsp, 38h
0x18000fb06  mov     rdi, [rsp+58h+lpType]
0x18000fb0e  lea     eax, [r8+r8]
0x18000fb12  mov     rbx, [rsp+58h+arg_20]
0x18000fb1a  mov     rsi, r9
0x18000fb1d  mov     rcx, [rcx]; hKey
0x18000fb20  mov     r14d, r8d
0x18000fb23  mov     [rsp+58h+cbData], eax
0x18000fb27  mov     r9, rdi; lpType
0x18000fb2a  lea     rax, [rsp+58h+cbData]
0x18000fb2f  xor     r8d, r8d; lpReserved
0x18000fb32  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000fb37  mov     [rsp+58h+lpData], rbx; lpData
0x18000fb3c  call    cs:__imp_RegQueryValueExW
0x18000fb42  xor     r9d, r9d
0x18000fb45  mov     r10d, 0EAh
0x18000fb4b  mov     edx, eax
0x18000fb4d  test    eax, eax
0x18000fb4f  jz      short loc_18000FB5F
0x18000fb51  cmp     eax, r10d
0x18000fb54  jz      short loc_18000FB5F
0x18000fb56  test    eax, eax
0x18000fb58  jle     short loc_18000FBD5
0x18000fb5a  movzx   edx, ax
0x18000fb5d  jmp     short loc_18000FBCF
0x18000fb5f  test    rdi, rdi
0x18000fb62  jz      short loc_18000FB75
0x18000fb64  cmp     dword ptr [rdi], 2
0x18000fb67  jbe     short loc_18000FB75
0x18000fb69  cmp     dword ptr [rdi], 7
0x18000fb6c  jz      short loc_18000FB75
0x18000fb6e  mov     eax, 8007070Ch
0x18000fb73  jmp     short loc_18000FBD7
0x18000fb75  mov     r8d, [rsp+58h+cbData]
0x18000fb7a  test    r8b, 1
0x18000fb7e  jz      short loc_18000FB87
0x18000fb80  mov     eax, 8007000Dh
0x18000fb85  jmp     short loc_18000FBD7
0x18000fb87  shr     r8d, 1
0x18000fb8a  jz      short loc_18000FBC0
0x18000fb8c  test    eax, eax
0x18000fb8e  jnz     short loc_18000FBBD
0x18000fb90  test    rbx, rbx
0x18000fb93  jz      short loc_18000FBBD
0x18000fb95  lea     ecx, [r8-1]
0x18000fb99  cmp     [rbx+rcx*2], r9w
0x18000fb9e  jnz     short loc_18000FBA5
0x18000fba0  mov     r8d, ecx
0x18000fba3  jmp     short loc_18000FBC0
0x18000fba5  lea     eax, [r8+1]
0x18000fba9  cmp     eax, r14d
0x18000fbac  ja      short loc_18000FBB5
0x18000fbae  mov     [rbx+r8*2], r9w
0x18000fbb3  jmp     short loc_18000FBC0
0x18000fbb5  mov     r8d, eax
0x18000fbb8  mov     edx, r10d
0x18000fbbb  jmp     short loc_18000FBC0
0x18000fbbd  dec     r8d
0x18000fbc0  test    rsi, rsi
0x18000fbc3  jz      short loc_18000FBC8
0x18000fbc5  mov     [rsi], r8d
0x18000fbc8  test    edx, edx
0x18000fbca  jle     short loc_18000FBD5
0x18000fbcc  movzx   edx, dx
0x18000fbcf  or      edx, 80070000h
0x18000fbd5  mov     eax, edx
0x18000fbd7  add     rsp, 38h
0x18000fbdb  pop     r14
0x18000fbdd  pop     rdi
0x18000fbde  pop     rsi
0x18000fbdf  pop     rbx
0x18000fbe0  retn
```
