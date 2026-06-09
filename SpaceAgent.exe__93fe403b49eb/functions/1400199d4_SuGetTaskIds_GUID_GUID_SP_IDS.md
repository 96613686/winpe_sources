# SuGetTaskIds(_GUID *,_GUID *,_SP_IDS * *)

- ea: `0x1400199d4`
- end: `0x140019ad2`
- name: `?SuGetTaskIds@@YAHPEAU_GUID@@0PEAPEAU_SP_IDS@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(struct _GUID *, struct _GUID *, struct _SP_IDS **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140015524`
- `0x1400198c0`

## callees

- `0x1400199d4`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140019a91`
- `KERNEL32!LocalFree` at `0x140019aa1`
- `KERNEL32!LocalFree` at `0x140019a91`
- `KERNEL32!LocalFree` at `0x140019aa1`
- `KERNEL32!SetLastError` at `0x140019a99`
- `KERNEL32!SetLastError` at `0x140019ab3`
- `KERNEL32!SetLastError` at `0x140019a99`
- `KERNEL32!SetLastError` at `0x140019ab3`
- `KERNEL32!GetLastError` at `0x140019a79`
- `KERNEL32!GetLastError` at `0x140019a79`
- `KERNEL32!DeviceIoControl` at `0x140019a6d`
- `KERNEL32!DeviceIoControl` at `0x140019a6d`
- `KERNEL32!LocalAlloc` at `0x140019a2c`
- `KERNEL32!LocalAlloc` at `0x140019a2c`

## pseudocode

```c
__int64 __fastcall SuGetTaskIds(struct _GUID *a1, struct _GUID *a2, struct _SP_IDS **a3)
{
  DWORD nOutBufferSize; // edi
  _DWORD *lpOutBuffer; // rbx
  unsigned int v6; // edi
  DWORD BytesReturned; // [rsp+40h] [rbp-48h] BYREF
  __m256i InBuffer; // [rsp+48h] [rbp-40h] BYREF

  BytesReturned = 0;
  *a3 = 0;
  *(_OWORD *)((char *)InBuffer.m256i_i64 + 4) = 0;
  if ( !a2 )
    a2 = &GUID_NULL;
  nOutBufferSize = 4116;
  *(struct _GUID *)InBuffer.m256i_i8 = *a1;
  *(struct _GUID *)&InBuffer.m256i_u64[2] = *a2;
  while ( 1 )
  {
    lpOutBuffer = LocalAlloc(0, nOutBufferSize);
    if ( !lpOutBuffer )
      break;
    v6 = DeviceIoControl(Spaceport, 0xE70C04u, &InBuffer, 0x20u, lpOutBuffer, nOutBufferSize, &BytesReturned, 0);
    if ( v6 )
    {
      *a3 = (struct _SP_IDS *)lpOutBuffer;
      return v6;
    }
    if ( GetLastError() != 234 )
    {
      LocalFree(lpOutBuffer);
      return v6;
    }
    nOutBufferSize = 16 * *lpOutBuffer + 4;
    LocalFree(lpOutBuffer);
    SetLastError(0);
  }
  SetLastError(0x5AAu);
  return 0;
}

```

## disassembly

```asm
0x1400199d4  push    rbx
0x1400199d6  push    rsi
0x1400199d7  push    rdi
0x1400199d8  sub     rsp, 70h
0x1400199dc  mov     rax, cs:__security_cookie
0x1400199e3  xor     rax, rsp
0x1400199e6  mov     [rsp+88h+var_20], rax
0x1400199eb  xor     eax, eax
0x1400199ed  mov     [rsp+88h+BytesReturned], 0
0x1400199f5  mov     [r8], rax
0x1400199f8  xorps   xmm0, xmm0
0x1400199fb  movups  [rsp+88h+var_3C], xmm0
0x140019a00  test    rdx, rdx
0x140019a03  lea     rax, GUID_NULL
0x140019a0a  movups  xmm0, xmmword ptr [rcx]
0x140019a0d  cmovz   rdx, rax
0x140019a11  mov     rsi, r8
0x140019a14  mov     edi, 1014h
0x140019a19  movdqu  xmmword ptr [rsp+48h], xmm0
0x140019a1f  movups  xmm0, xmmword ptr [rdx]
0x140019a22  movdqu  [rsp+88h+var_3C+0Ch], xmm0
0x140019a28  mov     edx, edi; uBytes
0x140019a2a  xor     ecx, ecx; uFlags
0x140019a2c  call    cs:__imp_LocalAlloc
0x140019a32  mov     rbx, rax
0x140019a35  test    rax, rax
0x140019a38  jz      short loc_140019AAE
0x140019a3a  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x140019a41  lea     rax, [rsp+88h+BytesReturned]
0x140019a46  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x140019a4f  lea     r8, [rsp+88h+InBuffer]; lpInBuffer
0x140019a54  mov     [rsp+88h+lpBytesReturned], rax; lpBytesReturned
0x140019a59  mov     r9d, 20h ; ' '; nInBufferSize
0x140019a5f  mov     [rsp+88h+nOutBufferSize], edi; nOutBufferSize
0x140019a63  mov     edx, 0E70C04h; dwIoControlCode
0x140019a68  mov     [rsp+88h+lpOutBuffer], rbx; lpOutBuffer
0x140019a6d  call    cs:__imp_DeviceIoControl
0x140019a73  mov     edi, eax
0x140019a75  test    eax, eax
0x140019a77  jnz     short loc_140019AA9
0x140019a79  call    cs:__imp_GetLastError
0x140019a7f  mov     rcx, rbx; hMem
0x140019a82  cmp     eax, 0EAh
0x140019a87  jnz     short loc_140019AA1
0x140019a89  mov     edi, [rbx]
0x140019a8b  shl     edi, 4
0x140019a8e  add     edi, 4
0x140019a91  call    cs:__imp_LocalFree
0x140019a97  xor     ecx, ecx; dwErrCode
0x140019a99  call    cs:__imp_SetLastError
0x140019a9f  jmp     short loc_140019A28
0x140019aa1  call    cs:__imp_LocalFree
0x140019aa7  jmp     short loc_140019ABB
0x140019aa9  mov     [rsi], rbx
0x140019aac  jmp     short loc_140019ABB
0x140019aae  mov     ecx, 5AAh; dwErrCode
0x140019ab3  call    cs:__imp_SetLastError
0x140019ab9  xor     edi, edi
0x140019abb  mov     eax, edi
0x140019abd  mov     rcx, [rsp+88h+var_20]
0x140019ac2  xor     rcx, rsp; StackCookie
0x140019ac5  call    __security_check_cookie
0x140019aca  add     rsp, 70h
0x140019ace  pop     rdi
0x140019acf  pop     rsi
0x140019ad0  pop     rbx
0x140019ad1  retn
```
