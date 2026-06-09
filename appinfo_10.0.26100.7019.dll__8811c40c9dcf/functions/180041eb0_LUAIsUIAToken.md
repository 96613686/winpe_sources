# LUAIsUIAToken

- ea: `0x180041eb0`
- end: `0x180041f03`
- name: `LUAIsUIAToken`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180026f80`
- `0x180041d78`

## callees

- `0x180041eb0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180041ede`
- `ntdll!NtQueryInformationToken` at `0x180041ede`

## pseudocode

```c
NTSTATUS __fastcall LUAIsUIAToken(void *a1, _DWORD *a2)
{
  int v2; // ebx
  NTSTATUS result; // eax
  int v5; // [rsp+48h] [rbp+10h] BYREF
  ULONG v6; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  *a2 = 0;
  v5 = 0;
  v6 = 4;
  result = NtQueryInformationToken(a1, TokenUIAccess, &v5, 4u, &v6);
  if ( result >= 0 )
  {
    LOBYTE(v2) = v5 != 0;
    *a2 = v2;
  }
  return result;
}

```

## disassembly

```asm
0x180041eb0  mov     r11, rsp
0x180041eb3  mov     [r11+8], rbx
0x180041eb7  push    rdi
0x180041eb8  sub     rsp, 30h
0x180041ebc  xor     ebx, ebx
0x180041ebe  lea     rax, [r11+18h]
0x180041ec2  mov     rdi, rdx
0x180041ec5  mov     [rdx], ebx
0x180041ec7  lea     r8, [r11+10h]; TokenInformation
0x180041ecb  mov     [rsp+38h+arg_8], ebx
0x180041ecf  mov     [r11-18h], rax
0x180041ed3  lea     r9d, [rbx+4]; TokenInformationLength
0x180041ed7  lea     edx, [rbx+1Ah]; TokenInformationClass
0x180041eda  mov     [r11+18h], r9d
0x180041ede  call    cs:__imp_NtQueryInformationToken
0x180041ee5  nop     dword ptr [rax+rax+00h]
0x180041eea  test    eax, eax
0x180041eec  js      short loc_180041EF7
0x180041eee  cmp     [rsp+38h+arg_8], ebx
0x180041ef2  setnz   bl
0x180041ef5  mov     [rdi], ebx
0x180041ef7  mov     rbx, [rsp+38h+arg_0]
0x180041efc  add     rsp, 30h
0x180041f00  pop     rdi
0x180041f01  retn
```
