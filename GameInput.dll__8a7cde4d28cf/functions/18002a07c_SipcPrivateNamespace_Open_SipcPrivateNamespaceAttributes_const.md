# SipcPrivateNamespace::Open(SipcPrivateNamespaceAttributes const &)

- ea: `0x18002a07c`
- end: `0x18002a1df`
- name: `?Open@SipcPrivateNamespace@@QEAAJAEBUSipcPrivateNamespaceAttributes@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(SipcPrivateNamespace *__hidden this, const struct SipcPrivateNamespaceAttributes *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025520`

## callees

- `0x180028cec`
- `0x18002a07c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a17c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002a090`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002a0a8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002a090`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002a0a8`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x18002a168`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x18002a168`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18002a14c`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18002a1a6`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18002a1be`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18002a14c`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18002a1a6`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x18002a1be`

## pseudocode

```c
__int64 __fastcall SipcPrivateNamespace::Open(
        SipcPrivateNamespace *this,
        const struct SipcPrivateNamespaceAttributes *a2)
{
  __int128 v4; // xmm0
  int BoundaryDescriptorAndInitializeName; // ebx
  HANDLE v7; // rbx
  HANDLE v8; // rax
  signed int LastError; // eax
  unsigned int v10; // edi
  HANDLE BoundaryDescriptor; // [rsp+38h] [rbp+10h] BYREF

  if ( !IsValidSid((char *)a2 + 16) || !IsValidSid((char *)a2 + 84) )
    return 2147942487LL;
  v4 = *(_OWORD *)a2;
  BoundaryDescriptor = 0;
  *(_OWORD *)((char *)this + 84) = v4;
  *(_OWORD *)((char *)this + 100) = *((_OWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 116) = *((_OWORD *)a2 + 2);
  *(_OWORD *)((char *)this + 132) = *((_OWORD *)a2 + 3);
  *(_OWORD *)((char *)this + 148) = *((_OWORD *)a2 + 4);
  *(_OWORD *)((char *)this + 164) = *((_OWORD *)a2 + 5);
  *(_OWORD *)((char *)this + 180) = *((_OWORD *)a2 + 6);
  *(_OWORD *)((char *)this + 196) = *((_OWORD *)a2 + 7);
  *(_OWORD *)((char *)this + 212) = *((_OWORD *)a2 + 8);
  *(_QWORD *)((char *)this + 228) = *((_QWORD *)a2 + 18);
  BoundaryDescriptorAndInitializeName = SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(
                                          this,
                                          &BoundaryDescriptor);
  if ( BoundaryDescriptorAndInitializeName >= 0 )
  {
    v7 = BoundaryDescriptor;
    v8 = OpenPrivateNamespaceW(BoundaryDescriptor, (LPCWSTR)this + 4);
    *(_QWORD *)this = v8;
    if ( v8 )
    {
      if ( v7 )
        DeleteBoundaryDescriptor(v7);
      return 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v10 = -2147418113;
      if ( LastError < 0 )
        v10 = LastError;
      if ( v7 )
        DeleteBoundaryDescriptor(v7);
      return v10;
    }
  }
  else
  {
    if ( BoundaryDescriptor )
      DeleteBoundaryDescriptor(BoundaryDescriptor);
    return (unsigned int)BoundaryDescriptorAndInitializeName;
  }
}

```

## disassembly

