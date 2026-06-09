# Windows::Internal::AssignedAccess::AAManagerHelper::AAManagerHelper(void)

- ea: `0x180048450`
- end: `0x18004852f`
- name: `??0AAManagerHelper@AssignedAccess@Internal@Windows@@QEAA@XZ`
- size: `223`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AAManagerHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800061f8`

## callees

- `0x180031960`
- `0x1800327d4`
- `0x180048450`
- `0x180048628`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800484b1`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800484b1`

## string_xrefs

- `0x180048482`: `Windows.Internal.AssignedAccess.AssignedAccessManager`

## pseudocode

```c
Windows::Internal::AssignedAccess::AAManagerHelper *__fastcall Windows::Internal::AssignedAccess::AAManagerHelper::AAManagerHelper(
        Windows::Internal::AssignedAccess::AAManagerHelper *this)
{
  __int64 v2; // rcx
  int v3; // edi
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]

  *(_QWORD *)this = 0;
  v7 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.AssignedAccess.AssignedAccessManager",
    0x36u,
    0x35u);
  v2 = v7;
  *(_QWORD *)this = 0;
  v5 = 0;
  v3 = RoActivateInstance(v2, &v5);
  if ( v3 >= 0 )
  {
    if ( !memcmp_0(&GUID_3ea0718b_7dc4_4cb2_83fa_9f86d639fc6a, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *(_QWORD *)this = v5;
    }
    else
    {
      v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, Windows::Internal::AssignedAccess::AAManagerHelper *))v5)(
             v5,
             &GUID_3ea0718b_7dc4_4cb2_83fa_9f86d639fc6a,
             this);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  *((_DWORD *)this + 2) = v3;
  return this;
}

```

## disassembly

```asm
0x180048450  mov     [rsp+arg_8], rbx
0x180048455  push    rdi
0x180048456  sub     rsp, 50h
0x18004845a  mov     rax, cs:__security_cookie
0x180048461  xor     rax, rsp
0x180048464  mov     [rsp+58h+var_10], rax
0x180048469  mov     r9d, 35h ; '5'; unsigned int
0x18004846f  mov     qword ptr [rcx], 0
0x180048476  mov     rbx, rcx
0x180048479  mov     [rsp+58h+var_18], 0
0x180048482  lea     rdx, ?RuntimeClass_Windows_Internal_AssignedAccess_AssignedAccessManager@@3QBGB; "Windows.Internal.AssignedAccess.Assigne"...
0x180048489  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x18004848e  lea     r8d, [r9+1]; unsigned int
0x180048492  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180048497  mov     rcx, [rsp+58h+var_18]
0x18004849c  lea     rdx, [rsp+58h+var_38]
0x1800484a1  mov     qword ptr [rbx], 0
0x1800484a8  mov     [rsp+58h+var_38], 0
0x1800484b1  call    cs:__imp_RoActivateInstance
0x1800484b7  mov     edi, eax
0x1800484b9  test    eax, eax
0x1800484bb  js      short loc_180048511
0x1800484bd  mov     r8d, 10h; Size
0x1800484c3  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800484ca  lea     rcx, _GUID_3ea0718b_7dc4_4cb2_83fa_9f86d639fc6a; Buf1
0x1800484d1  call    memcmp_0
0x1800484d6  test    eax, eax
0x1800484d8  jnz     short loc_1800484E4
0x1800484da  mov     rax, [rsp+58h+var_38]
0x1800484df  mov     [rbx], rax
0x1800484e2  jmp     short loc_180048511
0x1800484e4  mov     rcx, [rsp+58h+var_38]
0x1800484e9  lea     rdx, _GUID_3ea0718b_7dc4_4cb2_83fa_9f86d639fc6a
0x1800484f0  mov     r8, rbx
0x1800484f3  mov     rax, [rcx]
0x1800484f6  mov     rax, [rax]
0x1800484f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484fe  mov     rcx, [rsp+58h+var_38]
0x180048503  mov     edi, eax
0x180048505  mov     rdx, [rcx]
0x180048508  mov     rax, [rdx+10h]
0x18004850c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048511  mov     [rbx+8], edi
0x180048514  mov     rax, rbx
0x180048517  mov     rcx, [rsp+58h+var_10]
0x18004851c  xor     rcx, rsp; StackCookie
0x18004851f  call    __security_check_cookie
0x180048524  mov     rbx, [rsp+58h+arg_8]
0x180048529  add     rsp, 50h
0x18004852d  pop     rdi
0x18004852e  retn
```
