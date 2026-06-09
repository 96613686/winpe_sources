# CVaultPackageId::CVaultPackageId(void * const)

- ea: `0x18002ea00`
- end: `0x18002eab6`
- name: `??0CVaultPackageId@@QEAA@QEAX@Z`
- size: `182`
- prototype: `CVaultPackageId *__fastcall(CVaultPackageId *this, void *const)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006324`
- `0x1800135d0`
- `0x180016250`
- `0x180022290`
- `0x1800358a0`
- `0x18003c1e0`

## callees

- `0x18002ea00`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002ea85`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002ea85`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002ea61`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18002ea61`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18002ea4c`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18002ea4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CVaultPackageId *__fastcall CVaultPackageId::CVaultPackageId(CVaultPackageId *this, void *const a2)
{
  DWORD v5; // ebp
  DWORD *v6; // rsi
  PUCHAR SidSubAuthorityCount; // r14
  PDWORD SidSubAuthority; // rax

  *((_DWORD *)this + 10) = 0;
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *(_QWORD *)((char *)this + 31) = 0;
  if ( a2 )
  {
    *(struct _SID_IDENTIFIER_AUTHORITY *)this = *GetSidIdentifierAuthority(a2);
    v5 = 0;
    v6 = (DWORD *)((char *)this + 7);
    SidSubAuthorityCount = GetSidSubAuthorityCount(a2);
    *((_BYTE *)this + 6) = *SidSubAuthorityCount;
    if ( *SidSubAuthorityCount )
    {
      do
      {
        SidSubAuthority = GetSidSubAuthority(a2, v5++);
        *v6++ = *SidSubAuthority;
      }
      while ( v5 < *SidSubAuthorityCount );
    }
    *((_DWORD *)this + 10) = (_DWORD)v6 - (_DWORD)this;
  }
  return this;
}

```

## disassembly

```asm
0x18002ea00  mov     [rsp+arg_18], rbx
0x18002ea05  push    rdi
0x18002ea06  sub     rsp, 20h
0x18002ea0a  mov     dword ptr [rcx+28h], 0
0x18002ea11  xorps   xmm0, xmm0
0x18002ea14  xor     eax, eax
0x18002ea16  mov     rdi, rdx
0x18002ea19  mov     rbx, rcx
0x18002ea1c  movups  xmmword ptr [rcx], xmm0
0x18002ea1f  movups  xmmword ptr [rcx+10h], xmm0
0x18002ea23  mov     [rcx+1Fh], rax
0x18002ea27  test    rdx, rdx
0x18002ea2a  jnz     short loc_18002EA3A
0x18002ea2c  mov     rax, rbx
0x18002ea2f  mov     rbx, [rsp+28h+arg_18]
0x18002ea34  add     rsp, 20h
0x18002ea38  pop     rdi
0x18002ea39  retn
0x18002ea3a  mov     [rsp+28h+arg_0], rbp
0x18002ea3f  mov     rcx, rdi; pSid
0x18002ea42  mov     [rsp+28h+arg_8], rsi
0x18002ea47  mov     [rsp+28h+arg_10], r14
0x18002ea4c  call    cs:__imp_GetSidIdentifierAuthority
0x18002ea52  mov     ecx, [rax]
0x18002ea54  mov     [rbx], ecx
0x18002ea56  mov     rcx, rdi; pSid
0x18002ea59  movzx   eax, word ptr [rax+4]
0x18002ea5d  mov     [rbx+4], ax
0x18002ea61  call    cs:__imp_GetSidSubAuthorityCount
0x18002ea67  xor     ebp, ebp
0x18002ea69  lea     rsi, [rbx+7]
0x18002ea6d  mov     r14, rax
0x18002ea70  movzx   ecx, byte ptr [rax]
0x18002ea73  mov     [rbx+6], cl
0x18002ea76  cmp     [rax], bpl
0x18002ea79  jbe     short loc_18002EA9D
0x18002ea7b  nop     dword ptr [rax+rax+00h]
0x18002ea80  mov     edx, ebp; nSubAuthority
0x18002ea82  mov     rcx, rdi; pSid
0x18002ea85  call    cs:__imp_GetSidSubAuthority
0x18002ea8b  inc     ebp
0x18002ea8d  mov     ecx, [rax]
0x18002ea8f  mov     [rsi], ecx
0x18002ea91  add     rsi, 4
0x18002ea95  movzx   eax, byte ptr [r14]
0x18002ea99  cmp     ebp, eax
0x18002ea9b  jb      short loc_18002EA80
0x18002ea9d  mov     r14, [rsp+28h+arg_10]
0x18002eaa2  sub     esi, ebx
0x18002eaa4  mov     rbp, [rsp+28h+arg_0]
0x18002eaa9  mov     [rbx+28h], esi
0x18002eaac  mov     rsi, [rsp+28h+arg_8]
0x18002eab1  jmp     loc_18002EA2C
```
