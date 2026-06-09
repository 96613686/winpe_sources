# BfspCleanupNtldrSettings

- ea: `0x140004e98`
- end: `0x140004f95`
- name: `BfspCleanupNtldrSettings`
- size: `253`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140003d30`

## callees

- `0x140004e98`
- `0x14000619c`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`
- `0x1400140c4`
- `0x140026650`

## string_xrefs

- `0x140004ee7`: `Failed to open a handle to the bootmgr element. Status = [%x]`
- `0x140004f19`: `Failed to open a handle to the ntldr element. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCleanupNtldrSettings(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  HANDLE v7; // rdi
  int Object; // eax
  __int64 v9; // rdx
  HANDLE v11; // [rsp+20h] [rbp-38h] BYREF
  HANDLE Handle; // [rsp+28h] [rbp-30h] BYREF
  __int128 v13; // [rsp+30h] [rbp-28h] BYREF

  v11 = 0;
  Handle = 0;
  v13 = 0;
  v2 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v11);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = BcdOpenObject(a1, &GUID_WINDOWS_LEGACY_NTLDR, &Handle);
    v7 = Handle;
    v3 = v4;
    if ( v4 >= 0 )
    {
      Object = BcdQueryObject((__int64)Handle, v5, v6, (__int64)&v13);
      v3 = Object;
      if ( Object >= 0 )
        v3 = BfspDeleteObjectFromDisplayOrder(v11, v9, &v13);
      else
        BfspLogMessage(4, L"Failed to query the identifier of the ntldr element. Status = [%x]", (unsigned int)Object);
    }
    else
    {
      BfspLogMessage(4, L"Failed to open a handle to the ntldr element. Status = [%x]", (unsigned int)v4);
    }
    if ( v7 )
      BcdCloseObject(v7);
  }
  else
  {
    BfspLogMessage(4, L"Failed to open a handle to the bootmgr element. Status = [%x]", (unsigned int)v2);
  }
  if ( v11 )
    BcdCloseObject(v11);
  return v3;
}

```

## disassembly

```asm
0x140004e98  mov     r11, rsp
0x140004e9b  mov     [r11+10h], rbx
0x140004e9f  push    rdi
0x140004ea0  sub     rsp, 50h
0x140004ea4  mov     rax, cs:__security_cookie
0x140004eab  xor     rax, rsp
0x140004eae  mov     [rsp+58h+var_18], rax
0x140004eb3  xorps   xmm0, xmm0
0x140004eb6  mov     qword ptr [r11-38h], 0
0x140004ebe  lea     r8, [r11-38h]
0x140004ec2  mov     qword ptr [r11-30h], 0
0x140004eca  lea     rdx, GUID_WINDOWS_BOOTMGR
0x140004ed1  mov     rdi, rcx
0x140004ed4  movups  [rsp+58h+var_28], xmm0
0x140004ed9  call    BcdOpenObject
0x140004ede  mov     ebx, eax
0x140004ee0  test    eax, eax
0x140004ee2  jns     short loc_140004EFA
0x140004ee4  mov     r8d, eax
0x140004ee7  lea     rdx, aFailedToOpenAH_0; "Failed to open a handle to the bootmgr "...
0x140004eee  mov     ecx, 4
0x140004ef3  call    BfspLogMessage
0x140004ef8  jmp     short loc_140004F69
0x140004efa  lea     r8, [rsp+58h+Handle]
0x140004eff  mov     rcx, rdi
0x140004f02  lea     rdx, GUID_WINDOWS_LEGACY_NTLDR
0x140004f09  call    BcdOpenObject
0x140004f0e  mov     rdi, [rsp+58h+Handle]
0x140004f13  mov     ebx, eax
0x140004f15  test    eax, eax
0x140004f17  jns     short loc_140004F2F
0x140004f19  lea     rdx, aFailedToOpenAH_4; "Failed to open a handle to the ntldr el"...
0x140004f20  mov     r8d, eax
0x140004f23  mov     ecx, 4
0x140004f28  call    BfspLogMessage
0x140004f2d  jmp     short loc_140004F5C
0x140004f2f  lea     r9, [rsp+58h+var_28]
0x140004f34  mov     rcx, rdi
0x140004f37  call    BcdQueryObject
0x140004f3c  mov     ebx, eax
0x140004f3e  test    eax, eax
0x140004f40  jns     short loc_140004F4B
0x140004f42  lea     rdx, aFailedToQueryT; "Failed to query the identifier of the n"...
0x140004f49  jmp     short loc_140004F20
0x140004f4b  mov     rcx, [rsp+58h+var_38]
0x140004f50  lea     r8, [rsp+58h+var_28]
0x140004f55  call    BfspDeleteObjectFromDisplayOrder
0x140004f5a  mov     ebx, eax
0x140004f5c  test    rdi, rdi
0x140004f5f  jz      short loc_140004F69
0x140004f61  mov     rcx, rdi; Handle
0x140004f64  call    BcdCloseObject
0x140004f69  cmp     [rsp+58h+var_38], 0
0x140004f6f  jz      short loc_140004F7B
0x140004f71  mov     rcx, [rsp+58h+var_38]; Handle
0x140004f76  call    BcdCloseObject
0x140004f7b  mov     eax, ebx
0x140004f7d  mov     rcx, [rsp+58h+var_18]
0x140004f82  xor     rcx, rsp; StackCookie
0x140004f85  call    __security_check_cookie
0x140004f8a  mov     rbx, [rsp+58h+arg_8]
0x140004f8f  add     rsp, 50h
0x140004f93  pop     rdi
0x140004f94  retn
```
