# AhcVerifyAdminContext

- ea: `0x140045d6c`
- end: `0x140045df1`
- name: `AhcVerifyAdminContext`
- size: `133`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002b128`
- `0x14002b950`
- `0x14002baa8`
- `0x140045a00`

## callees

- `0x140045d6c`

## import_xrefs

- `ntoskrnl!RtlCheckTokenMembership` at `0x140045d8d`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140045dc9`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140045d8d`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140045dc9`
- `ntoskrnl!SeExports` at `0x140045d70`
- `ntoskrnl!SeExports` at `0x140045dac`

## pseudocode

```c
__int64 AhcVerifyAdminContext()
{
  char v1; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  if ( (int)RtlCheckTokenMembership(0, SeExports->SeAliasAdminsSid, &v1) >= 0 && v1 )
    return 0;
  v1 = 0;
  if ( (int)RtlCheckTokenMembership(0, SeExports->SeLocalSystemSid, &v1) >= 0 )
    return v1 == 0 ? 0xC0000022 : 0;
  else
    return 3221225506LL;
}

```

## disassembly

```asm
0x140045d6c  sub     rsp, 28h
0x140045d70  mov     rax, cs:__imp_SeExports
0x140045d77  lea     r8, [rsp+28h+arg_0]
0x140045d7c  mov     [rsp+28h+arg_0], 0
0x140045d81  xor     ecx, ecx
0x140045d83  mov     rdx, [rax]
0x140045d86  mov     rdx, [rdx+110h]
0x140045d8d  call    cs:__imp_RtlCheckTokenMembership
0x140045d94  nop     dword ptr [rax+rax+00h]
0x140045d99  test    eax, eax
0x140045d9b  js      short loc_140045DAC
0x140045d9d  cmp     [rsp+28h+arg_0], 0
0x140045da2  jz      short loc_140045DAC
0x140045da4  xor     eax, eax
0x140045da6  add     rsp, 28h
0x140045daa  retn
0x140045dac  mov     rax, cs:__imp_SeExports
0x140045db3  lea     r8, [rsp+28h+arg_0]
0x140045db8  mov     [rsp+28h+arg_0], 0
0x140045dbd  xor     ecx, ecx
0x140045dbf  mov     rdx, [rax]
0x140045dc2  mov     rdx, [rdx+108h]
0x140045dc9  call    cs:__imp_RtlCheckTokenMembership
0x140045dd0  nop     dword ptr [rax+rax+00h]
0x140045dd5  test    eax, eax
0x140045dd7  jns     short loc_140045DE0
0x140045dd9  mov     eax, 0C0000022h
0x140045dde  jmp     short loc_140045DA6
0x140045de0  mov     al, [rsp+28h+arg_0]
0x140045de4  neg     al
0x140045de6  sbb     eax, eax
0x140045de8  not     eax
0x140045dea  and     eax, 0C0000022h
0x140045def  jmp     short loc_140045DA6
```
