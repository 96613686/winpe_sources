# SuplNode::SetStringRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT)

- ea: `0x1801190e0`
- end: `0x18011924b`
- name: `?SetStringRegValue@SuplNode@@AEAAJPEAUHKEY__@@PEBG1UtagVARIANT@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(SuplNode *this, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *pvarSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180118a88`

## callees

- `0x1800a98c0`
- `0x1801190e0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180119123`
- `OLEAUT32!__imp_VariantInit` at `0x180119123`
- `OLEAUT32!__imp_VariantClear` at `0x180119226`
- `OLEAUT32!__imp_VariantClear` at `0x180119226`
- `OLEAUT32!__imp_VariantChangeType` at `0x180119168`
- `OLEAUT32!__imp_VariantChangeType` at `0x180119168`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011921b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011921b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180119144`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180119144`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801191f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801191f6`

## pseudocode

```c
__int64 __fastcall SuplNode::SetStringRegValue(
        SuplNode *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct tagVARIANT *pvarSrc)
{
  LSTATUS v7; // eax
  signed int v8; // ebx
  bool v9; // cc
  const BYTE *pbVal; // r8
  BSTR bstrVal; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  DWORD cbData; // ecx
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG pvargDest; // [rsp+38h] [rbp-40h] BYREF

  memset(&pvargDest, 0, sizeof(pvargDest));
  hKey = 0;
  VariantInit(&pvargDest);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 2u, &hKey);
  v8 = v7;
  v9 = v7 <= 0;
  if ( v7 )
    goto LABEL_15;
  if ( pvarSrc->vt )
  {
    v8 = VariantChangeType(&pvargDest, pvarSrc, 0, 8u);
    if ( v8 < 0 )
      goto LABEL_17;
    pbVal = pvargDest.pbVal;
    if ( !pvargDest.llVal )
    {
      v8 = -2147024809;
      goto LABEL_17;
    }
    bstrVal = pvargDest.bstrVal;
    v12 = 0x7FFFFFFF;
    do
    {
      if ( !*bstrVal )
        break;
      ++bstrVal;
      --v12;
    }
    while ( v12 );
    v8 = v12 == 0 ? 0x80070057 : 0;
    if ( !v12 )
      goto LABEL_17;
    v13 = (2 * (0x7FFFFFFF - v12)) & -(__int64)(v12 != 0);
    cbData = v13 + 2;
    if ( v13 + 2 < v13 )
    {
      v8 = -2147024362;
      goto LABEL_17;
    }
  }
  else
  {
    pbVal = 0;
    cbData = 0;
  }
  v7 = RegSetValueExW(hKey, a4, 0, 1u, pbVal, cbData);
  v8 = v7;
  v9 = v7 <= 0;
  if ( v7 )
  {
LABEL_15:
    if ( !v9 )
      v8 = (unsigned __int16)v7 | 0x80070000;
  }
  else
  {
    v8 = 0;
  }
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  VariantClear(&pvargDest);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801190e0  mov     r11, rsp
0x1801190e3  mov     [r11+8], rbx
0x1801190e7  push    rbp
0x1801190e8  push    rsi
0x1801190e9  push    rdi
0x1801190ea  sub     rsp, 60h
0x1801190ee  mov     rax, cs:__security_cookie
0x1801190f5  xor     rax, rsp
0x1801190f8  mov     [rsp+78h+var_28], rax
0x1801190fd  mov     rdi, [rsp+78h+pvarSrc]
0x180119105  lea     rcx, [r11-40h]; pvarg
0x180119109  xorps   xmm0, xmm0
0x18011910c  xor     eax, eax
0x18011910e  movups  xmmword ptr [rsp+78h+pvargDest], xmm0
0x180119113  xor     ebp, ebp
0x180119115  mov     [r11-30h], rax
0x180119119  mov     rsi, r9
0x18011911c  mov     [r11-48h], rbp
0x180119120  mov     rbx, r8
0x180119123  call    cs:__imp_VariantInit
0x180119129  lea     rax, [rsp+78h+hKey]
0x18011912e  xor     r8d, r8d; ulOptions
0x180119131  lea     r9d, [rbp+2]; samDesired
0x180119135  mov     [rsp+78h+phkResult], rax; phkResult
0x18011913a  mov     rdx, rbx; lpSubKey
0x18011913d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180119144  call    cs:__imp_RegOpenKeyExW
0x18011914a  mov     ebx, eax
0x18011914c  test    eax, eax
0x18011914e  jnz     loc_180119206
0x180119154  cmp     [rdi], bp
0x180119157  jz      short loc_1801191D6
0x180119159  lea     r9d, [rbp+8]; vt
0x18011915d  xor     r8d, r8d; wFlags
0x180119160  mov     rdx, rdi; pvarSrc
0x180119163  lea     rcx, [rsp+78h+pvargDest]; pvargDest
0x180119168  call    cs:__imp_VariantChangeType
0x18011916e  mov     ebx, eax
0x180119170  test    eax, eax
0x180119172  js      loc_180119211
0x180119178  mov     r8, qword ptr [rsp+78h+pvargDest+8]
0x18011917d  test    r8, r8
0x180119180  jz      short loc_1801191CF
0x180119182  mov     edx, 7FFFFFFFh
0x180119187  mov     rax, r8
0x18011918a  mov     ecx, edx
0x18011918c  cmp     [rax], bp
0x18011918f  jz      short loc_18011919B
0x180119191  add     rax, 2
0x180119195  sub     rcx, 1
0x180119199  jnz     short loc_18011918C
0x18011919b  mov     rax, rcx
0x18011919e  neg     rax
0x1801191a1  sbb     ebx, ebx
0x1801191a3  not     ebx
0x1801191a5  and     ebx, 80070057h
0x1801191ab  test    rcx, rcx
0x1801191ae  jz      short loc_180119211
0x1801191b0  sub     rdx, rcx
0x1801191b3  add     rdx, rdx
0x1801191b6  neg     rcx
0x1801191b9  sbb     rax, rax
0x1801191bc  and     rax, rdx
0x1801191bf  lea     rcx, [rax+2]
0x1801191c3  cmp     rcx, rax
0x1801191c6  jnb     short loc_1801191DC
0x1801191c8  mov     ebx, 80070216h
0x1801191cd  jmp     short loc_180119211
0x1801191cf  mov     ebx, 80070057h
0x1801191d4  jmp     short loc_180119211
0x1801191d6  mov     r8, rbp
0x1801191d9  mov     rcx, rbp
0x1801191dc  mov     [rsp+78h+cbData], ecx; cbData
0x1801191e0  mov     r9d, 1; dwType
0x1801191e6  mov     rcx, [rsp+78h+hKey]; hKey
0x1801191eb  mov     rdx, rsi; lpValueName
0x1801191ee  mov     [rsp+78h+phkResult], r8; lpData
0x1801191f3  xor     r8d, r8d; Reserved
0x1801191f6  call    cs:__imp_RegSetValueExW
0x1801191fc  mov     ebx, eax
0x1801191fe  test    eax, eax
0x180119200  jnz     short loc_180119206
0x180119202  mov     ebx, ebp
0x180119204  jmp     short loc_180119211
0x180119206  jle     short loc_180119211
0x180119208  movzx   ebx, ax
0x18011920b  or      ebx, 80070000h
0x180119211  mov     rcx, [rsp+78h+hKey]; hKey
0x180119216  test    rcx, rcx
0x180119219  jz      short loc_180119221
0x18011921b  call    cs:__imp_RegCloseKey
0x180119221  lea     rcx, [rsp+78h+pvargDest]; pvarg
0x180119226  call    cs:__imp_VariantClear
0x18011922c  mov     eax, ebx
0x18011922e  mov     rcx, [rsp+78h+var_28]
0x180119233  xor     rcx, rsp; StackCookie
0x180119236  call    __security_check_cookie
0x18011923b  mov     rbx, [rsp+78h+arg_0]
0x180119243  add     rsp, 60h
0x180119247  pop     rdi
0x180119248  pop     rsi
0x180119249  pop     rbp
0x18011924a  retn
```
