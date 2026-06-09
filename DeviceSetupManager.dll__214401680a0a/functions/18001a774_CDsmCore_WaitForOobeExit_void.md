# CDsmCore::_WaitForOobeExit(void)

- ea: `0x18001a774`
- end: `0x18001a88e`
- name: `?_WaitForOobeExit@CDsmCore@@AEAAJXZ`
- size: `282`
- prototype: `__int64 __fastcall(CDsmCore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800238e8`

## callees

- `0x180018508`
- `0x18001a774`
- `0x180021790`
- `0x180022070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a806`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a806`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a7e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a7e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a87b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a87b`

## pseudocode

```c
__int64 __fastcall CDsmCore::_WaitForOobeExit(CDsmCore *this)
{
  unsigned int v1; // ebx
  LSTATUS v2; // eax
  bool v3; // sf
  DWORD v4; // eax
  CDsmCore *v5; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = (HKEY)this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
  hKey = 0;
  v1 = -2147467259;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, &hKey);
  v3 = v2 < 0;
  if ( v2 > 0 )
    v3 = 1;
  if ( !v3 )
  {
    while ( 1 )
    {
      v4 = WaitForSingleObject(hHandle, 0xBB8u);
      if ( v4 != 258 )
        break;
      if ( !CDsmCore::_IsOOBEInProgress(v5, hKey) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids);
        v1 = 0;
        goto LABEL_16;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids, v4);
LABEL_16:
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x18001a774  mov     [rsp+arg_8], rbx
0x18001a779  mov     [rsp+hKey], rcx
0x18001a77e  push    rdi
0x18001a77f  sub     rsp, 30h
0x18001a783  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a78a  lea     rdi, WPP_GLOBAL_Control
0x18001a791  cmp     rcx, rdi
0x18001a794  jz      short loc_18001A7B1
0x18001a796  test    byte ptr [rcx+1Ch], 1
0x18001a79a  jz      short loc_18001A7B1
0x18001a79c  mov     rcx, [rcx+10h]
0x18001a7a0  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x18001a7a7  mov     edx, 1Fh
0x18001a7ac  call    WPP_SF_
0x18001a7b1  lea     rax, [rsp+38h+hKey]
0x18001a7b6  mov     [rsp+38h+hKey], 0
0x18001a7bf  mov     r9d, 20019h; samDesired
0x18001a7c5  mov     [rsp+38h+phkResult], rax; phkResult
0x18001a7ca  xor     r8d, r8d; ulOptions
0x18001a7cd  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18001a7d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a7db  mov     ebx, 80004005h
0x18001a7e0  call    cs:__imp_RegOpenKeyExW
0x18001a7e6  test    eax, eax
0x18001a7e8  jle     short loc_18001A7F4
0x18001a7ea  movzx   eax, ax
0x18001a7ed  or      eax, 80070000h
0x18001a7f2  test    eax, eax
0x18001a7f4  js      loc_18001A881
0x18001a7fa  mov     rcx, cs:hHandle; hHandle
0x18001a801  mov     edx, 0BB8h; dwMilliseconds
0x18001a806  call    cs:__imp_WaitForSingleObject
0x18001a80c  cmp     eax, 102h
0x18001a811  jnz     short loc_18001A84C
0x18001a813  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001a818  call    ?_IsOOBEInProgress@CDsmCore@@AEAA_NPEAUHKEY__@@@Z; CDsmCore::_IsOOBEInProgress(HKEY__ *)
0x18001a81d  test    al, al
0x18001a81f  jnz     short loc_18001A7FA
0x18001a821  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a828  cmp     rcx, rdi
0x18001a82b  jz      short loc_18001A848
0x18001a82d  test    byte ptr [rcx+1Ch], 1
0x18001a831  jz      short loc_18001A848
0x18001a833  mov     rcx, [rcx+10h]
0x18001a837  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x18001a83e  mov     edx, 21h ; '!'
0x18001a843  call    WPP_SF_
0x18001a848  xor     ebx, ebx
0x18001a84a  jmp     short loc_18001A876
0x18001a84c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a853  cmp     rcx, rdi
0x18001a856  jz      short loc_18001A876
0x18001a858  test    byte ptr [rcx+1Ch], 4
0x18001a85c  jz      short loc_18001A876
0x18001a85e  mov     rcx, [rcx+10h]
0x18001a862  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x18001a869  mov     edx, 20h ; ' '
0x18001a86e  mov     r9d, eax
0x18001a871  call    WPP_SF_d
0x18001a876  mov     rcx, [rsp+38h+hKey]; hKey
0x18001a87b  call    cs:__imp_RegCloseKey
0x18001a881  mov     eax, ebx
0x18001a883  mov     rbx, [rsp+38h+arg_8]
0x18001a888  add     rsp, 30h
0x18001a88c  pop     rdi
0x18001a88d  retn
```
