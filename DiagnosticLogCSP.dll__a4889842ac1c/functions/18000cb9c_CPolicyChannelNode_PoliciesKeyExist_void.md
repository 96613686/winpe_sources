# CPolicyChannelNode::PoliciesKeyExist(void)

- ea: `0x18000cb9c`
- end: `0x18000cd32`
- name: `?PoliciesKeyExist@CPolicyChannelNode@@CA_NXZ`
- size: `406`
- prototype: `bool(void)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bcc0`
- `0x18000bf50`
- `0x18000c260`
- `0x18000c870`
- `0x18000ced0`

## callees

- `0x180001104`
- `0x180001b60`
- `0x180006518`
- `0x18000cb9c`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000cbf5`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000cbf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ccb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ccb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cca6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cca6`

## pseudocode

```c
char CPolicyChannelNode::PoliciesKeyExist(void)
{
  unsigned int v0; // ebx
  __int64 v1; // rcx
  const wchar_t *v2; // rdx
  __int64 v3; // r8
  _WORD *v4; // rax
  _WORD *v5; // rcx
  unsigned int v7; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v10; // [rsp+70h] [rbp-90h]
  __int64 v11; // [rsp+78h] [rbp-88h]
  _BYTE v12[1024]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[512]; // [rsp+480h] [rbp+380h] BYREF

  hKey = 0;
  v0 = 0;
  if ( (int)RtlGetPersistedStateLocation(L"WINEVT", 0, 0, 0, v12, 1024, 0) < 0 )
  {
    v1 = 2147483646;
    v2 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT";
    v3 = 512;
    v4 = v12;
    do
    {
      if ( !v1 )
        break;
      if ( !*v2 )
        break;
      *v4++ = *v2++;
      --v1;
      --v3;
    }
    while ( v3 );
    v5 = v4 - 1;
    if ( v3 )
      v5 = v4;
    *v5 = 0;
    v0 = v3 == 0 ? 0x8007007A : 0;
    if ( !v3 )
      goto LABEL_11;
  }
  StringCchPrintfW(SubKey, 0x200u, L"%s\\%s", v12, L"Policies");
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
LABEL_11:
    if ( (unsigned int)dword_180048E90 > 5 )
    {
      v7 = v0;
      v10 = &v7;
      v11 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180048E90, (unsigned __int8 *)word_18003F00A, 0, 0, 3u, &v9);
    }
    return 0;
  }
  else
  {
    RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x18000cb9c  mov     [rsp-8+arg_0], rbx
0x18000cba1  mov     [rsp-8+arg_8], rdi
0x18000cba6  push    rbp
0x18000cba7  lea     rbp, [rsp-790h]
0x18000cbaf  sub     rsp, 890h
0x18000cbb6  mov     rax, cs:__security_cookie
0x18000cbbd  xor     rax, rsp
0x18000cbc0  mov     [rbp+790h+var_10], rax
0x18000cbc7  xor     edi, edi
0x18000cbc9  lea     rax, [rbp+790h+var_810]
0x18000cbcd  mov     [rsp+890h+var_860], rdi
0x18000cbd2  lea     rcx, aWinevt; "WINEVT"
0x18000cbd9  mov     dword ptr [rsp+890h+var_868], 400h
0x18000cbe1  xor     r9d, r9d
0x18000cbe4  xor     r8d, r8d
0x18000cbe7  mov     [rsp+890h+phkResult], rax
0x18000cbec  xor     edx, edx
0x18000cbee  mov     [rsp+890h+hKey], rdi
0x18000cbf3  mov     ebx, edi
0x18000cbf5  call    cs:__imp_RtlGetPersistedStateLocation
0x18000cbfb  mov     r10d, 200h
0x18000cc01  test    eax, eax
0x18000cc03  jns     short loc_18000CC5F
0x18000cc05  mov     ecx, 7FFFFFFEh
0x18000cc0a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000cc11  mov     r8d, r10d
0x18000cc14  lea     rax, [rbp+790h+var_810]
0x18000cc18  test    rcx, rcx
0x18000cc1b  jz      short loc_18000CC3C
0x18000cc1d  movzx   r9d, word ptr [rdx]
0x18000cc21  test    r9w, r9w
0x18000cc25  jz      short loc_18000CC3C
0x18000cc27  mov     [rax], r9w
0x18000cc2b  add     rdx, 2
0x18000cc2f  add     rax, 2
0x18000cc33  dec     rcx
0x18000cc36  sub     r8, 1
0x18000cc3a  jnz     short loc_18000CC18
0x18000cc3c  test    r8, r8
0x18000cc3f  lea     rcx, [rax-2]
0x18000cc43  cmovnz  rcx, rax
0x18000cc47  mov     rax, r8
0x18000cc4a  neg     rax
0x18000cc4d  sbb     ebx, ebx
0x18000cc4f  not     ebx
0x18000cc51  mov     [rcx], di
0x18000cc54  and     ebx, 8007007Ah
0x18000cc5a  test    r8, r8
0x18000cc5d  jz      short loc_18000CCBF
0x18000cc5f  lea     rax, aPolicies; "Policies"
0x18000cc66  mov     rdx, r10; unsigned __int64
0x18000cc69  lea     r9, [rbp+790h+var_810]
0x18000cc6d  mov     [rsp+890h+phkResult], rax
0x18000cc72  lea     r8, aSS_0; "%s\\%s"
0x18000cc79  lea     rcx, [rbp+790h+SubKey]; unsigned __int16 *
0x18000cc80  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cc85  lea     rcx, [rsp+890h+hKey]
0x18000cc8a  mov     r9d, 20019h; samDesired
0x18000cc90  mov     [rsp+890h+phkResult], rcx; phkResult
0x18000cc95  lea     rdx, [rbp+790h+SubKey]; lpSubKey
0x18000cc9c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000cca3  xor     r8d, r8d; ulOptions
0x18000cca6  call    cs:__imp_RegOpenKeyExW
0x18000ccac  test    eax, eax
0x18000ccae  jnz     short loc_18000CCBF
0x18000ccb0  mov     rcx, [rsp+890h+hKey]; hKey
0x18000ccb5  call    cs:__imp_RegCloseKey
0x18000ccbb  mov     al, 1
0x18000ccbd  jmp     short loc_18000CD0E
0x18000ccbf  mov     eax, cs:dword_180048E90
0x18000ccc5  cmp     eax, 5
0x18000ccc8  jbe     short loc_18000CD0C
0x18000ccca  lea     rax, [rsp+890h+var_850]
0x18000cccf  mov     [rsp+890h+var_850], ebx
0x18000ccd3  mov     [rsp+890h+var_820], rax
0x18000ccd8  lea     rdx, word_18003F00A
0x18000ccdf  lea     rax, [rsp+890h+var_840]
0x18000cce4  mov     [rsp+890h+var_818], 4
0x18000cced  mov     [rsp+890h+var_868], rax
0x18000ccf2  lea     rcx, dword_180048E90
0x18000ccf9  xor     r9d, r9d
0x18000ccfc  mov     dword ptr [rsp+890h+phkResult], 3
0x18000cd04  xor     r8d, r8d
0x18000cd07  call    _tlgWriteTransfer_EventWriteTransfer
0x18000cd0c  xor     al, al
0x18000cd0e  mov     rcx, [rbp+790h+var_10]
0x18000cd15  xor     rcx, rsp; StackCookie
0x18000cd18  call    __security_check_cookie
0x18000cd1d  lea     r11, [rsp+890h+var_s0]
0x18000cd25  mov     rbx, [r11+10h]
0x18000cd29  mov     rdi, [r11+18h]
0x18000cd2d  mov     rsp, r11
0x18000cd30  pop     rbp
0x18000cd31  retn
```
