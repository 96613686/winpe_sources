# CWorkspace::TriggerEvent(void)

- ea: `0x180039290`
- end: `0x1800394c4`
- name: `?TriggerEvent@CWorkspace@@QEAAJXZ`
- size: `564`
- prototype: `__int64 __fastcall(CWorkspace *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002eae0`
- `0x18004bd50`
- `0x18007525c`
- `0x180075d30`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x180039290`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800393c3`
- `ADVAPI32!RegGetValueW` at `0x1800393c3`
- `ADVAPI32!RegSetKeyValueW` at `0x180039445`
- `ADVAPI32!RegSetKeyValueW` at `0x180039445`
- `ADVAPI32!RegCloseKey` at `0x1800394ab`
- `ADVAPI32!RegCloseKey` at `0x1800394ab`
- `ADVAPI32!RegCreateKeyExW` at `0x18003933d`
- `ADVAPI32!RegCreateKeyExW` at `0x18003933d`

## pseudocode

```c
__int64 __fastcall CWorkspace::TriggerEvent(CWorkspace *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v2; // ebx
  unsigned int v3; // eax
  LSTATUS ValueW; // edi
  unsigned int v5; // eax
  LSTATUS v6; // edi
  unsigned int v7; // eax
  unsigned int pvData; // [rsp+70h] [rbp+20h] BYREF
  int pvData_4; // [rsp+74h] [rbp+24h]
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF
  HKEY hkey; // [rsp+80h] [rbp+30h] BYREF

  pvData_4 = HIDWORD(this);
  hkey = 0;
  pvData = 0;
  pcbData = 4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      285,
      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  v2 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Workspaces\\Events", 0, 0, 0, 0x2001Fu, 0, &hkey, 0);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 286, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v3, v2);
    }
    if ( v2 > 0 )
    {
      v2 = (unsigned __int16)v2;
LABEL_24:
      v2 |= 0x80070000;
    }
  }
  else
  {
    v2 = 0;
    ValueW = RegGetValueW(hkey, 0, &LocaleName, 0x10u, 0, &pvData, &pcbData);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 287, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v5, ValueW);
    }
    pvData = (pvData + 1) % 3;
    v6 = RegSetKeyValueW(hkey, 0, &LocaleName, 4u, &pvData, 4u);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 288, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v7, v6);
      }
      if ( v6 <= 0 )
      {
        v2 = v6;
        goto LABEL_25;
      }
      v2 = (unsigned __int16)v6;
      goto LABEL_24;
    }
  }
LABEL_25:
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180039290  mov     [rsp-18h+arg_18], rbx
0x180039295  mov     [rsp-18h+pvData], rcx
0x18003929a  push    rbp
0x18003929b  push    rdi
0x18003929c  push    r14
0x18003929e  mov     rbp, rsp
0x1800392a1  sub     rsp, 50h
0x1800392a5  mov     [rbp+hkey], 0
0x1800392ad  mov     dword ptr [rbp+pvData], 0
0x1800392b4  mov     [rbp+pcbData], 4
0x1800392bb  mov     rax, cs:WPP_GLOBAL_Control
0x1800392c2  lea     r14, WPP_GLOBAL_Control
0x1800392c9  cmp     rax, r14
0x1800392cc  jz      short loc_1800392FE
0x1800392ce  test    byte ptr [rax+1Ch], 1
0x1800392d2  jz      short loc_1800392FE
0x1800392d4  cmp     byte ptr [rax+19h], 4
0x1800392d8  jb      short loc_1800392FE
0x1800392da  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800392df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800392e6  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800392ed  mov     edx, 11Dh
0x1800392f2  mov     r9d, eax
0x1800392f5  mov     rcx, [rcx+10h]
0x1800392f9  call    WPP_SF_D
0x1800392fe  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180039307  lea     rax, [rbp+hkey]
0x18003930b  mov     [rsp+50h+phkResult], rax; phkResult
0x180039310  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Workspaces\\Events"
0x180039317  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180039320  xor     r9d, r9d; lpClass
0x180039323  mov     [rsp+50h+samDesired], 2001Fh; samDesired
0x18003932b  xor     r8d, r8d; Reserved
0x18003932e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180039335  mov     [rsp+50h+dwOptions], 0; dwOptions
0x18003933d  call    cs:__imp_RegCreateKeyExW
0x180039343  mov     ebx, eax
0x180039345  test    eax, eax
0x180039347  jz      short loc_180039399
0x180039349  mov     rax, cs:WPP_GLOBAL_Control
0x180039350  cmp     rax, r14
0x180039353  jz      short loc_180039389
0x180039355  test    byte ptr [rax+1Ch], 8
0x180039359  jz      short loc_180039389
0x18003935b  cmp     byte ptr [rax+19h], 2
0x18003935f  jb      short loc_180039389
0x180039361  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180039366  mov     rcx, cs:WPP_GLOBAL_Control
0x18003936d  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180039374  mov     edx, 11Eh
0x180039379  mov     [rsp+50h+dwOptions], ebx
0x18003937d  mov     r9d, eax
0x180039380  mov     rcx, [rcx+10h]
0x180039384  call    WPP_SF_Dd
0x180039389  test    ebx, ebx
0x18003938b  jle     loc_1800394A2
0x180039391  movzx   ebx, bx
0x180039394  jmp     loc_18003949C
0x180039399  mov     rcx, [rbp+hkey]; hkey
0x18003939d  lea     rax, [rbp+pcbData]
0x1800393a1  mov     [rsp+50h+lpSecurityAttributes], rax; pcbData
0x1800393a6  lea     r8, LocaleName; lpValue
0x1800393ad  xor     ebx, ebx
0x1800393af  lea     rax, [rbp+pvData]
0x1800393b3  mov     qword ptr [rsp+50h+samDesired], rax; pvData
0x1800393b8  xor     edx, edx; lpSubKey
0x1800393ba  mov     qword ptr [rsp+50h+dwOptions], rbx; pdwType
0x1800393bf  lea     r9d, [rbx+10h]; dwFlags
0x1800393c3  call    cs:__imp_RegGetValueW
0x1800393c9  mov     edi, eax
0x1800393cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393d2  cmp     rcx, r14
0x1800393d5  jz      short loc_18003940B
0x1800393d7  test    byte ptr [rcx+1Ch], 1
0x1800393db  jz      short loc_18003940B
0x1800393dd  cmp     byte ptr [rcx+19h], 5
0x1800393e1  jb      short loc_18003940B
0x1800393e3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800393e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393ef  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800393f6  mov     edx, 11Fh
0x1800393fb  mov     [rsp+50h+dwOptions], edi
0x1800393ff  mov     r9d, eax
0x180039402  mov     rcx, [rcx+10h]
0x180039406  call    WPP_SF_Dd
0x18003940b  mov     ecx, dword ptr [rbp+pvData]
0x18003940e  lea     r8, LocaleName; lpValueName
0x180039415  inc     ecx
0x180039417  mov     [rsp+50h+samDesired], 4; cbData
0x18003941f  mov     eax, 0AAAAAAABh
0x180039424  mov     r9d, 4; dwType
0x18003942a  mul     ecx
0x18003942c  shr     edx, 1
0x18003942e  lea     eax, [rdx+rdx*2]
0x180039431  xor     edx, edx; lpSubKey
0x180039433  sub     ecx, eax
0x180039435  lea     rax, [rbp+pvData]
0x180039439  mov     dword ptr [rbp+pvData], ecx
0x18003943c  mov     rcx, [rbp+hkey]; hKey
0x180039440  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180039445  call    cs:__imp_RegSetKeyValueW
0x18003944b  mov     edi, eax
0x18003944d  test    eax, eax
0x18003944f  jz      short loc_1800394A2
0x180039451  mov     rax, cs:WPP_GLOBAL_Control
0x180039458  cmp     rax, r14
0x18003945b  jz      short loc_180039491
0x18003945d  test    byte ptr [rax+1Ch], 8
0x180039461  jz      short loc_180039491
0x180039463  cmp     byte ptr [rax+19h], 2
0x180039467  jb      short loc_180039491
0x180039469  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003946e  mov     rcx, cs:WPP_GLOBAL_Control
0x180039475  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x18003947c  mov     edx, 120h
0x180039481  mov     [rsp+50h+dwOptions], edi
0x180039485  mov     r9d, eax
0x180039488  mov     rcx, [rcx+10h]
0x18003948c  call    WPP_SF_Dd
0x180039491  test    edi, edi
0x180039493  jg      short loc_180039499
0x180039495  mov     ebx, edi
0x180039497  jmp     short loc_1800394A2
0x180039499  movzx   ebx, di
0x18003949c  or      ebx, 80070000h
0x1800394a2  mov     rcx, [rbp+hkey]; hKey
0x1800394a6  test    rcx, rcx
0x1800394a9  jz      short loc_1800394B1
0x1800394ab  call    cs:__imp_RegCloseKey
0x1800394b1  mov     eax, ebx
0x1800394b3  mov     rbx, [rsp+50h+arg_18]
0x1800394bb  add     rsp, 50h
0x1800394bf  pop     r14
0x1800394c1  pop     rdi
0x1800394c2  pop     rbp
0x1800394c3  retn
```
