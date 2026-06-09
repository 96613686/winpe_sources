# Common::Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>::EnsureCapacity(unsigned __int64)

- ea: `0x140008af0`
- end: `0x140008b9a`
- name: `?EnsureCapacity@?$Array@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@V?$ContainerOperations@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@V1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@6@V?$ArrayOperations@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@VNoKey@Common@@@6@@Common@@QEAAJ_K@Z`
- size: `170`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140009cd8`

## callees

- `0x140003644`
- `0x1400036c0`
- `0x140003f80`
- `0x140008af0`

## pseudocode

```c
__int64 __fastcall Common::Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>::EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rax
  unsigned __int64 v5; // rbx
  void *v6; // rax
  void *v7; // rsi

  v2 = *(_QWORD *)(a1 + 8);
  if ( a2 > v2 )
  {
    if ( v2 == 0x3FFFFFFF )
      return 2147483659LL;
    if ( v2 )
      v5 = ((3 * v2) >> 1) + 1;
    else
      v5 = 16;
    if ( a2 > v5 )
      v5 = a2;
    if ( v5 > 0x3FFFFFFF )
      v5 = 0x3FFFFFFF;
    v6 = operator new[](8 * v5, (const struct std::nothrow_t *)std::nothrow);
    v7 = v6;
    if ( !v6 )
      return 2147942414LL;
    if ( *(_QWORD *)a1 )
    {
      memmove_0(v6, *(const void **)a1, 8LL * *(_QWORD *)(a1 + 16));
      operator delete(*(void **)a1);
    }
    *(_QWORD *)a1 = v7;
    *(_QWORD *)(a1 + 8) = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x140008af0  mov     [rsp+arg_0], rbx
0x140008af5  mov     [rsp+arg_8], rsi
0x140008afa  push    rdi
0x140008afb  sub     rsp, 20h
0x140008aff  mov     rax, [rcx+8]
0x140008b03  mov     rdi, rcx
0x140008b06  cmp     rdx, rax
0x140008b09  jbe     short loc_140008B88
0x140008b0b  mov     ecx, 3FFFFFFFh
0x140008b10  cmp     rax, rcx
0x140008b13  jnz     short loc_140008B1C
0x140008b15  mov     eax, 8000000Bh
0x140008b1a  jmp     short loc_140008B8A
0x140008b1c  test    rax, rax
0x140008b1f  jnz     short loc_140008B26
0x140008b21  lea     ebx, [rax+10h]
0x140008b24  jmp     short loc_140008B30
0x140008b26  lea     rbx, [rax+rax*2]
0x140008b2a  shr     rbx, 1
0x140008b2d  inc     rbx
0x140008b30  cmp     rdx, rbx
0x140008b33  cmova   rbx, rdx
0x140008b37  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140008b3e  cmp     rbx, rcx
0x140008b41  cmova   rbx, rcx
0x140008b45  lea     rcx, ds:0[rbx*8]; unsigned __int64
0x140008b4d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140008b52  mov     rsi, rax
0x140008b55  test    rax, rax
0x140008b58  jnz     short loc_140008B61
0x140008b5a  mov     eax, 8007000Eh
0x140008b5f  jmp     short loc_140008B8A
0x140008b61  mov     rdx, [rdi]; Src
0x140008b64  test    rdx, rdx
0x140008b67  jz      short loc_140008B81
0x140008b69  mov     r8, [rdi+10h]
0x140008b6d  mov     rcx, rsi; void *
0x140008b70  shl     r8, 3; Size
0x140008b74  call    memmove_0
0x140008b79  mov     rcx, [rdi]; void *
0x140008b7c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008b81  mov     [rdi], rsi
0x140008b84  mov     [rdi+8], rbx
0x140008b88  xor     eax, eax
0x140008b8a  mov     rbx, [rsp+28h+arg_0]
0x140008b8f  mov     rsi, [rsp+28h+arg_8]
0x140008b94  add     rsp, 20h
0x140008b98  pop     rdi
0x140008b99  retn
```
