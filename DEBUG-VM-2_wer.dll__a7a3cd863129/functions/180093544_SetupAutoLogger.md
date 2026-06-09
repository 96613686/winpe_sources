# SetupAutoLogger

- ea: `0x180093544`
- end: `0x180093761`
- name: `SetupAutoLogger`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180093768`

## callees

- `0x180093544`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800935ab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800935ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009374d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009374d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800935e5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009361b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093646`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093671`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800936de`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093708`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093733`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800935e5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009361b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093646`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093671`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800936de`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093708`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180093733`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180093743`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180093743`

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
0x180093544  mov     r11, rsp
0x180093547  mov     [r11+8], rbx
0x18009354b  push    rbp
0x18009354c  push    rsi
0x18009354d  push    r14
0x18009354f  mov     rbp, rsp
0x180093552  sub     rsp, 50h
0x180093556  lea     rax, [rbp+arg_10]
0x18009355a  mov     [rbp+hKey], 0
0x180093562  mov     [r11-28h], rax
0x180093566  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x18009356d  lea     rax, [rbp+hKey]
0x180093571  mov     [rbp+arg_10], 0
0x180093578  mov     [r11-30h], rax
0x18009357c  mov     rbx, rcx
0x18009357f  mov     qword ptr [r11-38h], 0
0x180093587  xor     r9d, r9d; lpClass
0x18009358a  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180093592  xor     r8d, r8d; Reserved
0x180093595  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009359c  mov     [rsp+50h+dwOptions], 0; dwOptions
0x1800935a4  mov     [rbp+Data], 0
0x1800935ab  call    cs:__imp_RegCreateKeyExW
0x1800935b1  test    eax, eax
0x1800935b3  jnz     loc_180093753
0x1800935b9  cmp     [rbp+arg_10], 2
0x1800935bd  mov     rcx, [rbp+hKey]; hKey
0x1800935c1  jz      loc_18009374D
0x1800935c7  mov     esi, 4
0x1800935cc  lea     rax, [rbx+30h]
0x1800935d0  mov     [rsp+50h+samDesired], esi; cbData
0x1800935d4  lea     r8, aBuffersize; "BufferSize"
0x1800935db  mov     r9d, esi; dwType
0x1800935de  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800935e3  xor     edx, edx; lpSubKey
0x1800935e5  call    cs:__imp_RegSetKeyValueW
0x1800935eb  test    eax, eax
0x1800935ed  jnz     loc_18009373D
0x1800935f3  mov     rcx, [rbp+hKey]; hKey
0x1800935f7  lea     rax, aC712af3dEd1e46; "{C712AF3D-ED1E-46A9-B843-E9014D29CAEE}"
0x1800935fe  lea     r14d, [rsi-3]
0x180093602  mov     [rsp+50h+samDesired], 4Eh ; 'N'; cbData
0x18009360a  mov     r9d, r14d; dwType
0x18009360d  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180093612  lea     r8, aGuid; "Guid"
0x180093619  xor     edx, edx; lpSubKey
0x18009361b  call    cs:__imp_RegSetKeyValueW
0x180093621  test    eax, eax
0x180093623  jnz     loc_18009373D
0x180093629  mov     rcx, [rbp+hKey]; hKey
0x18009362d  lea     rax, [rbx+40h]
0x180093631  mov     [rsp+50h+samDesired], esi; cbData
0x180093635  lea     r8, aLogfilemode; "LogFileMode"
0x18009363c  mov     r9d, esi; dwType
0x18009363f  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180093644  xor     edx, edx; lpSubKey
0x180093646  call    cs:__imp_RegSetKeyValueW
0x18009364c  test    eax, eax
0x18009364e  jnz     loc_18009373D
0x180093654  mov     rcx, [rbp+hKey]; hKey
0x180093658  lea     rax, [rbx+34h]
0x18009365c  mov     [rsp+50h+samDesired], esi; cbData
0x180093660  lea     r8, aMinimumbuffers; "MinimumBuffers"
0x180093667  mov     r9d, esi; dwType
0x18009366a  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18009366f  xor     edx, edx; lpSubKey
0x180093671  call    cs:__imp_RegSetKeyValueW
0x180093677  test    eax, eax
0x180093679  jnz     loc_18009373D
0x18009367f  cmp     [rbx+48h], eax
0x180093682  jge     short loc_1800936BC
0x180093684  movzx   eax, word ptr [rbx+48h]
0x180093688  lea     rcx, [rbx+4]
0x18009368c  add     rcx, rax
0x18009368f  xor     edx, edx
0x180093691  movzx   r8d, word ptr [rax+rbx+2]
0x180093697  test    r8d, r8d
0x18009369a  jz      short loc_1800936B2
0x18009369c  cmp     [rcx+2], r14w
0x1800936a1  jz      short loc_1800936B7
0x1800936a3  movzx   eax, word ptr [rcx]
0x1800936a6  add     edx, r14d
0x1800936a9  lea     rcx, [rcx+rax*4]
0x1800936ad  cmp     edx, r8d
0x1800936b0  jb      short loc_18009369C
0x1800936b2  cmp     edx, r8d
0x1800936b5  jnb     short loc_1800936BC
0x1800936b7  add     rcx, rsi
0x1800936ba  jmp     short loc_1800936BE
0x1800936bc  xor     ecx, ecx
0x1800936be  mov     [rsp+50h+samDesired], 20h ; ' '; cbData
0x1800936c6  lea     r8, aEnablekernelfl; "EnableKernelFlags"
0x1800936cd  mov     qword ptr [rsp+50h+dwOptions], rcx; lpData
0x1800936d2  mov     r9d, 3; dwType
0x1800936d8  mov     rcx, [rbp+hKey]; hKey
0x1800936dc  xor     edx, edx; lpSubKey
0x1800936de  call    cs:__imp_RegSetKeyValueW
0x1800936e4  test    eax, eax
0x1800936e6  jnz     short loc_18009373D
0x1800936e8  mov     rcx, [rbp+hKey]; hKey
0x1800936ec  lea     r8, aStatus; "Status"
0x1800936f3  mov     [rbp+Data], eax
0x1800936f6  mov     r9d, esi; dwType
0x1800936f9  lea     rax, [rbp+Data]
0x1800936fd  mov     [rsp+50h+samDesired], esi; cbData
0x180093701  xor     edx, edx; lpSubKey
0x180093703  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180093708  call    cs:__imp_RegSetKeyValueW
0x18009370e  test    eax, eax
0x180093710  jnz     short loc_18009373D
0x180093712  mov     rcx, [rbp+hKey]; hKey
0x180093716  lea     rax, [rbp+Data]
0x18009371a  mov     [rsp+50h+samDesired], esi; cbData
0x18009371e  lea     r8, aStart; "Start"
0x180093725  mov     r9d, esi; dwType
0x180093728  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x18009372d  xor     edx, edx; lpSubKey
0x18009372f  mov     [rbp+Data], r14d
0x180093733  call    cs:__imp_RegSetKeyValueW
0x180093739  test    eax, eax
0x18009373b  jz      short loc_180093749
0x18009373d  mov     rcx, [rbp+hKey]; hKey
0x180093741  xor     edx, edx; lpSubKey
0x180093743  call    cs:__imp_RegDeleteKeyA
0x180093749  mov     rcx, [rbp+hKey]; hKey
0x18009374d  call    cs:__imp_RegCloseKey
0x180093753  mov     rbx, [rsp+50h+arg_0]
0x180093758  add     rsp, 50h
0x18009375c  pop     r14
0x18009375e  pop     rsi
0x18009375f  pop     rbp
0x180093760  retn
```
