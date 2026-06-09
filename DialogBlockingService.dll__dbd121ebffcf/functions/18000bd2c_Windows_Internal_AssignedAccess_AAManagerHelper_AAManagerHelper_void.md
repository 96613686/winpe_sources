# Windows::Internal::AssignedAccess::AAManagerHelper::AAManagerHelper(void)

- ea: `0x18000bd2c`
- end: `0x18000be1b`
- name: `??0AAManagerHelper@AssignedAccess@Internal@Windows@@QEAA@XZ`
- size: `239`
- prototype: `Windows::Internal::AssignedAccess::AAManagerHelper *__fastcall(Windows::Internal::AssignedAccess::AAManagerHelper *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ab90`

## callees

- `0x180001620`
- `0x18000bd2c`
- `0x18000bff0`
- `0x18000c7e4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bd6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bd6d`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000bd95`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000bd95`

## string_xrefs

- `0x18000bd51`: `Windows.Internal.AssignedAccess.AssignedAccessManager`

## pseudocode

```c
Windows::Internal::AssignedAccess::AAManagerHelper *__fastcall Windows::Internal::AssignedAccess::AAManagerHelper::AAManagerHelper(
        Windows::Internal::AssignedAccess::AAManagerHelper *this)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  HSTRING v5; // rcx
  int v6; // edi
  __int64 v8; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER v9; // [rsp+28h] [rbp-30h] BYREF
  HSTRING v10; // [rsp+40h] [rbp-18h] BYREF

  *(_QWORD *)this = 0;
  v10 = 0;
  v2 = WindowsCreateStringReference(L"Windows.Internal.AssignedAccess.AssignedAccessManager", 0x35u, &v9, &v10);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x18000BE1ALL);
  }
  v5 = v10;
  *(_QWORD *)this = 0;
  v8 = 0;
  v6 = RoActivateInstance(v5, &v8);
  if ( v6 >= 0 )
  {
    if ( !memcmp_0(&GUID_3ea0718b_7dc4_4cb2_83fa_9f86d639fc6a, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *(_QWORD *)this = v8;
    }
    else
    {
      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, Windows::Internal::AssignedAccess::AAManagerHelper *))v8)(
             v8,
             &GUID_3ea0718b_7dc4_4cb2_83fa_9f86d639fc6a,
             this);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  *((_DWORD *)this + 2) = v6;
  return this;
}

```

## disassembly

```asm
0x18000bd2c  mov     r11, rsp
0x18000bd2f  mov     [r11+10h], rbx
0x18000bd33  push    rdi
0x18000bd34  sub     rsp, 50h
0x18000bd38  mov     rax, cs:__security_cookie
0x18000bd3f  xor     rax, rsp
0x18000bd42  mov     [rsp+58h+var_10], rax
0x18000bd47  mov     rbx, rcx
0x18000bd4a  mov     qword ptr [rcx], 0
0x18000bd51  lea     rcx, ?RuntimeClass_Windows_Internal_AssignedAccess_AssignedAccessManager@@3QBGB; "Windows.Internal.AssignedAccess.Assigne"...
0x18000bd58  mov     qword ptr [r11-18h], 0
0x18000bd60  lea     r9, [r11-18h]; string
0x18000bd64  mov     edx, 35h ; '5'; length
0x18000bd69  lea     r8, [r11-30h]; hstringHeader
0x18000bd6d  call    cs:__imp_WindowsCreateStringReference
0x18000bd73  test    eax, eax
0x18000bd75  js      loc_18000BE13
0x18000bd7b  mov     rcx, [rsp+58h+var_18]
0x18000bd80  lea     rdx, [rsp+58h+var_38]
0x18000bd85  mov     qword ptr [rbx], 0
0x18000bd8c  mov     [rsp+58h+var_38], 0
0x18000bd95  call    cs:__imp_RoActivateInstance
0x18000bd9b  mov     edi, eax
0x18000bd9d  test    eax, eax
0x18000bd9f  js      short loc_18000BDF5
0x18000bda1  mov     r8d, 10h; Size
0x18000bda7  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18000bdae  lea     rcx, _GUID_3ea0718b_7dc4_4cb2_83fa_9f86d639fc6a; Buf1
0x18000bdb5  call    memcmp_0
0x18000bdba  test    eax, eax
0x18000bdbc  jnz     short loc_18000BDC8
0x18000bdbe  mov     rax, [rsp+58h+var_38]
0x18000bdc3  mov     [rbx], rax
0x18000bdc6  jmp     short loc_18000BDF5
0x18000bdc8  mov     rcx, [rsp+58h+var_38]
0x18000bdcd  lea     rdx, _GUID_3ea0718b_7dc4_4cb2_83fa_9f86d639fc6a
0x18000bdd4  mov     r8, rbx
0x18000bdd7  mov     rax, [rcx]
0x18000bdda  mov     rax, [rax]
0x18000bddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde2  mov     rcx, [rsp+58h+var_38]
0x18000bde7  mov     edi, eax
0x18000bde9  mov     rdx, [rcx]
0x18000bdec  mov     rax, [rdx+10h]
0x18000bdf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf5  mov     [rbx+8], edi
0x18000bdf8  mov     rax, rbx
0x18000bdfb  mov     rcx, [rsp+58h+var_10]
0x18000be00  xor     rcx, rsp; StackCookie
0x18000be03  call    __security_check_cookie
0x18000be08  mov     rbx, [rsp+58h+arg_8]
0x18000be0d  add     rsp, 50h
0x18000be11  pop     rdi
0x18000be12  retn
0x18000be13  mov     ecx, eax; this
0x18000be15  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
