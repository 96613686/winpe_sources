# RegistryManager::GetValueInternal(HKEY__ * const,ushort const *,ushort const *,ushort const *,ulong &,uchar *,ulong &)

- ea: `0x140006b88`
- end: `0x140006ca2`
- name: `?GetValueInternal@RegistryManager@@CAJQEAUHKEY__@@PEBG11AEAKPEAE2@Z`
- size: `282`
- prototype: `LSTATUS __fastcall(HKEY, char *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int8 *pvData, unsigned int *pcbData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140006ad8`

## callees

- `0x140001480`
- `0x140001e7e`
- `0x1400048e4`
- `0x1400068b4`
- `0x140006b88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006c62`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006c62`

## string_xrefs

- `0x140006be4`: `onecore\enduser\windowsupdate\muse\orchestrator\common\lib\usocommon\registrymanager.cpp`

## pseudocode

```c
LSTATUS __fastcall RegistryManager::GetValueInternal(
        HKEY a1,
        char *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int8 *pvData,
        unsigned int *pcbData)
{
  __int64 v9; // rdx
  int RedirectedRegistryKeyName; // ebx
  LSTATUS result; // eax
  const unsigned __int16 *v12; // rdx
  unsigned __int64 v13; // r9
  int pdwType; // [rsp+20h] [rbp-248h]
  WCHAR SubKey[256]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( !a2 )
  {
    v9 = 942;
LABEL_3:
    RedirectedRegistryKeyName = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\common\\lib\\usocommon\\registrymanager.cpp",
      (const char *)(unsigned int)RedirectedRegistryKeyName,
      pdwType);
    return RedirectedRegistryKeyName;
  }
  if ( !a4 )
  {
    v9 = 943;
    goto LABEL_3;
  }
  if ( !pvData )
  {
    v9 = 944;
    goto LABEL_3;
  }
  memset_0(SubKey, 0, sizeof(SubKey));
  RedirectedRegistryKeyName = RegistryManager::GetRedirectedRegistryKeyName(a2, v12, SubKey, v13);
  if ( RedirectedRegistryKeyName < 0 )
  {
    v9 = 947;
    goto LABEL_4;
  }
  result = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, a4, 0xFFFFu, a5, pvData, pcbData);
  if ( !result )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140006b88  mov     [rsp+arg_0], rbx
0x140006b8d  mov     [rsp+arg_10], rbp
0x140006b92  push    rsi
0x140006b93  push    rdi
0x140006b94  push    r14
0x140006b96  sub     rsp, 250h
0x140006b9d  mov     rax, cs:__security_cookie
0x140006ba4  xor     rax, rsp
0x140006ba7  mov     [rsp+268h+var_28], rax
0x140006baf  mov     rbp, [rsp+268h+arg_20]
0x140006bb7  mov     rdi, r9
0x140006bba  mov     rsi, [rsp+268h+arg_28]
0x140006bc2  mov     rbx, rdx
0x140006bc5  mov     r14, [rsp+268h+arg_30]
0x140006bcd  test    rdx, rdx
0x140006bd0  jnz     short loc_140006BFA
0x140006bd2  mov     edx, 3AEh; void *
0x140006bd7  mov     ebx, 80070057h
0x140006bdc  mov     rcx, [rsp+268h]; this
0x140006be4  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140006beb  mov     r9d, ebx; char *
0x140006bee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006bf3  mov     eax, ebx
0x140006bf5  jmp     loc_140006C7A
0x140006bfa  test    rdi, rdi
0x140006bfd  jnz     short loc_140006C06
0x140006bff  mov     edx, 3AFh
0x140006c04  jmp     short loc_140006BD7
0x140006c06  test    rsi, rsi
0x140006c09  jnz     short loc_140006C12
0x140006c0b  mov     edx, 3B0h
0x140006c10  jmp     short loc_140006BD7
0x140006c12  xor     edx, edx; Val
0x140006c14  lea     rcx, [rsp+268h+SubKey]; void *
0x140006c19  mov     r8d, 200h; Size
0x140006c1f  call    memset_0
0x140006c24  lea     r8, [rsp+268h+SubKey]; unsigned __int16 *
0x140006c29  mov     rcx, rbx; char *
0x140006c2c  call    ?GetRedirectedRegistryKeyName@RegistryManager@@SAJPEBG0PEAG_K@Z; RegistryManager::GetRedirectedRegistryKeyName(ushort const *,ushort const *,ushort *,unsigned __int64)
0x140006c31  mov     ebx, eax
0x140006c33  test    eax, eax
0x140006c35  jns     short loc_140006C3E
0x140006c37  mov     edx, 3B3h
0x140006c3c  jmp     short loc_140006BDC
0x140006c3e  mov     [rsp+268h+pcbData], r14; pcbData
0x140006c43  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x140006c48  mov     [rsp+268h+pvData], rsi; pvData
0x140006c4d  mov     r9d, 0FFFFh; dwFlags
0x140006c53  mov     r8, rdi; lpValue
0x140006c56  mov     [rsp+268h+pdwType], rbp; pdwType
0x140006c5b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140006c62  call    cs:__imp_RegGetValueW
0x140006c68  test    eax, eax
0x140006c6a  jz      short loc_140006C78
0x140006c6c  jle     short loc_140006C7A
0x140006c6e  movzx   eax, ax
0x140006c71  or      eax, 80070000h
0x140006c76  jmp     short loc_140006C7A
0x140006c78  xor     eax, eax
0x140006c7a  mov     rcx, [rsp+268h+var_28]
0x140006c82  xor     rcx, rsp; StackCookie
0x140006c85  call    __security_check_cookie
0x140006c8a  lea     r11, [rsp+268h+var_18]
0x140006c92  mov     rbx, [r11+20h]
0x140006c96  mov     rbp, [r11+30h]
0x140006c9a  mov     rsp, r11
0x140006c9d  pop     r14
0x140006c9f  pop     rdi
0x140006ca0  pop     rsi
0x140006ca1  retn
```
