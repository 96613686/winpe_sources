# CLocationCamPrimitives::IsCtaPolicyActive(void)

- ea: `0x18004ac50`
- end: `0x18004ad5e`
- name: `?IsCtaPolicyActive@CLocationCamPrimitives@@SA_NXZ`
- size: `270`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004edbc`

## callees

- `0x18004ac50`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004aca8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004acf3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004aca8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004acf3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ad15`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004ad15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004acba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004acba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad56`

## string_xrefs

- `0x18004ac8a`: `Software\Microsoft\Windows\CurrentVersion\DeviceAccess`
- `0x18004accd`: `Software\Microsoft\Windows\CurrentVersion\DeviceAccess`

## pseudocode

```c
bool CLocationCamPrimitives::IsCtaPolicyActive(void)
{
  void *pvData; // rbx
  bool v1; // di
  SIZE_T cb; // [rsp+40h] [rbp-18h] BYREF

  LODWORD(cb) = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess",
         L"ActivePolicyCode",
         2u,
         0,
         0,
         (LPDWORD)&cb) )
  {
    return 0;
  }
  pvData = CoTaskMemAlloc((unsigned int)cb);
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess",
         L"ActivePolicyCode",
         2u,
         0,
         pvData,
         (LPDWORD)&cb) )
  {
    if ( pvData )
      CoTaskMemFree(pvData);
    return 0;
  }
  v1 = CompareStringOrdinal((LPCWCH)pvData, -1, L"zh", -1, 1) == 2;
  if ( pvData )
    CoTaskMemFree(pvData);
  return v1;
}

```

## disassembly

```asm
0x18004ac50  mov     r11, rsp
0x18004ac53  mov     [r11+8], rbx
0x18004ac57  push    rdi
0x18004ac58  sub     rsp, 50h
0x18004ac5c  mov     rax, cs:__security_cookie
0x18004ac63  xor     rax, rsp
0x18004ac66  mov     [rsp+58h+var_10], rax
0x18004ac6b  lea     rax, [r11-18h]
0x18004ac6f  mov     dword ptr [rsp+58h+cb], 0
0x18004ac77  mov     [r11-28h], rax
0x18004ac7b  lea     r8, ?c_activePolicyCodeName@@3QBGB; "ActivePolicyCode"
0x18004ac82  mov     qword ptr [r11-30h], 0
0x18004ac8a  lea     rdx, ?c_deviceAccessRegKey@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004ac91  mov     edi, 2
0x18004ac96  mov     qword ptr [r11-38h], 0
0x18004ac9e  mov     r9d, edi; dwFlags
0x18004aca1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18004aca8  call    cs:__imp_RegGetValueW
0x18004acae  test    eax, eax
0x18004acb0  jnz     loc_18004AD4F
0x18004acb6  mov     ecx, dword ptr [rsp+58h+cb]; cb
0x18004acba  call    cs:__imp_CoTaskMemAlloc
0x18004acc0  mov     r9d, edi; dwFlags
0x18004acc3  lea     r8, ?c_activePolicyCodeName@@3QBGB; "ActivePolicyCode"
0x18004acca  mov     rbx, rax
0x18004accd  lea     rdx, ?c_deviceAccessRegKey@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004acd4  lea     rax, [rsp+58h+cb]
0x18004acd9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18004ace0  mov     [rsp+58h+pcbData], rax; pcbData
0x18004ace5  mov     [rsp+58h+pvData], rbx; pvData
0x18004acea  mov     [rsp+58h+pdwType], 0; pdwType
0x18004acf3  call    cs:__imp_RegGetValueW
0x18004acf9  test    eax, eax
0x18004acfb  jnz     short loc_18004AD4A
0x18004acfd  or      edx, 0FFFFFFFFh; cchCount1
0x18004ad00  mov     dword ptr [rsp+58h+pdwType], 1; bIgnoreCase
0x18004ad08  mov     r9d, edx; cchCount2
0x18004ad0b  lea     r8, ?c_ctaPolicyCode@@3QBGB; "zh"
0x18004ad12  mov     rcx, rbx; lpString1
0x18004ad15  call    cs:__imp_CompareStringOrdinal
0x18004ad1b  cmp     eax, edi
0x18004ad1d  setz    dil
0x18004ad21  test    rbx, rbx
0x18004ad24  jz      short loc_18004AD2F
0x18004ad26  mov     rcx, rbx; pv
0x18004ad29  call    cs:__imp_CoTaskMemFree
0x18004ad2f  mov     al, dil
0x18004ad32  mov     rcx, [rsp+58h+var_10]
0x18004ad37  xor     rcx, rsp; StackCookie
0x18004ad3a  call    __security_check_cookie
0x18004ad3f  mov     rbx, [rsp+58h+arg_0]
0x18004ad44  add     rsp, 50h
0x18004ad48  pop     rdi
0x18004ad49  retn
0x18004ad4a  test    rbx, rbx
0x18004ad4d  jnz     short loc_18004AD53
0x18004ad4f  xor     al, al
0x18004ad51  jmp     short loc_18004AD32
0x18004ad53  mov     rcx, rbx; pv
0x18004ad56  call    cs:__imp_CoTaskMemFree
0x18004ad5c  jmp     short loc_18004AD4F
```
