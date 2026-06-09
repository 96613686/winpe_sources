# AiOpenTokenByProcessId

- ea: `0x140035c50`
- end: `0x140035cf2`
- name: `AiOpenTokenByProcessId`
- size: `162`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140001bbc`
- `0x140024280`
- `0x14002b5e0`
- `0x14002f560`

## callees

- `0x140035c50`

## import_xrefs

- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140035cc0`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140035cc0`
- `ntoskrnl!ZwOpenProcess` at `0x140035c9e`
- `ntoskrnl!ZwOpenProcess` at `0x140035c9e`
- `ntoskrnl!ZwClose` at `0x140035cd8`
- `ntoskrnl!ZwClose` at `0x140035cd8`

## pseudocode

```c
__int64 __fastcall AiOpenTokenByProcessId(void *a1, void **a2)
{
  NTSTATUS v3; // ebx
  struct _CLIENT_ID v5; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES v6; // [rsp+30h] [rbp-38h] BYREF
  HANDLE ProcessHandle; // [rsp+70h] [rbp+8h] BYREF

  v5.UniqueProcess = a1;
  *(_QWORD *)&v6.Length = 48;
  ProcessHandle = 0;
  v6.RootDirectory = 0;
  v6.ObjectName = 0;
  v5.UniqueThread = 0;
  *(_QWORD *)&v6.Attributes = 512;
  *(_OWORD *)&v6.SecurityDescriptor = 0;
  v3 = ZwOpenProcess(&ProcessHandle, 0x400u, &v6, &v5);
  if ( v3 >= 0 )
    v3 = ZwOpenProcessTokenEx(ProcessHandle, 0, 0x200u, a2);
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140035c50  mov     rax, rsp
0x140035c53  mov     [rax+10h], rbx
0x140035c57  push    rdi
0x140035c58  sub     rsp, 60h
0x140035c5c  mov     rdi, rdx
0x140035c5f  mov     [rax-48h], rcx
0x140035c63  xor     edx, edx
0x140035c65  mov     qword ptr [rax-38h], 30h ; '0'
0x140035c6d  mov     [rax+8], rdx
0x140035c71  lea     r9, [rax-48h]; ClientId
0x140035c75  mov     [rax-30h], rdx
0x140035c79  lea     r8, [rax-38h]; ObjectAttributes
0x140035c7d  mov     [rax-28h], rdx
0x140035c81  lea     rcx, [rax+8]; ProcessHandle
0x140035c85  mov     [rax-40h], rdx
0x140035c89  xorps   xmm0, xmm0
0x140035c8c  mov     edx, 400h; DesiredAccess
0x140035c91  mov     qword ptr [rax-20h], 200h
0x140035c99  movdqu  xmmword ptr [rax-18h], xmm0
0x140035c9e  call    cs:__imp_ZwOpenProcess
0x140035ca5  nop     dword ptr [rax+rax+00h]
0x140035caa  mov     ebx, eax
0x140035cac  test    eax, eax
0x140035cae  js      short loc_140035CCE
0x140035cb0  mov     rcx, [rsp+68h+ProcessHandle]; ProcessHandle
0x140035cb5  mov     r9, rdi; TokenHandle
0x140035cb8  xor     edx, edx; DesiredAccess
0x140035cba  mov     r8d, 200h; HandleAttributes
0x140035cc0  call    cs:__imp_ZwOpenProcessTokenEx
0x140035cc7  nop     dword ptr [rax+rax+00h]
0x140035ccc  mov     ebx, eax
0x140035cce  mov     rcx, [rsp+68h+ProcessHandle]; Handle
0x140035cd3  test    rcx, rcx
0x140035cd6  jz      short loc_140035CE4
0x140035cd8  call    cs:__imp_ZwClose
0x140035cdf  nop     dword ptr [rax+rax+00h]
0x140035ce4  mov     eax, ebx
0x140035ce6  mov     rbx, [rsp+68h+arg_8]
0x140035ceb  add     rsp, 60h
0x140035cef  pop     rdi
0x140035cf0  retn
```
