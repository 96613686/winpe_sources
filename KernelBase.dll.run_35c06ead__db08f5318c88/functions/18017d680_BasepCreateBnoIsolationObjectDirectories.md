# BasepCreateBnoIsolationObjectDirectories

- ea: `0x18017d680`
- end: `0x18017d841`
- name: `BasepCreateBnoIsolationObjectDirectories`
- size: `449`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x18007f610`

## callees

- `0x18006e604`
- `0x18017d680`
- `0x18017d848`

## import_xrefs

- `ntdll!NtClose` at `0x18017d7db`
- `ntdll!NtClose` at `0x18017d7ea`
- `ntdll!NtClose` at `0x18017d805`
- `ntdll!NtClose` at `0x18017d7db`
- `ntdll!NtClose` at `0x18017d7ea`
- `ntdll!NtClose` at `0x18017d805`
- `ntdll!RtlFreeHeap` at `0x18017d824`
- `ntdll!RtlFreeHeap` at `0x18017d824`
- `ntdll!NtOpenProcessToken` at `0x18017d6dd`
- `ntdll!NtOpenProcessToken` at `0x18017d6dd`
- `ntdll!NtCreateDirectoryObjectEx` at `0x18017d788`
- `ntdll!NtCreateDirectoryObjectEx` at `0x18017d788`
- `ntdll!RtlAllocateHeap` at `0x18017d706`
- `ntdll!RtlAllocateHeap` at `0x18017d706`

## pseudocode

```c
__int64 __fastcall BasepCreateBnoIsolationObjectDirectories(HANDLE TokenHandle, __int64 a2)
{
  HANDLE v3; // rdi
  int NamedObjectDirectoryForToken; // edi
  unsigned int v5; // r14d
  void **Heap; // rbx
  __int64 i; // rsi
  void *v8; // rcx
  __int128 v10; // [rsp+40h] [rbp-30h] BYREF
  __int128 v11; // [rsp+50h] [rbp-20h]
  __int128 v12; // [rsp+60h] [rbp-10h]
  HANDLE Handle; // [rsp+90h] [rbp+20h] BYREF
  HANDLE TokenHandlea; // [rsp+98h] [rbp+28h] BYREF

  *(_QWORD *)(a2 + 24) = 0;
  *(_DWORD *)(a2 + 16) = 0;
  TokenHandlea = 0;
  v3 = TokenHandle;
  Handle = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  if ( !TokenHandle )
  {
    NamedObjectDirectoryForToken = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandlea);
    if ( NamedObjectDirectoryForToken < 0 )
    {
      Heap = 0;
      v5 = 0;
      goto LABEL_11;
    }
    v3 = TokenHandlea;
  }
  v5 = 5;
  Heap = (void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x28u);
  if ( Heap )
  {
    NamedObjectDirectoryForToken = BasepGetNamedObjectDirectoryForToken(v3, 1, 0, 15, &Handle);
    if ( NamedObjectDirectoryForToken >= 0 )
    {
      LODWORD(v10) = 48;
      *((_QWORD *)&v10 + 1) = Handle;
      DWORD2(v11) = 128;
      *(_QWORD *)&v11 = a2;
      v12 = 0;
      NamedObjectDirectoryForToken = NtCreateDirectoryObjectEx(Heap, 15, &v10, 0, 1);
      if ( NamedObjectDirectoryForToken >= 0 )
      {
        NamedObjectDirectoryForToken = BasepCreateBnoIsolationSymbolicLinks(
                                         Handle,
                                         *Heap,
                                         a2,
                                         Heap + 1,
                                         Heap + 2,
                                         Heap + 3,
                                         Heap + 4);
        if ( NamedObjectDirectoryForToken >= 0 )
        {
          *(_QWORD *)(a2 + 24) = Heap;
          Heap = 0;
          *(_DWORD *)(a2 + 16) = 5;
        }
      }
    }
  }
  else
  {
    NamedObjectDirectoryForToken = -1073741801;
  }
