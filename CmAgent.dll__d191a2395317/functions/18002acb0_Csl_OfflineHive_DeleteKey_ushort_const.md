# Csl::OfflineHive::DeleteKey(ushort const *)

- ea: `0x18002acb0`
- end: `0x18002ad60`
- name: `?DeleteKey@OfflineHive@Csl@@QEAAJPEBG@Z`
- size: `176`
- prototype: `__int64 __fastcall(Csl::OfflineHive *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002ad68`

## callees

- `0x180007b4c`
- `0x18002acb0`
- `0x18002c6e0`
- `0x18002cdc4`
- `0x18002d190`

## string_xrefs

- `0x18002acdd`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18002ad1f`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::DeleteKey(Csl::OfflineHive *this, const unsigned __int16 *a2)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  __int64 v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // edi
  unsigned int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = 0;
  v2 = OROpenKey(*((_QWORD *)this + 1), a2, &v10);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x170,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)v2,
           v8);
    if ( v10 )
      ORCloseKey(v10);
    return v3;
  }
  else
  {
    v5 = v10;
    v6 = ORDeleteKey(v10, 0);
    if ( v6 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x173,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
             (const char *)v6,
             v8);
      if ( v5 )
        ORCloseKey(v5);
      return v7;
    }
    else
    {
      if ( v5 )
        ORCloseKey(v5);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18002acb0  mov     [rsp+arg_8], rbx
0x18002acb5  push    rdi; unsigned int
0x18002acb6  sub     rsp, 20h
0x18002acba  mov     [rsp+28h+arg_0], 0
0x18002acc3  lea     r8, [rsp+28h+arg_0]
0x18002acc8  mov     rcx, [rcx+8]
0x18002accc  call    OROpenKey
0x18002acd1  test    eax, eax
0x18002acd3  jz      short loc_18002AD04
0x18002acd5  mov     rcx, [rsp+28h]; this
0x18002acda  mov     r9d, eax; char *
0x18002acdd  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002ace4  mov     edx, 170h; void *
0x18002ace9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002acee  mov     ebx, eax
0x18002acf0  mov     rcx, [rsp+28h+arg_0]
0x18002acf5  test    rcx, rcx
0x18002acf8  jz      short loc_18002AD00
0x18002acfa  call    ORCloseKey
0x18002acff  nop
0x18002ad00  mov     eax, ebx
0x18002ad02  jmp     short loc_18002AD54
0x18002ad04  xor     edx, edx
0x18002ad06  mov     rbx, [rsp+28h+arg_0]
0x18002ad0b  mov     rcx, rbx
0x18002ad0e  call    ORDeleteKey
0x18002ad13  test    eax, eax
0x18002ad15  jz      short loc_18002AD44
0x18002ad17  mov     rcx, [rsp+28h]; this
0x18002ad1c  mov     r9d, eax; char *
0x18002ad1f  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002ad26  mov     edx, 173h; void *
0x18002ad2b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002ad30  mov     edi, eax
0x18002ad32  test    rbx, rbx
0x18002ad35  jz      short loc_18002AD40
0x18002ad37  mov     rcx, rbx
0x18002ad3a  call    ORCloseKey
0x18002ad3f  nop
0x18002ad40  mov     eax, edi
0x18002ad42  jmp     short loc_18002AD54
0x18002ad44  test    rbx, rbx
0x18002ad47  jz      short loc_18002AD52
0x18002ad49  mov     rcx, rbx
0x18002ad4c  call    ORCloseKey
0x18002ad51  nop
0x18002ad52  xor     eax, eax
0x18002ad54  mov     rbx, [rsp+28h+arg_8]
0x18002ad59  add     rsp, 20h
0x18002ad5d  pop     rdi
0x18002ad5e  retn
```
