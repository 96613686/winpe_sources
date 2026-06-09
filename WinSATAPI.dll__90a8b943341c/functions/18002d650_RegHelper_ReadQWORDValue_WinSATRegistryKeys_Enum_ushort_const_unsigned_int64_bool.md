# RegHelper::ReadQWORDValue(WinSATRegistryKeys::Enum,ushort const *,unsigned __int64 &,bool *)

- ea: `0x18002d650`
- end: `0x18002d763`
- name: `?ReadQWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_KPEA_N@Z`
- size: `275`
- prototype: `static unsigned int __high(enum WinSATRegistryKeys::Enum, const unsigned __int16 *, unsigned __int64 *, bool *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021898`
- `0x1800219d4`
- `0x180021f00`

## callees

- `0x18000ee1c`
- `0x1800161e0`
- `0x18002d650`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d6e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d6e5`

## pseudocode

```c
__int64 __fastcall RegHelper::ReadQWORDValue(int a1, const WCHAR *a2, _QWORD *a3, _BYTE *a4)
{
  const WCHAR *v7; // r8
  unsigned int v8; // edi
  LSTATUS v9; // eax
  DWORD cbData; // [rsp+30h] [rbp-30h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-28h] BYREF
  HKEY hKey[4]; // [rsp+40h] [rbp-20h] BYREF
  DWORD Type; // [rsp+80h] [rbp+20h] BYREF

  memset(hKey, 0, 24);
  *(_QWORD *)Data = 0;
  if ( !a1 )
  {
    v7 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSAT";
    goto LABEL_5;
  }
  if ( a1 == 1 )
  {
    v7 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI";
LABEL_5:
    v8 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_LOCAL_MACHINE, v7, 0x20019u);
    if ( !v8 )
    {
      Type = 0;
      cbData = 8;
      v9 = RegQueryValueExW(hKey[0], a2, 0, &Type, Data, &cbData);
      if ( v9 )
      {
        if ( v9 == 2 )
        {
          if ( a4 )
            *a4 = 1;
          *(_QWORD *)Data = 0;
LABEL_17:
          *a3 = *(_QWORD *)Data;
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          return 0;
        }
      }
      else
      {
        if ( Type == 11 )
        {
          if ( a4 )
            *a4 = 0;
          goto LABEL_17;
        }
        v9 = 13;
      }
      v8 = v9;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    return v8;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return 87;
}

```

## disassembly

```asm
0x18002d650  mov     [rsp-18h+arg_8], rbx
0x18002d655  mov     [rsp-18h+arg_10], rsi
0x18002d65a  push    rbp
0x18002d65b  push    rdi
0x18002d65c  push    r14
0x18002d65e  mov     rbp, rsp
0x18002d661  sub     rsp, 60h
0x18002d665  and     [rbp+hKey], 0
0x18002d66a  mov     rbx, r9
0x18002d66d  and     [rbp+var_18], 0
0x18002d672  mov     rsi, r8
0x18002d675  and     [rbp+var_10], 0
0x18002d67a  mov     r14, rdx
0x18002d67d  and     qword ptr [rbp+Data], 0
0x18002d682  test    ecx, ecx
0x18002d684  jnz     short loc_18002D68F
0x18002d686  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002d68d  jmp     short loc_18002D69F
0x18002d68f  cmp     ecx, 1
0x18002d692  jnz     loc_18002D73F
0x18002d698  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002d69f  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002d6a6  lea     rcx, [rbp+hKey]; this
0x18002d6aa  mov     r9d, 20019h; unsigned int
0x18002d6b0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002d6b5  mov     edi, eax
0x18002d6b7  test    eax, eax
0x18002d6b9  jnz     short loc_18002D716
0x18002d6bb  and     [rbp+Type], eax
0x18002d6be  lea     r9, [rbp+Type]; lpType
0x18002d6c2  mov     rcx, [rbp+hKey]; hKey
0x18002d6c6  lea     rax, [rbp+cbData]
0x18002d6ca  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002d6cf  xor     r8d, r8d; lpReserved
0x18002d6d2  lea     rax, [rbp+Data]
0x18002d6d6  mov     [rbp+cbData], 8
0x18002d6dd  mov     rdx, r14; lpValueName
0x18002d6e0  mov     [rsp+60h+lpData], rax; lpData
0x18002d6e5  call    cs:__imp_RegQueryValueExW
0x18002d6ec  nop     dword ptr [rax+rax+00h]
0x18002d6f1  test    eax, eax
0x18002d6f3  jz      short loc_18002D709
0x18002d6f5  cmp     eax, 2
0x18002d6f8  jnz     short loc_18002D714
0x18002d6fa  test    rbx, rbx
0x18002d6fd  jz      short loc_18002D702
0x18002d6ff  mov     byte ptr [rbx], 1
0x18002d702  and     qword ptr [rbp+Data], 0
0x18002d707  jmp     short loc_18002D72B
0x18002d709  cmp     [rbp+Type], 0Bh
0x18002d70d  jz      short loc_18002D723
0x18002d70f  mov     eax, 0Dh
0x18002d714  mov     edi, eax
0x18002d716  lea     rcx, [rbp+hKey]; this
0x18002d71a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d71f  mov     eax, edi
0x18002d721  jmp     short loc_18002D74D
0x18002d723  test    rbx, rbx
0x18002d726  jz      short loc_18002D72B
0x18002d728  mov     byte ptr [rbx], 0
0x18002d72b  mov     rax, qword ptr [rbp+Data]
0x18002d72f  lea     rcx, [rbp+hKey]; this
0x18002d733  mov     [rsi], rax
0x18002d736  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d73b  xor     eax, eax
0x18002d73d  jmp     short loc_18002D74D
0x18002d73f  lea     rcx, [rbp+hKey]; this
0x18002d743  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d748  mov     eax, 57h ; 'W'
0x18002d74d  lea     r11, [rsp+60h+var_s0]
0x18002d752  mov     rbx, [r11+28h]
0x18002d756  mov     rsi, [r11+30h]
0x18002d75a  mov     rsp, r11
0x18002d75d  pop     r14
0x18002d75f  pop     rdi
0x18002d760  pop     rbp
0x18002d761  retn
```
