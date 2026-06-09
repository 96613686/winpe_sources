# WcmCommon::Registry::CreateKeyRO(HKEY__ * const,wchar_t const * const)

- ea: `0x18000a9c0`
- end: `0x18000aa03`
- name: `?CreateKeyRO@Registry@WcmCommon@@YA?AVKey@12@QEAUHKEY__@@QEB_W@Z`
- size: `67`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009614`
- `0x1800135e0`
- `0x1800213d4`
- `0x180021d48`
- `0x1800222d0`

## callees

- `0x180006c78`
- `0x18000a9c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a9f4`

## pseudocode

```c
_QWORD *__fastcall WcmCommon::Registry::CreateKeyRO(_QWORD *a1, __int64 a2, const WCHAR *a3)
{
  _QWORD *v4; // rax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = (HKEY)a2;
  v4 = WcmCommon::Registry::Details::CreateKey(&hKey, a2, a3, 0x20019u);
  *a1 = *v4;
  *v4 = 0;
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x18000a9c0  mov     [rsp+hKey], rdx
0x18000a9c5  push    rbx
0x18000a9c6  sub     rsp, 30h
0x18000a9ca  mov     rbx, rcx
0x18000a9cd  mov     r9d, 20019h
0x18000a9d3  lea     rcx, [rsp+38h+hKey]
0x18000a9d8  call    ?CreateKey@Details@Registry@WcmCommon@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAUHKEY__@@QEB_WK@Z; WcmCommon::Registry::Details::CreateKey(HKEY__ * const,wchar_t const * const,ulong)
0x18000a9dd  mov     rdx, [rax]
0x18000a9e0  mov     [rbx], rdx
0x18000a9e3  mov     qword ptr [rax], 0
0x18000a9ea  mov     rcx, [rsp+38h+hKey]; hKey
0x18000a9ef  test    rcx, rcx
0x18000a9f2  jz      short loc_18000A9FA
0x18000a9f4  call    cs:__imp_RegCloseKey
0x18000a9fa  mov     rax, rbx
0x18000a9fd  add     rsp, 30h
0x18000aa01  pop     rbx
0x18000aa02  retn
```
