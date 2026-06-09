# UbpmpCopySid(uchar *,ulong,ulong *,void *,void * *)

- ea: `0x180037170`
- end: `0x1800371d8`
- name: `?UbpmpCopySid@@YAKPEAEKPEAKPEAXPEAPEAX@Z`
- size: `104`
- prototype: `unsigned int(unsigned __int8 *, unsigned int, unsigned int *, void *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020a80`

## callees

- `0x1800235c4`
- `0x180037170`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800371a6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800371a6`

## pseudocode

```c
__int64 __fastcall UbpmpCopySid(unsigned __int8 *a1, unsigned int a2, unsigned int *a3, void *a4, void **a5)
{
  DWORD LengthSid; // eax

  if ( a5 )
    *a5 = 0;
  if ( !a4 )
    return 0;
  LengthSid = GetLengthSid(a4);
  return UbpmpCopyArray<unsigned char>(a1, a2, a3, LengthSid, a4, a5);
}

```

## disassembly

```asm
0x180037170  push    rbx
0x180037172  push    rbp
0x180037173  push    rsi
0x180037174  push    rdi
0x180037175  push    r14
0x180037177  sub     rsp, 30h
0x18003717b  mov     rbx, [rsp+58h+arg_20]
0x180037183  mov     rdi, r9
0x180037186  mov     rsi, r8
0x180037189  mov     ebp, edx
0x18003718b  mov     r14, rcx
0x18003718e  test    rbx, rbx
0x180037191  jz      short loc_18003719A
0x180037193  mov     qword ptr [rbx], 0
0x18003719a  test    rdi, rdi
0x18003719d  jnz     short loc_1800371A3
0x18003719f  xor     eax, eax
0x1800371a1  jmp     short loc_1800371CC
0x1800371a3  mov     rcx, rdi; pSid
0x1800371a6  call    cs:__imp_GetLengthSid
0x1800371ad  nop     dword ptr [rax+rax+00h]
0x1800371b2  mov     [rsp+58h+var_30], rbx
0x1800371b7  mov     r8, rsi
0x1800371ba  mov     r9d, eax
0x1800371bd  mov     [rsp+58h+var_38], rdi
0x1800371c2  mov     edx, ebp
0x1800371c4  mov     rcx, r14
0x1800371c7  call    ??$UbpmpCopyArray@E@@YAKPEAEKPEAKKPEBEPEAPEAE@Z; UbpmpCopyArray<uchar>(uchar *,ulong,ulong *,ulong,uchar const *,uchar * *)
0x1800371cc  add     rsp, 30h
0x1800371d0  pop     r14
0x1800371d2  pop     rdi
0x1800371d3  pop     rsi
0x1800371d4  pop     rbp
0x1800371d5  pop     rbx
0x1800371d6  retn
```
