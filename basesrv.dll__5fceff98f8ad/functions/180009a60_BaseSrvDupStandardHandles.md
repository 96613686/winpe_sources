# BaseSrvDupStandardHandles

- ea: `0x180009a60`
- end: `0x180009c92`
- name: `BaseSrvDupStandardHandles`
- size: `562`
- prototype: `__int64 __fastcall(HANDLE SourceProcessHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008938`
- `0x18000c434`

## callees

- `0x180009a60`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x180009b09`
- `ntdll!NtDuplicateObject` at `0x180009b4d`
- `ntdll!NtDuplicateObject` at `0x180009b89`
- `ntdll!NtDuplicateObject` at `0x180009be3`
- `ntdll!NtDuplicateObject` at `0x180009c1c`
- `ntdll!NtDuplicateObject` at `0x180009c4e`
- `ntdll!NtDuplicateObject` at `0x180009b09`
- `ntdll!NtDuplicateObject` at `0x180009b4d`
- `ntdll!NtDuplicateObject` at `0x180009b89`
- `ntdll!NtDuplicateObject` at `0x180009be3`
- `ntdll!NtDuplicateObject` at `0x180009c1c`
- `ntdll!NtDuplicateObject` at `0x180009c4e`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvDupStandardHandles(HANDLE SourceProcessHandle, __int64 a2)
{
  __int64 v2; // rdi
  NTSTATUS result; // eax
  HANDLE *v5; // r14
  void *v6; // rbx
  HANDLE *v7; // rsi
  void *v8; // r13
  void **v9; // r15
  void *v10; // r12
  HANDLE v11; // rax
  NTSTATUS v12; // r12d
  HANDLE v13; // rdx
  NTSTATUS v14; // r15d
  HANDLE v15; // [rsp+88h] [rbp+10h]
  void *v16; // [rsp+90h] [rbp+18h]

  v2 = *(_QWORD *)(a2 + 32);
  if ( *(_BYTE *)(v2 + 249) )
    return 0;
  v5 = (HANDLE *)(v2 + 16);
  v6 = *(void **)(v2 + 16);
  if ( (unsigned __int64)v6 + 6 <= 5 )
    return -1073741816;
  v7 = (HANDLE *)(v2 + 24);
  v8 = *(void **)(v2 + 24);
  if ( (unsigned __int64)v8 + 6 <= 5 )
    return -1073741816;
  v9 = (void **)(v2 + 32);
  if ( (unsigned __int64)(*(_QWORD *)(v2 + 32) + 6LL) <= 5 )
    return -1073741816;
  v10 = *(void **)(*((_QWORD *)NtCurrentTeb()->CsrClientThread + 7) + 80LL);
  v16 = v10;
  if ( !v6 || (result = NtDuplicateObject(v10, v6, SourceProcessHandle, (PHANDLE)(v2 + 16), 0, 2u, 2u), result >= 0) )
  {
    v11 = 0;
    if ( *v7 )
    {
      v15 = *v7;
      v12 = NtDuplicateObject(v10, *v7, SourceProcessHandle, (PHANDLE)(v2 + 24), 0, 2u, 2u);
      if ( v12 < 0 )
      {
        if ( v6 )
        {
          NtDuplicateObject(SourceProcessHandle, *v5, 0, 0, 0, 0, 1u);
          *v5 = v6;
        }
        return v12;
      }
      v11 = v15;
      v10 = v16;
    }
    v13 = *v9;
    if ( *v9 )
    {
      if ( v13 == v11 )
      {
        *v9 = *v7;
      }
      else
      {
        v14 = NtDuplicateObject(v10, v13, SourceProcessHandle, (PHANDLE)(v2 + 32), 0, 2u, 2u);
        if ( v14 < 0 )
        {
          if ( v6 )
          {
            NtDuplicateObject(SourceProcessHandle, *v5, 0, 0, 0, 0, 1u);
            *v5 = v6;
          }
          if ( v8 )
          {
            NtDuplicateObject(SourceProcessHandle, *v7, 0, 0, 0, 0, 1u);
            *v7 = v8;
          }
          return v14;
        }
      }
    }
    *(_BYTE *)(v2 + 249) = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009a60  mov     [rsp+arg_0], rbx
0x180009a65  push    rbp
0x180009a66  push    rsi
0x180009a67  push    rdi
0x180009a68  push    r12
0x180009a6a  push    r13
0x180009a6c  push    r14
0x180009a6e  push    r15
0x180009a70  sub     rsp, 40h
0x180009a74  mov     rdi, [rdx+20h]
0x180009a78  mov     rbp, rcx
0x180009a7b  cmp     byte ptr [rdi+0F9h], 0
0x180009a82  jz      short loc_180009A8B
0x180009a84  xor     eax, eax
0x180009a86  jmp     loc_180009C79
0x180009a8b  lea     r14, [rdi+10h]
0x180009a8f  mov     rbx, [r14]
0x180009a92  lea     rax, [rbx+6]
0x180009a96  cmp     rax, 5
0x180009a9a  jbe     loc_180009C74
0x180009aa0  lea     rsi, [rdi+18h]
0x180009aa4  mov     r13, [rsi]
0x180009aa7  lea     rax, [r13+6]
0x180009aab  cmp     rax, 5
0x180009aaf  jbe     loc_180009C74
0x180009ab5  lea     r15, [rdi+20h]
0x180009ab9  mov     rax, [r15]
0x180009abc  add     rax, 6
0x180009ac0  cmp     rax, 5
0x180009ac4  jbe     loc_180009C74
0x180009aca  mov     rax, gs:70h
0x180009ad3  mov     rcx, [rax+38h]
0x180009ad7  mov     r12, [rcx+50h]
0x180009adb  mov     ecx, 2
0x180009ae0  mov     [rsp+78h+arg_10], r12
0x180009ae8  test    rbx, rbx
0x180009aeb  jz      short loc_180009B22
0x180009aed  mov     [rsp+78h+Options], ecx; Options
0x180009af1  mov     r9, r14; TargetHandle
0x180009af4  mov     [rsp+78h+HandleAttributes], ecx; HandleAttributes
0x180009af8  mov     r8, rbp; TargetProcessHandle
0x180009afb  mov     rcx, r12; SourceProcessHandle
0x180009afe  mov     [rsp+78h+DesiredAccess], 0; DesiredAccess
0x180009b06  mov     rdx, rbx; SourceHandle
0x180009b09  call    cs:__imp_NtDuplicateObject
0x180009b10  nop     dword ptr [rax+rax+00h]
0x180009b15  test    eax, eax
0x180009b17  js      loc_180009C79
0x180009b1d  mov     ecx, 2
0x180009b22  mov     rdx, [rsi]; SourceHandle
0x180009b25  xor     eax, eax
0x180009b27  test    rdx, rdx
0x180009b2a  jz      loc_180009BB0
0x180009b30  mov     [rsp+78h+Options], ecx; Options
0x180009b34  mov     r9, rsi; TargetHandle
0x180009b37  mov     [rsp+78h+HandleAttributes], ecx; HandleAttributes
0x180009b3b  mov     r8, rbp; TargetProcessHandle
0x180009b3e  mov     rcx, r12; SourceProcessHandle
0x180009b41  mov     [rsp+78h+arg_8], rdx
0x180009b49  mov     [rsp+78h+DesiredAccess], eax; DesiredAccess
0x180009b4d  call    cs:__imp_NtDuplicateObject
0x180009b54  nop     dword ptr [rax+rax+00h]
0x180009b59  mov     r12d, eax
0x180009b5c  test    eax, eax
0x180009b5e  jns     short loc_180009BA0
0x180009b60  test    rbx, rbx
0x180009b63  jz      short loc_180009B98
0x180009b65  mov     rdx, [r14]; SourceHandle
0x180009b68  xor     r9d, r9d; TargetHandle
0x180009b6b  mov     [rsp+78h+Options], 1; Options
0x180009b73  xor     r8d, r8d; TargetProcessHandle
0x180009b76  mov     [rsp+78h+HandleAttributes], 0; HandleAttributes
0x180009b7e  mov     rcx, rbp; SourceProcessHandle
0x180009b81  mov     [rsp+78h+DesiredAccess], 0; DesiredAccess
0x180009b89  call    cs:__imp_NtDuplicateObject
0x180009b90  nop     dword ptr [rax+rax+00h]
0x180009b95  mov     [r14], rbx
0x180009b98  mov     eax, r12d
0x180009b9b  jmp     loc_180009C79
0x180009ba0  mov     rax, [rsp+78h+arg_8]
0x180009ba8  mov     r12, [rsp+78h+arg_10]
0x180009bb0  mov     rdx, [r15]; SourceHandle
0x180009bb3  test    rdx, rdx
0x180009bb6  jz      loc_180009C68
0x180009bbc  cmp     rdx, rax
0x180009bbf  jz      loc_180009C62
0x180009bc5  mov     eax, 2
0x180009bca  mov     r9, r15; TargetHandle
0x180009bcd  mov     [rsp+78h+Options], eax; Options
0x180009bd1  mov     r8, rbp; TargetProcessHandle
0x180009bd4  mov     [rsp+78h+HandleAttributes], eax; HandleAttributes
0x180009bd8  mov     rcx, r12; SourceProcessHandle
0x180009bdb  mov     [rsp+78h+DesiredAccess], 0; DesiredAccess
0x180009be3  call    cs:__imp_NtDuplicateObject
0x180009bea  nop     dword ptr [rax+rax+00h]
0x180009bef  xor     r12d, r12d
0x180009bf2  mov     r15d, eax
0x180009bf5  test    eax, eax
0x180009bf7  jns     short loc_180009C68
0x180009bf9  test    rbx, rbx
0x180009bfc  jz      short loc_180009C2B
0x180009bfe  mov     rdx, [r14]; SourceHandle
0x180009c01  xor     r9d, r9d; TargetHandle
0x180009c04  mov     [rsp+78h+Options], 1; Options
0x180009c0c  xor     r8d, r8d; TargetProcessHandle
0x180009c0f  mov     [rsp+78h+HandleAttributes], r12d; HandleAttributes
0x180009c14  mov     rcx, rbp; SourceProcessHandle
0x180009c17  mov     [rsp+78h+DesiredAccess], r12d; DesiredAccess
0x180009c1c  call    cs:__imp_NtDuplicateObject
0x180009c23  nop     dword ptr [rax+rax+00h]
0x180009c28  mov     [r14], rbx
0x180009c2b  test    r13, r13
0x180009c2e  jz      short loc_180009C5D
0x180009c30  mov     rdx, [rsi]; SourceHandle
0x180009c33  xor     r9d, r9d; TargetHandle
0x180009c36  mov     [rsp+78h+Options], 1; Options
0x180009c3e  xor     r8d, r8d; TargetProcessHandle
0x180009c41  mov     [rsp+78h+HandleAttributes], r12d; HandleAttributes
0x180009c46  mov     rcx, rbp; SourceProcessHandle
0x180009c49  mov     [rsp+78h+DesiredAccess], r12d; DesiredAccess
0x180009c4e  call    cs:__imp_NtDuplicateObject
0x180009c55  nop     dword ptr [rax+rax+00h]
0x180009c5a  mov     [rsi], r13
0x180009c5d  mov     eax, r15d
0x180009c60  jmp     short loc_180009C79
0x180009c62  mov     rax, [rsi]
0x180009c65  mov     [r15], rax
0x180009c68  mov     byte ptr [rdi+0F9h], 1
0x180009c6f  jmp     loc_180009A84
0x180009c74  mov     eax, 0C0000008h
0x180009c79  mov     rbx, [rsp+78h+arg_0]
0x180009c81  add     rsp, 40h
0x180009c85  pop     r15
0x180009c87  pop     r14
0x180009c89  pop     r13
0x180009c8b  pop     r12
0x180009c8d  pop     rdi
0x180009c8e  pop     rsi
0x180009c8f  pop     rbp
0x180009c90  retn
```
