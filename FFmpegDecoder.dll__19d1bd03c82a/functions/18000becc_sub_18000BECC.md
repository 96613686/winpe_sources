# sub_18000BECC

- ea: `0x18000becc`
- end: `0x18000bff6`
- name: `sub_18000BECC`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180005cc0`

## callees

- `0x1800013e4`
- `0x180003710`
- `0x18000becc`
- `0x18000c4a8`
- `0x18000c6dc`
- `0x180017bd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bf05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bfc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bf05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bfc3`

## pseudocode

```c
int __fastcall sub_18000BECC(__int64 a1)
{
  _QWORD *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  _DWORD *v5; // rdi
  __int64 v6; // r8
  int v7; // r9d
  __int64 v8; // rbx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v11; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v13; // [rsp+60h] [rbp-38h]
  __int64 v14; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v16; // [rsp+78h] [rbp-20h]

  sub_18000C4A8();
  v2 = (_QWORD *)sub_180003710();
  v5 = (_DWORD *)v2[1];
  if ( *v5 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    v6 = *(_QWORD *)(a1 + 272);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v16 = 4;
    v13 = &v11;
    v14 = 8;
    LODWORD(v2) = sub_1800013E4((int)v5, (int)&byte_180027AF7, (int)v6 + 8, v7, 4u, &v12);
  }
  if ( !*(_DWORD *)(a1 + 312) )
  {
    v8 = a1 + 288;
    if ( qword_18002FF10 )
    {
      LOBYTE(v3) = 1;
      v2 = (_QWORD *)sub_18000C6DC(v4, v3);
      *(_QWORD *)v8 = v2;
      if ( v2 )
      {
        *(_QWORD *)(v8 + 16) = *v2;
        *v2 = v8;
        LODWORD(v2) = GetCurrentThreadId();
        *(_DWORD *)(v8 + 24) = (_DWORD)v2;
      }
    }
    else
    {
      *(_QWORD *)v8 = 0;
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x18000becc  mov     [rsp+arg_8], rbx
0x18000bed1  push    rdi
0x18000bed2  sub     rsp, 90h
0x18000bed9  mov     rax, cs:__security_cookie
0x18000bee0  xor     rax, rsp
0x18000bee3  mov     [rsp+98h+var_18], rax
0x18000beeb  mov     rbx, rcx
0x18000beee  call    sub_18000C4A8
0x18000bef3  call    sub_180003710
0x18000bef8  mov     rdi, [rax+8]
0x18000befc  cmp     dword ptr [rdi], 5
0x18000beff  jbe     loc_18000BF90
0x18000bf05  call    cs:GetCurrentThreadId
0x18000bf0b  mov     [rsp+98h+var_68], eax
0x18000bf0f  mov     [rsp+98h+var_60], 0
0x18000bf18  mov     r8, [rbx+110h]
0x18000bf1f  cmp     byte ptr [r8+4], 0
0x18000bf24  jz      short loc_18000BF45
0x18000bf26  lea     r9, [r8+18h]
0x18000bf2a  cmp     dword ptr [r9], 0
0x18000bf2e  jnz     short loc_18000BF48
0x18000bf30  cmp     dword ptr [r9+4], 0
0x18000bf35  jnz     short loc_18000BF48
0x18000bf37  cmp     dword ptr [r9+8], 0
0x18000bf3c  jnz     short loc_18000BF48
0x18000bf3e  cmp     dword ptr [r9+0Ch], 0
0x18000bf43  jnz     short loc_18000BF48
0x18000bf45  xor     r9d, r9d; int
0x18000bf48  lea     rax, [rsp+98h+var_68]
0x18000bf4d  mov     [rsp+98h+var_28], rax
0x18000bf52  mov     ecx, 4
0x18000bf57  mov     [rsp+98h+var_20], rcx
0x18000bf5c  lea     rax, [rsp+98h+var_60]
0x18000bf61  mov     [rsp+98h+var_38], rax
0x18000bf66  mov     [rsp+98h+var_30], 8
0x18000bf6f  add     r8, 8; int
0x18000bf73  lea     rax, [rsp+98h+var_58]
0x18000bf78  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x18000bf7d  mov     [rsp+98h+var_78], ecx; ULONG
0x18000bf81  lea     rdx, byte_180027AF7; int
0x18000bf88  mov     rcx, rdi; int
0x18000bf8b  call    sub_1800013E4
0x18000bf90  cmp     dword ptr [rbx+138h], 0
0x18000bf97  jnz     short loc_18000BFD5
0x18000bf99  add     rbx, 120h
0x18000bfa0  cmp     cs:qword_18002FF10, 0
0x18000bfa8  jz      short loc_18000BFCE
0x18000bfaa  mov     dl, 1
0x18000bfac  call    sub_18000C6DC
0x18000bfb1  mov     [rbx], rax
0x18000bfb4  test    rax, rax
0x18000bfb7  jz      short loc_18000BFD5
0x18000bfb9  mov     rcx, [rax]
0x18000bfbc  mov     [rbx+10h], rcx
0x18000bfc0  mov     [rax], rbx
0x18000bfc3  call    cs:GetCurrentThreadId
0x18000bfc9  mov     [rbx+18h], eax
0x18000bfcc  jmp     short loc_18000BFD5
0x18000bfce  mov     qword ptr [rbx], 0
0x18000bfd5  mov     rcx, [rsp+98h+var_18]
0x18000bfdd  xor     rcx, rsp; StackCookie
0x18000bfe0  call    __security_check_cookie
0x18000bfe5  mov     rbx, [rsp+98h+arg_8]
0x18000bfed  add     rsp, 90h
0x18000bff4  pop     rdi
0x18000bff5  retn
```
