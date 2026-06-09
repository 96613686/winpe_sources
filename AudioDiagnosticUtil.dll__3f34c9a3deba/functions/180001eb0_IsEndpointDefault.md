# IsEndpointDefault

- ea: `0x180001eb0`
- end: `0x180001f0c`
- name: `IsEndpointDefault`
- size: `92`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001b70`
- `0x180001eb0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001eeb`
- `msvcrt!_wcsicmp` at `0x180001eeb`

## pseudocode

```c
__int64 __fastcall IsEndpointDefault(wchar_t *String2, const wchar_t *a2, BOOL *a3)
{
  BOOL v5; // ebx
  int DefaultEndpointID; // edi
  wchar_t *String1; // [rsp+60h] [rbp+18h] BYREF

  String1 = 0;
  v5 = 1;
  DefaultEndpointID = GetDefaultEndpointID(a2, &String1);
  if ( DefaultEndpointID >= 0 )
    v5 = _wcsicmp(String1, String2) == 0;
  *a3 = v5;
  return (unsigned int)DefaultEndpointID;
}

```

## disassembly

```asm
0x180001eb0  push    rbx
0x180001eb2  push    rbp
0x180001eb3  push    rsi
0x180001eb4  push    rdi
0x180001eb5  sub     rsp, 28h
0x180001eb9  mov     rax, rdx
0x180001ebc  mov     [rsp+48h+String1], 0
0x180001ec5  mov     rbp, rcx
0x180001ec8  lea     rdx, [rsp+48h+String1]
0x180001ecd  mov     rcx, rax
0x180001ed0  mov     rsi, r8
0x180001ed3  mov     ebx, 1
0x180001ed8  call    GetDefaultEndpointID
0x180001edd  mov     edi, eax
0x180001edf  test    eax, eax
0x180001ee1  js      short loc_180001EFE
0x180001ee3  mov     rcx, [rsp+48h+String1]; String1
0x180001ee8  mov     rdx, rbp; String2
0x180001eeb  call    cs:__imp__wcsicmp
0x180001ef2  nop     dword ptr [rax+rax+00h]
0x180001ef7  xor     ebx, ebx
0x180001ef9  test    eax, eax
0x180001efb  setz    bl
0x180001efe  mov     [rsi], ebx
0x180001f00  mov     eax, edi
0x180001f02  add     rsp, 28h
0x180001f06  pop     rdi
0x180001f07  pop     rsi
0x180001f08  pop     rbp
0x180001f09  pop     rbx
0x180001f0a  retn
```
