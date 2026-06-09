# OpenMatchingDeviceCallback

- ea: `0x14001f9c0`
- end: `0x14001fa91`
- name: `OpenMatchingDeviceCallback`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001f9c0`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fa2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001fa2f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001fa52`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001fa52`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001f9f3`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x14001f9f3`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x14001fa25`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x14001fa25`

## string_xrefs

- `0x14001fa3e`: `Failed to open device '%ws'. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall OpenMatchingDeviceCallback(__int64 a1, __int64 a2)
{
  __int64 ThreadLogToken; // rax
  __int64 v5; // rcx
  __int64 v6; // rbp
  DWORD v7; // ebx
  DWORD LastError; // [rsp+28h] [rbp-60h]
  __int128 v10; // [rsp+30h] [rbp-58h] BYREF
  __int128 v11; // [rsp+40h] [rbp-48h]
  __int128 v12; // [rsp+50h] [rbp-38h]

  v10 = 0;
  v11 = 0;
  v12 = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  v5 = *(_QWORD *)(a2 + 8);
  v6 = ThreadLogToken;
  if ( (unsigned __int64)(v5 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    return 87;
  }
  else
  {
    LODWORD(v10) = 48;
    if ( (unsigned int)DevObjOpenDeviceInfo(v5, a1, 0, 0, &v10) )
    {
      v7 = 0;
      if ( DWORD1(v11) != *(_DWORD *)a2 )
        *(_DWORD *)(a2 + 16) = 1;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      DevRtlWriteTextLog(v6, 1, 1, "Failed to open device '%ws'. Error = 0x%08X", a1, LastError);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14001f9c0  mov     [rsp+arg_10], rbx
0x14001f9c5  push    rbp
0x14001f9c6  push    rsi
0x14001f9c7  push    rdi
0x14001f9c8  sub     rsp, 70h
0x14001f9cc  mov     rax, cs:__security_cookie
0x14001f9d3  xor     rax, rsp
0x14001f9d6  mov     [rsp+88h+var_28], rax
0x14001f9db  xorps   xmm0, xmm0
0x14001f9de  mov     rdi, rdx
0x14001f9e1  movups  [rsp+88h+var_58], xmm0
0x14001f9e6  mov     rsi, rcx
0x14001f9e9  movups  [rsp+88h+var_48], xmm0
0x14001f9ee  movups  [rsp+88h+var_38], xmm0
0x14001f9f3  call    cs:__imp_DevRtlGetThreadLogToken
0x14001f9f9  mov     rcx, [rdi+8]
0x14001f9fd  mov     rbp, rax
0x14001fa00  lea     rdx, [rcx-1]
0x14001fa04  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14001fa08  ja      short loc_14001FA6D
0x14001fa0a  lea     rax, [rsp+88h+var_58]
0x14001fa0f  mov     dword ptr [rsp+88h+var_58], 30h ; '0'
0x14001fa17  xor     r9d, r9d
0x14001fa1a  mov     [rsp+88h+var_68], rax
0x14001fa1f  xor     r8d, r8d
0x14001fa22  mov     rdx, rsi
0x14001fa25  call    cs:__imp_DevObjOpenDeviceInfo
0x14001fa2b  test    eax, eax
0x14001fa2d  jnz     short loc_14001FA5A
0x14001fa2f  call    cs:__imp_GetLastError
0x14001fa35  mov     edx, 1
0x14001fa3a  mov     [rsp+88h+var_60], eax
0x14001fa3e  lea     r9, aFailedToOpenDe; "Failed to open device '%ws'. Error = 0x"...
0x14001fa45  mov     [rsp+88h+var_68], rsi
0x14001fa4a  mov     r8d, edx
0x14001fa4d  mov     rcx, rbp
0x14001fa50  mov     ebx, eax
0x14001fa52  call    cs:__imp_DevRtlWriteTextLog
0x14001fa58  jmp     short loc_14001FA72
0x14001fa5a  mov     eax, [rdi]
0x14001fa5c  xor     ebx, ebx
0x14001fa5e  cmp     dword ptr [rsp+88h+var_48+4], eax
0x14001fa62  jz      short loc_14001FA72
0x14001fa64  mov     dword ptr [rdi+10h], 1
0x14001fa6b  jmp     short loc_14001FA72
0x14001fa6d  mov     ebx, 57h ; 'W'
0x14001fa72  mov     eax, ebx
0x14001fa74  mov     rcx, [rsp+88h+var_28]
0x14001fa79  xor     rcx, rsp; StackCookie
0x14001fa7c  call    __security_check_cookie
0x14001fa81  mov     rbx, [rsp+88h+arg_10]
0x14001fa89  add     rsp, 70h
0x14001fa8d  pop     rdi
0x14001fa8e  pop     rsi
0x14001fa8f  pop     rbp
0x14001fa90  retn
```
