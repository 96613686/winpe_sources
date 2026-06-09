# GetLockScreenInboxAssetLocation(ushort * *)

- ea: `0x180021aec`
- end: `0x180021d70`
- name: `?GetLockScreenInboxAssetLocation@@YAJPEAPEAG@Z`
- size: `644`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800219d4`
- `0x1800b8e98`

## callees

- `0x180021aec`
- `0x180034db4`
- `0x180050ba0`
- `0x180051524`
- `0x180056c06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021ba3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021ba3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021b3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021b3d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021b83`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021d4b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021b83`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d65`

## pseudocode

```c
__int64 __fastcall GetLockScreenInboxAssetLocation(LPVOID *a1)
{
  LSTATUS v2; // ebx
  LSTATUS ValueW; // eax
  bool v4; // sf
  unsigned int v5; // ebx
  unsigned __int16 *v7; // rcx
  __int64 v8; // r10
  unsigned __int16 *pvData; // rax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // r9
  __int64 v12; // rcx
  const wchar_t *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r11
  __int64 v16; // rdi
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  hkey = HKEY_LOCAL_MACHINE;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen", 0, 1u, &hkey);
  if ( v2 )
    goto LABEL_21;
  pcbData = 256;
  ValueW = RegGetValueW(hkey, 0, L"DefaultAssetLocation", 2u, 0, Src, &pcbData);
  v2 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = (unsigned __int16 *)CoTaskMemAlloc(pcbData);
    *a1 = pvData;
    if ( pvData )
    {
      if ( v2 )
      {
        if ( RegGetValueW(hkey, 0, L"DefaultAssetLocation", 2u, 0, pvData, &pcbData) )
        {
          v2 = 1003;
          CoTaskMemFree(*a1);
        }
        else
        {
          v2 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v2 = 14;
    }
  }
  RegCloseKey(hkey);
  v4 = v2 < 0;
  if ( v2 )
  {
LABEL_21:
    *a1 = 0;
    v4 = v2 < 0;
    if ( v2 > 0 )
      v4 = 1;
  }
  if ( v4 )
  {
    *a1 = 0;
    if ( !is_mul_ok(0x18u, 2u) )
    {
      v5 = -2147024362;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE,
        (unsigned int)"Internal\\Shell\\Inc\\LockScreenInboxAssets.h",
        (const char *)v5,
        phkResult);
      return v5;
    }
    v10 = (unsigned __int16 *)CoTaskMemAlloc(0x30u);
    *a1 = v10;
    v11 = v10;
    v5 = v10 == 0 ? 0x8007000E : 0;
    if ( !v10 )
      goto LABEL_8;
    v12 = 23;
    v13 = L"%SystemRoot%\\Web\\Screen";
    v14 = 24;
    v15 = 0;
    do
    {
      if ( !v12 )
        break;
      if ( !*v13 )
        break;
      *v10++ = *v13++;
      --v12;
      ++v15;
      --v14;
    }
    while ( v14 );
    v7 = v10 - 1;
    v8 = v15 - 1;
    if ( v14 )
    {
      v7 = v10;
      v8 = v15;
    }
    *v7 = 0;
    if ( v14 )
    {
      v16 = 24 - v8;
      if ( v8 != 24 && v8 != 23 && (unsigned __int64)(2 * v16) > 2 )
        memset_0(&v11[v8 + 1], 0, 2 * v16 - 2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180021aec  mov     [rsp-8+arg_8], rbx
0x180021af1  mov     [rsp-8+arg_10], rsi
0x180021af6  push    rbp
0x180021af7  push    rdi
0x180021af8  push    r14
0x180021afa  lea     rbp, [rsp-60h]
0x180021aff  sub     rsp, 160h
0x180021b06  mov     rax, cs:__security_cookie
0x180021b0d  xor     rax, rsp
0x180021b10  mov     [rbp+70h+var_20], rax
0x180021b14  mov     rsi, rcx
0x180021b17  lea     rax, [rsp+170h+hkey]
0x180021b1c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021b23  mov     [rsp+170h+phkResult], rax; phkResult
0x180021b28  mov     r9d, 1; samDesired
0x180021b2e  mov     [rsp+170h+hkey], rcx
0x180021b33  xor     r8d, r8d; ulOptions
0x180021b36  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180021b3d  call    cs:__imp_RegOpenKeyExW
0x180021b43  xor     r14d, r14d
0x180021b46  mov     ebx, eax
0x180021b48  test    eax, eax
0x180021b4a  jnz     loc_180021CBA
0x180021b50  mov     rcx, [rsp+170h+hkey]; hkey
0x180021b55  lea     rax, [rsp+170h+var_130]
0x180021b5a  mov     [rsp+170h+pcbData], rax; pcbData
0x180021b5f  lea     r9d, [rbx+2]; dwFlags
0x180021b63  lea     rax, [rsp+170h+Src]
0x180021b68  mov     [rsp+170h+var_130], 100h
0x180021b70  mov     [rsp+170h+pvData], rax; pvData
0x180021b75  lea     r8, aDefaultassetlo; "DefaultAssetLocation"
0x180021b7c  xor     edx, edx; lpSubKey
0x180021b7e  mov     [rsp+170h+phkResult], r14; int
0x180021b83  call    cs:__imp_RegGetValueW
0x180021b89  mov     ebx, eax
0x180021b8b  test    eax, eax
0x180021b8d  jz      loc_180021C2E
0x180021b93  cmp     eax, 0EAh
0x180021b98  jz      loc_180021C2E
0x180021b9e  mov     rcx, [rsp+170h+hkey]; hKey
0x180021ba3  call    cs:__imp_RegCloseKey
0x180021ba9  test    ebx, ebx
0x180021bab  jnz     loc_180021CBA
0x180021bb1  jns     short loc_180021C08
0x180021bb3  mov     edi, 18h
0x180021bb8  mov     [rsi], r14
0x180021bbb  lea     eax, [rdi-16h]
0x180021bbe  mul     rdi
0x180021bc1  test    rdx, rdx
0x180021bc4  jz      loc_180021C4C
0x180021bca  mov     ebx, 80070216h
0x180021bcf  mov     rcx, [rbp+78h]; this
0x180021bd3  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\LockScreenInboxAs"...
0x180021bda  mov     r9d, ebx; char *
0x180021bdd  mov     edx, 0Eh; void *
0x180021be2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021be7  mov     eax, ebx
0x180021be9  jmp     short loc_180021C0A
0x180021beb  test    rdx, rdx
0x180021bee  lea     rcx, [rax-2]
0x180021bf2  lea     r10, [r11-1]
0x180021bf6  cmovnz  rcx, rax
0x180021bfa  cmovnz  r10, r11
0x180021bfe  mov     [rcx], r14w
0x180021c02  jnz     loc_180021CD5
0x180021c08  xor     eax, eax
0x180021c0a  mov     rcx, [rbp+70h+var_20]
0x180021c0e  xor     rcx, rsp; StackCookie
0x180021c11  call    __security_check_cookie
0x180021c16  lea     r11, [rsp+170h+var_10]
0x180021c1e  mov     rbx, [r11+28h]
0x180021c22  mov     rsi, [r11+30h]
0x180021c26  mov     rsp, r11
0x180021c29  pop     r14
0x180021c2b  pop     rdi
0x180021c2c  pop     rbp
0x180021c2d  retn
0x180021c2e  mov     ecx, [rsp+170h+var_130]; cb
0x180021c32  call    cs:__imp_CoTaskMemAlloc
0x180021c38  mov     [rsi], rax
0x180021c3b  test    rax, rax
0x180021c3e  jnz     loc_180021D08
0x180021c44  lea     ebx, [rax+0Eh]
0x180021c47  jmp     loc_180021B9E
0x180021c4c  mov     rcx, rax; cb
0x180021c4f  call    cs:__imp_CoTaskMemAlloc
0x180021c55  mov     rcx, rax
0x180021c58  mov     [rsi], rax
0x180021c5b  neg     rcx
0x180021c5e  mov     r9, rax
0x180021c61  sbb     ebx, ebx
0x180021c63  not     ebx
0x180021c65  and     ebx, 8007000Eh
0x180021c6b  test    rax, rax
0x180021c6e  jz      loc_180021BCF
0x180021c74  mov     ecx, 17h
0x180021c79  lea     r8, aSystemrootWebS; "%SystemRoot%\\Web\\Screen"
0x180021c80  mov     rdx, rdi
0x180021c83  mov     r11, r14
0x180021c86  test    rcx, rcx
0x180021c89  jz      loc_180021BEB
0x180021c8f  movzx   r10d, word ptr [r8]
0x180021c93  test    r10w, r10w
0x180021c97  jz      loc_180021BEB
0x180021c9d  mov     [rax], r10w
0x180021ca1  add     r8, 2
0x180021ca5  add     rax, 2
0x180021ca9  dec     rcx
0x180021cac  inc     r11
0x180021caf  sub     rdx, 1
0x180021cb3  jnz     short loc_180021C86
0x180021cb5  jmp     loc_180021BEB
0x180021cba  mov     [rsi], r14
0x180021cbd  test    ebx, ebx
0x180021cbf  jle     loc_180021BB1
0x180021cc5  movzx   ebx, bx
0x180021cc8  or      ebx, 80070000h
0x180021cce  test    ebx, ebx
0x180021cd0  jmp     loc_180021BB1
0x180021cd5  sub     rdi, r10
0x180021cd8  cmp     rdi, 1
0x180021cdc  jbe     loc_180021C08
0x180021ce2  lea     r8, [rdi+rdi]
0x180021ce6  cmp     r8, 2
0x180021cea  jbe     loc_180021C08
0x180021cf0  add     r9, 2
0x180021cf4  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180021cf8  xor     edx, edx; Val
0x180021cfa  lea     rcx, [r9+r10*2]; void *
0x180021cfe  call    memset_0
0x180021d03  jmp     loc_180021C08
0x180021d08  test    ebx, ebx
0x180021d0a  jnz     short loc_180021D23
0x180021d0c  mov     r8d, [rsp+170h+var_130]; Size
0x180021d11  lea     rdx, [rsp+170h+Src]; Src
0x180021d16  mov     rcx, rax; void *
0x180021d19  call    memcpy_0
0x180021d1e  jmp     loc_180021B9E
0x180021d23  lea     rcx, [rsp+170h+var_130]
0x180021d28  mov     r9d, 2; dwFlags
0x180021d2e  mov     [rsp+170h+pcbData], rcx; pcbData
0x180021d33  lea     r8, aDefaultassetlo; "DefaultAssetLocation"
0x180021d3a  mov     rcx, [rsp+170h+hkey]; hkey
0x180021d3f  xor     edx, edx; lpSubKey
0x180021d41  mov     [rsp+170h+pvData], rax; pvData
0x180021d46  mov     [rsp+170h+phkResult], r14; pdwType
0x180021d4b  call    cs:__imp_RegGetValueW
0x180021d51  test    eax, eax
0x180021d53  jnz     short loc_180021D5D
0x180021d55  mov     ebx, r14d
0x180021d58  jmp     loc_180021B9E
0x180021d5d  mov     rcx, [rsi]; pv
0x180021d60  mov     ebx, 3EBh
0x180021d65  call    cs:__imp_CoTaskMemFree
0x180021d6b  jmp     loc_180021B9E
```
