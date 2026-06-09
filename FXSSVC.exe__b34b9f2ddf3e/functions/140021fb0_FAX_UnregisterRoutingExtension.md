# FAX_UnregisterRoutingExtension

- ea: `0x140021fb0`
- end: `0x14002217f`
- name: `FAX_UnregisterRoutingExtension`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x140021fb0`
- `0x1400452ac`
- `0x140070020`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140022139`
- `ADVAPI32!RegCloseKey` at `0x140022139`
- `ADVAPI32!RegOpenKeyExW` at `0x1400220b1`
- `ADVAPI32!RegOpenKeyExW` at `0x1400220b1`
- `KERNEL32!GetLastError` at `0x1400220fc`
- `KERNEL32!GetLastError` at `0x1400220fc`

## string_xrefs

- `0x1400220a3`: `Software\Microsoft\Fax\Routing Extensions`

## pseudocode

```c
__int64 __fastcall FAX_UnregisterRoutingExtension(__int64 a1, const WCHAR *a2)
{
  unsigned int v3; // ebx
  CMapDeviceId *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  DWORD LastError; // eax
  unsigned int v9; // eax
  int v10; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v10 = 0;
  hKey = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 395, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  v3 = FaxSvcAccessCheck(0x40u, &v10, 0, 1);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v5 = 396;
    goto LABEL_10;
  }
  if ( v10 )
  {
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Routing Extensions", 0, 0x2001Fu, &hKey);
    if ( !v3 )
    {
      if ( !(unsigned int)DeleteRegistryKey(hKey, a2) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            399,
            (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            (_DWORD)a2,
            LastError);
        }
      }
      v9 = RegCloseKey(hKey);
      if ( !v9 )
        return v3;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v3;
      }
      v5 = 400;
      v6 = v9;
      goto LABEL_32;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v3;
    }
    v5 = 398;
LABEL_10:
    v6 = v3;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v6);
    return v3;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 397, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  return 5;
}

```

## disassembly