LABEL_11:
  if ( TokenHandlea )
    NtClose(TokenHandlea);
  if ( Handle )
    NtClose(Handle);
  if ( Heap )
  {
    for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
    {
      v8 = Heap[i];
      if ( v8 )
        NtClose(v8);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  return (unsigned int)NamedObjectDirectoryForToken;
}

```

## disassembly

```asm
0x18017d680  mov     [rsp-18h+arg_10], rbx
0x18017d685  mov     [rsp-18h+arg_18], rsi
0x18017d68a  push    rbp
0x18017d68b  push    rdi
0x18017d68c  push    r14
0x18017d68e  mov     rbp, rsp
0x18017d691  sub     rsp, 70h
0x18017d695  mov     qword ptr [rdx+18h], 0
0x18017d69d  xorps   xmm0, xmm0
0x18017d6a0  mov     dword ptr [rdx+10h], 0
0x18017d6a7  mov     rsi, rdx
0x18017d6aa  mov     [rbp+TokenHandle], 0
0x18017d6b2  mov     rdi, rcx
0x18017d6b5  mov     [rbp+Handle], 0
0x18017d6bd  mov     ebx, 8
0x18017d6c2  movups  [rbp+var_30], xmm0
0x18017d6c6  movups  [rbp+var_20], xmm0
0x18017d6ca  movups  [rbp+var_10], xmm0
0x18017d6ce  test    rcx, rcx
0x18017d6d1  jnz     short loc_18017D6ED
0x18017d6d3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18017d6d7  mov     edx, ebx; DesiredAccess
0x18017d6d9  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18017d6dd  call    cs:__imp_NtOpenProcessToken
0x18017d6e3  mov     edi, eax
0x18017d6e5  test    eax, eax
0x18017d6e7  js      short loc_18017D71E
0x18017d6e9  mov     rdi, [rbp+TokenHandle]
0x18017d6ed  mov     rcx, gs:60h
0x18017d6f6  mov     r14d, 5
0x18017d6fc  mov     edx, ebx; Flags
0x18017d6fe  mov     rcx, [rcx+30h]; HeapHandle
0x18017d702  lea     r8d, [r14+23h]; Size
0x18017d706  call    cs:__imp_RtlAllocateHeap
0x18017d70c  mov     rbx, rax
0x18017d70f  test    rax, rax
0x18017d712  jnz     short loc_18017D728
0x18017d714  mov     edi, 0C0000017h
0x18017d719  jmp     loc_18017D7D2
0x18017d71e  xor     ebx, ebx
0x18017d720  xor     r14d, r14d
0x18017d723  jmp     loc_18017D7D2
0x18017d728  mov     r9d, 0Fh
0x18017d72e  lea     rax, [rbp+Handle]
0x18017d732  xor     r8d, r8d
0x18017d735  mov     [rsp+70h+var_50], rax; __int64
0x18017d73a  mov     rcx, rdi; TokenHandle
0x18017d73d  lea     edx, [r9-0Eh]
0x18017d741  call    BasepGetNamedObjectDirectoryForToken
0x18017d746  mov     edi, eax
0x18017d748  test    eax, eax
0x18017d74a  js      loc_18017D7D2
0x18017d750  mov     rax, [rbp+Handle]
0x18017d754  lea     r8, [rbp+var_30]
0x18017d758  xor     r9d, r9d
0x18017d75b  mov     dword ptr [rbp+var_30], 30h ; '0'
0x18017d762  xorps   xmm0, xmm0
0x18017d765  mov     qword ptr [rbp+var_30+8], rax
0x18017d769  mov     rcx, rbx
0x18017d76c  mov     dword ptr [rbp+var_20+8], 80h
0x18017d773  mov     qword ptr [rbp+var_20], rsi
0x18017d777  lea     edx, [r9+0Fh]
0x18017d77b  mov     dword ptr [rsp+70h+var_50], 1
0x18017d783  movdqu  [rbp+var_10], xmm0
0x18017d788  call    cs:__imp_NtCreateDirectoryObjectEx
0x18017d78e  mov     edi, eax
0x18017d790  test    eax, eax
0x18017d792  js      short loc_18017D7D2
0x18017d794  lea     rax, [rbx+20h]
0x18017d798  mov     r8, rsi
0x18017d79b  mov     [rsp+70h+var_40], rax; __int64
0x18017d7a0  lea     rcx, [rbx+18h]
0x18017d7a4  mov     [rsp+70h+var_48], rcx; __int64
0x18017d7a9  lea     rdx, [rbx+10h]
0x18017d7ad  mov     rcx, [rbp+Handle]; Handle
0x18017d7b1  lea     r9, [rbx+8]
0x18017d7b5  mov     [rsp+70h+var_50], rdx; __int64
0x18017d7ba  mov     rdx, [rbx]
0x18017d7bd  call    BasepCreateBnoIsolationSymbolicLinks
0x18017d7c2  mov     edi, eax
0x18017d7c4  test    eax, eax
0x18017d7c6  js      short loc_18017D7D2
0x18017d7c8  mov     [rsi+18h], rbx
0x18017d7cc  xor     ebx, ebx
0x18017d7ce  mov     [rsi+10h], r14d
0x18017d7d2  mov     rcx, [rbp+TokenHandle]; Handle
0x18017d7d6  test    rcx, rcx
0x18017d7d9  jz      short loc_18017D7E1
0x18017d7db  call    cs:__imp_NtClose
0x18017d7e1  mov     rcx, [rbp+Handle]; Handle
0x18017d7e5  test    rcx, rcx
0x18017d7e8  jz      short loc_18017D7F0
0x18017d7ea  call    cs:__imp_NtClose
0x18017d7f0  test    rbx, rbx
0x18017d7f3  jz      short loc_18017D82A
0x18017d7f5  xor     esi, esi
0x18017d7f7  test    r14d, r14d
0x18017d7fa  jz      short loc_18017D812
0x18017d7fc  mov     rcx, [rbx+rsi*8]; Handle
0x18017d800  test    rcx, rcx
0x18017d803  jz      short loc_18017D80B
0x18017d805  call    cs:__imp_NtClose
0x18017d80b  inc     esi
0x18017d80d  cmp     esi, r14d
0x18017d810  jb      short loc_18017D7FC
0x18017d812  mov     rcx, gs:60h
0x18017d81b  mov     r8, rbx; P
0x18017d81e  xor     edx, edx; Flags
0x18017d820  mov     rcx, [rcx+30h]; HeapHandle
0x18017d824  call    cs:__imp_RtlFreeHeap
0x18017d82a  lea     r11, [rsp+70h+var_s0]
0x18017d82f  mov     eax, edi
0x18017d831  mov     rbx, [r11+30h]
0x18017d835  mov     rsi, [r11+38h]
0x18017d839  mov     rsp, r11
0x18017d83c  pop     r14
0x18017d83e  pop     rdi
0x18017d83f  pop     rbp
0x18017d840  retn
```
