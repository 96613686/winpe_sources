# WsDeleteConnectionEx

- ea: `0x180008a4c`
- end: `0x180008afd`
- name: `WsDeleteConnectionEx`
- size: `177`
- prototype: `__int64 __fastcall(PLUID SourceLuid, HANDLE Handle)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800012a0`
- `0x180001710`
- `0x18002988c`
- `0x1800299a4`
- `0x18002a54c`

## callees

- `0x1800088a0`
- `0x180008a4c`
- `0x18001e420`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180008aa3`
- `ntdll!RtlCopyLuid` at `0x180008aa3`
- `ntdll!NtClose` at `0x180008ae0`
- `ntdll!NtClose` at `0x180008ae0`

## pseudocode

```c
__int64 __fastcall WsDeleteConnectionEx(PLUID SourceLuid, HANDLE Handle, DWORD a3, char a4)
{
  unsigned int v6; // ebx
  struct _LUID DestinationLuid[2]; // [rsp+40h] [rbp-48h] BYREF
  __int128 v9; // [rsp+50h] [rbp-38h]
  int v10; // [rsp+60h] [rbp-28h]

  v10 = 0;
  *(_OWORD *)&DestinationLuid[0].LowPart = 0;
  v9 = 0;
  if ( !a3 || a3 == 2 )
    DestinationLuid[1].LowPart = a3;
  DestinationLuid[0].HighPart = 6;
  RtlCopyLuid((PLUID)&DestinationLuid[1].HighPart, SourceLuid);
  v6 = WsRedirFsControl(Handle, 1311148, DestinationLuid, 36, 0, 0);
  if ( !v6 && a4 )
    NtClose(Handle);
  return v6;
}

```

## disassembly

```asm
0x180008a4c  push    rbx
0x180008a4e  push    rsi
0x180008a4f  push    rdi
0x180008a50  sub     rsp, 70h
0x180008a54  mov     rax, cs:__security_cookie
0x180008a5b  xor     rax, rsp
0x180008a5e  mov     [rsp+88h+var_20], rax
0x180008a63  xor     eax, eax
0x180008a65  xorps   xmm0, xmm0
0x180008a68  mov     [rsp+88h+var_28], eax
0x180008a6c  mov     eax, r8d
0x180008a6f  mov     sil, r9b
0x180008a72  mov     rdi, rdx
0x180008a75  movups  xmmword ptr [rsp+88h+DestinationLuid.LowPart], xmm0
0x180008a7a  movups  [rsp+88h+var_38], xmm0
0x180008a7f  test    r8d, r8d
0x180008a82  jz      short loc_180008A8E
0x180008a84  sub     eax, 1
0x180008a87  jz      short loc_180008A93
0x180008a89  cmp     eax, 1
0x180008a8c  jnz     short loc_180008A93
0x180008a8e  mov     [rsp+88h+DestinationLuid.LowPart+8], r8d
0x180008a93  mov     rdx, rcx; SourceLuid
0x180008a96  mov     [rsp+88h+DestinationLuid.HighPart], 6
0x180008a9e  lea     rcx, [rsp+88h+DestinationLuid.HighPart+8]; DestinationLuid
0x180008aa3  call    cs:__imp_RtlCopyLuid
0x180008aa9  mov     r9d, 24h ; '$'
0x180008aaf  mov     [rsp+88h+var_60], 0
0x180008ab7  lea     r8, [rsp+88h+DestinationLuid]
0x180008abc  mov     [rsp+88h+var_68], 0
0x180008ac5  mov     edx, 1401ACh
0x180008aca  mov     rcx, rdi
0x180008acd  call    WsRedirFsControl
0x180008ad2  mov     ebx, eax
0x180008ad4  test    eax, eax
0x180008ad6  jnz     short loc_180008AE6
0x180008ad8  test    sil, sil
0x180008adb  jz      short loc_180008AE6
0x180008add  mov     rcx, rdi; Handle
0x180008ae0  call    cs:__imp_NtClose
0x180008ae6  mov     eax, ebx
0x180008ae8  mov     rcx, [rsp+88h+var_20]
0x180008aed  xor     rcx, rsp; StackCookie
0x180008af0  call    __security_check_cookie
0x180008af5  add     rsp, 70h
0x180008af9  pop     rdi
0x180008afa  pop     rsi
0x180008afb  pop     rbx
0x180008afc  retn
```
