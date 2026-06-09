# Csl::OfflineHive::Open(void *,bool)

- ea: `0x18002ba38`
- end: `0x18002baf3`
- name: `?Open@OfflineHive@Csl@@QEAAJPEAX_N@Z`
- size: `187`
- prototype: `__int64 __fastcall(Csl::OfflineHive *this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180028fd8`

## callees

- `0x180007b4c`
- `0x18002ba38`
- `0x18002c068`
- `0x18002c1fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002baab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002baab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bac3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bac3`

## string_xrefs

- `0x18002ba66`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::Open(Csl::OfflineHive *this, void *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  unsigned int *v6; // rdi
  __int64 v7; // rbp
  __int64 v8; // rsi
  DWORD LastError; // ebx
  __int64 v10; // rcx
  unsigned int v11[14]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)v11 = 0;
  v3 = OROpenHiveInternal(a2);
  if ( v3 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x8E,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)v3,
           v11[0]);
    if ( *(_QWORD *)v11 )
      ORCloseHive(*(_QWORD *)v11);
    return v4;
  }
  else
  {
    *(_BYTE *)this = 0;
    v6 = (unsigned int *)((char *)this + 8);
    if ( v6 == v11 )
    {
      v10 = *(_QWORD *)v11;
    }
    else
    {
      v7 = *(_QWORD *)v11;
      v8 = *(_QWORD *)v6;
      if ( *(_QWORD *)v6 )
      {
        LastError = GetLastError();
        ORCloseHive(v8);
        SetLastError(LastError);
      }
      *(_QWORD *)v6 = v7;
      v10 = 0;
    }
    if ( v10 )
      ORCloseHive(v10);
    return 0;
  }
}

```

## disassembly

```asm
0x18002ba38  push    rbx
0x18002ba3a  push    rbp
0x18002ba3b  push    rsi
0x18002ba3c  push    rdi
0x18002ba3d  sub     rsp, 38h
0x18002ba41  mov     rdi, rcx
0x18002ba44  mov     qword ptr [rsp+58h+var_38], 0; unsigned int
0x18002ba4d  lea     r9, [rsp+58h+var_38]
0x18002ba52  mov     rcx, rdx; hFile
0x18002ba55  call    OROpenHiveInternal
0x18002ba5a  test    eax, eax
0x18002ba5c  jz      short loc_18002BA8D
0x18002ba5e  mov     rcx, [rsp+58h]; this
0x18002ba63  mov     r9d, eax; char *
0x18002ba66  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002ba6d  mov     edx, 8Eh; void *
0x18002ba72  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002ba77  mov     ebx, eax
0x18002ba79  mov     rcx, qword ptr [rsp+58h+var_38]
0x18002ba7e  test    rcx, rcx
0x18002ba81  jz      short loc_18002BA89
0x18002ba83  call    ORCloseHive
0x18002ba88  nop
0x18002ba89  mov     eax, ebx
0x18002ba8b  jmp     short loc_18002BAE9
0x18002ba8d  mov     byte ptr [rdi], 0
0x18002ba90  add     rdi, 8
0x18002ba94  lea     rax, [rsp+58h+var_38]
0x18002ba99  cmp     rdi, rax
0x18002ba9c  jz      short loc_18002BAD7
0x18002ba9e  mov     rbp, qword ptr [rsp+58h+var_38]
0x18002baa3  mov     rsi, [rdi]
0x18002baa6  test    rsi, rsi
0x18002baa9  jz      short loc_18002BAD0
0x18002baab  call    cs:__imp_GetLastError
0x18002bab2  nop     dword ptr [rax+rax+00h]
0x18002bab7  mov     ebx, eax
0x18002bab9  mov     rcx, rsi
0x18002babc  call    ORCloseHive
0x18002bac1  mov     ecx, ebx; dwErrCode
0x18002bac3  call    cs:__imp_SetLastError
0x18002baca  nop     dword ptr [rax+rax+00h]
0x18002bacf  nop
0x18002bad0  mov     [rdi], rbp
0x18002bad3  xor     ecx, ecx
0x18002bad5  jmp     short loc_18002BADC
0x18002bad7  mov     rcx, qword ptr [rsp+58h+var_38]
0x18002badc  test    rcx, rcx
0x18002badf  jz      short loc_18002BAE7
0x18002bae1  call    ORCloseHive
0x18002bae6  nop
0x18002bae7  xor     eax, eax
0x18002bae9  add     rsp, 38h
0x18002baed  pop     rdi
0x18002baee  pop     rsi
0x18002baef  pop     rbp
0x18002baf0  pop     rbx
0x18002baf1  retn
```
