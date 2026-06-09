# _anonymous_namespace_::CTracingSink::WriteUtf8NullTerminated

- ea: `0x180073aa0`
- end: `0x180073d2b`
- name: `_anonymous_namespace_::CTracingSink::WriteUtf8NullTerminated`
- size: `651`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x1800293a0`
- `0x180073aa0`
- `0x1800a0020`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180073b8e`
- `ntdll!NtWriteFile` at `0x180073bf3`
- `ntdll!NtWriteFile` at `0x180073b8e`
- `ntdll!NtWriteFile` at `0x180073bf3`
- `ntdll!DbgPrint` at `0x180073cd9`
- `ntdll!DbgPrint` at `0x180073cf7`
- `ntdll!DbgPrint` at `0x180073cd9`
- `ntdll!DbgPrint` at `0x180073cf7`

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
        || byte_1800D4D10
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
0x180073aa0  test    rdx, rdx
0x180073aa3  jz      locret_180073D29
0x180073aa9  mov     [rsp-8+arg_18], rbx
0x180073aae  push    rbp
0x180073aaf  push    rsi
0x180073ab0  push    rdi
0x180073ab1  push    r12
0x180073ab3  push    r13
0x180073ab5  push    r14
0x180073ab7  push    r15
0x180073ab9  lea     rbp, [rsp-27h]
0x180073abe  sub     rsp, 0B0h
0x180073ac5  mov     rax, cs:__security_cookie
0x180073acc  xor     rax, rsp
0x180073acf  mov     [rbp+57h+var_40], rax
0x180073ad3  mov     sil, r9b
0x180073ad6  mov     byte ptr [rbp+57h+var_60], r9b
0x180073ada  xor     r9d, r9d
0x180073add  mov     rdi, r8
0x180073ae0  mov     rbx, rdx
0x180073ae3  mov     r15, rcx
0x180073ae6  test    r8, r8
0x180073ae9  jz      loc_180073D03
0x180073aef  mov     rcx, [rcx+10h]
0x180073af3  xorps   xmm0, xmm0
0x180073af6  mov     r12b, [r8+rdx-1]
0x180073afb  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180073aff  lea     rax, [rcx-1]
0x180073b03  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180073b07  jbe     short loc_180073B48
0x180073b09  cmp     cs:byte_1800D4D10, r9b
0x180073b10  jz      loc_180073C02
0x180073b16  mov     r8, gs:60h
0x180073b1f  mov     rax, [r15+8]
0x180073b23  mov     cl, [rax+854h]
0x180073b29  mov     rax, [r8+20h]
0x180073b2d  neg     cl
0x180073b2f  sbb     rdx, rdx
0x180073b32  and     edx, 8
0x180073b35  mov     rcx, [rdx+rax+28h]; FileHandle
0x180073b3a  lea     rax, [rcx-1]
0x180073b3e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180073b42  ja      loc_180073C02
0x180073b48  mov     qword ptr [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x180073b50  mov     r14, rdi
0x180073b53  mov     esi, ebx
0x180073b55  cmp     rbx, 100000h
0x180073b5c  jbe     short loc_180073B63
0x180073b5e  mov     esi, 100000h
0x180073b63  mov     [rsp+0E0h+Key], r9; Key
0x180073b68  lea     rax, [rbp+57h+var_58]
0x180073b6c  mov     [rsp+0E0h+ByteOffset], rax; ByteOffset
0x180073b71  xor     r9d, r9d; ApcContext
0x180073b74  mov     [rsp+0E0h+Length], esi; Length
0x180073b78  lea     rax, [rbp+57h+var_50]
0x180073b7c  mov     [rsp+0E0h+Buffer], r14; Buffer
0x180073b81  xor     r8d, r8d; ApcRoutine
0x180073b84  xor     edx, edx; Event
0x180073b86  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x180073b8b  mov     r13, rcx
0x180073b8e  call    cs:__imp_NtWriteFile
0x180073b95  nop     dword ptr [rax+rax+00h]
0x180073b9a  xor     r9d, r9d; ApcContext
0x180073b9d  test    eax, eax
0x180073b9f  js      short loc_180073BAE
0x180073ba1  mov     eax, esi
0x180073ba3  mov     rcx, r13
0x180073ba6  add     r14, rax
0x180073ba9  sub     rbx, rax
0x180073bac  jnz     short loc_180073B53
0x180073bae  mov     sil, byte ptr [rbp+57h+var_60]
0x180073bb2  test    sil, sil
0x180073bb5  jnz     short loc_180073C02
0x180073bb7  cmp     r12b, 0Ah
0x180073bbb  jz      short loc_180073C02
0x180073bbd  mov     [rsp+0E0h+Key], r9; Key
0x180073bc2  lea     rax, [rbp+57h+var_58]
0x180073bc6  mov     [rsp+0E0h+ByteOffset], rax; ByteOffset
0x180073bcb  xor     r8d, r8d; ApcRoutine
0x180073bce  lea     rax, [rbp+57h+var_60]
0x180073bd2  mov     [rsp+0E0h+Length], 2; Length
0x180073bda  mov     [rsp+0E0h+Buffer], rax; Buffer
0x180073bdf  xor     edx, edx; Event
0x180073be1  lea     rax, [rbp+57h+var_50]
0x180073be5  mov     [rbp+57h+var_60], 0A0Dh
0x180073beb  mov     rcx, r13; FileHandle
0x180073bee  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x180073bf3  call    cs:__imp_NtWriteFile
0x180073bfa  nop     dword ptr [rax+rax+00h]
0x180073bff  xor     r9d, r9d
0x180073c02  mov     r10, cs:ProcedureAddress
0x180073c09  mov     rax, [r15+8]
0x180073c0d  test    r10, r10
0x180073c10  jz      loc_180073CB7
0x180073c16  xorps   xmm0, xmm0
0x180073c19  mov     ecx, 4000000h
0x180073c1e  movups  [rbp+57h+var_80], xmm0
0x180073c22  mov     dword ptr [rbp+57h+var_80], ecx
0x180073c25  mov     edx, 2000000h
0x180073c2a  movups  [rbp+57h+var_70], xmm0
0x180073c2e  cmp     [rax+854h], r9b
0x180073c35  cmovnz  ecx, edx
0x180073c38  mov     dword ptr [rbp+57h+var_80], ecx
0x180073c3b  mov     edx, [rax+858h]
0x180073c41  test    edx, edx
0x180073c43  jz      short loc_180073C4C
0x180073c45  or      edx, ecx
0x180073c47  mov     dword ptr [rbp+57h+var_80+4], edx
0x180073c4a  jmp     short loc_180073C50
0x180073c4c  mov     dword ptr [rbp+57h+var_80+4], r9d
0x180073c50  mov     [rsp+0E0h+var_90], r9d
0x180073c55  lea     r8, aD_0; "D"
0x180073c5c  mov     qword ptr [rbp+57h+var_80+8], rdi
0x180073c60  mov     edx, 18000h
0x180073c65  mov     ecx, [rax+850h]
0x180073c6b  mov     [rsp+0E0h+var_98], r9
0x180073c70  mov     r9, [rax+840h]
0x180073c77  mov     dword ptr [rsp+0E0h+Key], ecx
0x180073c7b  mov     rcx, [rax+848h]
0x180073c82  mov     [rsp+0E0h+ByteOffset], rcx
0x180073c87  mov     rcx, [rax+830h]
0x180073c8e  mov     qword ptr [rsp+0E0h+Length], rcx
0x180073c93  mov     rcx, [rax+828h]
0x180073c9a  mov     [rsp+0E0h+Buffer], rcx
0x180073c9f  mov     ecx, [rax+838h]
0x180073ca5  mov     rax, r10
0x180073ca8  mov     dword ptr [rsp+0E0h+IoStatusBlock], ecx
0x180073cac  lea     rcx, [rbp+57h+var_80]
0x180073cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073cb5  jmp     short loc_180073D03
0x180073cb7  cmp     [rax+854h], r9b
0x180073cbe  jnz     short loc_180073CCF
0x180073cc0  mov     rax, gs:60h
0x180073cc9  cmp     [rax+2], r9b
0x180073ccd  jz      short loc_180073D03
0x180073ccf  mov     rdx, rdi
0x180073cd2  lea     rcx, aHs; "%hs"
0x180073cd9  call    cs:__imp_DbgPrint
0x180073ce0  nop     dword ptr [rax+rax+00h]
0x180073ce5  test    sil, sil
0x180073ce8  jnz     short loc_180073D03
0x180073cea  cmp     r12b, 0Ah
0x180073cee  jz      short loc_180073D03
0x180073cf0  lea     rcx, asc_1800BEECC; "\n"
0x180073cf7  call    cs:__imp_DbgPrint
0x180073cfe  nop     dword ptr [rax+rax+00h]
0x180073d03  mov     rcx, [rbp+57h+var_40]
0x180073d07  xor     rcx, rsp; StackCookie
0x180073d0a  call    __security_check_cookie
0x180073d0f  mov     rbx, [rsp+0E0h+arg_18]
0x180073d17  add     rsp, 0B0h
0x180073d1e  pop     r15
0x180073d20  pop     r14
0x180073d22  pop     r13
0x180073d24  pop     r12
0x180073d26  pop     rdi
0x180073d27  pop     rsi
0x180073d28  pop     rbp
0x180073d29  retn
```
