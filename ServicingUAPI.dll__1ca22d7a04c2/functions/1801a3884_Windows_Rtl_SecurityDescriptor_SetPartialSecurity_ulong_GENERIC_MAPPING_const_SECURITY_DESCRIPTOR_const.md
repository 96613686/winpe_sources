# Windows::Rtl::SecurityDescriptor::SetPartialSecurity(ulong,_GENERIC_MAPPING const &,_SECURITY_DESCRIPTOR const &)

- ea: `0x1801a3884`
- end: `0x1801a3abe`
- name: `?SetPartialSecurity@SecurityDescriptor@Rtl@Windows@@QEAAJKAEBU_GENERIC_MAPPING@@AEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(Windows::Rtl::SecurityDescriptor *__hidden this, SECURITY_INFORMATION SecurityInformation, PGENERIC_MAPPING GenericMapping, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18015e730`

## callees

- `0x1800031d0`
- `0x1800497c0`
- `0x18004ecdc`
- `0x18004f350`
- `0x1801a1f0c`
- `0x1801a28c0`
- `0x1801a2abc`
- `0x1801a2b58`
- `0x1801a3884`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1801a391f`
- `ntdll!RtlFreeHeap` at `0x1801a3a83`
- `ntdll!RtlFreeHeap` at `0x1801a391f`
- `ntdll!RtlFreeHeap` at `0x1801a3a83`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1801a3a20`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1801a3a20`
- `ntdll!RtlSetSecurityObjectEx` at `0x1801a39ba`
- `ntdll!RtlSetSecurityObjectEx` at `0x1801a39ba`

## string_xrefs

- `0x1801a39cc`: `onecore\base\wcp\rtllib\nativelib\security_descriptor.cpp`
- `0x1801a39e6`: `Windows::Rtl::SecurityDescriptor::SetPartialSecurity`
- `0x1801a39f8`: `::RtlSetSecurityObjectEx( SecurityInformation, LocalSetSD.GetOpaque(), LocalSD.GetReAllocPointer(), 0x08, &Mapping, ( (HANDLE)(LONG_PTR) -6 ))`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SecurityDescriptor::SetPartialSecurity(
        const char **this,
        SECURITY_INFORMATION SecurityInformation,
        PGENERIC_MAPPING GenericMapping,
        const struct _SECURITY_DESCRIPTOR *a4)
{
  struct _SECURITY_DESCRIPTOR *v8; // rax
  int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  struct _SECURITY_DESCRIPTOR *v13; // rax
  NTSTATUS v14; // eax
  const char *v15; // rbx
  PVOID v16; // rcx
  ULONG v17; // eax
  int v18; // eax
  char *v19; // [rsp+30h] [rbp-49h] BYREF
  const char *v20; // [rsp+38h] [rbp-41h]
  __int64 v21; // [rsp+40h] [rbp-39h]
  const char *v22; // [rsp+48h] [rbp-31h]
  PVOID P; // [rsp+50h] [rbp-29h] BYREF
  __int128 v24; // [rsp+60h] [rbp-19h] BYREF
  __int64 v25; // [rsp+70h] [rbp-9h]
  char v26; // [rsp+78h] [rbp-1h]
  __int16 v27; // [rsp+7Ah] [rbp+1h]
  __int128 v28; // [rsp+80h] [rbp+7h]
  __int128 v29; // [rsp+90h] [rbp+17h]

  P = 0;
  v8 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)this);
  v19 = 0;
  v20 = 0;
  v9 = Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(&v19, v8);
  if ( v9 >= 0 )
  {
    v9 = 0;
    P = v19;
    v19 = 0;
    v20 = 0;
  }
  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v19);
  if ( v9 < 0 )
    goto LABEL_4;
  LOBYTE(v10) = *((_BYTE *)this + 24);
  v25 = 0;
  v24 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v26 = 0;
  v9 = Windows::Rtl::SecurityDescriptor::Initialize(&v24, v10, 0, a4);
  if ( v9 < 0 || (v9 = Windows::Rtl::SecurityDescriptor::MapGenericPermissions((void **)&v24, GenericMapping), v9 < 0) )
  {
LABEL_8:
    Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v24);
LABEL_4:
    LOBYTE(v11) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    if ( !v11 )
      __fastfail(7u);
    return (unsigned int)v9;
  }
  v13 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v24);
  v14 = RtlSetSecurityObjectEx(SecurityInformation, v13, &P, 8u, GenericMapping, (HANDLE)0xFFFFFFFFFFFFFFFALL);
  v9 = v14;
  if ( v14 < 0 )
  {
    v21 = 1397;
    v19 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_descriptor.cpp";
    v20 = "Windows::Rtl::SecurityDescriptor::SetPartialSecurity";
    v22 = "::RtlSetSecurityObjectEx( SecurityInformation, LocalSetSD.GetOpaque(), LocalSD.GetReAllocPointer(), 0x08, &Map"
          "ping, ( (HANDLE)(LONG_PTR) -6 ))";
    RtlReportErrorOrigination(&v19, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v14);
    goto LABEL_8;
  }
  v15 = (const char *)P;
  v16 = P;
  this[2] = 0;
  v17 = RtlLengthSecurityDescriptor(v16);
  P = 0;
  v19 = (char *)*this;
  v20 = this[1];
  *this = v15;
  this[1] = (const char *)v17;
  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v19);
  v9 = Windows::Rtl::SecurityDescriptor::CacheDecomposed((Windows::Rtl::SecurityDescriptor *)this);
  if ( v9 < 0 )
    goto LABEL_8;
  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v24);
  LOBYTE(v18) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( !v18 )
    __fastfail(7u);
  return 0;
}

```

