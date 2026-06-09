# _anonymous_namespace_::CTracingSink::WriteUtf8NullTerminated

- ea: `0x180035c70`
- end: `0x180035efb`
- name: `_anonymous_namespace_::CTracingSink::WriteUtf8NullTerminated`
- size: `651`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x1800031d0`
- `0x180035c70`
- `0x1801bd010`

## import_xrefs

- `ntdll!DbgPrint` at `0x180035ea9`
- `ntdll!DbgPrint` at `0x180035ec7`
- `ntdll!DbgPrint` at `0x180035ea9`
- `ntdll!DbgPrint` at `0x180035ec7`
- `ntdll!NtWriteFile` at `0x180035d5e`
- `ntdll!NtWriteFile` at `0x180035dc3`
- `ntdll!NtWriteFile` at `0x180035d5e`
- `ntdll!NtWriteFile` at `0x180035dc3`

## pseudocode

```c
void __fastcall anonymous_namespace_::CTracingSink::WriteUtf8NullTerminated(
        __int64 a1,
        unsigned __int64 a2,
        const char *a3,
        char a4)
{
  char v4; // si
  unsigned __int64 v6; // rbx
  char *v8; // rcx
  char v9; // r12
  char *Buffer; // r14
  ULONG Length; // esi
  char *v12; // r13
  __int64 v13; // rax
  int v14; // ecx
  int v15; // edx
  _OWORD v16[2]; // [rsp+60h] [rbp-29h] BYREF
  __int16 v17; // [rsp+80h] [rbp-9h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+88h] [rbp-1h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp+7h] BYREF

  if ( a2 )
  {
    v4 = a4;
    LOBYTE(v17) = a4;
    v6 = a2;
    if ( a3 )
    {
      v8 = *(char **)(a1 + 16);
      v9 = a3[a2 - 1];
      IoStatusBlock = 0;
      if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL
        || byte_180243850
        && (v8 = *(char **)((char *)&NtCurrentPeb()->ProcessParameters->StandardOutput
                          + (*(_BYTE *)(*(_QWORD *)(a1 + 8) + 2132LL) != 0 ? 8 : 0)),
            (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL) )
      {
        ByteOffset.QuadPart = -1;
        Buffer = (char *)a3;
        do
        {
          Length = v6;
          if ( v6 > 0x100000 )
            Length = 0x100000;
          v12 = v8;
          if ( NtWriteFile(v8, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0) < 0 )
            break;
          v8 = v12;
          Buffer += Length;
          v6 -= Length;
        }
        while ( v6 );
        v4 = v17;
        if ( !(_BYTE)v17 && v9 != 10 )
        {
          v17 = 2573;
          NtWriteFile(v12, 0, 0, 0, &IoStatusBlock, &v17, 2u, &ByteOffset, 0);
        }
      }
      v13 = *(_QWORD *)(a1 + 8);
      if ( ProcedureAddress )
      {
        v14 = 0x4000000;
        memset(v16, 0, sizeof(v16));
        LODWORD(v16[0]) = 0x4000000;
        if ( *(_BYTE *)(v13 + 2132) )
          v14 = 0x2000000;
        LODWORD(v16[0]) = v14;
        v15 = *(_DWORD *)(v13 + 2136);
        if ( v15 )
          DWORD1(v16[0]) = v14 | v15;
        else
          DWORD1(v16[0]) = 0;
        *((_QWORD *)&v16[0] + 1) = a3;
        ((void (__fastcall *)(_OWORD *, __int64, const char *, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))ProcedureAddress)(
          v16,
          98304,
          "D",
          *(_QWORD *)(v13 + 2112),
          *(_DWORD *)(v13 + 2104),
          *(_QWORD *)(v13 + 2088),
          *(_QWORD *)(v13 + 2096),
          *(_QWORD *)(v13 + 2120),
          *(_DWORD *)(v13 + 2128),
          0,
          0);
      }
      else if ( *(_BYTE *)(v13 + 2132) || NtCurrentPeb()->BeingDebugged )
      {
        DbgPrint("%hs", a3);
        if ( !v4 && v9 != 10 )
          DbgPrint("\n");
      }
    }
  }
}

