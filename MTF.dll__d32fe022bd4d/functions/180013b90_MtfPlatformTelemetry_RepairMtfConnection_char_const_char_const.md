# MtfPlatformTelemetry::RepairMtfConnection<char const *>(char const * &&)

- ea: `0x180013b90`
- end: `0x180013c78`
- name: `??$RepairMtfConnection@PEBD@MtfPlatformTelemetry@@SAX$$QEAPEBD@Z`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180019b00`

## callees

- `0x18000163c`
- `0x1800053cc`
- `0x180013b90`
- `0x18002bca0`

## pseudocode

```c
int __fastcall MtfPlatformTelemetry::RepairMtfConnection<char const *>(const unsigned __int16 **a1)
{
  __int64 v2; // r10
  __int64 v3; // rax
  const unsigned __int16 *v4; // rax
  __int64 v5; // rcx
  int v6; // ecx
  __int64 v8; // [rsp+30h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp-58h] BYREF
  const unsigned __int16 *v10; // [rsp+60h] [rbp-38h]
  int v11; // [rsp+68h] [rbp-30h]
  int v12; // [rsp+6Ch] [rbp-2Ch]
  __int64 *v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  v2 = *((_QWORD *)MtfPlatformTelemetry::Instance() + 1);
  LODWORD(v3) = *(_DWORD *)v2;
  if ( *(_DWORD *)v2 > 5u )
  {
    v3 = *(_QWORD *)(v2 + 16);
    if ( (v3 & 0x400000000000LL) != 0 )
    {
      LODWORD(v3) = 0;
      if ( (*(_QWORD *)(v2 + 24) & 0x400000000000LL) == *(_QWORD *)(v2 + 24) )
      {
        v4 = *a1;
        v8 = 0x1000000;
        v13 = &v8;
        v14 = 8;
        if ( v4 )
        {
          v5 = -1;
          do
            ++v5;
          while ( *((_BYTE *)v4 + v5) );
          v6 = v5 + 1;
        }
        else
        {
          v4 = &byte_180033D2B;
          v6 = 1;
        }
        v10 = v4;
        v11 = v6;
        v12 = 0;
        LODWORD(v3) = tlgWriteTransfer_EventWriteTransfer(v2, (unsigned __int8 *)byte_180036B81, 0, 0, 4u, &v9);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180013b90  push    rbx
0x180013b92  sub     rsp, 90h
0x180013b99  mov     rax, cs:__security_cookie
0x180013ba0  xor     rax, rsp
0x180013ba3  mov     [rsp+98h+var_18], rax
0x180013bab  mov     rbx, rcx
0x180013bae  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x180013bb3  mov     r10, [rax+8]
0x180013bb7  mov     eax, [r10]
0x180013bba  cmp     eax, 5
0x180013bbd  jbe     loc_180013C5F
0x180013bc3  mov     rdx, [r10+18h]
0x180013bc7  mov     rcx, 400000000000h
0x180013bd1  mov     rax, [r10+10h]
0x180013bd5  test    rcx, rax
0x180013bd8  jz      loc_180013C5F
0x180013bde  mov     rax, rdx
0x180013be1  and     rax, rcx
0x180013be4  cmp     rax, rdx
0x180013be7  jnz     short loc_180013C5F
0x180013be9  mov     rax, [rbx]
0x180013bec  lea     rcx, [rsp+98h+var_68]
0x180013bf1  xor     edx, edx
0x180013bf3  mov     [rsp+98h+var_68], 1000000h
0x180013bfc  mov     [rsp+98h+var_28], rcx
0x180013c01  mov     [rsp+98h+var_20], 8
0x180013c0a  test    rax, rax
0x180013c0d  jz      short loc_180013C1F
0x180013c0f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013c13  inc     rcx
0x180013c16  cmp     [rax+rcx], dl
0x180013c19  jnz     short loc_180013C13
0x180013c1b  inc     ecx
0x180013c1d  jmp     short loc_180013C2B
0x180013c1f  lea     rax, byte_180033D2B
0x180013c26  mov     ecx, 1
0x180013c2b  mov     [rsp+98h+var_38], rax
0x180013c30  xor     r9d, r9d
0x180013c33  lea     rax, [rsp+98h+var_58]
0x180013c38  mov     [rsp+98h+var_30], ecx
0x180013c3c  mov     [rsp+98h+var_2C], edx
0x180013c40  xor     r8d, r8d
0x180013c43  mov     [rsp+98h+var_70], rax
0x180013c48  lea     rdx, byte_180036B81
0x180013c4f  mov     rcx, r10
0x180013c52  mov     [rsp+98h+var_78], 4
0x180013c5a  call    _tlgWriteTransfer_EventWriteTransfer
0x180013c5f  mov     rcx, [rsp+98h+var_18]
0x180013c67  xor     rcx, rsp; StackCookie
0x180013c6a  call    __security_check_cookie
0x180013c6f  add     rsp, 90h
0x180013c76  pop     rbx
0x180013c77  retn
```