```asm
0x140021fb0  mov     [rsp+arg_0], rbx
0x140021fb5  push    rbp
0x140021fb6  push    rdi
0x140021fb7  push    r15
0x140021fb9  sub     rsp, 30h
0x140021fbd  mov     rdi, rdx
0x140021fc0  mov     [rsp+48h+arg_10], 0
0x140021fc8  mov     [rsp+48h+hKey], 0
0x140021fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140021fd8  lea     rbp, WPP_GLOBAL_Control
0x140021fdf  lea     r15, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140021fe6  cmp     rcx, rbp
0x140021fe9  jz      short loc_140022008
0x140021feb  test    byte ptr [rcx+1Ch], 4
0x140021fef  jz      short loc_140022008
0x140021ff1  cmp     byte ptr [rcx+19h], 5
0x140021ff5  jb      short loc_140022008
0x140021ff7  mov     rcx, [rcx+10h]
0x140021ffb  mov     edx, 18Bh
0x140022000  mov     r8, r15
0x140022003  call    WPP_SF_
0x140022008  mov     r9d, 1; int
0x14002200e  lea     rdx, [rsp+48h+arg_10]; int *
0x140022013  xor     r8d, r8d; unsigned int *
0x140022016  lea     ecx, [r9+3Fh]; unsigned int
0x14002201a  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14002201f  mov     ebx, eax
0x140022021  test    eax, eax
0x140022023  jz      short loc_140022056
0x140022025  mov     rcx, cs:WPP_GLOBAL_Control
0x14002202c  cmp     rcx, rbp
0x14002202f  jz      loc_14002216F
0x140022035  test    byte ptr [rcx+1Ch], 4
0x140022039  jz      loc_14002216F
0x14002203f  cmp     byte ptr [rcx+19h], 2
0x140022043  jb      loc_14002216F
0x140022049  mov     edx, 18Ch
0x14002204e  mov     r9d, ebx
0x140022051  jmp     loc_140022163
0x140022056  cmp     [rsp+48h+arg_10], 0
0x14002205b  jnz     short loc_140022090
0x14002205d  mov     rcx, cs:WPP_GLOBAL_Control
0x140022064  cmp     rcx, rbp
0x140022067  jz      short loc_140022086
0x140022069  test    byte ptr [rcx+1Ch], 4
0x14002206d  jz      short loc_140022086
0x14002206f  cmp     byte ptr [rcx+19h], 2
0x140022073  jb      short loc_140022086
0x140022075  mov     rcx, [rcx+10h]
0x140022079  mov     edx, 18Dh
0x14002207e  mov     r8, r15
0x140022081  call    WPP_SF_
0x140022086  mov     eax, 5
0x14002208b  jmp     loc_140022171
0x140022090  lea     rax, [rsp+48h+hKey]
0x140022095  mov     r9d, 2001Fh; samDesired
0x14002209b  xor     r8d, r8d; ulOptions
0x14002209e  mov     [rsp+48h+phkResult], rax; phkResult
0x1400220a3  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Fax\\Routing Exten"...
0x1400220aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400220b1  call    cs:__imp_RegOpenKeyExW
0x1400220b7  mov     ebx, eax
0x1400220b9  test    eax, eax
0x1400220bb  jz      short loc_1400220EB
0x1400220bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400220c4  cmp     rcx, rbp
0x1400220c7  jz      loc_14002216F
0x1400220cd  test    byte ptr [rcx+1Ch], 4
0x1400220d1  jz      loc_14002216F
0x1400220d7  cmp     byte ptr [rcx+19h], 2
0x1400220db  jb      loc_14002216F
0x1400220e1  mov     edx, 18Eh
0x1400220e6  jmp     loc_14002204E
0x1400220eb  mov     rcx, [rsp+48h+hKey]
0x1400220f0  mov     rdx, rdi
0x1400220f3  call    DeleteRegistryKey
0x1400220f8  test    eax, eax
0x1400220fa  jnz     short loc_140022134
0x1400220fc  call    cs:__imp_GetLastError
0x140022102  mov     ebx, eax
0x140022104  mov     rcx, cs:WPP_GLOBAL_Control
0x14002210b  cmp     rcx, rbp
0x14002210e  jz      short loc_140022134
0x140022110  test    byte ptr [rcx+1Ch], 4
0x140022114  jz      short loc_140022134
0x140022116  cmp     byte ptr [rcx+19h], 2
0x14002211a  jb      short loc_140022134
0x14002211c  mov     rcx, [rcx+10h]
0x140022120  mov     edx, 18Fh
0x140022125  mov     r9, rdi
0x140022128  mov     dword ptr [rsp+48h+phkResult], eax
0x14002212c  mov     r8, r15
0x14002212f  call    WPP_SF_Sd
0x140022134  mov     rcx, [rsp+48h+hKey]; hKey
0x140022139  call    cs:__imp_RegCloseKey
0x14002213f  test    eax, eax
0x140022141  jz      short loc_14002216F
0x140022143  mov     rcx, cs:WPP_GLOBAL_Control
0x14002214a  cmp     rcx, rbp
0x14002214d  jz      short loc_14002216F
0x14002214f  test    byte ptr [rcx+1Ch], 4
0x140022153  jz      short loc_14002216F
0x140022155  cmp     byte ptr [rcx+19h], 2
0x140022159  jb      short loc_14002216F
0x14002215b  mov     edx, 190h
0x140022160  mov     r9d, eax
0x140022163  mov     rcx, [rcx+10h]
0x140022167  mov     r8, r15
0x14002216a  call    WPP_SF_d
0x14002216f  mov     eax, ebx
0x140022171  mov     rbx, [rsp+48h+arg_0]
0x140022176  add     rsp, 30h
0x14002217a  pop     r15
0x14002217c  pop     rdi
0x14002217d  pop     rbp
0x14002217e  retn
```
