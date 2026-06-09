# CompareSids

- ea: `0x140034780`
- end: `0x140034874`
- name: `CompareSids`
- size: `244`
- prototype: `__int64 __fastcall(char *Sid, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003480`

## callees

- `0x140034780`
- `0x140078920`

## import_xrefs

- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400347f9`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x14003480b`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x1400347f9`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x14003480b`
- `ntoskrnl!RtlEqualSid` at `0x1400347a8`
- `ntoskrnl!RtlEqualSid` at `0x1400347a8`

## pseudocode

```c
__int64 __fastcall CompareSids(char *Sid, char *a2)
{
  BOOLEAN v4; // al
  unsigned int v5; // ecx
  int v7; // ecx
  unsigned int v8; // edi
  __int64 v9; // r8

  if ( Sid )
  {
    if ( a2 )
    {
      if ( Sid[1] != 1 && a2[1] != 1 )
      {
        if ( *Sid != *a2 )
          return 2;
        v7 = *(_DWORD *)(Sid + 2) - *(_DWORD *)(a2 + 2);
        if ( !v7 )
          v7 = *((unsigned __int16 *)Sid + 3) - *((unsigned __int16 *)a2 + 3);
        if ( v7 )
          return 2;
        v8 = *RtlSubAuthorityCountSid(Sid);
        v9 = *RtlSubAuthorityCountSid(a2);
        if ( (unsigned __int8)v8 <= (unsigned __int8)v9 )
          v9 = v8;
        if ( memcmp(Sid + 8, a2 + 8, 4 * v9) )
          return 2;
        return 0;
      }
      v4 = RtlEqualSid(Sid, a2);
      v5 = 2;
      if ( v4 )
        return 0;
      return v5;
    }
    else
    {
      return 0xFFFFFFFFLL;
    }
  }
  else
  {
    return a2 != 0;
  }
}

```

## disassembly

```asm
0x140034780  mov     [rsp+arg_8], rbx
0x140034785  push    rsi
0x140034786  sub     rsp, 20h
0x14003478a  mov     rsi, rdx
0x14003478d  mov     rbx, rcx
0x140034790  test    rcx, rcx
0x140034793  jz      loc_14003484D
0x140034799  test    rdx, rdx
0x14003479c  jz      loc_14003486A
0x1400347a2  cmp     byte ptr [rcx+1], 1
0x1400347a6  jnz     short loc_1400347CE
0x1400347a8  call    cs:__imp_RtlEqualSid
0x1400347af  nop     dword ptr [rax+rax+00h]
0x1400347b4  xor     edx, edx
0x1400347b6  mov     ecx, 2
0x1400347bb  test    al, al
0x1400347bd  cmovnz  ecx, edx
0x1400347c0  mov     eax, ecx
0x1400347c2  mov     rbx, [rsp+28h+arg_8]
0x1400347c7  add     rsp, 20h
0x1400347cb  pop     rsi
0x1400347cc  retn
0x1400347ce  cmp     byte ptr [rdx+1], 1
0x1400347d2  jz      short loc_1400347A8
0x1400347d4  movzx   eax, byte ptr [rdx]
0x1400347d7  cmp     [rcx], al
0x1400347d9  jnz     short loc_14003483C
0x1400347db  mov     ecx, [rcx+2]
0x1400347de  sub     ecx, [rdx+2]
0x1400347e1  jnz     short loc_1400347ED
0x1400347e3  movzx   ecx, word ptr [rbx+6]
0x1400347e7  movzx   eax, word ptr [rdx+6]
0x1400347eb  sub     ecx, eax
0x1400347ed  test    ecx, ecx
0x1400347ef  jnz     short loc_14003483C
0x1400347f1  mov     rcx, rbx; Sid
0x1400347f4  mov     [rsp+28h+arg_0], rdi
0x1400347f9  call    cs:__imp_RtlSubAuthorityCountSid
0x140034800  nop     dword ptr [rax+rax+00h]
0x140034805  mov     rcx, rsi; Sid
0x140034808  movzx   edi, byte ptr [rax]
0x14003480b  call    cs:__imp_RtlSubAuthorityCountSid
0x140034812  nop     dword ptr [rax+rax+00h]
0x140034817  lea     rdx, [rsi+8]; Buf2
0x14003481b  lea     rcx, [rbx+8]; Buf1
0x14003481f  movzx   r8d, byte ptr [rax]
0x140034823  cmp     dil, r8b
0x140034826  cmovbe  r8d, edi
0x14003482a  shl     r8, 2; Size
0x14003482e  call    memcmp
0x140034833  mov     rdi, [rsp+28h+arg_0]
0x140034838  test    eax, eax
0x14003483a  jz      short loc_140034852
0x14003483c  mov     eax, 2
0x140034841  mov     rbx, [rsp+28h+arg_8]
0x140034846  add     rsp, 20h
0x14003484a  pop     rsi
0x14003484b  retn
0x14003484d  test    rsi, rsi
0x140034850  jnz     short loc_140034859
0x140034852  xor     eax, eax
0x140034854  jmp     loc_1400347C2
0x140034859  mov     rbx, [rsp+28h+arg_8]
0x14003485e  mov     eax, 1
0x140034863  add     rsp, 20h
0x140034867  pop     rsi
0x140034868  retn
0x14003486a  mov     eax, 0FFFFFFFFh
0x14003486f  jmp     loc_1400347C2
```
