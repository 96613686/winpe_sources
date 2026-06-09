# sub_1800AACB8

- ea: `0x1800aacb8`
- end: `0x1800aad42`
- name: `sub_1800AACB8`
- size: `138`
- prototype: `__int64 __fastcall(WCHAR *, __int64, SECURITY_INFORMATION, void *, int, struct _ACL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a46b0`

## callees

- `0x18009caec`
- `0x1800aacb8`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800aace5`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800aace5`

## pseudocode

```c
__int64 __fastcall sub_1800AACB8(WCHAR *a1, __int64 a2, SECURITY_INFORMATION a3, void *a4, int a5, struct _ACL *a6)
{
  int v6; // edi
  signed int v7; // eax
  unsigned int v8; // ebx

  v6 = (int)a1;
  v7 = SetNamedSecurityInfoW(a1, SE_REGISTRY_KEY, a3, a4, 0, a6, 0);
  v8 = v7;
  if ( !v7 )
    return 0;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( RequestContext != &RequestContext && (*((_BYTE *)RequestContext + 28) & 1) != 0 )
    sub_18009CAEC(*((_QWORD *)RequestContext + 2), 21, (unsigned int)qword_1800D4DA0, v6, v8);
  return v8;
}

```

## disassembly

```asm
0x1800aacb8  mov     r11, rsp
0x1800aacbb  mov     [r11+8], rbx
0x1800aacbf  push    rdi
0x1800aacc0  sub     rsp, 40h
0x1800aacc4  mov     rax, [rsp+48h+arg_28]
0x1800aacc9  mov     edx, 4; ObjectType
0x1800aacce  mov     qword ptr [r11-18h], 0
0x1800aacd6  mov     rdi, rcx
0x1800aacd9  mov     [r11-20h], rax
0x1800aacdd  mov     qword ptr [r11-28h], 0
0x1800aace5  call    cs:SetNamedSecurityInfoW
0x1800aaceb  mov     ebx, eax
0x1800aaced  test    eax, eax
0x1800aacef  jz      short loc_1800AAD35
0x1800aacf1  jle     short loc_1800AACFC
0x1800aacf3  movzx   ebx, ax
0x1800aacf6  or      ebx, 80070000h
0x1800aacfc  mov     rcx, cs:RequestContext
0x1800aad03  lea     rax, RequestContext
0x1800aad0a  cmp     rcx, rax
0x1800aad0d  jz      short loc_1800AAD31
0x1800aad0f  test    byte ptr [rcx+1Ch], 1
0x1800aad13  jz      short loc_1800AAD31
0x1800aad15  mov     rcx, [rcx+10h]
0x1800aad19  lea     r8, qword_1800D4DA0
0x1800aad20  mov     edx, 15h
0x1800aad25  mov     [rsp+48h+var_28], ebx
0x1800aad29  mov     r9, rdi
0x1800aad2c  call    sub_18009CAEC
0x1800aad31  mov     eax, ebx
0x1800aad33  jmp     short loc_1800AAD37
0x1800aad35  xor     eax, eax
0x1800aad37  mov     rbx, [rsp+48h+arg_0]
0x1800aad3c  add     rsp, 40h
0x1800aad40  pop     rdi
0x1800aad41  retn
```
