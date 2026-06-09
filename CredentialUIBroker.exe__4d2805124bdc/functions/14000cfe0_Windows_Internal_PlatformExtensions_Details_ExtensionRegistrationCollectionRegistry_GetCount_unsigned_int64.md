# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetCount(unsigned __int64 *)

- ea: `0x14000cfe0`
- end: `0x14000d07f`
- name: `?GetCount@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJPEA_K@Z`
- size: `159`
- prototype: `int __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x14000cfe0`
- `0x140013720`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x14000d04b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000d04b`

## string_xrefs

- `0x14000d05a`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetCount(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *this,
        unsigned __int64 *a2)
{
  HKEY v3; // rcx
  unsigned int v4; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD v8; // [rsp+70h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = (HKEY)*((_QWORD *)this + 1);
  if ( v3 )
  {
    v8 = 0;
    v4 = RegQueryInfoKeyW(v3, 0, 0, 0, &v8, 0, 0, 0, 0, 0, 0, 0);
    if ( v4 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x137,
               (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
               (const char *)v4,
               lpcSubKeys);
    *a2 = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x14000cfe0  mov     rax, rsp
0x14000cfe3  push    rbx
0x14000cfe4  sub     rsp, 60h
0x14000cfe8  mov     qword ptr [rdx], 0
0x14000cfef  mov     rbx, rdx
0x14000cff2  mov     rcx, [rcx+8]; hKey
0x14000cff6  test    rcx, rcx
0x14000cff9  jz      short loc_14000D077
0x14000cffb  mov     qword ptr [rax-10h], 0
0x14000d003  xor     r9d, r9d; lpReserved
0x14000d006  mov     qword ptr [rax-18h], 0
0x14000d00e  xor     r8d, r8d; lpcchClass
0x14000d011  mov     qword ptr [rax-20h], 0
0x14000d019  xor     edx, edx; lpClass
0x14000d01b  mov     qword ptr [rax-28h], 0
0x14000d023  mov     qword ptr [rax-30h], 0
0x14000d02b  mov     qword ptr [rax-38h], 0
0x14000d033  mov     qword ptr [rax-40h], 0
0x14000d03b  mov     dword ptr [rax+8], 0
0x14000d042  lea     rax, [rax+8]
0x14000d046  mov     qword ptr [rsp+68h+lpcSubKeys], rax; unsigned int
0x14000d04b  call    cs:__imp_RegQueryInfoKeyW
0x14000d051  test    eax, eax
0x14000d053  jz      short loc_14000D070
0x14000d055  mov     rcx, [rsp+68h]; this
0x14000d05a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000d061  mov     r9d, eax; char *
0x14000d064  mov     edx, 137h; void *
0x14000d069  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000d06e  jmp     short loc_14000D079
0x14000d070  mov     eax, [rsp+68h+arg_0]
0x14000d074  mov     [rbx], rax
0x14000d077  xor     eax, eax
0x14000d079  add     rsp, 60h
0x14000d07d  pop     rbx
0x14000d07e  retn
```
