# BampThrottlingSetUserSettingsProcessInfo

- ea: `0x14000c6f0`
- end: `0x14000c833`
- name: `BampThrottlingSetUserSettingsProcessInfo`
- size: `323`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140001430`
- `0x1400026d0`
- `0x14000c6f0`
- `0x140010760`
- `0x1400107a0`
- `0x1400153a0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000c725`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000c744`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000c725`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000c744`

## pseudocode

```c
char __fastcall BampThrottlingSetUserSettingsProcessInfo(__int64 a1, PCUNICODE_STRING *a2)
{
  int *v4; // rdi
  char v5; // si
  int v6; // ecx
  int v7; // eax
  char v9; // [rsp+30h] [rbp-29h] BYREF
  int v10; // [rsp+34h] [rbp-25h] BYREF
  int v11; // [rsp+38h] [rbp-21h] BYREF
  char v12[32]; // [rsp+40h] [rbp-19h] BYREF
  int *v13; // [rsp+60h] [rbp+7h]
  __int64 v14; // [rsp+68h] [rbp+Fh]
  char *v15; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]
  int *v17; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]

  if ( !RtlCompareUnicodeString(*a2, (PCUNICODE_STRING)(a1 + 392), 0)
    && !RtlCompareUnicodeString(a2[1], (PCUNICODE_STRING)(a1 + 88), 1u) )
  {
    BampAcquireThrottledProcessLock(a1);
    if ( (*(_BYTE *)(a1 + 276) & 1) != 0 )
    {
      v4 = (int *)(a2 + 2);
      BampUpdateThrottledProcessState(a1, 0, 0, 0, v4);
      v5 = 1;
    }
    else
    {
      v5 = 0;
      v4 = (int *)(a2 + 2);
    }
    BampReleaseThrottledProcessLock(a1);
    if ( (unsigned int)dword_140007010 > 5 )
    {
      v6 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 464LL);
      v13 = &v10;
      v15 = &v9;
      v7 = *v4;
      v10 = v6;
      v11 = v7;
      v17 = &v11;
      v14 = 4;
      v9 = v5;
      v16 = 1;
      v18 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140007010, &dword_140004C54, 0, 0, 5, v12);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000c6f0  mov     [rsp-8+arg_10], rbx
0x14000c6f5  push    rbp
0x14000c6f6  push    rsi
0x14000c6f7  push    rdi
0x14000c6f8  lea     rbp, [rsp-47h]
0x14000c6fd  sub     rsp, 0A0h
0x14000c704  mov     rax, cs:__security_cookie
0x14000c70b  xor     rax, rsp
0x14000c70e  mov     [rbp+57h+var_20], rax
0x14000c712  mov     rdi, rdx
0x14000c715  mov     rbx, rcx
0x14000c718  lea     rdx, [rcx+188h]; String2
0x14000c71f  xor     r8d, r8d; CaseInSensitive
0x14000c722  mov     rcx, [rdi]; String1
0x14000c725  call    cs:__imp_RtlCompareUnicodeString
0x14000c72c  nop     dword ptr [rax+rax+00h]
0x14000c731  test    eax, eax
0x14000c733  jnz     loc_14000C811
0x14000c739  mov     rcx, [rdi+8]; String1
0x14000c73d  lea     rdx, [rbx+58h]; String2
0x14000c741  mov     r8b, 1; CaseInSensitive
0x14000c744  call    cs:__imp_RtlCompareUnicodeString
0x14000c74b  nop     dword ptr [rax+rax+00h]
0x14000c750  test    eax, eax
0x14000c752  jnz     loc_14000C811
0x14000c758  mov     rcx, rbx
0x14000c75b  call    BampAcquireThrottledProcessLock
0x14000c760  test    byte ptr [rbx+114h], 1
0x14000c767  jz      short loc_14000C787
0x14000c769  add     rdi, 10h
0x14000c76d  xor     r9d, r9d
0x14000c770  xor     r8d, r8d
0x14000c773  mov     [rsp+0B0h+var_90], rdi
0x14000c778  xor     edx, edx
0x14000c77a  mov     rcx, rbx
0x14000c77d  call    BampUpdateThrottledProcessState
0x14000c782  mov     sil, 1
0x14000c785  jmp     short loc_14000C78E
0x14000c787  xor     sil, sil
0x14000c78a  add     rdi, 10h
0x14000c78e  mov     rcx, rbx
0x14000c791  call    BampReleaseThrottledProcessLock
0x14000c796  mov     eax, cs:dword_140007010
0x14000c79c  cmp     eax, 5
0x14000c79f  jbe     short loc_14000C811
0x14000c7a1  mov     rax, [rbx+8]
0x14000c7a5  lea     rdx, dword_140004C54
0x14000c7ac  xor     r9d, r9d
0x14000c7af  xor     r8d, r8d
0x14000c7b2  mov     ecx, [rax+1D0h]
0x14000c7b8  lea     rax, [rbp+57h+var_7C]
0x14000c7bc  mov     [rbp+57h+var_50], rax
0x14000c7c0  lea     rax, [rbp+57h+var_80]
0x14000c7c4  mov     [rbp+57h+var_40], rax
0x14000c7c8  mov     eax, [rdi]
0x14000c7ca  mov     [rbp+57h+var_7C], ecx
0x14000c7cd  lea     rcx, [rbp+57h+var_70]
0x14000c7d1  mov     [rsp+0B0h+var_88], rcx
0x14000c7d6  lea     rcx, dword_140007010
0x14000c7dd  mov     [rbp+57h+var_78], eax
0x14000c7e0  lea     rax, [rbp+57h+var_78]
0x14000c7e4  mov     [rbp+57h+var_30], rax
0x14000c7e8  mov     [rbp+57h+var_48], 4
0x14000c7f0  mov     [rbp+57h+var_80], sil
0x14000c7f4  mov     [rbp+57h+var_38], 1
0x14000c7fc  mov     [rbp+57h+var_28], 4
0x14000c804  mov     dword ptr [rsp+0B0h+var_90], 5
0x14000c80c  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c811  mov     al, 1
0x14000c813  mov     rcx, [rbp+57h+var_20]
0x14000c817  xor     rcx, rsp; StackCookie
0x14000c81a  call    __security_check_cookie
0x14000c81f  mov     rbx, [rsp+0B0h+arg_10]
0x14000c827  add     rsp, 0A0h
0x14000c82e  pop     rdi
0x14000c82f  pop     rsi
0x14000c830  pop     rbp
0x14000c831  retn
```
