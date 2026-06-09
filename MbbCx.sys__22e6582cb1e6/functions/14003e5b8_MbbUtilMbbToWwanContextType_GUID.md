# MbbUtilMbbToWwanContextType(_GUID *)

- ea: `0x14003e5b8`
- end: `0x14003e7ee`
- name: `?MbbUtilMbbToWwanContextType@@YA?AW4_WWAN_CONTEXT_TYPE@@PEAU_GUID@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003bf28`
- `0x14003d580`
- `0x14003e480`

## callees

- `0x14003e5b8`
- `0x140047e50`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003e60d`
- `ntoskrnl!RtlCompareMemory` at `0x14003e633`
- `ntoskrnl!RtlCompareMemory` at `0x14003e65c`
- `ntoskrnl!RtlCompareMemory` at `0x14003e685`
- `ntoskrnl!RtlCompareMemory` at `0x14003e6ae`
- `ntoskrnl!RtlCompareMemory` at `0x14003e6d7`
- `ntoskrnl!RtlCompareMemory` at `0x14003e700`
- `ntoskrnl!RtlCompareMemory` at `0x14003e729`
- `ntoskrnl!RtlCompareMemory` at `0x14003e748`
- `ntoskrnl!RtlCompareMemory` at `0x14003e76e`
- `ntoskrnl!RtlCompareMemory` at `0x14003e794`
- `ntoskrnl!RtlCompareMemory` at `0x14003e7ba`
- `ntoskrnl!RtlCompareMemory` at `0x14003e60d`
- `ntoskrnl!RtlCompareMemory` at `0x14003e633`
- `ntoskrnl!RtlCompareMemory` at `0x14003e65c`
- `ntoskrnl!RtlCompareMemory` at `0x14003e685`
- `ntoskrnl!RtlCompareMemory` at `0x14003e6ae`
- `ntoskrnl!RtlCompareMemory` at `0x14003e6d7`
- `ntoskrnl!RtlCompareMemory` at `0x14003e700`
- `ntoskrnl!RtlCompareMemory` at `0x14003e729`
- `ntoskrnl!RtlCompareMemory` at `0x14003e748`
- `ntoskrnl!RtlCompareMemory` at `0x14003e76e`
- `ntoskrnl!RtlCompareMemory` at `0x14003e794`
- `ntoskrnl!RtlCompareMemory` at `0x14003e7ba`

## pseudocode

```c
__int64 __fastcall MbbUtilMbbToWwanContextType(struct _GUID *a1)
{
  unsigned int v1; // ecx
  SIZE_T v2; // rax
  unsigned __int32 Source1; // [rsp+20h] [rbp-20h] BYREF
  __int16 v5; // [rsp+24h] [rbp-1Ch]
  __int16 v6; // [rsp+26h] [rbp-1Ah]
  __int64 v7; // [rsp+28h] [rbp-18h]

  Source1 = _byteswap_ulong(a1->Data1);
  v5 = __ROR2__(a1->Data2, 8);
  v6 = __ROR2__(a1->Data3, 8);
  v7 = *(_QWORD *)a1->Data4;
  if ( RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_NONE, 0x10u) == 16 )
  {
    return 0;
  }
  else if ( RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_INTERNET, 0x10u) == 16 )
  {
    return 1;
  }
  else if ( RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_VPN, 0x10u) == 16 )
  {
    return 2;
  }
  else if ( RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_VOICE, 0x10u) == 16 )
  {
    return 3;
  }
  else if ( RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_VIDEO_SHARE, 0x10u) == 16 )
  {
    return 4;
  }
  else if ( RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_PURCHASE, 0x10u) == 16 )
  {
    return 6;
  }
  else if ( RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_MMS, 0x10u) == 16 )
  {
    return 7;
  }
  else if ( RtlCompareMemory(&Source1, MBB_UUID_CONTEXT_TYPE_LOCAL, 0x10u) == 16
         || RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_CUSTOM, 0x10u) == 16 )
  {
    return 5;
  }
  else if ( RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_IMS, 0x10u) == 16 )
  {
    return 8;
  }
  else if ( RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_MS_ADMIN, 0x10u) == 16 )
  {
    return 9;
  }
  else
  {
    v2 = RtlCompareMemory(&Source1, &MBB_UUID_CONTEXT_TYPE_MS_APP, 0x10u);
    v1 = 5;
    if ( v2 == 16 )
      return 10;
  }
  return v1;
}

