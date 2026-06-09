# ReadRpcPolicy

- ea: `0x18000654c`
- end: `0x180006624`
- name: `ReadRpcPolicy`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000662c`

## callees

- `0x18000654c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800065f2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800065f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800065a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800065a7`

## pseudocode

```c
__int64 __fastcall ReadRpcPolicy(__int64 a1, const WCHAR *a2, _DWORD *a3, _DWORD *a4)
{
  LSTATUS v7; // eax
  bool v8; // zf
  LSTATUS ValueW; // edi
  int pvData; // [rsp+60h] [rbp+8h] BYREF
  int v12; // [rsp+64h] [rbp+Ch]
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+78h] [rbp+20h] BYREF

  v12 = HIDWORD(a1);
  hkey = 0;
  pvData = 0;
  pcbData = 4;
  *a4 = 0;
  *a3 = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc", 0, 0x20019u, &hkey);
  if ( v7 )
  {
    v8 = v7 == 2;
  }
  else
  {
    ValueW = RegGetValueW(hkey, 0, a2, 0x18u, 0, &pvData, &pcbData);
    RegCloseKey(hkey);
    if ( !ValueW )
    {
      *a4 = pvData;
      *a3 = 1;
      return 0;
    }
    v8 = ValueW == 2;
  }
  if ( !v8 )
    return 14;
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000654c  mov     rax, rsp
0x18000654f  mov     [rax+8], rcx
0x180006553  push    rbx
0x180006554  push    rsi
0x180006555  push    rdi
0x180006556  sub     rsp, 40h
0x18000655a  mov     qword ptr [rax+20h], 0
0x180006562  mov     rsi, r9
0x180006565  mov     dword ptr [rax+8], 0
0x18000656c  mov     rbx, r8
0x18000656f  mov     dword ptr [rax+18h], 4
0x180006576  lea     rax, [rax+20h]
0x18000657a  mov     rdi, rdx
0x18000657d  mov     dword ptr [r9], 0
0x180006584  mov     dword ptr [r8], 0
0x18000658b  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Rpc"
0x180006592  mov     r9d, 20019h; samDesired
0x180006598  mov     [rsp+58h+phkResult], rax; phkResult
0x18000659d  xor     r8d, r8d; ulOptions
0x1800065a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800065a7  call    cs:__imp_RegOpenKeyExW
0x1800065ad  test    eax, eax
0x1800065af  jz      short loc_1800065C5
0x1800065b1  cmp     eax, 2
0x1800065b4  jnz     short loc_1800065BE
0x1800065b6  mov     dword ptr [rbx], 0
0x1800065bc  jmp     short loc_18000661A
0x1800065be  mov     eax, 0Eh
0x1800065c3  jmp     short loc_18000661C
0x1800065c5  mov     rcx, [rsp+58h+hkey]; hkey
0x1800065ca  lea     rax, [rsp+58h+arg_10]
0x1800065cf  mov     [rsp+58h+pcbData], rax; pcbData
0x1800065d4  mov     r9d, 18h; dwFlags
0x1800065da  lea     rax, [rsp+58h+arg_0]
0x1800065df  mov     r8, rdi; lpValue
0x1800065e2  mov     [rsp+58h+pvData], rax; pvData
0x1800065e7  xor     edx, edx; lpSubKey
0x1800065e9  mov     [rsp+58h+phkResult], 0; pdwType
0x1800065f2  call    cs:__imp_RegGetValueW
0x1800065f8  mov     rcx, [rsp+58h+hkey]; hKey
0x1800065fd  mov     edi, eax
0x1800065ff  call    cs:__imp_RegCloseKey
0x180006605  test    edi, edi
0x180006607  jz      short loc_18000660E
0x180006609  cmp     edi, 2
0x18000660c  jmp     short loc_1800065B4
0x18000660e  mov     eax, [rsp+58h+arg_0]
0x180006612  mov     [rsi], eax
0x180006614  mov     dword ptr [rbx], 1
0x18000661a  xor     eax, eax
0x18000661c  add     rsp, 40h
0x180006620  pop     rdi
0x180006621  pop     rsi
0x180006622  pop     rbx
0x180006623  retn
```
