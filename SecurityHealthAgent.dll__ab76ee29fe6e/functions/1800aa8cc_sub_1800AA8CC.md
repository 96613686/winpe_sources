# sub_1800AA8CC

- ea: `0x1800aa8cc`
- end: `0x1800aa954`
- name: `sub_1800AA8CC`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a6288`

## callees

- `0x180056834`
- `0x1800a9b54`
- `0x1800aa8cc`
- `0x1800ab834`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800aa946`
- `KERNEL32!LocalFree` at `0x1800aa946`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800aa8e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800aa8e9`

## pseudocode

```c
__int64 __fastcall sub_1800AA8CC(__int64 a1, void *a2)
{
  unsigned int v3; // ebx
  LPWSTR StringSid; // [rsp+40h] [rbp+18h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(a2, &StringSid) )
  {
    v3 = sub_1800A9B54(a1, StringSid);
  }
  else
  {
    v3 = sub_1800AB834();
    if ( RequestContext != &RequestContext && (*((_BYTE *)RequestContext + 28) & 1) != 0 )
      sub_180056834(*((_QWORD *)RequestContext + 2), 0xFu, (const GUID *)qword_1800D4DA0, v3);
  }
  if ( StringSid )
    LocalFree(StringSid);
  return v3;
}

```

## disassembly

```asm
0x1800aa8cc  push    rbx
0x1800aa8ce  sub     rsp, 20h
0x1800aa8d2  mov     rax, rdx
0x1800aa8d5  mov     [rsp+28h+StringSid], 0
0x1800aa8de  mov     rbx, rcx
0x1800aa8e1  lea     rdx, [rsp+28h+StringSid]; StringSid
0x1800aa8e6  mov     rcx, rax; Sid
0x1800aa8e9  call    cs:ConvertSidToStringSidW
0x1800aa8ef  test    eax, eax
0x1800aa8f1  jnz     short loc_1800AA92D
0x1800aa8f3  call    sub_1800AB834
0x1800aa8f8  mov     ebx, eax
0x1800aa8fa  mov     rcx, cs:RequestContext
0x1800aa901  lea     rax, RequestContext
0x1800aa908  cmp     rcx, rax
0x1800aa90b  jz      short loc_1800AA93C
0x1800aa90d  test    byte ptr [rcx+1Ch], 1
0x1800aa911  jz      short loc_1800AA93C
0x1800aa913  mov     rcx, [rcx+10h]
0x1800aa917  lea     r8, qword_1800D4DA0
0x1800aa91e  mov     edx, 0Fh
0x1800aa923  mov     r9d, ebx
0x1800aa926  call    sub_180056834
0x1800aa92b  jmp     short loc_1800AA93C
0x1800aa92d  mov     rdx, [rsp+28h+StringSid]
0x1800aa932  mov     rcx, rbx
0x1800aa935  call    sub_1800A9B54
0x1800aa93a  mov     ebx, eax
0x1800aa93c  mov     rcx, [rsp+28h+StringSid]; hMem
0x1800aa941  test    rcx, rcx
0x1800aa944  jz      short loc_1800AA94C
0x1800aa946  call    cs:__imp_LocalFree
0x1800aa94c  mov     eax, ebx
0x1800aa94e  add     rsp, 20h
0x1800aa952  pop     rbx
0x1800aa953  retn
```
