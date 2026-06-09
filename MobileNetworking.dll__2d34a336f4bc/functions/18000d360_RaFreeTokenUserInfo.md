# RaFreeTokenUserInfo

- ea: `0x18000d360`
- end: `0x18000d3c5`
- name: `RaFreeTokenUserInfo`
- size: `101`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cfe0`

## callees

- `0x180004b80`
- `0x18000d360`
- `0x18000d860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d387`

## string_xrefs

- `0x18000d370`: `RaFreeTokenUserInfo`

## pseudocode

```c
__int64 __fastcall RaFreeTokenUserInfo(void *a1)
{
  DWORD LastError; // ebx
  __int64 v2; // r8
  LPVOID v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  LastError = 0;
  if ( !(unsigned int)FreeMemory(&v4, (int)"RaFreeTokenUserInfo", 211) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v2, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000d360  mov     [rsp+arg_0], rcx
0x18000d365  push    rbx
0x18000d366  sub     rsp, 20h
0x18000d36a  mov     r8d, 0D3h
0x18000d370  lea     rdx, aRafreetokenuse_0; "RaFreeTokenUserInfo"
0x18000d377  lea     rcx, [rsp+28h+arg_0]
0x18000d37c  xor     ebx, ebx
0x18000d37e  call    FreeMemory
0x18000d383  test    eax, eax
0x18000d385  jnz     short loc_18000D3BD
0x18000d387  call    cs:__imp_GetLastError
0x18000d38d  mov     ebx, eax
0x18000d38f  test    eax, eax
0x18000d391  jz      short loc_18000D3BD
0x18000d393  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d39a  lea     rax, WPP_GLOBAL_Control
0x18000d3a1  cmp     rcx, rax
0x18000d3a4  jz      short loc_18000D3BD
0x18000d3a6  test    byte ptr [rcx+1Ch], 4
0x18000d3aa  jz      short loc_18000D3BD
0x18000d3ac  mov     rcx, [rcx+10h]
0x18000d3b0  mov     edx, 1Bh
0x18000d3b5  mov     r9d, ebx
0x18000d3b8  call    WPP_SF_D
0x18000d3bd  mov     eax, ebx
0x18000d3bf  add     rsp, 20h
0x18000d3c3  pop     rbx
0x18000d3c4  retn
```
