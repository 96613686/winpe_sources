# RegHelper::DoesValueExist(WinSATRegistryKeys::Enum,ushort const *,bool &)

- ea: `0x18002d430`
- end: `0x18002d4d5`
- name: `?DoesValueExist@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEA_N@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021898`

## callees

- `0x18000ee1c`
- `0x1800161e0`
- `0x18002d430`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d498`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d498`

## string_xrefs

- `0x18002d484`: `FirstIdleCompletionTimeDate`

## pseudocode

```c
__int64 __fastcall RegHelper::DoesValueExist(DWORD a1, __int64 a2, _BYTE *a3)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  HKEY hKey[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+8h] BYREF

  Type = a1;
  memset(hKey, 0, 24);
  v4 = ATL::CRegKey::Open(
         (ATL::CRegKey *)hKey,
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSATAPI",
         0x20019u);
  if ( !v4 )
  {
    Type = 0;
    v5 = RegQueryValueExW(hKey[0], L"FirstIdleCompletionTimeDate", 0, &Type, 0, 0);
    if ( v5 )
    {
      v4 = 2;
      if ( v5 == 2 )
        *a3 = 0;
      else
        v4 = v5;
    }
    else
    {
      *a3 = 1;
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v4;
}

```

## disassembly

```asm
0x18002d430  mov     rax, rsp
0x18002d433  mov     [rax+10h], rbx
0x18002d437  mov     [rax+8], ecx
0x18002d43a  push    rdi
0x18002d43b  sub     rsp, 50h
0x18002d43f  and     qword ptr [rax-28h], 0
0x18002d444  lea     rcx, [rax-28h]; this
0x18002d448  and     qword ptr [rax-20h], 0
0x18002d44d  mov     rdi, r8
0x18002d450  and     qword ptr [rax-18h], 0
0x18002d455  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002d45c  mov     r9d, 20019h; unsigned int
0x18002d462  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002d469  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002d46e  mov     ebx, eax
0x18002d470  test    eax, eax
0x18002d472  jnz     short loc_18002D4BD
0x18002d474  and     [rsp+58h+var_30], 0
0x18002d47a  lea     r9, [rsp+58h+Type]; lpType
0x18002d47f  mov     rcx, [rsp+58h+hKey]; hKey
0x18002d484  lea     rdx, ValueName; "FirstIdleCompletionTimeDate"
0x18002d48b  and     [rsp+58h+var_38], 0
0x18002d491  xor     r8d, r8d; lpReserved
0x18002d494  and     [rsp+58h+Type], eax
0x18002d498  call    cs:__imp_RegQueryValueExW
0x18002d49f  nop     dword ptr [rax+rax+00h]
0x18002d4a4  test    eax, eax
0x18002d4a6  jnz     short loc_18002D4AD
0x18002d4a8  mov     byte ptr [rdi], 1
0x18002d4ab  jmp     short loc_18002D4BD
0x18002d4ad  mov     ebx, 2
0x18002d4b2  cmp     eax, ebx
0x18002d4b4  jnz     short loc_18002D4BB
0x18002d4b6  mov     byte ptr [rdi], 0
0x18002d4b9  jmp     short loc_18002D4BD
0x18002d4bb  mov     ebx, eax
0x18002d4bd  lea     rcx, [rsp+58h+hKey]; this
0x18002d4c2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002d4c7  mov     eax, ebx
0x18002d4c9  mov     rbx, [rsp+58h+arg_8]
0x18002d4ce  add     rsp, 50h
0x18002d4d2  pop     rdi
0x18002d4d3  retn
```
