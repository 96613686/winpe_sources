# Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessConfiguration(Windows::Internal::AssignedAccess::IAssignedAccessConfiguration * *)

- ea: `0x18000be24`
- end: `0x18000be85`
- name: `?GetAssignedAccessConfiguration@AAManagerHelper@AssignedAccess@Internal@Windows@@AEAAJPEAPEAUIAssignedAccessConfiguration@234@@Z`
- size: `97`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AAManagerHelper *this, struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be8c`

## callees

- `0x180006804`
- `0x18000be24`
- `0x18000e010`

## string_xrefs

- `0x18000be4e`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\aamanagerhelper.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::AAManagerHelper::GetAssignedAccessConfiguration(
        Windows::Internal::AssignedAccess::AAManagerHelper *this,
        struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration **a2)
{
  int v2; // ebx
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = *((_DWORD *)this + 2);
  if ( v2 )
  {
    if ( v2 != -2147221164 )
    {
      if ( v2 >= 0 )
        return (unsigned int)v2;
      v3 = 161;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v3,
        (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\aamanagerhelper.cpp",
        (const char *)(unsigned int)v2,
        v5);
      return (unsigned int)v2;
    }
  }
  else
  {
    v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this);
    if ( v2 < 0 )
    {
      v3 = 163;
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000be24  push    rbx; int
0x18000be26  sub     rsp, 20h
0x18000be2a  mov     qword ptr [rdx], 0
0x18000be31  mov     ebx, [rcx+8]
0x18000be34  test    ebx, ebx
0x18000be36  jz      short loc_18000BE61
0x18000be38  cmp     ebx, 80040154h
0x18000be3e  jz      short loc_18000BE7D
0x18000be40  test    ebx, ebx
0x18000be42  jns     short loc_18000BE5D
0x18000be44  mov     edx, 0A1h; void *
0x18000be49  mov     rcx, [rsp+28h]; this
0x18000be4e  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x18000be55  mov     r9d, ebx; char *
0x18000be58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be5d  mov     eax, ebx
0x18000be5f  jmp     short loc_18000BE7F
0x18000be61  mov     rcx, [rcx]
0x18000be64  mov     rax, [rcx]
0x18000be67  mov     rax, [rax+38h]
0x18000be6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be70  mov     ebx, eax
0x18000be72  test    eax, eax
0x18000be74  jns     short loc_18000BE7D
0x18000be76  mov     edx, 0A3h
0x18000be7b  jmp     short loc_18000BE49
0x18000be7d  xor     eax, eax
0x18000be7f  add     rsp, 20h
0x18000be83  pop     rbx
0x18000be84  retn
```
