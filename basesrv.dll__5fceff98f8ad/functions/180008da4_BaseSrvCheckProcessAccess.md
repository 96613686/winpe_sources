# BaseSrvCheckProcessAccess

- ea: `0x180008da4`
- end: `0x180008e60`
- name: `BaseSrvCheckProcessAccess`
- size: `188`
- prototype: `__int64 __fastcall(int, int, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009de8`
- `0x18000a090`

## callees

- `0x180008da4`

## import_xrefs

- `ntdll!NtOpenProcess` at `0x180008e2c`
- `ntdll!NtOpenProcess` at `0x180008e2c`
- `CSRSRV!CsrRevertToSelf` at `0x180008e3e`
- `CSRSRV!CsrRevertToSelf` at `0x180008e3e`
- `CSRSRV!CsrImpersonateClient` at `0x180008dd3`
- `CSRSRV!CsrImpersonateClient` at `0x180008dd3`

## pseudocode

```c
__int64 __fastcall BaseSrvCheckProcessAccess(int a1, int a2, void **a3)
{
  void *v3; // rsi
  __int64 result; // rax
  NTSTATUS v7; // edi
  _CLIENT_ID ClientId; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF

  v3 = (void *)a1;
  ClientId = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a2 && !(unsigned __int8)CsrImpersonateClient(0) )
    return 3221225637LL;
  ClientId.UniqueThread = 0;
  ClientId.UniqueProcess = v3;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenProcess(a3, 0x400u, &ObjectAttributes, &ClientId);
  if ( a2 )
    CsrRevertToSelf();
  result = 0;
  if ( v7 < 0 )
    return 3221225485LL;
  return result;
}

```

## disassembly

```asm
0x180008da4  push    rbp
0x180008da6  push    rbx
0x180008da7  push    rsi
0x180008da8  push    rdi
0x180008da9  mov     rbp, rsp
0x180008dac  sub     rsp, 68h
0x180008db0  xorps   xmm0, xmm0
0x180008db3  movsxd  rsi, ecx
0x180008db6  xor     eax, eax
0x180008db8  mov     rdi, r8
0x180008dbb  mov     ebx, edx
0x180008dbd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180008dc1  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180008dc5  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x180008dc9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180008dcd  test    edx, edx
0x180008dcf  jz      short loc_180008DEA
0x180008dd1  xor     ecx, ecx
0x180008dd3  call    cs:__imp_CsrImpersonateClient
0x180008dda  nop     dword ptr [rax+rax+00h]
0x180008ddf  test    al, al
0x180008de1  jnz     short loc_180008DEA
0x180008de3  mov     eax, 0C00000A5h
0x180008de8  jmp     short loc_180008E56
0x180008dea  xorps   xmm0, xmm0
0x180008ded  mov     [rbp+ClientId.UniqueThread], 0
0x180008df5  lea     r9, [rbp+ClientId]; ClientId
0x180008df9  mov     [rbp+ClientId.UniqueProcess], rsi
0x180008dfd  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180008e01  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180008e08  mov     edx, 400h; DesiredAccess
0x180008e0d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180008e15  mov     rcx, rdi; ProcessHandle
0x180008e18  mov     [rbp+ObjectAttributes.Attributes], 0
0x180008e1f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180008e24  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180008e2c  call    cs:__imp_NtOpenProcess
0x180008e33  nop     dword ptr [rax+rax+00h]
0x180008e38  mov     edi, eax
0x180008e3a  test    ebx, ebx
0x180008e3c  jz      short loc_180008E4A
0x180008e3e  call    cs:__imp_CsrRevertToSelf
0x180008e45  nop     dword ptr [rax+rax+00h]
0x180008e4a  xor     eax, eax
0x180008e4c  mov     ecx, 0C000000Dh
0x180008e51  test    edi, edi
0x180008e53  cmovs   eax, ecx
0x180008e56  add     rsp, 68h
0x180008e5a  pop     rdi
0x180008e5b  pop     rsi
0x180008e5c  pop     rbx
0x180008e5d  pop     rbp
0x180008e5e  retn
```