```asm
0x18002a07c  mov     [rsp+arg_0], rbx
0x18002a081  push    rdi
0x18002a082  sub     rsp, 20h
0x18002a086  mov     rdi, rcx
0x18002a089  mov     rbx, rdx
0x18002a08c  lea     rcx, [rdx+10h]; pSid
0x18002a090  call    cs:__imp_IsValidSid
0x18002a097  nop     dword ptr [rax+rax+00h]
0x18002a09c  test    eax, eax
0x18002a09e  jz      loc_18002A1CE
0x18002a0a4  lea     rcx, [rbx+54h]; pSid
0x18002a0a8  call    cs:__imp_IsValidSid
0x18002a0af  nop     dword ptr [rax+rax+00h]
0x18002a0b4  test    eax, eax
0x18002a0b6  jz      loc_18002A1CE
0x18002a0bc  movups  xmm0, xmmword ptr [rbx]
0x18002a0bf  lea     rdx, [rsp+28h+BoundaryDescriptor]; void **
0x18002a0c4  mov     [rsp+28h+BoundaryDescriptor], 0
0x18002a0cd  mov     rcx, rdi; this
0x18002a0d0  movups  xmmword ptr [rdi+54h], xmm0
0x18002a0d4  movups  xmm1, xmmword ptr [rbx+10h]
0x18002a0d8  movups  xmmword ptr [rdi+64h], xmm1
0x18002a0dc  movups  xmm0, xmmword ptr [rbx+20h]
0x18002a0e0  movups  xmmword ptr [rdi+74h], xmm0
0x18002a0e4  movups  xmm1, xmmword ptr [rbx+30h]
0x18002a0e8  movups  xmmword ptr [rdi+84h], xmm1
0x18002a0ef  movups  xmm0, xmmword ptr [rbx+40h]
0x18002a0f3  movups  xmmword ptr [rdi+94h], xmm0
0x18002a0fa  movups  xmm1, xmmword ptr [rbx+50h]
0x18002a0fe  movups  xmmword ptr [rdi+0A4h], xmm1
0x18002a105  movups  xmm0, xmmword ptr [rbx+60h]
0x18002a109  movups  xmmword ptr [rdi+0B4h], xmm0
0x18002a110  movups  xmm1, xmmword ptr [rbx+70h]
0x18002a114  movups  xmmword ptr [rdi+0C4h], xmm1
0x18002a11b  movups  xmm0, xmmword ptr [rbx+80h]
0x18002a122  movups  xmmword ptr [rdi+0D4h], xmm0
0x18002a129  mov     rax, [rbx+90h]
0x18002a130  mov     [rdi+0E4h], rax
0x18002a137  call    ?GetBoundaryDescriptorAndInitializeName@SipcPrivateNamespace@@AEAAJPEAPEAX@Z; SipcPrivateNamespace::GetBoundaryDescriptorAndInitializeName(void * *)
0x18002a13c  mov     ebx, eax
0x18002a13e  test    eax, eax
0x18002a140  jns     short loc_18002A15C
0x18002a142  mov     rcx, [rsp+28h+BoundaryDescriptor]; BoundaryDescriptor
0x18002a147  test    rcx, rcx
0x18002a14a  jz      short loc_18002A158
0x18002a14c  call    cs:__imp_DeleteBoundaryDescriptor
0x18002a153  nop     dword ptr [rax+rax+00h]
0x18002a158  mov     eax, ebx
0x18002a15a  jmp     short loc_18002A1D3
0x18002a15c  mov     rbx, [rsp+28h+BoundaryDescriptor]
0x18002a161  lea     rdx, [rdi+8]; lpAliasPrefix
0x18002a165  mov     rcx, rbx; lpBoundaryDescriptor
0x18002a168  call    cs:__imp_OpenPrivateNamespaceW
0x18002a16f  nop     dword ptr [rax+rax+00h]
0x18002a174  mov     [rdi], rax
0x18002a177  test    rax, rax
0x18002a17a  jnz     short loc_18002A1B6
0x18002a17c  call    cs:__imp_GetLastError
0x18002a183  nop     dword ptr [rax+rax+00h]
0x18002a188  test    eax, eax
0x18002a18a  jle     short loc_18002A194
0x18002a18c  movzx   eax, ax
0x18002a18f  or      eax, 80070000h
0x18002a194  test    eax, eax
0x18002a196  mov     edi, 8000FFFFh
0x18002a19b  cmovs   edi, eax
0x18002a19e  test    rbx, rbx
0x18002a1a1  jz      short loc_18002A1B2
0x18002a1a3  mov     rcx, rbx; BoundaryDescriptor
0x18002a1a6  call    cs:__imp_DeleteBoundaryDescriptor
0x18002a1ad  nop     dword ptr [rax+rax+00h]
0x18002a1b2  mov     eax, edi
0x18002a1b4  jmp     short loc_18002A1D3
0x18002a1b6  test    rbx, rbx
0x18002a1b9  jz      short loc_18002A1CA
0x18002a1bb  mov     rcx, rbx; BoundaryDescriptor
0x18002a1be  call    cs:__imp_DeleteBoundaryDescriptor
0x18002a1c5  nop     dword ptr [rax+rax+00h]
0x18002a1ca  xor     eax, eax
0x18002a1cc  jmp     short loc_18002A1D3
0x18002a1ce  mov     eax, 80070057h
0x18002a1d3  mov     rbx, [rsp+28h+arg_0]
0x18002a1d8  add     rsp, 20h
0x18002a1dc  pop     rdi
0x18002a1dd  retn
```
