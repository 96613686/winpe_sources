# SuplNode::SetDwordRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT)

- ea: `0x180118fb0`
- end: `0x1801190d9`
- name: `?SetDwordRegValue@SuplNode@@AEAAJPEAUHKEY__@@PEBG1UtagVARIANT@@@Z`
- size: `297`
- prototype: `int(SuplNode *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180118a88`

## callees

- `0x1800a98c0`
- `0x180118fb0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180118ff9`
- `OLEAUT32!__imp_VariantInit` at `0x180118ff9`
- `OLEAUT32!__imp_VariantClear` at `0x180119043`
- `OLEAUT32!__imp_VariantClear` at `0x180119043`
- `OLEAUT32!__imp_VariantChangeType` at `0x180119082`
- `OLEAUT32!__imp_VariantChangeType` at `0x180119082`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119039`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119039`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180119019`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180119019`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801190be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801190be`

## pseudocode

```c
__int64 __fastcall SuplNode::SetDwordRegValue(
        SuplNode *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct tagVARIANT *pvarSrc)
{
  LSTATUS v7; // eax
  int v8; // ebx
  DWORD cbData; // eax
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 2u, &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 <= 0 )
      goto LABEL_4;
    goto LABEL_3;
  }
  if ( pvarSrc->vt )
  {
    v8 = VariantChangeType(&pvarg, pvarSrc, 0, 0x13u);
    if ( v8 < 0 )
      goto LABEL_4;
    cbData = 4;
    *(_DWORD *)Data = pvarg.lVal;
  }
  else
  {
    v8 = 0;
    cbData = 0;
  }
  v7 = RegSetValueExW(hKey, a4, 0, 4u, Data, cbData);
  if ( v7 )
  {
    if ( v7 > 0 )
    {
LABEL_3:
      v8 = (unsigned __int16)v7 | 0x80070000;
      goto LABEL_4;
    }
    v8 = v7;
  }
LABEL_4:
  if ( hKey )
    RegCloseKey(hKey);
  VariantClear(&pvarg);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180118fb0  mov     [rsp-18h+arg_0], rbx
0x180118fb5  mov     [rsp-18h+arg_8], rsi
0x180118fba  push    rbp
0x180118fbb  push    rdi
0x180118fbc  push    r14
0x180118fbe  mov     rbp, rsp
0x180118fc1  sub     rsp, 60h
0x180118fc5  mov     rax, cs:__security_cookie
0x180118fcc  xor     rax, rsp
0x180118fcf  mov     [rbp+var_8], rax
0x180118fd3  mov     rdi, [rbp+pvarSrc]
0x180118fd7  lea     rcx, [rbp+pvarg]; pvarg
0x180118fdb  xor     r14d, r14d
0x180118fde  xorps   xmm0, xmm0
0x180118fe1  xor     eax, eax
0x180118fe3  mov     [rbp+hKey], r14
0x180118fe7  mov     dword ptr [rbp+Data], r14d
0x180118feb  mov     rsi, r9
0x180118fee  movups  xmmword ptr [rbp+pvarg], xmm0
0x180118ff2  mov     qword ptr [rbp+pvarg+10h], rax
0x180118ff6  mov     rbx, r8
0x180118ff9  call    cs:__imp_VariantInit
0x180118fff  lea     rax, [rbp+hKey]
0x180119003  xor     r8d, r8d; ulOptions
0x180119006  lea     r9d, [r14+2]; samDesired
0x18011900a  mov     [rsp+60h+phkResult], rax; phkResult
0x18011900f  mov     rdx, rbx; lpSubKey
0x180119012  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180119019  call    cs:__imp_RegOpenKeyExW
0x18011901f  mov     ebx, eax
0x180119021  test    eax, eax
0x180119023  jz      short loc_18011906C
0x180119025  jle     short loc_180119030
0x180119027  movzx   ebx, ax
0x18011902a  or      ebx, 80070000h
0x180119030  mov     rcx, [rbp+hKey]; hKey
0x180119034  test    rcx, rcx
0x180119037  jz      short loc_18011903F
0x180119039  call    cs:__imp_RegCloseKey
0x18011903f  lea     rcx, [rbp+pvarg]; pvarg
0x180119043  call    cs:__imp_VariantClear
0x180119049  mov     eax, ebx
0x18011904b  mov     rcx, [rbp+var_8]
0x18011904f  xor     rcx, rsp; StackCookie
0x180119052  call    __security_check_cookie
0x180119057  lea     r11, [rsp+60h+var_s0]
0x18011905c  mov     rbx, [r11+20h]
0x180119060  mov     rsi, [r11+28h]
0x180119064  mov     rsp, r11
0x180119067  pop     r14
0x180119069  pop     rdi
0x18011906a  pop     rbp
0x18011906b  retn
0x18011906c  cmp     [rdi], r14w
0x180119070  jz      short loc_18011909B
0x180119072  mov     r9d, 13h; vt
0x180119078  lea     rcx, [rbp+pvarg]; pvargDest
0x18011907c  xor     r8d, r8d; wFlags
0x18011907f  mov     rdx, rdi; pvarSrc
0x180119082  call    cs:__imp_VariantChangeType
0x180119088  mov     ebx, eax
0x18011908a  test    eax, eax
0x18011908c  js      short loc_180119030
0x18011908e  mov     ecx, dword ptr [rbp+pvarg+8]
0x180119091  mov     eax, 4
0x180119096  mov     dword ptr [rbp+Data], ecx
0x180119099  jmp     short loc_1801190A1
0x18011909b  mov     ebx, r14d
0x18011909e  mov     eax, r14d
0x1801190a1  mov     rcx, [rbp+hKey]; hKey
0x1801190a5  mov     r9d, 4; dwType
0x1801190ab  mov     [rsp+60h+cbData], eax; cbData
0x1801190af  xor     r8d, r8d; Reserved
0x1801190b2  lea     rax, [rbp+Data]
0x1801190b6  mov     rdx, rsi; lpValueName
0x1801190b9  mov     [rsp+60h+phkResult], rax; lpData
0x1801190be  call    cs:__imp_RegSetValueExW
0x1801190c4  test    eax, eax
0x1801190c6  jz      loc_180119030
0x1801190cc  jg      loc_180119027
0x1801190d2  mov     ebx, eax
0x1801190d4  jmp     loc_180119030
```
