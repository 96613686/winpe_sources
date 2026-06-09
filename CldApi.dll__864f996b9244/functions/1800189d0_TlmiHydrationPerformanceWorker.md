# TlmiHydrationPerformanceWorker

- ea: `0x1800189d0`
- end: `0x180018b90`
- name: `TlmiHydrationPerformanceWorker`
- size: `448`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001070`
- `0x180001a80`
- `0x1800189d0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180018a5e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180018a5e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018aa5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018aa5`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180018ab3`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180018ab3`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180018abe`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x180018abe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018a2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018a46`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018a2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018a46`

## pseudocode

```c
__int64 __fastcall TlmiHydrationPerformanceWorker(PVOID Parameter)
{
  struct _RTL_AVL_TABLE *v1; // rbx
  int v2; // edi
  struct _RTL_AVL_TABLE *v3; // rax
  PVOID v4; // rax
  int v6; // [rsp+30h] [rbp-68h] BYREF
  __int64 v7; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-58h] BYREF
  int *v9; // [rsp+60h] [rbp-38h]
  __int64 v10; // [rsp+68h] [rbp-30h]
  __int64 *v11; // [rsp+70h] [rbp-28h]
  __int64 v12; // [rsp+78h] [rbp-20h]

  while ( byte_180028930
       && !NtCurrentPeb()->Ldr->ShutdownInProgress
       && !WaitForSingleObject(hEvent, 0xFFFFFFFF)
       && WaitForSingleObject(qword_180028B50, 0x36EE80u) == 258 )
  {
    RtlAcquireSRWLockExclusive(&qword_180028A60);
    v1 = qword_180028A68;
    v2 = dword_180028B40;
    dword_180028B40 = 0;
    v3 = &stru_180028AD8;
    if ( qword_180028A68 != &stru_180028A70 )
      v3 = &stru_180028A70;
    qword_180028A68 = v3;
    RtlReleaseSRWLockExclusive(&qword_180028A60);
    while ( 1 )
    {
      v4 = RtlEnumerateGenericTableAvl(v1, 1u);
      if ( !v4 )
        break;
      RtlDeleteElementGenericTableAvl(v1, v4);
    }
    if ( v2
      && (unsigned int)dword_1800281A0 > 5
      && (qword_1800281B0 & 0x400000000000LL) != 0
      && (qword_1800281B8 & 0x400000000000LL) == qword_1800281B8 )
    {
      v6 = v2;
      v9 = &v6;
      v10 = 4;
      v11 = &v7;
      v7 = 0x1000000;
      v12 = 8;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_1800281A0, (unsigned __int8 *)word_18002277A, 0, 0, 4u, &v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800189d0  mov     [rsp+arg_0], rbx
0x1800189d5  mov     [rsp+arg_8], rbp
0x1800189da  push    rdi
0x1800189db  sub     rsp, 90h
0x1800189e2  mov     rax, cs:__security_cookie
0x1800189e9  xor     rax, rsp
0x1800189ec  mov     [rsp+98h+var_18], rax
0x1800189f4  mov     rbp, 400000000000h
0x1800189fe  cmp     cs:byte_180028930, 0
0x180018a05  jz      loc_180018B69
0x180018a0b  mov     rax, gs:60h
0x180018a14  mov     rcx, [rax+18h]
0x180018a18  cmp     byte ptr [rcx+48h], 0
0x180018a1c  jnz     loc_180018B69
0x180018a22  mov     rcx, cs:hEvent; hHandle
0x180018a29  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180018a2c  call    cs:__imp_WaitForSingleObject
0x180018a32  test    eax, eax
0x180018a34  jnz     loc_180018B69
0x180018a3a  mov     rcx, cs:qword_180028B50; hHandle
0x180018a41  mov     edx, 36EE80h; dwMilliseconds
0x180018a46  call    cs:__imp_WaitForSingleObject
0x180018a4c  cmp     eax, 102h
0x180018a51  jnz     loc_180018B69
0x180018a57  lea     rcx, qword_180028A60
0x180018a5e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180018a64  mov     rbx, cs:qword_180028A68
0x180018a6b  lea     rcx, stru_180028A70
0x180018a72  mov     edi, cs:dword_180028B40
0x180018a78  lea     rdx, stru_180028A70
0x180018a7f  cmp     rbx, rcx
0x180018a82  mov     cs:dword_180028B40, 0
0x180018a8c  lea     rax, stru_180028AD8
0x180018a93  cmovnz  rax, rdx
0x180018a97  lea     rcx, qword_180028A60
0x180018a9e  mov     cs:qword_180028A68, rax
0x180018aa5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180018aab  jmp     short loc_180018AB9
0x180018aad  mov     rdx, rax; Buffer
0x180018ab0  mov     rcx, rbx; Table
0x180018ab3  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180018ab9  mov     dl, 1; Restart
0x180018abb  mov     rcx, rbx; Table
0x180018abe  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180018ac4  test    rax, rax
0x180018ac7  jnz     short loc_180018AAD
0x180018ac9  test    edi, edi
0x180018acb  jz      loc_1800189FE
0x180018ad1  mov     eax, cs:dword_1800281A0
0x180018ad7  cmp     eax, 5
0x180018ada  jbe     loc_1800189FE
0x180018ae0  mov     rcx, cs:qword_1800281B8
0x180018ae7  mov     rax, cs:qword_1800281B0
0x180018aee  test    rbp, rax
0x180018af1  jz      loc_1800189FE
0x180018af7  mov     rax, rcx
0x180018afa  and     rax, rbp
0x180018afd  cmp     rax, rcx
0x180018b00  jnz     loc_1800189FE
0x180018b06  lea     rax, [rsp+98h+var_68]
0x180018b0b  mov     [rsp+98h+var_68], edi
0x180018b0f  mov     [rsp+98h+var_38], rax
0x180018b14  lea     rdx, word_18002277A
0x180018b1b  lea     rax, [rsp+98h+var_60]
0x180018b20  mov     [rsp+98h+var_30], 4
0x180018b29  mov     [rsp+98h+var_28], rax
0x180018b2e  lea     rcx, dword_1800281A0
0x180018b35  lea     rax, [rsp+98h+var_58]
0x180018b3a  mov     [rsp+98h+var_60], 1000000h
0x180018b43  mov     [rsp+98h+var_70], rax
0x180018b48  xor     r9d, r9d
0x180018b4b  xor     r8d, r8d
0x180018b4e  mov     [rsp+98h+var_78], 4
0x180018b56  mov     [rsp+98h+var_20], 8
0x180018b5f  call    _tlgWriteTransfer_EventWriteTransfer
0x180018b64  jmp     loc_1800189FE
0x180018b69  xor     eax, eax
0x180018b6b  mov     rcx, [rsp+98h+var_18]
0x180018b73  xor     rcx, rsp; StackCookie
0x180018b76  call    __security_check_cookie
0x180018b7b  lea     r11, [rsp+98h+var_8]
0x180018b83  mov     rbx, [r11+10h]
0x180018b87  mov     rbp, [r11+18h]
0x180018b8b  mov     rsp, r11
0x180018b8e  pop     rdi
0x180018b8f  retn
```