```

## disassembly

```asm
0x14003e5b8  mov     [rsp-8+arg_8], rbx
0x14003e5bd  push    rbp
0x14003e5be  mov     rbp, rsp
0x14003e5c1  sub     rsp, 40h
0x14003e5c5  mov     rax, cs:__security_cookie
0x14003e5cc  xor     rax, rsp
0x14003e5cf  mov     [rbp+var_10], rax
0x14003e5d3  mov     eax, [rcx]
0x14003e5d5  lea     rdx, MBB_UUID_CONTEXT_TYPE_NONE; Source2
0x14003e5dc  bswap   eax
0x14003e5de  mov     [rbp+Source1], eax
0x14003e5e1  mov     ebx, 10h
0x14003e5e6  movzx   eax, word ptr [rcx+4]
0x14003e5ea  mov     r8d, ebx; Length
0x14003e5ed  ror     ax, 8
0x14003e5f1  mov     [rbp+var_1C], ax
0x14003e5f5  movzx   eax, word ptr [rcx+6]
0x14003e5f9  ror     ax, 8
0x14003e5fd  mov     [rbp+var_1A], ax
0x14003e601  mov     rax, [rcx+8]
0x14003e605  lea     rcx, [rbp+Source1]; Source1
0x14003e609  mov     [rbp+var_18], rax
0x14003e60d  call    cs:__imp_RtlCompareMemory
0x14003e614  nop     dword ptr [rax+rax+00h]
0x14003e619  cmp     rax, rbx
0x14003e61c  jnz     short loc_14003E625
0x14003e61e  xor     ecx, ecx
0x14003e620  jmp     loc_14003E7D4
0x14003e625  mov     r8, rbx; Length
0x14003e628  lea     rdx, MBB_UUID_CONTEXT_TYPE_INTERNET; Source2
0x14003e62f  lea     rcx, [rbp+Source1]; Source1
0x14003e633  call    cs:__imp_RtlCompareMemory
0x14003e63a  nop     dword ptr [rax+rax+00h]
0x14003e63f  cmp     rax, rbx
0x14003e642  jnz     short loc_14003E64E
0x14003e644  mov     ecx, 1
0x14003e649  jmp     loc_14003E7D4
0x14003e64e  mov     r8, rbx; Length
0x14003e651  lea     rdx, MBB_UUID_CONTEXT_TYPE_VPN; Source2
0x14003e658  lea     rcx, [rbp+Source1]; Source1
0x14003e65c  call    cs:__imp_RtlCompareMemory
0x14003e663  nop     dword ptr [rax+rax+00h]
0x14003e668  cmp     rax, rbx
0x14003e66b  jnz     short loc_14003E677
0x14003e66d  mov     ecx, 2
0x14003e672  jmp     loc_14003E7D4
0x14003e677  mov     r8, rbx; Length
0x14003e67a  lea     rdx, MBB_UUID_CONTEXT_TYPE_VOICE; Source2
0x14003e681  lea     rcx, [rbp+Source1]; Source1
0x14003e685  call    cs:__imp_RtlCompareMemory
0x14003e68c  nop     dword ptr [rax+rax+00h]
0x14003e691  cmp     rax, rbx
0x14003e694  jnz     short loc_14003E6A0
0x14003e696  mov     ecx, 3
0x14003e69b  jmp     loc_14003E7D4
0x14003e6a0  mov     r8, rbx; Length
0x14003e6a3  lea     rdx, MBB_UUID_CONTEXT_TYPE_VIDEO_SHARE; Source2
0x14003e6aa  lea     rcx, [rbp+Source1]; Source1
0x14003e6ae  call    cs:__imp_RtlCompareMemory
0x14003e6b5  nop     dword ptr [rax+rax+00h]
0x14003e6ba  cmp     rax, rbx
0x14003e6bd  jnz     short loc_14003E6C9
0x14003e6bf  mov     ecx, 4
0x14003e6c4  jmp     loc_14003E7D4
0x14003e6c9  mov     r8, rbx; Length
0x14003e6cc  lea     rdx, MBB_UUID_CONTEXT_TYPE_PURCHASE; Source2
0x14003e6d3  lea     rcx, [rbp+Source1]; Source1
0x14003e6d7  call    cs:__imp_RtlCompareMemory
0x14003e6de  nop     dword ptr [rax+rax+00h]
0x14003e6e3  cmp     rax, rbx
0x14003e6e6  jnz     short loc_14003E6F2
0x14003e6e8  mov     ecx, 6
0x14003e6ed  jmp     loc_14003E7D4
0x14003e6f2  mov     r8, rbx; Length
0x14003e6f5  lea     rdx, MBB_UUID_CONTEXT_TYPE_MMS; Source2
0x14003e6fc  lea     rcx, [rbp+Source1]; Source1
0x14003e700  call    cs:__imp_RtlCompareMemory
0x14003e707  nop     dword ptr [rax+rax+00h]
0x14003e70c  cmp     rax, rbx
0x14003e70f  jnz     short loc_14003E71B
0x14003e711  mov     ecx, 7
0x14003e716  jmp     loc_14003E7D4
0x14003e71b  mov     r8, rbx; Length
0x14003e71e  lea     rdx, MBB_UUID_CONTEXT_TYPE_LOCAL; Source2
0x14003e725  lea     rcx, [rbp+Source1]; Source1
0x14003e729  call    cs:__imp_RtlCompareMemory
0x14003e730  nop     dword ptr [rax+rax+00h]
0x14003e735  cmp     rax, rbx
0x14003e738  jz      short loc_14003E759
0x14003e73a  mov     r8, rbx; Length
0x14003e73d  lea     rdx, MBB_UUID_CONTEXT_TYPE_CUSTOM; Source2
0x14003e744  lea     rcx, [rbp+Source1]; Source1
0x14003e748  call    cs:__imp_RtlCompareMemory
0x14003e74f  nop     dword ptr [rax+rax+00h]
0x14003e754  cmp     rax, rbx
0x14003e757  jnz     short loc_14003E760
0x14003e759  mov     ecx, 5
0x14003e75e  jmp     short loc_14003E7D4
0x14003e760  mov     r8, rbx; Length
0x14003e763  lea     rdx, MBB_UUID_CONTEXT_TYPE_IMS; Source2
0x14003e76a  lea     rcx, [rbp+Source1]; Source1
0x14003e76e  call    cs:__imp_RtlCompareMemory
0x14003e775  nop     dword ptr [rax+rax+00h]
0x14003e77a  cmp     rax, rbx
0x14003e77d  jnz     short loc_14003E786
0x14003e77f  mov     ecx, 8
0x14003e784  jmp     short loc_14003E7D4
0x14003e786  mov     r8, rbx; Length
0x14003e789  lea     rdx, MBB_UUID_CONTEXT_TYPE_MS_ADMIN; Source2
0x14003e790  lea     rcx, [rbp+Source1]; Source1
0x14003e794  call    cs:__imp_RtlCompareMemory
0x14003e79b  nop     dword ptr [rax+rax+00h]
0x14003e7a0  cmp     rax, rbx
0x14003e7a3  jnz     short loc_14003E7AC
0x14003e7a5  mov     ecx, 9
0x14003e7aa  jmp     short loc_14003E7D4
0x14003e7ac  mov     r8, rbx; Length
0x14003e7af  lea     rdx, MBB_UUID_CONTEXT_TYPE_MS_APP; Source2
0x14003e7b6  lea     rcx, [rbp+Source1]; Source1
0x14003e7ba  call    cs:__imp_RtlCompareMemory
0x14003e7c1  nop     dword ptr [rax+rax+00h]
0x14003e7c6  mov     ecx, 5
0x14003e7cb  cmp     rax, rbx
0x14003e7ce  lea     edx, [rcx+5]
0x14003e7d1  cmovz   ecx, edx
0x14003e7d4  mov     eax, ecx
0x14003e7d6  mov     rcx, [rbp+var_10]
0x14003e7da  xor     rcx, rsp; StackCookie
0x14003e7dd  call    __security_check_cookie
0x14003e7e2  mov     rbx, [rsp+40h+arg_8]
0x14003e7e7  add     rsp, 40h
0x14003e7eb  pop     rbp
0x14003e7ec  retn
```
