# _anonymous_namespace_::CTracingSink::WriteUtf8NullTerminated

- ea: `0x180073840`
- end: `0x180073acb`
- name: `_anonymous_namespace_::CTracingSink::WriteUtf8NullTerminated`
- size: `651`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x18002d2b0`
- `0x180073840`
- `0x18009e020`

## import_xrefs

- `ntdll!NtWriteFile` at `0x18007392e`
- `ntdll!NtWriteFile` at `0x180073993`
- `ntdll!NtWriteFile` at `0x18007392e`
- `ntdll!NtWriteFile` at `0x180073993`
- `ntdll!DbgPrint` at `0x180073a79`
- `ntdll!DbgPrint` at `0x180073a97`
- `ntdll!DbgPrint` at `0x180073a79`
- `ntdll!DbgPrint` at `0x180073a97`

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
        || byte_1800D2D20
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
0x180073840  test    rdx, rdx
0x180073843  jz      locret_180073AC9
0x180073849  mov     [rsp-8+arg_18], rbx
0x18007384e  push    rbp
0x18007384f  push    rsi
0x180073850  push    rdi
0x180073851  push    r12
0x180073853  push    r13
0x180073855  push    r14
0x180073857  push    r15
0x180073859  lea     rbp, [rsp-27h]
0x18007385e  sub     rsp, 0B0h
0x180073865  mov     rax, cs:__security_cookie
0x18007386c  xor     rax, rsp
0x18007386f  mov     [rbp+57h+var_40], rax
0x180073873  mov     sil, r9b
0x180073876  mov     byte ptr [rbp+57h+var_60], r9b
0x18007387a  xor     r9d, r9d
0x18007387d  mov     rdi, r8
0x180073880  mov     rbx, rdx
0x180073883  mov     r15, rcx
0x180073886  test    r8, r8
0x180073889  jz      loc_180073AA3
0x18007388f  mov     rcx, [rcx+10h]
0x180073893  xorps   xmm0, xmm0
0x180073896  mov     r12b, [r8+rdx-1]
0x18007389b  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18007389f  lea     rax, [rcx-1]
0x1800738a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800738a7  jbe     short loc_1800738E8
0x1800738a9  cmp     cs:byte_1800D2D20, r9b
0x1800738b0  jz      loc_1800739A2
0x1800738b6  mov     r8, gs:60h
0x1800738bf  mov     rax, [r15+8]
0x1800738c3  mov     cl, [rax+854h]
0x1800738c9  mov     rax, [r8+20h]
0x1800738cd  neg     cl
0x1800738cf  sbb     rdx, rdx
0x1800738d2  and     edx, 8
0x1800738d5  mov     rcx, [rdx+rax+28h]; FileHandle
0x1800738da  lea     rax, [rcx-1]
0x1800738de  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800738e2  ja      loc_1800739A2
0x1800738e8  mov     qword ptr [rbp+57h+var_58], 0FFFFFFFFFFFFFFFFh
0x1800738f0  mov     r14, rdi
0x1800738f3  mov     esi, ebx
0x1800738f5  cmp     rbx, 100000h
0x1800738fc  jbe     short loc_180073903
0x1800738fe  mov     esi, 100000h
0x180073903  mov     [rsp+0E0h+Key], r9; Key
0x180073908  lea     rax, [rbp+57h+var_58]
0x18007390c  mov     [rsp+0E0h+ByteOffset], rax; ByteOffset
0x180073911  xor     r9d, r9d; ApcContext
0x180073914  mov     [rsp+0E0h+Length], esi; Length
0x180073918  lea     rax, [rbp+57h+var_50]
0x18007391c  mov     [rsp+0E0h+Buffer], r14; Buffer
0x180073921  xor     r8d, r8d; ApcRoutine
0x180073924  xor     edx, edx; Event
0x180073926  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x18007392b  mov     r13, rcx
0x18007392e  call    cs:__imp_NtWriteFile
0x180073935  nop     dword ptr [rax+rax+00h]
0x18007393a  xor     r9d, r9d; ApcContext
0x18007393d  test    eax, eax
0x18007393f  js      short loc_18007394E
0x180073941  mov     eax, esi
0x180073943  mov     rcx, r13
0x180073946  add     r14, rax
0x180073949  sub     rbx, rax
0x18007394c  jnz     short loc_1800738F3
0x18007394e  mov     sil, byte ptr [rbp+57h+var_60]
0x180073952  test    sil, sil
0x180073955  jnz     short loc_1800739A2
0x180073957  cmp     r12b, 0Ah
0x18007395b  jz      short loc_1800739A2
0x18007395d  mov     [rsp+0E0h+Key], r9; Key
0x180073962  lea     rax, [rbp+57h+var_58]
0x180073966  mov     [rsp+0E0h+ByteOffset], rax; ByteOffset
0x18007396b  xor     r8d, r8d; ApcRoutine
0x18007396e  lea     rax, [rbp+57h+var_60]
0x180073972  mov     [rsp+0E0h+Length], 2; Length
0x18007397a  mov     [rsp+0E0h+Buffer], rax; Buffer
0x18007397f  xor     edx, edx; Event
0x180073981  lea     rax, [rbp+57h+var_50]
0x180073985  mov     [rbp+57h+var_60], 0A0Dh
0x18007398b  mov     rcx, r13; FileHandle
0x18007398e  mov     [rsp+0E0h+IoStatusBlock], rax; IoStatusBlock
0x180073993  call    cs:__imp_NtWriteFile
0x18007399a  nop     dword ptr [rax+rax+00h]
0x18007399f  xor     r9d, r9d
0x1800739a2  mov     r10, cs:ProcedureAddress
0x1800739a9  mov     rax, [r15+8]
0x1800739ad  test    r10, r10
0x1800739b0  jz      loc_180073A57
0x1800739b6  xorps   xmm0, xmm0
0x1800739b9  mov     ecx, 4000000h
0x1800739be  movups  [rbp+57h+var_80], xmm0
0x1800739c2  mov     dword ptr [rbp+57h+var_80], ecx
0x1800739c5  mov     edx, 2000000h
0x1800739ca  movups  [rbp+57h+var_70], xmm0
0x1800739ce  cmp     [rax+854h], r9b
0x1800739d5  cmovnz  ecx, edx
0x1800739d8  mov     dword ptr [rbp+57h+var_80], ecx
0x1800739db  mov     edx, [rax+858h]
0x1800739e1  test    edx, edx
0x1800739e3  jz      short loc_1800739EC
0x1800739e5  or      edx, ecx
0x1800739e7  mov     dword ptr [rbp+57h+var_80+4], edx
0x1800739ea  jmp     short loc_1800739F0
0x1800739ec  mov     dword ptr [rbp+57h+var_80+4], r9d
0x1800739f0  mov     [rsp+0E0h+var_90], r9d
0x1800739f5  lea     r8, aD_0; "D"
0x1800739fc  mov     qword ptr [rbp+57h+var_80+8], rdi
0x180073a00  mov     edx, 18000h
0x180073a05  mov     ecx, [rax+850h]
0x180073a0b  mov     [rsp+0E0h+var_98], r9
0x180073a10  mov     r9, [rax+840h]
0x180073a17  mov     dword ptr [rsp+0E0h+Key], ecx
0x180073a1b  mov     rcx, [rax+848h]
0x180073a22  mov     [rsp+0E0h+ByteOffset], rcx
0x180073a27  mov     rcx, [rax+830h]
0x180073a2e  mov     qword ptr [rsp+0E0h+Length], rcx
0x180073a33  mov     rcx, [rax+828h]
0x180073a3a  mov     [rsp+0E0h+Buffer], rcx
0x180073a3f  mov     ecx, [rax+838h]
0x180073a45  mov     rax, r10
0x180073a48  mov     dword ptr [rsp+0E0h+IoStatusBlock], ecx
0x180073a4c  lea     rcx, [rbp+57h+var_80]
0x180073a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073a55  jmp     short loc_180073AA3
0x180073a57  cmp     [rax+854h], r9b
0x180073a5e  jnz     short loc_180073A6F
0x180073a60  mov     rax, gs:60h
0x180073a69  cmp     [rax+2], r9b
0x180073a6d  jz      short loc_180073AA3
0x180073a6f  mov     rdx, rdi
0x180073a72  lea     rcx, aHs; "%hs"
0x180073a79  call    cs:__imp_DbgPrint
0x180073a80  nop     dword ptr [rax+rax+00h]
0x180073a85  test    sil, sil
0x180073a88  jnz     short loc_180073AA3
0x180073a8a  cmp     r12b, 0Ah
0x180073a8e  jz      short loc_180073AA3
0x180073a90  lea     rcx, asc_1800BD154; "\n"
0x180073a97  call    cs:__imp_DbgPrint
0x180073a9e  nop     dword ptr [rax+rax+00h]
0x180073aa3  mov     rcx, [rbp+57h+var_40]
0x180073aa7  xor     rcx, rsp; StackCookie
0x180073aaa  call    __security_check_cookie
0x180073aaf  mov     rbx, [rsp+0E0h+arg_18]
0x180073ab7  add     rsp, 0B0h
0x180073abe  pop     r15
0x180073ac0  pop     r14
0x180073ac2  pop     r13
0x180073ac4  pop     r12
0x180073ac6  pop     rdi
0x180073ac7  pop     rsi
0x180073ac8  pop     rbp
0x180073ac9  retn
```
