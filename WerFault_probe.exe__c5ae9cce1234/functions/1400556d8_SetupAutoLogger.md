# SetupAutoLogger

- ea: `0x1400556d8`
- end: `0x1400558f5`
- name: `SetupAutoLogger`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140055a08`

## callees

- `0x1400556d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400558e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400558e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005573f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005573f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140055779`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400557af`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400557da`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140055805`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140055872`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005589c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400558c7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140055779`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400557af`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400557da`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140055805`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140055872`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005589c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400558c7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x1400558d7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x1400558d7`

## pseudocode

```c
LSTATUS __fastcall SetupAutoLogger(unsigned __int16 *a1)
{
  LSTATUS result; // eax
  HKEY v3; // rcx
  __int64 v4; // rax
  unsigned __int16 *v5; // rcx
  unsigned int v6; // edx
  unsigned int v7; // r8d
  const void *v8; // rcx
  int Data; // [rsp+78h] [rbp+28h] BYREF
  DWORD v10; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  v10 = 0;
  Data = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger\\Microsoft-OCA-IPT",
             0,
             0,
             0,
             0xF003Fu,
             0,
             &hKey,
             &v10);
  if ( !result )
  {
    v3 = hKey;
    if ( v10 == 2 )
      return RegCloseKey(v3);
    if ( RegSetKeyValueW(hKey, 0, L"BufferSize", 4u, a1 + 24, 4u)
      || RegSetKeyValueW(hKey, 0, L"Guid", 1u, L"{C712AF3D-ED1E-46A9-B843-E9014D29CAEE}", 0x4Eu)
      || RegSetKeyValueW(hKey, 0, L"LogFileMode", 4u, a1 + 32, 4u)
      || RegSetKeyValueW(hKey, 0, L"MinimumBuffers", 4u, a1 + 26, 4u) )
    {
LABEL_17:
      RegDeleteKeyA(hKey, 0);
LABEL_18:
      v3 = hKey;
      return RegCloseKey(v3);
    }
    if ( *((int *)a1 + 18) < 0 )
    {
      v4 = a1[36];
      v5 = (unsigned __int16 *)((char *)a1 + v4 + 4);
      v6 = 0;
      v7 = *(unsigned __int16 *)((char *)a1 + v4 + 2);
      if ( *(unsigned __int16 *)((char *)a1 + v4 + 2) )
      {
        while ( v5[1] != 1 )
        {
          ++v6;
          v5 += 2 * *v5;
          if ( v6 >= v7 )
            goto LABEL_11;
        }
        goto LABEL_12;
      }
LABEL_11:
      if ( v6 < v7 )
      {
LABEL_12:
        v8 = v5 + 2;
LABEL_14:
        if ( !RegSetKeyValueW(hKey, 0, L"EnableKernelFlags", 3u, v8, 0x20u) )
        {
          Data = 0;
          if ( !RegSetKeyValueW(hKey, 0, L"Status", 4u, &Data, 4u) )
          {
            Data = 1;
            if ( !RegSetKeyValueW(hKey, 0, L"Start", 4u, &Data, 4u) )
              goto LABEL_18;
          }
        }
        goto LABEL_17;
      }
    }
    v8 = 0;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x1400556d8  mov     r11, rsp
0x1400556db  mov     [r11+8], rbx
0x1400556df  push    rbp
0x1400556e0  push    rsi
0x1400556e1  push    r14
0x1400556e3  mov     rbp, rsp
0x1400556e6  sub     rsp, 50h
0x1400556ea  lea     rax, [rbp+arg_10]
0x1400556ee  mov     [rbp+hKey], 0
0x1400556f6  mov     [r11-28h], rax
0x1400556fa  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x140055701  lea     rax, [rbp+hKey]
0x140055705  mov     [rbp+arg_10], 0
0x14005570c  mov     [r11-30h], rax
0x140055710  mov     rbx, rcx
0x140055713  mov     qword ptr [r11-38h], 0
0x14005571b  xor     r9d, r9d; lpClass
0x14005571e  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x140055726  xor     r8d, r8d; Reserved
0x140055729  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140055730  mov     [rsp+50h+dwOptions], 0; dwOptions
0x140055738  mov     [rbp+Data], 0
0x14005573f  call    cs:__imp_RegCreateKeyExW
0x140055745  test    eax, eax
0x140055747  jnz     loc_1400558E7
0x14005574d  cmp     [rbp+arg_10], 2
0x140055751  mov     rcx, [rbp+hKey]; hKey
0x140055755  jz      loc_1400558E1
0x14005575b  mov     esi, 4
0x140055760  lea     rax, [rbx+30h]
0x140055764  mov     [rsp+50h+samDesired], esi; cbData
0x140055768  lea     r8, aBuffersize; "BufferSize"
0x14005576f  mov     r9d, esi; dwType
0x140055772  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140055777  xor     edx, edx; lpSubKey
0x140055779  call    cs:__imp_RegSetKeyValueW
0x14005577f  test    eax, eax
0x140055781  jnz     loc_1400558D1
0x140055787  mov     rcx, [rbp+hKey]; hKey
0x14005578b  lea     rax, aC712af3dEd1e46; "{C712AF3D-ED1E-46A9-B843-E9014D29CAEE}"
0x140055792  lea     r14d, [rsi-3]
0x140055796  mov     [rsp+50h+samDesired], 4Eh ; 'N'; cbData
0x14005579e  mov     r9d, r14d; dwType
0x1400557a1  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1400557a6  lea     r8, aGuid; "Guid"
0x1400557ad  xor     edx, edx; lpSubKey
0x1400557af  call    cs:__imp_RegSetKeyValueW
0x1400557b5  test    eax, eax
0x1400557b7  jnz     loc_1400558D1
0x1400557bd  mov     rcx, [rbp+hKey]; hKey
0x1400557c1  lea     rax, [rbx+40h]
0x1400557c5  mov     [rsp+50h+samDesired], esi; cbData
0x1400557c9  lea     r8, aLogfilemode; "LogFileMode"
0x1400557d0  mov     r9d, esi; dwType
0x1400557d3  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1400557d8  xor     edx, edx; lpSubKey
0x1400557da  call    cs:__imp_RegSetKeyValueW
0x1400557e0  test    eax, eax
0x1400557e2  jnz     loc_1400558D1
0x1400557e8  mov     rcx, [rbp+hKey]; hKey
0x1400557ec  lea     rax, [rbx+34h]
0x1400557f0  mov     [rsp+50h+samDesired], esi; cbData
0x1400557f4  lea     r8, aMinimumbuffers; "MinimumBuffers"
0x1400557fb  mov     r9d, esi; dwType
0x1400557fe  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140055803  xor     edx, edx; lpSubKey
0x140055805  call    cs:__imp_RegSetKeyValueW
0x14005580b  test    eax, eax
0x14005580d  jnz     loc_1400558D1
0x140055813  cmp     [rbx+48h], eax
0x140055816  jge     short loc_140055850
0x140055818  movzx   eax, word ptr [rbx+48h]
0x14005581c  lea     rcx, [rbx+4]
0x140055820  add     rcx, rax
0x140055823  xor     edx, edx
0x140055825  movzx   r8d, word ptr [rax+rbx+2]
0x14005582b  test    r8d, r8d
0x14005582e  jz      short loc_140055846
0x140055830  cmp     [rcx+2], r14w
0x140055835  jz      short loc_14005584B
0x140055837  movzx   eax, word ptr [rcx]
0x14005583a  add     edx, r14d
0x14005583d  lea     rcx, [rcx+rax*4]
0x140055841  cmp     edx, r8d
0x140055844  jb      short loc_140055830
0x140055846  cmp     edx, r8d
0x140055849  jnb     short loc_140055850
0x14005584b  add     rcx, rsi
0x14005584e  jmp     short loc_140055852
0x140055850  xor     ecx, ecx
0x140055852  mov     [rsp+50h+samDesired], 20h ; ' '; cbData
0x14005585a  lea     r8, aEnablekernelfl; "EnableKernelFlags"
0x140055861  mov     qword ptr [rsp+50h+dwOptions], rcx; lpData
0x140055866  mov     r9d, 3; dwType
0x14005586c  mov     rcx, [rbp+hKey]; hKey
0x140055870  xor     edx, edx; lpSubKey
0x140055872  call    cs:__imp_RegSetKeyValueW
0x140055878  test    eax, eax
0x14005587a  jnz     short loc_1400558D1
0x14005587c  mov     rcx, [rbp+hKey]; hKey
0x140055880  lea     r8, aStatus; "Status"
0x140055887  mov     [rbp+Data], eax
0x14005588a  mov     r9d, esi; dwType
0x14005588d  lea     rax, [rbp+Data]
0x140055891  mov     [rsp+50h+samDesired], esi; cbData
0x140055895  xor     edx, edx; lpSubKey
0x140055897  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14005589c  call    cs:__imp_RegSetKeyValueW
0x1400558a2  test    eax, eax
0x1400558a4  jnz     short loc_1400558D1
0x1400558a6  mov     rcx, [rbp+hKey]; hKey
0x1400558aa  lea     rax, [rbp+Data]
0x1400558ae  mov     [rsp+50h+samDesired], esi; cbData
0x1400558b2  lea     r8, aStart; "Start"
0x1400558b9  mov     r9d, esi; dwType
0x1400558bc  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1400558c1  xor     edx, edx; lpSubKey
0x1400558c3  mov     [rbp+Data], r14d
0x1400558c7  call    cs:__imp_RegSetKeyValueW
0x1400558cd  test    eax, eax
0x1400558cf  jz      short loc_1400558DD
0x1400558d1  mov     rcx, [rbp+hKey]; hKey
0x1400558d5  xor     edx, edx; lpSubKey
0x1400558d7  call    cs:__imp_RegDeleteKeyA
0x1400558dd  mov     rcx, [rbp+hKey]; hKey
0x1400558e1  call    cs:__imp_RegCloseKey
0x1400558e7  mov     rbx, [rsp+50h+arg_0]
0x1400558ec  add     rsp, 50h
0x1400558f0  pop     r14
0x1400558f2  pop     rsi
0x1400558f3  pop     rbp
0x1400558f4  retn
```