```

## disassembly

```asm
0x180035c70  test    rdx, rdx
0x180035c73  jz      locret_180035EF9
0x180035c79  mov     [rsp-8+arg_18], rbx
0x180035c7e  push    rbp
0x180035c7f  push    rsi
0x180035c80  push    rdi
0x180035c81  push    r12
0x180035c83  push    r13
0x180035c85  push    r14
0x180035c87  push    r15
0x180035c89  lea     rbp, [rsp-27h]
0x180035c8e  sub     rsp, 0B0h
0x180035c95  mov     rax, cs:__security_cookie
0x180035c9c  xor     rax, rsp
0x180035c9f  mov     [rbp+57h+var_40], rax
0x180035ca3  mov     sil, r9b
0x180035ca6  mov     byte ptr [rbp+57h+var_60], r9b
0x180035caa  xor     r9d, r9d
0x180035cad  mov     rdi, r8
0x180035cb0  mov     rbx, rdx
0x180035cb3  mov     r15, rcx
0x180035cb6  test    r8, r8
0x180035cb9  jz      loc_180035ED3
0x180035cbf  mov     rcx, [rcx+10h]
0x180035cc3  xorps   xmm0, xmm0
0x180035cc6  mov     r12b, [r8+rdx-1]
0x180035ccb  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180035ccf  lea     rax, [rcx-1]
0x180035cd3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180035cd7  jbe     short loc_180035D18
0x180035cd9  cmp     cs:byte_180243850, r9b
0x180035ce0  jz      loc_180035DD2
0x180035ce6  mov     r8, gs:60h
0x180035cef  mov     rax, [r15+8]
0x180035cf3  mov     cl, [rax+854h]
0x180035cf9  mov     rax, [r8+20h]
0x180035cfd  neg     cl
0x180035cff  sbb     rdx, rdx
0x180035d02  and     edx, 8
0x180035d05  mov     rcx, [rdx+rax+28h]; FileHandle
0x180035d0a  lea     rax, [rcx-1]
0x180035d0e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180035d12  ja      loc_180035DD2
0x180035d18  mov     qword ptr [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x180035d20  mov     r14, rdi
0x180035d23  mov     esi, ebx
0x180035d25  cmp     rbx, 100000h
0x180035d2c  jbe     short loc_180035D33
0x180035d2e  mov     esi, 100000h
0x180035d33  mov     [rsp+0E0h+Key], r9; Key
0x180035d38  lea     rax, [rbp+57h+var_58]
0x180035d3c  mov     [rsp+0E0h+ByteOffset], rax; ByteOffset
0x180035d41  xor     r9d, r9d; ApcContext
0x180035d44  mov     [rsp+0E0h+Length], esi; Length
0x180035d48  lea     rax, [rbp+57h+var_50]
0x180035d4c  mov     [rsp+0E0h+Buffer], r14; Buffer
0x180035d51  xor     r8d, r8d; ApcRoutine
0x180035d54  xor     edx, edx; Event
0x180035d56  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x180035d5b  mov     r13, rcx
0x180035d5e  call    cs:__imp_NtWriteFile
0x180035d65  nop     dword ptr [rax+rax+00h]
0x180035d6a  xor     r9d, r9d; ApcContext
0x180035d6d  test    eax, eax
0x180035d6f  js      short loc_180035D7E
0x180035d71  mov     eax, esi
0x180035d73  mov     rcx, r13
0x180035d76  add     r14, rax
0x180035d79  sub     rbx, rax
0x180035d7c  jnz     short loc_180035D23
0x180035d7e  mov     sil, byte ptr [rbp+57h+var_60]
0x180035d82  test    sil, sil
0x180035d85  jnz     short loc_180035DD2
0x180035d87  cmp     r12b, 0Ah
0x180035d8b  jz      short loc_180035DD2
0x180035d8d  mov     [rsp+0E0h+Key], r9; Key
0x180035d92  lea     rax, [rbp+57h+var_58]
0x180035d96  mov     [rsp+0E0h+ByteOffset], rax; ByteOffset
0x180035d9b  xor     r8d, r8d; ApcRoutine
0x180035d9e  lea     rax, [rbp+57h+var_60]
0x180035da2  mov     [rsp+0E0h+Length], 2; Length
0x180035daa  mov     [rsp+0E0h+Buffer], rax; Buffer
0x180035daf  xor     edx, edx; Event
0x180035db1  lea     rax, [rbp+57h+var_50]
0x180035db5  mov     [rbp+57h+var_60], 0A0Dh
0x180035dbb  mov     rcx, r13; FileHandle
0x180035dbe  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x180035dc3  call    cs:__imp_NtWriteFile
0x180035dca  nop     dword ptr [rax+rax+00h]
0x180035dcf  xor     r9d, r9d
0x180035dd2  mov     r10, cs:ProcedureAddress
0x180035dd9  mov     rax, [r15+8]
0x180035ddd  test    r10, r10
0x180035de0  jz      loc_180035E87
0x180035de6  xorps   xmm0, xmm0
0x180035de9  mov     ecx, 4000000h
0x180035dee  movups  [rbp+57h+var_80], xmm0
0x180035df2  mov     dword ptr [rbp+57h+var_80], ecx
0x180035df5  mov     edx, 2000000h
0x180035dfa  movups  [rbp+57h+var_70], xmm0
0x180035dfe  cmp     [rax+854h], r9b
0x180035e05  cmovnz  ecx, edx
0x180035e08  mov     dword ptr [rbp+57h+var_80], ecx
0x180035e0b  mov     edx, [rax+858h]
0x180035e11  test    edx, edx
0x180035e13  jz      short loc_180035E1C
0x180035e15  or      edx, ecx
0x180035e17  mov     dword ptr [rbp+57h+var_80+4], edx
0x180035e1a  jmp     short loc_180035E20
0x180035e1c  mov     dword ptr [rbp+57h+var_80+4], r9d
0x180035e20  mov     [rsp+0E0h+var_90], r9d
0x180035e25  lea     r8, aD_1; "D"
0x180035e2c  mov     qword ptr [rbp+57h+var_80+8], rdi
0x180035e30  mov     edx, 18000h
0x180035e35  mov     ecx, [rax+850h]
0x180035e3b  mov     [rsp+0E0h+var_98], r9
0x180035e40  mov     r9, [rax+840h]
0x180035e47  mov     dword ptr [rsp+0E0h+Key], ecx
0x180035e4b  mov     rcx, [rax+848h]
0x180035e52  mov     [rsp+0E0h+ByteOffset], rcx
0x180035e57  mov     rcx, [rax+830h]
0x180035e5e  mov     qword ptr [rsp+0E0h+Length], rcx
0x180035e63  mov     rcx, [rax+828h]
0x180035e6a  mov     [rsp+0E0h+Buffer], rcx
0x180035e6f  mov     ecx, [rax+838h]
0x180035e75  mov     rax, r10
0x180035e78  mov     dword ptr [rsp+0E0h+IoStatusBlock], ecx
0x180035e7c  lea     rcx, [rbp+57h+var_80]
0x180035e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e85  jmp     short loc_180035ED3
0x180035e87  cmp     [rax+854h], r9b
0x180035e8e  jnz     short loc_180035E9F
0x180035e90  mov     rax, gs:60h
0x180035e99  cmp     [rax+2], r9b
0x180035e9d  jz      short loc_180035ED3
0x180035e9f  mov     rdx, rdi
0x180035ea2  lea     rcx, aHs; "%hs"
0x180035ea9  call    cs:__imp_DbgPrint
0x180035eb0  nop     dword ptr [rax+rax+00h]
0x180035eb5  test    sil, sil
0x180035eb8  jnz     short loc_180035ED3
0x180035eba  cmp     r12b, 0Ah
0x180035ebe  jz      short loc_180035ED3
0x180035ec0  lea     rcx, asc_1801CF2AC; "\n"
0x180035ec7  call    cs:__imp_DbgPrint
0x180035ece  nop     dword ptr [rax+rax+00h]
0x180035ed3  mov     rcx, [rbp+57h+var_40]
0x180035ed7  xor     rcx, rsp; StackCookie
0x180035eda  call    __security_check_cookie
0x180035edf  mov     rbx, [rsp+0E0h+arg_18]
0x180035ee7  add     rsp, 0B0h
0x180035eee  pop     r15
0x180035ef0  pop     r14
0x180035ef2  pop     r13
0x180035ef4  pop     r12
0x180035ef6  pop     rdi
0x180035ef7  pop     rsi
0x180035ef8  pop     rbp
0x180035ef9  retn
```
