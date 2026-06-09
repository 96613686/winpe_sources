# SetupAutoLogger

- ea: `0x140059168`
- end: `0x1400593c2`
- name: `SetupAutoLogger`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400594e4`

## callees

- `0x140059168`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400593a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400593a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400591cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400591cf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005920f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005924b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005927c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400592ad`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140059320`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140059350`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140059381`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005920f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005924b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14005927c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400592ad`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140059320`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140059350`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140059381`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x140059397`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x140059397`

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
0x140059168  mov     r11, rsp
0x14005916b  mov     [r11+8], rbx
0x14005916f  push    rbp
0x140059170  push    rsi
0x140059171  push    r14
0x140059173  mov     rbp, rsp
0x140059176  sub     rsp, 50h
0x14005917a  lea     rax, [rbp+arg_10]
0x14005917e  mov     [rbp+hKey], 0
0x140059186  mov     [r11-28h], rax
0x14005918a  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x140059191  lea     rax, [rbp+hKey]
0x140059195  mov     [rbp+arg_10], 0
0x14005919c  mov     [r11-30h], rax
0x1400591a0  mov     rbx, rcx
0x1400591a3  mov     qword ptr [r11-38h], 0
0x1400591ab  xor     r9d, r9d; lpClass
0x1400591ae  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x1400591b6  xor     r8d, r8d; Reserved
0x1400591b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400591c0  mov     [rsp+50h+dwOptions], 0; dwOptions
0x1400591c8  mov     [rbp+Data], 0
0x1400591cf  call    cs:__imp_RegCreateKeyExW
0x1400591d6  nop     dword ptr [rax+rax+00h]
0x1400591db  test    eax, eax
0x1400591dd  jnz     loc_1400593B3
0x1400591e3  cmp     [rbp+arg_10], 2
0x1400591e7  mov     rcx, [rbp+hKey]; hKey
0x1400591eb  jz      loc_1400593A7
0x1400591f1  mov     esi, 4
0x1400591f6  lea     rax, [rbx+30h]
0x1400591fa  mov     [rsp+50h+samDesired], esi; cbData
0x1400591fe  lea     r8, aBuffersize; "BufferSize"
0x140059205  mov     r9d, esi; dwType
0x140059208  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14005920d  xor     edx, edx; lpSubKey
0x14005920f  call    cs:__imp_RegSetKeyValueW
0x140059216  nop     dword ptr [rax+rax+00h]
0x14005921b  test    eax, eax
0x14005921d  jnz     loc_140059391
0x140059223  mov     rcx, [rbp+hKey]; hKey
0x140059227  lea     rax, aC712af3dEd1e46; "{C712AF3D-ED1E-46A9-B843-E9014D29CAEE}"
0x14005922e  lea     r14d, [rsi-3]
0x140059232  mov     [rsp+50h+samDesired], 4Eh ; 'N'; cbData
0x14005923a  mov     r9d, r14d; dwType
0x14005923d  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140059242  lea     r8, aGuid; "Guid"
0x140059249  xor     edx, edx; lpSubKey
0x14005924b  call    cs:__imp_RegSetKeyValueW
0x140059252  nop     dword ptr [rax+rax+00h]
0x140059257  test    eax, eax
0x140059259  jnz     loc_140059391
0x14005925f  mov     rcx, [rbp+hKey]; hKey
0x140059263  lea     rax, [rbx+40h]
0x140059267  mov     [rsp+50h+samDesired], esi; cbData
0x14005926b  lea     r8, aLogfilemode; "LogFileMode"
0x140059272  mov     r9d, esi; dwType
0x140059275  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14005927a  xor     edx, edx; lpSubKey
0x14005927c  call    cs:__imp_RegSetKeyValueW
0x140059283  nop     dword ptr [rax+rax+00h]
0x140059288  test    eax, eax
0x14005928a  jnz     loc_140059391
0x140059290  mov     rcx, [rbp+hKey]; hKey
0x140059294  lea     rax, [rbx+34h]
0x140059298  mov     [rsp+50h+samDesired], esi; cbData
0x14005929c  lea     r8, aMinimumbuffers; "MinimumBuffers"
0x1400592a3  mov     r9d, esi; dwType
0x1400592a6  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1400592ab  xor     edx, edx; lpSubKey
0x1400592ad  call    cs:__imp_RegSetKeyValueW
0x1400592b4  nop     dword ptr [rax+rax+00h]
0x1400592b9  test    eax, eax
0x1400592bb  jnz     loc_140059391
0x1400592c1  cmp     [rbx+48h], eax
0x1400592c4  jge     short loc_1400592FE
0x1400592c6  movzx   eax, word ptr [rbx+48h]
0x1400592ca  lea     rcx, [rbx+4]
0x1400592ce  add     rcx, rax
0x1400592d1  xor     edx, edx
0x1400592d3  movzx   r8d, word ptr [rax+rbx+2]
0x1400592d9  test    r8d, r8d
0x1400592dc  jz      short loc_1400592F4
0x1400592de  cmp     [rcx+2], r14w
0x1400592e3  jz      short loc_1400592F9
0x1400592e5  movzx   eax, word ptr [rcx]
0x1400592e8  add     edx, r14d
0x1400592eb  lea     rcx, [rcx+rax*4]
0x1400592ef  cmp     edx, r8d
0x1400592f2  jb      short loc_1400592DE
0x1400592f4  cmp     edx, r8d
0x1400592f7  jnb     short loc_1400592FE
0x1400592f9  add     rcx, rsi
0x1400592fc  jmp     short loc_140059300
0x1400592fe  xor     ecx, ecx
0x140059300  mov     [rsp+50h+samDesired], 20h ; ' '; cbData
0x140059308  lea     r8, aEnablekernelfl; "EnableKernelFlags"
0x14005930f  mov     qword ptr [rsp+50h+dwOptions], rcx; lpData
0x140059314  mov     r9d, 3; dwType
0x14005931a  mov     rcx, [rbp+hKey]; hKey
0x14005931e  xor     edx, edx; lpSubKey
0x140059320  call    cs:__imp_RegSetKeyValueW
0x140059327  nop     dword ptr [rax+rax+00h]
0x14005932c  test    eax, eax
0x14005932e  jnz     short loc_140059391
0x140059330  mov     rcx, [rbp+hKey]; hKey
0x140059334  lea     r8, aStatus; "Status"
0x14005933b  mov     [rbp+Data], eax
0x14005933e  mov     r9d, esi; dwType
0x140059341  lea     rax, [rbp+Data]
0x140059345  mov     [rsp+50h+samDesired], esi; cbData
0x140059349  xor     edx, edx; lpSubKey
0x14005934b  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140059350  call    cs:__imp_RegSetKeyValueW
0x140059357  nop     dword ptr [rax+rax+00h]
0x14005935c  test    eax, eax
0x14005935e  jnz     short loc_140059391
0x140059360  mov     rcx, [rbp+hKey]; hKey
0x140059364  lea     rax, [rbp+Data]
0x140059368  mov     [rsp+50h+samDesired], esi; cbData
0x14005936c  lea     r8, aStart; "Start"
0x140059373  mov     r9d, esi; dwType
0x140059376  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x14005937b  xor     edx, edx; lpSubKey
0x14005937d  mov     [rbp+Data], r14d
0x140059381  call    cs:__imp_RegSetKeyValueW
0x140059388  nop     dword ptr [rax+rax+00h]
0x14005938d  test    eax, eax
0x14005938f  jz      short loc_1400593A3
0x140059391  mov     rcx, [rbp+hKey]; hKey
0x140059395  xor     edx, edx; lpSubKey
0x140059397  call    cs:__imp_RegDeleteKeyA
0x14005939e  nop     dword ptr [rax+rax+00h]
0x1400593a3  mov     rcx, [rbp+hKey]; hKey
0x1400593a7  call    cs:__imp_RegCloseKey
0x1400593ae  nop     dword ptr [rax+rax+00h]
0x1400593b3  mov     rbx, [rsp+50h+arg_0]
0x1400593b8  add     rsp, 50h
0x1400593bc  pop     r14
0x1400593be  pop     rsi
0x1400593bf  pop     rbp
0x1400593c0  retn
```