## disassembly

```asm
0x1801a3884  mov     [rsp-8+arg_18], rbx
0x1801a3889  push    rbp
0x1801a388a  push    rsi
0x1801a388b  push    rdi
0x1801a388c  push    r14
0x1801a388e  push    r15
0x1801a3890  lea     rbp, [rsp-37h]
0x1801a3895  sub     rsp, 0B0h
0x1801a389c  mov     rax, cs:__security_cookie
0x1801a38a3  xor     rax, rsp
0x1801a38a6  mov     [rbp+57h+var_30], rax
0x1801a38aa  mov     r14, r9
0x1801a38ad  mov     [rbp+57h+P], 0
0x1801a38b5  mov     rsi, r8
0x1801a38b8  mov     r15d, edx
0x1801a38bb  mov     rdi, rcx
0x1801a38be  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x1801a38c3  mov     rdx, rax
0x1801a38c6  mov     [rbp+57h+var_A0], 0
0x1801a38ce  lea     rcx, [rbp+57h+var_A0]
0x1801a38d2  mov     [rbp+57h+var_98], 0
0x1801a38da  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x1801a38df  mov     ebx, eax
0x1801a38e1  test    eax, eax
0x1801a38e3  js      short loc_1801A38FF
0x1801a38e5  mov     rax, [rbp+57h+var_A0]
0x1801a38e9  xor     ebx, ebx
0x1801a38eb  mov     [rbp+57h+P], rax
0x1801a38ef  mov     [rbp+57h+var_A0], 0
0x1801a38f7  mov     [rbp+57h+var_98], 0
0x1801a38ff  lea     rcx, [rbp+57h+var_A0]
0x1801a3903  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x1801a3908  test    ebx, ebx
0x1801a390a  jns     short loc_1801A393B
0x1801a390c  mov     rcx, gs:60h
0x1801a3915  xor     edx, edx; Flags
0x1801a3917  mov     r8, [rbp+57h+P]; P
0x1801a391b  mov     rcx, [rcx+30h]; HeapHandle
0x1801a391f  call    cs:__imp_RtlFreeHeap
0x1801a3926  nop     dword ptr [rax+rax+00h]
0x1801a392b  test    eax, eax
0x1801a392d  jnz     short loc_1801A3934
0x1801a392f  lea     ecx, [rax+7]
0x1801a3932  int     29h; Win8: RtlFailFast(ecx)
0x1801a3934  mov     eax, ebx
0x1801a3936  jmp     loc_1801A3A9A
0x1801a393b  mov     dl, [rdi+18h]
0x1801a393e  lea     rcx, [rbp+57h+var_70]
0x1801a3942  xorps   xmm0, xmm0
0x1801a3945  mov     [rbp+57h+var_60], 0
0x1801a394d  xor     eax, eax
0x1801a394f  movdqa  [rbp+57h+var_70], xmm0
0x1801a3954  xorps   xmm1, xmm1
0x1801a3957  mov     [rbp+57h+var_56], ax
0x1801a395b  mov     r9, r14
0x1801a395e  movdqa  [rbp+57h+var_50], xmm0
0x1801a3963  xor     r8d, r8d
0x1801a3966  movdqa  [rbp+57h+var_40], xmm1
0x1801a396b  mov     [rbp+57h+var_58], 0
0x1801a396f  call    ?Initialize@SecurityDescriptor@Rtl@Windows@@QEAAJ_NW4FixUpFlags@123@PEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Rtl::SecurityDescriptor::Initialize(bool,Windows::Rtl::SecurityDescriptor::FixUpFlags,_SECURITY_DESCRIPTOR const *)
0x1801a3974  lea     rcx, [rbp+57h+var_70]; this
0x1801a3978  mov     ebx, eax
0x1801a397a  test    eax, eax
0x1801a397c  jns     short loc_1801A3985
0x1801a397e  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x1801a3983  jmp     short loc_1801A390C
0x1801a3985  mov     rdx, rsi; GenericMapping
0x1801a3988  call    ?MapGenericPermissions@SecurityDescriptor@Rtl@Windows@@QEAAJAEBU_GENERIC_MAPPING@@@Z; Windows::Rtl::SecurityDescriptor::MapGenericPermissions(_GENERIC_MAPPING const &)
0x1801a398d  lea     rcx, [rbp+57h+var_70]; this
0x1801a3991  mov     ebx, eax
0x1801a3993  test    eax, eax
0x1801a3995  js      short loc_1801A397E
0x1801a3997  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x1801a399c  mov     r9d, 8; AutoInheritFlags
0x1801a39a2  mov     [rsp+0D0h+Token], 0FFFFFFFFFFFFFFFAh; Token
0x1801a39ab  lea     r8, [rbp+57h+P]; ObjectsSecurityDescriptor
0x1801a39af  mov     [rsp+0D0h+GenericMapping], rsi; GenericMapping
0x1801a39b4  mov     rdx, rax; ModificationDescriptor
0x1801a39b7  mov     ecx, r15d; SecurityInformation
0x1801a39ba  call    cs:__imp_RtlSetSecurityObjectEx
0x1801a39c1  nop     dword ptr [rax+rax+00h]
0x1801a39c6  mov     ebx, eax
0x1801a39c8  test    eax, eax
0x1801a39ca  jns     short loc_1801A3A11
0x1801a39cc  lea     rax, aOnecoreBaseWcp_12; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801a39d3  mov     [rbp+57h+var_90], 575h
0x1801a39db  mov     [rbp+57h+var_A0], rax
0x1801a39df  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801a39e6  lea     rax, aWindowsRtlSecu; "Windows::Rtl::SecurityDescriptor::SetPa"...
0x1801a39ed  mov     r8d, ebx
0x1801a39f0  mov     [rbp+57h+var_98], rax
0x1801a39f4  lea     rcx, [rbp+57h+var_A0]
0x1801a39f8  lea     rax, aRtlsetsecurity; "::RtlSetSecurityObjectEx( SecurityInfor"...
0x1801a39ff  mov     [rbp+57h+var_88], rax
0x1801a3a03  call    RtlReportErrorOrigination
0x1801a3a08  lea     rcx, [rbp+57h+var_70]
0x1801a3a0c  jmp     loc_1801A397E
0x1801a3a11  mov     rbx, [rbp+57h+P]
0x1801a3a15  mov     rcx, rbx; SecurityDescriptor
0x1801a3a18  mov     qword ptr [rdi+10h], 0
0x1801a3a20  call    cs:__imp_RtlLengthSecurityDescriptor
0x1801a3a27  nop     dword ptr [rax+rax+00h]
0x1801a3a2c  lea     rcx, [rbp+57h+var_A0]
0x1801a3a30  mov     [rbp+57h+P], 0
0x1801a3a38  mov     edx, eax
0x1801a3a3a  mov     rax, [rdi]
0x1801a3a3d  mov     [rbp+57h+var_A0], rax
0x1801a3a41  mov     rax, [rdi+8]
0x1801a3a45  mov     [rbp+57h+var_98], rax
0x1801a3a49  mov     [rdi], rbx
0x1801a3a4c  mov     [rdi+8], rdx
0x1801a3a50  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x1801a3a55  mov     rcx, rdi; this
0x1801a3a58  call    ?CacheDecomposed@SecurityDescriptor@Rtl@Windows@@AEAAJXZ; Windows::Rtl::SecurityDescriptor::CacheDecomposed(void)
0x1801a3a5d  lea     rcx, [rbp+57h+var_70]
0x1801a3a61  mov     ebx, eax
0x1801a3a63  test    eax, eax
0x1801a3a65  js      loc_1801A397E
0x1801a3a6b  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x1801a3a70  mov     rcx, gs:60h
0x1801a3a79  xor     edx, edx; Flags
0x1801a3a7b  mov     r8, [rbp+57h+P]; P
0x1801a3a7f  mov     rcx, [rcx+30h]; HeapHandle
0x1801a3a83  call    cs:__imp_RtlFreeHeap
0x1801a3a8a  nop     dword ptr [rax+rax+00h]
0x1801a3a8f  test    eax, eax
0x1801a3a91  jnz     short loc_1801A3A98
0x1801a3a93  lea     ecx, [rax+7]
0x1801a3a96  int     29h; Win8: RtlFailFast(ecx)
0x1801a3a98  xor     eax, eax
0x1801a3a9a  mov     rcx, [rbp+57h+var_30]
0x1801a3a9e  xor     rcx, rsp; StackCookie
0x1801a3aa1  call    __security_check_cookie
0x1801a3aa6  mov     rbx, [rsp+0D0h+arg_18]
0x1801a3aae  add     rsp, 0B0h
0x1801a3ab5  pop     r15
0x1801a3ab7  pop     r14
0x1801a3ab9  pop     rdi
0x1801a3aba  pop     rsi
0x1801a3abb  pop     rbp
0x1801a3abc  retn
```
