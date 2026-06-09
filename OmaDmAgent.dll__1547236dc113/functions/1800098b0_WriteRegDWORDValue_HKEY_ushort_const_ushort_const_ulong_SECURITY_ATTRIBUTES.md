# WriteRegDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800098b0`
- end: `0x180009a0e`
- name: `?WriteRegDWORDValue@@YAJPEAUHKEY__@@PEBG1KPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `350`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011574`
- `0x18001180c`
- `0x180011a44`
- `0x180012050`
- `0x180012338`

## callees

- `0x1800098b0`
- `0x18000a3c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800099e1`
- `ADVAPI32!RegCloseKey` at `0x1800099e1`
- `ADVAPI32!RegCreateKeyExW` at `0x18000991d`
- `ADVAPI32!RegCreateKeyExW` at `0x18000991d`
- `ADVAPI32!RegSetValueExW` at `0x180009983`
- `ADVAPI32!RegSetValueExW` at `0x180009983`
- `KERNEL32!SetLastError` at `0x1800099ef`
- `KERNEL32!SetLastError` at `0x1800099ef`

## pseudocode

```c
__int64 __fastcall WriteRegDWORDValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  int v5; // edi
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  LPCWSTR v8; // rcx
  int v9; // edx
  int v10; // r9d
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  hKey = 0;
  v5 = (int)a2;
  if ( !a1 || !a2 || !a3 )
  {
    v6 = -2147024809;
    goto LABEL_22;
  }
  v7 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0x20106u, 0, &hKey, 0);
  if ( v7 )
  {
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    else
      v6 = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_20;
    v9 = 31;
    v10 = v5;
  }
  else
  {
    v6 = 0;
    v7 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v7 )
      goto LABEL_20;
    v6 = v7 > 0 ? (unsigned __int16)v7 | 0x80070000 : v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_20;
    v9 = 32;
    v10 = (int)a3;
  }
  WPP_SF_Sd(*((_QWORD *)v8 + 2), v9, (unsigned int)&WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids, v10, v7);
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_22:
  SetLastError(0);
  return v6;
}

```

## disassembly

```asm
0x1800098b0  mov     rax, rsp
0x1800098b3  mov     [rax+10h], rbx
0x1800098b7  mov     [rax+18h], rsi
0x1800098bb  mov     [rax+20h], r9d
0x1800098bf  push    rdi
0x1800098c0  sub     rsp, 50h
0x1800098c4  mov     qword ptr [rax+8], 0
0x1800098cc  mov     rsi, r8
0x1800098cf  mov     rdi, rdx
0x1800098d2  test    rcx, rcx
0x1800098d5  jnz     short loc_1800098E1
0x1800098d7  mov     ebx, 80070057h
0x1800098dc  jmp     loc_1800099ED
0x1800098e1  test    rdi, rdi
0x1800098e4  jz      short loc_1800098D7
0x1800098e6  test    rsi, rsi
0x1800098e9  jz      short loc_1800098D7
0x1800098eb  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800098f4  lea     rax, [rsp+58h+hKey]
0x1800098f9  mov     [rsp+58h+phkResult], rax; phkResult
0x1800098fe  xor     r9d, r9d; lpClass
0x180009901  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000990a  xor     r8d, r8d; Reserved
0x18000990d  mov     [rsp+58h+samDesired], 20106h; samDesired
0x180009915  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000991d  call    cs:__imp_RegCreateKeyExW
0x180009924  nop     dword ptr [rax+rax+00h]
0x180009929  test    eax, eax
0x18000992b  jz      short loc_180009963
0x18000992d  jg      short loc_180009933
0x18000992f  mov     ebx, eax
0x180009931  jmp     short loc_18000993C
0x180009933  movzx   ebx, ax
0x180009936  or      ebx, 80070000h
0x18000993c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009943  lea     rdx, WPP_GLOBAL_Control
0x18000994a  cmp     rcx, rdx
0x18000994d  jz      loc_1800099D7
0x180009953  test    byte ptr [rcx+1Ch], 1
0x180009957  jz      short loc_1800099D7
0x180009959  mov     edx, 1Fh
0x18000995e  mov     r9, rdi
0x180009961  jmp     short loc_1800099C3
0x180009963  mov     rcx, [rsp+58h+hKey]; hKey
0x180009968  lea     rax, [rsp+58h+Data]
0x18000996d  xor     ebx, ebx
0x18000996f  xor     r8d, r8d; Reserved
0x180009972  mov     rdx, rsi; lpValueName
0x180009975  lea     r9d, [rbx+4]; dwType
0x180009979  mov     [rsp+58h+samDesired], r9d; cbData
0x18000997e  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180009983  call    cs:__imp_RegSetValueExW
0x18000998a  nop     dword ptr [rax+rax+00h]
0x18000998f  test    eax, eax
0x180009991  jz      short loc_1800099D7
0x180009993  jg      short loc_180009999
0x180009995  mov     ebx, eax
0x180009997  jmp     short loc_1800099A2
0x180009999  movzx   ebx, ax
0x18000999c  or      ebx, 80070000h
0x1800099a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099a9  lea     rdx, WPP_GLOBAL_Control
0x1800099b0  cmp     rcx, rdx
0x1800099b3  jz      short loc_1800099D7
0x1800099b5  test    byte ptr [rcx+1Ch], 1
0x1800099b9  jz      short loc_1800099D7
0x1800099bb  mov     edx, 20h ; ' '
0x1800099c0  mov     r9, rsi
0x1800099c3  mov     rcx, [rcx+10h]
0x1800099c7  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x1800099ce  mov     [rsp+58h+dwOptions], eax
0x1800099d2  call    WPP_SF_Sd
0x1800099d7  mov     rcx, [rsp+58h+hKey]; hKey
0x1800099dc  test    rcx, rcx
0x1800099df  jz      short loc_1800099ED
0x1800099e1  call    cs:__imp_RegCloseKey
0x1800099e8  nop     dword ptr [rax+rax+00h]
0x1800099ed  xor     ecx, ecx; dwErrCode
0x1800099ef  call    cs:__imp_SetLastError
0x1800099f6  nop     dword ptr [rax+rax+00h]
0x1800099fb  mov     rsi, [rsp+58h+arg_10]
0x180009a00  mov     eax, ebx
0x180009a02  mov     rbx, [rsp+58h+arg_8]
0x180009a07  add     rsp, 50h
0x180009a0b  pop     rdi
0x180009a0c  retn
```
