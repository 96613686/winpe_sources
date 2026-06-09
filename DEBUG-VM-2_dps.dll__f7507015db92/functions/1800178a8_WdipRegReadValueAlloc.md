# WdipRegReadValueAlloc

- ea: `0x1800178a8`
- end: `0x180017a57`
- name: `WdipRegReadValueAlloc`
- size: `431`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d298`
- `0x18000dc30`
- `0x18000e3d4`
- `0x18000e434`
- `0x18000ed8c`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009090`
- `0x18000a856`
- `0x1800178a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017995`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800179db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017995`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800179db`

## string_xrefs

- `0x180017900`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`
- `0x1800178f9`: `WdipRegReadValueAlloc`

## pseudocode

```c
__int64 __fastcall WdipRegReadValueAlloc(HKEY hKey, LPCWSTR lpValueName, __int64 a3, BYTE **a4, DWORD *a5)
{
  BYTE *v8; // rdi
  int v9; // r8d
  unsigned int v10; // ebx
  DWORD *v11; // rsi
  int v12; // r14d
  LSTATUS i; // eax
  DWORD v14; // ebx
  BYTE *v15; // rax
  LSTATUS v16; // eax
  int v17; // ebx
  DWORD v19; // eax
  LPBYTE lpData; // [rsp+20h] [rbp-20h]
  DWORD cbData[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD lpcbData; // [rsp+90h] [rbp+50h] BYREF
  int v23; // [rsp+94h] [rbp+54h]
  DWORD Type; // [rsp+98h] [rbp+58h] BYREF

  v23 = HIDWORD(a3);
  Type = 0;
  v8 = 0;
  lpcbData = 0;
  cbData[0] = 0;
  if ( !a4 )
  {
    v9 = 599;
LABEL_3:
    LODWORD(lpData) = 87;
    v10 = -2147024809;
    goto LABEL_4;
  }
  v11 = a5;
  if ( !a5 )
  {
    v9 = 600;
    goto LABEL_3;
  }
  *a4 = 0;
  v12 = 0;
  *v11 = 0;
  for ( i = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &lpcbData);
        ;
        i = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &lpcbData) )
  {
    v10 = i;
    if ( i )
    {
      if ( i <= 0 )
        goto LABEL_18;
      v17 = (unsigned __int16)i;
      goto LABEL_17;
    }
    if ( lpcbData > 0xFFFFFFFD )
    {
      v10 = -2147024362;
      goto LABEL_18;
    }
    v14 = lpcbData + 2;
    WdipFree(v8);
    v15 = (BYTE *)WdipAlloc(v14);
    v8 = v15;
    if ( !v15 )
    {
      v10 = -2147024882;
      LODWORD(lpData) = 14;
      v9 = 632;
LABEL_4:
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
        (__int64)L"WdipRegReadValueAlloc",
        v9,
        (const wchar_t *)L"Error = %d",
        lpData);
      goto LABEL_18;
    }
    memset_0(v15, 0, v14);
    cbData[0] = lpcbData;
    v16 = RegQueryValueExW(hKey, lpValueName, 0, &Type, v8, cbData);
    v10 = v16;
    if ( !v16 )
    {
      v19 = cbData[0];
      v10 = 0;
      *a4 = v8;
      v8 = 0;
      *v11 = v19;
      goto LABEL_18;
    }
    if ( v16 != 234 )
      break;
    if ( ++v12 > 8 )
    {
      v10 = -2147024662;
      goto LABEL_18;
    }
    lpcbData = 0;
  }
  if ( v16 > 0 )
  {
    v17 = (unsigned __int16)v16;
LABEL_17:
    v10 = v17 | 0x80070000;
  }
LABEL_18:
  WdipFree(v8);
  return v10;
}

