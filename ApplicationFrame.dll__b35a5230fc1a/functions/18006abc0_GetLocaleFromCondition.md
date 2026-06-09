# GetLocaleFromCondition

- ea: `0x18006abc0`
- end: `0x18006ac8f`
- name: `GetLocaleFromCondition`
- size: `207`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063f7c`
- `0x180067b90`
- `0x1800681f8`

## callees

- `0x180043c30`
- `0x18006ab9c`
- `0x18006abc0`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18006ac46`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18006ac46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ac60`

## pseudocode

```c
__int64 __fastcall GetLocaleFromCondition(__int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *), int *a2)
{
  __int64 (__fastcall **v2)(_QWORD, GUID *, __int64 *); // rax
  int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, LPCWSTR *); // rbx
  LCID v7; // eax
  int v8; // ecx
  LPCWSTR lpName; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+28h] [rbp-20h] BYREF

  *a2 = 0;
  v2 = *a1;
  v11 = 0;
  v4 = (*v2)(a1, &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7, &v11);
  if ( v4 >= 0 )
  {
    v5 = v11;
    lpName = 0;
    v6 = *(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v11 + 120LL);
    CoTaskMemFree(0);
    v4 = v6(v5, &lpName);
    if ( v4 >= 0 )
    {
      v7 = LocaleNameToLCID(lpName, 0);
      v8 = 127;
      if ( v7 != 4096 )
        v8 = v7;
      *a2 = v8;
    }
    CoTaskMemFree((LPVOID)lpName);
  }
  ATL::CComPtr<ICondition2>::~CComPtr<ICondition2>(&v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006abc0  mov     r11, rsp
0x18006abc3  mov     [r11+18h], rbx
0x18006abc7  mov     [r11+20h], rsi
0x18006abcb  push    rdi
0x18006abcc  sub     rsp, 40h
0x18006abd0  mov     rax, cs:__security_cookie
0x18006abd7  xor     rax, rsp
0x18006abda  mov     [rsp+48h+var_18], rax
0x18006abdf  mov     dword ptr [rdx], 0
0x18006abe5  lea     r8, [r11-20h]
0x18006abe9  mov     rax, [rcx]
0x18006abec  mov     rsi, rdx
0x18006abef  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x18006abf6  mov     qword ptr [r11-20h], 0
0x18006abfe  mov     rax, [rax]
0x18006ac01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac06  mov     ebx, eax
0x18006ac08  test    eax, eax
0x18006ac0a  js      short loc_18006AC66
0x18006ac0c  mov     rdi, [rsp+48h+var_20]
0x18006ac11  xor     ecx, ecx; pv
0x18006ac13  mov     [rsp+48h+lpName], 0
0x18006ac1c  mov     rax, [rdi]
0x18006ac1f  mov     rbx, [rax+78h]
0x18006ac23  call    cs:__imp_CoTaskMemFree
0x18006ac29  lea     rdx, [rsp+48h+lpName]
0x18006ac2e  mov     rcx, rdi
0x18006ac31  mov     rax, rbx
0x18006ac34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac39  mov     ebx, eax
0x18006ac3b  test    eax, eax
0x18006ac3d  js      short loc_18006AC5B
0x18006ac3f  mov     rcx, [rsp+48h+lpName]; lpName
0x18006ac44  xor     edx, edx; dwFlags
0x18006ac46  call    cs:__imp_LocaleNameToLCID
0x18006ac4c  cmp     eax, 1000h
0x18006ac51  mov     ecx, 7Fh
0x18006ac56  cmovnz  ecx, eax
0x18006ac59  mov     [rsi], ecx
0x18006ac5b  mov     rcx, [rsp+48h+lpName]; pv
0x18006ac60  call    cs:__imp_CoTaskMemFree
0x18006ac66  lea     rcx, [rsp+48h+var_20]
0x18006ac6b  call    ??1?$CComPtr@UICondition2@@@ATL@@QEAA@XZ; ATL::CComPtr<ICondition2>::~CComPtr<ICondition2>(void)
0x18006ac70  mov     eax, ebx
0x18006ac72  mov     rcx, [rsp+48h+var_18]
0x18006ac77  xor     rcx, rsp; StackCookie
0x18006ac7a  call    __security_check_cookie
0x18006ac7f  mov     rbx, [rsp+48h+arg_10]
0x18006ac84  mov     rsi, [rsp+48h+arg_18]
0x18006ac89  add     rsp, 40h
0x18006ac8d  pop     rdi
0x18006ac8e  retn
```
