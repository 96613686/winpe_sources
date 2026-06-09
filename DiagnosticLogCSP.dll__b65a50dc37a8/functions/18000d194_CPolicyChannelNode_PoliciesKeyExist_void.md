# CPolicyChannelNode::PoliciesKeyExist(void)

- ea: `0x18000d194`
- end: `0x18000d33d`
- name: `?PoliciesKeyExist@CPolicyChannelNode@@CA_NXZ`
- size: `425`
- prototype: `bool(void)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c210`
- `0x18000c4a0`
- `0x18000c7b0`
- `0x18000ce20`
- `0x18000d4f0`

## callees

- `0x180001108`
- `0x180001b90`
- `0x180006498`
- `0x18000d194`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18000d1ed`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000d1ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d2b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d2b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d2a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d2a4`

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
    if ( (unsigned int)dword_18004AE90 > 5 )
    {
      v7 = v0;
      v10 = &v7;
      v11 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004AE90, (unsigned __int8 *)word_18004100A, 0, 0, 3u, &v9);
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
0x18000d194  mov     [rsp-8+arg_0], rbx
0x18000d199  mov     [rsp-8+arg_8], rdi
0x18000d19e  push    rbp
0x18000d19f  lea     rbp, [rsp-790h]
0x18000d1a7  sub     rsp, 890h
0x18000d1ae  mov     rax, cs:__security_cookie
0x18000d1b5  xor     rax, rsp
0x18000d1b8  mov     [rbp+790h+var_10], rax
0x18000d1bf  xor     edi, edi
0x18000d1c1  lea     rax, [rbp+790h+var_810]
0x18000d1c5  mov     [rsp+890h+var_860], rdi
0x18000d1ca  lea     rcx, aWinevt; "WINEVT"
0x18000d1d1  mov     dword ptr [rsp+890h+var_868], 400h
0x18000d1d9  xor     r9d, r9d
0x18000d1dc  xor     r8d, r8d
0x18000d1df  mov     [rsp+890h+phkResult], rax
0x18000d1e4  xor     edx, edx
0x18000d1e6  mov     [rsp+890h+hKey], rdi
0x18000d1eb  mov     ebx, edi
0x18000d1ed  call    cs:__imp_RtlGetPersistedStateLocation
0x18000d1f4  nop     dword ptr [rax+rax+00h]
0x18000d1f9  mov     r10d, 200h
0x18000d1ff  test    eax, eax
0x18000d201  jns     short loc_18000D25D
0x18000d203  mov     ecx, 7FFFFFFEh
0x18000d208  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000d20f  mov     r8d, r10d
0x18000d212  lea     rax, [rbp+790h+var_810]
0x18000d216  test    rcx, rcx
0x18000d219  jz      short loc_18000D23A
0x18000d21b  movzx   r9d, word ptr [rdx]
0x18000d21f  test    r9w, r9w
0x18000d223  jz      short loc_18000D23A
0x18000d225  mov     [rax], r9w
0x18000d229  add     rdx, 2
0x18000d22d  add     rax, 2
0x18000d231  dec     rcx
0x18000d234  sub     r8, 1
0x18000d238  jnz     short loc_18000D216
0x18000d23a  test    r8, r8
0x18000d23d  lea     rcx, [rax-2]
0x18000d241  cmovnz  rcx, rax
0x18000d245  mov     rax, r8
0x18000d248  neg     rax
0x18000d24b  sbb     ebx, ebx
0x18000d24d  not     ebx
0x18000d24f  mov     [rcx], di
0x18000d252  and     ebx, 8007007Ah
0x18000d258  test    r8, r8
0x18000d25b  jz      short loc_18000D2C9
0x18000d25d  lea     rax, aPolicies; "Policies"
0x18000d264  mov     rdx, r10; unsigned __int64
0x18000d267  lea     r9, [rbp+790h+var_810]
0x18000d26b  mov     [rsp+890h+phkResult], rax
0x18000d270  lea     r8, aSS_0; "%s\\%s"
0x18000d277  lea     rcx, [rbp+790h+SubKey]; unsigned __int16 *
0x18000d27e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d283  lea     rcx, [rsp+890h+hKey]
0x18000d288  mov     r9d, 20019h; samDesired
0x18000d28e  mov     [rsp+890h+phkResult], rcx; phkResult
0x18000d293  lea     rdx, [rbp+790h+SubKey]; lpSubKey
0x18000d29a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d2a1  xor     r8d, r8d; ulOptions
0x18000d2a4  call    cs:__imp_RegOpenKeyExW
0x18000d2ab  nop     dword ptr [rax+rax+00h]
0x18000d2b0  test    eax, eax
0x18000d2b2  jnz     short loc_18000D2C9
0x18000d2b4  mov     rcx, [rsp+890h+hKey]; hKey
0x18000d2b9  call    cs:__imp_RegCloseKey
0x18000d2c0  nop     dword ptr [rax+rax+00h]
0x18000d2c5  mov     al, 1
0x18000d2c7  jmp     short loc_18000D318
0x18000d2c9  mov     eax, cs:dword_18004AE90
0x18000d2cf  cmp     eax, 5
0x18000d2d2  jbe     short loc_18000D316
0x18000d2d4  lea     rax, [rsp+890h+var_850]
0x18000d2d9  mov     [rsp+890h+var_850], ebx
0x18000d2dd  mov     [rsp+890h+var_820], rax
0x18000d2e2  lea     rdx, word_18004100A
0x18000d2e9  lea     rax, [rsp+890h+var_840]
0x18000d2ee  mov     [rsp+890h+var_818], 4
0x18000d2f7  mov     [rsp+890h+var_868], rax
0x18000d2fc  lea     rcx, dword_18004AE90
0x18000d303  xor     r9d, r9d
0x18000d306  mov     dword ptr [rsp+890h+phkResult], 3
0x18000d30e  xor     r8d, r8d
0x18000d311  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d316  xor     al, al
0x18000d318  mov     rcx, [rbp+790h+var_10]
0x18000d31f  xor     rcx, rsp; StackCookie
0x18000d322  call    __security_check_cookie
0x18000d327  lea     r11, [rsp+890h+var_s0]
0x18000d32f  mov     rbx, [r11+10h]
0x18000d333  mov     rdi, [r11+18h]
0x18000d337  mov     rsp, r11
0x18000d33a  pop     rbp
0x18000d33b  retn
```