```

## disassembly

```asm
0x1800178a8  mov     [rsp-38h+arg_0], rbx
0x1800178ad  mov     qword ptr [rsp-38h+arg_10], r8
0x1800178b2  push    rbp
0x1800178b3  push    rsi
0x1800178b4  push    rdi
0x1800178b5  push    r12
0x1800178b7  push    r13
0x1800178b9  push    r14
0x1800178bb  push    r15
0x1800178bd  mov     rbp, rsp
0x1800178c0  sub     rsp, 40h
0x1800178c4  mov     r13, rcx
0x1800178c7  mov     r15, r9
0x1800178ca  xor     ecx, ecx
0x1800178cc  mov     r12, rdx
0x1800178cf  mov     [rbp+Type], ecx
0x1800178d2  mov     edi, ecx
0x1800178d4  mov     [rbp+arg_10], ecx
0x1800178d7  mov     [rbp+cbData], ecx
0x1800178da  test    r9, r9
0x1800178dd  jnz     short loc_180017911
0x1800178df  mov     r8d, 257h; int
0x1800178e5  mov     dword ptr [rsp+40h+lpData], 57h ; 'W'; Args
0x1800178ed  mov     ebx, 80070057h
0x1800178f2  lea     r9, aErrorD; "Error = %d"
0x1800178f9  lea     rdx, aWdipregreadval; "WdipRegReadValueAlloc"
0x180017900  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180017907  call    WdipTraceError
0x18001790c  jmp     loc_1800179F8
0x180017911  mov     rsi, [rbp+arg_20]
0x180017915  test    rsi, rsi
0x180017918  jnz     short loc_180017922
0x18001791a  mov     r8d, 258h
0x180017920  jmp     short loc_1800178E5
0x180017922  lea     rax, [rbp+arg_10]
0x180017926  mov     [r9], rcx
0x180017929  mov     [rsp+40h+lpcbData], rax
0x18001792e  mov     r14d, ecx
0x180017931  mov     [rsp+40h+lpData], rcx
0x180017936  mov     [rsi], ecx
0x180017938  jmp     loc_1800179D1
0x18001793d  mov     ebx, [rbp+arg_10]
0x180017940  cmp     ebx, 0FFFFFFFDh
0x180017943  ja      loc_180017A50
0x180017949  mov     rcx, rdi
0x18001794c  add     ebx, 2
0x18001794f  call    WdipFree
0x180017954  mov     ecx, ebx
0x180017956  call    WdipAlloc
0x18001795b  mov     rdi, rax
0x18001795e  test    rax, rax
0x180017961  jz      loc_180017A38
0x180017967  mov     r8d, ebx; Size
0x18001796a  xor     edx, edx; Val
0x18001796c  mov     rcx, rax; void *
0x18001796f  call    memset_0
0x180017974  mov     eax, [rbp+arg_10]
0x180017977  lea     r9, [rbp+Type]; lpType
0x18001797b  mov     [rbp+cbData], eax
0x18001797e  xor     r8d, r8d; lpReserved
0x180017981  lea     rax, [rbp+cbData]
0x180017985  mov     rdx, r12; lpValueName
0x180017988  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001798d  mov     rcx, r13; hKey
0x180017990  mov     [rsp+40h+lpData], rdi; lpData
0x180017995  call    cs:__imp_RegQueryValueExW
0x18001799b  mov     ebx, eax
0x18001799d  test    eax, eax
0x18001799f  jz      loc_180017A2A
0x1800179a5  cmp     eax, 0EAh
0x1800179aa  jnz     short loc_180017A21
0x1800179ac  inc     r14d
0x1800179af  cmp     r14d, 8
0x1800179b3  jg      short loc_180017A1A
0x1800179b5  lea     rax, [rbp+arg_10]
0x1800179b9  mov     [rbp+arg_10], 0
0x1800179c0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800179c5  mov     rdx, r12; lpValueName
0x1800179c8  mov     [rsp+40h+lpData], 0; lpData
0x1800179d1  lea     r9, [rbp+Type]; lpType
0x1800179d5  xor     r8d, r8d; lpReserved
0x1800179d8  mov     rcx, r13; hKey
0x1800179db  call    cs:__imp_RegQueryValueExW
0x1800179e1  mov     ebx, eax
0x1800179e3  test    eax, eax
0x1800179e5  jz      loc_18001793D
0x1800179eb  test    eax, eax
0x1800179ed  jle     short loc_1800179F8
0x1800179ef  movzx   ebx, bx
0x1800179f2  or      ebx, 80070000h
0x1800179f8  mov     rcx, rdi
0x1800179fb  call    WdipFree
0x180017a00  mov     eax, ebx
0x180017a02  mov     rbx, [rsp+40h+arg_0]
0x180017a0a  add     rsp, 40h
0x180017a0e  pop     r15
0x180017a10  pop     r14
0x180017a12  pop     r13
0x180017a14  pop     r12
0x180017a16  pop     rdi
0x180017a17  pop     rsi
0x180017a18  pop     rbp
0x180017a19  retn
0x180017a1a  mov     ebx, 800700EAh
0x180017a1f  jmp     short loc_1800179F8
0x180017a21  test    eax, eax
0x180017a23  jle     short loc_1800179F8
0x180017a25  movzx   ebx, ax
0x180017a28  jmp     short loc_1800179F2
0x180017a2a  mov     eax, [rbp+cbData]
0x180017a2d  xor     ebx, ebx
0x180017a2f  mov     [r15], rdi
0x180017a32  xor     edi, edi
0x180017a34  mov     [rsi], eax
0x180017a36  jmp     short loc_1800179F8
0x180017a38  mov     ebx, 8007000Eh
0x180017a3d  mov     dword ptr [rsp+40h+lpData], 0Eh
0x180017a45  mov     r8d, 278h
0x180017a4b  jmp     loc_1800178F2
0x180017a50  mov     ebx, 80070216h
0x180017a55  jmp     short loc_1800179F8
```
